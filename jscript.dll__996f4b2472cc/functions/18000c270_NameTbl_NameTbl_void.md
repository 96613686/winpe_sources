# NameTbl::~NameTbl(void)

- ea: `0x18000c270`
- end: `0x18000c380`
- name: `??1NameTbl@@MEAA@XZ`
- size: `272`
- prototype: `void __fastcall(NameTbl *__hidden this)`
- caller_count: `10`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180016c08`
- `0x180042b00`
- `0x180048b18`
- `0x180048cf8`
- `0x18004a900`
- `0x18004a9d0`
- `0x18004aa60`
- `0x18004b378`
- `0x18005316c`
- `0x180062f70`

## callees

- `0x18000c270`
- `0x18000c390`
- `0x18000c860`
- `0x18000c8c0`
- `0x18003ba0c`
- `0x18003bd60`
- `0x1800585c4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000c2ec`
- `KERNEL32!DeleteCriticalSection` at `0x18000c2ec`

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
0x18000c270  mov     [rsp+arg_8], rbx
0x18000c275  mov     [rsp+arg_10], rsi
0x18000c27a  push    rdi
0x18000c27b  sub     rsp, 20h
0x18000c27f  lea     rax, ??_7NameTbl@@6B@; const NameTbl::`vftable'
0x18000c286  mov     rbx, rcx
0x18000c289  mov     [rcx], rax
0x18000c28c  call    ?Close@NameTbl@@MEAAXXZ; NameTbl::Close(void)
0x18000c291  lock dec cs:?g_cLibRef@@3JA; long g_cLibRef
0x18000c298  lea     rax, ??_7IScavenger@@6B@; const IScavenger::`vftable'
0x18000c29f  mov     rsi, [rbx+48h]
0x18000c2a3  mov     [rbx+40h], rax
0x18000c2a7  test    rsi, rsi
0x18000c2aa  jz      short loc_18000C2CB
0x18000c2ac  lea     rcx, [rsi+38h]; this
0x18000c2b0  call    ?Enter@MUTX@@QEAAHXZ; MUTX::Enter(void)
0x18000c2b5  test    eax, eax
0x18000c2b7  jz      short loc_18000C2CB
0x18000c2b9  mov     rcx, [rbx+58h]
0x18000c2bd  test    rcx, rcx
0x18000c2c0  jnz     short loc_18000C319
0x18000c2c2  lea     rcx, [rsi+38h]; this
0x18000c2c6  call    ?Leave@MUTX@@QEAAXXZ; MUTX::Leave(void)
0x18000c2cb  mov     rdi, [rbx+48h]
0x18000c2cf  test    rdi, rdi
0x18000c2d2  jz      short loc_18000C308
0x18000c2d4  mov     eax, 0FFFFFFFFh
0x18000c2d9  lock xadd [rdi], eax
0x18000c2dd  cmp     eax, 1
0x18000c2e0  jnz     short loc_18000C300
0x18000c2e2  cmp     byte ptr [rdi+61h], 0
0x18000c2e6  lea     rcx, [rdi+38h]; lpCriticalSection
0x18000c2ea  jz      short loc_18000C2F8
0x18000c2ec  call    cs:__imp_DeleteCriticalSection
0x18000c2f3  nop     dword ptr [rax+rax+00h]
0x18000c2f8  mov     rcx, rdi; Block
0x18000c2fb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c300  mov     qword ptr [rbx+48h], 0
0x18000c308  mov     rbx, [rsp+28h+arg_8]
0x18000c30d  mov     rsi, [rsp+28h+arg_10]
0x18000c312  add     rsp, 20h
0x18000c316  pop     rdi
0x18000c317  retn
0x18000c319  mov     rax, [rbx+50h]
0x18000c31d  mov     [rcx], rax
0x18000c320  mov     rax, [rbx+50h]
0x18000c324  mov     qword ptr [rbx+58h], 0
0x18000c32c  test    rax, rax
0x18000c32f  jz      short loc_18000C33F
0x18000c331  mov     [rax+18h], rcx
0x18000c335  mov     qword ptr [rbx+50h], 0
0x18000c33d  jmp     short loc_18000C2C2
0x18000c33f  lea     rax, [rsi+20h]
0x18000c343  cmp     rcx, rax
0x18000c346  jnz     loc_18000C2C2
0x18000c34c  mov     rcx, rsi; this
0x18000c34f  call    ?FBaseThread@GcContext@@QEAAHXZ; GcContext::FBaseThread(void)
0x18000c354  test    eax, eax
0x18000c356  jz      short loc_18000C374
0x18000c358  test    byte ptr [rsi+0Ch], 8
0x18000c35c  jnz     loc_18000C2C2
0x18000c362  mov     edx, 1; int
0x18000c367  mov     rcx, rsi; this
0x18000c36a  call    ?Reclaim@GcContext@@QEAAHJ@Z; GcContext::Reclaim(long)
0x18000c36f  jmp     loc_18000C2C2
0x18000c374  mov     dword ptr [rsi+8], 1
0x18000c37b  jmp     loc_18000C2C2
```
