# CscStorepLowIoDisableImplicitTimeUpdates

- ea: `0x14000b5a0`
- end: `0x14000b809`
- name: `CscStorepLowIoDisableImplicitTimeUpdates`
- size: `617`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x14000a884`
- `0x14000aaf0`
- `0x14000b0e0`
- `0x14000b810`
- `0x140016758`
- `0x140054e88`
- `0x1400593dc`
- `0x14005dc84`
- `0x14006c560`

## callees

- `0x14000b5a0`
- `0x14000c5f8`
- `0x140018930`
- `0x14001ac1c`
- `0x14002f010`
- `0x14002f0f0`
- `0x14002f440`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14000b709`
- `ntoskrnl!KeInitializeEvent` at `0x14000b709`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14000b60d`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14000b60d`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000b747`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000b770`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000b747`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000b770`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000b6ce`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000b6ce`
- `ntoskrnl!IoGetStackLimits` at `0x14000b657`
- `ntoskrnl!IoGetStackLimits` at `0x14000b657`

## pseudocode

```c
__int64 __fastcall CscStorepLowIoDisableImplicitTimeUpdates(__int64 a1)
{
  int Blink; // ebx
  NTSTATUS v4; // eax
  BOOLEAN v5; // si
  __int64 v6; // rcx
  struct _KEVENT Parameter; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 HighLimit; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 LowLimit; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v10[18]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v11[2]; // [rsp+F0h] [rbp-10h] BYREF
  __m128i si128; // [rsp+100h] [rbp+0h]
  __int64 v13; // [rsp+110h] [rbp+10h]

  v11[0] = 0;
  v11[1] = 0;
  v13 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  memset(v10, 0, sizeof(v10));
  v10[5] = a1;
  v10[6] = v11;
  v10[7] = 0x400000028LL;
  if ( !KeAreAllApcsDisabled() )
  {
    Parameter.Header.WaitListHead.Blink = 0;
    Parameter.Header.WaitListHead.Flink = (struct _LIST_ENTRY *)v10;
    HighLimit = 0;
    *(_QWORD *)&Parameter.Header.Lock = CscStorepLowIoSetInformationFilePostedRoutine;
    LowLimit = 0;
    IoGetStackLimits(&LowLimit, &HighLimit);
    if ( (unsigned __int64)&HighLimit - LowLimit >= (unsigned int)dword_14003BD20 )
    {
LABEL_3:
      Blink = (*(__int64 (__fastcall **)(struct _LIST_ENTRY *))&Parameter.Header.Lock)(Parameter.Header.WaitListHead.Flink);
      goto LABEL_4;
    }
    v4 = KeExpandKernelStackAndCalloutEx(CscStorepLowIoPost_Callout, &Parameter, 0x6000u, 0, 0);
    if ( v4 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          11,
          WPP_0d06f681978d342119bb40210e69c50f_Traceguids,
          (unsigned int)v4);
      }
      goto LABEL_3;
    }
    Blink = (int)Parameter.Header.WaitListHead.Blink;
LABEL_4:
    if ( Blink >= 0 )
      return (unsigned int)Blink;
    goto LABEL_15;
  }
  memset(&Parameter, 0, sizeof(Parameter));
  KeInitializeEvent(&Parameter, NotificationEvent, 0);
  v10[0] = KeGetCurrentThread();
  v10[2] = CscStorepLowIoSetInformationFilePostedRoutine;
  v10[4] = &Parameter;
  v10[1] = 0;
  LODWORD(v10[3]) = -1;
  v5 = KeSetKernelStackSwapEnable(0);
  Blink = CscStorepLowIoPostWorkItemAndWait(v6, v10, &Parameter);
  if ( v5 )
    KeSetKernelStackSwapEnable(v5);
  if ( Blink >= 0 )
  {
    Blink = v10[3];
    goto LABEL_4;
  }
LABEL_15:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_0d06f681978d342119bb40210e69c50f_Traceguids, a1, Blink);
  return (unsigned int)Blink;
}

```

## disassembly

