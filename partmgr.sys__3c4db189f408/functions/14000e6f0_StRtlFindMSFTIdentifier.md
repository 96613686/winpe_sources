# StRtlFindMSFTIdentifier

- ea: `0x14000e6f0`
- end: `0x14000e794`
- name: `StRtlFindMSFTIdentifier`
- size: `164`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000cd18`
- `0x14002589c`

## callees

- `0x14000e6f0`
- `0x140010f20`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14000e755`
- `ntoskrnl!RtlCompareMemory` at `0x14000e755`

## pseudocode

```c
__int64 __fastcall StRtlFindMSFTIdentifier(__int64 a1)
{
  __int64 v1; // rbx
  unsigned int v2; // edi
  _QWORD Source2[2]; // [rsp+20h] [rbp-48h] BYREF

  v1 = a1 + 12;
  v2 = 0;
  strcpy((char *)Source2, "MSFT    ");
  if ( !*(_DWORD *)(a1 + 8) )
    return 0;
  while ( *(_DWORD *)v1 != 1
       || *(_DWORD *)(v1 + 4) != 1
       || *(_DWORD *)(v1 + 12)
       || *(_WORD *)(v1 + 8) != 24
       || RtlCompareMemory((const void *)(v1 + 16), Source2, 8u) != 8 )
  {
    ++v2;
    v1 += *(unsigned __int16 *)(v1 + 10);
    if ( v2 >= *(_DWORD *)(a1 + 8) )
      return 0;
  }
  return v1 + 16;
}

```

## disassembly

```asm
0x14000e6f0  push    rbx
0x14000e6f2  push    rbp
0x14000e6f3  push    rsi
0x14000e6f4  push    rdi
0x14000e6f5  sub     rsp, 48h
0x14000e6f9  mov     rax, cs:__security_cookie
0x14000e700  xor     rax, rsp
0x14000e703  mov     [rsp+68h+var_38], rax
0x14000e708  movsd   xmm0, qword ptr cs:aMsft; "MSFT    "
0x14000e710  lea     rbx, [rcx+0Ch]
0x14000e714  mov     al, byte ptr cs:aMsft+8; ""
0x14000e71a  xor     edi, edi
0x14000e71c  mov     rbp, rcx
0x14000e71f  movsd   [rsp+68h+Source2], xmm0
0x14000e725  mov     [rsp+68h+var_40], al
0x14000e729  cmp     [rcx+8], edi
0x14000e72c  jbe     short loc_14000E775
0x14000e72e  cmp     dword ptr [rbx], 1
0x14000e731  jnz     short loc_14000E767
0x14000e733  cmp     dword ptr [rbx+4], 1
0x14000e737  jnz     short loc_14000E767
0x14000e739  cmp     dword ptr [rbx+0Ch], 0
0x14000e73d  jnz     short loc_14000E767
0x14000e73f  cmp     word ptr [rbx+8], 18h
0x14000e744  jnz     short loc_14000E767
0x14000e746  mov     r8d, 8; Length
0x14000e74c  lea     rdx, [rsp+68h+Source2]; Source2
0x14000e751  lea     rcx, [rbx+10h]; Source1
0x14000e755  call    cs:__imp_RtlCompareMemory
0x14000e75c  nop     dword ptr [rax+rax+00h]
0x14000e761  cmp     rax, 8
0x14000e765  jz      short loc_14000E78E
0x14000e767  movzx   eax, word ptr [rbx+0Ah]
0x14000e76b  inc     edi
0x14000e76d  add     rbx, rax
0x14000e770  cmp     edi, [rbp+8]
0x14000e773  jb      short loc_14000E72E
0x14000e775  xor     eax, eax
0x14000e777  mov     rcx, [rsp+68h+var_38]
0x14000e77c  xor     rcx, rsp; StackCookie
0x14000e77f  call    __security_check_cookie
0x14000e784  add     rsp, 48h
0x14000e788  pop     rdi
0x14000e789  pop     rsi
0x14000e78a  pop     rbp
0x14000e78b  pop     rbx
0x14000e78c  retn
0x14000e78e  lea     rax, [rbx+10h]
0x14000e792  jmp     short loc_14000E777
```
