# WxGetTokenAppContainerSID(void *,_SID *,ulong)

- ea: `0x18007773c`
- end: `0x18007781c`
- name: `?WxGetTokenAppContainerSID@@YAJPEAXPEAU_SID@@K@Z`
- size: `224`
- prototype: `int __fastcall(void *, struct _SID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003f3c0`

## callees

- `0x180046ec0`
- `0x18007773c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007778a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800777db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007778a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800777db`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180077780`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180077780`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800777d1`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800777d1`

## pseudocode

```c
int __fastcall WxGetTokenAppContainerSID(void *a1, struct _SID *a2)
{
  int result; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-78h] BYREF
  int v5; // [rsp+34h] [rbp-74h]
  PSID TokenInformation[10]; // [rsp+40h] [rbp-68h] BYREF

  v5 = 0;
  ReturnLength = 76;
  if ( GetTokenInformation(a1, TokenAppContainerSid, TokenInformation, 0x4Cu, &ReturnLength) )
  {
    if ( TokenInformation[0] )
    {
      if ( CopySid(0x44u, a2, TokenInformation[0]) )
      {
        return 0;
      }
      else
      {
        result = GetLastError();
        if ( result > 0 )
          result = (unsigned __int16)result | 0x80070000;
        v5 = 228;
        if ( result >= 0 )
          return -2147418113;
      }
    }
    else
    {
      result = -2147418113;
      v5 = 226;
    }
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    v5 = 224;
    if ( result >= 0 )
      return -2147418113;
  }
  return result;
}

```

## disassembly

```asm
0x18007773c  push    rbx
0x18007773e  sub     rsp, 0A0h
0x180077745  mov     rax, cs:__security_cookie
0x18007774c  xor     rax, rsp
0x18007774f  mov     [rsp+0A8h+var_18], rax
0x180077757  mov     r9d, 4Ch ; 'L'; TokenInformationLength
0x18007775d  mov     [rsp+0A8h+var_74], 0
0x180077765  mov     rbx, rdx
0x180077768  mov     [rsp+0A8h+var_78], r9d
0x18007776d  lea     rax, [rsp+0A8h+var_78]
0x180077772  lea     r8, [rsp+0A8h+TokenInformation]; TokenInformation
0x180077777  mov     [rsp+0A8h+ReturnLength], rax; ReturnLength
0x18007777c  lea     edx, [r9-2Dh]; TokenInformationClass
0x180077780  call    cs:__imp_GetTokenInformation
0x180077786  test    eax, eax
0x180077788  jnz     short loc_1800777B0
0x18007778a  call    cs:__imp_GetLastError
0x180077790  test    eax, eax
0x180077792  jle     short loc_18007779C
0x180077794  movzx   eax, ax
0x180077797  or      eax, 80070000h
0x18007779c  test    eax, eax
0x18007779e  mov     [rsp+0A8h+var_74], 0E0h
0x1800777a6  mov     ecx, 8000FFFFh
0x1800777ab  cmovns  eax, ecx
0x1800777ae  jmp     short loc_180077803
0x1800777b0  mov     r8, [rsp+0A8h+TokenInformation]; pSourceSid
0x1800777b5  test    r8, r8
0x1800777b8  jnz     short loc_1800777C9
0x1800777ba  mov     eax, 8000FFFFh
0x1800777bf  mov     [rsp+0A8h+var_74], 0E2h
0x1800777c7  jmp     short loc_180077803
0x1800777c9  mov     rdx, rbx; pDestinationSid
0x1800777cc  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x1800777d1  call    cs:__imp_CopySid
0x1800777d7  test    eax, eax
0x1800777d9  jnz     short loc_180077801
0x1800777db  call    cs:__imp_GetLastError
0x1800777e1  test    eax, eax
0x1800777e3  jle     short loc_1800777ED
0x1800777e5  movzx   eax, ax
0x1800777e8  or      eax, 80070000h
0x1800777ed  test    eax, eax
0x1800777ef  mov     [rsp+0A8h+var_74], 0E4h
0x1800777f7  mov     ecx, 8000FFFFh
0x1800777fc  cmovns  eax, ecx
0x1800777ff  jmp     short loc_180077803
0x180077801  xor     eax, eax
0x180077803  mov     rcx, [rsp+0A8h+var_18]
0x18007780b  xor     rcx, rsp; StackCookie
0x18007780e  call    __security_check_cookie
0x180077813  add     rsp, 0A0h
0x18007781a  pop     rbx
0x18007781b  retn
```
