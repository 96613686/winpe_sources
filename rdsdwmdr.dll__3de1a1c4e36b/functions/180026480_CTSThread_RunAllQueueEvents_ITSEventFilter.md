# CTSThread::RunAllQueueEvents(ITSEventFilter *)

- ea: `0x180026480`
- end: `0x18002671a`
- name: `?RunAllQueueEvents@CTSThread@@MEAAJPEAVITSEventFilter@@@Z`
- size: `666`
- prototype: `__int64 __fastcall(CTSThread *__hidden this, struct ITSEventFilter *)`
- caller_count: `3`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180025d90`
- `0x180028298`
- `0x180028514`

## callees

- `0x18000f068`
- `0x18000f08c`
- `0x18001c9d0`
- `0x18001d114`
- `0x180022390`
- `0x180024e2c`
- `0x180024eb0`
- `0x180026234`
- `0x180026254`
- `0x180026480`
- `0x180026720`
- `0x180026b30`
- `0x18002a1c4`
- `0x18002b564`

## pseudocode

```c
__int64 __fastcall CTSThread::RunAllQueueEvents(CTSThread *this, struct ITSEventFilter *a2)
{
  struct ITSEventFilter *v2; // rbx
  int v4; // r14d
  CTSReaderWriterLock *v5; // rbx
  __int64 v6; // rdx
  int TickCount; // esi
  __int64 v8; // r8
  __int64 v9; // r9
  int ActivityIdPrefix; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  struct CTSMsg *v14; // rdi
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  int v18; // eax
  int v19; // eax
  int v20; // edx
  const char *v21; // rcx
  unsigned int v22; // r14d
  int v24; // [rsp+70h] [rbp+38h] BYREF
  int v25; // [rsp+78h] [rbp+40h] BYREF
  struct CTSMsg *v26; // [rsp+80h] [rbp+48h] BYREF
  struct ITSEventFilter *v27; // [rsp+88h] [rbp+50h] BYREF

  v2 = a2;
  v27 = 0;
  v24 = 0;
  v4 = 0;
  if ( a2 )
  {
    TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v27);
    v27 = v2;
    TCntPtr<ITSAsyncCallback>::SafeAddRef(&v27);
  }
  else
  {
    v5 = (CTSThread *)((char *)this + 164);
    CTSReaderWriterLock::ReadLock((CTSThread *)((char *)this + 164));
    CComPtrList<ITSEventFilter,ComPlainSmartPtr<ITSEventFilter>>::GetHeadNode((__int64)this + 200, &v27);
    CTSReaderWriterLock::ReadUnlock(v5);
    v2 = v27;
  }
  *((_DWORD *)this + 47) = 1;
  TickCount = PAL_System_TimeGetTickCount(&v24);
  if ( TickCount < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v6, v8, v9);
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        69,
        (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
        ActivityIdPrefix,
        (__int64)"PAL_System_TimeGetTickCount failed",
        TickCount);
    }
    goto LABEL_32;
  }
  v4 = v24;
  v25 = v24;
  while ( 1 )
  {
    v26 = 0;
    TickCount = CTSThread::GetItem(this, v2, &v26);
    if ( TickCount < 0 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_31;
      }
      v19 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v11, v12, v13);
      v20 = 70;
      v21 = "GetItem failed";
LABEL_30:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v20,
        (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
        v19,
        (__int64)v21,
        TickCount);
      goto LABEL_31;
    }
    v14 = v26;
    if ( !v26 )
    {
      TickCount = 0;
LABEL_31:
      TCntPtr<CTSThread>::SafeRelease(&v26, v11, v12, v13);
      goto LABEL_32;
    }
    TickCount = CTSThread::RunQueueEvent(this, v26);
    CTSMsg::Terminate((struct CTSMsg *)((char *)v14 + 16));
    if ( TickCount < 0 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_31;
      }
      v19 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v11, v12, v13);
      v20 = 71;
      v21 = "RunQueueEvent failed";
      goto LABEL_30;
    }
    TickCount = PAL_System_TimeGetTickCount(&v25);
    if ( TickCount < 0 )
      break;
    TCntPtr<CTSThread>::SafeRelease(&v26, v15, v16, v17);
    v4 = v25;
    if ( (unsigned int)(v25 - v24) >= 0x14 )
      goto LABEL_32;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v18 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v15, v16, v17);
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      72,
      (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
      v18,
      (__int64)"PAL_System_TimeGetTickCount failed",
      TickCount);
  }
  TCntPtr<CTSThread>::SafeRelease(&v26, v15, v16, v17);
  v4 = v25;
LABEL_32:
  v22 = v4 - v24;
  *((_DWORD *)this + 47) = 0;
  if ( v22 >= 0x14 )
    CTSThread::SignalEventQueue((__int64)this, v6, v8, v9);
  TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v27);
  return (unsigned int)TickCount;
}

