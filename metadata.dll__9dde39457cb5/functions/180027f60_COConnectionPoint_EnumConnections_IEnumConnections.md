# COConnectionPoint::EnumConnections(IEnumConnections * *)

- ea: `0x180027f60`
- end: `0x18002809a`
- name: `?EnumConnections@COConnectionPoint@@UEAAJPEAPEAUIEnumConnections@@@Z`
- size: `314`
- prototype: `__int64 __fastcall(struct IUnknown *this, struct IEnumConnections **)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x1800089c8`
- `0x180008a08`
- `0x180008a14`
- `0x180027b40`
- `0x180027f60`
- `0x1800281dc`
- `0x180031010`

## import_xrefs

- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180028087`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180028087`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180027f8c`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180027f8c`

## pseudocode

```c
__int64 __fastcall COConnectionPoint::EnumConnections(struct IUnknown *this, struct IEnumConnections **a2)
{
  int v4; // ebx
  struct tagCONNECTDATA *v5; // rbp
  unsigned int v6; // r8d
  unsigned int i; // r9d
  struct IUnknownVtbl *lpVtbl; // rax
  __int64 v9; // rdx
  COEnumConnections *v10; // rax
  COEnumConnections *v11; // rax
  COEnumConnections *v12; // rsi

  if ( a2 )
  {
    v4 = -2147221500;
    CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)&g_LockSinkResource);
    *a2 = 0;
    if ( HIDWORD(this[5].lpVtbl) )
    {
      v5 = (struct tagCONNECTDATA *)operator new[](saturated_mul(HIDWORD(this[5].lpVtbl), 0x10u));
      if ( v5 )
      {
        v6 = 0;
        for ( i = 0; v6 < LODWORD(this[6].lpVtbl); ++v6 )
        {
          if ( i >= HIDWORD(this[5].lpVtbl) )
            break;
          lpVtbl = this[7].lpVtbl;
          if ( *((_DWORD *)&lpVtbl->AddRef + 4 * v6) )
          {
            v9 = i++;
            v5[v9].pUnk = (IUnknown *)*((_QWORD *)&lpVtbl->QueryInterface + 2 * v6);
            v5[v9].dwCookie = *((_DWORD *)&this[7].lpVtbl->AddRef + 4 * v6);
          }
        }
        v10 = (COEnumConnections *)operator new(0x28u);
        if ( v10 && (v11 = COEnumConnections::COEnumConnections(v10, this), (v12 = v11) != 0) )
        {
          v4 = COEnumConnections::Init(v11, HIDWORD(this[5].lpVtbl), v5, 0);
          if ( v4 >= 0 )
            v4 = (**(__int64 (__fastcall ***)(COEnumConnections *, GUID *, struct IEnumConnections **))v12)(
                   v12,
                   &IID_IEnumConnections,
                   a2);
        }
        else
        {
          v4 = -2147024882;
        }
        operator delete(v5);
      }
      else
      {
        v4 = -2147024882;
      }
    }
    CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)&g_LockSinkResource);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180027f60  push    rbx
0x180027f62  push    rbp
0x180027f63  push    rsi
0x180027f64  push    rdi
0x180027f65  push    r14
0x180027f67  sub     rsp, 20h
0x180027f6b  mov     r14, rdx
0x180027f6e  mov     rdi, rcx
0x180027f71  test    rdx, rdx
0x180027f74  jnz     short loc_180027F80
0x180027f76  mov     ebx, 80070057h
0x180027f7b  jmp     loc_18002808D
0x180027f80  lea     rcx, ?g_LockSinkResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockSinkResource
0x180027f87  mov     ebx, 80040004h
0x180027f8c  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180027f92  mov     qword ptr [r14], 0
0x180027f99  cmp     dword ptr [rdi+2Ch], 0
0x180027f9d  jz      loc_180028080
0x180027fa3  mov     ecx, [rdi+2Ch]
0x180027fa6  mov     eax, 10h
0x180027fab  mul     rcx
0x180027fae  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180027fb5  cmovb   rax, rcx
0x180027fb9  mov     rcx, rax; unsigned __int64
0x180027fbc  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180027fc1  mov     rbp, rax
0x180027fc4  test    rax, rax
0x180027fc7  jz      loc_18002807B
0x180027fcd  xor     r8d, r8d
0x180027fd0  xor     r9d, r9d
0x180027fd3  cmp     [rdi+30h], r8d
0x180027fd7  jbe     short loc_180028017
0x180027fd9  cmp     r9d, [rdi+2Ch]
0x180027fdd  jnb     short loc_180028017
0x180027fdf  mov     rax, [rdi+38h]
0x180027fe3  mov     ecx, r8d
0x180027fe6  add     rcx, rcx
0x180027fe9  cmp     dword ptr [rax+rcx*8+8], 0
0x180027fee  jz      short loc_18002800E
0x180027ff0  mov     rax, [rax+rcx*8]
0x180027ff4  mov     edx, r9d
0x180027ff7  add     rdx, rdx
0x180027ffa  inc     r9d
0x180027ffd  mov     [rbp+rdx*8+0], rax
0x180028002  mov     rax, [rdi+38h]
0x180028006  mov     ecx, [rax+rcx*8+8]
0x18002800a  mov     [rbp+rdx*8+8], ecx
0x18002800e  inc     r8d
0x180028011  cmp     r8d, [rdi+30h]
0x180028015  jb      short loc_180027FD9
0x180028017  mov     ecx, 28h ; '('; Size
0x18002801c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180028021  test    rax, rax
0x180028024  jz      short loc_18002806C
0x180028026  mov     rdx, rdi; struct IUnknown *
0x180028029  mov     rcx, rax; this
0x18002802c  call    ??0COEnumConnections@@QEAA@PEAUIUnknown@@@Z; COEnumConnections::COEnumConnections(IUnknown *)
0x180028031  mov     rsi, rax
0x180028034  test    rax, rax
0x180028037  jz      short loc_18002806C
0x180028039  mov     edx, [rdi+2Ch]; unsigned int
0x18002803c  xor     r9d, r9d; unsigned int
0x18002803f  mov     r8, rbp; struct tagCONNECTDATA *
0x180028042  mov     rcx, rax; this
0x180028045  call    ?Init@COEnumConnections@@QEAAJKPEAUtagCONNECTDATA@@K@Z; COEnumConnections::Init(ulong,tagCONNECTDATA *,ulong)
0x18002804a  mov     ebx, eax
0x18002804c  test    eax, eax
0x18002804e  js      short loc_180028071
0x180028050  mov     rax, [rsi]
0x180028053  lea     rdx, IID_IEnumConnections
0x18002805a  mov     r8, r14
0x18002805d  mov     rcx, rsi
0x180028060  mov     rax, [rax]
0x180028063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028068  mov     ebx, eax
0x18002806a  jmp     short loc_180028071
0x18002806c  mov     ebx, 8007000Eh
0x180028071  mov     rcx, rbp; Block
0x180028074  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180028079  jmp     short loc_180028080
0x18002807b  mov     ebx, 8007000Eh
0x180028080  lea     rcx, ?g_LockSinkResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockSinkResource
0x180028087  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18002808d  mov     eax, ebx
0x18002808f  add     rsp, 20h
0x180028093  pop     r14
0x180028095  pop     rdi
0x180028096  pop     rsi
0x180028097  pop     rbp
0x180028098  pop     rbx
0x180028099  retn
```
