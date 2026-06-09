# SetFileSAFERLevel(ushort const *,ulong)

- ea: `0x180055258`
- end: `0x180055385`
- name: `?SetFileSAFERLevel@@YAJPEBGK@Z`
- size: `301`
- prototype: `__int64 __fastcall(const unsigned __int16 *, DWORD dwLevelId)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003cd84`

## callees

- `0x180054f78`
- `0x180055258`
- `0x18005583a`
- `0x180055880`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800552d3`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800552d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005533c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005533c`
- `ADVAPI32!SaferCloseLevel` at `0x18005535b`
- `ADVAPI32!SaferCloseLevel` at `0x18005535b`
- `ADVAPI32!SaferSetLevelInformation` at `0x180055332`
- `ADVAPI32!SaferSetLevelInformation` at `0x180055332`
- `ADVAPI32!SaferCreateLevel` at `0x18005530c`
- `ADVAPI32!SaferCreateLevel` at `0x18005530c`

## pseudocode

```c
__int64 __fastcall SetFileSAFERLevel(const unsigned __int16 *a1, DWORD dwLevelId)
{
  int v4; // ebx
  signed int LastError; // eax
  SAFER_LEVEL_HANDLE pLevelHandle; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD QueryBuffer[2]; // [rsp+40h] [rbp-C0h] BYREF
  GUID v9; // [rsp+48h] [rbp-B8h] BYREF
  const unsigned __int16 *v10; // [rsp+260h] [rbp+160h]
  GUID pguid; // [rsp+270h] [rbp+170h] BYREF

  QueryBuffer[0] = 1;
  QueryBuffer[1] = 560;
  memset_0(&v9, 0, 0x228u);
  pLevelHandle = 0;
  pguid = 0;
  v4 = DisableSAFERForFile(a1);
  if ( v4 >= 0 )
  {
    v4 = CoCreateGuid(&pguid);
    if ( v4 >= 0 )
    {
      v10 = a1;
      v9 = pguid;
      if ( SaferCreateLevel(1u, dwLevelId, 1u, &pLevelHandle, 0) )
      {
        if ( !SaferSetLevelInformation(pLevelHandle, SaferObjectSingleIdentification, QueryBuffer, 0x230u) )
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError > 0 )
            v4 = (unsigned __int16)LastError | 0x80070000;
        }
      }
      else
      {
        v4 = -2146367454;
      }
    }
  }
  if ( pLevelHandle )
    SaferCloseLevel(pLevelHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180055258  mov     [rsp-8+arg_10], rbx
0x18005525d  push    rbp
0x18005525e  push    rsi
0x18005525f  push    rdi
0x180055260  lea     rbp, [rsp-190h]
0x180055268  sub     rsp, 290h
0x18005526f  mov     rax, cs:__security_cookie
0x180055276  xor     rax, rsp
0x180055279  mov     [rbp+1A0h+var_20], rax
0x180055280  mov     esi, edx
0x180055282  mov     [rsp+2A0h+QueryBuffer], 1
0x18005528a  mov     rdi, rcx
0x18005528d  mov     [rsp+2A0h+var_25C], 230h
0x180055295  xor     edx, edx; Val
0x180055297  lea     rcx, [rsp+2A0h+var_258]; void *
0x18005529c  mov     r8d, 228h; Size
0x1800552a2  call    memset_0
0x1800552a7  xorps   xmm0, xmm0
0x1800552aa  mov     [rsp+2A0h+pLevelHandle], 0
0x1800552b3  mov     rcx, rdi; unsigned __int16 *
0x1800552b6  movups  xmmword ptr [rbp+1A0h+pguid.Data1], xmm0
0x1800552bd  call    ?DisableSAFERForFile@@YAJPEBG@Z; DisableSAFERForFile(ushort const *)
0x1800552c2  mov     ebx, eax
0x1800552c4  test    eax, eax
0x1800552c6  js      loc_180055351
0x1800552cc  lea     rcx, [rbp+1A0h+pguid]; pguid
0x1800552d3  call    cs:__imp_CoCreateGuid
0x1800552d9  mov     ebx, eax
0x1800552db  test    eax, eax
0x1800552dd  js      short loc_180055351
0x1800552df  movups  xmm0, xmmword ptr [rbp+1A0h+pguid.Data1]
0x1800552e6  mov     r8d, 1; OpenFlags
0x1800552ec  mov     [rbp+1A0h+var_40], rdi
0x1800552f3  lea     r9, [rsp+2A0h+pLevelHandle]; pLevelHandle
0x1800552f8  mov     [rsp+2A0h+lpReserved], 0; lpReserved
0x180055301  mov     edx, esi; dwLevelId
0x180055303  mov     ecx, r8d; dwScopeId
0x180055306  movdqu  [rsp+2A0h+var_258], xmm0
0x18005530c  call    cs:__imp_SaferCreateLevel
0x180055312  test    eax, eax
0x180055314  jnz     short loc_18005531D
0x180055316  mov     ebx, 80110822h
0x18005531b  jmp     short loc_180055351
0x18005531d  mov     rcx, [rsp+2A0h+pLevelHandle]; LevelHandle
0x180055322  lea     r8, [rsp+2A0h+QueryBuffer]; lpQueryBuffer
0x180055327  mov     r9d, 230h; dwInBufferSize
0x18005532d  mov     edx, 0Fh; dwInfoType
0x180055332  call    cs:__imp_SaferSetLevelInformation
0x180055338  test    eax, eax
0x18005533a  jnz     short loc_180055351
0x18005533c  call    cs:__imp_GetLastError
0x180055342  mov     ebx, eax
0x180055344  test    eax, eax
0x180055346  jle     short loc_180055351
0x180055348  movzx   ebx, ax
0x18005534b  or      ebx, 80070000h
0x180055351  mov     rcx, [rsp+2A0h+pLevelHandle]; hLevelHandle
0x180055356  test    rcx, rcx
0x180055359  jz      short loc_180055361
0x18005535b  call    cs:__imp_SaferCloseLevel
0x180055361  mov     eax, ebx
0x180055363  mov     rcx, [rbp+1A0h+var_20]
0x18005536a  xor     rcx, rsp; StackCookie
0x18005536d  call    __security_check_cookie
0x180055372  mov     rbx, [rsp+2A0h+arg_10]
0x18005537a  add     rsp, 290h
0x180055381  pop     rdi
0x180055382  pop     rsi
0x180055383  pop     rbp
0x180055384  retn
```
