# IoctlFveGetKey

- ea: `0x14009cdf0`
- end: `0x14009d15c`
- name: `IoctlFveGetKey`
- size: `876`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x14006aad0`

## callees

- `0x140005e60`
- `0x140006170`
- `0x140007fbc`
- `0x140008e80`
- `0x140008f04`
- `0x140022c20`
- `0x140023040`
- `0x14005364c`
- `0x14008b614`
- `0x14009cdf0`
- `0x1400dce00`
- `0x1400dd144`
- `0x1400e092c`
- `0x1400e89fc`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x14009cf6b`
- `ntoskrnl!ProbeForWrite` at `0x14009cf6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009d0b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009d0f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009d0b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009d0f6`
- `ntoskrnl!ExAllocatePool2` at `0x14009cfd1`
- `ntoskrnl!ExAllocatePool2` at `0x14009cfd1`

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
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 93, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids);
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
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 94, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids, (unsigned int)v9);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14009cdf0  mov     [rsp+arg_0], rbx
0x14009cdf5  mov     [rsp+arg_10], rsi
0x14009cdfa  mov     [rsp+arg_8], rdx
0x14009cdff  push    rdi
0x14009ce00  push    r12
0x14009ce02  push    r13
0x14009ce04  push    r14
0x14009ce06  push    r15
0x14009ce08  sub     rsp, 0F0h
0x14009ce0f  mov     r12b, r8b
0x14009ce12  mov     r13, rdx
0x14009ce15  mov     r15, rcx
0x14009ce18  xor     edx, edx; Val
0x14009ce1a  mov     r8d, 90h; Size
0x14009ce20  lea     rcx, [rsp+118h+var_B8]; void *
0x14009ce25  call    memset
0x14009ce2a  lea     rax, WPP_GLOBAL_Control
0x14009ce31  mov     rcx, cs:WPP_GLOBAL_Control
0x14009ce38  cmp     rcx, rax
0x14009ce3b  jz      short loc_14009CE5F
0x14009ce3d  mov     eax, [rcx+2Ch]
0x14009ce40  test    al, 10h
0x14009ce42  jz      short loc_14009CE5F
0x14009ce44  cmp     byte ptr [rcx+29h], 5
0x14009ce48  jb      short loc_14009CE5F
0x14009ce4a  mov     edx, 5Dh ; ']'
0x14009ce4f  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x14009ce56  mov     rcx, [rcx+18h]
0x14009ce5a  call    WPP_SF_
0x14009ce5f  mov     rax, [r13+70h]
0x14009ce63  mov     [rsp+118h+Address], rax
0x14009ce68  mov     rax, [r13+0B8h]
0x14009ce6f  mov     esi, [rax+8]
0x14009ce72  mov     [rsp+118h+var_DC], esi
0x14009ce76  xor     edi, edi
0x14009ce78  mov     [rsp+118h+var_E8], di
0x14009ce7d  mov     [rsp+118h+P], rdi
0x14009ce82  mov     r14d, edi
0x14009ce85  mov     [rsp+118h+var_D8], rdi
0x14009ce8a  mov     [rsp+118h+var_C0], rdi
0x14009ce8f  xor     edx, edx
0x14009ce91  mov     rcx, r15
0x14009ce94  call    FveKickAllSystemsGo
0x14009ce99  mov     ebx, eax
0x14009ce9b  test    eax, eax
0x14009ce9d  js      loc_14009D08F
0x14009cea3  cmp     [r13+40h], dil
0x14009cea7  jz      short loc_14009CEB8
0x14009cea9  test    r12b, r12b
0x14009ceac  jz      short loc_14009CEB8
0x14009ceae  mov     ebx, 0C0000010h
0x14009ceb3  jmp     loc_14009D08F
0x14009ceb8  xor     r8d, r8d
0x14009cebb  lea     rdx, [rsp+118h+var_B8]
0x14009cec0  mov     rcx, r15
0x14009cec3  call    FvepAcquireDevFveLock
0x14009cec8  mov     al, 1
0x14009ceca  mov     [rsp+118h+arg_18], al
0x14009ced1  mov     [rsp+118h+var_E4], al
0x14009ced5  mov     rcx, [r15+3F8h]
0x14009cedc  test    rcx, rcx
0x14009cedf  jz      short loc_14009CF26
0x14009cee1  test    r12b, r12b
0x14009cee4  jz      short loc_14009CF15
0x14009cee6  lea     rdx, [rsp+118h+P]
0x14009ceeb  mov     rcx, r15
0x14009ceee  call    FveDuplicateInformation
0x14009cef3  mov     ebx, eax
0x14009cef5  test    eax, eax
0x14009cef7  js      short loc_14009CF26
0x14009cef9  mov     rcx, [rsp+118h+P]
0x14009cefe  add     rcx, 40h ; '@'
0x14009cf02  lea     r8, [rsp+118h+var_D8]
0x14009cf07  mov     rdx, [r15+3F8h]
0x14009cf0e  call    GetFvekDatumFromVmk
0x14009cf13  jmp     short loc_14009CF1F
0x14009cf15  lea     rdx, [rsp+118h+var_D8]
0x14009cf1a  call    FveDatumDuplicate
0x14009cf1f  mov     r14, [rsp+118h+var_D8]
0x14009cf24  mov     ebx, eax
0x14009cf26  test    ebx, ebx
0x14009cf28  js      short loc_14009CF44
0x14009cf2a  test    r14, r14
0x14009cf2d  jnz     short loc_14009CF50
0x14009cf2f  mov     ebx, [r15+328h]
0x14009cf36  shr     ebx, 6
0x14009cf39  not     ebx
0x14009cf3b  and     ebx, 1
0x14009cf3e  or      ebx, 0C0210000h
0x14009cf44  mov     al, [rsp+118h+arg_18]
0x14009cf4b  jmp     loc_14009D092
0x14009cf50  mov     r12, [rsp+118h+Address]
0x14009cf55  cmp     [r13+40h], dil
0x14009cf59  jz      short loc_14009CF77
0x14009cf5b  test    esi, esi
0x14009cf5d  jz      short loc_14009CF77
0x14009cf5f  mov     rdx, rsi; Length
0x14009cf62  mov     r8d, 2; Alignment
0x14009cf68  mov     rcx, r12; Address
0x14009cf6b  call    cs:__imp_ProbeForWrite
0x14009cf72  nop     dword ptr [rax+rax+00h]
0x14009cf77  mov     ebx, 8
0x14009cf7c  cmp     esi, ebx
0x14009cf7e  jb      short loc_14009CFB6
0x14009cf80  movzx   eax, word ptr [r14]
0x14009cf84  cmp     esi, eax
0x14009cf86  jnb     short loc_14009CFB6
0x14009cf88  mov     r8d, ebx; Size
0x14009cf8b  mov     rdx, r14; Src
0x14009cf8e  mov     rcx, r12; void *
0x14009cf91  cmp     [r13+40h], dil
0x14009cf95  jz      short loc_14009CF9E
0x14009cf97  call    RtlCopyToUser
0x14009cf9c  jmp     short loc_14009CFA3
0x14009cf9e  call    RtlCopyVolatileMemory
0x14009cfa3  mov     [rsp+118h+var_E8], bx
0x14009cfa8  mov     ebx, 80000005h
0x14009cfad  mov     [rsp+118h+var_E0], ebx
0x14009cfb1  jmp     loc_14009D059
0x14009cfb6  mov     eax, 0FFFFh
0x14009cfbb  cmp     esi, eax
0x14009cfbd  cmova   esi, eax
0x14009cfc0  mov     [rsp+118h+var_DC], esi
0x14009cfc4  mov     edx, esi
0x14009cfc6  mov     ecx, 100h
0x14009cfcb  mov     r8d, 30455646h
0x14009cfd1  call    cs:__imp_ExAllocatePool2
0x14009cfd8  nop     dword ptr [rax+rax+00h]
0x14009cfdd  mov     r15, rax
0x14009cfe0  mov     [rsp+118h+var_C0], rax
0x14009cfe5  test    rax, rax
0x14009cfe8  jnz     short loc_14009D006
0x14009cfea  mov     ebx, 0C000009Ah
0x14009cfef  mov     [rsp+118h+var_E0], ebx
0x14009cff3  mov     al, [rsp+118h+arg_18]
0x14009cffa  lea     r15, WPP_GLOBAL_Control
0x14009d001  jmp     loc_14009D099
0x14009d006  xor     r8d, r8d
0x14009d009  lea     rax, [rsp+118h+var_E8]
0x14009d00e  mov     [rsp+118h+var_F8], rax
0x14009d013  mov     r9, r14
0x14009d016  movzx   edx, si
0x14009d019  mov     rcx, r15
0x14009d01c  call    FveDatumCopy
0x14009d021  mov     ebx, eax
0x14009d023  mov     [rsp+118h+var_E0], eax
0x14009d027  test    eax, eax
0x14009d029  jns     short loc_14009D03B
0x14009d02b  mov     al, [rsp+118h+arg_18]
0x14009d032  lea     r15, WPP_GLOBAL_Control
0x14009d039  jmp     short loc_14009D099
0x14009d03b  movzx   r8d, [rsp+118h+var_E8]; Size
0x14009d041  mov     rdx, r15; Src
0x14009d044  mov     rcx, r12; void *
0x14009d047  cmp     [r13+40h], dil
0x14009d04b  jz      short loc_14009D054
0x14009d04d  call    RtlCopyToUser
0x14009d052  jmp     short loc_14009D059
0x14009d054  call    RtlCopyVolatileMemory
0x14009d059  mov     al, [rsp+118h+arg_18]
0x14009d060  lea     r15, WPP_GLOBAL_Control
0x14009d067  jmp     short loc_14009D099
0x14009d069  mov     ebx, eax
0x14009d06b  mov     [rsp+118h+var_E0], eax
0x14009d06f  lea     r15, WPP_GLOBAL_Control
0x14009d076  xor     edi, edi
0x14009d078  mov     r13, [rsp+118h+arg_8]
0x14009d080  mov     esi, [rsp+118h+var_DC]
0x14009d084  mov     r14, [rsp+118h+var_D8]
0x14009d089  mov     al, [rsp+118h+var_E4]
0x14009d08d  jmp     short loc_14009D099
0x14009d08f  mov     al, dil
0x14009d092  lea     r15, WPP_GLOBAL_Control
0x14009d099  test    al, al
0x14009d09b  jz      short loc_14009D0A7
0x14009d09d  lea     rcx, [rsp+118h+var_B8]
0x14009d0a2  call    FvepReleaseDevFveLock
0x14009d0a7  mov     rcx, [rsp+118h+P]; P
0x14009d0ac  test    rcx, rcx
0x14009d0af  jz      short loc_14009D0C2
0x14009d0b1  mov     edx, 30455646h; Tag
0x14009d0b6  call    cs:__imp_ExFreePoolWithTag
0x14009d0bd  nop     dword ptr [rax+rax+00h]
0x14009d0c2  test    r14, r14
0x14009d0c5  jz      short loc_14009D0CF
0x14009d0c7  mov     rcx, r14
0x14009d0ca  call    FveDatumFree
0x14009d0cf  mov     r8, [rsp+118h+var_C0]
0x14009d0d4  test    r8, r8
0x14009d0d7  jz      short loc_14009D102
0x14009d0d9  mov     ecx, esi
0x14009d0db  mov     rax, r8
0x14009d0de  test    esi, esi
0x14009d0e0  jz      short loc_14009D0EE
0x14009d0e2  mov     [rax], dil
0x14009d0e5  inc     rax
0x14009d0e8  sub     rcx, 1
0x14009d0ec  jnz     short loc_14009D0E2
0x14009d0ee  mov     edx, 30455646h; Tag
0x14009d0f3  mov     rcx, r8; P
0x14009d0f6  call    cs:__imp_ExFreePoolWithTag
0x14009d0fd  nop     dword ptr [rax+rax+00h]
0x14009d102  movzx   eax, [rsp+118h+var_E8]
0x14009d107  mov     [r13+38h], rax
0x14009d10b  mov     rcx, cs:WPP_GLOBAL_Control
0x14009d112  cmp     rcx, r15
0x14009d115  jz      short loc_14009D13C
0x14009d117  mov     eax, [rcx+2Ch]
0x14009d11a  test    al, 10h
0x14009d11c  jz      short loc_14009D13C
0x14009d11e  cmp     byte ptr [rcx+29h], 5
0x14009d122  jb      short loc_14009D13C
0x14009d124  mov     edx, 5Eh ; '^'
0x14009d129  mov     r9d, ebx
0x14009d12c  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x14009d133  mov     rcx, [rcx+18h]
0x14009d137  call    WPP_SF_d
0x14009d13c  mov     eax, ebx
0x14009d13e  lea     r11, [rsp+118h+var_28]
0x14009d146  mov     rbx, [r11+30h]
0x14009d14a  mov     rsi, [r11+40h]
0x14009d14e  mov     rsp, r11
0x14009d151  pop     r15
0x14009d153  pop     r14
0x14009d155  pop     r13
0x14009d157  pop     r12
0x14009d159  pop     rdi
0x14009d15a  retn
```
