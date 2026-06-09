# NsippIsMatchingObject

- ea: `0x140004d70`
- end: `0x140004e23`
- name: `NsippIsMatchingObject`
- size: `179`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140001880`
- `0x1400033c0`
- `0x140004d10`

## callees

- `0x140004d70`

## import_xrefs

- `NETIO!NsiGetModuleHandle` at `0x140004de4`
- `NETIO!NsiGetModuleHandle` at `0x140004de4`

## pseudocode

```c
bool __fastcall NsippIsMatchingObject(int *a1, int *a2)
{
  int v2; // eax
  int v3; // ebx
  _QWORD *v4; // r9
  _QWORD *v5; // r8
  __int64 v6; // rax
  __int64 v8; // [rsp+20h] [rbp-18h] BYREF
  __int64 v9; // [rsp+28h] [rbp-10h]

  v2 = a2[4];
  v9 = 0;
  if ( a1[4] != v2 )
    return 0;
  v3 = *a1;
  if ( !*a1 || !*a2 )
  {
    v4 = (_QWORD *)*((_QWORD *)a1 + 1);
    v5 = (_QWORD *)*((_QWORD *)a2 + 1);
    if ( v4 )
    {
      if ( v5 )
      {
        v6 = *v4 - *v5;
        if ( *v4 == *v5 )
        {
          v6 = v4[1] - v5[1];
          if ( !v6 )
            v6 = v4[2] - v5[2];
        }
        return !v6;
      }
      v3 = *a2;
      v8 = *((_QWORD *)a1 + 1);
      if ( !v3 )
        return 0;
    }
    else
    {
      if ( !v5 )
        return 0;
      v8 = *((_QWORD *)a2 + 1);
      if ( !v3 )
        return 0;
    }
    return (int)NsiGetModuleHandle(&v8) >= 0 && v3 == (_DWORD)v9;
  }
  return v3 == *a2;
}

```

## disassembly

```asm
0x140004d70  push    rbx
0x140004d72  sub     rsp, 30h
0x140004d76  mov     eax, [rdx+10h]
0x140004d79  mov     [rsp+38h+var_10], 0
0x140004d82  cmp     [rcx+10h], eax
0x140004d85  jnz     short loc_140004DD6
0x140004d87  mov     ebx, [rcx]
0x140004d89  test    ebx, ebx
0x140004d8b  jnz     loc_140004E13
0x140004d91  mov     r9, [rcx+8]
0x140004d95  mov     r8, [rdx+8]
0x140004d99  test    r9, r9
0x140004d9c  jz      short loc_140004E03
0x140004d9e  test    r8, r8
0x140004da1  jz      short loc_140004DCB
0x140004da3  mov     rax, [r9]
0x140004da6  sub     rax, [r8]
0x140004da9  jnz     short loc_140004DBD
0x140004dab  mov     rax, [r9+8]
0x140004daf  sub     rax, [r8+8]
0x140004db3  jnz     short loc_140004DBD
0x140004db5  mov     rax, [r9+10h]
0x140004db9  sub     rax, [r8+10h]
0x140004dbd  test    rax, rax
0x140004dc0  jz      short loc_140004DFA
0x140004dc2  xor     al, al
0x140004dc4  add     rsp, 30h
0x140004dc8  pop     rbx
0x140004dc9  retn
0x140004dcb  mov     ebx, [rdx]
0x140004dcd  mov     [rsp+38h+var_18], r9
0x140004dd2  test    ebx, ebx
0x140004dd4  jnz     short loc_140004DDF
0x140004dd6  xor     al, al
0x140004dd8  add     rsp, 30h
0x140004ddc  pop     rbx
0x140004ddd  retn
0x140004ddf  lea     rcx, [rsp+38h+var_18]
0x140004de4  call    cs:__imp_NsiGetModuleHandle
0x140004deb  nop     dword ptr [rax+rax+00h]
0x140004df0  test    eax, eax
0x140004df2  js      short loc_140004DD6
0x140004df4  cmp     ebx, dword ptr [rsp+38h+var_10]
0x140004df8  jnz     short loc_140004DD6
0x140004dfa  mov     al, 1
0x140004dfc  add     rsp, 30h
0x140004e00  pop     rbx
0x140004e01  retn
0x140004e03  test    r8, r8
0x140004e06  jz      short loc_140004DD6
0x140004e08  mov     [rsp+38h+var_18], r8
0x140004e0d  test    ebx, ebx
0x140004e0f  jz      short loc_140004DD6
0x140004e11  jmp     short loc_140004DDF
0x140004e13  mov     eax, [rdx]
0x140004e15  test    eax, eax
0x140004e17  jz      loc_140004D91
0x140004e1d  cmp     ebx, eax
0x140004e1f  jnz     short loc_140004DD6
0x140004e21  jmp     short loc_140004DFA
```
