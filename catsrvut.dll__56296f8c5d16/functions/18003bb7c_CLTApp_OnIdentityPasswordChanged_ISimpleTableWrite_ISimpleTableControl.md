# CLTApp::OnIdentityPasswordChanged(ISimpleTableWrite *,ISimpleTableControl *)

- ea: `0x18003bb7c`
- end: `0x18003befb`
- name: `?OnIdentityPasswordChanged@CLTApp@@AEAAJPEAUISimpleTableWrite@@PEAUISimpleTableControl@@@Z`
- size: `895`
- prototype: `__int64 __fastcall(CLTApp *__hidden this, struct ISimpleTableWrite *, struct ISimpleTableControl *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003ef60`

## callees

- `0x18001933c`
- `0x18003a8b4`
- `0x18003bb7c`
- `0x180043c9c`
- `0x180043cd4`
- `0x180055880`
- `0x180057010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003bcde`
- `msvcrt!_wcsicmp` at `0x18003bd17`
- `msvcrt!_wcsicmp` at `0x18003bcde`
- `msvcrt!_wcsicmp` at `0x18003bd17`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003bd69`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003bd7d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003bd91`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003bd69`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003bd7d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003bd91`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLTApp::OnIdentityPasswordChanged(
        CLTApp *this,
        struct ISimpleTableWrite *a2,
        struct ISimpleTableControl *a3)
{
  int v6; // esi
  int SecurityAdmin; // ebx
  int v8; // r15d
  OLECHAR *v9; // rdi
  unsigned __int16 *v10; // rax
  PSID v11; // rbx
  int v12; // eax
  int v13; // eax
  unsigned __int16 *v15; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *String1; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v17; // [rsp+50h] [rbp-B0h] BYREF
  int v18; // [rsp+58h] [rbp-A8h] BYREF
  int v19; // [rsp+5Ch] [rbp-A4h] BYREF
  int v20; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v21[3]; // [rsp+64h] [rbp-9Ch] BYREF
  struct ISecurityAdmin2 *v22[2]; // [rsp+70h] [rbp-90h] BYREF
  struct _GUID v23; // [rsp+80h] [rbp-80h] BYREF
  PSID pSid1; // [rsp+90h] [rbp-70h] BYREF
  int v25; // [rsp+98h] [rbp-68h]

  v6 = 0;
  v18 = 0;
  v20 = 0;
  v21[0] = 0;
  v19 = 0;
  v15 = 0;
  String1 = 0;
  v17 = 0;
  SecurityAdmin = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, int *, _QWORD, int *, unsigned __int16 **))(*(_QWORD *)a2 + 152LL))(
                    a2,
                    15,
                    &v18,
                    0,
                    &v19,
                    &v15);
  if ( SecurityAdmin < 0 )
    goto LABEL_39;
  SecurityAdmin = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, int *, _QWORD, int *, wchar_t **))(*(_QWORD *)a2 + 152LL))(
                    a2,
                    8,
                    &v20,
                    0,
                    &v19,
                    &String1);
  if ( SecurityAdmin < 0 )
    goto LABEL_39;
  SecurityAdmin = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, _QWORD, _QWORD, _QWORD, unsigned __int16 **))(*(_QWORD *)a2 + 152LL))(
                    a2,
                    6,
                    0,
                    0,
                    0,
                    &v17);
  if ( SecurityAdmin < 0 )
    goto LABEL_39;
  if ( !String1 || (((unsigned __int8)v18 | (unsigned __int8)v20) & 2) == 0 )
    goto LABEL_35;
  v22[0] = 0;
  SecurityAdmin = MyGetSecurityAdmin(v22);
  if ( SecurityAdmin < 0 )
    goto LABEL_39;
  v8 = 1;
  v9 = (OLECHAR *)&Password;
  if ( (v18 & 2) == 0 || !v15 )
    v15 = (unsigned __int16 *)&Password;
  if ( _wcsicmp(String1, L"LocalSystem") )
  {
    if ( !_wcsicmp(String1, L"Interactive User") )
    {
      v10 = v17;
      if ( !v17 || !*v17 )
      {
        v9 = 0;
        v15 = 0;
        String1 = 0;
        goto LABEL_28;
      }
LABEL_14:
      SecurityAdmin = -2146368492;
      goto LABEL_39;
    }
    pSid1 = 0;
    v25 = 0;
    if ( (int)CSid::InitializeFromName((CSid *)&pSid1, String1) >= 0 )
    {
      v11 = pSid1;
      if ( EqualSid(pSid1, &CSid::x_sidSystem)
        || EqualSid(v11, &CSid::x_sidLocalService)
        || EqualSid(v11, &CSid::x_sidNetworkService) )
      {
        v15 = (unsigned __int16 *)&Password;
        v6 = 1;
        v8 = 0;
      }
    }
    SecurityAdmin = 0;
    CSid::Initialize((CSid *)&pSid1);
    if ( !v6 )
    {
      v12 = (*(__int64 (__fastcall **)(struct ISecurityAdmin2 *, wchar_t *, unsigned __int16 *))(*(_QWORD *)v22[0] + 48LL))(
              v22[0],
              String1,
              v15);
      SecurityAdmin = v12;
      if ( v12 == 1 )
        goto LABEL_14;
      if ( v12 < 0 )
        goto LABEL_39;
    }
    v9 = v15;
    v10 = v17;
    goto LABEL_28;
  }
  v10 = v17;
  if ( !v17 || !*v17 )
    goto LABEL_14;
  v15 = (unsigned __int16 *)&Password;
