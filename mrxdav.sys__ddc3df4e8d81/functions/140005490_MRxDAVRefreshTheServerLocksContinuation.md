# MRxDAVRefreshTheServerLocksContinuation

- ea: `0x140005490`
- end: `0x14000554b`
- name: `MRxDAVRefreshTheServerLocksContinuation`
- size: `187`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x140005490`
- `0x1400287f4`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x1400054c0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140005517`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400054c0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140005517`

## pseudocode

```c
__int64 __fastcall MRxDAVRefreshTheServerLocksContinuation(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rbx
  HANDLE CurrentThreadId; // rax
  unsigned int v6; // edi
  __int64 v7; // rbx
  HANDLE v8; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v4 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    CurrentThreadId = PsGetCurrentThreadId();
    WPP_SF_q(v4, 42, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids, CurrentThreadId);
  }
  v6 = UMRxSubmitAsyncEngUserModeRequest(
         a1,
         a2,
         (__int64)MRxDAVFormatUserModeRefreshTheServerLockRequest,
         (__int64)MRxDAVPrecompleteUserModeRefreshTheServerLockRequest);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v7 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v8 = PsGetCurrentThreadId();
    WPP_SF_qD(v7, 43, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids, v8, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x140005490  push    rbx
0x140005492  push    rsi
0x140005493  push    rdi
0x140005494  push    r14
0x140005496  sub     rsp, 38h
0x14000549a  mov     rdi, rdx
0x14000549d  mov     rsi, rcx
0x1400054a0  mov     rbx, cs:WPP_GLOBAL_Control
0x1400054a7  lea     r14, WPP_GLOBAL_Control
0x1400054ae  cmp     rbx, r14
0x1400054b1  jz      short loc_1400054E3
0x1400054b3  test    dword ptr [rbx+2Ch], 4000h
0x1400054ba  jz      short loc_1400054E3
0x1400054bc  mov     rbx, [rbx+18h]
0x1400054c0  call    cs:__imp_PsGetCurrentThreadId
0x1400054c7  nop     dword ptr [rax+rax+00h]
0x1400054cc  mov     edx, 2Ah ; '*'
0x1400054d1  lea     r8, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids
0x1400054d8  mov     r9, rax
0x1400054db  mov     rcx, rbx
0x1400054de  call    WPP_SF_q
0x1400054e3  lea     r9, MRxDAVPrecompleteUserModeRefreshTheServerLockRequest
0x1400054ea  mov     rdx, rdi
0x1400054ed  lea     r8, MRxDAVFormatUserModeRefreshTheServerLockRequest
0x1400054f4  mov     rcx, rsi
0x1400054f7  call    UMRxSubmitAsyncEngUserModeRequest
0x1400054fc  mov     edi, eax
0x1400054fe  mov     rbx, cs:WPP_GLOBAL_Control
0x140005505  cmp     rbx, r14
0x140005508  jz      short loc_14000553E
0x14000550a  test    dword ptr [rbx+2Ch], 4000h
0x140005511  jz      short loc_14000553E
0x140005513  mov     rbx, [rbx+18h]
0x140005517  call    cs:__imp_PsGetCurrentThreadId
0x14000551e  nop     dword ptr [rax+rax+00h]
0x140005523  mov     edx, 2Bh ; '+'
0x140005528  mov     [rsp+58h+var_38], edi
0x14000552c  mov     r9, rax
0x14000552f  lea     r8, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids
0x140005536  mov     rcx, rbx
0x140005539  call    WPP_SF_qD
0x14000553e  mov     eax, edi
0x140005540  add     rsp, 38h
0x140005544  pop     r14
0x140005546  pop     rdi
0x140005547  pop     rsi
0x140005548  pop     rbx
0x140005549  retn
```
