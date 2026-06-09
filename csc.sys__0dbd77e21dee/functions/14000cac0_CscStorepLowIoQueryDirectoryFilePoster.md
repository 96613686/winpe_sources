# CscStorepLowIoQueryDirectoryFilePoster

- ea: `0x14000cac0`
- end: `0x14000ccb8`
- name: `CscStorepLowIoQueryDirectoryFilePoster`
- size: `504`
- prototype: `__int64 __fastcall(int, int, int, int, char, unsigned __int64 LowLimit, char, __int64)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x140029444`
- `0x14005c0ec`
- `0x14005e5c4`
- `0x1400724d0`
- `0x14008c4d0`

## callees

- `0x14000c5f8`
- `0x14000cac0`
- `0x140018930`
- `0x14002f0f0`
- `0x14002f440`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14000cbea`
- `ntoskrnl!KeInitializeEvent` at `0x14000cbea`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14000cb1d`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14000cb1d`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000cc26`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000cc4e`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000cc26`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000cc4e`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000cbb7`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000cbb7`
- `ntoskrnl!IoGetStackLimits` at `0x14000cb5f`
- `ntoskrnl!IoGetStackLimits` at `0x14000cb5f`

## pseudocode

```c
__int64 __fastcall CscStorepLowIoQueryDirectoryFilePoster(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        char a5,
        unsigned __int64 LowLimit,
        char a7,
        __int64 a8)
{
  NTSTATUS v13; // eax
  BOOLEAN v14; // di
  __int64 v15; // rcx
  int v16; // ebx
  struct _KEVENT Parameter; // [rsp+30h] [rbp-99h] BYREF
  unsigned __int64 HighLimit; // [rsp+48h] [rbp-81h] BYREF
  _QWORD v19[22]; // [rsp+50h] [rbp-79h] BYREF

  memset(v19, 0, 0x90u);
  LOBYTE(v19[8]) = a5;
  v19[9] = LowLimit;
  LOBYTE(v19[10]) = a7;
  v19[11] = a8;
  v19[5] = a1;
  v19[6] = a2;
  v19[7] = __PAIR64__(a4, a3);
  if ( KeAreAllApcsDisabled() )
  {
    memset(&Parameter, 0, sizeof(Parameter));
    KeInitializeEvent(&Parameter, NotificationEvent, 0);
    v19[0] = KeGetCurrentThread();
    v19[1] = 0;
    v19[2] = CscStorepLowIoQueryDirectoryFilePostedRoutine;
    v19[4] = &Parameter;
    LODWORD(v19[3]) = -1;
    v14 = KeSetKernelStackSwapEnable(0);
    v16 = CscStorepLowIoPostWorkItemAndWait(v15, v19, &Parameter);
    if ( v14 )
      KeSetKernelStackSwapEnable(v14);
    if ( v16 < 0 )
      return (unsigned int)v16;
    else
      return LODWORD(v19[3]);
  }
  else
  {
    Parameter.Header.WaitListHead.Flink = (struct _LIST_ENTRY *)v19;
    Parameter.Header.WaitListHead.Blink = 0;
    *(_QWORD *)&Parameter.Header.Lock = CscStorepLowIoQueryDirectoryFilePostedRoutine;
    HighLimit = 0;
    LowLimit = 0;
    IoGetStackLimits(&LowLimit, &HighLimit);
    if ( (unsigned __int64)&v19[-1] - LowLimit >= (unsigned int)dword_14003BD20 )
      return (*(__int64 (__fastcall **)(struct _LIST_ENTRY *))&Parameter.Header.Lock)(Parameter.Header.WaitListHead.Flink);
    v13 = KeExpandKernelStackAndCalloutEx(CscStorepLowIoPost_Callout, &Parameter, 0x6000u, 0, 0);
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          11,
          WPP_0d06f681978d342119bb40210e69c50f_Traceguids,
          (unsigned int)v13);
      }
      return (*(__int64 (__fastcall **)(struct _LIST_ENTRY *))&Parameter.Header.Lock)(Parameter.Header.WaitListHead.Flink);
    }
    return LODWORD(Parameter.Header.WaitListHead.Blink);
  }
}

