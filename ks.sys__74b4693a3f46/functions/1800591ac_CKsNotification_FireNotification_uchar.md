# CKsNotification::FireNotification(uchar)

- ea: `0x1800591ac`
- end: `0x18005945b`
- name: `?FireNotification@CKsNotification@@IEAAJE@Z`
- size: `687`
- prototype: `__int64 __fastcall(CKsNotification *__hidden this, unsigned __int8)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x180045420`
- `0x180045740`
- `0x180058f20`
- `0x180065724`

## callees

- `0x18000c630`
- `0x1800185d8`
- `0x180019fc0`
- `0x1800591ac`

## import_xrefs

- `ntoskrnl!ZwUpdateWnfStateData` at `0x1800592f1`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1800593f9`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x180059427`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1800592f1`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1800593f9`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x180059427`
- `ntoskrnl!ExFreePoolWithTag` at `0x180059309`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005943f`
- `ntoskrnl!ExFreePoolWithTag` at `0x180059309`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005943f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180059233`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180059341`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180059233`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180059341`

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
      McTemplateK0q_EtwWriteTransfer(this, a2, a3, *((unsigned int *)v4 + 24));
    updated = ZwUpdateWnfStateData(&WNF_KSV_STREAMSTATE, v6, v7, 0, 0, 0, 0);
    if ( v6 )
      ExFreePoolWithTag(v6, 0);
  }
  if ( !v3 )
    return updated;
  v11 = 48 * *((_DWORD *)v4 + 29);
  if ( !v11 )
    return (unsigned int)ZwUpdateWnfStateData(&WNF_KSV_KSSTREAMACTIVITY, 0, 0, 0, 0, 0, 0);
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
  updated = ZwUpdateWnfStateData(&WNF_KSV_KSSTREAMACTIVITY, v13, v11, 0, 0, 0, 0);
  ExFreePoolWithTag(v13, 0);
  return updated;
}

