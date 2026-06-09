# SleepstudyJsonWriter::StartArray(ushort const *)

- ea: `0x180025898`
- end: `0x180025984`
- name: `?StartArray@SleepstudyJsonWriter@@QEAAXPEBG@Z`
- size: `236`
- prototype: `void __fastcall(SleepstudyJsonWriter *__hidden this, const unsigned __int16 *)`
- caller_count: `9`
- callee_count: `6`
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

## callees

- `0x18001f6f4`
- `0x180025898`
- `0x180025a34`
- `0x180025b3c`
- `0x180025c30`
- `0x180025e28`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x1800258dd`
- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x18002594e`
- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x1800258dd`
- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x18002594e`

## pseudocode

```c
void __fastcall SleepstudyJsonWriter::StartArray(SleepstudyJsonWriter *this, unsigned __int16 *a2)
{
  char *v3; // rbx
  BOOL v5; // edx
  const wchar_t *v6; // rsi
  unsigned __int16 v7; // ax
  _BYTE *v8; // rdx
  const unsigned __int16 *v9; // rsi
  unsigned __int16 v10; // ax
  __int64 v11; // [rsp+50h] [rbp+8h] BYREF

  v3 = (char *)this + 280;
  v5 = a2 != 0;
  if ( *((_QWORD *)this + 35) != *((_QWORD *)this + 36) || a2 )
  {
    SleepstudyJsonWriter::InsertElement(this, v5);
    if ( a2 )
    {
      SleepstudyJsonWriter::Write(this, a2);
      v9 = L":";
      SleepstudyJsonWriter::WritePadding(this);
      v10 = 58;
      do
      {
        if ( __isascii(v10) )
          std::basic_ostream<unsigned short>::operator<<((char *)this + 16, *v9);
        v10 = *++v9;
      }
      while ( *v9 );
    }
  }
  v6 = L"[";
  SleepstudyJsonWriter::WritePadding(this);
  v7 = 91;
  do
  {
    if ( __isascii(v7) )
      std::basic_ostream<unsigned short>::operator<<((char *)this + 16, *v6);
    v7 = *++v6;
  }
  while ( *v6 );
  v8 = (_BYTE *)*((_QWORD *)v3 + 1);
  v11 = 0;
  if ( v8 == *((_BYTE **)v3 + 2) )
  {
    std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
      (void **)v3,
      v8,
      &v11);
  }
  else
  {
    *(_QWORD *)v8 = 0;
    *((_QWORD *)v3 + 1) += 8LL;
  }
}

```

## disassembly

```asm
0x180025898  push    rbx
0x18002589a  push    rbp
0x18002589b  push    rsi
0x18002589c  push    rdi
0x18002589d  sub     rsp, 28h
0x1800258a1  mov     rsi, rdx
0x1800258a4  lea     rbx, [rcx+118h]
0x1800258ab  mov     rax, [rbx+8]
0x1800258af  xor     ebp, ebp
0x1800258b1  test    rsi, rsi
0x1800258b4  mov     edx, ebp
0x1800258b6  mov     rdi, rcx
0x1800258b9  setnz   dl
0x1800258bc  cmp     [rbx], rax
0x1800258bf  jnz     short loc_180025922
0x1800258c1  test    rsi, rsi
0x1800258c4  jnz     short loc_180025922
0x1800258c6  mov     rcx, rdi; this
0x1800258c9  lea     rsi, asc_18009D144; "["
0x1800258d0  call    ?WritePadding@SleepstudyJsonWriter@@AEAAXXZ; SleepstudyJsonWriter::WritePadding(void)
0x1800258d5  mov     eax, 5Bh ; '['
0x1800258da  movzx   ecx, ax; C
0x1800258dd  call    cs:__imp___isascii
0x1800258e3  test    eax, eax
0x1800258e5  jz      short loc_1800258F3
0x1800258e7  movzx   edx, word ptr [rsi]
0x1800258ea  lea     rcx, [rdi+10h]
0x1800258ee  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x1800258f3  add     rsi, 2
0x1800258f7  movzx   eax, word ptr [rsi]
0x1800258fa  test    ax, ax
0x1800258fd  jnz     short loc_1800258DA
0x1800258ff  mov     rdx, [rbx+8]
0x180025903  mov     [rsp+48h+arg_0], rbp
0x180025908  cmp     rdx, [rbx+10h]
0x18002590c  jz      short loc_180025975
0x18002590e  mov     rax, rbp
0x180025911  mov     [rdx], rax
0x180025914  add     qword ptr [rbx+8], 8
0x180025919  add     rsp, 28h
0x18002591d  pop     rdi
0x18002591e  pop     rsi
0x18002591f  pop     rbp
0x180025920  pop     rbx
0x180025921  retn
0x180025922  call    ?InsertElement@SleepstudyJsonWriter@@AEAAXW4JsonPartialValueType@1@@Z; SleepstudyJsonWriter::InsertElement(SleepstudyJsonWriter::JsonPartialValueType)
0x180025927  test    rsi, rsi
0x18002592a  jz      short loc_1800258C6
0x18002592c  mov     rdx, rsi; unsigned __int16 *
0x18002592f  mov     rcx, rdi; this
0x180025932  call    ?Write@SleepstudyJsonWriter@@AEAAXPEBG@Z; SleepstudyJsonWriter::Write(ushort const *)
0x180025937  mov     rcx, rdi; this
0x18002593a  lea     rsi, asc_18009D148; ":"
0x180025941  call    ?WritePadding@SleepstudyJsonWriter@@AEAAXXZ; SleepstudyJsonWriter::WritePadding(void)
0x180025946  mov     eax, 3Ah ; ':'
0x18002594b  movzx   ecx, ax; C
0x18002594e  call    cs:__imp___isascii
0x180025954  test    eax, eax
0x180025956  jz      short loc_180025964
0x180025958  movzx   edx, word ptr [rsi]
0x18002595b  lea     rcx, [rdi+10h]
0x18002595f  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x180025964  add     rsi, 2
0x180025968  movzx   eax, word ptr [rsi]
0x18002596b  test    ax, ax
0x18002596e  jnz     short loc_18002594B
0x180025970  jmp     loc_1800258C6
0x180025975  lea     r8, [rsp+48h+arg_0]
0x18002597a  mov     rcx, rbx
0x18002597d  call    ??$_Emplace_reallocate@AEBQEAUScenarioInstanceScaffold@@@?$vector@PEAUScenarioInstanceScaffold@@V?$allocator@PEAUScenarioInstanceScaffold@@@std@@@std@@AEAAPEAPEAUScenarioInstanceScaffold@@QEAPEAU2@AEBQEAU2@@Z; std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(ScenarioInstanceScaffold * * const,ScenarioInstanceScaffold * const &)
0x180025982  jmp     short loc_180025919
```
