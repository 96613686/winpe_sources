# ServiceChangeProc

- ea: `0x18002b720`
- end: `0x18002b98c`
- name: `ServiceChangeProc`
- size: `620`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18002b720`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b7c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b841`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b7c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b841`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002b897`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002b897`
- `api-ms-win-service-winsvc-l1-1-0!NotifyServiceStatusChangeA` at `0x18002b8e1`
- `api-ms-win-service-winsvc-l1-1-0!NotifyServiceStatusChangeA` at `0x18002b8e1`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x18002b7b3`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x18002b7b3`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x18002b829`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x18002b829`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002b921`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002b935`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002b921`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002b935`

## string_xrefs

- `0x18002b7aa`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall ServiceChangeProc(PVOID Parameter)
{
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rsi
  DWORD v3; // eax
  DWORD v4; // ebx
  struct _LIST_ENTRY *v5; // rcx
  SC_HANDLE v6; // rdi
  DWORD LastError; // eax
  struct _LIST_ENTRY *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  DWORD v11; // eax
  DWORD v12; // eax
  SERVICE_NOTIFY_2A pNotifyBuffer; // [rsp+20h] [rbp-98h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 185, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
  }
  *(&pNotifyBuffer.dwVersion + 1) = 0;
  memset_0(&pNotifyBuffer, 0, 0x4Cu);
  pNotifyBuffer.dwVersion = 2;
  pNotifyBuffer.pfnNotifyCallback = (PFN_SC_NOTIFY_CALLBACK)MpssvcNotifcationCallBack;
  v1 = OpenSCManagerA(0, "ServicesActive", 1u);
  v2 = v1;
  if ( v1 )
  {
    v6 = OpenServiceA(v1, "MPSSVC", 4u);
    if ( v6 )
    {
      while ( 1 )
      {
        v12 = NotifyServiceStatusChangeA(v6, 4u, &pNotifyBuffer);
        v4 = v12;
        if ( v12 )
          break;
        v11 = WaitForSingleObjectEx(g_hExitServiceChangeThread, 0xFFFFFFFF, 1);
        v4 = v11;
        if ( !v11 )
          goto LABEL_28;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 189, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v11);
        }
      }
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_28;
      }
      v9 = 188;
      v10 = v12;
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( !LastError
        || (v8 = WPP_GLOBAL_Control, WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control)
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
LABEL_28:
        CloseServiceHandle(v2);
        if ( v6 )
          CloseServiceHandle(v6);
        goto LABEL_30;
      }
      v9 = 187;
      v10 = LastError;
    }
    WPP_SF_d(v8[1].Flink, v9, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v10);
    goto LABEL_28;
  }
  v3 = GetLastError();
  v4 = v3;
  if ( !v3 )
  {
LABEL_30:
    v5 = WPP_GLOBAL_Control;
    goto LABEL_31;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return v4;
  if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 186, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v3);
    goto LABEL_30;
  }
LABEL_31:
  if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v5[1].Blink) & 0x2000) != 0
    && BYTE1(v5[1].Blink) >= 6u )
  {
    WPP_SF_d(v5[1].Flink, 190, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x18002b720  push    rbx
0x18002b722  push    rbp
0x18002b723  push    rsi
0x18002b724  push    rdi
0x18002b725  push    r14
0x18002b727  push    r15
0x18002b729  sub     rsp, 88h
0x18002b730  mov     rax, cs:__security_cookie
0x18002b737  xor     rax, rsp
0x18002b73a  mov     [rsp+0B8h+var_48], rax
0x18002b73f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b746  lea     r14, WPP_GLOBAL_Control
0x18002b74d  lea     r15, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x18002b754  mov     ebp, 2000h
0x18002b759  cmp     rcx, r14
0x18002b75c  jz      short loc_18002B77A
0x18002b75e  test    [rcx+1Ch], ebp
0x18002b761  jz      short loc_18002B77A
0x18002b763  cmp     byte ptr [rcx+19h], 6
0x18002b767  jb      short loc_18002B77A
0x18002b769  mov     rcx, [rcx+10h]
0x18002b76d  mov     edx, 0B9h
0x18002b772  mov     r8, r15
0x18002b775  call    WPP_SF_
0x18002b77a  xor     eax, eax
0x18002b77c  lea     rcx, [rsp+0B8h+pNotifyBuffer]; void *
0x18002b781  xor     edx, edx; Val
0x18002b783  mov     dword ptr [rsp+0B8h+pNotifyBuffer+4], eax
0x18002b787  lea     r8d, [rax+4Ch]; Size
0x18002b78b  call    memset_0
0x18002b790  lea     rax, MpssvcNotifcationCallBack
0x18002b797  mov     [rsp+0B8h+pNotifyBuffer.dwVersion], 2
0x18002b79f  mov     r8d, 1; dwDesiredAccess
0x18002b7a5  mov     [rsp+0B8h+pNotifyBuffer.pfnNotifyCallback], rax
0x18002b7aa  lea     rdx, DatabaseName; "ServicesActive"
0x18002b7b1  xor     ecx, ecx; lpMachineName
0x18002b7b3  call    cs:__imp_OpenSCManagerA
0x18002b7ba  nop     dword ptr [rax+rax+00h]
0x18002b7bf  mov     rsi, rax
0x18002b7c2  test    rax, rax
0x18002b7c5  jnz     short loc_18002B819
0x18002b7c7  call    cs:__imp_GetLastError
0x18002b7ce  nop     dword ptr [rax+rax+00h]
0x18002b7d3  mov     ebx, eax
0x18002b7d5  test    eax, eax
0x18002b7d7  jz      loc_18002B941
0x18002b7dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b7e4  cmp     rcx, r14
0x18002b7e7  jz      loc_18002B96C
0x18002b7ed  test    [rcx+1Ch], ebp
0x18002b7f0  jz      loc_18002B948
0x18002b7f6  cmp     byte ptr [rcx+19h], 2
0x18002b7fa  jb      loc_18002B948
0x18002b800  mov     rcx, [rcx+10h]
0x18002b804  mov     edx, 0BAh
0x18002b809  mov     r9d, eax
0x18002b80c  mov     r8, r15
0x18002b80f  call    WPP_SF_d
0x18002b814  jmp     loc_18002B941
0x18002b819  mov     r8d, 4; dwDesiredAccess
0x18002b81f  lea     rdx, ServiceName; "MPSSVC"
0x18002b826  mov     rcx, rsi; hSCManager
0x18002b829  call    cs:__imp_OpenServiceA
0x18002b830  nop     dword ptr [rax+rax+00h]
0x18002b835  mov     rdi, rax
0x18002b838  test    rax, rax
0x18002b83b  jnz     loc_18002B8D4
0x18002b841  call    cs:__imp_GetLastError
0x18002b848  nop     dword ptr [rax+rax+00h]
0x18002b84d  mov     ebx, eax
0x18002b84f  test    eax, eax
0x18002b851  jz      loc_18002B91E
0x18002b857  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b85e  cmp     rcx, r14
0x18002b861  jz      loc_18002B91E
0x18002b867  test    [rcx+1Ch], ebp
0x18002b86a  jz      loc_18002B91E
0x18002b870  cmp     byte ptr [rcx+19h], 2
0x18002b874  jb      loc_18002B91E
0x18002b87a  mov     edx, 0BBh
0x18002b87f  mov     r9d, eax
0x18002b882  jmp     loc_18002B912
0x18002b887  mov     rcx, cs:g_hExitServiceChangeThread; hHandle
0x18002b88e  mov     r8d, 1; bAlertable
0x18002b894  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002b897  call    cs:__imp_WaitForSingleObjectEx
0x18002b89e  nop     dword ptr [rax+rax+00h]
0x18002b8a3  mov     ebx, eax
0x18002b8a5  test    eax, eax
0x18002b8a7  jz      short loc_18002B91E
0x18002b8a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b8b0  cmp     rcx, r14
0x18002b8b3  jz      short loc_18002B8D4
0x18002b8b5  test    [rcx+1Ch], ebp
0x18002b8b8  jz      short loc_18002B8D4
0x18002b8ba  cmp     byte ptr [rcx+19h], 2
0x18002b8be  jb      short loc_18002B8D4
0x18002b8c0  mov     rcx, [rcx+10h]
0x18002b8c4  mov     edx, 0BDh
0x18002b8c9  mov     r9d, eax
0x18002b8cc  mov     r8, r15
0x18002b8cf  call    WPP_SF_d
0x18002b8d4  lea     r8, [rsp+0B8h+pNotifyBuffer]; pNotifyBuffer
0x18002b8d9  mov     edx, 4; dwNotifyMask
0x18002b8de  mov     rcx, rdi; hService
0x18002b8e1  call    cs:__imp_NotifyServiceStatusChangeA
0x18002b8e8  nop     dword ptr [rax+rax+00h]
0x18002b8ed  mov     ebx, eax
0x18002b8ef  test    eax, eax
0x18002b8f1  jz      short loc_18002B887
0x18002b8f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b8fa  cmp     rcx, r14
0x18002b8fd  jz      short loc_18002B91E
0x18002b8ff  test    [rcx+1Ch], ebp
0x18002b902  jz      short loc_18002B91E
0x18002b904  cmp     byte ptr [rcx+19h], 2
0x18002b908  jb      short loc_18002B91E
0x18002b90a  mov     edx, 0BCh
0x18002b90f  mov     r9d, eax
0x18002b912  mov     rcx, [rcx+10h]
0x18002b916  mov     r8, r15
0x18002b919  call    WPP_SF_d
0x18002b91e  mov     rcx, rsi; hSCObject
0x18002b921  call    cs:__imp_CloseServiceHandle
0x18002b928  nop     dword ptr [rax+rax+00h]
0x18002b92d  test    rdi, rdi
0x18002b930  jz      short loc_18002B941
0x18002b932  mov     rcx, rdi; hSCObject
0x18002b935  call    cs:__imp_CloseServiceHandle
0x18002b93c  nop     dword ptr [rax+rax+00h]
0x18002b941  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b948  cmp     rcx, r14
0x18002b94b  jz      short loc_18002B96C
0x18002b94d  test    [rcx+1Ch], ebp
0x18002b950  jz      short loc_18002B96C
0x18002b952  cmp     byte ptr [rcx+19h], 6
0x18002b956  jb      short loc_18002B96C
0x18002b958  mov     rcx, [rcx+10h]
0x18002b95c  mov     edx, 0BEh
0x18002b961  mov     r9d, ebx
0x18002b964  mov     r8, r15
0x18002b967  call    WPP_SF_d
0x18002b96c  mov     eax, ebx
0x18002b96e  mov     rcx, [rsp+0B8h+var_48]
0x18002b973  xor     rcx, rsp; StackCookie
0x18002b976  call    __security_check_cookie
0x18002b97b  add     rsp, 88h
0x18002b982  pop     r15
0x18002b984  pop     r14
0x18002b986  pop     rdi
0x18002b987  pop     rsi
0x18002b988  pop     rbp
0x18002b989  pop     rbx
0x18002b98a  retn
```
