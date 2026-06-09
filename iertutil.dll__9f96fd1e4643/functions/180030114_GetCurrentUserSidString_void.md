# GetCurrentUserSidString(void)

- ea: `0x180030114`
- end: `0x18003019f`
- name: `?GetCurrentUserSidString@@YAPEBGXZ`
- size: `139`
- prototype: `const unsigned __int16 *(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002fe60`

## callees

- `0x180030114`
- `0x180030b00`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180030176`
- `msvcrt!wcscpy_s` at `0x180030176`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003015d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003015d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030181`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003018c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030181`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003018c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180030153`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180030153`

## pseudocode

```c
wchar_t *GetCurrentUserSidString(void)
{
  int CurrentUserSid; // eax
  bool v1; // sf
  LPWSTR StringSid; // [rsp+30h] [rbp+8h] BYREF
  PSID Sid; // [rsp+38h] [rbp+10h] BYREF

  if ( !word_18029A000 )
  {
    Sid = 0;
    CurrentUserSid = GetCurrentUserSid(&Sid);
    v1 = CurrentUserSid < 0;
    if ( CurrentUserSid > 0 )
      v1 = 1;
    if ( !v1 )
    {
      StringSid = 0;
      if ( ConvertSidToStringSidW(Sid, &StringSid) )
      {
        wcscpy_s(&word_18029A000, 0x88u, StringSid);
        LocalFree(StringSid);
      }
      else
      {
        GetLastError();
      }
      LocalFree(Sid);
    }
  }
  return &word_18029A000;
}

```

## disassembly

```asm
0x180030114  push    rbx
0x180030116  sub     rsp, 20h
0x18003011a  xor     ebx, ebx
0x18003011c  cmp     cs:word_18029A000, bx
0x180030123  jnz     short loc_180030192
0x180030125  lea     rcx, [rsp+28h+Sid]; void **
0x18003012a  mov     [rsp+28h+Sid], rbx
0x18003012f  call    ?GetCurrentUserSid@@YAKPEAPEAX@Z; GetCurrentUserSid(void * *)
0x180030134  test    eax, eax
0x180030136  jle     short loc_180030142
0x180030138  movzx   eax, ax
0x18003013b  or      eax, 80070000h
0x180030140  test    eax, eax
0x180030142  js      short loc_180030192
0x180030144  mov     rcx, [rsp+28h+Sid]; Sid
0x180030149  lea     rdx, [rsp+28h+StringSid]; StringSid
0x18003014e  mov     [rsp+28h+StringSid], rbx
0x180030153  call    cs:__imp_ConvertSidToStringSidW
0x180030159  test    eax, eax
0x18003015b  jnz     short loc_180030165
0x18003015d  call    cs:__imp_GetLastError
0x180030163  jmp     short loc_180030187
0x180030165  mov     r8, [rsp+28h+StringSid]; Source
0x18003016a  lea     rcx, word_18029A000; Destination
0x180030171  mov     edx, 88h; SizeInWords
0x180030176  call    cs:__imp_wcscpy_s
0x18003017c  mov     rcx, [rsp+28h+StringSid]; hMem
0x180030181  call    cs:__imp_LocalFree
0x180030187  mov     rcx, [rsp+28h+Sid]; hMem
0x18003018c  call    cs:__imp_LocalFree
0x180030192  lea     rax, word_18029A000
0x180030199  add     rsp, 20h
0x18003019d  pop     rbx
0x18003019e  retn
```
