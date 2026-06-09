# CSharingConfiguration::GetShare(DEF_SHARE_ID,IShareInfo * *)

- ea: `0x180003010`
- end: `0x180003233`
- name: `?GetShare@CSharingConfiguration@@UEAAJW4DEF_SHARE_ID@@PEAPEAUIShareInfo@@@Z`
- size: `547`
- prototype: `int(CSharingConfiguration *__hidden this, enum DEF_SHARE_ID, struct IShareInfo **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180002ef0`
- `0x180003010`
- `0x18000323c`
- `0x1800254e0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800030e8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800030e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800031be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800031be`
- `SHELL32!SHGetFolderPathEx` at `0x180003097`
- `SHELL32!SHGetFolderPathEx` at `0x180003097`
- `SHLWAPI!__imp_StrCmpICW` at `0x180003193`
- `SHLWAPI!__imp_StrCmpICW` at `0x180003193`

## pseudocode

```c
__int64 __fastcall CSharingConfiguration::GetShare(
        CSharingConfiguration *this,
        enum DEF_SHARE_ID a2,
        struct IShareInfo **a3)
{
  HRESULT ShareName; // ebx
  GUID v6; // xmm0
  CSharingConfiguration *v7; // rcx
  unsigned int v8; // r9d
  __int64 v10; // [rsp+30h] [rbp-D0h] BYREF
  int v11; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR pszStr2; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v13; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID ppv[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszStr1[88]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v16[528]; // [rsp+110h] [rbp+10h] BYREF

  ShareName = -2147467261;
  if ( !a3 )
    return (unsigned int)ShareName;
  CShareCache::Refresh(this);
  *a3 = 0;
  *(_OWORD *)ppv = 0;
  if ( a2 == DEFSHAREID_USERS )
  {
    v6 = FOLDERID_UserProfiles;
    goto LABEL_6;
  }
  if ( a2 == DEFSHAREID_PUBLIC )
  {
    v6 = FOLDERID_Public;
LABEL_6:
    *(GUID *)ppv = v6;
  }
  ShareName = SHGetFolderPathEx(ppv, 0, 0, v16, 260);
  if ( ShareName >= 0 )
  {
    ShareName = CSharingConfiguration::_GetShareName(v7, a2, pszStr1, v8);
    if ( ShareName >= 0 )
    {
      ppv[0] = 0;
      ShareName = CoCreateInstance(&CLSID_ShareManager, 0, 1u, &GUID_5bb62628_92e7_4f54_81a5_29c579341e13, ppv);
      if ( ShareName >= 0 )
      {
        v13 = 0;
        ShareName = (*(__int64 (__fastcall **)(LPVOID, _BYTE *, __int64, __int64 *))(*(_QWORD *)ppv[0] + 56LL))(
                      ppv[0],
                      v16,
                      1,
                      &v13);
        if ( ShareName >= 0 )
        {
          v11 = 0;
          v10 = 0;
          while ( !*a3 )
          {
            if ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v13 + 24LL))(
                    v13,
                    1,
                    &v10,
                    &v11) )
            {
              pszStr2 = 0;
              ShareName = (*(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v10 + 32LL))(v10, &pszStr2);
              if ( ShareName >= 0 )
              {
                if ( !StrCmpICW(pszStr1, pszStr2) )
                  ShareName = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IShareInfo **))v10)(
                                v10,
                                &GUID_98ab8446_e195_42ec_b4fc_5f8d1891a4ad,
                                a3);
                CoTaskMemFree((LPVOID)pszStr2);
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
              if ( ShareName >= 0 )
                continue;
            }
            if ( ShareName < 0 )
              goto LABEL_22;
            break;
          }
          if ( !*a3 )
            ShareName = -2147024894;
LABEL_22:
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        }
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv[0] + 16LL))(ppv[0]);
      }
    }
  }
  return (unsigned int)ShareName;
}

```

## disassembly

