# CPorts::SetConfig(ushort const *)

- ea: `0x18001acf8`
- end: `0x18001ae10`
- name: `?SetConfig@CPorts@@QEAAJPEBG@Z`
- size: `280`
- prototype: `__int64 __fastcall(CPorts *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000d1c0`

## callees

- `0x18000e4e0`
- `0x18001a2e0`
- `0x18001acf8`
- `0x18002cde0`
- `0x18002ce80`
- `0x18002d0a4`
- `0x18002e202`

## import_xrefs

- `msvcrt!free` at `0x18001add4`
- `msvcrt!free` at `0x18001adef`
- `msvcrt!free` at `0x18001add4`
- `msvcrt!free` at `0x18001adef`

## pseudocode

```c
__int64 __fastcall CPorts::SetConfig(CPorts *this, const unsigned __int16 *a2)
{
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rbx
  unsigned __int128 v7; // rax
  void *v8; // rax
  unsigned int inserted; // ebx
  unsigned __int16 *v10; // rdi
  void *Block; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int16 *v12; // [rsp+50h] [rbp+18h] BYREF
  const unsigned __int16 *v13; // [rsp+58h] [rbp+20h] BYREF

  if ( *(_QWORD *)this )
    return 2147549183LL;
  v5 = CPortParser::CountPorts(a2);
  v6 = v5;
  if ( !v5 )
    return 2147942487LL;
  v7 = v5 * (unsigned __int128)0x18uLL;
  if ( !is_mul_ok(v6, 0x18u) )
    *(_QWORD *)&v7 = -1;
  v8 = operator new[](v7, *((const struct std::nothrow_t **)&v7 + 1));
  *(_QWORD *)this = v8;
  if ( !v8 )
    return 2147942414LL;
  memset_0(v8, 0, 24 * v6);
  inserted = 0;
  v13 = a2;
  v12 = 0;
  do
  {
    if ( (unsigned int)CPortParser::GetIPAddress((CPortParser *)&v13, 1, &v12) )
      break;
    v10 = v12;
    Block = 0;
    do
    {
      if ( (unsigned int)CPortParser::GetNextPort((CPortParser *)&v13, 1, (unsigned __int16 **)&Block) )
        break;
      inserted = CPorts::InsertPort(this, v10, (const unsigned __int16 *)Block);
      free(Block);
      Block = 0;
    }
    while ( !inserted );
    if ( v10 )
    {
      free(v10);
      v12 = 0;
    }
  }
  while ( !inserted );
  return inserted;
}

```

## disassembly

```asm
0x18001acf8  push    rbx
0x18001acfa  push    rsi
0x18001acfb  push    rdi
0x18001acfc  sub     rsp, 20h
0x18001ad00  cmp     qword ptr [rcx], 0
0x18001ad04  mov     rdi, rdx
0x18001ad07  mov     rsi, rcx
0x18001ad0a  jz      short loc_18001AD16
0x18001ad0c  mov     eax, 8000FFFFh
0x18001ad11  jmp     loc_18001AE08
0x18001ad16  mov     rcx, rdi; unsigned __int16 *
0x18001ad19  call    ?CountPorts@CPortParser@@SA_KPEBG@Z; CPortParser::CountPorts(ushort const *)
0x18001ad1e  mov     rbx, rax
0x18001ad21  test    rax, rax
0x18001ad24  jnz     short loc_18001AD30
0x18001ad26  mov     eax, 80070057h
0x18001ad2b  jmp     loc_18001AE08
0x18001ad30  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001ad37  mov     eax, 18h
0x18001ad3c  mul     rbx
0x18001ad3f  cmovb   rax, rcx
0x18001ad43  mov     rcx, rax; Size
0x18001ad46  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001ad4b  mov     [rsi], rax
0x18001ad4e  test    rax, rax
0x18001ad51  jnz     short loc_18001AD5D
0x18001ad53  mov     eax, 8007000Eh
0x18001ad58  jmp     loc_18001AE08
0x18001ad5d  lea     r8, [rbx+rbx*2]
0x18001ad61  xor     edx, edx; Val
0x18001ad63  shl     r8, 3; Size
0x18001ad67  mov     rcx, rax; void *
0x18001ad6a  call    memset_0
0x18001ad6f  xor     ebx, ebx
0x18001ad71  mov     [rsp+38h+arg_18], rdi
0x18001ad76  mov     [rsp+38h+arg_10], 0
0x18001ad7f  lea     r8, [rsp+38h+arg_10]; unsigned __int16 **
0x18001ad84  mov     edx, 1; int
0x18001ad89  lea     rcx, [rsp+38h+arg_18]; this
0x18001ad8e  call    ?GetIPAddress@CPortParser@@QEAAJHPEAPEAG@Z; CPortParser::GetIPAddress(int,ushort * *)
0x18001ad93  test    eax, eax
0x18001ad95  jnz     short loc_18001AE06
0x18001ad97  mov     rdi, [rsp+38h+arg_10]
0x18001ad9c  mov     [rsp+38h+Block], 0
0x18001ada5  lea     r8, [rsp+38h+Block]; unsigned __int16 **
0x18001adaa  mov     edx, 1; int
0x18001adaf  lea     rcx, [rsp+38h+arg_18]; this
0x18001adb4  call    ?GetNextPort@CPortParser@@QEAAJHPEAPEAG@Z; CPortParser::GetNextPort(int,ushort * *)
0x18001adb9  test    eax, eax
0x18001adbb  jnz     short loc_18001ADE7
0x18001adbd  mov     r8, [rsp+38h+Block]; unsigned __int16 *
0x18001adc2  mov     rdx, rdi; unsigned __int16 *
0x18001adc5  mov     rcx, rsi; this
0x18001adc8  call    ?InsertPort@CPorts@@AEAAJPEBG0@Z; CPorts::InsertPort(ushort const *,ushort const *)
0x18001adcd  mov     rcx, [rsp+38h+Block]; Block
0x18001add2  mov     ebx, eax
0x18001add4  call    cs:__imp_free
0x18001adda  mov     [rsp+38h+Block], 0
0x18001ade3  test    ebx, ebx
0x18001ade5  jz      short loc_18001ADA5
0x18001ade7  test    rdi, rdi
0x18001adea  jz      short loc_18001ADFE
0x18001adec  mov     rcx, rdi; Block
0x18001adef  call    cs:__imp_free
0x18001adf5  mov     [rsp+38h+arg_10], 0
0x18001adfe  test    ebx, ebx
0x18001ae00  jz      loc_18001AD7F
0x18001ae06  mov     eax, ebx
0x18001ae08  add     rsp, 20h
0x18001ae0c  pop     rdi
0x18001ae0d  pop     rsi
0x18001ae0e  pop     rbx
0x18001ae0f  retn
```
