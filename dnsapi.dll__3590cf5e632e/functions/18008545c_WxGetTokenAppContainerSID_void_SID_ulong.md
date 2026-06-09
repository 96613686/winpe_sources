# WxGetTokenAppContainerSID(void *,_SID *,ulong)

- ea: `0x18008545c`
- end: `0x180085555`
- name: `?WxGetTokenAppContainerSID@@YAJPEAXPEAU_SID@@K@Z`
- size: `249`
- prototype: `int(void *, struct _SID *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800c9f20`

## callees

- `0x18008545c`
- `0x18008b5f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800854b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008550d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800854b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008550d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800854a0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800854a0`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800854fd`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800854fd`

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
0x18008545c  push    rbx
0x18008545e  sub     rsp, 0A0h
0x180085465  mov     rax, cs:__security_cookie
0x18008546c  xor     rax, rsp
0x18008546f  mov     [rsp+0A8h+var_18], rax
0x180085477  mov     r9d, 4Ch ; 'L'; TokenInformationLength
0x18008547d  mov     [rsp+0A8h+var_74], 0
0x180085485  mov     rbx, rdx
0x180085488  mov     [rsp+0A8h+var_78], r9d
0x18008548d  lea     rax, [rsp+0A8h+var_78]
0x180085492  lea     r8, [rsp+0A8h+TokenInformation]; TokenInformation
0x180085497  mov     [rsp+0A8h+ReturnLength], rax; ReturnLength
0x18008549c  lea     edx, [r9-2Dh]; TokenInformationClass
0x1800854a0  call    cs:__imp_GetTokenInformation
0x1800854a7  nop     dword ptr [rax+rax+00h]
0x1800854ac  test    eax, eax
0x1800854ae  jnz     short loc_1800854DC
0x1800854b0  call    cs:__imp_GetLastError
0x1800854b7  nop     dword ptr [rax+rax+00h]
0x1800854bc  test    eax, eax
0x1800854be  jle     short loc_1800854C8
0x1800854c0  movzx   eax, ax
0x1800854c3  or      eax, 80070000h
0x1800854c8  test    eax, eax
0x1800854ca  mov     [rsp+0A8h+var_74], 0E0h
0x1800854d2  mov     ecx, 8000FFFFh
0x1800854d7  cmovns  eax, ecx
0x1800854da  jmp     short loc_18008553B
0x1800854dc  mov     r8, [rsp+0A8h+TokenInformation]; pSourceSid
0x1800854e1  test    r8, r8
0x1800854e4  jnz     short loc_1800854F5
0x1800854e6  mov     eax, 8000FFFFh
0x1800854eb  mov     [rsp+0A8h+var_74], 0E2h
0x1800854f3  jmp     short loc_18008553B
0x1800854f5  mov     rdx, rbx; pDestinationSid
0x1800854f8  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x1800854fd  call    cs:__imp_CopySid
0x180085504  nop     dword ptr [rax+rax+00h]
0x180085509  test    eax, eax
0x18008550b  jnz     short loc_180085539
0x18008550d  call    cs:__imp_GetLastError
0x180085514  nop     dword ptr [rax+rax+00h]
0x180085519  test    eax, eax
0x18008551b  jle     short loc_180085525
0x18008551d  movzx   eax, ax
0x180085520  or      eax, 80070000h
0x180085525  test    eax, eax
0x180085527  mov     [rsp+0A8h+var_74], 0E4h
0x18008552f  mov     ecx, 8000FFFFh
0x180085534  cmovns  eax, ecx
0x180085537  jmp     short loc_18008553B
0x180085539  xor     eax, eax
0x18008553b  mov     rcx, [rsp+0A8h+var_18]
0x180085543  xor     rcx, rsp; StackCookie
0x180085546  call    __security_check_cookie
0x18008554b  add     rsp, 0A0h
0x180085552  pop     rbx
0x180085553  retn
```
