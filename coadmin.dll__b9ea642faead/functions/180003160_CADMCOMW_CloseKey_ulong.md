# CADMCOMW::CloseKey(ulong)

- ea: `0x180003160`
- end: `0x180003228`
- name: `?CloseKey@CADMCOMW@@UEAAJK@Z`
- size: `200`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180003160`
- `0x180007068`
- `0x18000be20`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CADMCOMW::CloseKey(CADMCOMW *this, unsigned int a2)
{
  int v3; // ebx
  __int64 v4; // rcx
  unsigned int v6; // [rsp+48h] [rbp+10h] BYREF
  unsigned int v7; // [rsp+50h] [rbp+18h] BYREF
  struct COpenHandle *v8; // [rsp+58h] [rbp+20h] BYREF

  v7 = 0;
  v6 = 0;
  v8 = 0;
  if ( a2 )
  {
    v3 = CADMCOMW::Lookup(this, a2, &v7, &v6, &v8);
    if ( v3 >= 0 )
    {
      v4 = *((_QWORD *)this + 101);
      if ( !v4 || !v6 || (v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 32LL))(v4), v3 >= 0) )
      {
        if ( !v7
          || (v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 288LL))(*((_QWORD *)this + 4)), v3 >= 0) )
        {
          COpenHandle::Release(v8, this);
        }
      }
    }
    if ( v8 )
      COpenHandle::Release(v8, this);
  }
  else
  {
    return (unsigned int)-2147024890;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180003160  mov     rax, rsp
0x180003163  mov     [rax+8], rbx
0x180003167  push    rdi
0x180003168  sub     rsp, 30h
0x18000316c  mov     dword ptr [rax+18h], 0
0x180003173  mov     rdi, rcx
0x180003176  mov     dword ptr [rax+10h], 0
0x18000317d  mov     qword ptr [rax+20h], 0
0x180003185  test    edx, edx
0x180003187  jnz     short loc_180003193
0x180003189  mov     ebx, 80070006h
0x18000318e  jmp     loc_18000321B
0x180003193  lea     rax, [rsp+38h+arg_18]
0x180003198  lea     r9, [rsp+38h+arg_8]; unsigned int *
0x18000319d  mov     [rsp+38h+var_18], rax; struct COpenHandle **
0x1800031a2  lea     r8, [rsp+38h+arg_10]; unsigned int *
0x1800031a7  call    ?Lookup@CADMCOMW@@QEAAJKPEAK0PEAPEAVCOpenHandle@@@Z; CADMCOMW::Lookup(ulong,ulong *,ulong *,COpenHandle * *)
0x1800031ac  mov     ebx, eax
0x1800031ae  test    eax, eax
0x1800031b0  js      short loc_180003206
0x1800031b2  mov     rcx, [rdi+328h]
0x1800031b9  test    rcx, rcx
0x1800031bc  jz      short loc_1800031D8
0x1800031be  mov     edx, [rsp+38h+arg_8]
0x1800031c2  test    edx, edx
0x1800031c4  jz      short loc_1800031D8
0x1800031c6  mov     rax, [rcx]
0x1800031c9  mov     rax, [rax+20h]
0x1800031cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031d2  mov     ebx, eax
0x1800031d4  test    eax, eax
0x1800031d6  js      short loc_180003206
0x1800031d8  mov     edx, [rsp+38h+arg_10]
0x1800031dc  test    edx, edx
0x1800031de  jz      short loc_1800031F9
0x1800031e0  mov     rcx, [rdi+20h]
0x1800031e4  mov     rax, [rcx]
0x1800031e7  mov     rax, [rax+120h]
0x1800031ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031f3  mov     ebx, eax
0x1800031f5  test    eax, eax
0x1800031f7  js      short loc_180003206
0x1800031f9  mov     rcx, [rsp+38h+arg_18]; this
0x1800031fe  mov     rdx, rdi; void *
0x180003201  call    ?Release@COpenHandle@@QEAAXPEAX@Z; COpenHandle::Release(void *)
0x180003206  cmp     [rsp+38h+arg_18], 0
0x18000320c  jz      short loc_18000321B
0x18000320e  mov     rcx, [rsp+38h+arg_18]; this
0x180003213  mov     rdx, rdi; void *
0x180003216  call    ?Release@COpenHandle@@QEAAXPEAX@Z; COpenHandle::Release(void *)
0x18000321b  mov     eax, ebx
0x18000321d  mov     rbx, [rsp+38h+arg_0]
0x180003222  add     rsp, 30h
0x180003226  pop     rdi
0x180003227  retn
```
