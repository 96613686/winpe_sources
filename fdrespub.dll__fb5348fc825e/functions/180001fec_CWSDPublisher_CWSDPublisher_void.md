# CWSDPublisher::~CWSDPublisher(void)

- ea: `0x180001fec`
- end: `0x1800020f1`
- name: `??1CWSDPublisher@@QEAA@XZ`
- size: `261`
- prototype: `void __fastcall(CWSDPublisher *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180001cc0`
- `0x1800041e0`

## callees

- `0x180001008`
- `0x180001020`
- `0x180001fec`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002007`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002014`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002007`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002014`
- `wsdapi!WSDRemoveFirewallCheck` at `0x18000205a`
- `wsdapi!WSDRemoveFirewallCheck` at `0x18000205a`

## pseudocode

```c
void __fastcall CWSDPublisher::~CWSDPublisher(CWSDPublisher *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  void *v4; // rcx
  __int64 v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void **v9; // rdi
  __int64 *v10; // rbx
  __int64 *v11; // rax
  __int64 v12; // rdx

  *(_QWORD *)this = &CWSDPublisher::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  v2 = *((_QWORD *)this + 5);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 5) = 0;
  }
  v3 = *((_QWORD *)this + 4);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 4) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 24);
  if ( v4 )
  {
    WSDRemoveFirewallCheck(v4);
    *((_QWORD *)this + 24) = 0;
  }
  v5 = *((_QWORD *)this + 1);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *((_QWORD *)this + 1) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 8);
  if ( v6 )
  {
    operator delete[](v6);
    *((_QWORD *)this + 8) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 6);
  if ( v7 )
  {
    operator delete[](v7);
    *((_QWORD *)this + 6) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 7);
  if ( v8 )
  {
    operator delete[](v8);
    *((_QWORD *)this + 7) = 0;
  }
  v9 = (void **)((char *)this + 176);
  while ( 1 )
  {
    v10 = (__int64 *)*v9;
    if ( *v9 == v9 )
      break;
    v11 = (__int64 *)v10[1];
    v12 = *v10;
    *v11 = *v10;
    *(_QWORD *)(v12 + 8) = v11;
    operator delete((void *)v10[2]);
    operator delete(v10);
  }
}

```

## disassembly

```asm
0x180001fec  mov     [rsp+arg_0], rbx
0x180001ff1  push    rdi
0x180001ff2  sub     rsp, 20h
0x180001ff6  lea     rax, ??_7CWSDPublisher@@6B@; const CWSDPublisher::`vftable'
0x180001ffd  mov     rbx, rcx
0x180002000  mov     [rcx], rax
0x180002003  add     rcx, 60h ; '`'; lpCriticalSection
0x180002007  call    cs:__imp_DeleteCriticalSection
0x18000200d  lea     rcx, [rbx+88h]; lpCriticalSection
0x180002014  call    cs:__imp_DeleteCriticalSection
0x18000201a  mov     rcx, [rbx+28h]
0x18000201e  xor     edi, edi
0x180002020  test    rcx, rcx
0x180002023  jz      short loc_180002035
0x180002025  mov     rax, [rcx]
0x180002028  mov     rax, [rax+10h]
0x18000202c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002031  mov     [rbx+28h], rdi
0x180002035  mov     rcx, [rbx+20h]
0x180002039  test    rcx, rcx
0x18000203c  jz      short loc_18000204E
0x18000203e  mov     rax, [rcx]
0x180002041  mov     rax, [rax+10h]
0x180002045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000204a  mov     [rbx+20h], rdi
0x18000204e  mov     rcx, [rbx+0C0h]
0x180002055  test    rcx, rcx
0x180002058  jz      short loc_180002067
0x18000205a  call    cs:__imp_?WSDRemoveFirewallCheck@@YAJPEAX@Z; WSDRemoveFirewallCheck(void *)
0x180002060  mov     [rbx+0C0h], rdi
0x180002067  mov     rcx, [rbx+8]
0x18000206b  test    rcx, rcx
0x18000206e  jz      short loc_180002080
0x180002070  mov     rax, [rcx]
0x180002073  mov     rax, [rax+10h]
0x180002077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000207c  mov     [rbx+8], rdi
0x180002080  mov     rcx, [rbx+40h]; Block
0x180002084  test    rcx, rcx
0x180002087  jz      short loc_180002092
0x180002089  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18000208e  mov     [rbx+40h], rdi
0x180002092  mov     rcx, [rbx+30h]; Block
0x180002096  test    rcx, rcx
0x180002099  jz      short loc_1800020A4
0x18000209b  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800020a0  mov     [rbx+30h], rdi
0x1800020a4  mov     rcx, [rbx+38h]; Block
0x1800020a8  test    rcx, rcx
0x1800020ab  jz      short loc_1800020B6
0x1800020ad  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800020b2  mov     [rbx+38h], rdi
0x1800020b6  lea     rdi, [rbx+0B0h]
0x1800020bd  mov     rbx, [rdi]
0x1800020c0  cmp     rbx, rdi
0x1800020c3  jz      short loc_1800020E6
0x1800020c5  mov     rax, [rbx+8]
0x1800020c9  mov     rdx, [rbx]
0x1800020cc  mov     [rax], rdx
0x1800020cf  mov     [rdx+8], rax
0x1800020d3  mov     rcx, [rbx+10h]; Block
0x1800020d7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800020dc  mov     rcx, rbx; Block
0x1800020df  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800020e4  jmp     short loc_1800020BD
0x1800020e6  mov     rbx, [rsp+28h+arg_0]
0x1800020eb  add     rsp, 20h
0x1800020ef  pop     rdi
0x1800020f0  retn
```
