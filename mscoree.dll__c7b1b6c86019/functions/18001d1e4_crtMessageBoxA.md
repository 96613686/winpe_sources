# __crtMessageBoxA

- ea: `0x18001d1e4`
- end: `0x18001d3fd`
- name: `__crtMessageBoxA`
- size: `537`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18001880c`

## callees

- `0x18000f6b0`
- `0x18000f6c0`
- `0x18000f6d0`
- `0x18001d1e4`
- `0x180041ac0`
- `0x180041b90`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18001d257`
- `KERNEL32!GetProcAddress` at `0x18001d27f`
- `KERNEL32!GetProcAddress` at `0x18001d29e`
- `KERNEL32!GetProcAddress` at `0x18001d2bd`
- `KERNEL32!GetProcAddress` at `0x18001d2e1`
- `KERNEL32!GetProcAddress` at `0x18001d257`
- `KERNEL32!GetProcAddress` at `0x18001d27f`
- `KERNEL32!GetProcAddress` at `0x18001d29e`
- `KERNEL32!GetProcAddress` at `0x18001d2bd`
- `KERNEL32!GetProcAddress` at `0x18001d2e1`
- `KERNEL32!LoadLibraryExW` at `0x18001d23b`
- `KERNEL32!LoadLibraryExW` at `0x18001d23b`

## string_xrefs

