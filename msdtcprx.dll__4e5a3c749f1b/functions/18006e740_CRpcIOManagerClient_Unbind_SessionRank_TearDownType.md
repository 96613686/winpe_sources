# CRpcIOManagerClient::Unbind(_SessionRank,_TearDownType)

- ea: `0x18006e740`
- end: `0x18006ed6f`
- name: `?Unbind@CRpcIOManagerClient@@UEAAJW4_SessionRank@@W4_TearDownType@@@Z`
- size: `1583`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180003cf0`
- `0x1800064d0`
- `0x180006cf8`
- `0x180012130`
- `0x180054968`
- `0x180058be4`
- `0x18006e740`
- `0x18006f1ec`
- `0x18006f3dc`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x180083758`
- `RPCRT4!RpcExceptionFilter` at `0x180083774`
- `RPCRT4!RpcExceptionFilter` at `0x180083790`
- `RPCRT4!RpcExceptionFilter` at `0x1800837ac`
- `RPCRT4!RpcExceptionFilter` at `0x1800837c8`
- `RPCRT4!RpcExceptionFilter` at `0x1800837e4`
- `RPCRT4!RpcExceptionFilter` at `0x180083800`
- `RPCRT4!RpcExceptionFilter` at `0x18008381c`
- `RPCRT4!RpcExceptionFilter` at `0x180083838`
- `RPCRT4!RpcExceptionFilter` at `0x180083758`
- `RPCRT4!RpcExceptionFilter` at `0x180083774`
- `RPCRT4!RpcExceptionFilter` at `0x180083790`
- `RPCRT4!RpcExceptionFilter` at `0x1800837ac`
- `RPCRT4!RpcExceptionFilter` at `0x1800837c8`
- `RPCRT4!RpcExceptionFilter` at `0x1800837e4`
- `RPCRT4!RpcExceptionFilter` at `0x180083800`
- `RPCRT4!RpcExceptionFilter` at `0x18008381c`
- `RPCRT4!RpcExceptionFilter` at `0x180083838`
- `RPCRT4!RpcSsDestroyClientContext` at `0x18006e8c3`
- `RPCRT4!RpcSsDestroyClientContext` at `0x18006eaad`
- `RPCRT4!RpcSsDestroyClientContext` at `0x18006ebd6`
- `RPCRT4!RpcSsDestroyClientContext` at `0x18006ecea`
- `RPCRT4!RpcSsDestroyClientContext` at `0x18006e8c3`
- `RPCRT4!RpcSsDestroyClientContext` at `0x18006eaad`
- `RPCRT4!RpcSsDestroyClientContext` at `0x18006ebd6`
- `RPCRT4!RpcSsDestroyClientContext` at `0x18006ecea`

## string_xrefs

- `0x18006e808`: `com\complus\dtc\dtc\cm\src\iomgrclt.cpp`
- `0x18006e843`: `com\complus\dtc\dtc\cm\src\iomgrclt.cpp`
- `0x18006e898`: `com\complus\dtc\dtc\cm\src\iomgrclt.cpp`
- `0x18006e8f2`: `com\complus\dtc\dtc\cm\src\iomgrclt.cpp`
- `0x18006e9ac`: `com\complus\dtc\dtc\cm\src\iomgrclt.cpp`
- `0x18006ea2d`: `com\complus\dtc\dtc\cm\src\iomgrclt.cpp`
- `0x18006ea82`: `com\complus\dtc\dtc\cm\src\iomgrclt.cpp`
- `0x18006eadc`: `com\complus\dtc\dtc\cm\src\iomgrclt.cpp`
- `0x18006eb56`: `com\complus\dtc\dtc\cm\src\iomgrclt.cpp`
- `0x18006ebab`: `com\complus\dtc\dtc\cm\src\iomgrclt.cpp`
- `0x18006ec05`: `com\complus\dtc\dtc\cm\src\iomgrclt.cpp`
- `0x18006ec6a`: `com\complus\dtc\dtc\cm\src\iomgrclt.cpp`
- `0x18006ecbf`: `com\complus\dtc\dtc\cm\src\iomgrclt.cpp`
- `0x18006ed19`: `com\complus\dtc\dtc\cm\src\iomgrclt.cpp`

## pseudocode

