# CKsNotification::FireNotification(uchar)

- ea: `0x18005934c`
- end: `0x1800595fb`
- name: `?FireNotification@CKsNotification@@IEAAJE@Z`
- size: `687`
- prototype: `__int64 __fastcall(CKsNotification *this, __int64, __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x180045420`
- `0x180045740`
- `0x1800590c0`
- `0x1800658c4`

## callees

- `0x18000c630`
- `0x180018628`
- `0x18001a000`
- `0x18005934c`

## import_xrefs

- `ntoskrnl!ZwUpdateWnfStateData` at `0x180059491`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x180059599`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1800595c7`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x180059491`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x180059599`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1800595c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800594a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800595df`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800594a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800595df`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800593d3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800594e1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800593d3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800594e1`

## pseudocode

```c
__int64 __fastcall CKsNotification::FireNotification(CKsNotification *this, __int64 a2, __int64 a3)
{
  char v3; // r14
  CKsNotification *v4; // rsi
  unsigned int updated; // ebx
  void *v6; // rdi
  unsigned int v7; // ebp
  PVOID PoolWithTag; // rax
  PVOID v9; // rbx
  unsigned int i; // r9d
  unsigned int v11; // ebx
  _DWORD *v12; // rax
  _DWORD *v13; // rdi
  unsigned int v14; // r8d
  __int64 *j; // rdx
  __int64 v16; // rcx

  v3 = a2;
  v4 = this;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    this = (CKsNotification *)WPP_GLOBAL_Control;
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        1,
        30,
        (__int64)WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids,
        *((_DWORD *)v4 + 24));
    }
  }
  updated = 0;
  v6 = 0;
  if ( *((_BYTE *)v4 + 8) )
  {
    v7 = 16 * *((_DWORD *)v4 + 24);
    if ( v7 )
    {
      PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1025, v7, 0x7363534Bu);
      v9 = PoolWithTag;
      if ( ExPoolZeroingNativelySupported )
      {
        if ( !PoolWithTag )
          return (unsigned int)-1073741670;
      }
      else
      {
        if ( !PoolWithTag )
          return (unsigned int)-1073741670;
        memset(PoolWithTag, 0, v7);
      }
      v6 = v9;
      this = (CKsNotification *)*((_QWORD *)v4 + 10);
      for ( i = 0; this != (CKsNotification *)((char *)v4 + 80) && i < *((_DWORD *)v4 + 24); ++i )
      {
        a2 = 2LL * i;
        *((_DWORD *)v9 + 2 * a2) = *((_DWORD *)this + 6);
        *((_DWORD *)v9 + 2 * a2 + 1) = *((_DWORD *)this + 7);
        if ( *((_DWORD *)this + 8) )
          a3 = 2 - (unsigned int)(*((_DWORD *)this + 5) != 0);
        else
          a3 = 0;
        *((_DWORD *)v9 + 4 * i + 2) = a3;
        *((_DWORD *)v9 + 2 * a2 + 3) = 0;
        this = *(CKsNotification **)this;
      }
    }
    if ( ((__int64)WPP_MAIN_CB.Dpc.SystemArgument1 & 1) != 0 )
      McTemplateK0q_EtwWriteTransfer((__int64)this, a2, a3, *((_DWORD *)v4 + 24));
    updated = ZwUpdateWnfStateData(&WNF_KSV_STREAMSTATE, v6, v7);
    if ( v6 )
      ExFreePoolWithTag(v6, 0);
  }
  if ( !v3 )
    return updated;
  v11 = 48 * *((_DWORD *)v4 + 29);
  if ( !v11 )
    return (unsigned int)ZwUpdateWnfStateData(&WNF_KSV_KSSTREAMACTIVITY, 0, 0);
  v12 = ExAllocatePoolWithTag((POOL_TYPE)1025, v11, 0x7363534Bu);
  v13 = v12;
  if ( !ExPoolZeroingNativelySupported )
  {
    if ( v12 )
    {
      memset(v12, 0, v11);
      goto LABEL_28;
    }
    return (unsigned int)-1073741670;
  }
  if ( !v12 )
    return (unsigned int)-1073741670;
LABEL_28:
  v14 = 0;
  for ( j = (__int64 *)*((_QWORD *)v4 + 15);
        j != (__int64 *)((char *)v4 + 120) && v14 < *((_DWORD *)v4 + 29);
        j = (__int64 *)*j )
  {
    v16 = 6LL * v14;
    v13[2 * v16 + 1] = *((_DWORD *)j + 9);
    ++v14;
    v13[2 * v16] = *((_DWORD *)j + 8) != 0;
    *(_QWORD *)&v13[2 * v16 + 2] = j[5];
    *(_QWORD *)&v13[2 * v16 + 4] = j[6];
    *(_OWORD *)&v13[2 * v16 + 6] = *(_OWORD *)(j + 7);
    *(_QWORD *)&v13[2 * v16 + 10] = j[9];
  }
  updated = ZwUpdateWnfStateData(&WNF_KSV_KSSTREAMACTIVITY, v13, v11);
  ExFreePoolWithTag(v13, 0);
  return updated;
}

