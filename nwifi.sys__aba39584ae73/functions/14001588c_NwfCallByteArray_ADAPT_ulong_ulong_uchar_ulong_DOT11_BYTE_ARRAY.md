# NwfCallByteArray(_ADAPT *,ulong,ulong,uchar *,ulong,DOT11_BYTE_ARRAY * *)

- ea: `0x14001588c`
- end: `0x140015b04`
- name: `?NwfCallByteArray@@YAHPEAU_ADAPT@@KKPEAEKPEAPEAUDOT11_BYTE_ARRAY@@@Z`
- size: `632`
- prototype: `__int64 __usercall@<rax>(struct _ADAPT *@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned __int8 *@<r9>, unsigned int, struct DOT11_BYTE_ARRAY **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14001559c`
- `0x140061204`

## callees

- `0x14001588c`
- `0x140015e24`
- `0x140030244`
- `0x14009bcc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140015933`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140015933`
- `ntoskrnl!ExAllocatePool2` at `0x14001594e`
- `ntoskrnl!ExAllocatePool2` at `0x14001594e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140015a03`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140015abc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140015a03`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140015abc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015a1a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015ad0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015a1a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015ad0`

## pseudocode

```c
__int64 __fastcall NwfCallByteArray(
        struct _ADAPT *a1,
        __int64 a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        struct DOT11_BYTE_ARRAY **a6)
{
  unsigned __int64 v6; // r14
  size_t v8; // r15
  unsigned int v10; // ebp
  struct DOT11_BYTE_ARRAY *v11; // rsi
  unsigned int v12; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  char *Pool2; // rax
  ULONG *v16; // rdi
  unsigned int v17; // eax
  unsigned int v18; // ebx
  unsigned int v19; // eax
  unsigned int *p_uNumOfBytes; // rdi
  unsigned int v21; // ecx
  unsigned int v22[22]; // [rsp+40h] [rbp-58h] BYREF
  unsigned int v23; // [rsp+A8h] [rbp+10h] BYREF

  v6 = a5;
  v8 = a3;
  v23 = 0;
  v22[0] = 0;
  if ( a5 == -1 )
  {
    v10 = 16;
    goto LABEL_3;
  }
  v10 = a5 + 16;
  if ( a5 + 16 < a5 )
    return 3221225473LL;
  while ( 1 )
  {
LABEL_3:
    if ( v10 < (unsigned int)v8 )
      v10 = v8;
    v11 = 0;
    v12 = v10 + 16;
    if ( v10 >= 0xFFFFFFF0 )
    {
LABEL_44:
      v18 = -1073741670;
      goto LABEL_45;
    }
    if ( v12 <= 0x40 )
    {
      p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_16:
      Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_DeviceQueue);
      goto LABEL_18;
    }
    if ( v12 <= 0x100 )
    {
      p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      goto LABEL_16;
    }
    if ( v12 <= 0x400 )
    {
      p_DeviceQueue = &Lookaside;
      goto LABEL_16;
    }
    if ( v12 <= 0x800 )
    {
      p_DeviceQueue = &stru_1400B31C0;
      goto LABEL_16;
    }
    p_DeviceQueue = 0;
    Pool2 = (char *)ExAllocatePool2(64, v12, 845771639);
LABEL_18:
    v16 = (ULONG *)Pool2;
    if ( !Pool2 )
      goto LABEL_44;
    v11 = (struct DOT11_BYTE_ARRAY *)(Pool2 + 16);
    *(_QWORD *)Pool2 = p_DeviceQueue;
    *((_DWORD *)Pool2 + 2) = 845771639;
    memmove(Pool2 + 16, a4, v8);
    v17 = PtCallAdapterSync(a1, 0xE010179u, v8, v10, v11, &v23, v22);
    v18 = v17;
    if ( ((v17 + 1073676268) & 0xFFFFFFFD) != 0 && v17 != -2147483643 )
      break;
    if ( v23 >= 0x10 && (unsigned __int64)v10 - 16 >= v6 )
    {
      v18 = -2147483643;
      goto LABEL_45;
    }
    v19 = v10;
    v10 = v22[0];
    if ( v22[0] <= v19 )
    {
      v18 = -1073741823;
LABEL_39:
      if ( v11 )
      {
        if ( *(_QWORD *)v16 )
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v16, v16);
        else
          ExFreePoolWithTag(v16, v16[2]);
        v11 = 0;
      }
      goto LABEL_45;
    }
    if ( v11 )
    {
      if ( *(_QWORD *)v16 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v16, v16);
      else
        ExFreePoolWithTag(v16, v16[2]);
    }
  }
  if ( v17 )
    goto LABEL_39;
  p_uNumOfBytes = &v11->uNumOfBytes;
  if ( v23 < 0xC || (v21 = *p_uNumOfBytes, *p_uNumOfBytes > v23 - 12) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
    {
      p_uNumOfBytes = &v11->uNumOfBytes;
      WPP_SF_lll(
        WPP_GLOBAL_Control->AttachedDevice,
        26,
        WPP_1a16315538383c43a34195ffa1e5eef4_Traceguids,
        v23,
        v11->uNumOfBytes,
        v11->uTotalNumOfBytes);
    }
    *p_uNumOfBytes = 0;
    v21 = 0;
  }
  v11->uTotalNumOfBytes = v21;
