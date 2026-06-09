# RegScan::SetKeyName(ushort *,ushort *)

- ea: `0x180052490`
- end: `0x18005264d`
- name: `?SetKeyName@RegScan@@AEAAJPEAG0@Z`
- size: `445`
- prototype: `int(RegScan *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800514a0`

## callees

- `0x180005944`
- `0x180014ec8`
- `0x180052490`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800525f7`
- `msvcrt!_wcsicmp` at `0x180052612`
- `msvcrt!_wcsicmp` at `0x1800525f7`
- `msvcrt!_wcsicmp` at `0x180052612`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052631`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052631`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052588`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052588`

## string_xrefs

- `0x1800525f0`: `CLSID`
- `0x1800524ee`: `com\complus\src\comcat\regscan\regscan.cpp`
- `0x180052535`: `com\complus\src\comcat\regscan\regscan.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RegScan::SetKeyName(RegScan *this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  __int64 v6; // rax
  __int64 v7; // rcx
  unsigned __int64 v8; // r14
  _WORD *v9; // rax
  int v11; // edi
  int v12; // eax
  int v13; // edx
  void *v14; // rcx
  int v15; // [rsp+20h] [rbp-30h] BYREF
  __int16 v16; // [rsp+24h] [rbp-2Ch]
  int v17; // [rsp+28h] [rbp-28h]
  const unsigned __int16 *v18; // [rsp+30h] [rbp-20h]
  __int64 v19; // [rsp+38h] [rbp-18h]
  __int64 v20; // [rsp+40h] [rbp-10h]
  int v21; // [rsp+48h] [rbp-8h]
  int v22; // [rsp+4Ch] [rbp-4h]

  if ( !a3 )
  {
    v15 = 0;
    v16 = 21;
    v17 = -1073605930;
    v18 = L"i_wszKeyName";
    v19 = 0;
    v20 = 0;
    v22 = 1;
    v21 = 1;
    CError::WriteToLog((CError *)&v15, L"com\\complus\\src\\comcat\\regscan\\regscan.cpp", 0xB8u, L"i_wszKeyName");
  }
  if ( *((_QWORD *)this + 10) )
  {
    v15 = 0;
    v16 = 21;
    v17 = -1073605930;
    v18 = L"NULL == m_wszFullKeyName";
    v19 = 0;
    v20 = 0;
    v22 = 1;
    v21 = 1;
    CError::WriteToLog(
      (CError *)&v15,
      L"com\\complus\\src\\comcat\\regscan\\regscan.cpp",
      0xB9u,
      L"NULL == m_wszFullKeyName");
  }
  *((_QWORD *)this + 4) = a3;
  v6 = -1;
  do
    ++v6;
  while ( a3[v6] );
  if ( a2 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a2[v7] );
    LODWORD(v6) = v7 + v6 + 1;
  }
  v8 = (unsigned int)(v6 + 1);
  v9 = CoTaskMemAlloc(saturated_mul(v8, 2u));
  *((_QWORD *)this + 10) = v9;
  if ( !v9 )
    return 2147942414LL;
  *v9 = 0;
  if ( a2
    && ((v11 = StringCchCatW(*((unsigned __int16 **)this + 10), v8, a2), v11 < 0)
     || (v11 = StringCchCatW(*((unsigned __int16 **)this + 10), v8, L"\\"), v11 < 0))
    || (v11 = StringCchCatW(*((unsigned __int16 **)this + 10), v8, a3), v11 < 0) )
  {
    v14 = (void *)*((_QWORD *)this + 10);
    if ( v14 )
    {
      CoTaskMemFree(v14);
      *((_QWORD *)this + 10) = 0;
    }
  }
  else
  {
    *((_DWORD *)this + 22) |= _wcsicmp(L"CLSID", a3) == 0;
    v12 = _wcsicmp(L"InProcServer32", a3);
    v13 = 4;
    if ( v12 )
      v13 = 0;
    *((_DWORD *)this + 22) |= v13;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180052490  push    rbp
0x180052492  push    rbx
0x180052493  push    rsi
0x180052494  push    rdi
0x180052495  push    r13
0x180052497  push    r14
0x180052499  push    r15
0x18005249b  mov     rbp, rsp
0x18005249e  sub     rsp, 50h
0x1800524a2  mov     rsi, r8
0x1800524a5  mov     rdi, rdx
0x1800524a8  mov     rbx, rcx
0x1800524ab  mov     r13d, 15h
0x1800524b1  lea     r14d, [r13-14h]
0x1800524b5  xor     r15d, r15d
0x1800524b8  test    r8, r8
0x1800524bb  jnz     short loc_1800524FE
0x1800524bd  mov     [rbp+var_30], r15d
0x1800524c1  mov     [rbp+var_2C], r13w
0x1800524c6  mov     [rbp+var_28], 0C00212D6h
0x1800524cd  lea     r9, aIWszkeyname; "i_wszKeyName"
0x1800524d4  mov     [rbp+var_20], r9
0x1800524d8  mov     [rbp+var_18], r15
0x1800524dc  mov     [rbp+var_10], r15
0x1800524e0  mov     [rbp+var_4], r14d
0x1800524e4  mov     [rbp+var_8], r14d
0x1800524e8  mov     r8d, 0B8h; unsigned int
0x1800524ee  lea     rdx, aComComplusSrcC; "com\\complus\\src\\comcat\\regscan\\reg"...
0x1800524f5  lea     rcx, [rbp+var_30]; this
0x1800524f9  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x1800524fe  cmp     [rbx+50h], r15
0x180052502  jz      short loc_180052545
0x180052504  mov     [rbp+var_30], r15d
0x180052508  mov     [rbp+var_2C], r13w
0x18005250d  mov     [rbp+var_28], 0C00212D6h
0x180052514  lea     r9, aNullMWszfullke; "NULL == m_wszFullKeyName"
0x18005251b  mov     [rbp+var_20], r9
0x18005251f  mov     [rbp+var_18], r15
0x180052523  mov     [rbp+var_10], r15
0x180052527  mov     [rbp+var_4], r14d
0x18005252b  mov     [rbp+var_8], r14d
0x18005252f  mov     r8d, 0B9h; unsigned int
0x180052535  lea     rdx, aComComplusSrcC; "com\\complus\\src\\comcat\\regscan\\reg"...
0x18005253c  lea     rcx, [rbp+var_30]; this
0x180052540  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180052545  mov     [rbx+20h], rsi
0x180052549  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005254d  mov     rax, r8
0x180052550  inc     rax
0x180052553  cmp     [rsi+rax*2], r15w
0x180052558  jnz     short loc_180052550
0x18005255a  test    rdi, rdi
0x18005255d  jz      short loc_180052572
0x18005255f  mov     rcx, r8
0x180052562  inc     rcx
0x180052565  cmp     [rdi+rcx*2], r15w
0x18005256a  jnz     short loc_180052562
0x18005256c  inc     rax
0x18005256f  add     rax, rcx
0x180052572  lea     r14, [rax+1]
0x180052576  mov     r14d, r14d
0x180052579  mov     eax, 2
0x18005257e  mul     r14
0x180052581  cmovb   rax, r8
0x180052585  mov     rcx, rax; cb
0x180052588  call    cs:__imp_CoTaskMemAlloc
0x18005258e  mov     [rbx+50h], rax
0x180052592  test    rax, rax
0x180052595  jnz     short loc_1800525A1
0x180052597  mov     eax, 8007000Eh
0x18005259c  jmp     loc_18005263E
0x1800525a1  mov     [rax], r15w
0x1800525a5  test    rdi, rdi
0x1800525a8  jz      short loc_1800525D8
0x1800525aa  mov     r8, rdi; unsigned __int16 *
0x1800525ad  mov     rdx, r14; unsigned __int64
0x1800525b0  mov     rcx, [rbx+50h]; unsigned __int16 *
0x1800525b4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800525b9  mov     edi, eax
0x1800525bb  test    eax, eax
0x1800525bd  js      short loc_180052628
0x1800525bf  lea     r8, asc_180061B34; "\\"
0x1800525c6  mov     rdx, r14; unsigned __int64
0x1800525c9  mov     rcx, [rbx+50h]; unsigned __int16 *
0x1800525cd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800525d2  mov     edi, eax
0x1800525d4  test    eax, eax
0x1800525d6  js      short loc_180052628
0x1800525d8  mov     r8, rsi; unsigned __int16 *
0x1800525db  mov     rdx, r14; unsigned __int64
0x1800525de  mov     rcx, [rbx+50h]; unsigned __int16 *
0x1800525e2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800525e7  mov     edi, eax
0x1800525e9  test    eax, eax
0x1800525eb  js      short loc_180052628
0x1800525ed  mov     rdx, rsi; String2
0x1800525f0  lea     rcx, aClsid; "CLSID"
0x1800525f7  call    cs:__imp__wcsicmp
0x1800525fd  mov     ecx, r15d
0x180052600  test    eax, eax
0x180052602  setz    cl
0x180052605  or      [rbx+58h], ecx
0x180052608  mov     rdx, rsi; String2
0x18005260b  lea     rcx, aInprocserver32_1; "InProcServer32"
0x180052612  call    cs:__imp__wcsicmp
0x180052618  mov     edx, 4
0x18005261d  test    eax, eax
0x18005261f  cmovnz  edx, r15d
0x180052623  or      [rbx+58h], edx
0x180052626  jmp     short loc_18005263C
0x180052628  mov     rcx, [rbx+50h]; pv
0x18005262c  test    rcx, rcx
0x18005262f  jz      short loc_18005263C
0x180052631  call    cs:__imp_CoTaskMemFree
0x180052637  nop
0x180052638  mov     [rbx+50h], r15
0x18005263c  mov     eax, edi
0x18005263e  add     rsp, 50h
0x180052642  pop     r15
0x180052644  pop     r14
0x180052646  pop     r13
0x180052648  pop     rdi
0x180052649  pop     rsi
0x18005264a  pop     rbx
0x18005264b  pop     rbp
0x18005264c  retn
```
