# FwTriggerUnregisterWait

- ea: `0x18002b1a0`
- end: `0x18002b28c`
- name: `FwTriggerUnregisterWait`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180012c00`

## callees

- `0x180004840`
- `0x18000ccd4`
- `0x180017d1c`
- `0x18002b1a0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b23e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b23e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18002b22c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18002b22c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18002b223`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18002b223`

## pseudocode

```c
__int64 __fastcall FwTriggerUnregisterWait(__int64 a1)
{
  _QWORD *v2; // rcx
  unsigned int v3; // edi
  void *v4; // rcx

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_daa71961c68f3192cca7fdfb2d6e33f5_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    v3 = 0;
    if ( *(_QWORD *)a1 )
    {
      WaitForThreadpoolWaitCallbacks(*(PTP_WAIT *)a1, 1);
      CloseThreadpoolWait(*(PTP_WAIT *)a1);
      *(_QWORD *)a1 = 0;
    }
    v4 = *(void **)(a1 + 8);
    if ( v4 )
    {
      CloseHandle(v4);
      *(_QWORD *)(a1 + 8) = 0;
    }
    FwFree(a1);
    goto LABEL_13;
  }
  v3 = 87;
  if ( v2 == &WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)v2 + 28) & 1) != 0 )
  {
    WPP_SF_d(v2[2], 17, WPP_daa71961c68f3192cca7fdfb2d6e33f5_Traceguids, 87);
LABEL_13:
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
    WPP_SF_d(v2[2], 18, WPP_daa71961c68f3192cca7fdfb2d6e33f5_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x18002b1a0  mov     [rsp+arg_0], rbx
0x18002b1a5  mov     [rsp+arg_8], rsi
0x18002b1aa  push    rdi
0x18002b1ab  sub     rsp, 20h
0x18002b1af  mov     rbx, rcx
0x18002b1b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b1b9  lea     rsi, WPP_GLOBAL_Control
0x18002b1c0  cmp     rcx, rsi
0x18002b1c3  jz      short loc_18002B1E7
0x18002b1c5  test    byte ptr [rcx+1Ch], 8
0x18002b1c9  jz      short loc_18002B1E7
0x18002b1cb  mov     rcx, [rcx+10h]
0x18002b1cf  lea     r8, WPP_daa71961c68f3192cca7fdfb2d6e33f5_Traceguids
0x18002b1d6  mov     edx, 10h
0x18002b1db  call    WPP_SF_
0x18002b1e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b1e7  test    rbx, rbx
0x18002b1ea  jnz     short loc_18002B216
0x18002b1ec  lea     edi, [rbx+57h]
0x18002b1ef  cmp     rcx, rsi
0x18002b1f2  jz      loc_18002B27A
0x18002b1f8  test    byte ptr [rcx+1Ch], 1
0x18002b1fc  jz      short loc_18002B257
0x18002b1fe  mov     rcx, [rcx+10h]
0x18002b202  lea     edx, [rbx+11h]
0x18002b205  mov     r9d, edi
0x18002b208  lea     r8, WPP_daa71961c68f3192cca7fdfb2d6e33f5_Traceguids
0x18002b20f  call    WPP_SF_d
0x18002b214  jmp     short loc_18002B250
0x18002b216  mov     rcx, [rbx]; pwa
0x18002b219  xor     edi, edi
0x18002b21b  test    rcx, rcx
0x18002b21e  jz      short loc_18002B235
0x18002b220  lea     edx, [rdi+1]; fCancelPendingCallbacks
0x18002b223  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18002b229  mov     rcx, [rbx]; pwa
0x18002b22c  call    cs:__imp_CloseThreadpoolWait
0x18002b232  mov     [rbx], rdi
0x18002b235  mov     rcx, [rbx+8]; hObject
0x18002b239  test    rcx, rcx
0x18002b23c  jz      short loc_18002B248
0x18002b23e  call    cs:__imp_CloseHandle
0x18002b244  mov     [rbx+8], rdi
0x18002b248  mov     rcx, rbx
0x18002b24b  call    FwFree
0x18002b250  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b257  cmp     rcx, rsi
0x18002b25a  jz      short loc_18002B27A
0x18002b25c  test    byte ptr [rcx+1Ch], 8
0x18002b260  jz      short loc_18002B27A
0x18002b262  mov     rcx, [rcx+10h]
0x18002b266  lea     r8, WPP_daa71961c68f3192cca7fdfb2d6e33f5_Traceguids
0x18002b26d  mov     edx, 12h
0x18002b272  mov     r9d, edi
0x18002b275  call    WPP_SF_d
0x18002b27a  mov     rbx, [rsp+28h+arg_0]
0x18002b27f  mov     eax, edi
0x18002b281  mov     rsi, [rsp+28h+arg_8]
0x18002b286  add     rsp, 20h
0x18002b28a  pop     rdi
0x18002b28b  retn
```