```asm
0x14000b5a0  mov     [rsp-8+arg_10], rbx
0x14000b5a5  push    rbp
0x14000b5a6  push    rdi
0x14000b5a7  push    r14
0x14000b5a9  lea     rbp, [rsp-20h]
0x14000b5ae  sub     rsp, 120h
0x14000b5b5  mov     rax, cs:__security_cookie
0x14000b5bc  xor     rax, rsp
0x14000b5bf  mov     [rbp+30h+var_18], rax
0x14000b5c3  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14000b5cb  xor     ebx, ebx
0x14000b5cd  mov     rdi, rcx
0x14000b5d0  mov     [rbp+30h+var_40], rbx
0x14000b5d4  lea     rcx, [rsp+130h+var_D0]; void *
0x14000b5d9  mov     [rbp+30h+var_38], rbx
0x14000b5dd  xor     edx, edx; Val
0x14000b5df  mov     [rbp+30h+var_20], rbx
0x14000b5e3  mov     r8d, 90h; Size
0x14000b5e9  movdqu  [rbp+30h+var_30], xmm0
0x14000b5ee  call    memset
0x14000b5f3  lea     rax, [rbp+30h+var_40]
0x14000b5f7  mov     [rbp+30h+var_A8], rdi
0x14000b5fb  mov     [rbp+30h+var_A0], rax
0x14000b5ff  mov     [rbp+30h+var_98], 28h ; '('
0x14000b606  mov     [rbp+30h+var_94], 4
0x14000b60d  call    cs:__imp_KeAreAllApcsDisabled
0x14000b614  nop     dword ptr [rax+rax+00h]
0x14000b619  lea     r14, WPP_GLOBAL_Control
0x14000b620  test    al, al
0x14000b622  jnz     loc_14000B6E8
0x14000b628  lea     rax, [rsp+130h+var_D0]
0x14000b62d  mov     [rsp+130h+var_F0], rbx
0x14000b632  mov     qword ptr [rsp+130h+Parameter+8], rax
0x14000b637  lea     rdx, [rsp+130h+HighLimit]; HighLimit
0x14000b63c  lea     rax, CscStorepLowIoSetInformationFilePostedRoutine
0x14000b643  mov     [rsp+130h+HighLimit], rbx
0x14000b648  lea     rcx, [rsp+130h+LowLimit]; LowLimit
0x14000b64d  mov     qword ptr [rsp+130h+Parameter], rax
0x14000b652  mov     [rsp+130h+LowLimit], rbx
0x14000b657  call    cs:__imp_IoGetStackLimits
0x14000b65e  nop     dword ptr [rax+rax+00h]
0x14000b663  mov     eax, cs:dword_14003BD20
0x14000b669  lea     rcx, [rsp+130h+HighLimit]
0x14000b66e  sub     rcx, [rsp+130h+LowLimit]
0x14000b673  cmp     rcx, rax
0x14000b676  jb      short loc_14000B6B4
0x14000b678  mov     rcx, qword ptr [rsp+130h+Parameter+8]
0x14000b67d  mov     rax, qword ptr [rsp+130h+Parameter]
0x14000b682  call    _guard_dispatch_icall
0x14000b687  mov     ebx, eax
0x14000b689  test    ebx, ebx
0x14000b68b  js      loc_14000B7CB
0x14000b691  mov     eax, ebx
0x14000b693  mov     rcx, [rbp+30h+var_18]
0x14000b697  xor     rcx, rsp; StackCookie
0x14000b69a  call    __security_check_cookie
0x14000b69f  mov     rbx, [rsp+130h+arg_10]
0x14000b6a7  add     rsp, 120h
0x14000b6ae  pop     r14
0x14000b6b0  pop     rdi
0x14000b6b1  pop     rbp
0x14000b6b2  retn
0x14000b6b4  xor     r9d, r9d; Wait
0x14000b6b7  mov     [rsp+130h+Context], rbx; Context
0x14000b6bc  mov     r8d, 6000h; Size
0x14000b6c2  lea     rdx, [rsp+130h+Parameter]; Parameter
0x14000b6c7  lea     rcx, CscStorepLowIoPost_Callout; Callout
0x14000b6ce  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x14000b6d5  nop     dword ptr [rax+rax+00h]
0x14000b6da  test    eax, eax
0x14000b6dc  js      loc_14000B791
0x14000b6e2  mov     ebx, dword ptr [rsp+130h+var_F0]
0x14000b6e6  jmp     short loc_14000B689
0x14000b6e8  xorps   xmm0, xmm0
0x14000b6eb  mov     [rsp+130h+arg_8], rsi
0x14000b6f3  xor     eax, eax
0x14000b6f5  lea     rcx, [rsp+130h+Parameter]; Event
0x14000b6fa  xor     r8d, r8d; State
0x14000b6fd  mov     [rsp+130h+var_F0], rax
0x14000b702  xor     edx, edx; Type
0x14000b704  movups  [rsp+130h+Parameter], xmm0
0x14000b709  call    cs:__imp_KeInitializeEvent
0x14000b710  nop     dword ptr [rax+rax+00h]
0x14000b715  mov     rax, gs:188h
0x14000b71e  xor     ecx, ecx; Enable
0x14000b720  mov     [rsp+130h+var_D0], rax
0x14000b725  lea     rax, CscStorepLowIoSetInformationFilePostedRoutine
0x14000b72c  mov     [rsp+130h+var_C0], rax
0x14000b731  lea     rax, [rsp+130h+Parameter]
0x14000b736  mov     [rbp+30h+var_B0], rax
0x14000b73a  mov     [rsp+130h+var_C8], rbx
0x14000b73f  mov     [rsp+130h+var_B8], 0FFFFFFFFh
0x14000b747  call    cs:__imp_KeSetKernelStackSwapEnable
0x14000b74e  nop     dword ptr [rax+rax+00h]
0x14000b753  lea     r8, [rsp+130h+Parameter]
0x14000b758  movzx   esi, al
0x14000b75b  lea     rdx, [rsp+130h+var_D0]
0x14000b760  call    CscStorepLowIoPostWorkItemAndWait
0x14000b765  mov     ebx, eax
0x14000b767  test    sil, sil
0x14000b76a  jz      short loc_14000B77C
0x14000b76c  movzx   ecx, sil; Enable
0x14000b770  call    cs:__imp_KeSetKernelStackSwapEnable
0x14000b777  nop     dword ptr [rax+rax+00h]
0x14000b77c  mov     rsi, [rsp+130h+arg_8]
0x14000b784  test    ebx, ebx
0x14000b786  js      short loc_14000B7CB
0x14000b788  mov     ebx, [rsp+130h+var_B8]
0x14000b78c  jmp     loc_14000B689
0x14000b791  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b798  cmp     rcx, r14
0x14000b79b  jz      loc_14000B678
0x14000b7a1  test    dword ptr [rcx+2Ch], 40000h
0x14000b7a8  jz      loc_14000B678
0x14000b7ae  mov     rcx, [rcx+18h]
0x14000b7b2  lea     r8, WPP_0d06f681978d342119bb40210e69c50f_Traceguids
0x14000b7b9  mov     edx, 0Bh
0x14000b7be  mov     r9d, eax
0x14000b7c1  call    WPP_SF_d
0x14000b7c6  jmp     loc_14000B678
0x14000b7cb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b7d2  cmp     rcx, r14
0x14000b7d5  jz      loc_14000B691
0x14000b7db  test    dword ptr [rcx+2Ch], 20000h
0x14000b7e2  jz      loc_14000B691
0x14000b7e8  mov     rcx, [rcx+18h]
0x14000b7ec  lea     r8, WPP_0d06f681978d342119bb40210e69c50f_Traceguids
0x14000b7f3  mov     edx, 2Dh ; '-'
0x14000b7f8  mov     dword ptr [rsp+130h+Context], ebx
0x14000b7fc  mov     r9, rdi
0x14000b7ff  call    WPP_SF_qD
0x14000b804  jmp     loc_14000B691
```
