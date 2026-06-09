# NgcUtils::GetNgcQueryEnabledResultsWithImpersonation

- ea: `0x1800158c4`
- end: `0x180015be6`
- name: `NgcUtils::GetNgcQueryEnabledResultsWithImpersonation`
- size: `802`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180011520`

## callees

- `0x180003080`
- `0x18000a594`
- `0x18000a5b4`
- `0x18000cfcc`
- `0x180013dc8`
- `0x180013ffc`
- `0x1800158c4`
- `0x180015c4c`
- `0x18001a4d0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015a1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015ac4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015b88`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015a1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015ac4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015b88`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800159f7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800159f7`
- `RPCRT4!RpcImpersonateClient` at `0x18001594a`
- `RPCRT4!RpcImpersonateClient` at `0x18001594a`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800159ba`
- `RPCRT4!RpcRevertToSelfEx` at `0x180015a32`
- `RPCRT4!RpcRevertToSelfEx` at `0x180015b9b`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800159ba`
- `RPCRT4!RpcRevertToSelfEx` at `0x180015a32`
- `RPCRT4!RpcRevertToSelfEx` at `0x180015b9b`
- `dsreg!DsrFreeJoinInfo` at `0x180015925`
- `dsreg!DsrFreeJoinInfo` at `0x1800159da`
- `dsreg!DsrFreeJoinInfo` at `0x180015bbd`
- `dsreg!DsrFreeJoinInfo` at `0x180015925`
- `dsreg!DsrFreeJoinInfo` at `0x1800159da`
- `dsreg!DsrFreeJoinInfo` at `0x180015bbd`
- `dsreg!DsrGetJoinInfo` at `0x1800158f7`
- `dsreg!DsrGetJoinInfo` at `0x1800158f7`
- `cryptngc!NgcQueryEnabled` at `0x180015a93`
- `cryptngc!NgcQueryEnabled` at `0x180015a93`

## string_xrefs

- `0x18001590a`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`
- `0x18001595b`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`
- `0x18001599e`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`
- `0x180015a05`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`
- `0x180015aa6`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 NgcUtils::GetNgcQueryEnabledResultsWithImpersonation()
{
  int JoinInfo; // eax
  unsigned int LastError; // ebx
  __int64 v3; // rcx
  unsigned int v4; // eax
  __int64 v5; // rcx
  int v6; // ebx
  int UserSidFromToken; // eax
  unsigned int v8; // edi
  unsigned int v9; // eax
  void *v10; // rdx
  unsigned int v11; // r8d
  const char *v12; // r9
  unsigned int v13; // eax
  void *v14; // rdx
  unsigned int v15; // r8d
  int v16; // eax
  __int64 v17; // r8
  __int64 *v18; // rcx
  int v19; // eax
  unsigned int v20; // eax
  void *v21; // rdx
  unsigned int v22; // r8d
  unsigned int v23; // [rsp+20h] [rbp-79h]
  unsigned int v24; // [rsp+20h] [rbp-79h]
  void *v25; // [rsp+20h] [rbp-79h]
  __int64 v26; // [rsp+30h] [rbp-69h] BYREF
  int v27; // [rsp+38h] [rbp-61h] BYREF
  int v28; // [rsp+3Ch] [rbp-5Dh] BYREF
  int v29; // [rsp+40h] [rbp-59h] BYREF
  int v30; // [rsp+48h] [rbp-51h] BYREF
  LPWSTR StringSid; // [rsp+50h] [rbp-49h] BYREF
  int v32; // [rsp+58h] [rbp-41h]
  int v33; // [rsp+60h] [rbp-39h] BYREF
  int v34; // [rsp+68h] [rbp-31h] BYREF
  PSID Sid[2]; // [rsp+70h] [rbp-29h] BYREF
  __int64 v36; // [rsp+80h] [rbp-19h]
  unsigned int v37; // [rsp+90h] [rbp-9h] BYREF
  __int64 *v38; // [rsp+A0h] [rbp+7h]
  int v39; // [rsp+A8h] [rbp+Fh]
  int v40; // [rsp+ACh] [rbp+13h]
  int *v41; // [rsp+B0h] [rbp+17h]
  __int64 v42; // [rsp+B8h] [rbp+1Fh]
  int *v43; // [rsp+C0h] [rbp+27h]
  __int64 v44; // [rsp+C8h] [rbp+2Fh]
  int *v45; // [rsp+D0h] [rbp+37h]
  __int64 v46; // [rsp+D8h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v26 = 0;
  JoinInfo = DsrGetJoinInfo(0, &v26);
  LastError = JoinInfo;
  if ( JoinInfo < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\policyutils.cpp",
      (const char *)(unsigned int)JoinInfo,
      v23);
LABEL_3:
    if ( v26 )
      DsrFreeJoinInfo();
    return LastError;
  }
  v3 = v26;
  if ( v26 && *(_DWORD *)v26 )
  {
    v4 = RpcImpersonateClient(0);
    if ( v4 )
    {
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x2D,
                    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\policyutils.cpp",
                    (const char *)v4,
                    v23);
      goto LABEL_3;
    }
    v6 = 1;
    BYTE1(v29) = 1;
    *(_OWORD *)Sid = 0;
    v36 = 0;
    UserSidFromToken = NgcUtils::GetUserSidFromToken(v5, Sid);
    v8 = UserSidFromToken;
    if ( UserSidFromToken < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x34,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\policyutils.cpp",
        (const char *)(unsigned int)UserSidFromToken,
        v23);
LABEL_12:
      std::vector<unsigned char>::~vector<unsigned char>(Sid);
      v9 = RpcRevertToSelfEx(0);
      if ( v9 )
        wil::details::in1diag3::_Log_Win32(retaddr, v10, v11, (const char *)v9, v24);
      if ( v26 )
        DsrFreeJoinInfo();
      return v8;
    }
    StringSid = 0;
    if ( !ConvertSidToStringSidW(Sid[0], &StringSid) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x37,
                    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\policyutils.cpp",
                    v12);
      if ( StringSid )
        LocalFree(StringSid);
      std::vector<unsigned char>::~vector<unsigned char>(Sid);
      v13 = RpcRevertToSelfEx(0);
      if ( v13 )
        wil::details::in1diag3::_Log_Win32(retaddr, v14, v15, (const char *)v13, v23);
      goto LABEL_3;
    }
    v32 = 0;
    v28 = 2;
    v30 = 0;
    v27 = 32;
    v25 = &v27;
    v16 = NgcQueryEnabled(StringSid, *(_QWORD *)(v26 + 32), &v28, &v30);
    v8 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x42,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\policyutils.cpp",
        (const char *)(unsigned int)v16,
        (int)&v27);
      if ( StringSid )
        LocalFree(StringSid);
      goto LABEL_12;
    }
    if ( (v27 & 2) == 0 )
      v6 = ((unsigned __int8)v27 >> 2) & 2;
    if ( (Microsoft_Windows_HelloForBusinessEnableBits & 0x10) != 0 )
    {
      v33 = v30;
      v29 = v28;
      v18 = (__int64 *)Sid[0];
      v34 = v6;
      if ( Sid[0] )
      {
        v19 = 4 * *((unsigned __int8 *)Sid[0] + 1) + 8;
      }
      else
      {
        v18 = &qword_180064FA0;
        v19 = 8;
      }
      v38 = v18;
      v39 = v19;
      v40 = 0;
      v41 = &v29;
      v42 = 4;
      v43 = &v33;
      v44 = 4;
      v45 = &v34;
      v46 = 4;
      v25 = &v37;
      McGenEventWrite_EventWriteTransfer(v18, EVENT_HFB_ENFORCING_ENABLE_POLICIES, v17, 5);
    }
    dword_180076938 = v28;
    if ( StringSid )
      LocalFree(StringSid);
    std::vector<unsigned char>::~vector<unsigned char>(Sid);
    v20 = RpcRevertToSelfEx(0);
    if ( v20 )
      wil::details::in1diag3::_Log_Win32(retaddr, v21, v22, (const char *)v20, (unsigned int)v25);
    v3 = v26;
  }
  if ( v3 )
    DsrFreeJoinInfo();
  return 0;
}

```

