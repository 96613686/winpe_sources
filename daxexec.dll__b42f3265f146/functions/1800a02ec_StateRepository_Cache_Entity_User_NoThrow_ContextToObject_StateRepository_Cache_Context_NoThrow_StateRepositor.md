# StateRepository::Cache::Entity::User_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::User_NoThrow &,StateRepository::Cache::Entity::User_NoThrow::CacheFlags,__int64)

- ea: `0x1800a02ec`
- end: `0x1800a04ea`
- name: `?ContextToObject@User_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `510`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a0b04`

## callees

- `0x18000b126`
- `0x18000ff04`
- `0x18000ff24`
- `0x1800a02ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a0431`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a0431`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0412`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0412`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0423`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0469`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a04ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0423`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0469`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a04ad`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800a0486`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800a0486`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800a03ed`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800a03ed`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800a032f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800a032f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a0377`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a03ac`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a04c7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a0377`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a03ac`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a04c7`

## string_xrefs

- `0x1800a0348`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800a038e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x1800a044d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x1800a0325`: `UserSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall StateRepository::Cache::Entity::User_NoThrow::ContextToObject(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  int Field_String; // eax
  int v7; // ebx
  __int64 v8; // rcx
  LPCWSTR v9; // rcx
  LPCWSTR v11; // rcx
  const char *v12; // r9
  BOOL v13; // r12d
  PSID v14; // r15
  _QWORD *v15; // rdi
  void *v16; // r14
  DWORD LastError; // ebx
  HLOCAL v18; // rbx
  DWORD LengthSid; // eax
  HLOCAL hMem; // [rsp+20h] [rbp-28h] BYREF
  _QWORD *p_StringSid; // [rsp+28h] [rbp-20h]
  PSID Sid; // [rsp+30h] [rbp-18h] BYREF
  char v23; // [rsp+38h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]
  LPCWSTR StringSid; // [rsp+A0h] [rbp+58h] BYREF

  StringSid = 0;
  p_StringSid = &StringSid;
  Sid = 0;
  v23 = 1;
  Field_String = SRCacheContext_GetField_String(*a1, L"UserSid", &Sid);
  v7 = Field_String;
  if ( Field_String >= 0 )
    v7 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_String,
      (int)hMem);
  if ( v23 )
  {
    v8 = *p_StringSid;
    *p_StringSid = Sid;
    if ( v8 )
      SRCache_Free();
  }
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x347,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v7,
      (int)hMem);
LABEL_9:
    v9 = StringSid;
    StringSid = 0;
    if ( v9 )
      SRCache_Free();
    return (unsigned int)v7;
  }
  v11 = StringSid;
  if ( StringSid )
  {
    hMem = 0;
    p_StringSid = &hMem;
    Sid = 0;
    v23 = 1;
    v13 = ConvertStringSidToSidW(StringSid, &Sid);
    if ( v23 )
    {
      v14 = Sid;
      v15 = p_StringSid;
      v16 = (void *)*p_StringSid;
      if ( *p_StringSid )
      {
        LastError = GetLastError();
        LocalFree(v16);
        SetLastError(LastError);
      }
      *v15 = v14;
    }
    if ( !v13 )
    {
      v7 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x34F,
             (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
             v12);
      if ( hMem )
        LocalFree(hMem);
      goto LABEL_9;
    }
    v18 = hMem;
    LengthSid = GetLengthSid(hMem);
    memcpy_0(a2 + 1, v18, LengthSid);
    a2[10] = a2 + 1;
    if ( hMem )
      LocalFree(hMem);
    v11 = StringSid;
  }
  else
  {
    a2[10] = 0;
  }
  StringSid = 0;
  if ( v11 )
    SRCache_Free();
  *a2 = a4;
  return 0;
}

```

## disassembly

