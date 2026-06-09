# NwfCallByteArray(_ADAPT *,ulong,ulong,uchar *,ulong,DOT11_BYTE_ARRAY * *)

- ea: `0x14001589c`
- end: `0x140015b14`
- name: `?NwfCallByteArray@@YAHPEAU_ADAPT@@KKPEAEKPEAPEAUDOT11_BYTE_ARRAY@@@Z`
- size: `632`
- prototype: `__int64 __usercall@<rax>(struct _ADAPT *@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned __int8 *@<r9>, unsigned int, struct DOT11_BYTE_ARRAY **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1400155ac`
- `0x14005f9d4`

## callees

- `0x14001589c`
- `0x140015e34`
- `0x14002ffb4`
- `0x14009a4c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140015943`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140015943`
- `ntoskrnl!ExAllocatePool2` at `0x14001595e`
- `ntoskrnl!ExAllocatePool2` at `0x14001595e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140015a13`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140015acc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140015a13`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140015acc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015a2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015ae0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015a2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015ae0`

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
      p_DeviceQueue = &stru_1400B0180;
      goto LABEL_16;
    }
    p_DeviceQueue = 0;
    Pool2 = (char *)ExAllocatePool2(64, v12, 845771639, a4);
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
0x14001589c  mov     rax, rsp
0x14001589f  mov     [rax+10h], edx
0x1400158a2  push    rbx
0x1400158a3  push    rbp
0x1400158a4  push    rsi
0x1400158a5  push    rdi
0x1400158a6  push    r12
0x1400158a8  push    r13
0x1400158aa  push    r14
0x1400158ac  push    r15
0x1400158ae  sub     rsp, 58h
0x1400158b2  mov     r14d, [rsp+98h+arg_20]
0x1400158ba  mov     r12, r9
0x1400158bd  mov     r15d, r8d
0x1400158c0  mov     r13, rcx
0x1400158c3  mov     dword ptr [rax+10h], 0
0x1400158ca  mov     dword ptr [rax-58h], 0
0x1400158d1  cmp     r14d, 0FFFFFFFFh
0x1400158d5  jnz     short loc_1400158FF
0x1400158d7  mov     ebp, 10h
0x1400158dc  cmp     ebp, r15d
0x1400158df  cmovb   ebp, r15d
0x1400158e3  xor     esi, esi
0x1400158e5  lea     eax, [rbp+10h]
0x1400158e8  cmp     eax, 10h
0x1400158eb  jb      loc_140015AF0
0x1400158f1  cmp     eax, 40h ; '@'
0x1400158f4  ja      short loc_140015912
0x1400158f6  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x1400158fd  jmp     short loc_140015940
0x1400158ff  lea     ebp, [r14+10h]
0x140015903  cmp     ebp, r14d
0x140015906  jnb     short loc_1400158DC
0x140015908  mov     eax, 0C0000001h
0x14001590d  jmp     loc_140015B02
0x140015912  cmp     eax, 100h
0x140015917  ja      short loc_140015922
0x140015919  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140015920  jmp     short loc_140015940
0x140015922  cmp     eax, 400h
0x140015927  ja      short loc_140015932
0x140015929  lea     rbx, Lookaside
0x140015930  jmp     short loc_140015940
0x140015932  cmp     eax, 800h
0x140015937  ja      short loc_140015951
0x140015939  lea     rbx, stru_1400B0180
0x140015940  mov     rcx, rbx; Lookaside
0x140015943  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14001594a  nop     dword ptr [rax+rax+00h]
0x14001594f  jmp     short loc_14001596A
0x140015951  xor     ebx, ebx
0x140015953  mov     edx, eax
0x140015955  mov     r8d, 32697377h
0x14001595b  lea     ecx, [rbx+40h]
0x14001595e  call    cs:__imp_ExAllocatePool2
0x140015965  nop     dword ptr [rax+rax+00h]
0x14001596a  mov     rdi, rax
0x14001596d  test    rax, rax
0x140015970  jz      loc_140015AF0
0x140015976  lea     rsi, [rax+10h]
0x14001597a  mov     [rax], rbx
0x14001597d  mov     rcx, rsi; void *
0x140015980  mov     dword ptr [rax+8], 32697377h
0x140015987  mov     r8, r15; Size
0x14001598a  mov     rdx, r12; Src
0x14001598d  call    memmove
0x140015992  lea     rax, [rsp+98h+var_58]
0x140015997  mov     r9d, ebp; unsigned int
0x14001599a  mov     [rsp+98h+var_68], rax; unsigned int *
0x14001599f  mov     r8d, r15d; unsigned int
0x1400159a2  lea     rax, [rsp+98h+arg_8]
0x1400159aa  mov     edx, 0E010179h; unsigned int
0x1400159af  mov     [rsp+98h+var_70], rax; unsigned int *
0x1400159b4  mov     rcx, r13; struct _ADAPT *
0x1400159b7  mov     [rsp+98h+var_78], rsi; void *
0x1400159bc  call    ?PtCallAdapterSync@@YAHPEAU_ADAPT@@KKKPEAXPEAK2@Z; PtCallAdapterSync(_ADAPT *,ulong,ulong,ulong,void *,ulong *,ulong *)
0x1400159c1  mov     ebx, eax
0x1400159c3  lea     ecx, [rax+3FFEFFECh]
0x1400159c9  test    ecx, 0FFFFFFFDh
0x1400159cf  jz      short loc_1400159D8
0x1400159d1  cmp     eax, 80000005h
0x1400159d6  jnz     short loc_140015A3B
0x1400159d8  cmp     [rsp+98h+arg_8], 10h
0x1400159e0  jb      short loc_1400159F1
0x1400159e2  mov     ecx, ebp
0x1400159e4  sub     rcx, 10h
0x1400159e8  cmp     rcx, r14
0x1400159eb  jnb     loc_140015AB0
0x1400159f1  mov     eax, ebp
0x1400159f3  mov     ebp, [rsp+98h+var_58]
0x1400159f7  cmp     ebp, eax
0x1400159f9  jbe     loc_140015AB7
0x1400159ff  test    rsi, rsi
0x140015a02  jz      loc_1400158DC
0x140015a08  mov     rcx, [rdi]; Lookaside
0x140015a0b  test    rcx, rcx
0x140015a0e  jz      short loc_140015A24
0x140015a10  mov     rdx, rdi; Entry
0x140015a13  call    cs:__imp_ExFreeToNPagedLookasideList
0x140015a1a  nop     dword ptr [rax+rax+00h]
0x140015a1f  jmp     loc_1400158DC
0x140015a24  mov     edx, [rdi+8]; Tag
0x140015a27  mov     rcx, rdi; P
0x140015a2a  call    cs:__imp_ExFreePoolWithTag
0x140015a31  nop     dword ptr [rax+rax+00h]
0x140015a36  jmp     loc_1400158DC
0x140015a3b  test    eax, eax
0x140015a3d  jnz     short loc_140015ABC
0x140015a3f  mov     r9d, [rsp+98h+arg_8]
0x140015a47  lea     rdi, [rsi+4]
0x140015a4b  cmp     r9d, 0Ch
0x140015a4f  jb      short loc_140015A5B
0x140015a51  mov     ecx, [rdi]
0x140015a53  lea     eax, [r9-0Ch]
0x140015a57  cmp     ecx, eax
0x140015a59  jbe     short loc_140015AAB
0x140015a5b  mov     rcx, cs:WPP_GLOBAL_Control
0x140015a62  lea     rax, WPP_GLOBAL_Control
0x140015a69  cmp     rcx, rax
0x140015a6c  jz      short loc_140015AA3
0x140015a6e  cmp     byte ptr [rcx+29h], 2
0x140015a72  jb      short loc_140015AA3
0x140015a74  test    dword ptr [rcx+2Ch], 100h
0x140015a7b  jz      short loc_140015AA3
0x140015a7d  mov     eax, [rsi+8]
0x140015a80  lea     rdi, [rsi+4]
0x140015a84  mov     rcx, [rcx+18h]
0x140015a88  lea     r8, WPP_1a16315538383c43a34195ffa1e5eef4_Traceguids
0x140015a8f  mov     dword ptr [rsp+98h+var_70], eax
0x140015a93  mov     edx, 1Ah
0x140015a98  mov     eax, [rdi]
0x140015a9a  mov     dword ptr [rsp+98h+var_78], eax
0x140015a9e  call    WPP_SF_lll
0x140015aa3  mov     dword ptr [rdi], 0
0x140015aa9  xor     ecx, ecx
0x140015aab  mov     [rsi+8], ecx
0x140015aae  jmp     short loc_140015AF5
0x140015ab0  mov     ebx, 80000005h
0x140015ab5  jmp     short loc_140015AF5
0x140015ab7  mov     ebx, 0C0000001h
0x140015abc  test    rsi, rsi
0x140015abf  jz      short loc_140015AF5
0x140015ac1  mov     rcx, [rdi]; Lookaside
0x140015ac4  test    rcx, rcx
0x140015ac7  jz      short loc_140015ADA
0x140015ac9  mov     rdx, rdi; Entry
0x140015acc  call    cs:__imp_ExFreeToNPagedLookasideList
0x140015ad3  nop     dword ptr [rax+rax+00h]
0x140015ad8  jmp     short loc_140015AEC
0x140015ada  mov     edx, [rdi+8]; Tag
0x140015add  mov     rcx, rdi; P
0x140015ae0  call    cs:__imp_ExFreePoolWithTag
0x140015ae7  nop     dword ptr [rax+rax+00h]
0x140015aec  xor     esi, esi
0x140015aee  jmp     short loc_140015AF5
0x140015af0  mov     ebx, 0C000009Ah
0x140015af5  mov     rax, [rsp+98h+arg_28]
0x140015afd  mov     [rax], rsi
0x140015b00  mov     eax, ebx
0x140015b02  add     rsp, 58h
0x140015b06  pop     r15
0x140015b08  pop     r14
0x140015b0a  pop     r13
0x140015b0c  pop     r12
0x140015b0e  pop     rdi
0x140015b0f  pop     rsi
0x140015b10  pop     rbp
0x140015b11  pop     rbx
0x140015b12  retn
```