```asm
0x180003010  mov     [rsp-8+arg_0], rbx
0x180003015  push    rbp
0x180003016  push    rsi
0x180003017  push    rdi
0x180003018  lea     rbp, [rsp-230h]
0x180003020  sub     rsp, 330h
0x180003027  mov     rax, cs:__security_cookie
0x18000302e  xor     rax, rsp
0x180003031  mov     [rbp+240h+var_20], rax
0x180003038  mov     rdi, r8
0x18000303b  mov     esi, edx
0x18000303d  mov     ebx, 80004003h
0x180003042  test    r8, r8
0x180003045  jz      loc_18000320F
0x18000304b  call    ?Refresh@CShareCache@@QEAAXXZ; CShareCache::Refresh(void)
0x180003050  mov     ecx, esi
0x180003052  mov     qword ptr [rdi], 0
0x180003059  xorps   xmm0, xmm0
0x18000305c  movups  xmmword ptr [rsp+340h+var_2F0], xmm0
0x180003061  sub     ecx, 1
0x180003064  jz      short loc_180003074
0x180003066  cmp     ecx, 1
0x180003069  jnz     short loc_180003081
0x18000306b  movups  xmm0, xmmword ptr cs:FOLDERID_Public.Data1
0x180003072  jmp     short loc_18000307B
0x180003074  movups  xmm0, xmmword ptr cs:FOLDERID_UserProfiles.Data1
0x18000307b  movdqu  xmmword ptr [rsp+340h+var_2F0], xmm0
0x180003081  lea     r9, [rbp+240h+var_230]
0x180003085  mov     dword ptr [rsp+340h+ppv], 104h
0x18000308d  xor     r8d, r8d
0x180003090  lea     rcx, [rsp+340h+var_2F0]
0x180003095  xor     edx, edx
0x180003097  call    cs:__imp_SHGetFolderPathEx
0x18000309d  mov     ebx, eax
0x18000309f  test    eax, eax
0x1800030a1  js      loc_18000320F
0x1800030a7  lea     r8, [rsp+340h+pszStr1]; unsigned __int16 *
0x1800030ac  mov     edx, esi; enum DEF_SHARE_ID
0x1800030ae  call    ?_GetShareName@CSharingConfiguration@@AEAAJW4DEF_SHARE_ID@@PEAGK@Z; CSharingConfiguration::_GetShareName(DEF_SHARE_ID,ushort *,ulong)
0x1800030b3  mov     ebx, eax
0x1800030b5  test    eax, eax
0x1800030b7  js      loc_18000320F
0x1800030bd  lea     rax, [rsp+340h+var_2F0]
0x1800030c2  mov     [rsp+340h+var_2F0], 0
0x1800030cb  mov     esi, 1
0x1800030d0  mov     [rsp+340h+ppv], rax; ppv
0x1800030d5  mov     r8d, esi; dwClsContext
0x1800030d8  lea     r9, _GUID_5bb62628_92e7_4f54_81a5_29c579341e13; riid
0x1800030df  xor     edx, edx; pUnkOuter
0x1800030e1  lea     rcx, CLSID_ShareManager; rclsid
0x1800030e8  call    cs:__imp_CoCreateInstance
0x1800030ee  mov     ebx, eax
0x1800030f0  test    eax, eax
0x1800030f2  js      loc_18000320F
0x1800030f8  mov     rcx, [rsp+340h+var_2F0]
0x1800030fd  lea     r9, [rsp+340h+var_2F8]
0x180003102  mov     [rsp+340h+var_2F8], 0
0x18000310b  lea     rdx, [rbp+240h+var_230]
0x18000310f  mov     r8d, esi
0x180003112  mov     rax, [rcx]
0x180003115  mov     rax, [rax+38h]
0x180003119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000311e  mov     ebx, eax
0x180003120  test    eax, eax
0x180003122  js      loc_1800031FE
0x180003128  mov     [rsp+340h+var_308], 0
0x180003130  mov     [rsp+340h+var_310], 0
0x180003139  cmp     qword ptr [rdi], 0
0x18000313d  jnz     loc_1800031E1
0x180003143  mov     rcx, [rsp+340h+var_2F8]
0x180003148  lea     r9, [rsp+340h+var_308]
0x18000314d  lea     r8, [rsp+340h+var_310]
0x180003152  mov     edx, esi
0x180003154  mov     rax, [rcx]
0x180003157  mov     rax, [rax+18h]
0x18000315b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003160  test    eax, eax
0x180003162  jnz     short loc_1800031DD
0x180003164  mov     rcx, [rsp+340h+var_310]
0x180003169  lea     rdx, [rsp+340h+pszStr2]
0x18000316e  mov     [rsp+340h+pszStr2], 0
0x180003177  mov     rax, [rcx]
0x18000317a  mov     rax, [rax+20h]
0x18000317e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003183  mov     ebx, eax
0x180003185  test    eax, eax
0x180003187  js      short loc_1800031C4
0x180003189  mov     rdx, [rsp+340h+pszStr2]; pszStr2
0x18000318e  lea     rcx, [rsp+340h+pszStr1]; pszStr1
0x180003193  call    cs:__imp_StrCmpICW
0x180003199  test    eax, eax
0x18000319b  jnz     short loc_1800031B9
0x18000319d  mov     rcx, [rsp+340h+var_310]
0x1800031a2  lea     rdx, _GUID_98ab8446_e195_42ec_b4fc_5f8d1891a4ad
0x1800031a9  mov     r8, rdi
0x1800031ac  mov     rax, [rcx]
0x1800031af  mov     rax, [rax]
0x1800031b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031b7  mov     ebx, eax
0x1800031b9  mov     rcx, [rsp+340h+pszStr2]; pv
0x1800031be  call    cs:__imp_CoTaskMemFree
0x1800031c4  mov     rcx, [rsp+340h+var_310]
0x1800031c9  mov     rax, [rcx]
0x1800031cc  mov     rax, [rax+10h]
0x1800031d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031d5  test    ebx, ebx
0x1800031d7  jns     loc_180003139
0x1800031dd  test    ebx, ebx
0x1800031df  js      short loc_1800031ED
0x1800031e1  cmp     qword ptr [rdi], 0
0x1800031e5  mov     eax, 80070002h
0x1800031ea  cmovz   ebx, eax
0x1800031ed  mov     rcx, [rsp+340h+var_2F8]
0x1800031f2  mov     rax, [rcx]
0x1800031f5  mov     rax, [rax+10h]
0x1800031f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031fe  mov     rcx, [rsp+340h+var_2F0]
0x180003203  mov     rax, [rcx]
0x180003206  mov     rax, [rax+10h]
0x18000320a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000320f  mov     eax, ebx
0x180003211  mov     rcx, [rbp+240h+var_20]
0x180003218  xor     rcx, rsp; StackCookie
0x18000321b  call    __security_check_cookie
0x180003220  mov     rbx, [rsp+340h+arg_0]
0x180003228  add     rsp, 330h
0x18000322f  pop     rdi
0x180003230  pop     rsi
0x180003231  pop     rbp
0x180003232  retn
```
