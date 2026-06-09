# std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Find_lower_bound<ushort const *>(ushort const * const &)

- ea: `0x180010714`
- end: `0x180010797`
- name: `??$_Find_lower_bound@PEBG@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@@1@AEBQEBG@Z`
- size: `131`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010d9c`
- `0x18001896c`

## callees

- `0x180010714`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180010756`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180010756`

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
0x180010714  mov     [rsp+arg_0], rbx
0x180010719  mov     [rsp+arg_8], rsi
0x18001071e  push    rdi
0x18001071f  sub     rsp, 20h
0x180010723  mov     rax, [rcx]
0x180010726  mov     rsi, r8
0x180010729  mov     rdi, rdx
0x18001072c  mov     r9, [rax+8]
0x180010730  mov     [rdx], r9
0x180010733  mov     rbx, r9
0x180010736  mov     qword ptr [rdx+8], 0
0x18001073e  mov     rax, [rcx]
0x180010741  mov     [rdx+10h], rax
0x180010745  cmp     byte ptr [r9+19h], 0
0x18001074a  jnz     short loc_180010783
0x18001074c  mov     [rdi], rbx
0x18001074f  mov     rdx, [rsi]
0x180010752  mov     rcx, [rbx+20h]
0x180010756  call    cs:__imp__o__wcsicmp
0x18001075d  nop     dword ptr [rax+rax+00h]
0x180010762  test    eax, eax
0x180010764  jns     short loc_18001076E
0x180010766  add     rbx, 10h
0x18001076a  xor     eax, eax
0x18001076c  jmp     short loc_180010777
0x18001076e  mov     [rdi+10h], rbx
0x180010772  mov     eax, 1
0x180010777  mov     [rdi+8], eax
0x18001077a  mov     rbx, [rbx]
0x18001077d  cmp     byte ptr [rbx+19h], 0
0x180010781  jz      short loc_18001074C
0x180010783  mov     rbx, [rsp+28h+arg_0]
0x180010788  mov     rax, rdi
0x18001078b  mov     rsi, [rsp+28h+arg_8]
0x180010790  add     rsp, 20h
0x180010794  pop     rdi
0x180010795  retn
```
