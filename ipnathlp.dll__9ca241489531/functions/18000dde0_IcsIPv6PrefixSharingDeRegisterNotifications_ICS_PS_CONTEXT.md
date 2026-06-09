# IcsIPv6PrefixSharingDeRegisterNotifications(_ICS_PS_CONTEXT *)

- ea: `0x18000dde0`
- end: `0x18000e05d`
- name: `?IcsIPv6PrefixSharingDeRegisterNotifications@@YAKPEAU_ICS_PS_CONTEXT@@@Z`
- size: `637`
- prototype: `unsigned int __fastcall(struct _ICS_PS_CONTEXT *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000cc20`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18000dde0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dee0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e027`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dee0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e027`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000def4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000def4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e035`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e035`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000de30`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000de30`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000de44`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e003`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000de44`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e003`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000df6e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000df6e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000e012`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000e012`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dfca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dfca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e021`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e021`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18000dfc0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18000dfc0`

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
0x18000dde0  sub     rsp, 28h
0x18000dde4  mov     [rsp+28h+arg_0], rbx
0x18000dde9  mov     rbx, rcx
0x18000ddec  mov     [rsp+28h+var_8], r14
0x18000ddf1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ddf8  lea     r14, WPP_GLOBAL_Control
0x18000ddff  cmp     rcx, r14
0x18000de02  jz      short loc_18000DE14
0x18000de04  test    byte ptr [rcx+1Ch], 80h
0x18000de08  jz      short loc_18000DE14
0x18000de0a  cmp     byte ptr [rcx+19h], 6
0x18000de0e  jnb     loc_18000DEBF
0x18000de14  cmp     dword ptr [rbx], 0
0x18000de17  mov     [rsp+28h+arg_8], rbp
0x18000de1c  jz      short loc_18000DE8F
0x18000de1e  mov     [rsp+28h+arg_10], rsi
0x18000de23  lea     rcx, [rbx+40h]; lpCriticalSection
0x18000de27  mov     [rsp+28h+arg_18], rdi
0x18000de2c  xor     esi, esi
0x18000de2e  xor     ebp, ebp
0x18000de30  call    cs:__imp_EnterCriticalSection
0x18000de36  cmp     [rbx+10h], rsi
0x18000de3a  jnz     loc_18000DEE0
0x18000de40  lea     rcx, [rbx+40h]; lpCriticalSection
0x18000de44  call    cs:__imp_LeaveCriticalSection
0x18000de4a  test    rsi, rsi
0x18000de4d  jnz     loc_18000E018
0x18000de53  mov     rsi, [rsp+28h+arg_10]
0x18000de58  mov     rdi, [rsp+28h+arg_18]
0x18000de5d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de64  mov     rbx, [rsp+28h+arg_0]
0x18000de69  cmp     rcx, r14
0x18000de6c  mov     r14, [rsp+28h+var_8]
0x18000de71  jz      short loc_18000DE83
0x18000de73  test    byte ptr [rcx+1Ch], 80h
0x18000de77  jz      short loc_18000DE83
0x18000de79  cmp     byte ptr [rcx+19h], 6
0x18000de7d  jnb     loc_18000E040
0x18000de83  mov     eax, ebp
0x18000de85  mov     rbp, [rsp+28h+arg_8]
0x18000de8a  add     rsp, 28h
0x18000de8e  retn
0x18000de8f  mov     ebp, 1
0x18000de94  cmp     rcx, r14
0x18000de97  jz      short loc_18000DE64
0x18000de99  test    byte ptr [rcx+1Ch], 80h
0x18000de9d  jz      short loc_18000DE64
0x18000de9f  cmp     byte ptr [rcx+19h], 2
0x18000dea3  jb      short loc_18000DE64
0x18000dea5  mov     rcx, [rcx+10h]
0x18000dea9  lea     r8, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids
0x18000deb0  mov     edx, 39h ; '9'
0x18000deb5  mov     r9d, ebp
0x18000deb8  call    WPP_SF_d
0x18000debd  jmp     short loc_18000DE5D
0x18000debf  mov     rcx, [rcx+10h]
0x18000dec3  lea     r8, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids
0x18000deca  mov     edx, 38h ; '8'
0x18000decf  call    WPP_SF_
0x18000ded4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dedb  jmp     loc_18000DE14
0x18000dee0  call    cs:__imp_GetProcessHeap
0x18000dee6  mov     edx, 8; dwFlags
0x18000deeb  mov     r8d, 18h; dwBytes
0x18000def1  mov     rcx, rax; hHeap
0x18000def4  call    cs:__imp_HeapAlloc
0x18000defa  mov     rsi, rax
0x18000defd  test    rax, rax
0x18000df00  jnz     short loc_18000DF52
0x18000df02  mov     ebp, 8
0x18000df07  mov     rcx, cs:WPP_GLOBAL_Control
0x18000df0e  cmp     rcx, r14
0x18000df11  jz      loc_18000DE40
0x18000df17  test    byte ptr [rcx+1Ch], 80h
0x18000df1b  jz      loc_18000DE40
0x18000df21  cmp     byte ptr [rcx+19h], 2
0x18000df25  jb      loc_18000DE40
0x18000df2b  mov     edx, 3Ah ; ':'
0x18000df30  mov     r9d, ebp
0x18000df33  jmp     short loc_18000DF3D
0x18000df35  mov     edx, 3Ch ; '<'
0x18000df3a  mov     r9d, eax
0x18000df3d  mov     rcx, [rcx+10h]
0x18000df41  lea     r8, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids
0x18000df48  call    WPP_SF_d
0x18000df4d  jmp     loc_18000DE40
0x18000df52  mov     rax, [rbx+8]
0x18000df56  xor     r9d, r9d; lpName
0x18000df59  mov     [rsi], rax
0x18000df5c  xor     r8d, r8d; bInitialState
0x18000df5f  mov     rax, [rbx+10h]
0x18000df63  mov     edx, 1; bManualReset
0x18000df68  xor     ecx, ecx; lpEventAttributes
0x18000df6a  mov     [rsi+8], rax
0x18000df6e  call    cs:__imp_CreateEventW
0x18000df74  mov     [rsi+10h], rax
0x18000df78  test    rax, rax
0x18000df7b  jnz     short loc_18000DFB3
0x18000df7d  call    cs:__imp_GetLastError
0x18000df83  mov     ebp, eax
0x18000df85  mov     rcx, cs:WPP_GLOBAL_Control
0x18000df8c  cmp     rcx, r14
0x18000df8f  jz      loc_18000DE40
0x18000df95  test    byte ptr [rcx+1Ch], 80h
0x18000df99  jz      loc_18000DE40
0x18000df9f  cmp     byte ptr [rcx+19h], 2
0x18000dfa3  jb      loc_18000DE40
0x18000dfa9  mov     edx, 3Bh ; ';'
0x18000dfae  mov     r9d, eax
0x18000dfb1  jmp     short loc_18000DF3D
0x18000dfb3  xor     r8d, r8d; Flags
0x18000dfb6  lea     rcx, ?IcsIPv6PrefixSharingDeRegisterNotificationsWorker@@YAKPEAX@Z; Function
0x18000dfbd  mov     rdx, rsi; Context
0x18000dfc0  call    cs:__imp_QueueUserWorkItem
0x18000dfc6  test    eax, eax
0x18000dfc8  jnz     short loc_18000DFFB
0x18000dfca  call    cs:__imp_GetLastError
0x18000dfd0  mov     ebp, eax
0x18000dfd2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dfd9  cmp     rcx, r14
0x18000dfdc  jz      loc_18000DE40
0x18000dfe2  test    byte ptr [rcx+1Ch], 80h
0x18000dfe6  jz      loc_18000DE40
0x18000dfec  cmp     byte ptr [rcx+19h], 2
0x18000dff0  jb      loc_18000DE40
0x18000dff6  jmp     loc_18000DF35
0x18000dffb  lea     rcx, [rbx+40h]; lpCriticalSection
0x18000dfff  mov     [rbx+10h], rbp
0x18000e003  call    cs:__imp_LeaveCriticalSection
0x18000e009  mov     rcx, [rsi+10h]; hHandle
0x18000e00d  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000e012  call    cs:__imp_WaitForSingleObject
0x18000e018  mov     rcx, [rsi+10h]; hObject
0x18000e01c  test    rcx, rcx
0x18000e01f  jz      short loc_18000E027
0x18000e021  call    cs:__imp_CloseHandle
0x18000e027  call    cs:__imp_GetProcessHeap
0x18000e02d  mov     r8, rsi; lpMem
0x18000e030  xor     edx, edx; dwFlags
0x18000e032  mov     rcx, rax; hHeap
0x18000e035  call    cs:__imp_HeapFree
0x18000e03b  jmp     loc_18000DE53
0x18000e040  mov     rcx, [rcx+10h]
0x18000e044  lea     r8, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids
0x18000e04b  mov     edx, 3Dh ; '='
0x18000e050  mov     r9d, ebp
0x18000e053  call    WPP_SF_d
0x18000e058  jmp     loc_18000DE83
```
