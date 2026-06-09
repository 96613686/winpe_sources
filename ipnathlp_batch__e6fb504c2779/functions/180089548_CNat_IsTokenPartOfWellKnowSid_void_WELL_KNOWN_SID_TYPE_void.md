# CNat::IsTokenPartOfWellKnowSid(void *,WELL_KNOWN_SID_TYPE,void * &)

- ea: `0x180089548`
- end: `0x1800896c2`
- name: `?IsTokenPartOfWellKnowSid@CNat@@AEAA_NPEAXW4WELL_KNOWN_SID_TYPE@@AEAPEAX@Z`
- size: `378`
- prototype: `bool(CNat *__hidden this, void *, enum WELL_KNOWN_SID_TYPE, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180033e0c`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x1800893d0`
- `0x180089548`
- `0x180089b68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008959e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008959e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800895ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800895ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089643`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089643`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18008961b`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18008961b`

## pseudocode

```c
char __fastcall CNat::IsTokenPartOfWellKnowSid(CNat *this, void *a2, enum WELL_KNOWN_SID_TYPE a3, void **a4)
{
  char SecuritySID; // bl
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
0x180089548  mov     [rsp+arg_8], rbx
0x18008954d  mov     [rsp+arg_10], rbp
0x180089552  push    rsi
0x180089553  push    rdi
0x180089554  push    r15
0x180089556  sub     rsp, 30h
0x18008955a  mov     rsi, r9
0x18008955d  mov     ebx, r8d
0x180089560  mov     rbp, rdx
0x180089563  mov     rdi, rcx
0x180089566  mov     rcx, cs:WPP_GLOBAL_Control
0x18008956d  lea     r15, WPP_GLOBAL_Control
0x180089574  cmp     rcx, r15
0x180089577  jz      short loc_18008959A
0x180089579  test    byte ptr [rcx+1Ch], 1
0x18008957d  jz      short loc_18008959A
0x18008957f  cmp     byte ptr [rcx+19h], 6
0x180089583  jb      short loc_18008959A
0x180089585  mov     rcx, [rcx+10h]
0x180089589  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x180089590  mov     edx, 10h
0x180089595  call    WPP_SF_
0x18008959a  lea     rcx, [rdi+48h]; lpCriticalSection
0x18008959e  call    cs:__imp_EnterCriticalSection
0x1800895a5  nop     dword ptr [rax+rax+00h]
0x1800895aa  mov     rdx, rsi; void **
0x1800895ad  mov     ecx, ebx; WellKnownSidType
0x1800895af  call    ?GetSecuritySID@@YA_NW4WELL_KNOWN_SID_TYPE@@AEAPEAX@Z; GetSecuritySID(WELL_KNOWN_SID_TYPE,void * &)
0x1800895b4  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800895b8  mov     bl, al
0x1800895ba  call    cs:__imp_LeaveCriticalSection
0x1800895c1  nop     dword ptr [rax+rax+00h]
0x1800895c6  test    bl, bl
0x1800895c8  jnz     short loc_180089608
0x1800895ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800895d1  cmp     rcx, r15
0x1800895d4  jz      loc_1800896A8
0x1800895da  test    byte ptr [rcx+1Ch], 1
0x1800895de  jz      loc_1800896A8
0x1800895e4  cmp     byte ptr [rcx+19h], 4
0x1800895e8  jb      loc_1800896A8
0x1800895ee  mov     rcx, [rcx+10h]
0x1800895f2  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x1800895f9  mov     edx, 11h
0x1800895fe  call    WPP_SF_
0x180089603  jmp     loc_1800896A8
0x180089608  mov     rdx, [rsi]; SidToCheck
0x18008960b  lea     r8, [rsp+48h+IsMember]; IsMember
0x180089610  mov     rcx, rbp; TokenHandle
0x180089613  mov     [rsp+48h+IsMember], 0
0x18008961b  call    cs:__imp_CheckTokenMembership
0x180089622  nop     dword ptr [rax+rax+00h]
0x180089627  test    eax, eax
0x180089629  jnz     short loc_180089670
0x18008962b  mov     rax, cs:WPP_GLOBAL_Control
0x180089632  cmp     rax, r15
0x180089635  jz      short loc_1800896A8
0x180089637  test    byte ptr [rax+1Ch], 1
0x18008963b  jz      short loc_1800896A8
0x18008963d  cmp     byte ptr [rax+19h], 2
0x180089641  jb      short loc_1800896A8
0x180089643  call    cs:__imp_GetLastError
0x18008964a  nop     dword ptr [rax+rax+00h]
0x18008964f  mov     rcx, cs:WPP_GLOBAL_Control
0x180089656  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x18008965d  mov     edx, 12h
0x180089662  mov     r9d, eax
0x180089665  mov     rcx, [rcx+10h]
0x180089669  call    WPP_SF_d
0x18008966e  jmp     short loc_1800896A8
0x180089670  cmp     [rsp+48h+IsMember], 0
0x180089675  jnz     short loc_1800896AC
0x180089677  mov     rcx, cs:WPP_GLOBAL_Control
0x18008967e  cmp     rcx, r15
0x180089681  jz      short loc_1800896A8
0x180089683  test    byte ptr [rcx+1Ch], 1
0x180089687  jz      short loc_1800896A8
0x180089689  cmp     byte ptr [rcx+19h], 4
0x18008968d  jb      short loc_1800896A8
0x18008968f  mov     rax, [rsi]
0x180089692  mov     edx, 13h
0x180089697  mov     rcx, [rcx+10h]
0x18008969b  mov     r9, rbp
0x18008969e  mov     [rsp+48h+var_28], rax
0x1800896a3  call    WPP_SF_qq
0x1800896a8  xor     al, al
0x1800896aa  jmp     short loc_1800896AE
0x1800896ac  mov     al, 1
0x1800896ae  mov     rbx, [rsp+48h+arg_8]
0x1800896b3  mov     rbp, [rsp+48h+arg_10]
0x1800896b8  add     rsp, 30h
0x1800896bc  pop     r15
0x1800896be  pop     rdi
0x1800896bf  pop     rsi
0x1800896c0  retn
```
