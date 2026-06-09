# NameTbl::Release(void)

- ea: `0x18000c4a0`
- end: `0x18000c69a`
- name: `?Release@NameTbl@@UEAAKXZ`
- size: `506`
- prototype: `__int64 __fastcall(NameTbl *this)`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180015660`
- `0x1800307e0`
- `0x180063200`
- `0x1800642e8`

## callees

- `0x18000c4a0`
- `0x18000c860`
- `0x18000c8c0`
- `0x180016d00`
- `0x18003ba0c`
- `0x18003bd60`
- `0x1800585c4`
- `0x180098010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000c5de`
- `KERNEL32!DeleteCriticalSection` at `0x18000c5de`

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
0x18000c4a0  push    r14
0x18000c4a2  sub     rsp, 40h
0x18000c4a6  mov     rax, [rcx+20h]
0x18000c4aa  mov     [rsp+48h+arg_8], rbx
0x18000c4af  mov     rbx, rcx
0x18000c4b2  mov     [rsp+48h+arg_10], rbp
0x18000c4b7  mov     [rsp+48h+arg_18], rsi
0x18000c4bc  mov     rsi, [rcx+48h]
0x18000c4c0  mov     [rsp+48h+var_10], rdi
0x18000c4c5  mov     [rsp+48h+var_28], r15
0x18000c4ca  test    rax, rax
0x18000c4cd  jz      loc_18000C65C
0x18000c4d3  lea     rcx, ?s_varNameTblConstructed@NameTbl@@1VVAR@@A; VAR NameTbl::s_varNameTblConstructed
0x18000c4da  cmp     rax, rcx
0x18000c4dd  jz      loc_18000C65C
0x18000c4e3  mov     r15d, 1
0x18000c4e9  lock inc dword ptr [rsi]
0x18000c4ec  mov     eax, [rbx+28h]
0x18000c4ef  xor     r14d, r14d
0x18000c4f2  mov     edi, 0FFFFFFFFh
0x18000c4f7  cmp     [rbx+8], eax
0x18000c4fa  jz      loc_18000C664
0x18000c500  lea     rcx, [rsi+38h]; this
0x18000c504  call    ?Enter@MUTX@@QEAAHXZ; MUTX::Enter(void)
0x18000c509  test    eax, eax
0x18000c50b  jz      short loc_18000C56E
0x18000c50d  mov     eax, [rbx+8]
0x18000c510  test    eax, eax
0x18000c512  jz      loc_18000C5F4
0x18000c518  sub     eax, 1
0x18000c51b  mov     [rbx+8], eax
0x18000c51e  jnz     short loc_18000C565
0x18000c520  mov     [rsp+48h+var_20], r13
0x18000c525  mov     r13, [rbx+48h]
0x18000c529  test    r13, r13
0x18000c52c  jz      short loc_18000C557
0x18000c52e  lea     rcx, [r13+38h]; this
0x18000c532  mov     [rsp+48h+var_18], r12
0x18000c537  call    ?Enter@MUTX@@QEAAHXZ; MUTX::Enter(void)
0x18000c53c  test    eax, eax
0x18000c53e  jz      short loc_18000C552
0x18000c540  mov     rcx, [rbx+58h]
0x18000c544  test    rcx, rcx
0x18000c547  jnz     short loc_18000C5AB
0x18000c549  lea     rcx, [r13+38h]; this
0x18000c54d  call    ?Leave@MUTX@@QEAAXXZ; MUTX::Leave(void)
0x18000c552  mov     r12, [rsp+48h+var_18]
0x18000c557  mov     r13, [rsp+48h+var_20]
0x18000c55c  test    r15d, r15d
0x18000c55f  jz      loc_18000C5FD
0x18000c565  lea     rcx, [rsi+38h]; this
0x18000c569  call    ?Leave@MUTX@@QEAAXXZ; MUTX::Leave(void)
0x18000c56e  lock xadd [rsi], edi
0x18000c572  mov     r15, [rsp+48h+var_28]
0x18000c577  cmp     edi, 1
0x18000c57a  mov     rdi, [rsp+48h+var_10]
0x18000c57f  mov     rbx, [rsp+48h+arg_8]
0x18000c584  jnz     short loc_18000C58B
0x18000c586  test    rsi, rsi
0x18000c589  jnz     short loc_18000C5D4
0x18000c58b  mov     rsi, [rsp+48h+arg_18]
0x18000c590  mov     rbp, [rsp+48h+arg_10]
0x18000c595  test    r14, r14
0x18000c598  jnz     loc_18000C68D
0x18000c59e  mov     eax, 1
0x18000c5a3  add     rsp, 40h
0x18000c5a7  pop     r14
0x18000c5a9  retn
0x18000c5ab  mov     rax, [rbx+50h]
0x18000c5af  mov     [rcx], rax
0x18000c5b2  mov     rax, [rbx+50h]
0x18000c5b6  mov     qword ptr [rbx+58h], 0
0x18000c5be  test    rax, rax
0x18000c5c1  jz      short loc_18000C619
0x18000c5c3  mov     [rax+18h], rcx
0x18000c5c7  mov     qword ptr [rbx+50h], 0
0x18000c5cf  jmp     loc_18000C549
0x18000c5d4  cmp     byte ptr [rsi+61h], 0
0x18000c5d8  jz      short loc_18000C5EA
0x18000c5da  lea     rcx, [rsi+38h]; lpCriticalSection
0x18000c5de  call    cs:__imp_DeleteCriticalSection
0x18000c5e5  nop     dword ptr [rax+rax+00h]
0x18000c5ea  mov     rcx, rsi; Block
0x18000c5ed  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c5f2  jmp     short loc_18000C58B
0x18000c5f4  test    r15d, r15d
0x18000c5f7  jnz     loc_18000C518
0x18000c5fd  mov     rax, [rbx]
0x18000c600  mov     edx, 1
0x18000c605  mov     rcx, rbx
0x18000c608  mov     rax, [rax+198h]
0x18000c60f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c614  jmp     loc_18000C565
0x18000c619  lea     rax, [r13+20h]
0x18000c61d  cmp     rcx, rax
0x18000c620  jnz     loc_18000C549
0x18000c626  mov     rcx, r13; this
0x18000c629  call    ?FBaseThread@GcContext@@QEAAHXZ; GcContext::FBaseThread(void)
0x18000c62e  test    eax, eax
0x18000c630  jz      short loc_18000C64F
0x18000c632  test    byte ptr [r13+0Ch], 8
0x18000c637  jnz     loc_18000C549
0x18000c63d  mov     edx, 1; int
0x18000c642  mov     rcx, r13; this
0x18000c645  call    ?Reclaim@GcContext@@QEAAHJ@Z; GcContext::Reclaim(long)
0x18000c64a  jmp     loc_18000C549
0x18000c64f  mov     dword ptr [r13+8], 1
0x18000c657  jmp     loc_18000C549
0x18000c65c  xor     r15d, r15d
0x18000c65f  jmp     loc_18000C4E9
0x18000c664  mov     rax, [rbx+18h]
0x18000c668  mov     rcx, [rax+28h]
0x18000c66c  test    rcx, rcx
0x18000c66f  jz      loc_18000C500
0x18000c675  cmp     [rcx+11Ch], r14d
0x18000c67c  jz      loc_18000C500
0x18000c682  mov     r14, rcx
0x18000c685  mov     [rbx+28h], edi
0x18000c688  jmp     loc_18000C500
0x18000c68d  mov     rcx, r14; this
0x18000c690  call    ?Release@COleScript@@UEAAKXZ; COleScript::Release(void)
0x18000c695  jmp     loc_18000C59E
```
