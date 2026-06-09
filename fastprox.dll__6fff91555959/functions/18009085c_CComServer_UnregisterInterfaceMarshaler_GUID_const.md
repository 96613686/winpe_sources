# CComServer::UnregisterInterfaceMarshaler(_GUID const &)

- ea: `0x18009085c`
- end: `0x180090ae7`
- name: `?UnregisterInterfaceMarshaler@CComServer@@IEAAJAEBU_GUID@@@Z`
- size: `651`
- prototype: `int(CComServer *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180084b80`

## callees

- `0x180080514`
- `0x18008fcb4`
- `0x18009085c`
- `0x1800910f8`
- `0x18009124c`
- `0x180091694`
- `0x180091760`
- `0x1800919b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800908a3`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800908a3`
- `wbemcomn!GetMemLogObject` at `0x18009092d`
- `wbemcomn!GetMemLogObject` at `0x180090983`
- `wbemcomn!GetMemLogObject` at `0x180090a23`
- `wbemcomn!GetMemLogObject` at `0x180090a7a`
- `wbemcomn!GetMemLogObject` at `0x18009092d`
- `wbemcomn!GetMemLogObject` at `0x180090983`
- `wbemcomn!GetMemLogObject` at `0x180090a23`
- `wbemcomn!GetMemLogObject` at `0x180090a7a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180090938`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009098e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180090a2e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180090a85`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180090938`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009098e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180090a2e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180090a85`

## string_xrefs

- `0x18009090f`: `ProxyStubClsid32`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CComServer::UnregisterInterfaceMarshaler(CComServer *this, const struct _GUID *a2)
{
  int v2; // edx
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
  int v6; // edi
  int v7; // edi
  CMemoryLog *v8; // rax
  int v9; // r8d
  int v10; // ecx
  __int64 v11; // r8
  int v12; // r9d
  CMemoryLog *MemLogObject; // rax
  int v14; // edi
  int v15; // edi
  CMemoryLog *v16; // rax
  int v17; // r8d
  CMemoryLog *v18; // rax
  int v19; // r8d
  __int64 v21; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v22[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 (__fastcall *v23)(); // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  OLECHAR sz[128]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v26[256]; // [rsp+160h] [rbp+60h] BYREF

  v21 = 0;
  StringFromGUID2(a2, sz, 128);
  CreatePathString(v26, v2, sz, L"SOFTWARE\\Classes\\Interface\\");
  v6 = DLRegOpenKeyExW(v3, (unsigned int)v26, v4, v5, (__int64)&v21);
  if ( v6 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v6);
    v10 = (int)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, v11, v26);
    }
  }
  else
  {
    v22[0] = 0;
    v23 = DLRegCloseKey;
    v24 = v21;
    v7 = DLRegDeleteKeyW(v21, L"ProxyStubClsid32");
    if ( v7 )
    {
      v8 = GetMemLogObject();
      CMemoryLog::Write(v8, v7);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_LS(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, v9, v7, (__int64)v26);
      }
    }
    ScopeGuardImpl1<unsigned short * (*)(unsigned short const *),unsigned short *>::~ScopeGuardImpl1<unsigned short * (*)(unsigned short const *),unsigned short *>((__int64)v22);
  }
  v14 = DLRegOpenKeyExW(v10, (unsigned int)L"SOFTWARE\\Classes\\Interface", v11, v12, (__int64)&v21);
  if ( v14 )
  {
    v18 = GetMemLogObject();
    CMemoryLog::Write(v18, v14);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_LS(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, v19, v14, (__int64)sz);
    }
  }
  else
  {
    v22[0] = 0;
    v23 = DLRegCloseKey;
    v24 = v21;
    v15 = DLRegDeleteKeyW(v21, sz);
    if ( v15 )
    {
      v16 = GetMemLogObject();
      CMemoryLog::Write(v16, v15);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_LS(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, v17, v15, (__int64)sz);
      }
    }
    ScopeGuardImpl1<unsigned short * (*)(unsigned short const *),unsigned short *>::~ScopeGuardImpl1<unsigned short * (*)(unsigned short const *),unsigned short *>((__int64)v22);
  }
  return 0;
}

