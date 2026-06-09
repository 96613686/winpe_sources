# UnregisterServer(CClassInfo *,int)

- ea: `0x180090af0`
- end: `0x180090de4`
- name: `?UnregisterServer@@YAJPEAUCClassInfo@@H@Z`
- size: `756`
- prototype: `__int64 __fastcall(struct CClassInfo *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180090f70`

## callees

- `0x180080514`
- `0x18008fcb4`
- `0x180090af0`
- `0x1800910f8`
- `0x18009124c`
- `0x180091694`
- `0x180091760`
- `0x1800919b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180090b37`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180090b37`
- `wbemcomn!GetMemLogObject` at `0x180090b58`
- `wbemcomn!GetMemLogObject` at `0x180090c1c`
- `wbemcomn!GetMemLogObject` at `0x180090c71`
- `wbemcomn!GetMemLogObject` at `0x180090d1f`
- `wbemcomn!GetMemLogObject` at `0x180090d77`
- `wbemcomn!GetMemLogObject` at `0x180090b58`
- `wbemcomn!GetMemLogObject` at `0x180090c1c`
- `wbemcomn!GetMemLogObject` at `0x180090c71`
- `wbemcomn!GetMemLogObject` at `0x180090d1f`
- `wbemcomn!GetMemLogObject` at `0x180090d77`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180090b63`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180090c28`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180090c7d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180090d2b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180090d83`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180090b63`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180090c28`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180090c7d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180090d2b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180090d83`

## string_xrefs

- `0x180090b3d`: `SOFTWARE\Classes\CLSID\`
- `0x180090cc6`: `SOFTWARE\Classes\CLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall UnregisterServer(const GUID *const *a1)
{
  int v1; // edx
  int v2; // ecx
  int PathString; // edi
  int v4; // r8d
  int v5; // r9d
  CMemoryLog *v6; // rax
  __int64 v7; // r8
  int v9; // r14d
  int v10; // r14d
  CMemoryLog *v11; // rax
  int v12; // r8d
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  CMemoryLog *MemLogObject; // rax
  int v17; // r14d
  int v18; // r14d
  CMemoryLog *v19; // rax
  int v20; // r8d
  CMemoryLog *v21; // rax
  int v22; // r8d
  __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v24[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 (__fastcall *v25)(); // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  OLECHAR sz[128]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v28[256]; // [rsp+160h] [rbp+60h] BYREF

  StringFromGUID2(a1[3], sz, 128);
  PathString = CreatePathString(v28, v1, sz, L"SOFTWARE\\Classes\\CLSID\\");
  if ( PathString >= 0 )
  {
    v23 = 0;
    v9 = DLRegOpenKeyExW(v2, (unsigned int)v28, v4, v5, (__int64)&v23);
    if ( v9 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v9);
      v13 = (int)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_LS(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, v14, v9, (__int64)v28);
      }
    }
    else
    {
      v24[0] = 0;
      v25 = DLRegCloseKey;
      v26 = v23;
      v10 = DLRegDeleteKeyW(v23, L"InProcServer32");
      if ( v10 )
      {
        v11 = GetMemLogObject();
        CMemoryLog::Write(v11, v10);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_LS(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v12, v10, (__int64)v28);
        }
      }
      ScopeGuardImpl1<unsigned short * (*)(unsigned short const *),unsigned short *>::~ScopeGuardImpl1<unsigned short * (*)(unsigned short const *),unsigned short *>((__int64)v24);
    }
    v17 = DLRegOpenKeyExW(v13, (unsigned int)L"SOFTWARE\\Classes\\CLSID", v14, v15, (__int64)&v23);
    if ( v17 )
    {
      v21 = GetMemLogObject();
      CMemoryLog::Write(v21, v17);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_LS(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v22, v17, (__int64)L"SOFTWARE\\Classes\\CLSID");
      }
    }
    else
    {
      v24[0] = 0;
      v25 = DLRegCloseKey;
      v26 = v23;
      v18 = DLRegDeleteKeyW(v23, sz);
      if ( v18 )
      {
        v19 = GetMemLogObject();
        CMemoryLog::Write(v19, v18);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_LS(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, v20, v18, (__int64)sz);
        }
      }
      ScopeGuardImpl1<unsigned short * (*)(unsigned short const *),unsigned short *>::~ScopeGuardImpl1<unsigned short * (*)(unsigned short const *),unsigned short *>((__int64)v24);
    }
    return 0;
  }
  else
  {
    v6 = GetMemLogObject();
    CMemoryLog::Write(v6, PathString);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, v7, sz);
    }
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180090af0  mov     [rsp-8+arg_8], rbx
0x180090af5  mov     [rsp-8+arg_10], rsi
0x180090afa  push    rbp
0x180090afb  push    rdi
0x180090afc  push    r12
0x180090afe  push    r13
0x180090b00  push    r14
0x180090b02  lea     rbp, [rsp-270h]
0x180090b0a  sub     rsp, 370h
0x180090b11  mov     rax, cs:__security_cookie
0x180090b18  xor     rax, rsp
0x180090b1b  mov     [rbp+290h+var_30], rax
0x180090b22  xor     ebx, ebx
0x180090b24  mov     [rsp+390h+var_360], ebx
0x180090b28  mov     r8d, 80h; cchMax
0x180090b2e  lea     rdx, [rsp+390h+sz]; lpsz
0x180090b33  mov     rcx, [rcx+18h]; rguid
0x180090b37  call    cs:__imp_StringFromGUID2
0x180090b3d  lea     r9, aSoftwareClasse_4; "SOFTWARE\\Classes\\CLSID\\"
0x180090b44  lea     r8, [rsp+390h+sz]; unsigned __int16 *
0x180090b49  lea     rcx, [rbp+290h+var_230]; unsigned __int16 *
0x180090b4d  call    ?CreatePathString@@YAJPEAGH00@Z; CreatePathString(ushort *,int,ushort *,ushort *)
0x180090b52  mov     edi, eax
0x180090b54  test    eax, eax
0x180090b56  jns     short loc_180090BA6
0x180090b58  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180090b5e  mov     edx, edi
0x180090b60  mov     rcx, rax
0x180090b63  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180090b69  lea     rsi, WPP_GLOBAL_Control
0x180090b70  mov     rcx, cs:WPP_GLOBAL_Control
0x180090b77  cmp     rcx, rsi
0x180090b7a  jz      short loc_180090B9C
0x180090b7c  test    byte ptr [rcx+1Ch], 1
0x180090b80  jz      short loc_180090B9C
0x180090b82  lea     edi, [rbx+2]
0x180090b85  cmp     [rcx+19h], dil
0x180090b89  jb      short loc_180090B9C
0x180090b8b  lea     edx, [rbx+16h]
0x180090b8e  lea     r9, [rsp+390h+sz]
0x180090b93  mov     rcx, [rcx+10h]
0x180090b97  call    WPP_SF_S
0x180090b9c  mov     eax, 80004005h
0x180090ba1  jmp     loc_180090DB9
0x180090ba6  mov     [rsp+390h+var_358], rbx
0x180090bab  lea     rax, [rsp+390h+var_358]
0x180090bb0  mov     [rsp+390h+var_370], rax
0x180090bb5  lea     rdx, [rbp+290h+var_230]
0x180090bb9  call    DLRegOpenKeyExW
0x180090bbe  mov     r14d, eax
0x180090bc1  mov     edi, 2
0x180090bc6  lea     r13, DLRegCloseKey
0x180090bcd  test    eax, eax
0x180090bcf  jnz     loc_180090C71
0x180090bd5  mov     rax, [rsp+390h+var_358]
0x180090bda  mov     [rsp+390h+var_350], r14b
0x180090bdf  mov     [rsp+390h+var_348], r13
0x180090be4  mov     [rsp+390h+var_340], rax
0x180090be9  mov     [rsp+390h+var_360], edi
0x180090bed  mov     ebx, edi
0x180090bef  and     ebx, 0FFFFFFFDh
0x180090bf2  mov     [rsp+390h+var_360], ebx
0x180090bf6  or      ebx, 1
0x180090bf9  mov     [rsp+390h+var_360], ebx
0x180090bfd  lea     rdx, aInprocserver32_0; "InProcServer32"
0x180090c04  mov     rcx, [rsp+390h+var_358]
0x180090c09  call    DLRegDeleteKeyW
0x180090c0e  mov     r14d, eax
0x180090c11  lea     rsi, WPP_GLOBAL_Control
0x180090c18  test    eax, eax
0x180090c1a  jz      short loc_180090C5E
0x180090c1c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180090c22  mov     edx, r14d
0x180090c25  mov     rcx, rax
0x180090c28  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180090c2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180090c35  cmp     rcx, rsi
0x180090c38  jz      short loc_180090C5E
0x180090c3a  test    byte ptr [rcx+1Ch], 1
0x180090c3e  jz      short loc_180090C5E
0x180090c40  cmp     [rcx+19h], dil
0x180090c44  jb      short loc_180090C5E
0x180090c46  lea     edx, [rdi+15h]
0x180090c49  lea     rax, [rbp+290h+var_230]
0x180090c4d  mov     [rsp+390h+var_370], rax
0x180090c52  mov     r9d, r14d
0x180090c55  mov     rcx, [rcx+10h]
0x180090c59  call    WPP_SF_LS
0x180090c5e  and     ebx, 0FFFFFFFEh
0x180090c61  mov     [rsp+390h+var_360], ebx
0x180090c65  lea     rcx, [rsp+390h+var_350]
0x180090c6a  call    ??1?$ScopeGuardImpl1@P6APEAGPEBG@ZPEAG@@QEAA@XZ; ScopeGuardImpl1<ushort * (*)(ushort const *),ushort *>::~ScopeGuardImpl1<ushort * (*)(ushort const *),ushort *>(void)
0x180090c6f  jmp     short loc_180090CBC
0x180090c71  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180090c77  mov     edx, r14d
0x180090c7a  mov     rcx, rax
0x180090c7d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180090c83  lea     rsi, WPP_GLOBAL_Control
0x180090c8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180090c91  cmp     rcx, rsi
0x180090c94  jz      short loc_180090CBC
0x180090c96  test    byte ptr [rcx+1Ch], 1
0x180090c9a  jz      short loc_180090CBC
0x180090c9c  cmp     [rcx+19h], dil
0x180090ca0  jb      short loc_180090CBC
0x180090ca2  mov     edx, 18h
0x180090ca7  lea     rax, [rbp+290h+var_230]
0x180090cab  mov     [rsp+390h+var_370], rax
0x180090cb0  mov     r9d, r14d
0x180090cb3  mov     rcx, [rcx+10h]
0x180090cb7  call    WPP_SF_LS
0x180090cbc  lea     rax, [rsp+390h+var_358]
0x180090cc1  mov     [rsp+390h+var_370], rax
0x180090cc6  lea     r12, aSoftwareClasse; "SOFTWARE\\Classes\\CLSID"
0x180090ccd  mov     rdx, r12
0x180090cd0  call    DLRegOpenKeyExW
0x180090cd5  mov     r14d, eax
0x180090cd8  test    eax, eax
0x180090cda  jnz     loc_180090D77
0x180090ce0  mov     rax, [rsp+390h+var_358]
0x180090ce5  mov     [rsp+390h+var_350], r14b
0x180090cea  mov     [rsp+390h+var_348], r13
0x180090cef  mov     [rsp+390h+var_340], rax
0x180090cf4  or      ebx, 8
0x180090cf7  mov     [rsp+390h+var_360], ebx
0x180090cfb  and     ebx, 0FFFFFFF7h
0x180090cfe  mov     [rsp+390h+var_360], ebx
0x180090d02  or      ebx, 4
0x180090d05  mov     [rsp+390h+var_360], ebx
0x180090d09  lea     rdx, [rsp+390h+sz]
0x180090d0e  mov     rcx, [rsp+390h+var_358]
0x180090d13  call    DLRegDeleteKeyW
0x180090d18  mov     r14d, eax
0x180090d1b  test    eax, eax
0x180090d1d  jz      short loc_180090D64
0x180090d1f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180090d25  mov     edx, r14d
0x180090d28  mov     rcx, rax
0x180090d2b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180090d31  mov     rcx, cs:WPP_GLOBAL_Control
0x180090d38  cmp     rcx, rsi
0x180090d3b  jz      short loc_180090D64
0x180090d3d  test    byte ptr [rcx+1Ch], 1
0x180090d41  jz      short loc_180090D64
0x180090d43  cmp     [rcx+19h], dil
0x180090d47  jb      short loc_180090D64
0x180090d49  mov     edx, 19h
0x180090d4e  lea     rax, [rsp+390h+sz]
0x180090d53  mov     [rsp+390h+var_370], rax
0x180090d58  mov     r9d, r14d
0x180090d5b  mov     rcx, [rcx+10h]
0x180090d5f  call    WPP_SF_LS
0x180090d64  and     ebx, 0FFFFFFFBh
0x180090d67  mov     [rsp+390h+var_360], ebx
0x180090d6b  lea     rcx, [rsp+390h+var_350]
0x180090d70  call    ??1?$ScopeGuardImpl1@P6APEAGPEBG@ZPEAG@@QEAA@XZ; ScopeGuardImpl1<ushort * (*)(ushort const *),ushort *>::~ScopeGuardImpl1<ushort * (*)(ushort const *),ushort *>(void)
0x180090d75  jmp     short loc_180090DB7
0x180090d77  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180090d7d  mov     edx, r14d
0x180090d80  mov     rcx, rax
0x180090d83  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180090d89  mov     rcx, cs:WPP_GLOBAL_Control
0x180090d90  cmp     rcx, rsi
0x180090d93  jz      short loc_180090DB7
0x180090d95  test    byte ptr [rcx+1Ch], 1
0x180090d99  jz      short loc_180090DB7
0x180090d9b  cmp     [rcx+19h], dil
0x180090d9f  jb      short loc_180090DB7
0x180090da1  mov     edx, 1Ah
0x180090da6  mov     [rsp+390h+var_370], r12
0x180090dab  mov     r9d, r14d
0x180090dae  mov     rcx, [rcx+10h]
0x180090db2  call    WPP_SF_LS
0x180090db7  xor     eax, eax
0x180090db9  mov     rcx, [rbp+290h+var_30]
0x180090dc0  xor     rcx, rsp; StackCookie
0x180090dc3  call    __security_check_cookie
0x180090dc8  lea     r11, [rsp+390h+var_20]
0x180090dd0  mov     rbx, [r11+38h]
0x180090dd4  mov     rsi, [r11+40h]
0x180090dd8  mov     rsp, r11
0x180090ddb  pop     r14
0x180090ddd  pop     r13
0x180090ddf  pop     r12
0x180090de1  pop     rdi
0x180090de2  pop     rbp
0x180090de3  retn
```
