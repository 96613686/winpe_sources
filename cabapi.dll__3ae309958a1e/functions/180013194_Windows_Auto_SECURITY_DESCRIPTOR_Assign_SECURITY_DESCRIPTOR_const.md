# Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(_SECURITY_DESCRIPTOR const *)

- ea: `0x180013194`
- end: `0x18001338d`
- name: `?Assign@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAJPEBU_SECURITY_DESCRIPTOR@@@Z`
- size: `505`
- prototype: `__int64 __fastcall(_QWORD *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800135f4`

## callees

- `0x180001540`
- `0x18000be58`
- `0x180012fd8`
- `0x180013194`
- `0x180013df8`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x18001323a`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18001323a`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x1800131d9`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x1800131d9`
- `ntdll!RtlMakeSelfRelativeSD` at `0x1800132e5`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18001335d`
- `ntdll!RtlMakeSelfRelativeSD` at `0x1800132e5`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18001335d`
- `ntdll!RtlAllocateHeap` at `0x180013254`
- `ntdll!RtlAllocateHeap` at `0x18001332a`
- `ntdll!RtlAllocateHeap` at `0x180013254`
- `ntdll!RtlAllocateHeap` at `0x18001332a`

## string_xrefs

- `0x1800131f4`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x180013271`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1800131ed`: `RtlGetControlSecurityDescriptor(pTempSd, &Control, &Revision)`
- `0x18001320a`: `Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign`
- `0x180013287`: `Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign`
- `0x18001326a`: `m_pSD = RtlAllocateHeap((((PPEB)__readgsqword(((LONG)__builtin_offsetof(TEB, ProcessEnvironmentBlock))))->ProcessHeap), 0, Size)`
- `0x180013375`: `RtlMakeSelfRelativeSD( pTempSd, m_pSD, &cbSecurityDescriptor)`
- `0x180013343`: `m_pSD = ::RtlAllocateHeap((((PPEB)__readgsqword(((LONG)__builtin_offsetof(TEB, ProcessEnvironmentBlock))))->ProcessHeap), 0, cbSecurityDescriptor)`

## pseudocode

```c
__int64 __fastcall Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(_QWORD *a1, void *a2)
{
  NTSTATUS ControlSecurityDescriptor; // ebx
  const char *v5; // rax
  SIZE_T v7; // rbx
  PVOID v8; // rax
  const char *v9; // rax
  NTSTATUS SelfRelativeSD; // eax
  int v11; // ecx
  PVOID Heap; // rax
  const char *v13; // [rsp+20h] [rbp-40h] BYREF
  const char *v14; // [rsp+28h] [rbp-38h]
  __int64 v15; // [rsp+30h] [rbp-30h]
  const char *v16; // [rsp+38h] [rbp-28h]
  WORD Control[2]; // [rsp+40h] [rbp-20h] BYREF
  ULONG BufferLength; // [rsp+44h] [rbp-1Ch] BYREF
  ULONG Revision; // [rsp+48h] [rbp-18h] BYREF

  if ( *a1 )
    INTERNAL_ERROR_ACTION((int)a1);
  Revision = 0;
  Control[0] = 0;
  ControlSecurityDescriptor = RtlGetControlSecurityDescriptor(a2, Control, &Revision);
  if ( ControlSecurityDescriptor < 0 )
  {
    v15 = 821;
    v5 = "RtlGetControlSecurityDescriptor(pTempSd, &Control, &Revision)";
LABEL_4:
    v16 = v5;
    v13 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v14 = "Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign";
    RtlReportErrorOrigination(&v13, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)ControlSecurityDescriptor);
    return (unsigned int)ControlSecurityDescriptor;
  }
  if ( (Control[0] & 0x8000u) == 0 )
  {
    BufferLength = 0;
    SelfRelativeSD = RtlMakeSelfRelativeSD(a2, 0, &BufferLength);
    ControlSecurityDescriptor = SelfRelativeSD;
    if ( SelfRelativeSD != -2147483643 && SelfRelativeSD != -1073741789 )
    {
      if ( SelfRelativeSD >= 0 )
        INTERNAL_ERROR_ACTION(v11);
      v15 = 841;
      v5 = "((TmpStatus == ((NTSTATUS)0x80000005L)) || (TmpStatus == ((NTSTATUS)0xC0000023L)))";
      goto LABEL_4;
    }
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, BufferLength);
    *a1 = Heap;
    if ( !Heap )
    {
      v15 = 843;
      v9 = "m_pSD = ::RtlAllocateHeap((((PPEB)__readgsqword(((LONG)__builtin_offsetof(TEB, ProcessEnvironmentBlock))))->P"
           "rocessHeap), 0, cbSecurityDescriptor)";
      goto LABEL_8;
    }
    a1[1] = BufferLength;
    ControlSecurityDescriptor = RtlMakeSelfRelativeSD(a2, Heap, &BufferLength);
    if ( ControlSecurityDescriptor < 0 )
    {
      v15 = 850;
      v5 = "RtlMakeSelfRelativeSD( pTempSd, m_pSD, &cbSecurityDescriptor)";
      goto LABEL_4;
    }
  }
  else
  {
    v7 = RtlLengthSecurityDescriptor(a2);
    v8 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
    *a1 = v8;
    if ( !v8 )
    {
      v15 = 827;
      v9 = "m_pSD = RtlAllocateHeap((((PPEB)__readgsqword(((LONG)__builtin_offsetof(TEB, ProcessEnvironmentBlock))))->Pro"
           "cessHeap), 0, Size)";
LABEL_8:
      v16 = v9;
      v13 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v14 = "Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign";
      RtlReportErrorOrigination(&v13, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225495LL);
      return 3221225495LL;
    }
    memcpy_0(v8, a2, v7);
    a1[1] = v7;
  }
  return 0;
}

```

