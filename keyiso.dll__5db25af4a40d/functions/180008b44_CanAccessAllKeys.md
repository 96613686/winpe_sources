# CanAccessAllKeys

- ea: `0x180008b44`
- end: `0x180008be9`
- name: `CanAccessAllKeys`
- size: `165`
- prototype: `__int64 __fastcall(__int64, PSID *, _BYTE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180008954`

## callees

- `0x180008b44`
- `0x180008bf0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180008bcc`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180008bcc`
- `ntdll!RtlIsMultiSessionSku` at `0x180008b81`
- `ntdll!RtlIsMultiSessionSku` at `0x180008b81`
- `ntdll!RtlNtStatusToDosError` at `0x180008ba6`
- `ntdll!RtlNtStatusToDosError` at `0x180008ba6`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180008b9a`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180008b9a`

## pseudocode

```c
__int64 __fastcall CanAccessAllKeys(__int64 a1, PSID *a2, _BYTE *a3)
{
  unsigned int v6; // ebx
  NTSTATUS v7; // eax
  signed int v8; // eax
  bool v9; // zf
  char v11; // [rsp+50h] [rbp+18h] BYREF
  int v12; // [rsp+58h] [rbp+20h] BYREF

  v11 = 0;
  v12 = 1;
  *a3 = 0;
  v6 = IsAppContainer(a1, &v12);
  if ( (v6 & 0x80000000) != 0 )
    return v6;
  if ( v12 )
  {
    if ( (unsigned __int8)RtlIsMultiSessionSku() )
      return v6;
    v7 = CapabilityCheck(a1, L"userSigninSupport", &v11);
    if ( v7 )
    {
      v8 = RtlNtStatusToDosError(v7);
      v6 = v8;
      if ( v8 > 0 )
        return (unsigned __int16)v8 | 0x80070000;
      return v6;
    }
    v9 = v11 == 0;
  }
  else
  {
    v9 = !IsWellKnownSid(*a2, WinLocalSystemSid);
  }
  if ( !v9 )
    *a3 = 1;
  return v6;
}

```

## disassembly

```asm
0x180008b44  mov     rax, rsp
0x180008b47  mov     [rax+8], rbx
0x180008b4b  push    rsi
0x180008b4c  push    rdi
0x180008b4d  push    r14
0x180008b4f  sub     rsp, 20h
0x180008b53  mov     r14, rdx
0x180008b56  mov     byte ptr [rax+18h], 0
0x180008b5a  lea     rdx, [rax+20h]
0x180008b5e  mov     dword ptr [rax+20h], 1
0x180008b65  mov     rdi, r8
0x180008b68  mov     byte ptr [r8], 0
0x180008b6c  mov     rsi, rcx
0x180008b6f  call    IsAppContainer
0x180008b74  mov     ebx, eax
0x180008b76  test    eax, eax
0x180008b78  js      short loc_180008BD9
0x180008b7a  cmp     [rsp+38h+arg_18], 0
0x180008b7f  jz      short loc_180008BC4
0x180008b81  call    cs:__imp_RtlIsMultiSessionSku
0x180008b87  test    al, al
0x180008b89  jnz     short loc_180008BD9
0x180008b8b  lea     r8, [rsp+38h+arg_10]
0x180008b90  mov     rcx, rsi
0x180008b93  lea     rdx, aUsersigninsupp; "userSigninSupport"
0x180008b9a  call    cs:__imp_CapabilityCheck
0x180008ba0  test    eax, eax
0x180008ba2  jz      short loc_180008BBD
0x180008ba4  mov     ecx, eax; Status
0x180008ba6  call    cs:__imp_RtlNtStatusToDosError
0x180008bac  mov     ebx, eax
0x180008bae  test    eax, eax
0x180008bb0  jle     short loc_180008BD9
0x180008bb2  movzx   ebx, ax
0x180008bb5  or      ebx, 80070000h
0x180008bbb  jmp     short loc_180008BD9
0x180008bbd  cmp     [rsp+38h+arg_10], 0
0x180008bc2  jmp     short loc_180008BD4
0x180008bc4  mov     rcx, [r14]; pSid
0x180008bc7  mov     edx, 16h; WellKnownSidType
0x180008bcc  call    cs:__imp_IsWellKnownSid
0x180008bd2  test    eax, eax
0x180008bd4  jz      short loc_180008BD9
0x180008bd6  mov     byte ptr [rdi], 1
0x180008bd9  mov     eax, ebx
0x180008bdb  mov     rbx, [rsp+38h+arg_0]
0x180008be0  add     rsp, 20h
0x180008be4  pop     r14
0x180008be6  pop     rdi
0x180008be7  pop     rsi
0x180008be8  retn
```