LABEL_28:
  if ( v10 && *v10 )
  {
    *(GUID *)v22 = GUID_NULL;
    v13 = CLTApp::AddToIdentityList(this, (struct _GUID *)v22, v10, String1, v9);
LABEL_34:
    SecurityAdmin = v13;
    if ( v13 < 0 )
      goto LABEL_39;
LABEL_35:
    v10 = v17;
    goto LABEL_36;
  }
  if ( v8 )
  {
    v22[0] = 0;
    SecurityAdmin = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, _QWORD, _DWORD *, _QWORD, int *, struct ISecurityAdmin2 **))(*(_QWORD *)a2 + 152LL))(
                      a2,
                      0,
                      v21,
                      0,
                      &v19,
                      v22);
    if ( SecurityAdmin < 0 )
      goto LABEL_39;
    v23 = *(struct _GUID *)v22[0];
    v13 = CLTApp::AddToIdentityList(this, &v23, 0, String1, v15);
    goto LABEL_34;
  }
LABEL_36:
  if ( v10 || (v20 & 2) == 0 )
    SecurityAdmin = (*(__int64 (__fastcall **)(struct ISimpleTableControl *, __int64, __int64))(*(_QWORD *)a3 + 72LL))(
                      a3,
                      8,
                      4);
LABEL_39:
  (*(void (__fastcall **)(struct ISimpleTableControl *, __int64))(*(_QWORD *)a3 + 72LL))(a3, 15);
  return (unsigned int)SecurityAdmin;
}

