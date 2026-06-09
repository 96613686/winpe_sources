# NameTbl::Release(void)

- ea: `0x18000f230`
- end: `0x18000f423`
- name: `?Release@NameTbl@@UEAAKXZ`
- size: `499`
- prototype: `unsigned int __fastcall(NameTbl *__hidden this)`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18001879c`
- `0x18004b450`
- `0x180061fc0`
- `0x180062fe8`

## callees

- `0x18000f230`
- `0x18000f5e0`
- `0x18000f630`
- `0x180019ce0`
- `0x180034200`
- `0x180034b80`
- `0x180057694`
- `0x180096010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000f36d`
- `KERNEL32!DeleteCriticalSection` at `0x18000f36d`

## pseudocode

```c
__int64 __fastcall NameTbl::Release(NameTbl *this)
{
  __int64 *v1; // rax
  __int64 v3; // rsi
  BOOL v4; // r15d
  COleScript *v5; // r14
  int v6; // eax
  int v7; // eax
  __int64 v8; // r13
  _QWORD *v9; // rcx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rcx

  v1 = (__int64 *)*((_QWORD *)this + 4);
  v3 = *((_QWORD *)this + 9);
  v4 = v1 && v1 != NameTbl::s_varNameTblConstructed;
  _InterlockedIncrement((volatile signed __int32 *)v3);
  v5 = 0;
  if ( *((_DWORD *)this + 2) == *((_DWORD *)this + 10) )
  {
    v12 = *((_QWORD *)this + 3);
    v13 = *(_QWORD *)(v12 + 40);
    if ( v13 )
    {
      if ( *(_DWORD *)(v13 + 284) )
      {
        v5 = *(COleScript **)(v12 + 40);
        *((_DWORD *)this + 10) = -1;
      }
    }
  }
  if ( (unsigned int)MUTX::Enter((MUTX *)(v3 + 56)) )
  {
    v6 = *((_DWORD *)this + 2);
    if ( !v6 && !v4 )
      goto LABEL_25;
    v7 = v6 - 1;
    *((_DWORD *)this + 2) = v7;
    if ( !v7 )
    {
      v8 = *((_QWORD *)this + 9);
      if ( v8 && (unsigned int)MUTX::Enter((MUTX *)(v8 + 56)) )
      {
        v9 = (_QWORD *)*((_QWORD *)this + 11);
        if ( v9 )
        {
          *v9 = *((_QWORD *)this + 10);
          v11 = *((_QWORD *)this + 10);
          *((_QWORD *)this + 11) = 0;
          if ( v11 )
          {
            *(_QWORD *)(v11 + 24) = v9;
            *((_QWORD *)this + 10) = 0;
          }
          else if ( v9 == (_QWORD *)(v8 + 32) )
          {
            if ( (unsigned int)GcContext::FBaseThread((GcContext *)v8) )
            {
              if ( (*(_BYTE *)(v8 + 12) & 8) == 0 )
                GcContext::Reclaim((GcContext *)v8, 1);
            }
            else
            {
              *(_DWORD *)(v8 + 8) = 1;
            }
          }
        }
        MUTX::Leave((MUTX *)(v8 + 56));
      }
      if ( !v4 )
LABEL_25:
        (*(void (__fastcall **)(NameTbl *, __int64))(*(_QWORD *)this + 408LL))(this, 1);
    }
    MUTX::Leave((MUTX *)(v3 + 56));
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v3, 0xFFFFFFFF) == 1 && v3 )
  {
    if ( *(_BYTE *)(v3 + 97) )
      DeleteCriticalSection((LPCRITICAL_SECTION)(v3 + 56));
    operator delete((void *)v3);
  }
  if ( v5 )
    COleScript::Release(v5);
  return 1;
}

