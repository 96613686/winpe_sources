# CASFReader::GetCurFile(ushort * *,_AMMediaType *)

- ea: `0x180009990`
- end: `0x180009a41`
- name: `?GetCurFile@CASFReader@@UEAAJPEAPEAGPEAU_AMMediaType@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(CASFReader *__hidden this, unsigned __int16 **, struct _AMMediaType *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180002660`
- `0x180009990`
- `0x18001f010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1800099f1`
- `ole32!CoTaskMemAlloc` at `0x1800099f1`

## pseudocode

```c
__int64 __fastcall CASFReader::GetCurFile(CASFReader *this, unsigned __int16 **a2, struct _AMMediaType *a3)
{
  __int64 v7; // rcx
  __int64 v8; // rax
  unsigned __int64 v9; // r14
  unsigned __int16 *v10; // rax

  if ( *((_QWORD *)this + 43) )
    return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 44) + 32LL))(*((_QWORD *)this + 44));
  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v7 = *((_QWORD *)this + 15);
  if ( v7 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(v7 + 2 * v8) );
    v9 = v8 + 1;
    v10 = (unsigned __int16 *)CoTaskMemAlloc(2 * (v8 + 1));
    *a2 = v10;
    if ( v10 )
      StringCchCopyW(v10, v9, *((const unsigned __int16 **)this + 15));
  }
  if ( a3 )
  {
    a3->majortype = GUID_NULL;
    a3->pUnk = 0;
    a3->lSampleSize = 0;
    a3->subtype = GUID_NULL;
    a3->cbFormat = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180009990  push    rbx
0x180009992  push    rbp
0x180009993  push    rsi
0x180009994  push    rdi
0x180009995  push    r14
0x180009997  sub     rsp, 20h
0x18000999b  xor     ebp, ebp
0x18000999d  mov     rbx, r8
0x1800099a0  mov     rdi, rdx
0x1800099a3  mov     rsi, rcx
0x1800099a6  cmp     [rcx+158h], rbp
0x1800099ad  jz      short loc_1800099C4
0x1800099af  mov     rcx, [rcx+160h]
0x1800099b6  mov     rax, [rcx]
0x1800099b9  mov     rax, [rax+20h]
0x1800099bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099c2  jmp     short loc_180009A36
0x1800099c4  test    rdi, rdi
0x1800099c7  jnz     short loc_1800099D0
0x1800099c9  mov     eax, 80004003h
0x1800099ce  jmp     short loc_180009A36
0x1800099d0  mov     [rdx], rbp
0x1800099d3  mov     rcx, [rcx+78h]
0x1800099d7  test    rcx, rcx
0x1800099da  jz      short loc_180009A0E
0x1800099dc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800099e0  inc     rax
0x1800099e3  cmp     [rcx+rax*2], bp
0x1800099e7  jnz     short loc_1800099E0
0x1800099e9  lea     r14, [rax+1]
0x1800099ed  lea     rcx, [r14+r14]; cb
0x1800099f1  call    cs:__imp_CoTaskMemAlloc
0x1800099f7  mov     [rdi], rax
0x1800099fa  test    rax, rax
0x1800099fd  jz      short loc_180009A0E
0x1800099ff  mov     r8, [rsi+78h]; unsigned __int16 *
0x180009a03  mov     rdx, r14; unsigned __int64
0x180009a06  mov     rcx, rax; unsigned __int16 *
0x180009a09  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009a0e  test    rbx, rbx
0x180009a11  jz      short loc_180009A34
0x180009a13  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180009a1a  movdqu  xmmword ptr [rbx], xmm0
0x180009a1e  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x180009a25  mov     [rbx+40h], rbp
0x180009a29  mov     [rbx+28h], ebp
0x180009a2c  movdqu  xmmword ptr [rbx+10h], xmm1
0x180009a31  mov     [rbx+48h], ebp
0x180009a34  xor     eax, eax
0x180009a36  add     rsp, 20h
0x180009a3a  pop     r14
0x180009a3c  pop     rdi
0x180009a3d  pop     rsi
0x180009a3e  pop     rbp
0x180009a3f  pop     rbx
0x180009a40  retn
```
