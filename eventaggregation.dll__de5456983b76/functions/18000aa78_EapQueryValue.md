# EapQueryValue

- ea: `0x18000aa78`
- end: `0x18000aae2`
- name: `EapQueryValue`
- size: `106`
- prototype: `__int64 __fastcall(int, int, int, int, void *, int, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180009370`
- `0x18000a21c`
- `0x18000a368`

## callees

- `0x18000a528`
- `0x18000aa78`
- `0x18000bde9`

## pseudocode

```c
__int64 __fastcall EapQueryValue(void *a1, const WCHAR *a2, int a3, __int64 a4, void *a5, unsigned int a6, __int64 a7)
{
  unsigned int v7; // ebx
  int Buffer; // eax

  if ( a5 )
  {
    Buffer = EapQueryBuffer(a1, a2, a3, a7);
    v7 = Buffer;
    if ( Buffer == -1073741772 )
    {
      return 0;
    }
    else if ( Buffer >= 0 )
    {
      if ( a6 >= *(_DWORD *)(*(_QWORD *)a7 + 12LL) )
        memcpy_0(
          a5,
          (const void *)(*(_QWORD *)a7 + *(unsigned int *)(*(_QWORD *)a7 + 8LL)),
          *(unsigned int *)(*(_QWORD *)a7 + 12LL));
      else
        return (unsigned int)-1073741789;
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return v7;
}

```

## disassembly

```asm
0x18000aa78  mov     [rsp+arg_0], rbx
0x18000aa7d  push    rdi
0x18000aa7e  sub     rsp, 20h
0x18000aa82  cmp     [rsp+28h+arg_20], 0
0x18000aa88  jnz     short loc_18000AA91
0x18000aa8a  mov     ebx, 0C000000Dh
0x18000aa8f  jmp     short loc_18000AAD5
0x18000aa91  mov     rdi, [rsp+28h+arg_30]
0x18000aa96  mov     r9, rdi
0x18000aa99  call    EapQueryBuffer
0x18000aa9e  mov     ebx, eax
0x18000aaa0  cmp     eax, 0C0000034h
0x18000aaa5  jnz     short loc_18000AAAB
0x18000aaa7  xor     ebx, ebx
0x18000aaa9  jmp     short loc_18000AAD5
0x18000aaab  test    eax, eax
0x18000aaad  js      short loc_18000AAD5
0x18000aaaf  mov     rax, [rdi]
0x18000aab2  mov     ecx, [rax+0Ch]
0x18000aab5  cmp     [rsp+28h+arg_28], ecx
0x18000aab9  jnb     short loc_18000AAC2
0x18000aabb  mov     ebx, 0C0000023h
0x18000aac0  jmp     short loc_18000AAD5
0x18000aac2  mov     edx, [rax+8]
0x18000aac5  mov     r8, rcx; Size
0x18000aac8  mov     rcx, [rsp+28h+arg_20]; void *
0x18000aacd  add     rdx, rax; Src
0x18000aad0  call    memcpy_0
0x18000aad5  mov     eax, ebx
0x18000aad7  mov     rbx, [rsp+28h+arg_0]
0x18000aadc  add     rsp, 20h
0x18000aae0  pop     rdi
0x18000aae1  retn
```
