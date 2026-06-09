# CProviderImpersonation::~CProviderImpersonation(void)

- ea: `0x140018f50`
- end: `0x140018f86`
- name: `??1CProviderImpersonation@@IEAA@XZ`
- size: `54`
- prototype: `void __fastcall(CProviderImpersonation *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400190f0`

## callees

- `0x140018f50`
- `0x14001c010`

## pseudocode

```c
void __fastcall CProviderImpersonation::~CProviderImpersonation(CProviderImpersonation *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &CProviderImpersonation::`vftable';
  v2 = *((_QWORD *)this + 2);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x140018f50  push    rbx
0x140018f52  sub     rsp, 20h
0x140018f56  mov     rbx, rcx
0x140018f59  lea     rax, ??_7CProviderImpersonation@@6B@; const CProviderImpersonation::`vftable'
0x140018f60  mov     [rcx], rax
0x140018f63  mov     rcx, [rcx+10h]
0x140018f67  test    rcx, rcx
0x140018f6a  jz      short loc_140018F80
0x140018f6c  mov     rax, [rcx]
0x140018f6f  mov     rax, [rax+10h]
0x140018f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018f78  mov     qword ptr [rbx+10h], 0
0x140018f80  add     rsp, 20h
0x140018f84  pop     rbx
0x140018f85  retn
```
