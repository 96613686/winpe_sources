# ComputeService::Client::IsCallerHyperVAdministrator(void)

- ea: `0x18002e5e0`
- end: `0x18002e6d7`
- name: `?IsCallerHyperVAdministrator@Client@ComputeService@@YA_NXZ`
- size: `247`
- prototype: `bool __fastcall(ComputeService::Client *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18009abc3`
- `0x18009ac5f`
- `0x18009ad04`
- `0x18009ad97`

## callees

- `0x1800067c0`
- `0x180009e8c`
- `0x18002e180`
- `0x18002e5e0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e645`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e695`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e645`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e695`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002e622`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002e67a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002e622`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002e67a`

## pseudocode

```c
bool __fastcall ComputeService::Client::IsCallerHyperVAdministrator(ComputeService::Client *this, __int64 a2, void *a3)
{
  char v3; // bl
  bool v4; // di
  void *v5; // r8
  PSID SidToCheck[2]; // [rsp+20h] [rbp-60h] BYREF
  _BYTE v8[32]; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v9[32]; // [rsp+50h] [rbp-30h] BYREF
  WINBOOL IsMember; // [rsp+70h] [rbp-10h] BYREF

  IsMember = 0;
  Vml::VmSid::VmSid((Vml::VmSid *)SidToCheck, WinBuiltinAdministratorsSid, a3);
  v3 = 1;
  v4 = CheckTokenMembership(0, SidToCheck[0], &IsMember) && IsMember;
  if ( SidToCheck[0] )
    LocalFree(SidToCheck[0]);
  std::wstring::~wstring(v9);
  std::wstring::~wstring(v8);
  if ( v4 )
    return 1;
  Vml::VmSid::VmSid((Vml::VmSid *)SidToCheck, WinBuiltinHyperVAdminsSid, v5);
  if ( !CheckTokenMembership(0, SidToCheck[0], &IsMember) || !IsMember )
    v3 = 0;
  if ( SidToCheck[0] )
    LocalFree(SidToCheck[0]);
  std::wstring::~wstring(v9);
  std::wstring::~wstring(v8);
  return v3 != 0;
}

```

## disassembly

```asm
0x18002e5e0  mov     [rsp-8+arg_0], rbx
0x18002e5e5  mov     [rsp-8+arg_8], rdi
0x18002e5ea  push    rbp
0x18002e5eb  mov     rbp, rsp
0x18002e5ee  sub     rsp, 80h
0x18002e5f5  mov     rax, cs:__security_cookie
0x18002e5fc  xor     rax, rsp
0x18002e5ff  mov     [rbp+var_8], rax
0x18002e603  mov     edx, 1Ah; enum WELL_KNOWN_SID_TYPE
0x18002e608  mov     [rbp+IsMember], 0
0x18002e60f  lea     rcx, [rbp+SidToCheck]; this
0x18002e613  call    ??0VmSid@Vml@@QEAA@W4WELL_KNOWN_SID_TYPE@@PEAX@Z; Vml::VmSid::VmSid(WELL_KNOWN_SID_TYPE,void *)
0x18002e618  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x18002e61c  lea     r8, [rbp+IsMember]; IsMember
0x18002e620  xor     ecx, ecx; TokenHandle
0x18002e622  call    cs:__imp_CheckTokenMembership
0x18002e628  mov     bl, 1
0x18002e62a  test    eax, eax
0x18002e62c  jz      short loc_18002E639
0x18002e62e  cmp     [rbp+IsMember], 0
0x18002e632  jz      short loc_18002E639
0x18002e634  mov     dil, bl
0x18002e637  jmp     short loc_18002E63C
0x18002e639  xor     dil, dil
0x18002e63c  mov     rcx, [rbp+SidToCheck]; hMem
0x18002e640  test    rcx, rcx
0x18002e643  jz      short loc_18002E64B
0x18002e645  call    cs:__imp_LocalFree
0x18002e64b  lea     rcx, [rbp+var_30]
0x18002e64f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002e654  lea     rcx, [rbp+var_50]
0x18002e658  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002e65d  test    dil, dil
0x18002e660  jnz     short loc_18002E6B4
0x18002e662  mov     edx, 63h ; 'c'; enum WELL_KNOWN_SID_TYPE
0x18002e667  lea     rcx, [rbp+SidToCheck]; this
0x18002e66b  call    ??0VmSid@Vml@@QEAA@W4WELL_KNOWN_SID_TYPE@@PEAX@Z; Vml::VmSid::VmSid(WELL_KNOWN_SID_TYPE,void *)
0x18002e670  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x18002e674  lea     r8, [rbp+IsMember]; IsMember
0x18002e678  xor     ecx, ecx; TokenHandle
0x18002e67a  call    cs:__imp_CheckTokenMembership
0x18002e680  test    eax, eax
0x18002e682  jz      short loc_18002E68A
0x18002e684  cmp     [rbp+IsMember], 0
0x18002e688  jnz     short loc_18002E68C
0x18002e68a  xor     bl, bl
0x18002e68c  mov     rcx, [rbp+SidToCheck]; hMem
0x18002e690  test    rcx, rcx
0x18002e693  jz      short loc_18002E69B
0x18002e695  call    cs:__imp_LocalFree
0x18002e69b  lea     rcx, [rbp+var_30]
0x18002e69f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002e6a4  lea     rcx, [rbp+var_50]
0x18002e6a8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002e6ad  test    bl, bl
0x18002e6af  setnz   al
0x18002e6b2  jmp     short loc_18002E6B6
0x18002e6b4  mov     al, bl
0x18002e6b6  mov     rcx, [rbp+var_8]
0x18002e6ba  xor     rcx, rsp; StackCookie
0x18002e6bd  call    __security_check_cookie
0x18002e6c2  lea     r11, [rsp+80h+var_s0]
0x18002e6ca  mov     rbx, [r11+10h]
0x18002e6ce  mov     rdi, [r11+18h]
0x18002e6d2  mov     rsp, r11
0x18002e6d5  pop     rbp
0x18002e6d6  retn
```
