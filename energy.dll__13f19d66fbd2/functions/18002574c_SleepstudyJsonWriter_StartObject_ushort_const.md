# SleepstudyJsonWriter::StartObject(ushort const *)

- ea: `0x18002574c`
- end: `0x180025816`
- name: `?StartObject@SleepstudyJsonWriter@@QEAAXPEBG@Z`
- size: `202`
- prototype: `void __fastcall(SleepstudyJsonWriter *__hidden this, const unsigned __int16 *)`
- caller_count: `11`
- callee_count: `7`
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

## callees

- `0x18001f6f4`
- `0x18002574c`
- `0x180025a34`
- `0x180025ae4`
- `0x180025b3c`
- `0x180025c30`
- `0x180025e28`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x180025796`
- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x180025796`

## pseudocode

```c
void __fastcall SleepstudyJsonWriter::StartObject(SleepstudyJsonWriter *this, unsigned __int16 *a2)
{
  char *v3; // rbx
  BOOL v5; // edx
  const wchar_t *v6; // rsi
  unsigned __int16 v7; // ax
  _BYTE *v8; // rdx
  __int64 v9; // [rsp+50h] [rbp+8h] BYREF

  v3 = (char *)this + 280;
  v5 = a2 != 0;
  if ( *((_QWORD *)this + 35) != *((_QWORD *)this + 36) || a2 )
  {
    SleepstudyJsonWriter::InsertElement(this, v5);
    if ( a2 )
    {
      SleepstudyJsonWriter::Write(this, a2);
      SleepstudyJsonWriter::WriteRawString(this, L":");
    }
  }
  v6 = L"{";
  SleepstudyJsonWriter::WritePadding(this);
  v7 = 123;
  do
  {
    if ( __isascii(v7) )
      std::basic_ostream<unsigned short>::operator<<((char *)this + 16, *v6);
    v7 = *++v6;
  }
  while ( *v6 );
  v8 = (_BYTE *)*((_QWORD *)v3 + 1);
  v9 = 1;
  if ( v8 == *((_BYTE **)v3 + 2) )
  {
    std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
      (void **)v3,
      v8,
      &v9);
  }
  else
  {
    *(_QWORD *)v8 = v9;
    *((_QWORD *)v3 + 1) += 8LL;
  }
}

```

## disassembly

```asm
0x18002574c  push    rbx
0x18002574e  push    rbp
0x18002574f  push    rsi
0x180025750  push    rdi
0x180025751  sub     rsp, 28h
0x180025755  mov     rsi, rdx
0x180025758  lea     rbx, [rcx+118h]
0x18002575f  mov     rax, [rbx+8]
0x180025763  xor     ebp, ebp
0x180025765  test    rsi, rsi
0x180025768  mov     edx, ebp
0x18002576a  mov     rdi, rcx
0x18002576d  setnz   dl
0x180025770  cmp     [rbx], rax
0x180025773  jz      short loc_1800257E1
0x180025775  call    ?InsertElement@SleepstudyJsonWriter@@AEAAXW4JsonPartialValueType@1@@Z; SleepstudyJsonWriter::InsertElement(SleepstudyJsonWriter::JsonPartialValueType)
0x18002577a  test    rsi, rsi
0x18002577d  jnz     short loc_1800257E8
0x18002577f  mov     rcx, rdi; this
0x180025782  lea     rsi, asc_18009D14C; "{"
0x180025789  call    ?WritePadding@SleepstudyJsonWriter@@AEAAXXZ; SleepstudyJsonWriter::WritePadding(void)
0x18002578e  mov     eax, 7Bh ; '{'
0x180025793  movzx   ecx, ax; C
0x180025796  call    cs:__imp___isascii
0x18002579c  test    eax, eax
0x18002579e  jz      short loc_1800257AC
0x1800257a0  movzx   edx, word ptr [rsi]
0x1800257a3  lea     rcx, [rdi+10h]
0x1800257a7  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x1800257ac  add     rsi, 2
0x1800257b0  movzx   eax, word ptr [rsi]
0x1800257b3  test    ax, ax
0x1800257b6  jnz     short loc_180025793
0x1800257b8  mov     rdx, [rbx+8]
0x1800257bc  mov     [rsp+48h+arg_0], 1
0x1800257c5  cmp     rdx, [rbx+10h]
0x1800257c9  jz      short loc_180025807
0x1800257cb  mov     rax, [rsp+48h+arg_0]
0x1800257d0  mov     [rdx], rax
0x1800257d3  add     qword ptr [rbx+8], 8
0x1800257d8  add     rsp, 28h
0x1800257dc  pop     rdi
0x1800257dd  pop     rsi
0x1800257de  pop     rbp
0x1800257df  pop     rbx
0x1800257e0  retn
0x1800257e1  test    rsi, rsi
0x1800257e4  jz      short loc_18002577F
0x1800257e6  jmp     short loc_180025775
0x1800257e8  mov     rdx, rsi; unsigned __int16 *
0x1800257eb  mov     rcx, rdi; this
0x1800257ee  call    ?Write@SleepstudyJsonWriter@@AEAAXPEBG@Z; SleepstudyJsonWriter::Write(ushort const *)
0x1800257f3  lea     rdx, asc_18009D148; ":"
0x1800257fa  mov     rcx, rdi; this
0x1800257fd  call    ?WriteRawString@SleepstudyJsonWriter@@AEAAXPEBG@Z; SleepstudyJsonWriter::WriteRawString(ushort const *)
0x180025802  jmp     loc_18002577F
0x180025807  lea     r8, [rsp+48h+arg_0]
0x18002580c  mov     rcx, rbx
0x18002580f  call    ??$_Emplace_reallocate@AEBQEAUScenarioInstanceScaffold@@@?$vector@PEAUScenarioInstanceScaffold@@V?$allocator@PEAUScenarioInstanceScaffold@@@std@@@std@@AEAAPEAPEAUScenarioInstanceScaffold@@QEAPEAU2@AEBQEAU2@@Z; std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(ScenarioInstanceScaffold * * const,ScenarioInstanceScaffold * const &)
0x180025814  jmp     short loc_1800257D8
```
