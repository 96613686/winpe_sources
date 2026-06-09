# PrintSid

- ea: `0x18007d204`
- end: `0x18007d42d`
- name: `PrintSid`
- size: `553`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18007c778`
- `0x18007cec0`
- `0x18007d8c4`

## callees

- `0x18000f35c`
- `0x180011578`
- `0x1800259d4`
- `0x18004bb50`
- `0x18007d204`
- `0x18007d978`
- `0x1800d6ea0`

## import_xrefs

- `ADVAPI32!LookupAccountSidW` at `0x18007d2d7`
- `ADVAPI32!LookupAccountSidW` at `0x18007d2d7`
- `ADVAPI32!ConvertSidToStringSidW` at `0x18007d23e`
- `ADVAPI32!ConvertSidToStringSidW` at `0x18007d23e`
- `KERNEL32!GetLastError` at `0x18007d248`
- `KERNEL32!GetLastError` at `0x18007d2e5`
- `KERNEL32!GetLastError` at `0x18007d248`
- `KERNEL32!GetLastError` at `0x18007d2e5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PrintSid(PSID Sid)
{
  DWORD v2; // eax
  DWORD LastError; // edi
  PVOID *v4; // rcx
  LPWSTR StringSid; // [rsp+40h] [rbp-C0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchReferencedDomainName; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD cchName; // [rsp+50h] [rbp-B0h] BYREF
  LPWSTR v9; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Name[128]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ReferencedDomainName[128]; // [rsp+160h] [rbp+60h] BYREF

  StringSid = 0;
  if ( ConvertSidToStringSidW(Sid, &StringSid) )
  {
    v9 = StringSid;
    cchName = 128;
    cchReferencedDomainName = 128;
    peUse = 0;
    if ( LookupAccountSidW(0, Sid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
    {
      if ( ReferencedDomainName[0] )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
          WPP_SF_SSS(
            *((_QWORD *)WPP_GLOBAL_Control + 32),
            23,
            &WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids,
            StringSid,
            ReferencedDomainName,
            Name);
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
      {
        WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 32), Name);
      }
    }
    else
    {
      LastError = GetLastError();
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 32));
          v4 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 268) & 1) != 0 )
          WPP_SF_d(v4[32], 21, &WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids, LastError);
      }
    }
    CAutoLocalFreePtr::~CAutoLocalFreePtr((CAutoLocalFreePtr *)&v9);
  }
  else
  {
    v2 = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 19, &WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids, v2);
  }
}

