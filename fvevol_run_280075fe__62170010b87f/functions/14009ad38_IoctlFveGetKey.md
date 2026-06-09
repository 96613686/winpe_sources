# IoctlFveGetKey

- ea: `0x14009ad38`
- end: `0x14009b0a4`
- name: `IoctlFveGetKey`
- size: `876`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x140068a40`

## callees

- `0x140005e50`
- `0x140006160`
- `0x140007efc`
- `0x140008dc0`
- `0x140008e44`
- `0x1400218f0`
- `0x140021d00`
- `0x14005164c`
- `0x140089574`
- `0x14009ad38`
- `0x1400da590`
- `0x1400da8d4`
- `0x1400de20c`
- `0x1400e614c`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x14009aeb3`
- `ntoskrnl!ProbeForWrite` at `0x14009aeb3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009affe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009b03e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009affe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009b03e`
- `ntoskrnl!ExAllocatePool2` at `0x14009af19`
- `ntoskrnl!ExAllocatePool2` at `0x14009af19`

## pseudocode

```c
__int64 __fastcall IoctlFveGetKey(__int64 a1, __int64 a2, char a3)
{
  __int64 v6; // rax
  SIZE_T v7; // rsi
  unsigned __int16 *v8; // r14
  signed int v9; // ebx
  __int64 v10; // rcx
  signed int FvekDatumFromVmk; // eax
  char v12; // al
  void *v13; // r12
  void *Pool2; // r15
  PVOID v15; // r8
  __int64 v16; // rcx
  _BYTE *v17; // rax
  unsigned __int16 v19[2]; // [rsp+30h] [rbp-E8h] BYREF
  char v20; // [rsp+34h] [rbp-E4h]
  int v21; // [rsp+38h] [rbp-E0h]
  int v22; // [rsp+3Ch] [rbp-DCh]
  unsigned __int16 *v23; // [rsp+40h] [rbp-D8h] BYREF
  volatile void *Address; // [rsp+48h] [rbp-D0h]
  PVOID P; // [rsp+50h] [rbp-C8h] BYREF
  PVOID v26; // [rsp+58h] [rbp-C0h]
  _BYTE v27[144]; // [rsp+60h] [rbp-B8h] BYREF

  memset(v27, 0, sizeof(v27));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 93, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids);
  }
  Address = *(volatile void **)(a2 + 112);
  v6 = *(_QWORD *)(a2 + 184);
  v7 = *(unsigned int *)(v6 + 8);
  v22 = *(_DWORD *)(v6 + 8);
  v19[0] = 0;
  P = 0;
  v8 = 0;
  v23 = 0;
  v26 = 0;
  v9 = FveKickAllSystemsGo((PVOID)a1);
  if ( v9 < 0 )
    goto LABEL_38;
  if ( *(_BYTE *)(a2 + 64) && a3 )
  {
    v9 = -1073741808;
LABEL_38:
    v12 = 0;
    goto LABEL_39;
  }
  FvepAcquireDevFveLock(a1, v27, 0);
  v20 = 1;
  v10 = *(_QWORD *)(a1 + 1016);
  if ( v10 )
  {
    if ( a3 )
    {
      v9 = FveDuplicateInformation(a1, &P);
      if ( v9 < 0 )
        goto LABEL_15;
      FvekDatumFromVmk = GetFvekDatumFromVmk((char *)P + 64, *(_QWORD *)(a1 + 1016), &v23);
    }
    else
    {
      FvekDatumFromVmk = FveDatumDuplicate(v10, &v23);
    }
    v8 = v23;
    v9 = FvekDatumFromVmk;
  }
LABEL_15:
  if ( v9 < 0 )
  {
LABEL_18:
    v12 = 1;
    goto LABEL_39;
  }
  if ( !v8 )
  {
    v9 = ((*(_DWORD *)(a1 + 808) & 0x40) == 0) | 0xC0210000;
    goto LABEL_18;
  }
  v13 = (void *)Address;
  if ( *(_BYTE *)(a2 + 64) && (_DWORD)v7 )
    ProbeForWrite(Address, v7, 2u);
  if ( (unsigned int)v7 < 8 || (unsigned int)v7 >= *v8 )
  {
    if ( (unsigned int)v7 > 0xFFFF )
      LODWORD(v7) = 0xFFFF;
    v22 = v7;
    Pool2 = (void *)ExAllocatePool2(256, (unsigned int)v7, 809850438);
    v26 = Pool2;
    if ( !Pool2 )
    {
      v9 = -1073741670;
      v21 = -1073741670;
      v12 = 1;
      goto LABEL_39;
    }
    v9 = FveDatumCopy((_DWORD)Pool2, (unsigned __int16)v7, 0, (_DWORD)v8, (__int64)v19);
    v21 = v9;
    if ( v9 < 0 )
    {
      v12 = 1;
      goto LABEL_39;
    }
    if ( *(_BYTE *)(a2 + 64) )
      RtlCopyToUser(v13, Pool2, v19[0]);
    else
      RtlCopyVolatileMemory(v13, Pool2, v19[0]);
  }
  else
  {
    if ( *(_BYTE *)(a2 + 64) )
      RtlCopyToUser(v13, v8, 8u);
    else
      RtlCopyVolatileMemory(v13, v8, 8u);
    v19[0] = 8;
    v9 = -2147483643;
    v21 = -2147483643;
  }
  v12 = 1;
LABEL_39:
  if ( v12 )
    FvepReleaseDevFveLock(v27);
  if ( P )
    ExFreePoolWithTag(P, 0x30455646u);
  if ( v8 )
    FveDatumFree(v8);
  v15 = v26;
  if ( v26 )
  {
    v16 = (unsigned int)v7;
    v17 = v26;
    if ( (_DWORD)v7 )
    {
      do
      {
        *v17++ = 0;
        --v16;
      }
      while ( v16 );
    }
    ExFreePoolWithTag(v15, 0x30455646u);
  }
  *(_QWORD *)(a2 + 56) = v19[0];
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 94, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids, (unsigned int)v9);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14009ad38  mov     [rsp+arg_0], rbx
0x14009ad3d  mov     [rsp+arg_10], rsi
0x14009ad42  mov     [rsp+arg_8], rdx
0x14009ad47  push    rdi
0x14009ad48  push    r12
0x14009ad4a  push    r13
0x14009ad4c  push    r14
0x14009ad4e  push    r15
0x14009ad50  sub     rsp, 0F0h
0x14009ad57  mov     r12b, r8b
0x14009ad5a  mov     r13, rdx
0x14009ad5d  mov     r15, rcx
0x14009ad60  xor     edx, edx; Val
0x14009ad62  mov     r8d, 90h; Size
0x14009ad68  lea     rcx, [rsp+118h+var_B8]; void *
0x14009ad6d  call    memset
0x14009ad72  lea     rax, WPP_GLOBAL_Control
0x14009ad79  mov     rcx, cs:WPP_GLOBAL_Control
0x14009ad80  cmp     rcx, rax
0x14009ad83  jz      short loc_14009ADA7
0x14009ad85  mov     eax, [rcx+2Ch]
0x14009ad88  test    al, 10h
0x14009ad8a  jz      short loc_14009ADA7
0x14009ad8c  cmp     byte ptr [rcx+29h], 5
0x14009ad90  jb      short loc_14009ADA7
0x14009ad92  mov     edx, 5Dh ; ']'
0x14009ad97  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x14009ad9e  mov     rcx, [rcx+18h]
0x14009ada2  call    WPP_SF_
0x14009ada7  mov     rax, [r13+70h]
0x14009adab  mov     [rsp+118h+Address], rax
0x14009adb0  mov     rax, [r13+0B8h]
0x14009adb7  mov     esi, [rax+8]
0x14009adba  mov     [rsp+118h+var_DC], esi
0x14009adbe  xor     edi, edi
0x14009adc0  mov     [rsp+118h+var_E8], di
0x14009adc5  mov     [rsp+118h+P], rdi
0x14009adca  mov     r14d, edi
0x14009adcd  mov     [rsp+118h+var_D8], rdi
0x14009add2  mov     [rsp+118h+var_C0], rdi
0x14009add7  xor     edx, edx
0x14009add9  mov     rcx, r15
0x14009addc  call    FveKickAllSystemsGo
0x14009ade1  mov     ebx, eax
0x14009ade3  test    eax, eax
0x14009ade5  js      loc_14009AFD7
0x14009adeb  cmp     [r13+40h], dil
0x14009adef  jz      short loc_14009AE00
0x14009adf1  test    r12b, r12b
0x14009adf4  jz      short loc_14009AE00
0x14009adf6  mov     ebx, 0C0000010h
0x14009adfb  jmp     loc_14009AFD7
0x14009ae00  xor     r8d, r8d
0x14009ae03  lea     rdx, [rsp+118h+var_B8]
0x14009ae08  mov     rcx, r15
0x14009ae0b  call    FvepAcquireDevFveLock
0x14009ae10  mov     al, 1
0x14009ae12  mov     [rsp+118h+arg_18], al
0x14009ae19  mov     [rsp+118h+var_E4], al
0x14009ae1d  mov     rcx, [r15+3F8h]
0x14009ae24  test    rcx, rcx
0x14009ae27  jz      short loc_14009AE6E
0x14009ae29  test    r12b, r12b
0x14009ae2c  jz      short loc_14009AE5D
0x14009ae2e  lea     rdx, [rsp+118h+P]
0x14009ae33  mov     rcx, r15
0x14009ae36  call    FveDuplicateInformation
0x14009ae3b  mov     ebx, eax
0x14009ae3d  test    eax, eax
0x14009ae3f  js      short loc_14009AE6E
0x14009ae41  mov     rcx, [rsp+118h+P]
0x14009ae46  add     rcx, 40h ; '@'
0x14009ae4a  lea     r8, [rsp+118h+var_D8]
0x14009ae4f  mov     rdx, [r15+3F8h]
0x14009ae56  call    GetFvekDatumFromVmk
0x14009ae5b  jmp     short loc_14009AE67
0x14009ae5d  lea     rdx, [rsp+118h+var_D8]
0x14009ae62  call    FveDatumDuplicate
0x14009ae67  mov     r14, [rsp+118h+var_D8]
0x14009ae6c  mov     ebx, eax
0x14009ae6e  test    ebx, ebx
0x14009ae70  js      short loc_14009AE8C
0x14009ae72  test    r14, r14
0x14009ae75  jnz     short loc_14009AE98
0x14009ae77  mov     ebx, [r15+328h]
0x14009ae7e  shr     ebx, 6
0x14009ae81  not     ebx
0x14009ae83  and     ebx, 1
0x14009ae86  or      ebx, 0C0210000h
0x14009ae8c  mov     al, [rsp+118h+arg_18]
0x14009ae93  jmp     loc_14009AFDA
0x14009ae98  mov     r12, [rsp+118h+Address]
0x14009ae9d  cmp     [r13+40h], dil
0x14009aea1  jz      short loc_14009AEBF
0x14009aea3  test    esi, esi
0x14009aea5  jz      short loc_14009AEBF
0x14009aea7  mov     rdx, rsi; Length
0x14009aeaa  mov     r8d, 2; Alignment
0x14009aeb0  mov     rcx, r12; Address
0x14009aeb3  call    cs:__imp_ProbeForWrite
0x14009aeba  nop     dword ptr [rax+rax+00h]
0x14009aebf  mov     ebx, 8
0x14009aec4  cmp     esi, ebx
0x14009aec6  jb      short loc_14009AEFE
0x14009aec8  movzx   eax, word ptr [r14]
0x14009aecc  cmp     esi, eax
0x14009aece  jnb     short loc_14009AEFE
0x14009aed0  mov     r8d, ebx; Size
0x14009aed3  mov     rdx, r14; Src
0x14009aed6  mov     rcx, r12; void *
0x14009aed9  cmp     [r13+40h], dil
0x14009aedd  jz      short loc_14009AEE6
0x14009aedf  call    RtlCopyToUser
0x14009aee4  jmp     short loc_14009AEEB
0x14009aee6  call    RtlCopyVolatileMemory
0x14009aeeb  mov     [rsp+118h+var_E8], bx
0x14009aef0  mov     ebx, 80000005h
0x14009aef5  mov     [rsp+118h+var_E0], ebx
0x14009aef9  jmp     loc_14009AFA1
0x14009aefe  mov     eax, 0FFFFh
0x14009af03  cmp     esi, eax
0x14009af05  cmova   esi, eax
0x14009af08  mov     [rsp+118h+var_DC], esi
0x14009af0c  mov     edx, esi
0x14009af0e  mov     ecx, 100h
0x14009af13  mov     r8d, 30455646h
0x14009af19  call    cs:__imp_ExAllocatePool2
0x14009af20  nop     dword ptr [rax+rax+00h]
0x14009af25  mov     r15, rax
0x14009af28  mov     [rsp+118h+var_C0], rax
0x14009af2d  test    rax, rax
0x14009af30  jnz     short loc_14009AF4E
0x14009af32  mov     ebx, 0C000009Ah
0x14009af37  mov     [rsp+118h+var_E0], ebx
0x14009af3b  mov     al, [rsp+118h+arg_18]
0x14009af42  lea     r15, WPP_GLOBAL_Control
0x14009af49  jmp     loc_14009AFE1
0x14009af4e  xor     r8d, r8d
0x14009af51  lea     rax, [rsp+118h+var_E8]
0x14009af56  mov     [rsp+118h+var_F8], rax
0x14009af5b  mov     r9, r14
0x14009af5e  movzx   edx, si
0x14009af61  mov     rcx, r15
0x14009af64  call    FveDatumCopy
0x14009af69  mov     ebx, eax
0x14009af6b  mov     [rsp+118h+var_E0], eax
0x14009af6f  test    eax, eax
0x14009af71  jns     short loc_14009AF83
0x14009af73  mov     al, [rsp+118h+arg_18]
0x14009af7a  lea     r15, WPP_GLOBAL_Control
0x14009af81  jmp     short loc_14009AFE1
0x14009af83  movzx   r8d, [rsp+118h+var_E8]; Size
0x14009af89  mov     rdx, r15; Src
0x14009af8c  mov     rcx, r12; void *
0x14009af8f  cmp     [r13+40h], dil
0x14009af93  jz      short loc_14009AF9C
0x14009af95  call    RtlCopyToUser
0x14009af9a  jmp     short loc_14009AFA1
0x14009af9c  call    RtlCopyVolatileMemory
0x14009afa1  mov     al, [rsp+118h+arg_18]
0x14009afa8  lea     r15, WPP_GLOBAL_Control
0x14009afaf  jmp     short loc_14009AFE1
0x14009afb1  mov     ebx, eax
0x14009afb3  mov     [rsp+118h+var_E0], eax
0x14009afb7  lea     r15, WPP_GLOBAL_Control
0x14009afbe  xor     edi, edi
0x14009afc0  mov     r13, [rsp+118h+arg_8]
0x14009afc8  mov     esi, [rsp+118h+var_DC]
0x14009afcc  mov     r14, [rsp+118h+var_D8]
0x14009afd1  mov     al, [rsp+118h+var_E4]
0x14009afd5  jmp     short loc_14009AFE1
0x14009afd7  mov     al, dil
0x14009afda  lea     r15, WPP_GLOBAL_Control
0x14009afe1  test    al, al
0x14009afe3  jz      short loc_14009AFEF
0x14009afe5  lea     rcx, [rsp+118h+var_B8]
0x14009afea  call    FvepReleaseDevFveLock
0x14009afef  mov     rcx, [rsp+118h+P]; P
0x14009aff4  test    rcx, rcx
0x14009aff7  jz      short loc_14009B00A
0x14009aff9  mov     edx, 30455646h; Tag
0x14009affe  call    cs:__imp_ExFreePoolWithTag
0x14009b005  nop     dword ptr [rax+rax+00h]
0x14009b00a  test    r14, r14
0x14009b00d  jz      short loc_14009B017
0x14009b00f  mov     rcx, r14
0x14009b012  call    FveDatumFree
0x14009b017  mov     r8, [rsp+118h+var_C0]
0x14009b01c  test    r8, r8
0x14009b01f  jz      short loc_14009B04A
0x14009b021  mov     ecx, esi
0x14009b023  mov     rax, r8
0x14009b026  test    esi, esi
0x14009b028  jz      short loc_14009B036
0x14009b02a  mov     [rax], dil
0x14009b02d  inc     rax
0x14009b030  sub     rcx, 1
0x14009b034  jnz     short loc_14009B02A
0x14009b036  mov     edx, 30455646h; Tag
0x14009b03b  mov     rcx, r8; P
0x14009b03e  call    cs:__imp_ExFreePoolWithTag
0x14009b045  nop     dword ptr [rax+rax+00h]
0x14009b04a  movzx   eax, [rsp+118h+var_E8]
0x14009b04f  mov     [r13+38h], rax
0x14009b053  mov     rcx, cs:WPP_GLOBAL_Control
0x14009b05a  cmp     rcx, r15
0x14009b05d  jz      short loc_14009B084
0x14009b05f  mov     eax, [rcx+2Ch]
0x14009b062  test    al, 10h
0x14009b064  jz      short loc_14009B084
0x14009b066  cmp     byte ptr [rcx+29h], 5
0x14009b06a  jb      short loc_14009B084
0x14009b06c  mov     edx, 5Eh ; '^'
0x14009b071  mov     r9d, ebx
0x14009b074  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x14009b07b  mov     rcx, [rcx+18h]
0x14009b07f  call    WPP_SF_d
0x14009b084  mov     eax, ebx
0x14009b086  lea     r11, [rsp+118h+var_28]
0x14009b08e  mov     rbx, [r11+30h]
0x14009b092  mov     rsi, [r11+40h]
0x14009b096  mov     rsp, r11
0x14009b099  pop     r15
0x14009b09b  pop     r14
0x14009b09d  pop     r13
0x14009b09f  pop     r12
0x14009b0a1  pop     rdi
0x14009b0a2  retn
```