```

## disassembly

```asm
0x18005934c  push    rbx
0x18005934e  push    rbp
0x18005934f  push    rsi
0x180059350  push    rdi
0x180059351  push    r14
0x180059353  push    r15
0x180059355  sub     rsp, 48h
0x180059359  mov     r14b, dl
0x18005935c  mov     rsi, rcx
0x18005935f  lea     rax, WPP_RECORDER_INITIALIZED
0x180059366  xor     r15d, r15d
0x180059369  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180059370  jz      short loc_1800593A6
0x180059372  mov     rcx, cs:WPP_GLOBAL_Control
0x180059379  cmp     [rcx+48h], r15w
0x18005937e  jz      short loc_1800593A6
0x180059380  mov     eax, [rsi+60h]
0x180059383  lea     r9d, [r15+1Eh]
0x180059387  mov     rcx, [rcx+40h]
0x18005938b  lea     r8d, [r15+1]
0x18005938f  mov     [rsp+78h+var_50], eax
0x180059393  mov     dl, 5
0x180059395  lea     rax, WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids
0x18005939c  mov     [rsp+78h+var_58], rax
0x1800593a1  call    WPP_RECORDER_SF_D
0x1800593a6  mov     ebx, r15d
0x1800593a9  mov     rdi, r15
0x1800593ac  cmp     [rsi+8], r15b
0x1800593b0  jz      loc_1800594B8
0x1800593b6  mov     ebp, [rsi+60h]
0x1800593b9  shl     ebp, 4
0x1800593bc  test    ebp, ebp
0x1800593be  jz      loc_180059460
0x1800593c4  mov     r8d, 7363534Bh; Tag
0x1800593ca  mov     edx, ebp; NumberOfBytes
0x1800593cc  mov     ecx, 401h; PoolType
0x1800593d1  mov     edi, ebp
0x1800593d3  call    cs:__imp_ExAllocatePoolWithTag
0x1800593da  nop     dword ptr [rax+rax+00h]
0x1800593df  cmp     cs:ExPoolZeroingNativelySupported, r15b
0x1800593e6  mov     rbx, rax
0x1800593e9  jnz     short loc_18005940C
0x1800593eb  test    rax, rax
0x1800593ee  jz      short loc_180059411
0x1800593f0  mov     r8d, edi; Size
0x1800593f3  xor     edx, edx; Val
0x1800593f5  mov     rcx, rax; void *
0x1800593f8  call    memset
0x1800593fd  lea     r10, [rsi+50h]
0x180059401  mov     rdi, rbx
0x180059404  mov     rcx, [r10]
0x180059407  mov     r9d, r15d
0x18005940a  jmp     short loc_18005945B
0x18005940c  test    rbx, rbx
0x18005940f  jnz     short loc_1800593FD
0x180059411  mov     ebx, 0C000009Ah
0x180059416  jmp     loc_1800595EB
0x18005941b  cmp     r9d, [rsi+60h]
0x18005941f  jnb     short loc_180059460
0x180059421  mov     eax, [rcx+18h]
0x180059424  mov     edx, r9d
0x180059427  add     rdx, rdx
0x18005942a  mov     [rbx+rdx*8], eax
0x18005942d  mov     eax, [rcx+1Ch]
0x180059430  mov     [rbx+rdx*8+4], eax
0x180059434  cmp     [rcx+20h], r15d
0x180059438  jz      short loc_180059448
0x18005943a  mov     eax, [rcx+14h]
0x18005943d  neg     eax
0x18005943f  sbb     r8d, r8d
0x180059442  add     r8d, 2
0x180059446  jmp     short loc_18005944B
0x180059448  mov     r8d, r15d
0x18005944b  mov     [rbx+rdx*8+8], r8d
0x180059450  inc     r9d
0x180059453  mov     [rbx+rdx*8+0Ch], r15d
0x180059458  mov     rcx, [rcx]
0x18005945b  cmp     rcx, r10
0x18005945e  jnz     short loc_18005941B
0x180059460  test    byte ptr cs:WPP_MAIN_CB.Dpc.SystemArgument1, 1
0x180059467  jz      short loc_180059472
0x180059469  mov     r9d, [rsi+60h]
0x18005946d  call    McTemplateK0q_EtwWriteTransfer
0x180059472  mov     [rsp+78h+var_48], r15d
0x180059477  lea     rcx, WNF_KSV_STREAMSTATE
0x18005947e  mov     [rsp+78h+var_50], r15d
0x180059483  xor     r9d, r9d
0x180059486  mov     r8d, ebp
0x180059489  mov     [rsp+78h+var_58], r15
0x18005948e  mov     rdx, rdi
0x180059491  call    cs:__imp_ZwUpdateWnfStateData
0x180059498  nop     dword ptr [rax+rax+00h]
0x18005949d  mov     ebx, eax
0x18005949f  test    rdi, rdi
0x1800594a2  jz      short loc_1800594B8
0x1800594a4  xor     edx, edx; Tag
0x1800594a6  mov     rcx, rdi; P
0x1800594a9  call    cs:__imp_ExFreePoolWithTag
0x1800594b0  nop     dword ptr [rax+rax+00h]
0x1800594b5  mov     rdi, r15
0x1800594b8  test    r14b, r14b
0x1800594bb  jz      loc_1800595D5
0x1800594c1  mov     eax, [rsi+74h]
0x1800594c4  lea     ebx, [rax+rax*2]
0x1800594c7  shl     ebx, 4
0x1800594ca  test    ebx, ebx
0x1800594cc  jz      loc_1800595A9
0x1800594d2  mov     r8d, 7363534Bh; Tag
0x1800594d8  mov     edx, ebx; NumberOfBytes
0x1800594da  mov     ecx, 401h; PoolType
0x1800594df  mov     ebp, ebx
0x1800594e1  call    cs:__imp_ExAllocatePoolWithTag
0x1800594e8  nop     dword ptr [rax+rax+00h]
0x1800594ed  cmp     cs:ExPoolZeroingNativelySupported, r15b
0x1800594f4  mov     rdi, rax
0x1800594f7  jnz     short loc_180059511
0x1800594f9  test    rax, rax
0x1800594fc  jz      loc_180059411
0x180059502  mov     r8d, ebp; Size
0x180059505  xor     edx, edx; Val
0x180059507  mov     rcx, rax; void *
0x18005950a  call    memset
0x18005950f  jmp     short loc_18005951A
0x180059511  test    rdi, rdi
0x180059514  jz      loc_180059411
0x18005951a  lea     r9, [rsi+78h]
0x18005951e  mov     r8d, r15d
0x180059521  mov     rdx, [r9]
0x180059524  jmp     short loc_180059575
0x180059526  cmp     r8d, [rsi+74h]
0x18005952a  jnb     short loc_18005957A
0x18005952c  mov     eax, r8d
0x18005952f  lea     rcx, [rax+rax*2]
0x180059533  mov     eax, [rdx+24h]
0x180059536  add     rcx, rcx
0x180059539  mov     [rdi+rcx*8+4], eax
0x18005953d  mov     eax, r15d
0x180059540  cmp     [rdx+20h], r15d
0x180059544  setnz   al
0x180059547  inc     r8d
0x18005954a  mov     [rdi+rcx*8], eax
0x18005954d  mov     rax, [rdx+28h]
0x180059551  mov     [rdi+rcx*8+8], rax
0x180059556  mov     rax, [rdx+30h]
0x18005955a  mov     [rdi+rcx*8+10h], rax
0x18005955f  movups  xmm0, xmmword ptr [rdx+38h]
0x180059563  movdqu  xmmword ptr [rdi+rcx*8+18h], xmm0
0x180059569  mov     rax, [rdx+48h]
0x18005956d  mov     [rdi+rcx*8+28h], rax
0x180059572  mov     rdx, [rdx]
0x180059575  cmp     rdx, r9
0x180059578  jnz     short loc_180059526
0x18005957a  mov     [rsp+78h+var_48], r15d
0x18005957f  lea     rcx, WNF_KSV_KSSTREAMACTIVITY
0x180059586  mov     [rsp+78h+var_50], r15d
0x18005958b  xor     r9d, r9d
0x18005958e  mov     r8d, ebx
0x180059591  mov     [rsp+78h+var_58], r15
0x180059596  mov     rdx, rdi
0x180059599  call    cs:__imp_ZwUpdateWnfStateData
0x1800595a0  nop     dword ptr [rax+rax+00h]
0x1800595a5  mov     ebx, eax
0x1800595a7  jmp     short loc_1800595DA
0x1800595a9  mov     [rsp+78h+var_48], r15d
0x1800595ae  lea     rcx, WNF_KSV_KSSTREAMACTIVITY
0x1800595b5  mov     [rsp+78h+var_50], r15d
0x1800595ba  xor     r9d, r9d
0x1800595bd  xor     r8d, r8d
0x1800595c0  mov     [rsp+78h+var_58], r15
0x1800595c5  xor     edx, edx
0x1800595c7  call    cs:__imp_ZwUpdateWnfStateData
0x1800595ce  nop     dword ptr [rax+rax+00h]
0x1800595d3  mov     ebx, eax
0x1800595d5  test    rdi, rdi
0x1800595d8  jz      short loc_1800595EB
0x1800595da  xor     edx, edx; Tag
0x1800595dc  mov     rcx, rdi; P
0x1800595df  call    cs:__imp_ExFreePoolWithTag
0x1800595e6  nop     dword ptr [rax+rax+00h]
0x1800595eb  mov     eax, ebx
0x1800595ed  add     rsp, 48h
0x1800595f1  pop     r15
0x1800595f3  pop     r14
0x1800595f5  pop     rdi
0x1800595f6  pop     rsi
0x1800595f7  pop     rbp
0x1800595f8  pop     rbx
0x1800595f9  retn
```
