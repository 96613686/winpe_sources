# DwzIsPhysicallyLoggedOn(int *)

- ea: `0x140020628`
- end: `0x14002073d`
- name: `?DwzIsPhysicallyLoggedOn@@YAJPEAH@Z`
- size: `277`
- prototype: `__int64 __fastcall(PBOOL IsMember)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14004f474`

## callees

- `0x140020420`
- `0x140020628`
- `0x140061c90`

## import_xrefs

- `ADVAPI32!CheckTokenMembership` at `0x1400206e2`
- `ADVAPI32!CheckTokenMembership` at `0x1400206e2`
- `KERNEL32!GetLastError` at `0x1400206f6`
- `KERNEL32!GetLastError` at `0x1400206f6`
- `ntdll!RtlSubAuthoritySid` at `0x1400206c6`
- `ntdll!RtlSubAuthoritySid` at `0x1400206c6`
- `ntdll!RtlNtStatusToDosError` at `0x14002067c`
- `ntdll!RtlNtStatusToDosError` at `0x14002067c`
- `ntdll!RtlInitializeSid` at `0x140020666`
- `ntdll!RtlInitializeSid` at `0x140020666`

## pseudocode

```c
__int64 __fastcall DwzIsPhysicallyLoggedOn(PBOOL IsMember)
{
  int v2; // eax
  signed int v3; // ebx
  signed int v4; // eax
  signed int LastError; // eax
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+30h] [rbp-78h] BYREF
  _BYTE Sid[80]; // [rsp+40h] [rbp-68h] BYREF

  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 512;
  v2 = RtlInitializeSid(Sid, &IdentifierAuthority, 1u);
  if ( v2 < 0 )
  {
    v4 = RtlNtStatusToDosError(v2);
    v3 = v4;
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
  }
  else
  {
    v3 = 0;
  }
  if ( v3 >= 0 )
  {
    *RtlSubAuthoritySid(Sid, 0) = 1;
    if ( CheckTokenMembership(0, Sid, IsMember) )
    {
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( v3 < 0 )
      {
        v3 = 0;
        *IsMember = 0;
      }
    }
  }
  else
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzIsPhysicallyLoggedOn", 1823, v3);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140020628  mov     [rsp+arg_8], rbx
0x14002062d  push    rdi
0x14002062e  sub     rsp, 0A0h
0x140020635  mov     rax, cs:__security_cookie
0x14002063c  xor     rax, rsp
0x14002063f  mov     [rsp+0A8h+var_18], rax
0x140020647  mov     rdi, rcx
0x14002064a  mov     dword ptr [rsp+0A8h+IdentifierAuthority.Value], 0
0x140020652  lea     rcx, [rsp+0A8h+Sid]; Sid
0x140020657  mov     word ptr [rsp+0A8h+IdentifierAuthority.Value+4], 200h
0x14002065e  mov     r8b, 1; SubAuthorityCount
0x140020661  lea     rdx, [rsp+0A8h+IdentifierAuthority]; IdentifierAuthority
0x140020666  call    cs:__imp_RtlInitializeSid
0x14002066d  nop     dword ptr [rax+rax+00h]
0x140020672  test    eax, eax
0x140020674  js      short loc_14002067A
0x140020676  xor     ebx, ebx
0x140020678  jmp     short loc_140020697
0x14002067a  mov     ecx, eax; Status
0x14002067c  call    cs:__imp_RtlNtStatusToDosError
0x140020683  nop     dword ptr [rax+rax+00h]
0x140020688  mov     ebx, eax
0x14002068a  test    eax, eax
0x14002068c  jle     short loc_140020697
0x14002068e  movzx   ebx, ax
0x140020691  or      ebx, 80070000h
0x140020697  test    ebx, ebx
0x140020699  jns     short loc_1400206BF
0x14002069b  mov     r9d, 71Fh
0x1400206a1  mov     [rsp+0A8h+var_88], ebx
0x1400206a5  lea     r8, aDwzisphysicall; "DwzIsPhysicallyLoggedOn"
0x1400206ac  mov     ecx, 1; Level
0x1400206b1  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400206b8  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400206bd  jmp     short loc_140020719
0x1400206bf  xor     edx, edx; SubAuthority
0x1400206c1  lea     rcx, [rsp+0A8h+Sid]; Sid
0x1400206c6  call    cs:__imp_RtlSubAuthoritySid
0x1400206cd  nop     dword ptr [rax+rax+00h]
0x1400206d2  mov     r8, rdi; IsMember
0x1400206d5  lea     rdx, [rsp+0A8h+Sid]; SidToCheck
0x1400206da  xor     ecx, ecx; TokenHandle
0x1400206dc  mov     dword ptr [rax], 1
0x1400206e2  call    cs:__imp_CheckTokenMembership
0x1400206e9  nop     dword ptr [rax+rax+00h]
0x1400206ee  test    eax, eax
0x1400206f0  jz      short loc_1400206F6
0x1400206f2  xor     ebx, ebx
0x1400206f4  jmp     short loc_140020719
0x1400206f6  call    cs:__imp_GetLastError
0x1400206fd  nop     dword ptr [rax+rax+00h]
0x140020702  mov     ebx, eax
0x140020704  test    eax, eax
0x140020706  jle     short loc_140020711
0x140020708  movzx   ebx, ax
0x14002070b  or      ebx, 80070000h
0x140020711  test    ebx, ebx
0x140020713  jns     short loc_140020719
0x140020715  xor     ebx, ebx
0x140020717  mov     [rdi], ebx
0x140020719  mov     eax, ebx
0x14002071b  mov     rcx, [rsp+0A8h+var_18]
0x140020723  xor     rcx, rsp; StackCookie
0x140020726  call    __security_check_cookie
0x14002072b  mov     rbx, [rsp+0A8h+arg_8]
0x140020733  add     rsp, 0A0h
0x14002073a  pop     rdi
0x14002073b  retn
```
