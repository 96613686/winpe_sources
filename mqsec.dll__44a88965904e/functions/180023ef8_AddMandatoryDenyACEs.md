# _AddMandatoryDenyACEs

- ea: `0x180023ef8`
- end: `0x1800241c0`
- name: `_AddMandatoryDenyACEs`
- size: `712`
- prototype: `__int64 __fastcall(__int64, __int64, struct _ACL *, DWORD *, PACL *, _DWORD *, _DWORD *, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1800247e4`

## callees

- `0x1800049ac`
- `0x18001722c`
- `0x180023ef8`
- `0x180024590`
- `0x18002f0a2`
- `0x18002f0e0`

## import_xrefs

- `msvcrt!free` at `0x180024048`
- `msvcrt!free` at `0x1800240e2`
- `msvcrt!free` at `0x180024164`
- `msvcrt!free` at `0x180024193`
- `msvcrt!free` at `0x180024048`
- `msvcrt!free` at `0x1800240e2`
- `msvcrt!free` at `0x180024164`
- `msvcrt!free` at `0x180024193`
- `RPCRT4!UuidFromStringW` at `0x180023f62`
- `RPCRT4!UuidFromStringW` at `0x180023f62`
- `ADVAPI32!FindFirstFreeAce` at `0x18002410b`
- `ADVAPI32!FindFirstFreeAce` at `0x18002410b`
- `ADVAPI32!AddAccessDeniedObjectAce` at `0x180024089`
- `ADVAPI32!AddAccessDeniedObjectAce` at `0x180024089`
- `ADVAPI32!InitializeAcl` at `0x180023fec`
- `ADVAPI32!InitializeAcl` at `0x180023fec`
- `KERNEL32!GetLastError` at `0x180023ff9`
- `KERNEL32!GetLastError` at `0x180024093`
- `KERNEL32!GetLastError` at `0x180024115`
- `KERNEL32!GetLastError` at `0x180023ff9`
- `KERNEL32!GetLastError` at `0x180024093`
- `KERNEL32!GetLastError` at `0x180024115`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AddMandatoryDenyACEs(
        __int64 a1,
        __int64 a2,
        struct _ACL *a3,
        DWORD *a4,
        PACL *a5,
        _DWORD *a6,
        _DWORD *a7,
        __int64 a8,
        _DWORD *a9)
{
  struct _ACL *v12; // rbx
  signed int LastError; // edi
  LPVOID pAce; // [rsp+40h] [rbp-30h] BYREF
  __int64 v16; // [rsp+48h] [rbp-28h]
  UUID Uuid; // [rsp+50h] [rbp-20h] BYREF

  v16 = a8;
  *a7 = 0;
  *a4 = 65520;
  Uuid = 0;
  UuidFromStringW((RPC_WSTR)L"bf96793f-0de6-11d0-a285-00aa003049e2", &Uuid);
  if ( a3 )
    *a6 = a3->AclRevision == 4;
  LODWORD(pAce) = 0;
  if ( !a2 )
    *a9 = 1;
  if ( *a6 && a3 && (unsigned int)CheckForMandatoryACEs(a3, v16, (__int64)a9) )
  {
    *a4 = a3->AclSize;
    *a7 = 1;
  }
  v12 = (struct _ACL *)MmAllocate(*a4);
  v16 = (__int64)v12;
  *a5 = v12;
  if ( !InitializeAcl(v12, *a4, 4u) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 32),
        14,
        WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids,
        (unsigned int)LastError);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_15:
    free(v12);
    return (unsigned int)LastError;
  }
  if ( !(_DWORD)pAce && !AddAccessDeniedObjectAce(*a5, 4u, 0, 0x20u, &Uuid, 0, g_pWorldSid) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 32),
        15,
        WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids,
        (unsigned int)LastError);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_15;
  }
  if ( *a6 && a3 )
  {
    pAce = 0;
    if ( !FindFirstFreeAce(*a5, &pAce) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 32),
          16,
          WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids,
          (unsigned int)LastError);
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      free(v12);
      return (unsigned int)LastError;
    }
    memcpy_0(pAce, &a3[1], (unsigned int)a3->AclSize - 8);
    (*a5)->AceCount += a3->AceCount;
  }
  free(0);
  return 0;
}

