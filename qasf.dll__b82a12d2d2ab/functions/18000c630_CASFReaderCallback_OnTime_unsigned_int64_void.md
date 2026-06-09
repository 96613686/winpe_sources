# CASFReaderCallback::OnTime(unsigned __int64,void *)

- ea: `0x18000c630`
- end: `0x18000c675`
- name: `?OnTime@CASFReaderCallback@@UEAAJ_KPEAX@Z`
- size: `69`
- prototype: `__int64 __fastcall(CASFReaderCallback *__hidden this, unsigned __int64, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000c630`
- `0x18000cba8`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReaderCallback::OnTime(CASFReaderCallback *this, unsigned __int64 a2, void *a3)
{
  __int64 v3; // rcx

  v3 = *((_QWORD *)this + 1);
  if ( !*(_QWORD *)(v3 + 384) || a2 < *(_QWORD *)(v3 + 264) )
    return (*(__int64 (__fastcall **)(_QWORD, unsigned __int64, void *))(**(_QWORD **)(v3 + 352) + 40LL))(
             *(_QWORD *)(v3 + 352),
             a2 + 10000000,
             a3);
  CASFReader::SendEOS((CASFReader *)v3);
  return 0;
}

```

## disassembly

```asm
0x18000c630  sub     rsp, 28h
0x18000c634  mov     rcx, [rcx+8]; this
0x18000c638  cmp     qword ptr [rcx+180h], 0
0x18000c640  jz      short loc_18000C657
0x18000c642  cmp     rdx, [rcx+108h]
0x18000c649  jb      short loc_18000C657
0x18000c64b  call    ?SendEOS@CASFReader@@AEAAJXZ; CASFReader::SendEOS(void)
0x18000c650  xor     eax, eax
0x18000c652  add     rsp, 28h
0x18000c656  retn
0x18000c657  mov     rcx, [rcx+160h]
0x18000c65e  add     rdx, 989680h
0x18000c665  mov     rax, [rcx]
0x18000c668  mov     rax, [rax+28h]
0x18000c66c  add     rsp, 28h
0x18000c670  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
