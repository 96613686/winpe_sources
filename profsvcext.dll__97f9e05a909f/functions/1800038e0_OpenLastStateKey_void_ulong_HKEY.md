# OpenLastStateKey(void *,ulong,HKEY__ * *)

- ea: `0x1800038e0`
- end: `0x180003b72`
- name: `?OpenLastStateKey@@YAJPEAXKPEAPEAUHKEY__@@@Z`
- size: `658`
- prototype: `int __fastcall(void *, REGSAM, HKEY *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180005b54`

## callees

- `0x1800038e0`
- `0x18000a520`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003a1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003a1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003986`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003986`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003a34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003a34`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003928`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003928`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003adb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003adb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000394d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000394d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall OpenLastStateKey(void *a1, REGSAM a2, HKEY *a3)
{
  __int64 v5; // rax
  bool v6; // zf
  __int64 v7; // rdi
  WCHAR *v8; // rax
  WCHAR *v9; // rbx
  __int64 v10; // r10
  __int64 v11; // rax
  WCHAR *v12; // rcx
  __int64 v13; // r9
  const wchar_t *v14; // r8
  __int64 v15; // rdx
  __int64 v16; // rcx
  WCHAR *v17; // r9
  WCHAR *v18; // rcx
  unsigned int v19; // edi
  LPWSTR v20; // rcx
  int result; // eax
  __int64 v22; // rax
  WCHAR *v23; // rcx
  __int64 v24; // rdx
  LPWSTR v25; // rcx
  __int64 v26; // rdi
  WCHAR *i; // rdx
  WCHAR *v28; // rcx
  LSTATUS v29; // eax
  signed int LastError; // eax
  LPWSTR StringSid; // [rsp+30h] [rbp-88h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-80h] BYREF
  PSID TokenInformation[8]; // [rsp+3Ch] [rbp-7Ch] BYREF

  *a3 = 0;
  ReturnLength = 0;
  if ( GetTokenInformation(a1, TokenUser, TokenInformation, 0x44u, &ReturnLength) )
  {
    StringSid = 0;
    if ( ConvertSidToStringSidW(TokenInformation[0], &StringSid) )
    {
      v5 = -1;
      do
        v6 = StringSid[++v5] == 0;
      while ( !v6 );
      v7 = (unsigned int)(v5 + 58);
      v8 = (WCHAR *)CoTaskMemAlloc(2 * v7);
      v9 = v8;
      if ( v8 )
      {
        *v8 = 0;
        v10 = 2147483646;
        if ( (unsigned __int64)(v7 - 1) > 0x7FFFFFFE )
          goto LABEL_18;
        v11 = (unsigned int)v7;
        v12 = v9;
        do
        {
          if ( !*v12 )
          {
            v13 = (unsigned int)v7 - v11;
            goto LABEL_10;
          }
          ++v12;
          --v11;
        }
        while ( v11 );
        v13 = 0;
LABEL_10:
        if ( !v11 )
          goto LABEL_18;
        v14 = L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList\\";
        v15 = v7 - v13;
        v6 = v7 == v13;
        v16 = 2147483646;
        v17 = &v9[v13];
        if ( !v6 )
        {
          do
          {
            if ( !v16 )
              break;
            if ( !*v14 )
              break;
            *v17++ = *v14++;
            --v16;
            --v15;
          }
          while ( v15 );
        }
        v18 = v17 - 1;
        if ( v15 )
          v18 = v17;
        *v18 = 0;
        if ( !v15 )
          goto LABEL_18;
        v22 = v7;
        v23 = v9;
        do
        {
          if ( !*v23 )
          {
            v24 = v7 - v22;
            goto LABEL_25;
          }
          ++v23;
          --v22;
        }
        while ( v22 );
        v24 = 0;
LABEL_25:
        if ( !v22 )
          goto LABEL_18;
        v25 = StringSid;
        v26 = v7 - v24;
        for ( i = &v9[v24]; v26; --v26 )
        {
          if ( !v10 )
            break;
          if ( !*v25 )
            break;
          *i++ = *v25++;
          --v10;
        }
        v28 = i - 1;
        if ( v26 )
          v28 = i;
        *v28 = 0;
        if ( v26 )
        {
          v29 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v9, 0, a2, a3);
          v19 = v29;
          if ( v29 )
          {
            if ( v29 > 0 )
              v19 = (unsigned __int16)v29 | 0x80070000;
          }
          else
          {
            v19 = 0;
          }
        }
        else
        {
LABEL_18:
          v19 = -2147418113;
        }
      }
      else
      {
        v19 = -2147024882;
      }
      CoTaskMemFree(v9);
    }
    else
    {
      LastError = GetLastError();
      v19 = LastError;
      if ( LastError > 0 )
        v19 = (unsigned __int16)LastError | 0x80070000;
    }
    v20 = StringSid;
    StringSid = 0;
    LocalFree(v20);
    return v19;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x1800038e0  push    rbp
0x1800038e2  push    rsi
0x1800038e3  push    r14
0x1800038e5  sub     rsp, 0A0h
0x1800038ec  mov     rax, cs:__security_cookie
0x1800038f3  xor     rax, rsp
0x1800038f6  mov     [rsp+0B8h+var_38], rax
0x1800038fe  xor     r14d, r14d
0x180003901  lea     rax, [rsp+0B8h+var_80]
0x180003906  mov     [r8], r14
0x180003909  mov     rsi, r8
0x18000390c  mov     ebp, edx
0x18000390e  mov     [rsp+0B8h+var_80], r14d
0x180003913  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x180003918  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x18000391d  mov     r9d, 44h ; 'D'; TokenInformationLength
0x180003923  mov     edx, 1; TokenInformationClass
0x180003928  call    cs:__imp_GetTokenInformation
0x18000392e  test    eax, eax
0x180003930  jz      loc_180003B21
0x180003936  mov     rcx, [rsp+0B8h+TokenInformation]; Sid
0x18000393b  lea     rdx, [rsp+0B8h+StringSid]; StringSid
0x180003940  mov     [rsp+0B8h+var_28], rdi
0x180003948  mov     [rsp+0B8h+StringSid], r14
0x18000394d  call    cs:__imp_ConvertSidToStringSidW
0x180003953  test    eax, eax
0x180003955  jz      loc_180003B03
0x18000395b  mov     rcx, [rsp+0B8h+StringSid]
0x180003960  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180003967  mov     [rsp+0B8h+var_20], rbx
0x18000396f  nop
0x180003970  cmp     [rcx+rax*2+2], r14w
0x180003976  lea     rax, [rax+1]
0x18000397a  jnz     short loc_180003970
0x18000397c  lea     rdi, [rax+3Ah]
0x180003980  mov     edi, edi
0x180003982  lea     rcx, [rdi+rdi]; cb
0x180003986  call    cs:__imp_CoTaskMemAlloc
0x18000398c  mov     rbx, rax
0x18000398f  test    rax, rax
0x180003992  jz      loc_180003B68
0x180003998  mov     [rax], r14w
0x18000399c  mov     r10d, 7FFFFFFEh
0x1800039a2  lea     rax, [rdi-1]
0x1800039a6  cmp     rax, r10
0x1800039a9  ja      short loc_180003A14
0x1800039ab  mov     eax, edi
0x1800039ad  mov     rcx, rbx
0x1800039b0  mov     r9d, edi
0x1800039b3  cmp     [rcx], r14w
0x1800039b7  jnz     loc_180003B3C
0x1800039bd  sub     r9, rax
0x1800039c0  test    rax, rax
0x1800039c3  jz      short loc_180003A14
0x1800039c5  mov     rdx, rdi
0x1800039c8  lea     r8, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800039cf  sub     rdx, r9
0x1800039d2  mov     rcx, r10
0x1800039d5  lea     r9, [rbx+r9*2]
0x1800039d9  jz      short loc_180003A03
0x1800039db  nop     dword ptr [rax+rax+00h]
0x1800039e0  test    rcx, rcx
0x1800039e3  jz      short loc_180003A03
0x1800039e5  movzx   eax, word ptr [r8]
0x1800039e9  test    ax, ax
0x1800039ec  jz      short loc_180003A03
0x1800039ee  mov     [r9], ax
0x1800039f2  add     r8, 2
0x1800039f6  add     r9, 2
0x1800039fa  dec     rcx
0x1800039fd  sub     rdx, 1
0x180003a01  jnz     short loc_1800039E0
0x180003a03  test    rdx, rdx
0x180003a06  lea     rcx, [r9-2]
0x180003a0a  cmovnz  rcx, r9
0x180003a0e  mov     [rcx], r14w
0x180003a12  jnz     short loc_180003A60
0x180003a14  mov     edi, 8000FFFFh
0x180003a19  mov     rcx, rbx; pv
0x180003a1c  call    cs:__imp_CoTaskMemFree
0x180003a22  mov     rbx, [rsp+0B8h+var_20]
0x180003a2a  mov     rcx, [rsp+0B8h+StringSid]; hMem
0x180003a2f  mov     [rsp+0B8h+StringSid], r14
0x180003a34  call    cs:__imp_LocalFree
0x180003a3a  mov     eax, edi
0x180003a3c  mov     rdi, [rsp+0B8h+var_28]
0x180003a44  mov     rcx, [rsp+0B8h+var_38]
0x180003a4c  xor     rcx, rsp; StackCookie
0x180003a4f  call    __security_check_cookie
0x180003a54  add     rsp, 0A0h
0x180003a5b  pop     r14
0x180003a5d  pop     rsi
0x180003a5e  pop     rbp
0x180003a5f  retn
0x180003a60  mov     rax, rdi
0x180003a63  mov     rcx, rbx
0x180003a66  cmp     [rcx], r14w
0x180003a6a  jnz     loc_180003B52
0x180003a70  mov     rdx, rdi
0x180003a73  sub     rdx, rax
0x180003a76  test    rax, rax
0x180003a79  jz      short loc_180003A14
0x180003a7b  mov     rcx, [rsp+0B8h+StringSid]
0x180003a80  sub     rdi, rdx
0x180003a83  lea     rdx, [rbx+rdx*2]
0x180003a87  jz      short loc_180003AB1
0x180003a89  nop     dword ptr [rax+00000000h]
0x180003a90  test    r10, r10
0x180003a93  jz      short loc_180003AB1
0x180003a95  movzx   eax, word ptr [rcx]
0x180003a98  test    ax, ax
0x180003a9b  jz      short loc_180003AB1
0x180003a9d  mov     [rdx], ax
0x180003aa0  add     rcx, 2
0x180003aa4  add     rdx, 2
0x180003aa8  dec     r10
0x180003aab  sub     rdi, 1
0x180003aaf  jnz     short loc_180003A90
0x180003ab1  test    rdi, rdi
0x180003ab4  lea     rcx, [rdx-2]
0x180003ab8  cmovnz  rcx, rdx
0x180003abc  mov     [rcx], r14w
0x180003ac0  jz      loc_180003A14
0x180003ac6  mov     r9d, ebp; samDesired
0x180003ac9  mov     [rsp+0B8h+ReturnLength], rsi; phkResult
0x180003ace  xor     r8d, r8d; ulOptions
0x180003ad1  mov     rdx, rbx; lpSubKey
0x180003ad4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003adb  call    cs:__imp_RegOpenKeyExW
0x180003ae1  mov     edi, eax
0x180003ae3  test    eax, eax
0x180003ae5  jnz     short loc_180003AEF
0x180003ae7  mov     edi, r14d
0x180003aea  jmp     loc_180003A19
0x180003aef  jle     loc_180003A19
0x180003af5  movzx   edi, ax
0x180003af8  or      edi, 80070000h
0x180003afe  jmp     loc_180003A19
0x180003b03  call    cs:__imp_GetLastError
0x180003b09  mov     edi, eax
0x180003b0b  test    eax, eax
0x180003b0d  jle     loc_180003A2A
0x180003b13  movzx   edi, ax
0x180003b16  or      edi, 80070000h
0x180003b1c  jmp     loc_180003A2A
0x180003b21  call    cs:__imp_GetLastError
0x180003b27  test    eax, eax
0x180003b29  jle     loc_180003A44
0x180003b2f  movzx   eax, ax
0x180003b32  or      eax, 80070000h
0x180003b37  jmp     loc_180003A44
0x180003b3c  add     rcx, 2
0x180003b40  sub     rax, 1
0x180003b44  jnz     loc_1800039B3
0x180003b4a  mov     r9, r14
0x180003b4d  jmp     loc_1800039C0
0x180003b52  add     rcx, 2
0x180003b56  sub     rax, 1
0x180003b5a  jnz     loc_180003A66
0x180003b60  mov     rdx, r14
0x180003b63  jmp     loc_180003A76
0x180003b68  mov     edi, 8007000Eh
0x180003b6d  jmp     loc_180003A19
```
