# SourceSelector_Log_OnError

- ea: `0x180021990`
- end: `0x180021c39`
- name: `SourceSelector_Log_OnError`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180021780`

## callees

- `0x180006e64`
- `0x1800077a0`
- `0x180007800`
- `0x180007c80`
- `0x180021990`
- `0x180022204`
- `0x18004370c`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180021ab4`
- `msvcrt!_wcsicmp` at `0x180021acd`
- `msvcrt!_wcsicmp` at `0x180021ae2`
- `msvcrt!_wcsicmp` at `0x180021ab4`
- `msvcrt!_wcsicmp` at `0x180021acd`
- `msvcrt!_wcsicmp` at `0x180021ae2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180021b26`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180021b26`

## string_xrefs

- `0x180021b15`: `mpunits.dll`
- `0x180021aad`: `MSFT DSC CU BINARY-LOG-READER`
- `0x180021ac6`: `FAILED-TO-OPEN-FILE`
- `0x180021adb`: `DIRECTORY-NOT-FOUND`

## pseudocode

```c
char __fastcall SourceSelector_Log_OnError(__int64 a1, unsigned int a2, _QWORD *a3)
{
  _QWORD **v3; // rsi
  _QWORD *v4; // rbx
  unsigned int ArbiterForJob; // edi
  __int64 v7; // rax
  _QWORD *v8; // rbx
  __int64 v9; // rdi
  HMODULE ModuleHandleA; // rax
  __int64 v11; // rax
  int v13; // [rsp+40h] [rbp-49h] BYREF
  int v14; // [rsp+44h] [rbp-45h] BYREF
  _QWORD *v15; // [rsp+48h] [rbp-41h] BYREF
  __int128 v16; // [rsp+50h] [rbp-39h]
  wchar_t *v17[2]; // [rsp+60h] [rbp-29h] BYREF
  __int128 v18; // [rsp+70h] [rbp-19h]
  __int64 v19; // [rsp+80h] [rbp-9h]
  wchar_t *String1[2]; // [rsp+88h] [rbp-1h] BYREF
  __int128 v21; // [rsp+98h] [rbp+Fh]
  __int64 v22; // [rsp+A8h] [rbp+1Fh]

  v3 = (_QWORD **)(a1 + 152);
  v13 = 0;
  v22 = 0;
  v19 = 0;
  v14 = 0;
  v4 = a3;
  v15 = 0;
  ArbiterForJob = a2;
  *(_OWORD *)String1 = 0;
  v21 = 0;
  *(_OWORD *)v17 = 0;
  v18 = 0;
  if ( !a3
    || a2 != 4
    || !*(_QWORD *)(a1 + 224)
    || !*a3
    || (*(unsigned int (__fastcall **)(_QWORD *, const wchar_t *, wchar_t **, int *, _QWORD, _QWORD))(*a3 + 88LL))(
         a3,
         L"OwningEntity",
         String1,
         &v13,
         0,
         0)
    || !*v4
    || (*(unsigned int (__fastcall **)(_QWORD *, const wchar_t *, wchar_t **, int *, _QWORD, _QWORD))(*v4 + 88LL))(
         v4,
         L"MessageID",
         v17,
         &v14,
         0,
         0)
    || v13 != 13
    || v14 != 13
    || !String1[0]
    || !v17[0]
    || _wcsicmp(String1[0], L"MSFT DSC CU BINARY-LOG-READER")
    || _wcsicmp(v17[0], L"FAILED-TO-OPEN-FILE") && _wcsicmp(v17[0], L"DIRECTORY-NOT-FOUND") )
  {
    goto LABEL_18;
  }
  ArbiterForJob = SourceSelector_QueryArbiterForJob(v3);
  if ( ArbiterForJob )
    goto LABEL_18;
  if ( !*((_BYTE *)v3 + 80) )
  {
    v7 = EnableErrorDetails();
    v8 = v3[8];
    v9 = v7;
    v16 = 0;
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    *(_QWORD *)&v16 = Intlstr_FormatString_FormatMessage(ModuleHandleA, 2138, v8);
    BYTE8(v16) = 1;
    MI_ReportErrorDetails_ForCustomError(4, (int)L"MI", 0, 0);
    CatchErrorDetails(v9, &v15);
    v4 = v15;
    ArbiterForJob = 4;
LABEL_18:
    if ( ((_DWORD)v3[6] & 7) == 1 )
    {
      *((_BYTE *)v3 + 56) = 1;
      CondLock_Broadcast();
    }
    LOBYTE(v11) = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD *))ObserverProtocol_PostErrorAndDispose)(
                    a1,
                    ArbiterForJob,
                    v4);
    if ( v15 )
    {
      v11 = *v15;
      if ( *v15 )
        LOBYTE(v11) = (*(__int64 (**)(void))(v11 + 16))();
    }
    return v11;
  }
  if ( *v3 )
    ((void (__fastcall *)(_QWORD))(*v3)[1])(**v3);
  if ( *v3 )
    ((void (__fastcall *)(_QWORD))(*v3)[3])(**v3);
  *v3 = 0;
  *((_DWORD *)v3 + 12) = (_DWORD)v3[6] & 0xFFFFFFF8 | 1;
  LOBYTE(v11) = (_DWORD)v3[6] & 7;
  if ( (_BYTE)v11 == 1 )
    LOBYTE(v11) = CondLock_Broadcast();
  return v11;
}

