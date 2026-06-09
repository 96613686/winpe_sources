# SleepstudyJsonWriter::WriteRawString(ushort const *)

- ea: `0x180025ae4`
- end: `0x180025b35`
- name: `?WriteRawString@SleepstudyJsonWriter@@AEAAXPEBG@Z`
- size: `81`
- prototype: `void __fastcall(SleepstudyJsonWriter *__hidden this, const unsigned __int16 *)`
- caller_count: `18`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002574c`
- `0x180039a14`
- `0x180041e94`
- `0x1800781f8`
- `0x180078254`
- `0x1800782b0`
- `0x18007830c`
- `0x180078368`
- `0x18007840c`
- `0x1800786b4`
- `0x180078d4c`
- `0x1800791f4`
- `0x18007a5f0`
- `0x18007a65c`
- `0x18007bb94`
- `0x18007bbf8`
- `0x18007bc64`
- `0x18007dbc0`

## callees

- `0x180025ae4`
- `0x180025c30`
- `0x180025e28`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x180025b09`
- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x180025b09`

## pseudocode

```c
void __fastcall SleepstudyJsonWriter::WriteRawString(SleepstudyJsonWriter *this, const unsigned __int16 *a2)
{
  SleepstudyJsonWriter::WritePadding(this);
  while ( *a2 )
  {
    if ( __isascii(*a2) )
      std::basic_ostream<unsigned short>::operator<<((char *)this + 16, *a2);
    ++a2;
  }
}

```

## disassembly

```asm
0x180025ae4  mov     [rsp+arg_0], rbx
0x180025ae9  mov     [rsp+arg_8], rsi
0x180025aee  push    rdi
0x180025aef  sub     rsp, 20h
0x180025af3  mov     rbx, rdx
0x180025af6  mov     rdi, rcx
0x180025af9  call    ?WritePadding@SleepstudyJsonWriter@@AEAAXXZ; SleepstudyJsonWriter::WritePadding(void)
0x180025afe  movzx   eax, word ptr [rbx]
0x180025b01  test    ax, ax
0x180025b04  jz      short loc_180025B25
0x180025b06  movzx   ecx, ax; C
0x180025b09  call    cs:__imp___isascii
0x180025b0f  test    eax, eax
0x180025b11  jz      short loc_180025B1F
0x180025b13  movzx   edx, word ptr [rbx]
0x180025b16  lea     rcx, [rdi+10h]
0x180025b1a  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x180025b1f  add     rbx, 2
0x180025b23  jmp     short loc_180025AFE
0x180025b25  mov     rbx, [rsp+28h+arg_0]
0x180025b2a  mov     rsi, [rsp+28h+arg_8]
0x180025b2f  add     rsp, 20h
0x180025b33  pop     rdi
0x180025b34  retn
```
