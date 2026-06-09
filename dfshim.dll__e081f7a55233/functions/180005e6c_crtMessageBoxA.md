# __crtMessageBoxA

- ea: `0x180005e6c`
- end: `0x180006085`
- name: `__crtMessageBoxA`
- size: `537`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180004720`

## callees

- `0x180001ae4`
- `0x180001af4`
- `0x180001b04`
- `0x180005e6c`
- `0x180127dc0`
- `0x180127e00`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180005edf`
- `KERNEL32!GetProcAddress` at `0x180005f07`
- `KERNEL32!GetProcAddress` at `0x180005f26`
- `KERNEL32!GetProcAddress` at `0x180005f45`
- `KERNEL32!GetProcAddress` at `0x180005f69`
- `KERNEL32!GetProcAddress` at `0x180005edf`
- `KERNEL32!GetProcAddress` at `0x180005f07`
- `KERNEL32!GetProcAddress` at `0x180005f26`
- `KERNEL32!GetProcAddress` at `0x180005f45`
- `KERNEL32!GetProcAddress` at `0x180005f69`
- `KERNEL32!LoadLibraryExW` at `0x180005ec3`
- `KERNEL32!LoadLibraryExW` at `0x180005ec3`

## string_xrefs

- `0x180005eba`: `USER32.DLL`

## pseudocode

```c
__int64 __fastcall _crtMessageBoxA(__int64 a1, __int64 a2, unsigned int a3)
{
  PVOID v6; // rdi
  HMODULE Library; // rax
  HMODULE v8; // rbx
  FARPROC ProcAddress; // rax
  FARPROC v10; // rax
  FARPROC v11; // rax
  FARPROC v12; // rax
  FARPROC v13; // rax
  PVOID v14; // rax
  __int64 v15; // rbx
  __int64 (*v16)(void); // rbp
  unsigned int (__fastcall *v17)(__int64, __int64, __int64 *, __int64, int *); // rax
  unsigned int (__fastcall *v18)(__int64, __int64, __int64 *, __int64, int *); // r14
  __int64 v19; // rax
  __int64 (*v20)(void); // rax
  __int64 (__fastcall *v21)(__int64); // rax
  __int64 (__fastcall *v22)(__int64, __int64, __int64, _QWORD); // rax
  int v24; // [rsp+30h] [rbp-58h] BYREF
  __int64 v25; // [rsp+38h] [rbp-50h] BYREF
  int v26; // [rsp+40h] [rbp-48h]

  v6 = (PVOID)encoded_null();
  v25 = 0;
  v26 = 0;
  v24 = 0;
  if ( qword_1801666A0 )
    goto LABEL_6;
  Library = LoadLibraryExW(L"USER32.DLL", 0, 0);
  v8 = Library;
  if ( !Library )
    return 0;
  ProcAddress = GetProcAddress(Library, "MessageBoxA");
  if ( !ProcAddress )
    return 0;
  qword_1801666A0 = encode_pointer(ProcAddress);
  v10 = GetProcAddress(v8, "GetActiveWindow");
  qword_1801666A8 = encode_pointer(v10);
  v11 = GetProcAddress(v8, "GetLastActivePopup");
  qword_1801666B0 = encode_pointer(v11);
  v12 = GetProcAddress(v8, "GetUserObjectInformationA");
  qword_1801666C0 = encode_pointer(v12);
  if ( !qword_1801666C0 )
  {
LABEL_6:
    v14 = (PVOID)qword_1801666B8;
  }
  else
  {
    v13 = GetProcAddress(v8, "GetProcessWindowStation");
    v14 = encode_pointer(v13);
    qword_1801666B8 = (__int64)v14;
  }
  v15 = 0;
  if ( v14 == v6
    || qword_1801666C0 == v6
    || (v16 = (__int64 (*)(void))decode_pointer(v14),
        v17 = (unsigned int (__fastcall *)(__int64, __int64, __int64 *, __int64, int *))decode_pointer(qword_1801666C0),
        v18 = v17,
        !v16)
    || !v17
    || (v19 = v16()) != 0 && v18(v19, 1, &v25, 12, &v24) && (v26 & 1) != 0 )
  {
    if ( qword_1801666A8 != v6 )
    {
      v20 = (__int64 (*)(void))decode_pointer(qword_1801666A8);
      if ( v20 )
      {
        v15 = v20();
        if ( v15 )
        {
          if ( qword_1801666B0 != v6 )
          {
            v21 = (__int64 (__fastcall *)(__int64))decode_pointer(qword_1801666B0);
            if ( v21 )
              v15 = v21(v15);
          }
        }
      }
    }
  }
  else
  {
    a3 |= 0x200000u;
  }
  v22 = (__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD))decode_pointer(qword_1801666A0);
  if ( v22 )
    return v22(v15, a1, a2, a3);
  return 0;
}

```

