# VidSchCheckSurfaceIndependentFlipAssignment

- ea: `0x14002f6f0`
- end: `0x14002fa91`
- name: `VidSchCheckSurfaceIndependentFlipAssignment`
- size: `929`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14002f6f0`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002f7fa`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002f7fa`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002f834`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002fa32`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002f834`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002fa32`
- `ntoskrnl!RtlCopyLuid` at `0x14002f78a`
- `ntoskrnl!RtlCopyLuid` at `0x14002f78a`

## pseudocode

```c
_DWORD *VidSchCheckSurfaceIndependentFlipAssignment(
        __int64 a1,
        _DWORD *a2,
        struct _LUID *a3,
        __int64 a4,
        __int64 a5,
        _DWORD *a6,
        _DWORD *a7,
        _DWORD *a8,
        _QWORD *a9,
        _DWORD *a10,
        _DWORD *a11,
        ...)
{
  _DWORD *result; // rax
  _DWORD *v19; // rbx
  __int128 v20; // xmm8
  __int128 v21; // xmm9
  __int128 v22; // xmm7
  __int128 v23; // xmm6
  int i; // r9d
  char v25; // di
  char v26; // r14
  __int64 v27; // r8
  unsigned int v28; // ecx
  __int64 v29; // rax
  __int64 v30; // rdx
  int v31; // ecx
  __int64 v32; // rcx
  __int64 v33; // rcx
  int v34; // [rsp+20h] [rbp-98h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+28h] [rbp-90h] BYREF
  __int64 v36; // [rsp+C0h] [rbp+8h]
  unsigned __int8 v38; // [rsp+E8h] [rbp+30h]
  char v39; // [rsp+F0h] [rbp+38h]
  char v40; // [rsp+F8h] [rbp+40h]
  int v41; // [rsp+100h] [rbp+48h]
  int v42; // [rsp+110h] [rbp+58h]
  _DWORD *v43; // [rsp+118h] [rbp+60h] BYREF
  va_list va; // [rsp+118h] [rbp+60h]
  _OWORD *v45; // [rsp+120h] [rbp+68h]
  _OWORD *v46; // [rsp+128h] [rbp+70h]
  va_list va1; // [rsp+130h] [rbp+78h] BYREF

  va_start(va1, a11);
  va_start(va, a11);
  v43 = va_arg(va1, _DWORD *);
  v45 = va_arg(va1, _OWORD *);
  v46 = va_arg(va1, _OWORD *);
  result = a10;
  v19 = v43;
  *a6 = 0;
  *a7 = 0;
  *a8 = 0;
  *a9 = 0;
  *a10 = 0;
  *a11 = 0;
  *v19 = 0;
  if ( *(_BYTE *)(a1 + 55) )
  {
    v43 = 0;
    RtlCopyLuid((PLUID)va, a3);
    v42 = 0;
    v34 = 0;
    v40 = 0;
    v20 = 0;
    v21 = 0;
    v39 = *(_BYTE *)(a1 + 164);
    v22 = 0;
    v36 = 0;
    v38 = 0;
    v23 = 0;
    v41 = 0;
    memset(&LockHandle, 0, sizeof(LockHandle));
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 2096), &LockHandle);
    for ( i = 0; ; ++i )
    {
      if ( i > *(_DWORD *)(a1 + 3840) )
      {
        v25 = 0;
        v26 = 0;
        goto LABEL_5;
      }
      v27 = *(_QWORD *)(a1 + 3656) + 160LL * i;
      if ( *(_DWORD **)v27 == v43 )
        break;
    }
    v28 = *(_DWORD *)(v27 + 16);
    v29 = 0;
    v41 = 0;
    if ( (v28 & 1) == 0 )
    {
      do
      {
        v28 >>= 1;
        v29 = (unsigned int)(v29 + 1);
      }
      while ( (v28 & 1) == 0 );
      v41 = v29;
    }
    v30 = *(_QWORD *)(a1 + 8 * v29 + 3528);
    v31 = *(_DWORD *)(v27 + 112);
    v22 = *(_OWORD *)(v30 + 3204);
    v40 = *(_BYTE *)(v30 + 3200);
    v23 = *(_OWORD *)(v30 + 3220);
    if ( (unsigned int)(v31 - 1) > 1 )
    {
      if ( v31 == 3 && a4 != -1 && a4 == *(_QWORD *)(v27 + 8) )
        *a11 = 1;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      goto LABEL_7;
    }
    v32 = *(unsigned int *)(v27 + 20);
    v42 = *(_DWORD *)(v27 + 20);
    if ( a4 == *(_QWORD *)(v27 + 8) || a4 == -1 )
    {
      if ( *(_BYTE *)(v27 + 96) )
      {
        v26 = 1;
        v36 = *(_QWORD *)(v27 + 88);
        v38 = *(_BYTE *)(v27 + 108);
        if ( v38 || v39 )
        {
          v33 = 304 * v32;
          v20 = *(_OWORD *)(v33 + v30 + 152);
          v34 = *(_DWORD *)(v33 + v30 + 184);
          v21 = *(_OWORD *)(v33 + v30 + 168);
        }
        v25 = 1;
      }
      else
      {
        v26 = 0;
        v25 = 1;
      }
    }
    else
    {
      v26 = 0;
      v25 = 1;
      *a10 = 1;
      *a8 = v32;
    }
