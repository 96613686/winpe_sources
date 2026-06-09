# FltpDataScanConflictResumeCompletion

- ea: `0x1800785a0`
- end: `0x180078684`
- name: `FltpDataScanConflictResumeCompletion`
- size: `228`
- prototype: `__int64 __fastcall(_QWORD *IoObject, IRP *Context, __int64)`
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
- `0x1800247a0`
- `0x1800785a0`

## import_xrefs

- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1800785e2`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1800785e2`
- `ntoskrnl!IoClearActivityIdThread` at `0x18007865d`
- `ntoskrnl!IoClearActivityIdThread` at `0x18007865d`

## pseudocode

```c
__int64 __fastcall FltpDataScanConflictResumeCompletion(_QWORD *IoObject, IRP *Context, __int64 a3)
{
  int v6; // eax
  __int64 v7; // r9
  int v8; // edi
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
  else if ( (unsigned int)FltpNoFilterCallbackCompletionWorker(IoObject, Context, 0, 1u) == -1073741802 )
  {
    goto LABEL_7;
  }
  FltpCompleteRequest(Context, Context->IoStatus.Status);
LABEL_7:
  result = FltpDbgStatus(v8);
  if ( (int)result >= 0 )
    return IoClearActivityIdThread(v11);
  return result;
}

```

## disassembly

```asm
0x1800785a0  mov     [rsp+arg_18], rbx
0x1800785a5  push    rbp
0x1800785a6  push    rsi
0x1800785a7  push    rdi
0x1800785a8  sub     rsp, 40h
0x1800785ac  mov     rax, cs:__security_cookie
0x1800785b3  xor     rax, rsp
0x1800785b6  mov     [rsp+58h+var_20], rax
0x1800785bb  mov     rbx, rdx
0x1800785be  mov     [rsp+58h+var_38], 0
0x1800785c7  mov     rbp, r8
0x1800785ca  lea     rdx, [rsp+58h+var_30]
0x1800785cf  mov     rsi, rcx
0x1800785d2  lea     r8, [rsp+58h+var_38]
0x1800785d7  xorps   xmm0, xmm0
0x1800785da  mov     rcx, rbx
0x1800785dd  movups  [rsp+58h+var_30], xmm0
0x1800785e2  call    cs:__imp_IoPropagateActivityIdToThread
0x1800785e9  nop     dword ptr [rax+rax+00h]
0x1800785ee  mov     r9b, 1
0x1800785f1  mov     edi, eax
0x1800785f3  test    rbp, rbp
0x1800785f6  jz      short loc_18007861D
0x1800785f8  mov     rdx, [rbp+30h]
0x1800785fc  mov     r8, rbp
0x1800785ff  mov     rcx, [rbp+68h]
0x180078603  mov     esi, [rbp+0E8h]
0x180078609  call    FltpPassThroughCompletionWorker
0x18007860e  cmp     eax, 0C0000016h
0x180078613  jz      short loc_18007863D
0x180078615  bt      esi, 10h
0x180078619  jnb     short loc_180078632
0x18007861b  jmp     short loc_18007863D
0x18007861d  xor     r8d, r8d; IoWorkItem
0x180078620  mov     rdx, rbx; Context
0x180078623  mov     rcx, rsi; IoObject
0x180078626  call    FltpNoFilterCallbackCompletionWorker
0x18007862b  cmp     eax, 0C0000016h
0x180078630  jz      short loc_18007863D
0x180078632  mov     edx, [rbx+30h]
0x180078635  mov     rcx, rbx
0x180078638  call    FltpCompleteRequest
0x18007863d  mov     r8d, 0BCDh
0x180078643  lea     rdx, aMinkernelFsFil_11; "minkernel\\fs\\filtermgr\\filter\\secti"...
0x18007864a  xor     r9d, r9d
0x18007864d  mov     ecx, edi
0x18007864f  call    FltpDbgStatus
0x180078654  test    eax, eax
0x180078656  js      short loc_180078669
0x180078658  mov     rcx, [rsp+58h+var_38]
0x18007865d  call    cs:__imp_IoClearActivityIdThread
0x180078664  nop     dword ptr [rax+rax+00h]
0x180078669  mov     rcx, [rsp+58h+var_20]
0x18007866e  xor     rcx, rsp; StackCookie
0x180078671  call    __security_check_cookie
0x180078676  mov     rbx, [rsp+58h+arg_18]
0x18007867b  add     rsp, 40h
0x18007867f  pop     rdi
0x180078680  pop     rsi
0x180078681  pop     rbp
0x180078682  retn
```
