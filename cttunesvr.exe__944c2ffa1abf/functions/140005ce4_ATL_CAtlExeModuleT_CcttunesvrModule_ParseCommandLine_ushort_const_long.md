# ATL::CAtlExeModuleT<CcttunesvrModule>::ParseCommandLine(ushort const *,long *)

- ea: `0x140005ce4`
- end: `0x140005f31`
- name: `?ParseCommandLine@?$CAtlExeModuleT@VCcttunesvrModule@@@ATL@@QEAA_NPEBGPEAJ@Z`
- size: `589`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400063fc`

## callees

- `0x140004f48`
- `0x14000552c`
- `0x1400059e8`
- `0x140005ce4`
- `0x1400061fc`
- `0x140006334`
- `0x1400065f0`
- `0x140007010`

## import_xrefs

- `USER32!CharNextW` at `0x140005d4a`
- `USER32!CharNextW` at `0x140005d58`
- `USER32!CharNextW` at `0x140005dd2`
- `USER32!CharNextW` at `0x140005de0`
- `USER32!CharNextW` at `0x140005df6`
- `USER32!CharNextW` at `0x140005d4a`
- `USER32!CharNextW` at `0x140005d58`
- `USER32!CharNextW` at `0x140005dd2`
- `USER32!CharNextW` at `0x140005de0`
- `USER32!CharNextW` at `0x140005df6`

## pseudocode

```c
char __fastcall ATL::CAtlExeModuleT<CcttunesvrModule>::ParseCommandLine(__int64 a1, const WCHAR *a2, int *a3)
{
  const WCHAR *v4; // rbx
  WCHAR *v5; // rax
  int v7; // edx
  ATL::CAtlComModule *v8; // rcx
  const struct _GUID *v9; // r8
  ATL::CAtlModule *v10; // rcx
  WCHAR *v11; // rax
  const WCHAR *v12; // rax
  int updated; // eax
  const unsigned __int16 *v14; // rdx
  struct ATL::_ATL_OBJMAP_ENTRY30 **v15; // rbx
  __int64 *i; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v17; // rdi
  int v18; // eax
  const struct ATL::_ATL_CATMAP_ENTRY *v19; // rax
  int v20; // eax
  const unsigned __int16 *v21; // [rsp+20h] [rbp-30h] BYREF
  const wchar_t *v22; // [rsp+28h] [rbp-28h]
  __int128 v23; // [rsp+30h] [rbp-20h]
  WCHAR sz[4]; // [rsp+40h] [rbp-10h] BYREF

  *a3 = 0;
  v4 = a2;
  wcscpy(sz, L"-/");
  if ( a2 )
  {
LABEL_2:
    if ( *v4 )
    {
      v5 = sz;
      while ( 1 )
      {
        if ( !*v5 )
        {
LABEL_7:
          v4 = CharNextW(v4);
          if ( v4 )
            goto LABEL_2;
          return 1;
        }
        if ( *v4 == *v5 )
          break;
        v5 = CharNextW(v5);
        if ( !v5 )
          goto LABEL_7;
      }
LABEL_19:
      v12 = CharNextW(v4);
      v4 = v12;
      if ( !v12 )
        return 1;
      if ( (unsigned int)ATL::CAtlModule::WordCmpI(v12, L"UnregServer") )
      {
        if ( (unsigned int)ATL::CAtlModule::WordCmpI(v4, L"RegServer") )
        {
          for ( ; v4; v4 = CharNextW(v4) )
          {
            if ( !*v4 )
              break;
            v11 = sz;
            do
            {
              if ( !*v11 )
                break;
              if ( *v4 == *v11 )
                goto LABEL_19;
              v11 = CharNextW(v11);
            }
            while ( v11 );
          }
          return 1;
        }
        v21 = L"APPID";
        v22 = L"{C3A34354-660F-41EE-B072-2AEA5E3A80AF}";
        v23 = 0;
        updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v10, 0x65u, 1, &v21);
        *a3 = updated;
        if ( updated < 0 )
          return 0;
        v15 = off_14000B100;
        for ( i = off_14000B108; v15 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)i; ++v15 )
        {
          v17 = *v15;
          if ( *v15 )
          {
            v18 = (*((__int64 (__fastcall **)(__int64))v17 + 1))(1);
            if ( v18 < 0 )
              goto LABEL_36;
            v19 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*((__int64 (**)(void))v17 + 7))();
            v18 = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v17, v19, 1);
            if ( v18 < 0 )
              goto LABEL_36;
            i = off_14000B108;
          }
        }
        v18 = ATL::AtlRegisterTypeLib(off_14000B0F8, v14);
        if ( v18 >= 0 )
        {
          if ( ATL::_pPerfRegFunc )
            v18 = ((__int64 (__fastcall *)(HMODULE))ATL::_pPerfRegFunc)(hInstance);
        }
      }
      else
      {
        if ( !ATL::_pPerfUnRegFunc || (v20 = ATL::_pPerfUnRegFunc(), v20 >= 0) )
          v20 = ATL::CAtlComModule::UnregisterServer(v8, v7, v9);
        *a3 = v20;
        if ( v20 < 0 )
          return 0;
        v21 = L"APPID";
        v22 = L"{C3A34354-660F-41EE-B072-2AEA5E3A80AF}";
        v23 = 0;
        v18 = ATL::CAtlModule::UpdateRegistryFromResourceS(v8, 0x65u, 0, &v21);
      }
