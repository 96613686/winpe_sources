# SleepstudyJsonWriter::EndArray(void)

- ea: `0x180042f00`
- end: `0x180042f72`
- name: `?EndArray@SleepstudyJsonWriter@@QEAAXXZ`
- size: `114`
- prototype: `void __fastcall(SleepstudyJsonWriter *__hidden this)`
- caller_count: `10`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180039a14`
- `0x1800488b4`
- `0x18004a360`
- `0x18007bc64`
- `0x18007cfc0`
- `0x18007d104`
- `0x18007d598`
- `0x18007dc1c`
- `0x18007e004`
- `0x18007e440`

## callees

- `0x180025c30`
- `0x180025e28`
- `0x180025ea8`
- `0x180025f74`
- `0x180042f00`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x180042f40`
- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x180042f40`

## pseudocode

```c
void __fastcall SleepstudyJsonWriter::EndArray(SleepstudyJsonWriter *this)
{
  const wchar_t *v2; // rbx
  unsigned __int16 v3; // ax

  SleepstudyJsonWriter::GetCurrentPartialValue((__int64)this, 0);
  *((_QWORD *)this + 36) -= 8LL;
  SleepstudyJsonWriter::WriteNewLine(this);
  v2 = L"]";
  SleepstudyJsonWriter::WritePadding(this);
  v3 = 93;
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
0x180042f00  mov     [rsp+arg_0], rbx
0x180042f05  mov     [rsp+arg_8], rsi
0x180042f0a  push    rdi
0x180042f0b  sub     rsp, 20h
0x180042f0f  xor     edx, edx
0x180042f11  mov     rdi, rcx
0x180042f14  call    ?GetCurrentPartialValue@SleepstudyJsonWriter@@AEAAAEAUJsonPartialValue@1@W4JsonPartialValueType@1@@Z; SleepstudyJsonWriter::GetCurrentPartialValue(SleepstudyJsonWriter::JsonPartialValueType)
0x180042f19  add     qword ptr [rdi+120h], 0FFFFFFFFFFFFFFF8h
0x180042f21  mov     rcx, rdi; this
0x180042f24  call    ?WriteNewLine@SleepstudyJsonWriter@@AEAAXXZ; SleepstudyJsonWriter::WriteNewLine(void)
0x180042f29  mov     rcx, rdi; this
0x180042f2c  lea     rbx, asc_18009F2BC; "]"
0x180042f33  call    ?WritePadding@SleepstudyJsonWriter@@AEAAXXZ; SleepstudyJsonWriter::WritePadding(void)
0x180042f38  mov     eax, 5Dh ; ']'
0x180042f3d  movzx   ecx, ax; C
0x180042f40  call    cs:__imp___isascii
0x180042f46  test    eax, eax
0x180042f48  jz      short loc_180042F56
0x180042f4a  movzx   edx, word ptr [rbx]
0x180042f4d  lea     rcx, [rdi+10h]
0x180042f51  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x180042f56  add     rbx, 2
0x180042f5a  movzx   eax, word ptr [rbx]
0x180042f5d  test    ax, ax
0x180042f60  jnz     short loc_180042F3D
0x180042f62  mov     rbx, [rsp+28h+arg_0]
0x180042f67  mov     rsi, [rsp+28h+arg_8]
0x180042f6c  add     rsp, 20h
0x180042f70  pop     rdi
0x180042f71  retn
```
