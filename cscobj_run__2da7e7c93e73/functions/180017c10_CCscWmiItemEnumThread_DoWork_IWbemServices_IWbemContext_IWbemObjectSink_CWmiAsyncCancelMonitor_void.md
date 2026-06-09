# CCscWmiItemEnumThread::_DoWork(IWbemServices *,IWbemContext *,IWbemObjectSink *,CWmiAsyncCancelMonitor *,void *)

- ea: `0x180017c10`
- end: `0x180017ea5`
- name: `?_DoWork@CCscWmiItemEnumThread@@EEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemObjectSink@@PEAVCWmiAsyncCancelMonitor@@PEAX@Z`
- size: `661`
- prototype: `int(CCscWmiItemEnumThread *__hidden this, struct IWbemServices *, struct IWbemContext *, struct IWbemObjectSink *, struct CWmiAsyncCancelMonitor *, void *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000f5cc`
- `0x1800161b8`
- `0x180016280`
- `0x1800162b4`
- `0x1800170bc`
- `0x1800173c0`
- `0x180017c10`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180017c69`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180017ca9`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180017c69`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180017ca9`

## pseudocode

```c
__int64 __fastcall CCscWmiItemEnumThread::_DoWork(
        CCscWmiItemEnumThread *this,
        struct IWbemServices *a2,
        struct IWbemContext *a3,
        struct IWbemObjectSink *a4,
        struct CWmiAsyncCancelMonitor *a5,
        struct IWbemObjectSink *a6)
{
  HRESULT InterfaceAndReleaseStream; // ebx
  CWmiAsyncCancelMonitor *v10; // r15
  int v11; // eax
  CCscControlWmiEnum *v12; // r14
  CRefCounted *v13; // rsi
  unsigned int v14; // r13d
  struct IWbemObjectSink *v15; // r15
  int v16; // r12d
  HRESULT v17; // eax
  int v19; // [rsp+28h] [rbp-38h]
  struct IWbemClassObject *v20; // [rsp+40h] [rbp-20h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-18h] BYREF
  struct IOfflineFilesItem *v22; // [rsp+50h] [rbp-10h] BYREF
  CRefCounted *v23; // [rsp+58h] [rbp-8h] BYREF
  CCscControlWmiEnum *v24; // [rsp+A0h] [rbp+40h] BYREF
  struct IWbemObjectSink *v25; // [rsp+B8h] [rbp+58h]

  v25 = a4;
  InterfaceAndReleaseStream = *((_DWORD *)this + 42);
  ppv = 0;
  v22 = 0;
  if ( InterfaceAndReleaseStream >= 0 )
  {
    if ( *((_QWORD *)this + 20) )
    {
      InterfaceAndReleaseStream = CoGetInterfaceAndReleaseStream(
                                    *((LPSTREAM *)this + 20),
                                    &GUID_3836f049_9413_45dd_bf46_b5aaa82dc310,
                                    &ppv);
      if ( InterfaceAndReleaseStream < 0 )
        goto LABEL_24;
      *((_QWORD *)this + 20) = 0;
    }
    InterfaceAndReleaseStream = *((_DWORD *)this + 48);
    if ( InterfaceAndReleaseStream >= 0 )
    {
      if ( !*((_QWORD *)this + 23) )
        goto LABEL_9;
      InterfaceAndReleaseStream = CoGetInterfaceAndReleaseStream(
                                    *((LPSTREAM *)this + 23),
                                    &GUID_4a753da6_e044_4f12_a718_5d14d079a906,
                                    (LPVOID *)&v22);
      if ( InterfaceAndReleaseStream >= 0 )
      {
        *((_QWORD *)this + 23) = 0;
LABEL_9:
        v10 = a5;
        v19 = *((_DWORD *)this + 51);
        v24 = 0;
        InterfaceAndReleaseStream = CCscWmiItemEnum::CreateInstance(
                                      a2,
                                      a3,
                                      (struct IOfflineFilesItemContainer *)ppv,
                                      v22,
                                      a5,
                                      v19,
                                      1,
                                      &v24);
        if ( InterfaceAndReleaseStream >= 0 )
        {
          v23 = 0;
          v11 = CWmiAsyncCancelMonitor::Register(v10, a6, &v23);
          v12 = v24;
          InterfaceAndReleaseStream = v11;
          if ( v11 < 0 )
          {
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
            {
              WPP_SF_d(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                10,
                WPP_588e877ce0d23322099500f7fb075f62_Traceguids,
                (unsigned int)v11);
            }
          }
          else
          {
            v13 = v23;
            v14 = 0;
            v15 = v25;
            v20 = 0;
            v16 = *((_DWORD *)this + 51) & 0x80;
            do
            {
              if ( v14 >= *((_DWORD *)this + 50) )
                break;
              InterfaceAndReleaseStream = CCscControlWmiEnum::NextAlreadyImpersonating(
                                            v12,
                                            -1,
                                            1u,
                                            &v20,
                                            (unsigned int *)&v24);
              if ( InterfaceAndReleaseStream )
                break;
              ++v14;
              ((void (__fastcall *)(struct IWbemObjectSink *, __int64, struct IWbemClassObject **))v15->lpVtbl->Indicate)(
                v15,
                1,
                &v20);
              ((void (__fastcall *)(struct IWbemClassObject *))v20->lpVtbl->Release)(v20);
              if ( v16 )
                ((void (__fastcall *)(struct IWbemObjectSink *, _QWORD, _QWORD, _QWORD, _QWORD))v15->lpVtbl->SetStatus)(
                  v15,
                  (unsigned int)(InterfaceAndReleaseStream + 2),
                  0,
                  0,
                  0);
            }
            while ( !*((_DWORD *)v13 + 4) );
            CWmiAsyncCancelMonitor::Unregister(a5, v13);
            CRefCounted::ReleaseReference(v13);
            v17 = 0;
            if ( InterfaceAndReleaseStream != 1 )
              v17 = InterfaceAndReleaseStream;
            InterfaceAndReleaseStream = v17;
          }
          (*(void (__fastcall **)(CCscControlWmiEnum *))(*(_QWORD *)v12 + 16LL))(v12);
        }
        goto LABEL_27;
      }
    }
  }
LABEL_24:
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      11,
      WPP_588e877ce0d23322099500f7fb075f62_Traceguids,
      (unsigned int)InterfaceAndReleaseStream);
LABEL_27:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v22 )
    ((void (__fastcall *)(struct IOfflineFilesItem *))v22->lpVtbl->Release)(v22);
  return (unsigned int)InterfaceAndReleaseStream;
}

```

