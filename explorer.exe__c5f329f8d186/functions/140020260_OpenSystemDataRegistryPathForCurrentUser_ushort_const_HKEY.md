# OpenSystemDataRegistryPathForCurrentUser(ushort const *,HKEY__ * *)

- ea: `0x140020260`
- end: `0x14002039e`
- name: `?OpenSystemDataRegistryPathForCurrentUser@@YAJPEBGPEAPEAUHKEY__@@@Z`
- size: `318`
- prototype: `int(const unsigned __int16 *, HKEY *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14001fae4`
- `0x14013ccdc`

## callees

- `0x14001c330`
- `0x140020260`
- `0x1400203a4`
- `0x140020580`
- `0x14010e160`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002032c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002032c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002034c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002035d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002034c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002035d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1400202b9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1400202b9`

## string_xrefs

- `0x1400202de`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SystemProtectedUserData`

## pseudocode

```c
__int64 __fastcall OpenSystemDataRegistryPathForCurrentUser(const unsigned __int16 *a1, HKEY *a2)
{
  signed int CurrentUserSid; // ebx
  LSTATUS v4; // eax
  LPWSTR StringSid; // [rsp+40h] [rbp-238h] BYREF
  PSID Sid; // [rsp+48h] [rbp-230h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-228h] BYREF

  *a2 = 0;
  Sid = 0;
  CurrentUserSid = GetCurrentUserSid(&Sid);
  if ( CurrentUserSid >= 0 )
  {
    StringSid = 0;
    if ( ConvertSidToStringSidW(Sid, &StringSid) || (CurrentUserSid = ResultFromKnownLastError(), CurrentUserSid >= 0) )
    {
      CurrentUserSid = StringCchPrintfW(
                         SubKey,
                         0x104u,
                         L"%s\\%s\\%s\\%s",
                         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SystemProtectedUserData",
                         StringSid,
                         L"AnyoneRead",
                         L"Colors");
      if ( CurrentUserSid >= 0 )
      {
        v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, a2);
        CurrentUserSid = v4;
        if ( v4 > 0 )
          CurrentUserSid = (unsigned __int16)v4 | 0x80070000;
      }
      LocalFree(StringSid);
    }
    LocalFree(Sid);
  }
  return (unsigned int)CurrentUserSid;
}

```

## disassembly

```asm
0x140020260  mov     [rsp+arg_0], rbx
0x140020265  push    rdi
0x140020266  sub     rsp, 270h
0x14002026d  mov     rax, cs:__security_cookie
0x140020274  xor     rax, rsp
0x140020277  mov     [rsp+278h+var_18], rax
0x14002027f  lea     rcx, [rsp+278h+Sid]; void **
0x140020284  mov     qword ptr [rdx], 0
0x14002028b  mov     rdi, rdx
0x14002028e  mov     [rsp+278h+Sid], 0
0x140020297  call    ?GetCurrentUserSid@@YAJPEAPEAX@Z; GetCurrentUserSid(void * *)
0x14002029c  mov     ebx, eax
0x14002029e  test    eax, eax
0x1400202a0  js      loc_140020369
0x1400202a6  mov     rcx, [rsp+278h+Sid]; Sid
0x1400202ab  lea     rdx, [rsp+278h+StringSid]; StringSid
0x1400202b0  mov     [rsp+278h+StringSid], 0
0x1400202b9  call    cs:__imp_ConvertSidToStringSidW
0x1400202c0  nop     dword ptr [rax+rax+00h]
0x1400202c5  test    eax, eax
0x1400202c7  jz      loc_14002038D
0x1400202cd  mov     rcx, [rsp+278h+StringSid]
0x1400202d2  lea     rax, aColors; "Colors"
0x1400202d9  mov     [rsp+278h+var_248], rax
0x1400202de  lea     r9, aSoftwareMicros_37; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400202e5  mov     rax, cs:off_1401DB440; "AnyoneRead"
0x1400202ec  lea     r8, aSSSS_0; "%s\\%s\\%s\\%s"
0x1400202f3  mov     [rsp+278h+var_250], rax
0x1400202f8  mov     edx, 104h; unsigned __int64
0x1400202fd  mov     [rsp+278h+phkResult], rcx
0x140020302  lea     rcx, [rsp+278h+SubKey]; unsigned __int16 *
0x140020307  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002030c  mov     ebx, eax
0x14002030e  test    eax, eax
0x140020310  js      short loc_140020347
0x140020312  mov     r9d, 20019h; samDesired
0x140020318  mov     [rsp+278h+phkResult], rdi; phkResult
0x14002031d  xor     r8d, r8d; ulOptions
0x140020320  lea     rdx, [rsp+278h+SubKey]; lpSubKey
0x140020325  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14002032c  call    cs:__imp_RegOpenKeyExW
0x140020333  nop     dword ptr [rax+rax+00h]
0x140020338  mov     ebx, eax
0x14002033a  test    eax, eax
0x14002033c  jle     short loc_140020347
0x14002033e  movzx   ebx, ax
0x140020341  or      ebx, 80070000h
0x140020347  mov     rcx, [rsp+278h+StringSid]; hMem
0x14002034c  call    cs:__imp_LocalFree
0x140020353  nop     dword ptr [rax+rax+00h]
0x140020358  mov     rcx, [rsp+278h+Sid]; hMem
0x14002035d  call    cs:__imp_LocalFree
0x140020364  nop     dword ptr [rax+rax+00h]
0x140020369  mov     eax, ebx
0x14002036b  mov     rcx, [rsp+278h+var_18]
0x140020373  xor     rcx, rsp; StackCookie
0x140020376  call    __security_check_cookie
0x14002037b  mov     rbx, [rsp+278h+arg_0]
0x140020383  add     rsp, 270h
0x14002038a  pop     rdi
0x14002038b  retn
0x14002038d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x140020392  mov     ebx, eax
0x140020394  test    eax, eax
0x140020396  jns     loc_1400202CD
0x14002039c  jmp     short loc_140020358
```
