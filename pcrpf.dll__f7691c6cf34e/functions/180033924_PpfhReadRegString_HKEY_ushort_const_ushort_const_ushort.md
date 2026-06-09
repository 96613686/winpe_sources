# PpfhReadRegString(HKEY__ *,ushort const *,ushort const *,ushort * *)

- ea: `0x180033924`
- end: `0x180033ade`
- name: `?PpfhReadRegString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z`
- size: `442`
- prototype: `int __fastcall(HKEY hkey, LPCWSTR lpSubKey, LPCWSTR lpValue, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000d1e8`
- `0x18004fe98`
- `0x1800518d0`

## callees

- `0x180009c64`
- `0x18000dfe0`
- `0x18000f0c8`
- `0x18002d5ec`
- `0x180033924`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033a52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033a52`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033a66`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033a66`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033970`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033a27`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033970`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033a27`

## string_xrefs

- `0x180033a87`: `PpfhReadRegString`
- `0x180033ab0`: `PpfhReadRegString`

## pseudocode

```c
int __fastcall PpfhReadRegString(HKEY hkey, LPCWSTR lpSubKey, LPCWSTR lpValue, unsigned __int16 **a4)
{
  unsigned int ValueW; // eax
  const char *v9; // r9
  PVOID v11; // rbx
  unsigned int v12; // eax
  int v13; // edi
  HANDLE ProcessHeap; // rax
  unsigned int pdwType; // [rsp+20h] [rbp-48h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-48h]
  PVOID lpMem[5]; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  DWORD pcbData; // [rsp+88h] [rbp+20h] BYREF

  *a4 = 0;
  pcbData = 0;
  ValueW = RegGetValueW(hkey, lpSubKey, lpValue, 0x20000002u, 0, 0, &pcbData);
  if ( ValueW - 2 <= 1 || pcbData <= 2 )
  {
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
      0x371u,
      "PpfhReadRegString",
      "%ws: <not set>",
      lpValue);
  }
  else
  {
    if ( ValueW )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x374,
               (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
               (const char *)ValueW,
               pdwType);
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      lpMem,
      0,
      pcbData,
      v9);
    v11 = lpMem[0];
    if ( !lpMem[0] )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x377,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
        (const char *)0x8007000ELL,
        pdwType);
      return -2147024882;
    }
    v12 = RegGetValueW(hkey, lpSubKey, lpValue, 0x20000002u, 0, lpMem[0], &pcbData);
    if ( v12 )
    {
      v13 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x37A,
              (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
              (const char *)v12,
              pdwTypea);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v11);
      return v13;
    }
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
      0x37Cu,
      "PpfhReadRegString",
      "%ws: %ws",
      lpValue,
      v11);
    *a4 = (unsigned __int16 *)v11;
  }
  return 0;
}

