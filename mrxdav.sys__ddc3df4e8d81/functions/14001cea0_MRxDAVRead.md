# MRxDAVRead

- ea: `0x14001cea0`
- end: `0x14001d014`
- name: `MRxDAVRead`
- size: `372`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400017e4`
- `0x14001cea0`
- `0x1400269d8`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ced2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001cf0e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001cf74`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001cfda`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ced2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001cf0e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001cf74`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001cfda`
- `rdbss!RxLowIoGetBufferAddress` at `0x14001cf39`
- `rdbss!RxLowIoGetBufferAddress` at `0x14001cf39`

## string_xrefs

- `0x14001cf99`: `MRxDAVRead`

## pseudocode

```c
__int64 __fastcall MRxDAVRead(PRX_CONTEXT RxContext)
{
  __int64 v2; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v4; // rbx
  HANDLE v5; // rax
  int v6; // edx
  int v7; // r8d
  unsigned int v8; // edi
  __int64 v9; // rbx
  HANDLE v10; // rax
  __int64 v11; // rbx
  HANDLE v12; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v2 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v2, 10, WPP_7ebb59d433c73ef4df0f91ab4e4668ee_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v4 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v5 = PsGetCurrentThreadId();
      WPP_SF_qq(v4, 11, WPP_7ebb59d433c73ef4df0f91ab4e4668ee_Traceguids, v5, RxContext);
    }
  }
  if ( RxLowIoGetBufferAddress(RxContext) || !*((_DWORD *)&RxContext->9 + 42) )
  {
    v8 = UMRxAsyncEngOuterWrapper((_DWORD)RxContext, v6, v7, 9, (__int64)MRxDAVReadContinuation, (__int64)"MRxDAVRead");
  }
  else
  {
    v8 = -1073741670;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v8;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v10 = PsGetCurrentThreadId();
      WPP_SF_q(v9, 12, WPP_7ebb59d433c73ef4df0f91ab4e4668ee_Traceguids, v10);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v11 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v12 = PsGetCurrentThreadId();
    WPP_SF_qD(v11, 13, WPP_7ebb59d433c73ef4df0f91ab4e4668ee_Traceguids, v12, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x14001cea0  mov     [rsp+arg_0], rbx
0x14001cea5  mov     [rsp+arg_8], rsi
0x14001ceaa  push    rdi
0x14001ceab  sub     rsp, 30h
0x14001ceaf  mov     rdi, rcx
0x14001ceb2  mov     rbx, cs:WPP_GLOBAL_Control
0x14001ceb9  lea     rsi, WPP_GLOBAL_Control
0x14001cec0  cmp     rbx, rsi
0x14001cec3  jz      short loc_14001CF36
0x14001cec5  test    dword ptr [rbx+2Ch], 4000h
0x14001cecc  jz      short loc_14001CEF5
0x14001cece  mov     rbx, [rbx+18h]
0x14001ced2  call    cs:__imp_PsGetCurrentThreadId
0x14001ced9  nop     dword ptr [rax+rax+00h]
0x14001cede  mov     edx, 0Ah
0x14001cee3  lea     r8, WPP_7ebb59d433c73ef4df0f91ab4e4668ee_Traceguids
0x14001ceea  mov     r9, rax
0x14001ceed  mov     rcx, rbx
0x14001cef0  call    WPP_SF_q
0x14001cef5  mov     rbx, cs:WPP_GLOBAL_Control
0x14001cefc  cmp     rbx, rsi
0x14001ceff  jz      short loc_14001CF36
0x14001cf01  test    dword ptr [rbx+2Ch], 2000h
0x14001cf08  jz      short loc_14001CF36
0x14001cf0a  mov     rbx, [rbx+18h]
0x14001cf0e  call    cs:__imp_PsGetCurrentThreadId
0x14001cf15  nop     dword ptr [rax+rax+00h]
0x14001cf1a  mov     edx, 0Bh
0x14001cf1f  mov     [rsp+38h+var_18], rdi
0x14001cf24  mov     r9, rax
0x14001cf27  lea     r8, WPP_7ebb59d433c73ef4df0f91ab4e4668ee_Traceguids
0x14001cf2e  mov     rcx, rbx
0x14001cf31  call    WPP_SF_qq
0x14001cf36  mov     rcx, rdi; RxContext
0x14001cf39  call    cs:__imp_RxLowIoGetBufferAddress
0x14001cf40  nop     dword ptr [rax+rax+00h]
0x14001cf45  test    rax, rax
0x14001cf48  jnz     short loc_14001CF99
0x14001cf4a  cmp     [rdi+238h], eax
0x14001cf50  jz      short loc_14001CF99
0x14001cf52  mov     edi, 0C000009Ah
0x14001cf57  mov     rbx, cs:WPP_GLOBAL_Control
0x14001cf5e  cmp     rbx, rsi
0x14001cf61  jz      loc_14001D001
0x14001cf67  test    dword ptr [rbx+2Ch], 2000h
0x14001cf6e  jz      short loc_14001CFC1
0x14001cf70  mov     rbx, [rbx+18h]
0x14001cf74  call    cs:__imp_PsGetCurrentThreadId
0x14001cf7b  nop     dword ptr [rax+rax+00h]
0x14001cf80  mov     edx, 0Ch
0x14001cf85  lea     r8, WPP_7ebb59d433c73ef4df0f91ab4e4668ee_Traceguids
0x14001cf8c  mov     r9, rax
0x14001cf8f  mov     rcx, rbx
0x14001cf92  call    WPP_SF_q
0x14001cf97  jmp     short loc_14001CFC1
0x14001cf99  lea     rax, aMrxdavread; "MRxDAVRead"
0x14001cfa0  mov     r9d, 9
0x14001cfa6  mov     [rsp+38h+var_10], rax
0x14001cfab  mov     rcx, rdi
0x14001cfae  lea     rax, MRxDAVReadContinuation
0x14001cfb5  mov     [rsp+38h+var_18], rax
0x14001cfba  call    UMRxAsyncEngOuterWrapper
0x14001cfbf  mov     edi, eax
0x14001cfc1  mov     rbx, cs:WPP_GLOBAL_Control
0x14001cfc8  cmp     rbx, rsi
0x14001cfcb  jz      short loc_14001D001
0x14001cfcd  test    dword ptr [rbx+2Ch], 4000h
0x14001cfd4  jz      short loc_14001D001
0x14001cfd6  mov     rbx, [rbx+18h]
0x14001cfda  call    cs:__imp_PsGetCurrentThreadId
0x14001cfe1  nop     dword ptr [rax+rax+00h]
0x14001cfe6  mov     edx, 0Dh
0x14001cfeb  mov     dword ptr [rsp+38h+var_18], edi
0x14001cfef  mov     r9, rax
0x14001cff2  lea     r8, WPP_7ebb59d433c73ef4df0f91ab4e4668ee_Traceguids
0x14001cff9  mov     rcx, rbx
0x14001cffc  call    WPP_SF_qD
0x14001d001  mov     rbx, [rsp+38h+arg_0]
0x14001d006  mov     eax, edi
0x14001d008  mov     rsi, [rsp+38h+arg_8]
0x14001d00d  add     rsp, 30h
0x14001d011  pop     rdi
0x14001d012  retn
```
