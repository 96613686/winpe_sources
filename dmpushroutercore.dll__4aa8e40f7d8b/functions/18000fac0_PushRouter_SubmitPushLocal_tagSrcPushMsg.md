# PushRouter_SubmitPushLocal(tagSrcPushMsg *)

- ea: `0x18000fac0`
- end: `0x180010058`
- name: `?PushRouter_SubmitPushLocal@@YAJPEAUtagSrcPushMsg@@@Z`
- size: `1432`
- prototype: `__int64 __fastcall(struct tagSrcPushMsg *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800107b0`

## callees

- `0x18000113c`
- `0x180001258`
- `0x1800039f0`
- `0x18000dc6c`
- `0x18000f694`
- `0x18000fac0`
- `0x1800103f8`
- `0x1800127c4`
- `0x180013528`
- `0x1800174e4`
- `0x18001ba3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fb5a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001001c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fb5a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001001c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fb03`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fbc3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fb03`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fbc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010026`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010030`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010026`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010030`
- `DMCmnUtils!CopyString` at `0x18000fd79`
- `DMCmnUtils!CopyString` at `0x18000fef9`
- `DMCmnUtils!CopyString` at `0x18000fd79`
- `DMCmnUtils!CopyString` at `0x18000fef9`
- `DMCmnUtils!InvStrCmpNIW` at `0x18000fd2e`
- `DMCmnUtils!InvStrCmpNIW` at `0x18000feae`
- `DMCmnUtils!InvStrCmpNIW` at `0x18000fd2e`
- `DMCmnUtils!InvStrCmpNIW` at `0x18000feae`

## pseudocode

```c
__int64 __fastcall PushRouter_SubmitPushLocal(struct tagSrcPushMsg *a1)
{
  HLOCAL v1; // r12
  signed int started; // eax
  __int64 v4; // r8
  signed int v5; // ebx
  __int64 v6; // r8
  int v7; // ebx
  __int64 v8; // r8
  PushRouter *v9; // rcx
  unsigned __int16 *v10; // rdi
  const unsigned __int16 *v11; // rax
  __int64 v12; // rdx
  signed int v13; // esi
  unsigned __int64 v14; // r14
  __int64 v15; // rdx
  unsigned __int16 *v16; // rax
  const unsigned __int16 *v17; // r12
  unsigned __int16 *v18; // rcx
  int v19; // r8d
  unsigned __int16 v20; // ax
  int v21; // eax
  unsigned __int16 *v22; // r14
  const unsigned __int16 *v23; // rax
  __int64 v24; // rdx
  int v25; // r9d
  __int64 v26; // rcx
  signed int v27; // edi
  unsigned __int16 *v28; // rax
  const unsigned __int16 *v29; // r13
  int EndOfHeader; // eax
  unsigned __int16 *v31; // r12
  unsigned __int16 *v32; // rcx
  int v33; // r8d
  unsigned __int16 v34; // ax
  int v35; // eax
  int v36; // eax
  unsigned int v38; // [rsp+40h] [rbp-59h] BYREF
  unsigned int v39; // [rsp+48h] [rbp-51h] BYREF
  unsigned int v40; // [rsp+4Ch] [rbp-4Dh] BYREF
  unsigned __int16 *v41; // [rsp+50h] [rbp-49h] BYREF
  unsigned __int16 *v42; // [rsp+58h] [rbp-41h] BYREF
  unsigned __int16 *v43; // [rsp+60h] [rbp-39h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-31h] BYREF
  HLOCAL v45; // [rsp+70h] [rbp-29h] BYREF
  int v46; // [rsp+78h] [rbp-21h]
  unsigned int *v47; // [rsp+90h] [rbp-9h]
  __int64 v48; // [rsp+98h] [rbp-1h]

  v1 = 0;
  v46 = 0;
  hMem = 0;
  v45 = 0;
  EnterCriticalSection(&g_csPushRouter);
  started = DmSvcSetServiceStartType();
  v5 = started;
  if ( started < 0 && (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 1) != 0 )
  {
    v38 = started;
    v48 = 4;
    v47 = &v38;
    McGenEventWrite_EventWriteTransfer(
      MDM_PUSHROUTER_Context,
      PushRouterChangingPushRouterToAutoStartupTypeFailed,
      v4,
      2);
  }
  LeaveCriticalSection(&g_csPushRouter);
  if ( v5 < 0 && (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 1) != 0 )
  {
    v38 = v5;
    v47 = &v38;
    v48 = 4;
    McGenEventWrite_EventWriteTransfer(MDM_PUSHROUTER_Context, PushRouterDemandStartingPushRouterFailed, v6, 2);
  }
  if ( !a1 )
    goto LABEL_8;
  if ( *(_DWORD *)a1 != 56 )
  {
    v7 = -2147024809;
    goto LABEL_17;
  }
  if ( *((_QWORD *)a1 + 1) && *((_QWORD *)a1 + 2) )
  {
    EnterCriticalSection(&g_csPushRouter);
    v46 = 1;
    if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 2) != 0 )
    {
      v38 = *((_DWORD *)a1 + 7);
      v48 = 4;
      v47 = &v38;
      McGenEventWrite_EventWriteTransfer(
        MDM_PUSHROUTER_Context,
        PushRouterPushRouterSubmitPushCallReceivedFromLocalCaller,
        v8,
        2);
    }
    v7 = EnsurePushRouterCreated();
    if ( v7 >= 0 )
      v7 = PushRouter::SubmitPush(v9, a1);
  }
  else
  {
LABEL_8:
    v7 = -2147467261;
  }
