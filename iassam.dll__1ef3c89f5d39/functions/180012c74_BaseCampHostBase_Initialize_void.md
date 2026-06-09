# BaseCampHostBase::Initialize(void)

- ea: `0x180012c74`
- end: `0x18001307b`
- name: `?Initialize@BaseCampHostBase@@UEAAJXZ`
- size: `1031`
- prototype: `__int64 __fastcall(BaseCampHostBase *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800099c0`

## callees

- `0x180001c88`
- `0x18000a760`
- `0x18000aae0`
- `0x18000d49c`
- `0x18000e754`
- `0x180012a38`
- `0x180012c74`
- `0x180013084`
- `0x1800139d0`
- `0x1800141d0`
- `0x1800145dc`
- `0x1800254a0`
- `0x18002b4a0`
- `0x18002e010`

## import_xrefs

- `msvcrt!free` at `0x180012d57`
- `msvcrt!free` at `0x180013053`
- `msvcrt!free` at `0x180012d57`
- `msvcrt!free` at `0x180013053`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012e4f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012e4f`

## string_xrefs

- `0x180012d16`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s`
- `0x180012e00`: `No %S extensions!`
- `0x180012e89`: `Failed to create IAS Extension host for %S: hr = %x`
- `0x180012edd`: `Created IAS Extension host for %S dlls`
- `0x180012f48`: `Failed to initialize Extension host for %S: hr=%x\nReleasing reference to extension host server`
- `0x18001301a`: `Successfully initialized extension host for %S`

## pseudocode

```c
__int64 __fastcall BaseCampHostBase::Initialize(BaseCampHostBase *this)
{
  enum _RADIUS_EXTENSION_POINT v1; // edx
  DWORD v3; // eax
  int v4; // ebx
  unsigned int v5; // eax
  __int64 v6; // rcx
  __int64 v8; // rbx
  const unsigned __int16 *i; // rdi
  bool v10; // al
  __int64 v11; // rcx
  __int64 v12; // rax
  const wchar_t *v13; // rsi
  bool v14; // zf
  int v15; // r9d
  HRESULT Instance; // ebp
  int v17; // r8d
  int v18; // r9d
  int v19; // r9d
  BaseCampHostBase *v20; // rcx
  int v21; // r8d
  int v22; // r9d
  bool v23; // al
  PVOID *v24; // rcx
  const char *v25; // rbx
  int v26; // r9d
  void *Block; // [rsp+30h] [rbp-158h] BYREF
  unsigned int v28; // [rsp+38h] [rbp-150h] BYREF
  char Buffer[256]; // [rsp+40h] [rbp-148h] BYREF

  v1 = *((_DWORD *)this + 21);
  v28 = 0;
  Block = 0;
  v3 = BaseCampHostBase::Load(this, v1, &v28, (unsigned __int8 **)&Block);
  v4 = v3;
  if ( v3 )
  {
    v5 = IASFormatSysErr(v3, Buffer);
    if ( v5 >= 0x100uLL )
      _report_rangecheckfailure(v6);
    Buffer[v5] = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s");
      WPP_SF_sss(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"BaseCampHostBase::Load", (__int64)Buffer);
    }
    if ( Block )
      free(Block);
    if ( v4 > 0 )
      return (unsigned __int16)v4 | 0x80070000;
    return (unsigned int)v4;
  }
  else
  {
    v8 = 0;
    if ( Block )
    {
      for ( i = (const unsigned __int16 *)Block; *i; i += v12 + 1 )
      {
        v10 = IsNT4Only(i);
        v11 = v8 + 1;
        if ( v10 )
          v11 = v8;
        v12 = -1;
        v8 = v11;
        do
          ++v12;
        while ( i[v12] );
      }
    }
    v13 = L"Authentication";
    v14 = *((_DWORD *)this + 21) == 0;
    *((_BYTE *)this + 96) = v8 == 0;
    if ( !v14 )
      v13 = L"Authorization";
    if ( v8 )
    {
      Instance = CoCreateInstance(
                   &GUID_8c334a55_ddb9_491c_817e_35a6b85d2ecb,
                   0,
                   4u,
                   &GUID_7469ae5e_1ca1_4181_970c_bdfd8eaa2c4f,
                   (LPVOID *)this + 11);
      if ( Instance >= 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WppDbgPrint("Created IAS Extension host for %S dlls");
          WPP_SF_sS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            (unsigned int)&WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids,
            v19,
            (__int64)v13);
        }
        Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, void *))(**((_QWORD **)this + 11) + 24LL))(
                     *((_QWORD *)this + 11),
                     *((unsigned int *)this + 21),
                     v28,
                     Block);
        if ( Instance >= 0 )
        {
          v23 = BaseCampHostBase::EnforceNetworkPolicyForPAPChallengeResponseEnabled(v20);
          BaseCampHostBase::isNetworkPolicyEnforcedForPAPChallengeResponse = v23;
          v24 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          {
            if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              v25 = "true";
              WppDbgPrint("Initialized isNetworkPolicyEnforcedForPAPChallengeResponse to %s");
              if ( !BaseCampHostBase::isNetworkPolicyEnforcedForPAPChallengeResponse )
                v25 = "false";
              WPP_SF_ss(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                27,
                (unsigned int)&WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids,
                (unsigned int)"NPSSVC",
                (__int64)v25);
              v24 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v24 != &WPP_GLOBAL_Control && *((_BYTE *)v24 + 25) >= 4u && (*((_BYTE *)v24 + 28) & 4) != 0 )
            {
              WppDbgPrint("Successfully initialized extension host for %S");
              WPP_SF_sS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                28,
                (unsigned int)&WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids,
                v26,
                (__int64)v13);
            }
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WppDbgPrint("Failed to initialize Extension host for %S: hr=%x\n"
                        "Releasing reference to extension host server");
            WPP_SF_sSD(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v21, v22, (__int64)v13, Instance);
          }
          ATL::CComPtrBase<IIASExtensionHost>::Release((char *)this + 88);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("Failed to create IAS Extension host for %S: hr = %x");
        WPP_SF_sSD(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, v17, v18, (__int64)v13, Instance);
      }
      if ( Block )
        free(Block);
      return (unsigned int)Instance;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("No %S extensions!");
        WPP_SF_sS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          (unsigned int)&WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids,
          v15,
          (__int64)v13);
      }
      return 0;
    }
  }
}

```

