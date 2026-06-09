# CCMLuaUtil::CallCustomActionDll(ushort const *,ushort const *,ushort const *,ushort const *,ulong *)

- ea: `0x180002420`
- end: `0x1800026aa`
- name: `?CallCustomActionDll@CCMLuaUtil@@UEAAJPEBG000PEAK@Z`
- size: `650`
- prototype: `__int64 __fastcall(CCMLuaUtil *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002420`
- `0x18000440c`
- `0x180004e1c`
- `0x180006010`

## import_xrefs

- `cmutil!CmFree` at `0x1800024f5`
- `cmutil!CmFree` at `0x180002564`
- `cmutil!CmFree` at `0x18000256d`
- `cmutil!CmFree` at `0x1800024f5`
- `cmutil!CmFree` at `0x180002564`
- `cmutil!CmFree` at `0x18000256d`
- `cmutil!WzToSzWithAlloc` at `0x1800024b8`
- `cmutil!WzToSzWithAlloc` at `0x180002507`
- `cmutil!WzToSzWithAlloc` at `0x1800024b8`
- `cmutil!WzToSzWithAlloc` at `0x180002507`
- `KERNEL32!FreeLibrary` at `0x1800024d1`
- `KERNEL32!FreeLibrary` at `0x180002691`
- `KERNEL32!FreeLibrary` at `0x1800024d1`
- `KERNEL32!FreeLibrary` at `0x180002691`
- `KERNEL32!LoadLibraryExW` at `0x180002463`
- `KERNEL32!LoadLibraryExW` at `0x180002463`
- `KERNEL32!GetProcAddress` at `0x1800024e9`
- `KERNEL32!GetProcAddress` at `0x1800024e9`
- `KERNEL32!GetLastError` at `0x180002476`
- `KERNEL32!GetLastError` at `0x1800024c6`
- `KERNEL32!GetLastError` at `0x18000265a`
- `KERNEL32!GetLastError` at `0x180002476`
- `KERNEL32!GetLastError` at `0x1800024c6`
- `KERNEL32!GetLastError` at `0x18000265a`

## string_xrefs

- `0x180002481`: `RunAsDll() LoadLibrary(%s) failed, GLE=%u.`
- `0x1800024da`: `RunAsDll() WzToSzWithAlloc(%s) failed, GLE=%u.`
- `0x180002584`: `RunAsDll() Executed module: %s`
- `0x1800025f1`: `Exception in RunAsDll() Module: %s`
- `0x18000267f`: `RunAsDll() GetProcAddress(*pszwModuleName=%s,*pszFunction=%s) failed, GLE=%u.`

## pseudocode

```c
__int64 __fastcall CCMLuaUtil::CallCustomActionDll(
        CCMLuaUtil *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        unsigned int *a6)
{
  const wchar_t *v8; // rbx
  unsigned int *v9; // r14
  HMODULE Library; // rsi
  DWORD LastError; // edi
  __int64 v12; // r9
  const wchar_t *v13; // rdx
  const CHAR *v15; // rax
  CHAR *v16; // r15
  FARPROC ProcAddress; // r13
  __int64 *v18; // rax
  __int64 *v19; // r15
  __int64 v20; // rcx
  unsigned int v21; // eax
  __int64 v22; // r9
  __int64 v23; // r9
  __int64 v24; // r9
  unsigned int v25; // r15d
  char *v26; // [rsp+30h] [rbp-48h]

  v8 = a2;
  v9 = a6;
  if ( a6 )
    *a6 = 0;
  Library = LoadLibraryExW(a2, 0, 0);
  if ( !Library )
  {
    LastError = GetLastError();
    v12 = LastError;
    v13 = L"RunAsDll() LoadLibrary(%s) failed, GLE=%u.";
LABEL_5:
    if ( !v8 )
      v8 = L"(null)";
    MyDbgPrintfW(0xFFFFFFFFLL, v13, v8, v12);
    if ( (int)LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return LastError;
  }
  v15 = WzToSzWithAlloc(a3);
  v16 = (CHAR *)v15;
  if ( !v15 )
  {
    LastError = GetLastError();
    FreeLibrary(Library);
    v12 = LastError;
    v13 = L"RunAsDll() WzToSzWithAlloc(%s) failed, GLE=%u.";
    goto LABEL_5;
  }
  ProcAddress = GetProcAddress(Library, v15);
  CmFree(v16);
  if ( ProcAddress )
  {
    v26 = WzToSzWithAlloc(a4);
    LODWORD(a6) = 0;
    v18 = (__int64 *)ConvertStringToBinary(a5, &a6);
    v19 = v18;
    if ( v18 )
      v20 = *v18;
    else
      v20 = 0;
    v21 = ((__int64 (__fastcall *)(__int64, HMODULE, char *, __int64))ProcAddress)(v20, Library, v26, 5);
    if ( v9 )
      *v9 = v21;
    CmFree(v26);
    CmFree(v19);
    if ( !v8 )
      v8 = L"(null)";
    MyDbgPrintfW(0xFFFFFFFFLL, L"RunAsDll() Executed module: %s", v8, v22);
    if ( !a3 )
      a3 = L"(null)";
    MyDbgPrintfW(0xFFFFFFFFLL, L"\tFunction:  %s", a3, v23);
    if ( !a4 )
      a4 = L"(null)";
    MyDbgPrintfW(0xFFFFFFFFLL, L"\tParams:  %s", a4, v24);
    MyDbgPrintfW(0xFFFFFFFFLL, L"\t Return Value:  %u = 0x%x", 0, 0);
    v25 = 0;
  }
  else
  {
    v25 = -2147024895;
    GetLastError();
    if ( !a3 )
      a3 = L"(null)";
    if ( !v8 )
      v8 = L"(null)";
    MyDbgPrintfW(0xFFFFFFFFLL, L"RunAsDll() GetProcAddress(*pszwModuleName=%s,*pszFunction=%s) failed, GLE=%u.", v8, a3);
  }
  FreeLibrary(Library);
  return v25;
}

```

