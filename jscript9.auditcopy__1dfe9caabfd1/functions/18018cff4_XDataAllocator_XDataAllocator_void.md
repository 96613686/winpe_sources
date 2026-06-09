# XDataAllocator::~XDataAllocator(void)

- ea: `0x18018cff4`
- end: `0x18018d137`
- name: `??1XDataAllocator@@UEAA@XZ`
- size: `323`
- prototype: `void __fastcall(XDataAllocator *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18025a1c0`

## callees

- `0x18012860c`
- `0x1801286d4`
- `0x18018cff4`
- `0x18018d140`
- `0x1801ac2f8`

## import_xrefs

- `msvcrt!free` at `0x18018d09d`
- `msvcrt!free` at `0x18018d09d`
- `KERNEL32!RtlDeleteFunctionTable` at `0x18018d075`
- `KERNEL32!RtlDeleteFunctionTable` at `0x18018d075`

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
      *((void **)this + 6));
    *((_QWORD *)this + 6) = 0;
  }
  XDataAllocator::ClearFreeList(this);
  *(_QWORD *)this = &SecondaryAllocator::`vftable';
}

```

## disassembly

```asm
0x18018cff4  mov     r11, rsp
0x18018cff7  mov     [r11+8], rcx
0x18018cffb  push    rsi
0x18018cffc  push    rdi
0x18018cffd  push    r15
0x18018cfff  sub     rsp, 30h
0x18018d003  mov     qword ptr [r11-28h], 0FFFFFFFFFFFFFFFEh
0x18018d00b  mov     [r11+10h], rbx
0x18018d00f  mov     [r11+18h], rbp
0x18018d013  lea     rax, ??_7XDataAllocator@@6B@; const XDataAllocator::`vftable'
0x18018d01a  mov     rbx, rcx
0x18018d01d  mov     [rcx], rax
0x18018d020  xor     ebp, ebp
0x18018d022  mov     r15, 0E38E38E38E38E39h
0x18018d02c  cmp     [rcx+28h], rbp
0x18018d030  jz      short loc_18018D0AD
0x18018d032  call    ?IsWin8OrLater@AutoSystemInfo@@QEAA_NXZ; AutoSystemInfo::IsWin8OrLater(void)
0x18018d037  test    al, al
0x18018d039  jnz     short loc_18018D089
0x18018d03b  mov     rcx, [rcx+10h]
0x18018d03f  sub     rcx, [rbx+8]
0x18018d043  mov     rax, r15
0x18018d046  imul    rcx
0x18018d049  mov     rsi, rdx
0x18018d04c  sar     rsi, 2
0x18018d050  mov     rax, rsi
0x18018d053  shr     rax, 3Fh
0x18018d057  add     rsi, rax
0x18018d05a  mov     edi, ebp
0x18018d05c  cmp     bp, si
0x18018d05f  jnb     short loc_18018D089
0x18018d061  movzx   eax, di
0x18018d064  lea     rcx, [rax+rax*2]
0x18018d068  mov     rax, [rbx+28h]
0x18018d06c  lea     rcx, [rax+rcx*4]; FunctionTable
0x18018d070  cmp     [rcx+8], ebp
0x18018d073  jz      short loc_18018D081
0x18018d075  call    cs:__imp_RtlDeleteFunctionTable
0x18018d07c  nop     dword ptr [rax+rax+00h]
0x18018d081  inc     di
0x18018d084  cmp     di, si
0x18018d087  jb      short loc_18018D061
0x18018d089  mov     eax, 38E38E39h
0x18018d08e  mul     dword ptr [rbx+18h]
0x18018d091  shr     edx, 4
0x18018d094  test    dx, dx
0x18018d097  jz      short loc_18018D0A9
0x18018d099  mov     rcx, [rbx+28h]; Block
0x18018d09d  call    cs:__imp_free
0x18018d0a4  nop     dword ptr [rax+rax+00h]
0x18018d0a9  mov     [rbx+28h], rbp
0x18018d0ad  cmp     [rbx+30h], rbp
0x18018d0b1  jz      short loc_18018D111
0x18018d0b3  mov     rcx, [rbx+10h]
0x18018d0b7  sub     rcx, [rbx+8]
0x18018d0bb  mov     rax, r15
0x18018d0be  imul    rcx
0x18018d0c1  mov     rsi, rdx
0x18018d0c4  sar     rsi, 2
0x18018d0c8  mov     rax, rsi
0x18018d0cb  shr     rax, 3Fh
0x18018d0cf  add     rsi, rax
0x18018d0d2  mov     edi, ebp
0x18018d0d4  cmp     bp, si
0x18018d0d7  jnb     short loc_18018D0F6
0x18018d0d9  movzx   edx, di
0x18018d0dc  mov     rcx, [rbx+30h]; this
0x18018d0e0  mov     rdx, [rcx+rdx*8]; void *
0x18018d0e4  test    rdx, rdx
0x18018d0e7  jz      short loc_18018D0EE
0x18018d0e9  call    ?DeleteGrowableFunctionTable@NtdllLibrary@@QEAAXPEAX@Z; NtdllLibrary::DeleteGrowableFunctionTable(void *)
0x18018d0ee  inc     di
0x18018d0f1  cmp     di, si
0x18018d0f4  jb      short loc_18018D0D9
0x18018d0f6  mov     eax, 38E38E39h
0x18018d0fb  mul     dword ptr [rbx+18h]
0x18018d0fe  shr     edx, 4
0x18018d101  movzx   edx, dx
0x18018d104  mov     r8, [rbx+30h]
0x18018d108  call    ??$DeleteArray@UHeapAllocator@@PEBG@@YAXPEAUHeapAllocator@@_KPEAPEBG@Z; DeleteArray<HeapAllocator,ushort const *>(HeapAllocator *,unsigned __int64,ushort const * *)
0x18018d10d  mov     [rbx+30h], rbp
0x18018d111  mov     rcx, rbx; this
0x18018d114  call    ?ClearFreeList@XDataAllocator@@AEAAXXZ; XDataAllocator::ClearFreeList(void)
0x18018d119  lea     rax, ??_7SecondaryAllocator@@6B@; const SecondaryAllocator::`vftable'
0x18018d120  mov     [rbx], rax
0x18018d123  mov     rbx, [rsp+48h+arg_8]
0x18018d128  mov     rbp, [rsp+48h+arg_10]
0x18018d12d  add     rsp, 30h
0x18018d131  pop     r15
0x18018d133  pop     rdi
0x18018d134  pop     rsi
0x18018d135  retn
```
