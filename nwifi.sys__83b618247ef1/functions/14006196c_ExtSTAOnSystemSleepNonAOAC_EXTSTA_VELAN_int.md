# ExtSTAOnSystemSleepNonAOAC(EXTSTA_VELAN *,int)

- ea: `0x14006196c`
- end: `0x140061b30`
- name: `?ExtSTAOnSystemSleepNonAOAC@@YAXPEAUEXTSTA_VELAN@@H@Z`
- size: `452`
- prototype: `void __fastcall(struct EXTSTA_VELAN *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140061740`

## callees

- `0x14000d22c`
- `0x14005e0c4`
- `0x14005e694`
- `0x1400605f0`
- `0x14006196c`
- `0x140062554`
- `0x1400627c8`
- `0x1400630a8`
- `0x140068be0`

## import_xrefs

- `NDIS!NdisAcquireRWLockWrite` at `0x1400619ca`
- `NDIS!NdisAcquireRWLockWrite` at `0x140061a6c`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400619ca`
- `NDIS!NdisAcquireRWLockWrite` at `0x140061a6c`
- `NDIS!NdisReleaseRWLock` at `0x1400619f1`
- `NDIS!NdisReleaseRWLock` at `0x140061ad6`
- `NDIS!NdisReleaseRWLock` at `0x1400619f1`
- `NDIS!NdisReleaseRWLock` at `0x140061ad6`

## pseudocode

```c
void __fastcall ExtSTAOnSystemSleepNonAOAC(struct EXTSTA_VELAN *a1, int a2)
{
  struct _IRP *pIrp; // rdi
  struct _LOCK_STATE_EX LockState; // [rsp+38h] [rbp+10h] BYREF

  LockState.OldIrql = 0;
  *(_WORD *)&LockState.LockState = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 130, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids);
  NdisAcquireRWLockWrite(a1->pGenVElan->pRWLock, &LockState, 0);
  ExtSTACancelConnRoamingTimer(a1);
  NdisReleaseRWLock(a1->pGenVElan->pRWLock, &LockState);
  if ( a2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 131, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids);
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
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 132, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids);
    ExtSTATerminateConnection(a1);
    ExtSTACompleteConnection(a1, pIrp, -1073741505);
  }
  NdisReleaseRWLock(a1->pGenVElan->pRWLock, &LockState);
  if ( a1->pGenVElan->pAdapt->uConfiguredOpMode == 64 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 133, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids);
    ExtSTAResetNic(a1);
  }
}

