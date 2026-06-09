# CTSThread::DispatchAsyncCallWithBuffer(ITSAsyncCallback *,ulong,void *,ulong)

- ea: `0x1800248a0`
- end: `0x18002499f`
- name: `?DispatchAsyncCallWithBuffer@CTSThread@@UEAAJPEAVITSAsyncCallback@@KPEAXK@Z`
- size: `255`
- prototype: `__int64 __fastcall(CTSThread *this, struct ITSAsyncCallback *, unsigned int, void *, char)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callees

- `0x180005f9c`
- `0x18001d114`
- `0x180022f00`
- `0x1800248a0`
- `0x180029688`
- `0x18002a1c4`

## string_xrefs

- `0x18002490c`: `CreateInstance failed for CTSBufferResult!`

## pseudocode

```c
__int64 __fastcall CTSThread::DispatchAsyncCallWithBuffer(
        CTSThread *this,
        struct ITSAsyncCallback *a2,
        unsigned int a3,
        void *a4,
        char a5)
{
  __int64 v7; // rdx
  int v8; // ebx
  __int64 v9; // r8
  __int64 v10; // r9
  int ActivityIdPrefix; // eax
  unsigned int v13; // [rsp+28h] [rbp-20h]
  struct CTSBufferResult *v14; // [rsp+50h] [rbp+8h] BYREF

  v14 = 0;
  v8 = CTSBufferResult::CreateInstance(*((_QWORD *)this + 84), a3, a4, &v14);
  if ( v8 >= 0 )
  {
    v8 = CTSThread::AddCallback(
           this,
           a2,
           (struct ITSAsyncResult *)(((unsigned __int64)v14 + 80) & -(__int64)(v14 != 0)),
           a5,
           0,
           0,
           0,
           0);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v7, v9, v10);
    v13 = v8;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      131,
      (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
      ActivityIdPrefix,
      (__int64)"CreateInstance failed for CTSBufferResult!",
      v13);
  }
  TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(&v14);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800248a0  mov     r11, rsp
0x1800248a3  mov     [r11+10h], rbx
0x1800248a7  mov     [r11+18h], rsi
0x1800248ab  push    rdi
0x1800248ac  sub     rsp, 40h
0x1800248b0  mov     rax, r9
0x1800248b3  mov     qword ptr [r11+8], 0
0x1800248bb  mov     r10d, r8d
0x1800248be  mov     rsi, rdx
0x1800248c1  mov     rdi, rcx
0x1800248c4  mov     rcx, [rcx+2A0h]
0x1800248cb  lea     r9, [r11+8]
0x1800248cf  mov     r8, rax
0x1800248d2  mov     edx, r10d
0x1800248d5  call    ?CreateInstance@CTSBufferResult@@SAJPEAV?$CTSObjectPool@VCTSBufferResult@@@@KPEAXPEAPEAV1@@Z; CTSBufferResult::CreateInstance(CTSObjectPool<CTSBufferResult> *,ulong,void *,CTSBufferResult * *)
0x1800248da  mov     ebx, eax
0x1800248dc  test    eax, eax
0x1800248de  jns     short loc_18002493D
0x1800248e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800248e7  lea     rax, WPP_GLOBAL_Control
0x1800248ee  cmp     rcx, rax
0x1800248f1  jz      loc_180024983
0x1800248f7  test    byte ptr [rcx+1Ch], 8
0x1800248fb  jz      loc_180024983
0x180024901  cmp     byte ptr [rcx+19h], 2
0x180024905  jb      short loc_180024983
0x180024907  call    RdpX_GetActivityIdPrefix
0x18002490c  lea     rcx, aCreateinstance; "CreateInstance failed for CTSBufferResu"...
0x180024913  mov     [rsp+48h+var_20], ebx
0x180024917  mov     [rsp+48h+var_28], rcx
0x18002491c  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x180024923  mov     rcx, cs:WPP_GLOBAL_Control
0x18002492a  mov     edx, 83h
0x18002492f  mov     r9d, eax
0x180024932  mov     rcx, [rcx+10h]
0x180024936  call    WPP_SF_DsD
0x18002493b  jmp     short loc_180024983
0x18002493d  mov     rax, [rsp+48h+arg_0]
0x180024942  mov     rdx, rsi; struct ITSAsyncCallback *
0x180024945  mov     r9d, [rsp+48h+arg_20]; unsigned int
0x18002494a  mov     [rsp+48h+var_10], 0; unsigned int
0x180024952  mov     [rsp+48h+var_18], 0; struct ITSQueuedCallback **
0x18002495b  lea     rcx, [rax+50h]
0x18002495f  mov     [rsp+48h+var_20], 0; unsigned int
0x180024967  neg     rax
0x18002496a  mov     [rsp+48h+var_28], 0; unsigned __int64
0x180024973  sbb     r8, r8
0x180024976  and     r8, rcx; struct ITSAsyncResult *
0x180024979  mov     rcx, rdi; this
0x18002497c  call    ?AddCallback@CTSThread@@UEAAJPEAVITSAsyncCallback@@PEAVITSAsyncResult@@K_KKPEAPEAVITSQueuedCallback@@I@Z; CTSThread::AddCallback(ITSAsyncCallback *,ITSAsyncResult *,ulong,unsigned __int64,ulong,ITSQueuedCallback * *,uint)
0x180024981  mov     ebx, eax
0x180024983  lea     rcx, [rsp+48h+arg_0]
0x180024988  call    ?SafeRelease@?$TCntPtr@VDirtySurface@RdpRemoteAppGfxRedirectionHandler@@@@AEAAXXZ; TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(void)
0x18002498d  mov     rsi, [rsp+48h+arg_10]
0x180024992  mov     eax, ebx
0x180024994  mov     rbx, [rsp+48h+arg_8]
0x180024999  add     rsp, 40h
0x18002499d  pop     rdi
0x18002499e  retn
```