```c
__int64 __fastcall CRpcIOManagerClient::Unbind(__int64 a1, unsigned int a2, int a3)
{
  CSessionObject **v6; // rdi
  int v7; // r12d
  unsigned int i; // r12d
  int v9; // ecx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  __int64 v14; // [rsp+28h] [rbp-50h]

  if ( !g_fShutDownAll )
  {
    v6 = (CSessionObject **)(a1 + 8);
    CSessionObject::SetRpcTimer(*(CSessionObject **)(a1 + 8));
    if ( a3 )
    {
      if ( a3 == 2 )
      {
        v7 = 0;
        StringCbCopyA((char *)*v6 + 48, 0x25u, "00000000-0000-0000-0000-000000000000");
        *(_DWORD *)(a1 + 40) = 0;
        *(_DWORD *)(a1 + 48) = 0;
        if ( *(_QWORD *)(a1 + 32) )
          v7 = C_TearDownContext(a1 + 32, a2);
        else
          TraceStringInline(
            1,
            240,
            L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrclt.cpp",
            1613,
            L"CRpcIOManagerClient::Unbind",
            0,
            L"m_phContext was null, therefore did not call TearDown");
        if ( v7 )
        {
          LODWORD(v14) = v7;
          TraceStringInline(
            1,
            1,
            L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrclt.cpp",
            1619,
            L"CRpcIOManagerClient::Unbind",
            v14,
            L"Failure return from C_TearDownConext");
        }
      }
      goto LABEL_30;
    }
    *(_DWORD *)(a1 + 40) = 0;
    *(_DWORD *)(a1 + 48) = 0;
    if ( a2 == 1 )
    {
      v12 = C_TearDownContext(a1 + 32, 1);
      if ( v12 )
      {
        LODWORD(v14) = v12;
        TraceStringInline(
          1,
          1,
          L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrclt.cpp",
          1669,
          L"CRpcIOManagerClient::Unbind",
          v14,
          L"Failure return from C_TearDownContext");
      }
    }
    else
    {
      if ( a2 != 2 )
        goto LABEL_30;
      if ( *((_DWORD *)*v6 + 6) != 1 )
      {
        for ( i = 0; i < 0xA && *((_DWORD *)*v6 + 6) != 1 && !(unsigned int)C_BeginTearDown(*(_QWORD *)(a1 + 32), 0); ++i )
          ;
      }
      v9 = *((_DWORD *)*v6 + 6);
      if ( !v9 )
      {
        StringCbCopyA((char *)*v6 + 48, 0x25u, "00000000-0000-0000-0000-000000000000");
        v11 = C_TearDownContext(a1 + 32, a2);
        if ( v11 )
        {
          LODWORD(v14) = v11;
          TraceStringInline(
            1,
            1,
            L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrclt.cpp",
            1807,
            L"CRpcIOManagerClient::Unbind",
            v14,
            L"Failure return from C_TearDownContext");
        }
        *((_DWORD *)*v6 + 6) = 0;
        goto LABEL_30;
      }
      if ( v9 != 1 )
      {
LABEL_30:
        CSessionObject::ResetRpcTimer(*v6);
        return 0;
      }
      v10 = C_TearDownContext(a1 + 32, a2);
      if ( v10 )
      {
        LODWORD(v14) = v10;
        TraceStringInline(
          1,
          1,
          L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrclt.cpp",
          1755,
          L"CRpcIOManagerClient::Unbind",
          v14,
          L"Failure return from C_TearDownContext");
      }
      *((_DWORD *)*v6 + 6) = 0;
    }
    StringCbCopyA((char *)*v6 + 48, 0x25u, "00000000-0000-0000-0000-000000000000");
    goto LABEL_30;
  }
  *(_DWORD *)(a1 + 40) = 0;
  *(_DWORD *)(a1 + 48) = 0;
  return 0;
}

```

## disassembly

