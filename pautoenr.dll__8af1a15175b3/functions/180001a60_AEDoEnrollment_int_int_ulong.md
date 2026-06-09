# AEDoEnrollment(int,int,ulong)

- ea: `0x180001a60`
- end: `0x180001d27`
- name: `?AEDoEnrollment@@YAHHHK@Z`
- size: `711`
- prototype: `__int64 __fastcall(int, int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001d90`

## callees

- `0x180001a60`
- `0x1800027e0`
- `0x180007d20`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001ccf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001ccf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180001afd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180001afd`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180001c3c`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180001c3c`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x180001b66`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x180001b66`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180001c46`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180001c46`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180001b4b`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180001b4b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180001d1c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180001d1c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180001b7c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180001b7c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180001bc5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180001bc5`
- `certenroll!__imp_AutoEnrollWizard` at `0x180001bf7`
- `certenroll!__imp_AutoEnrollWizard` at `0x180001bf7`
- `USER32!GetDesktopWindow` at `0x180001be5`
- `USER32!GetDesktopWindow` at `0x180001be5`

## pseudocode

```c
__int64 __fastcall AEDoEnrollment(int a1, int a2, unsigned int a3)
{
  unsigned int v6; // ebx
  BOOL v7; // r14d
  HANDLE v8; // rax
  void *v9; // rsi
  unsigned int v10; // edi
  HWND DesktopWindow; // rax
  unsigned int v12; // eax
  signed int LastError; // eax
  _WORD v15[2]; // [rsp+40h] [rbp-2A8h] BYREF
  BOOL v16; // [rsp+44h] [rbp-2A4h]
  LPVOID ppv; // [rsp+48h] [rbp-2A0h] BYREF
  ULONG_PTR Cookie; // [rsp+50h] [rbp-298h] BYREF
  ACTCTXW pActCtx; // [rsp+58h] [rbp-290h] BYREF
  WCHAR Filename[264]; // [rsp+90h] [rbp-258h] BYREF

  v6 = 0;
  v15[0] = 0;
  memset(&pActCtx, 0, sizeof(pActCtx));
  Cookie = 0;
  ppv = 0;
  AELogAutoEnrollmentEvent(a3, 0, 0, 3221225476LL, a1, 0, 0);
  v7 = 0;
  v16 = 0;
  Filename[0] = 0;
  if ( !GetModuleFileNameW(g_hmodThisDll, Filename, 0x105u) )
  {
    v9 = 0;
    goto LABEL_23;
  }
  *(_OWORD *)&pActCtx.wProcessorArchitecture = 0;
  *(_OWORD *)&pActCtx.lpApplicationName = 0;
  pActCtx.cbSize = 56;
  pActCtx.dwFlags = 8;
  pActCtx.lpSource = Filename;
  pActCtx.lpResourceName = (LPCWSTR)2;
  v8 = CreateActCtxW(&pActCtx);
  v9 = v8;
  if ( v8 == (HANDLE)-1LL || !ActivateActCtx(v8, &Cookie) )
  {
LABEL_23:
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_11;
  }
  if ( a2 )
  {
    DesktopWindow = GetDesktopWindow();
    v12 = AutoEnrollWizard(DesktopWindow, 1, (unsigned int)(a1 != 0) + 1);
LABEL_10:
    v10 = v12;
    AELogAutoEnrollmentEvent(a3, 0, 0, 3221225477LL, a1, 0, 0);
    goto LABEL_11;
  }
  v10 = CoInitializeEx(0, 0);
  if ( (int)(v10 + 0x80000000) < 0 || v10 == -2147417850 )
  {
    v7 = (v10 & 0x80000000) == 0;
    v10 = CoCreateInstance(
            &GUID_91f39001_217f_11da_b2a4_000e7bbb2b09,
            0,
            1u,
            &GUID_13b79001_2181_11da_b2a4_000e7bbb2b09,
            &ppv);
    if ( v10 )
    {
      v16 = v7;
      goto LABEL_11;
    }
    v12 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, _WORD *))(*(_QWORD *)ppv + 48LL))(
            ppv,
            (unsigned int)(a1 != 0) + 1,
            0,
            v15);
    v16 = v7;
    goto LABEL_10;
  }
LABEL_11:
  if ( v10 )
    AELogAutoEnrollmentEvent(a3, 1, v10, 1073741830, a1, 0, 0);
  if ( Cookie )
    DeactivateActCtx(0, Cookie);
  if ( v9 != (void *)-1LL )
    ReleaseActCtx(v9);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v7 )
    CoUninitialize();
  LOBYTE(v6) = v15[0] != 0;
  return v6;
}

