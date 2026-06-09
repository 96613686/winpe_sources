# ClassEnableMediaChangeDetection

- ea: `0x140054010`
- end: `0x140054159`
- name: `ClassEnableMediaChangeDetection`
- size: `329`
- prototype: `void __stdcall(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1400553f4`
- `0x14005d880`

## callees

- `0x140015210`
- `0x140016ea0`
- `0x14001fbf4`
- `0x14001feac`
- `0x140054010`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140054142`
- `ntoskrnl!KeReleaseMutex` at `0x140054142`
- `ntoskrnl!KeWaitForSingleObject` at `0x140054085`
- `ntoskrnl!KeWaitForSingleObject` at `0x140054085`

## pseudocode

```c
void __stdcall ClassEnableMediaChangeDetection(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension)
{
  _MEDIA_CHANGE_DETECTION_INFO *MediaChangeDetectionInfo; // rsi
  unsigned int v3; // r14d
  PDEVICE_OBJECT v4; // rcx
  __int64 v5; // rdx

  MediaChangeDetectionInfo = FdoExtension->MediaChangeDetectionInfo;
  if ( MediaChangeDetectionInfo )
  {
    KeWaitForSingleObject(MediaChangeDetectionInfo, UserRequest, 0, 0, 0);
    v3 = --MediaChangeDetectionInfo->MediaChangeDetectionDisableCount;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 89, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids, v3);
    }
    if ( v3 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        goto LABEL_20;
      }
      v5 = 91;
    }
    else
    {
      ClasspInternalSetMediaChangeState(FdoExtension);
      ClassResetMediaChangeTimer(FdoExtension);
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        goto LABEL_20;
      }
      v5 = 90;
    }
    WPP_SF_(v4->AttachedDevice, v5, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids);
LABEL_20:
    KeReleaseMutex(&MediaChangeDetectionInfo->MediaChangeMutex, 0);
    return;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 88, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids);
  }
}

```

## disassembly

```asm
0x140054010  push    rbp
0x140054012  push    rsi
0x140054013  push    rdi
0x140054014  push    r14
0x140054016  sub     rsp, 38h
0x14005401a  mov     rsi, [rcx+288h]
0x140054021  mov     rbp, rcx
0x140054024  test    rsi, rsi
0x140054027  jnz     short loc_14005406F
0x140054029  mov     rcx, cs:WPP_GLOBAL_Control
0x140054030  lea     rdi, WPP_GLOBAL_Control
0x140054037  cmp     rcx, rdi
0x14005403a  jz      loc_14005414E
0x140054040  test    dword ptr [rcx+2Ch], 1000h
0x140054047  jz      loc_14005414E
0x14005404d  cmp     byte ptr [rcx+29h], 4
0x140054051  jb      loc_14005414E
0x140054057  mov     rcx, [rcx+18h]
0x14005405b  lea     edx, [rsi+58h]
0x14005405e  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140054065  call    WPP_SF_
0x14005406a  jmp     loc_14005414E
0x14005406f  xor     r9d, r9d; Alertable
0x140054072  mov     [rsp+58h+Timeout], 0; Timeout
0x14005407b  xor     r8d, r8d; WaitMode
0x14005407e  mov     rcx, rsi; Object
0x140054081  lea     edx, [r9+6]; WaitReason
0x140054085  call    cs:__imp_KeWaitForSingleObject
0x14005408c  nop     dword ptr [rax+rax+00h]
0x140054091  dec     dword ptr [rsi+3Ch]
0x140054094  mov     r14d, [rsi+3Ch]
0x140054098  mov     rcx, cs:WPP_GLOBAL_Control
0x14005409f  lea     rdi, WPP_GLOBAL_Control
0x1400540a6  cmp     rcx, rdi
0x1400540a9  jz      short loc_1400540D2
0x1400540ab  test    dword ptr [rcx+2Ch], 1000h
0x1400540b2  jz      short loc_1400540D2
0x1400540b4  cmp     byte ptr [rcx+29h], 4
0x1400540b8  jb      short loc_1400540D2
0x1400540ba  mov     rcx, [rcx+18h]
0x1400540be  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x1400540c5  mov     edx, 59h ; 'Y'
0x1400540ca  mov     r9d, r14d
0x1400540cd  call    WPP_SF_d
0x1400540d2  test    r14d, r14d
0x1400540d5  jnz     short loc_14005410D
0x1400540d7  xor     r8d, r8d
0x1400540da  xor     edx, edx
0x1400540dc  mov     rcx, rbp; FdoExtension
0x1400540df  call    ClasspInternalSetMediaChangeState
0x1400540e4  mov     rcx, rbp; FdoExtension
0x1400540e7  call    ClassResetMediaChangeTimer
0x1400540ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400540f3  cmp     rcx, rdi
0x1400540f6  jz      short loc_14005413D
0x1400540f8  test    dword ptr [rcx+2Ch], 1000h
0x1400540ff  jz      short loc_14005413D
0x140054101  cmp     byte ptr [rcx+29h], 4
0x140054105  jb      short loc_14005413D
0x140054107  lea     edx, [r14+5Ah]
0x14005410b  jmp     short loc_14005412D
0x14005410d  mov     rcx, cs:WPP_GLOBAL_Control
0x140054114  cmp     rcx, rdi
0x140054117  jz      short loc_14005413D
0x140054119  test    dword ptr [rcx+2Ch], 1000h
0x140054120  jz      short loc_14005413D
0x140054122  cmp     byte ptr [rcx+29h], 4
0x140054126  jb      short loc_14005413D
0x140054128  mov     edx, 5Bh ; '['
0x14005412d  mov     rcx, [rcx+18h]
0x140054131  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140054138  call    WPP_SF_
0x14005413d  xor     edx, edx; Wait
0x14005413f  mov     rcx, rsi; Mutex
0x140054142  call    cs:__imp_KeReleaseMutex
0x140054149  nop     dword ptr [rax+rax+00h]
0x14005414e  add     rsp, 38h
0x140054152  pop     r14
0x140054154  pop     rdi
0x140054155  pop     rsi
0x140054156  pop     rbp
0x140054157  retn
```