LABEL_45:
  *a6 = v11;
  return v18;
}

```

## disassembly

```asm
0x14001588c  mov     rax, rsp
0x14001588f  mov     [rax+10h], edx
0x140015892  push    rbx
0x140015893  push    rbp
0x140015894  push    rsi
0x140015895  push    rdi
0x140015896  push    r12
0x140015898  push    r13
0x14001589a  push    r14
0x14001589c  push    r15
0x14001589e  sub     rsp, 58h
0x1400158a2  mov     r14d, [rsp+98h+arg_20]
0x1400158aa  mov     r12, r9
0x1400158ad  mov     r15d, r8d
0x1400158b0  mov     r13, rcx
0x1400158b3  mov     dword ptr [rax+10h], 0
0x1400158ba  mov     dword ptr [rax-58h], 0
0x1400158c1  cmp     r14d, 0FFFFFFFFh
0x1400158c5  jnz     short loc_1400158EF
0x1400158c7  mov     ebp, 10h
0x1400158cc  cmp     ebp, r15d
0x1400158cf  cmovb   ebp, r15d
0x1400158d3  xor     esi, esi
0x1400158d5  lea     eax, [rbp+10h]
0x1400158d8  cmp     eax, 10h
0x1400158db  jb      loc_140015AE0
0x1400158e1  cmp     eax, 40h ; '@'
0x1400158e4  ja      short loc_140015902
0x1400158e6  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x1400158ed  jmp     short loc_140015930
0x1400158ef  lea     ebp, [r14+10h]
0x1400158f3  cmp     ebp, r14d
0x1400158f6  jnb     short loc_1400158CC
0x1400158f8  mov     eax, 0C0000001h
0x1400158fd  jmp     loc_140015AF2
0x140015902  cmp     eax, 100h
0x140015907  ja      short loc_140015912
0x140015909  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140015910  jmp     short loc_140015930
0x140015912  cmp     eax, 400h
0x140015917  ja      short loc_140015922
0x140015919  lea     rbx, Lookaside
0x140015920  jmp     short loc_140015930
0x140015922  cmp     eax, 800h
0x140015927  ja      short loc_140015941
0x140015929  lea     rbx, stru_1400B31C0
0x140015930  mov     rcx, rbx; Lookaside
0x140015933  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14001593a  nop     dword ptr [rax+rax+00h]
0x14001593f  jmp     short loc_14001595A
0x140015941  xor     ebx, ebx
0x140015943  mov     edx, eax
0x140015945  mov     r8d, 32697377h
0x14001594b  lea     ecx, [rbx+40h]
0x14001594e  call    cs:__imp_ExAllocatePool2
0x140015955  nop     dword ptr [rax+rax+00h]
0x14001595a  mov     rdi, rax
0x14001595d  test    rax, rax
0x140015960  jz      loc_140015AE0
0x140015966  lea     rsi, [rax+10h]
0x14001596a  mov     [rax], rbx
0x14001596d  mov     rcx, rsi; void *
0x140015970  mov     dword ptr [rax+8], 32697377h
0x140015977  mov     r8, r15; Size
0x14001597a  mov     rdx, r12; Src
0x14001597d  call    memmove
0x140015982  lea     rax, [rsp+98h+var_58]
0x140015987  mov     r9d, ebp; unsigned int
0x14001598a  mov     [rsp+98h+var_68], rax; unsigned int *
0x14001598f  mov     r8d, r15d; unsigned int
0x140015992  lea     rax, [rsp+98h+arg_8]
0x14001599a  mov     edx, 0E010179h; unsigned int
0x14001599f  mov     [rsp+98h+var_70], rax; unsigned int *
0x1400159a4  mov     rcx, r13; struct _ADAPT *
0x1400159a7  mov     [rsp+98h+var_78], rsi; void *
0x1400159ac  call    ?PtCallAdapterSync@@YAHPEAU_ADAPT@@KKKPEAXPEAK2@Z; PtCallAdapterSync(_ADAPT *,ulong,ulong,ulong,void *,ulong *,ulong *)
0x1400159b1  mov     ebx, eax
0x1400159b3  lea     ecx, [rax+3FFEFFECh]
0x1400159b9  test    ecx, 0FFFFFFFDh
0x1400159bf  jz      short loc_1400159C8
0x1400159c1  cmp     eax, 80000005h
0x1400159c6  jnz     short loc_140015A2B
0x1400159c8  cmp     [rsp+98h+arg_8], 10h
0x1400159d0  jb      short loc_1400159E1
0x1400159d2  mov     ecx, ebp
0x1400159d4  sub     rcx, 10h
0x1400159d8  cmp     rcx, r14
0x1400159db  jnb     loc_140015AA0
0x1400159e1  mov     eax, ebp
0x1400159e3  mov     ebp, [rsp+98h+var_58]
0x1400159e7  cmp     ebp, eax
0x1400159e9  jbe     loc_140015AA7
0x1400159ef  test    rsi, rsi
0x1400159f2  jz      loc_1400158CC
0x1400159f8  mov     rcx, [rdi]; Lookaside
0x1400159fb  test    rcx, rcx
0x1400159fe  jz      short loc_140015A14
0x140015a00  mov     rdx, rdi; Entry
0x140015a03  call    cs:__imp_ExFreeToNPagedLookasideList
0x140015a0a  nop     dword ptr [rax+rax+00h]
0x140015a0f  jmp     loc_1400158CC
0x140015a14  mov     edx, [rdi+8]; Tag
0x140015a17  mov     rcx, rdi; P
0x140015a1a  call    cs:__imp_ExFreePoolWithTag
0x140015a21  nop     dword ptr [rax+rax+00h]
0x140015a26  jmp     loc_1400158CC
0x140015a2b  test    eax, eax
0x140015a2d  jnz     short loc_140015AAC
0x140015a2f  mov     r9d, [rsp+98h+arg_8]
0x140015a37  lea     rdi, [rsi+4]
0x140015a3b  cmp     r9d, 0Ch
0x140015a3f  jb      short loc_140015A4B
0x140015a41  mov     ecx, [rdi]
0x140015a43  lea     eax, [r9-0Ch]
0x140015a47  cmp     ecx, eax
0x140015a49  jbe     short loc_140015A9B
0x140015a4b  mov     rcx, cs:WPP_GLOBAL_Control
0x140015a52  lea     rax, WPP_GLOBAL_Control
0x140015a59  cmp     rcx, rax
0x140015a5c  jz      short loc_140015A93
0x140015a5e  cmp     byte ptr [rcx+29h], 2
0x140015a62  jb      short loc_140015A93
0x140015a64  test    dword ptr [rcx+2Ch], 100h
0x140015a6b  jz      short loc_140015A93
0x140015a6d  mov     eax, [rsi+8]
0x140015a70  lea     rdi, [rsi+4]
0x140015a74  mov     rcx, [rcx+18h]
0x140015a78  lea     r8, WPP_1a16315538383c43a34195ffa1e5eef4_Traceguids
0x140015a7f  mov     dword ptr [rsp+98h+var_70], eax
0x140015a83  mov     edx, 1Ah
0x140015a88  mov     eax, [rdi]
0x140015a8a  mov     dword ptr [rsp+98h+var_78], eax
0x140015a8e  call    WPP_SF_lll
0x140015a93  mov     dword ptr [rdi], 0
0x140015a99  xor     ecx, ecx
0x140015a9b  mov     [rsi+8], ecx
0x140015a9e  jmp     short loc_140015AE5
0x140015aa0  mov     ebx, 80000005h
0x140015aa5  jmp     short loc_140015AE5
0x140015aa7  mov     ebx, 0C0000001h
0x140015aac  test    rsi, rsi
0x140015aaf  jz      short loc_140015AE5
0x140015ab1  mov     rcx, [rdi]; Lookaside
0x140015ab4  test    rcx, rcx
0x140015ab7  jz      short loc_140015ACA
0x140015ab9  mov     rdx, rdi; Entry
0x140015abc  call    cs:__imp_ExFreeToNPagedLookasideList
0x140015ac3  nop     dword ptr [rax+rax+00h]
0x140015ac8  jmp     short loc_140015ADC
0x140015aca  mov     edx, [rdi+8]; Tag
0x140015acd  mov     rcx, rdi; P
0x140015ad0  call    cs:__imp_ExFreePoolWithTag
0x140015ad7  nop     dword ptr [rax+rax+00h]
0x140015adc  xor     esi, esi
0x140015ade  jmp     short loc_140015AE5
0x140015ae0  mov     ebx, 0C000009Ah
0x140015ae5  mov     rax, [rsp+98h+arg_28]
0x140015aed  mov     [rax], rsi
0x140015af0  mov     eax, ebx
0x140015af2  add     rsp, 58h
0x140015af6  pop     r15
0x140015af8  pop     r14
0x140015afa  pop     r13
0x140015afc  pop     r12
0x140015afe  pop     rdi
0x140015aff  pop     rsi
0x140015b00  pop     rbp
0x140015b01  pop     rbx
0x140015b02  retn
```
