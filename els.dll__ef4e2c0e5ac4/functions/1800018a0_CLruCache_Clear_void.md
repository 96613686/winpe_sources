# CLruCache::Clear(void)

- ea: `0x1800018a0`
- end: `0x180001909`
- name: `?Clear@CLruCache@@UEAAXXZ`
- size: `105`
- prototype: `void __fastcall(CLruCache *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180005de0`
- `0x180007ee4`

## callees

- `0x1800018a0`
- `0x180004f68`
- `0x180024010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800018b1`
- `KERNEL32!EnterCriticalSection` at `0x1800018b1`
- `KERNEL32!LeaveCriticalSection` at `0x180001902`

## pseudocode

```c
void __fastcall CLruCache::Clear(CLruCache *this)
{
  CDLink *v2; // rcx
  CDLink *v3; // rsi
  void (__fastcall ***v4)(_QWORD, __int64); // rcx

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
}

```

## disassembly

```asm
0x1800018a0  mov     [rsp+arg_8], rbx
0x1800018a5  push    rdi
0x1800018a6  sub     rsp, 20h
0x1800018aa  mov     rdi, rcx
0x1800018ad  add     rcx, 18h; lpCriticalSection
0x1800018b1  call    cs:__imp_EnterCriticalSection
0x1800018b7  mov     rcx, [rdi+10h]; this
0x1800018bb  test    rcx, rcx
0x1800018be  jz      short loc_1800018EB
0x1800018c0  mov     [rsp+28h+arg_0], rsi
0x1800018c5  mov     rsi, [rcx+8]
0x1800018c9  call    ?UnLink@CDLink@@QEAAXXZ; CDLink::UnLink(void)
0x1800018ce  mov     r9, [rcx]
0x1800018d1  mov     edx, 1
0x1800018d6  mov     rax, [r9]
0x1800018d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018de  mov     rcx, rsi
0x1800018e1  test    rsi, rsi
0x1800018e4  jnz     short loc_1800018C5
0x1800018e6  mov     rsi, [rsp+28h+arg_0]
0x1800018eb  xor     eax, eax
0x1800018ed  lea     rcx, [rdi+18h]
0x1800018f1  mov     [rdi+10h], rax
0x1800018f5  mov     [rdi+8], eax
0x1800018f8  mov     rbx, [rsp+28h+arg_8]
0x1800018fd  add     rsp, 20h
0x180001901  pop     rdi
0x180001902  jmp     cs:__imp_LeaveCriticalSection
```
