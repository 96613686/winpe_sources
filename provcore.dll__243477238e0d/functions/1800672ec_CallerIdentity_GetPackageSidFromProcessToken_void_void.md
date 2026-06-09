# CallerIdentity::GetPackageSidFromProcessToken(void *,void * *)

- ea: `0x1800672ec`
- end: `0x180067415`
- name: `?GetPackageSidFromProcessToken@CallerIdentity@@YAJPEAXPEAPEAX@Z`
- size: `297`
- prototype: `HRESULT __fastcall(void *hToken, void **ppPackageSid)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180067270`

## callees

- `0x180066b68`
- `0x1800672ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006732c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006732c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180067357`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800673bc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180067357`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800673bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800673fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180067403`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800673fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180067403`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800673ad`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800673ad`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180067318`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180067389`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180067318`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180067389`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800673d9`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800673d9`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetPackageSidFromProcessToken(void *hToken, void **ppPackageSid)
{
  signed int Error; // ebx
  signed int LastError; // eax
  PSID *v6; // rdi
  DWORD LengthSid; // ebx
  HLOCAL v8; // rax
  void *v9; // rsi
  unsigned int cbTokenInfo; // [rsp+70h] [rbp+18h] BYREF

  cbTokenInfo = 0;
  if ( GetTokenInformation(hToken, TokenAppContainerSid, 0, 0, &cbTokenInfo) )
    return (unsigned int)-2147418113;
  LastError = GetLastError();
  Error = LastError;
  if ( LastError == 122 )
    goto LABEL_24;
  if ( LastError > 0 )
    Error = (unsigned __int16)LastError | 0x80070000;
  if ( Error >= 0 )
  {
LABEL_24:
    v6 = (PSID *)LocalAlloc(0x40u, cbTokenInfo);
    if ( !v6 )
      return (unsigned int)-2147024882;
    if ( GetTokenInformation(hToken, TokenAppContainerSid, v6, cbTokenInfo, &cbTokenInfo)
      || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      if ( *v6 )
      {
        LengthSid = GetLengthSid(*v6);
        v8 = LocalAlloc(0x40u, LengthSid);
        v9 = v8;
        if ( v8 )
        {
          if ( CopySid(LengthSid, v8, *v6) )
          {
            Error = 0;
          }
          else
          {
            Error = ResultFromKnownLastError();
            if ( Error < 0 )
            {
              LocalFree(v9);
              goto LABEL_20;
            }
          }
          *ppPackageSid = v9;
        }
        else
        {
          Error = -2147024882;
        }
      }
      else
      {
        Error = -2147023728;
      }
LABEL_20:
      LocalFree(v6);
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800672ec  push    rbx
0x1800672ee  push    rsi
0x1800672ef  push    rdi
0x1800672f0  push    r14
0x1800672f2  sub     rsp, 38h
0x1800672f6  xor     r9d, r9d; TokenInformationLength
0x1800672f9  mov     [rsp+58h+cbTokenInfo], 0
0x180067301  mov     r14, ppPackageSid
0x180067304  lea     rax, [rsp+58h+cbTokenInfo]
0x180067309  xor     r8d, r8d; TokenInformation
0x18006730c  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180067311  mov     rsi, hToken
0x180067314  lea     edx, [r9+1Fh]; TokenInformationClass
0x180067318  call    cs:__imp_GetTokenInformation
0x18006731e  test    eax, eax
0x180067320  jz      short loc_18006732C
0x180067322  mov     ebx, 8000FFFFh
0x180067327  jmp     loc_180067409
0x18006732c  call    cs:__imp_GetLastError
0x180067332  mov     ebx, eax
0x180067334  cmp     eax, 7Ah ; 'z'
0x180067337  jz      short loc_18006734E
0x180067339  test    eax, eax
0x18006733b  jle     short loc_180067346
0x18006733d  movzx   ebx, ax
0x180067340  or      ebx, 80070000h
0x180067346  test    ebx, ebx
0x180067348  js      loc_180067409
0x18006734e  mov     edx, [rsp+58h+cbTokenInfo]; uBytes
0x180067352  mov     ecx, 40h ; '@'; uFlags
0x180067357  call    cs:__imp_LocalAlloc
0x18006735d  mov     rdi, rax
0x180067360  test    rax, rax
0x180067363  jnz     short loc_18006736F
0x180067365  mov     ebx, 8007000Eh
0x18006736a  jmp     loc_180067409
0x18006736f  mov     r9d, [rsp+58h+cbTokenInfo]; TokenInformationLength
0x180067374  lea     rax, [rsp+58h+cbTokenInfo]
0x180067379  mov     r8, rdi; TokenInformation
0x18006737c  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180067381  mov     edx, 1Fh; TokenInformationClass
0x180067386  mov     hToken, rsi; TokenHandle
0x180067389  call    cs:__imp_GetTokenInformation
0x18006738f  test    eax, eax
0x180067391  jnz     short loc_18006739E
0x180067393  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180067398  mov     ebx, eax
0x18006739a  test    eax, eax
0x18006739c  js      short loc_180067409
0x18006739e  mov     hToken, [rdi]; pSid
0x1800673a1  test    hToken, hToken
0x1800673a4  jnz     short loc_1800673AD
0x1800673a6  mov     ebx, 80070490h
0x1800673ab  jmp     short loc_180067400
0x1800673ad  call    cs:__imp_GetLengthSid
0x1800673b3  mov     edx, eax; uBytes
0x1800673b5  mov     ecx, 40h ; '@'; uFlags
0x1800673ba  mov     ebx, eax
0x1800673bc  call    cs:__imp_LocalAlloc
0x1800673c2  mov     rsi, rax
0x1800673c5  test    rax, rax
0x1800673c8  jnz     short loc_1800673D1
0x1800673ca  mov     ebx, 8007000Eh
0x1800673cf  jmp     short loc_180067400
0x1800673d1  mov     r8, [rdi]; pSourceSid
0x1800673d4  mov     ppPackageSid, rsi; pDestinationSid
0x1800673d7  mov     ecx, ebx; nDestinationSidLength
0x1800673d9  call    cs:__imp_CopySid
0x1800673df  test    eax, eax
0x1800673e1  jz      short loc_1800673E7
0x1800673e3  xor     ebx, ebx
0x1800673e5  jmp     short loc_1800673F2
0x1800673e7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800673ec  mov     ebx, eax
0x1800673ee  test    eax, eax
0x1800673f0  js      short loc_1800673F7
0x1800673f2  mov     [r14], rsi
0x1800673f5  jmp     short loc_180067400
0x1800673f7  mov     hToken, rsi; hMem
0x1800673fa  call    cs:__imp_LocalFree
0x180067400  mov     hToken, rdi; hMem
0x180067403  call    cs:__imp_LocalFree
0x180067409  mov     eax, ebx
0x18006740b  add     rsp, 38h
0x18006740f  pop     r14
0x180067411  pop     rdi
0x180067412  pop     rsi
0x180067413  pop     rbx
0x180067414  retn
```
