# CRegistry::GetDefaultProvider(ushort const *,_GUID *)

- ea: `0x180044fd0`
- end: `0x18004523c`
- name: `?GetDefaultProvider@CRegistry@@QEAAJPEBGPEAU_GUID@@@Z`
- size: `620`
- prototype: `int(CRegistry *__hidden this, const unsigned __int16 *, struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180044114`

## callees

- `0x1800112b0`
- `0x180011bcc`
- `0x180013870`
- `0x180029414`
- `0x180029560`
- `0x180044fd0`
- `0x180045488`
- `0x18007e700`
- `0x18007e7c0`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x18004507a`
- `MSDART!MpHeapAlloc` at `0x18004507a`
- `ADVAPI32!RegQueryValueExW` at `0x1800451b6`
- `ADVAPI32!RegQueryValueExW` at `0x1800451b6`
- `ADVAPI32!RegOpenKeyExW` at `0x180045180`
- `ADVAPI32!RegOpenKeyExW` at `0x180045180`
- `ADVAPI32!RegCloseKey` at `0x1800451d9`
- `ADVAPI32!RegCloseKey` at `0x1800451d9`
- `ole32!StringFromGUID2` at `0x1800451cd`
- `ole32!StringFromGUID2` at `0x1800451cd`

## string_xrefs

- `0x180045199`: `CLSID`
- `0x1800450a8`: `<CRegistry::GetDefaultProvider|OLEDB|ERR> `
- `0x180045128`: `<CRegistry::GetDefaultProvider|OLEDB|ERR> `
- `0x1800451f4`: `<CRegistry::GetDefaultProvider|Trace|HR> `
- `0x180045147`: `PROTOCOLS\Handler\`

## pseudocode

```c
__int64 __fastcall CRegistry::GetDefaultProvider(CRegistry *this, const unsigned __int16 *a2, struct _GUID *a3)
{
  __int64 v3; // rsi
  __int64 v5; // rax
  unsigned __int64 v7; // rdi
  unsigned __int16 *v8; // rbx
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rcx
  void *v11; // rsp
  void *v12; // rsp
  unsigned __int16 *v13; // rcx
  __int64 v14; // rax
  unsigned int Value; // edi
  __int64 v16; // rdx
  CRegistry *v17; // rcx
  DWORD cbData[2]; // [rsp+30h] [rbp+0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp+8h] BYREF
  unsigned __int16 *v21; // [rsp+40h] [rbp+10h] BYREF
  OLECHAR Data[40]; // [rsp+50h] [rbp+20h] BYREF
  WCHAR SubKey[384]; // [rsp+A0h] [rbp+70h] BYREF

  v3 = -1;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  v7 = v5 + 1;
  *(_QWORD *)cbData = 0;
  if ( (unsigned __int64)(v5 + 1) > 0x200 )
  {
    v14 = 2 * v7;
    if ( !is_mul_ok(v7, 2u) )
      v14 = -1;
    v8 = (unsigned __int16 *)MpHeapAlloc(g_hHeapHandle, 19922944, v14);
    v13 = v8;
  }
  else
  {
    v8 = 0;
    v9 = 2 * v7 + 15;
    if ( v9 <= 2 * v7 )
      v9 = 0xFFFFFFFFFFFFFF0LL;
    v10 = v9 & 0xFFFFFFFFFFFFFFF0uLL;
    v11 = alloca(v10);
    v12 = alloca(v10);
    v13 = (unsigned __int16 *)cbData;
  }
  v21 = v13;
  if ( v13 )
  {
    hKey = 0;
    Value = StringCchCopyW(v13, v7, a2);
    if ( (unsigned int)CRegistry::SeparateSchemeFromPrefix(v17, &v21, (unsigned __int16 **)cbData) )
    {
      do
        ++v3;
      while ( *(_WORD *)(*(_QWORD *)cbData + 2 * v3) );
      if ( (unsigned __int64)(v3 + 26) >= 0x180 )
      {
        Value = -2147024809;
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(-2147024809, L"<CRegistry::GetDefaultProvider|OLEDB|ERR> ", 0x262u);
        goto LABEL_26;
      }
      StringCchPrintfW(SubKey, 0x180u, L"%ls%ls%ls", L"PROTOCOLS\\Handler\\", *(_QWORD *)cbData, L"\\oledb");
      Value = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 1u, &hKey);
      if ( !Value )
      {
        cbData[0] = 78;
        Value = RegQueryValueExW(hKey, L"CLSID", 0, 0, (LPBYTE)Data, cbData);
        if ( !Value )
          Value = StringFromGUID2(a3, Data, 39);
        RegCloseKey(hKey);
      }
    }
    if ( (bidGblFlags & 2) != 0 )
    {
      v16 = 664585;
      goto LABEL_25;
    }
  }
  else
  {
    Value = -2147024882;
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(-2147024882, L"<CRegistry::GetDefaultProvider|OLEDB|ERR> ", 0x252u);
      if ( (bidGblFlags & 2) != 0 )
      {
        v16 = 608265;
LABEL_25:
        Value = bidTraceHR(off_1800C83A8[0], v16, L"<CRegistry::GetDefaultProvider|Trace|HR> ", Value);
      }
    }
  }