## disassembly

```asm
0x180013194  mov     [rsp-18h+arg_10], rbx
0x180013199  push    rbp
0x18001319a  push    rsi
0x18001319b  push    rdi
0x18001319c  mov     rbp, rsp
0x18001319f  sub     rsp, 60h
0x1800131a3  mov     rax, cs:__security_cookie
0x1800131aa  xor     rax, rsp
0x1800131ad  mov     [rbp+var_10], rax
0x1800131b1  cmp     qword ptr [rcx], 0
0x1800131b5  mov     rdi, rdx
0x1800131b8  mov     rsi, rcx
0x1800131bb  jnz     loc_180013381
0x1800131c1  xor     eax, eax
0x1800131c3  mov     [rbp+Revision], 0
0x1800131ca  lea     r8, [rbp+Revision]; Revision
0x1800131ce  mov     [rbp+Control], ax
0x1800131d2  lea     rdx, [rbp+Control]; Control
0x1800131d6  mov     rcx, rdi; SecurityDescriptor
0x1800131d9  call    cs:__imp_RtlGetControlSecurityDescriptor
0x1800131df  mov     ebx, eax
0x1800131e1  test    eax, eax
0x1800131e3  jns     short loc_180013228
0x1800131e5  mov     [rbp+var_30], 335h
0x1800131ed  lea     rax, aRtlgetcontrols; "RtlGetControlSecurityDescriptor(pTempSd"...
0x1800131f4  lea     rcx, aOnecoreBaseWcp; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1800131fb  mov     [rbp+var_28], rax
0x1800131ff  mov     [rbp+var_40], rcx
0x180013203  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18001320a  lea     rcx, aWindowsAutoStr; "Windows::Auto<struct _SECURITY_DESCRIPT"...
0x180013211  mov     r8d, ebx
0x180013214  mov     [rbp+var_38], rcx
0x180013218  lea     rcx, [rbp+var_40]
0x18001321c  call    RtlReportErrorOrigination
0x180013221  mov     eax, ebx
0x180013223  jmp     loc_1800132BC
0x180013228  mov     eax, 8000h
0x18001322d  mov     rcx, rdi; AbsoluteSD
0x180013230  test    [rbp+Control], ax
0x180013234  jz      loc_1800132D8
0x18001323a  call    cs:__imp_RtlLengthSecurityDescriptor
0x180013240  mov     rcx, gs:60h
0x180013249  xor     edx, edx; Flags
0x18001324b  mov     r8d, eax; Size
0x18001324e  mov     ebx, eax
0x180013250  mov     rcx, [rcx+30h]; HeapHandle
0x180013254  call    cs:__imp_RtlAllocateHeap
0x18001325a  mov     [rsi], rax
0x18001325d  test    rax, rax
0x180013260  jnz     short loc_1800132A8
0x180013262  mov     [rbp+var_30], 33Bh
0x18001326a  lea     rax, aMPsdRtlallocat; "m_pSD = RtlAllocateHeap((((PPEB)__readg"...
0x180013271  lea     rcx, aOnecoreBaseWcp; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x180013278  mov     [rbp+var_28], rax
0x18001327c  mov     [rbp+var_40], rcx
0x180013280  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180013287  lea     rcx, aWindowsAutoStr; "Windows::Auto<struct _SECURITY_DESCRIPT"...
0x18001328e  mov     r8d, 0C0000017h
0x180013294  mov     [rbp+var_38], rcx
0x180013298  lea     rcx, [rbp+var_40]
0x18001329c  call    RtlReportErrorOrigination
0x1800132a1  mov     eax, 0C0000017h
0x1800132a6  jmp     short loc_1800132BC
0x1800132a8  mov     r8, rbx; Size
0x1800132ab  mov     rdx, rdi; Src
0x1800132ae  mov     rcx, rax; void *
0x1800132b1  call    memcpy_0
0x1800132b6  mov     [rsi+8], rbx
0x1800132ba  xor     eax, eax
0x1800132bc  mov     rcx, [rbp+var_10]
0x1800132c0  xor     rcx, rsp; StackCookie
0x1800132c3  call    __security_check_cookie
0x1800132c8  mov     rbx, [rsp+60h+arg_10]
0x1800132d0  add     rsp, 60h
0x1800132d4  pop     rdi
0x1800132d5  pop     rsi
0x1800132d6  pop     rbp
0x1800132d7  retn
0x1800132d8  lea     r8, [rbp+BufferLength]; BufferLength
0x1800132dc  mov     [rbp+BufferLength], 0
0x1800132e3  xor     edx, edx; SelfRelativeSD
0x1800132e5  call    cs:__imp_RtlMakeSelfRelativeSD
0x1800132eb  mov     ebx, eax
0x1800132ed  cmp     eax, 80000005h
0x1800132f2  jz      short loc_180013317
0x1800132f4  cmp     eax, 0C0000023h
0x1800132f9  jz      short loc_180013317
0x1800132fb  test    eax, eax
0x1800132fd  jns     loc_180013387
0x180013303  mov     [rbp+var_30], 349h
0x18001330b  lea     rax, aTmpstatusNtsta; "((TmpStatus == ((NTSTATUS)0x80000005L))"...
0x180013312  jmp     loc_1800131F4
0x180013317  mov     rcx, gs:60h
0x180013320  xor     edx, edx; Flags
0x180013322  mov     r8d, [rbp+BufferLength]; Size
0x180013326  mov     rcx, [rcx+30h]; HeapHandle
0x18001332a  call    cs:__imp_RtlAllocateHeap
0x180013330  mov     [rsi], rax
0x180013333  mov     rdx, rax; SelfRelativeSD
0x180013336  test    rax, rax
0x180013339  jnz     short loc_18001334F
0x18001333b  mov     [rbp+var_30], 34Bh
0x180013343  lea     rax, aMPsdRtlallocat_0; "m_pSD = ::RtlAllocateHeap((((PPEB)__rea"...
0x18001334a  jmp     loc_180013271
0x18001334f  mov     eax, [rbp+BufferLength]
0x180013352  lea     r8, [rbp+BufferLength]; BufferLength
0x180013356  mov     rcx, rdi; AbsoluteSD
0x180013359  mov     [rsi+8], rax
0x18001335d  call    cs:__imp_RtlMakeSelfRelativeSD
0x180013363  mov     ebx, eax
0x180013365  test    eax, eax
0x180013367  jns     loc_1800132BA
0x18001336d  mov     [rbp+var_30], 352h
0x180013375  lea     rax, aRtlmakeselfrel; "RtlMakeSelfRelativeSD( pTempSd, m_pSD, "...
0x18001337c  jmp     loc_1800131F4
0x180013381  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x180013387  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
