# NatFastIoDeviceControl

- ea: `0x1400027d0`
- end: `0x140002b30`
- name: `NatFastIoDeviceControl`
- size: `864`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x1400027d0`
- `0x140002b38`
- `0x1400051e8`
- `0x14000522c`
- `0x14002c8c0`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140002879`
- `ntoskrnl!ProbeForRead` at `0x140002879`
- `ntoskrnl!ExGetPreviousMode` at `0x140002855`
- `ntoskrnl!ExGetPreviousMode` at `0x140002855`
- `ntoskrnl!ExAllocatePool2` at `0x14000295f`
- `ntoskrnl!ExAllocatePool2` at `0x14000295f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400029e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002a3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400029e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002a3d`

## pseudocode

```c
bool __fastcall NatFastIoDeviceControl(
        __int64 a1,
        __int64 a2,
        volatile void *a3,
        unsigned int a4,
        __int64 a5,
        int a6,
        unsigned int a7,
        __int64 a8)
{
  SIZE_T v8; // rbx
  void *Pool2; // rdi
  SIZE_T v12; // rsi
  KPROCESSOR_MODE PreviousMode; // al
  unsigned int v14; // r14d
  unsigned int v15; // eax
  __int64 v16; // r9
  int v17; // ebx
  int *v18; // rcx
  PDEVICE_OBJECT v19; // rcx
  __int64 v20; // rdx
  bool v21; // bl
  unsigned int v23; // [rsp+A8h] [rbp+20h] BYREF

  v8 = a4;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    LOBYTE(a2) = (_BYTE)a2 != 0;
    WPP_SF_dcdd(WPP_GLOBAL_Control->AttachedDevice, a2, a3, a7, (_BYTE)a2, a4, a6);
  }
  v23 = 0;
  if ( (_DWORD)v8 )
  {
    if ( (unsigned int)v8 >= 0x7FFFFFFF )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_bf6394432411365576a648e5337212b4_Traceguids);
      }
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
      {
        return 0;
      }
      v20 = 29;
    }
    else
    {
      v12 = v8;
      Pool2 = (void *)ExAllocatePool2(64, v8, 1330209102);
      if ( Pool2 )
        goto LABEL_7;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_bf6394432411365576a648e5337212b4_Traceguids);
      }
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
      {
        return 0;
      }
      v20 = 27;
    }
    WPP_SF_(v19->AttachedDevice, v20, WPP_bf6394432411365576a648e5337212b4_Traceguids);
    return 0;
  }
  Pool2 = 0;
  v12 = 0;
LABEL_7:
  PreviousMode = ExGetPreviousMode();
  v14 = PreviousMode;
  if ( (_DWORD)v8 )
  {
    if ( PreviousMode )
      ProbeForRead(a3, v12, 1u);
    memmove(Pool2, (const void *)a3, v12);
  }
  v15 = NatpExecuteIoDeviceControl(0, a1, v14, Pool2, v8, a5, a6, a7, &v23);
  v17 = v15;
  if ( v15
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_bf6394432411365576a648e5337212b4_Traceguids, v15);
  }
  if ( v17 < 0 || v17 == 259 )
  {
    v17 = 259;
  }
  else
  {
    v18 = (int *)a8;
    *(_QWORD *)(a8 + 8) = v23;
    *v18 = v17;
  }
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0);
  v21 = v17 != 259;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    LOBYTE(v16) = v21;
    WPP_SF_c(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_bf6394432411365576a648e5337212b4_Traceguids, v16);
  }
  return v21;
}

```

## disassembly

