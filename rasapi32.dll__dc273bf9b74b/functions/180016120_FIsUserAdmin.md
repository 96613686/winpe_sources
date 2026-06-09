# FIsUserAdmin

- ea: `0x180016120`
- end: `0x1800161c7`
- name: `FIsUserAdmin`
- size: `167`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800160ec`
- `0x180077fd0`
- `0x180079500`
- `0x18007c380`
- `0x1800a7f48`

## callees

- `0x18001601c`
- `0x180016120`
- `0x1800161d0`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180016166`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180016166`
- `rtutils!TracePrintfExA` at `0x1800161ba`
- `rtutils!TracePrintfExA` at `0x1800161ba`

## string_xrefs

- `0x1800161ae`: `CheckTokenMemberShip for local system failed.`

## pseudocode

```c
_BOOL8 __fastcall FIsUserAdmin(__int64 a1, void * near **a2, __int64 a3)
{
  WINBOOL v3; // eax
  WINBOOL IsMember; // [rsp+20h] [rbp-20h] BYREF
  _DWORD SidToCheck[4]; // [rsp+28h] [rbp-18h] BYREF

  IsMember = 0;
  SidToCheck[0] = 257;
  SidToCheck[1] = 83886080;
  SidToCheck[2] = 18;
  if ( (unsigned int)RasMobileCore(a1, a2, a3) )
    return 1;
  if ( CheckTokenMembership(0, SidToCheck, &IsMember) )
  {
    v3 = IsMember;
  }
  else
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "CheckTokenMemberShip for local system failed.");
    v3 = 0;
    IsMember = 0;
  }
  return v3 || (unsigned int)FIsUserGroupMember(0x220u) != 0;
}

```

## disassembly

```asm
0x180016120  push    rbp
0x180016122  mov     rbp, rsp
0x180016125  sub     rsp, 40h
0x180016129  mov     rax, cs:__security_cookie
0x180016130  xor     rax, rsp
0x180016133  mov     [rbp+var_8], rax
0x180016137  mov     [rbp+IsMember], 0
0x18001613e  mov     [rbp+SidToCheck], 101h
0x180016145  mov     [rbp+var_14], 5000000h
0x18001614c  mov     [rbp+var_10], 12h
0x180016153  call    RasMobileCore
0x180016158  test    eax, eax
0x18001615a  jnz     short loc_18001619C
0x18001615c  lea     r8, [rbp+IsMember]; IsMember
0x180016160  xor     ecx, ecx; TokenHandle
0x180016162  lea     rdx, [rbp+SidToCheck]; SidToCheck
0x180016166  call    cs:__imp_CheckTokenMembership
0x18001616c  test    eax, eax
0x18001616e  jz      short loc_1800161A3
0x180016170  mov     eax, [rbp+IsMember]
0x180016173  test    eax, eax
0x180016175  jnz     short loc_18001619C
0x180016177  mov     ecx, 220h; nSubAuthority1
0x18001617c  call    FIsUserGroupMember
0x180016181  xor     ecx, ecx
0x180016183  test    eax, eax
0x180016185  setnz   cl
0x180016188  mov     eax, ecx
0x18001618a  mov     rcx, [rbp+var_8]
0x18001618e  xor     rcx, rsp; StackCookie
0x180016191  call    __security_check_cookie
0x180016196  add     rsp, 40h
0x18001619a  pop     rbp
0x18001619b  retn
0x18001619c  mov     eax, 1
0x1800161a1  jmp     short loc_18001618A
0x1800161a3  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800161a9  cmp     ecx, 0FFFFFFFFh
0x1800161ac  jz      short loc_1800161C0
0x1800161ae  lea     r8, aChecktokenmemb; "CheckTokenMemberShip for local system f"...
0x1800161b5  mov     edx, 0Ch; dwFlags
0x1800161ba  call    cs:__imp_TracePrintfExA
0x1800161c0  xor     eax, eax
0x1800161c2  mov     [rbp+IsMember], eax
0x1800161c5  jmp     short loc_180016173
```
