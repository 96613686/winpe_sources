# GetStateSeparatedSiufRelativePath(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x14001785c`
- end: `0x1400178ff`
- name: `?GetStateSeparatedSiufRelativePath@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `163`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1400144a4`
- `0x140015e78`
- `0x140016230`

## callees

- `0x14000d96c`
- `0x140016f88`
- `0x140017770`
- `0x14001785c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001789e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400178cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001789e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400178cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400178ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400178dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400178ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400178dd`

## pseudocode

```c
__int64 __fastcall GetStateSeparatedSiufRelativePath(__int64 a1, void *a2)
{
  int StateSeparatedSiufMachineRegRoot; // esi
  HANDLE v4; // rax
  HANDLE ProcessHeap; // rax
  LPVOID lpMem; // [rsp+30h] [rbp+8h] BYREF

  lpMem = 0;
  std::wstring::operator=(a2, &dword_14001C5D4);
  StateSeparatedSiufMachineRegRoot = GetStateSeparatedSiufMachineRegRoot((unsigned __int16 **)&lpMem);
  if ( StateSeparatedSiufMachineRegRoot >= 0 )
  {
    std::wstring::operator=(a2, lpMem);
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMem);
    }
    std::wstring::operator+=(a2, L"\\Data");
    return 0;
  }
  else
  {
    if ( lpMem )
    {
      v4 = GetProcessHeap();
      HeapFree(v4, 0, lpMem);
    }
    return (unsigned int)StateSeparatedSiufMachineRegRoot;
  }
}

```

## disassembly

```asm
0x14001785c  mov     [rsp+arg_8], rsi
0x140017861  mov     [rsp+lpMem], rcx
0x140017866  push    rdi
0x140017867  sub     rsp, 20h
0x14001786b  mov     rdi, rdx
0x14001786e  mov     [rsp+28h+lpMem], 0
0x140017877  mov     rcx, rdi; void *
0x14001787a  lea     rdx, dword_14001C5D4; Src
0x140017881  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator=(ushort const *)
0x140017886  lea     rcx, [rsp+28h+lpMem]; unsigned __int16 **
0x14001788b  call    ?GetStateSeparatedSiufMachineRegRoot@@YAJPEAPEAG@Z; GetStateSeparatedSiufMachineRegRoot(ushort * *)
0x140017890  mov     esi, eax
0x140017892  test    eax, eax
0x140017894  jns     short loc_1400178B8
0x140017896  cmp     [rsp+28h+lpMem], 0
0x14001789c  jz      short loc_1400178B4
0x14001789e  call    cs:__imp_GetProcessHeap
0x1400178a4  mov     r8, [rsp+28h+lpMem]; lpMem
0x1400178a9  xor     edx, edx; dwFlags
0x1400178ab  mov     rcx, rax; hHeap
0x1400178ae  call    cs:__imp_HeapFree
0x1400178b4  mov     eax, esi
0x1400178b6  jmp     short loc_1400178F4
0x1400178b8  mov     rdx, [rsp+28h+lpMem]; Src
0x1400178bd  mov     rcx, rdi; void *
0x1400178c0  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator=(ushort const *)
0x1400178c5  cmp     [rsp+28h+lpMem], 0
0x1400178cb  jz      short loc_1400178E3
0x1400178cd  call    cs:__imp_GetProcessHeap
0x1400178d3  mov     r8, [rsp+28h+lpMem]; lpMem
0x1400178d8  xor     edx, edx; dwFlags
0x1400178da  mov     rcx, rax; hHeap
0x1400178dd  call    cs:__imp_HeapFree
0x1400178e3  lea     rdx, aData; "\\Data"
0x1400178ea  mov     rcx, rdi; Src
0x1400178ed  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator+=(ushort const *)
0x1400178f2  xor     eax, eax
0x1400178f4  mov     rsi, [rsp+28h+arg_8]
0x1400178f9  add     rsp, 20h
0x1400178fd  pop     rdi
0x1400178fe  retn
```
