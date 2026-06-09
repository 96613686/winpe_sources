# SERVER_CACHE_ITEM::~SERVER_CACHE_ITEM(void)

- ea: `0x18000487c`
- end: `0x1800048d6`
- name: `??1SERVER_CACHE_ITEM@@QEAA@XZ`
- size: `90`
- prototype: `void __fastcall(SERVER_CACHE_ITEM *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800047f4`
- `0x1800048f4`

## callees

- `0x18000487c`
- `0x18000dee4`
- `0x18000df38`
- `0x180012010`

## import_xrefs

- `IisRTL!??1STRU@@QEAA@XZ` at `0x1800048b5`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x1800048b5`

## pseudocode

```c
void __fastcall SERVER_CACHE_ITEM::~SERVER_CACHE_ITEM(SERVER_CACHE_ITEM *this)
{
  __int64 v2; // rcx

  v2 = *((_QWORD *)this + 13);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 13) = 0;
  }
  if ( *((_QWORD *)this + 14) )
    *((_QWORD *)this + 14) = 0;
  STRU::~STRU((SERVER_CACHE_ITEM *)((char *)this + 48));
  CCredentials::FreeUserName((unsigned __int16 **)this + 1);
  CCredentials::FreePassword((unsigned __int16 **)this + 2, (unsigned int *)this + 7);
}

```

## disassembly

```asm
0x18000487c  push    rbx
0x18000487e  sub     rsp, 20h
0x180004882  mov     rbx, rcx
0x180004885  mov     rcx, [rcx+68h]
0x180004889  test    rcx, rcx
0x18000488c  jz      short loc_1800048A2
0x18000488e  mov     rax, [rcx]
0x180004891  mov     rax, [rax+10h]
0x180004895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000489a  mov     qword ptr [rbx+68h], 0
0x1800048a2  cmp     qword ptr [rbx+70h], 0
0x1800048a7  jz      short loc_1800048B1
0x1800048a9  mov     qword ptr [rbx+70h], 0
0x1800048b1  lea     rcx, [rbx+30h]
0x1800048b5  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800048bb  lea     rcx, [rbx+8]; unsigned __int16 **
0x1800048bf  call    ?FreeUserName@CCredentials@@CAXAEAPEAG@Z; CCredentials::FreeUserName(ushort * &)
0x1800048c4  lea     rdx, [rbx+1Ch]; unsigned int *
0x1800048c8  lea     rcx, [rbx+10h]; unsigned __int16 **
0x1800048cc  add     rsp, 20h
0x1800048d0  pop     rbx
0x1800048d1  jmp     ?FreePassword@CCredentials@@CAXAEAPEAGAEAK@Z; CCredentials::FreePassword(ushort * &,ulong &)
```
