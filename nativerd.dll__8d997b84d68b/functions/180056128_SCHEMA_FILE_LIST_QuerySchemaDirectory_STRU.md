# SCHEMA_FILE_LIST::QuerySchemaDirectory(STRU *)

- ea: `0x180056128`
- end: `0x1800561a9`
- name: `?QuerySchemaDirectory@SCHEMA_FILE_LIST@@SAJPEAVSTRU@@@Z`
- size: `129`
- prototype: `__int64 __fastcall(struct STRU *)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x180016e30`
- `0x18004ff30`
- `0x180055d04`

## callees

- `0x180056128`
- `0x180059c30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005615a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005615a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180056150`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180056150`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180056176`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180056176`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18005618a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18005618a`

## string_xrefs

- `0x180056180`: `\inetsrv\config\schema\`

## pseudocode

```c
signed int __fastcall SCHEMA_FILE_LIST::QuerySchemaDirectory(struct STRU *a1)
{
  signed int result; // eax
  WCHAR Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  if ( GetSystemDirectoryW(Buffer, 0x104u) )
  {
    result = STRU::Copy(a1, Buffer);
    if ( result >= 0 )
      return STRU::Append(a1, L"\\inetsrv\\config\\schema\\");
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180056128  push    rbx
0x18005612a  sub     rsp, 240h
0x180056131  mov     rax, cs:__security_cookie
0x180056138  xor     rax, rsp
0x18005613b  mov     [rsp+248h+var_18], rax
0x180056143  mov     rbx, rcx
0x180056146  mov     edx, 104h; uSize
0x18005614b  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x180056150  call    cs:__imp_GetSystemDirectoryW
0x180056156  test    eax, eax
0x180056158  jnz     short loc_18005616E
0x18005615a  call    cs:__imp_GetLastError
0x180056160  test    eax, eax
0x180056162  jle     short loc_180056190
0x180056164  movzx   eax, ax
0x180056167  or      eax, 80070000h
0x18005616c  jmp     short loc_180056190
0x18005616e  lea     rdx, [rsp+248h+Buffer]
0x180056173  mov     rcx, rbx
0x180056176  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18005617c  test    eax, eax
0x18005617e  js      short loc_180056190
0x180056180  lea     rdx, aInetsrvConfigS; "\\inetsrv\\config\\schema\\"
0x180056187  mov     rcx, rbx
0x18005618a  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180056190  mov     rcx, [rsp+248h+var_18]
0x180056198  xor     rcx, rsp; StackCookie
0x18005619b  call    __security_check_cookie
0x1800561a0  add     rsp, 240h
0x1800561a7  pop     rbx
0x1800561a8  retn
```
