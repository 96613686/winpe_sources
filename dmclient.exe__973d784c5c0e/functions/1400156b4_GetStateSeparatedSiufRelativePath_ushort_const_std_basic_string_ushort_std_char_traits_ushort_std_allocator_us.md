# GetStateSeparatedSiufRelativePath(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1400156b4`
- end: `0x140015770`
- name: `?GetStateSeparatedSiufRelativePath@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `188`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140013ebc`
- `0x140014774`
- `0x140014a40`

## callees

- `0x14000deac`
- `0x140014cf8`
- `0x1400155a8`
- `0x1400156b4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400156f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015731`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400156f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015731`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001570c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015747`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001570c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015747`

## pseudocode

```c
__int64 __fastcall GetStateSeparatedSiufRelativePath(__int64 a1, void *a2)
{
  int StateSeparatedSiufMachineRegRoot; // esi
  HANDLE v4; // rax
  HANDLE ProcessHeap; // rax
  LPVOID lpMem; // [rsp+30h] [rbp+8h] BYREF

  lpMem = 0;
  std::wstring::operator=(a2, &dword_14001D5D4);
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
0x1400156b4  mov     [rsp+arg_8], rsi
0x1400156b9  mov     [rsp+lpMem], rcx
0x1400156be  push    rdi
0x1400156bf  sub     rsp, 20h
0x1400156c3  mov     rdi, rdx
0x1400156c6  mov     [rsp+28h+lpMem], 0
0x1400156cf  mov     rcx, rdi; void *
0x1400156d2  lea     rdx, dword_14001D5D4; Src
0x1400156d9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator=(ushort const *)
0x1400156de  lea     rcx, [rsp+28h+lpMem]; unsigned __int16 **
0x1400156e3  call    ?GetStateSeparatedSiufMachineRegRoot@@YAJPEAPEAG@Z; GetStateSeparatedSiufMachineRegRoot(ushort * *)
0x1400156e8  mov     esi, eax
0x1400156ea  test    eax, eax
0x1400156ec  jns     short loc_14001571C
0x1400156ee  cmp     [rsp+28h+lpMem], 0
0x1400156f4  jz      short loc_140015718
0x1400156f6  call    cs:__imp_GetProcessHeap
0x1400156fd  nop     dword ptr [rax+rax+00h]
0x140015702  mov     r8, [rsp+28h+lpMem]; lpMem
0x140015707  xor     edx, edx; dwFlags
0x140015709  mov     rcx, rax; hHeap
0x14001570c  call    cs:__imp_HeapFree
0x140015713  nop     dword ptr [rax+rax+00h]
0x140015718  mov     eax, esi
0x14001571a  jmp     short loc_140015764
0x14001571c  mov     rdx, [rsp+28h+lpMem]; Src
0x140015721  mov     rcx, rdi; void *
0x140015724  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator=(ushort const *)
0x140015729  cmp     [rsp+28h+lpMem], 0
0x14001572f  jz      short loc_140015753
0x140015731  call    cs:__imp_GetProcessHeap
0x140015738  nop     dword ptr [rax+rax+00h]
0x14001573d  mov     r8, [rsp+28h+lpMem]; lpMem
0x140015742  xor     edx, edx; dwFlags
0x140015744  mov     rcx, rax; hHeap
0x140015747  call    cs:__imp_HeapFree
0x14001574e  nop     dword ptr [rax+rax+00h]
0x140015753  lea     rdx, aData; "\\Data"
0x14001575a  mov     rcx, rdi; Src
0x14001575d  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator+=(ushort const *)
0x140015762  xor     eax, eax
0x140015764  mov     rsi, [rsp+28h+arg_8]
0x140015769  add     rsp, 20h
0x14001576d  pop     rdi
0x14001576e  retn
```
