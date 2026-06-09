# ASN1BERDecNotEndOfContents

- ea: `0x180002200`
- end: `0x180002249`
- name: `ASN1BERDecNotEndOfContents`
- size: `73`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x180001010`
- `0x180001f80`
- `0x1800026b0`
- `0x180002c20`
- `0x180003270`
- `0x180003be0`
- `0x180004a60`
- `0x180005300`
- `0x180009c10`

## callees

- `0x180001f50`
- `0x180002200`

## pseudocode

```c
_BOOL8 __fastcall ASN1BERDecNotEndOfContents(__int64 a1, unsigned __int64 a2)
{
  _BYTE *v4; // rax

  if ( a2 )
    return *(_QWORD *)(a1 + 40) < a2;
  if ( (unsigned int)ASN1BERDecCheck((_DWORD *)a1, 2u) )
  {
    v4 = *(_BYTE **)(a1 + 40);
    if ( *v4 || v4[1] )
      return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180002200  push    rbx
0x180002202  sub     rsp, 20h
0x180002206  mov     rbx, rcx
0x180002209  test    rdx, rdx
0x18000220c  jz      short loc_18000221D
0x18000220e  xor     eax, eax
0x180002210  cmp     [rcx+28h], rdx
0x180002214  setb    al
0x180002217  add     rsp, 20h
0x18000221b  pop     rbx
0x18000221c  retn
0x18000221d  mov     edx, 2
0x180002222  call    ASN1BERDecCheck
0x180002227  test    eax, eax
0x180002229  jz      short loc_180002245
0x18000222b  mov     rax, [rbx+28h]
0x18000222f  cmp     byte ptr [rax], 0
0x180002232  jz      short loc_18000223F
0x180002234  mov     eax, 1
0x180002239  add     rsp, 20h
0x18000223d  pop     rbx
0x18000223e  retn
0x18000223f  cmp     byte ptr [rax+1], 0
0x180002243  jnz     short loc_180002234
0x180002245  xor     eax, eax
0x180002247  jmp     short loc_180002217
```
