# RDVIsInWellKnownGroup

- ea: `0x18001cb54`
- end: `0x18001cc85`
- name: `RDVIsInWellKnownGroup`
- size: `305`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b740`

## callees

- `0x18001cb54`
- `0x18004b460`
- `0x180092b40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cc03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cc3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cc03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cc3e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001cbcc`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001cbcc`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001cbb5`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001cbb5`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001cbda`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001cbda`

## pseudocode

```c
bool RDVIsInWellKnownGroup()
{
  DWORD v1; // eax
  __int64 v2; // r8
  DWORD LastError; // eax
  __int64 v4; // r8
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  IsMember = AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x241u, 0, 0, 0, 0, 0, 0, &SidToCheck);
  if ( IsMember )
  {
    if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
    {
      IsMember = 0;
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v4, LastError);
      }
    }
    FreeSid(SidToCheck);
  }
  else
  {
    v1 = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v2, v1);
    }
  }
  return IsMember != 0;
}

```

## disassembly

```asm
0x18001cb54  mov     [rsp-8+arg_0], rbx
0x18001cb59  push    rbp
0x18001cb5a  mov     rbp, rsp
0x18001cb5d  sub     rsp, 80h
0x18001cb64  mov     rax, cs:__security_cookie
0x18001cb6b  xor     rax, rsp
0x18001cb6e  mov     [rbp+var_8], rax
0x18001cb72  xor     ebx, ebx
0x18001cb74  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x18001cb7a  lea     rax, [rbp+SidToCheck]
0x18001cb7e  mov     [rbp+IsMember], ebx
0x18001cb81  mov     [rsp+80h+pSid], rax; pSid
0x18001cb86  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x18001cb8a  mov     [rsp+80h+nSubAuthority7], ebx; nSubAuthority7
0x18001cb8e  mov     r9d, 241h; nSubAuthority1
0x18001cb94  mov     [rsp+80h+nSubAuthority6], ebx; nSubAuthority6
0x18001cb98  lea     r8d, [rbx+20h]; nSubAuthority0
0x18001cb9c  mov     [rsp+80h+nSubAuthority5], ebx; nSubAuthority5
0x18001cba0  mov     dl, 2; nSubAuthorityCount
0x18001cba2  mov     [rsp+80h+nSubAuthority4], ebx; nSubAuthority4
0x18001cba6  mov     [rsp+80h+nSubAuthority3], ebx; nSubAuthority3
0x18001cbaa  mov     [rsp+80h+nSubAuthority2], ebx; nSubAuthority2
0x18001cbae  mov     dword ptr [rbp+pIdentifierAuthority.Value], ebx
0x18001cbb1  mov     [rbp+SidToCheck], rbx
0x18001cbb5  call    cs:__imp_AllocateAndInitializeSid
0x18001cbbb  mov     [rbp+IsMember], eax
0x18001cbbe  test    eax, eax
0x18001cbc0  jz      short loc_18001CC03
0x18001cbc2  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x18001cbc6  lea     r8, [rbp+IsMember]; IsMember
0x18001cbca  xor     ecx, ecx; TokenHandle
0x18001cbcc  call    cs:__imp_CheckTokenMembership
0x18001cbd2  test    eax, eax
0x18001cbd4  jz      short loc_18001CC3B
0x18001cbd6  mov     rcx, [rbp+SidToCheck]; pSid
0x18001cbda  call    cs:__imp_FreeSid
0x18001cbe0  cmp     [rbp+IsMember], ebx
0x18001cbe3  setnz   al
0x18001cbe6  mov     rcx, [rbp+var_8]
0x18001cbea  xor     rcx, rsp; StackCookie
0x18001cbed  call    __security_check_cookie
0x18001cbf2  mov     rbx, [rsp+80h+arg_0]
0x18001cbfa  add     rsp, 80h
0x18001cc01  pop     rbp
0x18001cc02  retn
0x18001cc03  call    cs:__imp_GetLastError
0x18001cc09  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cc10  lea     rdx, WPP_GLOBAL_Control
0x18001cc17  cmp     rcx, rdx
0x18001cc1a  jz      short loc_18001CBE0
0x18001cc1c  test    byte ptr [rcx+1Ch], 1
0x18001cc20  jz      short loc_18001CBE0
0x18001cc22  cmp     byte ptr [rcx+19h], 2
0x18001cc26  jb      short loc_18001CBE0
0x18001cc28  mov     rcx, [rcx+10h]
0x18001cc2c  mov     edx, 0Bh
0x18001cc31  mov     r9d, eax
0x18001cc34  call    WPP_SF_Dd
0x18001cc39  jmp     short loc_18001CBE0
0x18001cc3b  mov     [rbp+IsMember], ebx
0x18001cc3e  call    cs:__imp_GetLastError
0x18001cc44  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cc4b  lea     rdx, WPP_GLOBAL_Control
0x18001cc52  cmp     rcx, rdx
0x18001cc55  jz      loc_18001CBD6
0x18001cc5b  test    byte ptr [rcx+1Ch], 1
0x18001cc5f  jz      loc_18001CBD6
0x18001cc65  cmp     byte ptr [rcx+19h], 2
0x18001cc69  jb      loc_18001CBD6
0x18001cc6f  mov     rcx, [rcx+10h]
0x18001cc73  mov     edx, 0Ah
0x18001cc78  mov     r9d, eax
0x18001cc7b  call    WPP_SF_Dd
0x18001cc80  jmp     loc_18001CBD6
```
