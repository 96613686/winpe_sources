# LRPC_BASE_CCALL::DoSendReceive(void)

- ea: `0x180026100`
- end: `0x1800266e3`
- name: `?DoSendReceive@LRPC_BASE_CCALL@@IEAAJXZ`
- size: `1507`
- prototype: `__int64 __fastcall(LRPC_BASE_CCALL *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180081170`
- `0x180095398`

## callees

- `0x180016ae8`
- `0x18001d65c`
- `0x180021e18`
- `0x180026100`
- `0x180026d10`
- `0x180026ea0`
- `0x180027d50`
- `0x180027dd4`
- `0x180027e10`
- `0x180028a00`
- `0x180079fa0`
- `0x18008a000`
- `0x1800ca025`
- `0x1800ca140`
- `0x1800d2010`

## import_xrefs

- `ntdll!NtAlpcSendWaitReceivePort` at `0x18002623f`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18002623f`
- `ntdll!EtwEventActivityIdControl` at `0x180026322`
- `ntdll!EtwEventActivityIdControl` at `0x180026322`
- `ntdll!EtwEventWriteTransfer` at `0x1800263ad`
- `ntdll!EtwEventWriteTransfer` at `0x180026520`
- `ntdll!EtwEventWriteTransfer` at `0x1800263ad`
- `ntdll!EtwEventWriteTransfer` at `0x180026520`

## pseudocode

```c
__int64 __fastcall LRPC_BASE_CCALL::DoSendReceive(LRPC_BASE_CCALL *this)
{
  __int64 v1; // rbx
  const struct _EVENT_DESCRIPTOR *v3; // rdx
  unsigned __int64 v4; // rcx
  __int64 v5; // r14
  __int64 v6; // rbx
  unsigned int v7; // r8d
  unsigned int v8; // edx
  unsigned int i; // eax
  int v10; // ebx
  unsigned __int64 v11; // r8
  int v12; // r9d
  signed __int64 v13; // rdx
  unsigned int j; // ecx
  unsigned int v15; // ebx
  unsigned int v17; // esi
  unsigned int k; // ecx
  struct tagExtendedErrorInfo *ExtendedErrorInfoRecord; // rax
  struct tagExtendedErrorInfo *v20; // rbx
  __int128 v21; // xmm0
  __int64 v22; // xmm1_8
  __int64 v23; // rax
  int v24; // eax
  unsigned __int8 v25; // [rsp+20h] [rbp-E0h]
  const struct _GUID *v26; // [rsp+28h] [rbp-D8h]
  unsigned int v27; // [rsp+30h] [rbp-D0h]
  char v28; // [rsp+40h] [rbp-C0h] BYREF
  char v29; // [rsp+48h] [rbp-B8h] BYREF
  signed __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v31; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v32; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v33; // [rsp+68h] [rbp-98h] BYREF
  __int64 v34; // [rsp+78h] [rbp-88h]
  struct _GUID v35; // [rsp+80h] [rbp-80h] BYREF
  __int128 v36; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v37[16]; // [rsp+A0h] [rbp-60h] BYREF
  char *v38; // [rsp+B0h] [rbp-50h]
  __int64 v39; // [rsp+B8h] [rbp-48h]
  char *v40; // [rsp+C0h] [rbp-40h]
  __int64 v41; // [rsp+C8h] [rbp-38h]
  signed __int64 *v42; // [rsp+D0h] [rbp-30h]
  __int64 v43; // [rsp+D8h] [rbp-28h]
  unsigned __int64 *v44; // [rsp+E0h] [rbp-20h]
  __int64 v45; // [rsp+E8h] [rbp-18h]
  signed __int64 *v46; // [rsp+F0h] [rbp-10h]
  __int64 v47; // [rsp+F8h] [rbp-8h]
  _QWORD v48[4]; // [rsp+100h] [rbp+0h] BYREF

  v1 = *((_QWORD *)this + 63);
  v32 = 0;
  v35 = 0;
  v36 = 0;
  LRPC_BASE_CCALL::InitializeRequestAndAttributes(this, 0);
  *(_QWORD *)(v1 + 72) = 0;
  *(_DWORD *)(v1 + 80) = 0;
  v32 = *(unsigned int *)(*((_QWORD *)this + 35) + 576LL);
  if ( !memcmp_0((char *)this + 208, &g_NullActivityId, 0x10u) )
  {
    if ( Microsoft_Windows_Networking_CorrelationEnabled )
    {
      (*(void (__fastcall **)(LRPC_BASE_CCALL *, struct _GUID *))(*(_QWORD *)this + 264LL))(this, &v35);
      EtwEventActivityIdControl(1, &v36);
      if ( Microsoft_Windows_Networking_CorrelationEnabled )
      {
        *(_QWORD *)&v33 = ActivityTransfer;
        LODWORD(v30) = 0;
        *((_QWORD *)&v33 + 1) = 0x8000000000000001uLL;
        if ( Microsoft_Windows_Networking_CorrelationTraceActivityPayload )
        {
          v48[1] = 16;
          v48[0] = &Microsoft_Windows_Networking_ProviderId;
          v48[2] = &v30;
          v48[3] = 4;
          EtwEventWriteTransfer(Microsoft_Windows_Networking_CorrelationHandle, &v33, &v35, &v36, 2, v48);
        }
        else
        {
          EtwEventWriteTransfer(Microsoft_Windows_Networking_CorrelationHandle, &v33, &v35, &v36, 0, 0);
        }
      }
    }
  }
  else
  {
    (*(void (__fastcall **)(LRPC_BASE_CCALL *, struct _GUID *))(*(_QWORD *)this + 264LL))(this, &v35);
    if ( Microsoft_Windows_Networking_CorrelationEnabled )
      EtwEx_tidActivityInfoTransfer(v4, v3, &v35, (const struct _GUID *)this + 13, v25, v26, v27);
  }
  v5 = *((_QWORD *)this + 35);
  v6 = *((_QWORD *)this + 63);
  if ( this == (LRPC_BASE_CCALL *)-296LL )
    v7 = 0;
  else
    v7 = *((_DWORD *)this + 75);
  if ( v6 )
    v8 = *(__int16 *)(v6 + 2);
  else
    v8 = 0;
  if ( dword_1800F9624 )
  {
    for ( i = 0; i < 4; ++i )
    {
      if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[i] == 76 )
        goto LABEL_15;
    }
    if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
    {
      v30 = *((_QWORD *)this + 63);
      v31 = *(_QWORD *)(v5 + 136);
      v38 = &v28;
      v40 = &v29;
      v42 = &v30;
      v44 = &v31;
      v46 = (signed __int64 *)&v33;
      *(_QWORD *)&v33 = v7 | (unsigned __int64)v8;
      v29 = 75;
      v28 = 76;
      v39 = 1;
      v41 = 1;
      v43 = 8;
      v45 = 8;
      v47 = 8;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&RpcEtwGuid_Context,
        (unsigned int)RPCLogEvent,
        v7,
        6,
        (__int64)v37);
    }
  }
