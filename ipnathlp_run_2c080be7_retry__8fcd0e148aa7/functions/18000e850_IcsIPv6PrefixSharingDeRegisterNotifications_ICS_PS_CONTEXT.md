# IcsIPv6PrefixSharingDeRegisterNotifications(_ICS_PS_CONTEXT *)

- ea: `0x18000e850`
- end: `0x18000eb1f`
- name: `?IcsIPv6PrefixSharingDeRegisterNotifications@@YAKPEAU_ICS_PS_CONTEXT@@@Z`
- size: `719`
- prototype: `unsigned int __fastcall(struct _ICS_PS_CONTEXT *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d590`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x18000e850`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e95d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eadd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e95d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eadd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e977`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e977`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eaf1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eaf1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e8a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e8a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e8ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eaa7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e8ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eaa7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e9f7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e9f7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000eabc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000eabc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ead1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ead1`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18000ea58`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18000ea58`

## pseudocode

```c
__int64 __fastcall IcsIPv6PrefixSharingDeRegisterNotifications(struct _ICS_PS_CONTEXT *a1)
{
  PVOID *v2; // rcx
  HANDLE *v3; // rsi
  unsigned int v4; // ebp
  HANDLE ProcessHeap; // rax
  HANDLE *v7; // rax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  HANDLE EventW; // rax
  DWORD v12; // eax
  DWORD LastError; // eax
  HANDLE v14; // rcx
  HANDLE v15; // rax

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *(_DWORD *)a1 )
  {
    v3 = 0;
    v4 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 64));
    if ( !*((_QWORD *)a1 + 2) )
      goto LABEL_7;
    ProcessHeap = GetProcessHeap();
    v7 = (HANDLE *)HeapAlloc(ProcessHeap, 8u, 0x18u);
    v3 = v7;
    if ( v7 )
    {
      *v7 = (HANDLE)*((_QWORD *)a1 + 1);
      v7[1] = (HANDLE)*((_QWORD *)a1 + 2);
      EventW = CreateEventW(0, 1, 0, 0);
      v3[2] = EventW;
      if ( EventW )
      {
        if ( QueueUserWorkItem(IcsIPv6PrefixSharingDeRegisterNotificationsWorker, v3, 0) )
        {
          *((_QWORD *)a1 + 2) = 0;
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 64));
          WaitForSingleObject(v3[2], 0xFFFFFFFF);
          goto LABEL_35;
        }
        LastError = GetLastError();
        v4 = LastError;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v9 = 60;
          v10 = LastError;
          goto LABEL_23;
        }
      }
      else
      {
        v12 = GetLastError();
        v4 = v12;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v9 = 59;
          v10 = v12;
          goto LABEL_23;
        }
      }
    }
    else
    {
      v4 = 8;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = 58;
        v10 = 8;
LABEL_23:
        WPP_SF_d(v8[2], v9, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids, v10);
      }
    }
LABEL_7:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 64));
    if ( !v3 )
    {
LABEL_8:
      v2 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_9;
    }
LABEL_35:
    v14 = v3[2];
    if ( v14 )
      CloseHandle(v14);
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v3);
    goto LABEL_8;
  }
  v4 = 1;
  if ( v2 != &WPP_GLOBAL_Control && *((char *)v2 + 28) < 0 && *((_BYTE *)v2 + 25) >= 2u )
  {
    WPP_SF_d(v2[2], 57, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids, 1);
    goto LABEL_8;
  }
LABEL_9:
  if ( v2 != &WPP_GLOBAL_Control && *((char *)v2 + 28) < 0 && *((_BYTE *)v2 + 25) >= 6u )
    WPP_SF_d(v2[2], 61, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18000e850  sub     rsp, 28h
0x18000e854  mov     [rsp+28h+arg_0], rbx
0x18000e859  mov     rbx, rcx
0x18000e85c  mov     [rsp+28h+var_8], r14
0x18000e861  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e868  lea     r14, WPP_GLOBAL_Control
0x18000e86f  cmp     rcx, r14
0x18000e872  jz      short loc_18000E884
0x18000e874  test    byte ptr [rcx+1Ch], 80h
0x18000e878  jz      short loc_18000E884
0x18000e87a  cmp     byte ptr [rcx+19h], 6
0x18000e87e  jnb     loc_18000E93C
0x18000e884  cmp     dword ptr [rbx], 0
0x18000e887  mov     [rsp+28h+arg_8], rbp
0x18000e88c  jz      short loc_18000E90C
0x18000e88e  mov     [rsp+28h+arg_10], rsi
0x18000e893  lea     rcx, [rbx+40h]; lpCriticalSection
0x18000e897  mov     [rsp+28h+arg_18], rdi
0x18000e89c  xor     esi, esi
0x18000e89e  xor     ebp, ebp
0x18000e8a0  call    cs:__imp_EnterCriticalSection
0x18000e8a7  nop     dword ptr [rax+rax+00h]
0x18000e8ac  cmp     [rbx+10h], rsi
0x18000e8b0  jnz     loc_18000E95D
0x18000e8b6  lea     rcx, [rbx+40h]; lpCriticalSection
0x18000e8ba  call    cs:__imp_LeaveCriticalSection
0x18000e8c1  nop     dword ptr [rax+rax+00h]
0x18000e8c6  test    rsi, rsi
0x18000e8c9  jnz     loc_18000EAC8
0x18000e8cf  mov     rsi, [rsp+28h+arg_10]
0x18000e8d4  mov     rdi, [rsp+28h+arg_18]
0x18000e8d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e8e0  mov     rbx, [rsp+28h+arg_0]
0x18000e8e5  cmp     rcx, r14
0x18000e8e8  mov     r14, [rsp+28h+var_8]
0x18000e8ed  jz      short loc_18000E8FF
0x18000e8ef  test    byte ptr [rcx+1Ch], 80h
0x18000e8f3  jz      short loc_18000E8FF
0x18000e8f5  cmp     byte ptr [rcx+19h], 6
0x18000e8f9  jnb     loc_18000EB02
0x18000e8ff  mov     eax, ebp
0x18000e901  mov     rbp, [rsp+28h+arg_8]
0x18000e906  add     rsp, 28h
0x18000e90a  retn
0x18000e90c  mov     ebp, 1
0x18000e911  cmp     rcx, r14
0x18000e914  jz      short loc_18000E8E0
0x18000e916  test    byte ptr [rcx+1Ch], 80h
0x18000e91a  jz      short loc_18000E8E0
0x18000e91c  cmp     byte ptr [rcx+19h], 2
0x18000e920  jb      short loc_18000E8E0
0x18000e922  mov     rcx, [rcx+10h]
0x18000e926  lea     r8, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids
0x18000e92d  mov     edx, 39h ; '9'
0x18000e932  mov     r9d, ebp
0x18000e935  call    WPP_SF_d
0x18000e93a  jmp     short loc_18000E8D9
0x18000e93c  mov     rcx, [rcx+10h]
0x18000e940  lea     r8, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids
0x18000e947  mov     edx, 38h ; '8'
0x18000e94c  call    WPP_SF_
0x18000e951  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e958  jmp     loc_18000E884
0x18000e95d  call    cs:__imp_GetProcessHeap
0x18000e964  nop     dword ptr [rax+rax+00h]
0x18000e969  mov     edx, 8; dwFlags
0x18000e96e  mov     r8d, 18h; dwBytes
0x18000e974  mov     rcx, rax; hHeap
0x18000e977  call    cs:__imp_HeapAlloc
0x18000e97e  nop     dword ptr [rax+rax+00h]
0x18000e983  mov     rsi, rax
0x18000e986  test    rax, rax
0x18000e989  jnz     short loc_18000E9DB
0x18000e98b  mov     ebp, 8
0x18000e990  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e997  cmp     rcx, r14
0x18000e99a  jz      loc_18000E8B6
0x18000e9a0  test    byte ptr [rcx+1Ch], 80h
0x18000e9a4  jz      loc_18000E8B6
0x18000e9aa  cmp     byte ptr [rcx+19h], 2
0x18000e9ae  jb      loc_18000E8B6
0x18000e9b4  mov     edx, 3Ah ; ':'
0x18000e9b9  mov     r9d, ebp
0x18000e9bc  jmp     short loc_18000E9C6
0x18000e9be  mov     edx, 3Ch ; '<'
0x18000e9c3  mov     r9d, eax
0x18000e9c6  mov     rcx, [rcx+10h]
0x18000e9ca  lea     r8, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids
0x18000e9d1  call    WPP_SF_d
0x18000e9d6  jmp     loc_18000E8B6
0x18000e9db  mov     rax, [rbx+8]
0x18000e9df  xor     r9d, r9d; lpName
0x18000e9e2  mov     [rsi], rax
0x18000e9e5  xor     r8d, r8d; bInitialState
0x18000e9e8  mov     rax, [rbx+10h]
0x18000e9ec  mov     edx, 1; bManualReset
0x18000e9f1  xor     ecx, ecx; lpEventAttributes
0x18000e9f3  mov     [rsi+8], rax
0x18000e9f7  call    cs:__imp_CreateEventW
0x18000e9fe  nop     dword ptr [rax+rax+00h]
0x18000ea03  mov     [rsi+10h], rax
0x18000ea07  test    rax, rax
0x18000ea0a  jnz     short loc_18000EA4B
0x18000ea0c  call    cs:__imp_GetLastError
0x18000ea13  nop     dword ptr [rax+rax+00h]
0x18000ea18  mov     ebp, eax
0x18000ea1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea21  cmp     rcx, r14
0x18000ea24  jz      loc_18000E8B6
0x18000ea2a  test    byte ptr [rcx+1Ch], 80h
0x18000ea2e  jz      loc_18000E8B6
0x18000ea34  cmp     byte ptr [rcx+19h], 2
0x18000ea38  jb      loc_18000E8B6
0x18000ea3e  mov     edx, 3Bh ; ';'
0x18000ea43  mov     r9d, eax
0x18000ea46  jmp     loc_18000E9C6
0x18000ea4b  xor     r8d, r8d; Flags
0x18000ea4e  lea     rcx, ?IcsIPv6PrefixSharingDeRegisterNotificationsWorker@@YAKPEAX@Z; Function
0x18000ea55  mov     rdx, rsi; Context
0x18000ea58  call    cs:__imp_QueueUserWorkItem
0x18000ea5f  nop     dword ptr [rax+rax+00h]
0x18000ea64  test    eax, eax
0x18000ea66  jnz     short loc_18000EA9F
0x18000ea68  call    cs:__imp_GetLastError
0x18000ea6f  nop     dword ptr [rax+rax+00h]
0x18000ea74  mov     ebp, eax
0x18000ea76  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea7d  cmp     rcx, r14
0x18000ea80  jz      loc_18000E8B6
0x18000ea86  test    byte ptr [rcx+1Ch], 80h
0x18000ea8a  jz      loc_18000E8B6
0x18000ea90  cmp     byte ptr [rcx+19h], 2
0x18000ea94  jb      loc_18000E8B6
0x18000ea9a  jmp     loc_18000E9BE
0x18000ea9f  lea     rcx, [rbx+40h]; lpCriticalSection
0x18000eaa3  mov     [rbx+10h], rbp
0x18000eaa7  call    cs:__imp_LeaveCriticalSection
0x18000eaae  nop     dword ptr [rax+rax+00h]
0x18000eab3  mov     rcx, [rsi+10h]; hHandle
0x18000eab7  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000eabc  call    cs:__imp_WaitForSingleObject
0x18000eac3  nop     dword ptr [rax+rax+00h]
0x18000eac8  mov     rcx, [rsi+10h]; hObject
0x18000eacc  test    rcx, rcx
0x18000eacf  jz      short loc_18000EADD
0x18000ead1  call    cs:__imp_CloseHandle
0x18000ead8  nop     dword ptr [rax+rax+00h]
0x18000eadd  call    cs:__imp_GetProcessHeap
0x18000eae4  nop     dword ptr [rax+rax+00h]
0x18000eae9  mov     r8, rsi; lpMem
0x18000eaec  xor     edx, edx; dwFlags
0x18000eaee  mov     rcx, rax; hHeap
0x18000eaf1  call    cs:__imp_HeapFree
0x18000eaf8  nop     dword ptr [rax+rax+00h]
0x18000eafd  jmp     loc_18000E8CF
0x18000eb02  mov     rcx, [rcx+10h]
0x18000eb06  lea     r8, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids
0x18000eb0d  mov     edx, 3Dh ; '='
0x18000eb12  mov     r9d, ebp
0x18000eb15  call    WPP_SF_d
0x18000eb1a  jmp     loc_18000E8FF
```
