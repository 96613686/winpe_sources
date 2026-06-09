# NsippSetAllParameters

- ea: `0x140001880`
- end: `0x140001dca`
- name: `NsippSetAllParameters`
- size: `1354`
- prototype: `__int64 __fastcall(void *Src, unsigned int, unsigned __int8, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x140001dd0`
- `0x140002090`

## callees

- `0x140001880`
- `0x1400043d0`
- `0x140004d70`
- `0x1400056e8`
- `0x140006560`
- `0x140006680`
- `0x140006980`
- `0x140006ea0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001a84`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001b33`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001a84`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001b33`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001b00`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001b69`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001d5f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001b00`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001b69`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001d5f`
- `ntoskrnl!ExAllocatePool2` at `0x140001cc9`
- `ntoskrnl!ExAllocatePool2` at `0x140001cc9`
- `ntoskrnl!IoIs32bitProcess` at `0x1400018e4`
- `ntoskrnl!IoIs32bitProcess` at `0x1400018e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001b80`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001d90`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001daf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001b80`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001d90`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001daf`
- `NETIO!NsiSetAllParametersEx` at `0x140001b18`
- `NETIO!NsiSetAllParametersEx` at `0x140001d75`
- `NETIO!NsiSetAllParametersEx` at `0x140001b18`
- `NETIO!NsiSetAllParametersEx` at `0x140001d75`

## pseudocode

