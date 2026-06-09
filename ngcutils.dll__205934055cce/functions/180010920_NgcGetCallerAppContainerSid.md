# NgcGetCallerAppContainerSid

- ea: `0x180010920`
- end: `0x180010a2b`
- name: `NgcGetCallerAppContainerSid`
- size: `267`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a594`
- `0x18000a5b4`
- `0x18000cfcc`
- `0x180010920`
- `0x1800191c4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800109e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800109e7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800109bb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800109bb`

## string_xrefs

- `0x18001093f`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180010988`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x1800109ca`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcGetCallerAppContainerSid(LPWSTR *a1)
{
  __int64 result; // rax
  int CallerAppContainerSid; // eax
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
      CallerAppContainerSid = NgcUtils::GetCallerAppContainerSid(Sid);
      v4 = CallerAppContainerSid;
      if ( CallerAppContainerSid >= 0 )
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
                        (void *)0x1AD,
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
          (void *)0x1AA,
          (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
          (const char *)(unsigned int)CallerAppContainerSid,
          (int)Sid[0]);
        std::vector<unsigned char>::~vector<unsigned char>(Sid);
        result = v4;
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x1B2,
                             (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
                             v5);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
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
0x180010920  mov     [rsp+arg_8], rbx
0x180010925  push    rdi
0x180010926  sub     rsp, 40h
0x18001092a  mov     rbx, rcx
0x18001092d  test    rcx, rcx
0x180010930  jnz     short loc_180010957
0x180010932  mov     rcx, [rsp+48h]; this
0x180010937  mov     ebx, 80004003h
0x18001093c  mov     r9d, ebx; char *
0x18001093f  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180010946  mov     edx, 1A6h; void *
0x18001094b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010950  mov     eax, ebx
0x180010952  jmp     loc_180010A1F
0x180010957  mov     qword ptr [rcx], 0
0x18001095e  xorps   xmm0, xmm0
0x180010961  movdqu  xmmword ptr [rsp+48h+Sid], xmm0; int
0x180010967  mov     [rsp+48h+var_18], 0
0x180010970  lea     rcx, [rsp+48h+Sid]
0x180010975  call    ?GetCallerAppContainerSid@NgcUtils@@YAJPEAV?$vector@EV?$allocator@E@std@@@std@@@Z; NgcUtils::GetCallerAppContainerSid(std::vector<uchar> *)
0x18001097a  mov     edi, eax
0x18001097c  test    eax, eax
0x18001097e  jns     short loc_1800109A8
0x180010980  mov     rcx, [rsp+48h]; this
0x180010985  mov     r9d, eax; char *
0x180010988  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001098f  mov     edx, 1AAh; void *
0x180010994  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010999  nop
0x18001099a  lea     rcx, [rsp+48h+Sid]
0x18001099f  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x1800109a4  mov     eax, edi
0x1800109a6  jmp     short loc_180010A1F
0x1800109a8  mov     [rsp+48h+StringSid], 0
0x1800109b1  lea     rdx, [rsp+48h+StringSid]; StringSid
0x1800109b6  mov     rcx, [rsp+48h+Sid]; Sid
0x1800109bb  call    cs:__imp_ConvertSidToStringSidW
0x1800109c1  test    eax, eax
0x1800109c3  jnz     short loc_1800109FC
0x1800109c5  mov     rcx, [rsp+48h]; this
0x1800109ca  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800109d1  mov     edx, 1ADh; void *
0x1800109d6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800109db  mov     ebx, eax
0x1800109dd  mov     rcx, [rsp+48h+StringSid]; hMem
0x1800109e2  test    rcx, rcx
0x1800109e5  jz      short loc_1800109EE
0x1800109e7  call    cs:__imp_LocalFree
0x1800109ed  nop
0x1800109ee  lea     rcx, [rsp+48h+Sid]
0x1800109f3  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x1800109f8  mov     eax, ebx
0x1800109fa  jmp     short loc_180010A1F
0x1800109fc  mov     rax, [rsp+48h+StringSid]
0x180010a01  mov     [rsp+48h+StringSid], 0
0x180010a0a  mov     [rbx], rax
0x180010a0d  lea     rcx, [rsp+48h+Sid]
0x180010a12  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180010a17  xor     eax, eax
0x180010a19  jmp     short loc_180010A1F
0x180010a1b  mov     eax, dword ptr [rsp+48h+StringSid]
0x180010a1f  mov     rbx, [rsp+48h+arg_8]
0x180010a24  add     rsp, 40h
0x180010a28  pop     rdi
0x180010a29  retn
```
