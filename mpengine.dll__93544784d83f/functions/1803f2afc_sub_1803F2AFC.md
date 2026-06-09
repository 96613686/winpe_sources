# sub_1803F2AFC

- ea: `0x1803f2afc`
- end: `0x1803f2eb4`
- name: `sub_1803F2AFC`
- size: `952`
- prototype: `__int64 __usercall@<rax>(__int64@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1803f3fb8`

## callees

- `0x18007dab0`
- `0x1801a166c`
- `0x1801a569c`
- `0x1801c8638`
- `0x18024d568`
- `0x1802ee490`
- `0x1803f2afc`
- `0x180b74350`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1803f2c23`
- `KERNEL32!CreateFileW` at `0x1803f2d8b`
- `KERNEL32!CreateFileW` at `0x1803f2dcf`
- `KERNEL32!CreateFileW` at `0x1803f2c23`
- `KERNEL32!CreateFileW` at `0x1803f2d8b`
- `KERNEL32!CreateFileW` at `0x1803f2dcf`
- `KERNEL32!CloseHandle` at `0x1803f2ccc`
- `KERNEL32!CloseHandle` at `0x1803f2ccc`
- `KERNEL32!GetLastError` at `0x1803f2c37`
- `KERNEL32!GetLastError` at `0x1803f2d33`
- `KERNEL32!GetLastError` at `0x1803f2d9c`
- `KERNEL32!GetLastError` at `0x1803f2de5`
- `KERNEL32!GetLastError` at `0x1803f2c37`
- `KERNEL32!GetLastError` at `0x1803f2d33`
- `KERNEL32!GetLastError` at `0x1803f2d9c`
- `KERNEL32!GetLastError` at `0x1803f2de5`
- `ADVAPI32!SetThreadToken` at `0x1803f2d29`
- `ADVAPI32!SetThreadToken` at `0x1803f2dfa`
- `ADVAPI32!SetThreadToken` at `0x1803f2d29`
- `ADVAPI32!SetThreadToken` at `0x1803f2dfa`

## string_xrefs

- `0x1803f2b8e`: `SeSecurityPrivilege`
- `0x1803f2b3a`: `SeRestorePrivilege`

## pseudocode

```c
__int64 __fastcall sub_1803F2AFC(const WCHAR *a1, __int64 a2, char a3, _BYTE *a4, _QWORD *a5)
{
  __int64 v8; // rbx
  int v9; // eax
  unsigned int v10; // esi
  HANDLE *v11; // rcx
  __int64 v12; // rdx
  int v13; // eax
  DWORD v14; // ebp
  DWORD v15; // edi
  HANDLE FileW; // rax
  DWORD LastError; // eax
  _QWORD *v18; // rax
  char v20; // di
  _QWORD *v21; // rax
  void *v22; // rax
  DWORD v23; // eax
  DWORD dwCreationDisposition; // r15d
  HANDLE v25; // rax
  DWORD v26; // eax
  __int64 v27; // rbp
  __int64 (__fastcall *v28)(__int64, __int64 *, _QWORD *); // rdi
  int v29; // [rsp+44h] [rbp-54h] BYREF
  __int64 v30; // [rsp+48h] [rbp-50h] BYREF
  __int64 v31; // [rsp+50h] [rbp-48h]

  v30 = a2;
  v8 = -1;
  v31 = -1;
  v29 = 0;
  v9 = sub_18024D568(&v29, L"SeRestorePrivilege");
  v10 = (unsigned __int16)v9;
  if ( v9 >= 0 )
  {
    v13 = sub_18024D568(&v29, L"SeSecurityPrivilege");
    v10 = (unsigned __int16)v13;
    if ( v13 >= 0 )
    {
      v14 = -1072955392;
      v15 = -1072955392;
      if ( v29 == 1 )
        v15 = -1056178176;
      if ( !*a4 && !(unsigned __int8)sub_1802EE490(a1) )
      {
        FileW = CreateFileW(a1, v15, 5u, 0, (a3 & 0x10 | 0x20u) >> 4, 0x2000000u, 0);
        if ( FileW != (HANDLE)-1LL )
        {
          v8 = (__int64)FileW;
          goto LABEL_45;
        }
        LastError = GetLastError();
        v10 = LastError;
        if ( !LastError )
          goto LABEL_47;
        if ( LastError != 3 && LastError != 5 && LastError != 67 && LastError != 1314
          || (v18 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 40LL))(v30),
              v14 = v15,
              !(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 24LL))(*v18)) )
        {
          v11 = (HANDLE *)hDevice;
          goto LABEL_23;
        }
      }
      *a4 = 1;
      v20 = 0;
      v21 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 40LL))(v30);
      v22 = (void *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v21 + 24LL))(*v21);
      if ( v22 )
      {
        if ( SetThreadToken(0, v22) )
        {
          v20 = 1;
          v23 = 0;
        }
        else
        {
          v23 = GetLastError();
        }
        if ( !v23 )
        {
          if ( !(unsigned __int8)sub_1802EE490(a1) )
            v14 |= 0x1000000u;
          dwCreationDisposition = (a3 & 0x10 | 0x20u) >> 4;
          v25 = CreateFileW(a1, v14, 5u, 0, dwCreationDisposition, 0x2000000u, 0);
          if ( v25 == (HANDLE)-1LL
            && ((v14 & 0x1000000) == 0
             || GetLastError() != 1314
             || (v25 = CreateFileW(a1, v14 & 0xFEFFFFFF, 5u, 0, dwCreationDisposition, 0x2000000u, 0),
                 v25 == (HANDLE)-1LL)) )
          {
            v26 = GetLastError();
            if ( !v10 )
              v10 = v26;
          }
          else
          {
            v8 = (__int64)v25;
            v10 = 0;
          }
        }
      }
      if ( v20 )
        SetThreadToken(0, 0);
      goto LABEL_45;
    }
    v11 = (HANDLE *)hDevice;
    if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
    {
      v12 = 18;
      goto LABEL_5;
    }
  }
  else
  {
    v11 = (HANDLE *)hDevice;
    if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
    {
      v12 = 17;
LABEL_5:
      sub_1801A166C(v11[2], v12, qword_180CBD248, v10);
LABEL_45:
      v11 = (HANDLE *)hDevice;
    }
  }
  if ( !v10 )
  {
LABEL_47:
    if ( (int)sub_18007DAB0((HANDLE)v8, (__int64)a1) >= 0 )
    {
      v27 = v30;
      v28 = *(__int64 (__fastcall **)(__int64, __int64 *, _QWORD *))(*(_QWORD *)v30 + 120LL);
      if ( *a5 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a5 + 8LL))(*a5);
        *a5 = 0;
      }
      v30 = v8;
      v8 = -1;
      v31 = -1;
      v10 = v28(v27, &v30, a5);
    }
    else
    {
      if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
        sub_1801C8638(*((_QWORD *)hDevice + 2), 22, qword_180CBD248, a1);
      v10 = 5;
    }
    goto LABEL_26;
  }
