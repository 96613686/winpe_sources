# IsWellKnownSid(ushort const *,bool *)

- ea: `0x18000e180`
- end: `0x18000e25e`
- name: `?IsWellKnownSid@@YAJPEBGPEA_N@Z`
- size: `222`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18000cbd8`
- `0x18000e0f0`

## callees

- `0x18000e180`
- `0x180011b78`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e1c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e249`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e1c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e249`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000e1e3`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000e1fb`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000e213`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000e22b`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000e1e3`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000e1fb`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000e213`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000e22b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000e197`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000e197`

## pseudocode

```c
__int64 __fastcall IsWellKnownSid(const unsigned __int16 *a1, bool *a2)
{
  const char *v3; // r9
  unsigned int LastError; // ebx
  BOOL v6; // eax
  PSID v7; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  PSID Sid; // [rsp+40h] [rbp+18h] BYREF

  Sid = 0;
  if ( ConvertStringSidToSidW(a1, &Sid) )
  {
    if ( IsWellKnownSid(Sid, WinLocalSystemSid)
      || IsWellKnownSid(Sid, WinLocalServiceSid)
      || IsWellKnownSid(Sid, WinNetworkServiceSid)
      || (v6 = IsWellKnownSid(Sid, WinSystemLabelSid)) )
    {
      LOBYTE(v6) = 1;
    }
    v7 = Sid;
    *a2 = v6;
    if ( v7 )
      LocalFree(v7);
    return 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x8FF,
                  (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmapi\\src\\omadmapi.cpp",
                  v3);
    if ( Sid )
      LocalFree(Sid);
    return LastError;
  }
}

```

## disassembly

```asm
0x18000e180  push    rbx
0x18000e182  sub     rsp, 20h
0x18000e186  mov     rbx, rdx
0x18000e189  mov     [rsp+28h+Sid], 0
0x18000e192  lea     rdx, [rsp+28h+Sid]; Sid
0x18000e197  call    cs:__imp_ConvertStringSidToSidW
0x18000e19e  nop     dword ptr [rax+rax+00h]
0x18000e1a3  test    eax, eax
0x18000e1a5  jnz     short loc_18000E1D9
0x18000e1a7  mov     rcx, [rsp+28h]; this
0x18000e1ac  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\dm\\omadm\\omadmapi"...
0x18000e1b3  mov     edx, 8FFh; void *
0x18000e1b8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e1bd  mov     rcx, [rsp+28h+Sid]; hMem
0x18000e1c2  mov     ebx, eax
0x18000e1c4  test    rcx, rcx
0x18000e1c7  jz      short loc_18000E1D5
0x18000e1c9  call    cs:__imp_LocalFree
0x18000e1d0  nop     dword ptr [rax+rax+00h]
0x18000e1d5  mov     eax, ebx
0x18000e1d7  jmp     short loc_18000E257
0x18000e1d9  mov     rcx, [rsp+28h+Sid]; pSid
0x18000e1de  mov     edx, 16h; WellKnownSidType
0x18000e1e3  call    cs:__imp_IsWellKnownSid
0x18000e1ea  nop     dword ptr [rax+rax+00h]
0x18000e1ef  test    eax, eax
0x18000e1f1  jnz     short loc_18000E23B
0x18000e1f3  mov     rcx, [rsp+28h+Sid]; pSid
0x18000e1f8  lea     edx, [rax+17h]; WellKnownSidType
0x18000e1fb  call    cs:__imp_IsWellKnownSid
0x18000e202  nop     dword ptr [rax+rax+00h]
0x18000e207  test    eax, eax
0x18000e209  jnz     short loc_18000E23B
0x18000e20b  mov     rcx, [rsp+28h+Sid]; pSid
0x18000e210  lea     edx, [rax+18h]; WellKnownSidType
0x18000e213  call    cs:__imp_IsWellKnownSid
0x18000e21a  nop     dword ptr [rax+rax+00h]
0x18000e21f  test    eax, eax
0x18000e221  jnz     short loc_18000E23B
0x18000e223  mov     rcx, [rsp+28h+Sid]; pSid
0x18000e228  lea     edx, [rax+45h]; WellKnownSidType
0x18000e22b  call    cs:__imp_IsWellKnownSid
0x18000e232  nop     dword ptr [rax+rax+00h]
0x18000e237  test    eax, eax
0x18000e239  jz      short loc_18000E23D
0x18000e23b  mov     al, 1
0x18000e23d  mov     rcx, [rsp+28h+Sid]; hMem
0x18000e242  mov     [rbx], al
0x18000e244  test    rcx, rcx
0x18000e247  jz      short loc_18000E255
0x18000e249  call    cs:__imp_LocalFree
0x18000e250  nop     dword ptr [rax+rax+00h]
0x18000e255  xor     eax, eax
0x18000e257  add     rsp, 20h
0x18000e25b  pop     rbx
0x18000e25c  retn
```
