# NameTbl::~NameTbl(void)

- ea: `0x18000f010`
- end: `0x18000f115`
- name: `??1NameTbl@@MEAA@XZ`
- size: `261`
- prototype: `void __fastcall(NameTbl *__hidden this)`
- caller_count: `10`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180019be8`
- `0x180041670`
- `0x180047df8`
- `0x180047fd8`
- `0x180049d00`
- `0x180049d40`
- `0x180049ea0`
- `0x18004a608`
- `0x1800523a0`
- `0x180061d30`

## callees

- `0x18000f010`
- `0x18000f120`
- `0x18000f5e0`
- `0x18000f630`
- `0x180034200`
- `0x180034b80`
- `0x180057694`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000f08c`
- `KERNEL32!DeleteCriticalSection` at `0x18000f08c`

## pseudocode

```c
void __fastcall NameTbl::~NameTbl(NameTbl *this)
{
  __int64 v2; // rsi
  _QWORD *v3; // rcx
  __int64 v4; // rdi
  __int64 v5; // rax

  *(_QWORD *)this = &NameTbl::`vftable';
  NameTbl::Close(this);
  _InterlockedDecrement(&g_cLibRef);
  v2 = *((_QWORD *)this + 9);
  *((_QWORD *)this + 8) = &IScavenger::`vftable';
  if ( v2 && (unsigned int)MUTX::Enter((MUTX *)(v2 + 56)) )
  {
    v3 = (_QWORD *)*((_QWORD *)this + 11);
    if ( v3 )
    {
      *v3 = *((_QWORD *)this + 10);
      v5 = *((_QWORD *)this + 10);
      *((_QWORD *)this + 11) = 0;
      if ( v5 )
      {
        *(_QWORD *)(v5 + 24) = v3;
        *((_QWORD *)this + 10) = 0;
      }
      else if ( v3 == (_QWORD *)(v2 + 32) )
      {
        if ( (unsigned int)GcContext::FBaseThread((GcContext *)v2) )
        {
          if ( (*(_BYTE *)(v2 + 12) & 8) == 0 )
            GcContext::Reclaim((GcContext *)v2, 1);
        }
        else
        {
          *(_DWORD *)(v2 + 8) = 1;
        }
      }
    }
    MUTX::Leave((MUTX *)(v2 + 56));
  }
  v4 = *((_QWORD *)this + 9);
  if ( v4 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4, 0xFFFFFFFF) == 1 )
    {
      if ( *(_BYTE *)(v4 + 97) )
        DeleteCriticalSection((LPCRITICAL_SECTION)(v4 + 56));
      operator delete((void *)v4);
    }
    *((_QWORD *)this + 9) = 0;
  }
}

```

## disassembly

```asm
0x18000f010  mov     [rsp+arg_8], rbx
0x18000f015  mov     [rsp+arg_10], rsi
0x18000f01a  push    rdi
0x18000f01b  sub     rsp, 20h
0x18000f01f  lea     rax, ??_7NameTbl@@6B@; const NameTbl::`vftable'
0x18000f026  mov     rbx, rcx
0x18000f029  mov     [rcx], rax
0x18000f02c  call    ?Close@NameTbl@@MEAAXXZ; NameTbl::Close(void)
0x18000f031  lock dec cs:?g_cLibRef@@3JA; long g_cLibRef
0x18000f038  lea     rax, ??_7IScavenger@@6B@; const IScavenger::`vftable'
0x18000f03f  mov     rsi, [rbx+48h]
0x18000f043  mov     [rbx+40h], rax
0x18000f047  test    rsi, rsi
0x18000f04a  jz      short loc_18000F06B
0x18000f04c  lea     rcx, [rsi+38h]; this
0x18000f050  call    ?Enter@MUTX@@QEAAHXZ; MUTX::Enter(void)
0x18000f055  test    eax, eax
0x18000f057  jz      short loc_18000F06B
0x18000f059  mov     rcx, [rbx+58h]
0x18000f05d  test    rcx, rcx
0x18000f060  jnz     short loc_18000F0B2
0x18000f062  lea     rcx, [rsi+38h]; this
0x18000f066  call    ?Leave@MUTX@@QEAAXXZ; MUTX::Leave(void)
0x18000f06b  mov     rdi, [rbx+48h]
0x18000f06f  test    rdi, rdi
0x18000f072  jz      short loc_18000F0A2
0x18000f074  mov     eax, 0FFFFFFFFh
0x18000f079  lock xadd [rdi], eax
0x18000f07d  cmp     eax, 1
0x18000f080  jnz     short loc_18000F09A
0x18000f082  cmp     byte ptr [rdi+61h], 0
0x18000f086  lea     rcx, [rdi+38h]; lpCriticalSection
0x18000f08a  jz      short loc_18000F092
0x18000f08c  call    cs:__imp_DeleteCriticalSection
0x18000f092  mov     rcx, rdi; Block
0x18000f095  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f09a  mov     qword ptr [rbx+48h], 0
0x18000f0a2  mov     rbx, [rsp+28h+arg_8]
0x18000f0a7  mov     rsi, [rsp+28h+arg_10]
0x18000f0ac  add     rsp, 20h
0x18000f0b0  pop     rdi
0x18000f0b1  retn
0x18000f0b2  mov     rax, [rbx+50h]
0x18000f0b6  mov     [rcx], rax
0x18000f0b9  mov     rax, [rbx+50h]
0x18000f0bd  mov     qword ptr [rbx+58h], 0
0x18000f0c5  test    rax, rax
0x18000f0c8  jz      short loc_18000F0D8
0x18000f0ca  mov     [rax+18h], rcx
0x18000f0ce  mov     qword ptr [rbx+50h], 0
0x18000f0d6  jmp     short loc_18000F062
0x18000f0d8  lea     rax, [rsi+20h]
0x18000f0dc  cmp     rcx, rax
0x18000f0df  jnz     short loc_18000F062
0x18000f0e1  mov     rcx, rsi; this
0x18000f0e4  call    ?FBaseThread@GcContext@@QEAAHXZ; GcContext::FBaseThread(void)
0x18000f0e9  test    eax, eax
0x18000f0eb  jz      short loc_18000F109
0x18000f0ed  test    byte ptr [rsi+0Ch], 8
0x18000f0f1  jnz     loc_18000F062
0x18000f0f7  mov     edx, 1; int
0x18000f0fc  mov     rcx, rsi; this
0x18000f0ff  call    ?Reclaim@GcContext@@QEAAHJ@Z; GcContext::Reclaim(long)
0x18000f104  jmp     loc_18000F062
0x18000f109  mov     dword ptr [rsi+8], 1
0x18000f110  jmp     loc_18000F062
```
