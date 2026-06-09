# SleepstudyJsonWriter::WriteKeyValue<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &>(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800255ac`
- end: `0x18002561f`
- name: `??$WriteKeyValue@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@SleepstudyJsonWriter@@QEAAXPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `115`
- prototype: `__int64 __fastcall(SleepstudyJsonWriter *this, unsigned __int16 *, __int64)`
- caller_count: `14`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180039a14`
- `0x180078a18`
- `0x180078d4c`
- `0x1800793a0`
- `0x1800793d8`
- `0x180079520`
- `0x180079658`
- `0x1800798f0`
- `0x18007a0fc`
- `0x18007bc64`
- `0x18007d104`
- `0x18007d598`
- `0x18007dc1c`
- `0x18007e004`

## callees

- `0x1800255ac`
- `0x180025a34`
- `0x180025b3c`
- `0x180025c30`
- `0x180025e28`
- `0x180045e80`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x1800255ea`
- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x1800255ea`

## pseudocode

```c
__int64 __fastcall SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(
        SleepstudyJsonWriter *this,
        unsigned __int16 *a2,
        __int64 a3)
{
  const unsigned __int16 *v6; // rbx
  unsigned __int16 v7; // ax

  SleepstudyJsonWriter::InsertElement(this, 1);
  SleepstudyJsonWriter::Write(this, a2);
  v6 = L":";
  SleepstudyJsonWriter::WritePadding(this);
  v7 = 58;
  do
  {
    if ( __isascii(v7) )
      std::basic_ostream<unsigned short>::operator<<((char *)this + 16, *v6);
    v7 = *++v6;
  }
  while ( *v6 );
  return SleepstudyJsonWriter::Write(this, a3);
}

```

## disassembly

```asm
0x1800255ac  push    rbx
0x1800255ae  push    rbp
0x1800255af  push    rsi
0x1800255b0  push    rdi
0x1800255b1  sub     rsp, 28h
0x1800255b5  mov     rbx, rdx
0x1800255b8  mov     rsi, r8
0x1800255bb  mov     edx, 1
0x1800255c0  mov     rdi, rcx
0x1800255c3  call    ?InsertElement@SleepstudyJsonWriter@@AEAAXW4JsonPartialValueType@1@@Z; SleepstudyJsonWriter::InsertElement(SleepstudyJsonWriter::JsonPartialValueType)
0x1800255c8  mov     rdx, rbx; unsigned __int16 *
0x1800255cb  mov     rcx, rdi; this
0x1800255ce  call    ?Write@SleepstudyJsonWriter@@AEAAXPEBG@Z; SleepstudyJsonWriter::Write(ushort const *)
0x1800255d3  mov     rcx, rdi; this
0x1800255d6  lea     rbx, asc_18009D148; ":"
0x1800255dd  call    ?WritePadding@SleepstudyJsonWriter@@AEAAXXZ; SleepstudyJsonWriter::WritePadding(void)
0x1800255e2  mov     eax, 3Ah ; ':'
0x1800255e7  movzx   ecx, ax; C
0x1800255ea  call    cs:__imp___isascii
0x1800255f0  test    eax, eax
0x1800255f2  jz      short loc_180025600
0x1800255f4  movzx   edx, word ptr [rbx]
0x1800255f7  lea     rcx, [rdi+10h]
0x1800255fb  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x180025600  add     rbx, 2
0x180025604  movzx   eax, word ptr [rbx]
0x180025607  test    ax, ax
0x18002560a  jnz     short loc_1800255E7
0x18002560c  mov     rdx, rsi
0x18002560f  mov     rcx, rdi
0x180025612  add     rsp, 28h
0x180025616  pop     rdi
0x180025617  pop     rsi
0x180025618  pop     rbp
0x180025619  pop     rbx
0x18002561a  jmp     ?Write@SleepstudyJsonWriter@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SleepstudyJsonWriter::Write(std::wstring const &)
```
