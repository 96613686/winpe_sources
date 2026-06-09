# NotifyCallback(void *,_MIB_NOTIFICATION_TYPE)

- ea: `0x18000d208`
- end: `0x18000d33d`
- name: `?NotifyCallback@@YAXPEAXW4_MIB_NOTIFICATION_TYPE@@@Z`
- size: `309`
- prototype: `void __fastcall(ULONG_PTR dwData, enum _MIB_NOTIFICATION_TYPE)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d350`
- `0x18000d3b0`
- `0x18000d410`

## callees

- `0x180004f34`
- `0x18000d208`
- `0x18000dd40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d331`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000d249`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000d249`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d2cc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d2cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d21b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d21b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d289`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d289`
- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x18000d263`
- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x18000d263`

## string_xrefs

- `0x18000d2f0`: `MibDeleteInstance`

## pseudocode

```c
void __fastcall NotifyCallback(ULONG_PTR dwData, enum _MIB_NOTIFICATION_TYPE a2)
{
  int v4; // r8d
  PVOID *v5; // rax
  DWORD LastError; // eax
  const char *v7; // r9

  EnterCriticalSection((LPCRITICAL_SECTION)(dwData + 72));
  if ( !*(_DWORD *)(dwData + 64) )
    goto LABEL_15;
  if ( *(_DWORD *)(dwData + 120) )
  {
    SetEvent(*(HANDLE *)dwData);
  }
  else
  {
    WaitForSingleObject(*(HANDLE *)(dwData + 56), 0xFFFFFFFF);
    if ( QueueUserAPC(RouteChangeNotifierAPC, *(HANDLE *)(dwData + 48), dwData) )
    {
      *(_DWORD *)(dwData + 120) = 1;
      *(_DWORD *)(dwData + 136) = 0;
    }
    else
    {
      v5 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_15;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_10;
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_b6091e6574da34fd67da549d87f23c15_Traceguids, LastError);
    }
  }
  v5 = (PVOID *)WPP_GLOBAL_Control;
LABEL_10:
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 4) != 0 )
  {
    ++*(_DWORD *)(dwData + 136);
    v7 = "MibAddInstance";
    if ( a2 != MibAddInstance )
      v7 = "MibDeleteInstance";
    WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, v4, (_DWORD)v7, *(_DWORD *)(dwData + 136));
  }
LABEL_15:
  LeaveCriticalSection((LPCRITICAL_SECTION)(dwData + 72));
}

```

## disassembly

```asm
0x18000d208  push    rbx
0x18000d20a  push    rsi
0x18000d20b  push    rdi
0x18000d20c  push    r15
0x18000d20e  sub     rsp, 38h
0x18000d212  mov     rbx, rcx
0x18000d215  mov     esi, edx
0x18000d217  add     rcx, 48h ; 'H'; lpCriticalSection
0x18000d21b  call    cs:__imp_EnterCriticalSection
0x18000d222  nop     dword ptr [rax+rax+00h]
0x18000d227  cmp     dword ptr [rbx+40h], 0
0x18000d22b  jz      loc_18000D324
0x18000d231  cmp     dword ptr [rbx+78h], 0
0x18000d235  lea     r15, WPP_GLOBAL_Control
0x18000d23c  jnz     loc_18000D2C9
0x18000d242  mov     rcx, [rbx+38h]; hHandle
0x18000d246  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000d249  call    cs:__imp_WaitForSingleObject
0x18000d250  nop     dword ptr [rax+rax+00h]
0x18000d255  mov     rdx, [rbx+30h]; hThread
0x18000d259  lea     rcx, ?RouteChangeNotifierAPC@@YAX_K@Z; pfnAPC
0x18000d260  mov     r8, rbx; dwData
0x18000d263  call    cs:__imp_QueueUserAPC
0x18000d26a  nop     dword ptr [rax+rax+00h]
0x18000d26f  test    eax, eax
0x18000d271  jnz     short loc_18000D2B6
0x18000d273  mov     rax, cs:WPP_GLOBAL_Control
0x18000d27a  cmp     rax, r15
0x18000d27d  jz      loc_18000D324
0x18000d283  test    byte ptr [rax+1Ch], 1
0x18000d287  jz      short loc_18000D2DF
0x18000d289  call    cs:__imp_GetLastError
0x18000d290  nop     dword ptr [rax+rax+00h]
0x18000d295  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d29c  lea     r8, WPP_b6091e6574da34fd67da549d87f23c15_Traceguids
0x18000d2a3  mov     edx, 0Dh
0x18000d2a8  mov     r9d, eax
0x18000d2ab  mov     rcx, [rcx+10h]
0x18000d2af  call    WPP_SF_d
0x18000d2b4  jmp     short loc_18000D2D8
0x18000d2b6  mov     dword ptr [rbx+78h], 1
0x18000d2bd  mov     dword ptr [rbx+88h], 0
0x18000d2c7  jmp     short loc_18000D2D8
0x18000d2c9  mov     rcx, [rbx]; hEvent
0x18000d2cc  call    cs:__imp_SetEvent
0x18000d2d3  nop     dword ptr [rax+rax+00h]
0x18000d2d8  mov     rax, cs:WPP_GLOBAL_Control
0x18000d2df  cmp     rax, r15
0x18000d2e2  jz      short loc_18000D324
0x18000d2e4  test    byte ptr [rax+1Ch], 4
0x18000d2e8  jz      short loc_18000D324
0x18000d2ea  inc     dword ptr [rbx+88h]
0x18000d2f0  lea     rcx, aMibdeleteinsta; "MibDeleteInstance"
0x18000d2f7  mov     eax, [rbx+88h]
0x18000d2fd  lea     r9, aMibaddinstance; "MibAddInstance"
0x18000d304  cmp     esi, 1
0x18000d307  mov     [rsp+58h+var_38], eax
0x18000d30b  mov     edx, 0Eh
0x18000d310  cmovnz  r9, rcx
0x18000d314  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d31b  mov     rcx, [rcx+10h]
0x18000d31f  call    WPP_SF_sd
0x18000d324  lea     rcx, [rbx+48h]
0x18000d328  add     rsp, 38h
0x18000d32c  pop     r15
0x18000d32e  pop     rdi
0x18000d32f  pop     rsi
0x18000d330  pop     rbx
0x18000d331  jmp     cs:__imp_LeaveCriticalSection
```
