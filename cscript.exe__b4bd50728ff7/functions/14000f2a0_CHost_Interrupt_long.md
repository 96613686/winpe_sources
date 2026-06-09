# CHost::Interrupt(long)

- ea: `0x14000f2a0`
- end: `0x14000f372`
- name: `?Interrupt@CHost@@QEAAJJ@Z`
- size: `210`
- prototype: `__int64 __fastcall(CHost *__hidden this, int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140007370`
- `0x14000fbb0`
- `0x140012820`

## callees

- `0x14000f12c`
- `0x14000f2a0`
- `0x14000f420`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall CHost::Interrupt(CHost *this, __int32 a2)
{
  CCriticalSection *v2; // rsi
  __int64 v5; // rcx
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rcx
  _QWORD v9[2]; // [rsp+30h] [rbp-48h] BYREF
  __int128 v10; // [rsp+40h] [rbp-38h]
  __int64 v11; // [rsp+50h] [rbp-28h]
  __int64 v12; // [rsp+58h] [rbp-20h]
  __int64 v13; // [rsp+60h] [rbp-18h]
  __int32 v14; // [rsp+68h] [rbp-10h]
  int v15; // [rsp+6Ch] [rbp-Ch]

  v2 = (CHost *)((char *)this + 696);
  _InterlockedExchange((volatile __int32 *)this + 10, a2);
  v9[0] = 0;
  v11 = 0;
  v15 = 0;
  v9[1] = 0;
  v10 = 0;
  v12 = 0;
  v13 = 0;
  v14 = a2;
  if ( !(unsigned int)CCriticalSection::Enter((CHost *)((char *)this + 696)) )
    return 2147500037LL;
  v5 = *((_QWORD *)this + 79);
  if ( v5 )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD *, __int64))(**(_QWORD **)(v5 + 96) + 112LL))(
           *(_QWORD *)(v5 + 96),
           4294967293LL,
           v9,
           2);
    v7 = 0;
    if ( v6 < 0 )
      v7 = v6;
  }
  else
  {
    v8 = *((_QWORD *)this + 85);
    v7 = -2147467259;
    if ( v8 )
      v7 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v8 + 32LL))(v8, v9);
  }
  CCriticalSection::Leave(v2);
  return v7;
}

```

## disassembly

```asm
0x14000f2a0  push    rbp
0x14000f2a2  push    rbx
0x14000f2a3  push    rsi
0x14000f2a4  push    rdi
0x14000f2a5  mov     rbp, rsp
0x14000f2a8  sub     rsp, 78h
0x14000f2ac  mov     eax, edx
0x14000f2ae  lea     rsi, [rcx+2B8h]
0x14000f2b5  xchg    eax, [rcx+28h]
0x14000f2b8  mov     rdi, rcx
0x14000f2bb  mov     [rbp+var_48], 0
0x14000f2c3  xorps   xmm0, xmm0
0x14000f2c6  mov     [rbp+var_28], 0
0x14000f2ce  mov     rcx, rsi; this
0x14000f2d1  mov     [rbp+var_C], 0
0x14000f2d8  mov     [rbp+var_40], 0
0x14000f2e0  movdqa  [rbp+var_38], xmm0
0x14000f2e5  mov     [rbp+var_20], 0
0x14000f2ed  mov     [rbp+var_18], 0
0x14000f2f5  mov     [rbp+var_10], edx
0x14000f2f8  call    ?Enter@CCriticalSection@@QEAAHXZ; CCriticalSection::Enter(void)
0x14000f2fd  test    eax, eax
0x14000f2ff  jnz     short loc_14000F308
0x14000f301  mov     eax, 80004005h
0x14000f306  jmp     short loc_14000F369
0x14000f308  mov     rcx, [rdi+278h]
0x14000f30f  test    rcx, rcx
0x14000f312  jz      short loc_14000F33C
0x14000f314  mov     rcx, [rcx+60h]
0x14000f318  lea     r8, [rbp+var_48]
0x14000f31c  mov     r9d, 2
0x14000f322  mov     edx, 0FFFFFFFDh
0x14000f327  mov     rax, [rcx]
0x14000f32a  mov     rax, [rax+70h]
0x14000f32e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f333  xor     ebx, ebx
0x14000f335  test    eax, eax
0x14000f337  cmovs   ebx, eax
0x14000f33a  jmp     short loc_14000F35F
0x14000f33c  mov     rcx, [rdi+2A8h]
0x14000f343  mov     ebx, 80004005h
0x14000f348  test    rcx, rcx
0x14000f34b  jz      short loc_14000F35F
0x14000f34d  mov     rax, [rcx]
0x14000f350  lea     rdx, [rbp+var_48]
0x14000f354  mov     rax, [rax+20h]
0x14000f358  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f35d  mov     ebx, eax
0x14000f35f  mov     rcx, rsi; this
0x14000f362  call    ?Leave@CCriticalSection@@QEAAXXZ; CCriticalSection::Leave(void)
0x14000f367  mov     eax, ebx
0x14000f369  add     rsp, 78h
0x14000f36d  pop     rdi
0x14000f36e  pop     rsi
0x14000f36f  pop     rbx
0x14000f370  pop     rbp
0x14000f371  retn
```
