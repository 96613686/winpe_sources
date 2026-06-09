# TlgAggregateInternalProviderCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x140046df0`
- end: `0x140046e52`
- name: `?TlgAggregateInternalProviderCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `98`
- prototype: `void __fastcall(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400468e0`
- `0x140046df0`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140046e3f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140046e3f`
- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x140046e09`
- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x140046e09`

## pseudocode

```c
void __fastcall TlgAggregateInternalProviderCallback(const struct _GUID *a1, int a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rdx
  int v5; // r8d
  int v6; // r9d
  const __m128i *i; // rbx

  if ( a2 == 2 && a4 == 32 && (unsigned __int8)ExTryAcquirePushLockExclusiveEx(&unk_14001AC08, 0) )
  {
    for ( i = (const __m128i *)qword_14001AC10; i; i = (const __m128i *)i[22].m128i_i64[0] )
      LookUpTableFlushComplete(i, v4, v5, v6);
    ExReleasePushLockExclusiveEx(&unk_14001AC08, 0);
  }
}

```

## disassembly

```asm
0x140046df0  cmp     edx, 2
0x140046df3  jnz     short locret_140046E50
0x140046df5  push    rbx
0x140046df6  sub     rsp, 20h
0x140046dfa  cmp     r9, 20h ; ' '
0x140046dfe  jnz     short loc_140046E4B
0x140046e00  xor     edx, edx
0x140046e02  lea     rcx, unk_14001AC08
0x140046e09  call    cs:__imp_ExTryAcquirePushLockExclusiveEx
0x140046e10  nop     dword ptr [rax+rax+00h]
0x140046e15  test    al, al
0x140046e17  jz      short loc_140046E4B
0x140046e19  mov     rbx, cs:qword_14001AC10
0x140046e20  jmp     short loc_140046E31
0x140046e22  mov     rcx, rbx
0x140046e25  call    LookUpTableFlushComplete
0x140046e2a  mov     rbx, [rbx+160h]
0x140046e31  test    rbx, rbx
0x140046e34  jnz     short loc_140046E22
0x140046e36  xor     edx, edx
0x140046e38  lea     rcx, unk_14001AC08
0x140046e3f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140046e46  nop     dword ptr [rax+rax+00h]
0x140046e4b  add     rsp, 20h
0x140046e4f  pop     rbx
0x140046e50  retn
```
