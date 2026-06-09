# CClfsRequest::GetArchivalDescriptors(void)

- ea: `0x14004116c`
- end: `0x1400412d7`
- name: `?GetArchivalDescriptors@CClfsRequest@@AEAAJXZ`
- size: `363`
- prototype: `__int64 __fastcall(CClfsRequest *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14006c874`

## callees

- `0x14000c2f0`
- `0x14000d084`
- `0x14004116c`
- `0x140045f54`
- `0x140059e80`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140041299`
- `ntoskrnl!KeSetEvent` at `0x14007eb25`
- `ntoskrnl!KeSetEvent` at `0x140041299`
- `ntoskrnl!KeSetEvent` at `0x14007eb25`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140041245`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140041245`

## pseudocode

```c
__int64 __fastcall CClfsRequest::GetArchivalDescriptors(CClfsRequest *this)
{
  CClfsLogCcb *v2; // rsi
  __int64 v3; // r9
  unsigned int ArchiveDescriptors; // ebx
  __int64 v5; // rbx
  __int64 v6; // r9
  __int64 v7; // r10
  unsigned int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rcx
  struct _CLS_ARCHIVE_DESCRIPTOR *v11; // rax
  struct _KEVENT *v12; // rcx
  unsigned int v14; // [rsp+68h] [rbp+10h] BYREF
  unsigned int v15; // [rsp+70h] [rbp+18h] BYREF

  v2 = 0;
  v15 = 0;
  v14 = 0;
  v3 = *((_QWORD *)this + 6);
  if ( *(_DWORD *)(*(_QWORD *)(v3 + 184) + 16LL) >= 4u )
  {
    v5 = **(unsigned int **)(v3 + 24);
    if ( (int)RtlULongLongToULong(592 * v5, &v14) >= 0 )
    {
      if ( *(_QWORD *)(v6 + 8) && (v8 = *(_DWORD *)(v7 + 8)) != 0 && v14 <= v8 )
      {
        v14 = *(_DWORD *)(v7 + 8);
        v2 = *(CClfsLogCcb **)(*(_QWORD *)(v7 + 48) + 32LL);
        CClfsLogCcb::AddRef(v2);
        v9 = *((_QWORD *)this + 6);
        if ( (*(_BYTE *)(v9 + 112) & 3) != 0 )
        {
          ArchiveDescriptors = -1073741592;
        }
        else
        {
          v10 = *(_QWORD *)(v9 + 8);
          if ( (*(_BYTE *)(v10 + 10) & 5) != 0 )
            v11 = *(struct _CLS_ARCHIVE_DESCRIPTOR **)(v10 + 24);
          else
            v11 = (struct _CLS_ARCHIVE_DESCRIPTOR *)MmMapLockedPagesSpecifyCache(
                                                      (PMDL)v10,
                                                      0,
                                                      MmCached,
                                                      0,
                                                      0,
                                                      0x40000010u);
          if ( v11 )
            ArchiveDescriptors = CClfsLogCcb::GetArchiveDescriptors(v2, v11, v5, &v15);
          else
            ArchiveDescriptors = -1073741670;
        }
      }
      else
      {
        ArchiveDescriptors = -1073741789;
      }
    }
    else
    {
      ArchiveDescriptors = -1073741811;
    }
  }
  else
  {
    ArchiveDescriptors = -1073741306;
  }
  if ( (*((_BYTE *)this + 16) & 1) != 0 )
  {
    v12 = *(struct _KEVENT **)(*((_QWORD *)this + 6) + 80LL);
    if ( v12 )
      KeSetEvent(v12, 0, 0);
  }
  if ( (*((_DWORD *)this + 4) & 4) == 0 )
  {
    *(_DWORD *)(*((_QWORD *)this + 6) + 48LL) = ArchiveDescriptors;
    *(_QWORD *)(*((_QWORD *)this + 6) + 56LL) = v15;
  }
  if ( v2 )
    CClfsLogCcb::Release(v2);
  return ArchiveDescriptors;
}

