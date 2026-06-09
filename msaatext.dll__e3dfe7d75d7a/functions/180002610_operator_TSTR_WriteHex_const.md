# operator<<(TSTR &,WriteHex const &)

- ea: `0x180002610`
- end: `0x180002697`
- name: `??6@YAAEAVTSTR@@AEAV0@AEBVWriteHex@@@Z`
- size: `135`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180002474`
- `0x1800026d0`
- `0x180008930`
- `0x18000d38c`
- `0x18000dab0`
- `0x18000dba0`
- `0x18000df20`

## callees

- `0x180002610`
- `0x180003078`

## pseudocode

```c
void *__fastcall operator<<(void *Src, __int64 *a2)
{
  int v2; // ebx
  unsigned __int64 v5; // rax
  wchar_t v7; // [rsp+30h] [rbp+8h] BYREF

  v2 = *((_DWORD *)a2 + 2);
  if ( v2 != -1 )
    goto LABEL_7;
  v5 = *a2;
  v2 = 0;
  if ( !*a2 )
    goto LABEL_5;
  do
  {
    ++v2;
    v5 >>= 4;
  }
  while ( v5 );
  if ( !v2 )
LABEL_5:
    v2 = 1;
  do
  {
    v7 = a0123456789abcd[((unsigned __int64)*a2 >> (4 * (unsigned __int8)--v2)) & 0xF];
    std::wstring::append(Src, &v7);
LABEL_7:
    ;
  }
  while ( v2 );
  return Src;
}

```

## disassembly

```asm
0x180002610  mov     [rsp+arg_8], rbx
0x180002615  mov     [rsp+arg_10], rsi
0x18000261a  push    rdi
0x18000261b  sub     rsp, 20h
0x18000261f  mov     ebx, [rdx+8]
0x180002622  mov     rdi, rdx
0x180002625  mov     rsi, rcx
0x180002628  cmp     ebx, 0FFFFFFFFh
0x18000262b  jnz     short loc_180002680
0x18000262d  mov     rax, [rdx]
0x180002630  xor     ebx, ebx
0x180002632  test    rax, rax
0x180002635  jz      short loc_180002646
0x180002637  inc     ebx
0x180002639  shr     rax, 4
0x18000263d  test    rax, rax
0x180002640  jnz     short loc_180002637
0x180002642  test    ebx, ebx
0x180002644  jnz     short loc_18000264B
0x180002646  mov     ebx, 1
0x18000264b  mov     rax, [rdi]
0x18000264e  lea     rdx, [rsp+28h+arg_0]; void *
0x180002653  dec     ebx
0x180002655  mov     r8d, 1
0x18000265b  lea     ecx, ds:0[rbx*4]
0x180002662  shr     rax, cl
0x180002665  lea     rcx, a0123456789abcd; "0123456789ABCDEF"
0x18000266c  and     eax, 0Fh
0x18000266f  movzx   eax, word ptr [rcx+rax*2]
0x180002673  mov     rcx, rsi; Src
0x180002676  mov     [rsp+28h+arg_0], ax
0x18000267b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180002680  test    ebx, ebx
0x180002682  jnz     short loc_18000264B
0x180002684  mov     rbx, [rsp+28h+arg_8]
0x180002689  mov     rax, rsi
0x18000268c  mov     rsi, [rsp+28h+arg_10]
0x180002691  add     rsp, 20h
0x180002695  pop     rdi
0x180002696  retn
```
