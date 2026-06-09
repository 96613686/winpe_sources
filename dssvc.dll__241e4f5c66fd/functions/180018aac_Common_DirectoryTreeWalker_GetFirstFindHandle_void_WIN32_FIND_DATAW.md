# Common::DirectoryTreeWalker::GetFirstFindHandle(void * *,_WIN32_FIND_DATAW * *)

- ea: `0x180018aac`
- end: `0x180018b88`
- name: `?GetFirstFindHandle@DirectoryTreeWalker@Common@@AEAAJPEAPEAXPEAPEAU_WIN32_FIND_DATAW@@@Z`
- size: `220`
- prototype: `__int64 __fastcall(Common::DirectoryTreeWalker *__hidden this, void **, struct _WIN32_FIND_DATAW **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180018ffc`

## callees

- `0x18000be00`
- `0x18000be3c`
- `0x180018aac`
- `0x180018dd8`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall Common::DirectoryTreeWalker::GetFirstFindHandle(
        Common::DirectoryTreeWalker *this,
        void **a2,
        struct _WIN32_FIND_DATAW **a3)
{
  unsigned int v7; // esi
  struct _WIN32_FIND_DATAW *v8; // rbx
  PVOID P; // [rsp+50h] [rbp+8h] BYREF
  __int64 v10; // [rsp+68h] [rbp+20h] BYREF

  if ( (unsigned __int64)(*((_QWORD *)this + 2) + 2LL) > 0x7FFF )
    return 206;
  RtlStringCchCatW(*((unsigned __int16 **)this + 1), (unsigned __int64)a2, L"\\*");
  *((_QWORD *)this + 2) += 2LL;
  v10 = -1;
  v7 = 14;
  P = 0;
  Common::GlobalHeap::Alloc((ReservedForLocalUse *)0x250, &P);
  v8 = (struct _WIN32_FIND_DATAW *)P;
  if ( P )
    v7 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *, PVOID))this + 7))(
           *((_QWORD *)this + 6),
           *((_QWORD *)this + 1),
           &v10,
           P);
  *((_QWORD *)this + 2) -= 2LL;
  *(_WORD *)(*((_QWORD *)this + 1) + 2LL * *((_QWORD *)this + 2)) = 0;
  if ( !v7 )
  {
    *a2 = (void *)v10;
    *a3 = v8;
    v8 = 0;
  }
  Common::GlobalHeap::Free(v8);
  return v7;
}

```

## disassembly

```asm
0x180018aac  mov     [rsp+arg_8], rbx
0x180018ab1  mov     [rsp+arg_10], rsi
0x180018ab6  push    rdi
0x180018ab7  push    r14
0x180018ab9  push    r15
0x180018abb  sub     rsp, 30h
0x180018abf  mov     rax, [rcx+10h]
0x180018ac3  mov     r14, r8
0x180018ac6  add     rax, 2
0x180018aca  mov     r15, rdx
0x180018acd  mov     rdi, rcx
0x180018ad0  cmp     rax, 7FFFh
0x180018ad6  jbe     short loc_180018AE2
0x180018ad8  mov     eax, 0CEh
0x180018add  jmp     loc_180018B74
0x180018ae2  mov     rcx, [rcx+8]; unsigned __int16 *
0x180018ae6  lea     r8, asc_180023998; "\\*"
0x180018aed  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180018af2  add     qword ptr [rdi+10h], 2
0x180018af7  lea     rdx, [rsp+48h+P]; void **
0x180018afc  mov     ecx, 250h; unsigned __int64
0x180018b01  mov     [rsp+48h+arg_18], 0FFFFFFFFFFFFFFFFh
0x180018b0a  mov     esi, 0Eh
0x180018b0f  mov     [rsp+48h+P], 0
0x180018b18  call    ?Alloc@GlobalHeap@Common@@SAJ_KPEAPEAX@Z; Common::GlobalHeap::Alloc(unsigned __int64,void * *)
0x180018b1d  mov     rbx, [rsp+48h+P]
0x180018b22  test    rbx, rbx
0x180018b25  jz      short loc_180018B42
0x180018b27  mov     rdx, [rdi+8]
0x180018b2b  lea     r8, [rsp+48h+arg_18]
0x180018b30  mov     rcx, [rdi+30h]
0x180018b34  mov     r9, rbx
0x180018b37  mov     rax, [rdi+38h]
0x180018b3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b40  mov     esi, eax
0x180018b42  add     qword ptr [rdi+10h], 0FFFFFFFFFFFFFFFEh
0x180018b47  xor     ecx, ecx
0x180018b49  mov     r8, [rdi+10h]
0x180018b4d  mov     rdx, [rdi+8]
0x180018b51  mov     [rdx+r8*2], cx
0x180018b56  test    esi, esi
0x180018b58  jnz     short loc_180018B6A
0x180018b5a  mov     rcx, [rsp+48h+arg_18]
0x180018b5f  mov     [r15], rcx
0x180018b62  mov     rcx, rbx
0x180018b65  mov     [r14], rcx
0x180018b68  xor     ebx, ebx
0x180018b6a  mov     rcx, rbx; P
0x180018b6d  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180018b72  mov     eax, esi
0x180018b74  mov     rbx, [rsp+48h+arg_8]
0x180018b79  mov     rsi, [rsp+48h+arg_10]
0x180018b7e  add     rsp, 30h
0x180018b82  pop     r15
0x180018b84  pop     r14
0x180018b86  pop     rdi
0x180018b87  retn
```