## disassembly

```asm
0x180002420  mov     [rsp+arg_18], r9
0x180002425  mov     [rsp+arg_10], r8
0x18000242a  mov     [rsp+arg_8], rdx
0x18000242f  push    rbx
0x180002430  push    rsi
0x180002431  push    rdi
0x180002432  push    r12
0x180002434  push    r13
0x180002436  push    r14
0x180002438  push    r15
0x18000243a  sub     rsp, 40h
0x18000243e  mov     r12, r9
0x180002441  mov     rdi, r8
0x180002444  mov     rbx, rdx
0x180002447  mov     r14, [rsp+78h+arg_28]
0x18000244f  test    r14, r14
0x180002452  jz      short loc_18000245B
0x180002454  mov     dword ptr [r14], 0
0x18000245b  xor     r8d, r8d; dwFlags
0x18000245e  xor     edx, edx; hFile
0x180002460  mov     rcx, rbx; lpLibFileName
0x180002463  call    cs:__imp_LoadLibraryExW
0x180002469  mov     rsi, rax
0x18000246c  mov     [rsp+78h+var_40], rax
0x180002471  test    rax, rax
0x180002474  jnz     short loc_1800024B5
0x180002476  call    cs:__imp_GetLastError
0x18000247c  mov     edi, eax
0x18000247e  mov     r9d, eax
0x180002481  lea     rdx, aRunasdllLoadli; "RunAsDll() LoadLibrary(%s) failed, GLE="...
0x180002488  test    rbx, rbx
0x18000248b  lea     r14, aNull; "(null)"
0x180002492  cmovz   rbx, r14
0x180002496  mov     r8, rbx
0x180002499  or      ecx, 0FFFFFFFFh
0x18000249c  call    MyDbgPrintfW
0x1800024a1  test    edi, edi
0x1800024a3  jle     short loc_1800024AE
0x1800024a5  movzx   edi, di
0x1800024a8  or      edi, 80070000h
0x1800024ae  mov     eax, edi
0x1800024b0  jmp     loc_18000269A
0x1800024b5  mov     rcx, rdi
0x1800024b8  call    cs:__imp_?WzToSzWithAlloc@@YAPEADPEBG@Z; WzToSzWithAlloc(ushort const *)
0x1800024be  mov     r15, rax
0x1800024c1  test    rax, rax
0x1800024c4  jnz     short loc_1800024E3
0x1800024c6  call    cs:__imp_GetLastError
0x1800024cc  mov     edi, eax
0x1800024ce  mov     rcx, rsi; hLibModule
0x1800024d1  call    cs:__imp_FreeLibrary
0x1800024d7  mov     r9d, edi
0x1800024da  lea     rdx, aRunasdllWztosz; "RunAsDll() WzToSzWithAlloc(%s) failed, "...
0x1800024e1  jmp     short loc_180002488
0x1800024e3  mov     rdx, r15; lpProcName
0x1800024e6  mov     rcx, rsi; hModule
0x1800024e9  call    cs:__imp_GetProcAddress
0x1800024ef  mov     r13, rax
0x1800024f2  mov     rcx, r15
0x1800024f5  call    cs:__imp_?CmFree@@YAXPEAX@Z; CmFree(void *)
0x1800024fb  test    r13, r13
0x1800024fe  jz      loc_180002654
0x180002504  mov     rcx, r12
0x180002507  call    cs:__imp_?WzToSzWithAlloc@@YAPEADPEBG@Z; WzToSzWithAlloc(ushort const *)
0x18000250d  mov     [rsp+78h+var_48], rax
0x180002512  mov     dword ptr [rsp+78h+arg_28], 0
0x18000251d  lea     rdx, [rsp+78h+arg_28]
0x180002525  mov     rcx, [rsp+78h+arg_20]
0x18000252d  call    ConvertStringToBinary
0x180002532  mov     r15, rax
0x180002535  test    rax, rax
0x180002538  jz      short loc_18000253F
0x18000253a  mov     rcx, [rax]
0x18000253d  jmp     short loc_180002541
0x18000253f  xor     ecx, ecx
0x180002541  mov     r9d, 5
0x180002547  mov     r8, [rsp+78h+var_48]
0x18000254c  mov     rdx, rsi
0x18000254f  mov     rax, r13
0x180002552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002557  test    r14, r14
0x18000255a  jz      short loc_18000255F
0x18000255c  mov     [r14], eax
0x18000255f  mov     rcx, [rsp+78h+var_48]
0x180002564  call    cs:__imp_?CmFree@@YAXPEAX@Z; CmFree(void *)
0x18000256a  mov     rcx, r15
0x18000256d  call    cs:__imp_?CmFree@@YAXPEAX@Z; CmFree(void *)
0x180002573  lea     r14, aNull; "(null)"
0x18000257a  test    rbx, rbx
0x18000257d  cmovz   rbx, r14
0x180002581  mov     r8, rbx
0x180002584  lea     rdx, aRunasdllExecut; "RunAsDll() Executed module: %s"
0x18000258b  or      ebx, 0FFFFFFFFh
0x18000258e  mov     ecx, ebx
0x180002590  call    MyDbgPrintfW
0x180002595  test    rdi, rdi
0x180002598  cmovz   rdi, r14
0x18000259c  mov     r8, rdi
0x18000259f  lea     rdx, aFunctionS; "\tFunction:  %s"
0x1800025a6  mov     ecx, ebx
0x1800025a8  call    MyDbgPrintfW
0x1800025ad  test    r12, r12
0x1800025b0  cmovz   r12, r14
0x1800025b4  mov     r8, r12
0x1800025b7  lea     rdx, aParamsS; "\tParams:  %s"
0x1800025be  mov     ecx, ebx
0x1800025c0  call    MyDbgPrintfW
0x1800025c5  xor     r9d, r9d
0x1800025c8  xor     r8d, r8d
0x1800025cb  lea     rdx, aReturnValueU0x; "\t Return Value:  %u = 0x%x"
0x1800025d2  mov     ecx, ebx
0x1800025d4  call    MyDbgPrintfW
0x1800025d9  jmp     short loc_18000264F
0x1800025db  lea     r8, aNull; "(null)"
0x1800025e2  mov     rax, [rsp+78h+arg_8]
0x1800025ea  test    rax, rax
0x1800025ed  cmovnz  r8, rax
0x1800025f1  lea     rdx, aExceptionInRun; "Exception in RunAsDll() Module: %s"
0x1800025f8  or      ecx, 0FFFFFFFFh
0x1800025fb  call    MyDbgPrintfW
0x180002600  lea     r8, aNull; "(null)"
0x180002607  mov     rax, [rsp+78h+arg_10]
0x18000260f  test    rax, rax
0x180002612  cmovnz  r8, rax
0x180002616  lea     rdx, aFunctionS; "\tFunction:  %s"
0x18000261d  or      ecx, 0FFFFFFFFh
0x180002620  call    MyDbgPrintfW
0x180002625  lea     r8, aNull; "(null)"
0x18000262c  mov     rax, [rsp+78h+arg_18]
0x180002634  test    rax, rax
0x180002637  cmovnz  r8, rax
0x18000263b  lea     rdx, aParamsS; "\tParams:  %s"
0x180002642  or      ecx, 0FFFFFFFFh
0x180002645  call    MyDbgPrintfW
0x18000264a  mov     rsi, [rsp+78h+var_40]
0x18000264f  xor     r15d, r15d
0x180002652  jmp     short loc_18000268E
0x180002654  mov     r15d, 80070001h
0x18000265a  call    cs:__imp_GetLastError
0x180002660  lea     r14, aNull; "(null)"
0x180002667  test    rdi, rdi
0x18000266a  cmovz   rdi, r14
0x18000266e  test    rbx, rbx
0x180002671  cmovz   rbx, r14
0x180002675  mov     [rsp+78h+var_58], eax
0x180002679  mov     r9, rdi
0x18000267c  mov     r8, rbx
0x18000267f  lea     rdx, aRunasdllGetpro; "RunAsDll() GetProcAddress(*pszwModuleNa"...
0x180002686  or      ecx, 0FFFFFFFFh
0x180002689  call    MyDbgPrintfW
0x18000268e  mov     rcx, rsi; hLibModule
0x180002691  call    cs:__imp_FreeLibrary
0x180002697  mov     eax, r15d
0x18000269a  add     rsp, 40h
0x18000269e  pop     r15
0x1800026a0  pop     r14
0x1800026a2  pop     r13
0x1800026a4  pop     r12
0x1800026a6  pop     rdi
0x1800026a7  pop     rsi
0x1800026a8  pop     rbx
0x1800026a9  retn
```
