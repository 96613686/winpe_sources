# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,ulong>>,0>>::_Check_rehash_required_1(void)

- ea: `0x18000fd1c`
- end: `0x18000fd7c`
- name: `?_Check_rehash_required_1@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEBA_NXZ`
- size: `96`
- prototype: `bool __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a460`
- `0x18000a9b8`
- `0x18000aab8`

## callees

- `0x18000fd1c`

## pseudocode

```c
bool __fastcall std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Check_rehash_required_1(
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
0x18000fd1c  mov     rdx, [rcx+10h]
0x18000fd20  mov     r8, rcx
0x18000fd23  add     rdx, 1
0x18000fd27  xorps   xmm0, xmm0
0x18000fd2a  js      short loc_18000FD33
0x18000fd2c  cvtsi2ss xmm0, rdx
0x18000fd31  jmp     short loc_18000FD48
0x18000fd33  mov     rax, rdx
0x18000fd36  and     edx, 1
0x18000fd39  shr     rax, 1
0x18000fd3c  or      rax, rdx
0x18000fd3f  cvtsi2ss xmm0, rax
0x18000fd44  addss   xmm0, xmm0
0x18000fd48  mov     rcx, [rcx+38h]
0x18000fd4c  xorps   xmm1, xmm1
0x18000fd4f  test    rcx, rcx
0x18000fd52  js      short loc_18000FD5B
0x18000fd54  cvtsi2ss xmm1, rcx
0x18000fd59  jmp     short loc_18000FD70
0x18000fd5b  mov     rax, rcx
0x18000fd5e  and     ecx, 1
0x18000fd61  shr     rax, 1
0x18000fd64  or      rax, rcx
0x18000fd67  cvtsi2ss xmm1, rax
0x18000fd6c  addss   xmm1, xmm1
0x18000fd70  divss   xmm0, xmm1
0x18000fd74  comiss  xmm0, dword ptr [r8]
0x18000fd78  setnbe  al
0x18000fd7b  retn
```