## disassembly

```asm
0x180017c10  mov     [rsp-38h+arg_8], rbx
0x180017c15  mov     [rsp-38h+arg_18], r9
0x180017c1a  push    rbp
0x180017c1b  push    rsi
0x180017c1c  push    rdi
0x180017c1d  push    r12
0x180017c1f  push    r13
0x180017c21  push    r14
0x180017c23  push    r15
0x180017c25  mov     rbp, rsp
0x180017c28  sub     rsp, 60h
0x180017c2c  mov     ebx, [rcx+0A8h]
0x180017c32  xor     r12d, r12d
0x180017c35  mov     [rbp+ppv], r12
0x180017c39  mov     rsi, r8
0x180017c3c  mov     [rbp+var_10], r12
0x180017c40  mov     r14, rdx
0x180017c43  mov     rdi, rcx
0x180017c46  test    ebx, ebx
0x180017c48  js      loc_180017E30
0x180017c4e  cmp     [rcx+0A0h], r12
0x180017c55  jz      short loc_180017C80
0x180017c57  mov     rcx, [rcx+0A0h]; pStm
0x180017c5e  lea     r8, [rbp+ppv]; ppv
0x180017c62  lea     rdx, _GUID_3836f049_9413_45dd_bf46_b5aaa82dc310; iid
0x180017c69  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x180017c6f  mov     ebx, eax
0x180017c71  test    eax, eax
0x180017c73  js      loc_180017E30
0x180017c79  mov     [rdi+0A0h], r12
0x180017c80  mov     ebx, [rdi+0C0h]
0x180017c86  test    ebx, ebx
0x180017c88  js      loc_180017E30
0x180017c8e  cmp     [rdi+0B8h], r12
0x180017c95  jz      short loc_180017CC0
0x180017c97  mov     rcx, [rdi+0B8h]; pStm
0x180017c9e  lea     r8, [rbp+var_10]; ppv
0x180017ca2  lea     rdx, _GUID_4a753da6_e044_4f12_a718_5d14d079a906; iid
0x180017ca9  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x180017caf  mov     ebx, eax
0x180017cb1  test    eax, eax
0x180017cb3  js      loc_180017E30
0x180017cb9  mov     [rdi+0B8h], r12
0x180017cc0  mov     r15, [rbp+arg_20]
0x180017cc4  lea     rax, [rbp+arg_0]
0x180017cc8  mov     r9, [rbp+var_10]; struct IOfflineFilesItem *
0x180017ccc  mov     rdx, rsi; struct IWbemContext *
0x180017ccf  mov     r8, [rbp+ppv]; struct IOfflineFilesItemContainer *
0x180017cd3  mov     rcx, r14; struct IWbemServices *
0x180017cd6  mov     [rsp+60h+var_28], rax; struct CCscWmiItemEnum **
0x180017cdb  mov     eax, [rdi+0CCh]
0x180017ce1  mov     [rsp+60h+var_30], 1; int
0x180017ce9  mov     [rsp+60h+var_38], eax; int
0x180017ced  mov     [rsp+60h+var_40], r15; struct CWmiAsyncCancelMonitor *
0x180017cf2  mov     [rbp+arg_0], r12
0x180017cf6  call    ?CreateInstance@CCscWmiItemEnum@@SAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIOfflineFilesItemContainer@@PEAUIOfflineFilesItem@@PEAVCWmiAsyncCancelMonitor@@JHPEAPEAV1@@Z; CCscWmiItemEnum::CreateInstance(IWbemServices *,IWbemContext *,IOfflineFilesItemContainer *,IOfflineFilesItem *,CWmiAsyncCancelMonitor *,long,int,CCscWmiItemEnum * *)
0x180017cfb  mov     ebx, eax
0x180017cfd  test    eax, eax
0x180017cff  js      loc_180017E61
0x180017d05  mov     rdx, [rbp+arg_28]; struct IWbemObjectSink *
0x180017d09  lea     r8, [rbp+var_8]; struct CWmiAsyncCancelState **
0x180017d0d  mov     rcx, r15; this
0x180017d10  mov     [rbp+var_8], r12
0x180017d14  call    ?Register@CWmiAsyncCancelMonitor@@QEAAJPEAUIWbemObjectSink@@PEAPEAVCWmiAsyncCancelState@@@Z; CWmiAsyncCancelMonitor::Register(IWbemObjectSink *,CWmiAsyncCancelState * *)
0x180017d19  mov     r14, [rbp+arg_0]
0x180017d1d  mov     ebx, eax
0x180017d1f  test    eax, eax
0x180017d21  js      loc_180017DEE
0x180017d27  mov     rsi, [rbp+var_8]
0x180017d2b  mov     r13d, r12d
0x180017d2e  mov     r15, [rbp+arg_18]
0x180017d32  mov     [rbp+var_20], r12
0x180017d36  mov     r12d, [rdi+0CCh]
0x180017d3d  and     r12d, 80h
0x180017d44  cmp     r13d, [rdi+0C8h]
0x180017d4b  jnb     short loc_180017DCA
0x180017d4d  lea     rax, [rbp+arg_0]
0x180017d51  mov     r8d, 1; unsigned int
0x180017d57  lea     r9, [rbp+var_20]; struct IWbemClassObject **
0x180017d5b  mov     [rsp+60h+var_40], rax; unsigned int *
0x180017d60  or      edx, 0FFFFFFFFh; int
0x180017d63  mov     rcx, r14; this
0x180017d66  call    ?NextAlreadyImpersonating@CCscControlWmiEnum@@QEAAJJKPEAPEAUIWbemClassObject@@PEAK@Z; CCscControlWmiEnum::NextAlreadyImpersonating(long,ulong,IWbemClassObject * *,ulong *)
0x180017d6b  mov     ebx, eax
0x180017d6d  test    eax, eax
0x180017d6f  jnz     short loc_180017DCA
0x180017d71  mov     rax, [r15]
0x180017d74  lea     r8, [rbp+var_20]
0x180017d78  lea     edx, [rbx+1]
0x180017d7b  mov     rcx, r15
0x180017d7e  inc     r13d
0x180017d81  mov     rax, [rax+18h]
0x180017d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d8a  mov     rcx, [rbp+var_20]
0x180017d8e  mov     rax, [rcx]
0x180017d91  mov     rax, [rax+10h]
0x180017d95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d9a  test    r12d, r12d
0x180017d9d  jz      short loc_180017DC0
0x180017d9f  mov     rax, [r15]
0x180017da2  lea     edx, [rbx+2]
0x180017da5  xor     r9d, r9d
0x180017da8  mov     [rsp+60h+var_40], 0
0x180017db1  xor     r8d, r8d
0x180017db4  mov     rcx, r15
0x180017db7  mov     rax, [rax+20h]
0x180017dbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017dc0  cmp     dword ptr [rsi+10h], 0
0x180017dc4  jz      loc_180017D44
0x180017dca  mov     rcx, [rbp+arg_20]; this
0x180017dce  mov     rdx, rsi; struct CWmiAsyncCancelState *
0x180017dd1  call    ?Unregister@CWmiAsyncCancelMonitor@@QEAAXPEAVCWmiAsyncCancelState@@@Z; CWmiAsyncCancelMonitor::Unregister(CWmiAsyncCancelState *)
0x180017dd6  mov     rcx, rsi; this
0x180017dd9  call    ?ReleaseReference@CRefCounted@@QEAAXXZ; CRefCounted::ReleaseReference(void)
0x180017dde  xor     r12d, r12d
0x180017de1  cmp     ebx, 1
0x180017de4  mov     eax, r12d
0x180017de7  cmovnz  eax, ebx
0x180017dea  mov     ebx, eax
0x180017dec  jmp     short loc_180017E1F
0x180017dee  mov     rcx, cs:WPP_GLOBAL_Control
0x180017df5  lea     rax, WPP_GLOBAL_Control
0x180017dfc  cmp     rcx, rax
0x180017dff  jz      short loc_180017E1F
0x180017e01  test    byte ptr [rcx+1Ch], 2
0x180017e05  jz      short loc_180017E1F
0x180017e07  mov     rcx, [rcx+10h]
0x180017e0b  lea     r8, WPP_588e877ce0d23322099500f7fb075f62_Traceguids
0x180017e12  mov     edx, 0Ah
0x180017e17  mov     r9d, ebx
0x180017e1a  call    WPP_SF_d
0x180017e1f  mov     rax, [r14]
0x180017e22  mov     rcx, r14
0x180017e25  mov     rax, [rax+10h]
0x180017e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e2e  jmp     short loc_180017E61
0x180017e30  mov     rcx, cs:WPP_GLOBAL_Control
0x180017e37  lea     rax, WPP_GLOBAL_Control
0x180017e3e  cmp     rcx, rax
0x180017e41  jz      short loc_180017E61
0x180017e43  test    byte ptr [rcx+1Ch], 2
0x180017e47  jz      short loc_180017E61
0x180017e49  mov     rcx, [rcx+10h]
0x180017e4d  lea     r8, WPP_588e877ce0d23322099500f7fb075f62_Traceguids
0x180017e54  mov     edx, 0Bh
0x180017e59  mov     r9d, ebx
0x180017e5c  call    WPP_SF_d
0x180017e61  mov     rcx, [rbp+ppv]
0x180017e65  test    rcx, rcx
0x180017e68  jz      short loc_180017E76
0x180017e6a  mov     rax, [rcx]
0x180017e6d  mov     rax, [rax+10h]
0x180017e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e76  mov     rcx, [rbp+var_10]
0x180017e7a  test    rcx, rcx
0x180017e7d  jz      short loc_180017E8B
0x180017e7f  mov     rax, [rcx]
0x180017e82  mov     rax, [rax+10h]
0x180017e86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e8b  mov     eax, ebx
0x180017e8d  mov     rbx, [rsp+60h+arg_8]
0x180017e95  add     rsp, 60h
0x180017e99  pop     r15
0x180017e9b  pop     r14
0x180017e9d  pop     r13
0x180017e9f  pop     r12
0x180017ea1  pop     rdi
0x180017ea2  pop     rsi
0x180017ea3  pop     rbp
0x180017ea4  retn
```
