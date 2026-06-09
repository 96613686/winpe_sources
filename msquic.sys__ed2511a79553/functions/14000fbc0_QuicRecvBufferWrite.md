# QuicRecvBufferWrite

- ea: `0x14000fbc0`
- end: `0x14000fd34`
- name: `QuicRecvBufferWrite`
- size: `372`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int16, __int64, unsigned __int64, _QWORD *, bool *, _QWORD *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140009438`
- `0x14000fdb0`

## callees

- `0x14000fbc0`
- `0x14000fd40`
- `0x1400123c0`
- `0x14002636c`
- `0x14002ea74`
- `0x14002edbc`
- `0x14003ed00`

## pseudocode

```c
__int64 __fastcall QuicRecvBufferWrite(
        __int64 a1,
        __int64 a2,
        unsigned __int16 a3,
        __int64 a4,
        unsigned __int64 a5,
        _QWORD *a6,
        bool *a7,
        _QWORD *a8)
{
  bool *v8; // r13
  _QWORD *v9; // r10
  _QWORD *v11; // r14
  __int64 v13; // r12
  unsigned __int64 v14; // r8
  unsigned __int64 v15; // rbx
  unsigned __int64 TotalLength; // rax
  _QWORD *v17; // r10
  __int64 TotalAllocLength; // rsi
  __int64 v19; // r8
  __int64 result; // rax
  unsigned int i; // edx
  _QWORD *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r9
  char v26; // [rsp+70h] [rbp+18h] BYREF
  __int64 v27; // [rsp+78h] [rbp+20h]

  v27 = a4;
  v8 = a7;
  v9 = a6;
  v11 = a8;
  v13 = a3;
  v14 = *(_QWORD *)(a1 + 192);
  *a7 = 0;
  *v9 = 0;
  v15 = v13 + a2;
  *v11 = 0;
  if ( v13 + a2 <= v14 )
    return 0;
  if ( v15 > v14 + *(unsigned int *)(a1 + 208) )
    return 3221225507LL;
  TotalLength = QuicRecvBufferGetTotalLength();
  if ( v15 > TotalLength )
  {
    if ( v15 - TotalLength <= a5 )
    {
      *v17 = v15 - TotalLength;
      goto LABEL_6;
    }
    return 3221225507LL;
  }
LABEL_6:
  TotalAllocLength = (unsigned int)QuicRecvBufferGetTotalAllocLength(a1);
  if ( v15 > TotalAllocLength + v19 )
  {
    if ( *(_DWORD *)(a1 + 216) == 3 )
    {
      *v11 = v15 - TotalAllocLength - v19;
      return 3221225507LL;
    }
    for ( i = 2 * *(_DWORD *)(*(_QWORD *)(a1 + 8) + 16LL); v15 > v19 + (unsigned __int64)i; i *= 2 )
      ;
    if ( !(unsigned __int8)QuicRecvBufferResize() )
    {
      result = 3221225495LL;
      *v11 = v15 - *(_QWORD *)(a1 + 192) - TotalAllocLength;
      return result;
    }
  }
  v26 = 0;
  v22 = (_QWORD *)QuicRangeAddRange(a1 + 32, a2, v13, &v26);
  if ( v22 )
  {
    if ( v26 )
    {
      v25 = v27;
      *v8 = *v22 == 0;
      QuicRecvBufferCopyIntoChunks(a1, a2, (unsigned __int16)v13, v25);
    }
    return 0;
  }
  if ( (Microsoft_QuicEnableBits & 2) != 0 )
    McTemplateU0sx_EtwWriteTransfer(v24, v23, "recv_buffer range", 0);
  return 3221225495LL;
}

