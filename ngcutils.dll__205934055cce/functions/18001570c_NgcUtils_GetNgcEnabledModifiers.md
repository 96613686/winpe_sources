# NgcUtils::GetNgcEnabledModifiers

- ea: `0x18001570c`
- end: `0x1800158bc`
- name: `NgcUtils::GetNgcEnabledModifiers`
- size: `432`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800112c0`
- `0x1800115d0`
- `0x180015bec`

## callees

- `0x18000a594`
- `0x18000a5b4`
- `0x18000cfcc`
- `0x18001570c`
- `0x18001a4d0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015801`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001587d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015801`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001587d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800157d9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800157d9`
- `dsreg!DsrFreeJoinInfo` at `0x180015763`
- `dsreg!DsrFreeJoinInfo` at `0x180015897`
- `dsreg!DsrFreeJoinInfo` at `0x1800158b4`
- `dsreg!DsrFreeJoinInfo` at `0x180015763`
- `dsreg!DsrFreeJoinInfo` at `0x180015897`
- `dsreg!DsrFreeJoinInfo` at `0x1800158b4`
- `dsreg!DsrGetJoinInfo` at `0x180015735`
- `dsreg!DsrGetJoinInfo` at `0x180015735`
- `cryptngc!NgcQueryEnabled` at `0x18001584e`
- `cryptngc!NgcQueryEnabled` at `0x18001584e`

## string_xrefs

- `0x180015748`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`
- `0x1800157ac`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`
- `0x1800157e7`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`
- `0x180015861`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NgcUtils::GetNgcEnabledModifiers(_DWORD *a1)
{
  int JoinInfo; // eax
  unsigned int LastError; // ebx
  __int64 v4; // rdx
  int UserSidFromToken; // eax
  const char *v7; // r9
  int v8; // eax
  __int64 v9; // rdx
  int v10; // [rsp+20h] [rbp-40h]
  __int64 v11; // [rsp+30h] [rbp-30h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-28h] BYREF
  PSID Sid[2]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v14; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  int v16; // [rsp+90h] [rbp+30h] BYREF
  int v17; // [rsp+98h] [rbp+38h] BYREF

  if ( dword_180077538 )
    goto LABEL_22;
  v11 = 0;
  JoinInfo = DsrGetJoinInfo(0, &v11);
  LastError = JoinInfo;
  if ( JoinInfo >= 0 )
  {
    if ( !v11 || !*(_DWORD *)v11 )
    {
      if ( v11 )
        ((void (*)(void))DsrFreeJoinInfo)();
      return 0;
    }
    *(_OWORD *)Sid = 0;
    v14 = 0;
    UserSidFromToken = NgcUtils::GetUserSidFromToken(v11, Sid);
    LastError = UserSidFromToken;
    if ( UserSidFromToken < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6B,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\policyutils.cpp",
        (const char *)(unsigned int)UserSidFromToken,
        v10);
LABEL_11:
      std::vector<unsigned char>::~vector<unsigned char>(Sid);
      goto LABEL_4;
    }
    StringSid = 0;
    if ( !ConvertSidToStringSidW(Sid[0], &StringSid) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x6E,
                    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\policyutils.cpp",
                    v7);
      goto LABEL_14;
    }
    v17 = 2;
    v16 = 0;
    dword_180077538 |= 0x20u;
    v8 = NgcQueryEnabled(StringSid, *(_QWORD *)(v11 + 32), &v17, &v16);
    LastError = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7A,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\policyutils.cpp",
        (const char *)(unsigned int)v8,
        (int)&dword_180077538);
LABEL_14:
      if ( StringSid )
        LocalFree(StringSid);
      goto LABEL_11;
    }
    if ( StringSid )
      LocalFree(StringSid);
    std::vector<unsigned char>::~vector<unsigned char>(Sid);
    if ( v11 )
      DsrFreeJoinInfo(v11, v9);
LABEL_22:
    *a1 = dword_180077538;
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x63,
    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\policyutils.cpp",
    (const char *)(unsigned int)JoinInfo,
    v10);
LABEL_4:
  if ( v11 )
    DsrFreeJoinInfo(v11, v4);
  return LastError;
}

