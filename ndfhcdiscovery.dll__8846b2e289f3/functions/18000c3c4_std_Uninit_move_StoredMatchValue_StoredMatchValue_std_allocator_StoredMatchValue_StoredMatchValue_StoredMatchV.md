# std::_Uninit_move<StoredMatchValue *,StoredMatchValue *,std::allocator<StoredMatchValue>,StoredMatchValue>(StoredMatchValue *,StoredMatchValue *,StoredMatchValue *,std::_Wrap_alloc<std::allocator<StoredMatchValue>> &,StoredMatchValue *,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x18000c3c4`
- end: `0x18000c488`
- name: `??$_Uninit_move@PEAUStoredMatchValue@@PEAU1@V?$allocator@UStoredMatchValue@@@std@@U1@@std@@YAPEAUStoredMatchValue@@PEAU1@00AEAU?$_Wrap_alloc@V?$allocator@UStoredMatchValue@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010d18`

## callees

- `0x180005460`
- `0x18000c3c4`

## pseudocode

```c
__int64 __fastcall std::_Uninit_move<StoredMatchValue *,StoredMatchValue *,std::allocator<StoredMatchValue>,StoredMatchValue>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v5; // rdi
  _QWORD *v6; // rsi

  v5 = a1;
  if ( a1 != a2 )
  {
    v6 = (_QWORD *)(a1 + 40);
    do
    {
      std::wstring::wstring(a3, v5);
      *(_DWORD *)(a3 + 32) = *(_DWORD *)(v5 + 32);
      *(_QWORD *)(a3 + 40) = 0;
      *(_QWORD *)(a3 + 48) = 0;
      *(_QWORD *)(a3 + 56) = 0;
      *(_QWORD *)(a3 + 40) = *v6;
      *(_QWORD *)(a3 + 48) = v6[1];
      *(_QWORD *)(a3 + 56) = v6[2];
      *v6 = 0;
      v6[1] = 0;
      v6[2] = 0;
      std::wstring::wstring(a3 + 64, v5 + 64);
      *(_DWORD *)(a3 + 96) = *(_DWORD *)(v5 + 96);
      a3 += 104;
      v5 += 104;
      v6 += 13;
    }
    while ( v5 != a2 );
  }
  return a3;
}

```

## disassembly

```asm
0x18000c3c4  mov     [rsp+arg_0], rbx
0x18000c3c9  mov     [rsp+arg_18], r9
0x18000c3ce  mov     [rsp+arg_10], r8
0x18000c3d3  push    rsi
0x18000c3d4  push    rdi
0x18000c3d5  push    r14
0x18000c3d7  sub     rsp, 20h
0x18000c3db  mov     rbx, r8
0x18000c3de  mov     r14, rdx
0x18000c3e1  mov     rdi, rcx
0x18000c3e4  mov     [rsp+38h+arg_18], rbx
0x18000c3e9  cmp     rcx, rdx
0x18000c3ec  jz      loc_18000C476
0x18000c3f2  lea     rsi, [rcx+28h]
0x18000c3f6  mov     rdx, rdi
0x18000c3f9  mov     rcx, rbx
0x18000c3fc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18000c401  mov     eax, [rdi+20h]
0x18000c404  mov     [rbx+20h], eax
0x18000c407  mov     qword ptr [rbx+28h], 0
0x18000c40f  mov     qword ptr [rbx+30h], 0
0x18000c417  mov     qword ptr [rbx+38h], 0
0x18000c41f  mov     rax, [rsi]
0x18000c422  mov     [rbx+28h], rax
0x18000c426  mov     rax, [rsi+8]
0x18000c42a  mov     [rbx+30h], rax
0x18000c42e  mov     rax, [rsi+10h]
0x18000c432  mov     [rbx+38h], rax
0x18000c436  mov     qword ptr [rsi], 0
0x18000c43d  mov     qword ptr [rsi+8], 0
0x18000c445  mov     qword ptr [rsi+10h], 0
0x18000c44d  lea     rdx, [rdi+40h]
0x18000c451  lea     rcx, [rbx+40h]
0x18000c455  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18000c45a  mov     eax, [rdi+60h]
0x18000c45d  mov     [rbx+60h], eax
0x18000c460  add     rbx, 68h ; 'h'
0x18000c464  mov     [rsp+38h+arg_10], rbx
0x18000c469  add     rdi, 68h ; 'h'
0x18000c46d  lea     rsi, [rsi+68h]
0x18000c471  cmp     rdi, r14
0x18000c474  jnz     short loc_18000C3F6
0x18000c476  mov     rax, rbx
0x18000c479  mov     rbx, [rsp+38h+arg_0]
0x18000c47e  add     rsp, 20h
0x18000c482  pop     r14
0x18000c484  pop     rdi
0x18000c485  pop     rsi
0x18000c486  retn
```
