# CNat::IsTokenPartOfWellKnowSid(void *,WELL_KNOWN_SID_TYPE,void * &)

- ea: `0x180082dc8`
- end: `0x180082f29`
- name: `?IsTokenPartOfWellKnowSid@CNat@@AEAA_NPEAXW4WELL_KNOWN_SID_TYPE@@AEAPEAX@Z`
- size: `353`
- prototype: `bool(CNat *__hidden this, void *, enum WELL_KNOWN_SID_TYPE, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180031790`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x180082c6c`
- `0x180082dc8`
- `0x18008339c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180082e1e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180082e1e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180082e34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180082e34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082eb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082eb1`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180082e8f`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180082e8f`

## pseudocode

```c
char __fastcall CNat::IsTokenPartOfWellKnowSid(CNat *this, void *a2, enum WELL_KNOWN_SID_TYPE a3, void **a4)
{
  bool SecuritySID; // bl
  void *v9; // rdx
  __int64 v10; // r8
  DWORD LastError; // eax
  WINBOOL IsMember; // [rsp+50h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_8ab209e1ee763061284517a200f37d51_Traceguids);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  SecuritySID = GetSecuritySID(a3, a4);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  if ( !SecuritySID )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_8ab209e1ee763061284517a200f37d51_Traceguids);
    }
    return 0;
  }
  v9 = *a4;
  IsMember = 0;
  if ( !CheckTokenMembership(a2, v9, &IsMember) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_8ab209e1ee763061284517a200f37d51_Traceguids, LastError);
    }
    return 0;
  }
  if ( !IsMember )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, v10, a2, *a4);
    }
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180082dc8  mov     [rsp+arg_8], rbx
0x180082dcd  mov     [rsp+arg_10], rbp
0x180082dd2  push    rsi
0x180082dd3  push    rdi
0x180082dd4  push    r15
0x180082dd6  sub     rsp, 30h
0x180082dda  mov     rsi, r9
0x180082ddd  mov     ebx, r8d
0x180082de0  mov     rbp, rdx
0x180082de3  mov     rdi, rcx
0x180082de6  mov     rcx, cs:WPP_GLOBAL_Control
0x180082ded  lea     r15, WPP_GLOBAL_Control
0x180082df4  cmp     rcx, r15
0x180082df7  jz      short loc_180082E1A
0x180082df9  test    byte ptr [rcx+1Ch], 1
0x180082dfd  jz      short loc_180082E1A
0x180082dff  cmp     byte ptr [rcx+19h], 6
0x180082e03  jb      short loc_180082E1A
0x180082e05  mov     rcx, [rcx+10h]
0x180082e09  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x180082e10  mov     edx, 10h
0x180082e15  call    WPP_SF_
0x180082e1a  lea     rcx, [rdi+48h]; lpCriticalSection
0x180082e1e  call    cs:__imp_EnterCriticalSection
0x180082e24  mov     rdx, rsi; void **
0x180082e27  mov     ecx, ebx; WellKnownSidType
0x180082e29  call    ?GetSecuritySID@@YA_NW4WELL_KNOWN_SID_TYPE@@AEAPEAX@Z; GetSecuritySID(WELL_KNOWN_SID_TYPE,void * &)
0x180082e2e  lea     rcx, [rdi+48h]; lpCriticalSection
0x180082e32  mov     bl, al
0x180082e34  call    cs:__imp_LeaveCriticalSection
0x180082e3a  test    bl, bl
0x180082e3c  jnz     short loc_180082E7C
0x180082e3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180082e45  cmp     rcx, r15
0x180082e48  jz      loc_180082F10
0x180082e4e  test    byte ptr [rcx+1Ch], 1
0x180082e52  jz      loc_180082F10
0x180082e58  cmp     byte ptr [rcx+19h], 4
0x180082e5c  jb      loc_180082F10
0x180082e62  mov     rcx, [rcx+10h]
0x180082e66  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x180082e6d  mov     edx, 11h
0x180082e72  call    WPP_SF_
0x180082e77  jmp     loc_180082F10
0x180082e7c  mov     rdx, [rsi]; SidToCheck
0x180082e7f  lea     r8, [rsp+48h+IsMember]; IsMember
0x180082e84  mov     rcx, rbp; TokenHandle
0x180082e87  mov     [rsp+48h+IsMember], 0
0x180082e8f  call    cs:__imp_CheckTokenMembership
0x180082e95  test    eax, eax
0x180082e97  jnz     short loc_180082ED8
0x180082e99  mov     rax, cs:WPP_GLOBAL_Control
0x180082ea0  cmp     rax, r15
0x180082ea3  jz      short loc_180082F10
0x180082ea5  test    byte ptr [rax+1Ch], 1
0x180082ea9  jz      short loc_180082F10
0x180082eab  cmp     byte ptr [rax+19h], 2
0x180082eaf  jb      short loc_180082F10
0x180082eb1  call    cs:__imp_GetLastError
0x180082eb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180082ebe  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x180082ec5  mov     edx, 12h
0x180082eca  mov     r9d, eax
0x180082ecd  mov     rcx, [rcx+10h]
0x180082ed1  call    WPP_SF_d
0x180082ed6  jmp     short loc_180082F10
0x180082ed8  cmp     [rsp+48h+IsMember], 0
0x180082edd  jnz     short loc_180082F14
0x180082edf  mov     rcx, cs:WPP_GLOBAL_Control
0x180082ee6  cmp     rcx, r15
0x180082ee9  jz      short loc_180082F10
0x180082eeb  test    byte ptr [rcx+1Ch], 1
0x180082eef  jz      short loc_180082F10
0x180082ef1  cmp     byte ptr [rcx+19h], 4
0x180082ef5  jb      short loc_180082F10
0x180082ef7  mov     rax, [rsi]
0x180082efa  mov     edx, 13h
0x180082eff  mov     rcx, [rcx+10h]
0x180082f03  mov     r9, rbp
0x180082f06  mov     [rsp+48h+var_28], rax
0x180082f0b  call    WPP_SF_qq
0x180082f10  xor     al, al
0x180082f12  jmp     short loc_180082F16
0x180082f14  mov     al, 1
0x180082f16  mov     rbx, [rsp+48h+arg_8]
0x180082f1b  mov     rbp, [rsp+48h+arg_10]
0x180082f20  add     rsp, 30h
0x180082f24  pop     r15
0x180082f26  pop     rdi
0x180082f27  pop     rsi
0x180082f28  retn
```
