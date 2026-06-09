# CheckKeyAccessRightInternal

- ea: `0x180008954`
- end: `0x180008a67`
- name: `CheckKeyAccessRightInternal`
- size: `275`
- prototype: `__int64 __fastcall(void *, const WCHAR *, unsigned int, unsigned int, __int64, __int64, LPWSTR *StringSid)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008690`

## callees

- `0x180008858`
- `0x180008954`
- `0x180008a70`
- `0x180008b44`
- `0x180017578`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008a4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008a4e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180008a23`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180008a23`

## pseudocode

```c
__int64 __fastcall CheckKeyAccessRightInternal(
        void *a1,
        const WCHAR *a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        LPWSTR *StringSid)
{
  int UserSid; // eax
  PSID *v12; // rdi
  signed int v13; // ebx
  signed int LastError; // eax
  _BYTE v16[8]; // [rsp+30h] [rbp-58h] BYREF
  HLOCAL hMem[10]; // [rsp+38h] [rbp-50h] BYREF

  hMem[0] = 0;
  v16[0] = 0;
  if ( StringSid )
    *StringSid = 0;
  UserSid = GetUserSid(a1, hMem);
  v12 = (PSID *)hMem[0];
  v13 = UserSid;
  if ( UserSid >= 0 )
  {
    v13 = CanAccessAllKeys(a1, hMem[0], v16);
    if ( v13 >= 0 )
    {
      if ( v16[0] )
        goto LABEL_22;
      if ( (a3 & 2) == 0 && a2 && !(unsigned int)IsParameterSidEqualsUserSidOnToken(*v12, a2) )
      {
        v13 = -2146893808;
        goto LABEL_17;
      }
      v13 = CheckBasedOnAppContainerAccessRight(a1, a4, a3, a5, a6);
      if ( v13 >= 0 )
      {
LABEL_22:
        if ( !StringSid || (a3 & 2) != 0 || ConvertSidToStringSidW(*v12, StringSid) )
        {
          v13 = 0;
        }
        else
        {
          LastError = GetLastError();
          v13 = LastError;
          if ( LastError > 0 )
            v13 = (unsigned __int16)LastError | 0x80070000;
        }
      }
    }
  }
LABEL_17:
  if ( v12 )
    LocalFree(v12);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180008954  push    rbx
0x180008956  push    rbp
0x180008957  push    rsi
0x180008958  push    rdi
0x180008959  push    r12
0x18000895b  push    r13
0x18000895d  push    r14
0x18000895f  push    r15
0x180008961  sub     rsp, 48h
0x180008965  mov     r14, [rsp+88h+StringSid]
0x18000896d  xor     eax, eax
0x18000896f  mov     [rsp+88h+hMem], rax
0x180008974  mov     r13d, r9d
0x180008977  mov     [rsp+88h+var_58], al
0x18000897b  mov     r12d, r8d
0x18000897e  mov     r15, rdx
0x180008981  mov     rbp, rcx
0x180008984  test    r14, r14
0x180008987  jz      short loc_18000898C
0x180008989  mov     [r14], rax
0x18000898c  lea     rdx, [rsp+88h+hMem]
0x180008991  call    GetUserSid
0x180008996  mov     rdi, [rsp+88h+hMem]
0x18000899b  mov     ebx, eax
0x18000899d  test    eax, eax
0x18000899f  js      loc_180008A46
0x1800089a5  lea     r8, [rsp+88h+var_58]
0x1800089aa  mov     rdx, rdi
0x1800089ad  mov     rcx, rbp
0x1800089b0  call    CanAccessAllKeys
0x1800089b5  mov     ebx, eax
0x1800089b7  test    eax, eax
0x1800089b9  js      loc_180008A46
0x1800089bf  mov     esi, r12d
0x1800089c2  and     esi, 2
0x1800089c5  cmp     [rsp+88h+var_58], 0
0x1800089ca  jnz     short loc_180008A14
0x1800089cc  test    esi, esi
0x1800089ce  jnz     short loc_1800089EB
0x1800089d0  test    r15, r15
0x1800089d3  jz      short loc_1800089EB
0x1800089d5  mov     rcx, [rdi]; pSid2
0x1800089d8  mov     rdx, r15; StringSid
0x1800089db  call    IsParameterSidEqualsUserSidOnToken
0x1800089e0  test    eax, eax
0x1800089e2  jnz     short loc_1800089EB
0x1800089e4  mov     ebx, 80090010h
0x1800089e9  jmp     short loc_180008A46
0x1800089eb  mov     rax, [rsp+88h+arg_28]
0x1800089f3  mov     r8d, r12d
0x1800089f6  mov     r9, [rsp+88h+arg_20]
0x1800089fe  mov     edx, r13d
0x180008a01  mov     rcx, rbp
0x180008a04  mov     [rsp+88h+var_68], rax
0x180008a09  call    CheckBasedOnAppContainerAccessRight
0x180008a0e  mov     ebx, eax
0x180008a10  test    eax, eax
0x180008a12  js      short loc_180008A46
0x180008a14  test    r14, r14
0x180008a17  jz      short loc_180008A44
0x180008a19  test    esi, esi
0x180008a1b  jnz     short loc_180008A44
0x180008a1d  mov     rcx, [rdi]; Sid
0x180008a20  mov     rdx, r14; StringSid
0x180008a23  call    cs:__imp_ConvertSidToStringSidW
0x180008a29  test    eax, eax
0x180008a2b  jnz     short loc_180008A44
0x180008a2d  call    cs:__imp_GetLastError
0x180008a33  mov     ebx, eax
0x180008a35  test    eax, eax
0x180008a37  jle     short loc_180008A46
0x180008a39  movzx   ebx, ax
0x180008a3c  or      ebx, 80070000h
0x180008a42  jmp     short loc_180008A46
0x180008a44  xor     ebx, ebx
0x180008a46  test    rdi, rdi
0x180008a49  jz      short loc_180008A54
0x180008a4b  mov     rcx, rdi; hMem
0x180008a4e  call    cs:__imp_LocalFree
0x180008a54  mov     eax, ebx
0x180008a56  add     rsp, 48h
0x180008a5a  pop     r15
0x180008a5c  pop     r14
0x180008a5e  pop     r13
0x180008a60  pop     r12
0x180008a62  pop     rdi
0x180008a63  pop     rsi
0x180008a64  pop     rbp
0x180008a65  pop     rbx
0x180008a66  retn
```
