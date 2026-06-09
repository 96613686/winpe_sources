# DupStringWithCoTaskMemAlloc(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ushort * *)

- ea: `0x1800217ec`
- end: `0x180021865`
- name: `?DupStringWithCoTaskMemAlloc@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAG@Z`
- size: `121`
- prototype: `HRESULT __fastcall(const std::wstring *In, wchar_t **Out)`
- caller_count: `6`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180032c2c`
- `0x180032cb8`
- `0x180032e58`
- `0x1800330fc`
- `0x1800359a0`
- `0x180035cf4`

## callees

- `0x180008bd0`
- `0x180011844`
- `0x1800217ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002180d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002180d`

## pseudocode

```c
__int64 __fastcall DupStringWithCoTaskMemAlloc(const std::wstring *In, _GUID **Out)
{
  _GUID *v4; // rdi
  __int64 result; // rax
  const wchar_t *v6; // rax
  _GUID *v7; // r9

  v4 = (_GUID *)CoTaskMemAlloc(2 * In->_Mypair._Myval2._Mysize + 2);
  if ( !v4 )
    return 2147942414LL;
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&In->_Mypair._Myval2);
  v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&In->_Mypair._Myval2);
  std::_Copy_memmove<_GUID *,_GUID *>(v7, (_GUID *)&v6[In->_Mypair._Myval2._Mysize], v4, (unsigned __int64)v7);
  result = 0;
  *((_WORD *)&v4->Data1 + In->_Mypair._Myval2._Mysize) = 0;
  *Out = v4;
  return result;
}

```

## disassembly

```asm
0x1800217ec  mov     [rsp+arg_10], rbx
0x1800217f1  mov     [rsp+arg_18], rsi
0x1800217f6  push    rdi
0x1800217f7  sub     rsp, 20h
0x1800217fb  mov     rbx, In
0x1800217fe  mov     rsi, Out
0x180021801  mov     In, [In+10h]
0x180021805  lea     In, ds:2[In*2]; cb
0x18002180d  call    cs:__imp_CoTaskMemAlloc
0x180021813  mov     rdi, rax
0x180021816  test    rax, rax
0x180021819  jnz     short loc_180021822
0x18002181b  mov     eax, 8007000Eh
0x180021820  jmp     short loc_180021855
0x180021822  mov     In, rbx; this
0x180021825  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002182a  mov     In, rbx; this
0x18002182d  mov     r9, rax
0x180021830  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180021835  mov     In, [rbx+10h]
0x180021839  mov     r8, rdi; _Dest
0x18002183c  lea     Out, [rax+In*2]; _Last
0x180021840  mov     In, r9; _First
0x180021843  call    ??$_Copy_memmove@PEAU_GUID@@PEAU1@@std@@YAPEAU_GUID@@PEAU1@00@Z; std::_Copy_memmove<_GUID *,_GUID *>(_GUID *,_GUID *,_GUID *)
0x180021848  mov     In, [rbx+10h]
0x18002184c  xor     eax, eax
0x18002184e  mov     [rdi+In*2], ax
0x180021852  mov     [rsi], rdi
0x180021855  mov     rbx, [rsp+28h+arg_10]
0x18002185a  mov     rsi, [rsp+28h+arg_18]
0x18002185f  add     rsp, 20h
0x180021863  pop     rdi
0x180021864  retn
```