```

## disassembly

```asm
0x180001a60  push    rbx
0x180001a62  push    rsi
0x180001a63  push    rdi
0x180001a64  push    r12
0x180001a66  push    r14
0x180001a68  push    r15
0x180001a6a  sub     rsp, 2B8h
0x180001a71  mov     rax, cs:__security_cookie
0x180001a78  xor     rax, rsp
0x180001a7b  mov     [rsp+2E8h+var_48], rax
0x180001a83  mov     r12d, r8d
0x180001a86  mov     edi, edx
0x180001a88  mov     r15d, ecx
0x180001a8b  xor     ebx, ebx
0x180001a8d  mov     [rsp+2E8h+var_2A8], bx
0x180001a92  xorps   xmm0, xmm0
0x180001a95  xor     eax, eax
0x180001a97  movups  xmmword ptr [rsp+2E8h+pActCtx.cbSize], xmm0
0x180001a9c  movups  xmmword ptr [rsp+2E8h+pActCtx.wProcessorArchitecture], xmm0
0x180001aa1  movups  xmmword ptr [rsp+2E8h+pActCtx.lpResourceName], xmm0
0x180001aa6  mov     [rsp+2E8h+pActCtx.hModule], rax
0x180001aae  mov     [rsp+2E8h+Cookie], rbx
0x180001ab3  mov     [rsp+2E8h+var_2A0], rbx
0x180001ab8  mov     [rsp+2E8h+var_2B8], rbx
0x180001abd  mov     [rsp+2E8h+var_2C0], rbx
0x180001ac2  mov     dword ptr [rsp+2E8h+ppv], ecx
0x180001ac6  mov     r9d, 0C0000004h
0x180001acc  xor     r8d, r8d
0x180001acf  xor     edx, edx
0x180001ad1  mov     ecx, r12d
0x180001ad4  call    AELogAutoEnrollmentEvent
0x180001ad9  mov     r14d, ebx
0x180001adc  mov     [rsp+2E8h+var_2A4], ebx
0x180001ae0  mov     [rsp+2E8h+Filename], bx
0x180001ae8  mov     r8d, 105h; nSize
0x180001aee  lea     rdx, [rsp+2E8h+Filename]; lpFilename
0x180001af6  mov     rcx, cs:g_hmodThisDll; hModule
0x180001afd  call    cs:__imp_GetModuleFileNameW
0x180001b03  test    eax, eax
0x180001b05  jz      loc_180001CED
0x180001b0b  xorps   xmm0, xmm0
0x180001b0e  movdqu  xmmword ptr [rsp+2E8h+pActCtx.wProcessorArchitecture], xmm0
0x180001b14  xorps   xmm1, xmm1
0x180001b17  movdqu  xmmword ptr [rsp+2E8h+pActCtx.lpApplicationName], xmm1
0x180001b20  mov     [rsp+2E8h+pActCtx.cbSize], 38h ; '8'
0x180001b28  mov     [rsp+2E8h+pActCtx.dwFlags], 8
0x180001b30  lea     rax, [rsp+2E8h+Filename]
0x180001b38  mov     [rsp+2E8h+pActCtx.lpSource], rax
0x180001b3d  mov     [rsp+2E8h+pActCtx.lpResourceName], 2
0x180001b46  lea     rcx, [rsp+2E8h+pActCtx]; pActCtx
0x180001b4b  call    cs:__imp_CreateActCtxW
0x180001b51  mov     rsi, rax
0x180001b54  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180001b58  jz      loc_180001CCF
0x180001b5e  lea     rdx, [rsp+2E8h+Cookie]; lpCookie
0x180001b63  mov     rcx, rax; hActCtx
0x180001b66  call    cs:__imp_ActivateActCtx
0x180001b6c  test    eax, eax
0x180001b6e  jz      loc_180001CCF
0x180001b74  test    edi, edi
0x180001b76  jnz     short loc_180001BDC
0x180001b78  xor     edx, edx; dwCoInit
0x180001b7a  xor     ecx, ecx; pvReserved
0x180001b7c  call    cs:__imp_CoInitializeEx
0x180001b82  mov     edi, eax
0x180001b84  mov     ecx, 80000000h
0x180001b89  add     eax, ecx
0x180001b8b  test    ecx, eax
0x180001b8d  jnz     short loc_180001B9B
0x180001b8f  cmp     edi, 80010106h
0x180001b95  jnz     loc_180001C21
0x180001b9b  mov     r14d, edi
0x180001b9e  not     r14d
0x180001ba1  shr     r14d, 1Fh
0x180001ba5  lea     rax, [rsp+2E8h+var_2A0]
0x180001baa  mov     [rsp+2E8h+ppv], rax; ppv
0x180001baf  lea     r9, _GUID_13b79001_2181_11da_b2a4_000e7bbb2b09; riid
0x180001bb6  xor     edx, edx; pUnkOuter
0x180001bb8  mov     r8d, 1; dwClsContext
0x180001bbe  lea     rcx, _GUID_91f39001_217f_11da_b2a4_000e7bbb2b09; rclsid
0x180001bc5  call    cs:__imp_CoCreateInstance
0x180001bcb  mov     edi, eax
0x180001bcd  test    eax, eax
0x180001bcf  jz      loc_180001CA2
0x180001bd5  mov     [rsp+2E8h+var_2A4], r14d
0x180001bda  jmp     short loc_180001C21
0x180001bdc  mov     edi, ebx
0x180001bde  test    r15d, r15d
0x180001be1  setnz   dil
0x180001be5  call    cs:__imp_GetDesktopWindow
0x180001beb  mov     rcx, rax
0x180001bee  lea     r8d, [rdi+1]
0x180001bf2  mov     edx, 1
0x180001bf7  call    cs:__imp_AutoEnrollWizard
0x180001bfd  mov     edi, eax
0x180001bff  mov     [rsp+2E8h+var_2B8], rbx
0x180001c04  mov     [rsp+2E8h+var_2C0], rbx
0x180001c09  mov     dword ptr [rsp+2E8h+ppv], r15d
0x180001c0e  mov     r9d, 0C0000005h
0x180001c14  xor     r8d, r8d
0x180001c17  xor     edx, edx
0x180001c19  mov     ecx, r12d
0x180001c1c  call    AELogAutoEnrollmentEvent
0x180001c21  test    edi, edi
0x180001c23  jnz     loc_180001CF2
0x180001c29  mov     rdx, [rsp+2E8h+Cookie]; ulCookie
0x180001c2e  test    rdx, rdx
0x180001c31  jnz     short loc_180001C44
0x180001c33  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180001c37  jz      short loc_180001C4E
0x180001c39  mov     rcx, rsi; hActCtx
0x180001c3c  call    cs:__imp_ReleaseActCtx
0x180001c42  jmp     short loc_180001C4E
0x180001c44  xor     ecx, ecx; dwFlags
0x180001c46  call    cs:__imp_DeactivateActCtx
0x180001c4c  jmp     short loc_180001C33
0x180001c4e  jmp     short loc_180001C57
0x180001c50  xor     ebx, ebx
0x180001c52  mov     r14d, [rsp+2E8h+var_2A4]
0x180001c57  mov     rcx, [rsp+2E8h+var_2A0]
0x180001c5c  test    rcx, rcx
0x180001c5f  jz      short loc_180001C6D
0x180001c61  mov     rax, [rcx]
0x180001c64  mov     rax, [rax+10h]
0x180001c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c6d  test    r14d, r14d
0x180001c70  jnz     loc_180001D1C
0x180001c76  cmp     [rsp+2E8h+var_2A8], 0
0x180001c7c  setnz   bl
0x180001c7f  mov     eax, ebx
0x180001c81  mov     rcx, [rsp+2E8h+var_48]
0x180001c89  xor     rcx, rsp; StackCookie
0x180001c8c  call    __security_check_cookie
0x180001c91  add     rsp, 2B8h
0x180001c98  pop     r15
0x180001c9a  pop     r14
0x180001c9c  pop     r12
0x180001c9e  pop     rdi
0x180001c9f  pop     rsi
0x180001ca0  pop     rbx
0x180001ca1  retn
0x180001ca2  mov     rcx, [rsp+2E8h+var_2A0]
0x180001ca7  mov     rax, [rcx]
0x180001caa  mov     edx, ebx
0x180001cac  test    r15d, r15d
0x180001caf  setnz   dl
0x180001cb2  inc     edx
0x180001cb4  lea     r9, [rsp+2E8h+var_2A8]
0x180001cb9  xor     r8d, r8d
0x180001cbc  mov     rax, [rax+30h]
0x180001cc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cc5  mov     [rsp+2E8h+var_2A4], r14d
0x180001cca  jmp     loc_180001BFD
0x180001ccf  call    cs:__imp_GetLastError
0x180001cd5  mov     edi, eax
0x180001cd7  test    eax, eax
0x180001cd9  jle     loc_180001C21
0x180001cdf  movzx   edi, ax
0x180001ce2  or      edi, 80070000h
0x180001ce8  jmp     loc_180001C21
0x180001ced  mov     rsi, rbx
0x180001cf0  jmp     short loc_180001CCF
0x180001cf2  mov     [rsp+2E8h+var_2B8], rbx
0x180001cf7  mov     [rsp+2E8h+var_2C0], rbx
0x180001cfc  mov     dword ptr [rsp+2E8h+ppv], r15d
0x180001d01  mov     r9d, 40000006h
0x180001d07  mov     r8d, edi
0x180001d0a  mov     edx, 1
0x180001d0f  mov     ecx, r12d
0x180001d12  call    AELogAutoEnrollmentEvent
0x180001d17  jmp     loc_180001C29
0x180001d1c  call    cs:__imp_CoUninitialize
0x180001d22  jmp     loc_180001C76
```