```

## disassembly

```asm
0x18007d204  mov     [rsp-8+arg_8], rbx
0x18007d209  mov     [rsp-8+arg_10], rdi
0x18007d20e  push    rbp
0x18007d20f  lea     rbp, [rsp-170h]
0x18007d217  sub     rsp, 270h
0x18007d21e  mov     rax, cs:__security_cookie
0x18007d225  xor     rax, rsp
0x18007d228  mov     [rbp+170h+var_10], rax
0x18007d22f  mov     rbx, rcx
0x18007d232  xor     edi, edi
0x18007d234  mov     [rsp+270h+StringSid], rdi
0x18007d239  lea     rdx, [rsp+270h+StringSid]; StringSid
0x18007d23e  call    cs:__imp_ConvertSidToStringSidW
0x18007d244  test    eax, eax
0x18007d246  jnz     short loc_18007D290
0x18007d248  call    cs:__imp_GetLastError
0x18007d24e  lea     rbx, WPP_GLOBAL_Control
0x18007d255  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d25c  cmp     rcx, rbx
0x18007d25f  jz      loc_18007D409
0x18007d265  test    byte ptr [rcx+10Ch], 1
0x18007d26c  jz      loc_18007D409
0x18007d272  lea     edx, [rdi+13h]
0x18007d275  mov     r9d, eax
0x18007d278  lea     r8, WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids
0x18007d27f  mov     rcx, [rcx+100h]
0x18007d286  call    WPP_SF_d
0x18007d28b  jmp     loc_18007D409
0x18007d290  mov     rax, [rsp+270h+StringSid]
0x18007d295  mov     [rsp+270h+var_218], rax
0x18007d29a  mov     eax, 80h
0x18007d29f  mov     [rsp+270h+cchName], eax
0x18007d2a3  mov     [rsp+270h+var_224], eax
0x18007d2a7  mov     [rsp+270h+var_228], edi
0x18007d2ab  lea     rax, [rsp+270h+var_228]
0x18007d2b0  mov     [rsp+270h+peUse], rax; peUse
0x18007d2b5  lea     rax, [rsp+270h+var_224]
0x18007d2ba  mov     [rsp+270h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18007d2bf  lea     rax, [rbp+170h+var_110]
0x18007d2c3  mov     [rsp+270h+ReferencedDomainName], rax; ReferencedDomainName
0x18007d2c8  lea     r9, [rsp+270h+cchName]; cchName
0x18007d2cd  lea     r8, [rsp+270h+Name]; Name
0x18007d2d2  mov     rdx, rbx; Sid
0x18007d2d5  xor     ecx, ecx; lpSystemName
0x18007d2d7  call    cs:__imp_LookupAccountSidW
0x18007d2dd  test    eax, eax
0x18007d2df  jnz     loc_18007D367
0x18007d2e5  call    cs:__imp_GetLastError
0x18007d2eb  mov     edi, eax
0x18007d2ed  lea     rbx, WPP_GLOBAL_Control
0x18007d2f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d2fb  cmp     rcx, rbx
0x18007d2fe  jz      loc_18007D3FF
0x18007d304  test    byte ptr [rcx+10Ch], 4
0x18007d30b  jz      short loc_18007D331
0x18007d30d  mov     edx, 14h
0x18007d312  mov     r9, [rsp+270h+StringSid]
0x18007d317  lea     r8, WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids
0x18007d31e  mov     rcx, [rcx+100h]; LoggerHandle
0x18007d325  call    WPP_SF_S
0x18007d32a  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d331  cmp     rcx, rbx
0x18007d334  jz      loc_18007D3FF
0x18007d33a  test    byte ptr [rcx+10Ch], 1
0x18007d341  jz      loc_18007D3FF
0x18007d347  mov     edx, 15h
0x18007d34c  mov     r9d, edi
0x18007d34f  lea     r8, WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids
0x18007d356  mov     rcx, [rcx+100h]
0x18007d35d  call    WPP_SF_d
0x18007d362  jmp     loc_18007D3FF
0x18007d367  cmp     [rbp+170h+var_110], di
0x18007d36b  jnz     short loc_18007D3B2
0x18007d36d  lea     rbx, WPP_GLOBAL_Control
0x18007d374  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d37b  cmp     rcx, rbx
0x18007d37e  jz      short loc_18007D3FF
0x18007d380  test    byte ptr [rcx+10Ch], 4
0x18007d387  jz      short loc_18007D3FF
0x18007d389  mov     edx, 16h
0x18007d38e  lea     rax, [rsp+270h+Name]
0x18007d393  mov     [rsp+270h+ReferencedDomainName], rax; wchar_t *
0x18007d398  mov     r9, [rsp+270h+StringSid]
0x18007d39d  lea     r8, WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids
0x18007d3a4  mov     rcx, [rcx+100h]; LoggerHandle
0x18007d3ab  call    WPP_SF_SS
0x18007d3b0  jmp     short loc_18007D3FF
0x18007d3b2  lea     rbx, WPP_GLOBAL_Control
0x18007d3b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d3c0  cmp     rcx, rbx
0x18007d3c3  jz      short loc_18007D3FF
0x18007d3c5  test    byte ptr [rcx+10Ch], 4
0x18007d3cc  jz      short loc_18007D3FF
0x18007d3ce  mov     edx, 17h
0x18007d3d3  lea     rax, [rsp+270h+Name]
0x18007d3d8  mov     [rsp+270h+cchReferencedDomainName], rax
0x18007d3dd  lea     rax, [rbp+170h+var_110]
0x18007d3e1  mov     [rsp+270h+ReferencedDomainName], rax
0x18007d3e6  mov     r9, [rsp+270h+StringSid]
0x18007d3eb  lea     r8, WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids
0x18007d3f2  mov     rcx, [rcx+100h]
0x18007d3f9  call    WPP_SF_SSS
0x18007d3fe  nop
0x18007d3ff  lea     rcx, [rsp+270h+var_218]; this
0x18007d404  call    ??1CAutoLocalFreePtr@@QEAA@XZ; CAutoLocalFreePtr::~CAutoLocalFreePtr(void)
0x18007d409  mov     rcx, [rbp+170h+var_10]
0x18007d410  xor     rcx, rsp; StackCookie
0x18007d413  call    __security_check_cookie
0x18007d418  lea     r11, [rsp+270h+var_s0]
0x18007d420  mov     rbx, [r11+18h]
0x18007d424  mov     rdi, [r11+20h]
0x18007d428  mov     rsp, r11
0x18007d42b  pop     rbp
0x18007d42c  retn
```
