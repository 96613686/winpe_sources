# SString::Replace(SString::Iterator const &,uint,SString const &)

- ea: `0x14000b578`
- end: `0x14000b6e7`
- name: `?Replace@SString@@QEAAXAEBVIterator@1@IAEBV1@@Z`
- size: `367`
- prototype: `void __fastcall(SString *this, const struct SString::Iterator *, int, const struct SString *)`
- caller_count: `4`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140001214`
- `0x140002168`
- `0x140006188`
- `0x140006a5c`

## callees

- `0x140001100`
- `0x14000b010`
- `0x14000b578`
- `0x14000c3d4`
- `0x14000c51c`
- `0x140010354`
- `0x140013200`
- `0x140013f0a`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000b6c0`
- `KERNEL32!HeapFree` at `0x14000b6c0`
- `KERNEL32!GetProcessHeap` at `0x14000b6ab`
- `KERNEL32!GetProcessHeap` at `0x14000b6ab`

## pseudocode

```c
void __fastcall SString::Replace(SString *this, const struct SString::Iterator *a2, int a3, const struct SString *a4)
{
  unsigned int v8; // ecx
  const struct SString *CompatibleString; // rbx
  char v10; // cl
  unsigned int v11; // r15d
  void *v12; // rbx
  HANDLE ProcessHeap; // rax
  int v14; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v15; // [rsp+24h] [rbp-DCh]
  LPVOID lpMem; // [rsp+30h] [rbp-D0h]
  __int16 v17; // [rsp+38h] [rbp-C8h] BYREF

  if ( (*((_BYTE *)this + 8) & 7) != 0 )
  {
    v15 = 512;
    lpMem = &v17;
    v14 = 2;
    v17 = 0;
    CompatibleString = SString::GetCompatibleString(this, a4, (struct SString *)&v14, a2);
    v10 = (*((_DWORD *)CompatibleString + 2) & 1) == 0;
    v11 = ((*(_DWORD *)CompatibleString >> v10) - 1) << v10;
    SBuffer::Replace(this, a2, a3 << ((*((_DWORD *)this + 2) & 1) == 0), v11);
    if ( v11 )
      memmove_0(*(void **)a2, *((const void **)CompatibleString + 2), v11);
    if ( (v15 & 0x800000000LL) != 0 )
    {
      v12 = lpMem;
      if ( lpMem )
      {
        ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          ProcessHeap = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
        }
        HeapFree(ProcessHeap, 0, v12);
      }
    }
  }
  else
  {
    SBuffer::Set(this, a4);
    v8 = *((_DWORD *)a4 + 2) & 7 | *((_DWORD *)this + 2) & 0xFFFFFEF8;
    *((_DWORD *)this + 2) = v8;
    if ( (~(v8 >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII(this) )
      SString::ConvertToUnicode(this);
    *(_QWORD *)a2 = *((_QWORD *)this + 2);
    *((_DWORD *)a2 + 2) = (*((_DWORD *)this + 2) & 1) == 0;
  }
}

```

## disassembly

