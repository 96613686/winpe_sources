# CTSThread::DispatchAsyncCallWithBufferAndParam(ITSAsyncCallback *,ulong,void *,unsigned __int64,ulong)

- ea: `0x1800249b0`
- end: `0x180024ab0`
- name: `?DispatchAsyncCallWithBufferAndParam@CTSThread@@UEAAJPEAVITSAsyncCallback@@KPEAX_KK@Z`
- size: `256`
- prototype: `__int64 __fastcall(CTSThread *this, struct ITSAsyncCallback *, unsigned int, void *, unsigned __int64, char)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callees

- `0x180005f9c`
- `0x18001d114`
- `0x180022f00`
- `0x1800249b0`
- `0x180029688`
- `0x18002a1c4`

## string_xrefs

- `0x180024a1c`: `CreateInstance failed for CTSBufferResult!`

## pseudocode

```c
__int64 __fastcall CTSThread::DispatchAsyncCallWithBufferAndParam(
        CTSThread *this,
        struct ITSAsyncCallback *a2,
        unsigned int a3,
        void *a4,
        unsigned __int64 a5,
        char a6)
{
  __int64 v8; // rdx
  int v9; // ebx
  __int64 v10; // r8
  __int64 v11; // r9
  int ActivityIdPrefix; // eax
  unsigned int v14; // [rsp+28h] [rbp-20h]
  struct CTSBufferResult *v15; // [rsp+50h] [rbp+8h] BYREF

  v15 = 0;
  v9 = CTSBufferResult::CreateInstance(*((_QWORD *)this + 84), a3, a4, &v15);
  if ( v9 >= 0 )
  {
    v9 = CTSThread::AddCallback(
           this,
           a2,
           (struct ITSAsyncResult *)(((unsigned __int64)v15 + 80) & -(__int64)(v15 != 0)),
           a6,
           a5,
           0,
           0,
           0);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v8, v10, v11);
    v14 = v9;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      128,
      (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
      ActivityIdPrefix,
      (__int64)"CreateInstance failed for CTSBufferResult!",
      v14);
  }
  TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(&v15);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800249b0  mov     r11, rsp
0x1800249b3  mov     [r11+10h], rbx
0x1800249b7  mov     [r11+18h], rsi
0x1800249bb  push    rdi
0x1800249bc  sub     rsp, 40h
0x1800249c0  mov     rax, r9
0x1800249c3  mov     qword ptr [r11+8], 0
0x1800249cb  mov     r10d, r8d
0x1800249ce  mov     rsi, rdx
0x1800249d1  mov     rdi, rcx
0x1800249d4  mov     rcx, [rcx+2A0h]
0x1800249db  lea     r9, [r11+8]
0x1800249df  mov     r8, rax
0x1800249e2  mov     edx, r10d
0x1800249e5  call    ?CreateInstance@CTSBufferResult@@SAJPEAV?$CTSObjectPool@VCTSBufferResult@@@@KPEAXPEAPEAV1@@Z; CTSBufferResult::CreateInstance(CTSObjectPool<CTSBufferResult> *,ulong,void *,CTSBufferResult * *)
0x1800249ea  mov     ebx, eax
0x1800249ec  test    eax, eax
0x1800249ee  jns     short loc_180024A4D
0x1800249f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800249f7  lea     rax, WPP_GLOBAL_Control
0x1800249fe  cmp     rcx, rax
0x180024a01  jz      loc_180024A94
0x180024a07  test    byte ptr [rcx+1Ch], 8
0x180024a0b  jz      loc_180024A94
0x180024a11  cmp     byte ptr [rcx+19h], 2
0x180024a15  jb      short loc_180024A94
0x180024a17  call    RdpX_GetActivityIdPrefix
0x180024a1c  lea     rcx, aCreateinstance; "CreateInstance failed for CTSBufferResu"...
0x180024a23  mov     [rsp+48h+var_20], ebx
0x180024a27  mov     [rsp+48h+var_28], rcx
0x180024a2c  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x180024a33  mov     rcx, cs:WPP_GLOBAL_Control
0x180024a3a  mov     edx, 80h
0x180024a3f  mov     r9d, eax
0x180024a42  mov     rcx, [rcx+10h]
0x180024a46  call    WPP_SF_DsD
0x180024a4b  jmp     short loc_180024A94
0x180024a4d  mov     rax, [rsp+48h+arg_0]
0x180024a52  mov     rdx, rsi; struct ITSAsyncCallback *
0x180024a55  mov     r9d, [rsp+48h+arg_28]; unsigned int
0x180024a5a  mov     [rsp+48h+var_10], 0; unsigned int
0x180024a62  mov     [rsp+48h+var_18], 0; struct ITSQueuedCallback **
0x180024a6b  lea     rcx, [rax+50h]
0x180024a6f  mov     [rsp+48h+var_20], 0; unsigned int
0x180024a77  neg     rax
0x180024a7a  mov     rax, [rsp+48h+arg_20]
0x180024a7f  sbb     r8, r8
0x180024a82  mov     [rsp+48h+var_28], rax; unsigned __int64
0x180024a87  and     r8, rcx; struct ITSAsyncResult *
0x180024a8a  mov     rcx, rdi; this
0x180024a8d  call    ?AddCallback@CTSThread@@UEAAJPEAVITSAsyncCallback@@PEAVITSAsyncResult@@K_KKPEAPEAVITSQueuedCallback@@I@Z; CTSThread::AddCallback(ITSAsyncCallback *,ITSAsyncResult *,ulong,unsigned __int64,ulong,ITSQueuedCallback * *,uint)
0x180024a92  mov     ebx, eax
0x180024a94  lea     rcx, [rsp+48h+arg_0]
0x180024a99  call    ?SafeRelease@?$TCntPtr@VDirtySurface@RdpRemoteAppGfxRedirectionHandler@@@@AEAAXXZ; TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(void)
0x180024a9e  mov     rsi, [rsp+48h+arg_10]
0x180024aa3  mov     eax, ebx
0x180024aa5  mov     rbx, [rsp+48h+arg_8]
0x180024aaa  add     rsp, 40h
0x180024aae  pop     rdi
0x180024aaf  retn
```
