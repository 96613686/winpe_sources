# ClasspSetMediaChangeStateEx

- ea: `0x140016d50`
- end: `0x140016e98`
- name: `ClasspSetMediaChangeStateEx`
- size: `328`
- prototype: `__int64 __fastcall(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400084b0`
- `0x140014aa0`
- `0x140021c78`

## callees

- `0x140016d50`
- `0x140016ea0`
- `0x14001feac`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140016e06`
- `ntoskrnl!KeReleaseMutex` at `0x140016e06`
- `ntoskrnl!KeWaitForSingleObject` at `0x140016ddc`
- `ntoskrnl!KeWaitForSingleObject` at `0x140016ddc`

## pseudocode

```c
void __fastcall ClasspSetMediaChangeStateEx(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension, int a2, char a3)
{
  _MEDIA_CHANGE_DETECTION_INFO *MediaChangeDetectionInfo; // rdi
  union _LARGE_INTEGER *Timeout; // rcx
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // [rsp+60h] [rbp+8h] BYREF

  MediaChangeDetectionInfo = FdoExtension->MediaChangeDetectionInfo;
  v10 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids);
  }
  if ( a2 == 2 )
  {
    FdoExtension->FailurePredicted = 0;
    FdoExtension->FailureReason = 0;
  }
  v10 = 0;
  if ( MediaChangeDetectionInfo )
  {
    Timeout = (union _LARGE_INTEGER *)&v10;
    if ( a3 == 1 )
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
      ClasspInternalSetMediaChangeState(FdoExtension);
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
0x140016d50  mov     [rsp+arg_8], rbx
0x140016d55  mov     [rsp+arg_10], rbp
0x140016d5a  push    rsi
0x140016d5b  push    rdi
0x140016d5c  push    r12
0x140016d5e  push    r14
0x140016d60  push    r15
0x140016d62  sub     rsp, 30h
0x140016d66  mov     rdi, [rcx+288h]
0x140016d6d  xor     r15d, r15d
0x140016d70  mov     [rsp+58h+arg_0], r15
0x140016d75  movzx   ebp, r9b
0x140016d79  movzx   r14d, r8b
0x140016d7d  mov     esi, edx
0x140016d7f  mov     rbx, rcx
0x140016d82  mov     rcx, cs:WPP_GLOBAL_Control
0x140016d89  lea     r12, WPP_GLOBAL_Control
0x140016d90  cmp     rcx, r12
0x140016d93  jz      short loc_140016DA2
0x140016d95  test    dword ptr [rcx+2Ch], 1000h
0x140016d9c  jnz     loc_140016E4F
0x140016da2  cmp     esi, 2
0x140016da5  jnz     short loc_140016DB5
0x140016da7  mov     [rbx+333h], r15b
0x140016dae  mov     [rbx+334h], r15d
0x140016db5  mov     [rsp+58h+arg_0], r15
0x140016dba  test    rdi, rdi
0x140016dbd  jz      short loc_140016E1E
0x140016dbf  cmp     r14b, 1
0x140016dc3  lea     rcx, [rsp+58h+arg_0]
0x140016dc8  cmovz   rcx, r15
0x140016dcc  xor     r9d, r9d; Alertable
0x140016dcf  mov     [rsp+58h+Timeout], rcx; Timeout
0x140016dd4  xor     r8d, r8d; WaitMode
0x140016dd7  mov     rcx, rdi; Object
0x140016dda  xor     edx, edx; WaitReason
0x140016ddc  call    cs:__imp_KeWaitForSingleObject
0x140016de3  nop     dword ptr [rax+rax+00h]
0x140016de8  cmp     eax, 102h
0x140016ded  jz      loc_140016E73
0x140016df3  movzx   r8d, bpl
0x140016df7  mov     edx, esi
0x140016df9  mov     rcx, rbx; FdoExtension
0x140016dfc  call    ClasspInternalSetMediaChangeState
0x140016e01  xor     edx, edx; Wait
0x140016e03  mov     rcx, rdi; Mutex
0x140016e06  call    cs:__imp_KeReleaseMutex
0x140016e0d  nop     dword ptr [rax+rax+00h]
0x140016e12  mov     rcx, cs:WPP_GLOBAL_Control
0x140016e19  cmp     rcx, r12
0x140016e1c  jnz     short loc_140016E36
0x140016e1e  mov     rbx, [rsp+58h+arg_8]
0x140016e23  mov     rbp, [rsp+58h+arg_10]
0x140016e28  add     rsp, 30h
0x140016e2c  pop     r15
0x140016e2e  pop     r14
0x140016e30  pop     r12
0x140016e32  pop     rdi
0x140016e33  pop     rsi
0x140016e34  retn
0x140016e36  test    dword ptr [rcx+2Ch], 1000h
0x140016e3d  jz      short loc_140016E1E
0x140016e3f  cmp     byte ptr [rcx+29h], 4
0x140016e43  jb      short loc_140016E1E
0x140016e45  mov     edx, 1Eh
0x140016e4a  jmp     loc_140040D26
0x140016e4f  cmp     byte ptr [rcx+29h], 4
0x140016e53  jb      loc_140016DA2
0x140016e59  mov     rcx, [rcx+18h]
0x140016e5d  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140016e64  mov     edx, 1Ch
0x140016e69  call    WPP_SF_
0x140016e6e  jmp     loc_140016DA2
0x140016e73  mov     rcx, cs:WPP_GLOBAL_Control
0x140016e7a  cmp     rcx, r12
0x140016e7d  jz      short loc_140016E1E
0x140016e7f  test    dword ptr [rcx+2Ch], 1000h
0x140016e86  jz      short loc_140016E1E
0x140016e88  cmp     byte ptr [rcx+29h], 3
0x140016e8c  jb      short loc_140016E1E
0x140016e8e  mov     edx, 1Dh
0x140016e93  jmp     loc_140040D26
0x140040d26  mov     rcx, [rcx+18h]
0x140040d2a  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140040d31  call    WPP_SF_
0x140040d36  nop
0x140040d37  jmp     loc_140016E1E
```
