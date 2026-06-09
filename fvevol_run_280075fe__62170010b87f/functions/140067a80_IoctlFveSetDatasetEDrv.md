# IoctlFveSetDatasetEDrv

- ea: `0x140067a80`
- end: `0x140067d63`
- name: `IoctlFveSetDatasetEDrv`
- size: `739`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140068a40`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x140021a00`
- `0x140021d00`
- `0x140064d8c`
- `0x140065a50`
- `0x140067a80`
- `0x140089574`
- `0x1400da590`
- `0x1400da8d4`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140067b7f`
- `ntoskrnl!ProbeForRead` at `0x140067b7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140067d10`
- `ntoskrnl!ExFreePoolWithTag` at `0x140067d10`
- `ntoskrnl!ExAllocatePool2` at `0x140067b99`
- `ntoskrnl!ExAllocatePool2` at `0x140067b99`

## pseudocode

```c
__int64 __fastcall IoctlFveSetDatasetEDrv(void *a1, __int64 a2)
{
  __int64 v4; // rax
  _BYTE *v5; // r15
  SIZE_T v6; // r13
  _BYTE *v7; // rdi
  int v8; // ebx
  __int64 v9; // r8
  char v10; // r12
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  _BYTE *Pool2; // rax
  __int64 v14; // rcx
  _BYTE *v15; // rax
  _BYTE v17[200]; // [rsp+30h] [rbp-C8h] BYREF

  memset(v17, 0, 0x90u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 87, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids);
  }
  v4 = *(_QWORD *)(a2 + 184);
  v5 = *(_BYTE **)(v4 + 32);
  v6 = *(unsigned int *)(v4 + 16);
  v7 = v5;
  v8 = FveKickAllSystemsGo(a1);
  if ( v8 >= 0 )
  {
    LOBYTE(v9) = 1;
    FvepAcquireDevFveLock(a1, v17, v9);
    v10 = 1;
    if ( !*(_BYTE *)(a2 + 64) )
      goto LABEL_23;
    ProbeForRead(v5, v6, 1u);
    Pool2 = (_BYTE *)ExAllocatePool2(256, v6, 809850438);
    v7 = Pool2;
    if ( Pool2 )
    {
      memmove(Pool2, v5, v6);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          89,
          WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids,
          (unsigned int)v6);
      }
      v8 = -1073741670;
    }
    if ( v8 >= 0 )
    {
LABEL_23:
      v8 = FveApplyDataSetUpdateAndCommitEDrv(a1, v7, (unsigned int)v6);
      FvepReleaseDevFveLock(v17);
      v10 = 0;
      if ( v8 >= 0 )
      {
        v8 = FveEnforceMountAndNotify(a1);
        if ( (v8 & 0xC0000000) == 0xC0000000 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v12 = 91;
            goto LABEL_25;
          }
        }
      }
    }
  }
  else
  {
    v10 = 0;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v12 = 88;
LABEL_25:
      WPP_SF_d(v11->AttachedDevice, v12, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids, (unsigned int)v8);
    }
  }
  if ( v10 )
    FvepReleaseDevFveLock(v17);
  if ( v7 != v5 && v7 )
  {
    v14 = (unsigned int)v6;
    v15 = v7;
    if ( (_DWORD)v6 )
    {
      do
      {
        *v15++ = 0;
        --v14;
      }
      while ( v14 );
    }
    ExFreePoolWithTag(v7, 0x30455646u);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 92, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids, (unsigned int)v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140067a80  mov     [rsp+arg_0], rcx
0x140067a85  push    rbx
0x140067a86  push    rsi
0x140067a87  push    rdi
0x140067a88  push    r12
0x140067a8a  push    r13
0x140067a8c  push    r14
0x140067a8e  push    r15
0x140067a90  sub     rsp, 0C0h
0x140067a97  mov     r14, rdx
0x140067a9a  mov     r12, rcx
0x140067a9d  xor     edx, edx; Val
0x140067a9f  mov     r8d, 90h; Size
0x140067aa5  lea     rcx, [rsp+0F8h+var_C8]; void *
0x140067aaa  call    memset
0x140067aaf  lea     rsi, WPP_GLOBAL_Control
0x140067ab6  mov     rcx, cs:WPP_GLOBAL_Control
0x140067abd  cmp     rcx, rsi
0x140067ac0  jz      short loc_140067AE4
0x140067ac2  mov     eax, [rcx+2Ch]
0x140067ac5  test    al, 10h
0x140067ac7  jz      short loc_140067AE4
0x140067ac9  cmp     byte ptr [rcx+29h], 5
0x140067acd  jb      short loc_140067AE4
0x140067acf  mov     edx, 57h ; 'W'
0x140067ad4  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x140067adb  mov     rcx, [rcx+18h]
0x140067adf  call    WPP_SF_
0x140067ae4  mov     rax, [r14+0B8h]
0x140067aeb  mov     r15, [rax+20h]
0x140067aef  mov     [rsp+0F8h+arg_18], r15
0x140067af7  mov     r13d, [rax+10h]
0x140067afb  mov     [rsp+0F8h+arg_10], r13d
0x140067b03  mov     rdi, r15
0x140067b06  mov     [rsp+0F8h+var_D0], r15
0x140067b0b  xor     edx, edx
0x140067b0d  mov     rcx, r12
0x140067b10  call    FveKickAllSystemsGo
0x140067b15  mov     ebx, eax
0x140067b17  test    eax, eax
0x140067b19  jns     short loc_140067B4D
0x140067b1b  xor     r12b, r12b
0x140067b1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140067b25  cmp     rcx, rsi
0x140067b28  jz      loc_140067CD8
0x140067b2e  mov     eax, [rcx+2Ch]
0x140067b31  test    al, 10h
0x140067b33  jz      loc_140067CD8
0x140067b39  cmp     byte ptr [rcx+29h], 2
0x140067b3d  jb      loc_140067CD8
0x140067b43  mov     edx, 58h ; 'X'
0x140067b48  jmp     loc_140067CC5
0x140067b4d  mov     r8b, 1
0x140067b50  lea     rdx, [rsp+0F8h+var_C8]
0x140067b55  mov     rcx, r12
0x140067b58  call    FvepAcquireDevFveLock
0x140067b5d  mov     r12b, 1
0x140067b60  mov     [rsp+0F8h+arg_8], r12b
0x140067b68  cmp     byte ptr [r14+40h], 0
0x140067b6d  jz      loc_140067C69
0x140067b73  mov     r8d, 1; Alignment
0x140067b79  mov     rdx, r13; Length
0x140067b7c  mov     rcx, r15; Address
0x140067b7f  call    cs:__imp_ProbeForRead
0x140067b86  nop     dword ptr [rax+rax+00h]
0x140067b8b  mov     r8d, 30455646h
0x140067b91  mov     rdx, r13
0x140067b94  mov     ecx, 100h
0x140067b99  call    cs:__imp_ExAllocatePool2
0x140067ba0  nop     dword ptr [rax+rax+00h]
0x140067ba5  mov     rdi, rax
0x140067ba8  mov     [rsp+0F8h+var_D0], rax
0x140067bad  test    rax, rax
0x140067bb0  jnz     short loc_140067BED
0x140067bb2  mov     rcx, cs:WPP_GLOBAL_Control
0x140067bb9  cmp     rcx, rsi
0x140067bbc  jz      short loc_140067BE2
0x140067bbe  mov     edx, [rcx+2Ch]
0x140067bc1  test    dl, 10h
0x140067bc4  jz      short loc_140067BE2
0x140067bc6  cmp     byte ptr [rcx+29h], 2
0x140067bca  jb      short loc_140067BE2
0x140067bcc  lea     edx, [rax+59h]
0x140067bcf  mov     r9d, r13d
0x140067bd2  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x140067bd9  mov     rcx, [rcx+18h]
0x140067bdd  call    WPP_SF_d
0x140067be2  mov     ebx, 0C000009Ah
0x140067be7  mov     [rsp+0F8h+var_D8], ebx
0x140067beb  jmp     short loc_140067BFC
0x140067bed  mov     r8, r13; Size
0x140067bf0  mov     rdx, r15; Src
0x140067bf3  mov     rcx, rax; void *
0x140067bf6  call    memmove
0x140067bfb  nop
0x140067bfc  test    ebx, ebx
0x140067bfe  jns     short loc_140067C69
0x140067c00  jmp     loc_140067CD8
0x140067c05  mov     ebx, eax
0x140067c07  mov     [rsp+0F8h+var_D8], eax
0x140067c0b  lea     rax, WPP_GLOBAL_Control
0x140067c12  mov     rcx, cs:WPP_GLOBAL_Control
0x140067c19  cmp     rcx, rax
0x140067c1c  jz      short loc_140067C43
0x140067c1e  mov     eax, [rcx+2Ch]
0x140067c21  test    al, 10h
0x140067c23  jz      short loc_140067C43
0x140067c25  cmp     byte ptr [rcx+29h], 2
0x140067c29  jb      short loc_140067C43
0x140067c2b  mov     edx, 5Ah ; 'Z'
0x140067c30  mov     r9d, ebx
0x140067c33  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x140067c3a  mov     rcx, [rcx+18h]
0x140067c3e  call    WPP_SF_d
0x140067c43  lea     rsi, WPP_GLOBAL_Control
0x140067c4a  mov     rdi, [rsp+0F8h+var_D0]
0x140067c4f  mov     r12b, [rsp+0F8h+arg_8]
0x140067c57  mov     r15, [rsp+0F8h+arg_18]
0x140067c5f  mov     r13d, [rsp+0F8h+arg_10]
0x140067c67  jmp     short loc_140067CD8
0x140067c69  mov     r8d, r13d
0x140067c6c  mov     rdx, rdi
0x140067c6f  mov     r14, [rsp+0F8h+arg_0]
0x140067c77  mov     rcx, r14
0x140067c7a  call    FveApplyDataSetUpdateAndCommitEDrv
0x140067c7f  mov     ebx, eax
0x140067c81  lea     rcx, [rsp+0F8h+var_C8]
0x140067c86  call    FvepReleaseDevFveLock
0x140067c8b  xor     r12b, r12b
0x140067c8e  test    ebx, ebx
0x140067c90  js      short loc_140067CD8
0x140067c92  mov     rcx, r14
0x140067c95  call    FveEnforceMountAndNotify
0x140067c9a  mov     ebx, eax
0x140067c9c  mov     ecx, 0C0000000h
0x140067ca1  and     eax, ecx
0x140067ca3  cmp     eax, ecx
0x140067ca5  jnz     short loc_140067CD8
0x140067ca7  mov     rcx, cs:WPP_GLOBAL_Control
0x140067cae  cmp     rcx, rsi
0x140067cb1  jz      short loc_140067CD8
0x140067cb3  mov     eax, [rcx+2Ch]
0x140067cb6  test    al, 10h
0x140067cb8  jz      short loc_140067CD8
0x140067cba  cmp     byte ptr [rcx+29h], 2
0x140067cbe  jb      short loc_140067CD8
0x140067cc0  mov     edx, 5Bh ; '['
0x140067cc5  mov     r9d, ebx
0x140067cc8  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x140067ccf  mov     rcx, [rcx+18h]
0x140067cd3  call    WPP_SF_d
0x140067cd8  test    r12b, r12b
0x140067cdb  jz      short loc_140067CE7
0x140067cdd  lea     rcx, [rsp+0F8h+var_C8]
0x140067ce2  call    FvepReleaseDevFveLock
0x140067ce7  cmp     rdi, r15
0x140067cea  jz      short loc_140067D1C
0x140067cec  test    rdi, rdi
0x140067cef  jz      short loc_140067D1C
0x140067cf1  mov     ecx, r13d
0x140067cf4  mov     rax, rdi
0x140067cf7  test    r13d, r13d
0x140067cfa  jz      short loc_140067D08
0x140067cfc  mov     byte ptr [rax], 0
0x140067cff  inc     rax
0x140067d02  sub     rcx, 1
0x140067d06  jnz     short loc_140067CFC
0x140067d08  mov     edx, 30455646h; Tag
0x140067d0d  mov     rcx, rdi; P
0x140067d10  call    cs:__imp_ExFreePoolWithTag
0x140067d17  nop     dword ptr [rax+rax+00h]
0x140067d1c  mov     rcx, cs:WPP_GLOBAL_Control
0x140067d23  cmp     rcx, rsi
0x140067d26  jz      short loc_140067D4D
0x140067d28  mov     eax, [rcx+2Ch]
0x140067d2b  test    al, 10h
0x140067d2d  jz      short loc_140067D4D
0x140067d2f  cmp     byte ptr [rcx+29h], 5
0x140067d33  jb      short loc_140067D4D
0x140067d35  mov     edx, 5Ch ; '\'
0x140067d3a  mov     r9d, ebx
0x140067d3d  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x140067d44  mov     rcx, [rcx+18h]
0x140067d48  call    WPP_SF_d
0x140067d4d  mov     eax, ebx
0x140067d4f  add     rsp, 0C0h
0x140067d56  pop     r15
0x140067d58  pop     r14
0x140067d5a  pop     r13
0x140067d5c  pop     r12
0x140067d5e  pop     rdi
0x140067d5f  pop     rsi
0x140067d60  pop     rbx
0x140067d61  retn
```
