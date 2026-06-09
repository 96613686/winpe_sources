# GetStateSeparatedDiagTrackRegistryPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1400174d0`
- end: `0x1400175e2`
- name: `?GetStateSeparatedDiagTrackRegistryPath@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `274`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000f65c`

## callees

- `0x140016f88`
- `0x1400174d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001751e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140017598`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001751e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140017598`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140017550`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140017550`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001753f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400175bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001753f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400175bc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400175ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400175ca`

## string_xrefs

- `0x1400174f0`: `RedirectedRegistryRoot`
- `0x140017575`: `RedirectedRegistryRoot`

## pseudocode

```c
__int64 __fastcall GetStateSeparatedDiagTrackRegistryPath(void *a1)
{
  LSTATUS ValueW; // eax
  signed int v3; // ebx
  unsigned int v4; // ebx
  HANDLE ProcessHeap; // rax
  void *pvData; // rdi
  LSTATUS v7; // eax
  HANDLE v8; // rax
  SIZE_T dwBytes; // [rsp+58h] [rbp+10h] BYREF

  LODWORD(dwBytes) = 0;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Diagnostics\\DiagTrack",
             L"RedirectedRegistryRoot",
             6u,
             0,
             0,
             (LPDWORD)&dwBytes);
  v3 = ValueW;
  if ( ValueW > 0 )
    v3 = (unsigned __int16)ValueW | 0x80070000;
  if ( !v3 )
  {
    v4 = dwBytes;
    ProcessHeap = GetProcessHeap();
    pvData = HeapAlloc(ProcessHeap, 8u, v4);
    if ( pvData )
    {
      v7 = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Diagnostics\\DiagTrack",
             L"RedirectedRegistryRoot",
             6u,
             0,
             pvData,
             (LPDWORD)&dwBytes);
      v3 = v7;
      if ( v7 > 0 )
        v3 = (unsigned __int16)v7 | 0x80070000;
      if ( v3 >= 0 )
        std::wstring::operator=(a1, pvData);
      v8 = GetProcessHeap();
      HeapFree(v8, 0, pvData);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400174d0  mov     r11, rsp
0x1400174d3  mov     [r11+8], rbx
0x1400174d7  mov     [r11+18h], rsi
0x1400174db  push    rdi
0x1400174dc  sub     rsp, 40h
0x1400174e0  lea     rax, [r11+10h]
0x1400174e4  mov     dword ptr [rsp+48h+dwBytes], 0
0x1400174ec  mov     [r11-18h], rax
0x1400174f0  lea     r8, aRedirectedregi; "RedirectedRegistryRoot"
0x1400174f7  mov     rsi, rcx
0x1400174fa  mov     qword ptr [r11-20h], 0
0x140017502  mov     r9d, 6; dwFlags
0x140017508  mov     qword ptr [r11-28h], 0
0x140017510  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140017517  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14001751e  call    cs:__imp_RegGetValueW
0x140017524  mov     ebx, eax
0x140017526  test    eax, eax
0x140017528  jle     short loc_140017533
0x14001752a  movzx   ebx, ax
0x14001752d  or      ebx, 80070000h
0x140017533  test    ebx, ebx
0x140017535  jnz     loc_1400175D0
0x14001753b  mov     ebx, dword ptr [rsp+48h+dwBytes]
0x14001753f  call    cs:__imp_GetProcessHeap
0x140017545  mov     r8d, ebx; dwBytes
0x140017548  mov     edx, 8; dwFlags
0x14001754d  mov     rcx, rax; hHeap
0x140017550  call    cs:__imp_HeapAlloc
0x140017556  mov     rdi, rax
0x140017559  test    rax, rax
0x14001755c  jnz     short loc_140017565
0x14001755e  mov     ebx, 8007000Eh
0x140017563  jmp     short loc_1400175D0
0x140017565  lea     rax, [rsp+48h+dwBytes]
0x14001756a  mov     r9d, 6; dwFlags
0x140017570  mov     [rsp+48h+pcbData], rax; pcbData
0x140017575  lea     r8, aRedirectedregi; "RedirectedRegistryRoot"
0x14001757c  mov     [rsp+48h+pvData], rdi; pvData
0x140017581  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140017588  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14001758f  mov     [rsp+48h+pdwType], 0; pdwType
0x140017598  call    cs:__imp_RegGetValueW
0x14001759e  mov     ebx, eax
0x1400175a0  test    eax, eax
0x1400175a2  jle     short loc_1400175AD
0x1400175a4  movzx   ebx, ax
0x1400175a7  or      ebx, 80070000h
0x1400175ad  test    ebx, ebx
0x1400175af  js      short loc_1400175BC
0x1400175b1  mov     rdx, rdi; Src
0x1400175b4  mov     rcx, rsi; void *
0x1400175b7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator=(ushort const *)
0x1400175bc  call    cs:__imp_GetProcessHeap
0x1400175c2  mov     r8, rdi; lpMem
0x1400175c5  xor     edx, edx; dwFlags
0x1400175c7  mov     rcx, rax; hHeap
0x1400175ca  call    cs:__imp_HeapFree
0x1400175d0  mov     rsi, [rsp+48h+arg_10]
0x1400175d5  mov     eax, ebx
0x1400175d7  mov     rbx, [rsp+48h+arg_0]
0x1400175dc  add     rsp, 40h
0x1400175e0  pop     rdi
0x1400175e1  retn
```
