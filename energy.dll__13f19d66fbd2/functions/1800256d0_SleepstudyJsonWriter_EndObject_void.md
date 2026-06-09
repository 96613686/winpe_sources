# SleepstudyJsonWriter::EndObject(void)

- ea: `0x1800256d0`
- end: `0x180025745`
- name: `?EndObject@SleepstudyJsonWriter@@QEAAXXZ`
- size: `117`
- prototype: `void __fastcall(SleepstudyJsonWriter *__hidden this)`
- caller_count: `12`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180039a14`
- `0x1800488b4`
- `0x18004a180`
- `0x18004a360`
- `0x18007bc64`
- `0x18007cfc0`
- `0x18007d104`
- `0x18007d598`
- `0x18007dc1c`
- `0x18007de30`
- `0x18007e004`
- `0x18007e440`

## callees

- `0x1800256d0`
- `0x180025c30`
- `0x180025e28`
- `0x180025ea8`
- `0x180025f74`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x180025713`
- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x180025713`

## pseudocode

```c
void __fastcall SleepstudyJsonWriter::EndObject(SleepstudyJsonWriter *this)
{
  const wchar_t *v2; // rbx
  unsigned __int16 v3; // ax

  SleepstudyJsonWriter::GetCurrentPartialValue((__int64)this, 1);
  *((_QWORD *)this + 36) -= 8LL;
  SleepstudyJsonWriter::WriteNewLine(this);
  v2 = L"}";
  SleepstudyJsonWriter::WritePadding(this);
  v3 = 125;
  do
  {
    if ( __isascii(v3) )
      std::basic_ostream<unsigned short>::operator<<((char *)this + 16, *v2);
    v3 = *++v2;
  }
  while ( *v2 );
}

```

## disassembly

```asm
0x1800256d0  mov     [rsp+arg_0], rbx
0x1800256d5  mov     [rsp+arg_8], rsi
0x1800256da  push    rdi
0x1800256db  sub     rsp, 20h
0x1800256df  mov     edx, 1
0x1800256e4  mov     rdi, rcx
0x1800256e7  call    ?GetCurrentPartialValue@SleepstudyJsonWriter@@AEAAAEAUJsonPartialValue@1@W4JsonPartialValueType@1@@Z; SleepstudyJsonWriter::GetCurrentPartialValue(SleepstudyJsonWriter::JsonPartialValueType)
0x1800256ec  add     qword ptr [rdi+120h], 0FFFFFFFFFFFFFFF8h
0x1800256f4  mov     rcx, rdi; this
0x1800256f7  call    ?WriteNewLine@SleepstudyJsonWriter@@AEAAXXZ; SleepstudyJsonWriter::WriteNewLine(void)
0x1800256fc  mov     rcx, rdi; this
0x1800256ff  lea     rbx, asc_18009D150; "}"
0x180025706  call    ?WritePadding@SleepstudyJsonWriter@@AEAAXXZ; SleepstudyJsonWriter::WritePadding(void)
0x18002570b  mov     eax, 7Dh ; '}'
0x180025710  movzx   ecx, ax; C
0x180025713  call    cs:__imp___isascii
0x180025719  test    eax, eax
0x18002571b  jz      short loc_180025729
0x18002571d  movzx   edx, word ptr [rbx]
0x180025720  lea     rcx, [rdi+10h]
0x180025724  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x180025729  add     rbx, 2
0x18002572d  movzx   eax, word ptr [rbx]
0x180025730  test    ax, ax
0x180025733  jnz     short loc_180025710
0x180025735  mov     rbx, [rsp+28h+arg_0]
0x18002573a  mov     rsi, [rsp+28h+arg_8]
0x18002573f  add     rsp, 20h
0x180025743  pop     rdi
0x180025744  retn
```
