# SmbPseExchangeFinalize_default

- ea: `0x14000b410`
- end: `0x14000b51b`
- name: `SmbPseExchangeFinalize_default`
- size: `267`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14000b410`
- `0x14000dfa8`
- `0x1400104d4`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000b4fa`
- `ntoskrnl!KeSetEvent` at `0x14000b4fa`
- `rdbss!RxPostToWorkerThread` at `0x14000b4b4`
- `rdbss!RxPostToWorkerThread` at `0x14000b4b4`
- `mrxsmb!MRxSmbDeviceObject` at `0x14000b48b`

## pseudocode

```c
__int64 __fastcall SmbPseExchangeFinalize_default(unsigned int *pContext, _BYTE *a2)
{
  unsigned int v4; // eax
  __int64 result; // rax

  if ( *(_BYTE *)(*((_QWORD *)pContext + 10) + 640LL) && (unsigned __int8)SmbCeIsReconnectableError(pContext[12]) )
    pContext[12] = -1069481983;
  v4 = pContext[10];
  if ( v4 )
    pContext[12] = v4;
  if ( *((_QWORD *)pContext + 53) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids);
    *((_WORD *)pContext + 192) |= 0x400u;
    RxPostToWorkerThread(
      MRxSmbDeviceObject,
      DelayedWorkQueue,
      (PRX_WORK_QUEUE_ITEM)(pContext + 44),
      SmbPseContinueOrdinaryExchange,
      pContext);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xAu) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids);
    }
    KeSetEvent(*((PRKEVENT *)pContext + 15), 0, 0);
  }
  result = 0;
  *a2 = 0;
  return result;
}

```

## disassembly

```asm
0x14000b410  mov     [rsp+arg_8], rbx
0x14000b415  push    rdi
0x14000b416  sub     rsp, 30h
0x14000b41a  mov     rax, [rcx+50h]
0x14000b41e  mov     rdi, rdx
0x14000b421  mov     rbx, rcx
0x14000b424  cmp     byte ptr [rax+280h], 0
0x14000b42b  jz      short loc_14000B440
0x14000b42d  mov     ecx, [rcx+30h]
0x14000b430  call    SmbCeIsReconnectableError
0x14000b435  test    al, al
0x14000b437  jz      short loc_14000B440
0x14000b439  mov     dword ptr [rbx+30h], 0C0410001h
0x14000b440  mov     eax, [rbx+28h]
0x14000b443  test    eax, eax
0x14000b445  jz      short loc_14000B44A
0x14000b447  mov     [rbx+30h], eax
0x14000b44a  cmp     qword ptr [rbx+1A8h], 0
0x14000b452  mov     [rsp+38h+arg_0], rsi
0x14000b457  jz      short loc_14000B4C2
0x14000b459  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000b460  lea     rax, WPP_GLOBAL_Control
0x14000b467  mov     esi, 400h
0x14000b46c  cmp     rcx, rax
0x14000b46f  jz      short loc_14000B48B
0x14000b471  test    [rcx+2Ch], esi
0x14000b474  jz      short loc_14000B48B
0x14000b476  mov     rcx, [rcx+18h]
0x14000b47a  lea     r8, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids
0x14000b481  mov     edx, 22h ; '"'
0x14000b486  call    WPP_SF_
0x14000b48b  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x14000b492  lea     r8, [rbx+0B0h]; pWorkQueueItem
0x14000b499  or      [rbx+180h], si
0x14000b4a0  lea     r9, SmbPseContinueOrdinaryExchange; Routine
0x14000b4a7  mov     edx, 1; WorkQueueType
0x14000b4ac  mov     [rsp+38h+pContext], rbx; pContext
0x14000b4b1  mov     rcx, [rcx]; pMRxDeviceObject
0x14000b4b4  call    cs:__imp_RxPostToWorkerThread
0x14000b4bb  nop     dword ptr [rax+rax+00h]
0x14000b4c0  jmp     short loc_14000B506
0x14000b4c2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000b4c9  lea     rax, WPP_GLOBAL_Control
0x14000b4d0  cmp     rcx, rax
0x14000b4d3  jz      short loc_14000B4F1
0x14000b4d5  bt      dword ptr [rcx+2Ch], 0Ah
0x14000b4da  jnb     short loc_14000B4F1
0x14000b4dc  mov     rcx, [rcx+18h]
0x14000b4e0  lea     r8, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids
0x14000b4e7  mov     edx, 23h ; '#'
0x14000b4ec  call    WPP_SF_
0x14000b4f1  mov     rcx, [rbx+78h]; Event
0x14000b4f5  xor     r8d, r8d; Wait
0x14000b4f8  xor     edx, edx; Increment
0x14000b4fa  call    cs:__imp_KeSetEvent
0x14000b501  nop     dword ptr [rax+rax+00h]
0x14000b506  mov     rsi, [rsp+38h+arg_0]
0x14000b50b  xor     eax, eax
0x14000b50d  mov     rbx, [rsp+38h+arg_8]
0x14000b512  mov     [rdi], al
0x14000b514  add     rsp, 30h
0x14000b518  pop     rdi
0x14000b519  retn
```
