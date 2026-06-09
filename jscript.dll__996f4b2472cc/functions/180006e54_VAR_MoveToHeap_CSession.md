# VAR::MoveToHeap(CSession *)

- ea: `0x180006e54`
- end: `0x180006f1d`
- name: `?MoveToHeap@VAR@@QEAAJPEAVCSession@@@Z`
- size: `201`
- prototype: `__int64 __fastcall(VARIANTARG *pvarg, struct CSession *this)`
- caller_count: `7`
- callee_count: `7`
- tags: ``

## callers

- `0x1800049d0`
- `0x18000eea4`
- `0x1800442b0`
- `0x180062140`
- `0x180062870`
- `0x1800632d0`
- `0x18006b144`

## callees

- `0x180006dbc`
- `0x180006e54`
- `0x180007588`
- `0x18000aa10`
- `0x18000ba90`
- `0x180014cd0`
- `0x180073e80`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x180006ed9`
- `KERNEL32!TlsGetValue` at `0x180006ed9`

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
      LODWORD(v5) = (unsigned int)CbVBArray(*((struct tagSAFEARRAY **)v4 + 1));
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
0x180006e54  mov     [rsp+arg_0], rbx
0x180006e59  push    rdi
0x180006e5a  sub     rsp, 20h
0x180006e5e  mov     rdi, rcx
0x180006e61  test    rdx, rdx
0x180006e64  jz      short loc_180006ED3
0x180006e66  mov     rcx, rdx; this
0x180006e69  call    ?GetGcAlloc@CSession@@QEAAPEAVGcAlloc@@XZ; CSession::GetGcAlloc(void)
0x180006e6e  mov     rbx, rax
0x180006e71  test    rax, rax
0x180006e74  jz      loc_180006F0E
0x180006e7a  mov     rcx, rbx; this
0x180006e7d  call    ?PvarAlloc@GcAlloc@@QEAAPEAVVAR@@XZ; GcAlloc::PvarAlloc(void)
0x180006e82  test    rax, rax
0x180006e85  jz      loc_180006F0E
0x180006e8b  movups  xmm0, xmmword ptr [rdi]
0x180006e8e  mov     ecx, 8
0x180006e93  movups  xmmword ptr [rax], xmm0
0x180006e96  movsd   xmm1, qword ptr [rdi+10h]
0x180006e9b  movsd   qword ptr [rax+10h], xmm1
0x180006ea0  mov     word ptr [rdi], 80h
0x180006ea5  mov     [rdi+8], rax
0x180006ea9  cmp     cx, [rax]
0x180006eac  jnz     short loc_180006EF7
0x180006eae  mov     rdx, [rax+8]
0x180006eb2  test    rdx, rdx
0x180006eb5  jz      short loc_180006ED1
0x180006eb7  mov     edx, [rdx-4]; int
0x180006eba  mov     rcx, [rbx+10h]; this
0x180006ebe  call    ?RecordSysAlloc@GcContext@@QEAAXJ@Z; GcContext::RecordSysAlloc(long)
0x180006ec3  xor     eax, eax
0x180006ec5  mov     rbx, [rsp+28h+arg_0]
0x180006eca  add     rsp, 20h
0x180006ece  pop     rdi
0x180006ecf  retn
0x180006ed1  jmp     short loc_180006EBA
0x180006ed3  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x180006ed9  call    cs:__imp_TlsGetValue
0x180006ee0  nop     dword ptr [rax+rax+00h]
0x180006ee5  mov     rcx, rax; struct ThreadGlobals *
0x180006ee8  call    ?GetAllocator@GcAlloc@@SAPEAV1@PEAVThreadGlobals@@@Z; GcAlloc::GetAllocator(ThreadGlobals *)
0x180006eed  mov     rbx, rax
0x180006ef0  test    rax, rax
0x180006ef3  jnz     short loc_180006E7A
0x180006ef5  jmp     short loc_180006EC3
0x180006ef7  mov     ecx, 200Ch
0x180006efc  cmp     cx, [rax]
0x180006eff  jnz     short loc_180006EC3
0x180006f01  mov     rcx, [rax+8]; struct tagSAFEARRAY *
0x180006f05  call    ?CbVBArray@@YAJPEAUtagSAFEARRAY@@@Z; CbVBArray(tagSAFEARRAY *)
0x180006f0a  mov     edx, eax
0x180006f0c  jmp     short loc_180006EBA
0x180006f0e  mov     rcx, rdi; pvarg
0x180006f11  call    ?Clear@VAR@@QEAAXXZ; VAR::Clear(void)
0x180006f16  mov     eax, 8007000Eh
0x180006f1b  jmp     short loc_180006EC5
```