## disassembly

```asm
0x180005e6c  push    rbx
0x180005e6e  push    rbp
0x180005e6f  push    rsi
0x180005e70  push    rdi
0x180005e71  push    r12
0x180005e73  push    r14
0x180005e75  push    r15
0x180005e77  sub     rsp, 50h
0x180005e7b  mov     rax, cs:__security_cookie
0x180005e82  xor     rax, rsp
0x180005e85  mov     [rsp+88h+var_40], rax
0x180005e8a  mov     esi, r8d
0x180005e8d  mov     r12, rdx
0x180005e90  mov     r15, rcx
0x180005e93  call    _encoded_null
0x180005e98  mov     rdi, rax
0x180005e9b  xor     eax, eax
0x180005e9d  cmp     cs:qword_1801666A0, rax
0x180005ea4  mov     [rsp+88h+var_50], rax
0x180005ea9  mov     [rsp+88h+var_48], eax
0x180005ead  mov     [rsp+88h+var_58], eax
0x180005eb1  jnz     loc_180005F80
0x180005eb7  xor     r8d, r8d; dwFlags
0x180005eba  lea     rcx, LibFileName; "USER32.DLL"
0x180005ec1  xor     edx, edx; hFile
0x180005ec3  call    cs:__imp_LoadLibraryExW
0x180005ec9  mov     rbx, rax
0x180005ecc  test    rax, rax
0x180005ecf  jz      loc_180006067
0x180005ed5  lea     rdx, aMessageboxa; "MessageBoxA"
0x180005edc  mov     rcx, rax; hModule
0x180005edf  call    cs:__imp_GetProcAddress
0x180005ee5  test    rax, rax
0x180005ee8  jz      loc_180006067
0x180005eee  mov     rcx, rax; Ptr
0x180005ef1  call    _encode_pointer
0x180005ef6  lea     rdx, aGetactivewindo; "GetActiveWindow"
0x180005efd  mov     cs:qword_1801666A0, rax
0x180005f04  mov     rcx, rbx; hModule
0x180005f07  call    cs:__imp_GetProcAddress
0x180005f0d  mov     rcx, rax; Ptr
0x180005f10  call    _encode_pointer
0x180005f15  lea     rdx, aGetlastactivep; "GetLastActivePopup"
0x180005f1c  mov     cs:qword_1801666A8, rax
0x180005f23  mov     rcx, rbx; hModule
0x180005f26  call    cs:__imp_GetProcAddress
0x180005f2c  mov     rcx, rax; Ptr
0x180005f2f  call    _encode_pointer
0x180005f34  lea     rdx, aGetuserobjecti; "GetUserObjectInformationA"
0x180005f3b  mov     cs:qword_1801666B0, rax
0x180005f42  mov     rcx, rbx; hModule
0x180005f45  call    cs:__imp_GetProcAddress
0x180005f4b  mov     rcx, rax; Ptr
0x180005f4e  call    _encode_pointer
0x180005f53  mov     cs:qword_1801666C0, rax
0x180005f5a  test    rax, rax
0x180005f5d  jz      short loc_180005F80
0x180005f5f  lea     rdx, aGetprocesswind; "GetProcessWindowStation"
0x180005f66  mov     rcx, rbx; hModule
0x180005f69  call    cs:__imp_GetProcAddress
0x180005f6f  mov     rcx, rax; Ptr
0x180005f72  call    _encode_pointer
0x180005f77  mov     cs:qword_1801666B8, rax
0x180005f7e  jmp     short loc_180005F87
0x180005f80  mov     rax, cs:qword_1801666B8
0x180005f87  xor     ebx, ebx
0x180005f89  cmp     rax, rdi
0x180005f8c  jz      short loc_180005FFC
0x180005f8e  cmp     cs:qword_1801666C0, rdi
0x180005f95  jz      short loc_180005FFC
0x180005f97  mov     rcx, rax; Ptr
0x180005f9a  call    _decode_pointer
0x180005f9f  mov     rcx, cs:qword_1801666C0; Ptr
0x180005fa6  mov     rbp, rax
0x180005fa9  call    _decode_pointer
0x180005fae  mov     r14, rax
0x180005fb1  test    rbp, rbp
0x180005fb4  jz      short loc_180005FFC
0x180005fb6  test    rax, rax
0x180005fb9  jz      short loc_180005FFC
0x180005fbb  mov     rax, rbp
0x180005fbe  call    cs:__guard_dispatch_icall_fptr
0x180005fc4  test    rax, rax
0x180005fc7  jz      short loc_180005FF6
0x180005fc9  lea     rcx, [rsp+88h+var_58]
0x180005fce  mov     [rsp+88h+var_68], rcx
0x180005fd3  lea     r9d, [rbx+0Ch]
0x180005fd7  mov     rcx, rax
0x180005fda  lea     r8, [rsp+88h+var_50]
0x180005fdf  mov     rax, r14
0x180005fe2  lea     edx, [rbx+1]
0x180005fe5  call    cs:__guard_dispatch_icall_fptr
0x180005feb  test    eax, eax
0x180005fed  jz      short loc_180005FF6
0x180005fef  test    byte ptr [rsp+88h+var_48], 1
0x180005ff4  jnz     short loc_180005FFC
0x180005ff6  bts     esi, 15h
0x180005ffa  jmp     short loc_180006042
0x180005ffc  mov     rcx, cs:qword_1801666A8; Ptr
0x180006003  cmp     rcx, rdi
0x180006006  jz      short loc_180006042
0x180006008  call    _decode_pointer
0x18000600d  test    rax, rax
0x180006010  jz      short loc_180006042
0x180006012  call    cs:__guard_dispatch_icall_fptr
0x180006018  mov     rbx, rax
0x18000601b  test    rax, rax
0x18000601e  jz      short loc_180006042
0x180006020  mov     rcx, cs:qword_1801666B0; Ptr
0x180006027  cmp     rcx, rdi
0x18000602a  jz      short loc_180006042
0x18000602c  call    _decode_pointer
0x180006031  test    rax, rax
0x180006034  jz      short loc_180006042
0x180006036  mov     rcx, rbx
0x180006039  call    cs:__guard_dispatch_icall_fptr
0x18000603f  mov     rbx, rax
0x180006042  mov     rcx, cs:qword_1801666A0; Ptr
0x180006049  call    _decode_pointer
0x18000604e  test    rax, rax
0x180006051  jz      short loc_180006067
0x180006053  mov     r9d, esi
0x180006056  mov     r8, r12
0x180006059  mov     rdx, r15
0x18000605c  mov     rcx, rbx
0x18000605f  call    cs:__guard_dispatch_icall_fptr
0x180006065  jmp     short loc_180006069
0x180006067  xor     eax, eax
0x180006069  mov     rcx, [rsp+88h+var_40]
0x18000606e  xor     rcx, rsp; StackCookie
0x180006071  call    __security_check_cookie
0x180006076  add     rsp, 50h
0x18000607a  pop     r15
0x18000607c  pop     r14
0x18000607e  pop     r12
0x180006080  pop     rdi
0x180006081  pop     rsi
0x180006082  pop     rbp
0x180006083  pop     rbx
0x180006084  retn
```
