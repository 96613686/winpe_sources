# W3_CONNECTION::OnDisconnect(void *)

- ea: `0x1800294a0`
- end: `0x18002950f`
- name: `?OnDisconnect@W3_CONNECTION@@SAXPEAX@Z`
- size: `111`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800294a0`
- `0x180035010`

## import_xrefs

- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180029508`

## pseudocode

```c
void __fastcall W3_CONNECTION::OnDisconnect(volatile __int32 *a1)
{
  W3_SERVER *v2; // rdx
  __int64 i; // rdi
  __int64 v4; // rcx

  _InterlockedExchange(a1 + 7, 0);
  if ( *((_QWORD *)a1 + 12) )
  {
    v2 = g_pW3Server;
    for ( i = 0; (unsigned int)i < *((_DWORD *)v2 + 152); i = (unsigned int)(i + 1) )
    {
      v4 = *(_QWORD *)(*((_QWORD *)a1 + 13) + 8 * i);
      if ( v4 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
        v2 = g_pW3Server;
      }
    }
  }
  CLKRHashTable::DeleteRecord(W3_CONNECTION::sm_pConnectionTable, a1);
}

```

## disassembly

```asm
0x1800294a0  mov     [rsp+arg_0], rbx
0x1800294a5  push    rdi
0x1800294a6  sub     rsp, 20h
0x1800294aa  xor     eax, eax
0x1800294ac  mov     rbx, rcx
0x1800294af  xchg    eax, [rcx+1Ch]
0x1800294b2  cmp     qword ptr [rcx+60h], 0
0x1800294b7  jz      short loc_1800294F4
0x1800294b9  mov     rdx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x1800294c0  xor     edi, edi
0x1800294c2  cmp     [rdx+260h], edi
0x1800294c8  jbe     short loc_1800294F4
0x1800294ca  mov     rax, [rbx+68h]
0x1800294ce  mov     rcx, [rax+rdi*8]
0x1800294d2  test    rcx, rcx
0x1800294d5  jz      short loc_1800294EA
0x1800294d7  mov     rax, [rcx]
0x1800294da  mov     rax, [rax+8]
0x1800294de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800294e3  mov     rdx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x1800294ea  inc     edi
0x1800294ec  cmp     edi, [rdx+260h]
0x1800294f2  jb      short loc_1800294CA
0x1800294f4  mov     rcx, cs:?sm_pConnectionTable@W3_CONNECTION@@0PEAVW3_CONNECTION_HASH@@EA; W3_CONNECTION_HASH * W3_CONNECTION::sm_pConnectionTable
0x1800294fb  mov     rdx, rbx
0x1800294fe  mov     rbx, [rsp+28h+arg_0]
0x180029503  add     rsp, 20h
0x180029507  pop     rdi
0x180029508  jmp     cs:__imp_?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z; CLKRHashTable::DeleteRecord(void const *)
```
