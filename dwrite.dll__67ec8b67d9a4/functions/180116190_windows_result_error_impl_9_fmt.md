# windows_result::error::impl$9::fmt

- ea: `0x180116190`
- end: `0x18011680c`
- name: `windows_result::error::impl$9::fmt`
- size: `1660`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180023e40`
- `0x1800250b0`
- `0x180025610`
- `0x180115e60`
- `0x180116190`
- `0x180316190`

## import_xrefs

- `kernel32!HeapFree` at `0x18011667f`
- `kernel32!HeapFree` at `0x1801166a7`
- `kernel32!HeapFree` at `0x18011667f`
- `kernel32!HeapFree` at `0x1801166a7`
- `kernel32!FormatMessageW` at `0x1801165e0`
- `kernel32!FormatMessageW` at `0x1801165e0`
- `kernel32!LoadLibraryExA` at `0x1801165b3`
- `kernel32!LoadLibraryExA` at `0x1801165b3`
- `kernel32!GetProcessHeap` at `0x180116671`
- `kernel32!GetProcessHeap` at `0x180116699`
- `kernel32!GetProcessHeap` at `0x180116671`
- `kernel32!GetProcessHeap` at `0x180116699`
- `oleaut32!SysFreeString` at `0x180116294`
- `oleaut32!SysFreeString` at `0x1801162c2`
- `oleaut32!SysFreeString` at `0x180116496`
- `oleaut32!SysFreeString` at `0x180116545`
- `oleaut32!SysFreeString` at `0x180116294`
- `oleaut32!SysFreeString` at `0x1801162c2`
- `oleaut32!SysFreeString` at `0x180116496`
- `oleaut32!SysFreeString` at `0x180116545`
- `oleaut32!SysStringLen` at `0x1801162a7`
- `oleaut32!SysStringLen` at `0x1801164b9`
- `oleaut32!SysStringLen` at `0x1801164eb`
- `oleaut32!SysStringLen` at `0x1801162a7`
- `oleaut32!SysStringLen` at `0x1801164b9`
- `oleaut32!SysStringLen` at `0x1801164eb`

## string_xrefs

- `0x1801165a4`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall windows_result::error::impl_9::fmt(__int64 *a1, OLECHAR **a2)
{
  OLECHAR *v4; // rdi
  OLECHAR *v5; // r15
  __int64 (__fastcall *v6)(OLECHAR *, char *, __int64); // rsi
  char v7; // al
  DWORD v8; // r12d
  char v9; // r14
  __int64 v10; // r13
  __int64 (__fastcall *v11)(OLECHAR *, char *, __int64); // rdi
  OLECHAR *v12; // rsi
  BSTR v13; // r14
  void (__fastcall *v14)(BSTR, BSTR *, int *, BSTR *, BSTR *); // rax
  char v15; // al
  OLECHAR *v16; // r15
  BSTR v17; // r14
  OLECHAR *v18; // r15
  __int64 v19; // rax
  OLECHAR *v20; // r14
  DWORD v21; // ecx
  HMODULE Library; // rdx
  int v23; // ecx
  __int64 v24; // rax
  void *v25; // r14
  int v26; // ecx
  HANDLE ProcessHeap; // rax
  void *v28; // rsi
  HANDLE v29; // rax
  char v31; // al
  DWORD v32; // eax
  OLECHAR *v33; // [rsp+40h] [rbp-40h]
  BSTR bstrString; // [rsp+48h] [rbp-38h] BYREF
  __int64 v35; // [rsp+50h] [rbp-30h]
  void *v36; // [rsp+58h] [rbp-28h]
  __int64 v37; // [rsp+60h] [rbp-20h]
  __int64 v38; // [rsp+68h] [rbp-18h]
  DWORD v39; // [rsp+7Ch] [rbp-4h] BYREF
  WCHAR Buffer[8]; // [rsp+80h] [rbp+0h] BYREF
  int v41; // [rsp+94h] [rbp+14h] BYREF
  BSTR v42; // [rsp+98h] [rbp+18h] BYREF
  LPVOID lpMem[2]; // [rsp+A0h] [rbp+20h]
  BSTR pbstr; // [rsp+B0h] [rbp+30h] BYREF
  char v45; // [rsp+BFh] [rbp+3Fh]
  __int64 v46; // [rsp+C0h] [rbp+40h]

  v46 = -2;
  v4 = *a2;
  v5 = a2[1];
  v6 = (__int64 (__fastcall *)(OLECHAR *, char *, __int64))*((_QWORD *)v5 + 3);
  v7 = v6(*a2, byte_180405FF8, 5);
  v8 = 0;
  if ( *((_DWORD *)a1 + 2) != 1398755147 )
    v8 = *((_DWORD *)a1 + 2);
  v39 = v8;
  v9 = 1;
  if ( !v7 )
  {
    if ( *((char *)a2 + 18) < 0 )
    {
      if ( (unsigned __int8)v6(
                              v4,
                              " {\n,\n { .. }(\n00010203040506070809101112131415161718192021222324252627282930313233343536373839404142434445464748495051525354555657585960616263646566676869707172737475767778798081828384858687888990919293949596979899library\\core\\src\\fmt\\mod.rs",
                              3) )
        goto LABEL_4;
      LOBYTE(v41) = 1;
      v42 = v4;
      lpMem[0] = v5;
      lpMem[1] = &v41;
      if ( (unsigned __int8)core::fmt::builders::impl_2::write_str(&v42, byte_180405FFD, 4) )
        goto LABEL_4;
      if ( (unsigned __int8)core::fmt::builders::impl_2::write_str(&v42, ": library\\std\\src\\panicking.rs", 2) )
        goto LABEL_4;
      pbstr = (BSTR)&v39;
      *(_QWORD *)Buffer = &pbstr;
      *(_QWORD *)&Buffer[4] = core::fmt::impl_75::fmt_windows_result::hresult::HRESULT_;
      bstrString = (BSTR)&off_180349370;
      v35 = 2;
      v38 = 0;
      v36 = Buffer;
      v37 = 1;
      if ( (unsigned __int8)core::fmt::write(&v42, &qword_180335CC8, &bstrString) )
        goto LABEL_4;
      v15 = core::fmt::builders::impl_2::write_str(
              &v42,
              ",\n { .. }(\n00010203040506070809101112131415161718192021222324252627282930313233343536373839404142434445464748495051525354555657585960616263646566676869707172737475767778798081828384858687888990919293949596979899library\\core\\src\\fmt\\mod.rs",
              2);
    }
    else
    {
      if ( (unsigned __int8)v6(v4, " {  }0x.llvm./rust/deps\\rustc-demangle-0.1.25\\src\\lib.rs", 3)
        || (unsigned __int8)v6(v4, byte_180405FFD, 4)
        || (unsigned __int8)v6(v4, ": library\\std\\src\\panicking.rs", 2) )
      {
        goto LABEL_4;
      }
      *(_QWORD *)Buffer = &v39;
      v42 = Buffer;
      lpMem[0] = core::fmt::impl_75::fmt_windows_result::hresult::HRESULT_;
      bstrString = (BSTR)&off_180349370;
      v35 = 2;
      v38 = 0;
      v36 = &v42;
      v37 = 1;
      v15 = core::fmt::write(v4, v5, &bstrString);
    }
    v9 = v15;
  }
LABEL_4:
  v45 = v9;
  v10 = *a1;
  if ( !v10 )
    goto LABEL_37;
  v33 = v4;
  v11 = v6;
  v12 = v5;
  pbstr = 0;
  bstrString = 0;
  (**(void (__fastcall ***)(__int64, int *, BSTR *))v10)(v10, &dword_18040601C, &bstrString);
  v13 = bstrString;
  if ( !bstrString )
    goto LABEL_29;
  v42 = 0;
  v41 = 0;
  v14 = *(void (__fastcall **)(BSTR, BSTR *, int *, BSTR *, BSTR *))(*(_QWORD *)bstrString + 24LL);
  bstrString = 0;
  v14(v13, &v42, &v41, &pbstr, &bstrString);
  if ( bstrString )
    SysFreeString(bstrString);
  if ( !pbstr )
  {
    v16 = v42;
LABEL_26:
    pbstr = v16;
    goto LABEL_27;
  }
  if ( !SysStringLen(pbstr) )
  {
    v16 = v42;
    if ( pbstr )
      SysFreeString(pbstr);
    goto LABEL_26;
  }
  if ( v42 )
    SysFreeString(v42);
LABEL_27:
  (*(void (__fastcall **)(BSTR))(*(_QWORD *)v13 + 16LL))(v13);
  if ( !pbstr || !SysStringLen(pbstr) )
LABEL_29:
    (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v10 + 40LL))(v10, &pbstr);
  v17 = pbstr;
  v18 = (OLECHAR *)&word_180405FF6;
  if ( pbstr && (LODWORD(v19) = SysStringLen(pbstr), (_DWORD)v19) )
  {
    v19 = (unsigned int)v19;
    v18 = v17;
    while ( 1 )
    {
      v23 = v17[v19 - 1];
      if ( (unsigned int)(v23 - 9) >= 5 && v23 != 32 )
        break;
      if ( !--v19 )
        goto LABEL_33;
    }
  }
  else
  {
LABEL_33:
    v19 = 0;
  }
  bstrString = v18;
  v35 = (__int64)&v18[v19];
  LOWORD(v36) = 0;
  core::iter::traits::iterator::Iterator::collect_core::iter::adapters::map::Map_core::char::decode::DecodeUtf16_core::iter::adapters::cloned::Cloned_core::slice::iter::Iter_u16______alloc::string::impl_0::from_utf16_lossy::closure_env_0__alloc::string::String_(
    &v42,
    &bstrString);
  v20 = v42;
  *(_OWORD *)Buffer = *(_OWORD *)lpMem;
  v5 = v12;
  if ( pbstr )
    SysFreeString(pbstr);
  v6 = v11;
  v4 = v33;
  if ( !__OFSUB__(-(__int64)v20, 1) )
  {
    *(_OWORD *)lpMem = *(_OWORD *)Buffer;
    v42 = v20;
    goto LABEL_56;
  }
LABEL_37:
  *(_QWORD *)Buffer = 0;
  if ( (v8 & 0x10000000) != 0 )
  {
    v8 &= ~0x10000000u;
    Library = LoadLibraryExA("ntdll.dll", 0, 0x1000u);
    v21 = 6912;
  }
  else
  {
    v21 = 4864;
    Library = 0;
  }
  LODWORD(v24) = FormatMessageW(v21, Library, v8, 0, Buffer, 0, 0);
  v25 = *(void **)Buffer;
  if ( *(_QWORD *)Buffer != 0 && (_DWORD)v24 != 0 )
  {
    v24 = (unsigned int)v24;
    while ( 1 )
    {
      v26 = *(unsigned __int16 *)(*(_QWORD *)Buffer + 2 * v24 - 2);
      if ( (unsigned int)(v26 - 9) >= 5 && v26 != 32 )
        break;
      if ( !--v24 )
      {
        v24 = 0;
        break;
      }
    }
    bstrString = *(BSTR *)Buffer;
    v35 = *(_QWORD *)Buffer + 2 * v24;
    LOWORD(v36) = 0;
    core::iter::traits::iterator::Iterator::collect_core::iter::adapters::map::Map_core::char::decode::DecodeUtf16_core::iter::adapters::cloned::Cloned_core::slice::iter::Iter_u16______alloc::string::impl_0::from_utf16_lossy::closure_env_0__alloc::string::String_(
      &v42,
      &bstrString);
    v25 = *(void **)Buffer;
    if ( *(_QWORD *)Buffer )
      goto LABEL_55;
  }
  else
  {
    v42 = 0;
    lpMem[0] = (LPVOID)1;
    lpMem[1] = 0;
    if ( *(_QWORD *)Buffer )
    {
LABEL_55:
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v25);
    }
  }
LABEL_56:
  LOBYTE(v8) = 1;
  if ( v45 )
    goto LABEL_57;
  if ( *((char *)a2 + 18) < 0 )
  {
    LOBYTE(Buffer[0]) = 1;
    bstrString = v4;
    v35 = (__int64)v5;
    v36 = Buffer;
    if ( (unsigned __int8)core::fmt::builders::impl_2::write_str(&bstrString, byte_180406001, 7)
      || (unsigned __int8)core::fmt::builders::impl_2::write_str(&bstrString, ": library\\std\\src\\panicking.rs", 2)
      || (unsigned __int8)core::fmt::impl_18::fmt(lpMem[0], lpMem[1], &bstrString, &qword_180335CC8) )
    {
      goto LABEL_57;
    }
    v31 = core::fmt::builders::impl_2::write_str(
            &bstrString,
            ",\n { .. }(\n00010203040506070809101112131415161718192021222324252627282930313233343536373839404142434445464748495051525354555657585960616263646566676869707172737475767778798081828384858687888990919293949596979899library\\core\\src\\fmt\\mod.rs",
            2);
  }
  else
  {
    if ( (unsigned __int8)v6(
                            v4,
                            ", []::{closureshim# as  mut const ; dyn  + unsafe extern \"\" fn( ->  = falsetrue{ {  }0x.llvm./rust/deps\\rustc-demangle-0.1.25\\src\\lib.rs",
                            2)
      || (unsigned __int8)v6(v4, byte_180406001, 7)
      || (unsigned __int8)v6(v4, ": library\\std\\src\\panicking.rs", 2) )
    {
      goto LABEL_57;
    }
    v31 = core::fmt::impl_18::fmt(lpMem[0], lpMem[1], v4, v5);
  }
  if ( !v31 )
  {
    if ( *((char *)a2 + 18) < 0 )
      v32 = v6(
              v4,
              "}0internal error: entered unreachable code: str::from_utf8() =  was expected to have 1 char, but  chars were foundboolcharstri8i16i32i64i128isizeu8u16u32u64u128usizef32f64!_...{invalid syntax}{recursion limit reached}?'for<> , []::{closureshim# as  mut const ; dyn  + unsafe extern \"\" fn( ->  = falsetrue{ {  }0x.llvm./rust/deps\\rustc-demangle-0.1.25\\src\\lib.rs",
              1);
    else
      v32 = v6(v4, " }0x.llvm./rust/deps\\rustc-demangle-0.1.25\\src\\lib.rs", 2);
    v8 = v32;
  }
LABEL_57:
  if ( v42 )
  {
    v28 = lpMem[0];
    v29 = GetProcessHeap();
    HeapFree(v29, 0, v28);
  }
  return v8;
}

```

