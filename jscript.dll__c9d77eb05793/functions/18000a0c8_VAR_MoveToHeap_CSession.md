# VAR::MoveToHeap(CSession *)

- ea: `0x18000a0c8`
- end: `0x18000a186`
- name: `?MoveToHeap@VAR@@QEAAJPEAVCSession@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(VARIANTARG *pvarg, struct CSession *this)`
- caller_count: `7`
- callee_count: `7`
- tags: ``

## callers

- `0x1800057f0`
- `0x180011c70`
- `0x180043510`
- `0x180060f20`
- `0x180061640`
- `0x180062080`
- `0x180069e04`

## callees

- `0x18000a040`
- `0x18000a0c8`
- `0x18000a4d0`
- `0x18000d820`
- `0x18000e870`
- `0x180033780`
- `0x180072a38`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x18000a148`
- `KERNEL32!TlsGetValue` at `0x18000a148`

## pseudocode

```c
__int64 __fastcall VAR::MoveToHeap(VARIANTARG *pvarg, struct CSession *this)
{
  struct GcAlloc *GcAlloc; // rbx
  struct VAR *v4; // rax
  __int64 v5; // rdx
  struct ThreadGlobals *Value; // rax

  if ( this )
  {
    GcAlloc = CSession::GetGcAlloc(this);
    if ( !GcAlloc )
      goto LABEL_14;
  }
  else
  {
    Value = (struct ThreadGlobals *)TlsGetValue(g_luTls);
    GcAlloc = GcAlloc::GetAllocator(Value);
    if ( !GcAlloc )
      return 0;
  }
  v4 = GcAlloc::PvarAlloc(GcAlloc);
  if ( v4 )
  {
    *(_OWORD *)v4 = *(_OWORD *)&pvarg->vt;
    *((_QWORD *)v4 + 2) = pvarg->pRecInfo;
    pvarg->vt = 128;
    pvarg->llVal = (LONGLONG)v4;
    if ( *(_WORD *)v4 == 8 )
    {
      v5 = *((_QWORD *)v4 + 1);
      if ( v5 )
        LODWORD(v5) = *(_DWORD *)(v5 - 4);
    }
    else
    {
      if ( *(_WORD *)v4 != 8204 )
        return 0;
      LODWORD(v5) = CbVBArray(*((struct tagSAFEARRAY **)v4 + 1));
    }
    GcContext::RecordSysAlloc(*((GcContext **)GcAlloc + 2), v5);
    return 0;
  }
LABEL_14:
  VAR::Clear(pvarg);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000a0c8  mov     [rsp+arg_0], rbx
0x18000a0cd  push    rdi
0x18000a0ce  sub     rsp, 20h
0x18000a0d2  mov     rdi, rcx
0x18000a0d5  test    rdx, rdx
0x18000a0d8  jz      short loc_18000A142
0x18000a0da  mov     rcx, rdx; this
0x18000a0dd  call    ?GetGcAlloc@CSession@@QEAAPEAVGcAlloc@@XZ; CSession::GetGcAlloc(void)
0x18000a0e2  mov     rbx, rax
0x18000a0e5  test    rax, rax
0x18000a0e8  jz      loc_18000A177
0x18000a0ee  mov     rcx, rbx; this
0x18000a0f1  call    ?PvarAlloc@GcAlloc@@QEAAPEAVVAR@@XZ; GcAlloc::PvarAlloc(void)
0x18000a0f6  test    rax, rax
0x18000a0f9  jz      short loc_18000A177
0x18000a0fb  movups  xmm0, xmmword ptr [rdi]
0x18000a0fe  mov     ecx, 8
0x18000a103  movups  xmmword ptr [rax], xmm0
0x18000a106  movsd   xmm1, qword ptr [rdi+10h]
0x18000a10b  movsd   qword ptr [rax+10h], xmm1
0x18000a110  mov     word ptr [rdi], 80h
0x18000a115  mov     [rdi+8], rax
0x18000a119  cmp     cx, [rax]
0x18000a11c  jnz     short loc_18000A160
0x18000a11e  mov     rdx, [rax+8]
0x18000a122  test    rdx, rdx
0x18000a125  jz      short loc_18000A140
0x18000a127  mov     edx, [rdx-4]; int
0x18000a12a  mov     rcx, [rbx+10h]; this
0x18000a12e  call    ?RecordSysAlloc@GcContext@@QEAAXJ@Z; GcContext::RecordSysAlloc(long)
0x18000a133  xor     eax, eax
0x18000a135  mov     rbx, [rsp+28h+arg_0]
0x18000a13a  add     rsp, 20h
0x18000a13e  pop     rdi
0x18000a13f  retn
0x18000a140  jmp     short loc_18000A12A
0x18000a142  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x18000a148  call    cs:__imp_TlsGetValue
0x18000a14e  mov     rcx, rax; struct ThreadGlobals *
0x18000a151  call    ?GetAllocator@GcAlloc@@SAPEAV1@PEAVThreadGlobals@@@Z; GcAlloc::GetAllocator(ThreadGlobals *)
0x18000a156  mov     rbx, rax
0x18000a159  test    rax, rax
0x18000a15c  jnz     short loc_18000A0EE
0x18000a15e  jmp     short loc_18000A133
0x18000a160  mov     ecx, 200Ch
0x18000a165  cmp     cx, [rax]
0x18000a168  jnz     short loc_18000A133
0x18000a16a  mov     rcx, [rax+8]; struct tagSAFEARRAY *
0x18000a16e  call    ?CbVBArray@@YAJPEAUtagSAFEARRAY@@@Z; CbVBArray(tagSAFEARRAY *)
0x18000a173  mov     edx, eax
0x18000a175  jmp     short loc_18000A12A
0x18000a177  mov     rcx, rdi; pvarg
0x18000a17a  call    ?Clear@VAR@@QEAAXXZ; VAR::Clear(void)
0x18000a17f  mov     eax, 8007000Eh
0x18000a184  jmp     short loc_18000A135
```
