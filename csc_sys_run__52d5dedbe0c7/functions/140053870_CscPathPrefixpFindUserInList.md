# CscPathPrefixpFindUserInList

- ea: `0x140053870`
- end: `0x1400538b6`
- name: `CscPathPrefixpFindUserInList`
- size: `70`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14004acac`
- `0x140053338`
- `0x1400537a0`

## callees

- `0x140053870`

## import_xrefs

- `ntoskrnl!RtlEqualSid` at `0x140053891`
- `ntoskrnl!RtlEqualSid` at `0x140053891`

## pseudocode

```c
_QWORD *__fastcall CscPathPrefixpFindUserInList(__int64 a1, void *a2)
{
  _QWORD *v2; // rsi
  _QWORD *v4; // rbx
  __int64 v5; // rdi

  v2 = (_QWORD *)(a1 + 120);
  v4 = *(_QWORD **)(a1 + 120);
  v5 = 0;
  while ( v4 != v2 )
  {
    if ( RtlEqualSid(v4 + 2, a2) )
      return v4;
    v4 = (_QWORD *)*v4;
  }
  return (_QWORD *)v5;
}

```

## disassembly

```asm
0x140053870  push    rbx
0x140053872  push    rbp
0x140053873  push    rsi
0x140053874  push    rdi
0x140053875  sub     rsp, 28h
0x140053879  lea     rsi, [rcx+78h]
0x14005387d  mov     rbp, rdx
0x140053880  mov     rbx, [rsi]
0x140053883  xor     edi, edi
0x140053885  cmp     rbx, rsi
0x140053888  jz      short loc_1400538A9
0x14005388a  lea     rcx, [rbx+10h]; Sid1
0x14005388e  mov     rdx, rbp; Sid2
0x140053891  call    cs:__imp_RtlEqualSid
0x140053898  nop     dword ptr [rax+rax+00h]
0x14005389d  test    al, al
0x14005389f  jnz     short loc_1400538A6
0x1400538a1  mov     rbx, [rbx]
0x1400538a4  jmp     short loc_140053885
0x1400538a6  mov     rdi, rbx
0x1400538a9  mov     rax, rdi
0x1400538ac  add     rsp, 28h
0x1400538b0  pop     rdi
0x1400538b1  pop     rsi
0x1400538b2  pop     rbp
0x1400538b3  pop     rbx
0x1400538b4  retn
```
