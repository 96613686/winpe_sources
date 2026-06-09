# ExtSTAOnSystemSleepNonAOAC(EXTSTA_VELAN *,int)

- ea: `0x14006319c`
- end: `0x140063360`
- name: `?ExtSTAOnSystemSleepNonAOAC@@YAXPEAUEXTSTA_VELAN@@H@Z`
- size: `452`
- prototype: `void __fastcall(struct EXTSTA_VELAN *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140062f70`

## callees

- `0x14000d21c`
- `0x14005f8f4`
- `0x14005fec4`
- `0x140061e20`
- `0x14006319c`
- `0x140063d84`
- `0x140063ff8`
- `0x1400648d8`
- `0x14006a410`

## import_xrefs

- `NDIS!NdisAcquireRWLockWrite` at `0x1400631fa`
- `NDIS!NdisAcquireRWLockWrite` at `0x14006329c`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400631fa`
- `NDIS!NdisAcquireRWLockWrite` at `0x14006329c`
- `NDIS!NdisReleaseRWLock` at `0x140063221`
- `NDIS!NdisReleaseRWLock` at `0x140063306`
- `NDIS!NdisReleaseRWLock` at `0x140063221`
- `NDIS!NdisReleaseRWLock` at `0x140063306`

## pseudocode

```c
void __fastcall ExtSTAOnSystemSleepNonAOAC(struct EXTSTA_VELAN *a1, int a2)
{
  struct _IRP *pIrp; // rdi
  struct _LOCK_STATE_EX LockState; // [rsp+38h] [rbp+10h] BYREF

  LockState.OldIrql = 0;
  *(_WORD *)&LockState.LockState = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 129, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids);
  NdisAcquireRWLockWrite(a1->pGenVElan->pRWLock, &LockState, 0);
  ExtSTACancelConnRoamingTimer(a1);
  NdisReleaseRWLock(a1->pGenVElan->pRWLock, &LockState);
  if ( a2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 130, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids);
    ExtSTAIoctlDisconnect(a1, 0, 0);
  }
  else
  {
    ExtSTAQueryBSSListOnSleep(a1);
    if ( !a1->pGenVElan->pAdapt->AdapterEnhancedCapabilities.uWindowsWifiCxVersion )
      ExtSTAOffloadGTKReKey(a1);
  }
  NdisAcquireRWLockWrite(a1->pGenVElan->pRWLock, &LockState, 0);
  pIrp = a1->AssocMgr.pIrp;
  a1->AssocMgr.pIrp = 0;
  if ( pIrp )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 131, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids);
    ExtSTATerminateConnection(a1);
    ExtSTACompleteConnection(a1, pIrp, -1073741505);
  }
  NdisReleaseRWLock(a1->pGenVElan->pRWLock, &LockState);
  if ( a1->pGenVElan->pAdapt->uConfiguredOpMode == 64 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 132, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids);
    ExtSTAResetNic(a1);
  }
}

