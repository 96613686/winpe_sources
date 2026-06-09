# CsrServerDllInitialization

- ea: `0x180008160`
- end: `0x180008187`
- name: `CsrServerDllInitialization`
- size: `39`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, installer_update`

## pseudocode

```c
__int64 __fastcall CsrServerDllInitialization(__int64 a1)
{
  __int64 result; // rax

  *(_DWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = CsrServerApiDispatchTable;
  *(_QWORD *)(a1 + 48) = &CsrServerApiServerValidTable;
  result = 0;
  *(_DWORD *)(a1 + 36) = 5;
  return result;
}

```

## disassembly

```asm
0x180008160  lea     rax, CsrServerApiDispatchTable
0x180008167  mov     dword ptr [rcx+20h], 0
0x18000816e  mov     [rcx+28h], rax
0x180008172  lea     rax, CsrServerApiServerValidTable
0x180008179  mov     [rcx+30h], rax
0x18000817d  xor     eax, eax
0x18000817f  mov     dword ptr [rcx+24h], 5
0x180008186  retn
```
