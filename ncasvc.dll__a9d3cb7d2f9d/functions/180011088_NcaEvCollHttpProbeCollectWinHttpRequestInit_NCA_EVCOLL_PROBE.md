# NcaEvCollHttpProbeCollectWinHttpRequestInit(NCA_EVCOLL_PROBE_ *)

- ea: `0x180011088`
- end: `0x180011173`
- name: `?NcaEvCollHttpProbeCollectWinHttpRequestInit@@YAKPEAUNCA_EVCOLL_PROBE_@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(struct NCA_EVCOLL_PROBE_ *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001400`

## callees

- `0x180004f34`
- `0x180011088`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800110d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001112b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800110d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001112b`
- `WINHTTP!WinHttpOpenRequest` at `0x1800110c0`
- `WINHTTP!WinHttpOpenRequest` at `0x1800110c0`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180011119`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180011119`

## pseudocode

```c
__int64 __fastcall NcaEvCollHttpProbeCollectWinHttpRequestInit(struct NCA_EVCOLL_PROBE_ *a1)
{
  void *v2; // rax
  DWORD LastError; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx

  v2 = WinHttpOpenRequest(*((HINTERNET *)a1 + 6), L"HEAD", *((LPCWSTR *)a1 + 16), 0, 0, 0, 0);
  *((_QWORD *)a1 + 21) = v2;
  if ( v2 )
  {
    LastError = 0;
    if ( WinHttpSetStatusCallback(v2, NcaEvCollHttpProbeCollectAsyncCallback, 0xFFFFFFFF, 0) == (WINHTTP_STATUS_CALLBACK)-1LL )
    {
      LastError = GetLastError();
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v5 = 57;
        goto LABEL_9;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 56;
LABEL_9:
      WPP_SF_d(v4[2], v5, &WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids, LastError);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180011088  push    rbx
0x18001108a  sub     rsp, 40h
0x18001108e  mov     r8, [rcx+80h]; pwszObjectName
0x180011095  lea     rdx, pwszVerb; "HEAD"
0x18001109c  mov     rbx, rcx
0x18001109f  mov     [rsp+48h+dwFlags], 0; dwFlags
0x1800110a7  mov     rcx, [rcx+30h]; hConnect
0x1800110ab  xor     r9d, r9d; pwszVersion
0x1800110ae  mov     [rsp+48h+ppwszAcceptTypes], 0; ppwszAcceptTypes
0x1800110b7  mov     [rsp+48h+pwszReferrer], 0; pwszReferrer
0x1800110c0  call    cs:__imp_WinHttpOpenRequest
0x1800110c7  nop     dword ptr [rax+rax+00h]
0x1800110cc  mov     [rbx+0A8h], rax
0x1800110d3  test    rax, rax
0x1800110d6  jnz     short loc_180011106
0x1800110d8  call    cs:__imp_GetLastError
0x1800110df  nop     dword ptr [rax+rax+00h]
0x1800110e4  mov     ebx, eax
0x1800110e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800110ed  lea     rax, WPP_GLOBAL_Control
0x1800110f4  cmp     rcx, rax
0x1800110f7  jz      short loc_18001116A
0x1800110f9  test    byte ptr [rcx+1Ch], 1
0x1800110fd  jz      short loc_18001116A
0x1800110ff  mov     edx, 38h ; '8'
0x180011104  jmp     short loc_180011157
0x180011106  xor     r9d, r9d; dwReserved
0x180011109  lea     rdx, ?NcaEvCollHttpProbeCollectAsyncCallback@@YAXPEAX_KK0K@Z; lpfnInternetCallback
0x180011110  or      r8d, 0FFFFFFFFh; dwNotificationFlags
0x180011114  mov     rcx, rax; hInternet
0x180011117  xor     ebx, ebx
0x180011119  call    cs:__imp_WinHttpSetStatusCallback
0x180011120  nop     dword ptr [rax+rax+00h]
0x180011125  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180011129  jnz     short loc_18001116A
0x18001112b  call    cs:__imp_GetLastError
0x180011132  nop     dword ptr [rax+rax+00h]
0x180011137  mov     ebx, eax
0x180011139  mov     rcx, cs:WPP_GLOBAL_Control
0x180011140  lea     rax, WPP_GLOBAL_Control
0x180011147  cmp     rcx, rax
0x18001114a  jz      short loc_18001116A
0x18001114c  test    byte ptr [rcx+1Ch], 1
0x180011150  jz      short loc_18001116A
0x180011152  mov     edx, 39h ; '9'
0x180011157  mov     rcx, [rcx+10h]
0x18001115b  lea     r8, WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids
0x180011162  mov     r9d, ebx
0x180011165  call    WPP_SF_d
0x18001116a  mov     eax, ebx
0x18001116c  add     rsp, 40h
0x180011170  pop     rbx
0x180011171  retn
```
