# CompressedStreamDump::CompressedMemStream::AppendMemoryRegion(MemoryRegion &)

- ea: `0x18001df74`
- end: `0x18001e020`
- name: `?AppendMemoryRegion@CompressedMemStream@CompressedStreamDump@@AEAAXAEAUMemoryRegion@@@Z`
- size: `172`
- prototype: `void __fastcall(CompressedStreamDump::CompressedMemStream *__hidden this, struct MemoryRegion *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001db40`

## callees

- `0x18001d100`
- `0x18001df74`
- `0x18001e804`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CompressedStreamDump::CompressedMemStream::AppendMemoryRegion(
        CompressedStreamDump::CompressedMemStream *this,
        struct MemoryRegion *a2)
{
  __int64 v4; // rcx
  char *v5; // rdi
  _OWORD *v6; // rdx

  *((_QWORD *)a2 + 2) = **((_QWORD **)this + 42);
  *((_DWORD *)a2 + 7) = *(_DWORD *)(*((_QWORD *)this + 42) + 8LL);
  v4 = *((_QWORD *)this + 42);
  if ( !*(_DWORD *)(v4 + 32) )
    *(_QWORD *)(v4 + 24) = *(_QWORD *)a2;
  v5 = (char *)this + 80;
  *(_DWORD *)(*((_QWORD *)this + 42) + 8LL) += *((_DWORD *)a2 + 6);
  ++*(_DWORD *)(*((_QWORD *)this + 42) + 32LL);
  if ( (__int64)(*((_QWORD *)this + 11) - *((_QWORD *)this + 10)) >> 5 == *((_DWORD *)this + 26) )
    CompressedStreamDump::CompressedMemStream::FlushCachedRegionsToStorage(this);
  v6 = (_OWORD *)*((_QWORD *)v5 + 1);
  if ( v6 == *((_OWORD **)v5 + 2) )
  {
    std::vector<MemoryRegion>::_Emplace_reallocate<MemoryRegion const &>(v5, v6, a2);
  }
  else
  {
    *v6 = *(_OWORD *)a2;
    v6[1] = *((_OWORD *)a2 + 1);
    *((_QWORD *)v5 + 1) += 32LL;
  }
}

```

## disassembly

```asm
0x18001df74  mov     [rsp+arg_0], rbx
0x18001df79  push    rdi
0x18001df7a  sub     rsp, 20h
0x18001df7e  mov     rax, [rcx+150h]
0x18001df85  mov     rbx, rdx
0x18001df88  mov     rdx, rcx
0x18001df8b  mov     r8, [rax]
0x18001df8e  mov     [rbx+10h], r8
0x18001df92  mov     rax, [rcx+150h]
0x18001df99  mov     r8d, [rax+8]
0x18001df9d  mov     [rbx+1Ch], r8d
0x18001dfa1  mov     rcx, [rcx+150h]
0x18001dfa8  cmp     dword ptr [rcx+20h], 0
0x18001dfac  jnz     short loc_18001DFB5
0x18001dfae  mov     rax, [rbx]
0x18001dfb1  mov     [rcx+18h], rax
0x18001dfb5  mov     rcx, [rdx+150h]
0x18001dfbc  lea     rdi, [rdx+50h]
0x18001dfc0  mov     eax, [rbx+18h]
0x18001dfc3  add     [rcx+8], eax
0x18001dfc6  mov     rax, [rdx+150h]
0x18001dfcd  inc     dword ptr [rax+20h]
0x18001dfd0  mov     rcx, [rdi+8]
0x18001dfd4  sub     rcx, [rdi]
0x18001dfd7  mov     eax, [rdx+68h]
0x18001dfda  sar     rcx, 5
0x18001dfde  cmp     rcx, rax
0x18001dfe1  jnz     short loc_18001DFEB
0x18001dfe3  mov     rcx, rdx; this
0x18001dfe6  call    ?FlushCachedRegionsToStorage@CompressedMemStream@CompressedStreamDump@@AEAA_NXZ; CompressedStreamDump::CompressedMemStream::FlushCachedRegionsToStorage(void)
0x18001dfeb  mov     rdx, [rdi+8]
0x18001dfef  cmp     rdx, [rdi+10h]
0x18001dff3  jz      short loc_18001E00A
0x18001dff5  movups  xmm0, xmmword ptr [rbx]
0x18001dff8  movups  xmmword ptr [rdx], xmm0
0x18001dffb  movups  xmm1, xmmword ptr [rbx+10h]
0x18001dfff  movups  xmmword ptr [rdx+10h], xmm1
0x18001e003  add     qword ptr [rdi+8], 20h ; ' '
0x18001e008  jmp     short loc_18001E015
0x18001e00a  mov     r8, rbx
0x18001e00d  mov     rcx, rdi
0x18001e010  call    ??$_Emplace_reallocate@AEBUMemoryRegion@@@?$vector@UMemoryRegion@@V?$allocator@UMemoryRegion@@@std@@@std@@AEAAPEAUMemoryRegion@@QEAU2@AEBU2@@Z; std::vector<MemoryRegion>::_Emplace_reallocate<MemoryRegion const &>(MemoryRegion * const,MemoryRegion const &)
0x18001e015  mov     rbx, [rsp+28h+arg_0]
0x18001e01a  add     rsp, 20h
0x18001e01e  pop     rdi
0x18001e01f  retn
```
