# FILTER_LIST::~FILTER_LIST(void)

- ea: `0x180006880`
- end: `0x1800068fd`
- name: `??1FILTER_LIST@@QEAA@XZ`
- size: `125`
- prototype: `void __fastcall(FILTER_LIST *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005f60`
- `0x180006840`

## callees

- `0x180006880`
- `0x1800092fc`

## import_xrefs

- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800068b5`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800068bf`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800068b5`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800068bf`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800068d7`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800068e5`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800068e5`

## pseudocode

```c
void __fastcall FILTER_LIST::~FILTER_LIST(FILTER_LIST *this)
{
  __int64 v1; // rsi
  BUFFER *v3; // rdi
  HTTP_FILTER_DLL **Ptr; // rax

  v1 = 0;
  *(_QWORD *)this = &FILTER_LIST::`vftable';
  if ( *((_DWORD *)this + 4) )
  {
    do
    {
      v3 = (FILTER_LIST *)((char *)this + 24);
      Ptr = (HTTP_FILTER_DLL **)BUFFER::QueryPtr((FILTER_LIST *)((char *)this + 24));
      HTTP_FILTER_DLL::DereferenceFilterDll(Ptr[v1]);
      v1 = (unsigned int)(v1 + 1);
    }
    while ( (unsigned int)v1 < *((_DWORD *)this + 4) );
  }
  else
  {
    v3 = (FILTER_LIST *)((char *)this + 24);
  }
  *((_DWORD *)this + 2) = 1936288870;
  BUFFER::~BUFFER((FILTER_LIST *)((char *)this + 136));
  BUFFER::~BUFFER((FILTER_LIST *)((char *)this + 80));
  BUFFER::~BUFFER(v3);
}

```

## disassembly

```asm
0x180006880  mov     [rsp+arg_0], rbx
0x180006885  mov     [rsp+arg_8], rsi
0x18000688a  push    rdi
0x18000688b  sub     rsp, 20h
0x18000688f  xor     esi, esi
0x180006891  lea     rax, ??_7FILTER_LIST@@6B@; const FILTER_LIST::`vftable'
0x180006898  mov     rbx, rcx
0x18000689b  mov     [rcx], rax
0x18000689e  cmp     [rcx+10h], esi
0x1800068a1  ja      short loc_1800068DE
0x1800068a3  lea     rdi, [rcx+18h]
0x1800068a7  lea     rcx, [rbx+88h]
0x1800068ae  mov     dword ptr [rbx+8], 73696C66h
0x1800068b5  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800068bb  lea     rcx, [rbx+50h]
0x1800068bf  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800068c5  mov     rcx, rdi
0x1800068c8  mov     rbx, [rsp+28h+arg_0]
0x1800068cd  mov     rsi, [rsp+28h+arg_8]
0x1800068d2  add     rsp, 20h
0x1800068d6  pop     rdi
0x1800068d7  jmp     cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800068de  lea     rdi, [rbx+18h]
0x1800068e2  mov     rcx, rdi
0x1800068e5  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800068eb  mov     rcx, [rax+rsi*8]; this
0x1800068ef  call    ?DereferenceFilterDll@HTTP_FILTER_DLL@@QEAAXXZ; HTTP_FILTER_DLL::DereferenceFilterDll(void)
0x1800068f4  inc     esi
0x1800068f6  cmp     esi, [rbx+10h]
0x1800068f9  jb      short loc_1800068DE
0x1800068fb  jmp     short loc_1800068A7
```
