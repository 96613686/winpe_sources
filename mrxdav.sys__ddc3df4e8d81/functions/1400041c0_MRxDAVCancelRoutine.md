# MRxDAVCancelRoutine

- ea: `0x1400041c0`
- end: `0x140004349`
- name: `MRxDAVCancelRoutine`
- size: `393`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140001680`
- `0x1400017e4`
- `0x1400041c0`
- `0x140004350`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x1400041ec`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000426f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400042bf`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000430b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400041ec`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000426f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400042bf`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000430b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000421d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000421d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000429c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000429c`

## pseudocode

```c
__int64 __fastcall MRxDAVCancelRoutine(PRX_CONTEXT RxContext)
{
  __int64 v2; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 *v4; // rcx
  __int64 v5; // rdi
  unsigned int v6; // edi
  __int64 v7; // rbx
  HANDLE v8; // rax
  __int64 v9; // rbx
  HANDLE v10; // rax
  __int64 v12; // rbx
  HANDLE v13; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xEu) )
  {
    v2 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    CurrentThreadId = PsGetCurrentThreadId();
    WPP_SF_qq(v2, 10, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids, CurrentThreadId, RxContext);
  }
  ExAcquireResourceExclusiveLite(&UMRxAsyncEngineContextListLock, 1u);
  v4 = (__int64 *)UMRxAsyncEngineContextList;
  do
  {
    if ( v4 == &UMRxAsyncEngineContextList )
    {
      v6 = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xEu) )
      {
        v7 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v8 = PsGetCurrentThreadId();
        WPP_SF_qq(v7, 12, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids, v8, RxContext);
      }
      goto LABEL_11;
    }
    v5 = (__int64)(v4 - 4);
    v4 = (__int64 *)*v4;
  }
  while ( *(PRX_CONTEXT *)(v5 + 80) != RxContext || !*(_DWORD *)(v5 + 64) );
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xEu) )
  {
    v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v13 = PsGetCurrentThreadId();
    WPP_SF_qq(v12, 11, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids, v13, RxContext);
  }
  v6 = MRxDAVCancelTheContext(v5, 1u, 0);
LABEL_11:
  ExReleaseResourceLite(&UMRxAsyncEngineContextListLock);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xEu) )
  {
    v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v10 = PsGetCurrentThreadId();
    WPP_SF_qD(v9, 13, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids, v10, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x1400041c0  push    rbx
0x1400041c2  push    rbp
0x1400041c3  push    rsi
0x1400041c4  push    rdi
0x1400041c5  push    r14
0x1400041c7  sub     rsp, 30h
0x1400041cb  mov     rsi, rcx
0x1400041ce  mov     rbx, cs:WPP_GLOBAL_Control
0x1400041d5  lea     r14, WPP_GLOBAL_Control
0x1400041dc  cmp     rbx, r14
0x1400041df  jz      short loc_140004214
0x1400041e1  bt      dword ptr [rbx+2Ch], 0Eh
0x1400041e6  jnb     short loc_140004214
0x1400041e8  mov     rbx, [rbx+18h]
0x1400041ec  call    cs:__imp_PsGetCurrentThreadId
0x1400041f3  nop     dword ptr [rax+rax+00h]
0x1400041f8  mov     edx, 0Ah
0x1400041fd  mov     [rsp+58h+var_38], rsi
0x140004202  mov     r9, rax
0x140004205  lea     r8, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids
0x14000420c  mov     rcx, rbx
0x14000420f  call    WPP_SF_qq
0x140004214  mov     dl, 1; Wait
0x140004216  lea     rcx, UMRxAsyncEngineContextListLock; Resource
0x14000421d  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140004224  nop     dword ptr [rax+rax+00h]
0x140004229  mov     rcx, cs:UMRxAsyncEngineContextList
0x140004230  lea     rdx, UMRxAsyncEngineContextList
0x140004237  jmp     short loc_140004251
0x140004239  lea     rdi, [rcx-20h]
0x14000423d  mov     rcx, [rcx]
0x140004240  cmp     [rdi+50h], rsi
0x140004244  jnz     short loc_140004251
0x140004246  mov     eax, [rdi+40h]
0x140004249  test    eax, eax
0x14000424b  jnz     loc_1400042F4
0x140004251  cmp     rcx, rdx
0x140004254  jnz     short loc_140004239
0x140004256  xor     edi, edi
0x140004258  mov     rbx, cs:WPP_GLOBAL_Control
0x14000425f  cmp     rbx, r14
0x140004262  jz      short loc_140004295
0x140004264  bt      dword ptr [rbx+2Ch], 0Eh
0x140004269  jnb     short loc_140004295
0x14000426b  mov     rbx, [rbx+18h]
0x14000426f  call    cs:__imp_PsGetCurrentThreadId
0x140004276  nop     dword ptr [rax+rax+00h]
0x14000427b  lea     edx, [rdi+0Ch]
0x14000427e  mov     [rsp+58h+var_38], rsi
0x140004283  mov     r9, rax
0x140004286  lea     r8, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids
0x14000428d  mov     rcx, rbx
0x140004290  call    WPP_SF_qq
0x140004295  lea     rcx, UMRxAsyncEngineContextListLock; Resource
0x14000429c  call    cs:__imp_ExReleaseResourceLite
0x1400042a3  nop     dword ptr [rax+rax+00h]
0x1400042a8  mov     rbx, cs:WPP_GLOBAL_Control
0x1400042af  cmp     rbx, r14
0x1400042b2  jz      short loc_1400042E6
0x1400042b4  bt      dword ptr [rbx+2Ch], 0Eh
0x1400042b9  jnb     short loc_1400042E6
0x1400042bb  mov     rbx, [rbx+18h]
0x1400042bf  call    cs:__imp_PsGetCurrentThreadId
0x1400042c6  nop     dword ptr [rax+rax+00h]
0x1400042cb  mov     edx, 0Dh
0x1400042d0  mov     dword ptr [rsp+58h+var_38], edi
0x1400042d4  mov     r9, rax
0x1400042d7  lea     r8, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids
0x1400042de  mov     rcx, rbx
0x1400042e1  call    WPP_SF_qD
0x1400042e6  mov     eax, edi
0x1400042e8  add     rsp, 30h
0x1400042ec  pop     r14
0x1400042ee  pop     rdi
0x1400042ef  pop     rsi
0x1400042f0  pop     rbp
0x1400042f1  pop     rbx
0x1400042f2  retn
0x1400042f4  mov     rbx, cs:WPP_GLOBAL_Control
0x1400042fb  cmp     rbx, r14
0x1400042fe  jz      short loc_140004333
0x140004300  bt      dword ptr [rbx+2Ch], 0Eh
0x140004305  jnb     short loc_140004333
0x140004307  mov     rbx, [rbx+18h]
0x14000430b  call    cs:__imp_PsGetCurrentThreadId
0x140004312  nop     dword ptr [rax+rax+00h]
0x140004317  mov     edx, 0Bh
0x14000431c  mov     [rsp+58h+var_38], rsi
0x140004321  mov     r9, rax
0x140004324  lea     r8, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids
0x14000432b  mov     rcx, rbx
0x14000432e  call    WPP_SF_qq
0x140004333  xor     r8d, r8d
0x140004336  mov     rcx, rdi
0x140004339  lea     edx, [r8+1]
0x14000433d  call    MRxDAVCancelTheContext
0x140004342  mov     edi, eax
0x140004344  jmp     loc_140004295
```
