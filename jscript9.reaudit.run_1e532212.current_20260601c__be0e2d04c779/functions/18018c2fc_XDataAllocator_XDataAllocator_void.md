# XDataAllocator::~XDataAllocator(void)

- ea: `0x18018c2fc`
- end: `0x18018c432`
- name: `??1XDataAllocator@@UEAA@XZ`
- size: `310`
- prototype: `void __fastcall(XDataAllocator *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180255a00`

## callees

- `0x1801201d0`
- `0x180120294`
- `0x18018c2fc`
- `0x18018c438`
- `0x1801aa3a4`

## import_xrefs

- `msvcrt!free` at `0x18018c39f`
- `msvcrt!free` at `0x18018c39f`
- `KERNEL32!RtlDeleteFunctionTable` at `0x18018c37d`
- `KERNEL32!RtlDeleteFunctionTable` at `0x18018c37d`

## pseudocode

```c
void __fastcall XDataAllocator::~XDataAllocator(XDataAllocator *this)
{
  __int64 v2; // rcx
  __int64 v3; // rsi
  unsigned __int16 i; // di
  struct _RUNTIME_FUNCTION *v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rsi
  unsigned __int16 j; // di
  void *v9; // rdx

  *(_QWORD *)this = &XDataAllocator::`vftable';
  if ( *((_QWORD *)this + 5) )
  {
    if ( !AutoSystemInfo::IsWin8OrLater(this) )
    {
      v3 = (*(_QWORD *)(v2 + 16) - *((_QWORD *)this + 1)) / 72LL;
      for ( i = 0; i < (unsigned __int16)v3; ++i )
      {
        v5 = (struct _RUNTIME_FUNCTION *)(*((_QWORD *)this + 5) + 12LL * i);
        if ( v5->UnwindData )
          RtlDeleteFunctionTable(v5);
      }
    }
    if ( (unsigned __int16)(*((_DWORD *)this + 6) / 0x48u) )
      free(*((void **)this + 5));
    *((_QWORD *)this + 5) = 0;
  }
  if ( *((_QWORD *)this + 6) )
  {
    v6 = *((_QWORD *)this + 2) - *((_QWORD *)this + 1);
    v7 = v6 / 72;
    for ( j = 0; j < (unsigned __int16)v7; ++j )
    {
      v6 = *((_QWORD *)this + 6);
      v9 = *(void **)(v6 + 8LL * j);
      if ( v9 )
        NtdllLibrary::DeleteGrowableFunctionTable((NtdllLibrary *)v6, v9);
    }
    DeleteArray<HeapAllocator,unsigned short const *>(
      v6,
      (unsigned __int16)(*((_DWORD *)this + 6) / 0x48u),
      *((_QWORD *)this + 6));
    *((_QWORD *)this + 6) = 0;
  }
  XDataAllocator::ClearFreeList(this);
  *(_QWORD *)this = &SecondaryAllocator::`vftable';
}

```

## disassembly

