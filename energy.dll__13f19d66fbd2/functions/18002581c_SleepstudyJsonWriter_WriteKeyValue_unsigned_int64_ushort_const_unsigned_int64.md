# SleepstudyJsonWriter::WriteKeyValue<unsigned __int64>(ushort const *,unsigned __int64 &&)

- ea: `0x18002581c`
- end: `0x18002588f`
- name: `??$WriteKeyValue@_K@SleepstudyJsonWriter@@QEAAXPEBG$$QEA_K@Z`
- size: `115`
- prototype: `void __fastcall(SleepstudyJsonWriter *this, unsigned __int16 *, unsigned __int64 *)`
- caller_count: `10`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18007840c`
- `0x18007850c`
- `0x180078a18`
- `0x1800791f4`
- `0x18007a130`
- `0x18007a218`
- `0x18007a318`
- `0x18007bc64`
- `0x18007d598`
- `0x18007dc1c`

## callees

- `0x18002581c`
- `0x18002598c`
- `0x180025a34`
- `0x180025b3c`
- `0x180025c30`
- `0x180025e28`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x18002585a`
- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x18002585a`

## pseudocode

```c
void __fastcall SleepstudyJsonWriter::WriteKeyValue<unsigned __int64>(
        SleepstudyJsonWriter *this,
        unsigned __int16 *a2,
        unsigned __int64 *a3)
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
  SleepstudyJsonWriter::Write(this, *a3);
}

```

## disassembly

```asm
0x18002581c  push    rbx
0x18002581e  push    rbp
0x18002581f  push    rsi
0x180025820  push    rdi
0x180025821  sub     rsp, 28h
0x180025825  mov     rbx, rdx
0x180025828  mov     rsi, r8
0x18002582b  mov     edx, 1
0x180025830  mov     rdi, rcx
0x180025833  call    ?InsertElement@SleepstudyJsonWriter@@AEAAXW4JsonPartialValueType@1@@Z; SleepstudyJsonWriter::InsertElement(SleepstudyJsonWriter::JsonPartialValueType)
0x180025838  mov     rdx, rbx; unsigned __int16 *
0x18002583b  mov     rcx, rdi; this
0x18002583e  call    ?Write@SleepstudyJsonWriter@@AEAAXPEBG@Z; SleepstudyJsonWriter::Write(ushort const *)
0x180025843  mov     rcx, rdi; this
0x180025846  lea     rbx, asc_18009D148; ":"
0x18002584d  call    ?WritePadding@SleepstudyJsonWriter@@AEAAXXZ; SleepstudyJsonWriter::WritePadding(void)
0x180025852  mov     eax, 3Ah ; ':'
0x180025857  movzx   ecx, ax; C
0x18002585a  call    cs:__imp___isascii
0x180025860  test    eax, eax
0x180025862  jz      short loc_180025870
0x180025864  movzx   edx, word ptr [rbx]
0x180025867  lea     rcx, [rdi+10h]
0x18002586b  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x180025870  add     rbx, 2
0x180025874  movzx   eax, word ptr [rbx]
0x180025877  test    ax, ax
0x18002587a  jnz     short loc_180025857
0x18002587c  mov     rdx, [rsi]; unsigned __int64
0x18002587f  mov     rcx, rdi; this
0x180025882  add     rsp, 28h
0x180025886  pop     rdi
0x180025887  pop     rsi
0x180025888  pop     rbp
0x180025889  pop     rbx
0x18002588a  jmp     ?Write@SleepstudyJsonWriter@@AEAAX_K@Z; SleepstudyJsonWriter::Write(unsigned __int64)
```
