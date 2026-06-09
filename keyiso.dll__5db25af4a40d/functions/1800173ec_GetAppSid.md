# GetAppSid

- ea: `0x1800173ec`
- end: `0x1800174e7`
- name: `GetAppSid`
- size: `251`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, LPWSTR *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800172ac`

## callees

- `0x1800173ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001742c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017489`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001748f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001742c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017489`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001748f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800174c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800174d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800174c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800174d2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017450`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017450`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800174a1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800174a1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017422`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001747f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017422`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001747f`

## pseudocode

```c
__int64 __fastcall GetAppSid(HANDLE TokenHandle, LPWSTR *a2)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  PSID *v6; // rdi
  SIZE_T uBytes; // [rsp+60h] [rbp+18h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp+20h] BYREF

  StringSid = 0;
  LODWORD(uBytes) = 0;
  if ( GetTokenInformation(TokenHandle, TokenAppContainerSid, 0, 0, (PDWORD)&uBytes)
    || (LastError = GetLastError(), v5 = LastError, LastError == 122) )
  {
    v6 = (PSID *)LocalAlloc(0, (unsigned int)uBytes);
    if ( !v6 )
    {
      v5 = -2146893810;
      goto LABEL_12;
    }
    if ( GetTokenInformation(TokenHandle, TokenAppContainerSid, v6, uBytes, (PDWORD)&uBytes)
      && ConvertSidToStringSidW(*v6, &StringSid) )
    {
      v5 = 0;
      *a2 = StringSid;
      StringSid = 0;
      goto LABEL_12;
    }
    GetLastError();
    LastError = GetLastError();
    v5 = LastError;
  }
  else
  {
    v6 = 0;
  }
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
LABEL_12:
  if ( StringSid )
    LocalFree(StringSid);
  if ( v6 )
    LocalFree(v6);
  return v5;
}

```

## disassembly

```asm
0x1800173ec  mov     rax, rsp
0x1800173ef  mov     [rax+8], rbx
0x1800173f3  push    rbp
0x1800173f4  push    rsi
0x1800173f5  push    rdi
0x1800173f6  sub     rsp, 30h
0x1800173fa  xor     r9d, r9d; TokenInformationLength
0x1800173fd  mov     qword ptr [rax+20h], 0
0x180017405  mov     dword ptr [rax+18h], 0
0x18001740c  lea     rax, [rax+18h]
0x180017410  mov     rsi, rdx
0x180017413  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180017418  xor     r8d, r8d; TokenInformation
0x18001741b  mov     rbp, rcx
0x18001741e  lea     edx, [r9+1Fh]; TokenInformationClass
0x180017422  call    cs:__imp_GetTokenInformation
0x180017428  test    eax, eax
0x18001742a  jnz     short loc_18001744A
0x18001742c  call    cs:__imp_GetLastError
0x180017432  mov     ebx, eax
0x180017434  cmp     eax, 7Ah ; 'z'
0x180017437  jz      short loc_18001744A
0x180017439  xor     edi, edi
0x18001743b  test    eax, eax
0x18001743d  jle     short loc_1800174BA
0x18001743f  movzx   ebx, ax
0x180017442  or      ebx, 80070000h
0x180017448  jmp     short loc_1800174BA
0x18001744a  mov     edx, dword ptr [rsp+48h+uBytes]; uBytes
0x18001744e  xor     ecx, ecx; uFlags
0x180017450  call    cs:__imp_LocalAlloc
0x180017456  mov     rdi, rax
0x180017459  test    rax, rax
0x18001745c  jnz     short loc_180017465
0x18001745e  mov     ebx, 8009000Eh
0x180017463  jmp     short loc_1800174BA
0x180017465  mov     r9d, dword ptr [rsp+48h+uBytes]; TokenInformationLength
0x18001746a  lea     rax, [rsp+48h+uBytes]
0x18001746f  mov     r8, rdi; TokenInformation
0x180017472  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180017477  mov     edx, 1Fh; TokenInformationClass
0x18001747c  mov     rcx, rbp; TokenHandle
0x18001747f  call    cs:__imp_GetTokenInformation
0x180017485  test    eax, eax
0x180017487  jnz     short loc_180017499
0x180017489  call    cs:__imp_GetLastError
0x18001748f  call    cs:__imp_GetLastError
0x180017495  mov     ebx, eax
0x180017497  jmp     short loc_18001743B
0x180017499  mov     rcx, [rdi]; Sid
0x18001749c  lea     rdx, [rsp+48h+StringSid]; StringSid
0x1800174a1  call    cs:__imp_ConvertSidToStringSidW
0x1800174a7  test    eax, eax
0x1800174a9  jz      short loc_180017489
0x1800174ab  mov     rax, [rsp+48h+StringSid]
0x1800174b0  xor     ebx, ebx
0x1800174b2  mov     [rsi], rax
0x1800174b5  mov     [rsp+48h+StringSid], rbx
0x1800174ba  mov     rcx, [rsp+48h+StringSid]; hMem
0x1800174bf  test    rcx, rcx
0x1800174c2  jz      short loc_1800174CA
0x1800174c4  call    cs:__imp_LocalFree
0x1800174ca  test    rdi, rdi
0x1800174cd  jz      short loc_1800174D8
0x1800174cf  mov     rcx, rdi; hMem
0x1800174d2  call    cs:__imp_LocalFree
0x1800174d8  mov     eax, ebx
0x1800174da  mov     rbx, [rsp+48h+arg_0]
0x1800174df  add     rsp, 30h
0x1800174e3  pop     rdi
0x1800174e4  pop     rsi
0x1800174e5  pop     rbp
0x1800174e6  retn
```
