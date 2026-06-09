# QuicConnReplaceRetiredCids

- ea: `0x140022950`
- end: `0x140022a95`
- name: `QuicConnReplaceRetiredCids`
- size: `325`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400108c0`

## callees

- `0x14001c638`
- `0x140022950`
- `0x140022a9c`
- `0x14003c8e0`
- `0x14003ec10`
- `0x140048c78`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x1400229e2`
- `ntoskrnl!_snprintf_s` at `0x1400229e2`

## string_xrefs

- `0x140022a65`: `Active path has no replacement for retired CID`
- `0x1400229cd`: `Non-active path has no replacement for retired CID.`

## pseudocode

```c
char __fastcall QuicConnReplaceRetiredCids(__int64 a1)
{
  unsigned __int8 v1; // di
  __int64 v3; // rax
  __int64 UnusedDestCid; // rax
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // rcx
  char DstBuf[128]; // [rsp+20h] [rbp-98h] BYREF

  v1 = 0;
  if ( !*(_BYTE *)(a1 + 275) )
    return 1;
  while ( 1 )
  {
    v3 = *(_QWORD *)(240LL * v1 + a1 + 464);
    if ( !v3 || (*(_BYTE *)(v3 + 32) & 0x20) == 0 )
      goto LABEL_10;
    UnusedDestCid = QuicConnGetUnusedDestCid(a1);
    if ( !UnusedDestCid )
      break;
    *(_QWORD *)(v6 + a1 + 464) = UnusedDestCid;
    *(_BYTE *)(UnusedDestCid + 32) |= 8u;
    *(_BYTE *)(v6 + a1 + 321) |= 4u;
LABEL_10:
    if ( ++v1 >= *(_BYTE *)(a1 + 275) )
      return 1;
  }
  if ( (*(_BYTE *)(v6 + a1 + 321) & 2) == 0 )
  {
    if ( (byte_14005C48B & 0x40) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Non-active path has no replacement for retired CID.");
      McTemplateU0ps_EtwWriteTransfer(v7, QuicConnLogWarning, a1, DstBuf);
    }
    QuicPathRemove(a1, v1--);
    goto LABEL_10;
  }
  if ( (byte_14005C48B & 4) != 0 )
    McTemplateU0ps_EtwWriteTransfer(v5, QuicConnError, a1, "Active path has no replacement for retired CID");
  QuicConnCloseLocally(a1, 19, -1073741536);
  return 0;
}

```

## disassembly

```asm
0x140022950  mov     [rsp+arg_8], rbx
0x140022955  push    rdi
0x140022956  sub     rsp, 0B0h
0x14002295d  mov     rax, cs:__security_cookie
0x140022964  xor     rax, rsp
0x140022967  mov     [rsp+0B8h+var_18], rax
0x14002296f  xor     dil, dil
0x140022972  mov     rbx, rcx
0x140022975  cmp     [rcx+113h], dil
0x14002297c  jbe     loc_140022A38
0x140022982  movzx   eax, dil
0x140022986  imul    r8, rax, 0F0h
0x14002298d  mov     rax, [r8+rbx+1D0h]
0x140022995  test    rax, rax
0x140022998  jz      loc_140022A28
0x14002299e  test    byte ptr [rax+20h], 20h
0x1400229a2  jz      loc_140022A28
0x1400229a8  mov     rcx, rbx
0x1400229ab  call    QuicConnGetUnusedDestCid
0x1400229b0  test    rax, rax
0x1400229b3  jnz     short loc_140022A13
0x1400229b5  test    byte ptr [r8+rbx+141h], 2
0x1400229be  jnz     loc_140022A5C
0x1400229c4  test    cs:byte_14005C48B, 40h
0x1400229cb  jz      short loc_140022A02
0x1400229cd  lea     r9, aNonActivePathH; "Non-active path has no replacement for "...
0x1400229d4  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1400229d8  mov     edx, 80h; SizeInBytes
0x1400229dd  lea     rcx, [rsp+0B8h+DstBuf]; DstBuf
0x1400229e2  call    cs:__imp__snprintf_s
0x1400229e9  nop     dword ptr [rax+rax+00h]
0x1400229ee  lea     r9, [rsp+0B8h+DstBuf]
0x1400229f3  mov     r8, rbx
0x1400229f6  lea     rdx, QuicConnLogWarning
0x1400229fd  call    McTemplateU0ps_EtwWriteTransfer
0x140022a02  mov     dl, dil
0x140022a05  mov     rcx, rbx
0x140022a08  call    QuicPathRemove
0x140022a0d  add     dil, 0FFh
0x140022a11  jmp     short loc_140022A28
0x140022a13  mov     [r8+rbx+1D0h], rax
0x140022a1b  or      byte ptr [rax+20h], 8
0x140022a1f  or      byte ptr [r8+rbx+141h], 4
0x140022a28  inc     dil
0x140022a2b  cmp     dil, [rbx+113h]
0x140022a32  jb      loc_140022982
0x140022a38  mov     al, 1
0x140022a3a  mov     rcx, [rsp+0B8h+var_18]
0x140022a42  xor     rcx, rsp; StackCookie
0x140022a45  call    __security_check_cookie
0x140022a4a  mov     rbx, [rsp+0B8h+arg_8]
0x140022a52  add     rsp, 0B0h
0x140022a59  pop     rdi
0x140022a5a  retn
0x140022a5c  test    cs:byte_14005C48B, 4
0x140022a63  jz      short loc_140022A7B
0x140022a65  lea     r9, aActivePathHasN; "Active path has no replacement for reti"...
0x140022a6c  mov     r8, rbx
0x140022a6f  lea     rdx, QuicConnError
0x140022a76  call    McTemplateU0ps_EtwWriteTransfer
0x140022a7b  xor     r9d, r9d
0x140022a7e  mov     r8, 0FFFFFFFFC0000120h
0x140022a85  mov     rcx, rbx
0x140022a88  lea     edx, [r9+13h]
0x140022a8c  call    QuicConnCloseLocally
0x140022a91  xor     al, al
0x140022a93  jmp     short loc_140022A3A
```