```

## disassembly

```asm
0x1800591ac  push    rbx
0x1800591ae  push    rbp
0x1800591af  push    rsi
0x1800591b0  push    rdi
0x1800591b1  push    r14
0x1800591b3  push    r15
0x1800591b5  sub     rsp, 48h
0x1800591b9  mov     r14b, dl
0x1800591bc  mov     rsi, rcx
0x1800591bf  lea     rax, WPP_RECORDER_INITIALIZED
0x1800591c6  xor     r15d, r15d
0x1800591c9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800591d0  jz      short loc_180059206
0x1800591d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800591d9  cmp     [rcx+48h], r15w
0x1800591de  jz      short loc_180059206
0x1800591e0  mov     eax, [rsi+60h]
0x1800591e3  lea     r9d, [r15+1Eh]
0x1800591e7  mov     rcx, [rcx+40h]
0x1800591eb  lea     r8d, [r15+1]
0x1800591ef  mov     [rsp+78h+var_50], eax
0x1800591f3  mov     dl, 5
0x1800591f5  lea     rax, WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids
0x1800591fc  mov     [rsp+78h+var_58], rax
0x180059201  call    WPP_RECORDER_SF_D
0x180059206  mov     ebx, r15d
0x180059209  mov     rdi, r15
0x18005920c  cmp     [rsi+8], r15b
0x180059210  jz      loc_180059318
0x180059216  mov     ebp, [rsi+60h]
0x180059219  shl     ebp, 4
0x18005921c  test    ebp, ebp
0x18005921e  jz      loc_1800592C0
0x180059224  mov     r8d, 7363534Bh; Tag
0x18005922a  mov     edx, ebp; NumberOfBytes
0x18005922c  mov     ecx, 401h; PoolType
0x180059231  mov     edi, ebp
0x180059233  call    cs:__imp_ExAllocatePoolWithTag
0x18005923a  nop     dword ptr [rax+rax+00h]
0x18005923f  cmp     cs:ExPoolZeroingNativelySupported, r15b
0x180059246  mov     rbx, rax
0x180059249  jnz     short loc_18005926C
0x18005924b  test    rax, rax
0x18005924e  jz      short loc_180059271
0x180059250  mov     r8d, edi; Size
0x180059253  xor     edx, edx; Val
0x180059255  mov     rcx, rax; void *
0x180059258  call    memset
0x18005925d  lea     r10, [rsi+50h]
0x180059261  mov     rdi, rbx
0x180059264  mov     rcx, [r10]
0x180059267  mov     r9d, r15d
0x18005926a  jmp     short loc_1800592BB
0x18005926c  test    rbx, rbx
0x18005926f  jnz     short loc_18005925D
0x180059271  mov     ebx, 0C000009Ah
0x180059276  jmp     loc_18005944B
0x18005927b  cmp     r9d, [rsi+60h]
0x18005927f  jnb     short loc_1800592C0
0x180059281  mov     eax, [rcx+18h]
0x180059284  mov     edx, r9d
0x180059287  add     rdx, rdx
0x18005928a  mov     [rbx+rdx*8], eax
0x18005928d  mov     eax, [rcx+1Ch]
0x180059290  mov     [rbx+rdx*8+4], eax
0x180059294  cmp     [rcx+20h], r15d
0x180059298  jz      short loc_1800592A8
0x18005929a  mov     eax, [rcx+14h]
0x18005929d  neg     eax
0x18005929f  sbb     r8d, r8d
0x1800592a2  add     r8d, 2
0x1800592a6  jmp     short loc_1800592AB
0x1800592a8  mov     r8d, r15d
0x1800592ab  mov     [rbx+rdx*8+8], r8d
0x1800592b0  inc     r9d
0x1800592b3  mov     [rbx+rdx*8+0Ch], r15d
0x1800592b8  mov     rcx, [rcx]
0x1800592bb  cmp     rcx, r10
0x1800592be  jnz     short loc_18005927B
0x1800592c0  test    byte ptr cs:WPP_MAIN_CB.Dpc.SystemArgument1, 1
0x1800592c7  jz      short loc_1800592D2
0x1800592c9  mov     r9d, [rsi+60h]
0x1800592cd  call    McTemplateK0q_EtwWriteTransfer
0x1800592d2  mov     [rsp+78h+var_48], r15d
0x1800592d7  lea     rcx, WNF_KSV_STREAMSTATE
0x1800592de  mov     [rsp+78h+var_50], r15d
0x1800592e3  xor     r9d, r9d
0x1800592e6  mov     r8d, ebp
0x1800592e9  mov     [rsp+78h+var_58], r15
0x1800592ee  mov     rdx, rdi
0x1800592f1  call    cs:__imp_ZwUpdateWnfStateData
0x1800592f8  nop     dword ptr [rax+rax+00h]
0x1800592fd  mov     ebx, eax
0x1800592ff  test    rdi, rdi
0x180059302  jz      short loc_180059318
0x180059304  xor     edx, edx; Tag
0x180059306  mov     rcx, rdi; P
0x180059309  call    cs:__imp_ExFreePoolWithTag
0x180059310  nop     dword ptr [rax+rax+00h]
0x180059315  mov     rdi, r15
0x180059318  test    r14b, r14b
0x18005931b  jz      loc_180059435
0x180059321  mov     eax, [rsi+74h]
0x180059324  lea     ebx, [rax+rax*2]
0x180059327  shl     ebx, 4
0x18005932a  test    ebx, ebx
0x18005932c  jz      loc_180059409
0x180059332  mov     r8d, 7363534Bh; Tag
0x180059338  mov     edx, ebx; NumberOfBytes
0x18005933a  mov     ecx, 401h; PoolType
0x18005933f  mov     ebp, ebx
0x180059341  call    cs:__imp_ExAllocatePoolWithTag
0x180059348  nop     dword ptr [rax+rax+00h]
0x18005934d  cmp     cs:ExPoolZeroingNativelySupported, r15b
0x180059354  mov     rdi, rax
0x180059357  jnz     short loc_180059371
0x180059359  test    rax, rax
0x18005935c  jz      loc_180059271
0x180059362  mov     r8d, ebp; Size
0x180059365  xor     edx, edx; Val
0x180059367  mov     rcx, rax; void *
0x18005936a  call    memset
0x18005936f  jmp     short loc_18005937A
0x180059371  test    rdi, rdi
0x180059374  jz      loc_180059271
0x18005937a  lea     r9, [rsi+78h]
0x18005937e  mov     r8d, r15d
0x180059381  mov     rdx, [r9]
0x180059384  jmp     short loc_1800593D5
0x180059386  cmp     r8d, [rsi+74h]
0x18005938a  jnb     short loc_1800593DA
0x18005938c  mov     eax, r8d
0x18005938f  lea     rcx, [rax+rax*2]
0x180059393  mov     eax, [rdx+24h]
0x180059396  add     rcx, rcx
0x180059399  mov     [rdi+rcx*8+4], eax
0x18005939d  mov     eax, r15d
0x1800593a0  cmp     [rdx+20h], r15d
0x1800593a4  setnz   al
0x1800593a7  inc     r8d
0x1800593aa  mov     [rdi+rcx*8], eax
0x1800593ad  mov     rax, [rdx+28h]
0x1800593b1  mov     [rdi+rcx*8+8], rax
0x1800593b6  mov     rax, [rdx+30h]
0x1800593ba  mov     [rdi+rcx*8+10h], rax
0x1800593bf  movups  xmm0, xmmword ptr [rdx+38h]
0x1800593c3  movdqu  xmmword ptr [rdi+rcx*8+18h], xmm0
0x1800593c9  mov     rax, [rdx+48h]
0x1800593cd  mov     [rdi+rcx*8+28h], rax
0x1800593d2  mov     rdx, [rdx]
0x1800593d5  cmp     rdx, r9
0x1800593d8  jnz     short loc_180059386
0x1800593da  mov     [rsp+78h+var_48], r15d
0x1800593df  lea     rcx, WNF_KSV_KSSTREAMACTIVITY
0x1800593e6  mov     [rsp+78h+var_50], r15d
0x1800593eb  xor     r9d, r9d
0x1800593ee  mov     r8d, ebx
0x1800593f1  mov     [rsp+78h+var_58], r15
0x1800593f6  mov     rdx, rdi
0x1800593f9  call    cs:__imp_ZwUpdateWnfStateData
0x180059400  nop     dword ptr [rax+rax+00h]
0x180059405  mov     ebx, eax
0x180059407  jmp     short loc_18005943A
0x180059409  mov     [rsp+78h+var_48], r15d
0x18005940e  lea     rcx, WNF_KSV_KSSTREAMACTIVITY
0x180059415  mov     [rsp+78h+var_50], r15d
0x18005941a  xor     r9d, r9d
0x18005941d  xor     r8d, r8d
0x180059420  mov     [rsp+78h+var_58], r15
0x180059425  xor     edx, edx
0x180059427  call    cs:__imp_ZwUpdateWnfStateData
0x18005942e  nop     dword ptr [rax+rax+00h]
0x180059433  mov     ebx, eax
0x180059435  test    rdi, rdi
0x180059438  jz      short loc_18005944B
0x18005943a  xor     edx, edx; Tag
0x18005943c  mov     rcx, rdi; P
0x18005943f  call    cs:__imp_ExFreePoolWithTag
0x180059446  nop     dword ptr [rax+rax+00h]
0x18005944b  mov     eax, ebx
0x18005944d  add     rsp, 48h
0x180059451  pop     r15
0x180059453  pop     r14
0x180059455  pop     rdi
0x180059456  pop     rsi
0x180059457  pop     rbp
0x180059458  pop     rbx
0x180059459  retn
```
