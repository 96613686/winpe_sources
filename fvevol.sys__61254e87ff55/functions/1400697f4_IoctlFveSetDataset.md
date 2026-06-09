# IoctlFveSetDataset

- ea: `0x1400697f4`
- end: `0x140069b0a`
- name: `IoctlFveSetDataset`
- size: `790`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14006aad0`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x14000ae80`
- `0x140023040`
- `0x14005745c`
- `0x140066554`
- `0x140067ae0`
- `0x1400697f4`
- `0x14008b614`
- `0x1400dce00`
- `0x1400dd144`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140069926`
- `ntoskrnl!ProbeForRead` at `0x140069926`
- `ntoskrnl!ExFreePoolWithTag` at `0x140069ab7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140069ab7`
- `ntoskrnl!ExAllocatePool2` at `0x140069940`
- `ntoskrnl!ExAllocatePool2` at `0x140069940`

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
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 62, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids);
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
    WPP_SF_d(v9->AttachedDevice, v10, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids, (unsigned int)IsActionAllowed);
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
        WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids,
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
          WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids,
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
      WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids,
      (unsigned int)IsActionAllowed);
  }
  return (unsigned int)IsActionAllowed;
}

```

## disassembly

```asm
0x1400697f4  push    rbx
0x1400697f6  push    rsi
0x1400697f7  push    rdi
0x1400697f8  push    r12
0x1400697fa  push    r13
0x1400697fc  push    r14
0x1400697fe  push    r15
0x140069800  sub     rsp, 0C0h
0x140069807  mov     r14, rdx
0x14006980a  mov     r15, rcx
0x14006980d  xor     edx, edx; Val
0x14006980f  mov     r8d, 90h; Size
0x140069815  lea     rcx, [rsp+0F8h+var_C8]; void *
0x14006981a  call    memset
0x14006981f  lea     rsi, WPP_GLOBAL_Control
0x140069826  mov     rcx, cs:WPP_GLOBAL_Control
0x14006982d  cmp     rcx, rsi
0x140069830  jz      short loc_140069854
0x140069832  mov     eax, [rcx+2Ch]
0x140069835  test    al, 10h
0x140069837  jz      short loc_140069854
0x140069839  cmp     byte ptr [rcx+29h], 5
0x14006983d  jb      short loc_140069854
0x14006983f  mov     edx, 3Eh ; '>'
0x140069844  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x14006984b  mov     rcx, [rcx+18h]
0x14006984f  call    WPP_SF_
0x140069854  mov     rax, [r14+0B8h]
0x14006985b  mov     r12, [rax+20h]
0x14006985f  mov     [rsp+0F8h+arg_18], r12
0x140069867  mov     r13d, [rax+10h]
0x14006986b  mov     [rsp+0F8h+arg_10], r13d
0x140069873  mov     rdi, r12
0x140069876  mov     [rsp+0F8h+var_D0], r12
0x14006987b  xor     edx, edx
0x14006987d  mov     rcx, r15
0x140069880  call    FveKickAllSystemsGo
0x140069885  mov     ebx, eax
0x140069887  test    eax, eax
0x140069889  jns     short loc_1400698C4
0x14006988b  mov     rcx, cs:WPP_GLOBAL_Control
0x140069892  cmp     rcx, rsi
0x140069895  jz      short loc_1400698BC
0x140069897  mov     eax, [rcx+2Ch]
0x14006989a  test    al, 10h
0x14006989c  jz      short loc_1400698BC
0x14006989e  cmp     byte ptr [rcx+29h], 2
0x1400698a2  jb      short loc_1400698BC
0x1400698a4  mov     edx, 3Fh ; '?'
0x1400698a9  mov     r9d, ebx
0x1400698ac  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x1400698b3  mov     rcx, [rcx+18h]
0x1400698b7  call    WPP_SF_d
0x1400698bc  xor     r14b, r14b
0x1400698bf  jmp     loc_140069A7F
0x1400698c4  xor     r8d, r8d
0x1400698c7  xor     edx, edx
0x1400698c9  mov     rcx, r15
0x1400698cc  call    FveIsActionAllowed
0x1400698d1  mov     ebx, eax
0x1400698d3  test    eax, eax
0x1400698d5  jns     short loc_1400698F7
0x1400698d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400698de  cmp     rcx, rsi
0x1400698e1  jz      short loc_1400698BC
0x1400698e3  mov     eax, [rcx+2Ch]
0x1400698e6  test    al, 10h
0x1400698e8  jz      short loc_1400698BC
0x1400698ea  cmp     byte ptr [rcx+29h], 2
0x1400698ee  jb      short loc_1400698BC
0x1400698f0  mov     edx, 40h ; '@'
0x1400698f5  jmp     short loc_1400698A9
0x1400698f7  mov     r8b, 1
0x1400698fa  lea     rdx, [rsp+0F8h+var_C8]
0x1400698ff  mov     rcx, r15
0x140069902  call    FvepAcquireDevFveLock
0x140069907  mov     [rsp+0F8h+arg_8], 1
0x14006990f  cmp     byte ptr [r14+40h], 0
0x140069914  jz      loc_140069A18
0x14006991a  mov     r8d, 1; Alignment
0x140069920  mov     rdx, r13; Length
0x140069923  mov     rcx, r12; Address
0x140069926  call    cs:__imp_ProbeForRead
0x14006992d  nop     dword ptr [rax+rax+00h]
0x140069932  mov     r8d, 30455646h
0x140069938  mov     rdx, r13
0x14006993b  mov     ecx, 100h
0x140069940  call    cs:__imp_ExAllocatePool2
0x140069947  nop     dword ptr [rax+rax+00h]
0x14006994c  mov     rdi, rax
0x14006994f  mov     [rsp+0F8h+var_D0], rax
0x140069954  test    rax, rax
0x140069957  jnz     short loc_140069994
0x140069959  mov     rcx, cs:WPP_GLOBAL_Control
0x140069960  cmp     rcx, rsi
0x140069963  jz      short loc_140069989
0x140069965  mov     edx, [rcx+2Ch]
0x140069968  test    dl, 10h
0x14006996b  jz      short loc_140069989
0x14006996d  cmp     byte ptr [rcx+29h], 2
0x140069971  jb      short loc_140069989
0x140069973  lea     edx, [rax+41h]
0x140069976  mov     r9d, r13d
0x140069979  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x140069980  mov     rcx, [rcx+18h]
0x140069984  call    WPP_SF_d
0x140069989  mov     ebx, 0C000009Ah
0x14006998e  mov     [rsp+0F8h+var_D8], ebx
0x140069992  jmp     short loc_1400699A3
0x140069994  mov     r8, r13; Size
0x140069997  mov     rdx, r12; Src
0x14006999a  mov     rcx, rax; void *
0x14006999d  call    RtlCopyFromUser
0x1400699a2  nop
0x1400699a3  test    ebx, ebx
0x1400699a5  jns     short loc_140069A18
0x1400699a7  mov     r14b, [rsp+0F8h+arg_8]
0x1400699af  jmp     loc_140069A7F
0x1400699b4  mov     ebx, eax
0x1400699b6  mov     [rsp+0F8h+var_D8], eax
0x1400699ba  lea     rax, WPP_GLOBAL_Control
0x1400699c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400699c8  cmp     rcx, rax
0x1400699cb  jz      short loc_1400699F2
0x1400699cd  mov     eax, [rcx+2Ch]
0x1400699d0  test    al, 10h
0x1400699d2  jz      short loc_1400699F2
0x1400699d4  cmp     byte ptr [rcx+29h], 2
0x1400699d8  jb      short loc_1400699F2
0x1400699da  mov     edx, 42h ; 'B'
0x1400699df  mov     r9d, ebx
0x1400699e2  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x1400699e9  mov     rcx, [rcx+18h]
0x1400699ed  call    WPP_SF_d
0x1400699f2  lea     rsi, WPP_GLOBAL_Control
0x1400699f9  mov     rdi, [rsp+0F8h+var_D0]
0x1400699fe  mov     r14b, [rsp+0F8h+arg_8]
0x140069a06  mov     r12, [rsp+0F8h+arg_18]
0x140069a0e  mov     r13d, [rsp+0F8h+arg_10]
0x140069a16  jmp     short loc_140069A7F
0x140069a18  mov     r8d, r13d
0x140069a1b  mov     rdx, rdi
0x140069a1e  mov     rcx, r15
0x140069a21  call    FveApplyDataSetUpdateAndCommit
0x140069a26  mov     ebx, eax
0x140069a28  lea     rcx, [rsp+0F8h+var_C8]
0x140069a2d  call    FvepReleaseDevFveLock
0x140069a32  xor     r14b, r14b
0x140069a35  test    ebx, ebx
0x140069a37  js      short loc_140069A7F
0x140069a39  mov     rcx, r15
0x140069a3c  call    FveEnforceMountAndNotify
0x140069a41  mov     ebx, eax
0x140069a43  mov     ecx, 0C0000000h
0x140069a48  and     eax, ecx
0x140069a4a  cmp     eax, ecx
0x140069a4c  jnz     short loc_140069A7F
0x140069a4e  mov     rcx, cs:WPP_GLOBAL_Control
0x140069a55  cmp     rcx, rsi
0x140069a58  jz      short loc_140069A7F
0x140069a5a  mov     eax, [rcx+2Ch]
0x140069a5d  test    al, 10h
0x140069a5f  jz      short loc_140069A7F
0x140069a61  cmp     byte ptr [rcx+29h], 2
0x140069a65  jb      short loc_140069A7F
0x140069a67  mov     edx, 43h ; 'C'
0x140069a6c  mov     r9d, ebx
0x140069a6f  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x140069a76  mov     rcx, [rcx+18h]
0x140069a7a  call    WPP_SF_d
0x140069a7f  test    r14b, r14b
0x140069a82  jz      short loc_140069A8E
0x140069a84  lea     rcx, [rsp+0F8h+var_C8]
0x140069a89  call    FvepReleaseDevFveLock
0x140069a8e  cmp     rdi, r12
0x140069a91  jz      short loc_140069AC3
0x140069a93  test    rdi, rdi
0x140069a96  jz      short loc_140069AC3
0x140069a98  mov     ecx, r13d
0x140069a9b  mov     rax, rdi
0x140069a9e  test    r13d, r13d
0x140069aa1  jz      short loc_140069AAF
0x140069aa3  mov     byte ptr [rax], 0
0x140069aa6  inc     rax
0x140069aa9  sub     rcx, 1
0x140069aad  jnz     short loc_140069AA3
0x140069aaf  mov     edx, 30455646h; Tag
0x140069ab4  mov     rcx, rdi; P
0x140069ab7  call    cs:__imp_ExFreePoolWithTag
0x140069abe  nop     dword ptr [rax+rax+00h]
0x140069ac3  mov     rcx, cs:WPP_GLOBAL_Control
0x140069aca  cmp     rcx, rsi
0x140069acd  jz      short loc_140069AF4
0x140069acf  mov     eax, [rcx+2Ch]
0x140069ad2  test    al, 10h
0x140069ad4  jz      short loc_140069AF4
0x140069ad6  cmp     byte ptr [rcx+29h], 5
0x140069ada  jb      short loc_140069AF4
0x140069adc  mov     edx, 44h ; 'D'
0x140069ae1  mov     r9d, ebx
0x140069ae4  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x140069aeb  mov     rcx, [rcx+18h]
0x140069aef  call    WPP_SF_d
0x140069af4  mov     eax, ebx
0x140069af6  add     rsp, 0C0h
0x140069afd  pop     r15
0x140069aff  pop     r14
0x140069b01  pop     r13
0x140069b03  pop     r12
0x140069b05  pop     rdi
0x140069b06  pop     rsi
0x140069b07  pop     rbx
0x140069b08  retn
```
