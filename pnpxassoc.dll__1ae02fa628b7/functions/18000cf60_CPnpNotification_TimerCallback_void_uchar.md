# CPnpNotification::TimerCallback(void *,uchar)

- ea: `0x18000cf60`
- end: `0x18000d096`
- name: `?TimerCallback@CPnpNotification@@KAXPEAXE@Z`
- size: `310`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x18000cf60`
- `0x18000d2a8`
- `0x180014010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000cfd3`
- `msvcrt!_wcsicmp` at `0x18000cfd3`
- `KERNEL32!GetLastError` at `0x18000d03c`
- `KERNEL32!GetLastError` at `0x18000d03c`
- `KERNEL32!LeaveCriticalSection` at `0x18000d059`
- `KERNEL32!LeaveCriticalSection` at `0x18000d059`
- `KERNEL32!EnterCriticalSection` at `0x18000cfb8`
- `KERNEL32!EnterCriticalSection` at `0x18000cfb8`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18000d032`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18000d032`
- `CFGMGR32!CMP_WaitNoPendingInstallEvents` at `0x18000cff7`
- `CFGMGR32!CMP_WaitNoPendingInstallEvents` at `0x18000cff7`

## pseudocode

```c
void __fastcall CPnpNotification::TimerCallback(PVOID a1)
{
  _QWORD *v2; // rcx
  __int64 ***v3; // rax
  __int64 **v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // r9
  void *v7; // rdx

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)a1 + 6) + 72LL));
    v3 = (__int64 ***)(*((_QWORD *)a1 + 6) + 128LL);
    v4 = *v3;
    while ( v4 != (__int64 **)v3 )
    {
      if ( !_wcsicmp(*((const wchar_t **)a1 + 3), (const wchar_t *)v4[3]) )
      {
        if ( !*((_DWORD *)a1 + 14) && !CMP_WaitNoPendingInstallEvents(0) )
        {
          v5 = *((_QWORD *)a1 + 5);
          v6 = *((_QWORD *)a1 + 2);
          *((_DWORD *)a1 + 14) = 1;
          (*(void (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v5 + 32LL))(v5, 2147944003LL, 0, v6);
          v7 = (void *)*((_QWORD *)a1 + 4);
          if ( v7 )
          {
            if ( DeleteTimerQueueTimer(0, v7, 0) || GetLastError() == 997 )
              *((_QWORD *)a1 + 4) = 0;
          }
        }
        break;
      }
      v4 = (__int64 **)*v4;
      v3 = (__int64 ***)(*((_QWORD *)a1 + 6) + 128LL);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)a1 + 6) + 72LL));
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 25) >= 4u )
    WPP_SF_s(v2[2], 52, &WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids);
}

```

## disassembly

```asm
0x18000cf60  mov     [rsp+arg_0], rbx
0x18000cf65  mov     [rsp+arg_8], rsi
0x18000cf6a  push    rdi
0x18000cf6b  sub     rsp, 30h
0x18000cf6f  mov     rbx, rcx
0x18000cf72  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf79  lea     rsi, WPP_GLOBAL_Control
0x18000cf80  cmp     rcx, rsi
0x18000cf83  jz      short loc_18000CFA7
0x18000cf85  cmp     byte ptr [rcx+19h], 4
0x18000cf89  jb      short loc_18000CFA7
0x18000cf8b  mov     rcx, [rcx+10h]
0x18000cf8f  lea     r8, WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids
0x18000cf96  mov     edx, 33h ; '3'
0x18000cf9b  call    WPP_SF_s
0x18000cfa0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cfa7  test    rbx, rbx
0x18000cfaa  jz      loc_18000D066
0x18000cfb0  mov     rcx, [rbx+30h]
0x18000cfb4  add     rcx, 48h ; 'H'; lpCriticalSection
0x18000cfb8  call    cs:__imp_EnterCriticalSection
0x18000cfbe  mov     rax, [rbx+30h]
0x18000cfc2  sub     rax, 0FFFFFFFFFFFFFF80h
0x18000cfc6  mov     rdi, [rax]
0x18000cfc9  jmp     short loc_18000CFE8
0x18000cfcb  mov     rdx, [rdi+18h]; String2
0x18000cfcf  mov     rcx, [rbx+18h]; String1
0x18000cfd3  call    cs:__imp__wcsicmp
0x18000cfd9  test    eax, eax
0x18000cfdb  jz      short loc_18000CFEF
0x18000cfdd  mov     rax, [rbx+30h]
0x18000cfe1  mov     rdi, [rdi]
0x18000cfe4  sub     rax, 0FFFFFFFFFFFFFF80h
0x18000cfe8  cmp     rdi, rax
0x18000cfeb  jnz     short loc_18000CFCB
0x18000cfed  jmp     short loc_18000D051
0x18000cfef  cmp     dword ptr [rbx+38h], 0
0x18000cff3  jnz     short loc_18000D051
0x18000cff5  xor     ecx, ecx; dwTimeout
0x18000cff7  call    cs:__imp_CMP_WaitNoPendingInstallEvents
0x18000cffd  test    eax, eax
0x18000cfff  jnz     short loc_18000D051
0x18000d001  mov     rcx, [rbx+28h]
0x18000d005  xor     r8d, r8d
0x18000d008  mov     r9, [rbx+10h]
0x18000d00c  mov     edx, 80070643h
0x18000d011  mov     dword ptr [rbx+38h], 1
0x18000d018  mov     rax, [rcx]
0x18000d01b  mov     rax, [rax+20h]
0x18000d01f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d024  mov     rdx, [rbx+20h]; Timer
0x18000d028  test    rdx, rdx
0x18000d02b  jz      short loc_18000D051
0x18000d02d  xor     r8d, r8d; CompletionEvent
0x18000d030  xor     ecx, ecx; TimerQueue
0x18000d032  call    cs:__imp_DeleteTimerQueueTimer
0x18000d038  test    eax, eax
0x18000d03a  jnz     short loc_18000D049
0x18000d03c  call    cs:__imp_GetLastError
0x18000d042  cmp     eax, 3E5h
0x18000d047  jnz     short loc_18000D051
0x18000d049  mov     qword ptr [rbx+20h], 0
0x18000d051  mov     rcx, [rbx+30h]
0x18000d055  add     rcx, 48h ; 'H'; lpCriticalSection
0x18000d059  call    cs:__imp_LeaveCriticalSection
0x18000d05f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d066  cmp     rcx, rsi
0x18000d069  jz      short loc_18000D086
0x18000d06b  cmp     byte ptr [rcx+19h], 4
0x18000d06f  jb      short loc_18000D086
0x18000d071  mov     rcx, [rcx+10h]
0x18000d075  lea     r8, WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids
0x18000d07c  mov     edx, 34h ; '4'
0x18000d081  call    WPP_SF_s
0x18000d086  mov     rbx, [rsp+38h+arg_0]
0x18000d08b  mov     rsi, [rsp+38h+arg_8]
0x18000d090  add     rsp, 30h
0x18000d094  pop     rdi
0x18000d095  retn
```