```c
__int64 __fastcall NsippSetAllParameters(void *Src, unsigned int a2, unsigned __int8 a3, __int64 a4)
{
  BOOLEAN v8; // al
  __int64 *v9; // r12
  KSPIN_LOCK *v10; // rdi
  int v11; // ebx
  char *v12; // rsi
  __int64 v13; // rbx
  size_t v14; // rcx
  char *v15; // r14
  __int64 *v16; // r14
  KIRQL v17; // r13
  __int64 *i; // rbx
  unsigned int v19; // ecx
  __int64 *v20; // rax
  __int64 **v21; // rcx
  KIRQL v22; // al
  __int64 ***v23; // rcx
  size_t v25; // r15
  __int64 Pool2; // rax
  __int64 v27; // rcx
  __int64 v28; // rax
  PVOID P; // [rsp+D0h] [rbp-118h] BYREF
  __int64 v30; // [rsp+D8h] [rbp-110h] BYREF
  char *v31; // [rsp+E0h] [rbp-108h] BYREF
  __int64 v32; // [rsp+E8h] [rbp-100h] BYREF
  __int128 v33; // [rsp+F0h] [rbp-F8h] BYREF
  __int128 v34; // [rsp+100h] [rbp-E8h]
  __int64 v35; // [rsp+110h] [rbp-D8h]
  _QWORD v36[10]; // [rsp+120h] [rbp-C8h] BYREF
  __m128i v37; // [rsp+170h] [rbp-78h] BYREF
  __m128i v38; // [rsp+180h] [rbp-68h] BYREF

  P = 0;
  v37 = 0;
  v38 = 0;
  v30 = 0;
  v32 = 0;
  v31 = 0;
  memset(v36, 0, 0x48u);
  v8 = IoIs32bitProcess(0);
  if ( !Src )
    return 3221225485LL;
  if ( !v8 )
  {
    if ( a2 >= 0x48 )
    {
      if ( a3 )
        RtlCopyFromUser(v36, Src, 0x48u);
      else
        RtlCopyVolatileMemory(v36, Src, 0x48u);
      goto LABEL_7;
    }
    return 3221225485LL;
  }
  if ( a2 < 0x28 )
    return 3221225485LL;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  if ( a3 )
    RtlCopyFromUser(&v33, Src, 0x28u);
  else
    RtlCopyVolatileMemory(&v33, Src, 0x28u);
  v36[5] = DWORD2(v34);
  LODWORD(v36[6]) = HIDWORD(v34);
  v36[2] = DWORD2(v33);
  LODWORD(v36[1]) = DWORD1(v33);
  LODWORD(v36[3]) = HIDWORD(v33);
  v36[7] = (unsigned int)v35;
  LODWORD(v36[8]) = HIDWORD(v35);
  v36[4] = v34;
  v36[0] = (int)v33;
LABEL_7:
  v9 = 0;
  v10 = *(KSPIN_LOCK **)(*(_QWORD *)(a4 + 48) + 24LL);
  v11 = NsippProbeAndAllocateParameters(
          v36,
          0x48u,
          (__int64)&v36[1],
          (__m128i *)&v36[5],
          0,
          0,
          (__int64)&v36[7],
          0,
          a3,
          1u,
          1,
          &v37,
          &v30,
          0,
          0,
          0,
          &v38,
          &v32,
          0,
          0,
          0,
          0,
          0,
          &v31,
          &P);
  v12 = (char *)P;
  if ( v11 >= 0 )
  {
    v13 = v30;
    *((_QWORD *)P + 5) = v30;
    v14 = v37.m128i_u32[2];
    *((_DWORD *)v12 + 12) = v37.m128i_i32[2];
    v15 = v31;
    *((_QWORD *)v12 + 2) = v31;
    *((_QWORD *)v12 + 7) = v32;
    *((_DWORD *)v12 + 16) = v38.m128i_i32[2];
    if ( *((_DWORD *)v12 + 9) == 6 )
    {
      v25 = v14;
      if ( v14 + 112 > 0xFFFFFFFF )
      {
        v11 = -1073741811;
        goto LABEL_28;
      }
      Pool2 = ExAllocatePool2(65, (unsigned int)(v14 + 112), 1668305742);
      v9 = (__int64 *)Pool2;
      if ( !Pool2 )
      {
        v11 = -1073741670;
        goto LABEL_28;
      }
      *(_DWORD *)(Pool2 + 16) = 1;
      *(_OWORD *)(Pool2 + 48) = *(_OWORD *)(v12 + 40);
      *(_OWORD *)(Pool2 + 24) = *(_OWORD *)(v12 + 8);
      *(_QWORD *)(Pool2 + 40) = *((_QWORD *)v12 + 3);
      if ( v15 )
      {
        v27 = Pool2 + 64;
        v28 = *((_QWORD *)v12 + 2);
        *(_OWORD *)v27 = *(_OWORD *)v28;
        *(_QWORD *)(v27 + 16) = *(_QWORD *)(v28 + 16);
        v9[4] = v27;
      }
      if ( v13 )
      {
        v9[6] = (__int64)(v9 + 11);
        memmove(v9 + 11, *((const void **)v12 + 5), v25);
      }
    }
    v16 = 0;
    if ( *((_DWORD *)v12 + 9) != 7 )
      goto LABEL_21;
    v17 = KeAcquireSpinLockRaiseToDpc(v10 + 3);
    for ( i = (__int64 *)*v10; ; i = (__int64 *)*i )
    {
      if ( i == (__int64 *)v10 )
        goto LABEL_20;
      if ( *((_DWORD *)i + 4) == 1 )
      {
        v16 = i;
        v19 = *((_DWORD *)i + 14);
        if ( v19 == *((_DWORD *)v12 + 12)
          && !memcmp((const void *)i[6], *((const void **)v12 + 5), v19)
          && (unsigned __int8)NsippIsMatchingObject(i + 3, v12 + 8) )
        {
          break;
        }
      }
    }
    v20 = (__int64 *)*i;
    if ( *(__int64 **)(*i + 8) != i )
      goto LABEL_32;
    v21 = (__int64 **)i[1];
    if ( *v21 != i )
      goto LABEL_32;
    *v21 = v20;
    v20[1] = (__int64)v21;
LABEL_20:
    KeReleaseSpinLock(v10 + 3, v17);
    if ( i == (__int64 *)v10 )
    {
      v11 = -1073741811;
    }
    else
    {
LABEL_21:
      v11 = NsiSetAllParametersEx(v12);
      if ( v11 < 0 || !v9 )
      {
LABEL_26:
        if ( *((_DWORD *)v12 + 9) == 7 )
          ExFreePoolWithTag(v16, 0);
        goto LABEL_28;
      }
      v22 = KeAcquireSpinLockRaiseToDpc(v10 + 3);
      if ( !*((_BYTE *)v10 + 16) )
      {
        v23 = (__int64 ***)v10[1];
        if ( *v23 == (__int64 **)v10 )
        {
          *v9 = (__int64)v10;
          v9[1] = (__int64)v23;
          *v23 = (__int64 **)v9;
          v10[1] = (KSPIN_LOCK)v9;
          KeReleaseSpinLock(v10 + 3, v22);
          goto LABEL_26;
        }
LABEL_32:
        __fastfail(3u);
      }
      KeReleaseSpinLock(v10 + 3, v22);
      *((_DWORD *)v12 + 9) = 7;
      NsiSetAllParametersEx(v12);
      v11 = -1073741738;
    }
  }
LABEL_28:
  if ( v12 )
    ExFreePoolWithTag(v12, 0);
  if ( v11 < 0 )
  {
    if ( v9 )
      ExFreePoolWithTag(v9, 0);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140001880  mov     rax, rsp
0x140001883  push    rbx
0x140001884  push    rsi
0x140001885  push    rdi
0x140001886  push    r12
0x140001888  push    r13
0x14000188a  push    r14
0x14000188c  push    r15
0x14000188e  sub     rsp, 1B0h
0x140001895  mov     r14, r9
0x140001898  movzx   esi, r8b
0x14000189c  mov     edi, edx
0x14000189e  mov     rbx, rcx
0x1400018a1  xor     r13d, r13d
0x1400018a4  mov     [rax-118h], r13
0x1400018ab  xorps   xmm0, xmm0
0x1400018ae  movups  xmmword ptr [rax-78h], xmm0
0x1400018b2  xorps   xmm1, xmm1
0x1400018b5  movups  xmmword ptr [rax-68h], xmm1
0x1400018b9  mov     [rax-110h], r13
0x1400018c0  mov     [rax-100h], r13
0x1400018c7  mov     [rax-108h], r13
0x1400018ce  xor     edx, edx; Val
0x1400018d0  mov     r8d, 48h ; 'H'; Size
0x1400018d6  lea     rcx, [rax-0C8h]; void *
0x1400018dd  call    memset
0x1400018e2  xor     ecx, ecx; Irp
0x1400018e4  call    cs:__imp_IoIs32bitProcess
0x1400018eb  nop     dword ptr [rax+rax+00h]
0x1400018f0  test    rbx, rbx
0x1400018f3  jz      loc_140001DC0
0x1400018f9  test    al, al
0x1400018fb  jnz     loc_140001C76
0x140001901  cmp     edi, 48h ; 'H'
0x140001904  jb      loc_140001DC0
0x14000190a  mov     r8d, 48h ; 'H'; Size
0x140001910  mov     rdx, rbx; Src
0x140001913  lea     rcx, [rsp+1E8h+var_C8]; void *
0x14000191b  test    sil, sil
0x14000191e  jz      short loc_140001927
0x140001920  call    RtlCopyFromUser
0x140001925  jmp     short loc_14000192C
0x140001927  call    RtlCopyVolatileMemory
0x14000192c  jmp     short loc_140001933
0x14000192e  jmp     loc_140001B9F
0x140001933  mov     r12, r13
0x140001936  mov     rax, [r14+30h]
0x14000193a  mov     rdi, [rax+18h]
0x14000193e  lea     rax, [rsp+1E8h+P]
0x140001946  mov     [rsp+1E8h+var_128], rax
0x14000194e  lea     rax, [rsp+1E8h+var_108]
0x140001956  mov     [rsp+1E8h+var_130], rax
0x14000195e  mov     [rsp+1E8h+var_138], r13
0x140001966  mov     [rsp+1E8h+var_140], r13
0x14000196e  mov     [rsp+1E8h+var_148], r13
0x140001976  mov     [rsp+1E8h+var_150], r13
0x14000197e  mov     [rsp+1E8h+var_158], r13
0x140001986  lea     rax, [rsp+1E8h+var_100]
0x14000198e  mov     [rsp+1E8h+var_160], rax
0x140001996  lea     rax, [rsp+1E8h+var_68]
0x14000199e  mov     [rsp+1E8h+var_168], rax
0x1400019a6  mov     [rsp+1E8h+var_170], r13
0x1400019ab  mov     [rsp+1E8h+var_178], r13
0x1400019b0  mov     [rsp+1E8h+var_180], r13
0x1400019b5  lea     rax, [rsp+1E8h+var_110]
0x1400019bd  mov     [rsp+1E8h+var_188], rax
0x1400019c2  lea     rax, [rsp+1E8h+var_78]
0x1400019ca  mov     [rsp+1E8h+var_190], rax
0x1400019cf  mov     [rsp+1E8h+var_198], 1
0x1400019d4  mov     [rsp+1E8h+var_1A0], 1
0x1400019dc  mov     [rsp+1E8h+var_1A8], sil
0x1400019e1  mov     [rsp+1E8h+var_1B0], r13
0x1400019e6  lea     rax, [rsp+1E8h+var_90]
0x1400019ee  mov     [rsp+1E8h+var_1B8], rax
0x1400019f3  mov     [rsp+1E8h+var_1C0], r13
0x1400019f8  mov     [rsp+1E8h+var_1C8], r13
0x1400019fd  lea     r9, [rsp+1E8h+var_A0]
0x140001a05  lea     r8, [rsp+1E8h+var_C0]
0x140001a0d  mov     edx, 48h ; 'H'
0x140001a12  lea     rcx, [rsp+1E8h+var_C8]
0x140001a1a  call    NsippProbeAndAllocateParameters
0x140001a1f  mov     ebx, eax
0x140001a21  mov     rsi, [rsp+1E8h+P]
0x140001a29  test    eax, eax
0x140001a2b  js      loc_140001B8C
0x140001a31  mov     rbx, [rsp+1E8h+var_110]
0x140001a39  mov     [rsi+28h], rbx
0x140001a3d  mov     ecx, dword ptr [rsp+1E8h+Size]
0x140001a44  mov     [rsi+30h], ecx
0x140001a47  mov     r14, [rsp+1E8h+var_108]
0x140001a4f  mov     [rsi+10h], r14
0x140001a53  mov     rax, [rsp+1E8h+var_100]
0x140001a5b  mov     [rsi+38h], rax
0x140001a5f  mov     eax, [rsp+1E8h+var_60]
0x140001a66  mov     [rsi+40h], eax
0x140001a69  cmp     dword ptr [rsi+24h], 6
0x140001a6d  jz      loc_140001CA1
0x140001a73  mov     r14, r13
0x140001a76  cmp     dword ptr [rsi+24h], 7
0x140001a7a  jnz     loc_140001B15
0x140001a80  lea     rcx, [rdi+18h]; SpinLock
0x140001a84  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001a8b  nop     dword ptr [rax+rax+00h]
0x140001a90  movzx   r13d, al
0x140001a94  mov     rbx, [rdi]
0x140001a97  cmp     rbx, rdi
0x140001a9a  jz      short loc_140001AF8
0x140001a9c  cmp     dword ptr [rbx+10h], 1
0x140001aa0  jz      short loc_140001AA7
0x140001aa2  mov     rbx, [rbx]
0x140001aa5  jmp     short loc_140001A97
0x140001aa7  mov     r14, rbx
0x140001aaa  mov     ecx, [rbx+38h]
0x140001aad  cmp     ecx, [rsi+30h]
0x140001ab0  jnz     short loc_140001AA2
0x140001ab2  mov     r8d, ecx; Size
0x140001ab5  mov     rdx, [rsi+28h]; Buf2
0x140001ab9  mov     rcx, [rbx+30h]; Buf1
0x140001abd  call    memcmp
0x140001ac2  test    eax, eax
0x140001ac4  jnz     short loc_140001AA2
0x140001ac6  lea     rdx, [rsi+8]
0x140001aca  lea     rcx, [rbx+18h]
0x140001ace  call    NsippIsMatchingObject
0x140001ad3  test    al, al
0x140001ad5  jz      short loc_140001AA2
0x140001ad7  mov     rax, [rbx]
0x140001ada  cmp     [rax+8], rbx
0x140001ade  jnz     loc_140001BB3
0x140001ae4  mov     rcx, [rbx+8]
0x140001ae8  cmp     [rcx], rbx
0x140001aeb  jnz     loc_140001BB3
0x140001af1  mov     [rcx], rax
0x140001af4  mov     [rax+8], rcx
0x140001af8  movzx   edx, r13b; NewIrql
0x140001afc  lea     rcx, [rdi+18h]; SpinLock
0x140001b00  call    cs:__imp_KeReleaseSpinLock
0x140001b07  nop     dword ptr [rax+rax+00h]
0x140001b0c  cmp     rbx, rdi
0x140001b0f  jz      loc_140001D4E
0x140001b15  mov     rcx, rsi
0x140001b18  call    cs:__imp_NsiSetAllParametersEx
0x140001b1f  nop     dword ptr [rax+rax+00h]
0x140001b24  mov     ebx, eax
0x140001b26  test    eax, eax
0x140001b28  js      short loc_140001B75
0x140001b2a  test    r12, r12
0x140001b2d  jz      short loc_140001B75
0x140001b2f  lea     rcx, [rdi+18h]; SpinLock
0x140001b33  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001b3a  nop     dword ptr [rax+rax+00h]
0x140001b3f  cmp     byte ptr [rdi+10h], 0
0x140001b43  jnz     loc_140001D58
0x140001b49  mov     rcx, [rdi+8]
0x140001b4d  cmp     [rcx], rdi
0x140001b50  jnz     short loc_140001BB3
0x140001b52  mov     [r12], rdi
0x140001b56  mov     [r12+8], rcx
0x140001b5b  mov     [rcx], r12
0x140001b5e  mov     [rdi+8], r12
0x140001b62  movzx   edx, al; NewIrql
0x140001b65  lea     rcx, [rdi+18h]; SpinLock
0x140001b69  call    cs:__imp_KeReleaseSpinLock
0x140001b70  nop     dword ptr [rax+rax+00h]
0x140001b75  cmp     dword ptr [rsi+24h], 7
0x140001b79  jnz     short loc_140001B8C
0x140001b7b  xor     edx, edx; Tag
0x140001b7d  mov     rcx, r14; P
0x140001b80  call    cs:__imp_ExFreePoolWithTag
0x140001b87  nop     dword ptr [rax+rax+00h]
0x140001b8c  test    rsi, rsi
0x140001b8f  jnz     loc_140001D8B
0x140001b95  test    ebx, ebx
0x140001b97  js      loc_140001DA1
0x140001b9d  mov     eax, ebx
0x140001b9f  add     rsp, 1B0h
0x140001ba6  pop     r15
0x140001ba8  pop     r14
0x140001baa  pop     r13
0x140001bac  pop     r12
0x140001bae  pop     rdi
0x140001baf  pop     rsi
0x140001bb0  pop     rbx
0x140001bb1  retn
0x140001bb3  mov     ecx, 3
0x140001bb8  int     29h; Win8: RtlFailFast(ecx)
0x140001bba  mov     r8d, 28h ; '('; Size
0x140001bc0  mov     rdx, rbx; Src
0x140001bc3  lea     rcx, [rsp+1E8h+var_F8]; void *
0x140001bcb  test    sil, sil
0x140001bce  jz      short loc_140001BD7
0x140001bd0  call    RtlCopyFromUser
0x140001bd5  jmp     short loc_140001BDC
0x140001bd7  call    RtlCopyVolatileMemory
0x140001bdc  jmp     short loc_140001BE0
0x140001bde  jmp     short loc_140001B9F
0x140001be0  mov     eax, dword ptr [rsp+1E8h+var_E8+4]
0x140001be7  mov     dword ptr [rsp+1E8h+var_A8+4], eax
0x140001bee  mov     eax, dword ptr [rsp+1E8h+var_E8+8]
0x140001bf5  mov     [rsp+1E8h+var_A0], rax
0x140001bfd  mov     eax, dword ptr [rsp+1E8h+var_E8+0Ch]
0x140001c04  mov     [rsp+1E8h+var_98], eax
0x140001c0b  mov     eax, dword ptr [rsp+1E8h+var_F8+8]
0x140001c12  mov     [rsp+1E8h+var_B8], rax
0x140001c1a  mov     eax, dword ptr [rsp+1E8h+var_F8+4]
0x140001c21  mov     [rsp+1E8h+var_C0], eax
0x140001c28  mov     eax, dword ptr [rsp+1E8h+var_F8+0Ch]
0x140001c2f  mov     [rsp+1E8h+var_B0], eax
0x140001c36  mov     eax, dword ptr [rsp+1E8h+var_D8]
0x140001c3d  mov     [rsp+1E8h+var_90], rax
0x140001c45  mov     eax, dword ptr [rsp+1E8h+var_D8+4]
0x140001c4c  mov     [rsp+1E8h+var_88], eax
0x140001c53  mov     eax, dword ptr [rsp+1E8h+var_E8]
0x140001c5a  mov     dword ptr [rsp+1E8h+var_A8], eax
0x140001c61  movsxd  rax, dword ptr [rsp+1E8h+var_F8]
0x140001c69  mov     [rsp+1E8h+var_C8], rax
0x140001c71  jmp     loc_140001933
0x140001c76  cmp     edi, 28h ; '('
0x140001c79  jb      loc_140001DC0
0x140001c7f  xorps   xmm0, xmm0
0x140001c82  xor     eax, eax
0x140001c84  movups  [rsp+1E8h+var_F8], xmm0
0x140001c8c  movups  [rsp+1E8h+var_E8], xmm0
0x140001c94  mov     [rsp+1E8h+var_D8], rax
0x140001c9c  jmp     loc_140001BBA
0x140001ca1  mov     r15, rcx
0x140001ca4  lea     rax, [rcx+70h]
0x140001ca8  mov     ecx, 0FFFFFFFFh
0x140001cad  cmp     rax, rcx
0x140001cb0  jbe     short loc_140001CBC
0x140001cb2  mov     ebx, 0C000000Dh
0x140001cb7  jmp     loc_140001B8C
0x140001cbc  mov     edx, eax
0x140001cbe  mov     ecx, 41h ; 'A'
0x140001cc3  mov     r8d, 6370534Eh
0x140001cc9  call    cs:__imp_ExAllocatePool2
0x140001cd0  nop     dword ptr [rax+rax+00h]
0x140001cd5  mov     r12, rax
0x140001cd8  test    rax, rax
0x140001cdb  jnz     short loc_140001CE7
0x140001cdd  mov     ebx, 0C000009Ah
0x140001ce2  jmp     loc_140001B8C
0x140001ce7  mov     dword ptr [rax+10h], 1
0x140001cee  movups  xmm0, xmmword ptr [rsi+28h]
0x140001cf2  movups  xmmword ptr [rax+30h], xmm0
0x140001cf6  movups  xmm0, xmmword ptr [rsi+8]
0x140001cfa  movups  xmmword ptr [rax+18h], xmm0
0x140001cfe  movsd   xmm1, qword ptr [rsi+18h]
0x140001d03  movsd   qword ptr [rax+28h], xmm1
0x140001d08  test    r14, r14
0x140001d0b  jz      short loc_140001D2A
0x140001d0d  lea     rcx, [rax+40h]
0x140001d11  mov     rax, [rsi+10h]
0x140001d15  movups  xmm0, xmmword ptr [rax]
0x140001d18  movups  xmmword ptr [rcx], xmm0
0x140001d1b  movsd   xmm1, qword ptr [rax+10h]
0x140001d20  movsd   qword ptr [rcx+10h], xmm1
0x140001d25  mov     [r12+20h], rcx
0x140001d2a  test    rbx, rbx
0x140001d2d  jz      loc_140001A73
0x140001d33  lea     rcx, [r12+58h]; void *
0x140001d38  mov     [r12+30h], rcx
0x140001d3d  mov     r8, r15; Size
0x140001d40  mov     rdx, [rsi+28h]; Src
0x140001d44  call    memmove
0x140001d49  jmp     loc_140001A73
0x140001d4e  mov     ebx, 0C000000Dh
0x140001d53  jmp     loc_140001B8C
0x140001d58  movzx   edx, al; NewIrql
0x140001d5b  lea     rcx, [rdi+18h]; SpinLock
0x140001d5f  call    cs:__imp_KeReleaseSpinLock
0x140001d66  nop     dword ptr [rax+rax+00h]
0x140001d6b  mov     dword ptr [rsi+24h], 7
0x140001d72  mov     rcx, rsi
0x140001d75  call    cs:__imp_NsiSetAllParametersEx
0x140001d7c  nop     dword ptr [rax+rax+00h]
0x140001d81  mov     ebx, 0C0000056h
0x140001d86  jmp     loc_140001B8C
0x140001d8b  xor     edx, edx; Tag
0x140001d8d  mov     rcx, rsi; P
0x140001d90  call    cs:__imp_ExFreePoolWithTag
0x140001d97  nop     dword ptr [rax+rax+00h]
0x140001d9c  jmp     loc_140001B95
0x140001da1  test    r12, r12
0x140001da4  jz      loc_140001B9D
0x140001daa  xor     edx, edx; Tag
0x140001dac  mov     rcx, r12; P
0x140001daf  call    cs:__imp_ExFreePoolWithTag
0x140001db6  nop     dword ptr [rax+rax+00h]
0x140001dbb  jmp     loc_140001B9D
0x140001dc0  mov     eax, 0C000000Dh
0x140001dc5  jmp     loc_140001B9F
```
