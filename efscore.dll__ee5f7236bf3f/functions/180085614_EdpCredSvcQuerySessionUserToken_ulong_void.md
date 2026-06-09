# EdpCredSvcQuerySessionUserToken(ulong,void * *)

- ea: `0x180085614`
- end: `0x1800857a2`
- name: `?EdpCredSvcQuerySessionUserToken@@YAJKPEAPEAX@Z`
- size: `398`
- prototype: `__int64 __fastcall(ULONG SessionId, void **)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180084508`
- `0x1800853a4`
- `0x1800857a8`
- `0x1800a1540`

## callees

- `0x180005718`
- `0x1800059a0`
- `0x180063698`
- `0x180085614`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008565f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800856ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008565f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800856ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008578a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008578a`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180085651`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180085651`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x1800856c4`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x1800856c4`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQuerySessionUserToken` at `0x18008568e`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQuerySessionUserToken` at `0x18008568e`

## pseudocode

```c
__int64 __fastcall EdpCredSvcQuerySessionUserToken(ULONG SessionId, void **a2)
{
  signed int v4; // ebx
  signed int LastError; // eax
  int v6; // eax
  signed int v7; // eax
  int v8; // r8d
  char v10; // [rsp+20h] [rbp-18h]
  void *phToken; // [rsp+48h] [rbp+10h] BYREF

  phToken = 0;
  if ( a2 )
  {
    v4 = 0;
    *a2 = 0;
    if ( (unsigned __int8)IsWTSEnumerateSessionsWPresent() )
    {
      if ( WTSQueryUserToken(SessionId, &phToken) )
        goto LABEL_19;
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v4, 38, 23);
    }
    else
    {
      if ( (unsigned __int8)IsUMgrQuerySessionUserTokenPresent() )
      {
        v6 = UMgrQuerySessionUserToken(SessionId, &phToken);
        v4 = v6;
        if ( v6 < 0 )
        {
          fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v6, 38, 32);
          goto LABEL_15;
        }
LABEL_19:
        *a2 = phToken;
        phToken = 0;
        goto LABEL_22;
      }
      if ( (unsigned int)QueryUserToken(SessionId, &phToken) )
        goto LABEL_19;
      v7 = GetLastError();
      v4 = v7;
      if ( v7 > 0 )
        v4 = (unsigned __int16)v7 | 0x80070000;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v4, 38, 40);
    }
    if ( v4 < 0 )
    {
LABEL_15:
      if ( v4 == -2147023888 || v4 == -2147024894 )
      {
        v4 = 1;
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, 1, 38, 49);
        goto LABEL_22;
      }
      v10 = 53;
      v8 = v4;
      goto LABEL_21;
    }
    goto LABEL_19;
  }
  v4 = -2147467261;
  v10 = 12;
  v8 = -2147467261;
LABEL_21:
  fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v8, 38, v10);
LABEL_22:
  if ( phToken )
    CloseHandle(phToken);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180085614  mov     [rsp+arg_0], rbx