## disassembly

```asm
0x180116190  push    rbp
0x180116191  push    r15
0x180116193  push    r14
0x180116195  push    r13
0x180116197  push    r12
0x180116199  push    rsi
0x18011619a  push    rdi
0x18011619b  push    rbx
0x18011619c  sub     rsp, 0C8h
0x1801161a3  lea     rbp, [rsp+100h+Buffer]
0x1801161ab  mov     [rbp+80h+var_40], 0FFFFFFFFFFFFFFFEh
0x1801161b3  mov     rbx, rdx
0x1801161b6  mov     r13, rcx
0x1801161b9  mov     rdi, [rdx]
0x1801161bc  mov     r15, [rdx+8]
0x1801161c0  mov     rsi, [r15+18h]
0x1801161c4  lea     rdx, byte_180405FF8
0x1801161cb  mov     r8d, 5
0x1801161d1  mov     rcx, rdi
0x1801161d4  mov     rax, rsi
0x1801161d7  call    cs:__guard_dispatch_icall_fptr
0x1801161dd  mov     ecx, [r13+8]
0x1801161e1  xor     r12d, r12d
0x1801161e4  cmp     ecx, 535F4F4Bh
0x1801161ea  cmovnz  r12d, ecx
0x1801161ee  mov     [rbp+80h+var_84], r12d
0x1801161f2  mov     r14b, 1
0x1801161f5  test    al, al
0x1801161f7  jz      loc_1801162CD
0x1801161fd  mov     [rbp+80h+var_41], r14b
0x180116201  mov     r13, [r13+0]
0x180116205  test    r13, r13
0x180116208  jz      loc_18011655E
0x18011620e  mov     [rbp+80h+var_C0], rdi
0x180116212  mov     rdi, rsi
0x180116215  mov     rsi, r15
0x180116218  mov     [rbp+80h+pbstr], 0
0x180116220  mov     [rbp+80h+bstrString], 0
0x180116228  mov     rax, [r13+0]
0x18011622c  mov     rax, [rax]
0x18011622f  lea     rdx, dword_18040601C
0x180116236  lea     r15, [rbp+80h+bstrString]
0x18011623a  mov     rcx, r13
0x18011623d  mov     r8, r15
0x180116240  call    cs:__guard_dispatch_icall_fptr
0x180116246  mov     r14, [rbp+80h+bstrString]
0x18011624a  test    r14, r14
0x18011624d  jz      loc_1801164C3
0x180116253  mov     [rbp+80h+var_68], 0
0x18011625b  mov     [rbp+80h+var_6C], 0
0x180116262  mov     rax, [r14]
0x180116265  mov     rax, [rax+18h]
0x180116269  mov     [rbp+80h+bstrString], 0
0x180116271  mov     [rsp+100h+lpBuffer], r15
0x180116276  lea     rdx, [rbp+80h+var_68]
0x18011627a  lea     r8, [rbp+80h+var_6C]
0x18011627e  lea     r9, [rbp+80h+pbstr]
0x180116282  mov     rcx, r14
0x180116285  call    cs:__guard_dispatch_icall_fptr
0x18011628b  mov     rcx, [rbp+80h+bstrString]; bstrString
0x18011628f  test    rcx, rcx
0x180116292  jz      short loc_18011629A
0x180116294  call    cs:__imp_SysFreeString
0x18011629a  mov     rcx, [rbp+80h+pbstr]; pbstr
0x18011629e  test    rcx, rcx
0x1801162a1  jz      loc_180116483
0x1801162a7  call    cs:__imp_SysStringLen
0x1801162ad  test    eax, eax
0x1801162af  jz      loc_180116489
0x1801162b5  mov     rcx, [rbp+80h+var_68]; bstrString
0x1801162b9  test    rcx, rcx
0x1801162bc  jz      loc_1801164A0
0x1801162c2  call    cs:__imp_SysFreeString
0x1801162c8  jmp     loc_1801164A0
0x1801162cd  test    byte ptr [rbx+12h], 80h
0x1801162d1  jnz     loc_180116393
0x1801162d7  lea     rdx, aFmtErrorSShoul+178h; " {  }0x.llvm./rust/deps\\rustc-demangle"...
0x1801162de  mov     r8d, 3
0x1801162e4  mov     rcx, rdi
0x1801162e7  mov     rax, rsi
0x1801162ea  call    cs:__guard_dispatch_icall_fptr
0x1801162f0  test    al, al
0x1801162f2  jnz     loc_1801161FD
0x1801162f8  lea     rdx, byte_180405FFD
0x1801162ff  mov     r8d, 4
0x180116305  mov     rcx, rdi
0x180116308  mov     rax, rsi
0x18011630b  call    cs:__guard_dispatch_icall_fptr
0x180116311  test    al, al
0x180116313  jnz     loc_1801161FD
0x180116319  lea     rdx, aLibraryStdSrcP; ": library\\std\\src\\panicking.rs"
0x180116320  mov     r8d, 2
0x180116326  mov     rcx, rdi
0x180116329  mov     rax, rsi
0x18011632c  call    cs:__guard_dispatch_icall_fptr
0x180116332  test    al, al
0x180116334  jnz     loc_1801161FD
0x18011633a  lea     rax, [rbp+80h+var_84]
0x18011633e  mov     qword ptr [rbp+80h+Buffer], rax
0x180116342  mov     rax, rbp
0x180116345  mov     [rbp+80h+var_68], rax
0x180116349  lea     rax, core__fmt__impl$75__fmt_windows_result__hresult__HRESULT_
0x180116350  mov     [rbp+80h+lpMem], rax
0x180116354  lea     rax, off_180349370; "HRESULT("
0x18011635b  mov     [rbp+80h+bstrString], rax
0x18011635f  mov     [rbp+80h+var_B0], 2
0x180116367  mov     [rbp+80h+var_98], 0
0x18011636f  lea     rax, [rbp+80h+var_68]
0x180116373  mov     [rbp+80h+var_A8], rax
0x180116377  mov     [rbp+80h+var_A0], 1
0x18011637f  lea     r8, [rbp+80h+bstrString]
0x180116383  mov     rcx, rdi
0x180116386  mov     rdx, r15
0x180116389  call    core__fmt__write
0x18011638e  jmp     loc_18011647B
0x180116393  lea     rdx, aExplicitPanici+0B7h; " {\n,\n { .. }(\n0001020304050607080910"...
0x18011639a  mov     r8d, 3
0x1801163a0  mov     rcx, rdi
0x1801163a3  mov     rax, rsi
0x1801163a6  call    cs:__guard_dispatch_icall_fptr
0x1801163ac  test    al, al
0x1801163ae  jnz     loc_1801161FD
0x1801163b4  mov     byte ptr [rbp+80h+var_6C], 1
0x1801163b8  mov     [rbp+80h+var_68], rdi
0x1801163bc  mov     [rbp+80h+lpMem], r15
0x1801163c0  lea     rax, [rbp+80h+var_6C]
0x1801163c4  mov     [rbp+80h+lpMem+8], rax
0x1801163c8  lea     rdx, byte_180405FFD
0x1801163cf  lea     rcx, [rbp+80h+var_68]
0x1801163d3  mov     r8d, 4
0x1801163d9  call    core__fmt__builders__impl$2__write_str
0x1801163de  test    al, al
0x1801163e0  jnz     loc_1801161FD
0x1801163e6  lea     rdx, aLibraryStdSrcP; ": library\\std\\src\\panicking.rs"
0x1801163ed  lea     rcx, [rbp+80h+var_68]
0x1801163f1  mov     r8d, 2
0x1801163f7  call    core__fmt__builders__impl$2__write_str
0x1801163fc  test    al, al
0x1801163fe  jnz     loc_1801161FD
0x180116404  lea     rax, [rbp+80h+var_84]
0x180116408  mov     [rbp+80h+pbstr], rax
0x18011640c  lea     rax, [rbp+80h+pbstr]
0x180116410  mov     qword ptr [rbp+80h+Buffer], rax
0x180116414  lea     rax, core__fmt__impl$75__fmt_windows_result__hresult__HRESULT_
0x18011641b  mov     qword ptr [rbp+80h+Buffer+8], rax
0x18011641f  lea     rax, off_180349370; "HRESULT("
0x180116426  mov     [rbp+80h+bstrString], rax
0x18011642a  mov     [rbp+80h+var_B0], 2
0x180116432  mov     [rbp+80h+var_98], 0
0x18011643a  mov     rax, rbp
0x18011643d  mov     [rbp+80h+var_A8], rax
0x180116441  mov     [rbp+80h+var_A0], 1
0x180116449  lea     rdx, qword_180335CC8
0x180116450  lea     rcx, [rbp+80h+var_68]
0x180116454  lea     r8, [rbp+80h+bstrString]
0x180116458  call    core__fmt__write
0x18011645d  test    al, al
0x18011645f  jnz     loc_1801161FD
0x180116465  lea     rdx, aExplicitPanici+0BAh; ",\n { .. }(\n00010203040506070809101112"...
0x18011646c  lea     rcx, [rbp+80h+var_68]
0x180116470  mov     r8d, 2
0x180116476  call    core__fmt__builders__impl$2__write_str
0x18011647b  mov     r14d, eax
0x18011647e  jmp     loc_1801161FD
0x180116483  mov     r15, [rbp+80h+var_68]
0x180116487  jmp     short loc_18011649C
0x180116489  mov     rcx, [rbp+80h+pbstr]; bstrString
0x18011648d  mov     r15, [rbp+80h+var_68]
0x180116491  test    rcx, rcx
0x180116494  jz      short loc_18011649C
0x180116496  call    cs:__imp_SysFreeString
0x18011649c  mov     [rbp+80h+pbstr], r15
0x1801164a0  mov     rax, [r14]
0x1801164a3  mov     rax, [rax+10h]
0x1801164a7  mov     rcx, r14
0x1801164aa  call    cs:__guard_dispatch_icall_fptr
0x1801164b0  mov     rcx, [rbp+80h+pbstr]; pbstr
0x1801164b4  test    rcx, rcx
0x1801164b7  jz      short loc_1801164C3
0x1801164b9  call    cs:__imp_SysStringLen
0x1801164bf  test    eax, eax
0x1801164c1  jnz     short loc_1801164D8
0x1801164c3  mov     rax, [r13+0]
0x1801164c7  mov     rax, [rax+28h]
0x1801164cb  lea     rdx, [rbp+80h+pbstr]
0x1801164cf  mov     rcx, r13
0x1801164d2  call    cs:__guard_dispatch_icall_fptr
0x1801164d8  mov     r14, [rbp+80h+pbstr]
0x1801164dc  lea     r15, word_180405FF6
0x1801164e3  test    r14, r14
0x1801164e6  jz      short loc_180116505
0x1801164e8  mov     rcx, r14; pbstr
0x1801164eb  call    cs:__imp_SysStringLen
0x1801164f1  test    eax, eax
0x1801164f3  jz      short loc_180116505
0x1801164f5  mov     eax, eax
0x1801164f7  mov     r15, r14
0x1801164fa  test    rax, rax
0x1801164fd  jnz     loc_180116585
0x180116503  jmp     short loc_18011650C
0x180116505  xor     eax, eax
0x180116507  test    rax, rax
0x18011650a  jnz     short loc_180116585
0x18011650c  xor     eax, eax
0x18011650e  lea     rax, [r15+rax*2]
0x180116512  mov     [rbp+80h+bstrString], r15
0x180116516  mov     [rbp+80h+var_B0], rax
0x18011651a  mov     word ptr [rbp+80h+var_A8], 0
0x180116520  lea     rcx, [rbp+80h+var_68]
0x180116524  lea     rdx, [rbp+80h+bstrString]
0x180116528  call    core__iter__traits__iterator__Iterator__collect_core__iter__adapters__map__Map_core__char__decode__DecodeUtf16_core__iter__adapters__cloned__Cloned_core__slice__iter__Iter_u16______alloc__string__impl$0__from_utf16_lossy__closure_env$0__alloc__string__String_
0x18011652d  mov     r14, [rbp+80h+var_68]
0x180116531  movups  xmm0, xmmword ptr [rbp+80h+lpMem]
0x180116535  movaps  xmmword ptr [rbp+80h+Buffer], xmm0
0x180116539  mov     rcx, [rbp+80h+pbstr]; bstrString
0x18011653d  test    rcx, rcx
0x180116540  mov     r15, rsi
0x180116543  jz      short loc_18011654B
0x180116545  call    cs:__imp_SysFreeString
0x18011654b  mov     rax, r14
0x18011654e  neg     rax
0x180116551  mov     rsi, rdi
0x180116554  mov     rdi, [rbp+80h+var_C0]
0x180116558  jno     loc_180116639
0x18011655e  mov     qword ptr [rbp+80h+Buffer], 0
0x180116566  test    r12d, 10000000h
0x18011656d  jnz     short loc_18011659D
0x18011656f  mov     ecx, 1300h
0x180116574  xor     edx, edx
0x180116576  jmp     short loc_1801165C1
0x180116580  dec     rax
0x180116583  jz      short loc_18011650C
0x180116585  movzx   ecx, word ptr [r15+rax*2-2]
0x18011658b  lea     edx, [rcx-9]
0x18011658e  cmp     edx, 5
0x180116591  jb      short loc_180116580
0x180116593  cmp     ecx, 20h ; ' '
0x180116596  jz      short loc_180116580
0x180116598  jmp     loc_18011650E
0x18011659d  and     r12d, 0EFFFFFFFh
0x1801165a4  lea     rcx, LibFileName; "ntdll.dll"
0x1801165ab  xor     edx, edx; hFile
0x1801165ad  mov     r8d, 1000h; dwFlags
0x1801165b3  call    cs:__imp_LoadLibraryExA
0x1801165b9  mov     rdx, rax; lpSource
0x1801165bc  mov     ecx, 1B00h; dwFlags
0x1801165c1  mov     rax, rbp
0x1801165c4  mov     [rsp+100h+lpBuffer], rax; lpBuffer
0x1801165c9  mov     [rsp+100h+Arguments], 0; Arguments
0x1801165d2  mov     [rsp+100h+nSize], 0; nSize
0x1801165da  mov     r8d, r12d; dwMessageId
0x1801165dd  xor     r9d, r9d; dwLanguageId
0x1801165e0  call    cs:__imp_FormatMessageW
0x1801165e6  mov     r14, qword ptr [rbp+80h+Buffer]
0x1801165ea  test    r14, r14
0x1801165ed  setnz   cl
0x1801165f0  test    eax, eax
0x1801165f2  setnz   dl
0x1801165f5  test    dl, cl
0x1801165f7  jz      short loc_18011661A
0x1801165f9  mov     eax, eax
0x1801165fb  jmp     short loc_180116605
0x180116600  dec     rax
0x180116603  jz      short loc_180116647
0x180116605  movzx   ecx, word ptr [r14+rax*2-2]
0x18011660b  lea     edx, [rcx-9]
0x18011660e  cmp     edx, 5
0x180116611  jb      short loc_180116600
0x180116613  cmp     ecx, 20h ; ' '
0x180116616  jz      short loc_180116600
0x180116618  jmp     short loc_180116649
0x18011661a  mov     [rbp+80h+var_68], 0
0x180116622  mov     [rbp+80h+lpMem], 1
0x18011662a  mov     [rbp+80h+lpMem+8], 0
0x180116632  test    r14, r14
0x180116635  jnz     short loc_180116671
0x180116637  jmp     short loc_180116685
0x180116639  movaps  xmm0, xmmword ptr [rbp+80h+Buffer]
0x18011663d  movups  xmmword ptr [rbp+80h+lpMem], xmm0
0x180116641  mov     [rbp+80h+var_68], r14
0x180116645  jmp     short loc_180116685
0x180116647  xor     eax, eax
0x180116649  lea     rax, [r14+rax*2]
0x18011664d  mov     [rbp+80h+bstrString], r14
0x180116651  mov     [rbp+80h+var_B0], rax
0x180116655  mov     word ptr [rbp+80h+var_A8], 0
0x18011665b  lea     rcx, [rbp+80h+var_68]
0x18011665f  lea     rdx, [rbp+80h+bstrString]
0x180116663  call    core__iter__traits__iterator__Iterator__collect_core__iter__adapters__map__Map_core__char__decode__DecodeUtf16_core__iter__adapters__cloned__Cloned_core__slice__iter__Iter_u16______alloc__string__impl$0__from_utf16_lossy__closure_env$0__alloc__string__String_
0x180116668  mov     r14, qword ptr [rbp+80h+Buffer]
0x18011666c  test    r14, r14
0x18011666f  jz      short loc_180116685
0x180116671  call    cs:__imp_GetProcessHeap
0x180116677  mov     rcx, rax; hHeap
0x18011667a  xor     edx, edx; dwFlags
0x18011667c  mov     r8, r14; lpMem
0x18011667f  call    cs:__imp_HeapFree
0x180116685  mov     r12b, 1
0x180116688  cmp     [rbp+80h+var_41], 0
0x18011668c  jz      short loc_1801166C4
  ... truncated ...
```
