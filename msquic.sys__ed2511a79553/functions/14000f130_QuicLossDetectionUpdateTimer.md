# QuicLossDetectionUpdateTimer

- ea: `0x14000f130`
- end: `0x14000f368`
- name: `QuicLossDetectionUpdateTimer`
- size: `568`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140013b30`
- `0x140016210`
- `0x14001e0ec`
- `0x140021664`
- `0x140049c74`

## callees

- `0x14000d7a0`
- `0x14000f130`
- `0x14001e0ec`
- `0x14002b8e8`
- `0x1400300a8`
- `0x140049238`

## import_xrefs

- `HAL!KeQueryPerformanceCounter` at `0x14000f1a7`
- `HAL!KeQueryPerformanceCounter` at `0x14000f1a7`

## pseudocode

```c
__int64 __fastcall QuicLossDetectionUpdateTimer(__int64 a1, char a2)
{
  __int64 v2; // rsi
  __int64 **v5; // rbx
  LARGE_INTEGER PerformanceCounter; // rax
  unsigned __int64 v7; // r14
  int v8; // eax
  unsigned __int64 v9; // rcx
  __int64 v10; // rdi
  __int64 v11; // rax
  int v12; // edx
  unsigned __int64 v13; // rcx
  int v14; // r9d
  unsigned __int64 v15; // rdi

  v2 = a1 - 2632;
  if ( (*(_BYTE *)(a1 - 2384) & 0x30) != 0 )
    return QuicConnTimerCancel(a1 - 2632, 2);
  v5 = *(__int64 ***)(a1 + 88);
  if ( v5 )
  {
    while ( ((_BYTE)v5[11] & 4) == 0 )
    {
      v5 = (__int64 **)*v5;
      if ( !v5 )
        goto LABEL_5;
    }
  }
  else
  {
LABEL_5:
    if ( *(_DWORD *)v2 == 4 || *(_DWORD *)(v2 + 2812) == 3 )
      return QuicConnTimerCancel(a1 - 2632, 2);
  }
  if ( (*(_BYTE *)(v2 + 321) & 0x20) == 0 && *(_DWORD *)(v2 + 528) < 0x4Cu )
    return QuicConnTimerCancel(a1 - 2632, 2);
  PerformanceCounter = KeQueryPerformanceCounter(0);
  v7 = ((1000000 * HIDWORD(PerformanceCounter.QuadPart) / (unsigned __int64)CxPlatPerfFreq.QuadPart) << 32)
     + (1000000LL * PerformanceCounter.LowPart
      + ((1000000 * HIDWORD(PerformanceCounter.QuadPart) % (unsigned __int64)CxPlatPerfFreq.QuadPart) << 32))
     / CxPlatPerfFreq.QuadPart;
  if ( v5
    && (unsigned __int64)v5[2] < *(_QWORD *)(a1 + 8)
    && (((_BYTE)v5[11] & 3) == 0 ? (v8 = 0) : ((_BYTE)v5[11] & 3) == 2 ? (v8 = 1) : (v8 = 2), v8 <= *(_DWORD *)(a1 + 16)) )
  {
    v9 = *(_QWORD *)(v2 + 472);
    if ( v9 <= *(_QWORD *)(v2 + 480) )
      v9 = *(_QWORD *)(v2 + 480);
    v10 = (__int64)v5[4] + (v9 >> 3) + v9;
  }
  else
  {
    v11 = *(_QWORD *)(v2 + 472);
    if ( (*(_BYTE *)(v2 + 321) & 8) != 0 )
      v10 = *(_QWORD *)(a1 + 24)
          + (unsigned int)(1 << *(_BYTE *)(a1 + 120))
          * (v11 + 4 * (*(_QWORD *)(v2 + 504) + 250LL * *(_QWORD *)(a1 - 928)));
    else
      v10 = *(_QWORD *)(a1 + 24) + ((v11 + 4LL * *(_QWORD *)(v2 + 504)) << *(_BYTE *)(a1 + 120));
  }
  if ( (unsigned __int8)CxPlatTimeAtOrBefore64(v10) )
  {
    v15 = 0;
    goto LABEL_31;
  }
  v15 = v10 - v7;
  if ( v5 )
  {
    if ( (unsigned __int8)CxPlatTimeAtOrBefore64((char *)v5[4] + (unsigned int)(1000 * *(_DWORD *)(v2 + 200))) )
    {
      v15 = 0;
      goto LABEL_31;
    }
    v13 -= v7;
    if ( v15 > v13 )
      v15 = v13;
  }
  if ( !v15 )
  {
LABEL_31:
    if ( a2 )
      return QuicLossDetectionProcessTimerOperation(a1);
  }
  if ( (byte_14005C48B & 1) != 0 )
    McTemplateU0puqh_EtwWriteTransfer(v13, v12, v2, v14, v15, *(_WORD *)(a1 + 120));
  return QuicConnTimerSetEx(v2, 2, v15, v7);
}