```asm
0x1800a02ec  mov     [rsp-40h+StringSid], r8
0x1800a02f1  push    rbp
0x1800a02f2  push    rbx
0x1800a02f3  push    rsi
0x1800a02f4  push    rdi
0x1800a02f5  push    r12
0x1800a02f7  push    r13
0x1800a02f9  push    r14
0x1800a02fb  push    r15
0x1800a02fd  mov     rbp, rsp
0x1800a0300  sub     rsp, 48h
0x1800a0304  mov     r13, r9
0x1800a0307  mov     rsi, rdx
0x1800a030a  xor     r14d, r14d
0x1800a030d  mov     [rbp+StringSid], r14
0x1800a0311  lea     rax, [rbp+StringSid]
0x1800a0315  mov     [rbp+var_20], rax
0x1800a0319  mov     [rbp+Sid], r14
0x1800a031d  mov     [rbp+var_10], 1
0x1800a0321  lea     r8, [rbp+Sid]
0x1800a0325  lea     rdx, aUsersid; "UserSid"
0x1800a032c  mov     rcx, [rcx]
0x1800a032f  call    cs:__imp_SRCacheContext_GetField_String
0x1800a0336  nop     dword ptr [rax+rax+00h]
0x1800a033b  mov     ebx, eax
0x1800a033d  test    eax, eax
0x1800a033f  jns     short loc_1800A035B
0x1800a0341  mov     rcx, [rbp+40h]; this
0x1800a0345  mov     r9d, eax; char *
0x1800a0348  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a034f  mov     edx, 246h; void *
0x1800a0354  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0359  jmp     short loc_1800A035E
0x1800a035b  mov     ebx, r14d
0x1800a035e  cmp     [rbp+var_10], r14b
0x1800a0362  jz      short loc_1800A0383
0x1800a0364  mov     rdx, [rbp+var_20]
0x1800a0368  mov     rcx, [rdx]
0x1800a036b  mov     rax, [rbp+Sid]
0x1800a036f  mov     [rdx], rax
0x1800a0372  test    rcx, rcx
0x1800a0375  jz      short loc_1800A0383
0x1800a0377  call    cs:__imp_SRCache_Free
0x1800a037e  nop     dword ptr [rax+rax+00h]
0x1800a0383  test    ebx, ebx
0x1800a0385  jns     short loc_1800A03BF
0x1800a0387  mov     rcx, [rbp+40h]; this
0x1800a038b  mov     r9d, ebx; char *
0x1800a038e  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a0395  mov     edx, 347h; void *
0x1800a039a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a039f  mov     rcx, [rbp+StringSid]
0x1800a03a3  mov     [rbp+StringSid], r14
0x1800a03a7  test    rcx, rcx
0x1800a03aa  jz      short loc_1800A03B8
0x1800a03ac  call    cs:__imp_SRCache_Free
0x1800a03b3  nop     dword ptr [rax+rax+00h]
0x1800a03b8  mov     eax, ebx
0x1800a03ba  jmp     loc_1800A04D8
0x1800a03bf  mov     rcx, [rbp+StringSid]
0x1800a03c3  test    rcx, rcx
0x1800a03c6  jnz     short loc_1800A03D1
0x1800a03c8  mov     [rsi+50h], r14
0x1800a03cc  jmp     loc_1800A04BE
0x1800a03d1  mov     [rbp+hMem], r14
0x1800a03d5  lea     rax, [rbp+hMem]
0x1800a03d9  mov     [rbp+var_20], rax
0x1800a03dd  mov     [rbp+Sid], r14
0x1800a03e1  mov     [rbp+var_10], 1
0x1800a03e5  lea     rdx, [rbp+Sid]; Sid
0x1800a03e9  mov     rcx, [rbp+StringSid]; StringSid
0x1800a03ed  call    cs:__imp_ConvertStringSidToSidW
0x1800a03f4  nop     dword ptr [rax+rax+00h]
0x1800a03f9  mov     r12d, eax
0x1800a03fc  cmp     [rbp+var_10], r14b
0x1800a0400  jz      short loc_1800A0444
0x1800a0402  mov     r15, [rbp+Sid]
0x1800a0406  mov     rdi, [rbp+var_20]
0x1800a040a  mov     r14, [rdi]
0x1800a040d  test    r14, r14
0x1800a0410  jz      short loc_1800A043E
0x1800a0412  call    cs:__imp_GetLastError
0x1800a0419  nop     dword ptr [rax+rax+00h]
0x1800a041e  mov     ebx, eax
0x1800a0420  mov     rcx, r14; hMem
0x1800a0423  call    cs:__imp_LocalFree
0x1800a042a  nop     dword ptr [rax+rax+00h]
0x1800a042f  mov     ecx, ebx; dwErrCode
0x1800a0431  call    cs:__imp_SetLastError
0x1800a0438  nop     dword ptr [rax+rax+00h]
0x1800a043d  nop
0x1800a043e  mov     [rdi], r15
0x1800a0441  xor     r14d, r14d
0x1800a0444  test    r12d, r12d
0x1800a0447  jnz     short loc_1800A047B
0x1800a0449  mov     rcx, [rbp+40h]; this
0x1800a044d  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a0454  mov     edx, 34Fh; void *
0x1800a0459  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a045e  mov     ebx, eax
0x1800a0460  mov     rcx, [rbp+hMem]; hMem
0x1800a0464  test    rcx, rcx
0x1800a0467  jz      short loc_1800A0476
0x1800a0469  call    cs:__imp_LocalFree
0x1800a0470  nop     dword ptr [rax+rax+00h]
0x1800a0475  nop
0x1800a0476  jmp     loc_1800A039F
0x1800a047b  mov     rbx, [rbp+hMem]
0x1800a047f  lea     rdi, [rsi+8]
0x1800a0483  mov     rcx, rbx; pSid
0x1800a0486  call    cs:__imp_GetLengthSid
0x1800a048d  nop     dword ptr [rax+rax+00h]
0x1800a0492  mov     r8d, eax; Size
0x1800a0495  mov     rdx, rbx; Src
0x1800a0498  mov     rcx, rdi; void *
0x1800a049b  call    memcpy_0
0x1800a04a0  mov     [rsi+50h], rdi
0x1800a04a4  mov     rcx, [rbp+hMem]; hMem
0x1800a04a8  test    rcx, rcx
0x1800a04ab  jz      short loc_1800A04BA
0x1800a04ad  call    cs:__imp_LocalFree
0x1800a04b4  nop     dword ptr [rax+rax+00h]
0x1800a04b9  nop
0x1800a04ba  mov     rcx, [rbp+StringSid]
0x1800a04be  mov     [rbp+StringSid], r14
0x1800a04c2  test    rcx, rcx
0x1800a04c5  jz      short loc_1800A04D3
0x1800a04c7  call    cs:__imp_SRCache_Free
0x1800a04ce  nop     dword ptr [rax+rax+00h]
0x1800a04d3  mov     [rsi], r13
0x1800a04d6  xor     eax, eax
0x1800a04d8  add     rsp, 48h
0x1800a04dc  pop     r15
0x1800a04de  pop     r14
0x1800a04e0  pop     r13
0x1800a04e2  pop     r12
0x1800a04e4  pop     rdi
0x1800a04e5  pop     rsi
0x1800a04e6  pop     rbx
0x1800a04e7  pop     rbp
0x1800a04e8  retn
```
