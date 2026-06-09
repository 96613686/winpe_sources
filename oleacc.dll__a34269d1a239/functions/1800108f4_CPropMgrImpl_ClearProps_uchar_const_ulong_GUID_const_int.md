# CPropMgrImpl::ClearProps(uchar const *,ulong,_GUID const *,int)

- ea: `0x1800108f4`
- end: `0x180010a25`
- name: `?ClearProps@CPropMgrImpl@@QEAAJPEBEKPEBU_GUID@@H@Z`
- size: `305`
- prototype: `__int64 __usercall@<rax>(CPropMgrImpl *__hidden this@<rcx>, const unsigned __int8 *@<rdx>, unsigned int@<r8d>, const struct _GUID *@<r9>, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180010830`

## callees

- `0x1800108f4`
- `0x180010a84`
- `0x18001102c`
- `0x180011140`
- `0x180011340`
- `0x180011ee0`

## import_xrefs

- `ntdll!NtFreeVirtualMemory` at `0x1800109f1`
- `ntdll!NtFreeVirtualMemory` at `0x1800109f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010946`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010946`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010968`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010a10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010968`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010a10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800109d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800109d8`
- `USER32!RemovePropW` at `0x1800109c3`
- `USER32!RemovePropW` at `0x1800109c3`
- `USER32!SetPropW` at `0x1800109bb`
- `USER32!SetPropW` at `0x1800109bb`

## pseudocode

```c
__int64 __fastcall CPropMgrImpl::ClearProps(
        CPropMgrImpl *this,
        const unsigned __int8 *a2,
        signed int a3,
        const struct _GUID *a4,
        int a5)
{
  int v10; // ebp
  struct AccInfo *v11; // rdi
  int v12; // esi
  void *v13; // rbp
  ULONG_PTR v14; // r14
  unsigned __int8 *v15; // rax
  const WCHAR *v16; // rdx
  unsigned __int8 *v17; // rsi
  HWND v18; // rcx
  HANDLE CurrentProcess; // rax
  bool v20; // zf
  PVOID BaseAddress[9]; // [rsp+20h] [rbp-48h] BYREF
  ULONG_PTR RegionSize; // [rsp+78h] [rbp+10h] BYREF

  CPropMgrImpl::Clean(this);
  if ( !a2 )
    return 2147500035LL;
  if ( a3 <= 0 )
    return 2147942487LL;
  if ( !a4 )
    return 2147500035LL;
  v10 = a5;
  if ( a5 <= 0 )
    return 2147942487LL;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v11 = CPropMgrImpl::LookupKey(this, a2, a3, 0);
  if ( !v11 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    return 2147942487LL;
  }
  v12 = 0;
  do
  {
    *(struct _GUID *)BaseAddress = a4[v12];
    AccInfo::ClearProp(v11, (struct _GUID *)BaseAddress);
    ++v12;
  }
  while ( v12 < v10 );
  v13 = (void *)*((_QWORD *)v11 + 7);
  v14 = *((_QWORD *)v11 + 8);
  v15 = AccInfo::CalcBlob(v11, (unsigned __int64 *)v11 + 8);
  v16 = (const WCHAR *)*((_QWORD *)v11 + 6);
  v17 = v15;
  v18 = (HWND)*((_QWORD *)v11 + 5);
  if ( v15 )
    SetPropW(v18, v16, v15);
  else
    RemovePropW(v18, v16);
  if ( v13 )
  {
    RegionSize = v14;
    BaseAddress[0] = v13;
    CurrentProcess = GetCurrentProcess();
    NtFreeVirtualMemory(CurrentProcess, BaseAddress, &RegionSize, 0x8000u);
  }
  v20 = *((_QWORD *)v11 + 4) == 0;
  *((_QWORD *)v11 + 7) = v17;
  if ( v20 )
    CPropMgrImpl::RemoveEntry(this, v11);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  return 0;
}

```

## disassembly

