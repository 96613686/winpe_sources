# JsonObject::~JsonObject(void)

- ea: `0x14001c95c`
- end: `0x14001ca07`
- name: `??1JsonObject@@UEAA@XZ`
- size: `171`
- prototype: `void __fastcall(JsonObject *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14001cce0`
- `0x140029854`
- `0x14002a154`
- `0x14002f64d`
- `0x14002f7bc`

## callees

- `0x14001c884`
- `0x14001c95c`
- `0x140030010`

## pseudocode

```c
void __fastcall JsonObject::~JsonObject(JsonObject *this)
{
  void **v2; // rdi
  _QWORD *v3; // rbx
  void (__fastcall ***v4)(_QWORD, __int64); // rcx
  __int64 **v5; // rcx
  __int64 i; // rax
  __int64 *j; // rcx

  *(_QWORD *)this = &JsonObject::`vftable';
  v2 = (void **)((char *)this + 16);
  v3 = (_QWORD *)**((_QWORD **)this + 2);
  while ( v3 != *v2 )
  {
    v4 = (void (__fastcall ***)(_QWORD, __int64))v3[8];
    if ( v4 )
      (**v4)(v4, 1);
    v5 = (__int64 **)v3[2];
    if ( *((_BYTE *)v5 + 25) )
    {
      for ( i = v3[1]; !*(_BYTE *)(i + 25) && v3 == *(_QWORD **)(i + 16); i = *(_QWORD *)(i + 8) )
        v3 = (_QWORD *)i;
      v3 = (_QWORD *)i;
    }
    else
    {
      v3 = (_QWORD *)v3[2];
      for ( j = *v5; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v3 = j;
    }
  }
  std::_Tree<std::_Tmap_traits<std::wstring,JsonValue const *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,JsonValue const *>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,JsonValue const *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,JsonValue const *>>,0>>(v2);
  *(_QWORD *)this = &JsonValue::`vftable';
}

```

## disassembly

```asm
0x14001c95c  mov     [rsp+arg_0], rbx
0x14001c961  mov     [rsp+arg_8], rsi
0x14001c966  push    rdi
0x14001c967  sub     rsp, 20h
0x14001c96b  lea     rax, ??_7JsonObject@@6B@; const JsonObject::`vftable'
0x14001c972  mov     rsi, rcx
0x14001c975  mov     [rcx], rax
0x14001c978  lea     rdi, [rcx+10h]
0x14001c97c  mov     rbx, [rdi]
0x14001c97f  mov     rbx, [rbx]
0x14001c982  cmp     rbx, [rdi]
0x14001c985  jz      short loc_14001C9E5
0x14001c987  mov     rcx, [rbx+40h]
0x14001c98b  test    rcx, rcx
0x14001c98e  jz      short loc_14001C9A0
0x14001c990  mov     rax, [rcx]
0x14001c993  mov     edx, 1
0x14001c998  mov     rax, [rax]
0x14001c99b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c9a0  mov     rcx, [rbx+10h]
0x14001c9a4  cmp     byte ptr [rcx+19h], 0
0x14001c9a8  jz      short loc_14001C9C8
0x14001c9aa  mov     rax, [rbx+8]
0x14001c9ae  jmp     short loc_14001C9BD
0x14001c9b0  cmp     rbx, [rax+10h]
0x14001c9b4  jnz     short loc_14001C9C3
0x14001c9b6  mov     rbx, rax
0x14001c9b9  mov     rax, [rax+8]
0x14001c9bd  cmp     byte ptr [rax+19h], 0
0x14001c9c1  jz      short loc_14001C9B0
0x14001c9c3  mov     rbx, rax
0x14001c9c6  jmp     short loc_14001C982
0x14001c9c8  mov     rbx, rcx
0x14001c9cb  mov     rcx, [rcx]
0x14001c9ce  cmp     byte ptr [rcx+19h], 0
0x14001c9d2  jnz     short loc_14001C982
0x14001c9d4  mov     rax, [rcx]
0x14001c9d7  mov     rbx, rcx
0x14001c9da  mov     rcx, rax
0x14001c9dd  cmp     byte ptr [rax+19h], 0
0x14001c9e1  jz      short loc_14001C9D4
0x14001c9e3  jmp     short loc_14001C982
0x14001c9e5  mov     rcx, rdi
0x14001c9e8  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,JsonValue const *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,JsonValue const *>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,JsonValue const *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,JsonValue const *>>,0>>(void)
0x14001c9ed  mov     rbx, [rsp+28h+arg_0]
0x14001c9f2  lea     rax, ??_7JsonValue@@6B@; const JsonValue::`vftable'
0x14001c9f9  mov     [rsi], rax
0x14001c9fc  mov     rsi, [rsp+28h+arg_8]
0x14001ca01  add     rsp, 20h
0x14001ca05  pop     rdi
0x14001ca06  retn
```