```

## disassembly

```asm
0x180033924  mov     r11, rsp
0x180033927  mov     [r11+8], rbx
0x18003392b  mov     [r11+10h], rbp
0x18003392f  push    rsi
0x180033930  push    rdi
0x180033931  push    r14
0x180033933  sub     rsp, 50h
0x180033937  mov     rsi, r9
0x18003393a  mov     rdi, r8
0x18003393d  mov     rbp, rdx
0x180033940  mov     r14, rcx
0x180033943  mov     qword ptr [r9], 0
0x18003394a  mov     dword ptr [r11+20h], 0
0x180033952  lea     rax, [r11+20h]
0x180033956  mov     [r11-38h], rax
0x18003395a  mov     qword ptr [r11-40h], 0
0x180033962  mov     qword ptr [r11-48h], 0
0x18003396a  mov     r9d, 20000002h; dwFlags
0x180033970  call    cs:__imp_RegGetValueW
0x180033977  nop     dword ptr [rax+rax+00h]
0x18003397c  lea     ecx, [rax-2]
0x18003397f  cmp     ecx, 1
0x180033982  jbe     loc_180033AA4
0x180033988  cmp     [rsp+68h+arg_18], 2
0x180033990  jbe     loc_180033AA4
0x180033996  test    eax, eax
0x180033998  jz      short loc_1800339B8
0x18003399a  mov     rcx, [rsp+68h]; this
0x18003399f  mov     r9d, eax; char *
0x1800339a2  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x1800339a9  mov     edx, 374h; void *
0x1800339ae  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800339b3  jmp     loc_180033ACA
0x1800339b8  mov     r8d, [rsp+68h+arg_18]
0x1800339c0  xor     edx, edx
0x1800339c2  lea     rcx, [rsp+68h+lpMem]
0x1800339c7  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800339cc  nop
0x1800339cd  mov     rbx, [rsp+68h+lpMem]
0x1800339d2  test    rbx, rbx
0x1800339d5  jnz     short loc_1800339FD
0x1800339d7  mov     rcx, [rsp+68h]; this
0x1800339dc  mov     ebx, 8007000Eh
0x1800339e1  mov     r9d, ebx; char *
0x1800339e4  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x1800339eb  mov     edx, 377h; void *
0x1800339f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800339f5  nop
0x1800339f6  mov     eax, ebx
0x1800339f8  jmp     loc_180033ACA
0x1800339fd  lea     rax, [rsp+68h+arg_18]
0x180033a05  mov     [rsp+68h+pcbData], rax; pcbData
0x180033a0a  mov     [rsp+68h+pvData], rbx; pvData
0x180033a0f  mov     [rsp+68h+pdwType], 0; unsigned int
0x180033a18  mov     r9d, 20000002h; dwFlags
0x180033a1e  mov     r8, rdi; lpValue
0x180033a21  mov     rdx, rbp; lpSubKey
0x180033a24  mov     rcx, r14; hkey
0x180033a27  call    cs:__imp_RegGetValueW
0x180033a2e  nop     dword ptr [rax+rax+00h]
0x180033a33  test    eax, eax
0x180033a35  jz      short loc_180033A76
0x180033a37  mov     rcx, [rsp+68h]; this
0x180033a3c  mov     r9d, eax; char *
0x180033a3f  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180033a46  mov     edx, 37Ah; void *
0x180033a4b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180033a50  mov     edi, eax
0x180033a52  call    cs:__imp_GetProcessHeap
0x180033a59  nop     dword ptr [rax+rax+00h]
0x180033a5e  mov     rcx, rax; hHeap
0x180033a61  mov     r8, rbx; lpMem
0x180033a64  xor     edx, edx; dwFlags
0x180033a66  call    cs:__imp_HeapFree
0x180033a6d  nop     dword ptr [rax+rax+00h]
0x180033a72  mov     eax, edi
0x180033a74  jmp     short loc_180033ACA
0x180033a76  mov     [rsp+68h+pvData], rbx
0x180033a7b  mov     [rsp+68h+pdwType], rdi
0x180033a80  lea     r9, aWsWs; "%ws: %ws"
0x180033a87  lea     r8, aPpfhreadregstr; "PpfhReadRegString"
0x180033a8e  mov     edx, 37Ch; unsigned int
0x180033a93  lea     rcx, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180033a9a  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180033a9f  mov     [rsi], rbx
0x180033aa2  jmp     short loc_180033AC8
0x180033aa4  mov     [rsp+68h+pdwType], rdi
0x180033aa9  lea     r9, aWsNotSet; "%ws: <not set>"
0x180033ab0  lea     r8, aPpfhreadregstr; "PpfhReadRegString"
0x180033ab7  mov     edx, 371h; unsigned int
0x180033abc  lea     rcx, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180033ac3  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180033ac8  xor     eax, eax
0x180033aca  mov     rbx, [rsp+68h+arg_0]
0x180033acf  mov     rbp, [rsp+68h+arg_8]
0x180033ad4  add     rsp, 50h
0x180033ad8  pop     r14
0x180033ada  pop     rdi
0x180033adb  pop     rsi
0x180033adc  retn
```
