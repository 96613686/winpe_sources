# Smb2AttemptToUseCachedShareRootHandle

- ea: `0x140011d00`
- end: `0x140011e84`
- name: `Smb2AttemptToUseCachedShareRootHandle`
- size: `388`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140010950`

## callees

- `0x140011d00`
- `0x1400122d0`
- `0x140033d44`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140011da2`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140011da2`

## pseudocode

```c
__int64 __fastcall Smb2AttemptToUseCachedShareRootHandle(__m128i *a1, __int64 a2)
{
  __int64 v3; // rbp
  int v5; // r15d
  __m128i si128; // xmm7
  __m128i v7; // xmm6
  __int64 v8; // rdi
  KIRQL v9; // al
  __int32 v10; // r12d
  __int32 v11; // r14d
  __int32 v12; // r13d
  unsigned __int64 v13; // xmm0_8
  __int32 v15; // [rsp+90h] [rbp+8h]
  __int32 v16; // [rsp+98h] [rbp+10h]

  v3 = *(_QWORD *)(a2 + 48);
  v5 = *(_DWORD *)(a2 + 120);
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v7 = si128;
  v8 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 40) + 40LL) + 24LL);
  v9 = SmbCeAcquireSpinLock(v8);
  v10 = a1[41].m128i_i32[0];
  v11 = a1[41].m128i_i32[1];
  v12 = a1[41].m128i_i32[2];
  v15 = a1[41].m128i_i32[3];
  v16 = a1[42].m128i_i32[0];
  if ( v10 == a1[16].m128i_i32[2] )
  {
    if ( (v5 | v11) != v11 )
      goto LABEL_3;
    v7 = a1[40];
  }
  a1[40] = si128;
LABEL_3:
  *(_DWORD *)(v8 + 2352) = -1;
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v8 + 1920), v9);
  v13 = _mm_srli_si128(v7, 8).m128i_u64[0];
  if ( v7.m128i_i64[0] == -1 && v13 == -1 )
    return 3221225494LL;
  *(_DWORD *)(v3 + 8) |= 0x10u;
  *(__m128i *)(v3 + 28) = v7;
  *(_DWORD *)(v3 + 44) = v10;
  *(_DWORD *)(v3 + 48) = v11;
  *(_DWORD *)(v3 + 52) = v12;
  *(_DWORD *)(a2 + 72) &= ~0x100000u;
  *(_DWORD *)(a2 + 152) = v15;
  *(_DWORD *)(a2 + 156) = v16;
  *(_DWORD *)(v3 + 4) = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_iiq(WPP_GLOBAL_Control->AttachedDevice);
  }
  return 0;
}

```

## disassembly

```asm
0x140011d00  mov     [rsp+arg_10], rbx
0x140011d05  push    rbp
0x140011d06  push    rsi
0x140011d07  push    rdi
0x140011d08  push    r12
0x140011d0a  push    r13
0x140011d0c  push    r14
0x140011d0e  push    r15
0x140011d10  sub     rsp, 50h
0x140011d14  mov     rax, [rdx+28h]
0x140011d18  mov     rbx, rcx
0x140011d1b  mov     rbp, [rdx+30h]
0x140011d1f  mov     rsi, rdx
0x140011d22  mov     r15d, [rdx+78h]
0x140011d26  movaps  [rsp+88h+var_48], xmm6
0x140011d2b  mov     rcx, [rax+28h]
0x140011d2f  movaps  [rsp+88h+var_58], xmm7
0x140011d34  movdqa  xmm7, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140011d3c  movups  xmm6, xmm7
0x140011d3f  mov     rdi, [rcx+18h]
0x140011d43  mov     rcx, rdi
0x140011d46  call    SmbCeAcquireSpinLock
0x140011d4b  mov     r12d, [rbx+290h]
0x140011d52  movzx   edx, al; OldIrql
0x140011d55  mov     eax, [rbx+29Ch]
0x140011d5b  mov     r14d, [rbx+294h]
0x140011d62  mov     r13d, [rbx+298h]
0x140011d69  mov     [rsp+88h+arg_0], eax
0x140011d70  mov     eax, [rbx+2A0h]
0x140011d76  mov     [rsp+88h+arg_8], eax
0x140011d7d  cmp     r12d, [rbx+108h]
0x140011d84  jz      loc_140011E4E
0x140011d8a  movups  xmmword ptr [rbx+280h], xmm7
0x140011d91  lea     rcx, [rdi+780h]; SpinLock
0x140011d98  mov     dword ptr [rdi+930h], 0FFFFFFFFh
0x140011da2  call    cs:__imp_ExReleaseSpinLockExclusive
0x140011da9  nop     dword ptr [rax+rax+00h]
0x140011dae  movdqa  xmm0, xmm6
0x140011db2  movq    r9, xmm6
0x140011db7  psrldq  xmm0, 8
0x140011dbc  movq    rcx, xmm0
0x140011dc1  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x140011dc5  jnz     short loc_140011DF4
0x140011dc7  cmp     rcx, r9
0x140011dca  jnz     short loc_140011DF4
0x140011dcc  mov     eax, 0C0000016h
0x140011dd1  mov     rbx, [rsp+88h+arg_10]
0x140011dd9  movaps  xmm6, [rsp+88h+var_48]
0x140011dde  movaps  xmm7, [rsp+88h+var_58]
0x140011de3  add     rsp, 50h
0x140011de7  pop     r15
0x140011de9  pop     r14
0x140011deb  pop     r13
0x140011ded  pop     r12
0x140011def  pop     rdi
0x140011df0  pop     rsi
0x140011df1  pop     rbp
0x140011df2  retn
0x140011df4  or      dword ptr [rbp+8], 10h
0x140011df8  mov     eax, [rsp+88h+arg_0]
0x140011dff  movups  xmmword ptr [rbp+1Ch], xmm6
0x140011e03  mov     [rbp+2Ch], r12d
0x140011e07  mov     [rbp+30h], r14d
0x140011e0b  mov     [rbp+34h], r13d
0x140011e0f  and     dword ptr [rsi+48h], 0FFEFFFFFh
0x140011e16  mov     [rsi+98h], eax
0x140011e1c  mov     eax, [rsp+88h+arg_8]
0x140011e23  mov     [rsi+9Ch], eax
0x140011e29  mov     dword ptr [rbp+4], 0
0x140011e30  mov     rdx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140011e37  lea     rax, WPP_GLOBAL_Control
0x140011e3e  cmp     rdx, rax
0x140011e41  jz      short loc_140011E4A
0x140011e43  mov     eax, [rdx+2Ch]
0x140011e46  test    al, 40h
0x140011e48  jnz     short loc_140011E69
0x140011e4a  xor     eax, eax
0x140011e4c  jmp     short loc_140011DD1
0x140011e4e  mov     eax, r14d
0x140011e51  or      eax, r15d
0x140011e54  cmp     eax, r14d
0x140011e57  jnz     loc_140011D91
0x140011e5d  movups  xmm6, xmmword ptr [rbx+280h]
0x140011e64  jmp     loc_140011D8A
0x140011e69  cmp     byte ptr [rdx+29h], 2
0x140011e6d  jb      short loc_140011E4A
0x140011e6f  mov     [rsp+88h+var_60], rsi
0x140011e74  mov     [rsp+88h+var_68], rcx
0x140011e79  mov     rcx, [rdx+18h]
0x140011e7d  call    WPP_SF_iiq
0x140011e82  jmp     short loc_140011E4A
```
