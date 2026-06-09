# W3_CONNECTION::OnDisconnect(void *)

- ea: `0x18002b930`
- end: `0x18002b9a4`
- name: `?OnDisconnect@W3_CONNECTION@@SAXPEAX@Z`
- size: `116`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18002b930`
- `0x180038010`

## import_xrefs

- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x18002b998`

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
0x18002b930  mov     [rsp+arg_0], rbx
0x18002b935  push    rdi
0x18002b936  sub     rsp, 20h
0x18002b93a  xor     eax, eax
0x18002b93c  mov     rbx, rcx
0x18002b93f  xchg    eax, [rcx+1Ch]
0x18002b942  cmp     qword ptr [rcx+60h], 0
0x18002b947  jz      short loc_18002B984
0x18002b949  mov     rdx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18002b950  xor     edi, edi
0x18002b952  cmp     [rdx+260h], edi
0x18002b958  jbe     short loc_18002B984
0x18002b95a  mov     rax, [rbx+68h]
0x18002b95e  mov     rcx, [rax+rdi*8]
0x18002b962  test    rcx, rcx
0x18002b965  jz      short loc_18002B97A
0x18002b967  mov     rax, [rcx]
0x18002b96a  mov     rax, [rax+8]
0x18002b96e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b973  mov     rdx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18002b97a  inc     edi
0x18002b97c  cmp     edi, [rdx+260h]
0x18002b982  jb      short loc_18002B95A
0x18002b984  mov     rcx, cs:?sm_pConnectionTable@W3_CONNECTION@@0PEAVW3_CONNECTION_HASH@@EA; W3_CONNECTION_HASH * W3_CONNECTION::sm_pConnectionTable
0x18002b98b  mov     rdx, rbx
0x18002b98e  mov     rbx, [rsp+28h+arg_0]
0x18002b993  add     rsp, 20h
0x18002b997  pop     rdi
0x18002b998  jmp     cs:__imp_?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z; CLKRHashTable::DeleteRecord(void const *)
```
