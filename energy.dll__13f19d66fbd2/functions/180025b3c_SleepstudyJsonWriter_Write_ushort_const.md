# SleepstudyJsonWriter::Write(ushort const *)

- ea: `0x180025b3c`
- end: `0x180025c1d`
- name: `?Write@SleepstudyJsonWriter@@AEAAXPEBG@Z`
- size: `225`
- prototype: `void __fastcall(SleepstudyJsonWriter *__hidden this, const unsigned __int16 *)`
- caller_count: `21`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180025480`
- `0x1800255ac`
- `0x180025628`
- `0x18002574c`
- `0x18002581c`
- `0x180025898`
- `0x180039a14`
- `0x180041e1c`
- `0x180045e80`
- `0x1800781f8`
- `0x180078254`
- `0x1800782b0`
- `0x18007830c`
- `0x180078368`
- `0x18007840c`
- `0x1800786b4`
- `0x180078d4c`
- `0x1800791f4`
- `0x18007baa8`
- `0x18007bc64`
- `0x18007dbc0`

## callees

- `0x18001fcac`
- `0x180025b3c`
- `0x180025c30`
- `0x180025e28`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x180025b9f`
- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x180025b9f`

## pseudocode

```c
void __fastcall SleepstudyJsonWriter::Write(SleepstudyJsonWriter *this, unsigned __int16 *a2)
{
  char *v4; // rbx
  unsigned __int16 v5; // ax
  const wchar_t *v6; // rdx

  SleepstudyJsonWriter::WritePadding(this);
  v4 = (char *)this + 16;
  std::basic_ostream<unsigned short>::operator<<(v4, 34);
  while ( 1 )
  {
    v5 = *a2;
    if ( !*a2 )
      break;
    switch ( v5 )
    {
      case 8u:
        v6 = L"\\b";
        goto LABEL_15;
      case 9u:
        v6 = L"\\t";
        goto LABEL_15;
      case 0xAu:
        v6 = L"\\n";
        goto LABEL_15;
      case 0xCu:
        v6 = L"\\f";
        goto LABEL_15;
      case 0xDu:
        v6 = L"\\r";
        goto LABEL_15;
      case 0x22u:
        v6 = L"\\\"";
        goto LABEL_15;
      case 0x5Cu:
        v6 = L"\\\\";
LABEL_15:
        std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64)v4, (__int64)v6);
        goto LABEL_12;
    }
    if ( __isascii(v5) )
      std::basic_ostream<unsigned short>::operator<<(v4, *a2);
LABEL_12:
    ++a2;
  }
  std::basic_ostream<unsigned short>::operator<<(v4, 34);
}

```

## disassembly

```asm
0x180025b3c  mov     [rsp+arg_0], rbx
0x180025b41  mov     [rsp+arg_8], rsi
0x180025b46  push    rdi
0x180025b47  sub     rsp, 20h
0x180025b4b  mov     rdi, rdx
0x180025b4e  mov     rbx, rcx
0x180025b51  call    ?WritePadding@SleepstudyJsonWriter@@AEAAXXZ; SleepstudyJsonWriter::WritePadding(void)
0x180025b56  add     rbx, 10h
0x180025b5a  mov     edx, 22h ; '"'
0x180025b5f  mov     rcx, rbx
0x180025b62  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x180025b67  movzx   eax, word ptr [rdi]
0x180025b6a  test    ax, ax
0x180025b6d  jz      short loc_180025BBA
0x180025b6f  movzx   ecx, ax; C
0x180025b72  mov     edx, ecx
0x180025b74  sub     edx, 8
0x180025b77  jz      loc_180025C14
0x180025b7d  sub     edx, 1
0x180025b80  jz      loc_180025C0B
0x180025b86  sub     edx, 1
0x180025b89  jz      short loc_180025C02
0x180025b8b  sub     edx, 2
0x180025b8e  jz      short loc_180025BF9
0x180025b90  sub     edx, 1
0x180025b93  jz      short loc_180025BF0
0x180025b95  sub     edx, 15h
0x180025b98  jz      short loc_180025BE7
0x180025b9a  cmp     edx, 3Ah ; ':'
0x180025b9d  jz      short loc_180025BD6
0x180025b9f  call    cs:__imp___isascii
0x180025ba5  test    eax, eax
0x180025ba7  jz      short loc_180025BB4
0x180025ba9  movzx   edx, word ptr [rdi]
0x180025bac  mov     rcx, rbx
0x180025baf  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x180025bb4  add     rdi, 2
0x180025bb8  jmp     short loc_180025B67
0x180025bba  mov     edx, 22h ; '"'
0x180025bbf  mov     rcx, rbx
0x180025bc2  mov     rbx, [rsp+28h+arg_0]
0x180025bc7  mov     rsi, [rsp+28h+arg_8]
0x180025bcc  add     rsp, 20h
0x180025bd0  pop     rdi
0x180025bd1  jmp     ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x180025bd6  lea     rdx, asc_18009D154; "\\\\"
0x180025bdd  mov     rcx, rbx
0x180025be0  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180025be5  jmp     short loc_180025BB4
0x180025be7  lea     rdx, asc_1800A6DBC; "\\\""
0x180025bee  jmp     short loc_180025BDD
0x180025bf0  lea     rdx, aR; "\\r"
0x180025bf7  jmp     short loc_180025BDD
0x180025bf9  lea     rdx, asc_1800A6D9C; "\\f"
0x180025c00  jmp     short loc_180025BDD
0x180025c02  lea     rdx, aN; "\\n"
0x180025c09  jmp     short loc_180025BDD
0x180025c0b  lea     rdx, aT; "\\t"
0x180025c12  jmp     short loc_180025BDD
0x180025c14  lea     rdx, aB; "\\b"
0x180025c1b  jmp     short loc_180025BDD
```
