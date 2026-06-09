# FREB_LOG_NT_EVENT_TABLE::LogEvent(ulong,ushort,ushort const * * const,ulong)

- ea: `0x18000a4dc`
- end: `0x18000a6a2`
- name: `?LogEvent@FREB_LOG_NT_EVENT_TABLE@@SAXKGQEAPEBGK@Z`
- size: `454`
- prototype: `void __fastcall(unsigned int, unsigned __int16, const unsigned __int16 **const, unsigned int)`
- caller_count: `10`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800023cc`
- `0x180006944`
- `0x180006f98`
- `0x1800075d4`
- `0x18000795c`
- `0x180007a80`
- `0x180007f70`
- `0x180008548`
- `0x18000a6a8`
- `0x18000a6d8`

## callees

- `0x180001008`
- `0x180001048`
- `0x18000a2e8`
- `0x18000a4dc`
- `0x18000a7e0`

## import_xrefs

- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000a591`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000a5e2`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000a591`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000a5e2`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18000a5b1`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18000a5b1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a630`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a67b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a630`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a67b`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000a626`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000a671`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000a626`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000a671`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000a526`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000a526`

## pseudocode

```c
void __fastcall FREB_LOG_NT_EVENT_TABLE::LogEvent(
        unsigned int a1,
        unsigned __int16 a2,
        const unsigned __int16 **const a3,
        unsigned int a4)
{
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  __int64 v10; // rdi
  __int64 v11; // rdx
  int Key; // eax
  __int64 v13; // rdx
  int v14; // eax
  void *v15; // rcx
  void *v16; // rcx
  _QWORD v17[2]; // [rsp+30h] [rbp-38h] BYREF

  v8 = operator new(0xC8u);
  v9 = v8;
  if ( !v8 )
    return;
  *v8 = 1;
  v10 = 0;
  STRU::STRU((STRU *)(v8 + 1));
  *((_DWORD *)v9 + 16) = 0;
  *((_BYTE *)v9 + 136) = 0;
  v9[15] = v9 + 17;
  *((_WORD *)v9 + 34) = 0;
  v9[9] = 0;
  *((_DWORD *)v9 + 20) = 0;
  *((_DWORD *)v9 + 32) = 64;
  *((_WORD *)v9 + 66) = 256;
  if ( FREB_LOG_NT_EVENT::InitializeInstance((FREB_LOG_NT_EVENT *)v9, a1, a2, a3, a4) >= 0 )
  {
    v11 = v9[5];
    v17[0] = 0;
    Key = CLKRHashTable::FindKey((char *)g_pFrebLogNtEventTable + 8, v11, v17);
    v10 = v17[0];
    if ( Key )
    {
      if ( !(unsigned int)CLKRHashTable::InsertRecord((char *)g_pFrebLogNtEventTable + 8, v9, 0) )
      {
        _InterlockedIncrement((volatile signed __int32 *)v9 + 1);
        FREB_LOG_NT_EVENT::RealLogEvent((FREB_LOG_NT_EVENT *)v9);
        goto LABEL_8;
      }
      v13 = v9[5];
      v17[0] = 0;
      v14 = CLKRHashTable::FindKey((char *)g_pFrebLogNtEventTable + 8, v13, v17);
      v10 = v17[0];
      if ( v14 )
        goto LABEL_8;
    }
    _InterlockedIncrement((volatile signed __int32 *)(v10 + 4));
  }
LABEL_8:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9, 0xFFFFFFFF) == 1 )
  {
    if ( *((_DWORD *)v9 + 1) )
      FREB_LOG_NT_EVENT::RealLogEvent((FREB_LOG_NT_EVENT *)v9);
    v15 = (void *)v9[9];
    if ( v15 )
    {
      operator delete(v15);
      v9[9] = 0;
    }
    BUFFER::~BUFFER((BUFFER *)(v9 + 11));
    STRU::~STRU((STRU *)(v9 + 1));
    operator delete(v9);
  }
  if ( v10 && !_InterlockedDecrement((volatile signed __int32 *)v10) )
  {
    if ( *(_DWORD *)(v10 + 4) )
      FREB_LOG_NT_EVENT::RealLogEvent((FREB_LOG_NT_EVENT *)v10);
    v16 = *(void **)(v10 + 72);
    if ( v16 )
    {
      operator delete(v16);
      *(_QWORD *)(v10 + 72) = 0;
    }
    BUFFER::~BUFFER((BUFFER *)(v10 + 88));
    STRU::~STRU((STRU *)(v10 + 8));
    operator delete((void *)v10);
  }
}

