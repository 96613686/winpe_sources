# TextLogFindSection

- ea: `0x180004e74`
- end: `0x180004ebc`
- name: `TextLogFindSection`
- size: `72`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800063bc`
- `0x180006590`

## callees

- `0x180004e0c`
- `0x180004e74`

## pseudocode

```c
__int64 __fastcall TextLogFindSection(__int64 a1, int a2, __int64 a3, unsigned int *a4)
{
  unsigned int v4; // ebx
  unsigned int v6; // edx
  __int64 v8; // rdi
  __int64 i; // r14
  __int64 result; // rax

  v4 = 0;
  v6 = 0;
  v8 = a3;
  for ( i = a1; ; a1 = i )
  {
    result = TextLogEnumerateOpenSections(a1, v6, a3);
    if ( !(_DWORD)result )
      break;
    if ( *(_DWORD *)(v8 + 4) == a2 )
    {
      *a4 = v4;
      return 1;
    }
    ++v4;
    a3 = v8;
    v6 = v4;
  }
  return result;
}

```

## disassembly

```asm
0x180004e74  push    rbx
0x180004e76  push    rbp
0x180004e77  push    rsi
0x180004e78  push    rdi
0x180004e79  push    r14
0x180004e7b  sub     rsp, 20h
0x180004e7f  xor     ebx, ebx
0x180004e81  mov     ebp, edx
0x180004e83  xor     edx, edx
0x180004e85  mov     rsi, r9
0x180004e88  mov     rdi, r8
0x180004e8b  mov     r14, rcx
0x180004e8e  jmp     short loc_180004E9F
0x180004e90  cmp     [rdi+4], ebp
0x180004e93  jz      short loc_180004EB3
0x180004e95  inc     ebx
0x180004e97  mov     r8, rdi
0x180004e9a  mov     edx, ebx
0x180004e9c  mov     rcx, r14
0x180004e9f  call    TextLogEnumerateOpenSections
0x180004ea4  test    eax, eax
0x180004ea6  jnz     short loc_180004E90
0x180004ea8  add     rsp, 20h
0x180004eac  pop     r14
0x180004eae  pop     rdi
0x180004eaf  pop     rsi
0x180004eb0  pop     rbp
0x180004eb1  pop     rbx
0x180004eb2  retn
0x180004eb3  mov     [rsi], ebx
0x180004eb5  mov     eax, 1
0x180004eba  jmp     short loc_180004EA8
```
