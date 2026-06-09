# FreeMatchBufListInternal

- ea: `0x140004bf0`
- end: `0x140004d38`
- name: `FreeMatchBufListInternal`
- size: `328`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `17`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400016d0`
- `0x140005b60`
- `0x140006060`
- `0x140006240`
- `0x140007ee0`
- `0x1400085f0`
- `0x14001a914`
- `0x14001c2e0`
- `0x14001d6b0`
- `0x14001d86c`
- `0x14001e040`
- `0x140039800`
- `0x140041cf0`
- `0x14004ccb0`
- `0x14004cee0`
- `0x140061480`
- `0x1400679dc`

## callees

- `0x140004970`
- `0x140004bf0`
- `0x140006c40`
- `0x14000c210`
- `0x140038dc8`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140004d20`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140004d20`
- `ntoskrnl!KeGetCurrentIrql` at `0x140004cd2`
- `ntoskrnl!KeGetCurrentIrql` at `0x140004cd2`

## pseudocode

```c
__int64 __fastcall FreeMatchBufListInternal(_QWORD *Entry)
{
  _QWORD *v1; // rsi
  _QWORD *v2; // rbp
  __int64 v3; // rdi
  __int64 v4; // rbx
  bool v5; // dl
  signed __int64 v6; // rcx

  v1 = Entry;
  if ( Entry )
  {
    while ( 1 )
    {
      v2 = (_QWORD *)v1[2];
      v3 = 0;
      if ( *((_WORD *)v1 + 12) )
        break;
LABEL_10:
      if ( (*((_DWORD *)v1 + 7) & 1) == 0 )
      {
        if ( v1[11] )
          WfpPoolFree(v1 + 11);
        ExFreeToNPagedLookasideList(gWfpGlobal, v1);
      }
      v1 = v2;
      if ( !v2 )
        return 0;
    }
    while ( 1 )
    {
      v4 = v1[v3 + 4];
      v5 = 0;
      _InterlockedIncrement64((volatile signed __int64 *)(v4 + 16));
      v6 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v4 + 16), 0xFFFFFFFFFFFFFFFFuLL) - 2;
      if ( (_DWORD)v6 == HIDWORD(v6) )
      {
        _m_prefetchw((const void *)(v4 + 52));
        v5 = (_InterlockedOr((volatile signed __int32 *)(v4 + 52), 0x10u) & 0x10) == 0;
      }
      if ( (*(_DWORD *)(*(_QWORD *)(v4 + 24) + 40LL) & 0x4000) == 0 || !v5 )
        goto LABEL_7;
      if ( !KeGetCurrentIrql() )
        break;
      NetioInsertWorkQueue(&gWfpGlobal[10].L.FreeEx);
LABEL_9:
      v3 = (unsigned int)(v3 + 1);
      if ( (unsigned int)v3 >= *((unsigned __int16 *)v1 + 12) )
        goto LABEL_10;
    }
    FeNotifyIntFilterDelete(v4);
LABEL_7:
    if ( _InterlockedExchangeAdd64((volatile signed __int64 *)(v4 + 16), 0xFFFFFFFFFFFFFFFFuLL) == 1 )
      FreeWFPFilter((PVOID)v4);
    goto LABEL_9;
  }
  return 0;
}

