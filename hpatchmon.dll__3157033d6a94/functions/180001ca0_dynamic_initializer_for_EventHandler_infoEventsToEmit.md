# _dynamic_initializer_for__EventHandler::infoEventsToEmit__

- ea: `0x180001ca0`
- end: `0x180001e75`
- name: `_dynamic_initializer_for__EventHandler::infoEventsToEmit__`
- size: `469`
- prototype: `int()`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001ca0`
- `0x180002270`
- `0x180002620`
- `0x180002cdc`
- `0x180002d20`
- `0x18000d984`
- `0x180011d60`
- `0x1800130f4`

## string_xrefs

- `0x180001d2f`: `ImageHotPatchThreadOperationStatus`
- `0x180001d40`: `ImageHotPatchSectionCreateOperationStatus`

## pseudocode

```c
int dynamic_initializer_for__EventHandler::infoEventsToEmit__()
{
  _QWORD *v0; // rax
  __int64 v1; // rcx
  __int64 *v2; // rbx
  _BYTE v4[16]; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v5[4]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v6[4]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v7[4]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v8[4]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v9[4]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v10[4]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v11[4]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v12[4]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v13[4]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v14[4]; // [rsp+150h] [rbp+50h] BYREF
  _QWORD v15[4]; // [rsp+170h] [rbp+70h] BYREF
  _QWORD v16[4]; // [rsp+190h] [rbp+90h] BYREF
  __int64 v17; // [rsp+1B0h] [rbp+B0h] BYREF

  std::wstring::wstring(v5, L"ActiveUserPatchRundown");
  std::wstring::wstring(v6, L"ActiveSecureUserPatchRundown");
  std::wstring::wstring(v7, L"ActiveKernelPatchRundown");
  std::wstring::wstring(v8, L"ActiveSecureKernelPatchRundown");
  std::wstring::wstring(v9, L"ImageHotPatchOperation");
  std::wstring::wstring(v10, L"ImageHotPatchOperationStatus");
  std::wstring::wstring(v11, L"ImageHotPatchThreadOperationStatus");
  std::wstring::wstring(v12, L"ImageHotPatchSectionCreateOperationStatus");
  std::wstring::wstring(v13, L"KernelHotPatchOperationStatus");
  std::wstring::wstring(v14, L"SecureKernelHotPatchOperationStatus");
  std::wstring::wstring(v15, L"SessionHotPatchLoadStatus");
  std::wstring::wstring(v16, L"ImageHotPatchOperationReverseOnly");
  EventHandler::infoEventsToEmit = 0;
  qword_180022EC8 = 0;
  qword_180022ED0 = 0;
  v0 = operator new(0x30u);
  *v0 = v0;
  v0[1] = v0;
  qword_180022EC8 = (__int64)v0;
  qword_180022ED8 = 0;
  xmmword_180022EE0 = 0;
  qword_180022EF0 = 7;
  qword_180022EF8 = 8;
  EventHandler::infoEventsToEmit = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(
    (__int64)&qword_180022ED8,
    0x10u,
    (unsigned __int64)v0);
  v2 = v5;
  do
  {
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
      v1,
      (__int64)v4,
      v2);
    v2 += 4;
  }
  while ( v2 != &v17 );
  `eh vector destructor iterator'(v5, 0x20u, 0xCu, (void (*)(void *))std::wstring::~wstring);
  return atexit(dynamic_atexit_destructor_for__EventHandler::infoEventsToEmit__);
}

```

## disassembly