0x180085619  mov     [rsp+arg_10], rsi
0x18008561e  push    rdi
0x18008561f  sub     rsp, 30h
0x180085623  mov     [rsp+38h+phToken], 0
0x18008562c  mov     rsi, rdx
0x18008562f  mov     edi, ecx
0x180085631  test    rdx, rdx
0x180085634  jz      loc_180085754
0x18008563a  xor     eax, eax
0x18008563c  xor     ebx, ebx
0x18008563e  mov     [rdx], rax
0x180085641  call    IsWTSEnumerateSessionsWPresent
0x180085646  test    al, al
0x180085648  jz      short loc_18008567E
0x18008564a  lea     rdx, [rsp+38h+phToken]; phToken
0x18008564f  mov     ecx, edi; SessionId
0x180085651  call    cs:__imp_WTSQueryUserToken
0x180085657  test    eax, eax
0x180085659  jnz     loc_180085741
0x18008565f  call    cs:__imp_GetLastError
0x180085665  mov     ebx, eax
0x180085667  test    eax, eax
0x180085669  jle     short loc_180085674
0x18008566b  movzx   ebx, ax
0x18008566e  or      ebx, 80070000h
0x180085674  mov     dword ptr [rsp+38h+var_18], 917h
0x18008567c  jmp     short loc_1800856EB
0x18008567e  call    IsUMgrQuerySessionUserTokenPresent
0x180085683  lea     rdx, [rsp+38h+phToken]
0x180085688  mov     ecx, edi
0x18008568a  test    al, al
0x18008568c  jz      short loc_1800856C4
0x18008568e  call    cs:__imp_UMgrQuerySessionUserToken
0x180085694  mov     ebx, eax
0x180085696  test    eax, eax
0x180085698  jns     loc_180085741
0x18008569e  mov     rcx, cs:g_hPublisher
0x1800856a5  lea     rdx, EFS_TRACE_ERROR
0x1800856ac  mov     r9d, 26h ; '&'
0x1800856b2  mov     dword ptr [rsp+38h+var_18], 920h
0x1800856ba  mov     r8d, eax
0x1800856bd  call    fnEfsLogTrace1
0x1800856c2  jmp     short loc_18008570B
0x1800856c4  call    cs:__imp_QueryUserToken
0x1800856ca  test    eax, eax
0x1800856cc  jnz     short loc_180085741
0x1800856ce  call    cs:__imp_GetLastError
0x1800856d4  mov     ebx, eax
0x1800856d6  test    eax, eax
0x1800856d8  jle     short loc_1800856E3
0x1800856da  movzx   ebx, ax
0x1800856dd  or      ebx, 80070000h
0x1800856e3  mov     dword ptr [rsp+38h+var_18], 928h
0x1800856eb  mov     rcx, cs:g_hPublisher
0x1800856f2  lea     rdx, EFS_TRACE_ERROR
0x1800856f9  mov     r9d, 26h ; '&'
0x1800856ff  mov     r8d, ebx
0x180085702  call    fnEfsLogTrace1
0x180085707  test    ebx, ebx
0x180085709  jns     short loc_180085741
0x18008570b  cmp     ebx, 800703F0h
0x180085711  jz      short loc_180085728
0x180085713  cmp     ebx, 80070002h
0x180085719  jz      short loc_180085728
0x18008571b  mov     dword ptr [rsp+38h+var_18], 935h
0x180085723  mov     r8d, ebx
0x180085726  jmp     short loc_180085767
0x180085728  mov     ebx, 1
0x18008572d  mov     dword ptr [rsp+38h+var_18], 931h
0x180085735  mov     r8d, ebx
0x180085738  lea     rdx, EFS_TRACE_STATUS
0x18008573f  jmp     short loc_18008576E
0x180085741  mov     rax, [rsp+38h+phToken]
0x180085746  mov     [rsi], rax
0x180085749  mov     [rsp+38h+phToken], 0
0x180085752  jmp     short loc_180085780
0x180085754  mov     ebx, 80004003h
0x180085759  mov     dword ptr [rsp+38h+var_18], 90Ch
0x180085761  mov     r8d, 80004003h
0x180085767  lea     rdx, EFS_TRACE_ERROR
0x18008576e  mov     rcx, cs:g_hPublisher
0x180085775  mov     r9d, 26h ; '&'
0x18008577b  call    fnEfsLogTrace1
0x180085780  mov     rcx, [rsp+38h+phToken]; hObject
0x180085785  test    rcx, rcx
0x180085788  jz      short loc_180085790
0x18008578a  call    cs:__imp_CloseHandle
0x180085790  mov     rsi, [rsp+38h+arg_10]
0x180085795  mov     eax, ebx
0x180085797  mov     rbx, [rsp+38h+arg_0]
0x18008579c  add     rsp, 30h
0x1800857a0  pop     rdi
0x1800857a1  retn
```
