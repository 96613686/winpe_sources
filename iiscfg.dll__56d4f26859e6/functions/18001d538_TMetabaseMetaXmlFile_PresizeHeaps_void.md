# TMetabaseMetaXmlFile::PresizeHeaps(void)

- ea: `0x18001d538`
- end: `0x18001d5fd`
- name: `?PresizeHeaps@TMetabaseMetaXmlFile@@AEAAXXZ`
- size: `197`
- prototype: `void __fastcall(TMetabaseMetaXmlFile *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180017e84`

## callees

- `0x180015990`
- `0x180016db0`
- `0x18001d538`
- `0x180030010`

## pseudocode

```c
void __fastcall TMetabaseMetaXmlFile::PresizeHeaps(TMetabaseMetaXmlFile *this)
{
  TPooledHeap *v1; // rdi
  __int64 v3; // rsi
  unsigned int MatchingHeapEntry; // eax
  unsigned int v5; // eax
  int v6; // [rsp+50h] [rbp+8h] BYREF

  v1 = (TMetabaseMetaXmlFile *)((char *)this + 248);
  *((_DWORD *)this + 68) = 0x1000000;
  v3 = 0;
  do
  {
    v6 = v3;
    MatchingHeapEntry = TPooledHeap::FindMatchingHeapEntry(v1, (const unsigned __int8 *)&v6, 4u);
    if ( !MatchingHeapEntry )
    {
      if ( (unsigned int)(*((_DWORD *)this + 66) - *((_DWORD *)this + 67)) < 4 )
        (*(void (__fastcall **)(TPooledHeap *, __int64))(*(_QWORD *)v1 + 8LL))(v1, 4);
      *(_DWORD *)(*((unsigned int *)this + 67) + *((_QWORD *)this + 32)) = 4;
      *((_DWORD *)this + 67) += 4;
      MatchingHeapEntry = THeap<unsigned long>::AddItemToHeap(v1, &v6, 4);
    }
    *((_DWORD *)this + v3 + 204) = MatchingHeapEntry;
    v3 = (unsigned int)(v3 + 1);
  }
  while ( (_DWORD)v3 != 429 );
  v5 = (*(__int64 (__fastcall **)(TPooledHeap *))(*(_QWORD *)v1 + 16LL))(v1);
  if ( v5 > 0x1000000 )
    v5 = 0x1000000;
  *((_DWORD *)this + 68) = v5;
}

```

## disassembly

```asm
0x18001d538  push    rbx
0x18001d53a  push    rsi
0x18001d53b  push    rdi
0x18001d53c  push    r14
0x18001d53e  sub     rsp, 28h
0x18001d542  lea     rdi, [rcx+0F8h]
0x18001d549  mov     r14d, 1000000h
0x18001d54f  mov     [rdi+18h], r14d
0x18001d553  mov     rbx, rcx
0x18001d556  xor     esi, esi
0x18001d558  mov     r8d, 4; unsigned int
0x18001d55e  mov     [rsp+48h+arg_0], esi
0x18001d562  lea     rdx, [rsp+48h+arg_0]; unsigned __int8 *
0x18001d567  mov     rcx, rdi; this
0x18001d56a  call    ?FindMatchingHeapEntry@TPooledHeap@@QEBAKPEBEK@Z; TPooledHeap::FindMatchingHeapEntry(uchar const *,ulong)
0x18001d56f  test    eax, eax
0x18001d571  jnz     short loc_18001D5C6
0x18001d573  mov     eax, [rbx+108h]
0x18001d579  sub     eax, [rbx+10Ch]
0x18001d57f  cmp     eax, 4
0x18001d582  jnb     short loc_18001D598
0x18001d584  mov     rax, [rdi]
0x18001d587  mov     edx, 4
0x18001d58c  mov     rcx, rdi
0x18001d58f  mov     rax, [rax+8]
0x18001d593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d598  mov     ecx, [rbx+10Ch]
0x18001d59e  lea     rdx, [rsp+48h+arg_0]
0x18001d5a3  mov     rax, [rbx+100h]
0x18001d5aa  mov     r8d, 4
0x18001d5b0  mov     dword ptr [rcx+rax], 4
0x18001d5b7  mov     rcx, rdi
0x18001d5ba  add     dword ptr [rbx+10Ch], 4
0x18001d5c1  call    ?AddItemToHeap@?$THeap@K@@QEAAKPEBEK@Z; THeap<ulong>::AddItemToHeap(uchar const *,ulong)
0x18001d5c6  mov     [rbx+rsi*4+330h], eax
0x18001d5cd  inc     esi
0x18001d5cf  cmp     esi, 1ADh
0x18001d5d5  jnz     short loc_18001D558
0x18001d5d7  mov     rax, [rdi]
0x18001d5da  mov     rcx, rdi
0x18001d5dd  mov     rax, [rax+10h]
0x18001d5e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5e6  cmp     eax, r14d
0x18001d5e9  cmova   eax, r14d
0x18001d5ed  mov     [rbx+110h], eax
0x18001d5f3  add     rsp, 28h
0x18001d5f7  pop     r14
0x18001d5f9  pop     rdi
0x18001d5fa  pop     rsi
0x18001d5fb  pop     rbx
0x18001d5fc  retn
```
