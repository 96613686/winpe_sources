# SleepstudyJsonWriter::InsertElement(SleepstudyJsonWriter::JsonPartialValueType)

- ea: `0x180025a34`
- end: `0x180025adb`
- name: `?InsertElement@SleepstudyJsonWriter@@AEAAXW4JsonPartialValueType@1@@Z`
- size: `167`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `17`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800255ac`
- `0x18002574c`
- `0x18002581c`
- `0x180025898`
- `0x180039a14`
- `0x180041e1c`
- `0x1800781f8`
- `0x180078254`
- `0x1800782b0`
- `0x18007830c`
- `0x180078368`
- `0x18007840c`
- `0x1800786b4`
- `0x180078d4c`
- `0x1800791f4`
- `0x18007bc64`
- `0x18007dbc0`

## callees

- `0x180025a34`
- `0x180025c30`
- `0x180025e28`
- `0x180025ea8`
- `0x18004a420`
- `0x1800907f0`

## import_xrefs

- `msvcp_win!?flush@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@XZ` at `0x180025ab2`
- `msvcp_win!?flush@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@XZ` at `0x180025ab2`
- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x180025a71`
- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x180025a71`

## string_xrefs

- `0x180025ab8`: `Attempted invalid operation in JSON stream.`

## pseudocode

```c
void __fastcall SleepstudyJsonWriter::InsertElement(SleepstudyJsonWriter *a1, int a2)
{
  __int64 v2; // rax
  __int64 v4; // rdi
  const wchar_t *v5; // rsi
  unsigned __int16 v6; // ax
  _BYTE pExceptionObject[72]; // [rsp+20h] [rbp-48h] BYREF

  v2 = *((_QWORD *)a1 + 36);
  if ( *((_QWORD *)a1 + 35) == v2 || (v4 = *((_QWORD *)a1 + 36), *(_DWORD *)(v2 - 8) != a2) )
  {
    std::basic_ostream<unsigned short>::flush((char *)a1 + 16);
    std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Attempted invalid operation in JSON stream.");
    throw (std::logic_error *)pExceptionObject;
  }
  if ( *(_DWORD *)(v2 - 4) )
  {
    v5 = L",";
    SleepstudyJsonWriter::WritePadding(a1);
    v6 = 44;
    do
    {
      if ( __isascii(v6) )
        std::basic_ostream<unsigned short>::operator<<((char *)a1 + 16, *v5);
      v6 = *++v5;
    }
    while ( *v5 );
  }
  ++*(_DWORD *)(v4 - 4);
  SleepstudyJsonWriter::WriteNewLine(a1);
  SleepstudyJsonWriter::WritePadding(a1);
}

```

## disassembly

```asm
0x180025a34  push    rbx
0x180025a36  push    rbp
0x180025a37  push    rsi
0x180025a38  push    rdi
0x180025a39  sub     rsp, 48h
0x180025a3d  mov     rax, [rcx+120h]
0x180025a44  mov     rbx, rcx
0x180025a47  cmp     [rcx+118h], rax
0x180025a4e  jz      short loc_180025AAE
0x180025a50  mov     rdi, rax
0x180025a53  cmp     [rax-8], edx
0x180025a56  jnz     short loc_180025AAE
0x180025a58  xor     ebp, ebp
0x180025a5a  cmp     [rax-4], ebp
0x180025a5d  jbe     short loc_180025A93
0x180025a5f  lea     rsi, asc_18009D140; ","
0x180025a66  call    ?WritePadding@SleepstudyJsonWriter@@AEAAXXZ; SleepstudyJsonWriter::WritePadding(void)
0x180025a6b  lea     eax, [rbp+2Ch]
0x180025a6e  movzx   ecx, ax; C
0x180025a71  call    cs:__imp___isascii
0x180025a77  test    eax, eax
0x180025a79  jz      short loc_180025A87
0x180025a7b  movzx   edx, word ptr [rsi]
0x180025a7e  lea     rcx, [rbx+10h]
0x180025a82  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x180025a87  add     rsi, 2
0x180025a8b  movzx   eax, word ptr [rsi]
0x180025a8e  test    ax, ax
0x180025a91  jnz     short loc_180025A6E
0x180025a93  inc     dword ptr [rdi-4]
0x180025a96  mov     rcx, rbx; this
0x180025a99  call    ?WriteNewLine@SleepstudyJsonWriter@@AEAAXXZ; SleepstudyJsonWriter::WriteNewLine(void)
0x180025a9e  mov     rcx, rbx; this
0x180025aa1  add     rsp, 48h
0x180025aa5  pop     rdi
0x180025aa6  pop     rsi
0x180025aa7  pop     rbp
0x180025aa8  pop     rbx
0x180025aa9  jmp     ?WritePadding@SleepstudyJsonWriter@@AEAAXXZ; SleepstudyJsonWriter::WritePadding(void)
0x180025aae  add     rcx, 10h
0x180025ab2  call    cs:__imp_?flush@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@XZ; std::basic_ostream<ushort>::flush(void)
0x180025ab8  lea     rdx, aAttemptedInval; "Attempted invalid operation in JSON str"...
0x180025abf  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180025ac4  call    ??0logic_error@std@@QEAA@PEBD@Z; std::logic_error::logic_error(char const *)
0x180025ac9  lea     rdx, _TI2?AVlogic_error@std@@; pThrowInfo
0x180025ad0  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180025ad5  call    _CxxThrowException_0
```
