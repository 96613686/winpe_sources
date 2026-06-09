# NgcGetUserSid

- ea: `0x180011190`
- end: `0x1800112ba`
- name: `NgcGetUserSid`
- size: `298`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a594`
- `0x18000a5b4`
- `0x18000cfcc`
- `0x180011190`
- `0x18001a1fc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011265`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011265`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180011239`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180011239`

## string_xrefs

- `0x1800111b7`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180011203`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180011248`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcGetUserSid(const WCHAR *a1, LPWSTR *a2, _DWORD *a3)
{
  __int64 result; // rax
  int UserSid; // eax
  unsigned int v7; // ebx
  const char *v8; // r9
  const char *v9; // r9
  unsigned int LastError; // ebx
  LPWSTR v11; // rax
  PSID Sid[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v13; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPWSTR StringSid; // [rsp+68h] [rbp+20h] BYREF

  if ( a2 )
  {
    *(_OWORD *)Sid = 0;
    v13 = 0;
    try
    {
      UserSid = NgcUtils::GetUserSid(a1);
      v7 = UserSid;
      if ( UserSid >= 0 )
      {
        StringSid = 0;
        if ( ConvertSidToStringSidW(Sid[0], &StringSid) )
        {
          v11 = StringSid;
          StringSid = 0;
          *a2 = v11;
          if ( a3 )
            *a3 = 0;
          std::vector<unsigned char>::~vector<unsigned char>(Sid);
          result = 0;
        }
        else
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x1CE,
                        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
                        v9);
          if ( StringSid )
            LocalFree(StringSid);
          std::vector<unsigned char>::~vector<unsigned char>(Sid);
          result = LastError;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1CB,
          (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
          (const char *)(unsigned int)UserSid,
          (int)Sid[0]);
        std::vector<unsigned char>::~vector<unsigned char>(Sid);
        result = v7;
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x1DA,
                             (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
                             v8);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C7,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
      (const char *)0x80004003LL,
      (int)Sid[0]);
    return 2147500035LL;
  }
  return result;
}

```

## disassembly

```asm
0x180011190  mov     [rsp+arg_0], rbx
0x180011195  mov     [rsp+arg_10], rsi
0x18001119a  push    rdi
0x18001119b  sub     rsp, 40h
0x18001119f  mov     rdi, r8
0x1800111a2  mov     rsi, rdx
0x1800111a5  test    rdx, rdx
0x1800111a8  jnz     short loc_1800111CF
0x1800111aa  mov     rcx, [rsp+48h]; this
0x1800111af  mov     ebx, 80004003h
0x1800111b4  mov     r9d, ebx; char *
0x1800111b7  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800111be  mov     edx, 1C7h; void *
0x1800111c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800111c8  mov     eax, ebx
0x1800111ca  jmp     loc_1800112A9
0x1800111cf  xorps   xmm0, xmm0
0x1800111d2  movdqu  xmmword ptr [rsp+48h+Sid], xmm0; int
0x1800111d8  mov     [rsp+48h+var_18], 0
0x1800111e1  mov     byte ptr [rsp+48h+arg_8], 0
0x1800111e6  lea     r8, [rsp+48h+arg_8]
0x1800111eb  lea     rdx, [rsp+48h+Sid]
0x1800111f0  call    ?GetUserSid@NgcUtils@@YAJPEBGPEAV?$vector@EV?$allocator@E@std@@@std@@PEA_N@Z; NgcUtils::GetUserSid(ushort const *,std::vector<uchar> *,bool *)
0x1800111f5  mov     ebx, eax
0x1800111f7  test    eax, eax
0x1800111f9  jns     short loc_180011226
0x1800111fb  mov     rcx, [rsp+48h]; this
0x180011200  mov     r9d, eax; char *
0x180011203  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001120a  mov     edx, 1CBh; void *
0x18001120f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011214  nop
0x180011215  lea     rcx, [rsp+48h+Sid]
0x18001121a  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18001121f  mov     eax, ebx
0x180011221  jmp     loc_1800112A9
0x180011226  mov     [rsp+48h+StringSid], 0
0x18001122f  lea     rdx, [rsp+48h+StringSid]; StringSid
0x180011234  mov     rcx, [rsp+48h+Sid]; Sid
0x180011239  call    cs:__imp_ConvertSidToStringSidW
0x18001123f  test    eax, eax
0x180011241  jnz     short loc_18001127A
0x180011243  mov     rcx, [rsp+48h]; this
0x180011248  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001124f  mov     edx, 1CEh; void *
0x180011254  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011259  mov     ebx, eax
0x18001125b  mov     rcx, [rsp+48h+StringSid]; hMem
0x180011260  test    rcx, rcx
0x180011263  jz      short loc_18001126C
0x180011265  call    cs:__imp_LocalFree
0x18001126b  nop
0x18001126c  lea     rcx, [rsp+48h+Sid]
0x180011271  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180011276  mov     eax, ebx
0x180011278  jmp     short loc_1800112A9
0x18001127a  mov     rax, [rsp+48h+StringSid]
0x18001127f  mov     [rsp+48h+StringSid], 0
0x180011288  mov     [rsi], rax
0x18001128b  test    rdi, rdi
0x18001128e  jz      short loc_180011297
0x180011290  movzx   eax, byte ptr [rsp+48h+arg_8]
0x180011295  mov     [rdi], eax
0x180011297  lea     rcx, [rsp+48h+Sid]
0x18001129c  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x1800112a1  xor     eax, eax
0x1800112a3  jmp     short loc_1800112A9
0x1800112a5  mov     eax, [rsp+48h+arg_8]
0x1800112a9  mov     rbx, [rsp+48h+arg_0]
0x1800112ae  mov     rsi, [rsp+48h+arg_10]
0x1800112b3  add     rsp, 40h
0x1800112b7  pop     rdi
0x1800112b8  retn
```