```

## disassembly

```asm
0x14004116c  mov     rax, rsp
0x14004116f  mov     [rax+8], rcx
0x140041173  push    rbx
0x140041174  push    rsi
0x140041175  push    rdi
0x140041176  sub     rsp, 40h
0x14004117a  mov     rdi, rcx
0x14004117d  xor     esi, esi
0x14004117f  mov     [rax-20h], rsi
0x140041183  mov     [rax-28h], esi
0x140041186  mov     [rax+18h], esi
0x140041189  mov     [rax+10h], esi
0x14004118c  mov     r9, [rcx+30h]
0x140041190  mov     r10, [r9+0B8h]
0x140041197  cmp     dword ptr [r10+10h], 4
0x14004119c  jnb     short loc_1400411A8
0x14004119e  mov     ebx, 0C0000206h
0x1400411a3  jmp     loc_14004127D
0x1400411a8  mov     rax, [r9+18h]
0x1400411ac  mov     ebx, [rax]
0x1400411ae  imul    rcx, rbx, 250h; unsigned __int64
0x1400411b5  lea     rdx, [rsp+58h+arg_8]; unsigned int *
0x1400411ba  call    ?RtlULongLongToULong@@YAJ_KPEAK@Z; RtlULongLongToULong(unsigned __int64,ulong *)
0x1400411bf  mov     [rsp+58h+var_28], eax
0x1400411c3  test    eax, eax
0x1400411c5  jns     short loc_1400411D1
0x1400411c7  mov     ebx, 0C000000Dh
0x1400411cc  jmp     loc_14004127D
0x1400411d1  cmp     qword ptr [r9+8], 0
0x1400411d6  jz      loc_140041278
0x1400411dc  mov     eax, [r10+8]
0x1400411e0  test    eax, eax
0x1400411e2  jz      loc_140041278
0x1400411e8  cmp     [rsp+58h+arg_8], eax
0x1400411ec  ja      loc_140041278
0x1400411f2  mov     [rsp+58h+arg_8], eax
0x1400411f6  mov     rax, [r10+30h]
0x1400411fa  mov     rsi, [rax+20h]
0x1400411fe  mov     [rsp+58h+var_20], rsi
0x140041203  mov     rcx, rsi; this
0x140041206  call    ?AddRef@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::AddRef(void)
0x14004120b  mov     rcx, [rdi+30h]
0x14004120f  test    byte ptr [rcx+70h], 3
0x140041213  jz      short loc_14004121C
0x140041215  mov     ebx, 0C00000E8h
0x14004121a  jmp     short loc_14004127D
0x14004121c  mov     rcx, [rcx+8]; MemoryDescriptorList
0x140041220  test    byte ptr [rcx+0Ah], 5
0x140041224  jz      short loc_14004122C
0x140041226  mov     rax, [rcx+18h]
0x14004122a  jmp     short loc_140041251
0x14004122c  mov     [rsp+58h+Priority], 40000010h; Priority
0x140041234  mov     [rsp+58h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14004123c  xor     r9d, r9d; RequestedAddress
0x14004123f  xor     edx, edx; AccessMode
0x140041241  lea     r8d, [r9+1]; CacheType
0x140041245  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004124c  nop     dword ptr [rax+rax+00h]
0x140041251  test    rax, rax
0x140041254  jnz     short loc_14004125D
0x140041256  mov     ebx, 0C000009Ah
0x14004125b  jmp     short loc_14004127D
0x14004125d  lea     r9, [rsp+58h+arg_10]; unsigned int *
0x140041262  mov     r8d, ebx; unsigned int
0x140041265  mov     rdx, rax; struct _CLS_ARCHIVE_DESCRIPTOR *
0x140041268  mov     rcx, rsi; this
0x14004126b  call    ?GetArchiveDescriptors@CClfsLogCcb@@QEAAJQEAU_CLS_ARCHIVE_DESCRIPTOR@@KAEAK@Z; CClfsLogCcb::GetArchiveDescriptors(_CLS_ARCHIVE_DESCRIPTOR * const,ulong,ulong &)
0x140041270  mov     ebx, eax
0x140041272  mov     [rsp+58h+var_28], eax
0x140041276  jmp     short loc_140041281
0x140041278  mov     ebx, 0C0000023h
0x14004127d  mov     [rsp+58h+var_28], ebx
0x140041281  test    byte ptr [rdi+10h], 1
0x140041285  jz      short loc_1400412A5
0x140041287  mov     rax, [rdi+30h]
0x14004128b  mov     rcx, [rax+50h]; Event
0x14004128f  test    rcx, rcx
0x140041292  jz      short loc_1400412A5
0x140041294  xor     r8d, r8d; Wait
0x140041297  xor     edx, edx; Increment
0x140041299  call    cs:__imp_KeSetEvent
0x1400412a0  nop     dword ptr [rax+rax+00h]
0x1400412a5  mov     eax, [rdi+10h]
0x1400412a8  test    al, 4
0x1400412aa  jnz     short loc_1400412BF
0x1400412ac  mov     rax, [rdi+30h]
0x1400412b0  mov     [rax+30h], ebx
0x1400412b3  mov     edx, [rsp+58h+arg_10]
0x1400412b7  mov     rax, [rdi+30h]
0x1400412bb  mov     [rax+38h], rdx
0x1400412bf  test    rsi, rsi
0x1400412c2  jz      short loc_1400412CC
0x1400412c4  mov     rcx, rsi; Entry
0x1400412c7  call    ?Release@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::Release(void)
0x1400412cc  mov     eax, ebx
0x1400412ce  add     rsp, 40h
0x1400412d2  pop     rdi
0x1400412d3  pop     rsi
0x1400412d4  pop     rbx
0x1400412d5  retn
0x14007eaee  push    rbx
0x14007eaf0  push    rbp
0x14007eaf1  sub     rsp, 38h
0x14007eaf5  mov     rbp, rdx
0x14007eaf8  xor     cl, cl
0x14007eafa  mov     rbx, [rbp+60h]
0x14007eafe  test    byte ptr [rbx+10h], 1
0x14007eb02  movzx   eax, cl
0x14007eb05  mov     ecx, 1
0x14007eb0a  cmovnz  eax, ecx
0x14007eb0d  test    al, al
0x14007eb0f  jz      short loc_14007EB32
0x14007eb11  mov     rax, [rbx+30h]
0x14007eb15  cmp     qword ptr [rax+50h], 0
0x14007eb1a  jz      short loc_14007EB32
0x14007eb1c  xor     r8d, r8d; Wait
0x14007eb1f  xor     edx, edx; Increment
0x14007eb21  mov     rcx, [rax+50h]; Event
0x14007eb25  call    cs:__imp_KeSetEvent
0x14007eb2c  nop     dword ptr [rax+rax+00h]
0x14007eb31  nop
0x14007eb32  xor     cl, cl
0x14007eb34  test    byte ptr [rbx+10h], 4
0x14007eb38  movzx   eax, cl
0x14007eb3b  mov     ecx, 1
0x14007eb40  cmovnz  eax, ecx
0x14007eb43  test    al, al
0x14007eb45  jnz     short loc_14007EB5C
0x14007eb47  mov     rcx, [rbx+30h]
0x14007eb4b  mov     eax, [rbp+30h]
0x14007eb4e  mov     [rcx+30h], eax
0x14007eb51  mov     ecx, [rbp+70h]
0x14007eb54  mov     rax, [rbx+30h]
0x14007eb58  mov     [rax+38h], rcx
0x14007eb5c  mov     rcx, [rbp+38h]; Entry
0x14007eb60  test    rcx, rcx
0x14007eb63  jz      short loc_14007EB72
0x14007eb65  call    ?Release@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::Release(void)
0x14007eb6a  mov     qword ptr [rbp+38h], 0
0x14007eb72  add     rsp, 38h
0x14007eb76  pop     rbp
0x14007eb77  pop     rbx
0x14007eb78  retn
```