## disassembly

```asm
0x180012c74  push    rbx
0x180012c76  push    rbp
0x180012c77  push    rsi
0x180012c78  push    rdi
0x180012c79  push    r12
0x180012c7b  push    r15
0x180012c7d  sub     rsp, 158h
0x180012c84  mov     rax, cs:__security_cookie
0x180012c8b  xor     rax, rsp
0x180012c8e  mov     [rsp+188h+var_48], rax
0x180012c96  mov     edx, [rcx+54h]; enum _RADIUS_EXTENSION_POINT
0x180012c99  lea     r9, [rsp+188h+Block]; unsigned __int8 **
0x180012c9e  xor     r12d, r12d
0x180012ca1  lea     r8, [rsp+188h+var_150]; unsigned int *
0x180012ca6  mov     [rsp+188h+var_150], r12d
0x180012cab  mov     r15, rcx
0x180012cae  mov     [rsp+188h+Block], r12
0x180012cb3  call    ?Load@BaseCampHostBase@@IEAAKW4_RADIUS_EXTENSION_POINT@@PEAKPEAPEAE@Z; BaseCampHostBase::Load(_RADIUS_EXTENSION_POINT,ulong *,uchar * *)
0x180012cb8  mov     ebx, eax
0x180012cba  test    eax, eax
0x180012cbc  jz      loc_180012D77
0x180012cc2  lea     rdx, [rsp+188h+Buffer]; Buffer
0x180012cc7  mov     ecx, eax; dwMessageId
0x180012cc9  call    IASFormatSysErr
0x180012cce  mov     eax, eax
0x180012cd0  cmp     rax, 100h
0x180012cd6  jnb     loc_180012D71
0x180012cdc  mov     [rsp+rax+188h+Buffer], r12b
0x180012ce1  mov     rax, cs:WPP_GLOBAL_Control
0x180012ce8  lea     rdi, WPP_GLOBAL_Control
0x180012cef  cmp     rax, rdi
0x180012cf2  jz      short loc_180012D4D
0x180012cf4  cmp     byte ptr [rax+19h], 2
0x180012cf8  jb      short loc_180012D4D
0x180012cfa  test    byte ptr [rax+1Ch], 4
0x180012cfe  jz      short loc_180012D4D
0x180012d00  lea     rdi, aBasecamphostba_0; "BaseCampHostBase::Load"
0x180012d07  mov     r8, rdi
0x180012d0a  lea     r9, [rsp+188h+Buffer]
0x180012d0f  lea     rdx, aNpssvc; "NPSSVC"
0x180012d16  lea     rcx, aCpuPidTidNowSL; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x180012d1d  call    WppDbgPrint
0x180012d22  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d29  lea     rax, [rsp+188h+Buffer]
0x180012d2e  mov     [rsp+188h+var_160], rax; __int64
0x180012d33  lea     edx, [r12+16h]
0x180012d38  lea     r8, WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids
0x180012d3f  mov     [rsp+188h+ppv], rdi; __int64
0x180012d44  mov     rcx, [rcx+10h]; LoggerHandle
0x180012d48  call    WPP_SF_sss
0x180012d4d  mov     rcx, [rsp+188h+Block]; Block
0x180012d52  test    rcx, rcx
0x180012d55  jz      short loc_180012D5D
0x180012d57  call    cs:__imp_free
0x180012d5d  test    ebx, ebx
0x180012d5f  jle     short loc_180012D6A
0x180012d61  movzx   ebx, bx
0x180012d64  or      ebx, 80070000h
0x180012d6a  mov     eax, ebx
0x180012d6c  jmp     loc_18001305B
0x180012d71  call    __report_rangecheckfailure
0x180012d77  mov     rbx, r12
0x180012d7a  cmp     [rsp+188h+Block], r12
0x180012d7f  jz      short loc_180012DB9
0x180012d81  mov     rdi, [rsp+188h+Block]
0x180012d86  jmp     short loc_180012DB3
0x180012d88  mov     rcx, rdi; unsigned __int16 *
0x180012d8b  call    ?IsNT4Only@@YA?B_NPEBG@Z; IsNT4Only(ushort const *)
0x180012d90  test    al, al
0x180012d92  lea     rcx, [rbx+1]
0x180012d96  cmovnz  rcx, rbx
0x180012d9a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012d9e  mov     rbx, rcx
0x180012da1  inc     rax
0x180012da4  cmp     [rdi+rax*2], r12w
0x180012da9  jnz     short loc_180012DA1
0x180012dab  lea     rdi, [rdi+rax*2]
0x180012daf  add     rdi, 2
0x180012db3  cmp     [rdi], r12w
0x180012db7  jnz     short loc_180012D88
0x180012db9  test    rbx, rbx
0x180012dbc  lea     rsi, aAuthentication; "Authentication"
0x180012dc3  setz    al
0x180012dc6  cmp     [r15+54h], r12d
0x180012dca  mov     [r15+60h], al
0x180012dce  lea     rax, aAuthorization; "Authorization"
0x180012dd5  cmovnz  rsi, rax
0x180012dd9  test    rbx, rbx
0x180012ddc  jnz     short loc_180012E32
0x180012dde  mov     rax, cs:WPP_GLOBAL_Control
0x180012de5  lea     rdi, WPP_GLOBAL_Control
0x180012dec  cmp     rax, rdi
0x180012def  jz      short loc_180012E2B
0x180012df1  cmp     byte ptr [rax+19h], 4
0x180012df5  jb      short loc_180012E2B
0x180012df7  test    byte ptr [rax+1Ch], 4
0x180012dfb  jz      short loc_180012E2B
0x180012dfd  mov     rdx, rsi
0x180012e00  lea     rcx, aNoSExtensions; "No %S extensions!"
0x180012e07  call    WppDbgPrint
0x180012e0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e13  lea     edx, [rbx+17h]
0x180012e16  lea     r8, WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids
0x180012e1d  mov     [rsp+188h+ppv], rsi
0x180012e22  mov     rcx, [rcx+10h]
0x180012e26  call    WPP_SF_sS
0x180012e2b  xor     eax, eax
0x180012e2d  jmp     loc_18001305B
0x180012e32  xor     edx, edx; pUnkOuter
0x180012e34  lea     rbx, [r15+58h]
0x180012e38  lea     r9, _GUID_7469ae5e_1ca1_4181_970c_bdfd8eaa2c4f; riid
0x180012e3f  mov     [rsp+188h+ppv], rbx; ppv
0x180012e44  lea     rcx, _GUID_8c334a55_ddb9_491c_817e_35a6b85d2ecb; rclsid
0x180012e4b  lea     r8d, [rdx+4]; dwClsContext
0x180012e4f  call    cs:__imp_CoCreateInstance
0x180012e55  mov     ebp, eax
0x180012e57  test    eax, eax
0x180012e59  jns     short loc_180012EBB
0x180012e5b  mov     rax, cs:WPP_GLOBAL_Control
0x180012e62  lea     rdi, WPP_GLOBAL_Control
0x180012e69  cmp     rax, rdi
0x180012e6c  jz      loc_180013047
0x180012e72  cmp     byte ptr [rax+19h], 4
0x180012e76  jb      loc_180013047
0x180012e7c  test    byte ptr [rax+1Ch], 4
0x180012e80  jz      loc_180013047
0x180012e86  mov     r8d, ebp
0x180012e89  lea     rcx, aFailedToCreate; "Failed to create IAS Extension host for"...
0x180012e90  mov     rdx, rsi
0x180012e93  call    WppDbgPrint
0x180012e98  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e9f  mov     edx, 18h
0x180012ea4  mov     dword ptr [rsp+188h+var_160], ebp
0x180012ea8  mov     [rsp+188h+ppv], rsi
0x180012ead  mov     rcx, [rcx+10h]
0x180012eb1  call    WPP_SF_sSD
0x180012eb6  jmp     loc_180013047
0x180012ebb  mov     rax, cs:WPP_GLOBAL_Control
0x180012ec2  lea     rdi, WPP_GLOBAL_Control
0x180012ec9  cmp     rax, rdi
0x180012ecc  jz      short loc_180012F0A
0x180012ece  cmp     byte ptr [rax+19h], 2
0x180012ed2  jb      short loc_180012F0A
0x180012ed4  test    byte ptr [rax+1Ch], 4
0x180012ed8  jz      short loc_180012F0A
0x180012eda  mov     rdx, rsi
0x180012edd  lea     rcx, aCreatedIasExte; "Created IAS Extension host for %S dlls"
0x180012ee4  call    WppDbgPrint
0x180012ee9  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ef0  lea     r8, WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids
0x180012ef7  mov     edx, 19h
0x180012efc  mov     [rsp+188h+ppv], rsi
0x180012f01  mov     rcx, [rcx+10h]
0x180012f05  call    WPP_SF_sS
0x180012f0a  mov     rcx, [rbx]
0x180012f0d  mov     r9, [rsp+188h+Block]
0x180012f12  mov     r8d, [rsp+188h+var_150]
0x180012f17  mov     edx, [r15+54h]
0x180012f1b  mov     rax, [rcx]
0x180012f1e  mov     rax, [rax+18h]
0x180012f22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f27  mov     ebp, eax
0x180012f29  test    eax, eax
0x180012f2b  jns     short loc_180012F82
0x180012f2d  mov     rax, cs:WPP_GLOBAL_Control
0x180012f34  cmp     rax, rdi
0x180012f37  jz      short loc_180012F75
0x180012f39  cmp     byte ptr [rax+19h], 2
0x180012f3d  jb      short loc_180012F75
0x180012f3f  test    byte ptr [rax+1Ch], 4
0x180012f43  jz      short loc_180012F75
0x180012f45  mov     r8d, ebp
0x180012f48  lea     rcx, aFailedToInitia; "Failed to initialize Extension host for"...
0x180012f4f  mov     rdx, rsi
0x180012f52  call    WppDbgPrint
0x180012f57  mov     rcx, cs:WPP_GLOBAL_Control
0x180012f5e  mov     edx, 1Ah
0x180012f63  mov     dword ptr [rsp+188h+var_160], ebp
0x180012f67  mov     [rsp+188h+ppv], rsi
0x180012f6c  mov     rcx, [rcx+10h]
0x180012f70  call    WPP_SF_sSD
0x180012f75  mov     rcx, rbx
0x180012f78  call    ?Release@?$CComPtrBase@UIIASExtensionHost@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IIASExtensionHost>::Release(void)
0x180012f7d  jmp     loc_180013047
0x180012f82  call    ?EnforceNetworkPolicyForPAPChallengeResponseEnabled@BaseCampHostBase@@IEAA_NXZ; BaseCampHostBase::EnforceNetworkPolicyForPAPChallengeResponseEnabled(void)
0x180012f87  mov     cs:?isNetworkPolicyEnforcedForPAPChallengeResponse@BaseCampHostBase@@1_NA, al; bool BaseCampHostBase::isNetworkPolicyEnforcedForPAPChallengeResponse
0x180012f8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012f94  cmp     rcx, rdi
0x180012f97  jz      loc_180013047
0x180012f9d  cmp     byte ptr [rcx+19h], 4
0x180012fa1  jb      short loc_180013006
0x180012fa3  test    byte ptr [rcx+1Ch], 4
0x180012fa7  jz      short loc_180013006
0x180012fa9  test    al, al
0x180012fab  lea     rbx, aTrue; "true"
0x180012fb2  mov     rdx, rbx
0x180012fb5  lea     r15, aFalse; "false"
0x180012fbc  cmovz   rdx, r15
0x180012fc0  lea     rcx, aInitializedIsn; "Initialized isNetworkPolicyEnforcedForP"...
0x180012fc7  call    WppDbgPrint
0x180012fcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180012fd3  lea     r9, aNpssvc; "NPSSVC"
0x180012fda  cmp     cs:?isNetworkPolicyEnforcedForPAPChallengeResponse@BaseCampHostBase@@1_NA, r12b; bool BaseCampHostBase::isNetworkPolicyEnforcedForPAPChallengeResponse
0x180012fe1  lea     r8, WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids
0x180012fe8  mov     edx, 1Bh
0x180012fed  cmovz   rbx, r15
0x180012ff1  mov     rcx, [rcx+10h]
0x180012ff5  mov     [rsp+188h+ppv], rbx
0x180012ffa  call    WPP_SF_ss
0x180012fff  mov     rcx, cs:WPP_GLOBAL_Control
0x180013006  cmp     rcx, rdi
0x180013009  jz      short loc_180013047
0x18001300b  cmp     byte ptr [rcx+19h], 4
0x18001300f  jb      short loc_180013047
0x180013011  test    byte ptr [rcx+1Ch], 4
0x180013015  jz      short loc_180013047
0x180013017  mov     rdx, rsi
0x18001301a  lea     rcx, aSuccessfullyIn; "Successfully initialized extension host"...
0x180013021  call    WppDbgPrint
0x180013026  mov     rcx, cs:WPP_GLOBAL_Control
0x18001302d  lea     r8, WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids
0x180013034  mov     edx, 1Ch
0x180013039  mov     [rsp+188h+ppv], rsi
0x18001303e  mov     rcx, [rcx+10h]
0x180013042  call    WPP_SF_sS
0x180013047  cmp     [rsp+188h+Block], r12
0x18001304c  jz      short loc_180013059
0x18001304e  mov     rcx, [rsp+188h+Block]; Block
0x180013053  call    cs:__imp_free
0x180013059  mov     eax, ebp
0x18001305b  mov     rcx, [rsp+188h+var_48]
0x180013063  xor     rcx, rsp; StackCookie
0x180013066  call    __security_check_cookie
0x18001306b  add     rsp, 158h
0x180013072  pop     r15
0x180013074  pop     r12
0x180013076  pop     rdi
0x180013077  pop     rsi
0x180013078  pop     rbp
0x180013079  pop     rbx
0x18001307a  retn
```