```asm
0x180001ca0  mov     [rsp-8+arg_0], rbx
0x180001ca5  push    rbp
0x180001ca6  lea     rbp, [rsp-0C0h]
0x180001cae  sub     rsp, 1C0h
0x180001cb5  mov     rax, cs:__security_cookie
0x180001cbc  xor     rax, rsp
0x180001cbf  mov     [rbp+0C0h+var_10], rax
0x180001cc6  lea     rdx, aActiveuserpatc; "ActiveUserPatchRundown"
0x180001ccd  lea     rcx, [rsp+1C0h+var_190]
0x180001cd2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180001cd7  nop
0x180001cd8  lea     rdx, aActivesecureus; "ActiveSecureUserPatchRundown"
0x180001cdf  lea     rcx, [rsp+1C0h+var_170]
0x180001ce4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180001ce9  nop
0x180001cea  lea     rdx, aActivekernelpa; "ActiveKernelPatchRundown"
0x180001cf1  lea     rcx, [rsp+1C0h+var_150]
0x180001cf6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180001cfb  nop
0x180001cfc  lea     rdx, aActivesecureke; "ActiveSecureKernelPatchRundown"
0x180001d03  lea     rcx, [rbp+0C0h+var_130]
0x180001d07  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180001d0c  nop
0x180001d0d  lea     rdx, aImagehotpatcho; "ImageHotPatchOperation"
0x180001d14  lea     rcx, [rbp+0C0h+var_110]
0x180001d18  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180001d1d  nop
0x180001d1e  lea     rdx, aImagehotpatcho_1; "ImageHotPatchOperationStatus"
0x180001d25  lea     rcx, [rbp+0C0h+var_F0]
0x180001d29  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180001d2e  nop
0x180001d2f  lea     rdx, aImagehotpatcht; "ImageHotPatchThreadOperationStatus"
0x180001d36  lea     rcx, [rbp+0C0h+var_D0]
0x180001d3a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180001d3f  nop
0x180001d40  lea     rdx, aImagehotpatchs; "ImageHotPatchSectionCreateOperationStat"...
0x180001d47  lea     rcx, [rbp+0C0h+var_B0]
0x180001d4b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180001d50  nop
0x180001d51  lea     rdx, aKernelhotpatch; "KernelHotPatchOperationStatus"
0x180001d58  lea     rcx, [rbp+0C0h+var_90]
0x180001d5c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180001d61  nop
0x180001d62  lea     rdx, aSecurekernelho; "SecureKernelHotPatchOperationStatus"
0x180001d69  lea     rcx, [rbp+0C0h+var_70]
0x180001d6d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180001d72  nop
0x180001d73  lea     rdx, aSessionhotpatc; "SessionHotPatchLoadStatus"
0x180001d7a  lea     rcx, [rbp+0C0h+var_50]
0x180001d7e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180001d83  nop
0x180001d84  lea     rdx, aImagehotpatcho_0; "ImageHotPatchOperationReverseOnly"
0x180001d8b  lea     rcx, [rbp+0C0h+var_30]
0x180001d92  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180001d97  nop
0x180001d98  mov     cs:?infoEventsToEmit@EventHandler@@0V?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@A, 0; std::unordered_set<std::wstring> EventHandler::infoEventsToEmit
0x180001da2  xor     ebx, ebx
0x180001da4  mov     cs:qword_180022EC8, rbx
0x180001dab  mov     cs:qword_180022ED0, rbx
0x180001db2  lea     ecx, [rbx+30h]; Size
0x180001db5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001dba  mov     [rax], rax
0x180001dbd  mov     [rax+8], rax
0x180001dc1  mov     cs:qword_180022EC8, rax
0x180001dc8  mov     cs:qword_180022ED8, rbx
0x180001dcf  xorps   xmm0, xmm0
0x180001dd2  movdqa  cs:xmmword_180022EE0, xmm0
0x180001dda  mov     cs:qword_180022EF0, 7
0x180001de5  mov     cs:qword_180022EF8, 8
0x180001df0  mov     cs:?infoEventsToEmit@EventHandler@@0V?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@A, 3F800000h; std::unordered_set<std::wstring> EventHandler::infoEventsToEmit
0x180001dfa  mov     r8, rax
0x180001dfd  lea     edx, [rbx+10h]
0x180001e00  lea     rcx, qword_180022ED8
0x180001e07  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x180001e0c  nop
0x180001e0d  lea     rbx, [rsp+1C0h+var_190]
0x180001e12  mov     r8, rbx
0x180001e15  lea     rdx, [rsp+1C0h+var_1A0]
0x180001e1a  call    ??$emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(std::wstring const &)
0x180001e1f  add     rbx, 20h ; ' '
0x180001e23  lea     rax, [rbp+0C0h+var_10]
0x180001e2a  cmp     rbx, rax
0x180001e2d  jnz     short loc_180001E12
0x180001e2f  lea     r9, ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; void (*)(void *)
0x180001e36  mov     edx, 20h ; ' '; unsigned __int64
0x180001e3b  lea     r8d, [rdx-14h]; unsigned __int64
0x180001e3f  lea     rcx, [rsp+1C0h+var_190]; void *
0x180001e44  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180001e49  lea     rcx, _dynamic_atexit_destructor_for__EventHandler__infoEventsToEmit__; void (__cdecl *)()
0x180001e50  call    atexit
0x180001e55  mov     rcx, [rbp+0C0h+var_10]
0x180001e5c  xor     rcx, rsp; StackCookie
0x180001e5f  call    __security_check_cookie
0x180001e64  mov     rbx, [rsp+1C0h+arg_0]
0x180001e6c  add     rsp, 1C0h
0x180001e73  pop     rbp
0x180001e74  retn
```
