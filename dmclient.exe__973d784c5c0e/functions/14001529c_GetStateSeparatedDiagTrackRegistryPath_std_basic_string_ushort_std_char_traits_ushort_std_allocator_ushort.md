# GetStateSeparatedDiagTrackRegistryPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x14001529c`
- end: `0x1400153d3`
- name: `?GetStateSeparatedDiagTrackRegistryPath@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `311`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000fbf8`

## callees

- `0x140014cf8`
- `0x14001529c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400152ea`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140015376`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400152ea`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140015376`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140015328`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140015328`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015311`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400153a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015311`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400153a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400153b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400153b4`

## string_xrefs

- `0x1400152bc`: `RedirectedRegistryRoot`
- `0x140015353`: `RedirectedRegistryRoot`

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
0x14001529c  mov     r11, rsp
0x14001529f  mov     [r11+8], rbx
0x1400152a3  mov     [r11+18h], rsi
0x1400152a7  push    rdi
0x1400152a8  sub     rsp, 40h
0x1400152ac  lea     rax, [r11+10h]
0x1400152b0  mov     dword ptr [rsp+48h+dwBytes], 0
0x1400152b8  mov     [r11-18h], rax
0x1400152bc  lea     r8, aRedirectedregi; "RedirectedRegistryRoot"
0x1400152c3  mov     rsi, rcx
0x1400152c6  mov     qword ptr [r11-20h], 0
0x1400152ce  mov     r9d, 6; dwFlags
0x1400152d4  mov     qword ptr [r11-28h], 0
0x1400152dc  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400152e3  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1400152ea  call    cs:__imp_RegGetValueW
0x1400152f1  nop     dword ptr [rax+rax+00h]
0x1400152f6  mov     ebx, eax
0x1400152f8  test    eax, eax
0x1400152fa  jle     short loc_140015305
0x1400152fc  movzx   ebx, ax
0x1400152ff  or      ebx, 80070000h
0x140015305  test    ebx, ebx
0x140015307  jnz     loc_1400153C0
0x14001530d  mov     ebx, dword ptr [rsp+48h+dwBytes]
0x140015311  call    cs:__imp_GetProcessHeap
0x140015318  nop     dword ptr [rax+rax+00h]
0x14001531d  mov     r8d, ebx; dwBytes
0x140015320  mov     edx, 8; dwFlags
0x140015325  mov     rcx, rax; hHeap
0x140015328  call    cs:__imp_HeapAlloc
0x14001532f  nop     dword ptr [rax+rax+00h]
0x140015334  mov     rdi, rax
0x140015337  test    rax, rax
0x14001533a  jnz     short loc_140015343
0x14001533c  mov     ebx, 8007000Eh
0x140015341  jmp     short loc_1400153C0
0x140015343  lea     rax, [rsp+48h+dwBytes]
0x140015348  mov     r9d, 6; dwFlags
0x14001534e  mov     [rsp+48h+pcbData], rax; pcbData
0x140015353  lea     r8, aRedirectedregi; "RedirectedRegistryRoot"
0x14001535a  mov     [rsp+48h+pvData], rdi; pvData
0x14001535f  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140015366  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14001536d  mov     [rsp+48h+pdwType], 0; pdwType
0x140015376  call    cs:__imp_RegGetValueW
0x14001537d  nop     dword ptr [rax+rax+00h]
0x140015382  mov     ebx, eax
0x140015384  test    eax, eax
0x140015386  jle     short loc_140015391
0x140015388  movzx   ebx, ax
0x14001538b  or      ebx, 80070000h
0x140015391  test    ebx, ebx
0x140015393  js      short loc_1400153A0
0x140015395  mov     rdx, rdi; Src
0x140015398  mov     rcx, rsi; void *
0x14001539b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator=(ushort const *)
0x1400153a0  call    cs:__imp_GetProcessHeap
0x1400153a7  nop     dword ptr [rax+rax+00h]
0x1400153ac  mov     r8, rdi; lpMem
0x1400153af  xor     edx, edx; dwFlags
0x1400153b1  mov     rcx, rax; hHeap
0x1400153b4  call    cs:__imp_HeapFree
0x1400153bb  nop     dword ptr [rax+rax+00h]
0x1400153c0  mov     rsi, [rsp+48h+arg_10]
0x1400153c5  mov     eax, ebx
0x1400153c7  mov     rbx, [rsp+48h+arg_0]
0x1400153cc  add     rsp, 40h
0x1400153d0  pop     rdi
0x1400153d1  retn
```
