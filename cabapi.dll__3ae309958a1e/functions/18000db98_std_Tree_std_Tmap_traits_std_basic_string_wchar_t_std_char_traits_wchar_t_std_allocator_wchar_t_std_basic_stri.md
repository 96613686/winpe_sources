# std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>>,0>>::_Find_lower_bound<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18000db98`
- end: `0x18000dc29`
- name: `??$_Find_lower_bound@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@UWStringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z`
- size: `145`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000dc30`
- `0x18000dd60`
- `0x18000e458`
- `0x18000e604`
- `0x18000e68c`

## callees

- `0x180001f76`
- `0x18000db98`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 *v5; // r9
  __int64 *v6; // rbx
  const wchar_t *v7; // rcx
  const wchar_t *v8; // rdx
  int v9; // eax

  v5 = *(__int64 **)(*(_QWORD *)a1 + 8LL);
  *a2 = v5;
  v6 = v5;
  a2[1] = 0;
  for ( a2[2] = *(_QWORD *)a1; !*((_BYTE *)v6 + 25); v6 = (__int64 *)*v6 )
  {
    *a2 = v6;
    v7 = (const wchar_t *)(v6 + 4);
    if ( *(_QWORD *)(a3 + 24) <= 7u )
      v8 = (const wchar_t *)a3;
    else
      v8 = *(const wchar_t **)a3;
    if ( (unsigned __int64)v6[7] > 7 )
      v7 = *(const wchar_t **)v7;
    if ( wcsicmp(v7, v8) >= 0 )
    {
      a2[2] = v6;
      v9 = 1;
    }
    else
    {
      v6 += 2;
      v9 = 0;
    }
    *((_DWORD *)a2 + 2) = v9;
  }
  return a2;
}

```

## disassembly

```asm
0x18000db98  mov     [rsp+arg_0], rbx
0x18000db9d  mov     [rsp+arg_8], rsi
0x18000dba2  push    rdi
0x18000dba3  sub     rsp, 20h
0x18000dba7  mov     rax, [rcx]
0x18000dbaa  mov     rsi, r8
0x18000dbad  mov     rdi, rdx
0x18000dbb0  mov     r9, [rax+8]
0x18000dbb4  mov     [rdx], r9
0x18000dbb7  mov     rbx, r9
0x18000dbba  mov     qword ptr [rdx+8], 0
0x18000dbc2  mov     rax, [rcx]
0x18000dbc5  mov     [rdx+10h], rax
0x18000dbc9  cmp     byte ptr [r9+19h], 0
0x18000dbce  jnz     short loc_18000DC16
0x18000dbd0  mov     [rdi], rbx
0x18000dbd3  lea     rcx, [rbx+20h]
0x18000dbd7  cmp     qword ptr [rsi+18h], 7
0x18000dbdc  jbe     short loc_18000DBE3
0x18000dbde  mov     rdx, [rsi]
0x18000dbe1  jmp     short loc_18000DBE6
0x18000dbe3  mov     rdx, rsi; String2
0x18000dbe6  cmp     qword ptr [rcx+18h], 7
0x18000dbeb  jbe     short loc_18000DBF0
0x18000dbed  mov     rcx, [rcx]; String1
0x18000dbf0  call    _wcsicmp
0x18000dbf5  test    eax, eax
0x18000dbf7  jns     short loc_18000DC01
0x18000dbf9  add     rbx, 10h
0x18000dbfd  xor     eax, eax
0x18000dbff  jmp     short loc_18000DC0A
0x18000dc01  mov     [rdi+10h], rbx
0x18000dc05  mov     eax, 1
0x18000dc0a  mov     [rdi+8], eax
0x18000dc0d  mov     rbx, [rbx]
0x18000dc10  cmp     byte ptr [rbx+19h], 0
0x18000dc14  jz      short loc_18000DBD0
0x18000dc16  mov     rbx, [rsp+28h+arg_0]
0x18000dc1b  mov     rax, rdi
0x18000dc1e  mov     rsi, [rsp+28h+arg_8]
0x18000dc23  add     rsp, 20h
0x18000dc27  pop     rdi
0x18000dc28  retn
```
