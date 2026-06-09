# MdaIsEAPresent

- ea: `0x14002840c`
- end: `0x140028470`
- name: `MdaIsEAPresent`
- size: `100`
- prototype: `char __fastcall(char *Str1, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140025be0`

## callees

- `0x14002840c`
- `0x14003aad6`

## string_xrefs

- `0x140028452`: `MountOptions`

## pseudocode

```c
char __fastcall MdaIsEAPresent(char *Str1, unsigned int a2)
{
  unsigned int i; // ebx

  for ( i = 0; ; ++i )
  {
    while ( 1 )
    {
      if ( i >= a2 )
        return 0;
      if ( *Str1 == 77 )
        break;
      ++Str1;
      ++i;
    }
    if ( i + 12 <= a2 && !strncmp_0(Str1, "MountOptions", 0xCu) )
      break;
    ++Str1;
  }
  return 1;
}

```

## disassembly

```asm
0x14002840c  mov     [rsp+arg_0], rbx
0x140028411  mov     [rsp+arg_8], rsi
0x140028416  push    rdi
0x140028417  sub     rsp, 20h
0x14002841b  mov     esi, edx
0x14002841d  mov     rdi, rcx
0x140028420  xor     ebx, ebx
0x140028422  jmp     short loc_14002842E
0x140028424  cmp     byte ptr [rdi], 4Dh ; 'M'
0x140028427  jz      short loc_140028445
0x140028429  inc     rdi
0x14002842c  inc     ebx
0x14002842e  cmp     ebx, esi
0x140028430  jb      short loc_140028424
0x140028432  xor     al, al
0x140028434  mov     rbx, [rsp+28h+arg_0]
0x140028439  mov     rsi, [rsp+28h+arg_8]
0x14002843e  add     rsp, 20h
0x140028442  pop     rdi
0x140028443  retn
0x140028445  lea     eax, [rbx+0Ch]
0x140028448  cmp     eax, esi
0x14002844a  ja      short loc_140028465
0x14002844c  mov     r8d, 0Ch; MaxCount
0x140028452  lea     rdx, Str2; "MountOptions"
0x140028459  mov     rcx, rdi; Str1
0x14002845c  call    strncmp_0
0x140028461  test    eax, eax
0x140028463  jz      short loc_14002846C
0x140028465  inc     rdi
0x140028468  inc     ebx
0x14002846a  jmp     short loc_14002842E
0x14002846c  mov     al, 1
0x14002846e  jmp     short loc_140028434
```