```

## disassembly

```asm
0x18001570c  push    rbp
0x18001570e  push    rbx
0x18001570f  push    rdi
0x180015710  mov     rbp, rsp
0x180015713  sub     rsp, 60h
0x180015717  mov     rdi, rcx
0x18001571a  cmp     cs:dword_180077538, 0
0x180015721  jnz     loc_18001589D
0x180015727  mov     [rbp+var_30], 0
0x18001572f  lea     rdx, [rbp+var_30]
0x180015733  xor     ecx, ecx
0x180015735  call    cs:__imp_DsrGetJoinInfo
0x18001573b  mov     ebx, eax
0x18001573d  test    eax, eax
0x18001573f  jns     short loc_180015770
0x180015741  mov     rcx, [rbp+18h]; this
0x180015745  mov     r9d, eax; char *
0x180015748  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001574f  mov     edx, 63h ; 'c'; void *
0x180015754  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015759  nop
0x18001575a  mov     rcx, [rbp+var_30]
0x18001575e  test    rcx, rcx
0x180015761  jz      short loc_180015769
0x180015763  call    cs:__imp_DsrFreeJoinInfo
0x180015769  mov     eax, ebx
0x18001576b  jmp     loc_1800158A7
0x180015770  mov     rcx, [rbp+var_30]
0x180015774  test    rcx, rcx
0x180015777  jz      loc_1800158AF
0x18001577d  cmp     dword ptr [rcx], 0
0x180015780  jz      loc_1800158AF
0x180015786  xorps   xmm0, xmm0
0x180015789  movdqu  xmmword ptr [rbp+Sid], xmm0
0x18001578e  mov     [rbp+var_10], 0
0x180015796  lea     rdx, [rbp+Sid]
0x18001579a  call    NgcUtils__GetUserSidFromToken
0x18001579f  mov     ebx, eax
0x1800157a1  test    eax, eax
0x1800157a3  jns     short loc_1800157C9
0x1800157a5  mov     rcx, [rbp+18h]; this
0x1800157a9  mov     r9d, eax; char *
0x1800157ac  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800157b3  mov     edx, 6Bh ; 'k'; void *
0x1800157b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800157bd  nop
0x1800157be  lea     rcx, [rbp+Sid]
0x1800157c2  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x1800157c7  jmp     short loc_18001575A
0x1800157c9  mov     [rbp+StringSid], 0
0x1800157d1  lea     rdx, [rbp+StringSid]; StringSid
0x1800157d5  mov     rcx, [rbp+Sid]; Sid
0x1800157d9  call    cs:__imp_ConvertSidToStringSidW
0x1800157df  test    eax, eax
0x1800157e1  jnz     short loc_180015809
0x1800157e3  mov     rcx, [rbp+18h]; this
0x1800157e7  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800157ee  lea     edx, [rax+6Eh]; void *
0x1800157f1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800157f6  mov     ebx, eax
0x1800157f8  mov     rcx, [rbp+StringSid]; hMem
0x1800157fc  test    rcx, rcx
0x1800157ff  jz      short loc_1800157BE
0x180015801  call    cs:__imp_LocalFree
0x180015807  jmp     short loc_1800157BE
0x180015809  mov     [rbp+arg_18], 2
0x180015810  mov     [rbp+arg_10], 0
0x180015817  mov     [rbp+arg_8], 0
0x18001581e  or      cs:dword_180077538, 20h
0x180015825  lea     rax, [rbp+arg_8]
0x180015829  mov     [rsp+60h+var_38], rax
0x18001582e  lea     rax, dword_180077538
0x180015835  mov     qword ptr [rsp+60h+var_40], rax; int
0x18001583a  lea     r9, [rbp+arg_10]
0x18001583e  lea     r8, [rbp+arg_18]
0x180015842  mov     rdx, [rbp+var_30]
0x180015846  mov     rdx, [rdx+20h]
0x18001584a  mov     rcx, [rbp+StringSid]
0x18001584e  call    cs:__imp_NgcQueryEnabled
0x180015854  mov     ebx, eax
0x180015856  test    eax, eax
0x180015858  jns     short loc_180015874
0x18001585a  mov     rcx, [rbp+18h]; this
0x18001585e  mov     r9d, eax; char *
0x180015861  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180015868  mov     edx, 7Ah ; 'z'; void *
0x18001586d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015872  jmp     short loc_1800157F8
0x180015874  mov     rcx, [rbp+StringSid]; hMem
0x180015878  test    rcx, rcx
0x18001587b  jz      short loc_180015884
0x18001587d  call    cs:__imp_LocalFree
0x180015883  nop
0x180015884  lea     rcx, [rbp+Sid]
0x180015888  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18001588d  nop
0x18001588e  mov     rcx, [rbp+var_30]
0x180015892  test    rcx, rcx
0x180015895  jz      short loc_18001589D
0x180015897  call    cs:__imp_DsrFreeJoinInfo
0x18001589d  mov     eax, cs:dword_180077538
0x1800158a3  mov     [rdi], eax
0x1800158a5  xor     eax, eax
0x1800158a7  add     rsp, 60h
0x1800158ab  pop     rdi
0x1800158ac  pop     rbx
0x1800158ad  pop     rbp
0x1800158ae  retn
0x1800158af  test    rcx, rcx
0x1800158b2  jz      short loc_1800158A5
0x1800158b4  call    cs:__imp_DsrFreeJoinInfo
0x1800158ba  jmp     short loc_1800158A5
```
