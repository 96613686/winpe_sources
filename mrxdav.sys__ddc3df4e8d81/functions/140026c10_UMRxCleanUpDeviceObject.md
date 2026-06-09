# UMRxCleanUpDeviceObject

- ea: `0x140026c10`
- end: `0x140026df3`
- name: `UMRxCleanUpDeviceObject`
- size: `483`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140018350`

## callees

- `0x14000163c`
- `0x1400017e4`
- `0x140026c10`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140026c47`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026c83`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026d1f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026d80`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026dbc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026c47`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026c83`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026d1f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026d80`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026dbc`
- `ntoskrnl!ExDeleteResourceLite` at `0x140026cb2`
- `ntoskrnl!ExDeleteResourceLite` at `0x140026d58`
- `ntoskrnl!ExDeleteResourceLite` at `0x140026cb2`
- `ntoskrnl!ExDeleteResourceLite` at `0x140026d58`
- `ntoskrnl!KeRundownQueue` at `0x140026cdf`
- `ntoskrnl!KeRundownQueue` at `0x140026cdf`
- `rdbss!RxDestroyMidAtlas` at `0x140026ccc`
- `rdbss!RxDestroyMidAtlas` at `0x140026ccc`

## pseudocode

```c
__int64 __fastcall UMRxCleanUpDeviceObject(__int64 a1)
{
  char v2; // r15
  __int64 v3; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v5; // rbx
  HANDLE v6; // rax
  struct _RX_MID_ATLAS *v7; // rcx
  PLIST_ENTRY v8; // rax
  PLIST_ENTRY v9; // rbp
  _QWORD *p_Flink; // rsi
  _QWORD *v11; // r14
  __int64 v12; // rbx
  HANDLE v13; // rax
  __int64 v14; // rbx
  HANDLE v15; // rax
  __int64 v16; // rbx
  HANDLE v17; // rax

  v2 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
    {
      v3 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v3, 119, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) != 0 )
    {
      v5 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v6 = PsGetCurrentThreadId();
      WPP_SF_qq(v5, 120, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v6, a1);
    }
  }
  ExDeleteResourceLite(&UMRxAsyncEngineContextListLock);
  v7 = *(struct _RX_MID_ATLAS **)(a1 + 1312);
  if ( v7 )
    RxDestroyMidAtlas(v7, 0);
  v8 = KeRundownQueue((PRKQUEUE)(a1 + 1392));
  v9 = v8;
  if ( v8 )
  {
    p_Flink = &v8->Flink;
    do
    {
      v11 = p_Flink;
      p_Flink = (_QWORD *)*p_Flink;
      if ( v11 == (_QWORD *)(a1 + 1568) )
      {
        v2 = 1;
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
             && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0 )
      {
        v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v13 = PsGetCurrentThreadId();
        WPP_SF_qq(v12, 121, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v13, v11);
      }
    }
    while ( p_Flink != (_QWORD *)v9 );
  }
  ExDeleteResourceLite((PERESOURCE)(a1 + 1456));
  if ( !v2 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return 0;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0 )
    {
      v14 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v15 = PsGetCurrentThreadId();
      WPP_SF_q(v14, 122, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v15);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
  {
    v16 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v17 = PsGetCurrentThreadId();
    WPP_SF_q(v16, 123, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v17);
  }
  return 0;
}

```

## disassembly