LABEL_15:
  v10 = NtAlpcSendWaitReceivePort(
          *(_QWORD *)(v5 + 136),
          0x20000,
          v6,
          (char *)this + 296,
          v6,
          &v32,
          (char *)this + 296,
          0);
  if ( v10 >= 0 )
  {
    do
    {
      v13 = *(_QWORD *)(v5 + 248);
      if ( (_DWORD)v13 )
      {
        LRPC_CASSOCIATION::MessageReceivedWithClosePending((LRPC_CASSOCIATION *)v5);
        goto LABEL_25;
      }
      v30 = v13 + 0x100000000LL;
      v11 = (unsigned __int64)(v13 + 0x100000000LL) >> 32;
    }
    while ( v13 != _InterlockedCompareExchange64((volatile signed __int64 *)(v5 + 248), v13 + 0x100000000LL, v13) );
    if ( dword_1800F9624 )
    {
      for ( j = 0; j < 4; ++j )
      {
        if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[j] == 97 )
          goto LABEL_25;
      }
      if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
      {
        v30 = 0;
        v31 = (unsigned __int64)(v13 + 0x100000000LL) >> 32;
        v38 = &v29;
        *(_QWORD *)&v33 = v5;
        v40 = &v28;
        v42 = (signed __int64 *)&v33;
        v44 = &v31;
        v46 = &v30;
        v28 = 81;
        v29 = 97;
        v39 = 1;
        v41 = 1;
        v43 = 8;
        v45 = 8;
        v47 = 8;
        McGenEventWrite_EtwEventWriteTransfer(
          (unsigned int)&RpcEtwGuid_Context,
          (unsigned int)RPCLogEvent,
          v11,
          6,
          (__int64)v37);
      }
    }
  }
