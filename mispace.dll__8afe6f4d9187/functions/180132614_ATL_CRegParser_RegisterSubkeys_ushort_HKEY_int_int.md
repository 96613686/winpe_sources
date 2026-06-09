# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180132614`
- end: `0x180132b8c`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1400`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18013230c`
- `0x180132614`

## callees

- `0x180006290`
- `0x1801300cc`
- `0x180130620`
- `0x180130638`
- `0x180130d74`
- `0x180130da0`
- `0x180130fc0`
- `0x1801314c0`
- `0x180131d24`
- `0x180131e9c`
- `0x1801321f8`
- `0x180132614`
- `0x180132d94`
- `0x180132e64`
- `0x1801f2c00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1801329d3`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1801329d3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180132863`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180132863`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180132688`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18013269b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18013276c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18013279b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180132688`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18013269b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18013276c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18013279b`

## string_xrefs

- `0x180132691`: `ForceRemove`
- `0x180132762`: `NoRemove`
- `0x18013267e`: `Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        HKEY a3,
        int a4,
        int a5)
{
  int v5; // r15d
  unsigned __int16 *v7; // rdi
  ATL::CRegParser *v8; // rsi
  int Token; // eax
  int v10; // ebx
  int v11; // r14d
  ATL::CRegParser *v12; // rcx
  int v13; // eax
  int v14; // r12d
  unsigned int v15; // eax
  unsigned __int16 *v16; // r9
  unsigned int v17; // eax
  __int64 v18; // rax
  int v19; // r14d
  int v20; // r15d
  ATL::CRegParser *v21; // rcx
  __int64 v22; // rax
  unsigned int v23; // ecx
  int HasSubKeys; // r14d
  __int64 v26; // [rsp+20h] [rbp-E0h]
  unsigned int v27; // [rsp+28h] [rbp-D8h]
  struct _SECURITY_ATTRIBUTES *v28; // [rsp+30h] [rbp-D0h]
  unsigned int *v29; // [rsp+38h] [rbp-C8h]
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v32; // [rsp+50h] [rbp-B0h]
  __int64 v33; // [rsp+58h] [rbp-A8h]
  HKEY v34[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v35[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ValueName[4096]; // [rsp+290h] [rbp+190h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  memset(v34, 0, 24);
LABEL_2:
  Token = ATL::CRegParser::NextToken(this, a2);
  while ( 2 )
  {
    v10 = Token;
    if ( Token < 0 )
      goto LABEL_80;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( *v7 == 125 )
          goto LABEL_80;
        v11 = lstrcmpiW(v7, L"Delete");
        if ( lstrcmpiW(v7, L"ForceRemove") )
        {
          if ( v11 )
            break;
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_80;
        if ( !v5 )
          break;
        hKey = 0;
        v32 = 0;
        v33 = 0;
        if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        {
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_79:
          v10 = -2147352567;
          goto LABEL_80;
        }
        if ( ATL::CRegParser::CanForceRemoveKey(v12, v7) )
        {
          hKey = a3;
          ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, v7);
          hKey = 0;
        }
        if ( v11 )
        {
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          break;
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_82;
        v13 = ATL::CRegParser::SkipAssignment(v8, v7);
LABEL_15:
        v10 = v13;
        if ( v13 < 0 )
          goto LABEL_82;
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_40:
        if ( *v7 == 123 )
        {
          v18 = -1;
          do
            ++v18;
          while ( v7[v18] );
          if ( v18 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v34[0], v5, 0);
            if ( v10 < 0 )
              goto LABEL_80;
            a2 = v7;
            this = v8;
            goto LABEL_2;
          }
        }
      }
      v14 = 1;
      if ( !lstrcmpiW(v7, L"NoRemove") )
      {
        v14 = 0;
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_80;
      }
      if ( !lstrcmpiW(v7, L"Val") )
        break;
      if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        goto LABEL_79;
      if ( v5 )
      {
        if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v34, a3, v7, 0x2001Fu)
          || !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v34, a3, v7, 0x20019u)
          || (v17 = ATL::CRegKey::Create((ATL::CRegKey *)v34, a3, v7, v16, v26, v27, v28, v29)) == 0 )
        {
          v10 = ATL::CRegParser::NextToken(v8, v7);
          if ( v10 < 0 )
            goto LABEL_80;
          if ( *v7 == 61 )
          {
            v10 = ATL::CRegParser::AddValue(v8, v34, 0, v7);
            if ( v10 < 0 )
              goto LABEL_80;
          }
          goto LABEL_40;
        }
LABEL_83:
        v23 = v17;
LABEL_64:
        v10 = ATL::AtlHresultFromWin32(v23);
        goto LABEL_80;
      }
      if ( a5 )
        v19 = 2;
      else
        v19 = ATL::CRegKey::Open((ATL::CRegKey *)v34, a3, v7, 0x20019u);
      v20 = 1;
      if ( !v19 )
        v20 = a5;
      _o_wcsncpy_s(v35, 260, v7, -1, v26);
      v10 = ATL::CRegParser::NextToken(v8, v7);
      if ( v10 < 0 )
        goto LABEL_80;
      v10 = ATL::CRegParser::SkipAssignment(v8, v7);
      v21 = 0;
      if ( v10 < 0 )
        goto LABEL_80;
      if ( *v7 == 123 )
      {
        v22 = -1;
        do
          ++v22;
        while ( v7[v22] );
        if ( v22 == 1 )
        {
          v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v34[0], 0, v20);
          if ( v10 < 0 && !v20 )
            goto LABEL_80;
          v10 = ATL::CRegParser::NextToken(v8, v7);
          if ( v10 < 0 )
            goto LABEL_80;
        }
      }
      if ( v19 != 2 )
      {
        if ( v19 )
        {
          if ( !a5 )
          {
            v23 = v19;
            goto LABEL_64;
          }
        }
        else if ( a5 && ATL::CRegParser::HasSubKeys(v21, v34[0]) )
        {
          if ( ATL::CRegParser::CanForceRemoveKey(v21, v35) && v14 )
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v34, v35);
        }
        else
        {
          HasSubKeys = ATL::CRegParser::HasSubKeys(v21, v34[0]);
          v17 = ATL::CRegKey::Close((ATL::CRegKey *)v34);
          if ( v17 )
            goto LABEL_83;
          if ( v14 && !HasSubKeys )
          {
            v32 = 0;
            v33 = 0;
            hKey = a3;
            v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, v35);
            hKey = 0;
            if ( v15 )
              goto LABEL_81;
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          }
        }
      }
      v5 = a4;
    }
    v10 = ATL::CRegParser::NextToken(v8, ValueName);
    if ( v10 < 0 )
      goto LABEL_80;
    v10 = ATL::CRegParser::NextToken(v8, v7);
    if ( v10 < 0 )
      goto LABEL_80;
    if ( *v7 != 61 )
      goto LABEL_79;
    if ( v5 )
    {
      v32 = 0;
      v33 = 0;
      hKey = a3;
      v13 = ATL::CRegParser::AddValue(v8, &hKey, ValueName, v7);
      hKey = 0;
      goto LABEL_15;
    }
    if ( a5 || !v14 )
      goto LABEL_31;
    hKey = 0;
    v32 = 0;
    v33 = 0;
    v15 = ATL::CRegKey::Open((ATL::CRegKey *)&hKey, a3, 0, 0x20006u);
    if ( !v15 )
    {
      v15 = RegDeleteValueW(hKey, ValueName);
      if ( (v15 & 0xFFFFFFFD) == 0 )
      {
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_31:
        Token = ATL::CRegParser::SkipAssignment(v8, v7);
        continue;
      }
    }
    break;
  }