```

## disassembly

```asm
0x14000cac0  push    rbp
0x14000cac2  push    rbx
0x14000cac3  push    rsi
0x14000cac4  push    rdi
0x14000cac5  push    r14
0x14000cac7  lea     rbp, [rsp-17h]
0x14000cacc  sub     rsp, 0E0h
0x14000cad3  mov     esi, r8d
0x14000cad6  mov     rdi, rdx
0x14000cad9  mov     rbx, rcx
0x14000cadc  xor     edx, edx; Val
0x14000cade  mov     r8d, 90h; Size
0x14000cae4  lea     rcx, [rbp+37h+var_B0]; void *
0x14000cae8  mov     r14d, r9d
0x14000caeb  call    memset
0x14000caf0  movzx   eax, [rbp+37h+arg_20]
0x14000caf4  mov     [rbp+37h+var_70], al
0x14000caf7  mov     rax, [rbp+37h+LowLimit]
0x14000cafb  mov     [rbp+37h+var_68], rax
0x14000caff  movzx   eax, [rbp+37h+arg_30]
0x14000cb03  mov     [rbp+37h+var_60], al
0x14000cb06  mov     rax, [rbp+37h+arg_38]
0x14000cb0a  mov     [rbp+37h+var_58], rax
0x14000cb0e  mov     [rbp+37h+var_88], rbx
0x14000cb12  mov     [rbp+37h+var_80], rdi
0x14000cb16  mov     [rbp+37h+var_78], esi
0x14000cb19  mov     [rbp+37h+var_74], r14d
0x14000cb1d  call    cs:__imp_KeAreAllApcsDisabled
0x14000cb24  nop     dword ptr [rax+rax+00h]
0x14000cb29  test    al, al
0x14000cb2b  jnz     loc_14000CBD1
0x14000cb31  xor     ebx, ebx
0x14000cb33  lea     rax, [rbp+37h+var_B0]
0x14000cb37  mov     qword ptr [rsp+100h+Parameter+8], rax
0x14000cb3c  lea     rdx, [rsp+100h+HighLimit]; HighLimit
0x14000cb41  lea     rax, CscStorepLowIoQueryDirectoryFilePostedRoutine
0x14000cb48  mov     [rsp+100h+var_C0], rbx
0x14000cb4d  lea     rcx, [rbp+37h+LowLimit]; LowLimit
0x14000cb51  mov     qword ptr [rsp+100h+Parameter], rax
0x14000cb56  mov     [rsp+100h+HighLimit], rbx
0x14000cb5b  mov     [rbp+37h+LowLimit], rbx
0x14000cb5f  call    cs:__imp_IoGetStackLimits
0x14000cb66  nop     dword ptr [rax+rax+00h]
0x14000cb6b  mov     eax, cs:dword_14003BD20
0x14000cb71  lea     rcx, [rsp+100h+HighLimit]
0x14000cb76  sub     rcx, [rbp+37h+LowLimit]
0x14000cb7a  cmp     rcx, rax
0x14000cb7d  jb      short loc_14000CB9D
0x14000cb7f  mov     rcx, qword ptr [rsp+100h+Parameter+8]
0x14000cb84  mov     rax, qword ptr [rsp+100h+Parameter]
0x14000cb89  call    _guard_dispatch_icall
0x14000cb8e  add     rsp, 0E0h
0x14000cb95  pop     r14
0x14000cb97  pop     rdi
0x14000cb98  pop     rsi
0x14000cb99  pop     rbx
0x14000cb9a  pop     rbp
0x14000cb9b  retn
0x14000cb9d  xor     r9d, r9d; Wait
0x14000cba0  mov     [rsp+100h+Context], rbx; Context
0x14000cba5  mov     r8d, 6000h; Size
0x14000cbab  lea     rdx, [rsp+100h+Parameter]; Parameter
0x14000cbb0  lea     rcx, CscStorepLowIoPost_Callout; Callout
0x14000cbb7  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x14000cbbe  nop     dword ptr [rax+rax+00h]
0x14000cbc3  test    eax, eax
0x14000cbc5  js      loc_14000CC77
0x14000cbcb  mov     eax, dword ptr [rsp+100h+var_C0]
0x14000cbcf  jmp     short loc_14000CB8E
0x14000cbd1  xorps   xmm0, xmm0
0x14000cbd4  lea     rcx, [rsp+100h+Parameter]; Event
0x14000cbd9  xor     eax, eax
0x14000cbdb  xor     r8d, r8d; State
0x14000cbde  xor     edx, edx; Type
0x14000cbe0  mov     [rsp+100h+var_C0], rax
0x14000cbe5  movups  [rsp+100h+Parameter], xmm0
0x14000cbea  call    cs:__imp_KeInitializeEvent
0x14000cbf1  nop     dword ptr [rax+rax+00h]
0x14000cbf6  mov     rax, gs:188h
0x14000cbff  xor     ebx, ebx
0x14000cc01  mov     [rbp+37h+var_B0], rax
0x14000cc05  xor     ecx, ecx; Enable
0x14000cc07  lea     rax, CscStorepLowIoQueryDirectoryFilePostedRoutine
0x14000cc0e  mov     [rbp+37h+var_A8], rbx
0x14000cc12  mov     [rbp+37h+var_A0], rax
0x14000cc16  lea     rax, [rsp+100h+Parameter]
0x14000cc1b  mov     [rbp+37h+var_90], rax
0x14000cc1f  mov     [rbp+37h+var_98], 0FFFFFFFFh
0x14000cc26  call    cs:__imp_KeSetKernelStackSwapEnable
0x14000cc2d  nop     dword ptr [rax+rax+00h]
0x14000cc32  lea     r8, [rsp+100h+Parameter]
0x14000cc37  movzx   edi, al
0x14000cc3a  lea     rdx, [rbp+37h+var_B0]
0x14000cc3e  call    CscStorepLowIoPostWorkItemAndWait
0x14000cc43  mov     ebx, eax
0x14000cc45  test    dil, dil
0x14000cc48  jz      short loc_14000CC5A
0x14000cc4a  movzx   ecx, dil; Enable
0x14000cc4e  call    cs:__imp_KeSetKernelStackSwapEnable
0x14000cc55  nop     dword ptr [rax+rax+00h]
0x14000cc5a  test    ebx, ebx
0x14000cc5c  js      short loc_14000CC70
0x14000cc5e  mov     eax, [rbp+37h+var_98]
0x14000cc61  add     rsp, 0E0h
0x14000cc68  pop     r14
0x14000cc6a  pop     rdi
0x14000cc6b  pop     rsi
0x14000cc6c  pop     rbx
0x14000cc6d  pop     rbp
0x14000cc6e  retn
0x14000cc70  mov     eax, ebx
0x14000cc72  jmp     loc_14000CB8E
0x14000cc77  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cc7e  lea     rdx, WPP_GLOBAL_Control
0x14000cc85  cmp     rcx, rdx
0x14000cc88  jz      loc_14000CB7F
0x14000cc8e  test    dword ptr [rcx+2Ch], 40000h
0x14000cc95  jz      loc_14000CB7F
0x14000cc9b  mov     rcx, [rcx+18h]
0x14000cc9f  lea     r8, WPP_0d06f681978d342119bb40210e69c50f_Traceguids
0x14000cca6  mov     edx, 0Bh
0x14000ccab  mov     r9d, eax
0x14000ccae  call    WPP_SF_d
0x14000ccb3  jmp     loc_14000CB7F
```