LABEL_25:
  if ( !v10 )
  {
    v15 = 0;
    goto LABEL_27;
  }
  if ( v10 > -1073741769 )
  {
    if ( v10 == -1073740031 )
    {
      v24 = 1818;
      if ( (*((_DWORD *)this + 72) & 1) == 0 )
        v24 = 1726;
      v17 = v24;
      goto LABEL_38;
    }
    if ( v10 == -1073741659 )
    {
      v17 = 5;
      goto LABEL_38;
    }
    if ( v10 != -1073741756 && v10 != -1073741670 )
    {
      if ( v10 == 258 )
      {
        v17 = 1818;
        goto LABEL_38;
      }
      goto LABEL_70;
    }
LABEL_65:
    v17 = 14;
    goto LABEL_38;
  }
  if ( v10 != -1073741769 && v10 != -1073741816 )
  {
    if ( v10 != -1073741801 )
    {
      switch ( v10 )
      {
        case -1073741790:
          v17 = 1783;
          goto LABEL_38;
        case -1073741788:
          v17 = 1836;
          goto LABEL_38;
        case -1073741770:
          v17 = 1834;
          goto LABEL_38;
      }
LABEL_70:
      v17 = 1726;
      goto LABEL_38;
    }
    goto LABEL_65;
  }
  v17 = 1727;
LABEL_38:
  LODWORD(v33) = 3;
  DWORD2(v33) = v10;
  if ( dword_1800F9624 )
  {
    for ( k = 0; k < 4; ++k )
    {
      if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[k] == 73 )
        goto LABEL_45;
    }
    if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
    {
      LOBYTE(v12) = 2;
      LOBYTE(v11) = 73;
      McTemplateU0uuxxx_EtwEventWriteTransfer(k, v17, v11, v12, v17, 242, v10);
    }
  }
LABEL_45:
  ExtendedErrorInfoRecord = AllocateExtendedErrorInfoRecord(1u);
  v20 = ExtendedErrorInfoRecord;
  if ( ExtendedErrorInfoRecord )
  {
    InitializePrivateEEInfo(ExtendedErrorInfoRecord);
    v21 = v33;
    *((_WORD *)v20 + 28) = 1010;
    v22 = v34;
    *((_DWORD *)v20 + 12) = 2;
    *((_DWORD *)v20 + 13) = v17;
    *((_OWORD *)v20 + 4) = v21;
    *((_QWORD *)v20 + 10) = v22;
    if ( (unsigned int)AddPrivateRecord(v20) )
      FreeEEInfoRecord(v20);
  }
  else
  {
    FreeEEInfoPrivateParam(&v33);
  }
  v23 = *(_QWORD *)this;
  *((_DWORD *)this + 67) = 2;
  v15 = (*(__int64 (__fastcall **)(LRPC_BASE_CCALL *, _QWORD))(v23 + 344))(this, v17);
LABEL_27:
  LRPC_SYSTEM_HANDLE_DATA::CleanupSystemHandles((LRPC_BASE_CCALL *)((char *)this + 616), 0);
  return v15;
}