LABEL_5:
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( v26 )
    {
      *a6 = 1;
      *a8 = v42;
      *a7 = v38;
      *a9 = v36;
      if ( v38 || v39 )
      {
        *(_OWORD *)a5 = v20;
        *(_OWORD *)(a5 + 16) = v21;
        *(_DWORD *)(a5 + 32) = v34;
      }
    }
    if ( v25 )
LABEL_7:
      *a2 = v41;
    *v19 = v40 != 0;
    if ( v45 )
      *v45 = v22;
    result = v46;
    if ( v46 )
      *v46 = v23;
  }
  return result;
}

```

## disassembly

```asm
0x14002f6f0  mov     r11, rsp
0x14002f6f3  mov     [r11+10h], rbx
0x14002f6f7  mov     [r11+20h], r9
0x14002f6fb  push    rbp
0x14002f6fc  push    rsi
0x14002f6fd  push    rdi
0x14002f6fe  push    r12
0x14002f700  push    r13
0x14002f702  push    r14
0x14002f704  push    r15
0x14002f706  sub     rsp, 80h
0x14002f70d  mov     rbp, [rsp+0B8h+arg_28]
0x14002f715  mov     rdi, rcx
0x14002f718  mov     r12, [rsp+0B8h+arg_30]
0x14002f720  xor     ecx, ecx
0x14002f722  mov     r15, [rsp+0B8h+arg_38]
0x14002f72a  mov     rsi, rdx
0x14002f72d  mov     r13, [rsp+0B8h+arg_40]
0x14002f735  mov     rax, [rsp+0B8h+arg_48]
0x14002f73d  mov     r14, [rsp+0B8h+arg_50]
0x14002f745  mov     rbx, [rsp+0B8h+arg_58]
0x14002f74d  mov     [rbp+0], ecx
0x14002f750  mov     [r12], ecx
0x14002f754  mov     [r15], ecx
0x14002f757  mov     [r13+0], rcx
0x14002f75b  mov     [rax], ecx
0x14002f75d  mov     [r14], ecx
0x14002f760  mov     [rbx], ecx
0x14002f762  cmp     [rdi+37h], cl
0x14002f765  jz      loc_14002F89B
0x14002f76b  movaps  [rsp+0B8h+var_48], xmm6
0x14002f770  mov     rdx, r8; SourceLuid
0x14002f773  movaps  [rsp+0B8h+var_58], xmm7
0x14002f778  mov     [r11+60h], rcx
0x14002f77c  lea     rcx, [r11+60h]; DestinationLuid
0x14002f780  movaps  xmmword ptr [r11-68h], xmm8
0x14002f785  movaps  xmmword ptr [r11-78h], xmm9
0x14002f78a  call    cs:__imp_RtlCopyLuid
0x14002f791  nop     dword ptr [rax+rax+00h]
0x14002f796  xor     ecx, ecx
0x14002f798  lea     rdx, [rsp+0B8h+LockHandle]; LockHandle
0x14002f79d  xor     eax, eax
0x14002f79f  mov     dword ptr [rsp+0B8h+arg_50], ecx
0x14002f7a6  mov     [rsp+0B8h+var_98], rax
0x14002f7ab  xorps   xmm0, xmm0
0x14002f7ae  mov     byte ptr [rsp+0B8h+arg_38], al
0x14002f7b5  xorps   xmm8, xmm8
0x14002f7b9  movzx   eax, byte ptr [rdi+0A4h]
0x14002f7c0  xorps   xmm9, xmm9
0x14002f7c4  mov     byte ptr [rsp+0B8h+arg_30], al
0x14002f7cb  xorps   xmm7, xmm7
0x14002f7ce  xor     eax, eax
0x14002f7d0  mov     [rsp+0B8h+arg_0], rcx
0x14002f7d8  mov     byte ptr [rsp+0B8h+arg_28], cl
0x14002f7df  xorps   xmm6, xmm6
0x14002f7e2  mov     dword ptr [rsp+0B8h+arg_40], ecx
0x14002f7e9  lea     rcx, [rdi+830h]; SpinLock
0x14002f7f0  mov     qword ptr [rsp+0B8h+LockHandle.OldIrql], rax
0x14002f7f5  movups  xmmword ptr [rsp+0B8h+LockHandle.LockQueue.Next], xmm0
0x14002f7fa  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14002f801  nop     dword ptr [rax+rax+00h]
0x14002f806  mov     r10d, [rdi+0F00h]
0x14002f80d  xor     r9d, r9d
0x14002f810  mov     rax, [rsp+0B8h+arg_58]
0x14002f818  mov     r11d, dword ptr [rsp+0B8h+arg_58+4]
0x14002f820  cmp     r9d, r10d
0x14002f823  jle     loc_14002F8B7
0x14002f829  xor     dil, dil
0x14002f82c  xor     r14b, r14b
0x14002f82f  lea     rcx, [rsp+0B8h+LockHandle]; LockHandle
0x14002f834  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14002f83b  nop     dword ptr [rax+rax+00h]
0x14002f840  test    r14b, r14b
0x14002f843  jnz     loc_14002F99D
0x14002f849  test    dil, dil
0x14002f84c  jz      short loc_14002F857
0x14002f84e  mov     eax, dword ptr [rsp+0B8h+arg_40]
0x14002f855  mov     [rsi], eax
0x14002f857  movaps  xmm9, [rsp+0B8h+var_78]
0x14002f85d  xor     eax, eax
0x14002f85f  cmp     byte ptr [rsp+0B8h+arg_38], al
0x14002f866  movaps  xmm8, [rsp+0B8h+var_68]
0x14002f86c  setnz   al
0x14002f86f  mov     [rbx], eax
0x14002f871  mov     rax, [rsp+0B8h+arg_60]
0x14002f879  test    rax, rax
0x14002f87c  jz      short loc_14002F881
0x14002f87e  movups  xmmword ptr [rax], xmm7
0x14002f881  mov     rax, [rsp+0B8h+arg_68]
0x14002f889  movaps  xmm7, [rsp+0B8h+var_58]
0x14002f88e  test    rax, rax
0x14002f891  jz      short loc_14002F896
0x14002f893  movups  xmmword ptr [rax], xmm6
0x14002f896  movaps  xmm6, [rsp+0B8h+var_48]
0x14002f89b  mov     rbx, [rsp+0B8h+arg_8]
0x14002f8a3  add     rsp, 80h
0x14002f8aa  pop     r15
0x14002f8ac  pop     r14
0x14002f8ae  pop     r13
0x14002f8b0  pop     r12
0x14002f8b2  pop     rdi
0x14002f8b3  pop     rsi
0x14002f8b4  pop     rbp
0x14002f8b5  retn
0x14002f8b7  movsxd  rcx, r9d
0x14002f8ba  lea     r8, [rcx+rcx*4]
0x14002f8be  shl     r8, 5
0x14002f8c2  add     r8, [rdi+0E48h]
0x14002f8c9  cmp     [r8], eax
0x14002f8cc  jnz     loc_14002F9E8
0x14002f8d2  cmp     [r8+4], r11d
0x14002f8d6  jnz     loc_14002F9E8
0x14002f8dc  mov     ecx, [r8+10h]
0x14002f8e0  xor     eax, eax
0x14002f8e2  mov     dword ptr [rsp+0B8h+arg_40], eax
0x14002f8e9  test    cl, 1
0x14002f8ec  jz      loc_14002F9F0
0x14002f8f2  mov     rdx, [rdi+rax*8+0DC8h]
0x14002f8fa  mov     ecx, [r8+70h]
0x14002f8fe  movzx   eax, byte ptr [rdx+0C80h]
0x14002f905  movups  xmm7, xmmword ptr [rdx+0C84h]
0x14002f90c  mov     byte ptr [rsp+0B8h+arg_38], al
0x14002f913  lea     eax, [rcx-1]
0x14002f916  movups  xmm6, xmmword ptr [rdx+0C94h]
0x14002f91d  cmp     eax, 1
0x14002f920  ja      loc_14002FA28
0x14002f926  mov     rax, [rsp+0B8h+arg_18]
0x14002f92e  mov     ecx, [r8+14h]
0x14002f932  mov     dword ptr [rsp+0B8h+arg_50], ecx
0x14002f939  cmp     rax, [r8+8]
0x14002f93d  jnz     loc_14002FA43
0x14002f943  cmp     byte ptr [r8+60h], 0
0x14002f948  jz      loc_14002FA69
0x14002f94e  movzx   eax, byte ptr [r8+6Ch]
0x14002f953  mov     r14b, 1
0x14002f956  mov     r8, [r8+58h]
0x14002f95a  mov     [rsp+0B8h+arg_0], r8
0x14002f962  mov     byte ptr [rsp+0B8h+arg_28], al
0x14002f969  test    al, al
0x14002f96b  jz      loc_14002FA15
0x14002f971  imul    rcx, 130h
0x14002f978  mov     eax, [rcx+rdx+0B8h]
0x14002f97f  movups  xmm8, xmmword ptr [rcx+rdx+98h]
0x14002f988  mov     dword ptr [rsp+0B8h+var_98], eax
0x14002f98c  movups  xmm9, xmmword ptr [rcx+rdx+0A8h]
0x14002f995  mov     dil, 1
0x14002f998  jmp     loc_14002F82F
0x14002f99d  mov     eax, dword ptr [rsp+0B8h+arg_50]
0x14002f9a4  movzx   ecx, byte ptr [rsp+0B8h+arg_28]
0x14002f9ac  mov     dword ptr [rbp+0], 1
0x14002f9b3  mov     [r15], eax
0x14002f9b6  mov     rax, [rsp+0B8h+arg_0]
0x14002f9be  mov     [r12], ecx
0x14002f9c2  mov     [r13+0], rax
0x14002f9c6  test    cl, cl
0x14002f9c8  jz      short loc_14002FA05
0x14002f9ca  mov     rax, [rsp+0B8h+arg_20]
0x14002f9d2  mov     rcx, [rsp+0B8h+var_98]
0x14002f9d7  movups  xmmword ptr [rax], xmm8
0x14002f9db  movups  xmmword ptr [rax+10h], xmm9
0x14002f9e0  mov     [rax+20h], ecx
0x14002f9e3  jmp     loc_14002F849
0x14002f9e8  inc     r9d
0x14002f9eb  jmp     loc_14002F820
0x14002f9f0  shr     ecx, 1
0x14002f9f2  inc     eax
0x14002f9f4  test    cl, 1
0x14002f9f7  jz      short loc_14002F9F0
0x14002f9f9  mov     dword ptr [rsp+0B8h+arg_40], eax
0x14002fa00  jmp     loc_14002F8F2
0x14002fa05  cmp     byte ptr [rsp+0B8h+arg_30], 0
0x14002fa0d  jz      loc_14002F849
0x14002fa13  jmp     short loc_14002F9CA
0x14002fa15  cmp     byte ptr [rsp+0B8h+arg_30], 0
0x14002fa1d  jnz     loc_14002F971
0x14002fa23  jmp     loc_14002F995
0x14002fa28  cmp     ecx, 3
0x14002fa2b  jz      short loc_14002FA74
0x14002fa2d  lea     rcx, [rsp+0B8h+LockHandle]; LockHandle
0x14002fa32  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14002fa39  nop     dword ptr [rax+rax+00h]
0x14002fa3e  jmp     loc_14002F84E
0x14002fa43  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14002fa47  jz      loc_14002F943
0x14002fa4d  mov     rax, [rsp+0B8h+arg_48]
0x14002fa55  xor     r14b, r14b
0x14002fa58  mov     dil, 1
0x14002fa5b  mov     dword ptr [rax], 1
0x14002fa61  mov     [r15], ecx
0x14002fa64  jmp     loc_14002F82F
0x14002fa69  xor     r14b, r14b
0x14002fa6c  mov     dil, 1
0x14002fa6f  jmp     loc_14002F82F
0x14002fa74  mov     rax, [rsp+0B8h+arg_18]
0x14002fa7c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14002fa80  jz      short loc_14002FA2D
0x14002fa82  cmp     rax, [r8+8]
0x14002fa86  jnz     short loc_14002FA2D
0x14002fa88  mov     dword ptr [r14], 1
0x14002fa8f  jmp     short loc_14002FA2D
```
