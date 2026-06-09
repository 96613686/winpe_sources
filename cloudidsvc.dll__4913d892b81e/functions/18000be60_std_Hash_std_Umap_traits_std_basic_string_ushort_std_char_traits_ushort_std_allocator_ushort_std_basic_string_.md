# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::_Check_rehash_required_1(void)

- ea: `0x18000be60`
- end: `0x18000bec0`
- name: `?_Check_rehash_required_1@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA_NXZ`
- size: `96`
- prototype: `bool __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000983c`
- `0x18000da04`

## callees

- `0x18000be60`

## pseudocode

```c
bool __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Check_rehash_required_1(
        __int64 a1)
{
  __int64 v2; // rdx
  float v3; // xmm0_4
  __int64 v4; // rcx
  float v5; // xmm1_4

  v2 = *(_QWORD *)(a1 + 16) + 1LL;
  if ( v2 < 0 )
    v3 = (float)(v2 & 1 | (unsigned int)((unsigned __int64)v2 >> 1))
       + (float)(v2 & 1 | (unsigned int)((unsigned __int64)v2 >> 1));
  else
    v3 = (float)(int)v2;
  v4 = *(_QWORD *)(a1 + 56);
  if ( v4 < 0 )
    v5 = (float)(v4 & 1 | (unsigned int)((unsigned __int64)v4 >> 1))
       + (float)(v4 & 1 | (unsigned int)((unsigned __int64)v4 >> 1));
  else
    v5 = (float)(int)v4;
  return (float)(v3 / v5) > *(float *)a1;
}

```

## disassembly

```asm
0x18000be60  mov     rdx, [rcx+10h]
0x18000be64  mov     r8, rcx
0x18000be67  add     rdx, 1
0x18000be6b  xorps   xmm0, xmm0
0x18000be6e  js      short loc_18000BE77
0x18000be70  cvtsi2ss xmm0, rdx
0x18000be75  jmp     short loc_18000BE8C
0x18000be77  mov     rax, rdx
0x18000be7a  and     edx, 1
0x18000be7d  shr     rax, 1
0x18000be80  or      rax, rdx
0x18000be83  cvtsi2ss xmm0, rax
0x18000be88  addss   xmm0, xmm0
0x18000be8c  mov     rcx, [rcx+38h]
0x18000be90  xorps   xmm1, xmm1
0x18000be93  test    rcx, rcx
0x18000be96  js      short loc_18000BE9F
0x18000be98  cvtsi2ss xmm1, rcx
0x18000be9d  jmp     short loc_18000BEB4
0x18000be9f  mov     rax, rcx
0x18000bea2  and     ecx, 1
0x18000bea5  shr     rax, 1
0x18000bea8  or      rax, rcx
0x18000beab  cvtsi2ss xmm1, rax
0x18000beb0  addss   xmm1, xmm1
0x18000beb4  divss   xmm0, xmm1
0x18000beb8  comiss  xmm0, dword ptr [r8]
0x18000bebc  setnbe  al
0x18000bebf  retn
```
