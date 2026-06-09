# GetChannelServiceSid

- ea: `0x180074b88`
- end: `0x180074c95`
- name: `GetChannelServiceSid`
- size: `269`
- prototype: `__int64 __fastcall(char *String1)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180074c9c`

## callees

- `0x180074b88`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp_l` at `0x180074bed`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp_l` at `0x180074c04`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp_l` at `0x180074c1b`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp_l` at `0x180074bed`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp_l` at `0x180074c04`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp_l` at `0x180074c1b`
- `api-ms-win-crt-private-l1-1-0!_o__free_locale` at `0x180074c7d`
- `api-ms-win-crt-private-l1-1-0!_o__free_locale` at `0x180074c7d`
- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x180074bc8`
- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x180074bc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074c4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074c4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180074bac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180074c72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180074bac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180074c72`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180074c41`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180074c41`

## pseudocode

```c
__int64 __fastcall GetChannelServiceSid(char *String1, void **a2)
{
  void *v4; // rcx
  struct localeinfo_struct *locale; // rax
  struct localeinfo_struct *v7; // rdi
  unsigned int v8; // ebx
  signed int LastError; // eax
  void *v10; // rcx
  PSID Sid; // [rsp+30h] [rbp+8h] BYREF

  v4 = *a2;
  *a2 = 0;
  if ( v4 )
    LocalFree(v4);
  if ( !String1 )
    return 1;
  locale = _create_locale(0, "C");
  v7 = locale;
  if ( !locale )
    return 2147942414LL;
  if ( _stricmp_l(String1, "AUDIO_PLAYBACK_DVC", locale)
    && _stricmp_l(String1, "AUDIO_PLAYBACK_LOSSY_DVC", v7)
    && _stricmp_l(String1, "RDPSND", v7) )
  {
    v8 = 1;
  }
  else
  {
    Sid = 0;
    if ( ConvertStringSidToSidW(L"S-1-5-80-2676549577-1911656217-2625096541-4178041876-1366760775", &Sid) )
    {
      v10 = *a2;
      *a2 = Sid;
      if ( v10 )
        LocalFree(v10);
      v8 = 0;
    }
    else
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  _free_locale(v7);
  return v8;
}

```

## disassembly

```asm
0x180074b88  mov     [rsp+arg_8], rbx
0x180074b8d  mov     [rsp+arg_10], rsi
0x180074b92  push    rdi
0x180074b93  sub     rsp, 20h
0x180074b97  mov     rsi, rcx
0x180074b9a  mov     rbx, rdx
0x180074b9d  mov     rcx, [rdx]; hMem
0x180074ba0  mov     qword ptr [rdx], 0
0x180074ba7  test    rcx, rcx
0x180074baa  jz      short loc_180074BB2
0x180074bac  call    cs:__imp_LocalFree
0x180074bb2  test    rsi, rsi
0x180074bb5  jnz     short loc_180074BBF
0x180074bb7  lea     eax, [rsi+1]
0x180074bba  jmp     loc_180074C85
0x180074bbf  lea     rdx, Locale; "C"
0x180074bc6  xor     ecx, ecx; Category
0x180074bc8  call    cs:__imp__create_locale
0x180074bce  mov     rdi, rax
0x180074bd1  test    rax, rax
0x180074bd4  jnz     short loc_180074BE0
0x180074bd6  mov     eax, 8007000Eh
0x180074bdb  jmp     loc_180074C85
0x180074be0  mov     r8, rdi; Locale
0x180074be3  lea     rdx, aAudioPlaybackD; "AUDIO_PLAYBACK_DVC"
0x180074bea  mov     rcx, rsi; String1
0x180074bed  call    cs:__imp__stricmp_l
0x180074bf3  test    eax, eax
0x180074bf5  jz      short loc_180074C2C
0x180074bf7  mov     r8, rdi; Locale
0x180074bfa  lea     rdx, aAudioPlaybackL; "AUDIO_PLAYBACK_LOSSY_DVC"
0x180074c01  mov     rcx, rsi; String1
0x180074c04  call    cs:__imp__stricmp_l
0x180074c0a  test    eax, eax
0x180074c0c  jz      short loc_180074C2C
0x180074c0e  mov     r8, rdi; Locale
0x180074c11  lea     rdx, aRdpsnd; "RDPSND"
0x180074c18  mov     rcx, rsi; String1
0x180074c1b  call    cs:__imp__stricmp_l
0x180074c21  test    eax, eax
0x180074c23  jz      short loc_180074C2C
0x180074c25  mov     ebx, 1
0x180074c2a  jmp     short loc_180074C7A
0x180074c2c  lea     rdx, [rsp+28h+Sid]; Sid
0x180074c31  mov     [rsp+28h+Sid], 0
0x180074c3a  lea     rcx, StringSid; "S-1-5-80-2676549577-1911656217-26250965"...
0x180074c41  call    cs:__imp_ConvertStringSidToSidW
0x180074c47  test    eax, eax
0x180074c49  jnz     short loc_180074C62
0x180074c4b  call    cs:__imp_GetLastError
0x180074c51  mov     ebx, eax
0x180074c53  test    eax, eax
0x180074c55  jle     short loc_180074C7A
0x180074c57  movzx   ebx, ax
0x180074c5a  or      ebx, 80070000h
0x180074c60  jmp     short loc_180074C7A
0x180074c62  mov     rcx, [rbx]; hMem
0x180074c65  mov     rax, [rsp+28h+Sid]
0x180074c6a  mov     [rbx], rax
0x180074c6d  test    rcx, rcx
0x180074c70  jz      short loc_180074C78
0x180074c72  call    cs:__imp_LocalFree
0x180074c78  xor     ebx, ebx
0x180074c7a  mov     rcx, rdi; Locale
0x180074c7d  call    cs:__imp__free_locale
0x180074c83  mov     eax, ebx
0x180074c85  mov     rbx, [rsp+28h+arg_8]
0x180074c8a  mov     rsi, [rsp+28h+arg_10]
0x180074c8f  add     rsp, 20h
0x180074c93  pop     rdi
0x180074c94  retn
```
