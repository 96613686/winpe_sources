# CommonUtil::GetLpasvcPersistentSettingsKey(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180079c60`
- end: `0x180079d3d`
- name: `?GetLpasvcPersistentSettingsKey@CommonUtil@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `221`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007cf20`
- `0x18008fb10`

## callees

- `0x18005fa18`
- `0x1800715d0`
- `0x18007516c`
- `0x180079c60`
- `0x180080f38`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180079c99`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180079cee`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180079c99`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180079cee`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CommonUtil::GetLpasvcPersistentSettingsKey(__int64 a1, __int64 a2)
{
  signed int PersistedRegistryLocationW; // eax
  int v4; // ebx
  __int64 v6; // [rsp+30h] [rbp-20h] BYREF
  int v7; // [rsp+38h] [rbp-18h]
  char v8; // [rsp+60h] [rbp+10h] BYREF
  unsigned int v9; // [rsp+70h] [rbp+20h] BYREF

  v9 = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(L"Wlpasvc", L"Software\\Microsoft\\Wlpasvc", 0, 0, &v9);
  if ( PersistedRegistryLocationW > 0 )
    PersistedRegistryLocationW = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
  if ( PersistedRegistryLocationW == -2147024662 )
  {
    std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<PipeManager::PipeImplementation *>>,std::_Iterator_base0>>>::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<PipeManager::PipeImplementation *>>,std::_Iterator_base0>>>(&v6);
    std::vector<unsigned char>::_Resize<std::_Value_init_tag>(&v6, v9, &v8);
    v4 = GetPersistedRegistryLocationW(L"Wlpasvc", L"Software\\Microsoft\\Wlpasvc", v6, (unsigned int)(v7 - v6), &v9);
    if ( v4 >= 0 )
    {
      if ( (v9 & 1) != 0 )
        v4 = -2147418113;
      else
        std::wstring::assign(a2, v6);
    }
    std::vector<unsigned char>::_Tidy(&v6);
  }
  else
  {
    if ( PersistedRegistryLocationW >= 0 )
      return (unsigned int)-2147418113;
    return (unsigned int)PersistedRegistryLocationW;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180079c60  mov     [rsp-8+arg_8], rbx
0x180079c65  mov     [rsp-8+arg_18], rdi
0x180079c6a  push    rbp
0x180079c6b  mov     rbp, rsp
0x180079c6e  sub     rsp, 50h
0x180079c72  mov     rdi, rdx
0x180079c75  mov     [rbp+arg_10], 0
0x180079c7c  lea     rax, [rbp+arg_10]
0x180079c80  mov     [rsp+50h+var_30], rax
0x180079c85  xor     r9d, r9d
0x180079c88  xor     r8d, r8d
0x180079c8b  lea     rdx, SubKey; "Software\\Microsoft\\Wlpasvc"
0x180079c92  lea     rcx, aWlpasvc_0; "Wlpasvc"
0x180079c99  call    cs:__imp_GetPersistedRegistryLocationW
0x180079c9f  test    eax, eax
0x180079ca1  jle     short loc_180079CAB
0x180079ca3  movzx   eax, ax
0x180079ca6  or      eax, 80070000h
0x180079cab  cmp     eax, 800700EAh
0x180079cb0  jnz     short loc_180079D1F
0x180079cb2  lea     rcx, [rbp+var_20]
0x180079cb6  call    ??$?0AEBV?$allocator@U?$_List_node@PEAVPipeImplementation@PipeManager@@PEAX@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVPipeImplementation@PipeManager@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$_List_node@PEAVPipeImplementation@PipeManager@@PEAX@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<PipeManager::PipeImplementation *>>,std::_Iterator_base0>>>::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<PipeManager::PipeImplementation *>>,std::_Iterator_base0>>>(std::allocator<std::_List_node<PipeManager::PipeImplementation *,void *>> const &)
0x180079cbb  nop
0x180079cbc  mov     edx, [rbp+arg_10]
0x180079cbf  lea     r8, [rbp+arg_0]
0x180079cc3  lea     rcx, [rbp+var_20]
0x180079cc7  call    ??$_Resize@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180079ccc  mov     r8, [rbp+var_20]
0x180079cd0  mov     r9d, [rbp+var_18]
0x180079cd4  sub     r9d, r8d
0x180079cd7  lea     rax, [rbp+arg_10]
0x180079cdb  mov     [rsp+50h+var_30], rax
0x180079ce0  lea     rdx, SubKey; "Software\\Microsoft\\Wlpasvc"
0x180079ce7  lea     rcx, aWlpasvc_0; "Wlpasvc"
0x180079cee  call    cs:__imp_GetPersistedRegistryLocationW
0x180079cf4  mov     ebx, eax
0x180079cf6  test    eax, eax
0x180079cf8  js      short loc_180079D14
0x180079cfa  test    byte ptr [rbp+arg_10], 1
0x180079cfe  jz      short loc_180079D07
0x180079d00  mov     ebx, 8000FFFFh
0x180079d05  jmp     short loc_180079D14
0x180079d07  mov     rdx, [rbp+var_20]
0x180079d0b  mov     rcx, rdi
0x180079d0e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180079d13  nop
0x180079d14  lea     rcx, [rbp+var_20]
0x180079d18  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180079d1d  jmp     short loc_180079D2B
0x180079d1f  mov     ebx, 8000FFFFh
0x180079d24  test    eax, eax
0x180079d26  cmovns  eax, ebx
0x180079d29  mov     ebx, eax
0x180079d2b  mov     eax, ebx
0x180079d2d  mov     rbx, [rsp+50h+arg_8]
0x180079d32  mov     rdi, [rsp+50h+arg_18]
0x180079d37  add     rsp, 50h
0x180079d3b  pop     rbp
0x180079d3c  retn
```
