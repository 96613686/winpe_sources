# CPropMgrImpl::SetPropValue(uchar const *,ulong,_GUID,tagVARIANT *)

- ea: `0x180010d94`
- end: `0x180011026`
- name: `?SetPropValue@CPropMgrImpl@@QEAAJPEBEKU_GUID@@PEAUtagVARIANT@@@Z`
- size: `658`
- prototype: `__int64 __fastcall(CPropMgrImpl *this, const unsigned __int8 *, signed int, struct _GUID *, struct tagVARIANT *)`
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180010390`
- `0x180010be0`
- `0x180023c30`
- `0x180023dc0`
- `0x180023ec0`

## callees

- `0x180010d94`
- `0x18001102c`
- `0x180011140`
- `0x180011230`
- `0x180011340`

## import_xrefs

- `ntdll!NtFreeVirtualMemory` at `0x180010f5b`
- `ntdll!NtFreeVirtualMemory` at `0x180010f5b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010de3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010de3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010f6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001100c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010f6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001100c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010f3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010f3f`
- `USER32!RemovePropW` at `0x180010fe0`
- `USER32!RemovePropW` at `0x180010fe0`
- `USER32!SetPropW` at `0x180010f27`
- `USER32!SetPropW` at `0x180010f27`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPropMgrImpl::SetPropValue(
        CPropMgrImpl *this,
        const unsigned __int8 *a2,
        signed int a3,
        struct _GUID *a4,
        struct tagVARIANT *a5)
{
  struct tagVARIANT *v9; // rbp
  struct _RTL_CRITICAL_SECTION *v10; // rbx
  struct AccInfo *v11; // rdi
  struct _GUID v12; // xmm0
  unsigned int i; // ecx
  GUID *v14; // r8
  unsigned __int64 v15; // rax
  unsigned int j; // ecx
  GUID *v17; // rdx
  __int64 v18; // rax
  void *v19; // rbp
  ULONG_PTR v20; // r14
  unsigned __int8 *v21; // rax
  const WCHAR *v22; // rdx
  unsigned __int8 *v23; // rsi
  HWND v24; // rcx
  HANDLE CurrentProcess; // rax
  unsigned int v26; // edi
  PVOID BaseAddress[11]; // [rsp+20h] [rbp-58h] BYREF
  ULONG_PTR RegionSize; // [rsp+88h] [rbp+10h] BYREF

  CPropMgrImpl::Clean(this);
  if ( !a2 )
    return (unsigned int)-2147467261;
  if ( a3 <= 0 )
    return (unsigned int)-2147024809;
  v9 = a5;
  if ( !a5 )
    return 2147500035LL;
  v10 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v11 = CPropMgrImpl::LookupKey(this, a2, a3, 1);
  if ( v11 )
  {
    v12 = *a4;
    *(struct _GUID *)BaseAddress = *a4;
    for ( i = 0; i < 0xC; ++i )
    {
      v14 = off_18004CAA0[3 * (int)i];
      v15 = *(_QWORD *)&v14->Data1 - (unsigned __int64)BaseAddress[0];
      if ( *(PVOID *)&v14->Data1 == BaseAddress[0] )
        v15 = *(_QWORD *)v14->Data4 - (unsigned __int64)BaseAddress[1];
      if ( !v15 )
      {
        if ( dword_18004CAB0[6 * i] )
        {
          _mm_lfence();
          v12 = **(&off_18004CAA8 + 3 * (int)i);
        }
        break;
      }
    }
    *a4 = v12;
    for ( j = 0; j < 0xC9; ++j )
    {
      v17 = (&off_18004CD80)[2 * (int)j];
      v18 = *(_QWORD *)&v17->Data1 - *(_QWORD *)&a4->Data1;
      if ( *(_QWORD *)&v17->Data1 == *(_QWORD *)&a4->Data1 )
        v18 = *(_QWORD *)v17->Data4 - *(_QWORD *)a4->Data4;
      if ( !v18 )
      {
        if ( word_18004CD88[8 * j] != 1 && v9->vt == word_18004CD88[8 * j] && dword_18004CD8C[4 * j] )
          goto LABEL_21;
LABEL_37:
        v26 = -2147024809;
        goto LABEL_27;
      }
    }
    if ( v9->vt != 31 && v9->vt && v9->vt != 3 && v9->vt != 5 && v9->vt != 8 && v9->vt != 11 && v9->vt != 27 )
      goto LABEL_37;
LABEL_21:
    *(struct _GUID *)BaseAddress = v12;
    if ( AccInfo::SetPropValue(v11, (struct _GUID *)BaseAddress, v9) )
    {
      v19 = (void *)*((_QWORD *)v11 + 7);
      v20 = *((_QWORD *)v11 + 8);
      v21 = AccInfo::CalcBlob(v11, (unsigned __int64 *)v11 + 8);
      v22 = (const WCHAR *)*((_QWORD *)v11 + 6);
      v23 = v21;
      v24 = (HWND)*((_QWORD *)v11 + 5);
      if ( v21 )
        SetPropW(v24, v22, v21);
      else
        RemovePropW(v24, v22);
      if ( v19 )
      {
        RegionSize = v20;
        BaseAddress[0] = v19;
        CurrentProcess = GetCurrentProcess();
        NtFreeVirtualMemory(CurrentProcess, BaseAddress, &RegionSize, 0x8000u);
      }
      *((_QWORD *)v11 + 7) = v23;
      v26 = 0;
    }
    else
    {
      v26 = -2147467259;
    }
LABEL_27:
    LeaveCriticalSection(v10);
    return v26;
  }
  LeaveCriticalSection(v10);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180010d94  push    rbx
0x180010d96  push    rbp
0x180010d97  push    rsi
0x180010d98  push    rdi
0x180010d99  push    r12
0x180010d9b  push    r13
0x180010d9d  push    r14
0x180010d9f  push    r15
0x180010da1  sub     rsp, 38h
0x180010da5  mov     rsi, r9
0x180010da8  mov     r14d, r8d
0x180010dab  mov     r15, rdx
0x180010dae  mov     rdi, rcx
0x180010db1  call    ?Clean@CPropMgrImpl@@QEAAXXZ; CPropMgrImpl::Clean(void)
0x180010db6  xor     r12d, r12d
0x180010db9  test    r15, r15
0x180010dbc  jz      loc_180010FEB
0x180010dc2  test    r14d, r14d
0x180010dc5  jle     loc_180010FF5
0x180010dcb  mov     rbp, [rsp+78h+arg_20]
0x180010dd3  test    rbp, rbp
0x180010dd6  jz      loc_180010FFF
0x180010ddc  lea     rbx, [rdi+20h]
0x180010de0  mov     rcx, rbx; lpCriticalSection
0x180010de3  call    cs:__imp_EnterCriticalSection
0x180010de9  lea     r13d, [r12+1]
0x180010dee  mov     r8d, r14d; unsigned int
0x180010df1  mov     r9d, r13d; int
0x180010df4  mov     rdx, r15; unsigned __int8 *
0x180010df7  mov     rcx, rdi; this
0x180010dfa  call    ?LookupKey@CPropMgrImpl@@QEAAPEAVAccInfo@@PEBEKH@Z; CPropMgrImpl::LookupKey(uchar const *,ulong,int)
0x180010dff  mov     rdi, rax
0x180010e02  test    rax, rax
0x180010e05  jz      loc_180011009
0x180010e0b  movaps  xmm0, xmmword ptr [rsi]
0x180010e0e  lea     r9, __ImageBase
0x180010e15  movdqa  xmmword ptr [rsp+78h+BaseAddress], xmm0
0x180010e1b  mov     ecx, r12d
0x180010e1e  cmp     ecx, 0Ch
0x180010e21  jnb     short loc_180010E66
0x180010e23  movsxd  rax, ecx
0x180010e26  lea     rdx, [rax+rax*2]
0x180010e2a  mov     r8, ds:rva off_18004CAA0[r9+rdx*8]
0x180010e32  mov     rax, [r8]
0x180010e35  sub     rax, [rsp+78h+BaseAddress]
0x180010e3a  jnz     short loc_180010E45
0x180010e3c  mov     rax, [r8+8]
0x180010e40  sub     rax, [rsp+78h+BaseAddress+8]
0x180010e45  test    rax, rax
0x180010e48  jnz     loc_180010F84
0x180010e4e  cmp     ds:rva dword_18004CAB0[r9+rdx*8], r12d
0x180010e56  jz      short loc_180010E66
0x180010e58  lfence
0x180010e5b  mov     rax, ds:rva off_18004CAA8[r9+rdx*8]
0x180010e63  movups  xmm0, xmmword ptr [rax]
0x180010e66  movdqu  xmmword ptr [rsi], xmm0
0x180010e6a  mov     ecx, r12d
0x180010e6d  cmp     ecx, 0C9h
0x180010e73  jnb     loc_180010F8C
0x180010e79  movsxd  rax, ecx
0x180010e7c  add     rax, rax
0x180010e7f  mov     rdx, ds:rva off_18004CD80[r9+rax*8]
0x180010e87  mov     rax, [rdx]
0x180010e8a  sub     rax, [rsi]
0x180010e8d  jnz     short loc_180010E97
0x180010e8f  mov     rax, [rdx+8]
0x180010e93  sub     rax, [rsi+8]
0x180010e97  test    rax, rax
0x180010e9a  jz      short loc_180010EA1
0x180010e9c  add     ecx, r13d
0x180010e9f  jmp     short loc_180010E6D
0x180010ea1  cmp     ecx, 0FFFFFFFFh
0x180010ea4  jz      loc_180010F8C
0x180010eaa  movsxd  rdx, ecx
0x180010ead  add     rdx, rdx
0x180010eb0  movsx   eax, ds:rva word_18004CD88[r9+rdx*8]
0x180010eb9  cmp     r13w, ax
0x180010ebd  jz      loc_180010FD9
0x180010ec3  mov     ecx, eax
0x180010ec5  movzx   eax, word ptr [rbp+0]
0x180010ec9  cmp     eax, ecx
0x180010ecb  jnz     loc_180010FD9
0x180010ed1  cmp     ds:rva dword_18004CD8C[r9+rdx*8], r12d
0x180010ed9  jz      loc_180010FD9
0x180010edf  mov     r8, rbp; struct tagVARIANT *
0x180010ee2  movdqa  xmmword ptr [rsp+78h+BaseAddress], xmm0
0x180010ee8  lea     rdx, [rsp+78h+BaseAddress]; struct _GUID
0x180010eed  mov     rcx, rdi; this
0x180010ef0  call    ?SetPropValue@AccInfo@@QEAAHU_GUID@@PEAUtagVARIANT@@@Z; AccInfo::SetPropValue(_GUID,tagVARIANT *)
0x180010ef5  test    eax, eax
0x180010ef7  jz      loc_18001101C
0x180010efd  mov     rbp, [rdi+38h]
0x180010f01  lea     rdx, [rdi+40h]; unsigned __int64 *
0x180010f05  mov     r14, [rdx]
0x180010f08  mov     rcx, rdi; this
0x180010f0b  call    ?CalcBlob@AccInfo@@AEAAPEAEPEA_K@Z; AccInfo::CalcBlob(unsigned __int64 *)
0x180010f10  mov     rdx, [rdi+30h]; lpString
0x180010f14  mov     rsi, rax
0x180010f17  mov     rcx, [rdi+28h]; hWnd
0x180010f1b  test    rax, rax
0x180010f1e  jz      loc_180010FE0
0x180010f24  mov     r8, rax; hData
0x180010f27  call    cs:__imp_SetPropW
0x180010f2d  test    rbp, rbp
0x180010f30  jz      short loc_180010F61
0x180010f32  mov     [rsp+78h+RegionSize], r14
0x180010f3a  mov     [rsp+78h+BaseAddress], rbp
0x180010f3f  call    cs:__imp_GetCurrentProcess
0x180010f45  mov     r9d, 8000h; FreeType
0x180010f4b  lea     r8, [rsp+78h+RegionSize]; RegionSize
0x180010f53  mov     rcx, rax; ProcessHandle
0x180010f56  lea     rdx, [rsp+78h+BaseAddress]; BaseAddress
0x180010f5b  call    cs:__imp_NtFreeVirtualMemory
0x180010f61  mov     [rdi+38h], rsi
0x180010f65  mov     edi, r12d
0x180010f68  mov     rcx, rbx; lpCriticalSection
0x180010f6b  call    cs:__imp_LeaveCriticalSection
0x180010f71  mov     eax, edi
0x180010f73  add     rsp, 38h
0x180010f77  pop     r15
0x180010f79  pop     r14
0x180010f7b  pop     r13
0x180010f7d  pop     r12
0x180010f7f  pop     rdi
0x180010f80  pop     rsi
0x180010f81  pop     rbp
0x180010f82  pop     rbx
0x180010f83  retn
0x180010f84  add     ecx, r13d
0x180010f87  jmp     loc_180010E1E
0x180010f8c  cmp     word ptr [rbp+0], 1Fh
0x180010f91  jz      loc_180010EDF
0x180010f97  cmp     [rbp+0], r12w
0x180010f9c  jz      loc_180010EDF
0x180010fa2  cmp     word ptr [rbp+0], 3
0x180010fa7  jz      loc_180010EDF
0x180010fad  cmp     word ptr [rbp+0], 5
0x180010fb2  jz      loc_180010EDF
0x180010fb8  cmp     word ptr [rbp+0], 8
0x180010fbd  jz      loc_180010EDF
0x180010fc3  cmp     word ptr [rbp+0], 0Bh
0x180010fc8  jz      loc_180010EDF
0x180010fce  cmp     word ptr [rbp+0], 1Bh
0x180010fd3  jz      loc_180010EDF
0x180010fd9  mov     edi, 80070057h
0x180010fde  jmp     short loc_180010F68
0x180010fe0  call    cs:__imp_RemovePropW
0x180010fe6  jmp     loc_180010F2D
0x180010feb  mov     edi, 80004003h
0x180010ff0  jmp     loc_180010F71
0x180010ff5  mov     edi, 80070057h
0x180010ffa  jmp     loc_180010F71
0x180010fff  mov     eax, 80004003h
0x180011004  jmp     loc_180010F73
0x180011009  mov     rcx, rbx; lpCriticalSection
0x18001100c  call    cs:__imp_LeaveCriticalSection
0x180011012  mov     eax, 80070057h
0x180011017  jmp     loc_180010F73
0x18001101c  mov     edi, 80004005h
0x180011021  jmp     loc_180010F68
```
