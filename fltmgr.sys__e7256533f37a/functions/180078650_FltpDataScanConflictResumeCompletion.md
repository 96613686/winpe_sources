# FltpDataScanConflictResumeCompletion

- ea: `0x180078650`
- end: `0x180078734`
- name: `FltpDataScanConflictResumeCompletion`
- size: `228`
- prototype: `__int64 __fastcall(PVOID IoObject, PVOID Context)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180001ad0`
- `0x1800546e0`
- `0x180054760`

## callees

- `0x180005b80`
- `0x180009f20`
- `0x180016f40`
- `0x18001e8b0`
- `0x180024800`
- `0x180078650`

## import_xrefs

- `ntoskrnl!IoPropagateActivityIdToThread` at `0x180078692`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x180078692`
- `ntoskrnl!IoClearActivityIdThread` at `0x18007870d`
- `ntoskrnl!IoClearActivityIdThread` at `0x18007870d`

## pseudocode

```c
__int64 __fastcall FltpDataScanConflictResumeCompletion(PVOID IoObject, unsigned int *Context, __int64 a3)
{
  unsigned int v6; // eax
  __int64 v7; // r9
  unsigned int v8; // edi
  int v9; // esi
  __int64 result; // rax
  __int64 v11; // [rsp+20h] [rbp-38h] BYREF
  __int128 v12; // [rsp+28h] [rbp-30h] BYREF

  v11 = 0;
  v12 = 0;
  v6 = IoPropagateActivityIdToThread(Context, &v12, &v11);
  LOBYTE(v7) = 1;
  v8 = v6;
  if ( a3 )
  {
    v9 = *(_DWORD *)(a3 + 232);
    if ( (unsigned int)FltpPassThroughCompletionWorker(*(_QWORD *)(a3 + 104), *(_QWORD *)(a3 + 48), a3, v7) == -1073741802
      || (v9 & 0x10000) != 0 )
    {
      goto LABEL_7;
    }
  }
  else if ( (unsigned int)FltpNoFilterCallbackCompletionWorker(IoObject, Context, 0) == -1073741802 )
  {
    goto LABEL_7;
  }
  FltpCompleteRequest(Context, Context[12]);
LABEL_7:
  result = FltpDbgStatus(v8, "minkernel\\fs\\filtermgr\\filter\\sectionsup.c", 3021, 0);
  if ( (int)result >= 0 )
    return IoClearActivityIdThread(v11);
  return result;
}

```

## disassembly

```asm
0x180078650  mov     [rsp+arg_18], rbx
0x180078655  push    rbp
0x180078656  push    rsi
0x180078657  push    rdi
0x180078658  sub     rsp, 40h
0x18007865c  mov     rax, cs:__security_cookie
0x180078663  xor     rax, rsp
0x180078666  mov     [rsp+58h+var_20], rax
0x18007866b  mov     rbx, rdx
0x18007866e  mov     [rsp+58h+var_38], 0
0x180078677  mov     rbp, r8
0x18007867a  lea     rdx, [rsp+58h+var_30]
0x18007867f  mov     rsi, rcx
0x180078682  lea     r8, [rsp+58h+var_38]
0x180078687  xorps   xmm0, xmm0
0x18007868a  mov     rcx, rbx
0x18007868d  movups  [rsp+58h+var_30], xmm0
0x180078692  call    cs:__imp_IoPropagateActivityIdToThread
0x180078699  nop     dword ptr [rax+rax+00h]
0x18007869e  mov     r9b, 1
0x1800786a1  mov     edi, eax
0x1800786a3  test    rbp, rbp
0x1800786a6  jz      short loc_1800786CD
0x1800786a8  mov     rdx, [rbp+30h]
0x1800786ac  mov     r8, rbp
0x1800786af  mov     rcx, [rbp+68h]
0x1800786b3  mov     esi, [rbp+0E8h]
0x1800786b9  call    FltpPassThroughCompletionWorker
0x1800786be  cmp     eax, 0C0000016h
0x1800786c3  jz      short loc_1800786ED
0x1800786c5  bt      esi, 10h
0x1800786c9  jnb     short loc_1800786E2
0x1800786cb  jmp     short loc_1800786ED
0x1800786cd  xor     r8d, r8d; IoWorkItem
0x1800786d0  mov     rdx, rbx; Context
0x1800786d3  mov     rcx, rsi; IoObject
0x1800786d6  call    FltpNoFilterCallbackCompletionWorker
0x1800786db  cmp     eax, 0C0000016h
0x1800786e0  jz      short loc_1800786ED
0x1800786e2  mov     edx, [rbx+30h]
0x1800786e5  mov     rcx, rbx
0x1800786e8  call    FltpCompleteRequest
0x1800786ed  mov     r8d, 0BCDh
0x1800786f3  lea     rdx, aMinkernelFsFil_11; "minkernel\\fs\\filtermgr\\filter\\secti"...
0x1800786fa  xor     r9d, r9d
0x1800786fd  mov     ecx, edi
0x1800786ff  call    FltpDbgStatus
0x180078704  test    eax, eax
0x180078706  js      short loc_180078719
0x180078708  mov     rcx, [rsp+58h+var_38]
0x18007870d  call    cs:__imp_IoClearActivityIdThread
0x180078714  nop     dword ptr [rax+rax+00h]
0x180078719  mov     rcx, [rsp+58h+var_20]
0x18007871e  xor     rcx, rsp; StackCookie
0x180078721  call    __security_check_cookie
0x180078726  mov     rbx, [rsp+58h+arg_18]
0x18007872b  add     rsp, 40h
0x18007872f  pop     rdi
0x180078730  pop     rsi
0x180078731  pop     rbp
0x180078732  retn
```
