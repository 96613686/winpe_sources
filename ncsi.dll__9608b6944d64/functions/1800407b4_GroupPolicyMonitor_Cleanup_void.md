# GroupPolicyMonitor::Cleanup(void)

- ea: `0x1800407b4`
- end: `0x180040853`
- name: `?Cleanup@GroupPolicyMonitor@@IEAAXXZ`
- size: `159`
- prototype: `void __fastcall(GroupPolicyMonitor *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180040784`
- `0x18005d8a0`
- `0x18005da88`

## callees

- `0x180011a58`
- `0x1800407b4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800407cb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800407cb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800407da`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800407da`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800407e4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800407e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040824`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040824`
- `USERENV!UnregisterGPNotification` at `0x1800407fb`
- `USERENV!UnregisterGPNotification` at `0x1800407fb`

## pseudocode

```c
void __fastcall GroupPolicyMonitor::Cleanup(GroupPolicyMonitor *this)
{
  struct _TP_WAIT *v2; // rcx
  DWORD LastError; // eax

  v2 = (struct _TP_WAIT *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    SetThreadpoolWait(v2, 0, 0);
    WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)this + 1), 1);
    CloseThreadpoolWait(*((PTP_WAIT *)this + 1));
    *((_QWORD *)this + 1) = 0;
  }
  if ( *((_BYTE *)this + 16) )
  {
    if ( !UnregisterGPNotification(*(HANDLE *)this)
      && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
    {
      LastError = GetLastError();
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 17, WPP_8c649a3b49c335dd6fdbca526a2b3512_Traceguids, LastError);
    }
    *((_BYTE *)this + 16) = 0;
  }
}

```

## disassembly

```asm
0x1800407b4  push    rbx
0x1800407b6  sub     rsp, 20h
0x1800407ba  mov     rbx, rcx
0x1800407bd  mov     rcx, [rcx+8]; pwa
0x1800407c1  test    rcx, rcx
0x1800407c4  jz      short loc_1800407F2
0x1800407c6  xor     r8d, r8d; pftTimeout
0x1800407c9  xor     edx, edx; h
0x1800407cb  call    cs:__imp_SetThreadpoolWait
0x1800407d1  mov     rcx, [rbx+8]; pwa
0x1800407d5  mov     edx, 1; fCancelPendingCallbacks
0x1800407da  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800407e0  mov     rcx, [rbx+8]; pwa
0x1800407e4  call    cs:__imp_CloseThreadpoolWait
0x1800407ea  mov     qword ptr [rbx+8], 0
0x1800407f2  cmp     byte ptr [rbx+10h], 0
0x1800407f6  jz      short loc_18004084D
0x1800407f8  mov     rcx, [rbx]; hEvent
0x1800407fb  call    cs:__imp_UnregisterGPNotification
0x180040801  test    eax, eax
0x180040803  jnz     short loc_180040849
0x180040805  mov     rax, cs:WPP_GLOBAL_Control
0x18004080c  lea     rcx, WPP_GLOBAL_Control
0x180040813  cmp     rax, rcx
0x180040816  jz      short loc_180040849
0x180040818  test    byte ptr [rax+1Ch], 10h
0x18004081c  jz      short loc_180040849
0x18004081e  cmp     byte ptr [rax+19h], 3
0x180040822  jb      short loc_180040849
0x180040824  call    cs:__imp_GetLastError
0x18004082a  mov     rcx, cs:WPP_GLOBAL_Control
0x180040831  lea     r8, WPP_8c649a3b49c335dd6fdbca526a2b3512_Traceguids
0x180040838  mov     edx, 11h
0x18004083d  mov     r9d, eax
0x180040840  mov     rcx, [rcx+10h]
0x180040844  call    WPP_SF_d
0x180040849  mov     byte ptr [rbx+10h], 0
0x18004084d  add     rsp, 20h
0x180040851  pop     rbx
0x180040852  retn
```
