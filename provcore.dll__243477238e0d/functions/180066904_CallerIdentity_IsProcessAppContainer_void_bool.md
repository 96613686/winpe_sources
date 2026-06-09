# CallerIdentity::IsProcessAppContainer(void *,bool *)

- ea: `0x180066904`
- end: `0x1800669b6`
- name: `?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z`
- size: `178`
- prototype: `HRESULT __fastcall(void *hProcess, bool *pfAppContainer)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180067438`

## callees

- `0x180066904`
- `0x180066b14`
- `0x180066b68`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800669a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800669a3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180066968`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180066968`

## pseudocode

```c
__int64 __fastcall CallerIdentity::IsProcessAppContainer(void *hProcess, bool *pfAppContainer)
{
  signed int v3; // eax
  signed int Error; // ebx
  char *obj; // rcx
  unsigned int IsAppContainer; // [rsp+48h] [rbp+10h] BYREF
  unsigned int cbToken; // [rsp+50h] [rbp+18h] BYREF
  CAutoHandle<void *> shToken; // [rsp+58h] [rbp+20h] BYREF

  *pfAppContainer = 0;
  shToken._obj = 0;
  v3 = ARI::ProcessToken::SysAppId::OpenTokenForProcess(hProcess, &shToken._obj);
  Error = v3;
  if ( v3 > 0 )
    Error = (unsigned __int16)v3 | 0x80070000;
  if ( Error >= 0 )
  {
    cbToken = 0;
    IsAppContainer = 0;
    if ( GetTokenInformation(shToken._obj, TokenIsAppContainer, &IsAppContainer, 4u, &cbToken) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        goto LABEL_8;
    }
    *pfAppContainer = IsAppContainer != 0;
  }
LABEL_8:
  obj = (char *)shToken._obj;
  shToken._obj = 0;
  if ( (unsigned __int64)(obj - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(obj);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180066904  mov     [rsp+arg_0], rbx
0x180066909  push    rdi
0x18006690a  sub     rsp, 30h
0x18006690e  mov     rdi, pfAppContainer
0x180066911  mov     byte ptr [pfAppContainer], 0
0x180066914  lea     pfAppContainer, [rsp+38h+shToken]; token
0x180066919  mov     [rsp+38h+shToken._obj], 0
0x180066922  call    ?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z; ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)
0x180066927  mov     ebx, eax
0x180066929  test    eax, eax
0x18006692b  jle     short loc_180066936
0x18006692d  movzx   ebx, ax
0x180066930  or      ebx, 80070000h
0x180066936  test    ebx, ebx
0x180066938  js      short loc_18006698B
0x18006693a  mov     hProcess, [rsp+38h+shToken._obj]; TokenHandle
0x18006693f  lea     rax, [rsp+38h+cbToken]
0x180066944  mov     r9d, 4; TokenInformationLength
0x18006694a  mov     [rsp+38h+cbToken], 0
0x180066952  lea     r8, [rsp+38h+IsAppContainer]; TokenInformation
0x180066957  mov     [rsp+38h+IsAppContainer], 0
0x18006695f  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180066964  lea     edx, [r9+19h]; TokenInformationClass
0x180066968  call    cs:__imp_GetTokenInformation
0x18006696e  test    eax, eax
0x180066970  jz      short loc_180066976
0x180066972  xor     ebx, ebx
0x180066974  jmp     short loc_180066981
0x180066976  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18006697b  mov     ebx, eax
0x18006697d  test    eax, eax
0x18006697f  js      short loc_18006698B
0x180066981  cmp     [rsp+38h+IsAppContainer], 0
0x180066986  setnz   al
0x180066989  mov     [rdi], al
0x18006698b  mov     hProcess, [rsp+38h+shToken._obj]; hObject
0x180066990  mov     [rsp+38h+shToken._obj], 0
0x180066999  lea     pfAppContainer, [hProcess-1]
0x18006699d  cmp     pfAppContainer, 0FFFFFFFFFFFFFFFDh
0x1800669a1  ja      short loc_1800669A9
0x1800669a3  call    cs:__imp_CloseHandle
0x1800669a9  mov     eax, ebx
0x1800669ab  mov     rbx, [rsp+38h+arg_0]
0x1800669b0  add     rsp, 30h
0x1800669b4  pop     rdi
0x1800669b5  retn
```
