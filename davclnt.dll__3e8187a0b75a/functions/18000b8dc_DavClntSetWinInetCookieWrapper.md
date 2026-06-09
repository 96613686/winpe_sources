# DavClntSetWinInetCookieWrapper

- ea: `0x18000b8dc`
- end: `0x18000ba82`
- name: `DavClntSetWinInetCookieWrapper`
- size: `422`
- prototype: `_UNKNOWN **__fastcall(LPCWSTR UncPath, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180004340`
- `0x180007ad0`

## callees

- `0x18000b494`
- `0x18000b8dc`
- `0x18000ba88`
- `0x18000f048`
- `0x180010be8`
- `0x180010c28`
- `0x180011e82`
- `0x180011eb0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18000ba25`
- `KERNEL32!LocalFree` at `0x18000ba25`
- `RPCRT4!NdrClientCall3` at `0x18000b9c3`
- `RPCRT4!NdrClientCall3` at `0x18000b9c3`

## pseudocode

```c
_UNKNOWN **__fastcall DavClntSetWinInetCookieWrapper(LPCWSTR UncPath, __int64 a2)
{
  _UNKNOWN **result; // rax
  HLOCAL hMem[2]; // [rsp+30h] [rbp-238h] BYREF
  _BYTE v6[528]; // [rsp+40h] [rbp-228h] BYREF

  memset_0(v6, 0, 0x202u);
  if ( UncPath && a2 )
  {
    result = (_UNKNOWN **)CallBackRegistered();
    if ( (_DWORD)result )
    {
      hMem[0] = 0;
      memset_0(v6, 0, 0x202u);
      if ( (unsigned int)GetServerNameOrSpn(UncPath, 0, v6) )
      {
        result = &WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          return (_UNKNOWN **)WPP_SF_S(
                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                365,
                                WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids,
                                UncPath);
      }
      else
      {
        result = (_UNKNOWN **)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 1u, 0, a2, v6, hMem).Pointer;
        if ( !(_DWORD)result && hMem[0] )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 366, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, hMem[0]);
          DavClntSetWinInetCookies(UncPath);
          return (_UNKNOWN **)LocalFree(hMem[0]);
        }
      }
    }
  }
  else
  {
    result = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      return (_UNKNOWN **)WPP_SF_d(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            364,
                            WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids,
                            87);
  }
  return result;
}

```

## disassembly

```asm
0x18000b8dc  mov     [rsp+arg_10], rbx
0x18000b8e1  push    rdi
0x18000b8e2  sub     rsp, 260h
0x18000b8e9  mov     rax, cs:__security_cookie
0x18000b8f0  xor     rax, rsp
0x18000b8f3  mov     [rsp+268h+var_18], rax
0x18000b8fb  mov     rdi, rdx
0x18000b8fe  mov     rbx, rcx
0x18000b901  xor     edx, edx; Val
0x18000b903  lea     rcx, [rsp+268h+var_228]; void *
0x18000b908  mov     r8d, 202h; Size
0x18000b90e  call    memset_0
0x18000b913  test    rbx, rbx
0x18000b916  jz      loc_18000BA2D
0x18000b91c  test    rdi, rdi
0x18000b91f  jz      loc_18000BA2D
0x18000b925  call    CallBackRegistered
0x18000b92a  test    eax, eax
0x18000b92c  jz      loc_18000BA61
0x18000b932  xor     edx, edx; Val
0x18000b934  mov     [rsp+268h+hMem], 0
0x18000b93d  mov     r8d, 202h; Size
0x18000b943  lea     rcx, [rsp+268h+var_228]; void *
0x18000b948  call    memset_0
0x18000b94d  lea     r8, [rsp+268h+var_228]
0x18000b952  xor     edx, edx
0x18000b954  mov     rcx, rbx
0x18000b957  call    GetServerNameOrSpn
0x18000b95c  test    eax, eax
0x18000b95e  jz      short loc_18000B99E
0x18000b960  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b967  lea     rax, WPP_GLOBAL_Control
0x18000b96e  cmp     rcx, rax
0x18000b971  jz      loc_18000BA61
0x18000b977  test    byte ptr [rcx+1Ch], 2
0x18000b97b  jz      loc_18000BA61
0x18000b981  mov     rcx, [rcx+10h]
0x18000b985  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000b98c  mov     edx, 16Dh
0x18000b991  mov     r9, rbx
0x18000b994  call    WPP_SF_S
0x18000b999  jmp     loc_18000BA61
0x18000b99e  xor     r8d, r8d; pReturnValue
0x18000b9a1  lea     rax, [rsp+268h+hMem]
0x18000b9a6  mov     [rsp+268h+var_240], rax
0x18000b9ab  lea     rcx, pProxyInfo; pProxyInfo
0x18000b9b2  lea     rax, [rsp+268h+var_228]
0x18000b9b7  mov     r9, rdi
0x18000b9ba  mov     [rsp+268h+var_248], rax
0x18000b9bf  lea     edx, [r8+1]; nProcNum
0x18000b9c3  call    cs:__imp_NdrClientCall3
0x18000b9c9  test    eax, eax
0x18000b9cb  jnz     loc_18000BA61
0x18000b9d1  mov     r8, [rsp+268h+hMem]
0x18000b9d6  test    r8, r8
0x18000b9d9  jz      loc_18000BA61
0x18000b9df  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b9e6  lea     rax, WPP_GLOBAL_Control
0x18000b9ed  cmp     rcx, rax
0x18000b9f0  jz      short loc_18000BA15
0x18000b9f2  test    byte ptr [rcx+1Ch], 1
0x18000b9f6  jz      short loc_18000BA15
0x18000b9f8  mov     rcx, [rcx+10h]
0x18000b9fc  mov     r9, r8
0x18000b9ff  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000ba06  mov     edx, 16Eh
0x18000ba0b  call    WPP_SF_S
0x18000ba10  mov     r8, [rsp+268h+hMem]
0x18000ba15  mov     rdx, r8
0x18000ba18  mov     rcx, rbx; UncPath
0x18000ba1b  call    DavClntSetWinInetCookies
0x18000ba20  mov     rcx, [rsp+268h+hMem]; hMem
0x18000ba25  call    cs:__imp_LocalFree
0x18000ba2b  jmp     short loc_18000BA61
0x18000ba2d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba34  lea     rax, WPP_GLOBAL_Control
0x18000ba3b  cmp     rcx, rax
0x18000ba3e  jz      short loc_18000BA61
0x18000ba40  test    byte ptr [rcx+1Ch], 2
0x18000ba44  jz      short loc_18000BA61
0x18000ba46  mov     rcx, [rcx+10h]
0x18000ba4a  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000ba51  mov     edx, 16Ch
0x18000ba56  mov     r9d, 57h ; 'W'
0x18000ba5c  call    WPP_SF_d
0x18000ba61  mov     rcx, [rsp+268h+var_18]
0x18000ba69  xor     rcx, rsp; StackCookie
0x18000ba6c  call    __security_check_cookie
0x18000ba71  mov     rbx, [rsp+268h+arg_10]
0x18000ba79  add     rsp, 260h
0x18000ba80  pop     rdi
0x18000ba81  retn
```