```

## disassembly

```asm
0x14000f130  mov     [rsp+arg_10], rbx
0x14000f135  push    rbp
0x14000f136  push    rsi
0x14000f137  push    r15
0x14000f139  sub     rsp, 30h
0x14000f13d  test    byte ptr [rcx-950h], 30h
0x14000f144  lea     rsi, [rcx-0A48h]
0x14000f14b  movzx   r15d, dl
0x14000f14f  mov     rbp, rcx
0x14000f152  jnz     loc_14000F34C
0x14000f158  mov     rbx, [rcx+58h]
0x14000f15c  test    rbx, rbx
0x14000f15f  jz      short loc_14000F16F
0x14000f161  test    byte ptr [rbx+58h], 4
0x14000f165  jnz     short loc_14000F185
0x14000f167  mov     rbx, [rbx]
0x14000f16a  test    rbx, rbx
0x14000f16d  jnz     short loc_14000F161
0x14000f16f  cmp     dword ptr [rsi], 4
0x14000f172  jz      loc_14000F34C
0x14000f178  cmp     dword ptr [rsi+0AFCh], 3
0x14000f17f  jz      loc_14000F34C
0x14000f185  test    byte ptr [rsi+141h], 20h
0x14000f18c  jnz     short loc_14000F19B
0x14000f18e  cmp     dword ptr [rsi+210h], 4Ch ; 'L'
0x14000f195  jb      loc_14000F34C
0x14000f19b  mov     [rsp+48h+arg_0], rdi
0x14000f1a0  xor     ecx, ecx; PerformanceFrequency
0x14000f1a2  mov     [rsp+48h+arg_8], r14
0x14000f1a7  call    cs:__imp_KeQueryPerformanceCounter
0x14000f1ae  nop     dword ptr [rax+rax+00h]
0x14000f1b3  mov     r8, qword ptr cs:CxPlatPerfFreq
0x14000f1ba  xor     edx, edx
0x14000f1bc  mov     rcx, rax
0x14000f1bf  shr     rax, 20h
0x14000f1c3  imul    r9, rax, 0F4240h
0x14000f1ca  mov     rax, r9
0x14000f1cd  div     r8
0x14000f1d0  mov     rax, rdx
0x14000f1d3  mov     edx, ecx
0x14000f1d5  imul    rcx, rdx, 0F4240h
0x14000f1dc  shl     rax, 20h
0x14000f1e0  xor     edx, edx
0x14000f1e2  add     rax, rcx
0x14000f1e5  div     r8
0x14000f1e8  xor     edx, edx
0x14000f1ea  mov     r14, rax
0x14000f1ed  mov     rax, r9
0x14000f1f0  div     r8
0x14000f1f3  mov     edx, 1
0x14000f1f8  shl     rax, 20h
0x14000f1fc  add     r14, rax
0x14000f1ff  test    rbx, rbx
0x14000f202  jz      short loc_14000F25A
0x14000f204  mov     rax, [rbp+8]
0x14000f208  cmp     [rbx+10h], rax
0x14000f20c  jnb     short loc_14000F25A
0x14000f20e  movzx   ecx, byte ptr [rbx+58h]
0x14000f212  and     ecx, 3
0x14000f215  jz      short loc_14000F22A
0x14000f217  sub     ecx, edx
0x14000f219  jz      short loc_14000F21F
0x14000f21b  cmp     ecx, edx
0x14000f21d  jz      short loc_14000F226
0x14000f21f  mov     eax, 2
0x14000f224  jmp     short loc_14000F22C
0x14000f226  mov     eax, edx
0x14000f228  jmp     short loc_14000F22C
0x14000f22a  xor     eax, eax
0x14000f22c  cmp     eax, [rbp+10h]
0x14000f22f  jg      short loc_14000F25A
0x14000f231  mov     rcx, [rsi+1D8h]
0x14000f238  movzx   r9d, dl
0x14000f23c  mov     rax, [rsi+1E0h]
0x14000f243  cmp     rcx, rax
0x14000f246  cmovbe  rcx, rax
0x14000f24a  mov     rdi, rcx
0x14000f24d  shr     rdi, 3
0x14000f251  add     rdi, [rbx+20h]
0x14000f255  add     rdi, rcx
0x14000f258  jmp     short loc_14000F2AE
0x14000f25a  test    byte ptr [rsi+141h], 8
0x14000f261  mov     rax, [rsi+1D8h]
0x14000f268  jnz     short loc_14000F285
0x14000f26a  mov     rcx, [rsi+1F8h]
0x14000f271  lea     rdi, [rax+rcx*4]
0x14000f275  movzx   ecx, byte ptr [rbp+78h]
0x14000f279  shl     rdi, cl
0x14000f27c  add     rdi, [rbp+18h]
0x14000f280  xor     r9b, r9b
0x14000f283  jmp     short loc_14000F2AE
0x14000f285  imul    rcx, [rbp-3A0h], 0FAh
0x14000f290  mov     r9b, 2
0x14000f293  add     rcx, [rsi+1F8h]
0x14000f29a  lea     rdi, [rax+rcx*4]
0x14000f29e  movzx   ecx, byte ptr [rbp+78h]
0x14000f2a2  shl     edx, cl
0x14000f2a4  mov     eax, edx
0x14000f2a6  imul    rdi, rax
0x14000f2aa  add     rdi, [rbp+18h]
0x14000f2ae  mov     rdx, r14
0x14000f2b1  mov     rcx, rdi
0x14000f2b4  call    CxPlatTimeAtOrBefore64
0x14000f2b9  test    al, al
0x14000f2bb  jz      short loc_14000F2C1
0x14000f2bd  xor     edi, edi
0x14000f2bf  jmp     short loc_14000F2F3
0x14000f2c1  sub     rdi, r14
0x14000f2c4  test    rbx, rbx
0x14000f2c7  jz      short loc_14000F2EE
0x14000f2c9  imul    ecx, [rsi+0C8h], 3E8h
0x14000f2d3  add     rcx, [rbx+20h]
0x14000f2d7  call    CxPlatTimeAtOrBefore64
0x14000f2dc  test    al, al
0x14000f2de  jz      short loc_14000F2E4
0x14000f2e0  xor     edi, edi
0x14000f2e2  jmp     short loc_14000F2F3
0x14000f2e4  sub     rcx, r14
0x14000f2e7  cmp     rdi, rcx
0x14000f2ea  cmova   rdi, rcx
0x14000f2ee  test    rdi, rdi
0x14000f2f1  jnz     short loc_14000F319
0x14000f2f3  test    r15b, r15b
0x14000f2f6  jz      short loc_14000F319
0x14000f2f8  mov     rcx, rbp
0x14000f2fb  call    QuicLossDetectionProcessTimerOperation
0x14000f300  mov     rdi, [rsp+48h+arg_0]
0x14000f305  mov     r14, [rsp+48h+arg_8]
0x14000f30a  mov     rbx, [rsp+48h+arg_10]
0x14000f30f  add     rsp, 30h
0x14000f313  pop     r15
0x14000f315  pop     rsi
0x14000f316  pop     rbp
0x14000f317  retn
0x14000f319  test    cs:byte_14005C48B, 1
0x14000f320  jz      short loc_14000F337
0x14000f322  movzx   eax, word ptr [rbp+78h]
0x14000f326  mov     r8, rsi
0x14000f329  mov     [rsp+48h+var_20], ax
0x14000f32e  mov     [rsp+48h+var_28], edi
0x14000f332  call    McTemplateU0puqh_EtwWriteTransfer
0x14000f337  mov     r9, r14
0x14000f33a  mov     r8, rdi
0x14000f33d  mov     edx, 2
0x14000f342  mov     rcx, rsi
0x14000f345  call    QuicConnTimerSetEx
0x14000f34a  jmp     short loc_14000F300
0x14000f34c  mov     edx, 2
0x14000f351  mov     rcx, rsi
0x14000f354  call    QuicConnTimerCancel
0x14000f359  mov     rbx, [rsp+48h+arg_10]
0x14000f35e  add     rsp, 30h
0x14000f362  pop     r15
0x14000f364  pop     rsi
0x14000f365  pop     rbp
0x14000f366  retn
```
