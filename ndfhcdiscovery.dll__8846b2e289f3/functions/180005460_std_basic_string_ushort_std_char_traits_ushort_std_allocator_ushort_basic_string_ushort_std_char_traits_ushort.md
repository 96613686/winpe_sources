# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &&)

- ea: `0x180005460`
- end: `0x1800054e1`
- name: `??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z`
- size: `129`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x180003e68`
- `0x180003ebc`
- `0x18000597c`
- `0x180005aac`
- `0x18000c2b4`
- `0x18000c32c`
- `0x18000c3c4`
- `0x18000c4c4`
- `0x1800117e8`

## callees

- `0x180001fc2`
- `0x180005460`

## pseudocode

```c
_QWORD *__fastcall std::wstring::wstring(_QWORD *a1, _QWORD *a2)
{
  a1[3] = 7;
  a1[2] = 0;
  *(_WORD *)a1 = 0;
  if ( a2[3] >= 8u )
  {
    *a1 = *a2;
    *a2 = 0;
  }
  else if ( a2[2] != -1 )
  {
    memmove_0(a1, a2, 2 * (a2[2] + 1LL));
  }
  a1[2] = a2[2];
  a1[3] = a2[3];
  a2[3] = 7;
  a2[2] = 0;
  *(_WORD *)a2 = 0;
  return a1;
}

```

## disassembly

```asm
0x180005460  mov     [rsp+arg_0], rbx
0x180005465  push    rdi
0x180005466  sub     rsp, 20h
0x18000546a  xor     eax, eax
0x18000546c  mov     qword ptr [rcx+18h], 7
0x180005474  mov     qword ptr [rcx+10h], 0
0x18000547c  mov     rbx, rdx
0x18000547f  mov     [rcx], ax
0x180005482  mov     rdi, rcx
0x180005485  cmp     qword ptr [rdx+18h], 8
0x18000548a  jnb     short loc_1800054A0
0x18000548c  mov     r8, [rdx+10h]
0x180005490  add     r8, 1
0x180005494  jz      short loc_1800054AD
0x180005496  add     r8, r8; Size
0x180005499  call    memmove_0
0x18000549e  jmp     short loc_1800054AD
0x1800054a0  mov     rax, [rdx]
0x1800054a3  mov     [rcx], rax
0x1800054a6  mov     qword ptr [rdx], 0
0x1800054ad  mov     rax, [rbx+10h]
0x1800054b1  mov     [rdi+10h], rax
0x1800054b5  mov     rax, [rbx+18h]
0x1800054b9  mov     [rdi+18h], rax
0x1800054bd  xor     eax, eax
0x1800054bf  mov     qword ptr [rbx+18h], 7
0x1800054c7  mov     qword ptr [rbx+10h], 0
0x1800054cf  mov     [rbx], ax
0x1800054d2  mov     rax, rdi
0x1800054d5  mov     rbx, [rsp+28h+arg_0]
0x1800054da  add     rsp, 20h
0x1800054de  pop     rdi
0x1800054df  retn
```
