# IoctlFveSetDataset

- ea: `0x140067764`
- end: `0x140067a7a`
- name: `IoctlFveSetDataset`
- size: `790`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140068a40`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x14000adc0`
- `0x140021d00`
- `0x140055410`
- `0x1400644c4`
- `0x140065a50`
- `0x140067764`
- `0x140089574`
- `0x1400da590`
- `0x1400da8d4`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140067896`
- `ntoskrnl!ProbeForRead` at `0x140067896`
- `ntoskrnl!ExFreePoolWithTag` at `0x140067a27`
- `ntoskrnl!ExFreePoolWithTag` at `0x140067a27`
- `ntoskrnl!ExAllocatePool2` at `0x1400678b0`
- `ntoskrnl!ExAllocatePool2` at `0x1400678b0`

## pseudocode

```c
__int64 __fastcall IoctlFveSetDataset(void *a1, __int64 a2)
{
  __int64 v4; // rax
  _BYTE *v5; // r12
  SIZE_T v6; // r13
  _BYTE *v7; // rdi
  int IsActionAllowed; // ebx
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  char v11; // r14
  __int64 v12; // r8
  _BYTE *Pool2; // rax
  __int64 v14; // rcx
  _BYTE *v15; // rax
  _BYTE v17[200]; // [rsp+30h] [rbp-C8h] BYREF

  memset(v17, 0, 0x90u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 62, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids);
  }
  v4 = *(_QWORD *)(a2 + 184);
  v5 = *(_BYTE **)(v4 + 32);
  v6 = *(unsigned int *)(v4 + 16);
  v7 = v5;
  IsActionAllowed = FveKickAllSystemsGo(a1);
  if ( IsActionAllowed < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_11;
    }
    v10 = 63;
LABEL_10:
    WPP_SF_d(v9->AttachedDevice, v10, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids, (unsigned int)IsActionAllowed);
LABEL_11:
    v11 = 0;
    goto LABEL_33;
  }
  IsActionAllowed = FveIsActionAllowed(a1, 0, 0);
  if ( IsActionAllowed < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_11;
    }
    v10 = 64;
    goto LABEL_10;
  }
  LOBYTE(v12) = 1;
  FvepAcquireDevFveLock(a1, v17, v12);
  if ( !*(_BYTE *)(a2 + 64) )
    goto LABEL_27;
  ProbeForRead(v5, v6, 1u);
  Pool2 = (_BYTE *)ExAllocatePool2(256, v6, 809850438);
  v7 = Pool2;
  if ( Pool2 )
  {
    RtlCopyFromUser(Pool2, v5, v6);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        65,
        WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids,
        (unsigned int)v6);
    }
    IsActionAllowed = -1073741670;
  }
  if ( IsActionAllowed < 0 )
  {
    v11 = 1;
  }
  else
  {
LABEL_27:
    IsActionAllowed = FveApplyDataSetUpdateAndCommit((_DWORD)a1);
    FvepReleaseDevFveLock(v17);
    v11 = 0;
    if ( IsActionAllowed >= 0 )
    {
      IsActionAllowed = FveEnforceMountAndNotify(a1);
      if ( (IsActionAllowed & 0xC0000000) == 0xC0000000
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          67,
          WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids,
          (unsigned int)IsActionAllowed);
      }
    }
  }
LABEL_33:
  if ( v11 )
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
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      68,
      WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids,
      (unsigned int)IsActionAllowed);
  }
  return (unsigned int)IsActionAllowed;
}

