# ServiceDispatcherThread(void *)

- ea: `0x1800f3260`
- end: `0x1800f3477`
- name: `?ServiceDispatcherThread@@YAKPEAX@Z`
- size: `535`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180011278`
- `0x1800284d4`
- `0x1800ada18`
- `0x1800f3260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800f32eb`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800f32eb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f32b0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f32b0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800f3385`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800f3385`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f32c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f32ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f3434`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f32c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f32ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f3434`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f3396`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f3396`
- `api-ms-win-service-core-l1-1-0!StartServiceCtrlDispatcherW` at `0x1800f33fe`
- `api-ms-win-service-core-l1-1-0!StartServiceCtrlDispatcherW` at `0x1800f33fe`
- `api-ms-win-service-private-l1-1-0!I_ScIsSecurityProcess` at `0x1800f33eb`
- `api-ms-win-service-private-l1-1-0!I_ScIsSecurityProcess` at `0x1800f33eb`

## string_xrefs

- `0x1800f32a3`: `SECURITY_SERVICES_STARTED`
- `0x1800f32dd`: `SECURITY_SERVICES_STARTED`

## pseudocode

```c
__int64 __fastcall ServiceDispatcherThread(PVOID Parameter)
{
  HANDLE EventW; // rdi
  DWORD LastError; // ebx
  LsaHandleCache *v3; // rcx
  __int64 v4; // rdx
  DWORD v5; // eax

  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids);
  }
  EventW = CreateEventW(0, 1, 0, L"SECURITY_SERVICES_STARTED");
  if ( EventW )
    goto LABEL_14;
  LastError = GetLastError();
  if ( LastError == 183 )
  {
    EventW = OpenEventW(0x1F0003u, 0, L"SECURITY_SERVICES_STARTED");
    if ( !EventW )
    {
      LastError = GetLastError();
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      {
        v4 = 49;
LABEL_10:
        WPP_SF_d(*((_QWORD *)v3 + 2), v4, &WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids, LastError);
        return LastError;
      }
      return LastError;
    }
LABEL_14:
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids);
    }
    LastError = WaitForSingleObject(EventW, 0xFFFFFFFF);
    CloseHandle(EventW);
    if ( LastError )
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      {
        v4 = 52;
        goto LABEL_10;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids);
      }
      I_ScIsSecurityProcess();
      LastError = StartServiceCtrlDispatcherW(&SecurityServiceDispatchTable);
      if ( LastError )
      {
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids);
        }
      }
      else
      {
        v5 = GetLastError();
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
        {
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids, v5, v5);
        }
      }
    }
    return LastError;
  }
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
  {
    v4 = 50;
    goto LABEL_10;
  }
  return LastError;
}

