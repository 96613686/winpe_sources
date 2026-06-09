# NgcGetCallerSid

- ea: `0x180010a40`
- end: `0x180010b4b`
- name: `NgcGetCallerSid`
- size: `267`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a594`
- `0x18000a5b4`
- `0x18000cfcc`
- `0x180010a40`
- `0x18001a4d0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010b07`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010b07`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180010adb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180010adb`

## string_xrefs

- `0x180010a5f`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180010aa8`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180010aea`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcGetCallerSid(LPWSTR *a1)
{
  __int64 result; // rax
  int UserSidFromToken; // eax
  unsigned int v4; // edi
  const char *v5; // r9
  const char *v6; // r9
  unsigned int LastError; // ebx
  LPWSTR v8; // rax
  PSID Sid[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v10; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPWSTR StringSid; // [rsp+50h] [rbp+8h] BYREF

  if ( a1 )
  {
    *a1 = 0;
    *(_OWORD *)Sid = 0;
    v10 = 0;
    try
    {
      UserSidFromToken = NgcUtils::GetUserSidFromToken((__int64)a1, Sid);
      v4 = UserSidFromToken;
      if ( UserSidFromToken >= 0 )
      {
        StringSid = 0;
        if ( ConvertSidToStringSidW(Sid[0], &StringSid) )
        {
          v8 = StringSid;
          StringSid = 0;
          *a1 = v8;
          std::vector<unsigned char>::~vector<unsigned char>(Sid);
          result = 0;
        }
        else
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x1BD,
                        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
                        v6);
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
          (void *)0x1BA,
          (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
          (const char *)(unsigned int)UserSidFromToken,
          (int)Sid[0]);
        std::vector<unsigned char>::~vector<unsigned char>(Sid);
        result = v4;
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x1C3,
                             (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
                             v5);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B6,
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
0x180010a40  mov     [rsp+arg_8], rbx
0x180010a45  push    rdi
0x180010a46  sub     rsp, 40h
0x180010a4a  mov     rbx, rcx
0x180010a4d  test    rcx, rcx
0x180010a50  jnz     short loc_180010A77
0x180010a52  mov     rcx, [rsp+48h]; this
0x180010a57  mov     ebx, 80004003h
0x180010a5c  mov     r9d, ebx; char *
0x180010a5f  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180010a66  mov     edx, 1B6h; void *
0x180010a6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010a70  mov     eax, ebx
0x180010a72  jmp     loc_180010B3F
0x180010a77  mov     qword ptr [rcx], 0
0x180010a7e  xorps   xmm0, xmm0
0x180010a81  movdqu  xmmword ptr [rsp+48h+Sid], xmm0; int
0x180010a87  mov     [rsp+48h+var_18], 0
0x180010a90  lea     rdx, [rsp+48h+Sid]
0x180010a95  call    NgcUtils__GetUserSidFromToken
0x180010a9a  mov     edi, eax
0x180010a9c  test    eax, eax
0x180010a9e  jns     short loc_180010AC8
0x180010aa0  mov     rcx, [rsp+48h]; this
0x180010aa5  mov     r9d, eax; char *
0x180010aa8  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180010aaf  mov     edx, 1BAh; void *
0x180010ab4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010ab9  nop
0x180010aba  lea     rcx, [rsp+48h+Sid]
0x180010abf  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180010ac4  mov     eax, edi
0x180010ac6  jmp     short loc_180010B3F
0x180010ac8  mov     [rsp+48h+StringSid], 0
0x180010ad1  lea     rdx, [rsp+48h+StringSid]; StringSid
0x180010ad6  mov     rcx, [rsp+48h+Sid]; Sid
0x180010adb  call    cs:__imp_ConvertSidToStringSidW
0x180010ae1  test    eax, eax
0x180010ae3  jnz     short loc_180010B1C
0x180010ae5  mov     rcx, [rsp+48h]; this
0x180010aea  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180010af1  mov     edx, 1BDh; void *
0x180010af6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010afb  mov     ebx, eax
0x180010afd  mov     rcx, [rsp+48h+StringSid]; hMem
0x180010b02  test    rcx, rcx
0x180010b05  jz      short loc_180010B0E
0x180010b07  call    cs:__imp_LocalFree
0x180010b0d  nop
0x180010b0e  lea     rcx, [rsp+48h+Sid]
0x180010b13  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180010b18  mov     eax, ebx
0x180010b1a  jmp     short loc_180010B3F
0x180010b1c  mov     rax, [rsp+48h+StringSid]
0x180010b21  mov     [rsp+48h+StringSid], 0
0x180010b2a  mov     [rbx], rax
0x180010b2d  lea     rcx, [rsp+48h+Sid]
0x180010b32  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180010b37  xor     eax, eax
0x180010b39  jmp     short loc_180010B3F
0x180010b3b  mov     eax, dword ptr [rsp+48h+StringSid]
0x180010b3f  mov     rbx, [rsp+48h+arg_8]
0x180010b44  add     rsp, 40h
0x180010b48  pop     rdi
0x180010b49  retn
```
