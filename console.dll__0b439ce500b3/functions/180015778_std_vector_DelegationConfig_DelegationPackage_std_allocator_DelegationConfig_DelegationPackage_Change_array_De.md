# std::vector<DelegationConfig::DelegationPackage,std::allocator<DelegationConfig::DelegationPackage>>::_Change_array(DelegationConfig::DelegationPackage * const,unsigned __int64,unsigned __int64)

- ea: `0x180015778`
- end: `0x180015811`
- name: `?_Change_array@?$vector@UDelegationPackage@DelegationConfig@@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@AEAAXQEAUDelegationPackage@DelegationConfig@@_K1@Z`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180014c20`

## callees

- `0x180008c34`
- `0x180008c74`
- `0x180015778`

## pseudocode

```c
__int64 __fastcall std::vector<DelegationConfig::DelegationPackage>::_Change_array(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 result; // rax

  if ( g_availablePackages )
  {
    std::_Destroy_range<std::allocator<DelegationConfig::DelegationPackage>>(g_availablePackages, xmmword_180023990);
    std::_Deallocate<16>(g_availablePackages, 16 * ((*((_QWORD *)&xmmword_180023990 + 1) - g_availablePackages) >> 4));
  }
  g_availablePackages = a2;
  *(_QWORD *)&xmmword_180023990 = a2 + 176 * a3;
  result = a2 + 176 * a4;
  *((_QWORD *)&xmmword_180023990 + 1) = result;
  return result;
}

```

## disassembly

```asm
0x180015778  mov     [rsp+arg_0], rbx
0x18001577d  mov     [rsp+arg_8], rsi
0x180015782  push    rdi
0x180015783  sub     rsp, 20h
0x180015787  mov     rcx, cs:?g_availablePackages@@3V?$vector@UDelegationPackage@DelegationConfig@@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@A; std::vector<DelegationConfig::DelegationPackage> g_availablePackages
0x18001578e  mov     rdi, r9
0x180015791  mov     rsi, r8
0x180015794  mov     rbx, rdx
0x180015797  test    rcx, rcx
0x18001579a  jz      short loc_1800157D7
0x18001579c  mov     rdx, qword ptr cs:xmmword_180023990
0x1800157a3  call    ??$_Destroy_range@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@YAXPEAUDelegationPackage@DelegationConfig@@QEAU12@AEAV?$allocator@UDelegationPackage@DelegationConfig@@@0@@Z; std::_Destroy_range<std::allocator<DelegationConfig::DelegationPackage>>(DelegationConfig::DelegationPackage *,DelegationConfig::DelegationPackage * const,std::allocator<DelegationConfig::DelegationPackage> &)
0x1800157a8  mov     rcx, cs:?g_availablePackages@@3V?$vector@UDelegationPackage@DelegationConfig@@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@A; std::vector<DelegationConfig::DelegationPackage> g_availablePackages
0x1800157af  mov     rdx, 2E8BA2E8BA2E8BA3h
0x1800157b9  mov     rax, qword ptr cs:xmmword_180023990+8
0x1800157c0  sub     rax, rcx
0x1800157c3  sar     rax, 4
0x1800157c7  imul    rax, rdx
0x1800157cb  imul    rdx, rax, 0B0h
0x1800157d2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800157d7  imul    rax, rsi, 0B0h
0x1800157de  mov     rsi, [rsp+28h+arg_8]
0x1800157e3  add     rax, rbx
0x1800157e6  mov     cs:?g_availablePackages@@3V?$vector@UDelegationPackage@DelegationConfig@@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@A, rbx; std::vector<DelegationConfig::DelegationPackage> g_availablePackages
0x1800157ed  mov     qword ptr cs:xmmword_180023990, rax
0x1800157f4  imul    rax, rdi, 0B0h
0x1800157fb  add     rax, rbx
0x1800157fe  mov     rbx, [rsp+28h+arg_0]
0x180015803  mov     qword ptr cs:xmmword_180023990+8, rax
0x18001580a  add     rsp, 20h
0x18001580e  pop     rdi
0x18001580f  retn
```