```

## disassembly

```asm
0x180021990  mov     [rsp-8+arg_18], rbx
0x180021995  push    rbp
0x180021996  push    rsi
0x180021997  push    rdi
0x180021998  push    r14
0x18002199a  push    r15
0x18002199c  lea     rbp, [rsp-37h]
0x1800219a1  sub     rsp, 0C0h
0x1800219a8  mov     rax, cs:__security_cookie
0x1800219af  xor     rax, rsp
0x1800219b2  mov     [rbp+57h+var_30], rax
0x1800219b6  xor     r15d, r15d
0x1800219b9  lea     rsi, [rcx+98h]
0x1800219c0  xor     eax, eax
0x1800219c2  mov     [rbp+57h+var_A0], r15d
0x1800219c6  mov     [rbp+57h+var_38], rax
0x1800219ca  xorps   xmm0, xmm0
0x1800219cd  mov     [rbp+57h+var_60], rax
0x1800219d1  xorps   xmm1, xmm1
0x1800219d4  mov     [rbp+57h+var_9C], r15d
0x1800219d8  mov     rbx, r8
0x1800219db  mov     [rbp+57h+var_98], r15
0x1800219df  mov     edi, edx
0x1800219e1  mov     r14, rcx
0x1800219e4  movups  xmmword ptr [rbp+57h+String1], xmm0
0x1800219e8  movups  [rbp+57h+var_48], xmm0
0x1800219ec  movups  xmmword ptr [rbp+57h+var_80], xmm1
0x1800219f0  movups  [rbp+57h+var_70], xmm1
0x1800219f4  test    r8, r8
0x1800219f7  jz      loc_180021B86
0x1800219fd  cmp     edx, 4
0x180021a00  jnz     loc_180021B86
0x180021a06  cmp     [rsi+48h], r15
0x180021a0a  jz      loc_180021B86
0x180021a10  mov     rax, [r8]
0x180021a13  test    rax, rax
0x180021a16  jz      loc_180021B86
0x180021a1c  mov     rax, [rax+58h]
0x180021a20  lea     r9, [rbp+57h+var_A0]
0x180021a24  mov     [rsp+0E0h+var_B8], r15
0x180021a29  lea     r8, [rbp+57h+String1]
0x180021a2d  lea     rdx, aOwningentity; "OwningEntity"
0x180021a34  mov     [rsp+0E0h+var_C0], r15
0x180021a39  mov     rcx, rbx
0x180021a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a41  test    eax, eax
0x180021a43  jnz     loc_180021B86
0x180021a49  mov     rax, [rbx]
0x180021a4c  test    rax, rax
0x180021a4f  jz      loc_180021B86
0x180021a55  mov     rax, [rax+58h]
0x180021a59  lea     r9, [rbp+57h+var_9C]
0x180021a5d  mov     [rsp+0E0h+var_B8], r15
0x180021a62  lea     r8, [rbp+57h+var_80]
0x180021a66  lea     rdx, aMessageid; "MessageID"
0x180021a6d  mov     [rsp+0E0h+var_C0], r15
0x180021a72  mov     rcx, rbx
0x180021a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a7a  test    eax, eax
0x180021a7c  jnz     loc_180021B86
0x180021a82  cmp     [rbp+57h+var_A0], 0Dh
0x180021a86  jnz     loc_180021B86
0x180021a8c  cmp     [rbp+57h+var_9C], 0Dh
0x180021a90  jnz     loc_180021B86
0x180021a96  mov     rcx, [rbp+57h+String1]; String1
0x180021a9a  test    rcx, rcx
0x180021a9d  jz      loc_180021B86
0x180021aa3  cmp     [rbp+57h+var_80], r15
0x180021aa7  jz      loc_180021B86
0x180021aad  lea     rdx, aMsftDscCuBinar_0; "MSFT DSC CU BINARY-LOG-READER"
0x180021ab4  call    cs:__imp__wcsicmp
0x180021aba  test    eax, eax
0x180021abc  jnz     loc_180021B86
0x180021ac2  mov     rcx, [rbp+57h+var_80]; String1
0x180021ac6  lea     rdx, aFailedToOpenFi; "FAILED-TO-OPEN-FILE"
0x180021acd  call    cs:__imp__wcsicmp
0x180021ad3  test    eax, eax
0x180021ad5  jz      short loc_180021AF0
0x180021ad7  mov     rcx, [rbp+57h+var_80]; String1
0x180021adb  lea     rdx, aDirectoryNotFo; "DIRECTORY-NOT-FOUND"
0x180021ae2  call    cs:__imp__wcsicmp
0x180021ae8  test    eax, eax
0x180021aea  jnz     loc_180021B86
0x180021af0  mov     rcx, rsi
0x180021af3  call    SourceSelector_QueryArbiterForJob
0x180021af8  mov     edi, eax
0x180021afa  test    eax, eax
0x180021afc  jnz     loc_180021B86
0x180021b02  cmp     [rsi+50h], r15b
0x180021b06  jnz     loc_180021BEF
0x180021b0c  call    EnableErrorDetails
0x180021b11  mov     rbx, [rsi+40h]
0x180021b15  lea     rcx, ModuleName; "mpunits.dll"
0x180021b1c  xorps   xmm0, xmm0
0x180021b1f  mov     rdi, rax
0x180021b22  movups  [rbp+57h+var_90], xmm0
0x180021b26  call    cs:__imp_GetModuleHandleA
0x180021b2c  mov     r8, rbx
0x180021b2f  mov     edx, 85Ah
0x180021b34  mov     rcx, rax
0x180021b37  call    _Intlstr_FormatString_FormatMessage
0x180021b3c  mov     qword ptr [rbp+57h+var_90], rax
0x180021b40  lea     r9, [rbp+57h+var_90]
0x180021b44  mov     byte ptr [rbp+57h+var_90+8], 1
0x180021b48  lea     rdx, aMi; "MI"
0x180021b4f  movaps  xmm0, [rbp+57h+var_90]
0x180021b53  mov     r8d, 5
0x180021b59  mov     [rsp+0E0h+var_B8], r15; __int64
0x180021b5e  movdqa  [rbp+57h+var_90], xmm0
0x180021b63  mov     [rsp+0E0h+var_C0], r15; __int64
0x180021b68  lea     ecx, [r8-1]; int
0x180021b6c  call    MI_ReportErrorDetails_ForCustomError
0x180021b71  lea     rdx, [rbp+57h+var_98]
0x180021b75  mov     rcx, rdi
0x180021b78  call    CatchErrorDetails
0x180021b7d  mov     rbx, [rbp+57h+var_98]
0x180021b81  mov     edi, 4
0x180021b86  lea     rcx, [rsi+30h]
0x180021b8a  mov     eax, [rcx]
0x180021b8c  and     al, 7
0x180021b8e  cmp     al, 1
0x180021b90  jnz     short loc_180021B9A
0x180021b92  mov     [rsi+38h], al
0x180021b95  call    CondLock_Broadcast
0x180021b9a  mov     rax, cs:off_180047BB0
0x180021ba1  mov     r8, rbx
0x180021ba4  mov     edx, edi
0x180021ba6  mov     rcx, r14
0x180021ba9  mov     rax, [rax+60h]
0x180021bad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021bb2  mov     rcx, [rbp+57h+var_98]
0x180021bb6  test    rcx, rcx
0x180021bb9  jz      short loc_180021BCC
0x180021bbb  mov     rax, [rcx]
0x180021bbe  test    rax, rax
0x180021bc1  jz      short loc_180021BCC
0x180021bc3  mov     rax, [rax+10h]
0x180021bc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021bcc  mov     rcx, [rbp+57h+var_30]
0x180021bd0  xor     rcx, rsp; StackCookie
0x180021bd3  call    __security_check_cookie
0x180021bd8  mov     rbx, [rsp+0E0h+arg_18]
0x180021be0  add     rsp, 0C0h
0x180021be7  pop     r15
0x180021be9  pop     r14
0x180021beb  pop     rdi
0x180021bec  pop     rsi
0x180021bed  pop     rbp
0x180021bee  retn
0x180021bef  mov     rax, [rsi]
0x180021bf2  test    rax, rax
0x180021bf5  jz      short loc_180021C03
0x180021bf7  mov     rcx, [rax]
0x180021bfa  mov     rax, [rax+8]
0x180021bfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c03  mov     rax, [rsi]
0x180021c06  test    rax, rax
0x180021c09  jz      short loc_180021C17
0x180021c0b  mov     rcx, [rax]
0x180021c0e  mov     rax, [rax+18h]
0x180021c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c17  lea     rcx, [rsi+30h]
0x180021c1b  mov     [rsi], r15
0x180021c1e  mov     eax, [rcx]
0x180021c20  and     eax, 0FFFFFFF9h
0x180021c23  or      eax, 1
0x180021c26  mov     [rsi+30h], eax
0x180021c29  mov     eax, [rsi+30h]
0x180021c2c  and     al, 7
0x180021c2e  cmp     al, 1
0x180021c30  jnz     short loc_180021BCC
0x180021c32  call    CondLock_Broadcast
0x180021c37  jmp     short loc_180021BCC
```
