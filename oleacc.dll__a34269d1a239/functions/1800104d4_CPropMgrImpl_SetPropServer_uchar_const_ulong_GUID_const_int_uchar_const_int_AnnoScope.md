# CPropMgrImpl::SetPropServer(uchar const *,ulong,_GUID const *,int,uchar const *,int,AnnoScope)

- ea: `0x1800104d4`
- end: `0x1800106fd`
- name: `?SetPropServer@CPropMgrImpl@@QEAAJPEBEKPEBU_GUID@@H0HW4AnnoScope@@@Z`
- size: `553`
- prototype: `__int64 __fastcall(CPropMgrImpl *this, const unsigned __int8 *, signed int, const struct _GUID *, int, unsigned __int8 *, int, enum AnnoScope)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180013f50`

## callees

- `0x1800104d4`
- `0x180010704`
- `0x18001102c`
- `0x180011140`
- `0x180011340`

## import_xrefs

- `ntdll!NtFreeVirtualMemory` at `0x180010684`
- `ntdll!NtFreeVirtualMemory` at `0x180010684`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010529`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010529`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010693`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800106e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010693`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800106e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001066d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001066d`
- `USER32!RemovePropW` at `0x1800106d0`
- `USER32!RemovePropW` at `0x1800106d0`
- `USER32!SetPropW` at `0x18001065a`
- `USER32!SetPropW` at `0x18001065a`

## pseudocode

```c
__int64 __fastcall CPropMgrImpl::SetPropServer(
        CPropMgrImpl *this,
        const unsigned __int8 *a2,
        signed int a3,
        const struct _GUID *a4,
        int a5,
        unsigned __int8 *a6,
        int a7,
        enum AnnoScope a8)
{
  struct _RTL_CRITICAL_SECTION *v12; // rbx
  struct AccInfo *v13; // rdi
  enum AnnoScope v14; // r14d
  int v15; // esi
  unsigned int v16; // ecx
  struct _GUID v17; // xmm0
  GUID *v18; // r9
  unsigned __int64 v19; // rax
  unsigned int i; // ecx
  GUID *v21; // rdx
  unsigned __int64 v22; // rax
  void *v23; // r14
  ULONG_PTR v24; // r15
  unsigned __int8 *v25; // rax
  const WCHAR *v26; // rdx
  unsigned __int8 *v27; // rsi
  HWND v28; // rcx
  HANDLE CurrentProcess; // rax
  unsigned int v30; // edi
  PVOID BaseAddress[2]; // [rsp+30h] [rbp-10h] BYREF
  ULONG_PTR RegionSize; // [rsp+78h] [rbp+38h] BYREF