LABEL_36:
      *a3 = v18;
      return 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x140005ce4  mov     [rsp-18h+arg_0], rbx
0x140005ce9  mov     [rsp-18h+arg_18], rsi
0x140005cee  push    rbp
0x140005cef  push    rdi
0x140005cf0  push    r14
0x140005cf2  mov     rbp, rsp
0x140005cf5  sub     rsp, 50h
0x140005cf9  mov     rax, cs:__security_cookie
0x140005d00  xor     rax, rsp
0x140005d03  mov     [rbp+var_8], rax
0x140005d07  xor     r14d, r14d
0x140005d0a  mov     rsi, r8
0x140005d0d  mov     [r8], r14d
0x140005d10  mov     rbx, rdx
0x140005d13  mov     eax, dword ptr cs:asc_140008F28; "-/"
0x140005d19  mov     dword ptr [rbp+sz], eax
0x140005d1c  movzx   eax, word ptr cs:asc_140008F28+4; ""
0x140005d23  mov     [rbp+var_C], ax
0x140005d27  test    rdx, rdx
0x140005d2a  jz      short loc_140005D66
0x140005d2c  cmp     [rbx], r14w
0x140005d30  jz      short loc_140005D66
0x140005d32  lea     rax, [rbp+sz]
0x140005d36  movzx   ecx, word ptr [rax]
0x140005d39  test    cx, cx
0x140005d3c  jz      short loc_140005D55
0x140005d3e  cmp     [rbx], cx
0x140005d41  jz      loc_140005DF3
0x140005d47  mov     rcx, rax; lpsz
0x140005d4a  call    cs:__imp_CharNextW
0x140005d50  test    rax, rax
0x140005d53  jnz     short loc_140005D36
0x140005d55  mov     rcx, rbx; lpsz
0x140005d58  call    cs:__imp_CharNextW
0x140005d5e  mov     rbx, rax
0x140005d61  test    rax, rax
0x140005d64  jnz     short loc_140005D2C
0x140005d66  mov     al, 1
0x140005d68  mov     rcx, [rbp+var_8]
0x140005d6c  xor     rcx, rsp; StackCookie
0x140005d6f  call    __security_check_cookie
0x140005d74  lea     r11, [rsp+50h+var_s0]
0x140005d79  mov     rbx, [r11+20h]
0x140005d7d  mov     rsi, [r11+38h]
0x140005d81  mov     rsp, r11
0x140005d84  pop     r14
0x140005d86  pop     rdi
0x140005d87  pop     rbp
0x140005d88  retn
0x140005d89  lea     rdx, aUnregserver; "UnregServer"
0x140005d90  mov     rcx, rbx; lpsz
0x140005d93  call    ?WordCmpI@CAtlModule@ATL@@SAHPEBG0@Z; ATL::CAtlModule::WordCmpI(ushort const *,ushort const *)
0x140005d98  test    eax, eax
0x140005d9a  jz      loc_140005EDA
0x140005da0  lea     rdx, aRegserver; "RegServer"
0x140005da7  mov     rcx, rbx; lpsz
0x140005daa  call    ?WordCmpI@CAtlModule@ATL@@SAHPEBG0@Z; ATL::CAtlModule::WordCmpI(ushort const *,ushort const *)
0x140005daf  test    eax, eax
0x140005db1  jz      short loc_140005E09
0x140005db3  test    rbx, rbx
0x140005db6  jz      short loc_140005D66
0x140005db8  cmp     [rbx], r14w
0x140005dbc  jz      short loc_140005D66
0x140005dbe  lea     rax, [rbp+sz]
0x140005dc2  movzx   ecx, word ptr [rax]
0x140005dc5  test    cx, cx
0x140005dc8  jz      short loc_140005DDD
0x140005dca  cmp     [rbx], cx
0x140005dcd  jz      short loc_140005DF3
0x140005dcf  mov     rcx, rax; lpsz
0x140005dd2  call    cs:__imp_CharNextW
0x140005dd8  test    rax, rax
0x140005ddb  jnz     short loc_140005DC2
0x140005ddd  mov     rcx, rbx; lpsz
0x140005de0  call    cs:__imp_CharNextW
0x140005de6  mov     rbx, rax
0x140005de9  test    rax, rax
0x140005dec  jnz     short loc_140005DB8
0x140005dee  jmp     loc_140005D66
0x140005df3  mov     rcx, rbx; lpsz
0x140005df6  call    cs:__imp_CharNextW
0x140005dfc  mov     rbx, rax
0x140005dff  test    rax, rax
0x140005e02  jnz     short loc_140005D89
0x140005e04  jmp     loc_140005D66
0x140005e09  mov     edx, 65h ; 'e'; unsigned int
0x140005e0e  lea     rax, aAppid; "APPID"
0x140005e15  mov     [rbp+var_30], rax
0x140005e19  lea     r9, [rbp+var_30]; struct ATL::_ATL_REGMAP_ENTRY *
0x140005e1d  lea     rax, aC3a34354660f41; "{C3A34354-660F-41EE-B072-2AEA5E3A80AF}"
0x140005e24  xorps   xmm0, xmm0
0x140005e27  mov     [rbp+var_28], rax
0x140005e2b  lea     r8d, [rdx-64h]; int
0x140005e2f  movdqu  [rbp+var_20], xmm0
0x140005e34  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x140005e39  mov     [rsi], eax
0x140005e3b  test    eax, eax
0x140005e3d  js      loc_140005F2A
0x140005e43  mov     rbx, cs:off_14000B100
0x140005e4a  mov     eax, r14d
0x140005e4d  mov     rcx, cs:off_14000B108
0x140005e54  cmp     rbx, rcx
0x140005e57  jnb     short loc_140005EAD
0x140005e59  mov     rdi, [rbx]
0x140005e5c  test    rdi, rdi
0x140005e5f  jz      short loc_140005EA0
0x140005e61  mov     rax, [rdi+8]
0x140005e65  mov     ecx, 1
0x140005e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e6f  test    eax, eax
0x140005e71  js      loc_140005F28
0x140005e77  mov     rax, [rdi+38h]
0x140005e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e80  mov     rcx, [rdi]; rguid
0x140005e83  mov     r8d, 1; int
0x140005e89  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x140005e8c  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x140005e91  test    eax, eax
0x140005e93  js      loc_140005F28
0x140005e99  mov     rcx, cs:off_14000B108
0x140005ea0  add     rbx, 8
0x140005ea4  cmp     rbx, rcx
0x140005ea7  jb      short loc_140005E59
0x140005ea9  test    eax, eax
0x140005eab  js      short loc_140005F28
0x140005ead  mov     rcx, cs:off_14000B0F8; HINSTANCE
0x140005eb4  call    ?AtlRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBG@Z; ATL::AtlRegisterTypeLib(HINSTANCE__ *,ushort const *)
0x140005eb9  test    eax, eax
0x140005ebb  js      short loc_140005F28
0x140005ebd  mov     rdx, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x140005ec4  test    rdx, rdx
0x140005ec7  jz      short loc_140005F28
0x140005ec9  mov     rcx, cs:hInstance
0x140005ed0  mov     rax, rdx
0x140005ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ed8  jmp     short loc_140005F28
0x140005eda  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x140005ee1  test    rax, rax
0x140005ee4  jz      short loc_140005EEF
0x140005ee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005eeb  test    eax, eax
0x140005eed  js      short loc_140005EF4
0x140005eef  call    ?UnregisterServer@CAtlComModule@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlComModule::UnregisterServer(int,_GUID const *)
0x140005ef4  mov     [rsi], eax
0x140005ef6  test    eax, eax
0x140005ef8  js      short loc_140005F2A
0x140005efa  xor     r8d, r8d; int
0x140005efd  lea     rax, aAppid; "APPID"
0x140005f04  mov     [rbp+var_30], rax
0x140005f08  lea     r9, [rbp+var_30]; struct ATL::_ATL_REGMAP_ENTRY *
0x140005f0c  lea     rax, aC3a34354660f41; "{C3A34354-660F-41EE-B072-2AEA5E3A80AF}"
0x140005f13  xorps   xmm0, xmm0
0x140005f16  mov     [rbp+var_28], rax
0x140005f1a  lea     edx, [r8+65h]; unsigned int
0x140005f1e  movdqu  [rbp+var_20], xmm0
0x140005f23  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x140005f28  mov     [rsi], eax
0x140005f2a  xor     al, al
0x140005f2c  jmp     loc_140005D68
```