```asm
0x1400027d0  mov     [rsp+arg_0], rbx
0x1400027d5  mov     [rsp+arg_8], rsi
0x1400027da  push    rdi
0x1400027db  push    r12
0x1400027dd  push    r13
0x1400027df  push    r14
0x1400027e1  push    r15
0x1400027e3  sub     rsp, 60h
0x1400027e7  mov     ebx, r9d
0x1400027ea  mov     r15, r8
0x1400027ed  mov     r12, rcx
0x1400027f0  lea     r13, WPP_GLOBAL_Control
0x1400027f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400027fe  cmp     rcx, r13
0x140002801  jz      short loc_140002839
0x140002803  mov     eax, [rcx+2Ch]
0x140002806  test    al, 1
0x140002808  jz      short loc_140002839
0x14000280a  cmp     byte ptr [rcx+29h], 6
0x14000280e  jb      short loc_140002839
0x140002810  test    dl, dl
0x140002812  setnz   dl
0x140002815  mov     eax, [rsp+88h+arg_28]
0x14000281c  mov     [rsp+88h+var_58], eax
0x140002820  mov     dword ptr [rsp+88h+var_60], ebx
0x140002824  mov     byte ptr [rsp+88h+var_68], dl
0x140002828  mov     r9d, [rsp+88h+arg_30]
0x140002830  mov     rcx, [rcx+18h]
0x140002834  call    WPP_SF_dcdd
0x140002839  mov     [rsp+88h+arg_18], 0
0x140002844  test    ebx, ebx
0x140002846  jnz     loc_140002942
0x14000284c  xor     edi, edi
0x14000284e  mov     [rsp+88h+P], rdi
0x140002853  xor     esi, esi
0x140002855  call    cs:__imp_ExGetPreviousMode
0x14000285c  nop     dword ptr [rax+rax+00h]
0x140002861  movsx   r14d, al
0x140002865  test    ebx, ebx
0x140002867  jz      short loc_140002893
0x140002869  test    al, al
0x14000286b  jz      short loc_140002885
0x14000286d  mov     r8d, 1; Alignment
0x140002873  mov     rdx, rsi; Length
0x140002876  mov     rcx, r15; Address
0x140002879  call    cs:__imp_ProbeForRead
0x140002880  nop     dword ptr [rax+rax+00h]
0x140002885  mov     r8, rsi; Size
0x140002888  mov     rdx, r15; Src
0x14000288b  mov     rcx, rdi; void *
0x14000288e  call    memmove
0x140002893  lea     rax, [rsp+88h+arg_18]
0x14000289b  mov     [rsp+88h+var_48], rax
0x1400028a0  mov     eax, [rsp+88h+arg_30]
0x1400028a7  mov     [rsp+88h+var_50], eax
0x1400028ab  mov     eax, [rsp+88h+arg_28]
0x1400028b2  mov     [rsp+88h+var_58], eax
0x1400028b6  mov     rax, [rsp+88h+arg_20]
0x1400028be  mov     [rsp+88h+var_60], rax
0x1400028c3  mov     [rsp+88h+var_68], ebx
0x1400028c7  mov     r9, rdi
0x1400028ca  mov     r8d, r14d
0x1400028cd  mov     rdx, r12
0x1400028d0  xor     ecx, ecx
0x1400028d2  call    NatpExecuteIoDeviceControl
0x1400028d7  mov     ebx, eax
0x1400028d9  mov     [rsp+88h+var_38], eax
0x1400028dd  test    eax, eax
0x1400028df  jz      short loc_140002913
0x1400028e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400028e8  cmp     rcx, r13
0x1400028eb  jz      short loc_140002913
0x1400028ed  mov     edx, [rcx+2Ch]
0x1400028f0  test    dl, 1
0x1400028f3  jz      short loc_140002913
0x1400028f5  cmp     byte ptr [rcx+29h], 2
0x1400028f9  jb      short loc_140002913
0x1400028fb  mov     edx, 1Eh
0x140002900  mov     r9d, eax
0x140002903  lea     r8, WPP_bf6394432411365576a648e5337212b4_Traceguids
0x14000290a  mov     rcx, [rcx+18h]
0x14000290e  call    WPP_SF_d
0x140002913  mov     esi, 103h
0x140002918  test    ebx, ebx
0x14000291a  js      loc_1400029D7
0x140002920  cmp     ebx, esi
0x140002922  jz      loc_1400029D7
0x140002928  mov     eax, [rsp+88h+arg_18]
0x14000292f  mov     rcx, [rsp+88h+arg_38]
0x140002937  mov     [rcx+8], rax
0x14000293b  mov     [rcx], ebx
0x14000293d  jmp     loc_1400029DD
0x140002942  cmp     ebx, 7FFFFFFFh
0x140002948  jnb     loc_140002AB7
0x14000294e  mov     rsi, rbx
0x140002951  mov     r8d, 4F49614Eh
0x140002957  mov     rdx, rbx
0x14000295a  mov     ecx, 40h ; '@'
0x14000295f  call    cs:__imp_ExAllocatePool2
0x140002966  nop     dword ptr [rax+rax+00h]
0x14000296b  mov     rdi, rax
0x14000296e  mov     [rsp+88h+P], rax
0x140002973  test    rax, rax
0x140002976  jnz     loc_140002855
0x14000297c  mov     rcx, cs:WPP_GLOBAL_Control
0x140002983  cmp     rcx, r13
0x140002986  jz      short loc_1400029A8
0x140002988  mov     eax, [rcx+2Ch]
0x14000298b  test    al, 1
0x14000298d  jz      short loc_1400029A8
0x14000298f  cmp     byte ptr [rcx+29h], 2
0x140002993  jb      short loc_1400029A8
0x140002995  lea     edx, [rdi+1Ah]
0x140002998  lea     r8, WPP_bf6394432411365576a648e5337212b4_Traceguids
0x14000299f  mov     rcx, [rcx+18h]
0x1400029a3  call    WPP_SF_
0x1400029a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400029af  cmp     rcx, r13
0x1400029b2  jz      loc_140002B13
0x1400029b8  mov     eax, [rcx+2Ch]
0x1400029bb  test    al, 1
0x1400029bd  jz      loc_140002B13
0x1400029c3  cmp     byte ptr [rcx+29h], 6
0x1400029c7  jb      loc_140002B13
0x1400029cd  mov     edx, 1Bh
0x1400029d2  jmp     loc_140002B03
0x1400029d7  mov     ebx, esi
0x1400029d9  mov     [rsp+88h+var_38], ebx
0x1400029dd  test    rdi, rdi
0x1400029e0  jz      short loc_1400029F3
0x1400029e2  xor     edx, edx; Tag
0x1400029e4  mov     rcx, rdi; P
0x1400029e7  call    cs:__imp_ExFreePoolWithTag
0x1400029ee  nop     dword ptr [rax+rax+00h]
0x1400029f3  cmp     ebx, esi
0x1400029f5  setnz   bl
0x1400029f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400029ff  cmp     rcx, r13
0x140002a02  jz      short loc_140002A2A
0x140002a04  mov     edx, [rcx+2Ch]
0x140002a07  test    dl, 1
0x140002a0a  jz      short loc_140002A2A
0x140002a0c  cmp     byte ptr [rcx+29h], 6
0x140002a10  jb      short loc_140002A2A
0x140002a12  mov     edx, 21h ; '!'
0x140002a17  mov     r9b, bl
0x140002a1a  lea     r8, WPP_bf6394432411365576a648e5337212b4_Traceguids
0x140002a21  mov     rcx, [rcx+18h]
0x140002a25  call    WPP_SF_c
0x140002a2a  mov     al, bl
0x140002a2c  jmp     loc_140002B15
0x140002a31  mov     rcx, [rsp+88h+P]; P
0x140002a36  test    rcx, rcx
0x140002a39  jz      short loc_140002A49
0x140002a3b  xor     edx, edx; Tag
0x140002a3d  call    cs:__imp_ExFreePoolWithTag
0x140002a44  nop     dword ptr [rax+rax+00h]
0x140002a49  lea     rax, WPP_GLOBAL_Control
0x140002a50  mov     rcx, cs:WPP_GLOBAL_Control
0x140002a57  cmp     rcx, rax
0x140002a5a  jz      short loc_140002A7E
0x140002a5c  mov     eax, [rcx+2Ch]
0x140002a5f  test    al, 1
0x140002a61  jz      short loc_140002A7E
0x140002a63  cmp     byte ptr [rcx+29h], 2
0x140002a67  jb      short loc_140002A7E
0x140002a69  mov     edx, 1Fh
0x140002a6e  lea     r8, WPP_bf6394432411365576a648e5337212b4_Traceguids
0x140002a75  mov     rcx, [rcx+18h]
0x140002a79  call    WPP_SF_
0x140002a7e  lea     rax, WPP_GLOBAL_Control
0x140002a85  mov     rcx, cs:WPP_GLOBAL_Control
0x140002a8c  cmp     rcx, rax
0x140002a8f  jz      short loc_140002AB3
0x140002a91  mov     eax, [rcx+2Ch]
0x140002a94  test    al, 1
0x140002a96  jz      short loc_140002AB3
0x140002a98  cmp     byte ptr [rcx+29h], 6
0x140002a9c  jb      short loc_140002AB3
0x140002a9e  mov     edx, 20h ; ' '
0x140002aa3  lea     r8, WPP_bf6394432411365576a648e5337212b4_Traceguids
0x140002aaa  mov     rcx, [rcx+18h]
0x140002aae  call    WPP_SF_
0x140002ab3  xor     al, al
0x140002ab5  jmp     short loc_140002B15
0x140002ab7  mov     rcx, cs:WPP_GLOBAL_Control
0x140002abe  cmp     rcx, r13
0x140002ac1  jz      short loc_140002AE5
0x140002ac3  mov     eax, [rcx+2Ch]
0x140002ac6  test    al, 1
0x140002ac8  jz      short loc_140002AE5
0x140002aca  cmp     byte ptr [rcx+29h], 2
0x140002ace  jb      short loc_140002AE5
0x140002ad0  mov     edx, 1Ch
0x140002ad5  lea     r8, WPP_bf6394432411365576a648e5337212b4_Traceguids
0x140002adc  mov     rcx, [rcx+18h]
0x140002ae0  call    WPP_SF_
0x140002ae5  mov     rcx, cs:WPP_GLOBAL_Control
0x140002aec  cmp     rcx, r13
0x140002aef  jz      short loc_140002B13
0x140002af1  mov     eax, [rcx+2Ch]
0x140002af4  test    al, 1
0x140002af6  jz      short loc_140002B13
0x140002af8  cmp     byte ptr [rcx+29h], 6
0x140002afc  jb      short loc_140002B13
0x140002afe  mov     edx, 1Dh
0x140002b03  lea     r8, WPP_bf6394432411365576a648e5337212b4_Traceguids
0x140002b0a  mov     rcx, [rcx+18h]
0x140002b0e  call    WPP_SF_
0x140002b13  xor     al, al
0x140002b15  lea     r11, [rsp+88h+var_28]
0x140002b1a  mov     rbx, [r11+30h]
0x140002b1e  mov     rsi, [r11+38h]
0x140002b22  mov     rsp, r11
0x140002b25  pop     r15
0x140002b27  pop     r14
0x140002b29  pop     r13
0x140002b2b  pop     r12
0x140002b2d  pop     rdi
0x140002b2e  retn
```