LABEL_23:
  if ( v11 != &hDevice && (*((_BYTE *)v11 + 28) & 1) != 0 )
    sub_1801A569C((unsigned int)v11[2], 23, (unsigned int)qword_180CBD248, (_DWORD)a1, v10);
LABEL_26:
  if ( v8 != -1 )
    CloseHandle((HANDLE)v8);
  return v10;
}

```

## disassembly

```asm
0x1803f2afc  mov     [rsp+arg_10], rbx
0x1803f2b01  push    rbp
0x1803f2b02  push    rsi
0x1803f2b03  push    rdi
0x1803f2b04  push    r12
0x1803f2b06  push    r13
0x1803f2b08  push    r14
0x1803f2b0a  push    r15
0x1803f2b0c  sub     rsp, 60h
0x1803f2b10  mov     r12, r9
0x1803f2b13  mov     r15d, r8d
0x1803f2b16  mov     [rsp+98h+var_50], rdx
0x1803f2b1b  mov     r14, rcx
0x1803f2b1e  mov     r13, [rsp+98h+arg_20]
0x1803f2b26  or      rax, 0FFFFFFFFFFFFFFFFh
0x1803f2b2a  mov     rbx, rax
0x1803f2b2d  mov     [rsp+98h+var_48], rax
0x1803f2b32  mov     [rsp+98h+var_54], 0
0x1803f2b3a  lea     rdx, aSerestoreprivi; "SeRestorePrivilege"
0x1803f2b41  lea     rcx, [rsp+98h+var_54]
0x1803f2b46  call    sub_18024D568
0x1803f2b4b  movzx   esi, ax
0x1803f2b4e  lea     rdi, hDevice
0x1803f2b55  test    eax, eax
0x1803f2b57  jns     short loc_1803F2B8E
0x1803f2b59  mov     rcx, cs:hDevice
0x1803f2b60  cmp     rcx, rdi
0x1803f2b63  jz      loc_1803F2E07
0x1803f2b69  test    byte ptr [rcx+1Ch], 1
0x1803f2b6d  jz      loc_1803F2E07
0x1803f2b73  lea     edx, [rbx+12h]
0x1803f2b76  mov     r9d, esi
0x1803f2b79  lea     r8, qword_180CBD248
0x1803f2b80  mov     rcx, [rcx+10h]
0x1803f2b84  call    sub_1801A166C
0x1803f2b89  jmp     loc_1803F2E00
0x1803f2b8e  lea     rdx, aSesecuritypriv; "SeSecurityPrivilege"
0x1803f2b95  lea     rcx, [rsp+98h+var_54]
0x1803f2b9a  call    sub_18024D568
0x1803f2b9f  movzx   esi, ax
0x1803f2ba2  test    eax, eax
0x1803f2ba4  jns     short loc_1803F2BC7
0x1803f2ba6  mov     rcx, cs:hDevice
0x1803f2bad  cmp     rcx, rdi
0x1803f2bb0  jz      loc_1803F2E07
0x1803f2bb6  test    byte ptr [rcx+1Ch], 1
0x1803f2bba  jz      loc_1803F2E07
0x1803f2bc0  mov     edx, 12h
0x1803f2bc5  jmp     short loc_1803F2B76
0x1803f2bc7  mov     ebp, 0C00C0000h
0x1803f2bcc  mov     edi, ebp
0x1803f2bce  mov     eax, 0C10C0000h
0x1803f2bd3  cmp     [rsp+98h+var_54], 1
0x1803f2bd8  cmovz   edi, eax
0x1803f2bdb  cmp     byte ptr [r12], 0
0x1803f2be0  jnz     loc_1803F2CEC
0x1803f2be6  mov     rcx, r14
0x1803f2be9  call    sub_1802EE490
0x1803f2bee  test    al, al
0x1803f2bf0  jnz     loc_1803F2CEC
0x1803f2bf6  mov     eax, r15d
0x1803f2bf9  and     eax, 10h
0x1803f2bfc  or      eax, 20h
0x1803f2bff  shr     eax, 4
0x1803f2c02  mov     [rsp+98h+hTemplateFile], 0; hTemplateFile
0x1803f2c0b  mov     [rsp+98h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x1803f2c13  mov     [rsp+98h+dwCreationDisposition], eax; dwCreationDisposition
0x1803f2c17  xor     r9d, r9d; lpSecurityAttributes
0x1803f2c1a  lea     r8d, [r9+5]; dwShareMode
0x1803f2c1e  mov     edx, edi; dwDesiredAccess
0x1803f2c20  mov     rcx, r14; lpFileName
0x1803f2c23  call    cs:__imp_CreateFileW
0x1803f2c29  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1803f2c2d  jz      short loc_1803F2C37
0x1803f2c2f  mov     rbx, rax
0x1803f2c32  jmp     loc_1803F2E00
0x1803f2c37  call    cs:__imp_GetLastError
0x1803f2c3d  mov     esi, eax
0x1803f2c3f  test    eax, eax
0x1803f2c41  jz      loc_1803F2E0F
0x1803f2c47  cmp     eax, 3
0x1803f2c4a  jz      short loc_1803F2C5D
0x1803f2c4c  cmp     eax, 5
0x1803f2c4f  jz      short loc_1803F2C5D
0x1803f2c51  cmp     eax, 43h ; 'C'
0x1803f2c54  jz      short loc_1803F2C5D
0x1803f2c56  cmp     eax, 522h
0x1803f2c5b  jnz     short loc_1803F2C8A
0x1803f2c5d  mov     rbp, [rsp+98h+var_50]
0x1803f2c62  mov     rax, [rbp+0]
0x1803f2c66  mov     rcx, rbp
0x1803f2c69  mov     rax, [rax+28h]
0x1803f2c6d  call    cs:__guard_dispatch_icall_fptr
0x1803f2c73  mov     rcx, [rax]
0x1803f2c76  mov     ebp, edi
0x1803f2c78  mov     rax, [rcx]
0x1803f2c7b  mov     rax, [rax+18h]
0x1803f2c7f  call    cs:__guard_dispatch_icall_fptr
0x1803f2c85  test    rax, rax
0x1803f2c88  jnz     short loc_1803F2CEC
0x1803f2c8a  mov     rcx, cs:hDevice
0x1803f2c91  lea     rax, hDevice
0x1803f2c98  cmp     rcx, rax
0x1803f2c9b  jz      short loc_1803F2CC0
0x1803f2c9d  test    byte ptr [rcx+1Ch], 1
0x1803f2ca1  jz      short loc_1803F2CC0
0x1803f2ca3  mov     edx, 17h
0x1803f2ca8  mov     [rsp+98h+dwCreationDisposition], esi
0x1803f2cac  mov     r9, r14
0x1803f2caf  lea     r8, qword_180CBD248
0x1803f2cb6  mov     rcx, [rcx+10h]
0x1803f2cba  call    sub_1801A569C
0x1803f2cbf  nop
0x1803f2cc0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1803f2cc4  cmp     rbx, rax
0x1803f2cc7  jz      short loc_1803F2CD2
0x1803f2cc9  mov     rcx, rbx; hObject
0x1803f2ccc  call    cs:__imp_CloseHandle
0x1803f2cd2  mov     eax, esi
0x1803f2cd4  mov     rbx, [rsp+98h+arg_10]
0x1803f2cdc  add     rsp, 60h
0x1803f2ce0  pop     r15
0x1803f2ce2  pop     r14
0x1803f2ce4  pop     r13
0x1803f2ce6  pop     r12
0x1803f2ce8  pop     rdi
0x1803f2ce9  pop     rsi
0x1803f2cea  pop     rbp
0x1803f2ceb  retn
0x1803f2cec  mov     byte ptr [r12], 1
0x1803f2cf1  xor     dil, dil
0x1803f2cf4  mov     [rsp+98h+var_58], dil
0x1803f2cf9  mov     rcx, [rsp+98h+var_50]
0x1803f2cfe  mov     rax, [rcx]
0x1803f2d01  mov     rax, [rax+28h]
0x1803f2d05  call    cs:__guard_dispatch_icall_fptr
0x1803f2d0b  mov     rcx, [rax]
0x1803f2d0e  mov     rax, [rcx]
0x1803f2d11  mov     rax, [rax+18h]
0x1803f2d15  call    cs:__guard_dispatch_icall_fptr
0x1803f2d1b  test    rax, rax
0x1803f2d1e  jz      loc_1803F2DF1
0x1803f2d24  mov     rdx, rax; Token
0x1803f2d27  xor     ecx, ecx; Thread
0x1803f2d29  call    cs:SetThreadToken
0x1803f2d2f  test    eax, eax
0x1803f2d31  jnz     short loc_1803F2D3B
0x1803f2d33  call    cs:__imp_GetLastError
0x1803f2d39  jmp     short loc_1803F2D40
0x1803f2d3b  mov     dil, 1
0x1803f2d3e  xor     eax, eax
0x1803f2d40  test    eax, eax
0x1803f2d42  jnz     loc_1803F2DF1
0x1803f2d48  mov     rcx, r14
0x1803f2d4b  call    sub_1802EE490
0x1803f2d50  mov     r12d, 1000000h
0x1803f2d56  test    al, al
0x1803f2d58  jnz     short loc_1803F2D5D
0x1803f2d5a  or      ebp, r12d
0x1803f2d5d  and     r15d, 10h
0x1803f2d61  or      r15d, 20h
0x1803f2d65  shr     r15d, 4
0x1803f2d69  mov     [rsp+98h+hTemplateFile], 0; hTemplateFile
0x1803f2d72  mov     [rsp+98h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x1803f2d7a  mov     [rsp+98h+dwCreationDisposition], r15d; dwCreationDisposition
0x1803f2d7f  xor     r9d, r9d; lpSecurityAttributes
0x1803f2d82  lea     r8d, [r9+5]; dwShareMode
0x1803f2d86  mov     edx, ebp; dwDesiredAccess
0x1803f2d88  mov     rcx, r14; lpFileName
0x1803f2d8b  call    cs:__imp_CreateFileW
0x1803f2d91  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1803f2d95  jnz     short loc_1803F2DDE
0x1803f2d97  test    r12d, ebp
0x1803f2d9a  jz      short loc_1803F2DE5
0x1803f2d9c  call    cs:__imp_GetLastError
0x1803f2da2  cmp     eax, 522h
0x1803f2da7  jnz     short loc_1803F2DE5
0x1803f2da9  btr     ebp, 18h
0x1803f2dad  mov     [rsp+98h+hTemplateFile], 0; hTemplateFile
0x1803f2db6  mov     [rsp+98h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x1803f2dbe  mov     [rsp+98h+dwCreationDisposition], r15d; dwCreationDisposition
0x1803f2dc3  xor     r9d, r9d; lpSecurityAttributes
0x1803f2dc6  lea     r8d, [r9+5]; dwShareMode
0x1803f2dca  mov     edx, ebp; dwDesiredAccess
0x1803f2dcc  mov     rcx, r14; lpFileName
0x1803f2dcf  call    cs:__imp_CreateFileW
0x1803f2dd5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1803f2dd9  cmp     rcx, rax
0x1803f2ddc  jz      short loc_1803F2DE5
0x1803f2dde  mov     rbx, rax
0x1803f2de1  xor     esi, esi
0x1803f2de3  jmp     short loc_1803F2DF1
0x1803f2de5  call    cs:__imp_GetLastError
0x1803f2deb  test    esi, esi
0x1803f2ded  jnz     short loc_1803F2DF1
0x1803f2def  mov     esi, eax
0x1803f2df1  test    dil, dil
0x1803f2df4  jz      short loc_1803F2E00
0x1803f2df6  xor     edx, edx; Token
0x1803f2df8  xor     ecx, ecx; Thread
0x1803f2dfa  call    cs:SetThreadToken
0x1803f2e00  mov     rcx, cs:hDevice
0x1803f2e07  test    esi, esi
0x1803f2e09  jnz     loc_1803F2C91
0x1803f2e0f  mov     r8b, 1
0x1803f2e12  mov     rdx, r14; __int64
0x1803f2e15  mov     rcx, rbx; hFile
0x1803f2e18  call    sub_18007DAB0
0x1803f2e1d  test    eax, eax
0x1803f2e1f  jns     short loc_1803F2E5C
0x1803f2e21  mov     rcx, cs:hDevice
0x1803f2e28  lea     rax, hDevice
0x1803f2e2f  cmp     rcx, rax
0x1803f2e32  jz      short loc_1803F2E52
0x1803f2e34  test    byte ptr [rcx+1Ch], 1
0x1803f2e38  jz      short loc_1803F2E52
0x1803f2e3a  mov     edx, 16h
0x1803f2e3f  mov     r9, r14
0x1803f2e42  lea     r8, qword_180CBD248
0x1803f2e49  mov     rcx, [rcx+10h]
0x1803f2e4d  call    sub_1801C8638
0x1803f2e52  mov     esi, 5
0x1803f2e57  jmp     loc_1803F2CC0
0x1803f2e5c  mov     rbp, [rsp+98h+var_50]
0x1803f2e61  mov     rax, [rbp+0]
0x1803f2e65  mov     rdi, [rax+78h]
0x1803f2e69  mov     rcx, [r13+0]
0x1803f2e6d  test    rcx, rcx
0x1803f2e70  jz      short loc_1803F2E87
0x1803f2e72  mov     rax, [rcx]
0x1803f2e75  mov     rax, [rax+8]
0x1803f2e79  call    cs:__guard_dispatch_icall_fptr
0x1803f2e7f  mov     qword ptr [r13+0], 0
0x1803f2e87  mov     [rsp+98h+var_50], rbx
0x1803f2e8c  or      rax, 0FFFFFFFFFFFFFFFFh
0x1803f2e90  mov     rbx, rax
0x1803f2e93  mov     [rsp+98h+var_48], rax
0x1803f2e98  mov     r8, r13
0x1803f2e9b  lea     rdx, [rsp+98h+var_50]
0x1803f2ea0  mov     rcx, rbp
0x1803f2ea3  mov     rax, rdi
0x1803f2ea6  call    cs:__guard_dispatch_icall_fptr
0x1803f2eac  mov     esi, eax
0x1803f2eae  jmp     loc_1803F2CC0
```
