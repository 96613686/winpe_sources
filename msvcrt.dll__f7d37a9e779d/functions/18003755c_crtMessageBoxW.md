# __crtMessageBoxW

- ea: `0x18003755c`
- end: `0x180037775`
- name: `__crtMessageBoxW`
- size: `537`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180030630`

## callees

- `0x18003755c`
- `0x18003de80`
- `0x18003de90`
- `0x18003dea0`
- `0x180079760`
- `0x1800798c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800375cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800375f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037616`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037635`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037659`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800375cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800375f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037616`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037635`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037659`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800375b3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800375b3`

## string_xrefs

- `0x1800375aa`: `USER32.DLL`

## pseudocode

```c
__int64 __fastcall _crtMessageBoxW(__int64 a1, __int64 a2, unsigned int a3)
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
  if ( qword_18009E858 )
    goto LABEL_6;
  Library = LoadLibraryExW(L"USER32.DLL", 0, 0);
  v8 = Library;
  if ( !Library )
    return 0;
  ProcAddress = GetProcAddress(Library, "MessageBoxW");
  if ( !ProcAddress )
    return 0;
  qword_18009E858 = encode_pointer(ProcAddress);
  v10 = GetProcAddress(v8, "GetActiveWindow");
  qword_18009E860 = encode_pointer(v10);
  v11 = GetProcAddress(v8, "GetLastActivePopup");
  qword_18009E868 = encode_pointer(v11);
  v12 = GetProcAddress(v8, "GetUserObjectInformationW");
  qword_18009E878 = encode_pointer(v12);
  if ( !qword_18009E878 )
  {
LABEL_6:
    v14 = (PVOID)qword_18009E870;
  }
  else
  {
    v13 = GetProcAddress(v8, "GetProcessWindowStation");
    v14 = encode_pointer(v13);
    qword_18009E870 = (__int64)v14;
  }
  v15 = 0;
  if ( v14 == v6
    || qword_18009E878 == v6
    || (v16 = (__int64 (*)(void))decode_pointer(v14),
        v17 = (unsigned int (__fastcall *)(__int64, __int64, __int64 *, __int64, int *))decode_pointer(qword_18009E878),
        v18 = v17,
        !v16)
    || !v17
    || (v19 = v16()) != 0 && v18(v19, 1, &v25, 12, &v24) && (v26 & 1) != 0 )
  {
    if ( qword_18009E860 != v6 )
    {
      v20 = (__int64 (*)(void))decode_pointer(qword_18009E860);
      if ( v20 )
      {
        v15 = v20();
        if ( v15 )
        {
          if ( qword_18009E868 != v6 )
          {
            v21 = (__int64 (__fastcall *)(__int64))decode_pointer(qword_18009E868);
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
  v22 = (__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD))decode_pointer(qword_18009E858);
  if ( v22 )
    return v22(v15, a1, a2, a3);
  return 0;
}

```

## disassembly

```asm
0x18003755c  push    rbx
0x18003755e  push    rbp
0x18003755f  push    rsi
0x180037560  push    rdi
0x180037561  push    r12
0x180037563  push    r14
0x180037565  push    r15
0x180037567  sub     rsp, 50h
0x18003756b  mov     rax, cs:__security_cookie
0x180037572  xor     rax, rsp
0x180037575  mov     [rsp+88h+var_40], rax
0x18003757a  mov     esi, r8d
0x18003757d  mov     r12, rdx
0x180037580  mov     r15, rcx
0x180037583  call    _encoded_null
0x180037588  mov     rdi, rax
0x18003758b  xor     eax, eax
0x18003758d  cmp     cs:qword_18009E858, rax
0x180037594  mov     [rsp+88h+var_50], rax
0x180037599  mov     [rsp+88h+var_48], eax
0x18003759d  mov     [rsp+88h+var_58], eax
0x1800375a1  jnz     loc_180037670
0x1800375a7  xor     r8d, r8d; dwFlags
0x1800375aa  lea     rcx, aUser32Dll; "USER32.DLL"
0x1800375b1  xor     edx, edx; hFile
0x1800375b3  call    cs:__imp_LoadLibraryExW
0x1800375b9  mov     rbx, rax
0x1800375bc  test    rax, rax
0x1800375bf  jz      loc_180037757
0x1800375c5  lea     rdx, aMessageboxw; "MessageBoxW"
0x1800375cc  mov     rcx, rax; hModule
0x1800375cf  call    cs:__imp_GetProcAddress
0x1800375d5  test    rax, rax
0x1800375d8  jz      loc_180037757
0x1800375de  mov     rcx, rax; Ptr
0x1800375e1  call    _encode_pointer
0x1800375e6  lea     rdx, aGetactivewindo; "GetActiveWindow"
0x1800375ed  mov     cs:qword_18009E858, rax
0x1800375f4  mov     rcx, rbx; hModule
0x1800375f7  call    cs:__imp_GetProcAddress
0x1800375fd  mov     rcx, rax; Ptr
0x180037600  call    _encode_pointer
0x180037605  lea     rdx, aGetlastactivep; "GetLastActivePopup"
0x18003760c  mov     cs:qword_18009E860, rax
0x180037613  mov     rcx, rbx; hModule
0x180037616  call    cs:__imp_GetProcAddress
0x18003761c  mov     rcx, rax; Ptr
0x18003761f  call    _encode_pointer
0x180037624  lea     rdx, aGetuserobjecti; "GetUserObjectInformationW"
0x18003762b  mov     cs:qword_18009E868, rax
0x180037632  mov     rcx, rbx; hModule
0x180037635  call    cs:__imp_GetProcAddress
0x18003763b  mov     rcx, rax; Ptr
0x18003763e  call    _encode_pointer
0x180037643  mov     cs:qword_18009E878, rax
0x18003764a  test    rax, rax
0x18003764d  jz      short loc_180037670
0x18003764f  lea     rdx, aGetprocesswind; "GetProcessWindowStation"
0x180037656  mov     rcx, rbx; hModule
0x180037659  call    cs:__imp_GetProcAddress
0x18003765f  mov     rcx, rax; Ptr
0x180037662  call    _encode_pointer
0x180037667  mov     cs:qword_18009E870, rax
0x18003766e  jmp     short loc_180037677
0x180037670  mov     rax, cs:qword_18009E870
0x180037677  xor     ebx, ebx
0x180037679  cmp     rax, rdi
0x18003767c  jz      short loc_1800376EC
0x18003767e  cmp     cs:qword_18009E878, rdi
0x180037685  jz      short loc_1800376EC
0x180037687  mov     rcx, rax; Ptr
0x18003768a  call    _decode_pointer
0x18003768f  mov     rcx, cs:qword_18009E878; Ptr
0x180037696  mov     rbp, rax
0x180037699  call    _decode_pointer
0x18003769e  mov     r14, rax
0x1800376a1  test    rbp, rbp
0x1800376a4  jz      short loc_1800376EC
0x1800376a6  test    rax, rax
0x1800376a9  jz      short loc_1800376EC
0x1800376ab  mov     rax, rbp
0x1800376ae  call    cs:__guard_dispatch_icall_fptr
0x1800376b4  test    rax, rax
0x1800376b7  jz      short loc_1800376E6
0x1800376b9  lea     rcx, [rsp+88h+var_58]
0x1800376be  mov     [rsp+88h+var_68], rcx
0x1800376c3  lea     r9d, [rbx+0Ch]
0x1800376c7  mov     rcx, rax
0x1800376ca  lea     r8, [rsp+88h+var_50]
0x1800376cf  mov     rax, r14
0x1800376d2  lea     edx, [rbx+1]
0x1800376d5  call    cs:__guard_dispatch_icall_fptr
0x1800376db  test    eax, eax
0x1800376dd  jz      short loc_1800376E6
0x1800376df  test    byte ptr [rsp+88h+var_48], 1
0x1800376e4  jnz     short loc_1800376EC
0x1800376e6  bts     esi, 15h
0x1800376ea  jmp     short loc_180037732
0x1800376ec  mov     rcx, cs:qword_18009E860; Ptr
0x1800376f3  cmp     rcx, rdi
0x1800376f6  jz      short loc_180037732
0x1800376f8  call    _decode_pointer
0x1800376fd  test    rax, rax
0x180037700  jz      short loc_180037732
0x180037702  call    cs:__guard_dispatch_icall_fptr
0x180037708  mov     rbx, rax
0x18003770b  test    rax, rax
0x18003770e  jz      short loc_180037732
0x180037710  mov     rcx, cs:qword_18009E868; Ptr
0x180037717  cmp     rcx, rdi
0x18003771a  jz      short loc_180037732
0x18003771c  call    _decode_pointer
0x180037721  test    rax, rax
0x180037724  jz      short loc_180037732
0x180037726  mov     rcx, rbx
0x180037729  call    cs:__guard_dispatch_icall_fptr
0x18003772f  mov     rbx, rax
0x180037732  mov     rcx, cs:qword_18009E858; Ptr
0x180037739  call    _decode_pointer
0x18003773e  test    rax, rax
0x180037741  jz      short loc_180037757
0x180037743  mov     r9d, esi
0x180037746  mov     r8, r12
0x180037749  mov     rdx, r15
0x18003774c  mov     rcx, rbx
0x18003774f  call    cs:__guard_dispatch_icall_fptr
0x180037755  jmp     short loc_180037759
0x180037757  xor     eax, eax
0x180037759  mov     rcx, [rsp+88h+var_40]
0x18003775e  xor     rcx, rsp; StackCookie
0x180037761  call    __security_check_cookie
0x180037766  add     rsp, 50h
0x18003776a  pop     r15
0x18003776c  pop     r14
0x18003776e  pop     r12
0x180037770  pop     rdi
0x180037771  pop     rsi
0x180037772  pop     rbp
0x180037773  pop     rbx
0x180037774  retn
```
