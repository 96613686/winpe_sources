# CWMDSPPropImpl::~CWMDSPPropImpl(void)

- ea: `0x180008564`
- end: `0x1800085da`
- name: `??1CWMDSPPropImpl@@QEAA@XZ`
- size: `118`
- prototype: `void __fastcall(CWMDSPPropImpl *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000828c`

## callees

- `0x180008564`
- `0x180008684`
- `0x18000a728`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800085bb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800085bb`

## pseudocode

```c
void __fastcall CWMDSPPropImpl::~CWMDSPPropImpl(CWMDSPPropImpl *this)
{
  bool v1; // zf
  __int64 i; // rdi
  void *v4; // rcx

  v1 = *((_QWORD *)this + 3) == 0;
  *(_QWORD *)this = &CWMDSPPropImpl::`vftable';
  if ( !v1 )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 2); i = (unsigned int)(i + 1) )
      WMDSPPropClear(
        *(unsigned __int16 *)(96 * i + *((_QWORD *)this + 2) + 20),
        *((_QWORD *)this + 3) + 8 * ((unsigned int)i + 1LL + 8 * i));
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v4 = (void *)*((_QWORD *)this + 3);
  if ( v4 )
    operator delete(v4);
}

```

## disassembly

```asm
0x180008564  mov     [rsp+arg_0], rbx
0x180008569  push    rdi
0x18000856a  sub     rsp, 20h
0x18000856e  cmp     qword ptr [rcx+18h], 0
0x180008573  lea     rax, ??_7CWMDSPPropImpl@@6B@; const CWMDSPPropImpl::`vftable'
0x18000857a  mov     [rcx], rax
0x18000857d  mov     rbx, rcx
0x180008580  jz      short loc_1800085B7
0x180008582  xor     edi, edi
0x180008584  cmp     [rcx+8], edi
0x180008587  jbe     short loc_1800085B7
0x180008589  mov     rax, [rbx+18h]
0x18000858d  mov     ecx, edi
0x18000858f  inc     rcx
0x180008592  lea     rcx, [rcx+rdi*8]
0x180008596  lea     rdx, [rax+rcx*8]
0x18000859a  mov     rcx, [rbx+10h]
0x18000859e  lea     rax, [rdi+rdi*2]
0x1800085a2  shl     rax, 5
0x1800085a6  movzx   ecx, word ptr [rax+rcx+14h]
0x1800085ab  call    WMDSPPropClear
0x1800085b0  inc     edi
0x1800085b2  cmp     edi, [rbx+8]
0x1800085b5  jb      short loc_180008589
0x1800085b7  lea     rcx, [rbx+30h]; lpCriticalSection
0x1800085bb  call    cs:__imp_DeleteCriticalSection
0x1800085c1  mov     rcx, [rbx+18h]; Block
0x1800085c5  test    rcx, rcx
0x1800085c8  jz      short loc_1800085CF
0x1800085ca  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800085cf  mov     rbx, [rsp+28h+arg_0]
0x1800085d4  add     rsp, 20h
0x1800085d8  pop     rdi
0x1800085d9  retn
```
