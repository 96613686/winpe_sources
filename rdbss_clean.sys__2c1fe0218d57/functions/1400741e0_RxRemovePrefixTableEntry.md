# RxRemovePrefixTableEntry

- ea: `0x1400741e0`
- end: `0x140074307`
- name: `RxRemovePrefixTableEntry`
- size: `295`
- prototype: `void __stdcall(PRX_PREFIX_TABLE ThisTable, PRX_PREFIX_ENTRY Entry)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140010760`
- `0x140010fb0`
- `0x140012370`
- `0x1400780a0`

## callees

- `0x14001b178`
- `0x1400741e0`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14007421a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14007421a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14007423e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14007423e`
- `ntoskrnl!RtlRbRemoveNode` at `0x140074251`
- `ntoskrnl!RtlRbRemoveNode` at `0x140074251`

## pseudocode

```c
void __stdcall RxRemovePrefixTableEntry(PRX_PREFIX_TABLE ThisTable, PRX_PREFIX_ENTRY Entry)
{
  struct _LIST_ENTRY **p_Blink; // rsi
  struct _RX_PREFIX_TABLE *i; // rdx
  unsigned __int64 Flink; // r8
  _QWORD *v7; // r9
  struct _LIST_ENTRY **v8; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqZ(
      WPP_GLOBAL_Control->AttachedDevice,
      12,
      (unsigned int)&WPP_04af8fc7118b317781e27056f3398603_Traceguids,
      (_DWORD)Entry,
      (char)Entry->Prefix.Buffer,
      (__int64)&Entry->SavedHashValue);
  }
  p_Blink = &Entry->HashLinks.Blink;
  ExAcquirePushLockExclusiveEx(&ThisTable->CaseInsensitiveMatch, 0);
  for ( i = (struct _RX_PREFIX_TABLE *)ThisTable->HashBuckets[0].Flink;
        i != (struct _RX_PREFIX_TABLE *)ThisTable->HashBuckets;
        i = *(struct _RX_PREFIX_TABLE **)&i->NodeTypeCode )
  {
    if ( (struct _LIST_ENTRY **)i->TableLock.OwnerTable == p_Blink )
    {
      Flink = (unsigned __int64)Entry->MemberQLinks.Flink;
      if ( Flink )
      {
        v7 = *(_QWORD **)Flink;
        if ( *(_QWORD *)Flink )
        {
          do
          {
            Flink = (unsigned __int64)v7;
            v7 = (_QWORD *)*v7;
          }
          while ( v7 );
        }
      }
      else
      {
        v8 = &Entry->HashLinks.Blink;
        for ( Flink = (unsigned __int64)Entry->MemberQLinks.Blink & 0xFFFFFFFFFFFFFFFCuLL;
              Flink;
              Flink = *(_QWORD *)(Flink + 16) & 0xFFFFFFFFFFFFFFFCuLL )
        {
          if ( *(struct _LIST_ENTRY ***)Flink == v8 )
            break;
          v8 = (struct _LIST_ENTRY **)Flink;
        }
      }
      i->TableLock.OwnerTable = (POWNER_ENTRY)Flink;
    }
  }
  ExReleasePushLockExclusiveEx(&ThisTable->CaseInsensitiveMatch, 0);
  RtlRbRemoveNode(&ThisTable->MemberQueue, &Entry->HashLinks.Blink);
  *(_OWORD *)p_Blink = 0;
  Entry->MemberQLinks.Blink = 0;
  Entry->Prefix.Buffer = 0;
  ++ThisTable->Version;
}

```

## disassembly

```asm
0x1400741e0  push    rbx
0x1400741e2  push    rbp
0x1400741e3  push    rsi
0x1400741e4  push    rdi
0x1400741e5  sub     rsp, 38h
0x1400741e9  mov     rdi, rdx
0x1400741ec  mov     rbx, rcx
0x1400741ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400741f6  lea     rax, WPP_GLOBAL_Control
0x1400741fd  cmp     rcx, rax
0x140074200  jz      short loc_14007420D
0x140074202  mov     eax, [rcx+2Ch]
0x140074205  test    al, al
0x140074207  js      loc_1400742CE
0x14007420d  xor     edx, edx
0x14007420f  lea     rcx, [rbx+88h]
0x140074216  lea     rsi, [rdi+18h]
0x14007421a  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140074221  nop     dword ptr [rax+rax+00h]
0x140074226  lea     rcx, [rbx+90h]
0x14007422d  mov     rdx, [rcx]
0x140074230  cmp     rdx, rcx
0x140074233  jnz     short loc_140074286
0x140074235  xor     edx, edx
0x140074237  lea     rcx, [rbx+88h]
0x14007423e  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140074245  nop     dword ptr [rax+rax+00h]
0x14007424a  lea     rcx, [rbx+8]
0x14007424e  mov     rdx, rsi
0x140074251  call    cs:__imp_RtlRbRemoveNode
0x140074258  nop     dword ptr [rax+rax+00h]
0x14007425d  xor     eax, eax
0x14007425f  xorps   xmm0, xmm0
0x140074262  movups  xmmword ptr [rsi], xmm0
0x140074265  mov     [rsi+10h], rax
0x140074269  mov     [rdi+38h], rax
0x14007426d  inc     dword ptr [rbx+4]
0x140074270  add     rsp, 38h
0x140074274  pop     rdi
0x140074275  pop     rsi
0x140074276  pop     rbp
0x140074277  pop     rbx
0x140074278  retn
0x14007427a  mov     [rdx+28h], r8
0x14007427e  mov     rdx, [rdx]
0x140074281  cmp     rdx, rcx
0x140074284  jz      short loc_140074235
0x140074286  cmp     [rdx+28h], rsi
0x14007428a  jnz     short loc_14007427E
0x14007428c  mov     r8, [rsi+8]
0x140074290  test    r8, r8
0x140074293  jz      short loc_1400742AD
0x140074295  mov     r9, [r8]
0x140074298  test    r9, r9
0x14007429b  jz      short loc_14007427A
0x14007429d  mov     rax, [r9]
0x1400742a0  mov     r8, r9
0x1400742a3  mov     r9, rax
0x1400742a6  test    rax, rax
0x1400742a9  jnz     short loc_14007429D
0x1400742ab  jmp     short loc_14007427A
0x1400742ad  mov     r8, [rsi+10h]
0x1400742b1  mov     rax, rsi
0x1400742b4  and     r8, 0FFFFFFFFFFFFFFFCh
0x1400742b8  jz      short loc_14007427A
0x1400742ba  cmp     [r8], rax
0x1400742bd  jz      short loc_14007427A
0x1400742bf  mov     rax, r8
0x1400742c2  mov     r8, [r8+10h]
0x1400742c6  and     r8, 0FFFFFFFFFFFFFFFCh
0x1400742ca  jnz     short loc_1400742BA
0x1400742cc  jmp     short loc_14007427A
0x1400742ce  cmp     byte ptr [rcx+29h], 4
0x1400742d2  jb      loc_14007420D
0x1400742d8  mov     rcx, [rcx+18h]
0x1400742dc  lea     rax, [rdx+8]
0x1400742e0  mov     [rsp+58h+var_30], rax
0x1400742e5  lea     r8, WPP_04af8fc7118b317781e27056f3398603_Traceguids
0x1400742ec  mov     rax, [rdi+38h]
0x1400742f0  mov     edx, 0Ch
0x1400742f5  mov     r9, rdi
0x1400742f8  mov     [rsp+58h+var_38], rax
0x1400742fd  call    WPP_SF_qqZ
0x140074302  jmp     loc_14007420D
```