LABEL_81:
  v10 = ATL::AtlHresultFromWin32(v15);
LABEL_82:
  ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_80:
  ATL::CRegKey::Close((ATL::CRegKey *)v34);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180132614  push    rbp
0x180132616  push    rbx
0x180132617  push    rsi
0x180132618  push    rdi
0x180132619  push    r12
0x18013261b  push    r13
0x18013261d  push    r14
0x18013261f  push    r15
0x180132621  lea     rbp, [rsp-21A8h]
0x180132629  mov     eax, 22A8h
0x18013262e  call    _alloca_probe
0x180132633  sub     rsp, rax
0x180132636  mov     rax, cs:__security_cookie
0x18013263d  xor     rax, rsp
0x180132640  mov     [rbp+21E0h+var_50], rax
0x180132647  mov     r15d, r9d
0x18013264a  mov     [rsp+22E0h+var_22A0], r9d
0x18013264f  mov     r13, r8
0x180132652  mov     rdi, rdx
0x180132655  mov     rsi, rcx
0x180132658  xor     r12d, r12d
0x18013265b  mov     [rsp+22E0h+var_2280], r12
0x180132660  mov     [rsp+22E0h+var_2278], r12
0x180132665  mov     [rsp+22E0h+var_2270], r12
0x18013266a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18013266f  mov     ebx, eax
0x180132671  test    eax, eax
0x180132673  js      loc_180132B40
0x180132679  jmp     loc_180132AC7
0x18013267e  lea     rdx, aDelete; "Delete"
0x180132685  mov     rcx, rdi; lpString1
0x180132688  call    cs:__imp_lstrcmpiW
0x18013268e  mov     r14d, eax
0x180132691  lea     rdx, aForceremove; "ForceRemove"
0x180132698  mov     rcx, rdi; lpString1
0x18013269b  call    cs:__imp_lstrcmpiW
0x1801326a1  test    eax, eax
0x1801326a3  jz      short loc_1801326AE
0x1801326a5  test    r14d, r14d
0x1801326a8  jnz     loc_18013275C
0x1801326ae  mov     rdx, rdi; unsigned __int16 *
0x1801326b1  mov     rcx, rsi; this
0x1801326b4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1801326b9  mov     ebx, eax
0x1801326bb  test    eax, eax
0x1801326bd  js      loc_180132B40
0x1801326c3  test    r15d, r15d
0x1801326c6  jz      loc_18013275C
0x1801326cc  mov     [rsp+22E0h+hKey], r12
0x1801326d1  mov     [rsp+22E0h+var_2290], r12
0x1801326d6  mov     [rsp+22E0h+var_2288], r12
0x1801326db  mov     edx, 5Ch ; '\'; unsigned __int16
0x1801326e0  mov     rcx, rdi; lpsz
0x1801326e3  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1801326e8  test    rax, rax
0x1801326eb  jnz     loc_180132B31
0x1801326f1  mov     rdx, rdi; unsigned __int16 *
0x1801326f4  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x1801326f9  test    eax, eax
0x1801326fb  jz      short loc_180132714
0x1801326fd  mov     [rsp+22E0h+hKey], r13
0x180132702  mov     rdx, rdi; unsigned __int16 *
0x180132705  lea     rcx, [rsp+22E0h+hKey]; this
0x18013270a  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18013270f  mov     [rsp+22E0h+hKey], r12
0x180132714  test    r14d, r14d
0x180132717  jnz     short loc_180132752
0x180132719  mov     rdx, rdi; unsigned __int16 *
0x18013271c  mov     rcx, rsi; this
0x18013271f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180132724  mov     ebx, eax
0x180132726  test    eax, eax
0x180132728  js      loc_180132B78
0x18013272e  mov     rdx, rdi; unsigned __int16 *
0x180132731  mov     rcx, rsi; this
0x180132734  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180132739  test    eax, eax
0x18013273b  lea     rcx, [rsp+22E0h+hKey]; this
0x180132740  mov     ebx, eax
0x180132742  js      loc_180132B7D
0x180132748  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18013274d  jmp     loc_180132939
0x180132752  lea     rcx, [rsp+22E0h+hKey]; this
0x180132757  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18013275c  mov     r12d, 1
0x180132762  lea     rdx, aNoremove; "NoRemove"
0x180132769  mov     rcx, rdi; lpString1
0x18013276c  call    cs:__imp_lstrcmpiW
0x180132772  xor     r14d, r14d
0x180132775  test    eax, eax
0x180132777  jnz     short loc_180132791
0x180132779  mov     r12d, r14d
0x18013277c  mov     rdx, rdi; unsigned __int16 *
0x18013277f  mov     rcx, rsi; this
0x180132782  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180132787  mov     ebx, eax
0x180132789  test    eax, eax
0x18013278b  js      loc_180132B40
0x180132791  lea     rdx, aVal; "Val"
0x180132798  mov     rcx, rdi; lpString1
0x18013279b  call    cs:__imp_lstrcmpiW
0x1801327a1  test    eax, eax
0x1801327a3  jnz     loc_180132893
0x1801327a9  lea     rdx, [rbp+21E0h+ValueName]; unsigned __int16 *
0x1801327b0  mov     rcx, rsi; this
0x1801327b3  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1801327b8  mov     ebx, eax
0x1801327ba  test    eax, eax
0x1801327bc  js      loc_180132B40
0x1801327c2  mov     rdx, rdi; unsigned __int16 *
0x1801327c5  mov     rcx, rsi; this
0x1801327c8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1801327cd  mov     ebx, eax
0x1801327cf  test    eax, eax
0x1801327d1  js      loc_180132B40
0x1801327d7  cmp     word ptr [rdi], 3Dh ; '='
0x1801327db  jnz     loc_180132B3B
0x1801327e1  test    r15d, r15d
0x1801327e4  jz      short loc_180132819
0x1801327e6  xor     r12d, r12d
0x1801327e9  mov     [rsp+22E0h+var_2290], r12
0x1801327ee  mov     [rsp+22E0h+var_2288], r12
0x1801327f3  mov     [rsp+22E0h+hKey], r13
0x1801327f8  mov     r9, rdi; unsigned __int16 *
0x1801327fb  lea     r8, [rbp+21E0h+ValueName]; unsigned __int16 *
0x180132802  lea     rdx, [rsp+22E0h+hKey]; struct ATL::CRegKey *
0x180132807  mov     rcx, rsi; this
0x18013280a  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18013280f  mov     [rsp+22E0h+hKey], r12
0x180132814  jmp     loc_180132739
0x180132819  cmp     [rbp+21E0h+arg_20], r14d
0x180132820  jnz     short loc_180132880
0x180132822  test    r12d, r12d
0x180132825  jz      short loc_180132880
0x180132827  xor     r12d, r12d
0x18013282a  mov     [rsp+22E0h+hKey], r12
0x18013282f  mov     [rsp+22E0h+var_2290], r12
0x180132834  mov     [rsp+22E0h+var_2288], r12
0x180132839  mov     r9d, 20006h; unsigned int
0x18013283f  xor     r8d, r8d; lpSubKey
0x180132842  mov     rdx, r13; hKey
0x180132845  lea     rcx, [rsp+22E0h+hKey]; this
0x18013284a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18013284f  test    eax, eax
0x180132851  jnz     loc_180132B6F
0x180132857  lea     rdx, [rbp+21E0h+ValueName]; lpValueName
0x18013285e  mov     rcx, [rsp+22E0h+hKey]; hKey
0x180132863  call    cs:__imp_RegDeleteValueW
0x180132869  test    eax, 0FFFFFFFDh
0x18013286e  jnz     loc_180132B6F
0x180132874  lea     rcx, [rsp+22E0h+hKey]; this
0x180132879  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18013287e  jmp     short loc_180132883
0x180132880  xor     r12d, r12d
0x180132883  mov     rdx, rdi; unsigned __int16 *
0x180132886  mov     rcx, rsi; this
0x180132889  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18013288e  jmp     loc_18013266F
0x180132893  mov     edx, 5Ch ; '\'; unsigned __int16
0x180132898  mov     rcx, rdi; lpsz
0x18013289b  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1801328a0  test    rax, rax
0x1801328a3  jnz     loc_180132B3B
0x1801328a9  test    r15d, r15d
0x1801328ac  jz      loc_180132988
0x1801328b2  mov     r9d, 2001Fh; unsigned int
0x1801328b8  mov     r8, rdi; lpSubKey
0x1801328bb  mov     rdx, r13; hKey
0x1801328be  lea     rcx, [rsp+22E0h+var_2280]; this
0x1801328c3  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1801328c8  xor     r12d, r12d
0x1801328cb  test    eax, eax
0x1801328cd  jz      short loc_180132901
0x1801328cf  mov     r9d, 20019h; unsigned int
0x1801328d5  mov     r8, rdi; lpSubKey
0x1801328d8  mov     rdx, r13; hKey
0x1801328db  lea     rcx, [rsp+22E0h+var_2280]; this
0x1801328e0  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1801328e5  test    eax, eax
0x1801328e7  jz      short loc_180132901
0x1801328e9  mov     r8, rdi; lpSubKey
0x1801328ec  mov     rdx, r13; hKey
0x1801328ef  lea     rcx, [rsp+22E0h+var_2280]; this
0x1801328f4  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x1801328f9  test    eax, eax
0x1801328fb  jnz     loc_180132B84
0x180132901  mov     rdx, rdi; unsigned __int16 *
0x180132904  mov     rcx, rsi; this
0x180132907  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18013290c  mov     ebx, eax
0x18013290e  test    eax, eax
0x180132910  js      loc_180132B40
0x180132916  cmp     word ptr [rdi], 3Dh ; '='
0x18013291a  jnz     short loc_180132939
0x18013291c  mov     r9, rdi; unsigned __int16 *
0x18013291f  xor     r8d, r8d; unsigned __int16 *
0x180132922  lea     rdx, [rsp+22E0h+var_2280]; struct ATL::CRegKey *
0x180132927  mov     rcx, rsi; this
0x18013292a  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18013292f  mov     ebx, eax
0x180132931  test    eax, eax
0x180132933  js      loc_180132B40
0x180132939  cmp     word ptr [rdi], 7Bh ; '{'
0x18013293d  jnz     loc_180132AC7
0x180132943  or      rax, 0FFFFFFFFFFFFFFFFh
0x180132947  inc     rax
0x18013294a  cmp     [rdi+rax*2], r12w
0x18013294f  jnz     short loc_180132947
0x180132951  cmp     rax, 1
0x180132955  jnz     loc_180132AC7
0x18013295b  mov     dword ptr [rsp+22E0h+var_22C0], r12d; int
0x180132960  mov     r9d, r15d; int
0x180132963  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x180132968  mov     rdx, rdi; unsigned __int16 *
0x18013296b  mov     rcx, rsi; this
0x18013296e  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180132973  mov     ebx, eax
0x180132975  test    eax, eax
0x180132977  js      loc_180132B40
0x18013297d  mov     rdx, rdi
0x180132980  mov     rcx, rsi
0x180132983  jmp     loc_18013266A
0x180132988  cmp     [rbp+21E0h+arg_20], r14d
0x18013298f  jnz     short loc_1801329AC
0x180132991  mov     r9d, 20019h; unsigned int
0x180132997  mov     r8, rdi; lpSubKey
0x18013299a  mov     rdx, r13; hKey
0x18013299d  lea     rcx, [rsp+22E0h+var_2280]; this
0x1801329a2  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1801329a7  mov     r14d, eax
0x1801329aa  jmp     short loc_1801329B2
0x1801329ac  mov     r14d, 2
0x1801329b2  mov     r15d, 1
0x1801329b8  test    r14d, r14d
0x1801329bb  cmovz   r15d, [rbp+21E0h+arg_20]
0x1801329c3  or      r9, 0FFFFFFFFFFFFFFFFh
0x1801329c7  mov     r8, rdi
0x1801329ca  mov     edx, 104h
0x1801329cf  lea     rcx, [rbp+21E0h+var_2260]
0x1801329d3  call    cs:__imp__o_wcsncpy_s
0x1801329d9  mov     rdx, rdi; unsigned __int16 *
0x1801329dc  mov     rcx, rsi; this
0x1801329df  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1801329e4  mov     ebx, eax
0x1801329e6  test    eax, eax
0x1801329e8  js      loc_180132B40
0x1801329ee  mov     rdx, rdi; unsigned __int16 *
0x1801329f1  mov     rcx, rsi; this
0x1801329f4  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1801329f9  mov     ebx, eax
0x1801329fb  xor     ecx, ecx; this
0x1801329fd  test    eax, eax
0x1801329ff  js      loc_180132B40
0x180132a05  cmp     word ptr [rdi], 7Bh ; '{'
0x180132a09  jnz     short loc_180132A5F
0x180132a0b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180132a0f  inc     rax
0x180132a12  cmp     [rdi+rax*2], cx
0x180132a16  jnz     short loc_180132A0F
0x180132a18  cmp     rax, 1
0x180132a1c  jnz     short loc_180132A5F
0x180132a1e  mov     dword ptr [rsp+22E0h+var_22C0], r15d; int
0x180132a23  xor     r9d, r9d; int
0x180132a26  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x180132a2b  mov     rdx, rdi; unsigned __int16 *
0x180132a2e  mov     rcx, rsi; this
0x180132a31  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180132a36  mov     ebx, eax
0x180132a38  test    eax, eax
0x180132a3a  jns     short loc_180132A45
0x180132a3c  test    r15d, r15d
0x180132a3f  jz      loc_180132B40
0x180132a45  mov     rdx, rdi; unsigned __int16 *
0x180132a48  mov     rcx, rsi; this
0x180132a4b  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180132a50  mov     ebx, eax
0x180132a52  xor     r15d, r15d
0x180132a55  test    eax, eax
0x180132a57  js      loc_180132B40
0x180132a5d  jmp     short loc_180132A62
0x180132a5f  xor     r15d, r15d
0x180132a62  cmp     r14d, 2
0x180132a66  jz      short loc_180132ABF
0x180132a68  test    r14d, r14d
0x180132a6b  jz      short loc_180132A88
0x180132a6d  xor     r12d, r12d
0x180132a70  cmp     [rbp+21E0h+arg_20], r12d
0x180132a77  jnz     short loc_180132AC2
0x180132a79  mov     ecx, r14d; unsigned int
0x180132a7c  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180132a81  mov     ebx, eax
0x180132a83  jmp     loc_180132B40
0x180132a88  cmp     [rbp+21E0h+arg_20], r15d
0x180132a8f  jz      short loc_180132AD3
0x180132a91  mov     rdx, [rsp+22E0h+var_2280]; HKEY
0x180132a96  call    ?HasSubKeys@CRegParser@ATL@@IEAAHPEAUHKEY__@@@Z; ATL::CRegParser::HasSubKeys(HKEY__ *)
0x180132a9b  test    eax, eax
0x180132a9d  jz      short loc_180132AD3
0x180132a9f  lea     rdx, [rbp+21E0h+var_2260]; unsigned __int16 *
0x180132aa3  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
  ... truncated ...
```