```

## disassembly

```asm
0x14006196c  mov     [rsp+arg_0], rbx
0x140061971  mov     [rsp+arg_10], rsi
0x140061976  push    rdi
0x140061977  sub     rsp, 20h
0x14006197b  xor     eax, eax
0x14006197d  mov     [rsp+28h+LockState.OldIrql], 0
0x140061982  mov     word ptr [rsp+28h+LockState.LockState], ax
0x140061987  mov     edi, edx
0x140061989  mov     rbx, rcx
0x14006198c  mov     rcx, cs:WPP_GLOBAL_Control
0x140061993  lea     rsi, WPP_GLOBAL_Control
0x14006199a  cmp     rcx, rsi
0x14006199d  jz      short loc_1400619B4
0x14006199f  mov     rcx, [rcx+18h]
0x1400619a3  lea     r8, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids
0x1400619aa  mov     edx, 82h
0x1400619af  call    WPP_SF_
0x1400619b4  mov     rcx, [rbx+0A38h]
0x1400619bb  lea     rdx, [rsp+28h+LockState]; LockState
0x1400619c0  xor     r8d, r8d; Flags
0x1400619c3  mov     rcx, [rcx+90h]; Lock
0x1400619ca  call    cs:__imp_NdisAcquireRWLockWrite
0x1400619d1  nop     dword ptr [rax+rax+00h]
0x1400619d6  mov     rcx, rbx; struct EXTSTA_VELAN *
0x1400619d9  call    ?ExtSTACancelConnRoamingTimer@@YAEPEAUEXTSTA_VELAN@@@Z; ExtSTACancelConnRoamingTimer(EXTSTA_VELAN *)
0x1400619de  mov     rcx, [rbx+0A38h]
0x1400619e5  lea     rdx, [rsp+28h+LockState]; LockState
0x1400619ea  mov     rcx, [rcx+90h]; Lock
0x1400619f1  call    cs:__imp_NdisReleaseRWLock
0x1400619f8  nop     dword ptr [rax+rax+00h]
0x1400619fd  test    edi, edi
0x1400619ff  jz      short loc_140061A31
0x140061a01  mov     rcx, cs:WPP_GLOBAL_Control
0x140061a08  cmp     rcx, rsi
0x140061a0b  jz      short loc_140061A22
0x140061a0d  mov     rcx, [rcx+18h]
0x140061a11  lea     r8, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids
0x140061a18  mov     edx, 83h
0x140061a1d  call    WPP_SF_
0x140061a22  xor     r8d, r8d; unsigned int
0x140061a25  xor     edx, edx; void *
0x140061a27  mov     rcx, rbx; struct EXTSTA_VELAN *
0x140061a2a  call    ?ExtSTAIoctlDisconnect@@YAJPEAUEXTSTA_VELAN@@PEAXK@Z; ExtSTAIoctlDisconnect(EXTSTA_VELAN *,void *,ulong)
0x140061a2f  jmp     short loc_140061A56
0x140061a31  mov     rcx, rbx; struct EXTSTA_VELAN *
0x140061a34  call    ?ExtSTAQueryBSSListOnSleep@@YAXPEAUEXTSTA_VELAN@@@Z; ExtSTAQueryBSSListOnSleep(EXTSTA_VELAN *)
0x140061a39  mov     rax, [rbx+0A38h]
0x140061a40  mov     rcx, [rax+10h]
0x140061a44  cmp     qword ptr [rcx+610h], 0
0x140061a4c  jnz     short loc_140061A56
0x140061a4e  mov     rcx, rbx; struct EXTSTA_VELAN *
0x140061a51  call    ?ExtSTAOffloadGTKReKey@@YAXPEAUEXTSTA_VELAN@@@Z; ExtSTAOffloadGTKReKey(EXTSTA_VELAN *)
0x140061a56  mov     rcx, [rbx+0A38h]
0x140061a5d  lea     rdx, [rsp+28h+LockState]; LockState
0x140061a62  xor     r8d, r8d; Flags
0x140061a65  mov     rcx, [rcx+90h]; Lock
0x140061a6c  call    cs:__imp_NdisAcquireRWLockWrite
0x140061a73  nop     dword ptr [rax+rax+00h]
0x140061a78  mov     rdi, [rbx+10h]
0x140061a7c  mov     qword ptr [rbx+10h], 0
0x140061a84  test    rdi, rdi
0x140061a87  jz      short loc_140061AC3
0x140061a89  mov     rcx, cs:WPP_GLOBAL_Control
0x140061a90  cmp     rcx, rsi
0x140061a93  jz      short loc_140061AAA
0x140061a95  mov     rcx, [rcx+18h]
0x140061a99  lea     r8, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids
0x140061aa0  mov     edx, 84h
0x140061aa5  call    WPP_SF_
0x140061aaa  mov     rcx, rbx; struct EXTSTA_VELAN *
0x140061aad  call    ?ExtSTATerminateConnection@@YAXPEAUEXTSTA_VELAN@@@Z; ExtSTATerminateConnection(EXTSTA_VELAN *)
0x140061ab2  mov     r8d, 0C000013Fh; int
0x140061ab8  mov     rdx, rdi; struct _IRP *
0x140061abb  mov     rcx, rbx; struct EXTSTA_VELAN *
0x140061abe  call    ?ExtSTACompleteConnection@@YAXPEAUEXTSTA_VELAN@@PEAU_IRP@@J@Z; ExtSTACompleteConnection(EXTSTA_VELAN *,_IRP *,long)
0x140061ac3  mov     rcx, [rbx+0A38h]
0x140061aca  lea     rdx, [rsp+28h+LockState]; LockState
0x140061acf  mov     rcx, [rcx+90h]; Lock
0x140061ad6  call    cs:__imp_NdisReleaseRWLock
0x140061add  nop     dword ptr [rax+rax+00h]
0x140061ae2  mov     rax, [rbx+0A38h]
0x140061ae9  mov     rcx, [rax+10h]
0x140061aed  cmp     dword ptr [rcx+118h], 40h ; '@'
0x140061af4  jnz     short loc_140061B1F
0x140061af6  mov     rcx, cs:WPP_GLOBAL_Control
0x140061afd  cmp     rcx, rsi
0x140061b00  jz      short loc_140061B17
0x140061b02  mov     rcx, [rcx+18h]
0x140061b06  lea     r8, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids
0x140061b0d  mov     edx, 85h
0x140061b12  call    WPP_SF_
0x140061b17  mov     rcx, rbx; struct EXTSTA_VELAN *
0x140061b1a  call    ExtSTAResetNic
0x140061b1f  mov     rbx, [rsp+28h+arg_0]
0x140061b24  mov     rsi, [rsp+28h+arg_10]
0x140061b29  add     rsp, 20h
0x140061b2d  pop     rdi
0x140061b2e  retn
```
