# DenyAccessIfRemoteUserWithInsufficientPermissions(void)

- ea: `0x180009e70`
- end: `0x18000a0c0`
- name: `?DenyAccessIfRemoteUserWithInsufficientPermissions@@YAJXZ`
- size: `592`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a680`

## callees

- `0x180008b70`
- `0x180009e70`
- `0x18000dcb0`
- `0x18009d024`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009eb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ebc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ec4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009fe4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009fee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ff6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009eb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ebc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ec4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009fe4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009fee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ff6`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180009ea8`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180009f43`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180009fda`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180009ea8`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180009f43`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180009fda`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 DenyAccessIfRemoteUserWithInsufficientPermissions(void)
{
  unsigned int LastError; // eax
  unsigned int v1; // eax
  unsigned int v2; // eax
  __int64 result; // rax
  const ComError *v4; // rbx
  const ComError *v5; // [rsp+30h] [rbp-168h] BYREF
  _BYTE v6[16]; // [rsp+38h] [rbp-160h] BYREF
  HANDLE *v7; // [rsp+48h] [rbp-150h]
  void **pExceptionObject; // [rsp+70h] [rbp-128h] BYREF
  __int128 v9; // [rsp+78h] [rbp-120h]
  unsigned int v10; // [rsp+88h] [rbp-110h]
  int v11; // [rsp+8Ch] [rbp-10Ch]
  int v12; // [rsp+90h] [rbp-108h]
  void **v13; // [rsp+D0h] [rbp-C8h] BYREF
  __int128 v14; // [rsp+D8h] [rbp-C0h]
  unsigned int v15; // [rsp+E8h] [rbp-B0h]
  int v16; // [rsp+ECh] [rbp-ACh]
  int v17; // [rsp+F0h] [rbp-A8h]
  void **v18; // [rsp+130h] [rbp-68h] BYREF
  __int128 v19; // [rsp+138h] [rbp-60h]
  unsigned int v20; // [rsp+148h] [rbp-50h]
  int v21; // [rsp+14Ch] [rbp-4Ch]
  int v22; // [rsp+150h] [rbp-48h]
  WINBOOL IsMember; // [rsp+1A0h] [rbp+8h] BYREF
  WINBOOL v24; // [rsp+1A8h] [rbp+10h] BYREF
  WINBOOL v25; // [rsp+1B0h] [rbp+18h] BYREF

  try
  {
    CNestedImpersonation::CNestedImpersonation((CNestedImpersonation *)v6);
    IsMember = 0;
    if ( !CheckTokenMembership(*v7, *((PSID *)g_GlobalInfo + 13), &IsMember) )
    {
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0x80070000;
      else
        LastError = GetLastError();
      v9 = 0;
      pExceptionObject = &ComError::`vftable';
      v10 = LastError;
      v11 = 1135;
      v12 = 1;
      throw (ComError *)&pExceptionObject;
    }
    if ( !IsMember )
      goto LABEL_24;
    v24 = 0;
    if ( !CheckTokenMembership(*v7, *((PSID *)g_GlobalInfo + 7), &v24) )
    {
      if ( (int)GetLastError() > 0 )
        v1 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v1 = GetLastError();
      v14 = 0;
      v13 = &ComError::`vftable';
      v15 = v1;
      v16 = 1146;
      v17 = 1;
      throw (ComError *)&v13;
    }
    v25 = 0;
    if ( !CheckTokenMembership(*v7, *((PSID *)g_GlobalInfo + 9), &v25) )
    {
      if ( (int)GetLastError() > 0 )
        v2 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v2 = GetLastError();
      v19 = 0;
      v18 = &ComError::`vftable';
      v20 = v2;
      v21 = 1155;
      v22 = 1;
      throw (ComError *)&v18;
    }
    if ( v24 || v25 )
    {
LABEL_24:
      CNestedImpersonation::~CNestedImpersonation((CNestedImpersonation *)v6);
      result = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids);
      CNestedImpersonation::~CNestedImpersonation((CNestedImpersonation *)v6);
      result = 2149580820LL;
    }
  }
  catch ( const ComError *v5 )
  {
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      v4 = v5;
    }
    else
    {
      v4 = v5;
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        &WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids,
        *((unsigned int *)v4 + 6),
        *((_DWORD *)v4 + 7));
    }
    return (unsigned int)*((_DWORD *)v4 + 6);
  }
  return result;
}

```

## disassembly

```asm
0x180009e70  push    rbx
0x180009e72  sub     rsp, 190h
0x180009e79  lea     rcx, [rsp+198h+var_160]; this
0x180009e7e  call    ??0CNestedImpersonation@@QEAA@XZ; CNestedImpersonation::CNestedImpersonation(void)
0x180009e83  nop
0x180009e84  xor     ebx, ebx
0x180009e86  mov     [rsp+198h+IsMember], ebx
0x180009e8d  lea     r8, [rsp+198h+IsMember]; IsMember
0x180009e95  mov     rdx, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x180009e9c  mov     rdx, [rdx+68h]; SidToCheck
0x180009ea0  mov     rcx, [rsp+198h+var_150]
0x180009ea5  mov     rcx, [rcx]; TokenHandle
0x180009ea8  call    cs:__imp_CheckTokenMembership
0x180009eae  test    eax, eax
0x180009eb0  jnz     short loc_180009F14
0x180009eb2  call    cs:__imp_GetLastError
0x180009eb8  test    eax, eax
0x180009eba  jg      short loc_180009EC4
0x180009ebc  call    cs:__imp_GetLastError
0x180009ec2  jmp     short loc_180009ED2
0x180009ec4  call    cs:__imp_GetLastError
0x180009eca  movzx   eax, ax
0x180009ecd  or      eax, 80070000h
0x180009ed2  xorps   xmm0, xmm0
0x180009ed5  movups  [rsp+198h+var_120], xmm0
0x180009eda  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180009ee1  mov     [rsp+198h+pExceptionObject], rcx
0x180009ee6  mov     [rsp+198h+var_110], eax
0x180009eed  mov     [rsp+198h+var_10C], 46Fh
0x180009ef8  mov     [rsp+198h+var_108], 1
0x180009f03  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180009f0a  lea     rcx, [rsp+198h+pExceptionObject]; pExceptionObject
0x180009f0f  call    _CxxThrowException_0
0x180009f14  cmp     [rsp+198h+IsMember], ebx
0x180009f1b  jz      loc_18000A0A1
0x180009f21  mov     [rsp+198h+arg_8], ebx
0x180009f28  lea     r8, [rsp+198h+arg_8]; IsMember
0x180009f30  mov     rdx, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x180009f37  mov     rdx, [rdx+38h]; SidToCheck
0x180009f3b  mov     rcx, [rsp+198h+var_150]
0x180009f40  mov     rcx, [rcx]; TokenHandle
0x180009f43  call    cs:__imp_CheckTokenMembership
0x180009f49  test    eax, eax
0x180009f4b  jnz     short loc_180009FB8
0x180009f4d  call    cs:__imp_GetLastError
0x180009f53  test    eax, eax
0x180009f55  jg      short loc_180009F5F
0x180009f57  call    cs:__imp_GetLastError
0x180009f5d  jmp     short loc_180009F6D
0x180009f5f  call    cs:__imp_GetLastError
0x180009f65  movzx   eax, ax
0x180009f68  or      eax, 80070000h
0x180009f6d  xorps   xmm0, xmm0
0x180009f70  movups  [rsp+198h+var_C0], xmm0
0x180009f78  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180009f7f  mov     [rsp+198h+var_C8], rcx
0x180009f87  mov     [rsp+198h+var_B0], eax
0x180009f8e  mov     [rsp+198h+var_AC], 47Ah
0x180009f99  mov     [rsp+198h+var_A8], 1
0x180009fa4  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180009fab  lea     rcx, [rsp+198h+var_C8]; pExceptionObject
0x180009fb3  call    _CxxThrowException_0
0x180009fb8  mov     [rsp+198h+arg_10], ebx
0x180009fbf  lea     r8, [rsp+198h+arg_10]; IsMember
0x180009fc7  mov     rdx, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x180009fce  mov     rdx, [rdx+48h]; SidToCheck
0x180009fd2  mov     rcx, [rsp+198h+var_150]
0x180009fd7  mov     rcx, [rcx]; TokenHandle
0x180009fda  call    cs:__imp_CheckTokenMembership
0x180009fe0  test    eax, eax
0x180009fe2  jnz     short loc_18000A04F
0x180009fe4  call    cs:__imp_GetLastError
0x180009fea  test    eax, eax
0x180009fec  jg      short loc_180009FF6
0x180009fee  call    cs:__imp_GetLastError
0x180009ff4  jmp     short loc_18000A004
0x180009ff6  call    cs:__imp_GetLastError
0x180009ffc  movzx   eax, ax
0x180009fff  or      eax, 80070000h
0x18000a004  xorps   xmm0, xmm0
0x18000a007  movups  [rsp+198h+var_60], xmm0
0x18000a00f  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18000a016  mov     [rsp+198h+var_68], rcx
0x18000a01e  mov     [rsp+198h+var_50], eax
0x18000a025  mov     [rsp+198h+var_4C], 483h
0x18000a030  mov     [rsp+198h+var_48], 1
0x18000a03b  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18000a042  lea     rcx, [rsp+198h+var_68]; pExceptionObject
0x18000a04a  call    _CxxThrowException_0
0x18000a04f  cmp     [rsp+198h+arg_8], ebx
0x18000a056  jnz     short loc_18000A0A1
0x18000a058  cmp     [rsp+198h+arg_10], ebx
0x18000a05f  jnz     short loc_18000A0A1
0x18000a061  lea     rax, WPP_GLOBAL_Control
0x18000a068  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a06f  cmp     rcx, rax
0x18000a072  jz      short loc_18000A090
0x18000a074  test    byte ptr [rcx+1Ch], 4
0x18000a078  jz      short loc_18000A090
0x18000a07a  mov     edx, 27h ; '''
0x18000a07f  lea     r8, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids
0x18000a086  mov     rcx, [rcx+10h]
0x18000a08a  call    WPP_SF_
0x18000a08f  nop
0x18000a090  lea     rcx, [rsp+198h+var_160]; this
0x18000a095  call    ??1CNestedImpersonation@@QEAA@XZ; CNestedImpersonation::~CNestedImpersonation(void)
0x18000a09a  mov     eax, 80200014h
0x18000a09f  jmp     short loc_18000A0B6
0x18000a0a1  lea     rcx, [rsp+198h+var_160]; this
0x18000a0a6  call    ??1CNestedImpersonation@@QEAA@XZ; CNestedImpersonation::~CNestedImpersonation(void)
0x18000a0ab  xor     eax, eax
0x18000a0ad  jmp     short loc_18000A0B6
0x18000a0af  mov     eax, [rsp+198h+IsMember]
0x18000a0b6  add     rsp, 190h
0x18000a0bd  pop     rbx
0x18000a0be  retn
```
