# CallpSendComplete

- ea: `0x140018890`
- end: `0x140018b04`
- name: `CallpSendComplete`
- size: `628`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140001a70`
- `0x1400028f0`
- `0x140003e38`
- `0x140004308`
- `0x140007710`
- `0x140018890`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140018aa4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018aa4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018a81`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018a81`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400188f5`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140018a71`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400188f5`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140018a71`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x140018971`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x140018971`

## pseudocode

```c
__int64 __fastcall CallpSendComplete(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, unsigned int a6)
{
  __int64 v8; // rsi
  ULONG v9; // edx
  __int64 v10; // r8
  __int64 result; // rax
  char v12; // r14
  __int64 v13; // rcx
  KIRQL v14; // al

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqD(WPP_GLOBAL_Control->AttachedDevice, 95, a3, a3, a2, a6);
  }
  v8 = *(_QWORD *)(a2 + 128);
  if ( a6 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 96, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids, a6);
    }
    *(_DWORD *)(v8 + 140) = -1073741823;
    _InterlockedIncrement(&dword_14000B3F8);
    _InterlockedIncrement((volatile signed __int32 *)(a3 + 672));
  }
  v9 = *(_DWORD *)(a2 + 136);
  if ( v8 == *(_QWORD *)(a3 + 480) )
  {
    NdisAdvanceNetBufferDataStart((PNET_BUFFER)a2, v9, 0, 0);
    v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a3 + 96));
    ++*(_DWORD *)(a3 + 460);
    *(_BYTE *)(a3 + 104) = v14;
    *(_BYTE *)(a3 + 464) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)(a3 + 96), v14);
    _InterlockedIncrement(&dword_14000B3F4);
    _InterlockedIncrement((volatile signed __int32 *)(a3 + 684));
    _InterlockedIncrement((volatile signed __int32 *)(a3 + 664));
    DereferenceRefCount(a3);
    return DereferenceRefCount(a3 + 32);
  }
  NdisAdvanceNetBufferDataStart((PNET_BUFFER)a2, v9, 1u, 0);
  _InterlockedIncrement(&dword_14000B3F4);
  _InterlockedIncrement((volatile signed __int32 *)(a3 + 664));
  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(v8 + 112), 0xFFFFFFFF);
  if ( (_DWORD)result != 1 )
    return result;
  if ( _InterlockedIncrement((volatile signed __int32 *)(a3 + 504)) >= 5 )
  {
    v12 = 0;
    result = ScheduleWorkItem(CallpSendCompleteDeferred, a3, v8, a6);
    if ( !(_DWORD)result )
      goto LABEL_10;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqD(WPP_GLOBAL_Control->AttachedDevice, 97, v10, a3, v8, a6);
  }
  NdisMCoSendNetBufferListsComplete(*(NDIS_HANDLE *)(a3 + 224), (PNET_BUFFER_LIST)v8, 0);
  v12 = 1;
  v13 = *(_QWORD *)(a3 + 56) + 192LL;
  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)v13, 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
  {
    result = (*(__int64 (**)(void))(v13 + 8))();
    _InterlockedDecrement((volatile signed __int32 *)(a3 + 504));
  }
  else
  {
LABEL_10:
    _InterlockedDecrement((volatile signed __int32 *)(a3 + 504));
    if ( !v12 )
      return result;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a3 + 32), 0xFFFFFFFF) == 1 )
    return (*(__int64 (**)(void))(a3 + 40))();
  return result;
}

