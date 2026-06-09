# SipcSignalFactory::OpenServerEvents(ushort,SipcPrivateNamespace const &,void * *,void * *)

- ea: `0x1800a3c10`
- end: `0x1800a3da1`
- name: `?OpenServerEvents@SipcSignalFactory@@SAJGAEBVSipcPrivateNamespace@@PEAPEAX1@Z`
- size: `401`
- prototype: `__int64 __fastcall(unsigned __int16, const struct SipcPrivateNamespace *, void **, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800a32c0`

## callees

- `0x1800a3c10`
- `0x1800a4198`
- `0x1800f0990`
- `0x1800f0e70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3cfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3d32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3cfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3d32`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800a3ce8`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800a3d22`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800a3ce8`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800a3d22`

## pseudocode

```c
__int64 __fastcall SipcSignalFactory::OpenServerEvents(
        unsigned __int16 a1,
        const struct SipcPrivateNamespace *a2,
        void **a3,
        void **a4)
{
  char *v4; // r14
  char *v7; // r9
  int v8; // ebx
  signed int v9; // eax
  unsigned int v10; // ebx
  HANDLE v11; // rax
  signed int LastError; // eax
  __int64 v14; // [rsp+20h] [rbp-E0h]
  HANDLE v15; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE v16; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Buffer[56]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t Name[56]; // [rsp+B0h] [rbp-50h] BYREF

  v4 = (char *)a2 + 8;
  *a3 = 0;
  *a4 = 0;
  v7 = (char *)a2 + 8;
  if ( a1 )
  {
    v8 = a1;
    swprintf_s(Buffer, 0x38u, L"%s\\%4.4X_%s", v7, a1, L"ClientSignal");
    LODWORD(v14) = v8;
    swprintf_s(Name, 0x38u, L"%s\\%4.4X_%s", v4, v14, L"ServerSignal");
  }
  else
  {
    swprintf_s(Buffer, 0x38u, L"%s\\%s", v7, L"ClientSignal");
    swprintf_s(Name, 0x38u, L"%s\\%s", v4, L"ServerSignal");
  }
  v16 = OpenEventW(0x100002u, 0, Buffer);
  if ( v16 )
  {
    v11 = OpenEventW(2u, 0, Name);
    v15 = v11;
    if ( v11 )
    {
      *a3 = v16;
      *a4 = v11;
      v16 = 0;
      v15 = 0;
      SipcWin32Handle::Reset((SipcWin32Handle *)&v15);
      v10 = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v10 = -2147418113;
      if ( LastError < 0 )
        v10 = LastError;
      SipcWin32Handle::Reset((SipcWin32Handle *)&v15);
    }
  }
  else
  {
    v9 = GetLastError();
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    v10 = -2147418113;
    if ( v9 < 0 )
      v10 = v9;
  }
  SipcWin32Handle::Reset((SipcWin32Handle *)&v16);
  return v10;
}

```

## disassembly