```

## disassembly

```asm
0x18003bb7c  mov     [rsp-8+arg_18], rbx
0x18003bb81  push    rbp
0x18003bb82  push    rsi
0x18003bb83  push    rdi
0x18003bb84  push    r12
0x18003bb86  push    r13
0x18003bb88  push    r14
0x18003bb8a  push    r15
0x18003bb8c  lea     rbp, [rsp-1E0h]
0x18003bb94  sub     rsp, 2E0h
0x18003bb9b  mov     rax, cs:__security_cookie
0x18003bba2  xor     rax, rsp
0x18003bba5  mov     [rbp+210h+var_40], rax
0x18003bbac  mov     r12, r8
0x18003bbaf  mov     r14, rdx
0x18003bbb2  mov     r13, rcx
0x18003bbb5  xor     esi, esi
0x18003bbb7  mov     [rsp+310h+var_2B8], esi
0x18003bbbb  mov     [rsp+310h+var_2B0], esi
0x18003bbbf  mov     [rsp+310h+var_2AC], esi
0x18003bbc3  mov     [rsp+310h+var_2B4], esi
0x18003bbc7  mov     [rsp+310h+var_2D0], rsi
0x18003bbcc  mov     [rsp+310h+String1], rsi
0x18003bbd1  mov     [rsp+310h+var_2C0], rsi
0x18003bbd6  mov     rax, [rdx]
0x18003bbd9  lea     rcx, [rsp+310h+var_2D0]
0x18003bbde  mov     [rsp+310h+var_2E8], rcx
0x18003bbe3  lea     rcx, [rsp+310h+var_2B4]
0x18003bbe8  mov     [rsp+310h+var_2F0], rcx
0x18003bbed  xor     r9d, r9d
0x18003bbf0  lea     r8, [rsp+310h+var_2B8]
0x18003bbf5  lea     edx, [rsi+0Fh]
0x18003bbf8  mov     rcx, r14
0x18003bbfb  mov     rax, [rax+98h]
0x18003bc02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc07  mov     ebx, eax
0x18003bc09  test    eax, eax
0x18003bc0b  js      loc_18003BEB8
0x18003bc11  mov     rax, [r14]
0x18003bc14  lea     rcx, [rsp+310h+String1]
0x18003bc19  mov     [rsp+310h+var_2E8], rcx
0x18003bc1e  lea     rcx, [rsp+310h+var_2B4]
0x18003bc23  mov     [rsp+310h+var_2F0], rcx
0x18003bc28  xor     r9d, r9d
0x18003bc2b  lea     r8, [rsp+310h+var_2B0]
0x18003bc30  lea     edx, [rsi+8]
0x18003bc33  mov     rcx, r14
0x18003bc36  mov     rax, [rax+98h]
0x18003bc3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc42  mov     ebx, eax
0x18003bc44  test    eax, eax
0x18003bc46  js      loc_18003BEB8
0x18003bc4c  mov     rax, [r14]
0x18003bc4f  lea     rcx, [rsp+310h+var_2C0]
0x18003bc54  mov     [rsp+310h+var_2E8], rcx
0x18003bc59  mov     [rsp+310h+var_2F0], rsi
0x18003bc5e  xor     r9d, r9d
0x18003bc61  xor     r8d, r8d
0x18003bc64  lea     edx, [rsi+6]
0x18003bc67  mov     rcx, r14
0x18003bc6a  mov     rax, [rax+98h]
0x18003bc71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc76  mov     ebx, eax
0x18003bc78  test    eax, eax
0x18003bc7a  js      loc_18003BEB8
0x18003bc80  cmp     [rsp+310h+String1], rsi
0x18003bc85  jz      loc_18003BE8C
0x18003bc8b  mov     eax, [rsp+310h+var_2B0]
0x18003bc8f  or      eax, [rsp+310h+var_2B8]
0x18003bc93  test    al, 2
0x18003bc95  jz      loc_18003BE8C
0x18003bc9b  mov     [rsp+310h+var_2A0], rsi
0x18003bca0  lea     rcx, [rsp+310h+var_2A0]; struct ISecurityAdmin2 **
0x18003bca5  call    ?MyGetSecurityAdmin@@YAJPEAPEAUISecurityAdmin2@@@Z; MyGetSecurityAdmin(ISecurityAdmin2 * *)
0x18003bcaa  mov     ebx, eax
0x18003bcac  test    eax, eax
0x18003bcae  js      loc_18003BEB8
0x18003bcb4  lea     r15d, [rsi+1]
0x18003bcb8  lea     rdi, Password
0x18003bcbf  test    byte ptr [rsp+310h+var_2B8], 2
0x18003bcc4  jz      short loc_18003BCCD
0x18003bcc6  cmp     [rsp+310h+var_2D0], rsi
0x18003bccb  jnz     short loc_18003BCD2
0x18003bccd  mov     [rsp+310h+var_2D0], rdi
0x18003bcd2  lea     rdx, aLocalsystem; "LocalSystem"
0x18003bcd9  mov     rcx, [rsp+310h+String1]; String1
0x18003bcde  call    cs:__imp__wcsicmp
0x18003bce4  test    eax, eax
0x18003bce6  jnz     short loc_18003BD0B
0x18003bce8  mov     rax, [rsp+310h+var_2C0]
0x18003bced  test    rax, rax
0x18003bcf0  jz      short loc_18003BD01
0x18003bcf2  cmp     [rax], si
0x18003bcf5  jz      short loc_18003BD01
0x18003bcf7  mov     [rsp+310h+var_2D0], rdi
0x18003bcfc  jmp     loc_18003BDF5
0x18003bd01  mov     ebx, 80110414h
0x18003bd06  jmp     loc_18003BEB8
0x18003bd0b  lea     rdx, aInteractiveUse; "Interactive User"
0x18003bd12  mov     rcx, [rsp+310h+String1]; String1
0x18003bd17  call    cs:__imp__wcsicmp
0x18003bd1d  test    eax, eax
0x18003bd1f  jnz     short loc_18003BD42
0x18003bd21  mov     rax, [rsp+310h+var_2C0]
0x18003bd26  test    rax, rax
0x18003bd29  jz      short loc_18003BD30
0x18003bd2b  cmp     [rax], si
0x18003bd2e  jnz     short loc_18003BD01
0x18003bd30  mov     rdi, rsi
0x18003bd33  mov     [rsp+310h+var_2D0], rsi
0x18003bd38  mov     [rsp+310h+String1], rsi
0x18003bd3d  jmp     loc_18003BDF5
0x18003bd42  mov     [rbp+210h+pSid1], rsi
0x18003bd46  mov     [rbp+210h+var_278], esi
0x18003bd49  mov     rdx, [rsp+310h+String1]; unsigned __int16 *
0x18003bd4e  lea     rcx, [rbp+210h+pSid1]; this
0x18003bd52  call    ?InitializeFromName@CSid@@QEAAJPEAG@Z; CSid::InitializeFromName(ushort *)
0x18003bd57  test    eax, eax
0x18003bd59  js      short loc_18003BDA8
0x18003bd5b  lea     rdx, ?x_sidSystem@CSid@@0U_SID1@1@B; pSid2
0x18003bd62  mov     rbx, [rbp+210h+pSid1]
0x18003bd66  mov     rcx, rbx; pSid1
0x18003bd69  call    cs:__imp_EqualSid
0x18003bd6f  test    eax, eax
0x18003bd71  jnz     short loc_18003BD9B
0x18003bd73  lea     rdx, ?x_sidLocalService@CSid@@0U_SID1@1@B; pSid2
0x18003bd7a  mov     rcx, rbx; pSid1
0x18003bd7d  call    cs:__imp_EqualSid
0x18003bd83  test    eax, eax
0x18003bd85  jnz     short loc_18003BD9B
0x18003bd87  lea     rdx, ?x_sidNetworkService@CSid@@0U_SID1@1@B; pSid2
0x18003bd8e  mov     rcx, rbx; pSid1
0x18003bd91  call    cs:__imp_EqualSid
0x18003bd97  test    eax, eax
0x18003bd99  jz      short loc_18003BDA8
0x18003bd9b  mov     [rsp+310h+var_2D0], rdi
0x18003bda0  mov     esi, 1
0x18003bda5  xor     r15d, r15d
0x18003bda8  xor     ebx, ebx
0x18003bdaa  lea     rcx, [rbp+210h+pSid1]; this
0x18003bdae  call    ?Initialize@CSid@@AEAAXXZ; CSid::Initialize(void)
0x18003bdb3  test    esi, esi
0x18003bdb5  jnz     short loc_18003BDE9
0x18003bdb7  mov     rcx, [rsp+310h+var_2A0]
0x18003bdbc  mov     rax, [rcx]
0x18003bdbf  mov     r8, [rsp+310h+var_2D0]
0x18003bdc4  mov     rdx, [rsp+310h+String1]
0x18003bdc9  mov     rax, [rax+30h]
0x18003bdcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bdd2  mov     ebx, eax
0x18003bdd4  cmp     eax, 1
0x18003bdd7  jz      loc_18003BD01
0x18003bddd  xor     esi, esi
0x18003bddf  test    eax, eax
0x18003bde1  js      loc_18003BEB8
0x18003bde7  jmp     short loc_18003BDEB
0x18003bde9  xor     esi, esi
0x18003bdeb  mov     rdi, [rsp+310h+var_2D0]
0x18003bdf0  mov     rax, [rsp+310h+var_2C0]
0x18003bdf5  test    rax, rax
0x18003bdf8  jz      short loc_18003BE1B
0x18003bdfa  cmp     [rax], si
0x18003bdfd  jz      short loc_18003BE1B
0x18003bdff  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003be06  movdqu  xmmword ptr [rsp+310h+var_2A0], xmm0
0x18003be0c  mov     [rsp+310h+var_2F0], rdi
0x18003be11  mov     r8, rax
0x18003be14  lea     rdx, [rsp+310h+var_2A0]
0x18003be19  jmp     short loc_18003BE79
0x18003be1b  test    r15d, r15d
0x18003be1e  jz      short loc_18003BE91
0x18003be20  mov     [rsp+310h+var_2A0], rsi
0x18003be25  mov     rax, [r14]
0x18003be28  lea     rcx, [rsp+310h+var_2A0]
0x18003be2d  mov     [rsp+310h+var_2E8], rcx
0x18003be32  lea     rcx, [rsp+310h+var_2B4]
0x18003be37  mov     [rsp+310h+var_2F0], rcx
0x18003be3c  xor     r9d, r9d
0x18003be3f  lea     r8, [rsp+310h+var_2AC]
0x18003be44  xor     edx, edx
0x18003be46  mov     rcx, r14
0x18003be49  mov     rax, [rax+98h]
0x18003be50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be55  mov     ebx, eax
0x18003be57  test    eax, eax
0x18003be59  js      short loc_18003BEB8
0x18003be5b  mov     rax, [rsp+310h+var_2A0]
0x18003be60  movups  xmm0, xmmword ptr [rax]
0x18003be63  movdqu  xmmword ptr [rbp+210h+var_290.Data1], xmm0
0x18003be68  mov     rax, [rsp+310h+var_2D0]
0x18003be6d  mov     [rsp+310h+var_2F0], rax; unsigned __int16 *
0x18003be72  xor     r8d, r8d; unsigned __int16 *
0x18003be75  lea     rdx, [rbp+210h+var_290]; struct _GUID
0x18003be79  mov     r9, [rsp+310h+String1]; unsigned __int16 *
0x18003be7e  mov     rcx, r13; this
0x18003be81  call    ?AddToIdentityList@CLTApp@@AEAAJU_GUID@@PEAG11@Z; CLTApp::AddToIdentityList(_GUID,ushort *,ushort *,ushort *)
0x18003be86  test    eax, eax
0x18003be88  mov     ebx, eax
0x18003be8a  js      short loc_18003BEB8
0x18003be8c  mov     rax, [rsp+310h+var_2C0]
0x18003be91  test    rax, rax
0x18003be94  jnz     short loc_18003BE9D
0x18003be96  test    byte ptr [rsp+310h+var_2B0], 2
0x18003be9b  jnz     short loc_18003BEB8
0x18003be9d  mov     rax, [r12]
0x18003bea1  mov     edx, 8
0x18003bea6  lea     r8d, [rdx-4]
0x18003beaa  mov     rcx, r12
0x18003bead  mov     rax, [rax+48h]
0x18003beb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003beb6  mov     ebx, eax
0x18003beb8  mov     rax, [r12]
0x18003bebc  xor     r8d, r8d
0x18003bebf  lea     edx, [r8+0Fh]
0x18003bec3  mov     rcx, r12
0x18003bec6  mov     rax, [rax+48h]
0x18003beca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003becf  mov     eax, ebx
0x18003bed1  mov     rcx, [rbp+210h+var_40]
0x18003bed8  xor     rcx, rsp; StackCookie
0x18003bedb  call    __security_check_cookie
0x18003bee0  mov     rbx, [rsp+310h+arg_18]
0x18003bee8  add     rsp, 2E0h
0x18003beef  pop     r15
0x18003bef1  pop     r14
0x18003bef3  pop     r13
0x18003bef5  pop     r12
0x18003bef7  pop     rdi
0x18003bef8  pop     rsi
0x18003bef9  pop     rbp
0x18003befa  retn
```
