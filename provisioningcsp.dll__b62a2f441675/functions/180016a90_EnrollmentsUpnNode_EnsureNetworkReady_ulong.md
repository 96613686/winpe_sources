# EnrollmentsUpnNode::EnsureNetworkReady(ulong)

- ea: `0x180016a90`
- end: `0x180016c52`
- name: `?EnsureNetworkReady@EnrollmentsUpnNode@@CAJK@Z`
- size: `450`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180014e20`

## callees

- `0x180007834`
- `0x180016a90`
- `0x180022928`
- `0x1800358a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016bac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016bac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c0b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016b12`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016b12`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180016b86`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180016b86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016bea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016bf9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016bea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016bf9`
- `IPHLPAPI!GetNetworkConnectivityHint` at `0x180016abd`
- `IPHLPAPI!GetNetworkConnectivityHint` at `0x180016abd`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x180016bcf`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x180016bcf`
- `IPHLPAPI!NotifyNetworkConnectivityHintChange` at `0x180016b45`
- `IPHLPAPI!NotifyNetworkConnectivityHintChange` at `0x180016b45`

## pseudocode

```c
__int64 __fastcall EnrollmentsUpnNode::EnsureNetworkReady()
{
  int NetworkConnectivityHint; // eax
  signed int v1; // edi
  HANDLE EventW; // rax
  __int64 v3; // r8
  void *v4; // rbx
  int v5; // eax
  DWORD v6; // eax
  signed int LastError; // eax
  unsigned int v8; // r8d
  const char *v9; // r9
  signed int v10; // eax
  HANDLE NotificationHandle; // [rsp+20h] [rbp-28h] BYREF
  __int64 v13; // [rsp+28h] [rbp-20h] BYREF
  int v14; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v13 = 0;
  v14 = 0;
  NetworkConnectivityHint = GetNetworkConnectivityHint(&v13);
  v1 = NetworkConnectivityHint;
  if ( NetworkConnectivityHint > 0 )
    v1 = (unsigned __int16)NetworkConnectivityHint | 0x80070000;
  if ( v1 >= 0 )
  {
    if ( (_DWORD)v13 != 3 )
    {
      EventW = CreateEventW(0, 1, 0, 0);
      v4 = EventW;
      if ( EventW )
      {
        NotificationHandle = 0;
        LOBYTE(v3) = 1;
        v5 = NotifyNetworkConnectivityHintChange(
               &NetworkConnectivityHintChangedCallback,
               EventW,
               v3,
               &NotificationHandle);
        v1 = v5;
        if ( v5 > 0 )
          v1 = (unsigned __int16)v5 | 0x80070000;
        if ( v1 >= 0 )
        {
          v6 = WaitForSingleObjectEx(v4, 0x1D4C0u, 0);
          if ( (v6 & 0xFFFFFF7F) != 0 )
          {
            if ( v6 == 258 )
            {
              v1 = -2147023436;
            }
            else if ( v6 == -1 )
            {
              LastError = GetLastError();
              v1 = LastError;
              if ( LastError > 0 )
                v1 = (unsigned __int16)LastError | 0x80070000;
            }
            else
            {
              v1 = -2147418113;
            }
          }
          CancelMibChangeNotify2(NotificationHandle);
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xA8,
            (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\enrollmentsupnnode.cpp",
            (const char *)(unsigned int)v1,
            (int)NotificationHandle);
        }
        if ( (char *)NotificationHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(NotificationHandle);
        if ( !CloseHandle(v4) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v8, v9);
      }
      else
      {
        v10 = GetLastError();
        v1 = v10;
        if ( v10 > 0 )
          return (unsigned __int16)v10 | 0x80070000;
      }
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x99,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\enrollmentsupnnode.cpp",
      (const char *)(unsigned int)v1,
      (int)NotificationHandle);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180016a90  mov     r11, rsp
0x180016a93  mov     [r11+8], rbx
0x180016a97  mov     [r11+10h], rsi
0x180016a9b  push    rdi
0x180016a9c  sub     rsp, 40h
0x180016aa0  mov     rax, cs:__security_cookie
0x180016aa7  xor     rax, rsp
0x180016aaa  mov     [rsp+48h+var_10], rax
0x180016aaf  xor     eax, eax
0x180016ab1  lea     rcx, [r11-20h]
0x180016ab5  mov     [r11-20h], rax
0x180016ab9  mov     [rsp+48h+var_18], eax
0x180016abd  call    cs:__imp_GetNetworkConnectivityHint
0x180016ac4  nop     dword ptr [rax+rax+00h]
0x180016ac9  mov     edi, eax
0x180016acb  mov     esi, 80070000h
0x180016ad0  test    eax, eax
0x180016ad2  jle     short loc_180016AD9
0x180016ad4  movzx   edi, ax
0x180016ad7  or      edi, esi
0x180016ad9  test    edi, edi
0x180016adb  jns     short loc_180016AFB
0x180016add  mov     rcx, [rsp+48h]; this
0x180016ae2  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\prov\\provcsp\\enrol"...
0x180016ae9  mov     r9d, edi; char *
0x180016aec  mov     edx, 99h; void *
0x180016af1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180016af6  jmp     loc_180016C22
0x180016afb  cmp     dword ptr [rsp+48h+var_20], 3
0x180016b00  jz      loc_180016C22
0x180016b06  xor     r9d, r9d; lpName
0x180016b09  xor     r8d, r8d; bInitialState
0x180016b0c  xor     ecx, ecx; lpEventAttributes
0x180016b0e  lea     edx, [r9+1]; bManualReset
0x180016b12  call    cs:__imp_CreateEventW
0x180016b19  nop     dword ptr [rax+rax+00h]
0x180016b1e  mov     rbx, rax
0x180016b21  test    rax, rax
0x180016b24  jz      loc_180016C0B
0x180016b2a  lea     r9, [rsp+48h+NotificationHandle]
0x180016b2f  mov     [rsp+48h+NotificationHandle], 0; int
0x180016b38  mov     r8b, 1
0x180016b3b  lea     rcx, ?NetworkConnectivityHintChangedCallback@@YAXPEAXU_NL_NETWORK_CONNECTIVITY_HINT@@@Z; NetworkConnectivityHintChangedCallback(void *,_NL_NETWORK_CONNECTIVITY_HINT)
0x180016b42  mov     rdx, rax
0x180016b45  call    cs:__imp_NotifyNetworkConnectivityHintChange
0x180016b4c  nop     dword ptr [rax+rax+00h]
0x180016b51  mov     edi, eax
0x180016b53  test    eax, eax
0x180016b55  jle     short loc_180016B5C
0x180016b57  movzx   edi, ax
0x180016b5a  or      edi, esi
0x180016b5c  test    edi, edi
0x180016b5e  jns     short loc_180016B7B
0x180016b60  mov     rcx, [rsp+48h]; this
0x180016b65  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\prov\\provcsp\\enrol"...
0x180016b6c  mov     r9d, edi; char *
0x180016b6f  mov     edx, 0A8h; void *
0x180016b74  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180016b79  jmp     short loc_180016BDB
0x180016b7b  xor     r8d, r8d; bAlertable
0x180016b7e  mov     edx, 1D4C0h; dwMilliseconds
0x180016b83  mov     rcx, rbx; hHandle
0x180016b86  call    cs:__imp_WaitForSingleObjectEx
0x180016b8d  nop     dword ptr [rax+rax+00h]
0x180016b92  test    eax, 0FFFFFF7Fh
0x180016b97  jz      short loc_180016BCA
0x180016b99  cmp     eax, 102h
0x180016b9e  jz      short loc_180016BC5
0x180016ba0  cmp     eax, 0FFFFFFFFh
0x180016ba3  jz      short loc_180016BAC
0x180016ba5  mov     edi, 8000FFFFh
0x180016baa  jmp     short loc_180016BCA
0x180016bac  call    cs:__imp_GetLastError
0x180016bb3  nop     dword ptr [rax+rax+00h]
0x180016bb8  mov     edi, eax
0x180016bba  test    eax, eax
0x180016bbc  jle     short loc_180016BCA
0x180016bbe  movzx   edi, ax
0x180016bc1  or      edi, esi
0x180016bc3  jmp     short loc_180016BCA
0x180016bc5  mov     edi, 800705B4h
0x180016bca  mov     rcx, [rsp+48h+NotificationHandle]; NotificationHandle
0x180016bcf  call    cs:__imp_CancelMibChangeNotify2
0x180016bd6  nop     dword ptr [rax+rax+00h]
0x180016bdb  mov     rcx, [rsp+48h+NotificationHandle]; hObject
0x180016be0  lea     rax, [rcx-1]
0x180016be4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180016be8  ja      short loc_180016BF6
0x180016bea  call    cs:__imp_CloseHandle
0x180016bf1  nop     dword ptr [rax+rax+00h]
0x180016bf6  mov     rcx, rbx; hObject
0x180016bf9  call    cs:__imp_CloseHandle
0x180016c00  nop     dword ptr [rax+rax+00h]
0x180016c05  test    eax, eax
0x180016c07  jz      short loc_180016C42
0x180016c09  jmp     short loc_180016C22
0x180016c0b  call    cs:__imp_GetLastError
0x180016c12  nop     dword ptr [rax+rax+00h]
0x180016c17  mov     edi, eax
0x180016c19  test    eax, eax
0x180016c1b  jle     short loc_180016C22
0x180016c1d  movzx   edi, ax
0x180016c20  or      edi, esi
0x180016c22  mov     eax, edi
0x180016c24  mov     rcx, [rsp+48h+var_10]
0x180016c29  xor     rcx, rsp; StackCookie
0x180016c2c  call    __security_check_cookie
0x180016c31  mov     rbx, [rsp+48h+arg_0]
0x180016c36  mov     rsi, [rsp+48h+arg_8]
0x180016c3b  add     rsp, 40h
0x180016c3f  pop     rdi
0x180016c40  retn
0x180016c42  mov     rcx, [rsp+48h]; this
0x180016c47  mov     edx, 0A0Bh; void *
0x180016c4c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
