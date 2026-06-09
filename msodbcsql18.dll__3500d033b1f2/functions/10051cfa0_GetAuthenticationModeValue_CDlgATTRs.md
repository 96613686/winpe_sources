# GetAuthenticationModeValue(CDlgATTRs &)

- ea: `0x10051cfa0`
- end: `0x10051d0af`
- name: `?GetAuthenticationModeValue@@YAKAEAVCDlgATTRs@@@Z`
- size: `271`
- prototype: `unsigned int __fastcall(struct CDlgATTRs *)`
- caller_count: `8`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x1005152c0`
- `0x100516470`
- `0x1005172d0`
- `0x1005190b0`
- `0x10051ac58`
- `0x10051baa0`
- `0x10051d274`
- `0x10051eb60`

## callees

- `0x10051cfa0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051cfd8`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051cff1`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051d00a`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051d023`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051d03c`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051d050`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051d084`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051d098`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051cfd8`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051cff1`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051d00a`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051d023`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051d03c`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051d050`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051d084`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051d098`

## string_xrefs

- `0x10051cfe7`: `ActiveDirectoryIntegrated`
- `0x10051cfce`: `ActiveDirectoryPassword`
- `0x10051d019`: `ActiveDirectoryInteractive`
- `0x10051d000`: `ActiveDirectoryMSI`
- `0x10051d046`: `ActiveDirectoryServicePrincipal`

## pseudocode

```c
__int64 __fastcall GetAuthenticationModeValue(struct CDlgATTRs *a1)
{
  __int64 v1; // rdx
  unsigned int v2; // ebx
  const wchar_t *v3; // rdi
  const wchar_t *v5; // rdi

  v1 = *((_QWORD *)a1 + 1);
  v2 = 1;
  if ( (*(_BYTE *)(v1 + 912) & 1) != 0 )
  {
    v3 = (const wchar_t *)(*(_QWORD *)(v1 + 920) + *(_QWORD *)(*((_QWORD *)a1 + 2) + 32LL));
    if ( _wcsicmp(v3, L"ActiveDirectoryPassword") )
    {
      if ( _wcsicmp(v3, L"ActiveDirectoryIntegrated") )
      {
        if ( _wcsicmp(v3, L"ActiveDirectoryMSI") )
        {
          if ( _wcsicmp(v3, L"ActiveDirectoryInteractive") )
          {
            if ( _wcsicmp(v3, L"SqlPassword") )
              return _wcsicmp(v3, L"ActiveDirectoryServicePrincipal") == 0 ? 7 : 0;
          }
          else
          {
            return 4;
          }
        }
        else
        {
          return 6;
        }
      }
      else
      {
        return 2;
      }
    }
    else
    {
      return 3;
    }
    return v2;
  }
  if ( (*(_BYTE *)(v1 + 192) & 1) != 0 )
  {
    v5 = (const wchar_t *)(*(_QWORD *)(v1 + 200) + *(_QWORD *)(*((_QWORD *)a1 + 2) + 32LL));
    if ( _wcsicmp(v5, L"No") )
    {
      if ( !_wcsicmp(v5, L"Yes") )
        return v2;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x10051cfa0  mov     [rsp+arg_0], rbx
0x10051cfa5  push    rdi
0x10051cfa6  sub     rsp, 20h
0x10051cfaa  mov     rdx, [rcx+8]
0x10051cfae  mov     ebx, 1
0x10051cfb3  test    [rdx+390h], bl
0x10051cfb9  jz      loc_10051D063
0x10051cfbf  mov     rax, [rcx+10h]
0x10051cfc3  mov     rdi, [rax+20h]
0x10051cfc7  add     rdi, [rdx+398h]
0x10051cfce  lea     rdx, aActivedirector_2; "ActiveDirectoryPassword"
0x10051cfd5  mov     rcx, rdi; String1
0x10051cfd8  call    cs:__imp__wcsicmp
0x10051cfde  test    eax, eax
0x10051cfe0  jnz     short loc_10051CFE7
0x10051cfe2  lea     ebx, [rax+3]
0x10051cfe5  jmp     short loc_10051D05F
0x10051cfe7  lea     rdx, aActivedirector_1; "ActiveDirectoryIntegrated"
0x10051cfee  mov     rcx, rdi; String1
0x10051cff1  call    cs:__imp__wcsicmp
0x10051cff7  test    eax, eax
0x10051cff9  jnz     short loc_10051D000
0x10051cffb  lea     ebx, [rax+2]
0x10051cffe  jmp     short loc_10051D05F
0x10051d000  lea     rdx, aActivedirector_3; "ActiveDirectoryMSI"
0x10051d007  mov     rcx, rdi; String1
0x10051d00a  call    cs:__imp__wcsicmp
0x10051d010  test    eax, eax
0x10051d012  jnz     short loc_10051D019
0x10051d014  lea     ebx, [rax+6]
0x10051d017  jmp     short loc_10051D05F
0x10051d019  lea     rdx, aActivedirector; "ActiveDirectoryInteractive"
0x10051d020  mov     rcx, rdi; String1
0x10051d023  call    cs:__imp__wcsicmp
0x10051d029  test    eax, eax
0x10051d02b  jnz     short loc_10051D032
0x10051d02d  lea     ebx, [rax+4]
0x10051d030  jmp     short loc_10051D05F
0x10051d032  lea     rdx, aSqlpassword; "SqlPassword"
0x10051d039  mov     rcx, rdi; String1
0x10051d03c  call    cs:__imp__wcsicmp
0x10051d042  test    eax, eax
0x10051d044  jz      short loc_10051D05F
0x10051d046  lea     rdx, aActivedirector_0; "ActiveDirectoryServicePrincipal"
0x10051d04d  mov     rcx, rdi; String1
0x10051d050  call    cs:__imp__wcsicmp
0x10051d056  neg     eax
0x10051d058  sbb     ebx, ebx
0x10051d05a  not     ebx
0x10051d05c  and     ebx, 7
0x10051d05f  mov     eax, ebx
0x10051d061  jmp     short loc_10051D0A4
0x10051d063  test    [rdx+0C0h], bl
0x10051d069  jz      short loc_10051D0A2
0x10051d06b  mov     rax, [rcx+10h]
0x10051d06f  mov     rdi, [rax+20h]
0x10051d073  add     rdi, [rdx+0C8h]
0x10051d07a  lea     rdx, aNo; "No"
0x10051d081  mov     rcx, rdi; String1
0x10051d084  call    cs:__imp__wcsicmp
0x10051d08a  test    eax, eax
0x10051d08c  jz      short loc_10051D0A2
0x10051d08e  lea     rdx, aYes_1; "Yes"
0x10051d095  mov     rcx, rdi; String1
0x10051d098  call    cs:__imp__wcsicmp
0x10051d09e  test    eax, eax
0x10051d0a0  jz      short loc_10051D05F
0x10051d0a2  xor     eax, eax
0x10051d0a4  mov     rbx, [rsp+28h+arg_0]
0x10051d0a9  add     rsp, 20h
0x10051d0ad  pop     rdi
0x10051d0ae  retn
```
