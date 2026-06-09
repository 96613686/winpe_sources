# CContextMap::DeleteContext(ulong)

- ea: `0x180013640`
- end: `0x1800136d5`
- name: `?DeleteContext@CContextMap@@QEAAXK@Z`
- size: `149`
- prototype: `void(CContextMap *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180017c30`

## callees

- `0x180013640`
- `0x1800136dc`
- `0x180013bbc`
- `0x1800145dc`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800136c3`
- `KERNEL32!LeaveCriticalSection` at `0x1800136c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CContextMap::DeleteContext(CContextMap *this, unsigned int a2)
{
  CContextMap *v3; // rcx
  struct CContextMap::ContextEntry *Context; // rax
  CContextMap *v5; // rcx
  int v6; // eax
  int v7; // edx

  CCriticalSection::Lock((CCriticalSection *)&CriticalSection);
  Context = CContextMap::FindContext(v3, a2);
  *(_QWORD *)Context = 0;
  ++*((_BYTE *)Context + 8);
  --dword_18003D260;
  if ( a2 >> 8 == *(&g_map_RT_SecCtx + 1) )
  {
    v6 = *(&g_map_RT_SecCtx + 1) - 1;
    *(&g_map_RT_SecCtx + 1) = v6;
    if ( v6 )
    {
      v7 = v6;
      do
      {
        v5 = (CContextMap *)(2LL * (unsigned int)(v6 - 1));
        if ( *((_QWORD *)Src + 2 * (unsigned int)(v6 - 1)) )
          break;
        v6 = v7 - 1;
        *(&g_map_RT_SecCtx + 1) = v6;
        --v7;
      }
      while ( v6 );
    }
  }
  CContextMap::Shrink(v5);
  LeaveCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x180013640  mov     [rsp+arg_8], rbx
0x180013645  mov     [rsp+arg_0], rcx
0x18001364a  push    rdi
0x18001364b  sub     rsp, 20h
0x18001364f  mov     ebx, edx
0x180013651  lea     rdi, CriticalSection
0x180013658  mov     [rsp+28h+arg_0], rdi
0x18001365d  mov     rcx, rdi; this
0x180013660  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x180013665  nop
0x180013666  mov     edx, ebx; unsigned int
0x180013668  call    ?FindContext@CContextMap@@IEAAPEAUContextEntry@1@K@Z; CContextMap::FindContext(ulong)
0x18001366d  mov     qword ptr [rax], 0
0x180013674  inc     byte ptr [rax+8]
0x180013677  dec     cs:dword_18003D260
0x18001367d  mov     eax, dword ptr cs:?g_map_RT_SecCtx@@3VCContextMap@@A+4; CContextMap g_map_RT_SecCtx
0x180013683  shr     ebx, 8
0x180013686  cmp     ebx, eax
0x180013688  jnz     short loc_1800136BA
0x18001368a  sub     eax, 1
0x18001368d  mov     dword ptr cs:?g_map_RT_SecCtx@@3VCContextMap@@A+4, eax; CContextMap g_map_RT_SecCtx
0x180013693  jz      short loc_1800136BA
0x180013695  mov     edx, eax
0x180013697  mov     r8, cs:Src
0x18001369e  lea     ecx, [rax-1]
0x1800136a1  add     rcx, rcx; this
0x1800136a4  cmp     qword ptr [r8+rcx*8], 0
0x1800136a9  jnz     short loc_1800136BA
0x1800136ab  lea     eax, [rdx-1]
0x1800136ae  mov     dword ptr cs:?g_map_RT_SecCtx@@3VCContextMap@@A+4, eax; CContextMap g_map_RT_SecCtx
0x1800136b4  mov     edx, eax
0x1800136b6  test    eax, eax
0x1800136b8  jnz     short loc_18001369E
0x1800136ba  call    ?Shrink@CContextMap@@IEAAXXZ; CContextMap::Shrink(void)
0x1800136bf  nop
0x1800136c0  mov     rcx, rdi; lpCriticalSection
0x1800136c3  call    cs:__imp_LeaveCriticalSection
0x1800136c9  nop
0x1800136ca  mov     rbx, [rsp+28h+arg_8]
0x1800136cf  add     rsp, 20h
0x1800136d3  pop     rdi
0x1800136d4  retn
```
