# CXMLRowset::~CXMLRowset(void)

- ea: `0x180028df0`
- end: `0x180028ef5`
- name: `??1CXMLRowset@@UEAA@XZ`
- size: `261`
- prototype: `void __fastcall(CXMLRowset *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180023e68`
- `0x180028f00`

## callees

- `0x180001db8`
- `0x180003c38`
- `0x1800207a0`
- `0x180023ea4`
- `0x1800241b0`
- `0x180028df0`
- `0x180031010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180028ecb`
- `OLEAUT32!__imp_SysFreeString` at `0x180028ecb`

## pseudocode

```c
void __fastcall CXMLRowset::~CXMLRowset(CXMLRowset *this, unsigned int a2)
{
  unsigned __int16 v3; // di
  unsigned __int8 *v4; // rsi
  __int64 v5; // rcx
  unsigned __int8 *v6; // rcx
  unsigned __int8 *v7; // rcx
  CScope *v8; // rcx

  *(_QWORD *)this = &CXMLRowset::`vftable';
  v3 = 1;
  if ( *((_DWORD *)this + 38) )
  {
    do
    {
      if ( (CMetaData::mdGetFlags((CXMLRowset *)((char *)this + 304), v3 - 1) & 0x2000) != 0 )
      {
        v4 = *(unsigned __int8 **)(*((_QWORD *)this + 68) + 8LL * v3);
        if ( v4 && *(_QWORD *)v4 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v4 + 16LL))(*(_QWORD *)v4);
        operator delete(v4);
      }
      ++v3;
    }
    while ( (unsigned int)v3 <= *((_DWORD *)this + 38) );
  }
  v5 = *((_QWORD *)this + 75);
  if ( v5 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v5 + 448) + 16LL))(*(_QWORD *)(v5 + 448));
  v6 = (unsigned __int8 *)*((_QWORD *)this + 68);
  if ( v6 )
    operator delete(v6);
  v7 = (unsigned __int8 *)*((_QWORD *)this + 78);
  if ( v7 )
    operator delete(v7);
  v8 = (CScope *)*((_QWORD *)this + 79);
  if ( v8 )
    CScope::`scalar deleting destructor'(v8, a2);
  SysFreeString(*((BSTR *)this + 80));
  CCollectionList::~CCollectionList((CXMLRowset *)((char *)this + 552));
  CRowset::~CRowset(this);
}

```

## disassembly

```asm
0x180028df0  push    rbx
0x180028df2  push    rbp
0x180028df3  push    rsi
0x180028df4  push    rdi
0x180028df5  push    r14
0x180028df7  sub     rsp, 20h
0x180028dfb  mov     rbx, rcx
0x180028dfe  lea     rax, ??_7CXMLRowset@@6B@; const CXMLRowset::`vftable'
0x180028e05  mov     [rcx], rax
0x180028e08  mov     r14d, 1
0x180028e0e  movzx   edi, r14w
0x180028e12  cmp     [rcx+98h], r14d
0x180028e19  jb      short loc_180028E72
0x180028e1b  movzx   edx, di
0x180028e1e  sub     dx, r14w; unsigned __int16
0x180028e22  lea     rcx, [rbx+130h]; this
0x180028e29  call    ?mdGetFlags@CMetaData@@QEAAKG@Z; CMetaData::mdGetFlags(ushort)
0x180028e2e  bt      eax, 0Dh
0x180028e32  jnb     short loc_180028E63
0x180028e34  movzx   ecx, di
0x180028e37  mov     rax, [rbx+220h]
0x180028e3e  mov     rsi, [rax+rcx*8]
0x180028e42  test    rsi, rsi
0x180028e45  jz      short loc_180028E5B
0x180028e47  mov     rcx, [rsi]
0x180028e4a  test    rcx, rcx
0x180028e4d  jz      short loc_180028E5B
0x180028e4f  mov     rax, [rcx]
0x180028e52  mov     rax, [rax+10h]
0x180028e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e5b  mov     rcx, rsi; void *
0x180028e5e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180028e63  add     di, r14w
0x180028e67  movzx   eax, di
0x180028e6a  cmp     eax, [rbx+98h]
0x180028e70  jbe     short loc_180028E1B
0x180028e72  mov     rcx, [rbx+258h]
0x180028e79  test    rcx, rcx
0x180028e7c  jz      short loc_180028E91
0x180028e7e  mov     rcx, [rcx+1C0h]
0x180028e85  mov     rax, [rcx]
0x180028e88  mov     rax, [rax+10h]
0x180028e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e91  mov     rcx, [rbx+220h]; void *
0x180028e98  test    rcx, rcx
0x180028e9b  jz      short loc_180028EA2
0x180028e9d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180028ea2  mov     rcx, [rbx+270h]; void *
0x180028ea9  test    rcx, rcx
0x180028eac  jz      short loc_180028EB3
0x180028eae  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180028eb3  mov     rcx, [rbx+278h]; this
0x180028eba  test    rcx, rcx
0x180028ebd  jz      short loc_180028EC4
0x180028ebf  call    ??_GCScope@@QEAAPEAXI@Z; CScope::`scalar deleting destructor'(uint)
0x180028ec4  mov     rcx, [rbx+280h]; bstrString
0x180028ecb  call    cs:__imp_SysFreeString
0x180028ed2  nop     dword ptr [rax+rax+00h]
0x180028ed7  lea     rcx, [rbx+228h]; this
0x180028ede  call    ??1CCollectionList@@QEAA@XZ; CCollectionList::~CCollectionList(void)
0x180028ee3  mov     rcx, rbx; this
0x180028ee6  add     rsp, 20h
0x180028eea  pop     r14
0x180028eec  pop     rdi
0x180028eed  pop     rsi
0x180028eee  pop     rbp
0x180028eef  pop     rbx
0x180028ef0  jmp     ??1CRowset@@UEAA@XZ; CRowset::~CRowset(void)
```