```asm
0x14000b578  push    rbp
0x14000b57a  push    rbx
0x14000b57b  push    rsi
0x14000b57c  push    rdi
0x14000b57d  push    r12
0x14000b57f  push    r14
0x14000b581  push    r15
0x14000b583  lea     rbp, [rsp-150h]
0x14000b58b  sub     rsp, 250h
0x14000b592  mov     rax, cs:__security_cookie
0x14000b599  xor     rax, rsp
0x14000b59c  mov     [rbp+180h+var_40], rax
0x14000b5a3  mov     rbx, r9
0x14000b5a6  mov     r12d, r8d
0x14000b5a9  mov     r14, rdx
0x14000b5ac  mov     rdi, rcx
0x14000b5af  test    byte ptr [rcx+8], 7
0x14000b5b3  jnz     short loc_14000B607
0x14000b5b5  mov     rdx, rbx; struct SBuffer *
0x14000b5b8  call    ?Set@SBuffer@@QEAAXAEBV1@@Z; SBuffer::Set(SBuffer const &)
0x14000b5bd  mov     eax, [rbx+8]
0x14000b5c0  and     eax, 7
0x14000b5c3  mov     ecx, [rdi+8]
0x14000b5c6  and     ecx, 0FFFFFFF8h
0x14000b5c9  or      ecx, eax
0x14000b5cb  btr     ecx, 8
0x14000b5cf  mov     [rdi+8], ecx
0x14000b5d2  shr     ecx, 1
0x14000b5d4  not     ecx
0x14000b5d6  test    cl, 1
0x14000b5d9  jnz     short loc_14000B5EF
0x14000b5db  mov     rcx, rdi; this
0x14000b5de  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x14000b5e3  test    eax, eax
0x14000b5e5  jnz     short loc_14000B5EF
0x14000b5e7  mov     rcx, rdi; this
0x14000b5ea  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x14000b5ef  mov     rax, [rdi+10h]
0x14000b5f3  mov     [r14], rax
0x14000b5f6  mov     eax, [rdi+8]
0x14000b5f9  not     eax
0x14000b5fb  and     eax, 1
0x14000b5fe  mov     [r14+8], eax
0x14000b602  jmp     loc_14000B6C6
0x14000b607  xor     esi, esi
0x14000b609  mov     [rsp+280h+var_260], rsi
0x14000b60e  mov     [rsp+280h+var_260+4], 200h
0x14000b617  mov     [rsp+280h+lpMem], rsi
0x14000b61c  lea     rax, [rsp+280h+var_248]
0x14000b621  mov     [rsp+280h+lpMem], rax
0x14000b626  mov     dword ptr [rsp+280h+var_260], 2
0x14000b62e  mov     rax, [rsp+280h+lpMem]
0x14000b633  mov     [rax], si
0x14000b636  mov     r9, r14; struct SString::CIterator *
0x14000b639  lea     r8, [rsp+280h+var_260]; struct SString *
0x14000b63e  mov     rdx, rbx; struct SString *
0x14000b641  call    ?GetCompatibleString@SString@@AEBAAEBV1@AEBV1@AEAV1@AEBVCIterator@1@@Z; SString::GetCompatibleString(SString const &,SString &,SString::CIterator const &)
0x14000b646  mov     rbx, rax
0x14000b649  mov     ecx, [rdi+8]
0x14000b64c  not     ecx
0x14000b64e  and     ecx, 1
0x14000b651  shl     r12d, cl
0x14000b654  mov     ecx, [rax+8]
0x14000b657  not     ecx
0x14000b659  and     ecx, 1
0x14000b65c  mov     r15d, [rax]
0x14000b65f  shr     r15d, cl
0x14000b662  dec     r15d
0x14000b665  shl     r15d, cl
0x14000b668  mov     r9d, r15d; unsigned int
0x14000b66b  mov     r8d, r12d; unsigned int
0x14000b66e  mov     rdx, r14; struct SBuffer::Iterator *
0x14000b671  mov     rcx, rdi; this
0x14000b674  call    ?Replace@SBuffer@@QEAAXAEBVIterator@1@II@Z; SBuffer::Replace(SBuffer::Iterator const &,uint,uint)
0x14000b679  test    r15d, r15d
0x14000b67c  jz      short loc_14000B68E
0x14000b67e  mov     r8d, r15d; Size
0x14000b681  mov     rdx, [rbx+10h]; Src
0x14000b685  mov     rcx, [r14]; void *
0x14000b688  call    memmove_0
0x14000b68d  nop
0x14000b68e  test    [rsp+280h+var_258], 8
0x14000b693  jz      short loc_14000B6C6
0x14000b695  mov     rbx, [rsp+280h+lpMem]
0x14000b69a  test    rbx, rbx
0x14000b69d  jz      short loc_14000B6C6
0x14000b69f  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x14000b6a6  test    rax, rax
0x14000b6a9  jnz     short loc_14000B6B8
0x14000b6ab  call    cs:__imp_GetProcessHeap
0x14000b6b1  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x14000b6b8  mov     r8, rbx; lpMem
0x14000b6bb  xor     edx, edx; dwFlags
0x14000b6bd  mov     rcx, rax; hHeap
0x14000b6c0  call    cs:__imp_HeapFree
0x14000b6c6  mov     rcx, [rbp+180h+var_40]
0x14000b6cd  xor     rcx, rsp; StackCookie
0x14000b6d0  call    __security_check_cookie
0x14000b6d5  add     rsp, 250h
0x14000b6dc  pop     r15
0x14000b6de  pop     r14
0x14000b6e0  pop     r12
0x14000b6e2  pop     rdi
0x14000b6e3  pop     rsi
0x14000b6e4  pop     rbx
0x14000b6e5  pop     rbp
0x14000b6e6  retn
```