```

## disassembly

```asm
0x18000f230  push    r14
0x18000f232  sub     rsp, 40h
0x18000f236  mov     rax, [rcx+20h]
0x18000f23a  mov     [rsp+48h+arg_8], rbx
0x18000f23f  mov     rbx, rcx
0x18000f242  mov     [rsp+48h+arg_10], rbp
0x18000f247  mov     [rsp+48h+arg_18], rsi
0x18000f24c  mov     rsi, [rcx+48h]
0x18000f250  mov     [rsp+48h+var_10], rdi
0x18000f255  mov     [rsp+48h+var_28], r15
0x18000f25a  test    rax, rax
0x18000f25d  jz      loc_18000F3E5
0x18000f263  lea     rcx, ?s_varNameTblConstructed@NameTbl@@1VVAR@@A; VAR NameTbl::s_varNameTblConstructed
0x18000f26a  cmp     rax, rcx
0x18000f26d  jz      loc_18000F3E5
0x18000f273  mov     r15d, 1
0x18000f279  lock inc dword ptr [rsi]
0x18000f27c  mov     eax, [rbx+28h]
0x18000f27f  xor     r14d, r14d
0x18000f282  mov     edi, 0FFFFFFFFh
0x18000f287  cmp     [rbx+8], eax
0x18000f28a  jz      loc_18000F3ED
0x18000f290  lea     rcx, [rsi+38h]; this
0x18000f294  call    ?Enter@MUTX@@QEAAHXZ; MUTX::Enter(void)
0x18000f299  test    eax, eax
0x18000f29b  jz      short loc_18000F2FE
0x18000f29d  mov     eax, [rbx+8]
0x18000f2a0  test    eax, eax
0x18000f2a2  jz      loc_18000F37D
0x18000f2a8  sub     eax, 1
0x18000f2ab  mov     [rbx+8], eax
0x18000f2ae  jnz     short loc_18000F2F5
0x18000f2b0  mov     [rsp+48h+var_20], r13
0x18000f2b5  mov     r13, [rbx+48h]
0x18000f2b9  test    r13, r13
0x18000f2bc  jz      short loc_18000F2E7
0x18000f2be  lea     rcx, [r13+38h]; this
0x18000f2c2  mov     [rsp+48h+var_18], r12
0x18000f2c7  call    ?Enter@MUTX@@QEAAHXZ; MUTX::Enter(void)
0x18000f2cc  test    eax, eax
0x18000f2ce  jz      short loc_18000F2E2
0x18000f2d0  mov     rcx, [rbx+58h]
0x18000f2d4  test    rcx, rcx
0x18000f2d7  jnz     short loc_18000F33A
0x18000f2d9  lea     rcx, [r13+38h]; this
0x18000f2dd  call    ?Leave@MUTX@@QEAAXXZ; MUTX::Leave(void)
0x18000f2e2  mov     r12, [rsp+48h+var_18]
0x18000f2e7  mov     r13, [rsp+48h+var_20]
0x18000f2ec  test    r15d, r15d
0x18000f2ef  jz      loc_18000F386
0x18000f2f5  lea     rcx, [rsi+38h]; this
0x18000f2f9  call    ?Leave@MUTX@@QEAAXXZ; MUTX::Leave(void)
0x18000f2fe  lock xadd [rsi], edi
0x18000f302  mov     r15, [rsp+48h+var_28]
0x18000f307  cmp     edi, 1
0x18000f30a  mov     rdi, [rsp+48h+var_10]
0x18000f30f  mov     rbx, [rsp+48h+arg_8]
0x18000f314  jnz     short loc_18000F31B
0x18000f316  test    rsi, rsi
0x18000f319  jnz     short loc_18000F363
0x18000f31b  mov     rsi, [rsp+48h+arg_18]
0x18000f320  mov     rbp, [rsp+48h+arg_10]
0x18000f325  test    r14, r14
0x18000f328  jnz     loc_18000F416
0x18000f32e  mov     eax, 1
0x18000f333  add     rsp, 40h
0x18000f337  pop     r14
0x18000f339  retn
0x18000f33a  mov     rax, [rbx+50h]
0x18000f33e  mov     [rcx], rax
0x18000f341  mov     rax, [rbx+50h]
0x18000f345  mov     qword ptr [rbx+58h], 0
0x18000f34d  test    rax, rax
0x18000f350  jz      short loc_18000F3A2
0x18000f352  mov     [rax+18h], rcx
0x18000f356  mov     qword ptr [rbx+50h], 0
0x18000f35e  jmp     loc_18000F2D9
0x18000f363  cmp     byte ptr [rsi+61h], 0
0x18000f367  jz      short loc_18000F373
0x18000f369  lea     rcx, [rsi+38h]; lpCriticalSection
0x18000f36d  call    cs:__imp_DeleteCriticalSection
0x18000f373  mov     rcx, rsi; Block
0x18000f376  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f37b  jmp     short loc_18000F31B
0x18000f37d  test    r15d, r15d
0x18000f380  jnz     loc_18000F2A8
0x18000f386  mov     rax, [rbx]
0x18000f389  mov     edx, 1
0x18000f38e  mov     rcx, rbx
0x18000f391  mov     rax, [rax+198h]
0x18000f398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f39d  jmp     loc_18000F2F5
0x18000f3a2  lea     rax, [r13+20h]
0x18000f3a6  cmp     rcx, rax
0x18000f3a9  jnz     loc_18000F2D9
0x18000f3af  mov     rcx, r13; this
0x18000f3b2  call    ?FBaseThread@GcContext@@QEAAHXZ; GcContext::FBaseThread(void)
0x18000f3b7  test    eax, eax
0x18000f3b9  jz      short loc_18000F3D8
0x18000f3bb  test    byte ptr [r13+0Ch], 8
0x18000f3c0  jnz     loc_18000F2D9
0x18000f3c6  mov     edx, 1; int
0x18000f3cb  mov     rcx, r13; this
0x18000f3ce  call    ?Reclaim@GcContext@@QEAAHJ@Z; GcContext::Reclaim(long)
0x18000f3d3  jmp     loc_18000F2D9
0x18000f3d8  mov     dword ptr [r13+8], 1
0x18000f3e0  jmp     loc_18000F2D9
0x18000f3e5  xor     r15d, r15d
0x18000f3e8  jmp     loc_18000F279
0x18000f3ed  mov     rax, [rbx+18h]
0x18000f3f1  mov     rcx, [rax+28h]
0x18000f3f5  test    rcx, rcx
0x18000f3f8  jz      loc_18000F290
0x18000f3fe  cmp     [rcx+11Ch], r14d
0x18000f405  jz      loc_18000F290
0x18000f40b  mov     r14, rcx
0x18000f40e  mov     [rbx+28h], edi
0x18000f411  jmp     loc_18000F290
0x18000f416  mov     rcx, r14; this
0x18000f419  call    ?Release@COleScript@@UEAAKXZ; COleScript::Release(void)
0x18000f41e  jmp     loc_18000F32E
```
