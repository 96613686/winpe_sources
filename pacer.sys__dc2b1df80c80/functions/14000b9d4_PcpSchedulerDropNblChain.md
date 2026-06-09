# PcpSchedulerDropNblChain

- ea: `0x14000b9d4`
- end: `0x14000bac5`
- name: `PcpSchedulerDropNblChain`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140009b80`

## callees

- `0x140009050`
- `0x14000b9d4`
- `0x140011e28`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000ba62`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000ba62`

## pseudocode

```c
void __fastcall PcpSchedulerDropNblChain(__int64 a1, _QWORD *a2, struct _NET_BUFFER_LIST *a3, ULONG a4)
{
  struct _NET_BUFFER_LIST **p_Next; // r14
  struct _NET_BUFFER_LIST *Alignment; // r15
  struct _NET_BUFFER_LIST *v9; // rbx
  PNET_BUFFER_LIST_CONTEXT Context; // rax
  __int64 Offset; // rdi
  __int64 v12; // rdi
  struct _NET_BUFFER_LIST *v13; // [rsp+60h] [rbp+18h] BYREF

  if ( a3 )
  {
    v13 = 0;
    p_Next = &v13;
    while ( 1 )
    {
      Alignment = (struct _NET_BUFFER_LIST *)a3->Link.Alignment;
      a3->Link.Alignment = 0;
      if ( a3->SourceHandle == (NDIS_HANDLE)a2[7] )
      {
        Context = a3->Context;
        Offset = Context->Offset;
        if ( *(_DWORD *)&Context->ContextData[Offset + 40] )
        {
          v9 = a3;
LABEL_9:
          if ( v9 )
            _InterlockedIncrement((volatile signed __int32 *)(a1 + 172));
          goto LABEL_11;
        }
        Context->ContextData[Offset + 44] = 1;
        v9 = 0;
        v12 = *(_QWORD *)&Context->ContextData[Offset + 16];
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v12 + 48), 0xFFFFFFFF) == 1 )
        {
          QosNblCadReassemble(v12, 0);
          v9 = *(struct _NET_BUFFER_LIST **)(v12 + 24);
          ExFreeToNPagedLookasideList(QosgNblCadLookasideList, (PVOID)v12);
          goto LABEL_9;
        }
      }
      else
      {
        v9 = a3;
      }
LABEL_11:
      *p_Next = v9;
      a3 = Alignment;
      if ( !v9 )
        v9 = (struct _NET_BUFFER_LIST *)p_Next;
      p_Next = &v9->Next;
      if ( !Alignment )
      {
        if ( v13 )
          PcpSchedulerCompleteNblChain(a1, a2, v13, a4);
        return;
      }
    }
  }
}

```

## disassembly

```asm
0x14000b9d4  test    r8, r8
0x14000b9d7  jz      locret_14000BAC3
0x14000b9dd  mov     rax, rsp
0x14000b9e0  mov     [rax+8], rbx
0x14000b9e4  mov     [rax+10h], rbp
0x14000b9e8  push    rsi
0x14000b9e9  push    rdi
0x14000b9ea  push    r12
0x14000b9ec  push    r14
0x14000b9ee  push    r15
0x14000b9f0  sub     rsp, 20h
0x14000b9f4  mov     r12d, r9d
0x14000b9f7  mov     qword ptr [rax+18h], 0
0x14000b9ff  mov     rsi, rdx
0x14000ba02  lea     r14, [rax+18h]
0x14000ba06  mov     rbp, rcx
0x14000ba09  mov     r15, [r8]
0x14000ba0c  mov     qword ptr [r8], 0
0x14000ba13  mov     rax, [rsi+38h]
0x14000ba17  cmp     [r8+78h], rax
0x14000ba1b  jz      short loc_14000BA22
0x14000ba1d  mov     rbx, r8
0x14000ba20  jmp     short loc_14000BA7F
0x14000ba22  mov     rax, [r8+10h]
0x14000ba26  movzx   edi, word ptr [rax+0Ah]
0x14000ba2a  cmp     dword ptr [rdi+rax+38h], 0
0x14000ba2f  jnz     short loc_14000BA70
0x14000ba31  mov     byte ptr [rdi+rax+3Ch], 1
0x14000ba36  xor     ebx, ebx
0x14000ba38  mov     rdi, [rdi+rax+20h]
0x14000ba3d  or      eax, 0FFFFFFFFh
0x14000ba40  lock xadd [rdi+30h], eax
0x14000ba45  cmp     eax, 1
0x14000ba48  jnz     short loc_14000BA7F
0x14000ba4a  xor     edx, edx
0x14000ba4c  mov     rcx, rdi
0x14000ba4f  call    QosNblCadReassemble
0x14000ba54  mov     rcx, cs:QosgNblCadLookasideList; Lookaside
0x14000ba5b  mov     rdx, rdi; Entry
0x14000ba5e  mov     rbx, [rdi+18h]
0x14000ba62  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000ba69  nop     dword ptr [rax+rax+00h]
0x14000ba6e  jmp     short loc_14000BA73
0x14000ba70  mov     rbx, r8
0x14000ba73  test    rbx, rbx
0x14000ba76  jz      short loc_14000BA7F
0x14000ba78  lock inc dword ptr [rbp+0ACh]
0x14000ba7f  test    rbx, rbx
0x14000ba82  mov     [r14], rbx
0x14000ba85  mov     r8, r15
0x14000ba88  cmovz   rbx, r14
0x14000ba8c  mov     r14, rbx
0x14000ba8f  test    r15, r15
0x14000ba92  jnz     loc_14000BA09
0x14000ba98  mov     r8, [rsp+48h+arg_10]
0x14000ba9d  test    r8, r8
0x14000baa0  jz      short loc_14000BAAD
0x14000baa2  mov     r9d, r12d
0x14000baa5  mov     rdx, rsi
0x14000baa8  call    PcpSchedulerCompleteNblChain
0x14000baad  mov     rbx, [rsp+48h+arg_0]
0x14000bab2  mov     rbp, [rsp+48h+arg_8]
0x14000bab7  add     rsp, 20h
0x14000babb  pop     r15
0x14000babd  pop     r14
0x14000babf  pop     r12
0x14000bac1  pop     rdi
0x14000bac2  pop     rsi
0x14000bac3  retn
```
