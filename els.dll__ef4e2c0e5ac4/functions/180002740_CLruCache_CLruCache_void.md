# CLruCache::~CLruCache(void)

- ea: `0x180002740`
- end: `0x1800027bd`
- name: `??1CLruCache@@UEAA@XZ`
- size: `125`
- prototype: `void __fastcall(CLruCache *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000c230`
- `0x18000c2b0`

## callees

- `0x180002740`
- `0x180004f68`
- `0x180024010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000275b`
- `KERNEL32!EnterCriticalSection` at `0x18000275b`
- `KERNEL32!LeaveCriticalSection` at `0x1800027a2`
- `KERNEL32!LeaveCriticalSection` at `0x1800027a2`
- `KERNEL32!DeleteCriticalSection` at `0x1800027b6`

## pseudocode

```c
void __fastcall CLruCache::~CLruCache(CLruCache *this)
{
  CDLink *v2; // rcx
  CDLink *v3; // rsi
  void (__fastcall ***v4)(_QWORD, __int64); // rcx

  *(_QWORD *)this = &CLruCache::`vftable';
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v2 = (CDLink *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    do
    {
      v3 = (CDLink *)*((_QWORD *)v2 + 1);
      CDLink::UnLink(v2);
      (**v4)(v4, 1);
      v2 = v3;
    }
    while ( v3 );
  }
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 2) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
}

```

## disassembly

```asm
0x180002740  mov     [rsp+arg_8], rbx
0x180002745  push    rdi
0x180002746  sub     rsp, 20h
0x18000274a  lea     rax, ??_7CLruCache@@6B@; const CLruCache::`vftable'
0x180002751  mov     rdi, rcx
0x180002754  mov     [rcx], rax
0x180002757  add     rcx, 18h; lpCriticalSection
0x18000275b  call    cs:__imp_EnterCriticalSection
0x180002761  mov     rcx, [rdi+10h]; this
0x180002765  test    rcx, rcx
0x180002768  jz      short loc_180002795
0x18000276a  mov     [rsp+28h+arg_0], rsi
0x18000276f  mov     rsi, [rcx+8]
0x180002773  call    ?UnLink@CDLink@@QEAAXXZ; CDLink::UnLink(void)
0x180002778  mov     r9, [rcx]
0x18000277b  mov     edx, 1
0x180002780  mov     rax, [r9]
0x180002783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002788  mov     rcx, rsi
0x18000278b  test    rsi, rsi
0x18000278e  jnz     short loc_18000276F
0x180002790  mov     rsi, [rsp+28h+arg_0]
0x180002795  xor     eax, eax
0x180002797  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000279b  mov     [rdi+10h], rax
0x18000279f  mov     [rdi+8], eax
0x1800027a2  call    cs:__imp_LeaveCriticalSection
0x1800027a8  lea     rcx, [rdi+18h]
0x1800027ac  mov     rbx, [rsp+28h+arg_8]
0x1800027b1  add     rsp, 20h
0x1800027b5  pop     rdi
0x1800027b6  jmp     cs:__imp_DeleteCriticalSection
```