- `0x18001d232`: `USER32.DLL`

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
  if ( qword_180060CF8 )
    goto LABEL_6;
  Library = LoadLibraryExW(L"USER32.DLL", 0, 0);
  v8 = Library;
  if ( !Library )
    return 0;
  ProcAddress = GetProcAddress(Library, "MessageBoxA");
  if ( !ProcAddress )
    return 0;
  qword_180060CF8 = encode_pointer(ProcAddress);
  v10 = GetProcAddress(v8, "GetActiveWindow");
  qword_180060D00 = encode_pointer(v10);
  v11 = GetProcAddress(v8, "GetLastActivePopup");
  qword_180060D08 = encode_pointer(v11);
  v12 = GetProcAddress(v8, "GetUserObjectInformationA");
  qword_180060D18 = encode_pointer(v12);
  if ( !qword_180060D18 )
  {
LABEL_6:
    v14 = (PVOID)qword_180060D10;
  }
  else
  {
    v13 = GetProcAddress(v8, "GetProcessWindowStation");
    v14 = encode_pointer(v13);
    qword_180060D10 = (__int64)v14;
  }
  v15 = 0;
  if ( v14 == v6
    || qword_180060D18 == v6
    || (v16 = (__int64 (*)(void))decode_pointer(v14),
        v17 = (unsigned int (__fastcall *)(__int64, __int64, __int64 *, __int64, int *))decode_pointer(qword_180060D18),
        v18 = v17,
        !v16)
    || !v17
    || (v19 = v16()) != 0 && v18(v19, 1, &v25, 12, &v24) && (v26 & 1) != 0 )
  {
    if ( qword_180060D00 != v6 )
    {
      v20 = (__int64 (*)(void))decode_pointer(qword_180060D00);
      if ( v20 )
      {
        v15 = v20();
        if ( v15 )
        {
          if ( qword_180060D08 != v6 )
          {
            v21 = (__int64 (__fastcall *)(__int64))decode_pointer(qword_180060D08);
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
  v22 = (__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD))decode_pointer(qword_180060CF8);
  if ( v22 )
    return v22(v15, a1, a2, a3);
  return 0;
}

```

## disassembly

```asm
0x18001d1e4  push    rbx
0x18001d1e6  push    rbp
0x18001d1e7  push    rsi
0x18001d1e8  push    rdi
0x18001d1e9  push    r12
0x18001d1eb  push    r14
0x18001d1ed  push    r15
0x18001d1ef  sub     rsp, 50h
0x18001d1f3  mov     rax, cs:__security_cookie
0x18001d1fa  xor     rax, rsp
0x18001d1fd  mov     [rsp+88h+var_40], rax
0x18001d202  mov     esi, r8d
0x18001d205  mov     r12, rdx
0x18001d208  mov     r15, rcx
0x18001d20b  call    _encoded_null
0x18001d210  mov     rdi, rax
0x18001d213  xor     eax, eax
0x18001d215  cmp     cs:qword_180060CF8, rax
0x18001d21c  mov     [rsp+88h+var_50], rax
0x18001d221  mov     [rsp+88h+var_48], eax
0x18001d225  mov     [rsp+88h+var_58], eax
0x18001d229  jnz     loc_18001D2F8
0x18001d22f  xor     r8d, r8d; dwFlags
0x18001d232  lea     rcx, aUser32Dll_0; "USER32.DLL"
0x18001d239  xor     edx, edx; hFile
0x18001d23b  call    cs:__imp_LoadLibraryExW
0x18001d241  mov     rbx, rax
0x18001d244  test    rax, rax
0x18001d247  jz      loc_18001D3DF
0x18001d24d  lea     rdx, aMessageboxa; "MessageBoxA"
0x18001d254  mov     rcx, rax; hModule
0x18001d257  call    cs:__imp_GetProcAddress
0x18001d25d  test    rax, rax
0x18001d260  jz      loc_18001D3DF
0x18001d266  mov     rcx, rax; Ptr
0x18001d269  call    _encode_pointer
0x18001d26e  lea     rdx, aGetactivewindo; "GetActiveWindow"
0x18001d275  mov     cs:qword_180060CF8, rax
0x18001d27c  mov     rcx, rbx; hModule
0x18001d27f  call    cs:__imp_GetProcAddress
0x18001d285  mov     rcx, rax; Ptr
0x18001d288  call    _encode_pointer
0x18001d28d  lea     rdx, aGetlastactivep; "GetLastActivePopup"
0x18001d294  mov     cs:qword_180060D00, rax
0x18001d29b  mov     rcx, rbx; hModule
0x18001d29e  call    cs:__imp_GetProcAddress
0x18001d2a4  mov     rcx, rax; Ptr
0x18001d2a7  call    _encode_pointer
0x18001d2ac  lea     rdx, aGetuserobjecti_0; "GetUserObjectInformationA"
0x18001d2b3  mov     cs:qword_180060D08, rax
0x18001d2ba  mov     rcx, rbx; hModule
0x18001d2bd  call    cs:__imp_GetProcAddress
0x18001d2c3  mov     rcx, rax; Ptr
0x18001d2c6  call    _encode_pointer
0x18001d2cb  mov     cs:qword_180060D18, rax
0x18001d2d2  test    rax, rax
0x18001d2d5  jz      short loc_18001D2F8
0x18001d2d7  lea     rdx, aGetprocesswind_0; "GetProcessWindowStation"
0x18001d2de  mov     rcx, rbx; hModule
0x18001d2e1  call    cs:__imp_GetProcAddress
0x18001d2e7  mov     rcx, rax; Ptr
0x18001d2ea  call    _encode_pointer
0x18001d2ef  mov     cs:qword_180060D10, rax
0x18001d2f6  jmp     short loc_18001D2FF
0x18001d2f8  mov     rax, cs:qword_180060D10
0x18001d2ff  xor     ebx, ebx
0x18001d301  cmp     rax, rdi
0x18001d304  jz      short loc_18001D374
0x18001d306  cmp     cs:qword_180060D18, rdi
0x18001d30d  jz      short loc_18001D374
0x18001d30f  mov     rcx, rax; Ptr
0x18001d312  call    _decode_pointer
0x18001d317  mov     rcx, cs:qword_180060D18; Ptr
0x18001d31e  mov     rbp, rax
0x18001d321  call    _decode_pointer
0x18001d326  mov     r14, rax
0x18001d329  test    rbp, rbp
0x18001d32c  jz      short loc_18001D374
0x18001d32e  test    rax, rax
0x18001d331  jz      short loc_18001D374
0x18001d333  mov     rax, rbp
0x18001d336  call    cs:__guard_dispatch_icall_fptr
0x18001d33c  test    rax, rax
0x18001d33f  jz      short loc_18001D36E
0x18001d341  lea     rcx, [rsp+88h+var_58]
0x18001d346  mov     [rsp+88h+var_68], rcx
0x18001d34b  lea     r9d, [rbx+0Ch]
0x18001d34f  mov     rcx, rax
0x18001d352  lea     r8, [rsp+88h+var_50]
0x18001d357  mov     rax, r14
0x18001d35a  lea     edx, [rbx+1]
0x18001d35d  call    cs:__guard_dispatch_icall_fptr
0x18001d363  test    eax, eax
0x18001d365  jz      short loc_18001D36E
0x18001d367  test    byte ptr [rsp+88h+var_48], 1
0x18001d36c  jnz     short loc_18001D374
0x18001d36e  bts     esi, 15h
0x18001d372  jmp     short loc_18001D3BA
0x18001d374  mov     rcx, cs:qword_180060D00; Ptr
0x18001d37b  cmp     rcx, rdi
0x18001d37e  jz      short loc_18001D3BA
0x18001d380  call    _decode_pointer
0x18001d385  test    rax, rax
0x18001d388  jz      short loc_18001D3BA
0x18001d38a  call    cs:__guard_dispatch_icall_fptr
0x18001d390  mov     rbx, rax
0x18001d393  test    rax, rax
0x18001d396  jz      short loc_18001D3BA
0x18001d398  mov     rcx, cs:qword_180060D08; Ptr
0x18001d39f  cmp     rcx, rdi
0x18001d3a2  jz      short loc_18001D3BA
0x18001d3a4  call    _decode_pointer
0x18001d3a9  test    rax, rax
0x18001d3ac  jz      short loc_18001D3BA
0x18001d3ae  mov     rcx, rbx
0x18001d3b1  call    cs:__guard_dispatch_icall_fptr
0x18001d3b7  mov     rbx, rax
0x18001d3ba  mov     rcx, cs:qword_180060CF8; Ptr
0x18001d3c1  call    _decode_pointer
0x18001d3c6  test    rax, rax
0x18001d3c9  jz      short loc_18001D3DF
0x18001d3cb  mov     r9d, esi
0x18001d3ce  mov     r8, r12
0x18001d3d1  mov     rdx, r15
0x18001d3d4  mov     rcx, rbx
0x18001d3d7  call    cs:__guard_dispatch_icall_fptr
0x18001d3dd  jmp     short loc_18001D3E1
0x18001d3df  xor     eax, eax
0x18001d3e1  mov     rcx, [rsp+88h+var_40]
0x18001d3e6  xor     rcx, rsp; StackCookie
0x18001d3e9  call    __security_check_cookie
0x18001d3ee  add     rsp, 50h
0x18001d3f2  pop     r15
0x18001d3f4  pop     r14
0x18001d3f6  pop     r12
0x18001d3f8  pop     rdi
0x18001d3f9  pop     rsi
0x18001d3fa  pop     rbp
0x18001d3fb  pop     rbx
0x18001d3fc  retn
```
