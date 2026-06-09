# CreateSymbolicLinkA

- ea: `0x180073140`
- end: `0x1800731fe`
- name: `CreateSymbolicLinkA`
- size: `190`
- prototype: `BOOLEAN __stdcall(LPCSTR lpSymlinkFileName, LPCSTR lpTargetFileName, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x180028f60`
- `0x180073140`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180073190`
- `ntdll!RtlFreeUnicodeString` at `0x1800731be`
- `ntdll!RtlFreeUnicodeString` at `0x1800731cf`
- `ntdll!RtlFreeUnicodeString` at `0x180073190`
- `ntdll!RtlFreeUnicodeString` at `0x1800731be`
- `ntdll!RtlFreeUnicodeString` at `0x1800731cf`
- `ntdll!RtlSetLastWin32Error` at `0x1800731e4`
- `ntdll!RtlSetLastWin32Error` at `0x1800731e4`
- `api-ms-win-core-file-l2-1-0!CreateSymbolicLinkW` at `0x1800731ab`
- `api-ms-win-core-file-l2-1-0!CreateSymbolicLinkW` at `0x1800731ab`

## pseudocode

```c
BOOLEAN __stdcall CreateSymbolicLinkA(LPCSTR lpSymlinkFileName, LPCSTR lpTargetFileName, DWORD dwFlags)
{
  BOOLEAN SymbolicLinkW; // bl
  struct _UNICODE_STRING UnicodeString; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING v8; // [rsp+30h] [rbp-18h] BYREF

  UnicodeString = 0;
  v8 = 0;
  if ( lpSymlinkFileName && lpTargetFileName )
  {
    if ( (unsigned int)Basep8BitStringToDynamicUnicodeString(&UnicodeString, lpSymlinkFileName) )
    {
      if ( (unsigned int)Basep8BitStringToDynamicUnicodeString(&v8, lpTargetFileName) )
      {
        SymbolicLinkW = CreateSymbolicLinkW(UnicodeString.Buffer, v8.Buffer, dwFlags);
        RtlFreeUnicodeString(&v8);
        RtlFreeUnicodeString(&UnicodeString);
        return SymbolicLinkW;
      }
      RtlFreeUnicodeString(&UnicodeString);
    }
  }
  else
  {
    RtlSetLastWin32Error(0x57u);
  }
  return 0;
}

```

## disassembly

```asm
0x180073140  mov     rax, rsp
0x180073143  mov     [rax+8], rbx
0x180073147  push    rdi
0x180073148  sub     rsp, 40h
0x18007314c  xorps   xmm0, xmm0
0x18007314f  xorps   xmm1, xmm1
0x180073152  mov     edi, r8d
0x180073155  mov     rbx, rdx
0x180073158  movups  xmmword ptr [rax-28h], xmm0
0x18007315c  movups  xmmword ptr [rax-18h], xmm1
0x180073160  test    rcx, rcx
0x180073163  jz      short loc_1800731DF
0x180073165  test    rdx, rdx
0x180073168  jz      short loc_1800731DF
0x18007316a  mov     rdx, rcx
0x18007316d  lea     rcx, [rax-28h]
0x180073171  call    Basep8BitStringToDynamicUnicodeString
0x180073176  test    eax, eax
0x180073178  jz      short loc_1800731F0
0x18007317a  mov     rdx, rbx
0x18007317d  lea     rcx, [rsp+48h+var_18]
0x180073182  call    Basep8BitStringToDynamicUnicodeString
0x180073187  test    eax, eax
0x180073189  jnz     short loc_18007319E
0x18007318b  lea     rcx, [rsp+48h+UnicodeString]; UnicodeString
0x180073190  call    cs:__imp_RtlFreeUnicodeString
0x180073197  nop     dword ptr [rax+rax+00h]
0x18007319c  jmp     short loc_1800731F0
0x18007319e  mov     rdx, [rsp+48h+var_18.Buffer]; lpTargetFileName
0x1800731a3  mov     r8d, edi; dwFlags
0x1800731a6  mov     rcx, [rsp+48h+UnicodeString.Buffer]; lpSymlinkFileName
0x1800731ab  call    cs:__imp_CreateSymbolicLinkW
0x1800731b2  nop     dword ptr [rax+rax+00h]
0x1800731b7  lea     rcx, [rsp+48h+var_18]; UnicodeString
0x1800731bc  mov     bl, al
0x1800731be  call    cs:__imp_RtlFreeUnicodeString
0x1800731c5  nop     dword ptr [rax+rax+00h]
0x1800731ca  lea     rcx, [rsp+48h+UnicodeString]; UnicodeString
0x1800731cf  call    cs:__imp_RtlFreeUnicodeString
0x1800731d6  nop     dword ptr [rax+rax+00h]
0x1800731db  mov     al, bl
0x1800731dd  jmp     short loc_1800731F2
0x1800731df  mov     ecx, 57h ; 'W'; LastError
0x1800731e4  call    cs:__imp_RtlSetLastWin32Error
0x1800731eb  nop     dword ptr [rax+rax+00h]
0x1800731f0  xor     al, al
0x1800731f2  mov     rbx, [rsp+48h+arg_0]
0x1800731f7  add     rsp, 40h
0x1800731fb  pop     rdi
0x1800731fc  retn
```
