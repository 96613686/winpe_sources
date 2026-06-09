# R_ResolverQuery

- ea: `0x180038980`
- end: `0x180038f21`
- name: `R_ResolverQuery`
- size: `1441`
- prototype: `__int64 __usercall@<rax>(PRPC_ASYNC_STATE pAsync@<rcx>, int, int, int, int, __int64, __int16, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003240`
- `0x180003f30`
- `0x180005270`
- `0x180005370`
- `0x18000b130`
- `0x180017c60`
- `0x180038980`
- `0x180046ec0`
- `0x18005020c`
- `0x18005167c`
- `0x180066e08`
- `0x180078ad8`
- `0x180086700`
- `0x180086714`
- `0x180086b1c`

## import_xrefs

- `RPCRT4!RpcServerSubscribeForNotification` at `0x180038d54`
- `RPCRT4!RpcServerSubscribeForNotification` at `0x180038d54`
- `RPCRT4!RpcRevertToSelf` at `0x180038cd0`
- `RPCRT4!RpcRevertToSelf` at `0x180038cd0`
- `RPCRT4!RpcImpersonateClient` at `0x180038ca1`
- `RPCRT4!RpcImpersonateClient` at `0x180038ca1`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180038e67`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180038e67`
- `DNSAPI!AddRefQueryBlobEx` at `0x180038d0e`
- `DNSAPI!AddRefQueryBlobEx` at `0x180038d2a`
- `DNSAPI!AddRefQueryBlobEx` at `0x180038d0e`
- `DNSAPI!AddRefQueryBlobEx` at `0x180038d2a`
- `DNSAPI!DeRefQueryBlobEx` at `0x180038d9b`
- `DNSAPI!DeRefQueryBlobEx` at `0x180038e52`
- `DNSAPI!DeRefQueryBlobEx` at `0x180038ea7`
- `DNSAPI!DeRefQueryBlobEx` at `0x180038ec8`
- `DNSAPI!DeRefQueryBlobEx` at `0x180038d9b`
- `DNSAPI!DeRefQueryBlobEx` at `0x180038e52`
- `DNSAPI!DeRefQueryBlobEx` at `0x180038ea7`
- `DNSAPI!DeRefQueryBlobEx` at `0x180038ec8`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180038a68`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180038e71`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180038a68`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180038e71`

## pseudocode

