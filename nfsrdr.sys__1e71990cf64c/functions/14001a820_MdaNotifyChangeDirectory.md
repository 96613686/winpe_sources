# MdaNotifyChangeDirectory

- ea: `0x14001a820`
- end: `0x14001a947`
- name: `MdaNotifyChangeDirectory`
- size: `295`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140008140`
- `0x1400159cc`
- `0x140015a40`
- `0x14001a820`
- `0x14002fa64`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14001a902`
- `ntoskrnl!KeReleaseMutex` at `0x14001a902`

## pseudocode

```c
__int64 __fastcall MdaNotifyChangeDirectory(PRX_CONTEXT RxContext)
{
  PMRX_FCB pFcb; // rdi
  PMRX_FOBX pFobx; // rbp
  ULONGLONG ActualAllocationLength; // rdi
  __int64 v5; // rbx
  const UNICODE_STRING *v6; // r9
  int v8; // [rsp+28h] [rbp-40h]

  pFcb = RxContext->pFcb;
  pFobx = RxContext->pFobx;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_Z(
        WPP_GLOBAL_Control->AttachedDevice,
        40,
        WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids,
        &RxContext->pFcb[2].Header.Resource);
  }
  ActualAllocationLength = pFcb->ActualAllocationLength;
  v5 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)pFobx->Context2 + 5) + 32LL) + 40LL);
  HacAcquireLock(*(_QWORD *)(ActualAllocationLength + 8));
  v6 = &Slash;
  if ( *(_WORD *)(*(_QWORD *)(ActualAllocationLength + 8) + 64LL) )
    v6 = (const UNICODE_STRING *)(*(_QWORD *)(ActualAllocationLength + 8) + 64LL);
  MdaNotifyFullChangeDirectory(
    *(PFAST_MUTEX *)(v5 + 104),
    (_QWORD *)(v5 + 88),
    (__int64)pFobx,
    v6,
    *((_BYTE *)&RxContext->9 + 136),
    v8,
    *((_DWORD *)&RxContext->9 + 35),
    RxContext);
  KeReleaseMutex(*(PRKMUTEX *)(*(_QWORD *)(ActualAllocationLength + 8) + 40LL), 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids);
  return 259;
}

```

## disassembly

```asm
0x14001a820  push    rbx
0x14001a822  push    rbp
0x14001a823  push    rsi
0x14001a824  push    rdi
0x14001a825  push    r15
0x14001a827  sub     rsp, 40h
0x14001a82b  mov     rdi, [rcx+38h]
0x14001a82f  mov     rsi, rcx
0x14001a832  mov     rbp, [rcx+40h]
0x14001a836  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a83d  lea     r15, WPP_GLOBAL_Control
0x14001a844  cmp     rcx, r15
0x14001a847  jz      short loc_14001A898
0x14001a849  mov     eax, [rcx+2Ch]
0x14001a84c  test    al, 8
0x14001a84e  jz      short loc_14001A865
0x14001a850  mov     rcx, [rcx+18h]
0x14001a854  lea     r8, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids
0x14001a85b  mov     edx, 27h ; '''
0x14001a860  call    WPP_SF_
0x14001a865  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a86c  cmp     rcx, r15
0x14001a86f  jz      short loc_14001A898
0x14001a871  mov     eax, [rcx+2Ch]
0x14001a874  test    al, 4
0x14001a876  jz      short loc_14001A898
0x14001a878  mov     r9, [rsi+38h]
0x14001a87c  lea     r8, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids
0x14001a883  mov     rcx, [rcx+18h]
0x14001a887  add     r9, 168h
0x14001a88e  mov     edx, 28h ; '('
0x14001a893  call    WPP_SF_Z
0x14001a898  mov     rax, [rbp+20h]
0x14001a89c  mov     rdi, [rdi+88h]
0x14001a8a3  mov     rcx, [rax+28h]
0x14001a8a7  mov     rax, [rcx+20h]
0x14001a8ab  mov     rcx, [rdi+8]
0x14001a8af  mov     rbx, [rax+28h]
0x14001a8b3  call    HacAcquireLock
0x14001a8b8  mov     rax, [rdi+8]
0x14001a8bc  lea     r9, Slash
0x14001a8c3  mov     rcx, [rbx+68h]; FastMutex
0x14001a8c7  lea     rdx, [rbx+58h]
0x14001a8cb  add     rax, 40h ; '@'
0x14001a8cf  mov     [rsp+68h+RxContext], rsi; RxContext
0x14001a8d4  mov     r8, rbp
0x14001a8d7  cmp     word ptr [rax], 0
0x14001a8db  cmovnz  r9, rax
0x14001a8df  mov     eax, [rsi+21Ch]
0x14001a8e5  mov     [rsp+68h+var_38], eax; int
0x14001a8e9  mov     al, [rsi+218h]
0x14001a8ef  mov     [rsp+68h+var_48], al; char
0x14001a8f3  call    MdaNotifyFullChangeDirectory
0x14001a8f8  mov     rcx, [rdi+8]
0x14001a8fc  xor     edx, edx; Wait
0x14001a8fe  mov     rcx, [rcx+28h]; Mutex
0x14001a902  call    cs:__imp_KeReleaseMutex
0x14001a909  nop     dword ptr [rax+rax+00h]
0x14001a90e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a915  cmp     rcx, r15
0x14001a918  jz      short loc_14001A936
0x14001a91a  mov     eax, [rcx+2Ch]
0x14001a91d  test    al, 8
0x14001a91f  jz      short loc_14001A936
0x14001a921  mov     rcx, [rcx+18h]
0x14001a925  lea     r8, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids
0x14001a92c  mov     edx, 29h ; ')'
0x14001a931  call    WPP_SF_
0x14001a936  mov     eax, 103h
0x14001a93b  add     rsp, 40h
0x14001a93f  pop     r15
0x14001a941  pop     rdi
0x14001a942  pop     rsi
0x14001a943  pop     rbp
0x14001a944  pop     rbx
0x14001a945  retn
```
