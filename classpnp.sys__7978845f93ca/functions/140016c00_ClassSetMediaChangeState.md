# ClassSetMediaChangeState

- ea: `0x140016c00`
- end: `0x140016d40`
- name: `ClassSetMediaChangeState`
- size: `320`
- prototype: `void __stdcall(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension, MEDIA_CHANGE_DETECTION_STATE State, BOOLEAN Wait)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x140016c00`
- `0x140016ea0`
- `0x14001feac`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140016cb2`
- `ntoskrnl!KeReleaseMutex` at `0x140016cb2`
- `ntoskrnl!KeWaitForSingleObject` at `0x140016c8d`
- `ntoskrnl!KeWaitForSingleObject` at `0x140016c8d`

## pseudocode

```c
void __stdcall ClassSetMediaChangeState(
        PFUNCTIONAL_DEVICE_EXTENSION FdoExtension,
        MEDIA_CHANGE_DETECTION_STATE State,
        BOOLEAN Wait)
{
  _MEDIA_CHANGE_DETECTION_INFO *MediaChangeDetectionInfo; // rdi
  union _LARGE_INTEGER *Timeout; // rcx
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // [rsp+50h] [rbp+8h] BYREF

  MediaChangeDetectionInfo = FdoExtension->MediaChangeDetectionInfo;
  v10 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids);
  }
  if ( State == MediaNotPresent )
  {
    FdoExtension->FailurePredicted = 0;
    FdoExtension->FailureReason = 0;
  }
  v10 = 0;
  if ( MediaChangeDetectionInfo )
  {
    Timeout = (union _LARGE_INTEGER *)&v10;
    if ( Wait == 1 )
      Timeout = 0;
    if ( KeWaitForSingleObject(MediaChangeDetectionInfo, Executive, 0, 0, Timeout) == 258 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        v9 = 29;
        goto LABEL_20;
      }
    }
    else
    {
      ClasspInternalSetMediaChangeState(FdoExtension, State, 0);
      KeReleaseMutex(&MediaChangeDetectionInfo->MediaChangeMutex, 0);
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v9 = 30;
LABEL_20:
        WPP_SF_(v8->AttachedDevice, v9, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids);
      }
    }
  }
}

```

## disassembly

```asm
0x140016c00  mov     [rsp+arg_8], rbx
0x140016c05  mov     [rsp+arg_10], rbp
0x140016c0a  push    rsi
0x140016c0b  push    rdi
0x140016c0c  push    r13
0x140016c0e  sub     rsp, 30h
0x140016c12  mov     rdi, [rcx+288h]
0x140016c19  mov     bpl, r8b
0x140016c1c  mov     esi, edx
0x140016c1e  mov     [rsp+48h+arg_0], 0
0x140016c27  mov     rbx, rcx
0x140016c2a  mov     rcx, cs:WPP_GLOBAL_Control
0x140016c31  lea     r13, WPP_GLOBAL_Control
0x140016c38  cmp     rcx, r13
0x140016c3b  jz      short loc_140016C4A
0x140016c3d  test    dword ptr [rcx+2Ch], 1000h
0x140016c44  jnz     loc_140016CF7
0x140016c4a  cmp     esi, 2
0x140016c4d  jnz     short loc_140016C60
0x140016c4f  mov     byte ptr [rbx+333h], 0
0x140016c56  mov     dword ptr [rbx+334h], 0
0x140016c60  mov     [rsp+48h+arg_0], 0
0x140016c69  test    rdi, rdi
0x140016c6c  jz      short loc_140016CCA
0x140016c6e  xor     eax, eax
0x140016c70  lea     rcx, [rsp+48h+arg_0]
0x140016c75  cmp     bpl, 1
0x140016c79  cmovz   rcx, rax
0x140016c7d  xor     r9d, r9d; Alertable
0x140016c80  mov     [rsp+48h+Timeout], rcx; Timeout
0x140016c85  xor     r8d, r8d; WaitMode
0x140016c88  mov     rcx, rdi; Object
0x140016c8b  xor     edx, edx; WaitReason
0x140016c8d  call    cs:__imp_KeWaitForSingleObject
0x140016c94  nop     dword ptr [rax+rax+00h]
0x140016c99  cmp     eax, 102h
0x140016c9e  jz      short loc_140016D1B
0x140016ca0  xor     r8d, r8d
0x140016ca3  mov     edx, esi
0x140016ca5  mov     rcx, rbx; FdoExtension
0x140016ca8  call    ClasspInternalSetMediaChangeState
0x140016cad  xor     edx, edx; Wait
0x140016caf  mov     rcx, rdi; Mutex
0x140016cb2  call    cs:__imp_KeReleaseMutex
0x140016cb9  nop     dword ptr [rax+rax+00h]
0x140016cbe  mov     rcx, cs:WPP_GLOBAL_Control
0x140016cc5  cmp     rcx, r13
0x140016cc8  jnz     short loc_140016CDE
0x140016cca  mov     rbx, [rsp+48h+arg_8]
0x140016ccf  mov     rbp, [rsp+48h+arg_10]
0x140016cd4  add     rsp, 30h
0x140016cd8  pop     r13
0x140016cda  pop     rdi
0x140016cdb  pop     rsi
0x140016cdc  retn
0x140016cde  test    dword ptr [rcx+2Ch], 1000h
0x140016ce5  jz      short loc_140016CCA
0x140016ce7  cmp     byte ptr [rcx+29h], 4
0x140016ceb  jb      short loc_140016CCA
0x140016ced  mov     edx, 1Eh
0x140016cf2  jmp     loc_140040D10
0x140016cf7  cmp     byte ptr [rcx+29h], 4
0x140016cfb  jb      loc_140016C4A
0x140016d01  mov     rcx, [rcx+18h]
0x140016d05  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140016d0c  mov     edx, 1Ch
0x140016d11  call    WPP_SF_
0x140016d16  jmp     loc_140016C4A
0x140016d1b  mov     rcx, cs:WPP_GLOBAL_Control
0x140016d22  cmp     rcx, r13
0x140016d25  jz      short loc_140016CCA
0x140016d27  test    dword ptr [rcx+2Ch], 1000h
0x140016d2e  jz      short loc_140016CCA
0x140016d30  cmp     byte ptr [rcx+29h], 3
0x140016d34  jb      short loc_140016CCA
0x140016d36  mov     edx, 1Dh
0x140016d3b  jmp     loc_140040D10
0x140040d10  mov     rcx, [rcx+18h]
0x140040d14  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140040d1b  call    WPP_SF_
0x140040d20  nop
0x140040d21  jmp     loc_140016CCA
```
