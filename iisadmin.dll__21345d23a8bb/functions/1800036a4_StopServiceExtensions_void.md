# StopServiceExtensions(void)

- ea: `0x1800036a4`
- end: `0x18000379e`
- name: `?StopServiceExtensions@@YAXXZ`
- size: `250`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x180001e60`

## callees

- `0x180001048`
- `0x1800036a4`
- `0x180005010`

## import_xrefs

- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x180003728`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x180003783`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x180003728`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x180003783`

## pseudocode

```c
void StopServiceExtensions(void)
{
  void *v0; // rcx
  __int64 v1; // rdi
  __int64 v2; // rbx
  __int64 v3; // rax

  while ( 1 )
  {
    v0 = g_piaecHead;
    if ( !g_piaecHead )
      break;
    v1 = *(_QWORD *)g_piaecHead;
    v2 = *((_QWORD *)g_piaecHead + 2);
    g_piaecHead = (void *)*((_QWORD *)g_piaecHead + 1);
    operator delete(v0);
    if ( *((_DWORD *)g_pEtwGlobalTracer + 2)
      && (*((_BYTE *)g_pEtwGlobalTracer + 40) & 2) != 0
      && *((_DWORD *)g_pEtwGlobalTracer + 11) >= 4u )
    {
      v3 = -1;
      do
        ++v3;
      while ( *(_WORD *)(v2 + 2 * v3) );
      CEtwTracer::EtwTraceEvent(
        (CEtwTracer *)g_pEtwGlobalTracer,
        (const struct _GUID *)IISAdminShutdownGuid,
        0x12u,
        v2,
        2 * v3 + 2,
        0,
        0);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 40LL))(v1);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
    if ( *((_DWORD *)g_pEtwGlobalTracer + 2)
      && (*((_BYTE *)g_pEtwGlobalTracer + 40) & 2) != 0
      && *((_DWORD *)g_pEtwGlobalTracer + 11) >= 4u )
    {
      CEtwTracer::EtwTraceEvent((CEtwTracer *)g_pEtwGlobalTracer, (const struct _GUID *)IISAdminShutdownGuid, 0x13u);
    }
  }
}

```

## disassembly

```asm
0x1800036a4  mov     [rsp+arg_0], rbx
0x1800036a9  mov     [rsp+arg_8], rsi
0x1800036ae  push    rdi
0x1800036af  sub     rsp, 40h
0x1800036b3  xor     esi, esi
0x1800036b5  mov     rcx, cs:?g_piaecHead@@3PEAU_IADMEXT_CONTAINER@@EA; Block
0x1800036bc  test    rcx, rcx
0x1800036bf  jz      loc_18000378E
0x1800036c5  mov     rax, [rcx+8]
0x1800036c9  mov     rdi, [rcx]
0x1800036cc  mov     rbx, [rcx+10h]
0x1800036d0  mov     cs:?g_piaecHead@@3PEAU_IADMEXT_CONTAINER@@EA, rax; _IADMEXT_CONTAINER * g_piaecHead
0x1800036d7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800036dc  mov     rcx, cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwGlobalTracer
0x1800036e3  cmp     [rcx+8], esi
0x1800036e6  jz      short loc_18000372E
0x1800036e8  test    byte ptr [rcx+28h], 2
0x1800036ec  jz      short loc_18000372E
0x1800036ee  cmp     dword ptr [rcx+2Ch], 4
0x1800036f2  jb      short loc_18000372E
0x1800036f4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800036f8  inc     rax
0x1800036fb  cmp     [rbx+rax*2], si
0x1800036ff  jnz     short loc_1800036F8
0x180003701  lea     rax, ds:2[rax*2]
0x180003709  mov     [rsp+48h+var_18], rsi
0x18000370e  mov     [rsp+48h+var_20], rsi
0x180003713  lea     rdx, IISAdminShutdownGuid
0x18000371a  mov     r9, rbx
0x18000371d  mov     [rsp+48h+var_28], rax
0x180003722  mov     r8d, 12h
0x180003728  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ; CEtwTracer::EtwTraceEvent(_GUID const *,ulong,...)
0x18000372e  mov     rax, [rdi]
0x180003731  mov     rcx, rdi
0x180003734  mov     rax, [rax+28h]
0x180003738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000373d  mov     rax, [rdi]
0x180003740  mov     rcx, rdi
0x180003743  mov     rax, [rax+10h]
0x180003747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000374c  mov     rcx, cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwGlobalTracer
0x180003753  cmp     [rcx+8], esi
0x180003756  jz      loc_1800036B5
0x18000375c  test    byte ptr [rcx+28h], 2
0x180003760  jz      loc_1800036B5
0x180003766  cmp     dword ptr [rcx+2Ch], 4
0x18000376a  jb      loc_1800036B5
0x180003770  xor     r9d, r9d
0x180003773  mov     [rsp+48h+var_28], rsi
0x180003778  lea     rdx, IISAdminShutdownGuid
0x18000377f  lea     r8d, [r9+13h]
0x180003783  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ; CEtwTracer::EtwTraceEvent(_GUID const *,ulong,...)
0x180003789  jmp     loc_1800036B5
0x18000378e  mov     rbx, [rsp+48h+arg_0]
0x180003793  mov     rsi, [rsp+48h+arg_8]
0x180003798  add     rsp, 40h
0x18000379c  pop     rdi
0x18000379d  retn
```
