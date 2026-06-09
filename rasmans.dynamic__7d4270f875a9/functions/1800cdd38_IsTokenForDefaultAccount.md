# IsTokenForDefaultAccount

- ea: `0x1800cdd38`
- end: `0x1800cde98`
- name: `IsTokenForDefaultAccount`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800dacd8`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x1800cdd38`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cddb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cde02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cddb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cde02`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800cdda7`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800cdda7`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x1800cddf2`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x1800cddf2`

## pseudocode

```c
__int64 __fastcall IsTokenForDefaultAccount(__int64 a1)
{
  DWORD LastError; // eax
  int v3; // ebx
  struct _LIST_ENTRY *v4; // rcx
  __int64 v5; // rdx
  unsigned int v7; // [rsp+20h] [rbp-78h] BYREF
  DWORD cbSid[3]; // [rsp+24h] [rbp-74h] BYREF
  _BYTE pSid[80]; // [rsp+30h] [rbp-68h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 373, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
  cbSid[0] = 68;
  v7 = 0;
  if ( CreateWellKnownSid(WinAccountProtectedUsersSid|WinCreatorGroupSid, 0, pSid, cbSid) )
  {
    if ( (unsigned int)CheckTokenMembershipEx(a1, pSid, 0, &v7) )
      return v7;
    LastError = GetLastError();
    v3 = LastError;
    if ( !LastError )
      goto LABEL_15;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      v5 = 375;
      goto LABEL_14;
    }
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( !LastError )
    {
LABEL_15:
      v4 = WPP_GLOBAL_Control;
      goto LABEL_16;
    }
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      v5 = 374;
LABEL_14:
      WPP_SF_d(v4[1].Flink, v5, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, LastError);
      goto LABEL_15;
    }
  }
LABEL_16:
  v7 = 0;
  if ( v3 < 0 && v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v4[1].Blink) & 8) != 0 )
    WPP_SF_d(v4[1].Flink, 376, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, (unsigned int)v3);
  return v7;
}

```

## disassembly

```asm
0x1800cdd38  mov     [rsp+arg_8], rbx
0x1800cdd3d  push    rdi
0x1800cdd3e  sub     rsp, 90h
0x1800cdd45  mov     rax, cs:__security_cookie
0x1800cdd4c  xor     rax, rsp
0x1800cdd4f  mov     [rsp+98h+var_18], rax
0x1800cdd57  mov     rbx, rcx
0x1800cdd5a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cdd61  lea     rdi, WPP_GLOBAL_Control
0x1800cdd68  cmp     rcx, rdi
0x1800cdd6b  jz      short loc_1800CDD88
0x1800cdd6d  test    byte ptr [rcx+1Ch], 8
0x1800cdd71  jz      short loc_1800CDD88
0x1800cdd73  mov     rcx, [rcx+10h]
0x1800cdd77  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800cdd7e  mov     edx, 175h
0x1800cdd83  call    WPP_SF_
0x1800cdd88  xor     edx, edx; DomainSid
0x1800cdd8a  mov     [rsp+98h+cbSid], 44h ; 'D'
0x1800cdd92  lea     r9, [rsp+98h+cbSid]; cbSid
0x1800cdd97  mov     [rsp+98h+var_78], 0
0x1800cdd9f  lea     r8, [rsp+98h+pSid]; pSid
0x1800cdda4  lea     ecx, [rdx+6Fh]; WellKnownSidType
0x1800cdda7  call    cs:__imp_CreateWellKnownSid
0x1800cddae  nop     dword ptr [rax+rax+00h]
0x1800cddb3  test    eax, eax
0x1800cddb5  jnz     short loc_1800CDDE2
0x1800cddb7  call    cs:__imp_GetLastError
0x1800cddbe  nop     dword ptr [rax+rax+00h]
0x1800cddc3  mov     ebx, eax
0x1800cddc5  test    eax, eax
0x1800cddc7  jz      short loc_1800CDE3E
0x1800cddc9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cddd0  cmp     rcx, rdi
0x1800cddd3  jz      short loc_1800CDE45
0x1800cddd5  test    byte ptr [rcx+1Ch], 1
0x1800cddd9  jz      short loc_1800CDE45
0x1800cdddb  mov     edx, 176h
0x1800cdde0  jmp     short loc_1800CDE2B
0x1800cdde2  lea     r9, [rsp+98h+var_78]
0x1800cdde7  xor     r8d, r8d
0x1800cddea  lea     rdx, [rsp+98h+pSid]
0x1800cddef  mov     rcx, rbx
0x1800cddf2  call    cs:__imp_CheckTokenMembershipEx
0x1800cddf9  nop     dword ptr [rax+rax+00h]
0x1800cddfe  test    eax, eax
0x1800cde00  jnz     short loc_1800CDE72
0x1800cde02  call    cs:__imp_GetLastError
0x1800cde09  nop     dword ptr [rax+rax+00h]
0x1800cde0e  mov     ebx, eax
0x1800cde10  test    eax, eax
0x1800cde12  jz      short loc_1800CDE3E
0x1800cde14  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cde1b  cmp     rcx, rdi
0x1800cde1e  jz      short loc_1800CDE45
0x1800cde20  test    byte ptr [rcx+1Ch], 1
0x1800cde24  jz      short loc_1800CDE45
0x1800cde26  mov     edx, 177h
0x1800cde2b  mov     rcx, [rcx+10h]
0x1800cde2f  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800cde36  mov     r9d, eax
0x1800cde39  call    WPP_SF_d
0x1800cde3e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cde45  xor     eax, eax
0x1800cde47  mov     [rsp+98h+var_78], eax
0x1800cde4b  test    ebx, ebx
0x1800cde4d  jns     short loc_1800CDE72
0x1800cde4f  cmp     rcx, rdi
0x1800cde52  jz      short loc_1800CDE72
0x1800cde54  test    byte ptr [rcx+1Ch], 8
0x1800cde58  jz      short loc_1800CDE72
0x1800cde5a  mov     rcx, [rcx+10h]
0x1800cde5e  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800cde65  mov     edx, 178h
0x1800cde6a  mov     r9d, ebx
0x1800cde6d  call    WPP_SF_d
0x1800cde72  mov     eax, [rsp+98h+var_78]
0x1800cde76  mov     rcx, [rsp+98h+var_18]
0x1800cde7e  xor     rcx, rsp; StackCookie
0x1800cde81  call    __security_check_cookie
0x1800cde86  mov     rbx, [rsp+98h+arg_8]
0x1800cde8e  add     rsp, 90h
0x1800cde95  pop     rdi
0x1800cde96  retn
```