```c
void __fastcall R_ResolverQuery(
        PRPC_ASYNC_STATE pAsync,
        int a2,
        __int64 a3,
        unsigned __int16 a4,
        int a5,
        int a6,
        int a7,
        int a8,
        __int64 a9,
        __int16 a10,
        _QWORD *a11,
        _QWORD *a12,
        _QWORD *a13,
        _QWORD *a14,
        _QWORD *a15)
{
  void *RuntimeInfo; // rcx
  bool v17; // zf
  unsigned int v18; // eax
  int v19; // edi
  __int64 v20; // rdx
  __int64 v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // r15
  void *v24; // rcx
  unsigned int v25; // eax
  __int64 v26; // r9
  __int64 v27; // rdx
  int v29; // [rsp+88h] [rbp-61h]
  __int64 v30; // [rsp+90h] [rbp-59h]
  __int64 v31; // [rsp+A0h] [rbp-49h] BYREF
  void *v32; // [rsp+A8h] [rbp-41h] BYREF
  RPC_ASYNC_NOTIFICATION_INFO NotificationInfo; // [rsp+B0h] [rbp-39h] BYREF
  unsigned int Reply; // [rsp+D0h] [rbp-19h] BYREF
  LARGE_INTEGER v35; // [rsp+D8h] [rbp-11h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+E0h] [rbp-9h] BYREF

  Reply = 0;
  PerformanceCount.QuadPart = 0;
  v35.QuadPart = 0;
  v31 = 0;
  v30 = 0;
  v32 = 0;
  v29 = a3;
  memset(&NotificationInfo, 0, sizeof(NotificationInfo));
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_qSDDlDDqqqqqq(
      a5,
      a2,
      a3,
      (_DWORD)pAsync,
      a3,
      a4,
      a5,
      a6,
      a7,
      a8,
      a9,
      (__int64)a11,
      (__int64)a12,
      (__int64)a13,
      (__int64)a14,
      (__int64)a15);
  QueryPerformanceCounter(&PerformanceCount);
  if ( a12 )
    *a12 = 0;
  if ( a13 )
    *a13 = 0;
  if ( a14 )
    *a14 = 0;
  if ( a15 )
    *a15 = 0;
  if ( !a12 || !a13 || !a14 || !a15 || !a11 )
  {
    Reply = 87;
    goto LABEL_55;
  }
  Reply = 0;
  if ( pAsync )
  {
    Reply = Query_PrepareBlob(v29, a4, a5, a6, a7, g_DefaultCompartmentId, a8, a9, a10, (__int64)a11, (__int64)&v31);
    if ( Reply )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
        goto LABEL_54;
      v20 = 79;
    }
    else
    {
      v17 = g_fHvsiActive == 0;
      *(_QWORD *)(v31 + 336) = pAsync;
      *(_QWORD *)(v31 + 368) = a12;
      *(_QWORD *)(v31 + 3376) = a13;
      *(_QWORD *)(v31 + 360) = a14;
      *(_QWORD *)(v31 + 384) = a15;
      if ( v17 || (*a11 & 0x18000000000000LL) != 0x8000000000000LL )
      {
        v19 = 0;
        *(_DWORD *)(v31 + 3432) = 1;
        goto LABEL_32;
      }
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_(1035, 80, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids);
      v18 = HvsiR_ResolverQuery(v29, a4, a5, a6, a7, (__int64)a11, (__int64)a12, v31 + 3384);
      Reply = v18;
      LOBYTE(RuntimeInfo) = BYTE1(xmmword_1800AB5A0);
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      {
        WPP_SF_d(1035, 81, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v18);
        LOBYTE(RuntimeInfo) = BYTE1(xmmword_1800AB5A0);
      }
      if ( !Reply )
      {
        v19 = 1;
LABEL_32:
        *(_QWORD *)(v31 + 3392) = R_ResolverQuery;
        CRpcWatchDog::AddEntry((CRpcWatchDog *)R_ResolverQuery, (struct _WatchDogEntry *)(v31 + 3392), 1);
        v21 = v31;
        *(_DWORD *)(v21 + 344) = GetRpcClientPid();
        RuntimeInfo = pAsync->RuntimeInfo;
        if ( RuntimeInfo )
        {
          Reply = 0;
          Reply = RpcImpersonateClient(RuntimeInfo);
          if ( Reply )
          {
            if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
              goto LABEL_54;
            v20 = 84;
          }
          else
          {
            Reply = Dns_GetApplicationIdentifier(&v32, v31 + 3304, v31 + 3372);
            RpcRevertToSelf();
            if ( !Reply )
            {
              *(_QWORD *)(v31 + 3296) = v32;
              v22 = v31;
              pAsync->UserInfo = (void *)v31;
              v32 = 0;
              AddRefQueryBlobEx(v22, "R_ResolverQuery", 2505, 1);
              v23 = v31;
              AddRefQueryBlobEx(v31, "R_ResolverQuery", 2514, 25);
              v24 = pAsync->RuntimeInfo;
              v30 = v31;
              NotificationInfo.APC.NotificationRoutine = (PFN_RPCNOTIFICATION_ROUTINE)ResolverCancelQuery;
              v25 = RpcServerSubscribeForNotification(
                      v24,
                      RpcNotificationCallCancel,
                      RpcNotificationTypeCallback,
                      &NotificationInfo);
              Reply = v25;
              if ( v25 )
              {
                if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
                  WPP_SF_d(1035, 86, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v25);
                if ( v23 )
                {
                  DeRefQueryBlobEx(v23, "R_ResolverQuery", 2542, 1);
                  pAsync->UserInfo = 0;
                }
              }
              else
              {
                if ( v19 )
                  ResolverCompleteHvsiQuery(v31);
                else
                  RpcConcurrentQueryStart(v31);
                v31 = 0;
              }
              goto LABEL_54;
            }
            if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
              goto LABEL_54;
            v20 = 85;
          }
          goto LABEL_52;
        }
        Reply = 87;
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        {
          v20 = 83;
          v26 = 87;
LABEL_53:
          WPP_SF_d(1035, v20, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v26);
          goto LABEL_54;
        }
LABEL_55:
        if ( v31 )
        {
          CRpcWatchDog::RemoveEntry((CRpcWatchDog *)RuntimeInfo, (struct _WatchDogEntry *)(v31 + 3392));
          DeRefQueryBlobEx(v31, "R_ResolverQuery", 2578, 0);
          v31 = 0;
        }
        RpcAsyncCompleteCall(pAsync, &Reply);
        QueryPerformanceCounter(&v35);
        Trace_LogQueryDuration(v35.QuadPart - PerformanceCount.QuadPart, v27, Reply);
        goto LABEL_58;
      }
      if ( ((unsigned __int8)RuntimeInfo & 8) == 0 )
        goto LABEL_54;
      v20 = 82;
    }
LABEL_52:
    v26 = Reply;
    goto LABEL_53;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
    goto LABEL_60;
  WPP_SF_(1035, 78, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids);
LABEL_54:
  if ( Reply )
    goto LABEL_55;
LABEL_58:
  if ( v30 )
    DeRefQueryBlobEx(v30, "R_ResolverQuery", 2591, 25);
LABEL_60:
  MIDL_user_free(v32);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 87, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, Reply);
}

```