```

## disassembly

```asm
0x180026480  push    rbp
0x180026482  push    rbx
0x180026483  push    rsi
0x180026484  push    rdi
0x180026485  push    r14
0x180026487  push    r15
0x180026489  mov     rbp, rsp
0x18002648c  sub     rsp, 38h
0x180026490  mov     rbx, rdx
0x180026493  mov     [rbp+arg_18], 0
0x18002649b  mov     r15, rcx
0x18002649e  mov     [rbp+arg_0], 0
0x1800264a5  xor     r14d, r14d
0x1800264a8  test    rdx, rdx
0x1800264ab  jz      short loc_1800264C5
0x1800264ad  lea     rcx, [rbp+arg_18]
0x1800264b1  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x1800264b6  lea     rcx, [rbp+arg_18]
0x1800264ba  mov     [rbp+arg_18], rbx
0x1800264be  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800264c3  jmp     short loc_1800264F0
0x1800264c5  lea     rbx, [rcx+0A4h]
0x1800264cc  mov     rcx, rbx; this
0x1800264cf  call    ?ReadLock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::ReadLock(void)
0x1800264d4  lea     rcx, [r15+0C8h]
0x1800264db  lea     rdx, [rbp+arg_18]
0x1800264df  call    ?GetHeadNode@?$CComPtrList@VITSEventFilter@@V?$ComPlainSmartPtr@VITSEventFilter@@@@@@QEBAHAEAV?$ComPlainSmartPtr@VITSEventFilter@@@@@Z; CComPtrList<ITSEventFilter,ComPlainSmartPtr<ITSEventFilter>>::GetHeadNode(ComPlainSmartPtr<ITSEventFilter> &)
0x1800264e4  mov     rcx, rbx; this
0x1800264e7  call    ?ReadUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::ReadUnlock(void)
0x1800264ec  mov     rbx, [rbp+arg_18]
0x1800264f0  lea     rcx, [rbp+arg_0]
0x1800264f4  mov     dword ptr [r15+0BCh], 1
0x1800264ff  call    PAL_System_TimeGetTickCount
0x180026504  mov     esi, eax
0x180026506  test    eax, eax
0x180026508  jns     short loc_18002656E
0x18002650a  mov     rcx, cs:WPP_GLOBAL_Control
0x180026511  lea     rax, WPP_GLOBAL_Control
0x180026518  cmp     rcx, rax
0x18002651b  jz      loc_1800266E5
0x180026521  test    byte ptr [rcx+1Ch], 8
0x180026525  jz      loc_1800266E5
0x18002652b  cmp     byte ptr [rcx+19h], 2
0x18002652f  jb      loc_1800266E5
0x180026535  call    RdpX_GetActivityIdPrefix
0x18002653a  lea     rcx, aPalSystemTimeg; "PAL_System_TimeGetTickCount failed"
0x180026541  mov     [rsp+38h+var_10], esi
0x180026545  mov     [rsp+38h+var_18], rcx
0x18002654a  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x180026551  mov     rcx, cs:WPP_GLOBAL_Control
0x180026558  mov     edx, 45h ; 'E'
0x18002655d  mov     r9d, eax
0x180026560  mov     rcx, [rcx+10h]
0x180026564  call    WPP_SF_DsD
0x180026569  jmp     loc_1800266E5
0x18002656e  mov     r14d, [rbp+arg_0]
0x180026572  mov     [rbp+arg_8], r14d
0x180026576  lea     r8, [rbp+arg_10]; struct CTSMsg **
0x18002657a  mov     [rbp+arg_10], 0
0x180026582  mov     rdx, rbx; struct ITSEventFilter *
0x180026585  mov     rcx, r15; this
0x180026588  call    ?GetItem@CTSThread@@AEAAJPEAVITSEventFilter@@PEAPEAVCTSMsg@@@Z; CTSThread::GetItem(ITSEventFilter *,CTSMsg * *)
0x18002658d  mov     esi, eax
0x18002658f  test    eax, eax
0x180026591  js      loc_180026689
0x180026597  mov     rdi, [rbp+arg_10]
0x18002659b  test    rdi, rdi
0x18002659e  jz      loc_180026685
0x1800265a4  mov     rdx, rdi; struct CTSMsg *
0x1800265a7  mov     rcx, r15; this
0x1800265aa  call    ?RunQueueEvent@CTSThread@@IEAAJPEAVCTSMsg@@@Z; CTSThread::RunQueueEvent(CTSMsg *)
0x1800265af  lea     rcx, [rdi+10h]; this
0x1800265b3  mov     esi, eax
0x1800265b5  call    ?Terminate@CTSMsg@@UEAAJXZ; CTSMsg::Terminate(void)
0x1800265ba  test    esi, esi
0x1800265bc  js      loc_180026653
0x1800265c2  lea     rcx, [rbp+arg_8]
0x1800265c6  call    PAL_System_TimeGetTickCount
0x1800265cb  mov     esi, eax
0x1800265cd  test    eax, eax
0x1800265cf  js      short loc_1800265EE
0x1800265d1  lea     rcx, [rbp+arg_10]
0x1800265d5  call    ?SafeRelease@?$TCntPtr@VCTSThread@@@@AEAAXXZ; TCntPtr<CTSThread>::SafeRelease(void)
0x1800265da  mov     r14d, [rbp+arg_8]
0x1800265de  mov     eax, r14d
0x1800265e1  sub     eax, [rbp+arg_0]
0x1800265e4  cmp     eax, 14h
0x1800265e7  jb      short loc_180026576
0x1800265e9  jmp     loc_1800266E5
0x1800265ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800265f5  lea     rax, WPP_GLOBAL_Control
0x1800265fc  cmp     rcx, rax
0x1800265ff  jz      short loc_180026641
0x180026601  test    byte ptr [rcx+1Ch], 8
0x180026605  jz      short loc_180026641
0x180026607  cmp     byte ptr [rcx+19h], 2
0x18002660b  jb      short loc_180026641
0x18002660d  call    RdpX_GetActivityIdPrefix
0x180026612  lea     rcx, aPalSystemTimeg; "PAL_System_TimeGetTickCount failed"
0x180026619  mov     [rsp+38h+var_10], esi
0x18002661d  mov     [rsp+38h+var_18], rcx
0x180026622  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x180026629  mov     rcx, cs:WPP_GLOBAL_Control
0x180026630  mov     edx, 48h ; 'H'
0x180026635  mov     r9d, eax
0x180026638  mov     rcx, [rcx+10h]
0x18002663c  call    WPP_SF_DsD
0x180026641  lea     rcx, [rbp+arg_10]
0x180026645  call    ?SafeRelease@?$TCntPtr@VCTSThread@@@@AEAAXXZ; TCntPtr<CTSThread>::SafeRelease(void)
0x18002664a  mov     r14d, [rbp+arg_8]
0x18002664e  jmp     loc_1800266E5
0x180026653  mov     rcx, cs:WPP_GLOBAL_Control
0x18002665a  lea     rax, WPP_GLOBAL_Control
0x180026661  cmp     rcx, rax
0x180026664  jz      short loc_1800266DC
0x180026666  test    byte ptr [rcx+1Ch], 8
0x18002666a  jz      short loc_1800266DC
0x18002666c  cmp     byte ptr [rcx+19h], 2
0x180026670  jb      short loc_1800266DC
0x180026672  call    RdpX_GetActivityIdPrefix
0x180026677  mov     edx, 47h ; 'G'
0x18002667c  lea     rcx, aRunqueueeventF; "RunQueueEvent failed"
0x180026683  jmp     short loc_1800266B9
0x180026685  xor     esi, esi
0x180026687  jmp     short loc_1800266DC
0x180026689  mov     rcx, cs:WPP_GLOBAL_Control
0x180026690  lea     rax, WPP_GLOBAL_Control
0x180026697  cmp     rcx, rax
0x18002669a  jz      short loc_1800266DC
0x18002669c  test    byte ptr [rcx+1Ch], 8
0x1800266a0  jz      short loc_1800266DC
0x1800266a2  cmp     byte ptr [rcx+19h], 2
0x1800266a6  jb      short loc_1800266DC
0x1800266a8  call    RdpX_GetActivityIdPrefix
0x1800266ad  mov     edx, 46h ; 'F'
0x1800266b2  lea     rcx, aGetitemFailed; "GetItem failed"
0x1800266b9  mov     [rsp+38h+var_10], esi
0x1800266bd  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x1800266c4  mov     [rsp+38h+var_18], rcx
0x1800266c9  mov     r9d, eax
0x1800266cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800266d3  mov     rcx, [rcx+10h]
0x1800266d7  call    WPP_SF_DsD
0x1800266dc  lea     rcx, [rbp+arg_10]
0x1800266e0  call    ?SafeRelease@?$TCntPtr@VCTSThread@@@@AEAAXXZ; TCntPtr<CTSThread>::SafeRelease(void)
0x1800266e5  sub     r14d, [rbp+arg_0]
0x1800266e9  mov     dword ptr [r15+0BCh], 0
0x1800266f4  cmp     r14d, 14h
0x1800266f8  jb      short loc_180026702
0x1800266fa  mov     rcx, r15; this
0x1800266fd  call    ?SignalEventQueue@CTSThread@@MEAAJXZ; CTSThread::SignalEventQueue(void)
0x180026702  lea     rcx, [rbp+arg_18]
0x180026706  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x18002670b  mov     eax, esi
0x18002670d  add     rsp, 38h
0x180026711  pop     r15
0x180026713  pop     r14
0x180026715  pop     rdi
0x180026716  pop     rsi
0x180026717  pop     rbx
0x180026718  pop     rbp
0x180026719  retn
```
