# ResolverRpcComplete

- ea: `0x180004d90`
- end: `0x180005262`
- name: `ResolverRpcComplete`
- size: `1234`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180004c40`
- `0x180034c80`

## callees

- `0x180004d90`
- `0x1800054d0`
- `0x18002e94c`
- `0x180040cd4`
- `0x180046ec0`
- `0x180086b1c`
- `0x180086f24`
- `0x180086f78`
- `0x180087a64`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18000504b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000504b`
- `DNSAPI!DeRefQueryBlobEx` at `0x18000506f`
- `DNSAPI!DeRefQueryBlobEx` at `0x180005093`
- `DNSAPI!DeRefQueryBlobEx` at `0x18000506f`
- `DNSAPI!DeRefQueryBlobEx` at `0x180005093`
- `DNSAPI!DnsGlobals` at `0x180004ff4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004eb9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005039`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004eb9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005039`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004e69`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004fc6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004e69`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004fc6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004f1d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004f1d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800050f7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800050f7`

## string_xrefs

- `0x18000505f`: `ResolverRpcComplete`
- `0x180005089`: `ResolverRpcComplete`

## pseudocode

```c
__int64 __fastcall ResolverRpcComplete(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax
  __int64 v6; // rdx
  int v7; // ett
  __int64 v8; // r8
  _QWORD *v9; // rax
  __int64 v10; // rcx
  _QWORD *v11; // rdx
  __int64 v12; // rbx
  __int64 v13; // rcx
  char *v14; // r10
  __int64 v15; // r9
  _WORD *v16; // r8
  _WORD *v17; // rdx
  _WORD *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // edx
  unsigned int v26; // eax
  unsigned int Reply; // [rsp+30h] [rbp-18h] BYREF

  Reply = *(_DWORD *)(a1 + 508);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_q(1035, 26, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, a1);
  _m_prefetchw((const void *)(a1 + 784));
  LODWORD(result) = *(_DWORD *)(a1 + 784);
  do
  {
    v6 = (unsigned int)result;
    LODWORD(v6) = result | 0x4000;
    v7 = result;
    result = (unsigned int)_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 784), result | 0x4000, result);
  }
  while ( v7 != (_DWORD)result );
  if ( (result & 0x4000) != 0 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      return WPP_SF_q(1035, 27, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, a1);
  }
  else
  {
    if ( (*(_QWORD *)(a1 + 264) & 0x4000000000000LL) != 0 )
      GetNameResolutionHandle(a1);
    if ( **(_QWORD **)(a1 + 360) )
      MicrosoftTelemetryAssertTriggeredNoArgs(a1, v6, a3, a4);
    if ( (*(_DWORD *)(a1 + 528) & 0x200LL) != 0 )
      **(_QWORD **)(a1 + 360) |= 1uLL;
    if ( (*(_BYTE *)(a1 + 528) & 0x10) != 0 )
      **(_QWORD **)(a1 + 360) |= 2uLL;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_qi(a1, 28, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, a1, **(_QWORD **)(a1 + 360));
    if ( (BYTE1(xmmword_1800AB5A0) & 0x40) != 0 )
      WPP_SF_qq(
        1038,
        16,
        (unsigned int)WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids,
        a1 + 3392,
        *(_QWORD *)(a1 + 3392));
    if ( dword_1800ABC8C )
    {
      EnterCriticalSection(&stru_1800ABC58);
      v9 = (_QWORD *)(a1 + 3408);
      v10 = *(_QWORD *)(a1 + 3408);
      if ( *(_QWORD *)(v10 + 8) != a1 + 3408 || (v11 = *(_QWORD **)(a1 + 3416), (_QWORD *)*v11 != v9) )
        __fastfail(3u);
      *v11 = v10;
      *(_QWORD *)(v10 + 8) = v11;
      *(_QWORD *)(a1 + 3416) = a1 + 3408;
      *v9 = v9;
      if ( (__int64 *)qword_1800ABC38 == &qword_1800ABC38 && *(unsigned int **)&qword_1800ABC48 == &qword_1800ABC48 )
        WxSetThreadpoolTimer(g_RpcWatchDog, 0, v8, 0);
      LeaveCriticalSection(&stru_1800ABC58);
    }
    if ( (BYTE1(xmmword_1800AB5A0) & 0x40) != 0 )
      WPP_SF_qq(
        1038,
        17,
        (unsigned int)WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids,
        a1 + 3392,
        *(_QWORD *)(a1 + 3392));
    if ( g_pDnsResolverErrorLogging && *(_DWORD *)(a1 + 508) && *(_QWORD *)(a1 + 248) )
    {
      v12 = 160LL * (((unsigned __int8)_InterlockedExchangeAdd(&g_dwDnsResolverErrorLoggingPosition, 1u) + 1) & 0x3F);
      GetSystemTimeAsFileTime((LPFILETIME)((char *)g_pDnsResolverErrorLogging + v12 + 8));
      v13 = 63;
      v14 = (char *)g_pDnsResolverErrorLogging + v12;
      v15 = 64;
      *((_DWORD *)v14 + 4) = *(_DWORD *)(a1 + 508);
      v16 = v14 + 24;
      v17 = *(_WORD **)(a1 + 248);
      do
      {
        if ( !v13 )
          break;
        if ( !*v17 )
          break;
        *v16++ = *v17++;
        --v13;
        --v15;
      }
      while ( v15 );
      v18 = v16 - 1;
      if ( v15 )
        v18 = v16;
      *v18 = 0;
      *((_WORD *)v14 + 78) = *(_WORD *)(a1 + 256);
      *(_QWORD *)v14 = *(_QWORD *)(a1 + 264);
      *((_DWORD *)v14 + 5) = *(_DWORD *)(a1 + 404);
      *((_DWORD *)v14 + 38) = *(_DWORD *)(a1 + 344);
    }
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_q(1035, 13, WPP_78ecab3900143121f591626d703c42fb_Traceguids, a1);
    EnterCriticalSection(&CriticalSection);
    if ( *(_QWORD *)(a1 + 152) != a1 + 152 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v20, v19, v21, v22);
    if ( *(_DWORD *)(a1 + 3432) == 3 )
    {
      v23 = HIDWORD(qword_1800ABD18);
      if ( !HIDWORD(qword_1800ABD18) )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(0, v19, v21, v22);
        v23 = HIDWORD(qword_1800ABD18);
      }
      v24 = v23 - 1;
      HIDWORD(qword_1800ABD18) = v24;
      v25 = DnsGlobals[91];
      if ( (!v25 || v24 < v25) && (unsigned int)qword_1800ABD18 < 0x80 && (__int64 *)qword_1800ABD28 != &qword_1800ABD28 )
      {
        LODWORD(qword_1800ABD18) = qword_1800ABD18 + 1;
        SubmitThreadpoolWork(pwk);
      }
    }
    LeaveCriticalSection(&CriticalSection);
    v26 = RpcAsyncCompleteCall(*(PRPC_ASYNC_STATE *)(a1 + 336), &Reply);
    if ( v26 && (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_d(1035, 29, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v26);
    DeRefQueryBlobEx(a1, "ResolverRpcComplete", 690, 1);
    *(_QWORD *)(a1 + 336) = 0;
    result = DeRefQueryBlobEx(a1, "ResolverRpcComplete", 694, 0);
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      return WPP_SF_d(1035, 30, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, Reply);
  }
  return result;
}

```

