# CompareCategoryAscending(void const *,void const *)

- ea: `0x18001a0c0`
- end: `0x18001a134`
- name: `?CompareCategoryAscending@@YAHPEBX0@Z`
- size: `116`
- prototype: `__int64 __fastcall(const void *, const void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001a140`

## callees

- `0x18001a0c0`

## import_xrefs

- `KERNEL32!lstrcmpW` at `0x18001a0f7`
- `KERNEL32!lstrcmpW` at `0x18001a0f7`

## pseudocode

```c
int __fastcall CompareCategoryAscending(_QWORD *a1, int *a2)
{
  const WCHAR *v3; // rcx
  __int64 v5; // r8
  int result; // eax
  int v7; // eax
  __int16 v8; // cx

  v3 = (const WCHAR *)a1[1];
  v5 = *((_QWORD *)a2 + 1) >> 16;
  if ( WORD1(v3) )
  {
    if ( !(_WORD)v5 )
      return 1;
    result = lstrcmpW(v3, *((LPCWSTR *)a2 + 1));
    if ( result )
      return result;
    v7 = *a2;
    return v7 - *(_DWORD *)a1;
  }
  if ( (_WORD)v5 )
    return -1;
  v8 = (_WORD)v3 - *((_WORD *)a2 + 4);
  result = v8;
  if ( !v8 )
  {
    v7 = *a2;
    return v7 - *(_DWORD *)a1;
  }
  return result;
}

```

## disassembly

```asm
0x18001a0c0  mov     [rsp+arg_0], rbx
0x18001a0c5  mov     [rsp+arg_8], rsi
0x18001a0ca  push    rdi
0x18001a0cb  sub     rsp, 20h
0x18001a0cf  mov     r8, [rdx+8]
0x18001a0d3  mov     rdi, rcx
0x18001a0d6  mov     rcx, [rcx+8]; lpString1
0x18001a0da  mov     rbx, rdx
0x18001a0dd  mov     rax, rcx
0x18001a0e0  shr     r8, 10h
0x18001a0e4  shr     rax, 10h
0x18001a0e8  test    ax, ax
0x18001a0eb  jz      short loc_18001A10C
0x18001a0ed  test    r8w, r8w
0x18001a0f1  jz      short loc_18001A105
0x18001a0f3  mov     rdx, [rdx+8]; lpString2
0x18001a0f7  call    cs:__imp_lstrcmpW
0x18001a0fd  test    eax, eax
0x18001a0ff  jnz     short loc_18001A124
0x18001a101  mov     eax, [rbx]
0x18001a103  jmp     short loc_18001A122
0x18001a105  mov     eax, 1
0x18001a10a  jmp     short loc_18001A124
0x18001a10c  test    r8w, r8w
0x18001a110  jz      short loc_18001A117
0x18001a112  or      eax, 0FFFFFFFFh
0x18001a115  jmp     short loc_18001A124
0x18001a117  sub     cx, [rdx+8]
0x18001a11b  movsx   eax, cx
0x18001a11e  jnz     short loc_18001A124
0x18001a120  mov     eax, [rdx]
0x18001a122  sub     eax, [rdi]
0x18001a124  mov     rbx, [rsp+28h+arg_0]
0x18001a129  mov     rsi, [rsp+28h+arg_8]
0x18001a12e  add     rsp, 20h
0x18001a132  pop     rdi
0x18001a133  retn
```
