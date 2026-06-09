# CreateSymbolicLinkA

- ea: `0x18006bc70`
- end: `0x18006bd0f`
- name: `CreateSymbolicLinkA`
- size: `159`
- prototype: `BOOLEAN __stdcall(LPCSTR lpSymlinkFileName, LPCSTR lpTargetFileName, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x18000d6c0`
- `0x18006bc70`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18006bcc0`
- `ntdll!RtlFreeUnicodeString` at `0x18006bce2`
- `ntdll!RtlFreeUnicodeString` at `0x18006bced`
- `ntdll!RtlFreeUnicodeString` at `0x18006bcc0`
- `ntdll!RtlFreeUnicodeString` at `0x18006bce2`
- `ntdll!RtlFreeUnicodeString` at `0x18006bced`
- `ntdll!RtlSetLastWin32Error` at `0x18006bcfc`
- `ntdll!RtlSetLastWin32Error` at `0x18006bcfc`
- `api-ms-win-core-file-l2-1-0!CreateSymbolicLinkW` at `0x18006bcd5`
- `api-ms-win-core-file-l2-1-0!CreateSymbolicLinkW` at `0x18006bcd5`

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
0x18006bc70  mov     rax, rsp
0x18006bc73  mov     [rax+8], rbx
0x18006bc77  push    rdi
0x18006bc78  sub     rsp, 40h
0x18006bc7c  xorps   xmm0, xmm0
0x18006bc7f  xorps   xmm1, xmm1
0x18006bc82  mov     edi, r8d
0x18006bc85  mov     rbx, rdx
0x18006bc88  movups  xmmword ptr [rax-28h], xmm0
0x18006bc8c  movups  xmmword ptr [rax-18h], xmm1
0x18006bc90  test    rcx, rcx
0x18006bc93  jz      short loc_18006BCF7
0x18006bc95  test    rdx, rdx
0x18006bc98  jz      short loc_18006BCF7
0x18006bc9a  mov     rdx, rcx
0x18006bc9d  lea     rcx, [rax-28h]
0x18006bca1  call    Basep8BitStringToDynamicUnicodeString
0x18006bca6  test    eax, eax
0x18006bca8  jz      short loc_18006BD02
0x18006bcaa  mov     rdx, rbx
0x18006bcad  lea     rcx, [rsp+48h+var_18]
0x18006bcb2  call    Basep8BitStringToDynamicUnicodeString
0x18006bcb7  test    eax, eax
0x18006bcb9  jnz     short loc_18006BCC8
0x18006bcbb  lea     rcx, [rsp+48h+UnicodeString]; UnicodeString
0x18006bcc0  call    cs:__imp_RtlFreeUnicodeString
0x18006bcc6  jmp     short loc_18006BD02
0x18006bcc8  mov     rdx, [rsp+48h+var_18.Buffer]; lpTargetFileName
0x18006bccd  mov     r8d, edi; dwFlags
0x18006bcd0  mov     rcx, [rsp+48h+UnicodeString.Buffer]; lpSymlinkFileName
0x18006bcd5  call    cs:__imp_CreateSymbolicLinkW
0x18006bcdb  lea     rcx, [rsp+48h+var_18]; UnicodeString
0x18006bce0  mov     bl, al
0x18006bce2  call    cs:__imp_RtlFreeUnicodeString
0x18006bce8  lea     rcx, [rsp+48h+UnicodeString]; UnicodeString
0x18006bced  call    cs:__imp_RtlFreeUnicodeString
0x18006bcf3  mov     al, bl
0x18006bcf5  jmp     short loc_18006BD04
0x18006bcf7  mov     ecx, 57h ; 'W'; LastError
0x18006bcfc  call    cs:__imp_RtlSetLastWin32Error
0x18006bd02  xor     al, al
0x18006bd04  mov     rbx, [rsp+48h+arg_0]
0x18006bd09  add     rsp, 40h
0x18006bd0d  pop     rdi
0x18006bd0e  retn
```