```

## disassembly

```asm
0x180026100  mov     [rsp-8+arg_8], rbx
0x180026105  mov     [rsp-8+arg_10], rsi
0x18002610a  push    rbp
0x18002610b  push    rdi
0x18002610c  push    r12
0x18002610e  push    r14
0x180026110  push    r15
0x180026112  lea     rbp, [rsp-30h]
0x180026117  sub     rsp, 130h
0x18002611e  mov     rax, cs:__security_cookie
0x180026125  xor     rax, rsp
0x180026128  mov     [rbp+50h+var_30], rax
0x18002612c  mov     rbx, [rcx+1F8h]
0x180026133  xorps   xmm0, xmm0
0x180026136  xorps   xmm1, xmm1
0x180026139  xor     r15d, r15d
0x18002613c  xor     edx, edx; int
0x18002613e  mov     [rsp+150h+var_F0], r15
0x180026143  movups  xmmword ptr [rbp+50h+var_D0.Data1], xmm0
0x180026147  mov     rdi, rcx
0x18002614a  movups  [rbp+50h+var_C0], xmm1
0x18002614e  call    ?InitializeRequestAndAttributes@LRPC_BASE_CCALL@@IEAAJH@Z; LRPC_BASE_CCALL::InitializeRequestAndAttributes(int)
0x180026153  mov     [rbx+48h], r15
0x180026157  lea     rdx, ?g_NullActivityId@@3U_GUID@@B; Buf2
0x18002615e  mov     [rbx+50h], r15d
0x180026162  mov     r8d, 10h; Size
0x180026168  mov     rax, [rdi+118h]
0x18002616f  mov     ecx, [rax+240h]
0x180026175  mov     [rsp+150h+var_F0], rcx
0x18002617a  lea     rcx, [rdi+0D0h]; Buf1
0x180026181  call    memcmp_0
0x180026186  test    eax, eax
0x180026188  jz      loc_1800262F5
0x18002618e  mov     rax, [rdi]
0x180026191  lea     rdx, [rbp+50h+var_D0]
0x180026195  mov     rcx, rdi
0x180026198  mov     rax, [rax+108h]
0x18002619f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800261a4  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1800261aa  test    eax, eax
0x1800261ac  jnz     loc_1800264F4
0x1800261b2  mov     r14, [rdi+118h]
0x1800261b9  lea     rsi, [rdi+128h]
0x1800261c0  mov     rbx, [rdi+1F8h]
0x1800261c7  test    rsi, rsi
0x1800261ca  jz      loc_180026629
0x1800261d0  mov     r8d, [rsi+4]
0x1800261d4  test    rbx, rbx
0x1800261d7  jz      loc_180026631
0x1800261dd  movsx   edx, word ptr [rbx+2]
0x1800261e1  cmp     cs:dword_1800F9624, r15d
0x1800261e8  lea     r12, ?EtwEventSubjectFilter@?1??LogEventToEtw@@YAXEE_J00@Z@4QBEB; "HbBr"
0x1800261ef  jz      short loc_180026214
0x1800261f1  mov     eax, r15d
0x1800261f4  cmp     eax, 4
0x1800261f7  jnb     short loc_180026207
0x1800261f9  movsxd  rcx, eax
0x1800261fc  cmp     byte ptr [rcx+r12], 4Ch ; 'L'
0x180026201  jz      short loc_180026214
0x180026203  inc     eax
0x180026205  jmp     short loc_1800261F4
0x180026207  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x18002620e  jnz     loc_1800263B8
0x180026214  mov     rcx, [r14+88h]
0x18002621b  lea     rax, [rsp+150h+var_F0]
0x180026220  mov     [rsp+150h+var_118], r15
0x180026225  mov     r9, rsi
0x180026228  mov     [rsp+150h+var_120], rsi
0x18002622d  mov     r8, rbx
0x180026230  mov     [rsp+150h+var_128], rax
0x180026235  mov     edx, 20000h
0x18002623a  mov     [rsp+150h+var_130], rbx
0x18002623f  call    cs:__imp_NtAlpcSendWaitReceivePort
0x180026245  movsxd  rbx, eax
0x180026248  test    eax, eax
0x18002624a  js      short loc_1800262B2
0x18002624c  mov     rdx, [r14+0F8h]
0x180026253  test    edx, edx
0x180026255  jnz     loc_180026509
0x18002625b  mov     rcx, rdx
0x18002625e  mov     dword ptr [rsp+150h+var_100], edx
0x180026262  shr     rcx, 20h
0x180026266  mov     rax, rdx
0x180026269  inc     ecx
0x18002626b  mov     dword ptr [rsp+150h+var_100+4], ecx
0x18002626f  mov     rcx, [rsp+150h+var_100]
0x180026274  mov     r8, rcx
0x180026277  shr     r8, 20h
0x18002627b  lock cmpxchg [r14+0F8h], rcx
0x180026284  jnz     short loc_18002624C
0x180026286  cmp     cs:dword_1800F9624, r15d
0x18002628d  jz      short loc_1800262B2
0x18002628f  mov     ecx, r15d
0x180026292  cmp     ecx, 4
0x180026295  jnb     short loc_1800262A5
0x180026297  movsxd  rax, ecx
0x18002629a  cmp     byte ptr [rax+r12], 61h ; 'a'
0x18002629f  jz      short loc_1800262B2
0x1800262a1  inc     ecx
0x1800262a3  jmp     short loc_180026292
0x1800262a5  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x1800262ac  jnz     loc_18002645C
0x1800262b2  test    ebx, ebx
0x1800262b4  jnz     loc_18002652B
0x1800262ba  mov     ebx, r15d
0x1800262bd  lea     rcx, [rdi+268h]; this
0x1800262c4  xor     edx, edx; unsigned int
0x1800262c6  call    ?CleanupSystemHandles@LRPC_SYSTEM_HANDLE_DATA@@QEAAHK@Z; LRPC_SYSTEM_HANDLE_DATA::CleanupSystemHandles(ulong)
0x1800262cb  mov     eax, ebx
0x1800262cd  mov     rcx, [rbp+50h+var_30]
0x1800262d1  xor     rcx, rsp; StackCookie
0x1800262d4  call    __security_check_cookie
0x1800262d9  lea     r11, [rsp+150h+var_20]
0x1800262e1  mov     rbx, [r11+38h]
0x1800262e5  mov     rsi, [r11+40h]
0x1800262e9  mov     rsp, r11
0x1800262ec  pop     r15
0x1800262ee  pop     r14
0x1800262f0  pop     r12
0x1800262f2  pop     rdi
0x1800262f3  pop     rbp
0x1800262f4  retn
0x1800262f5  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1800262fb  test    eax, eax
0x1800262fd  jz      loc_1800261B2
0x180026303  mov     rax, [rdi]
0x180026306  lea     rdx, [rbp+50h+var_D0]
0x18002630a  mov     rcx, rdi
0x18002630d  mov     rax, [rax+108h]
0x180026314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026319  lea     rdx, [rbp+50h+var_C0]
0x18002631d  mov     ecx, 1
0x180026322  call    cs:__imp_EtwEventActivityIdControl
0x180026328  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x18002632e  test    eax, eax
0x180026330  jz      loc_1800261B2
0x180026336  mov     rax, cs:ActivityTransfer
0x18002633d  lea     r9, [rbp+50h+var_C0]
0x180026341  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle
0x180026348  lea     r8, [rbp+50h+var_D0]
0x18002634c  mov     qword ptr [rsp+150h+var_E8], rax
0x180026351  lea     rdx, [rsp+150h+var_E8]
0x180026356  mov     rax, 8000000000000001h
0x180026360  mov     dword ptr [rsp+150h+var_100], r15d
0x180026365  mov     qword ptr [rsp+150h+var_E8+8], rax
0x18002636a  mov     eax, cs:Microsoft_Windows_Networking_CorrelationTraceActivityPayload
0x180026370  test    eax, eax
0x180026372  jz      loc_180026516
0x180026378  lea     rax, Microsoft_Windows_Networking_ProviderId
0x18002637f  mov     [rbp+50h+var_48], 10h
0x180026387  mov     [rbp+50h+var_50], rax
0x18002638b  lea     rax, [rsp+150h+var_100]
0x180026390  mov     [rbp+50h+var_40], rax
0x180026394  lea     rax, [rbp+50h+var_50]
0x180026398  mov     [rsp+150h+var_128], rax
0x18002639d  mov     dword ptr [rsp+150h+var_130], 2
0x1800263a5  mov     [rbp+50h+var_38], 4
0x1800263ad  call    cs:__imp_EtwEventWriteTransfer
0x1800263b3  jmp     loc_1800261B2
0x1800263b8  mov     ecx, edx
0x1800263ba  mov     r9d, 6
0x1800263c0  mov     eax, r8d
0x1800263c3  lea     rdx, RPCLogEvent
0x1800263ca  or      rcx, rax
0x1800263cd  mov     [rsp+150h+var_100], rbx
0x1800263d2  mov     rax, [r14+88h]
0x1800263d9  mov     [rsp+150h+var_F8], rax
0x1800263de  lea     rax, [rsp+150h+var_110]
0x1800263e3  mov     [rbp+50h+var_A0], rax
0x1800263e7  lea     rax, [rsp+150h+var_108]
0x1800263ec  mov     [rbp+50h+var_90], rax
0x1800263f0  lea     rax, [rsp+150h+var_100]
0x1800263f5  mov     [rbp+50h+var_80], rax
0x1800263f9  lea     rax, [rsp+150h+var_F8]
0x1800263fe  mov     [rbp+50h+var_70], rax
0x180026402  lea     rax, [rsp+150h+var_E8]
0x180026407  mov     [rbp+50h+var_60], rax
0x18002640b  lea     rax, [rbp+50h+var_B0]
0x18002640f  mov     qword ptr [rsp+150h+var_E8], rcx
0x180026414  lea     rcx, RpcEtwGuid_Context
0x18002641b  mov     [rsp+150h+var_130], rax
0x180026420  mov     [rsp+150h+var_108], 4Bh ; 'K'
0x180026425  mov     [rsp+150h+var_110], 4Ch ; 'L'
0x18002642a  mov     [rbp+50h+var_98], 1
0x180026432  mov     [rbp+50h+var_88], 1
0x18002643a  mov     [rbp+50h+var_78], 8
0x180026442  mov     [rbp+50h+var_68], 8
0x18002644a  mov     [rbp+50h+var_58], 8
0x180026452  call    McGenEventWrite_EtwEventWriteTransfer
0x180026457  jmp     loc_180026214
0x18002645c  movsxd  rax, edx
0x18002645f  lea     rcx, RpcEtwGuid_Context
0x180026466  mov     [rsp+150h+var_100], rax
0x18002646b  lea     rdx, RPCLogEvent
0x180026472  lea     rax, [rsp+150h+var_108]
0x180026477  mov     [rsp+150h+var_F8], r8
0x18002647c  mov     [rbp+50h+var_A0], rax
0x180026480  mov     r9d, 6
0x180026486  lea     rax, [rsp+150h+var_110]
0x18002648b  mov     qword ptr [rsp+150h+var_E8], r14
0x180026490  mov     [rbp+50h+var_90], rax
0x180026494  lea     rax, [rsp+150h+var_E8]
0x180026499  mov     [rbp+50h+var_80], rax
0x18002649d  lea     rax, [rsp+150h+var_F8]
0x1800264a2  mov     [rbp+50h+var_70], rax
0x1800264a6  lea     rax, [rsp+150h+var_100]
0x1800264ab  mov     [rbp+50h+var_60], rax
0x1800264af  lea     rax, [rbp+50h+var_B0]
0x1800264b3  mov     [rsp+150h+var_130], rax
0x1800264b8  mov     [rsp+150h+var_110], 51h ; 'Q'
0x1800264bd  mov     [rsp+150h+var_108], 61h ; 'a'
0x1800264c2  mov     [rbp+50h+var_98], 1
0x1800264ca  mov     [rbp+50h+var_88], 1
0x1800264d2  mov     [rbp+50h+var_78], 8
0x1800264da  mov     [rbp+50h+var_68], 8
0x1800264e2  mov     [rbp+50h+var_58], 8
0x1800264ea  call    McGenEventWrite_EtwEventWriteTransfer
0x1800264ef  jmp     loc_1800262B2
0x1800264f4  lea     r9, [rdi+0D0h]; struct _GUID *
0x1800264fb  lea     r8, [rbp+50h+var_D0]; struct _GUID *
0x1800264ff  call    ?EtwEx_tidActivityInfoTransfer@@YAK_KPEBU_EVENT_DESCRIPTOR@@PEBU_GUID@@2E2K@Z; EtwEx_tidActivityInfoTransfer(unsigned __int64,_EVENT_DESCRIPTOR const *,_GUID const *,_GUID const *,uchar,_GUID const *,ulong)
0x180026504  jmp     loc_1800261B2
0x180026509  mov     rcx, r14; this
0x18002650c  call    ?MessageReceivedWithClosePending@LRPC_CASSOCIATION@@AEAAXXZ; LRPC_CASSOCIATION::MessageReceivedWithClosePending(void)
0x180026511  jmp     loc_1800262B2
0x180026516  mov     [rsp+150h+var_128], r15
0x18002651b  mov     dword ptr [rsp+150h+var_130], r15d
0x180026520  call    cs:__imp_EtwEventWriteTransfer
0x180026526  jmp     loc_1800261B2
0x18002652b  cmp     ebx, 0C0000037h
0x180026531  jg      loc_180026639
0x180026537  jz      short loc_180026545
0x180026539  cmp     ebx, 0C0000008h
0x18002653f  jnz     loc_18002665D
0x180026545  mov     esi, 6BFh
0x18002654a  cmp     cs:dword_1800F9624, r15d
0x180026551  mov     r14d, 3F2h
0x180026557  mov     dword ptr [rsp+150h+var_E8], 3
0x18002655f  mov     dword ptr [rsp+150h+var_E8+8], ebx
0x180026563  jz      short loc_180026584
0x180026565  mov     ecx, r15d
0x180026568  cmp     ecx, 4
0x18002656b  jnb     short loc_18002657B
0x18002656d  movsxd  rax, ecx
0x180026570  cmp     byte ptr [rax+r12], 49h ; 'I'
0x180026575  jz      short loc_180026584
0x180026577  inc     ecx
0x180026579  jmp     short loc_180026568
0x18002657b  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x180026582  jnz     short loc_1800265F2
0x180026584  mov     ecx, 1; unsigned int
0x180026589  call    ?AllocateExtendedErrorInfoRecord@@YAPEAUtagExtendedErrorInfo@@K@Z; AllocateExtendedErrorInfoRecord(ulong)
0x18002658e  mov     rbx, rax
0x180026591  test    rax, rax
0x180026594  jz      short loc_180026613
0x180026596  mov     rcx, rax; struct tagExtendedErrorInfo *
0x180026599  call    ?InitializePrivateEEInfo@@YAXPEAUtagExtendedErrorInfo@@@Z; InitializePrivateEEInfo(tagExtendedErrorInfo *)
0x18002659e  movups  xmm0, [rsp+150h+var_E8]
0x1800265a3  mov     rcx, rbx; struct tagExtendedErrorInfo *
0x1800265a6  mov     [rbx+38h], r14w
0x1800265ab  movsd   xmm1, [rsp+150h+var_D8]
0x1800265b1  mov     dword ptr [rbx+30h], 2
0x1800265b8  mov     [rbx+34h], esi
0x1800265bb  movups  xmmword ptr [rbx+40h], xmm0
0x1800265bf  movsd   qword ptr [rbx+50h], xmm1
0x1800265c4  call    ?AddPrivateRecord@@YAJPEAUtagExtendedErrorInfo@@@Z; AddPrivateRecord(tagExtendedErrorInfo *)
0x1800265c9  test    eax, eax
0x1800265cb  jnz     short loc_18002661F
0x1800265cd  mov     rax, [rdi]
0x1800265d0  mov     edx, esi
0x1800265d2  mov     rcx, rdi
0x1800265d5  mov     dword ptr [rdi+10Ch], 2
0x1800265df  mov     rax, [rax+158h]
0x1800265e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800265eb  mov     ebx, eax
0x1800265ed  jmp     loc_1800262BD
0x1800265f2  mov     edx, esi
0x1800265f4  mov     r9b, 2
0x1800265f7  mov     [rsp+150h+var_120], rbx
0x1800265fc  mov     r8b, 49h ; 'I'
0x1800265ff  mov     [rsp+150h+var_128], r14
0x180026604  mov     [rsp+150h+var_130], rdx
0x180026609  call    McTemplateU0uuxxx_EtwEventWriteTransfer
0x18002660e  jmp     loc_180026584
0x180026613  lea     rcx, [rsp+150h+var_E8]
0x180026618  call    FreeEEInfoPrivateParam
0x18002661d  jmp     short loc_1800265CD
0x18002661f  mov     rcx, rbx; lpMem
0x180026622  call    FreeEEInfoRecord
0x180026627  jmp     short loc_1800265CD
0x180026629  mov     r8d, r15d
0x18002662c  jmp     loc_1800261D4
0x180026631  mov     edx, r15d
0x180026634  jmp     loc_1800261E1
0x180026639  cmp     ebx, 0C0000701h
0x18002663f  jnz     short loc_18002669B
0x180026641  mov     eax, [rdi+120h]
0x180026647  mov     esi, 6BEh
0x18002664c  test    al, 1
0x18002664e  mov     eax, 71Ah
  ... truncated ...
```