## disassembly

```asm
0x180004d90  push    rdi
0x180004d92  sub     rsp, 40h
0x180004d96  mov     rax, cs:__security_cookie
0x180004d9d  xor     rax, rsp
0x180004da0  mov     [rsp+48h+var_10], rax
0x180004da5  mov     eax, [rcx+1FCh]
0x180004dab  mov     rdi, rcx
0x180004dae  mov     [rsp+48h+Reply], eax
0x180004db2  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180004db9  jnz     loc_1800051FF
0x180004dbf  prefetchw byte ptr [rdi+310h]
0x180004dc6  mov     eax, [rdi+310h]
0x180004dcc  mov     edx, eax
0x180004dce  bts     edx, 0Eh
0x180004dd2  lock cmpxchg [rdi+310h], edx
0x180004dda  jnz     short loc_180004DCC
0x180004ddc  bt      eax, 0Eh
0x180004de0  jb      loc_180005109
0x180004de6  mov     rax, 4000000000000h
0x180004df0  mov     [rsp+48h+arg_8], rbx
0x180004df5  test    [rdi+108h], rax
0x180004dfc  jnz     loc_18000515E
0x180004e02  mov     rax, [rdi+168h]
0x180004e09  cmp     qword ptr [rax], 0
0x180004e0d  jnz     loc_18000521D
0x180004e13  mov     eax, [rdi+210h]
0x180004e19  bt      rax, 9
0x180004e1e  jnb     short loc_180004E2B
0x180004e20  mov     rax, [rdi+168h]
0x180004e27  or      qword ptr [rax], 1
0x180004e2b  test    byte ptr [rdi+210h], 10h
0x180004e32  jz      short loc_180004E3F
0x180004e34  mov     rax, [rdi+168h]
0x180004e3b  or      qword ptr [rax], 2
0x180004e3f  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180004e46  jnz     loc_1800051A9
0x180004e4c  test    byte ptr cs:xmmword_1800AB5A0+1, 40h
0x180004e53  jnz     loc_180005130
0x180004e59  cmp     cs:dword_1800ABC8C, 0
0x180004e60  jz      short loc_180004EBF
0x180004e62  lea     rcx, stru_1800ABC58; lpCriticalSection
0x180004e69  call    cs:__imp_EnterCriticalSection
0x180004e6f  lea     rax, [rdi+0D50h]
0x180004e76  mov     rcx, [rax]
0x180004e79  cmp     [rcx+8], rax
0x180004e7d  jnz     loc_180005102
0x180004e83  mov     rdx, [rax+8]
0x180004e87  cmp     [rdx], rax
0x180004e8a  jnz     loc_180005102
0x180004e90  mov     [rdx], rcx
0x180004e93  mov     [rcx+8], rdx
0x180004e97  mov     [rax+8], rax
0x180004e9b  mov     [rax], rax
0x180004e9e  lea     rax, qword_1800ABC38
0x180004ea5  cmp     cs:qword_1800ABC38, rax
0x180004eac  jz      loc_1800050BE
0x180004eb2  lea     rcx, stru_1800ABC58; lpCriticalSection
0x180004eb9  call    cs:__imp_LeaveCriticalSection
0x180004ebf  test    byte ptr cs:xmmword_1800AB5A0+1, 40h
0x180004ec6  jnz     loc_1800051D1
0x180004ecc  cmp     cs:g_pDnsResolverErrorLogging, 0
0x180004ed4  jz      loc_180004FB2
0x180004eda  cmp     dword ptr [rdi+1FCh], 0
0x180004ee1  jz      loc_180004FB2
0x180004ee7  cmp     qword ptr [rdi+0F8h], 0
0x180004eef  jz      loc_180004FB2
0x180004ef5  mov     eax, 1
0x180004efa  lock xadd cs:g_dwDnsResolverErrorLoggingPosition, eax
0x180004f02  mov     rcx, cs:g_pDnsResolverErrorLogging
0x180004f09  inc     eax
0x180004f0b  and     eax, 3Fh
0x180004f0e  add     rcx, 8
0x180004f12  lea     rbx, [rax+rax*4]
0x180004f16  shl     rbx, 5
0x180004f1a  add     rcx, rbx; lpSystemTimeAsFileTime
0x180004f1d  call    cs:__imp_GetSystemTimeAsFileTime
0x180004f23  mov     r10, cs:g_pDnsResolverErrorLogging
0x180004f2a  mov     ecx, 3Fh ; '?'
0x180004f2f  mov     eax, [rdi+1FCh]
0x180004f35  add     r10, rbx
0x180004f38  mov     r9d, 40h ; '@'
0x180004f3e  mov     [r10+10h], eax
0x180004f42  lea     r8, [r10+18h]
0x180004f46  mov     rdx, [rdi+0F8h]
0x180004f4d  nop     dword ptr [rax]
0x180004f50  test    rcx, rcx
0x180004f53  jz      short loc_180004F72
0x180004f55  movzx   eax, word ptr [rdx]
0x180004f58  test    ax, ax
0x180004f5b  jz      short loc_180004F72
0x180004f5d  mov     [r8], ax
0x180004f61  add     rdx, 2
0x180004f65  add     r8, 2
0x180004f69  dec     rcx
0x180004f6c  sub     r9, 1
0x180004f70  jnz     short loc_180004F50
0x180004f72  test    r9, r9
0x180004f75  lea     rcx, [r8-2]
0x180004f79  cmovnz  rcx, r8
0x180004f7d  xor     eax, eax
0x180004f7f  mov     [rcx], ax
0x180004f82  movzx   eax, word ptr [rdi+100h]
0x180004f89  mov     [r10+9Ch], ax
0x180004f91  mov     rax, [rdi+108h]
0x180004f98  mov     [r10], rax
0x180004f9b  mov     eax, [rdi+194h]
0x180004fa1  mov     [r10+14h], eax
0x180004fa5  mov     eax, [rdi+158h]
0x180004fab  mov     [r10+98h], eax
0x180004fb2  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180004fb9  jnz     loc_18000518B
0x180004fbf  lea     rcx, CriticalSection; lpCriticalSection
0x180004fc6  call    cs:__imp_EnterCriticalSection
0x180004fcc  lea     rax, [rdi+98h]
0x180004fd3  cmp     [rax], rax
0x180004fd6  jz      short loc_180004FDD
0x180004fd8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180004fdd  cmp     dword ptr [rdi+0D68h], 3
0x180004fe4  jnz     short loc_180005032
0x180004fe6  mov     ecx, dword ptr cs:qword_1800ABD18+4
0x180004fec  test    ecx, ecx
0x180004fee  jz      loc_180005227
0x180004ff4  mov     rax, cs:__imp_DnsGlobals
0x180004ffb  dec     ecx
0x180004ffd  mov     dword ptr cs:qword_1800ABD18+4, ecx
0x180005003  mov     edx, [rax+16Ch]
0x180005009  test    edx, edx
0x18000500b  jz      short loc_180005011
0x18000500d  cmp     ecx, edx
0x18000500f  jnb     short loc_180005032
0x180005011  mov     eax, dword ptr cs:qword_1800ABD18
0x180005017  cmp     eax, 80h
0x18000501c  jnb     short loc_180005032
0x18000501e  lea     rdx, qword_1800ABD28
0x180005025  cmp     cs:qword_1800ABD28, rdx
0x18000502c  jnz     loc_1800050E8
0x180005032  lea     rcx, CriticalSection; lpCriticalSection
0x180005039  call    cs:__imp_LeaveCriticalSection
0x18000503f  mov     rcx, [rdi+150h]; pAsync
0x180005046  lea     rdx, [rsp+48h+Reply]; Reply
0x18000504b  call    cs:__imp_RpcAsyncCompleteCall
0x180005051  test    eax, eax
0x180005053  jnz     loc_180005237
0x180005059  mov     r9d, 1
0x18000505f  lea     rdx, aResolverrpccom; "ResolverRpcComplete"
0x180005066  mov     r8d, 2B2h
0x18000506c  mov     rcx, rdi
0x18000506f  call    cs:__imp_DeRefQueryBlobEx
0x180005075  xor     r9d, r9d
0x180005078  mov     qword ptr [rdi+150h], 0
0x180005083  mov     r8d, 2B6h
0x180005089  lea     rdx, aResolverrpccom; "ResolverRpcComplete"
0x180005090  mov     rcx, rdi
0x180005093  call    cs:__imp_DeRefQueryBlobEx
0x180005099  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800050a0  jnz     loc_18000516B
0x1800050a6  mov     rbx, [rsp+48h+arg_8]
0x1800050ab  mov     rcx, [rsp+48h+var_10]
0x1800050b0  xor     rcx, rsp; StackCookie
0x1800050b3  call    __security_check_cookie
0x1800050b8  add     rsp, 40h
0x1800050bc  pop     rdi
0x1800050bd  retn
0x1800050be  lea     rax, qword_1800ABC48
0x1800050c5  cmp     cs:qword_1800ABC48, rax
0x1800050cc  jnz     loc_180004EB2
0x1800050d2  mov     rcx, cs:?g_RpcWatchDog@@3VCRpcWatchDog@@A; struct _TP_TIMER *
0x1800050d9  xor     r9d, r9d; unsigned int
0x1800050dc  xor     edx, edx; struct _FILETIME *
0x1800050de  call    ?WxSetThreadpoolTimer@@YAXPEAU_TP_TIMER@@PEAU_FILETIME@@KK@Z; WxSetThreadpoolTimer(_TP_TIMER *,_FILETIME *,ulong,ulong)
0x1800050e3  jmp     loc_180004EB2
0x1800050e8  mov     rcx, cs:pwk; pwk
0x1800050ef  inc     eax
0x1800050f1  mov     dword ptr cs:qword_1800ABD18, eax
0x1800050f7  call    cs:__imp_SubmitThreadpoolWork
0x1800050fd  jmp     loc_180005032
0x180005102  mov     ecx, 3
0x180005107  int     29h; Win8: RtlFailFast(ecx)
0x180005109  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180005110  jz      short loc_1800050AB
0x180005112  mov     edx, 1Bh
0x180005117  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x18000511e  mov     ecx, 40Bh
0x180005123  mov     r9, rdi
0x180005126  call    WPP_SF_q
0x18000512b  jmp     loc_1800050AB
0x180005130  mov     rax, [rdi+0D40h]
0x180005137  lea     r9, [rdi+0D40h]
0x18000513e  mov     edx, 10h
0x180005143  mov     [rsp+48h+var_28], rax
0x180005148  mov     ecx, 40Eh
0x18000514d  lea     r8, WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids
0x180005154  call    WPP_SF_qq
0x180005159  jmp     loc_180004E59
0x18000515e  mov     rcx, rdi
0x180005161  call    GetNameResolutionHandle
0x180005166  jmp     loc_180004E02
0x18000516b  mov     r9d, [rsp+48h+Reply]
0x180005170  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x180005177  mov     edx, 1Eh
0x18000517c  mov     ecx, 40Bh
0x180005181  call    WPP_SF_d
0x180005186  jmp     loc_1800050A6
0x18000518b  mov     edx, 0Dh
0x180005190  lea     r8, WPP_78ecab3900143121f591626d703c42fb_Traceguids
0x180005197  mov     ecx, 40Bh
0x18000519c  mov     r9, rdi
0x18000519f  call    WPP_SF_q
0x1800051a4  jmp     loc_180004FBF
0x1800051a9  mov     rax, [rdi+168h]
0x1800051b0  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x1800051b7  mov     edx, 1Ch
0x1800051bc  mov     r9, rdi
0x1800051bf  mov     rax, [rax]
0x1800051c2  mov     [rsp+48h+var_28], rax
0x1800051c7  call    WPP_SF_qi
0x1800051cc  jmp     loc_180004E4C
0x1800051d1  mov     rax, [rdi+0D40h]
0x1800051d8  lea     r9, [rdi+0D40h]
0x1800051df  mov     edx, 11h
0x1800051e4  mov     [rsp+48h+var_28], rax
0x1800051e9  mov     ecx, 40Eh
0x1800051ee  lea     r8, WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids
0x1800051f5  call    WPP_SF_qq
0x1800051fa  jmp     loc_180004ECC
0x1800051ff  mov     edx, 1Ah
0x180005204  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x18000520b  mov     ecx, 40Bh
0x180005210  mov     r9, rdi
0x180005213  call    WPP_SF_q
0x180005218  jmp     loc_180004DBF
0x18000521d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180005222  jmp     loc_180004E13
0x180005227  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000522c  mov     ecx, dword ptr cs:qword_1800ABD18+4
0x180005232  jmp     loc_180004FF4
0x180005237  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18000523e  jz      loc_180005059
0x180005244  mov     edx, 1Dh
0x180005249  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x180005250  mov     ecx, 40Bh
0x180005255  mov     r9d, eax
0x180005258  call    WPP_SF_d
0x18000525d  jmp     loc_180005059
```
