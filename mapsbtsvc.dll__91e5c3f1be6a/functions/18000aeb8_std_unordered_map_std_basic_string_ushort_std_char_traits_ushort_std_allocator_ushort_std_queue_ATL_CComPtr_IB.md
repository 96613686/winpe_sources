# std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::queue<ATL::CComPtr<IBackgroundCopyFile>,std::deque<ATL::CComPtr<IBackgroundCopyFile>,std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::queue<ATL::CComPtr<IBackgroundCopyFile>,std::deque<ATL::CComPtr<IBackgroundCopyFile>,std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>>>>>::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::queue<ATL::CComPtr<IBackgroundCopyFile>,std::deque<ATL::CComPtr<IBackgroundCopyFile>,std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::queue<ATL::CComPtr<IBackgroundCopyFile>,std::deque<ATL::CComPtr<IBackgroundCopyFile>,std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>>>>>(void)

- ea: `0x18000aeb8`
- end: `0x18000aee0`
- name: `??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@@std@@@2@@std@@QEAA@XZ`
- size: `40`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000aee8`
- `0x18000f49c`

## callees

- `0x18000acd8`

## pseudocode

```c
__int64 __fastcall std::unordered_map<std::wstring,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>::unordered_map<std::wstring,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>(
        __int64 a1)
{
  int v3; // [rsp+30h] [rbp+8h] BYREF
  int v4; // [rsp+34h] [rbp+Ch]

  v4 = HIDWORD(a1);
  v3 = 0;
  __0___Hash_V___Umap_traits_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__queue_V__CComPtr_UIBackgroundCopyFile___ATL__V__deque_V__CComPtr_UIBackgroundCopyFile___ATL__V__allocator_V__CComPtr_UIBackgroundCopyFile___ATL___std___std___2_V___Uhash_compare_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2__2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__queue_V__CComPtr_UIBackgroundCopyFile___ATL__V__deque_V__CComPtr_UIBackgroundCopyFile___ATL__V__allocator_V__CComPtr_UIBackgroundCopyFile___ATL___std___std___2__std___2__0A__std___std__IEAA_AEBV___Uhash_compare_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2__1_AEBV__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__queue_V__CComPtr_UIBackgroundCopyFile___ATL__V__deque_V__CComPtr_UIBackgroundCopyFile___ATL__V__allocator_V__CComPtr_UIBackgroundCopyFile___ATL___std___std___2__std___1__Z(
    a1,
    &v3);
  return a1;
}

```

## disassembly

```asm
0x18000aeb8  mov     [rsp+arg_0], rcx
0x18000aebd  push    rbx
0x18000aebe  sub     rsp, 20h
0x18000aec2  lea     rdx, [rsp+28h+arg_0]
0x18000aec7  mov     dword ptr [rsp+28h+arg_0], 0
0x18000aecf  mov     rbx, rcx
0x18000aed2  call    ??0?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAA@AEBV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@1@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@@std@@@1@@Z
0x18000aed7  mov     rax, rbx
0x18000aeda  add     rsp, 20h
0x18000aede  pop     rbx
0x18000aedf  retn
```