## disassembly

```asm
0x1800158c4  mov     [rsp-8+arg_0], rbx
0x1800158c9  mov     [rsp-8+arg_8], rdi
0x1800158ce  push    rbp
0x1800158cf  lea     rbp, [rsp-57h]
0x1800158d4  sub     rsp, 0F0h
0x1800158db  mov     rax, cs:__security_cookie
0x1800158e2  xor     rax, rsp
0x1800158e5  mov     [rbp+57h+var_10], rax
0x1800158e9  mov     [rbp+57h+var_C0], 0
0x1800158f1  lea     rdx, [rbp+57h+var_C0]
0x1800158f5  xor     ecx, ecx
0x1800158f7  call    cs:__imp_DsrGetJoinInfo
0x1800158fd  mov     ebx, eax
0x1800158ff  test    eax, eax
0x180015901  jns     short loc_180015932
0x180015903  mov     rcx, [rbp+5Fh]; this
0x180015907  mov     r9d, eax; char *
0x18001590a  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180015911  mov     edx, 26h ; '&'; void *
0x180015916  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001591b  nop
0x18001591c  mov     rcx, [rbp+57h+var_C0]
0x180015920  test    rcx, rcx
0x180015923  jz      short loc_18001592B
0x180015925  call    cs:__imp_DsrFreeJoinInfo
0x18001592b  mov     eax, ebx
0x18001592d  jmp     loc_180015BC5
0x180015932  mov     rcx, [rbp+57h+var_C0]
0x180015936  test    rcx, rcx
0x180015939  jz      loc_180015BB8
0x18001593f  cmp     dword ptr [rcx], 0
0x180015942  jz      loc_180015BB8
0x180015948  xor     ecx, ecx; BindingHandle
0x18001594a  call    cs:__imp_RpcImpersonateClient
0x180015950  test    eax, eax
0x180015952  jz      short loc_180015970
0x180015954  mov     rcx, [rbp+5Fh]; this
0x180015958  mov     r9d, eax; char *
0x18001595b  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180015962  mov     edx, 2Dh ; '-'; void *
0x180015967  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001596c  mov     ebx, eax
0x18001596e  jmp     short loc_18001591C
0x180015970  mov     ebx, 1
0x180015975  mov     byte ptr [rbp+57h+var_B0+1], bl
0x180015978  xorps   xmm0, xmm0
0x18001597b  movdqu  xmmword ptr [rbp+57h+Sid], xmm0
0x180015980  mov     [rbp+57h+var_70], 0
0x180015988  lea     rdx, [rbp+57h+Sid]
0x18001598c  call    NgcUtils__GetUserSidFromToken
0x180015991  mov     edi, eax
0x180015993  test    eax, eax
0x180015995  jns     short loc_1800159E7
0x180015997  mov     rcx, [rbp+5Fh]; this
0x18001599b  mov     r9d, eax; char *
0x18001599e  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800159a5  lea     edx, [rbx+33h]; void *
0x1800159a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800159ad  nop
0x1800159ae  lea     rcx, [rbp+57h+Sid]
0x1800159b2  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x1800159b7  nop
0x1800159b8  xor     ecx, ecx; BindingHandle
0x1800159ba  call    cs:__imp_RpcRevertToSelfEx
0x1800159c0  test    eax, eax
0x1800159c2  mov     rcx, [rbp+5Fh]; this
0x1800159c6  jz      short loc_1800159D1
0x1800159c8  mov     r9d, eax; char *
0x1800159cb  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800159d0  nop
0x1800159d1  mov     rcx, [rbp+57h+var_C0]
0x1800159d5  test    rcx, rcx
0x1800159d8  jz      short loc_1800159E0
0x1800159da  call    cs:__imp_DsrFreeJoinInfo
0x1800159e0  mov     eax, edi
0x1800159e2  jmp     loc_180015BC5
0x1800159e7  mov     [rbp+57h+StringSid], 0
0x1800159ef  lea     rdx, [rbp+57h+StringSid]; StringSid
0x1800159f3  mov     rcx, [rbp+57h+Sid]; Sid
0x1800159f7  call    cs:__imp_ConvertSidToStringSidW
0x1800159fd  test    eax, eax
0x1800159ff  jnz     short loc_180015A51
0x180015a01  mov     rcx, [rbp+5Fh]; this
0x180015a05  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180015a0c  lea     edx, [rax+37h]; void *
0x180015a0f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180015a14  mov     ebx, eax
0x180015a16  mov     rcx, [rbp+57h+StringSid]; hMem
0x180015a1a  test    rcx, rcx
0x180015a1d  jz      short loc_180015A26
0x180015a1f  call    cs:__imp_LocalFree
0x180015a25  nop
0x180015a26  lea     rcx, [rbp+57h+Sid]
0x180015a2a  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180015a2f  nop
0x180015a30  xor     ecx, ecx; BindingHandle
0x180015a32  call    cs:__imp_RpcRevertToSelfEx
0x180015a38  mov     rcx, [rbp+5Fh]; this
0x180015a3c  test    eax, eax
0x180015a3e  jz      loc_18001591C
0x180015a44  mov     r9d, eax; char *
0x180015a47  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180015a4c  jmp     loc_18001591C
0x180015a51  mov     [rbp+57h+var_98], 0
0x180015a58  mov     [rbp+57h+var_B4], 2
0x180015a5f  mov     [rbp+57h+var_A8], 0
0x180015a66  mov     [rbp+57h+var_B8], 20h ; ' '
0x180015a6d  lea     rax, [rbp+57h+var_98]
0x180015a71  mov     [rsp+0F0h+var_C8], rax
0x180015a76  lea     rax, [rbp+57h+var_B8]
0x180015a7a  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x180015a7f  lea     r9, [rbp+57h+var_A8]
0x180015a83  lea     r8, [rbp+57h+var_B4]
0x180015a87  mov     rdx, [rbp+57h+var_C0]
0x180015a8b  mov     rdx, [rdx+20h]
0x180015a8f  mov     rcx, [rbp+57h+StringSid]
0x180015a93  call    cs:__imp_NgcQueryEnabled
0x180015a99  mov     edi, eax
0x180015a9b  test    eax, eax
0x180015a9d  jns     short loc_180015ACF
0x180015a9f  mov     rcx, [rbp+5Fh]; this
0x180015aa3  mov     r9d, eax; char *
0x180015aa6  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180015aad  mov     edx, 42h ; 'B'; void *
0x180015ab2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015ab7  mov     rcx, [rbp+57h+StringSid]; hMem
0x180015abb  test    rcx, rcx
0x180015abe  jz      loc_1800159AE
0x180015ac4  call    cs:__imp_LocalFree
0x180015aca  jmp     loc_1800159AE
0x180015acf  test    byte ptr [rbp+57h+var_B8], 2
0x180015ad3  jnz     short loc_180015ADF
0x180015ad5  movzx   ebx, byte ptr [rbp+57h+var_B8]
0x180015ad9  shr     ebx, 2
0x180015adc  and     ebx, 2
0x180015adf  test    cs:Microsoft_Windows_HelloForBusinessEnableBits, 10h
0x180015ae6  jz      loc_180015B76
0x180015aec  mov     eax, [rbp+57h+var_A8]
0x180015aef  mov     [rbp+57h+var_90], eax
0x180015af2  mov     eax, [rbp+57h+var_B4]
0x180015af5  mov     [rbp+57h+var_B0], eax
0x180015af8  mov     rcx, [rbp+57h+Sid]
0x180015afc  mov     [rbp+57h+var_88], ebx
0x180015aff  test    rcx, rcx
0x180015b02  jz      short loc_180015B11
0x180015b04  movzx   eax, byte ptr [rcx+1]
0x180015b08  lea     eax, ds:8[rax*4]
0x180015b0f  jmp     short loc_180015B1D
0x180015b11  lea     rcx, qword_180064FA0
0x180015b18  mov     eax, 8
0x180015b1d  mov     [rbp+57h+var_50], rcx
0x180015b21  mov     [rbp+57h+var_48], eax
0x180015b24  mov     [rbp+57h+var_44], 0
0x180015b2b  lea     rax, [rbp+57h+var_B0]
0x180015b2f  mov     [rbp+57h+var_40], rax
0x180015b33  mov     [rbp+57h+var_38], 4
0x180015b3b  lea     rax, [rbp+57h+var_90]
0x180015b3f  mov     [rbp+57h+var_30], rax
0x180015b43  mov     [rbp+57h+var_28], 4
0x180015b4b  lea     rax, [rbp+57h+var_88]
0x180015b4f  mov     [rbp+57h+var_20], rax
0x180015b53  mov     [rbp+57h+var_18], 4
0x180015b5b  lea     rax, [rbp+57h+var_60]
0x180015b5f  mov     qword ptr [rsp+0F0h+var_D0], rax; unsigned int
0x180015b64  mov     r9d, 5
0x180015b6a  lea     rdx, EVENT_HFB_ENFORCING_ENABLE_POLICIES
0x180015b71  call    McGenEventWrite_EventWriteTransfer
0x180015b76  mov     eax, [rbp+57h+var_B4]
0x180015b79  mov     cs:dword_180076938, eax
0x180015b7f  mov     rcx, [rbp+57h+StringSid]; hMem
0x180015b83  test    rcx, rcx
0x180015b86  jz      short loc_180015B8F
0x180015b88  call    cs:__imp_LocalFree
0x180015b8e  nop
0x180015b8f  lea     rcx, [rbp+57h+Sid]
0x180015b93  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180015b98  nop
0x180015b99  xor     ecx, ecx; BindingHandle
0x180015b9b  call    cs:__imp_RpcRevertToSelfEx
0x180015ba1  mov     rcx, [rbp+5Fh]; this
0x180015ba5  test    eax, eax
0x180015ba7  jz      short loc_180015BB2
0x180015ba9  mov     r9d, eax; char *
0x180015bac  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180015bb1  nop
0x180015bb2  mov     rcx, [rbp+57h+var_C0]
0x180015bb6  jmp     short $+2
0x180015bb8  test    rcx, rcx
0x180015bbb  jz      short loc_180015BC3
0x180015bbd  call    cs:__imp_DsrFreeJoinInfo
0x180015bc3  xor     eax, eax
0x180015bc5  mov     rcx, [rbp+57h+var_10]
0x180015bc9  xor     rcx, rsp; StackCookie
0x180015bcc  call    __security_check_cookie
0x180015bd1  lea     r11, [rsp+0F0h+var_s0]
0x180015bd9  mov     rbx, [r11+10h]
0x180015bdd  mov     rdi, [r11+18h]
0x180015be1  mov     rsp, r11
0x180015be4  pop     rbp
0x180015be5  retn
```
