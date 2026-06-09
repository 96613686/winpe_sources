# _dynamic_initializer_for__c_SuccessfulReplacementResult__

- ea: `0x1400025b0`
- end: `0x1400025dd`
- name: `_dynamic_initializer_for__c_SuccessfulReplacementResult__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140003218`
- `0x14000dd20`

## string_xrefs

- `0x1400025ba`: `<Status><CmdID>2</CmdID><MsgRef>1</MsgRef><CmdRef>1</CmdRef><Cmd>Replace</Cmd><Data>200</Data></Status>`

## pseudocode

```c
int dynamic_initializer_for__c_SuccessfulReplacementResult__()
{
  std::wstring::_Construct<1,unsigned short const *>(
    qword_140075C68,
    L"<Status><CmdID>2</CmdID><MsgRef>1</MsgRef><CmdRef>1</CmdRef><Cmd>Replace</Cmd><Data>200</Data></Status>",
    0x67u);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__c_SuccessfulReplacementResult__);
}

```

## disassembly

```asm
0x1400025b0  sub     rsp, 28h
0x1400025b4  mov     r8d, 67h ; 'g'
0x1400025ba  lea     rdx, aStatusCmdid2Cm; "<Status><CmdID>2</CmdID><MsgRef>1</MsgR"...
0x1400025c1  lea     rcx, qword_140075C68
0x1400025c8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400025cd  lea     rcx, _dynamic_atexit_destructor_for__c_SuccessfulReplacementResult__
0x1400025d4  add     rsp, 28h
0x1400025d8  jmp     atexit
```