```asm
0x18006e740  mov     [rsp+arg_10], rbx
0x18006e745  mov     [rsp+arg_8], edx
0x18006e749  mov     [rsp+arg_0], rcx
0x18006e74e  push    rsi
0x18006e74f  push    rdi
0x18006e750  push    r12
0x18006e752  push    r14
0x18006e754  push    r15
0x18006e756  sub     rsp, 50h
0x18006e75a  mov     r14d, r8d
0x18006e75d  mov     r15d, edx
0x18006e760  mov     rsi, rcx
0x18006e763  xor     ebx, ebx
0x18006e765  cmp     cs:?g_fShutDownAll@@3HA, ebx; int g_fShutDownAll
0x18006e76b  jz      short loc_18006E778
0x18006e76d  mov     [rcx+28h], ebx
0x18006e770  mov     [rcx+30h], ebx
0x18006e773  jmp     loc_18006ED58
0x18006e778  lea     rdi, [rcx+8]
0x18006e77c  mov     [rsp+78h+arg_18], rdi
0x18006e784  mov     rcx, [rdi]; this
0x18006e787  call    ?SetRpcTimer@CSessionObject@@AEAAXXZ; CSessionObject::SetRpcTimer(void)
0x18006e78c  test    r14d, r14d
0x18006e78f  jz      loc_18006E916
0x18006e795  cmp     r14d, 2
0x18006e799  jnz     loc_18006ED50
0x18006e79f  mov     r12d, ebx
0x18006e7a2  mov     rcx, [rdi]
0x18006e7a5  add     rcx, 30h ; '0'; char *
0x18006e7a9  lea     r8, a00000000000000; "00000000-0000-0000-0000-000000000000"
0x18006e7b0  lea     edx, [r14+23h]; unsigned __int64
0x18006e7b4  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x18006e7b9  mov     [rsi+28h], ebx
0x18006e7bc  mov     [rsi+30h], ebx
0x18006e7bf  lea     rcx, [rsi+20h]
0x18006e7c3  cmp     [rcx], rbx
0x18006e7c6  jz      short loc_18006E7E5
0x18006e7c8  mov     r8d, r14d
0x18006e7cb  mov     edx, r15d
0x18006e7ce  call    C_TearDownContext
0x18006e7d3  mov     r12d, eax
0x18006e7d6  lea     rsi, aCrpciomanagerc_10; "CRpcIOManagerClient::Unbind"
0x18006e7dd  mov     r14d, 1
0x18006e7e3  jmp     short loc_18006E822
0x18006e7e5  lea     rax, aMPhcontextWasN_0; "m_phContext was null, therefore did not"...
0x18006e7ec  mov     [rsp+78h+var_48], rax
0x18006e7f1  mov     [rsp+78h+var_50], rbx
0x18006e7f6  lea     rsi, aCrpciomanagerc_10; "CRpcIOManagerClient::Unbind"
0x18006e7fd  mov     [rsp+78h+var_58], rsi
0x18006e802  mov     r9d, 64Dh
0x18006e808  lea     r8, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrc"...
0x18006e80f  mov     edx, 0F0h
0x18006e814  mov     r14d, 1
0x18006e81a  mov     ecx, r14d
0x18006e81d  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18006e822  test    r12d, r12d
0x18006e825  jz      short loc_18006E855
0x18006e827  lea     rax, aFailureReturnF; "Failure return from C_TearDownConext"
0x18006e82e  mov     [rsp+78h+var_48], rax
0x18006e833  mov     dword ptr [rsp+78h+var_50], r12d
0x18006e838  mov     [rsp+78h+var_58], rsi
0x18006e83d  mov     r9d, 653h
0x18006e843  lea     r8, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrc"...
0x18006e84a  mov     edx, r14d
0x18006e84d  mov     ecx, r14d
0x18006e850  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18006e855  jmp     loc_18006ED50
0x18006e85a  mov     ebx, eax
0x18006e85c  mov     rdi, [rsp+78h+arg_0]
0x18006e864  mov     rcx, [rdi+18h]
0x18006e868  mov     [rsp+78h+var_38], rcx
0x18006e86d  mov     rcx, [rdi+10h]
0x18006e871  mov     [rsp+78h+var_40], rcx
0x18006e876  lea     rax, aRemoteS8sExcep_6; "[Remote:%s %.8s] Exception raised in th"...
0x18006e87d  mov     [rsp+78h+var_48], rax
0x18006e882  mov     dword ptr [rsp+78h+var_50], ebx
0x18006e886  lea     rax, aCrpciomanagerc_10; "CRpcIOManagerClient::Unbind"
0x18006e88d  mov     [rsp+78h+var_58], rax
0x18006e892  mov     r9d, 65Ch
0x18006e898  lea     r8, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrc"...
0x18006e89f  mov     edx, 1
0x18006e8a4  mov     ecx, edx
0x18006e8a6  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18006e8ab  call    ?TraceRpcEEInfo@@YAXXZ; TraceRpcEEInfo(void)
0x18006e8b0  mov     ecx, ebx; int
0x18006e8b2  call    ?RpcStatusToHresult@@YAJJ@Z; RpcStatusToHresult(long)
0x18006e8b7  nop
0x18006e8b8  cmp     qword ptr [rdi+20h], 0
0x18006e8bd  jz      short loc_18006E8C9
0x18006e8bf  lea     rcx, [rdi+20h]; ContextHandle
0x18006e8c3  call    cs:__imp_RpcSsDestroyClientContext
0x18006e8c9  jmp     short loc_18006E909
0x18006e8cb  lea     rax, aExceptionWhile; "EXCEPTION : While destroying the Contex"...
0x18006e8d2  mov     [rsp+78h+var_48], rax
0x18006e8d7  mov     [rsp+78h+var_50], 0
0x18006e8e0  lea     rax, aCrpciomanagerc_10; "CRpcIOManagerClient::Unbind"
0x18006e8e7  mov     [rsp+78h+var_58], rax
0x18006e8ec  mov     r9d, 66Bh
0x18006e8f2  lea     r8, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrc"...
0x18006e8f9  mov     edx, 0F0h
0x18006e8fe  mov     ecx, 1
0x18006e903  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18006e908  nop
0x18006e909  mov     rdi, [rsp+78h+arg_18]
0x18006e911  jmp     loc_18006ED50
0x18006e916  mov     [rsi+28h], ebx
0x18006e919  mov     [rsi+30h], ebx
0x18006e91c  mov     ecx, r15d
0x18006e91f  sub     ecx, 1
0x18006e922  jz      loc_18006EC31
0x18006e928  cmp     ecx, 1
0x18006e92b  jnz     loc_18006ED50
0x18006e931  mov     rax, [rdi]
0x18006e934  mov     r14d, ecx
0x18006e937  cmp     [rax+18h], ecx
0x18006e93a  jz      loc_18006E9E1
0x18006e940  mov     r12d, ebx
0x18006e943  cmp     r12d, 0Ah
0x18006e947  jnb     loc_18006E9E1
0x18006e94d  mov     rax, [rdi]
0x18006e950  cmp     [rax+18h], r14d
0x18006e954  jz      loc_18006E9E1
0x18006e95a  xor     edx, edx
0x18006e95c  mov     rcx, [rsi+20h]
0x18006e960  call    C_BeginTearDown
0x18006e965  test    eax, eax
0x18006e967  jnz     short loc_18006E9E1
0x18006e969  add     r12d, r14d
0x18006e96c  jmp     short loc_18006E943
0x18006e96e  mov     ebx, eax
0x18006e970  mov     rsi, [rsp+78h+arg_0]
0x18006e978  mov     rcx, [rsi+18h]
0x18006e97c  mov     [rsp+78h+var_38], rcx
0x18006e981  mov     rcx, [rsi+10h]
0x18006e985  mov     [rsp+78h+var_40], rcx
0x18006e98a  lea     rax, aRemoteS8sExcep_5; "[Remote:%s %.8s] Exception raised in th"...
0x18006e991  mov     [rsp+78h+var_48], rax
0x18006e996  mov     dword ptr [rsp+78h+var_50], ebx
0x18006e99a  lea     rax, aCrpciomanagerc_10; "CRpcIOManagerClient::Unbind"
0x18006e9a1  mov     [rsp+78h+var_58], rax
0x18006e9a6  mov     r9d, 6C3h
0x18006e9ac  lea     r8, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrc"...
0x18006e9b3  mov     edx, 1
0x18006e9b8  mov     ecx, edx
0x18006e9ba  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18006e9bf  call    ?TraceRpcEEInfo@@YAXXZ; TraceRpcEEInfo(void)
0x18006e9c4  mov     ecx, ebx; int
0x18006e9c6  call    ?RpcStatusToHresult@@YAJJ@Z; RpcStatusToHresult(long)
0x18006e9cb  xor     ebx, ebx
0x18006e9cd  lea     r14d, [rbx+1]
0x18006e9d1  mov     r15d, [rsp+78h+arg_8]
0x18006e9d9  mov     rdi, [rsp+78h+arg_18]
0x18006e9e1  mov     rdx, [rdi]
0x18006e9e4  mov     ecx, [rdx+18h]
0x18006e9e7  test    ecx, ecx
0x18006e9e9  jz      loc_18006EB08
0x18006e9ef  cmp     ecx, 1
0x18006e9f2  jnz     loc_18006ED50
0x18006e9f8  lea     rcx, [rsi+20h]
0x18006e9fc  xor     r8d, r8d
0x18006e9ff  mov     edx, r15d
0x18006ea02  call    C_TearDownContext
0x18006ea07  test    eax, eax
0x18006ea09  jz      short loc_18006EA3F
0x18006ea0b  lea     rcx, aFailureReturnF_0; "Failure return from C_TearDownContext"
0x18006ea12  mov     [rsp+78h+var_48], rcx
0x18006ea17  mov     dword ptr [rsp+78h+var_50], eax
0x18006ea1b  lea     rsi, aCrpciomanagerc_10; "CRpcIOManagerClient::Unbind"
0x18006ea22  mov     [rsp+78h+var_58], rsi
0x18006ea27  mov     r9d, 6DBh
0x18006ea2d  lea     r8, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrc"...
0x18006ea34  mov     edx, r14d
0x18006ea37  mov     ecx, r14d
0x18006ea3a  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18006ea3f  jmp     loc_18006EAFD
0x18006ea44  mov     ebx, eax
0x18006ea46  mov     rdi, [rsp+78h+arg_0]
0x18006ea4e  mov     rcx, [rdi+18h]
0x18006ea52  mov     [rsp+78h+var_38], rcx
0x18006ea57  mov     rcx, [rdi+10h]
0x18006ea5b  mov     [rsp+78h+var_40], rcx
0x18006ea60  lea     rax, aRemoteS8sExcep_6; "[Remote:%s %.8s] Exception raised in th"...
0x18006ea67  mov     [rsp+78h+var_48], rax
0x18006ea6c  mov     dword ptr [rsp+78h+var_50], ebx
0x18006ea70  lea     rax, aCrpciomanagerc_10; "CRpcIOManagerClient::Unbind"
0x18006ea77  mov     [rsp+78h+var_58], rax
0x18006ea7c  mov     r9d, 6E4h
0x18006ea82  lea     r8, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrc"...
0x18006ea89  mov     edx, 1
0x18006ea8e  mov     ecx, edx
0x18006ea90  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18006ea95  call    ?TraceRpcEEInfo@@YAXXZ; TraceRpcEEInfo(void)
0x18006ea9a  mov     ecx, ebx; int
0x18006ea9c  call    ?RpcStatusToHresult@@YAJJ@Z; RpcStatusToHresult(long)
0x18006eaa1  nop
0x18006eaa2  cmp     qword ptr [rdi+20h], 0
0x18006eaa7  jz      short loc_18006EAB3
0x18006eaa9  lea     rcx, [rdi+20h]; ContextHandle
0x18006eaad  call    cs:__imp_RpcSsDestroyClientContext
0x18006eab3  jmp     short loc_18006EAF3
0x18006eab5  lea     rax, aExceptionWhile; "EXCEPTION : While destroying the Contex"...
0x18006eabc  mov     [rsp+78h+var_48], rax
0x18006eac1  mov     [rsp+78h+var_50], 0
0x18006eaca  lea     rax, aCrpciomanagerc_10; "CRpcIOManagerClient::Unbind"
0x18006ead1  mov     [rsp+78h+var_58], rax
0x18006ead6  mov     r9d, 6F3h
0x18006eadc  lea     r8, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrc"...
0x18006eae3  mov     edx, 0F0h
0x18006eae8  mov     ecx, 1
0x18006eaed  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18006eaf2  nop
0x18006eaf3  xor     ebx, ebx
0x18006eaf5  mov     rdi, [rsp+78h+arg_18]
0x18006eafd  mov     rax, [rdi]
0x18006eb00  mov     [rax+18h], ebx
0x18006eb03  jmp     loc_18006ED38
0x18006eb08  lea     rcx, [rdx+30h]; char *
0x18006eb0c  lea     r8, a00000000000000; "00000000-0000-0000-0000-000000000000"
0x18006eb13  mov     edx, 25h ; '%'; unsigned __int64
0x18006eb18  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x18006eb1d  nop
0x18006eb1e  lea     rcx, [rsi+20h]
0x18006eb22  mov     r8d, 2
0x18006eb28  mov     edx, r15d
0x18006eb2b  call    C_TearDownContext
0x18006eb30  test    eax, eax
0x18006eb32  jz      short loc_18006EB68
0x18006eb34  lea     rcx, aFailureReturnF_0; "Failure return from C_TearDownContext"
0x18006eb3b  mov     [rsp+78h+var_48], rcx
0x18006eb40  mov     dword ptr [rsp+78h+var_50], eax
0x18006eb44  lea     rsi, aCrpciomanagerc_10; "CRpcIOManagerClient::Unbind"
0x18006eb4b  mov     [rsp+78h+var_58], rsi
0x18006eb50  mov     r9d, 70Fh
0x18006eb56  lea     r8, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrc"...
0x18006eb5d  mov     edx, r14d
0x18006eb60  mov     ecx, r14d
0x18006eb63  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18006eb68  jmp     loc_18006EC26
0x18006eb6d  mov     ebx, eax
0x18006eb6f  mov     rdi, [rsp+78h+arg_0]
0x18006eb77  mov     rcx, [rdi+18h]
0x18006eb7b  mov     [rsp+78h+var_38], rcx
0x18006eb80  mov     rcx, [rdi+10h]
0x18006eb84  mov     [rsp+78h+var_40], rcx
0x18006eb89  lea     rax, aRemoteS8sExcep_6; "[Remote:%s %.8s] Exception raised in th"...
0x18006eb90  mov     [rsp+78h+var_48], rax
0x18006eb95  mov     dword ptr [rsp+78h+var_50], ebx
0x18006eb99  lea     rax, aCrpciomanagerc_10; "CRpcIOManagerClient::Unbind"
0x18006eba0  mov     [rsp+78h+var_58], rax
0x18006eba5  mov     r9d, 718h
0x18006ebab  lea     r8, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrc"...
0x18006ebb2  mov     edx, 1
0x18006ebb7  mov     ecx, edx
0x18006ebb9  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18006ebbe  call    ?TraceRpcEEInfo@@YAXXZ; TraceRpcEEInfo(void)
0x18006ebc3  mov     ecx, ebx; int
0x18006ebc5  call    ?RpcStatusToHresult@@YAJJ@Z; RpcStatusToHresult(long)
0x18006ebca  nop
0x18006ebcb  cmp     qword ptr [rdi+20h], 0
0x18006ebd0  jz      short loc_18006EBDC
0x18006ebd2  lea     rcx, [rdi+20h]; ContextHandle
0x18006ebd6  call    cs:__imp_RpcSsDestroyClientContext
0x18006ebdc  jmp     short loc_18006EC1C
0x18006ebde  lea     rax, aExceptionWhile; "EXCEPTION : While destroying the Contex"...
0x18006ebe5  mov     [rsp+78h+var_48], rax
0x18006ebea  mov     [rsp+78h+var_50], 0
0x18006ebf3  lea     rax, aCrpciomanagerc_10; "CRpcIOManagerClient::Unbind"
0x18006ebfa  mov     [rsp+78h+var_58], rax
0x18006ebff  mov     r9d, 727h
0x18006ec05  lea     r8, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrc"...
0x18006ec0c  mov     edx, 0F0h
0x18006ec11  mov     ecx, 1
0x18006ec16  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18006ec1b  nop
0x18006ec1c  xor     ebx, ebx
0x18006ec1e  mov     rdi, [rsp+78h+arg_18]
0x18006ec26  mov     rax, [rdi]
0x18006ec29  mov     [rax+18h], ebx
0x18006ec2c  jmp     loc_18006ED50
0x18006ec31  lea     rcx, [rsi+20h]
0x18006ec35  xor     r8d, r8d
0x18006ec38  lea     r14d, [r8+1]
0x18006ec3c  mov     edx, r14d
0x18006ec3f  call    C_TearDownContext
0x18006ec44  test    eax, eax
0x18006ec46  jz      short loc_18006EC7C
0x18006ec48  lea     rcx, aFailureReturnF_0; "Failure return from C_TearDownContext"
0x18006ec4f  mov     [rsp+78h+var_48], rcx
0x18006ec54  mov     dword ptr [rsp+78h+var_50], eax
0x18006ec58  lea     rsi, aCrpciomanagerc_10; "CRpcIOManagerClient::Unbind"
0x18006ec5f  mov     [rsp+78h+var_58], rsi
0x18006ec64  mov     r9d, 685h
0x18006ec6a  lea     r8, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrc"...
0x18006ec71  mov     edx, r14d
0x18006ec74  mov     ecx, r14d
0x18006ec77  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18006ec7c  jmp     loc_18006ED38
0x18006ec81  mov     ebx, eax
0x18006ec83  mov     rdi, [rsp+78h+arg_0]
0x18006ec8b  mov     rcx, [rdi+18h]
  ... truncated ...
```