LABEL_17:
  v10 = (unsigned __int16 *)*((_QWORD *)a1 + 1);
  v11 = L"Content-Type";
  v42 = v10;
  v41 = v10;
  v12 = 0x7FFFFFFF;
  v39 = 0;
  hMem = 0;
  do
  {
    if ( !*v11 )
      break;
    ++v11;
    --v12;
  }
  while ( v12 );
  v13 = v12 == 0 ? 0x80070057 : 0;
  v14 = (0x7FFFFFFF - v12) & -(__int64)(v12 != 0);
  if ( v12 && v10 )
  {
    v15 = 0x7FFFFFFF;
    v16 = v10;
    do
    {
      if ( !*v16 )
        break;
      ++v16;
      --v15;
    }
    while ( v15 );
    v13 = v15 == 0 ? 0x80070057 : 0;
    v6 = (0x7FFFFFFF - v15) & -(__int64)(v15 != 0);
    if ( v15 )
    {
      v17 = &v10[v6];
      while ( (unsigned int)FindEndOfHeader((const unsigned __int16 **)&v42, v17, &v39) )
      {
        v18 = v10;
        v19 = 0;
        if ( v39 )
        {
          while ( 1 )
          {
            v20 = *v18++;
            if ( v20 == 58 )
              break;
            if ( ++v19 >= v39 )
              goto LABEL_34;
          }
          v43 = v18;
          v40 = v18 - v10 - 1;
          v38 = v39 - v40;
          if ( (unsigned int)Trim((const unsigned __int16 **)&v41, &v40) )
          {
            if ( v40 == v14 && !InvStrCmpNIW(v41, L"Content-Type", v14) )
            {
              v21 = Trim((const unsigned __int16 **)&v43, &v38);
              v13 = CopyString(v43, v21 != 0 ? v38 : 0, (unsigned __int16 **)&hMem);
              break;
            }
          }
        }
LABEL_34:
        v10 = v42;
        v41 = v42;
      }
      v1 = 0;
    }
  }
  v22 = (unsigned __int16 *)*((_QWORD *)a1 + 1);
  v23 = L"X-Wap-Application-Id";
  v41 = v22;
  v24 = 0x7FFFFFFF;
  v42 = v22;
  v25 = 0;
  v39 = 0;
  v45 = 0;
  do
  {
    if ( !*v23 )
      break;
    ++v23;
    --v24;
  }
  while ( v24 );
  LODWORD(v26) = 0x7FFFFFFF - v24;
  v27 = v24 == 0 ? 0x80070057 : 0;
  v43 = (unsigned __int16 *)((0x7FFFFFFF - v24) & -(__int64)(v24 != 0));
  if ( v24 && v22 )
  {
    v26 = 0x7FFFFFFF;
    v28 = v22;
    do
    {
      if ( !*v28 )
        break;
      ++v28;
      --v26;
    }
    while ( v26 );
    v27 = v26 == 0 ? 0x80070057 : 0;
    if ( v26 )
    {
      v29 = &v22[(0x7FFFFFFF - v26) & ((unsigned __int128)-(__int128)(unsigned __int64)v26 >> 64)];
      EndOfHeader = FindEndOfHeader((const unsigned __int16 **)&v41, v29, &v39);
      v25 = 0;
      if ( EndOfHeader )
      {
        v31 = v43;
        while ( 1 )
        {
          v32 = v22;
          v33 = 0;
          if ( v39 )
          {
            while ( 1 )
            {
              v34 = *v32++;
              if ( v34 == 58 )
                break;
              if ( ++v33 >= v39 )
                goto LABEL_57;
            }
            v43 = v32;
            v38 = v32 - v22 - 1;
            v40 = v39 - v38;
            if ( (unsigned int)Trim((const unsigned __int16 **)&v42, &v38) )
            {
              if ( (unsigned __int16 *)v38 == v31 && !InvStrCmpNIW(v42, L"X-Wap-Application-Id", (unsigned __int64)v31) )
                break;
            }
          }
LABEL_57:
          v22 = v41;
          v42 = v41;
          v35 = FindEndOfHeader((const unsigned __int16 **)&v41, v29, &v39);
          v25 = 0;
          if ( !v35 )
            goto LABEL_60;
        }
        v36 = Trim((const unsigned __int16 **)&v43, &v40);
        v27 = CopyString(v43, v36 != 0 ? v40 : 0, (unsigned __int16 **)&v45);
LABEL_60:
        v1 = v45;
      }
    }
  }
  if ( v13 >= 0 && v27 >= 0 )
  {
    if ( v7 >= 0 )
    {
      if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 2) != 0 )
        McTemplateU0zzzd_EventWriteTransfer(
          v26,
          (unsigned int)PushRouterPushRouterSubmitPushCallReceivedFromLocalCallerSucceeded,
          *((_QWORD *)a1 + 4),
          (_DWORD)hMem,
          (__int64)v1,
          v7);
      if ( (unsigned int)dword_180050060 > 4 )
      {
        v43 = (unsigned __int16 *)v45;
        v42 = (unsigned __int16 *)hMem;
        v41 = (unsigned __int16 *)*((_QWORD *)a1 + 4);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v26,
          (unsigned int)byte_1800463E9,
          v6,
          v25,
          (__int64)&v41,
          (__int64)&v42,
          (__int64)&v43);
      }
    }
    else
    {
      if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 1) != 0 )
        McTemplateU0zzzd_EventWriteTransfer(
          v26,
          (unsigned int)PushRouterPushRouterSubmitPushCallReceivedFromLocalCallerFailed,
          *((_QWORD *)a1 + 4),
          (_DWORD)hMem,
          (__int64)v1,
          v7);
      if ( (unsigned int)dword_180050060 > 2 )
      {
        v43 = (unsigned __int16 *)v45;
        v42 = (unsigned __int16 *)hMem;
        v41 = (unsigned __int16 *)*((_QWORD *)a1 + 4);
        v38 = v7;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v26,
          (unsigned int)&byte_180046437,
          v6,
          v25,
          (__int64)&v38,
          (__int64)&v41,
          (__int64)&v42,
          (__int64)&v43);
      }
    }
  }
  if ( v46 )
    LeaveCriticalSection(&g_csPushRouter);
  LocalFree(hMem);
  LocalFree(v45);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000fac0  push    rbp