```

## disassembly

```asm
0x140018890  mov     [rsp+arg_8], rbx
0x140018895  mov     [rsp+arg_10], rbp
0x14001889a  push    rsi
0x14001889b  push    rdi
0x14001889c  push    r15
0x14001889e  sub     rsp, 30h
0x1400188a2  mov     rbx, r8
0x1400188a5  mov     rdi, rdx
0x1400188a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400188af  lea     r15, WPP_GLOBAL_Control
0x1400188b6  mov     ebp, [rsp+48h+arg_28]
0x1400188ba  cmp     rcx, r15
0x1400188bd  jz      short loc_1400188CA
0x1400188bf  mov     eax, [rcx+2Ch]
0x1400188c2  test    al, 20h
0x1400188c4  jnz     loc_1400189F7
0x1400188ca  mov     rsi, [rdi+80h]
0x1400188d1  test    ebp, ebp
0x1400188d3  jnz     loc_140018A20
0x1400188d9  mov     edx, [rdi+88h]; DataOffsetDelta
0x1400188df  xor     r9d, r9d; FreeMdlHandler
0x1400188e2  mov     rcx, rdi; NetBuffer
0x1400188e5  cmp     rsi, [rbx+1E0h]
0x1400188ec  jz      loc_140018A6E
0x1400188f2  mov     r8b, 1; FreeMdl
0x1400188f5  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x1400188fc  nop     dword ptr [rax+rax+00h]
0x140018901  lock inc cs:dword_14000B3F4
0x140018908  lock inc dword ptr [rbx+298h]
0x14001890f  mov     edi, 0FFFFFFFFh
0x140018914  mov     eax, edi
0x140018916  lock xadd [rsi+70h], eax
0x14001891b  cmp     eax, 1
0x14001891e  jz      short loc_140018934
0x140018920  mov     rbx, [rsp+48h+arg_8]
0x140018925  mov     rbp, [rsp+48h+arg_10]
0x14001892a  add     rsp, 30h
0x14001892e  pop     r15
0x140018930  pop     rdi
0x140018931  pop     rsi
0x140018932  retn
0x140018934  mov     [rsp+48h+arg_0], r14
0x140018939  mov     eax, 1
0x14001893e  lock xadd [rbx+1F8h], eax
0x140018946  inc     eax
0x140018948  cmp     eax, 5
0x14001894b  jge     short loc_1400189B9
0x14001894d  mov     rcx, cs:WPP_GLOBAL_Control
0x140018954  cmp     rcx, r15
0x140018957  jz      short loc_140018964
0x140018959  mov     eax, [rcx+2Ch]
0x14001895c  test    al, 20h
0x14001895e  jnz     loc_140018ADB
0x140018964  mov     rcx, [rbx+0E0h]; NdisVcHandle
0x14001896b  xor     r8d, r8d; SendCompleteFlags
0x14001896e  mov     rdx, rsi; NetBufferLists
0x140018971  call    cs:__imp_NdisMCoSendNetBufferListsComplete
0x140018978  nop     dword ptr [rax+rax+00h]
0x14001897d  mov     rcx, [rbx+38h]
0x140018981  mov     r14b, 1
0x140018984  add     rcx, 0C0h
0x14001898b  mov     eax, edi
0x14001898d  lock xadd [rcx], eax
0x140018991  cmp     eax, 1
0x140018994  jz      short loc_1400189E5
0x140018996  lock dec dword ptr [rbx+1F8h]
0x14001899d  test    r14b, r14b
0x1400189a0  jz      short loc_1400189AF
0x1400189a2  lea     rcx, [rbx+20h]
0x1400189a6  lock xadd [rcx], edi
0x1400189aa  cmp     edi, 1
0x1400189ad  jz      short loc_1400189DA
0x1400189af  mov     r14, [rsp+48h+arg_0]
0x1400189b4  jmp     loc_140018920
0x1400189b9  mov     r9d, ebp
0x1400189bc  lea     rcx, CallpSendCompleteDeferred
0x1400189c3  mov     r8, rsi
0x1400189c6  mov     rdx, rbx
0x1400189c9  xor     r14b, r14b
0x1400189cc  call    ScheduleWorkItem
0x1400189d1  test    eax, eax
0x1400189d3  jz      short loc_140018996
0x1400189d5  jmp     loc_14001894D
0x1400189da  mov     rax, [rcx+8]
0x1400189de  call    _guard_dispatch_icall
0x1400189e3  jmp     short loc_1400189AF
0x1400189e5  mov     rax, [rcx+8]
0x1400189e9  call    _guard_dispatch_icall
0x1400189ee  lock dec dword ptr [rbx+1F8h]
0x1400189f5  jmp     short loc_1400189A2
0x1400189f7  cmp     byte ptr [rcx+29h], 2
0x1400189fb  jb      loc_1400188CA
0x140018a01  mov     rcx, [rcx+18h]
0x140018a05  mov     edx, 5Fh ; '_'
0x140018a0a  mov     [rsp+48h+var_20], ebp
0x140018a0e  mov     r9, rbx
0x140018a11  mov     [rsp+48h+var_28], rdi
0x140018a16  call    WPP_SF_qqD
0x140018a1b  jmp     loc_1400188CA
0x140018a20  mov     rcx, cs:WPP_GLOBAL_Control
0x140018a27  cmp     rcx, r15
0x140018a2a  jz      short loc_140018A51
0x140018a2c  mov     eax, [rcx+2Ch]
0x140018a2f  test    al, 10h
0x140018a31  jz      short loc_140018A51
0x140018a33  cmp     byte ptr [rcx+29h], 1
0x140018a37  jb      short loc_140018A51
0x140018a39  mov     rcx, [rcx+18h]
0x140018a3d  lea     r8, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids
0x140018a44  mov     edx, 60h ; '`'
0x140018a49  mov     r9d, ebp
0x140018a4c  call    WPP_SF_d
0x140018a51  mov     dword ptr [rsi+8Ch], 0C0000001h
0x140018a5b  lock inc cs:dword_14000B3F8
0x140018a62  lock inc dword ptr [rbx+2A0h]
0x140018a69  jmp     loc_1400188D9
0x140018a6e  xor     r8d, r8d; FreeMdl
0x140018a71  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x140018a78  nop     dword ptr [rax+rax+00h]
0x140018a7d  lea     rcx, [rbx+60h]; SpinLock
0x140018a81  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140018a88  nop     dword ptr [rax+rax+00h]
0x140018a8d  inc     dword ptr [rbx+1CCh]
0x140018a93  lea     rcx, [rbx+60h]; SpinLock
0x140018a97  movzx   edx, al; NewIrql
0x140018a9a  mov     [rbx+68h], al
0x140018a9d  mov     byte ptr [rbx+1D0h], 0
0x140018aa4  call    cs:__imp_KeReleaseSpinLock
0x140018aab  nop     dword ptr [rax+rax+00h]
0x140018ab0  lock inc cs:dword_14000B3F4
0x140018ab7  lock inc dword ptr [rbx+2ACh]
0x140018abe  lock inc dword ptr [rbx+298h]
0x140018ac5  mov     rcx, rbx
0x140018ac8  call    DereferenceRefCount
0x140018acd  lea     rcx, [rbx+20h]
0x140018ad1  call    DereferenceRefCount
0x140018ad6  jmp     loc_140018920
0x140018adb  cmp     byte ptr [rcx+29h], 2
0x140018adf  jb      loc_140018964
0x140018ae5  mov     rcx, [rcx+18h]
0x140018ae9  mov     edx, 61h ; 'a'
0x140018aee  mov     [rsp+48h+var_20], ebp
0x140018af2  mov     r9, rbx
0x140018af5  mov     [rsp+48h+var_28], rsi
0x140018afa  call    WPP_SF_qqD
0x140018aff  jmp     loc_140018964
```