```asm
0x140026c10  push    rbx
0x140026c12  push    rbp
0x140026c13  push    rsi
0x140026c14  push    rdi
0x140026c15  push    r12
0x140026c17  push    r13
0x140026c19  push    r14
0x140026c1b  push    r15
0x140026c1d  sub     rsp, 38h
0x140026c21  mov     rdi, rcx
0x140026c24  xor     r15b, r15b
0x140026c27  mov     rbx, cs:WPP_GLOBAL_Control
0x140026c2e  lea     r13, WPP_GLOBAL_Control
0x140026c35  cmp     rbx, r13
0x140026c38  jz      short loc_140026CAB
0x140026c3a  test    dword ptr [rbx+2Ch], 800h
0x140026c41  jz      short loc_140026C6A
0x140026c43  mov     rbx, [rbx+18h]
0x140026c47  call    cs:__imp_PsGetCurrentThreadId
0x140026c4e  nop     dword ptr [rax+rax+00h]
0x140026c53  mov     edx, 77h ; 'w'
0x140026c58  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140026c5f  mov     r9, rax
0x140026c62  mov     rcx, rbx
0x140026c65  call    WPP_SF_q
0x140026c6a  mov     rbx, cs:WPP_GLOBAL_Control
0x140026c71  cmp     rbx, r13
0x140026c74  jz      short loc_140026CAB
0x140026c76  test    dword ptr [rbx+2Ch], 200h
0x140026c7d  jz      short loc_140026CAB
0x140026c7f  mov     rbx, [rbx+18h]
0x140026c83  call    cs:__imp_PsGetCurrentThreadId
0x140026c8a  nop     dword ptr [rax+rax+00h]
0x140026c8f  mov     edx, 78h ; 'x'
0x140026c94  mov     [rsp+78h+var_58], rdi
0x140026c99  mov     r9, rax
0x140026c9c  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140026ca3  mov     rcx, rbx
0x140026ca6  call    WPP_SF_qq
0x140026cab  lea     rcx, UMRxAsyncEngineContextListLock; Resource
0x140026cb2  call    cs:__imp_ExDeleteResourceLite
0x140026cb9  nop     dword ptr [rax+rax+00h]
0x140026cbe  mov     rcx, [rdi+520h]; MidAtlas
0x140026cc5  test    rcx, rcx
0x140026cc8  jz      short loc_140026CD8
0x140026cca  xor     edx, edx; ContextDestructor
0x140026ccc  call    cs:__imp_RxDestroyMidAtlas
0x140026cd3  nop     dword ptr [rax+rax+00h]
0x140026cd8  lea     rcx, [rdi+570h]; Queue
0x140026cdf  call    cs:__imp_KeRundownQueue
0x140026ce6  nop     dword ptr [rax+rax+00h]
0x140026ceb  mov     rbp, rax
0x140026cee  test    rax, rax
0x140026cf1  jz      short loc_140026D51
0x140026cf3  mov     rsi, rax
0x140026cf6  lea     r12, [rdi+620h]
0x140026cfd  mov     r14, rsi
0x140026d00  mov     rsi, [rsi]
0x140026d03  cmp     r14, r12
0x140026d06  jz      short loc_140026D49
0x140026d08  mov     rbx, cs:WPP_GLOBAL_Control
0x140026d0f  cmp     rbx, r13
0x140026d12  jz      short loc_140026D4C
0x140026d14  mov     eax, [rbx+2Ch]
0x140026d17  test    al, al
0x140026d19  jns     short loc_140026D4C
0x140026d1b  mov     rbx, [rbx+18h]
0x140026d1f  call    cs:__imp_PsGetCurrentThreadId
0x140026d26  nop     dword ptr [rax+rax+00h]
0x140026d2b  mov     edx, 79h ; 'y'
0x140026d30  mov     [rsp+78h+var_58], r14
0x140026d35  mov     r9, rax
0x140026d38  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140026d3f  mov     rcx, rbx
0x140026d42  call    WPP_SF_qq
0x140026d47  jmp     short loc_140026D4C
0x140026d49  mov     r15b, 1
0x140026d4c  cmp     rsi, rbp
0x140026d4f  jnz     short loc_140026CFD
0x140026d51  lea     rcx, [rdi+5B0h]; Resource
0x140026d58  call    cs:__imp_ExDeleteResourceLite
0x140026d5f  nop     dword ptr [rax+rax+00h]
0x140026d64  test    r15b, r15b
0x140026d67  jnz     short loc_140026DA3
0x140026d69  mov     rbx, cs:WPP_GLOBAL_Control
0x140026d70  cmp     rbx, r13
0x140026d73  jz      short loc_140026DDF
0x140026d75  mov     eax, [rbx+2Ch]
0x140026d78  test    al, al
0x140026d7a  jns     short loc_140026DA3
0x140026d7c  mov     rbx, [rbx+18h]
0x140026d80  call    cs:__imp_PsGetCurrentThreadId
0x140026d87  nop     dword ptr [rax+rax+00h]
0x140026d8c  mov     edx, 7Ah ; 'z'
0x140026d91  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140026d98  mov     r9, rax
0x140026d9b  mov     rcx, rbx
0x140026d9e  call    WPP_SF_q
0x140026da3  mov     rbx, cs:WPP_GLOBAL_Control
0x140026daa  cmp     rbx, r13
0x140026dad  jz      short loc_140026DDF
0x140026daf  test    dword ptr [rbx+2Ch], 800h
0x140026db6  jz      short loc_140026DDF
0x140026db8  mov     rbx, [rbx+18h]
0x140026dbc  call    cs:__imp_PsGetCurrentThreadId
0x140026dc3  nop     dword ptr [rax+rax+00h]
0x140026dc8  mov     edx, 7Bh ; '{'
0x140026dcd  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140026dd4  mov     r9, rax
0x140026dd7  mov     rcx, rbx
0x140026dda  call    WPP_SF_q
0x140026ddf  xor     eax, eax
0x140026de1  add     rsp, 38h
0x140026de5  pop     r15
0x140026de7  pop     r14
0x140026de9  pop     r13
0x140026deb  pop     r12
0x140026ded  pop     rdi
0x140026dee  pop     rsi
0x140026def  pop     rbp
0x140026df0  pop     rbx
0x140026df1  retn
```