```

## disassembly

```asm
0x18009085c  mov     [rsp-8+arg_0], rbx
0x180090861  mov     [rsp-8+arg_10], rsi
0x180090866  push    rbp
0x180090867  push    rdi
0x180090868  push    r12
0x18009086a  lea     rbp, [rsp-270h]
0x180090872  sub     rsp, 370h
0x180090879  mov     rax, cs:__security_cookie
0x180090880  xor     rax, rsp
0x180090883  mov     [rbp+280h+var_20], rax
0x18009088a  mov     rcx, rdx; rguid
0x18009088d  xor     ebx, ebx
0x18009088f  mov     [rsp+380h+var_350], ebx
0x180090893  mov     [rsp+380h+var_348], rbx
0x180090898  mov     r8d, 80h; cchMax
0x18009089e  lea     rdx, [rsp+380h+sz]; lpsz
0x1800908a3  call    cs:__imp_StringFromGUID2
0x1800908a9  lea     r9, aSoftwareClasse_0; "SOFTWARE\\Classes\\Interface\\"
0x1800908b0  lea     r8, [rsp+380h+sz]; unsigned __int16 *
0x1800908b5  lea     rcx, [rbp+280h+var_220]; unsigned __int16 *
0x1800908b9  call    ?CreatePathString@@YAJPEAGH00@Z; CreatePathString(ushort *,int,ushort *,ushort *)
0x1800908be  lea     rax, [rsp+380h+var_348]
0x1800908c3  mov     [rsp+380h+var_360], rax
0x1800908c8  lea     rdx, [rbp+280h+var_220]
0x1800908cc  call    DLRegOpenKeyExW
0x1800908d1  mov     edi, eax
0x1800908d3  lea     r12, DLRegCloseKey
0x1800908da  test    eax, eax
0x1800908dc  jnz     loc_180090983
0x1800908e2  mov     rax, [rsp+380h+var_348]
0x1800908e7  mov     [rsp+380h+var_340], dil
0x1800908ec  mov     [rsp+380h+var_338], r12
0x1800908f1  mov     [rsp+380h+var_330], rax
0x1800908f6  mov     [rsp+380h+var_350], 2
0x1800908fe  lea     ebx, [rdi+2]
0x180090901  and     ebx, 0FFFFFFFDh
0x180090904  mov     [rsp+380h+var_350], ebx
0x180090908  or      ebx, 1
0x18009090b  mov     [rsp+380h+var_350], ebx
0x18009090f  lea     rdx, aProxystubclsid; "ProxyStubClsid32"
0x180090916  mov     rcx, [rsp+380h+var_348]
0x18009091b  call    DLRegDeleteKeyW
0x180090920  mov     edi, eax
0x180090922  lea     rsi, WPP_GLOBAL_Control
0x180090929  test    eax, eax
0x18009092b  jz      short loc_180090970
0x18009092d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180090933  mov     edx, edi
0x180090935  mov     rcx, rax
0x180090938  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009093e  mov     rcx, cs:WPP_GLOBAL_Control
0x180090945  cmp     rcx, rsi
0x180090948  jz      short loc_180090970
0x18009094a  test    byte ptr [rcx+1Ch], 1
0x18009094e  jz      short loc_180090970
0x180090950  cmp     byte ptr [rcx+19h], 2
0x180090954  jb      short loc_180090970
0x180090956  mov     edx, 2Bh ; '+'
0x18009095b  lea     rax, [rbp+280h+var_220]
0x18009095f  mov     [rsp+380h+var_360], rax
0x180090964  mov     r9d, edi
0x180090967  mov     rcx, [rcx+10h]
0x18009096b  call    WPP_SF_LS
0x180090970  and     ebx, 0FFFFFFFEh
0x180090973  mov     [rsp+380h+var_350], ebx
0x180090977  lea     rcx, [rsp+380h+var_340]
0x18009097c  call    ??1?$ScopeGuardImpl1@P6APEAGPEBG@ZPEAG@@QEAA@XZ; ScopeGuardImpl1<ushort * (*)(ushort const *),ushort *>::~ScopeGuardImpl1<ushort * (*)(ushort const *),ushort *>(void)
0x180090981  jmp     short loc_1800909C5
0x180090983  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180090989  mov     edx, edi
0x18009098b  mov     rcx, rax
0x18009098e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180090994  lea     rsi, WPP_GLOBAL_Control
0x18009099b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800909a2  cmp     rcx, rsi
0x1800909a5  jz      short loc_1800909C5
0x1800909a7  test    byte ptr [rcx+1Ch], 1
0x1800909ab  jz      short loc_1800909C5
0x1800909ad  cmp     byte ptr [rcx+19h], 2
0x1800909b1  jb      short loc_1800909C5
0x1800909b3  mov     edx, 2Ch ; ','
0x1800909b8  lea     r9, [rbp+280h+var_220]
0x1800909bc  mov     rcx, [rcx+10h]
0x1800909c0  call    WPP_SF_S
0x1800909c5  lea     rax, [rsp+380h+var_348]
0x1800909ca  mov     [rsp+380h+var_360], rax
0x1800909cf  lea     rdx, aSoftwareClasse_1; "SOFTWARE\\Classes\\Interface"
0x1800909d6  call    DLRegOpenKeyExW
0x1800909db  mov     edi, eax
0x1800909dd  test    eax, eax
0x1800909df  jnz     loc_180090A7A
0x1800909e5  mov     rax, [rsp+380h+var_348]
0x1800909ea  mov     [rsp+380h+var_340], dil
0x1800909ef  mov     [rsp+380h+var_338], r12
0x1800909f4  mov     [rsp+380h+var_330], rax
0x1800909f9  or      ebx, 8
0x1800909fc  mov     [rsp+380h+var_350], ebx
0x180090a00  and     ebx, 0FFFFFFF7h
0x180090a03  mov     [rsp+380h+var_350], ebx
0x180090a07  or      ebx, 4
0x180090a0a  mov     [rsp+380h+var_350], ebx
0x180090a0e  lea     rdx, [rsp+380h+sz]
0x180090a13  mov     rcx, [rsp+380h+var_348]
0x180090a18  call    DLRegDeleteKeyW
0x180090a1d  mov     edi, eax
0x180090a1f  test    eax, eax
0x180090a21  jz      short loc_180090A67
0x180090a23  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180090a29  mov     edx, edi
0x180090a2b  mov     rcx, rax
0x180090a2e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180090a34  mov     rcx, cs:WPP_GLOBAL_Control
0x180090a3b  cmp     rcx, rsi
0x180090a3e  jz      short loc_180090A67
0x180090a40  test    byte ptr [rcx+1Ch], 1
0x180090a44  jz      short loc_180090A67
0x180090a46  cmp     byte ptr [rcx+19h], 2
0x180090a4a  jb      short loc_180090A67
0x180090a4c  mov     edx, 2Dh ; '-'
0x180090a51  lea     rax, [rsp+380h+sz]
0x180090a56  mov     [rsp+380h+var_360], rax
0x180090a5b  mov     r9d, edi
0x180090a5e  mov     rcx, [rcx+10h]
0x180090a62  call    WPP_SF_LS
0x180090a67  and     ebx, 0FFFFFFFBh
0x180090a6a  mov     [rsp+380h+var_350], ebx
0x180090a6e  lea     rcx, [rsp+380h+var_340]
0x180090a73  call    ??1?$ScopeGuardImpl1@P6APEAGPEBG@ZPEAG@@QEAA@XZ; ScopeGuardImpl1<ushort * (*)(ushort const *),ushort *>::~ScopeGuardImpl1<ushort * (*)(ushort const *),ushort *>(void)
0x180090a78  jmp     short loc_180090ABE
0x180090a7a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180090a80  mov     edx, edi
0x180090a82  mov     rcx, rax
0x180090a85  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180090a8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180090a92  cmp     rcx, rsi
0x180090a95  jz      short loc_180090ABE
0x180090a97  test    byte ptr [rcx+1Ch], 1
0x180090a9b  jz      short loc_180090ABE
0x180090a9d  cmp     byte ptr [rcx+19h], 2
0x180090aa1  jb      short loc_180090ABE
0x180090aa3  mov     edx, 2Eh ; '.'
0x180090aa8  lea     rax, [rsp+380h+sz]
0x180090aad  mov     [rsp+380h+var_360], rax
0x180090ab2  mov     r9d, edi
0x180090ab5  mov     rcx, [rcx+10h]
0x180090ab9  call    WPP_SF_LS
0x180090abe  xor     eax, eax
0x180090ac0  mov     rcx, [rbp+280h+var_20]
0x180090ac7  xor     rcx, rsp; StackCookie
0x180090aca  call    __security_check_cookie
0x180090acf  lea     r11, [rsp+380h+var_10]
0x180090ad7  mov     rbx, [r11+20h]
0x180090adb  mov     rsi, [r11+30h]
0x180090adf  mov     rsp, r11
0x180090ae2  pop     r12
0x180090ae4  pop     rdi
0x180090ae5  pop     rbp
0x180090ae6  retn
```