0x18000fac2  push    rbx
0x18000fac3  push    rsi
0x18000fac4  push    rdi
0x18000fac5  push    r12
0x18000fac7  push    r13
0x18000fac9  push    r14
0x18000facb  push    r15
0x18000facd  lea     rbp, [rsp-1Fh]
0x18000fad2  sub     rsp, 0B8h
0x18000fad9  mov     rax, cs:__security_cookie
0x18000fae0  xor     rax, rsp
0x18000fae3  mov     [rbp+57h+var_50], rax
0x18000fae7  xor     r12d, r12d
0x18000faea  lea     r14, ?g_csPushRouter@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csPushRouter
0x18000faf1  mov     r15, rcx
0x18000faf4  mov     [rbp+57h+var_78], r12d
0x18000faf8  mov     rcx, r14; lpCriticalSection
0x18000fafb  mov     [rbp+57h+hMem], r12
0x18000faff  mov     [rbp+57h+var_80], r12
0x18000fb03  call    cs:__imp_EnterCriticalSection
0x18000fb09  call    DmSvcSetServiceStartType
0x18000fb0e  lea     esi, [r12+2]
0x18000fb13  mov     ebx, eax
0x18000fb15  lea     rdi, MDM_PUSHROUTER_Context
0x18000fb1c  test    eax, eax
0x18000fb1e  jns     short loc_18000FB57
0x18000fb20  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 1
0x18000fb27  jz      short loc_18000FB57
0x18000fb29  mov     [rbp+57h+var_B0], eax
0x18000fb2c  lea     rdx, PushRouterChangingPushRouterToAutoStartupTypeFailed
0x18000fb33  lea     rax, [rbp+57h+var_B0]
0x18000fb37  mov     [rbp+57h+var_58], 4
0x18000fb3f  mov     [rbp+57h+var_60], rax
0x18000fb43  mov     r9d, esi
0x18000fb46  lea     rax, [rbp+57h+var_70]
0x18000fb4a  mov     rcx, rdi
0x18000fb4d  mov     [rsp+0F0h+var_D0], rax
0x18000fb52  call    McGenEventWrite_EventWriteTransfer
0x18000fb57  mov     rcx, r14; lpCriticalSection
0x18000fb5a  call    cs:__imp_LeaveCriticalSection
0x18000fb60  test    ebx, ebx
0x18000fb62  jns     short loc_18000FB9B
0x18000fb64  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 1
0x18000fb6b  jz      short loc_18000FB9B
0x18000fb6d  lea     rax, [rbp+57h+var_B0]
0x18000fb71  mov     [rbp+57h+var_B0], ebx
0x18000fb74  mov     [rbp+57h+var_60], rax
0x18000fb78  lea     rdx, PushRouterDemandStartingPushRouterFailed
0x18000fb7f  lea     rax, [rbp+57h+var_70]
0x18000fb83  mov     [rbp+57h+var_58], 4
0x18000fb8b  mov     r9d, esi
0x18000fb8e  mov     [rsp+0F0h+var_D0], rax
0x18000fb93  mov     rcx, rdi
0x18000fb96  call    McGenEventWrite_EventWriteTransfer
0x18000fb9b  test    r15, r15
0x18000fb9e  jnz     short loc_18000FBA7
0x18000fba0  mov     ebx, 80004003h
0x18000fba5  jmp     short loc_18000FC20
0x18000fba7  cmp     dword ptr [r15], 38h ; '8'
0x18000fbab  jz      short loc_18000FBB4
0x18000fbad  mov     ebx, 80070057h
0x18000fbb2  jmp     short loc_18000FC20
0x18000fbb4  cmp     [r15+8], r12
0x18000fbb8  jz      short loc_18000FBA0
0x18000fbba  cmp     [r15+10h], r12
0x18000fbbe  jz      short loc_18000FBA0
0x18000fbc0  mov     rcx, r14; lpCriticalSection
0x18000fbc3  call    cs:__imp_EnterCriticalSection
0x18000fbc9  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, sil
0x18000fbd0  mov     [rbp+57h+var_78], 1
0x18000fbd7  jz      short loc_18000FC0B
0x18000fbd9  mov     eax, [r15+1Ch]
0x18000fbdd  lea     rdx, PushRouterPushRouterSubmitPushCallReceivedFromLocalCaller
0x18000fbe4  mov     [rbp+57h+var_B0], eax
0x18000fbe7  mov     r9d, esi
0x18000fbea  lea     rax, [rbp+57h+var_B0]
0x18000fbee  mov     [rbp+57h+var_58], 4
0x18000fbf6  mov     [rbp+57h+var_60], rax
0x18000fbfa  mov     rcx, rdi
0x18000fbfd  lea     rax, [rbp+57h+var_70]
0x18000fc01  mov     [rsp+0F0h+var_D0], rax
0x18000fc06  call    McGenEventWrite_EventWriteTransfer
0x18000fc0b  call    ?EnsurePushRouterCreated@@YAJXZ; EnsurePushRouterCreated(void)
0x18000fc10  mov     ebx, eax
0x18000fc12  test    eax, eax
0x18000fc14  js      short loc_18000FC20
0x18000fc16  mov     rdx, r15; struct tagSrcPushMsg *
0x18000fc19  call    ?SubmitPush@PushRouter@@QEAAJPEAUtagSrcPushMsg@@@Z; PushRouter::SubmitPush(tagSrcPushMsg *)
0x18000fc1e  mov     ebx, eax
0x18000fc20  mov     rdi, [r15+8]
0x18000fc24  lea     rax, aContentType; "Content-Type"
0x18000fc2b  mov     r13d, 7FFFFFFFh
0x18000fc31  mov     [rbp+57h+var_98], rdi
0x18000fc35  mov     [rbp+57h+var_A0], rdi
0x18000fc39  mov     edx, r13d
0x18000fc3c  mov     [rbp+57h+var_A8], r12d
0x18000fc40  mov     [rbp+57h+hMem], r12
0x18000fc44  cmp     [rax], r12w
0x18000fc48  jz      short loc_18000FC53
0x18000fc4a  add     rax, rsi
0x18000fc4d  sub     rdx, 1
0x18000fc51  jnz     short loc_18000FC44
0x18000fc53  mov     rax, rdx
0x18000fc56  mov     rcx, r13
0x18000fc59  neg     rax
0x18000fc5c  mov     rax, rdx
0x18000fc5f  sbb     esi, esi
0x18000fc61  sub     rcx, rdx
0x18000fc64  not     esi
0x18000fc66  and     esi, 80070057h
0x18000fc6c  neg     rax
0x18000fc6f  sbb     r14, r14
0x18000fc72  and     r14, rcx
0x18000fc75  test    rdx, rdx
0x18000fc78  jz      loc_18000FD84
0x18000fc7e  test    rdi, rdi
0x18000fc81  jz      loc_18000FD84
0x18000fc87  mov     rdx, r13
0x18000fc8a  mov     rax, rdi
0x18000fc8d  cmp     [rax], r12w
0x18000fc91  jz      short loc_18000FC9D
0x18000fc93  add     rax, 2
0x18000fc97  sub     rdx, 1
0x18000fc9b  jnz     short loc_18000FC8D
0x18000fc9d  mov     rax, rdx
0x18000fca0  mov     rcx, r13
0x18000fca3  neg     rax
0x18000fca6  mov     rax, rdx
0x18000fca9  sbb     esi, esi
0x18000fcab  sub     rcx, rdx
0x18000fcae  not     esi
0x18000fcb0  and     esi, 80070057h
0x18000fcb6  neg     rax
0x18000fcb9  sbb     r8, r8
0x18000fcbc  and     r8, rcx
0x18000fcbf  test    rdx, rdx
0x18000fcc2  jz      loc_18000FD84
0x18000fcc8  lea     r12, [rdi+r8*2]
0x18000fccc  jmp     short loc_18000FD40
0x18000fcce  mov     edx, [rbp+57h+var_A8]
0x18000fcd1  mov     rcx, rdi
0x18000fcd4  mov     r8d, r9d
0x18000fcd7  test    edx, edx
0x18000fcd9  jz      short loc_18000FD38
0x18000fcdb  movzx   eax, word ptr [rcx]
0x18000fcde  add     rcx, 2
0x18000fce2  cmp     ax, 3Ah ; ':'
0x18000fce6  jz      short loc_18000FCF2
0x18000fce8  inc     r8d
0x18000fceb  cmp     r8d, edx
0x18000fcee  jb      short loc_18000FCDB
0x18000fcf0  jmp     short loc_18000FD38
0x18000fcf2  mov     [rbp+57h+var_90], rcx
0x18000fcf6  sub     rcx, rdi
0x18000fcf9  sar     rcx, 1
0x18000fcfc  lea     eax, [rcx-1]
0x18000fcff  sub     edx, eax
0x18000fd01  mov     [rbp+57h+var_A4], eax
0x18000fd04  mov     [rbp+57h+var_B0], edx
0x18000fd07  lea     rcx, [rbp+57h+var_A0]; unsigned __int16 **
0x18000fd0b  lea     rdx, [rbp+57h+var_A4]; unsigned int *
0x18000fd0f  call    ?Trim@@YAHPEAPEBGPEAK@Z; Trim(ushort const * *,ulong *)
0x18000fd14  test    eax, eax
0x18000fd16  jz      short loc_18000FD38
0x18000fd18  mov     eax, [rbp+57h+var_A4]
0x18000fd1b  cmp     rax, r14
0x18000fd1e  jnz     short loc_18000FD38
0x18000fd20  mov     rcx, [rbp+57h+var_A0]
0x18000fd24  lea     rdx, aContentType; "Content-Type"
0x18000fd2b  mov     r8, r14
0x18000fd2e  call    cs:__imp_?InvStrCmpNIW@@YAHPEBG0_K@Z; InvStrCmpNIW(ushort const *,ushort const *,unsigned __int64)
0x18000fd34  test    eax, eax
0x18000fd36  jz      short loc_18000FD5D
0x18000fd38  mov     rdi, [rbp+57h+var_98]
0x18000fd3c  mov     [rbp+57h+var_A0], rdi
0x18000fd40  lea     r8, [rbp+57h+var_A8]; unsigned int *
0x18000fd44  mov     rdx, r12; unsigned __int16 *
0x18000fd47  lea     rcx, [rbp+57h+var_98]; unsigned __int16 **
0x18000fd4b  call    ?FindEndOfHeader@@YAHPEAPEBGPEBGPEAK@Z; FindEndOfHeader(ushort const * *,ushort const *,ulong *)
0x18000fd50  xor     r9d, r9d
0x18000fd53  test    eax, eax
0x18000fd55  jnz     loc_18000FCCE
0x18000fd5b  jmp     short loc_18000FD81
0x18000fd5d  lea     rdx, [rbp+57h+var_B0]; unsigned int *
0x18000fd61  lea     rcx, [rbp+57h+var_90]; unsigned __int16 **
0x18000fd65  call    ?Trim@@YAHPEAPEBGPEAK@Z; Trim(ushort const * *,ulong *)
0x18000fd6a  mov     rcx, [rbp+57h+var_90]
0x18000fd6e  lea     r8, [rbp+57h+hMem]
0x18000fd72  neg     eax
0x18000fd74  sbb     edx, edx
0x18000fd76  and     edx, [rbp+57h+var_B0]
0x18000fd79  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18000fd7f  mov     esi, eax
0x18000fd81  xor     r12d, r12d
0x18000fd84  mov     r14, [r15+8]
0x18000fd88  lea     rax, ?c_szAppIdHeader@@3QBGB; "X-Wap-Application-Id"
0x18000fd8f  mov     [rbp+57h+var_A0], r14
0x18000fd93  mov     rdx, r13
0x18000fd96  mov     [rbp+57h+var_98], r14
0x18000fd9a  xor     r9d, r9d
0x18000fd9d  mov     [rbp+57h+var_A8], r12d
0x18000fda1  mov     [rbp+57h+var_80], r12
0x18000fda5  cmp     [rax], r9w
0x18000fda9  jz      short loc_18000FDB5
0x18000fdab  add     rax, 2
0x18000fdaf  sub     rdx, 1
0x18000fdb3  jnz     short loc_18000FDA5
0x18000fdb5  mov     rax, rdx
0x18000fdb8  mov     rcx, r13
0x18000fdbb  neg     rax
0x18000fdbe  mov     rax, rdx
0x18000fdc1  sbb     edi, edi
0x18000fdc3  sub     rcx, rdx
0x18000fdc6  not     edi
0x18000fdc8  and     edi, 80070057h
0x18000fdce  neg     rax
0x18000fdd1  sbb     rax, rax
0x18000fdd4  and     rax, rcx
0x18000fdd7  mov     [rbp+57h+var_90], rax
0x18000fddb  test    rdx, rdx
0x18000fdde  jz      loc_18000FF05
0x18000fde4  test    r14, r14
0x18000fde7  jz      loc_18000FF05
0x18000fded  mov     rcx, r13
0x18000fdf0  mov     rax, r14
0x18000fdf3  cmp     [rax], r9w
0x18000fdf7  jz      short loc_18000FE03
0x18000fdf9  add     rax, 2
0x18000fdfd  sub     rcx, 1
0x18000fe01  jnz     short loc_18000FDF3
0x18000fe03  mov     rax, rcx
0x18000fe06  neg     rax
0x18000fe09  mov     rax, rcx
0x18000fe0c  sbb     edi, edi
0x18000fe0e  sub     r13, rcx
0x18000fe11  not     edi
0x18000fe13  and     edi, 80070057h
0x18000fe19  neg     rax
0x18000fe1c  sbb     rdx, rdx
0x18000fe1f  and     rdx, r13
0x18000fe22  test    rcx, rcx
0x18000fe25  jz      loc_18000FF05
0x18000fe2b  lea     r13, [r14+rdx*2]
0x18000fe2f  mov     rdx, r13; unsigned __int16 *
0x18000fe32  lea     r8, [rbp+57h+var_A8]; unsigned int *
0x18000fe36  lea     rcx, [rbp+57h+var_A0]; unsigned __int16 **
0x18000fe3a  call    ?FindEndOfHeader@@YAHPEAPEBGPEBGPEAK@Z; FindEndOfHeader(ushort const * *,ushort const *,ulong *)
0x18000fe3f  xor     r9d, r9d
0x18000fe42  test    eax, eax
0x18000fe44  jz      loc_18000FF05
0x18000fe4a  mov     r12, [rbp+57h+var_90]
0x18000fe4e  mov     edx, [rbp+57h+var_A8]
0x18000fe51  mov     rcx, r14
0x18000fe54  mov     r8d, r9d
0x18000fe57  test    edx, edx
0x18000fe59  jz      short loc_18000FEB8
0x18000fe5b  movzx   eax, word ptr [rcx]
0x18000fe5e  add     rcx, 2
0x18000fe62  cmp     ax, 3Ah ; ':'
0x18000fe66  jz      short loc_18000FE72
0x18000fe68  inc     r8d
0x18000fe6b  cmp     r8d, edx
0x18000fe6e  jb      short loc_18000FE5B
0x18000fe70  jmp     short loc_18000FEB8
0x18000fe72  mov     [rbp+57h+var_90], rcx
0x18000fe76  sub     rcx, r14
0x18000fe79  sar     rcx, 1
0x18000fe7c  lea     eax, [rcx-1]
0x18000fe7f  sub     edx, eax
0x18000fe81  mov     [rbp+57h+var_B0], eax
0x18000fe84  mov     [rbp+57h+var_A4], edx
0x18000fe87  lea     rcx, [rbp+57h+var_98]; unsigned __int16 **
0x18000fe8b  lea     rdx, [rbp+57h+var_B0]; unsigned int *
0x18000fe8f  call    ?Trim@@YAHPEAPEBGPEAK@Z; Trim(ushort const * *,ulong *)
0x18000fe94  test    eax, eax
0x18000fe96  jz      short loc_18000FEB8
0x18000fe98  mov     eax, [rbp+57h+var_B0]
0x18000fe9b  cmp     rax, r12
0x18000fe9e  jnz     short loc_18000FEB8
0x18000fea0  mov     rcx, [rbp+57h+var_98]
0x18000fea4  lea     rdx, ?c_szAppIdHeader@@3QBGB; "X-Wap-Application-Id"
0x18000feab  mov     r8, r12
0x18000feae  call    cs:__imp_?InvStrCmpNIW@@YAHPEBG0_K@Z; InvStrCmpNIW(ushort const *,ushort const *,unsigned __int64)
0x18000feb4  test    eax, eax
0x18000feb6  jz      short loc_18000FEDD
0x18000feb8  mov     r14, [rbp+57h+var_A0]
0x18000febc  lea     r8, [rbp+57h+var_A8]; unsigned int *
0x18000fec0  mov     rdx, r13; unsigned __int16 *
0x18000fec3  mov     [rbp+57h+var_98], r14
0x18000fec7  lea     rcx, [rbp+57h+var_A0]; unsigned __int16 **
0x18000fecb  call    ?FindEndOfHeader@@YAHPEAPEBGPEBGPEAK@Z; FindEndOfHeader(ushort const * *,ushort const *,ulong *)
0x18000fed0  xor     r9d, r9d
0x18000fed3  test    eax, eax
0x18000fed5  jnz     loc_18000FE4E
0x18000fedb  jmp     short loc_18000FF01
0x18000fedd  lea     rdx, [rbp+57h+var_A4]; unsigned int *
0x18000fee1  lea     rcx, [rbp+57h+var_90]; unsigned __int16 **
0x18000fee5  call    ?Trim@@YAHPEAPEBGPEAK@Z; Trim(ushort const * *,ulong *)
0x18000feea  mov     rcx, [rbp+57h+var_90]
  ... truncated ...
```