```

## disassembly

```asm
0x14000fbc0  mov     [rsp+arg_0], rbx
0x14000fbc5  mov     [rsp+arg_18], r9
0x14000fbca  push    rbp
0x14000fbcb  push    rsi
0x14000fbcc  push    rdi
0x14000fbcd  push    r12
0x14000fbcf  push    r13
0x14000fbd1  push    r14
0x14000fbd3  push    r15
0x14000fbd5  sub     rsp, 20h
0x14000fbd9  mov     r13, [rsp+58h+arg_30]
0x14000fbe1  xor     eax, eax
0x14000fbe3  mov     r10, [rsp+58h+arg_28]
0x14000fbeb  mov     rbp, rdx
0x14000fbee  mov     r14, [rsp+58h+arg_38]
0x14000fbf6  mov     rdi, rcx
0x14000fbf9  movzx   r12d, r8w
0x14000fbfd  mov     r8, [rcx+0C0h]
0x14000fc04  mov     byte ptr [r13+0], 0
0x14000fc09  mov     [r10], rax
0x14000fc0c  lea     rbx, [r12+rdx]
0x14000fc10  mov     [r14], rax
0x14000fc13  cmp     rbx, r8
0x14000fc16  jbe     loc_14000FD1C
0x14000fc1c  mov     eax, [rcx+0D0h]
0x14000fc22  add     rax, r8
0x14000fc25  cmp     rbx, rax
0x14000fc28  ja      short loc_14000FC6C
0x14000fc2a  call    QuicRecvBufferGetTotalLength
0x14000fc2f  cmp     rbx, rax
0x14000fc32  jbe     short loc_14000FC47
0x14000fc34  mov     rcx, rbx
0x14000fc37  sub     rcx, rax
0x14000fc3a  cmp     rcx, [rsp+58h+arg_20]
0x14000fc42  ja      short loc_14000FC6C
0x14000fc44  mov     [r10], rcx
0x14000fc47  mov     rcx, rdi
0x14000fc4a  call    QuicRecvBufferGetTotalAllocLength
0x14000fc4f  mov     esi, eax
0x14000fc51  lea     rax, [rsi+r8]
0x14000fc55  cmp     rbx, rax
0x14000fc58  jbe     short loc_14000FCB9
0x14000fc5a  cmp     dword ptr [rdi+0D8h], 3
0x14000fc61  jnz     short loc_14000FC76
0x14000fc63  sub     rbx, rsi
0x14000fc66  sub     rbx, r8
0x14000fc69  mov     [r14], rbx
0x14000fc6c  mov     eax, 0C0000023h
0x14000fc71  jmp     loc_14000FD1E
0x14000fc76  mov     rax, [rdi+8]
0x14000fc7a  mov     edx, [rax+10h]
0x14000fc7d  add     edx, edx
0x14000fc7f  mov     eax, edx
0x14000fc81  add     rax, r8
0x14000fc84  cmp     rbx, rax
0x14000fc87  jbe     short loc_14000FC9C
0x14000fc89  nop     dword ptr [rax+00000000h]
0x14000fc90  add     edx, edx
0x14000fc92  mov     eax, edx
0x14000fc94  add     rax, r8
0x14000fc97  cmp     rbx, rax
0x14000fc9a  ja      short loc_14000FC90
0x14000fc9c  call    QuicRecvBufferResize
0x14000fca1  test    al, al
0x14000fca3  jnz     short loc_14000FCB9
0x14000fca5  sub     rbx, [rdi+0C0h]
0x14000fcac  mov     eax, 0C0000017h
0x14000fcb1  sub     rbx, rsi
0x14000fcb4  mov     [r14], rbx
0x14000fcb7  jmp     short loc_14000FD1E
0x14000fcb9  lea     rcx, [rdi+20h]
0x14000fcbd  mov     [rsp+58h+arg_10], 0
0x14000fcc2  lea     r9, [rsp+58h+arg_10]
0x14000fcc7  mov     r8, r12
0x14000fcca  mov     rdx, rbp
0x14000fccd  call    QuicRangeAddRange
0x14000fcd2  test    rax, rax
0x14000fcd5  jnz     short loc_14000FCF6
0x14000fcd7  test    cs:Microsoft_QuicEnableBits, 2
0x14000fcde  jz      short loc_14000FCEF
0x14000fce0  xor     r9d, r9d
0x14000fce3  lea     r8, aRecvBufferRang; "recv_buffer range"
0x14000fcea  call    McTemplateU0sx_EtwWriteTransfer
0x14000fcef  mov     eax, 0C0000017h
0x14000fcf4  jmp     short loc_14000FD1E
0x14000fcf6  cmp     [rsp+58h+arg_10], 0
0x14000fcfb  jz      short loc_14000FD1C
0x14000fcfd  cmp     qword ptr [rax], 0
0x14000fd01  movzx   r8d, r12w
0x14000fd05  mov     r9, [rsp+58h+arg_18]
0x14000fd0a  mov     rdx, rbp
0x14000fd0d  setz    al
0x14000fd10  mov     rcx, rdi
0x14000fd13  mov     [r13+0], al
0x14000fd17  call    QuicRecvBufferCopyIntoChunks
0x14000fd1c  xor     eax, eax
0x14000fd1e  mov     rbx, [rsp+58h+arg_0]
0x14000fd23  add     rsp, 20h
0x14000fd27  pop     r15
0x14000fd29  pop     r14
0x14000fd2b  pop     r13
0x14000fd2d  pop     r12
0x14000fd2f  pop     rdi
0x14000fd30  pop     rsi
0x14000fd31  pop     rbp
0x14000fd32  retn
```