```asm
0x1800a3c10  push    rbp
0x1800a3c12  push    rbx
0x1800a3c13  push    rsi
0x1800a3c14  push    rdi
0x1800a3c15  push    r12
0x1800a3c17  push    r14
0x1800a3c19  push    r15
0x1800a3c1b  lea     rbp, [rsp-30h]
0x1800a3c20  sub     rsp, 130h
0x1800a3c27  mov     rax, cs:__security_cookie
0x1800a3c2e  xor     rax, rsp
0x1800a3c31  mov     [rbp+60h+var_40], rax
0x1800a3c35  xor     r12d, r12d
0x1800a3c38  lea     r14, [rdx+8]
0x1800a3c3c  mov     [r8], r12
0x1800a3c3f  mov     rsi, r9
0x1800a3c42  mov     [r9], r12
0x1800a3c45  mov     rdi, r8
0x1800a3c48  lea     rax, ?ClientSignalName@SipcSignalFactory@@0QBGB; "ClientSignal"
0x1800a3c4f  mov     r9, r14
0x1800a3c52  lea     r15d, [r12+38h]
0x1800a3c57  mov     edx, r15d; BufferCount
0x1800a3c5a  test    cx, cx
0x1800a3c5d  jz      short loc_1800A3CA4
0x1800a3c5f  movzx   ebx, cx
0x1800a3c62  lea     r8, aS44xS; "%s\\%4.4X_%s"
0x1800a3c69  mov     [rsp+160h+var_138], rax
0x1800a3c6e  lea     rcx, [rsp+160h+Buffer]; Buffer
0x1800a3c73  mov     dword ptr [rsp+160h+var_140], ebx
0x1800a3c77  call    swprintf_s
0x1800a3c7c  lea     rax, ?ServerSignalName@SipcSignalFactory@@0QBGB; "ServerSignal"
0x1800a3c83  mov     r9, r14
0x1800a3c86  mov     [rsp+160h+var_138], rax
0x1800a3c8b  lea     r8, aS44xS; "%s\\%4.4X_%s"
0x1800a3c92  mov     edx, r15d; BufferCount
0x1800a3c95  mov     dword ptr [rsp+160h+var_140], ebx
0x1800a3c99  lea     rcx, [rbp+60h+Name]; Buffer
0x1800a3c9d  call    swprintf_s
0x1800a3ca2  jmp     short loc_1800A3CDC
0x1800a3ca4  lea     r8, aSS; "%s\\%s"
0x1800a3cab  mov     [rsp+160h+var_140], rax
0x1800a3cb0  lea     rcx, [rsp+160h+Buffer]; Buffer
0x1800a3cb5  call    swprintf_s
0x1800a3cba  lea     rax, ?ServerSignalName@SipcSignalFactory@@0QBGB; "ServerSignal"
0x1800a3cc1  mov     r9, r14
0x1800a3cc4  lea     r8, aSS; "%s\\%s"
0x1800a3ccb  mov     [rsp+160h+var_140], rax
0x1800a3cd0  mov     rdx, r15; BufferCount
0x1800a3cd3  lea     rcx, [rbp+60h+Name]; Buffer
0x1800a3cd7  call    swprintf_s
0x1800a3cdc  lea     r8, [rsp+160h+Buffer]; lpName
0x1800a3ce1  xor     edx, edx; bInheritHandle
0x1800a3ce3  mov     ecx, 100002h; dwDesiredAccess
0x1800a3ce8  call    cs:__imp_OpenEventW
0x1800a3cee  mov     [rsp+160h+var_128], rax
0x1800a3cf3  mov     rbx, rax
0x1800a3cf6  test    rax, rax
0x1800a3cf9  jnz     short loc_1800A3D19
0x1800a3cfb  call    cs:__imp_GetLastError
0x1800a3d01  test    eax, eax
0x1800a3d03  jle     short loc_1800A3D0D
0x1800a3d05  movzx   eax, ax
0x1800a3d08  or      eax, 80070000h
0x1800a3d0d  test    eax, eax
0x1800a3d0f  mov     ebx, 8000FFFFh
0x1800a3d14  cmovs   ebx, eax
0x1800a3d17  jmp     short loc_1800A3D77
0x1800a3d19  xor     edx, edx; bInheritHandle
0x1800a3d1b  lea     r8, [rbp+60h+Name]; lpName
0x1800a3d1f  lea     ecx, [rdx+2]; dwDesiredAccess
0x1800a3d22  call    cs:__imp_OpenEventW
0x1800a3d28  mov     [rsp+160h+var_130], rax
0x1800a3d2d  test    rax, rax
0x1800a3d30  jnz     short loc_1800A3D5A
0x1800a3d32  call    cs:__imp_GetLastError
0x1800a3d38  test    eax, eax
0x1800a3d3a  jle     short loc_1800A3D44
0x1800a3d3c  movzx   eax, ax
0x1800a3d3f  or      eax, 80070000h
0x1800a3d44  test    eax, eax
0x1800a3d46  lea     rcx, [rsp+160h+var_130]; this
0x1800a3d4b  mov     ebx, 8000FFFFh
0x1800a3d50  cmovs   ebx, eax
0x1800a3d53  call    ?Reset@SipcWin32Handle@@QEAAXXZ; SipcWin32Handle::Reset(void)
0x1800a3d58  jmp     short loc_1800A3D77
0x1800a3d5a  mov     [rdi], rbx
0x1800a3d5d  lea     rcx, [rsp+160h+var_130]; this
0x1800a3d62  mov     [rsi], rax
0x1800a3d65  mov     [rsp+160h+var_128], r12
0x1800a3d6a  mov     [rsp+160h+var_130], r12
0x1800a3d6f  call    ?Reset@SipcWin32Handle@@QEAAXXZ; SipcWin32Handle::Reset(void)
0x1800a3d74  mov     ebx, r12d
0x1800a3d77  lea     rcx, [rsp+160h+var_128]; this
0x1800a3d7c  call    ?Reset@SipcWin32Handle@@QEAAXXZ; SipcWin32Handle::Reset(void)
0x1800a3d81  mov     eax, ebx
0x1800a3d83  mov     rcx, [rbp+60h+var_40]
0x1800a3d87  xor     rcx, rsp; StackCookie
0x1800a3d8a  call    __security_check_cookie
0x1800a3d8f  add     rsp, 130h
0x1800a3d96  pop     r15
0x1800a3d98  pop     r14
0x1800a3d9a  pop     r12
0x1800a3d9c  pop     rdi
0x1800a3d9d  pop     rsi
0x1800a3d9e  pop     rbx
0x1800a3d9f  pop     rbp
0x1800a3da0  retn
```