```

## disassembly

```asm
0x140004bf0  push    rsi
0x140004bf2  sub     rsp, 20h
0x140004bf6  mov     rsi, rcx
0x140004bf9  test    rcx, rcx
0x140004bfc  jz      loc_140004CAB
0x140004c02  mov     [rsp+28h+arg_0], rbx
0x140004c07  mov     [rsp+28h+arg_8], rbp
0x140004c0c  mov     [rsp+28h+arg_10], rdi
0x140004c11  mov     [rsp+28h+arg_18], r14
0x140004c16  mov     r14d, 1
0x140004c1c  mov     rbp, [rsi+10h]
0x140004c20  xor     edi, edi
0x140004c22  xor     eax, eax
0x140004c24  cmp     ax, [rsi+18h]
0x140004c28  jnb     short loc_140004C87
0x140004c2a  mov     rbx, [rsi+rdi*8+20h]
0x140004c2f  xor     dl, dl
0x140004c31  lock inc qword ptr [rbx+10h]
0x140004c36  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140004c3d  lock xadd [rbx+10h], rcx
0x140004c43  sub     rcx, 2
0x140004c47  mov     rax, rcx
0x140004c4a  shr     rax, 20h
0x140004c4e  cmp     ecx, eax
0x140004c50  jz      short loc_140004CB4
0x140004c52  mov     rax, [rbx+18h]
0x140004c56  test    dword ptr [rax+28h], 4000h
0x140004c5d  jz      short loc_140004C63
0x140004c5f  test    dl, dl
0x140004c61  jnz     short loc_140004CD2
0x140004c63  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140004c6a  lock xadd [rbx+10h], rax
0x140004c70  cmp     rax, r14
0x140004c73  jnz     short loc_140004C7D
0x140004c75  mov     rcx, rbx; P
0x140004c78  call    FreeWFPFilter
0x140004c7d  movzx   eax, word ptr [rsi+18h]
0x140004c81  inc     edi
0x140004c83  cmp     edi, eax
0x140004c85  jb      short loc_140004C2A
0x140004c87  mov     eax, [rsi+1Ch]
0x140004c8a  test    r14b, al
0x140004c8d  jz      short loc_140004D0B
0x140004c8f  mov     rsi, rbp
0x140004c92  test    rbp, rbp
0x140004c95  jnz     short loc_140004C1C
0x140004c97  mov     r14, [rsp+28h+arg_18]
0x140004c9c  mov     rdi, [rsp+28h+arg_10]
0x140004ca1  mov     rbp, [rsp+28h+arg_8]
0x140004ca6  mov     rbx, [rsp+28h+arg_0]
0x140004cab  xor     eax, eax
0x140004cad  add     rsp, 20h
0x140004cb1  pop     rsi
0x140004cb2  retn
0x140004cb4  prefetchw byte ptr [rbx+34h]
0x140004cb8  mov     eax, [rbx+34h]
0x140004cbb  mov     ecx, eax
0x140004cbd  or      ecx, 10h
0x140004cc0  lock cmpxchg [rbx+34h], ecx
0x140004cc5  jnz     short loc_140004CBB
0x140004cc7  test    al, 10h
0x140004cc9  movzx   edx, dl
0x140004ccc  cmovz   edx, r14d
0x140004cd0  jmp     short loc_140004C52
0x140004cd2  call    cs:__imp_KeGetCurrentIrql
0x140004cd9  nop     dword ptr [rax+rax+00h]
0x140004cde  test    al, al
0x140004ce0  jnz     short loc_140004CEF
0x140004ce2  mov     rcx, rbx
0x140004ce5  call    FeNotifyIntFilterDelete
0x140004cea  jmp     loc_140004C63
0x140004cef  mov     rcx, cs:gWfpGlobal
0x140004cf6  lea     rdx, [rbx+28h]
0x140004cfa  add     rcx, 538h; Context
0x140004d01  call    NetioInsertWorkQueue
0x140004d06  jmp     loc_140004C7D
0x140004d0b  cmp     qword ptr [rsi+58h], 0
0x140004d10  lea     rcx, [rsi+58h]
0x140004d14  jnz     short loc_140004D31
0x140004d16  mov     rcx, cs:gWfpGlobal; Lookaside
0x140004d1d  mov     rdx, rsi; Entry
0x140004d20  call    cs:__imp_ExFreeToNPagedLookasideList
0x140004d27  nop     dword ptr [rax+rax+00h]
0x140004d2c  jmp     loc_140004C8F
0x140004d31  call    WfpPoolFree
0x140004d36  jmp     short loc_140004D16
```