```

## disassembly

```asm
0x14006319c  mov     [rsp+arg_0], rbx
0x1400631a1  mov     [rsp+arg_10], rsi
0x1400631a6  push    rdi
0x1400631a7  sub     rsp, 20h
0x1400631ab  xor     eax, eax
0x1400631ad  mov     [rsp+28h+LockState.OldIrql], 0
0x1400631b2  mov     word ptr [rsp+28h+LockState.LockState], ax
0x1400631b7  mov     edi, edx
0x1400631b9  mov     rbx, rcx
0x1400631bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400631c3  lea     rsi, WPP_GLOBAL_Control
0x1400631ca  cmp     rcx, rsi
0x1400631cd  jz      short loc_1400631E4
0x1400631cf  mov     rcx, [rcx+18h]
0x1400631d3  lea     r8, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids
0x1400631da  mov     edx, 81h
0x1400631df  call    WPP_SF_
0x1400631e4  mov     rcx, [rbx+0A38h]
0x1400631eb  lea     rdx, [rsp+28h+LockState]; LockState
0x1400631f0  xor     r8d, r8d; Flags
0x1400631f3  mov     rcx, [rcx+90h]; Lock
0x1400631fa  call    cs:__imp_NdisAcquireRWLockWrite
0x140063201  nop     dword ptr [rax+rax+00h]
0x140063206  mov     rcx, rbx; struct EXTSTA_VELAN *
0x140063209  call    ?ExtSTACancelConnRoamingTimer@@YAEPEAUEXTSTA_VELAN@@@Z; ExtSTACancelConnRoamingTimer(EXTSTA_VELAN *)
0x14006320e  mov     rcx, [rbx+0A38h]
0x140063215  lea     rdx, [rsp+28h+LockState]; LockState
0x14006321a  mov     rcx, [rcx+90h]; Lock
0x140063221  call    cs:__imp_NdisReleaseRWLock
0x140063228  nop     dword ptr [rax+rax+00h]
0x14006322d  test    edi, edi
0x14006322f  jz      short loc_140063261
0x140063231  mov     rcx, cs:WPP_GLOBAL_Control
0x140063238  cmp     rcx, rsi
0x14006323b  jz      short loc_140063252
0x14006323d  mov     rcx, [rcx+18h]
0x140063241  lea     r8, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids
0x140063248  mov     edx, 82h
0x14006324d  call    WPP_SF_
0x140063252  xor     r8d, r8d; unsigned int
0x140063255  xor     edx, edx; void *
0x140063257  mov     rcx, rbx; struct EXTSTA_VELAN *
0x14006325a  call    ?ExtSTAIoctlDisconnect@@YAJPEAUEXTSTA_VELAN@@PEAXK@Z; ExtSTAIoctlDisconnect(EXTSTA_VELAN *,void *,ulong)
0x14006325f  jmp     short loc_140063286
0x140063261  mov     rcx, rbx; struct EXTSTA_VELAN *
0x140063264  call    ?ExtSTAQueryBSSListOnSleep@@YAXPEAUEXTSTA_VELAN@@@Z; ExtSTAQueryBSSListOnSleep(EXTSTA_VELAN *)
0x140063269  mov     rax, [rbx+0A38h]
0x140063270  mov     rcx, [rax+10h]
0x140063274  cmp     qword ptr [rcx+610h], 0
0x14006327c  jnz     short loc_140063286
0x14006327e  mov     rcx, rbx; struct EXTSTA_VELAN *
0x140063281  call    ?ExtSTAOffloadGTKReKey@@YAXPEAUEXTSTA_VELAN@@@Z; ExtSTAOffloadGTKReKey(EXTSTA_VELAN *)
0x140063286  mov     rcx, [rbx+0A38h]
0x14006328d  lea     rdx, [rsp+28h+LockState]; LockState
0x140063292  xor     r8d, r8d; Flags
0x140063295  mov     rcx, [rcx+90h]; Lock
0x14006329c  call    cs:__imp_NdisAcquireRWLockWrite
0x1400632a3  nop     dword ptr [rax+rax+00h]
0x1400632a8  mov     rdi, [rbx+10h]
0x1400632ac  mov     qword ptr [rbx+10h], 0
0x1400632b4  test    rdi, rdi
0x1400632b7  jz      short loc_1400632F3
0x1400632b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400632c0  cmp     rcx, rsi
0x1400632c3  jz      short loc_1400632DA
0x1400632c5  mov     rcx, [rcx+18h]
0x1400632c9  lea     r8, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids
0x1400632d0  mov     edx, 83h
0x1400632d5  call    WPP_SF_
0x1400632da  mov     rcx, rbx; struct EXTSTA_VELAN *
0x1400632dd  call    ?ExtSTATerminateConnection@@YAXPEAUEXTSTA_VELAN@@@Z; ExtSTATerminateConnection(EXTSTA_VELAN *)
0x1400632e2  mov     r8d, 0C000013Fh; int
0x1400632e8  mov     rdx, rdi; struct _IRP *
0x1400632eb  mov     rcx, rbx; struct EXTSTA_VELAN *
0x1400632ee  call    ?ExtSTACompleteConnection@@YAXPEAUEXTSTA_VELAN@@PEAU_IRP@@J@Z; ExtSTACompleteConnection(EXTSTA_VELAN *,_IRP *,long)
0x1400632f3  mov     rcx, [rbx+0A38h]
0x1400632fa  lea     rdx, [rsp+28h+LockState]; LockState
0x1400632ff  mov     rcx, [rcx+90h]; Lock
0x140063306  call    cs:__imp_NdisReleaseRWLock
0x14006330d  nop     dword ptr [rax+rax+00h]
0x140063312  mov     rax, [rbx+0A38h]
0x140063319  mov     rcx, [rax+10h]
0x14006331d  cmp     dword ptr [rcx+118h], 40h ; '@'
0x140063324  jnz     short loc_14006334F
0x140063326  mov     rcx, cs:WPP_GLOBAL_Control
0x14006332d  cmp     rcx, rsi
0x140063330  jz      short loc_140063347
0x140063332  mov     rcx, [rcx+18h]
0x140063336  lea     r8, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids
0x14006333d  mov     edx, 84h
0x140063342  call    WPP_SF_
0x140063347  mov     rcx, rbx; struct EXTSTA_VELAN *
0x14006334a  call    ExtSTAResetNic
0x14006334f  mov     rbx, [rsp+28h+arg_0]
0x140063354  mov     rsi, [rsp+28h+arg_10]
0x140063359  add     rsp, 20h
0x14006335d  pop     rdi
0x14006335e  retn
```
