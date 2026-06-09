# __crtMessageBoxA

- ea: `0x180036b64`
- end: `0x180036d7d`
- name: `__crtMessageBoxA`
- size: `537`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18002e8e0`
- `0x18003f8e4`

## callees

- `0x180036b64`
- `0x18003de80`
- `0x18003de90`
- `0x18003dea0`
- `0x180079760`
- `0x1800798c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036bd7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036bff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036c1e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036c3d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036c61`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036bd7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036bff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036c1e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036c3d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036c61`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180036bbb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180036bbb`

## string_xrefs

- `0x180036bb2`: `USER32.DLL`

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
  if ( qword_18009E830 )
    goto LABEL_6;
  Library = LoadLibraryExW(L"USER32.DLL", 0, 0);
  v8 = Library;
  if ( !Library )
    return 0;
  ProcAddress = GetProcAddress(Library, "MessageBoxA");
  if ( !ProcAddress )
    return 0;
  qword_18009E830 = encode_pointer(ProcAddress);
  v10 = GetProcAddress(v8, "GetActiveWindow");
  qword_18009E838 = encode_pointer(v10);
  v11 = GetProcAddress(v8, "GetLastActivePopup");
  qword_18009E840 = encode_pointer(v11);
  v12 = GetProcAddress(v8, "GetUserObjectInformationA");
  qword_18009E850 = encode_pointer(v12);
  if ( !qword_18009E850 )
  {
LABEL_6:
    v14 = (PVOID)qword_18009E848;
  }
  else
  {
    v13 = GetProcAddress(v8, "GetProcessWindowStation");
    v14 = encode_pointer(v13);
    qword_18009E848 = (__int64)v14;
  }
  v15 = 0;
  if ( v14 == v6
    || qword_18009E850 == v6
    || (v16 = (__int64 (*)(void))decode_pointer(v14),
        v17 = (unsigned int (__fastcall *)(__int64, __int64, __int64 *, __int64, int *))decode_pointer(qword_18009E850),
        v18 = v17,
        !v16)
    || !v17
    || (v19 = v16()) != 0 && v18(v19, 1, &v25, 12, &v24) && (v26 & 1) != 0 )
  {
    if ( qword_18009E838 != v6 )
    {
      v20 = (__int64 (*)(void))decode_pointer(qword_18009E838);
      if ( v20 )
      {
        v15 = v20();
        if ( v15 )
        {
          if ( qword_18009E840 != v6 )
          {
            v21 = (__int64 (__fastcall *)(__int64))decode_pointer(qword_18009E840);
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
  v22 = (__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD))decode_pointer(qword_18009E830);
  if ( v22 )
    return v22(v15, a1, a2, a3);
  return 0;
}

```

## disassembly