```asm
0x1800108f4  push    rbx
0x1800108f6  push    rbp
0x1800108f7  push    rsi
0x1800108f8  push    rdi
0x1800108f9  push    r14
0x1800108fb  push    r15
0x1800108fd  sub     rsp, 38h
0x180010901  mov     r14, r9
0x180010904  mov     edi, r8d
0x180010907  mov     rsi, rdx
0x18001090a  mov     r15, rcx
0x18001090d  call    ?Clean@CPropMgrImpl@@QEAAXXZ; CPropMgrImpl::Clean(void)
0x180010912  test    rsi, rsi
0x180010915  jnz     short loc_180010921
0x180010917  mov     eax, 80004003h
0x18001091c  jmp     loc_180010A18
0x180010921  test    edi, edi
0x180010923  jg      short loc_18001092F
0x180010925  mov     eax, 80070057h
0x18001092a  jmp     loc_180010A18
0x18001092f  test    r14, r14
0x180010932  jz      short loc_180010917
0x180010934  mov     ebp, [rsp+68h+arg_20]
0x18001093b  test    ebp, ebp
0x18001093d  jle     short loc_180010925
0x18001093f  lea     rbx, [r15+20h]
0x180010943  mov     rcx, rbx; lpCriticalSection
0x180010946  call    cs:__imp_EnterCriticalSection
0x18001094c  xor     r9d, r9d; int
0x18001094f  mov     r8d, edi; unsigned int
0x180010952  mov     rdx, rsi; unsigned __int8 *
0x180010955  mov     rcx, r15; this
0x180010958  call    ?LookupKey@CPropMgrImpl@@QEAAPEAVAccInfo@@PEBEKH@Z; CPropMgrImpl::LookupKey(uchar const *,ulong,int)
0x18001095d  mov     rdi, rax
0x180010960  test    rax, rax
0x180010963  jnz     short loc_180010970
0x180010965  mov     rcx, rbx; lpCriticalSection
0x180010968  call    cs:__imp_LeaveCriticalSection
0x18001096e  jmp     short loc_180010925
0x180010970  xor     esi, esi
0x180010972  mov     eax, esi
0x180010974  lea     rdx, [rsp+68h+BaseAddress]; struct _GUID
0x180010979  add     rax, rax
0x18001097c  mov     rcx, rdi; this
0x18001097f  movups  xmm0, xmmword ptr [r14+rax*8]
0x180010984  movdqu  xmmword ptr [rsp+68h+BaseAddress], xmm0
0x18001098a  call    ?ClearProp@AccInfo@@QEAAXU_GUID@@@Z; AccInfo::ClearProp(_GUID)
0x18001098f  inc     esi
0x180010991  cmp     esi, ebp
0x180010993  jl      short loc_180010972
0x180010995  mov     rbp, [rdi+38h]
0x180010999  lea     rdx, [rdi+40h]; unsigned __int64 *
0x18001099d  mov     r14, [rdx]
0x1800109a0  mov     rcx, rdi; this
0x1800109a3  call    ?CalcBlob@AccInfo@@AEAAPEAEPEA_K@Z; AccInfo::CalcBlob(unsigned __int64 *)
0x1800109a8  mov     rdx, [rdi+30h]; lpString
0x1800109ac  mov     rsi, rax
0x1800109af  mov     rcx, [rdi+28h]; hWnd
0x1800109b3  test    rax, rax
0x1800109b6  jz      short loc_1800109C3
0x1800109b8  mov     r8, rax; hData
0x1800109bb  call    cs:__imp_SetPropW
0x1800109c1  jmp     short loc_1800109C9
0x1800109c3  call    cs:__imp_RemovePropW
0x1800109c9  test    rbp, rbp
0x1800109cc  jz      short loc_1800109F7
0x1800109ce  mov     [rsp+68h+RegionSize], r14
0x1800109d3  mov     [rsp+68h+BaseAddress], rbp
0x1800109d8  call    cs:__imp_GetCurrentProcess
0x1800109de  mov     r9d, 8000h; FreeType
0x1800109e4  lea     r8, [rsp+68h+RegionSize]; RegionSize
0x1800109e9  mov     rcx, rax; ProcessHandle
0x1800109ec  lea     rdx, [rsp+68h+BaseAddress]; BaseAddress
0x1800109f1  call    cs:__imp_NtFreeVirtualMemory
0x1800109f7  cmp     qword ptr [rdi+20h], 0
0x1800109fc  mov     [rdi+38h], rsi
0x180010a00  jnz     short loc_180010A0D
0x180010a02  mov     rdx, rdi; struct AccInfo *
0x180010a05  mov     rcx, r15; this
0x180010a08  call    ?RemoveEntry@CPropMgrImpl@@QEAAXPEAVAccInfo@@@Z; CPropMgrImpl::RemoveEntry(AccInfo *)
0x180010a0d  mov     rcx, rbx; lpCriticalSection
0x180010a10  call    cs:__imp_LeaveCriticalSection
0x180010a16  xor     eax, eax
0x180010a18  add     rsp, 38h
0x180010a1c  pop     r15
0x180010a1e  pop     r14
0x180010a20  pop     rdi
0x180010a21  pop     rsi
0x180010a22  pop     rbp
0x180010a23  pop     rbx
0x180010a24  retn
```