LABEL_26:
  operator delete(v8);
  return Value;
}

```

## disassembly

```asm
0x180044fd0  push    rbp
0x180044fd2  push    rdi
0x180044fd3  push    r12
0x180044fd5  push    r14
0x180044fd7  push    r15
0x180044fd9  sub     rsp, 3B0h
0x180044fe0  lea     rbp, [rsp+30h]
0x180044fe5  mov     [rbp+3A0h+arg_0], rbx
0x180044fec  mov     [rbp+3A0h+arg_18], rsi
0x180044ff3  mov     rax, cs:__security_cookie
0x180044ffa  xor     rax, rbp
0x180044ffd  mov     [rbp+3A0h+var_30], rax
0x180045004  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180045008  mov     r15, r8
0x18004500b  mov     rax, rsi
0x18004500e  xor     r12d, r12d
0x180045011  mov     r14, rdx
0x180045014  inc     rax
0x180045017  cmp     [rdx+rax*2], r12w
0x18004501c  jnz     short loc_180045014
0x18004501e  lea     rdi, [rax+1]
0x180045022  mov     qword ptr [rbp+3A0h+cbData], r12
0x180045026  cmp     rdi, 200h
0x18004502d  ja      short loc_18004505F
0x18004502f  lea     rax, [rdi+rdi]
0x180045033  mov     rbx, r12
0x180045036  lea     rcx, [rax+0Fh]
0x18004503a  cmp     rcx, rax
0x18004503d  ja      short loc_180045049
0x18004503f  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180045049  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18004504d  mov     rax, rcx
0x180045050  call    _alloca_probe
0x180045055  sub     rsp, rcx
0x180045058  lea     rcx, [rsp+3D0h+cbData]
0x18004505d  jmp     short loc_180045086
0x18004505f  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180045066  mov     eax, 2
0x18004506b  mul     rdi
0x18004506e  mov     edx, 1300000h
0x180045073  cmovb   rax, rsi
0x180045077  mov     r8, rax
0x18004507a  call    cs:__imp_MpHeapAlloc
0x180045080  mov     rbx, rax
0x180045083  mov     rcx, rax; unsigned __int16 *
0x180045086  mov     [rbp+3A0h+var_390], rcx
0x18004508a  test    rcx, rcx
0x18004508d  jnz     short loc_1800450CE
0x18004508f  mov     eax, cs:_bidGblFlags
0x180045095  mov     edi, 8007000Eh
0x18004509a  test    al, 2
0x18004509c  jz      loc_180045205
0x1800450a2  mov     r8d, 252h; unsigned int
0x1800450a8  lea     rdx, aCregistryGetde_0; "<CRegistry::GetDefaultProvider|OLEDB|ER"...
0x1800450af  mov     ecx, edi; int
0x1800450b1  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800450b6  mov     eax, cs:_bidGblFlags
0x1800450bc  test    al, 2
0x1800450be  jz      loc_180045205
0x1800450c4  mov     edx, 94809h
0x1800450c9  jmp     loc_1800451ED
0x1800450ce  mov     r8, r14; unsigned __int16 *
0x1800450d1  mov     [rbp+3A0h+hKey], r12
0x1800450d5  mov     rdx, rdi; unsigned __int64
0x1800450d8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800450dd  lea     r8, [rbp+3A0h+cbData]; unsigned __int16 **
0x1800450e1  mov     edi, eax
0x1800450e3  lea     rdx, [rbp+3A0h+var_390]; unsigned __int16 **
0x1800450e7  call    ?SeparateSchemeFromPrefix@CRegistry@@AEAAHPEAPEAG0@Z; CRegistry::SeparateSchemeFromPrefix(ushort * *,ushort * *)
0x1800450ec  test    eax, eax
0x1800450ee  jz      loc_1800451DF
0x1800450f4  mov     rcx, qword ptr [rbp+3A0h+cbData]
0x1800450f8  inc     rsi
0x1800450fb  cmp     [rcx+rsi*2], r12w
0x180045100  jnz     short loc_1800450F8
0x180045102  lea     rax, [rsi+1Ah]
0x180045106  mov     edx, 180h; unsigned __int64
0x18004510b  cmp     rax, rdx
0x18004510e  jb      short loc_18004513B
0x180045110  test    byte ptr cs:_bidGblFlags, 2
0x180045117  mov     edi, 80070057h
0x18004511c  jz      loc_180045205
0x180045122  mov     r8d, 262h; unsigned int
0x180045128  lea     rdx, aCregistryGetde_0; "<CRegistry::GetDefaultProvider|OLEDB|ER"...
0x18004512f  mov     ecx, edi; int
0x180045131  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180045136  jmp     loc_180045205
0x18004513b  lea     rax, aOledb; "\\oledb"
0x180045142  mov     [rsp+3D0h+lpcbData], rax
0x180045147  lea     r9, aProtocolsHandl; "PROTOCOLS\\Handler\\"
0x18004514e  mov     [rsp+3D0h+phkResult], rcx
0x180045153  lea     r8, aLsLsLs; "%ls%ls%ls"
0x18004515a  lea     rcx, [rbp+3A0h+SubKey]; unsigned __int16 *
0x18004515e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180045163  lea     rax, [rbp+3A0h+hKey]
0x180045167  mov     r9d, 1; samDesired
0x18004516d  xor     r8d, r8d; ulOptions
0x180045170  mov     [rsp+3D0h+phkResult], rax; phkResult
0x180045175  lea     rdx, [rbp+3A0h+SubKey]; lpSubKey
0x180045179  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180045180  call    cs:__imp_RegOpenKeyExW
0x180045186  mov     edi, eax
0x180045188  test    eax, eax
0x18004518a  jnz     short loc_1800451DF
0x18004518c  mov     rcx, [rbp+3A0h+hKey]; hKey
0x180045190  lea     rax, [rbp+3A0h+cbData]
0x180045194  mov     [rsp+3D0h+lpcbData], rax; lpcbData
0x180045199  lea     rdx, aClsid_0; "CLSID"
0x1800451a0  lea     rax, [rbp+3A0h+Data]
0x1800451a4  mov     [rbp+3A0h+cbData], 4Eh ; 'N'
0x1800451ab  xor     r9d, r9d; lpType
0x1800451ae  mov     [rsp+3D0h+phkResult], rax; lpData
0x1800451b3  xor     r8d, r8d; lpReserved
0x1800451b6  call    cs:__imp_RegQueryValueExW
0x1800451bc  mov     edi, eax
0x1800451be  test    eax, eax
0x1800451c0  jnz     short loc_1800451D5
0x1800451c2  lea     r8d, [rax+27h]; cchMax
0x1800451c6  mov     rcx, r15; rguid
0x1800451c9  lea     rdx, [rbp+3A0h+Data]; lpsz
0x1800451cd  call    cs:__imp_StringFromGUID2
0x1800451d3  mov     edi, eax
0x1800451d5  mov     rcx, [rbp+3A0h+hKey]; hKey
0x1800451d9  call    cs:__imp_RegCloseKey
0x1800451df  test    byte ptr cs:_bidGblFlags, 2
0x1800451e6  jz      short loc_180045205
0x1800451e8  mov     edx, 0A2409h
0x1800451ed  mov     rcx, cs:off_1800C83A8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800451f4  lea     r8, aCregistryGetde; "<CRegistry::GetDefaultProvider|Trace|HR"...
0x1800451fb  mov     r9d, edi
0x1800451fe  call    _bidTraceHR
0x180045203  mov     edi, eax
0x180045205  mov     rcx, rbx; void *
0x180045208  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004520d  mov     eax, edi
0x18004520f  mov     rcx, [rbp+3A0h+var_30]
0x180045216  xor     rcx, rbp; StackCookie
0x180045219  call    __security_check_cookie
0x18004521e  mov     rbx, [rbp+3A0h+arg_0]
0x180045225  mov     rsi, [rbp+3A0h+arg_18]
0x18004522c  lea     rsp, [rbp+380h]
0x180045233  pop     r15
0x180045235  pop     r14
0x180045237  pop     r12
0x180045239  pop     rdi
0x18004523a  pop     rbp
0x18004523b  retn
```
