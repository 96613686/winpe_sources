# std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Find_lower_bound<ushort const *>(ushort const * const &)

- ea: `0x18000ff88`
- end: `0x180010004`
- name: `??$_Find_lower_bound@PEBG@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@@1@AEBQEBG@Z`
- size: `124`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010610`
- `0x180017f24`

## callees

- `0x18000ff88`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000ffca`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000ffca`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Find_lower_bound<unsigned short const *>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  __int64 *v5; // r9
  __int64 *v6; // rbx
  int v7; // eax

  v5 = *(__int64 **)(*(_QWORD *)a1 + 8LL);
  *a2 = v5;
  v6 = v5;
  a2[1] = 0;
  for ( a2[2] = *(_QWORD *)a1; !*((_BYTE *)v6 + 25); v6 = (__int64 *)*v6 )
  {
    *a2 = v6;
    if ( (int)_o__wcsicmp(v6[4], *a3) >= 0 )
    {
      a2[2] = v6;
      v7 = 1;
    }
    else
    {
      v6 += 2;
      v7 = 0;
    }
    *((_DWORD *)a2 + 2) = v7;
  }
  return a2;
}

```

## disassembly

```asm
0x18000ff88  mov     [rsp+arg_0], rbx
0x18000ff8d  mov     [rsp+arg_8], rsi
0x18000ff92  push    rdi
0x18000ff93  sub     rsp, 20h
0x18000ff97  mov     rax, [rcx]
0x18000ff9a  mov     rsi, r8
0x18000ff9d  mov     rdi, rdx
0x18000ffa0  mov     r9, [rax+8]
0x18000ffa4  mov     [rdx], r9
0x18000ffa7  mov     rbx, r9
0x18000ffaa  mov     qword ptr [rdx+8], 0
0x18000ffb2  mov     rax, [rcx]
0x18000ffb5  mov     [rdx+10h], rax
0x18000ffb9  cmp     byte ptr [r9+19h], 0
0x18000ffbe  jnz     short loc_18000FFF1
0x18000ffc0  mov     [rdi], rbx
0x18000ffc3  mov     rdx, [rsi]
0x18000ffc6  mov     rcx, [rbx+20h]
0x18000ffca  call    cs:__imp__o__wcsicmp
0x18000ffd0  test    eax, eax
0x18000ffd2  jns     short loc_18000FFDC
0x18000ffd4  add     rbx, 10h
0x18000ffd8  xor     eax, eax
0x18000ffda  jmp     short loc_18000FFE5
0x18000ffdc  mov     [rdi+10h], rbx
0x18000ffe0  mov     eax, 1
0x18000ffe5  mov     [rdi+8], eax
0x18000ffe8  mov     rbx, [rbx]
0x18000ffeb  cmp     byte ptr [rbx+19h], 0
0x18000ffef  jz      short loc_18000FFC0
0x18000fff1  mov     rbx, [rsp+28h+arg_0]
0x18000fff6  mov     rax, rdi
0x18000fff9  mov     rsi, [rsp+28h+arg_8]
0x18000fffe  add     rsp, 20h
0x180010002  pop     rdi
0x180010003  retn
```
