# CUserProfileRoamingProvider::UploadRoamingProfile(int,int *)

- ea: `0x1800159b0`
- end: `0x180015aaa`
- name: `?UploadRoamingProfile@CUserProfileRoamingProvider@@UEAAJHPEAH@Z`
- size: `250`
- prototype: `__int64 __fastcall(CUserProfileRoamingProvider *__hidden this, int, int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180006a9c`
- `0x180008258`
- `0x180009dfc`
- `0x1800159b0`
- `0x180016ef8`
- `0x180020010`

## string_xrefs

- `0x1800159ea`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x180015a87`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x180015a0b`: `ProfileAttemptedProfileUploadTimeHigh`
- `0x180015a19`: `ProfileAttemptedProfileUploadTimeLow`

## pseudocode

```c
__int64 __fastcall CUserProfileRoamingProvider::UploadRoamingProfile(
        CUserProfileRoamingProvider *this,
        int a2,
        int *a3)
{
  int IsRoaming; // edi
  __int64 v7; // rdx
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v13; // [rsp+60h] [rbp+18h] BYREF

  *a3 = 0;
  v13 = 0;
  IsRoaming = CUserProfileRoamingProvider::_IsRoaming(this, &v13);
  if ( IsRoaming < 0 )
  {
    v7 = 249;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
      (const char *)(unsigned int)IsRoaming,
      v11);
    return (unsigned int)IsRoaming;
  }
  if ( !v13 )
    return 0;
  *((_DWORD *)this + 4) = 1;
  IsRoaming = CUserProfileRoamingProvider::_SaveUnloadTime(
                this,
                L"ProfileAttemptedProfileUploadTimeLow",
                L"ProfileAttemptedProfileUploadTimeHigh");
  if ( IsRoaming < 0 )
  {
    v7 = 257;
    goto LABEL_3;
  }
  IsRoaming = CUserProfileRoamingProvider::_UploadProfileDirectory(this, a2);
  if ( IsRoaming < 0 )
  {
    v7 = 259;
    goto LABEL_3;
  }
  *a3 = 1;
  if ( ((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 8LL))(*((_QWORD *)this + 1)) & 4) != 0 )
    return 0;
  v9 = CUserProfileRoamingProvider::_SaveUnloadTime(this, L"ProfileUnloadTimeLow", L"ProfileUnloadTimeHigh");
  v10 = v9;
  if ( v9 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x10A,
    (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
    (const char *)(unsigned int)v9,
    v11);
  return v10;
}

```

## disassembly

```asm
0x1800159b0  push    rbx
0x1800159b2  push    rbp
0x1800159b3  push    rsi
0x1800159b4  push    rdi
0x1800159b5  sub     rsp, 28h
0x1800159b9  mov     ebp, edx
0x1800159bb  mov     dword ptr [r8], 0
0x1800159c2  lea     rdx, [rsp+48h+arg_10]; int *
0x1800159c7  mov     [rsp+48h+arg_10], 0
0x1800159cf  mov     rsi, r8
0x1800159d2  mov     rbx, rcx
0x1800159d5  call    ?_IsRoaming@CUserProfileRoamingProvider@@AEAAJPEAH@Z; CUserProfileRoamingProvider::_IsRoaming(int *)
0x1800159da  mov     edi, eax
0x1800159dc  test    eax, eax
0x1800159de  jns     short loc_180015A00
0x1800159e0  mov     edx, 0F9h; void *
0x1800159e5  mov     rcx, [rsp+48h]; this
0x1800159ea  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x1800159f1  mov     r9d, edi; char *
0x1800159f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800159f9  mov     eax, edi
0x1800159fb  jmp     loc_180015AA1
0x180015a00  cmp     [rsp+48h+arg_10], 0
0x180015a05  jz      loc_180015A9F
0x180015a0b  lea     r8, aProfileattempt; "ProfileAttemptedProfileUploadTimeHigh"
0x180015a12  mov     dword ptr [rbx+10h], 1
0x180015a19  lea     rdx, aProfileattempt_0; "ProfileAttemptedProfileUploadTimeLow"
0x180015a20  mov     rcx, rbx; this
0x180015a23  call    ?_SaveUnloadTime@CUserProfileRoamingProvider@@AEAAJPEBG0@Z; CUserProfileRoamingProvider::_SaveUnloadTime(ushort const *,ushort const *)
0x180015a28  mov     edi, eax
0x180015a2a  test    eax, eax
0x180015a2c  jns     short loc_180015A35
0x180015a2e  mov     edx, 101h
0x180015a33  jmp     short loc_1800159E5
0x180015a35  mov     edx, ebp; int
0x180015a37  mov     rcx, rbx; this
0x180015a3a  call    ?_UploadProfileDirectory@CUserProfileRoamingProvider@@AEAAJH@Z; CUserProfileRoamingProvider::_UploadProfileDirectory(int)
0x180015a3f  mov     edi, eax
0x180015a41  test    eax, eax
0x180015a43  jns     short loc_180015A4C
0x180015a45  mov     edx, 103h
0x180015a4a  jmp     short loc_1800159E5
0x180015a4c  mov     dword ptr [rsi], 1
0x180015a52  mov     rcx, [rbx+8]
0x180015a56  mov     rax, [rcx]
0x180015a59  mov     rax, [rax+8]
0x180015a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a62  test    al, 4
0x180015a64  jnz     short loc_180015A9F
0x180015a66  lea     r8, aProfileunloadt_0; "ProfileUnloadTimeHigh"
0x180015a6d  mov     rcx, rbx; this
0x180015a70  lea     rdx, aProfileunloadt; "ProfileUnloadTimeLow"
0x180015a77  call    ?_SaveUnloadTime@CUserProfileRoamingProvider@@AEAAJPEBG0@Z; CUserProfileRoamingProvider::_SaveUnloadTime(ushort const *,ushort const *)
0x180015a7c  mov     ebx, eax
0x180015a7e  test    eax, eax
0x180015a80  jns     short loc_180015A9F
0x180015a82  mov     rcx, [rsp+48h]; this
0x180015a87  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180015a8e  mov     r9d, eax; char *
0x180015a91  mov     edx, 10Ah; void *
0x180015a96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015a9b  mov     eax, ebx
0x180015a9d  jmp     short loc_180015AA1
0x180015a9f  xor     eax, eax
0x180015aa1  add     rsp, 28h
0x180015aa5  pop     rdi
0x180015aa6  pop     rsi
0x180015aa7  pop     rbp
0x180015aa8  pop     rbx
0x180015aa9  retn
```