```

## disassembly

```asm
0x180023ef8  mov     [rsp-38h+arg_0], rbx
0x180023efd  push    rbp
0x180023efe  push    rsi
0x180023eff  push    rdi
0x180023f00  push    r12
0x180023f02  push    r13
0x180023f04  push    r14
0x180023f06  push    r15
0x180023f08  mov     rbp, rsp
0x180023f0b  sub     rsp, 70h
0x180023f0f  mov     rax, cs:__security_cookie
0x180023f16  xor     rax, rsp
0x180023f19  mov     [rbp+var_10], rax
0x180023f1d  mov     r15, r9
0x180023f20  mov     rdi, r8
0x180023f23  mov     rbx, rdx
0x180023f26  mov     rsi, [rbp+arg_20]
0x180023f2a  mov     r14, [rbp+arg_28]
0x180023f2e  mov     r13, [rbp+arg_30]
0x180023f32  mov     rax, [rbp+arg_38]
0x180023f36  mov     [rbp+var_28], rax
0x180023f3a  mov     r12, [rbp+arg_40]
0x180023f41  mov     dword ptr [r13+0], 0
0x180023f49  mov     dword ptr [r9], 0FFF0h
0x180023f50  xorps   xmm0, xmm0
0x180023f53  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x180023f57  lea     rdx, [rbp+Uuid]; Uuid
0x180023f5b  lea     rcx, StringUuid; "bf96793f-0de6-11d0-a285-00aa003049e2"
0x180023f62  call    cs:__imp_UuidFromStringW
0x180023f68  test    rdi, rdi
0x180023f6b  jz      short loc_180023F78
0x180023f6d  xor     eax, eax
0x180023f6f  cmp     byte ptr [rdi], 4
0x180023f72  setz    al
0x180023f75  mov     [r14], eax
0x180023f78  mov     dword ptr [rbp+pAce], 0
0x180023f7f  test    rbx, rbx
0x180023f82  jnz     short loc_180023F8C
0x180023f84  mov     dword ptr [r12], 1
0x180023f8c  cmp     dword ptr [r14], 0
0x180023f90  jz      short loc_180023FCB
0x180023f92  test    rdi, rdi
0x180023f95  jz      short loc_180023FCB
0x180023f97  mov     [rsp+70h+InheritedObjectTypeGuid], r12; __int64
0x180023f9c  mov     rax, [rbp+var_28]
0x180023fa0  mov     [rsp+70h+ObjectTypeGuid], rax; __int64
0x180023fa5  lea     r9, [rbp+pAce]
0x180023fa9  lea     r8, [rbp+Uuid]
0x180023fad  mov     rdx, rbx
0x180023fb0  mov     rcx, rdi; pAcl
0x180023fb3  call    _CheckForMandatoryACEs
0x180023fb8  test    eax, eax
0x180023fba  jz      short loc_180023FCB
0x180023fbc  movzx   eax, word ptr [rdi+2]
0x180023fc0  mov     [r15], eax
0x180023fc3  mov     dword ptr [r13+0], 1
0x180023fcb  mov     ecx, [r15]; unsigned __int64
0x180023fce  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180023fd3  mov     rbx, rax
0x180023fd6  mov     [rbp+var_28], rax
0x180023fda  mov     [rsi], rax
0x180023fdd  mov     r12d, 4
0x180023fe3  mov     r8d, r12d; dwAclRevision
0x180023fe6  mov     edx, [r15]; nAclLength
0x180023fe9  mov     rcx, rax; pAcl
0x180023fec  call    cs:__imp_InitializeAcl
0x180023ff2  xor     r15d, r15d
0x180023ff5  test    eax, eax
0x180023ff7  jnz     short loc_180024056
0x180023ff9  call    cs:__imp_GetLastError
0x180023fff  mov     edi, eax
0x180024001  lea     rax, WPP_GLOBAL_Control
0x180024008  mov     rcx, cs:WPP_GLOBAL_Control
0x18002400f  cmp     rcx, rax
0x180024012  jz      short loc_180024038
0x180024014  test    byte ptr [rcx+10Ch], 1
0x18002401b  jz      short loc_180024038
0x18002401d  lea     edx, [r12+0Ah]
0x180024022  mov     r9d, edi
0x180024025  lea     r8, WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids
0x18002402c  mov     rcx, [rcx+100h]
0x180024033  call    WPP_SF_d
0x180024038  test    edi, edi
0x18002403a  jle     short loc_180024045
0x18002403c  movzx   edi, di
0x18002403f  or      edi, 80070000h
0x180024045  mov     rcx, rbx; Block
0x180024048  call    cs:__imp_free
0x18002404e  nop
0x18002404f  mov     eax, edi
0x180024051  jmp     loc_18002419C
0x180024056  cmp     dword ptr [rbp+pAce], r15d
0x18002405a  jnz     loc_1800240EE
0x180024060  mov     rax, cs:?g_pWorldSid@@3PEAXEA; void * g_pWorldSid
0x180024067  mov     [rsp+70h+pSid], rax; pSid
0x18002406c  mov     [rsp+70h+InheritedObjectTypeGuid], r15; InheritedObjectTypeGuid
0x180024071  lea     rax, [rbp+Uuid]
0x180024075  mov     [rsp+70h+ObjectTypeGuid], rax; ObjectTypeGuid
0x18002407a  mov     r9d, 20h ; ' '; AccessMask
0x180024080  xor     r8d, r8d; AceFlags
0x180024083  mov     edx, r12d; dwAceRevision
0x180024086  mov     rcx, [rsi]; pAcl
0x180024089  call    cs:__imp_AddAccessDeniedObjectAce
0x18002408f  test    eax, eax
0x180024091  jnz     short loc_1800240EE
0x180024093  call    cs:__imp_GetLastError
0x180024099  mov     edi, eax
0x18002409b  lea     rax, WPP_GLOBAL_Control
0x1800240a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800240a9  cmp     rcx, rax
0x1800240ac  jz      short loc_1800240D2
0x1800240ae  test    byte ptr [rcx+10Ch], 1
0x1800240b5  jz      short loc_1800240D2
0x1800240b7  mov     edx, 0Fh
0x1800240bc  mov     r9d, edi
0x1800240bf  lea     r8, WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids
0x1800240c6  mov     rcx, [rcx+100h]
0x1800240cd  call    WPP_SF_d
0x1800240d2  test    edi, edi
0x1800240d4  jle     short loc_1800240DF
0x1800240d6  movzx   edi, di
0x1800240d9  or      edi, 80070000h
0x1800240df  mov     rcx, rbx; Block
0x1800240e2  call    cs:__imp_free
0x1800240e8  nop
0x1800240e9  jmp     loc_18002404F
0x1800240ee  cmp     [r14], r15d
0x1800240f1  jz      loc_180024191
0x1800240f7  test    rdi, rdi
0x1800240fa  jz      loc_180024191
0x180024100  mov     [rbp+pAce], r15
0x180024104  lea     rdx, [rbp+pAce]; pAce
0x180024108  mov     rcx, [rsi]; pAcl
0x18002410b  call    cs:__imp_FindFirstFreeAce
0x180024111  test    eax, eax
0x180024113  jnz     short loc_180024170
0x180024115  call    cs:__imp_GetLastError
0x18002411b  mov     edi, eax
0x18002411d  lea     rax, WPP_GLOBAL_Control
0x180024124  mov     rcx, cs:WPP_GLOBAL_Control
0x18002412b  cmp     rcx, rax
0x18002412e  jz      short loc_180024154
0x180024130  test    byte ptr [rcx+10Ch], 1
0x180024137  jz      short loc_180024154
0x180024139  mov     edx, 10h
0x18002413e  mov     r9d, edi
0x180024141  lea     r8, WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids
0x180024148  mov     rcx, [rcx+100h]
0x18002414f  call    WPP_SF_d
0x180024154  test    edi, edi
0x180024156  jle     short loc_180024161
0x180024158  movzx   edi, di
0x18002415b  or      edi, 80070000h
0x180024161  mov     rcx, rbx; Block
0x180024164  call    cs:__imp_free
0x18002416a  nop
0x18002416b  jmp     loc_18002404F
0x180024170  movzx   r8d, word ptr [rdi+2]
0x180024175  sub     r8d, 8; Size
0x180024179  lea     rdx, [rdi+8]; Src
0x18002417d  mov     rcx, [rbp+pAce]; void *
0x180024181  call    memcpy_0
0x180024186  mov     rcx, [rsi]
0x180024189  movzx   eax, word ptr [rdi+4]
0x18002418d  add     [rcx+4], ax
0x180024191  xor     ecx, ecx; Block
0x180024193  call    cs:__imp_free
0x180024199  nop
0x18002419a  xor     eax, eax
0x18002419c  mov     rcx, [rbp+var_10]
0x1800241a0  xor     rcx, rsp; StackCookie
0x1800241a3  call    __security_check_cookie
0x1800241a8  mov     rbx, [rsp+70h+arg_0]
0x1800241b0  add     rsp, 70h
0x1800241b4  pop     r15
0x1800241b6  pop     r14
0x1800241b8  pop     r13
0x1800241ba  pop     r12
0x1800241bc  pop     rdi
0x1800241bd  pop     rsi
0x1800241be  pop     rbp
0x1800241bf  retn
```