```

## disassembly

```asm
0x140067764  push    rbx
0x140067766  push    rsi
0x140067767  push    rdi
0x140067768  push    r12
0x14006776a  push    r13
0x14006776c  push    r14
0x14006776e  push    r15
0x140067770  sub     rsp, 0C0h
0x140067777  mov     r14, rdx
0x14006777a  mov     r15, rcx
0x14006777d  xor     edx, edx; Val
0x14006777f  mov     r8d, 90h; Size
0x140067785  lea     rcx, [rsp+0F8h+var_C8]; void *
0x14006778a  call    memset
0x14006778f  lea     rsi, WPP_GLOBAL_Control
0x140067796  mov     rcx, cs:WPP_GLOBAL_Control
0x14006779d  cmp     rcx, rsi
0x1400677a0  jz      short loc_1400677C4
0x1400677a2  mov     eax, [rcx+2Ch]
0x1400677a5  test    al, 10h
0x1400677a7  jz      short loc_1400677C4
0x1400677a9  cmp     byte ptr [rcx+29h], 5
0x1400677ad  jb      short loc_1400677C4
0x1400677af  mov     edx, 3Eh ; '>'
0x1400677b4  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x1400677bb  mov     rcx, [rcx+18h]
0x1400677bf  call    WPP_SF_
0x1400677c4  mov     rax, [r14+0B8h]
0x1400677cb  mov     r12, [rax+20h]
0x1400677cf  mov     [rsp+0F8h+arg_18], r12
0x1400677d7  mov     r13d, [rax+10h]
0x1400677db  mov     [rsp+0F8h+arg_10], r13d
0x1400677e3  mov     rdi, r12
0x1400677e6  mov     [rsp+0F8h+var_D0], r12
0x1400677eb  xor     edx, edx
0x1400677ed  mov     rcx, r15
0x1400677f0  call    FveKickAllSystemsGo
0x1400677f5  mov     ebx, eax
0x1400677f7  test    eax, eax
0x1400677f9  jns     short loc_140067834
0x1400677fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140067802  cmp     rcx, rsi
0x140067805  jz      short loc_14006782C
0x140067807  mov     eax, [rcx+2Ch]
0x14006780a  test    al, 10h
0x14006780c  jz      short loc_14006782C
0x14006780e  cmp     byte ptr [rcx+29h], 2
0x140067812  jb      short loc_14006782C
0x140067814  mov     edx, 3Fh ; '?'
0x140067819  mov     r9d, ebx
0x14006781c  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x140067823  mov     rcx, [rcx+18h]
0x140067827  call    WPP_SF_d
0x14006782c  xor     r14b, r14b
0x14006782f  jmp     loc_1400679EF
0x140067834  xor     r8d, r8d
0x140067837  xor     edx, edx
0x140067839  mov     rcx, r15
0x14006783c  call    FveIsActionAllowed
0x140067841  mov     ebx, eax
0x140067843  test    eax, eax
0x140067845  jns     short loc_140067867
0x140067847  mov     rcx, cs:WPP_GLOBAL_Control
0x14006784e  cmp     rcx, rsi
0x140067851  jz      short loc_14006782C
0x140067853  mov     eax, [rcx+2Ch]
0x140067856  test    al, 10h
0x140067858  jz      short loc_14006782C
0x14006785a  cmp     byte ptr [rcx+29h], 2
0x14006785e  jb      short loc_14006782C
0x140067860  mov     edx, 40h ; '@'
0x140067865  jmp     short loc_140067819
0x140067867  mov     r8b, 1
0x14006786a  lea     rdx, [rsp+0F8h+var_C8]
0x14006786f  mov     rcx, r15
0x140067872  call    FvepAcquireDevFveLock
0x140067877  mov     [rsp+0F8h+arg_8], 1
0x14006787f  cmp     byte ptr [r14+40h], 0
0x140067884  jz      loc_140067988
0x14006788a  mov     r8d, 1; Alignment
0x140067890  mov     rdx, r13; Length
0x140067893  mov     rcx, r12; Address
0x140067896  call    cs:__imp_ProbeForRead
0x14006789d  nop     dword ptr [rax+rax+00h]
0x1400678a2  mov     r8d, 30455646h
0x1400678a8  mov     rdx, r13
0x1400678ab  mov     ecx, 100h
0x1400678b0  call    cs:__imp_ExAllocatePool2
0x1400678b7  nop     dword ptr [rax+rax+00h]
0x1400678bc  mov     rdi, rax
0x1400678bf  mov     [rsp+0F8h+var_D0], rax
0x1400678c4  test    rax, rax
0x1400678c7  jnz     short loc_140067904
0x1400678c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400678d0  cmp     rcx, rsi
0x1400678d3  jz      short loc_1400678F9
0x1400678d5  mov     edx, [rcx+2Ch]
0x1400678d8  test    dl, 10h
0x1400678db  jz      short loc_1400678F9
0x1400678dd  cmp     byte ptr [rcx+29h], 2
0x1400678e1  jb      short loc_1400678F9
0x1400678e3  lea     edx, [rax+41h]
0x1400678e6  mov     r9d, r13d
0x1400678e9  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x1400678f0  mov     rcx, [rcx+18h]
0x1400678f4  call    WPP_SF_d
0x1400678f9  mov     ebx, 0C000009Ah
0x1400678fe  mov     [rsp+0F8h+var_D8], ebx
0x140067902  jmp     short loc_140067913
0x140067904  mov     r8, r13; Size
0x140067907  mov     rdx, r12; Src
0x14006790a  mov     rcx, rax; void *
0x14006790d  call    RtlCopyFromUser
0x140067912  nop
0x140067913  test    ebx, ebx
0x140067915  jns     short loc_140067988
0x140067917  mov     r14b, [rsp+0F8h+arg_8]
0x14006791f  jmp     loc_1400679EF
0x140067924  mov     ebx, eax
0x140067926  mov     [rsp+0F8h+var_D8], eax
0x14006792a  lea     rax, WPP_GLOBAL_Control
0x140067931  mov     rcx, cs:WPP_GLOBAL_Control
0x140067938  cmp     rcx, rax
0x14006793b  jz      short loc_140067962
0x14006793d  mov     eax, [rcx+2Ch]
0x140067940  test    al, 10h
0x140067942  jz      short loc_140067962
0x140067944  cmp     byte ptr [rcx+29h], 2
0x140067948  jb      short loc_140067962
0x14006794a  mov     edx, 42h ; 'B'
0x14006794f  mov     r9d, ebx
0x140067952  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x140067959  mov     rcx, [rcx+18h]
0x14006795d  call    WPP_SF_d
0x140067962  lea     rsi, WPP_GLOBAL_Control
0x140067969  mov     rdi, [rsp+0F8h+var_D0]
0x14006796e  mov     r14b, [rsp+0F8h+arg_8]
0x140067976  mov     r12, [rsp+0F8h+arg_18]
0x14006797e  mov     r13d, [rsp+0F8h+arg_10]
0x140067986  jmp     short loc_1400679EF
0x140067988  mov     r8d, r13d
0x14006798b  mov     rdx, rdi
0x14006798e  mov     rcx, r15
0x140067991  call    FveApplyDataSetUpdateAndCommit
0x140067996  mov     ebx, eax
0x140067998  lea     rcx, [rsp+0F8h+var_C8]
0x14006799d  call    FvepReleaseDevFveLock
0x1400679a2  xor     r14b, r14b
0x1400679a5  test    ebx, ebx
0x1400679a7  js      short loc_1400679EF
0x1400679a9  mov     rcx, r15
0x1400679ac  call    FveEnforceMountAndNotify
0x1400679b1  mov     ebx, eax
0x1400679b3  mov     ecx, 0C0000000h
0x1400679b8  and     eax, ecx
0x1400679ba  cmp     eax, ecx
0x1400679bc  jnz     short loc_1400679EF
0x1400679be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400679c5  cmp     rcx, rsi
0x1400679c8  jz      short loc_1400679EF
0x1400679ca  mov     eax, [rcx+2Ch]
0x1400679cd  test    al, 10h
0x1400679cf  jz      short loc_1400679EF
0x1400679d1  cmp     byte ptr [rcx+29h], 2
0x1400679d5  jb      short loc_1400679EF
0x1400679d7  mov     edx, 43h ; 'C'
0x1400679dc  mov     r9d, ebx
0x1400679df  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x1400679e6  mov     rcx, [rcx+18h]
0x1400679ea  call    WPP_SF_d
0x1400679ef  test    r14b, r14b
0x1400679f2  jz      short loc_1400679FE
0x1400679f4  lea     rcx, [rsp+0F8h+var_C8]
0x1400679f9  call    FvepReleaseDevFveLock
0x1400679fe  cmp     rdi, r12
0x140067a01  jz      short loc_140067A33
0x140067a03  test    rdi, rdi
0x140067a06  jz      short loc_140067A33
0x140067a08  mov     ecx, r13d
0x140067a0b  mov     rax, rdi
0x140067a0e  test    r13d, r13d
0x140067a11  jz      short loc_140067A1F
0x140067a13  mov     byte ptr [rax], 0
0x140067a16  inc     rax
0x140067a19  sub     rcx, 1
0x140067a1d  jnz     short loc_140067A13
0x140067a1f  mov     edx, 30455646h; Tag
0x140067a24  mov     rcx, rdi; P
0x140067a27  call    cs:__imp_ExFreePoolWithTag
0x140067a2e  nop     dword ptr [rax+rax+00h]
0x140067a33  mov     rcx, cs:WPP_GLOBAL_Control
0x140067a3a  cmp     rcx, rsi
0x140067a3d  jz      short loc_140067A64
0x140067a3f  mov     eax, [rcx+2Ch]
0x140067a42  test    al, 10h
0x140067a44  jz      short loc_140067A64
0x140067a46  cmp     byte ptr [rcx+29h], 5
0x140067a4a  jb      short loc_140067A64
0x140067a4c  mov     edx, 44h ; 'D'
0x140067a51  mov     r9d, ebx
0x140067a54  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x140067a5b  mov     rcx, [rcx+18h]
0x140067a5f  call    WPP_SF_d
0x140067a64  mov     eax, ebx
0x140067a66  add     rsp, 0C0h
0x140067a6d  pop     r15
0x140067a6f  pop     r14
0x140067a71  pop     r13
0x140067a73  pop     r12
0x140067a75  pop     rdi
0x140067a76  pop     rsi
0x140067a77  pop     rbx
0x140067a78  retn
```