```

## disassembly

```asm
0x1800f3260  push    rbx
0x1800f3262  push    rbp
0x1800f3263  push    rsi
0x1800f3264  push    rdi
0x1800f3265  push    r14
0x1800f3267  sub     rsp, 30h
0x1800f326b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f3272  lea     rbp, WPP_GLOBAL_Control
0x1800f3279  lea     r14, WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids
0x1800f3280  mov     esi, 8000000h
0x1800f3285  cmp     rcx, rbp
0x1800f3288  jz      short loc_1800F32A0
0x1800f328a  test    [rcx+1Ch], esi
0x1800f328d  jz      short loc_1800F32A0
0x1800f328f  mov     rcx, [rcx+10h]
0x1800f3293  mov     edx, 30h ; '0'
0x1800f3298  mov     r8, r14
0x1800f329b  call    WPP_SF_
0x1800f32a0  xor     r8d, r8d; bInitialState
0x1800f32a3  lea     r9, aSecurityServic; "SECURITY_SERVICES_STARTED"
0x1800f32aa  xor     ecx, ecx; lpEventAttributes
0x1800f32ac  lea     edx, [r8+1]; bManualReset
0x1800f32b0  call    cs:__imp_CreateEventW
0x1800f32b7  nop     dword ptr [rax+rax+00h]
0x1800f32bc  mov     rdi, rax
0x1800f32bf  test    rax, rax
0x1800f32c2  jnz     loc_1800F335D
0x1800f32c8  call    cs:__imp_GetLastError
0x1800f32cf  nop     dword ptr [rax+rax+00h]
0x1800f32d4  mov     ebx, eax
0x1800f32d6  cmp     eax, 0B7h
0x1800f32db  jnz     short loc_1800F333D
0x1800f32dd  lea     r8, aSecurityServic; "SECURITY_SERVICES_STARTED"
0x1800f32e4  xor     edx, edx; bInheritHandle
0x1800f32e6  mov     ecx, 1F0003h; dwDesiredAccess
0x1800f32eb  call    cs:__imp_OpenEventW
0x1800f32f2  nop     dword ptr [rax+rax+00h]
0x1800f32f7  mov     rdi, rax
0x1800f32fa  test    rax, rax
0x1800f32fd  jnz     short loc_1800F335D
0x1800f32ff  call    cs:__imp_GetLastError
0x1800f3306  nop     dword ptr [rax+rax+00h]
0x1800f330b  mov     ebx, eax
0x1800f330d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f3314  cmp     rcx, rbp
0x1800f3317  jz      loc_1800F3469
0x1800f331d  test    [rcx+1Ch], esi
0x1800f3320  jz      loc_1800F3469
0x1800f3326  lea     edx, [rdi+31h]
0x1800f3329  mov     rcx, [rcx+10h]
0x1800f332d  mov     r9d, ebx
0x1800f3330  mov     r8, r14
0x1800f3333  call    WPP_SF_d
0x1800f3338  jmp     loc_1800F3469
0x1800f333d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f3344  cmp     rcx, rbp
0x1800f3347  jz      loc_1800F3469
0x1800f334d  test    [rcx+1Ch], esi
0x1800f3350  jz      loc_1800F3469
0x1800f3356  mov     edx, 32h ; '2'
0x1800f335b  jmp     short loc_1800F3329
0x1800f335d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f3364  cmp     rcx, rbp
0x1800f3367  jz      short loc_1800F337F
0x1800f3369  test    [rcx+1Ch], esi
0x1800f336c  jz      short loc_1800F337F
0x1800f336e  mov     rcx, [rcx+10h]
0x1800f3372  mov     edx, 33h ; '3'
0x1800f3377  mov     r8, r14
0x1800f337a  call    WPP_SF_
0x1800f337f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800f3382  mov     rcx, rdi; hHandle
0x1800f3385  call    cs:__imp_WaitForSingleObject
0x1800f338c  nop     dword ptr [rax+rax+00h]
0x1800f3391  mov     rcx, rdi; hObject
0x1800f3394  mov     ebx, eax
0x1800f3396  call    cs:__imp_CloseHandle
0x1800f339d  nop     dword ptr [rax+rax+00h]
0x1800f33a2  test    ebx, ebx
0x1800f33a4  jz      short loc_1800F33C9
0x1800f33a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f33ad  cmp     rcx, rbp
0x1800f33b0  jz      loc_1800F3469
0x1800f33b6  test    [rcx+1Ch], esi
0x1800f33b9  jz      loc_1800F3469
0x1800f33bf  mov     edx, 34h ; '4'
0x1800f33c4  jmp     loc_1800F3329
0x1800f33c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f33d0  cmp     rcx, rbp
0x1800f33d3  jz      short loc_1800F33EB
0x1800f33d5  test    [rcx+1Ch], esi
0x1800f33d8  jz      short loc_1800F33EB
0x1800f33da  mov     rcx, [rcx+10h]
0x1800f33de  mov     edx, 35h ; '5'
0x1800f33e3  mov     r8, r14
0x1800f33e6  call    WPP_SF_
0x1800f33eb  call    cs:__imp_I_ScIsSecurityProcess
0x1800f33f2  nop     dword ptr [rax+rax+00h]
0x1800f33f7  lea     rcx, ?SecurityServiceDispatchTable@@3PAU_SERVICE_TABLE_ENTRYW@@A; lpServiceStartTable
0x1800f33fe  call    cs:__imp_StartServiceCtrlDispatcherW
0x1800f3405  nop     dword ptr [rax+rax+00h]
0x1800f340a  mov     ebx, eax
0x1800f340c  test    eax, eax
0x1800f340e  jz      short loc_1800F3434
0x1800f3410  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f3417  cmp     rcx, rbp
0x1800f341a  jz      short loc_1800F3469
0x1800f341c  test    [rcx+1Ch], esi
0x1800f341f  jz      short loc_1800F3469
0x1800f3421  mov     rcx, [rcx+10h]
0x1800f3425  mov     edx, 36h ; '6'
0x1800f342a  mov     r8, r14
0x1800f342d  call    WPP_SF_
0x1800f3432  jmp     short loc_1800F3469
0x1800f3434  call    cs:__imp_GetLastError
0x1800f343b  nop     dword ptr [rax+rax+00h]
0x1800f3440  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f3447  cmp     rcx, rbp
0x1800f344a  jz      short loc_1800F3469
0x1800f344c  test    [rcx+1Ch], esi
0x1800f344f  jz      short loc_1800F3469
0x1800f3451  mov     rcx, [rcx+10h]
0x1800f3455  mov     edx, 37h ; '7'
0x1800f345a  mov     r9d, eax
0x1800f345d  mov     [rsp+58h+var_38], eax
0x1800f3461  mov     r8, r14
0x1800f3464  call    WPP_SF_Dd
0x1800f3469  mov     eax, ebx
0x1800f346b  add     rsp, 30h
0x1800f346f  pop     r14
0x1800f3471  pop     rdi
0x1800f3472  pop     rsi
0x1800f3473  pop     rbp
0x1800f3474  pop     rbx
0x1800f3475  retn
```