## disassembly

```asm
0x180038980  mov     [rsp-8+arg_8], rbx
0x180038985  push    rbp
0x180038986  push    rsi
0x180038987  push    rdi
0x180038988  push    r12
0x18003898a  push    r13
0x18003898c  push    r14
0x18003898e  push    r15
0x180038990  lea     rbp, [rsp-7]
0x180038995  sub     rsp, 0F0h
0x18003899c  mov     rax, cs:__security_cookie
0x1800389a3  xor     rax, rsp
0x1800389a6  mov     [rbp+37h+var_38], rax
0x1800389aa  mov     r12, [rbp+37h+arg_50]
0x1800389b1  xorps   xmm0, xmm0
0x1800389b4  mov     rbx, [rbp+37h+arg_58]
0x1800389bb  mov     r13, rcx
0x1800389be  mov     rcx, [rbp+37h+arg_40]
0x1800389c5  mov     rdi, [rbp+37h+arg_60]
0x1800389cc  mov     rsi, [rbp+37h+arg_68]
0x1800389d3  mov     r14, [rbp+37h+arg_70]
0x1800389da  movzx   eax, r9w
0x1800389de  xor     r9d, r9d
0x1800389e1  mov     [rbp+37h+var_88], rcx
0x1800389e5  mov     r15d, r9d
0x1800389e8  mov     [rbp+37h+Reply], r9d
0x1800389ec  mov     qword ptr [rbp+37h+PerformanceCount], r9
0x1800389f0  mov     qword ptr [rbp+37h+var_48], r9
0x1800389f4  mov     [rbp+37h+var_80], r9
0x1800389f8  mov     [rbp+37h+var_90], r9
0x1800389fc  mov     [rbp+37h+var_78], r9
0x180038a00  mov     [rbp+37h+var_A0], ax
0x180038a04  mov     [rbp+37h+var_98], r8
0x180038a08  movups  xmmword ptr [rbp+37h+NotificationInfo], xmm0
0x180038a0c  movups  xmmword ptr [rbp+37h+NotificationInfo+10h], xmm0
0x180038a10  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180038a17  jz      short loc_180038A64
0x180038a19  mov     [rsp+120h+var_A8], r14
0x180038a1e  mov     r9, r13
0x180038a21  mov     [rsp+120h+var_B0], rsi
0x180038a26  mov     [rsp+120h+var_B8], rdi
0x180038a2b  mov     [rsp+120h+var_C0], rbx
0x180038a30  mov     [rsp+120h+var_C8], r12
0x180038a35  mov     [rsp+120h+var_D0], rcx
0x180038a3a  mov     ecx, [rbp+37h+arg_38]
0x180038a3d  mov     dword ptr [rsp+120h+var_D8], ecx
0x180038a41  mov     ecx, [rbp+37h+arg_30]
0x180038a44  mov     [rsp+120h+var_E0], ecx
0x180038a48  mov     ecx, [rbp+37h+arg_28]
0x180038a4b  mov     dword ptr [rsp+120h+var_E8], ecx
0x180038a4f  mov     ecx, [rbp+37h+arg_20]
0x180038a52  mov     dword ptr [rsp+120h+var_F0], ecx
0x180038a56  mov     dword ptr [rsp+120h+var_F8], eax
0x180038a5a  mov     [rsp+120h+var_100], r8
0x180038a5f  call    WPP_SF_qSDDlDDqqqqqq
0x180038a64  lea     rcx, [rbp+37h+PerformanceCount]; lpPerformanceCount
0x180038a68  call    cs:__imp_QueryPerformanceCounter
0x180038a6e  xor     edx, edx
0x180038a70  test    rbx, rbx
0x180038a73  jz      short loc_180038A78
0x180038a75  mov     [rbx], rdx
0x180038a78  test    rdi, rdi
0x180038a7b  jz      short loc_180038A80
0x180038a7d  mov     [rdi], rdx
0x180038a80  test    rsi, rsi
0x180038a83  jz      short loc_180038A88
0x180038a85  mov     [rsi], rdx
0x180038a88  test    r14, r14
0x180038a8b  jz      short loc_180038A90
0x180038a8d  mov     [r14], rdx
0x180038a90  mov     eax, 57h ; 'W'
0x180038a95  test    rbx, rbx
0x180038a98  jnz     short loc_180038AA2
0x180038a9a  mov     [rbp+37h+Reply], eax
0x180038a9d  jmp     loc_180038E29
0x180038aa2  test    rdi, rdi
0x180038aa5  jz      short loc_180038A9A
0x180038aa7  test    rsi, rsi
0x180038aaa  jz      short loc_180038A9A
0x180038aac  test    r14, r14
0x180038aaf  jz      short loc_180038A9A
0x180038ab1  test    r12, r12
0x180038ab4  jz      short loc_180038A9A
0x180038ab6  mov     [rbp+37h+Reply], edx
0x180038ab9  test    r13, r13
0x180038abc  jnz     short loc_180038AE5
0x180038abe  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180038ac5  jz      loc_180038ECE
0x180038acb  lea     edx, [r13+4Eh]
0x180038acf  mov     ecx, 40Bh
0x180038ad4  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x180038adb  call    WPP_SF_
0x180038ae0  jmp     loc_180038E23
0x180038ae5  mov     r9d, [rbp+37h+arg_28]
0x180038ae9  lea     rax, [rbp+37h+var_80]
0x180038aed  mov     r8d, [rbp+37h+arg_20]
0x180038af1  movzx   edx, [rbp+37h+var_A0]
0x180038af5  mov     rcx, [rbp+37h+var_98]
0x180038af9  mov     [rsp+120h+var_D0], rax
0x180038afe  movzx   eax, [rbp+37h+arg_48]
0x180038b05  mov     [rsp+120h+var_D8], r12
0x180038b0a  mov     word ptr [rsp+120h+var_E0], ax
0x180038b0f  mov     rax, [rbp+37h+var_88]
0x180038b13  mov     [rsp+120h+var_E8], rax
0x180038b18  mov     eax, [rbp+37h+arg_38]
0x180038b1b  mov     dword ptr [rsp+120h+var_F0], eax
0x180038b1f  mov     eax, cs:g_DefaultCompartmentId
0x180038b25  mov     dword ptr [rsp+120h+var_F8], eax
0x180038b29  mov     eax, [rbp+37h+arg_30]
0x180038b2c  mov     dword ptr [rsp+120h+var_100], eax
0x180038b30  call    Query_PrepareBlob
0x180038b35  xor     r9d, r9d
0x180038b38  mov     [rbp+37h+Reply], eax
0x180038b3b  test    eax, eax
0x180038b3d  jnz     loc_180038E00
0x180038b43  cmp     cs:g_fHvsiActive, r9d
0x180038b4a  mov     rax, [rbp+37h+var_80]
0x180038b4e  mov     [rax+150h], r13
0x180038b55  mov     rax, [rbp+37h+var_80]
0x180038b59  mov     [rax+170h], rbx
0x180038b60  mov     rax, [rbp+37h+var_80]
0x180038b64  mov     [rax+0D30h], rdi
0x180038b6b  mov     rax, [rbp+37h+var_80]
0x180038b6f  mov     [rax+168h], rsi
0x180038b76  mov     rax, [rbp+37h+var_80]
0x180038b7a  mov     [rax+180h], r14
0x180038b81  jz      loc_180038C4D
0x180038b87  mov     rax, [r12]
0x180038b8b  mov     rcx, 18000000000000h
0x180038b95  and     rax, rcx
0x180038b98  mov     rcx, 8000000000000h
0x180038ba2  cmp     rax, rcx
0x180038ba5  jnz     loc_180038C4D
0x180038bab  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180038bb2  jz      short loc_180038BC9
0x180038bb4  lea     edx, [r9+50h]
0x180038bb8  mov     ecx, 40Bh
0x180038bbd  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x180038bc4  call    WPP_SF_
0x180038bc9  mov     rax, [rbp+37h+var_80]
0x180038bcd  mov     r9d, [rbp+37h+arg_28]
0x180038bd1  add     rax, 0D38h
0x180038bd7  mov     r8d, [rbp+37h+arg_20]
0x180038bdb  movzx   edx, [rbp+37h+var_A0]
0x180038bdf  mov     rcx, [rbp+37h+var_98]
0x180038be3  mov     [rsp+120h+var_E8], rax
0x180038be8  mov     eax, [rbp+37h+arg_30]
0x180038beb  mov     [rsp+120h+var_F0], rbx
0x180038bf0  mov     [rsp+120h+var_F8], r12
0x180038bf5  mov     dword ptr [rsp+120h+var_100], eax
0x180038bf9  call    HvsiR_ResolverQuery
0x180038bfe  mov     [rbp+37h+Reply], eax
0x180038c01  mov     cl, byte ptr cs:xmmword_1800AB5A0+1
0x180038c07  test    cl, 8
0x180038c0a  jz      short loc_180038C2B
0x180038c0c  mov     edx, 51h ; 'Q'
0x180038c11  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x180038c18  mov     ecx, 40Bh
0x180038c1d  mov     r9d, eax
0x180038c20  call    WPP_SF_d
0x180038c25  mov     cl, byte ptr cs:xmmword_1800AB5A0+1
0x180038c2b  cmp     [rbp+37h+Reply], r15d
0x180038c2f  jnz     short loc_180038C3A
0x180038c31  mov     esi, 1
0x180038c36  mov     edi, esi
0x180038c38  jmp     short loc_180038C5C
0x180038c3a  test    cl, 8
0x180038c3d  jz      loc_180038E23
0x180038c43  mov     edx, 52h ; 'R'
0x180038c48  jmp     loc_180038E0E
0x180038c4d  mov     rax, [rbp+37h+var_80]
0x180038c51  xor     edi, edi
0x180038c53  lea     esi, [rdi+1]
0x180038c56  mov     [rax+0D68h], esi
0x180038c5c  mov     rax, [rbp+37h+var_80]
0x180038c60  lea     rcx, R_ResolverQuery; this
0x180038c67  mov     r8d, esi; int
0x180038c6a  mov     [rax+0D40h], rcx
0x180038c71  mov     rdx, [rbp+37h+var_80]
0x180038c75  add     rdx, 0D40h; struct _WatchDogEntry *
0x180038c7c  call    ?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z; CRpcWatchDog::AddEntry(_WatchDogEntry *,int)
0x180038c81  mov     rbx, [rbp+37h+var_80]
0x180038c85  call    GetRpcClientPid
0x180038c8a  mov     [rbx+158h], eax
0x180038c90  mov     rcx, [r13+20h]; BindingHandle
0x180038c94  test    rcx, rcx
0x180038c97  jz      loc_180038DE7
0x180038c9d  mov     [rbp+37h+Reply], r15d
0x180038ca1  call    cs:__imp_RpcImpersonateClient
0x180038ca7  mov     [rbp+37h+Reply], eax
0x180038caa  test    eax, eax
0x180038cac  jnz     loc_180038DD7
0x180038cb2  mov     rdx, [rbp+37h+var_80]
0x180038cb6  lea     rcx, [rbp+37h+var_78]
0x180038cba  lea     r8, [rdx+0D2Ch]
0x180038cc1  add     rdx, 0CE8h
0x180038cc8  call    Dns_GetApplicationIdentifier
0x180038ccd  mov     [rbp+37h+Reply], eax
0x180038cd0  call    cs:__imp_RpcRevertToSelf
0x180038cd6  cmp     [rbp+37h+Reply], r15d
0x180038cda  jnz     loc_180038DC7
0x180038ce0  mov     rcx, [rbp+37h+var_80]
0x180038ce4  lea     rbx, aRResolverquery; "R_ResolverQuery"
0x180038ceb  mov     rax, [rbp+37h+var_78]
0x180038cef  mov     r9d, esi
0x180038cf2  mov     r8d, 9C9h
0x180038cf8  mov     rdx, rbx
0x180038cfb  mov     [rcx+0CE0h], rax
0x180038d02  mov     rcx, [rbp+37h+var_80]
0x180038d06  mov     [r13+18h], rcx
0x180038d0a  mov     [rbp+37h+var_78], r15
0x180038d0e  call    cs:__imp_AddRefQueryBlobEx
0x180038d14  mov     r15, [rbp+37h+var_80]
0x180038d18  mov     r9d, 19h
0x180038d1e  mov     rcx, r15
0x180038d21  mov     r8d, 9D2h
0x180038d27  mov     rdx, rbx
0x180038d2a  call    cs:__imp_AddRefQueryBlobEx
0x180038d30  mov     rdx, [rbp+37h+var_80]
0x180038d34  lea     rax, ResolverCancelQuery
0x180038d3b  mov     rcx, [r13+20h]; Binding
0x180038d3f  lea     r9, [rbp+37h+NotificationInfo]; NotificationInfo
0x180038d43  mov     [rbp+37h+var_90], rdx
0x180038d47  mov     edx, 2; Notification
0x180038d4c  mov     qword ptr [rbp+37h+NotificationInfo], rax
0x180038d50  lea     r8d, [rdx+3]; NotificationType
0x180038d54  call    cs:__imp_RpcServerSubscribeForNotification
0x180038d5a  mov     [rbp+37h+Reply], eax
0x180038d5d  test    eax, eax
0x180038d5f  jz      short loc_180038DAA
0x180038d61  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180038d68  jz      short loc_180038D83
0x180038d6a  mov     edx, 56h ; 'V'
0x180038d6f  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x180038d76  mov     ecx, 40Bh
0x180038d7b  mov     r9d, eax
0x180038d7e  call    WPP_SF_d
0x180038d83  test    r15, r15
0x180038d86  jz      loc_180038E23
0x180038d8c  mov     r9d, esi
0x180038d8f  mov     r8d, 9EEh
0x180038d95  mov     rdx, rbx
0x180038d98  mov     rcx, r15
0x180038d9b  call    cs:__imp_DeRefQueryBlobEx
0x180038da1  xor     r15d, r15d
0x180038da4  mov     [r13+18h], r15
0x180038da8  jmp     short loc_180038E23
0x180038daa  mov     rcx, [rbp+37h+var_80]
0x180038dae  xor     r15d, r15d
0x180038db1  test    edi, edi
0x180038db3  jz      short loc_180038DBC
0x180038db5  call    ResolverCompleteHvsiQuery
0x180038dba  jmp     short loc_180038DC1
0x180038dbc  call    RpcConcurrentQueryStart
0x180038dc1  mov     [rbp+37h+var_80], r15
0x180038dc5  jmp     short loc_180038E23
0x180038dc7  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180038dce  jz      short loc_180038E23
0x180038dd0  mov     edx, 55h ; 'U'
0x180038dd5  jmp     short loc_180038E0E
0x180038dd7  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180038dde  jz      short loc_180038E23
0x180038de0  mov     edx, 54h ; 'T'
0x180038de5  jmp     short loc_180038E0E
0x180038de7  mov     eax, 57h ; 'W'
0x180038dec  mov     [rbp+37h+Reply], eax
0x180038def  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180038df6  jz      short loc_180038E29
0x180038df8  lea     edx, [rax-4]
0x180038dfb  mov     r9d, eax
0x180038dfe  jmp     short loc_180038E12
0x180038e00  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180038e07  jz      short loc_180038E23
0x180038e09  mov     edx, 4Fh ; 'O'
0x180038e0e  mov     r9d, [rbp+37h+Reply]
0x180038e12  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x180038e19  mov     ecx, 40Bh
0x180038e1e  call    WPP_SF_d
0x180038e23  cmp     [rbp+37h+Reply], 0
0x180038e27  jz      short loc_180038E88
0x180038e29  mov     rdx, [rbp+37h+var_80]
0x180038e2d  test    rdx, rdx
0x180038e30  jz      short loc_180038E60
0x180038e32  add     rdx, 0D40h; struct _WatchDogEntry *
0x180038e39  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x180038e3e  mov     rcx, [rbp+37h+var_80]
0x180038e42  lea     rdx, aRResolverquery; "R_ResolverQuery"
0x180038e49  xor     r9d, r9d
0x180038e4c  mov     r8d, 0A12h
0x180038e52  call    cs:__imp_DeRefQueryBlobEx
0x180038e58  mov     [rbp+37h+var_80], 0
0x180038e60  lea     rdx, [rbp+37h+Reply]; Reply
0x180038e64  mov     rcx, r13; pAsync
0x180038e67  call    cs:__imp_RpcAsyncCompleteCall
0x180038e6d  lea     rcx, [rbp+37h+var_48]; lpPerformanceCount
0x180038e71  call    cs:__imp_QueryPerformanceCounter
0x180038e77  mov     rcx, qword ptr [rbp+37h+var_48]
0x180038e7b  sub     rcx, qword ptr [rbp+37h+PerformanceCount]
0x180038e7f  mov     r8d, [rbp+37h+Reply]
0x180038e83  call    Trace_LogQueryDuration
  ... truncated ...
```