```

## disassembly

```asm
0x18000a4dc  mov     [rsp+arg_0], rbx
0x18000a4e1  mov     [rsp+arg_10], rbp
0x18000a4e6  push    rsi
0x18000a4e7  push    rdi
0x18000a4e8  push    r12
0x18000a4ea  push    r14
0x18000a4ec  push    r15
0x18000a4ee  sub     rsp, 40h
0x18000a4f2  mov     r15d, ecx
0x18000a4f5  mov     esi, r9d
0x18000a4f8  mov     ecx, 0C8h; Size
0x18000a4fd  mov     rbp, r8
0x18000a500  movzx   r14d, dx
0x18000a504  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a509  xor     r12d, r12d
0x18000a50c  mov     rbx, rax
0x18000a50f  test    rax, rax
0x18000a512  jz      loc_18000A689
0x18000a518  lea     rcx, [rax+8]
0x18000a51c  mov     qword ptr [rax], 1
0x18000a523  mov     edi, r12d
0x18000a526  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000a52c  lea     rax, [rbx+88h]
0x18000a533  mov     [rbx+40h], r12d
0x18000a537  mov     r9, rbp; unsigned __int16 **
0x18000a53a  mov     [rax], r12b
0x18000a53d  movzx   r8d, r14w; unsigned __int16
0x18000a541  mov     [rbx+78h], rax
0x18000a545  mov     edx, r15d; unsigned int
0x18000a548  mov     [rbx+44h], r12w
0x18000a54d  mov     rcx, rbx; this
0x18000a550  mov     [rbx+48h], r12
0x18000a554  mov     [rbx+50h], r12d
0x18000a558  mov     dword ptr [rbx+80h], 40h ; '@'
0x18000a562  mov     word ptr [rbx+84h], 100h
0x18000a56b  mov     [rsp+68h+var_48], esi; unsigned int
0x18000a56f  call    ?InitializeInstance@FREB_LOG_NT_EVENT@@QEAAJKGQEAPEBGK@Z; FREB_LOG_NT_EVENT::InitializeInstance(ulong,ushort,ushort const * * const,ulong)
0x18000a574  test    eax, eax
0x18000a576  js      short loc_18000A5F5
0x18000a578  mov     rcx, cs:?g_pFrebLogNtEventTable@@3PEAVFREB_LOG_NT_EVENT_TABLE@@EA; FREB_LOG_NT_EVENT_TABLE * g_pFrebLogNtEventTable
0x18000a57f  lea     r8, [rsp+68h+var_38]
0x18000a584  mov     rdx, [rbx+28h]
0x18000a588  add     rcx, 8
0x18000a58c  mov     [rsp+68h+var_38], r12
0x18000a591  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x18000a597  mov     rdi, [rsp+68h+var_38]
0x18000a59c  test    eax, eax
0x18000a59e  jz      short loc_18000A5F1
0x18000a5a0  mov     rcx, cs:?g_pFrebLogNtEventTable@@3PEAVFREB_LOG_NT_EVENT_TABLE@@EA; FREB_LOG_NT_EVENT_TABLE * g_pFrebLogNtEventTable
0x18000a5a7  xor     r8d, r8d
0x18000a5aa  add     rcx, 8
0x18000a5ae  mov     rdx, rbx
0x18000a5b1  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x18000a5b7  test    eax, eax
0x18000a5b9  jnz     short loc_18000A5C9
0x18000a5bb  lock inc dword ptr [rbx+4]
0x18000a5bf  mov     rcx, rbx; this
0x18000a5c2  call    ?RealLogEvent@FREB_LOG_NT_EVENT@@QEAAXXZ; FREB_LOG_NT_EVENT::RealLogEvent(void)
0x18000a5c7  jmp     short loc_18000A5F5
0x18000a5c9  mov     rcx, cs:?g_pFrebLogNtEventTable@@3PEAVFREB_LOG_NT_EVENT_TABLE@@EA; FREB_LOG_NT_EVENT_TABLE * g_pFrebLogNtEventTable
0x18000a5d0  lea     r8, [rsp+68h+var_38]
0x18000a5d5  mov     rdx, [rbx+28h]
0x18000a5d9  add     rcx, 8
0x18000a5dd  mov     [rsp+68h+var_38], r12
0x18000a5e2  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x18000a5e8  mov     rdi, [rsp+68h+var_38]
0x18000a5ed  test    eax, eax
0x18000a5ef  jnz     short loc_18000A5F5
0x18000a5f1  lock inc dword ptr [rdi+4]
0x18000a5f5  or      esi, 0FFFFFFFFh
0x18000a5f8  mov     eax, esi
0x18000a5fa  lock xadd [rbx], eax
0x18000a5fe  add     eax, esi
0x18000a600  jnz     short loc_18000A63E
0x18000a602  cmp     [rbx+4], r12d
0x18000a606  jz      short loc_18000A610
0x18000a608  mov     rcx, rbx; this
0x18000a60b  call    ?RealLogEvent@FREB_LOG_NT_EVENT@@QEAAXXZ; FREB_LOG_NT_EVENT::RealLogEvent(void)
0x18000a610  mov     rcx, [rbx+48h]; Block
0x18000a614  test    rcx, rcx
0x18000a617  jz      short loc_18000A622
0x18000a619  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a61e  mov     [rbx+48h], r12
0x18000a622  lea     rcx, [rbx+58h]
0x18000a626  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000a62c  lea     rcx, [rbx+8]
0x18000a630  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000a636  mov     rcx, rbx; Block
0x18000a639  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a63e  test    rdi, rdi
0x18000a641  jz      short loc_18000A689
0x18000a643  mov     eax, esi
0x18000a645  lock xadd [rdi], eax
0x18000a649  add     eax, esi
0x18000a64b  jnz     short loc_18000A689
0x18000a64d  cmp     [rdi+4], r12d
0x18000a651  jz      short loc_18000A65B
0x18000a653  mov     rcx, rdi; this
0x18000a656  call    ?RealLogEvent@FREB_LOG_NT_EVENT@@QEAAXXZ; FREB_LOG_NT_EVENT::RealLogEvent(void)
0x18000a65b  mov     rcx, [rdi+48h]; Block
0x18000a65f  test    rcx, rcx
0x18000a662  jz      short loc_18000A66D
0x18000a664  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a669  mov     [rdi+48h], r12
0x18000a66d  lea     rcx, [rdi+58h]
0x18000a671  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000a677  lea     rcx, [rdi+8]
0x18000a67b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000a681  mov     rcx, rdi; Block
0x18000a684  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a689  lea     r11, [rsp+68h+var_28]
0x18000a68e  mov     rbx, [r11+30h]
0x18000a692  mov     rbp, [r11+40h]
0x18000a696  mov     rsp, r11
0x18000a699  pop     r15
0x18000a69b  pop     r14
0x18000a69d  pop     r12
0x18000a69f  pop     rdi
0x18000a6a0  pop     rsi
0x18000a6a1  retn
```
