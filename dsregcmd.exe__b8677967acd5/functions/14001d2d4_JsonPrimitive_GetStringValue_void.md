# JsonPrimitive::GetStringValue(void)

- ea: `0x14001d2d4`
- end: `0x14001d366`
- name: `?GetStringValue@JsonPrimitive@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `146`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14000baf8`
- `0x14001cf60`

## callees

- `0x140003044`
- `0x14001c2d0`
- `0x14001c644`
- `0x14001c78c`
- `0x14001d2d4`
- `0x14002c3e8`

## pseudocode

```c
_QWORD *__fastcall JsonPrimitive::GetStringValue(__int64 a1, _QWORD *a2)
{
  wchar_t *v3; // rdx
  _BYTE pExceptionObject[32]; // [rsp+28h] [rbp-20h] BYREF

  if ( *(_DWORD *)(a1 + 8) == 3 )
  {
    std::wstring::wstring(a2, a1 + 32);
  }
  else if ( *(_DWORD *)(a1 + 8) == 4 )
  {
    StringUtility::ToString<__int64>(a2, a1 + 24);
  }
  else
  {
    if ( *(_DWORD *)(a1 + 8) == 5 )
    {
      v3 = L"true";
      if ( !*(_BYTE *)(a1 + 16) )
        v3 = (wchar_t *)L"false";
    }
    else
    {
      if ( *(_DWORD *)(a1 + 8) != 6 )
      {
        JsonException::JsonException((JsonException *)pExceptionObject, -895090685);
        throw (JsonException *)pExceptionObject;
      }
      v3 = (wchar_t *)L"null";
    }
    std::wstring::wstring(a2, v3);
  }
  return a2;
}

```

## disassembly

```asm
0x14001d2d4  push    rbx
0x14001d2d6  sub     rsp, 40h
0x14001d2da  mov     r8d, [rcx+8]
0x14001d2de  mov     rbx, rdx
0x14001d2e1  sub     r8d, 3
0x14001d2e5  jz      short loc_14001D330
0x14001d2e7  sub     r8d, 1
0x14001d2eb  jz      short loc_14001D322
0x14001d2ed  sub     r8d, 1
0x14001d2f1  jz      short loc_14001D30A
0x14001d2f3  cmp     r8d, 1
0x14001d2f7  jnz     short loc_14001D345
0x14001d2f9  lea     rdx, aNull; "null"
0x14001d300  mov     rcx, rbx
0x14001d303  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14001d308  jmp     short loc_14001D33C
0x14001d30a  cmp     byte ptr [rcx+10h], 0
0x14001d30e  lea     rax, aFalse; "false"
0x14001d315  lea     rdx, aTrue; "true"
0x14001d31c  cmovz   rdx, rax
0x14001d320  jmp     short loc_14001D300
0x14001d322  lea     rdx, [rcx+18h]
0x14001d326  mov     rcx, rbx
0x14001d329  call    ??$ToString@_J@StringUtility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEB_J@Z; StringUtility::ToString<__int64>(__int64 const &)
0x14001d32e  jmp     short loc_14001D33C
0x14001d330  lea     rdx, [rcx+20h]
0x14001d334  mov     rcx, rbx
0x14001d337  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14001d33c  mov     rax, rbx
0x14001d33f  add     rsp, 40h
0x14001d343  pop     rbx
0x14001d344  retn
0x14001d345  mov     edx, 0CAA60003h; int
0x14001d34a  lea     rcx, [rsp+48h+pExceptionObject]; this
0x14001d34f  call    ??0JsonException@@QEAA@J@Z; JsonException::JsonException(long)
0x14001d354  lea     rdx, _TI2?AVJsonException@@; pThrowInfo
0x14001d35b  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x14001d360  call    _CxxThrowException_0
```
