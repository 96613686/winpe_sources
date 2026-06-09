# SendPayloadUnseqComplete

- ea: `0x140019810`
- end: `0x140019932`
- name: `SendPayloadUnseqComplete`
- size: `290`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001c6d0`

## callees

- `0x1400012e0`
- `0x140003050`
- `0x140019810`
- `0x14001b830`

## import_xrefs

- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14001985d`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14001985d`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x140019894`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x140019894`

## pseudocode

```c
__int64 __fastcall SendPayloadUnseqComplete(__int64 a1, __int64 a2)
{
  __int64 v3; // rdi
  __int64 v4; // rsi
  __int64 v5; // rbp
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids);
  }
  v3 = *(_QWORD *)(a2 + 144);
  v4 = *(_QWORD *)(a2 + 128);
  v5 = *(_QWORD *)(v3 + 24);
  NdisAdvanceNetBufferDataStart((PNET_BUFFER)a2, *(_DWORD *)(a2 + 136), 1u, 0);
  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 112), 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
  {
    if ( _InterlockedIncrement((volatile signed __int32 *)(v3 + 480)) <= 5
      || (result = ScheduleWork(v5, &SendCompleteDeferred, a2), (_DWORD)result) )
    {
      NdisMCoSendNetBufferListsComplete(*(NDIS_HANDLE *)(v3 + 304), (PNET_BUFFER_LIST)v4, 0);
      _InterlockedDecrement((volatile signed __int32 *)(v3 + 480));
      result = DereferenceCall(v3);
    }
    else
    {
      _InterlockedDecrement((volatile signed __int32 *)(v3 + 480));
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x140019810  push    rbx
0x140019812  push    rbp
0x140019813  push    rsi
0x140019814  push    rdi
0x140019815  push    r14
0x140019817  sub     rsp, 20h
0x14001981b  mov     rbx, rdx
0x14001981e  mov     rcx, cs:WPP_GLOBAL_Control
0x140019825  lea     r14, WPP_GLOBAL_Control
0x14001982c  cmp     rcx, r14
0x14001982f  jz      short loc_14001983C
0x140019831  mov     eax, [rcx+2Ch]
0x140019834  test    al, 10h
0x140019836  jnz     loc_1400198CE
0x14001983c  mov     rdi, [rbx+90h]
0x140019843  xor     r9d, r9d; FreeMdlHandler
0x140019846  mov     edx, [rbx+88h]; DataOffsetDelta
0x14001984c  mov     r8b, 1; FreeMdl
0x14001984f  mov     rsi, [rbx+80h]
0x140019856  mov     rcx, rbx; NetBuffer
0x140019859  mov     rbp, [rdi+18h]
0x14001985d  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x140019864  nop     dword ptr [rax+rax+00h]
0x140019869  mov     eax, 0FFFFFFFFh
0x14001986e  lock xadd [rsi+70h], eax
0x140019873  cmp     eax, 1
0x140019876  jnz     short loc_1400198AF
0x140019878  lock xadd [rdi+1E0h], eax
0x140019880  inc     eax
0x140019882  cmp     eax, 5
0x140019885  jg      short loc_1400198F2
0x140019887  mov     rcx, [rdi+130h]; NdisVcHandle
0x14001988e  xor     r8d, r8d; SendCompleteFlags
0x140019891  mov     rdx, rsi; NetBufferLists
0x140019894  call    cs:__imp_NdisMCoSendNetBufferListsComplete
0x14001989b  nop     dword ptr [rax+rax+00h]
0x1400198a0  lock dec dword ptr [rdi+1E0h]
0x1400198a7  mov     rcx, rdi
0x1400198aa  call    DereferenceCall
0x1400198af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400198b6  cmp     rcx, r14
0x1400198b9  jz      short loc_1400198C2
0x1400198bb  mov     eax, [rcx+2Ch]
0x1400198be  test    al, 10h
0x1400198c0  jnz     short loc_140019915
0x1400198c2  add     rsp, 20h
0x1400198c6  pop     r14
0x1400198c8  pop     rdi
0x1400198c9  pop     rsi
0x1400198ca  pop     rbp
0x1400198cb  pop     rbx
0x1400198cc  retn
0x1400198ce  cmp     byte ptr [rcx+29h], 4
0x1400198d2  jb      loc_14001983C
0x1400198d8  mov     rcx, [rcx+18h]
0x1400198dc  lea     r8, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids
0x1400198e3  mov     edx, 28h ; '('
0x1400198e8  call    WPP_SF_
0x1400198ed  jmp     loc_14001983C
0x1400198f2  mov     r8, rbx
0x1400198f5  lea     rdx, SendCompleteDeferred
0x1400198fc  mov     rcx, rbp
0x1400198ff  call    ScheduleWork
0x140019904  test    eax, eax
0x140019906  jnz     loc_140019887
0x14001990c  lock dec dword ptr [rdi+1E0h]
0x140019913  jmp     short loc_1400198AF
0x140019915  cmp     byte ptr [rcx+29h], 4
0x140019919  jb      short loc_1400198C2
0x14001991b  mov     rcx, [rcx+18h]
0x14001991f  lea     r8, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids
0x140019926  mov     edx, 29h ; ')'
0x14001992b  call    WPP_SF_
0x140019930  jmp     short loc_1400198C2
```
