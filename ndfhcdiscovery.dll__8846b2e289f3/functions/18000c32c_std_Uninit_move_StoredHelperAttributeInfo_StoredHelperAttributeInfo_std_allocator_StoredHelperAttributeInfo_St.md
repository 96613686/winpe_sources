# std::_Uninit_move<StoredHelperAttributeInfo *,StoredHelperAttributeInfo *,std::allocator<StoredHelperAttributeInfo>,StoredHelperAttributeInfo>(StoredHelperAttributeInfo *,StoredHelperAttributeInfo *,StoredHelperAttributeInfo *,std::_Wrap_alloc<std::allocator<StoredHelperAttributeInfo>> &,StoredHelperAttributeInfo *,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x18000c32c`
- end: `0x18000c3bb`
- name: `??$_Uninit_move@PEAUStoredHelperAttributeInfo@@PEAU1@V?$allocator@UStoredHelperAttributeInfo@@@std@@U1@@std@@YAPEAUStoredHelperAttributeInfo@@PEAU1@00AEAU?$_Wrap_alloc@V?$allocator@UStoredHelperAttributeInfo@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010c18`

## callees

- `0x180005460`
- `0x18000c32c`

## pseudocode

```c
_DWORD *__fastcall std::_Uninit_move<StoredHelperAttributeInfo *,StoredHelperAttributeInfo *,std::allocator<StoredHelperAttributeInfo>,StoredHelperAttributeInfo>(
        _DWORD *a1,
        _DWORD *a2,
        _DWORD *a3)
{
  _DWORD *i; // rdi

  for ( i = a1; i != a2; i += 34 )
  {
    *a3 = *i;
    std::wstring::wstring(a3 + 2, i + 2);
    std::wstring::wstring(a3 + 10, i + 10);
    std::wstring::wstring(a3 + 18, i + 18);
    std::wstring::wstring(a3 + 26, i + 26);
    a3 += 34;
  }
  return a3;
}

```

## disassembly

```asm
0x18000c32c  mov     rax, rsp
0x18000c32f  mov     [rax+8], rbx
0x18000c333  mov     [rax+10h], rsi
0x18000c337  mov     [rax+20h], r9
0x18000c33b  mov     [rax+18h], r8
0x18000c33f  push    rdi
0x18000c340  sub     rsp, 20h
0x18000c344  mov     rbx, r8
0x18000c347  mov     rsi, rdx
0x18000c34a  mov     rdi, rcx
0x18000c34d  mov     [rsp+28h+arg_18], rbx
0x18000c352  cmp     rcx, rdx
0x18000c355  jz      short loc_18000C3A7
0x18000c357  mov     eax, [rdi]
0x18000c359  mov     [rbx], eax
0x18000c35b  lea     rdx, [rdi+8]
0x18000c35f  lea     rcx, [rbx+8]
0x18000c363  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18000c368  lea     rdx, [rdi+28h]
0x18000c36c  lea     rcx, [rbx+28h]
0x18000c370  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18000c375  lea     rdx, [rdi+48h]
0x18000c379  lea     rcx, [rbx+48h]
0x18000c37d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18000c382  lea     rdx, [rdi+68h]
0x18000c386  lea     rcx, [rbx+68h]
0x18000c38a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18000c38f  add     rbx, 88h
0x18000c396  mov     [rsp+28h+arg_10], rbx
0x18000c39b  add     rdi, 88h
0x18000c3a2  cmp     rdi, rsi
0x18000c3a5  jnz     short loc_18000C357
0x18000c3a7  mov     rax, rbx
0x18000c3aa  mov     rbx, [rsp+28h+arg_0]
0x18000c3af  mov     rsi, [rsp+28h+arg_8]
0x18000c3b4  add     rsp, 20h
0x18000c3b8  pop     rdi
0x18000c3b9  retn
```