```asm
0x18018c2fc  mov     r11, rsp
0x18018c2ff  mov     [r11+8], rcx
0x18018c303  push    rsi
0x18018c304  push    rdi
0x18018c305  push    r15
0x18018c307  sub     rsp, 30h
0x18018c30b  mov     qword ptr [r11-28h], 0FFFFFFFFFFFFFFFEh
0x18018c313  mov     [r11+10h], rbx
0x18018c317  mov     [r11+18h], rbp
0x18018c31b  lea     rax, ??_7XDataAllocator@@6B@; const XDataAllocator::`vftable'
0x18018c322  mov     rbx, rcx
0x18018c325  mov     [rcx], rax
0x18018c328  xor     ebp, ebp
0x18018c32a  mov     r15, 0E38E38E38E38E39h
0x18018c334  cmp     [rcx+28h], rbp
0x18018c338  jz      short loc_18018C3A9
0x18018c33a  call    ?IsWin8OrLater@AutoSystemInfo@@QEAA_NXZ; AutoSystemInfo::IsWin8OrLater(void)
0x18018c33f  test    al, al
0x18018c341  jnz     short loc_18018C38B
0x18018c343  mov     rcx, [rcx+10h]
0x18018c347  sub     rcx, [rbx+8]
0x18018c34b  mov     rax, r15
0x18018c34e  imul    rcx
0x18018c351  mov     rsi, rdx
0x18018c354  sar     rsi, 2
0x18018c358  mov     rax, rsi
0x18018c35b  shr     rax, 3Fh
0x18018c35f  add     rsi, rax
0x18018c362  mov     edi, ebp
0x18018c364  cmp     bp, si
0x18018c367  jnb     short loc_18018C38B
0x18018c369  movzx   eax, di
0x18018c36c  lea     rcx, [rax+rax*2]
0x18018c370  mov     rax, [rbx+28h]
0x18018c374  lea     rcx, [rax+rcx*4]; FunctionTable
0x18018c378  cmp     [rcx+8], ebp
0x18018c37b  jz      short loc_18018C383
0x18018c37d  call    cs:__imp_RtlDeleteFunctionTable
0x18018c383  inc     di
0x18018c386  cmp     di, si
0x18018c389  jb      short loc_18018C369
0x18018c38b  mov     eax, 38E38E39h
0x18018c390  mul     dword ptr [rbx+18h]
0x18018c393  shr     edx, 4
0x18018c396  test    dx, dx
0x18018c399  jz      short loc_18018C3A5
0x18018c39b  mov     rcx, [rbx+28h]; Block
0x18018c39f  call    cs:__imp_free
0x18018c3a5  mov     [rbx+28h], rbp
0x18018c3a9  cmp     [rbx+30h], rbp
0x18018c3ad  jz      short loc_18018C40D
0x18018c3af  mov     rcx, [rbx+10h]
0x18018c3b3  sub     rcx, [rbx+8]
0x18018c3b7  mov     rax, r15
0x18018c3ba  imul    rcx
0x18018c3bd  mov     rsi, rdx
0x18018c3c0  sar     rsi, 2
0x18018c3c4  mov     rax, rsi
0x18018c3c7  shr     rax, 3Fh
0x18018c3cb  add     rsi, rax
0x18018c3ce  mov     edi, ebp
0x18018c3d0  cmp     bp, si
0x18018c3d3  jnb     short loc_18018C3F2
0x18018c3d5  movzx   edx, di
0x18018c3d8  mov     rcx, [rbx+30h]; this
0x18018c3dc  mov     rdx, [rcx+rdx*8]; void *
0x18018c3e0  test    rdx, rdx
0x18018c3e3  jz      short loc_18018C3EA
0x18018c3e5  call    ?DeleteGrowableFunctionTable@NtdllLibrary@@QEAAXPEAX@Z; NtdllLibrary::DeleteGrowableFunctionTable(void *)
0x18018c3ea  inc     di
0x18018c3ed  cmp     di, si
0x18018c3f0  jb      short loc_18018C3D5
0x18018c3f2  mov     eax, 38E38E39h
0x18018c3f7  mul     dword ptr [rbx+18h]
0x18018c3fa  shr     edx, 4
0x18018c3fd  movzx   edx, dx
0x18018c400  mov     r8, [rbx+30h]
0x18018c404  call    ??$DeleteArray@UHeapAllocator@@PEBG@@YAXPEAUHeapAllocator@@_KPEAPEBG@Z; DeleteArray<HeapAllocator,ushort const *>(HeapAllocator *,unsigned __int64,ushort const * *)
0x18018c409  mov     [rbx+30h], rbp
0x18018c40d  mov     rcx, rbx; this
0x18018c410  call    ?ClearFreeList@XDataAllocator@@AEAAXXZ; XDataAllocator::ClearFreeList(void)
0x18018c415  lea     rax, ??_7SecondaryAllocator@@6B@; const SecondaryAllocator::`vftable'
0x18018c41c  mov     [rbx], rax
0x18018c41f  mov     rbx, [rsp+48h+arg_8]
0x18018c424  mov     rbp, [rsp+48h+arg_10]
0x18018c429  add     rsp, 30h
0x18018c42d  pop     r15
0x18018c42f  pop     rdi
0x18018c430  pop     rsi
0x18018c431  retn
```