  CPropMgrImpl::Clean(this);
  if ( !a2 )
    return (unsigned int)-2147467261;
  if ( a3 <= 0 )
    return (unsigned int)-2147024809;
  if ( !a4 )
    return (unsigned int)-2147467261;
  if ( a5 <= 0 )
    return (unsigned int)-2147024809;
  v12 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v13 = CPropMgrImpl::LookupKey(this, a2, a3, 1);
  if ( v13 )
  {
    v14 = a8;
    v15 = 0;
    while ( 2 )
    {
      if ( v15 >= a5 )
      {
        v23 = (void *)*((_QWORD *)v13 + 7);
        v24 = *((_QWORD *)v13 + 8);
        v25 = AccInfo::CalcBlob(v13, (unsigned __int64 *)v13 + 8);
        v26 = (const WCHAR *)*((_QWORD *)v13 + 6);
        v27 = v25;
        v28 = (HWND)*((_QWORD *)v13 + 5);
        if ( v25 )
          SetPropW(v28, v26, v25);
        else
          RemovePropW(v28, v26);
        if ( v23 )
        {
          RegionSize = v24;
          BaseAddress[0] = v23;
          CurrentProcess = GetCurrentProcess();
          NtFreeVirtualMemory(CurrentProcess, BaseAddress, &RegionSize, 0x8000u);
        }
        *((_QWORD *)v13 + 7) = v27;
        v30 = 0;
      }
      else
      {
        v16 = 0;
        v17 = a4[v15];
        *(struct _GUID *)BaseAddress = v17;
        while ( v16 < 0xC )
        {
          v18 = off_18004CAA0[3 * (int)v16];
          v19 = *(_QWORD *)&v18->Data1 - (unsigned __int64)BaseAddress[0];
          if ( *(PVOID *)&v18->Data1 == BaseAddress[0] )
            v19 = *(_QWORD *)v18->Data4 - (unsigned __int64)BaseAddress[1];
          if ( !v19 )
          {
            if ( dword_18004CAB0[6 * v16] )
              v17 = **(&off_18004CAA8 + 3 * (int)v16);
            break;
          }
          ++v16;
        }
        *(struct _GUID *)BaseAddress = v17;
        for ( i = 0; i < 0xC9; ++i )
        {
          v21 = (&off_18004CD80)[2 * (int)i];
          v22 = *(_QWORD *)&v21->Data1 - (unsigned __int64)BaseAddress[0];
          if ( *(PVOID *)&v21->Data1 == BaseAddress[0] )
            v22 = *(_QWORD *)v21->Data4 - (unsigned __int64)BaseAddress[1];
          if ( !v22 )
          {
            if ( word_18004CD88[8 * i] == 1 )
            {
              v30 = -2147024809;
              goto LABEL_30;
            }
            break;
          }
        }
        *(struct _GUID *)BaseAddress = v17;
        if ( AccInfo::SetPropServer(v13, (struct _GUID *)BaseAddress, a6, a7, v14) )
        {
          ++v15;
          continue;
        }
        v30 = -2147467259;
      }
      break;
    }
LABEL_30:
    LeaveCriticalSection(v12);
    return v30;
  }
  LeaveCriticalSection(v12);
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800104d4  mov     [rsp-28h+arg_0], rbx
0x1800104d9  mov     [rsp-28h+arg_10], rsi
0x1800104de  push    rbp
0x1800104df  push    rdi
0x1800104e0  push    r13
0x1800104e2  push    r14
0x1800104e4  push    r15
0x1800104e6  mov     rbp, rsp
0x1800104e9  sub     rsp, 40h
0x1800104ed  mov     r15, r9
0x1800104f0  mov     esi, r8d
0x1800104f3  mov     r14, rdx
0x1800104f6  mov     rdi, rcx
0x1800104f9  call    ?Clean@CPropMgrImpl@@QEAAXXZ; CPropMgrImpl::Clean(void)
0x1800104fe  test    r14, r14
0x180010501  jz      loc_1800106D8
0x180010507  test    esi, esi
0x180010509  jle     loc_1800106DF
0x18001050f  test    r15, r15
0x180010512  jz      loc_1800106D8
0x180010518  cmp     [rbp+arg_20], 0
0x18001051c  jle     loc_1800106DF
0x180010522  lea     rbx, [rdi+20h]
0x180010526  mov     rcx, rbx; lpCriticalSection
0x180010529  call    cs:__imp_EnterCriticalSection
0x18001052f  mov     r13d, 1
0x180010535  mov     r8d, esi; unsigned int
0x180010538  mov     r9d, r13d; int
0x18001053b  mov     rdx, r14; unsigned __int8 *
0x18001053e  mov     rcx, rdi; this
0x180010541  call    ?LookupKey@CPropMgrImpl@@QEAAPEAVAccInfo@@PEBEKH@Z; CPropMgrImpl::LookupKey(uchar const *,ulong,int)
0x180010546  mov     rdi, rax
0x180010549  test    rax, rax
0x18001054c  jz      loc_1800106E6
0x180010552  mov     r14d, [rbp+arg_38]
0x180010556  xor     esi, esi
0x180010558  lea     r10, __ImageBase
0x18001055f  cmp     esi, [rbp+arg_20]
0x180010562  jge     loc_180010634
0x180010568  movsxd  rdx, esi
0x18001056b  add     rdx, rdx
0x18001056e  xor     ecx, ecx
0x180010570  movups  xmm0, xmmword ptr [r15+rdx*8]
0x180010575  movdqu  xmmword ptr [rbp+BaseAddress], xmm0
0x18001057a  cmp     ecx, 0Ch
0x18001057d  jnb     short loc_1800105BD
0x18001057f  movsxd  rax, ecx
0x180010582  lea     r8, [rax+rax*2]
0x180010586  mov     r9, ds:rva off_18004CAA0[r10+r8*8]
0x18001058e  mov     rax, [r9]
0x180010591  sub     rax, [rbp+BaseAddress]
0x180010595  jnz     short loc_18001059F
0x180010597  mov     rax, [r9+8]
0x18001059b  sub     rax, [rbp+BaseAddress+8]
0x18001059f  test    rax, rax
0x1800105a2  jnz     loc_18001062C
0x1800105a8  cmp     ds:rva dword_18004CAB0[r10+r8*8], eax
0x1800105b0  jz      short loc_1800105BD
0x1800105b2  mov     rax, ds:rva off_18004CAA8[r10+r8*8]
0x1800105ba  movups  xmm0, xmmword ptr [rax]
0x1800105bd  movdqa  xmmword ptr [rbp+BaseAddress], xmm0
0x1800105c2  xor     ecx, ecx
0x1800105c4  cmp     ecx, 0C9h
0x1800105ca  jnb     short loc_1800105F9
0x1800105cc  movsxd  rax, ecx
0x1800105cf  add     rax, rax
0x1800105d2  mov     rdx, ds:rva off_18004CD80[r10+rax*8]
0x1800105da  mov     rax, [rdx]
0x1800105dd  sub     rax, [rbp+BaseAddress]
0x1800105e1  jnz     short loc_1800105EB
0x1800105e3  mov     rax, [rdx+8]
0x1800105e7  sub     rax, [rbp+BaseAddress+8]
0x1800105eb  test    rax, rax
0x1800105ee  jnz     short loc_180010627
0x1800105f0  cmp     ecx, 0FFFFFFFFh
0x1800105f3  jnz     loc_1800106B4
0x1800105f9  mov     r9d, [rbp+arg_30]; int
0x1800105fd  lea     rdx, [rbp+BaseAddress]; struct _GUID
0x180010601  mov     r8, [rbp+arg_28]; unsigned __int8 *
0x180010605  mov     rcx, rdi; this
0x180010608  movdqa  xmmword ptr [rbp+BaseAddress], xmm0
0x18001060d  mov     [rsp+40h+var_20], r14d; enum AnnoScope
0x180010612  call    ?SetPropServer@AccInfo@@QEAAHU_GUID@@PEBEHW4AnnoScope@@@Z; AccInfo::SetPropServer(_GUID,uchar const *,int,AnnoScope)
0x180010617  test    eax, eax
0x180010619  jz      loc_1800106F6
0x18001061f  add     esi, r13d
0x180010622  jmp     loc_180010558
0x180010627  add     ecx, r13d
0x18001062a  jmp     short loc_1800105C4
0x18001062c  add     ecx, r13d
0x18001062f  jmp     loc_18001057A
0x180010634  mov     r14, [rdi+38h]
0x180010638  lea     rdx, [rdi+40h]; unsigned __int64 *
0x18001063c  mov     r15, [rdx]
0x18001063f  mov     rcx, rdi; this
0x180010642  call    ?CalcBlob@AccInfo@@AEAAPEAEPEA_K@Z; AccInfo::CalcBlob(unsigned __int64 *)
0x180010647  mov     rdx, [rdi+30h]; lpString
0x18001064b  mov     rsi, rax
0x18001064e  mov     rcx, [rdi+28h]; hWnd
0x180010652  test    rax, rax
0x180010655  jz      short loc_1800106D0
0x180010657  mov     r8, rax; hData
0x18001065a  call    cs:__imp_SetPropW
0x180010660  test    r14, r14
0x180010663  jz      short loc_18001068A
0x180010665  mov     [rbp+RegionSize], r15
0x180010669  mov     [rbp+BaseAddress], r14
0x18001066d  call    cs:__imp_GetCurrentProcess
0x180010673  mov     r9d, 8000h; FreeType
0x180010679  lea     r8, [rbp+RegionSize]; RegionSize
0x18001067d  mov     rcx, rax; ProcessHandle
0x180010680  lea     rdx, [rbp+BaseAddress]; BaseAddress
0x180010684  call    cs:__imp_NtFreeVirtualMemory
0x18001068a  mov     [rdi+38h], rsi
0x18001068e  xor     edi, edi
0x180010690  mov     rcx, rbx; lpCriticalSection
0x180010693  call    cs:__imp_LeaveCriticalSection
0x180010699  mov     eax, edi
0x18001069b  lea     r11, [rsp+40h+var_s0]
0x1800106a0  mov     rbx, [r11+30h]
0x1800106a4  mov     rsi, [r11+40h]
0x1800106a8  mov     rsp, r11
0x1800106ab  pop     r15
0x1800106ad  pop     r14
0x1800106af  pop     r13
0x1800106b1  pop     rdi
0x1800106b2  pop     rbp
0x1800106b3  retn
0x1800106b4  movsxd  rax, ecx
0x1800106b7  add     rax, rax
0x1800106ba  cmp     r13w, ds:rva word_18004CD88[r10+rax*8]
0x1800106c3  jnz     loc_1800105F9
0x1800106c9  mov     edi, 80070057h
0x1800106ce  jmp     short loc_180010690
0x1800106d0  call    cs:__imp_RemovePropW
0x1800106d6  jmp     short loc_180010660
0x1800106d8  mov     edi, 80004003h
0x1800106dd  jmp     short loc_180010699
0x1800106df  mov     edi, 80070057h
0x1800106e4  jmp     short loc_180010699
0x1800106e6  mov     rcx, rbx; lpCriticalSection
0x1800106e9  call    cs:__imp_LeaveCriticalSection
0x1800106ef  mov     eax, 80070057h
0x1800106f4  jmp     short loc_18001069B
0x1800106f6  mov     edi, 80004005h
0x1800106fb  jmp     short loc_180010690
```
