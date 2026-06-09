# __memset_repmovs

- ea: `0x140003a40`
- end: `0x140003a83`
- name: `__memset_repmovs`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003900`

## callees

- `0x140003a40`
- `0x140003ac0`

## pseudocode

```c
__int64 __fastcall _memset_repmovs(_OWORD *a1, __int64 a2, __int64 a3)
{
  __int128 v3; // xmm0
  __int64 result; // rax

  if ( (WmiRegistrationContext.DeviceQueue.Busy & 1) == 0 )
    result = _memset_query();
  *a1 = v3;
  a1[1] = v3;
  a1[2] = v3;
  a1[3] = v3;
  memset(
    (void *)((unsigned __int64)(a1 + 4) & 0xFFFFFFFFFFFFFFC0uLL),
    v3,
    (unsigned __int64)a1 + a3 - ((unsigned __int64)(a1 + 4) & 0xFFFFFFFFFFFFFFC0uLL));
  return result;
}

```

## disassembly

```asm
0x140003a40  push    rdi
0x140003a41  test    byte ptr cs:WmiRegistrationContext.DeviceQueue.20h, 1
0x140003a48  jz      short loc_140003A7C
0x140003a4a  mov     rdi, rcx
0x140003a4d  add     r8, rcx
0x140003a50  movups  xmmword ptr [rcx], xmm0
0x140003a53  add     rdi, 40h ; '@'
0x140003a57  movups  xmmword ptr [rcx+10h], xmm0
0x140003a5b  and     rdi, 0FFFFFFFFFFFFFFC0h
0x140003a5f  movups  xmmword ptr [rcx+20h], xmm0
0x140003a63  sub     r8, rdi
0x140003a66  movups  xmmword ptr [rcx+30h], xmm0
0x140003a6a  mov     rcx, r8
0x140003a6d  mov     r9, rax
0x140003a70  movq    rax, xmm0
0x140003a75  rep stosb
0x140003a77  mov     rax, r9
0x140003a7a  pop     rdi
0x140003a7b  retn
0x140003a7c  call    __memset_query
0x140003a81  jmp     short loc_140003A4A
```