```asm
0x180036b64  push    rbx
0x180036b66  push    rbp
0x180036b67  push    rsi
0x180036b68  push    rdi
0x180036b69  push    r12
0x180036b6b  push    r14
0x180036b6d  push    r15
0x180036b6f  sub     rsp, 50h
0x180036b73  mov     rax, cs:__security_cookie
0x180036b7a  xor     rax, rsp
0x180036b7d  mov     [rsp+88h+var_40], rax
0x180036b82  mov     esi, r8d
0x180036b85  mov     r12, rdx
0x180036b88  mov     r15, rcx
0x180036b8b  call    _encoded_null
0x180036b90  mov     rdi, rax
0x180036b93  xor     eax, eax
0x180036b95  cmp     cs:qword_18009E830, rax
0x180036b9c  mov     [rsp+88h+var_50], rax
0x180036ba1  mov     [rsp+88h+var_48], eax
0x180036ba5  mov     [rsp+88h+var_58], eax
0x180036ba9  jnz     loc_180036C78
0x180036baf  xor     r8d, r8d; dwFlags
0x180036bb2  lea     rcx, aUser32Dll; "USER32.DLL"
0x180036bb9  xor     edx, edx; hFile
0x180036bbb  call    cs:__imp_LoadLibraryExW
0x180036bc1  mov     rbx, rax
0x180036bc4  test    rax, rax
0x180036bc7  jz      loc_180036D5F
0x180036bcd  lea     rdx, aMessageboxa; "MessageBoxA"
0x180036bd4  mov     rcx, rax; hModule
0x180036bd7  call    cs:__imp_GetProcAddress
0x180036bdd  test    rax, rax
0x180036be0  jz      loc_180036D5F
0x180036be6  mov     rcx, rax; Ptr
0x180036be9  call    _encode_pointer
0x180036bee  lea     rdx, aGetactivewindo; "GetActiveWindow"
0x180036bf5  mov     cs:qword_18009E830, rax
0x180036bfc  mov     rcx, rbx; hModule
0x180036bff  call    cs:__imp_GetProcAddress
0x180036c05  mov     rcx, rax; Ptr
0x180036c08  call    _encode_pointer
0x180036c0d  lea     rdx, aGetlastactivep; "GetLastActivePopup"
0x180036c14  mov     cs:qword_18009E838, rax
0x180036c1b  mov     rcx, rbx; hModule
0x180036c1e  call    cs:__imp_GetProcAddress
0x180036c24  mov     rcx, rax; Ptr
0x180036c27  call    _encode_pointer
0x180036c2c  lea     rdx, aGetuserobjecti_0; "GetUserObjectInformationA"
0x180036c33  mov     cs:qword_18009E840, rax
0x180036c3a  mov     rcx, rbx; hModule
0x180036c3d  call    cs:__imp_GetProcAddress
0x180036c43  mov     rcx, rax; Ptr
0x180036c46  call    _encode_pointer
0x180036c4b  mov     cs:qword_18009E850, rax
0x180036c52  test    rax, rax
0x180036c55  jz      short loc_180036C78
0x180036c57  lea     rdx, aGetprocesswind; "GetProcessWindowStation"
0x180036c5e  mov     rcx, rbx; hModule
0x180036c61  call    cs:__imp_GetProcAddress
0x180036c67  mov     rcx, rax; Ptr
0x180036c6a  call    _encode_pointer
0x180036c6f  mov     cs:qword_18009E848, rax
0x180036c76  jmp     short loc_180036C7F
0x180036c78  mov     rax, cs:qword_18009E848
0x180036c7f  xor     ebx, ebx
0x180036c81  cmp     rax, rdi
0x180036c84  jz      short loc_180036CF4
0x180036c86  cmp     cs:qword_18009E850, rdi
0x180036c8d  jz      short loc_180036CF4
0x180036c8f  mov     rcx, rax; Ptr
0x180036c92  call    _decode_pointer
0x180036c97  mov     rcx, cs:qword_18009E850; Ptr
0x180036c9e  mov     rbp, rax
0x180036ca1  call    _decode_pointer
0x180036ca6  mov     r14, rax
0x180036ca9  test    rbp, rbp
0x180036cac  jz      short loc_180036CF4
0x180036cae  test    rax, rax
0x180036cb1  jz      short loc_180036CF4
0x180036cb3  mov     rax, rbp
0x180036cb6  call    cs:__guard_dispatch_icall_fptr
0x180036cbc  test    rax, rax
0x180036cbf  jz      short loc_180036CEE
0x180036cc1  lea     rcx, [rsp+88h+var_58]
0x180036cc6  mov     [rsp+88h+var_68], rcx
0x180036ccb  lea     r9d, [rbx+0Ch]
0x180036ccf  mov     rcx, rax
0x180036cd2  lea     r8, [rsp+88h+var_50]
0x180036cd7  mov     rax, r14
0x180036cda  lea     edx, [rbx+1]
0x180036cdd  call    cs:__guard_dispatch_icall_fptr
0x180036ce3  test    eax, eax
0x180036ce5  jz      short loc_180036CEE
0x180036ce7  test    byte ptr [rsp+88h+var_48], 1
0x180036cec  jnz     short loc_180036CF4
0x180036cee  bts     esi, 15h
0x180036cf2  jmp     short loc_180036D3A
0x180036cf4  mov     rcx, cs:qword_18009E838; Ptr
0x180036cfb  cmp     rcx, rdi
0x180036cfe  jz      short loc_180036D3A
0x180036d00  call    _decode_pointer
0x180036d05  test    rax, rax
0x180036d08  jz      short loc_180036D3A
0x180036d0a  call    cs:__guard_dispatch_icall_fptr
0x180036d10  mov     rbx, rax
0x180036d13  test    rax, rax
0x180036d16  jz      short loc_180036D3A
0x180036d18  mov     rcx, cs:qword_18009E840; Ptr
0x180036d1f  cmp     rcx, rdi
0x180036d22  jz      short loc_180036D3A
0x180036d24  call    _decode_pointer
0x180036d29  test    rax, rax
0x180036d2c  jz      short loc_180036D3A
0x180036d2e  mov     rcx, rbx
0x180036d31  call    cs:__guard_dispatch_icall_fptr
0x180036d37  mov     rbx, rax
0x180036d3a  mov     rcx, cs:qword_18009E830; Ptr
0x180036d41  call    _decode_pointer
0x180036d46  test    rax, rax
0x180036d49  jz      short loc_180036D5F
0x180036d4b  mov     r9d, esi
0x180036d4e  mov     r8, r12
0x180036d51  mov     rdx, r15
0x180036d54  mov     rcx, rbx
0x180036d57  call    cs:__guard_dispatch_icall_fptr
0x180036d5d  jmp     short loc_180036D61
0x180036d5f  xor     eax, eax
0x180036d61  mov     rcx, [rsp+88h+var_40]
0x180036d66  xor     rcx, rsp; StackCookie
0x180036d69  call    __security_check_cookie
0x180036d6e  add     rsp, 50h
0x180036d72  pop     r15
0x180036d74  pop     r14
0x180036d76  pop     r12
0x180036d78  pop     rdi
0x180036d79  pop     rsi
0x180036d7a  pop     rbp
0x180036d7b  pop     rbx
0x180036d7c  retn
```
