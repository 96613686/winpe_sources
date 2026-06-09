# SyncContext_DestroySyncItemIDArray(ushort * *,ulong)

- ea: `0x18003dbbc`
- end: `0x18003dc04`
- name: `?SyncContext_DestroySyncItemIDArray@@YAXPEAPEAGK@Z`
- size: `72`
- prototype: `void __fastcall(unsigned __int16 **pv, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800195f0`
- `0x180022420`

## callees

- `0x18003dbbc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dbdf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dbee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dbdf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dbee`

## pseudocode

```c
void __fastcall SyncContext_DestroySyncItemIDArray(unsigned __int16 **pv, unsigned int a2)
{
  __int64 i; // rdi

  if ( pv )
  {
    for ( i = 0; (unsigned int)i < a2; i = (unsigned int)(i + 1) )
      CoTaskMemFree(pv[i]);
    CoTaskMemFree(pv);
  }
}

```

## disassembly

```asm
0x18003dbbc  test    rcx, rcx
0x18003dbbf  jz      short locret_18003DC03
0x18003dbc1  mov     [rsp+arg_0], rbx
0x18003dbc6  mov     [rsp+arg_8], rsi
0x18003dbcb  push    rdi
0x18003dbcc  sub     rsp, 20h
0x18003dbd0  xor     edi, edi
0x18003dbd2  mov     esi, edx
0x18003dbd4  mov     rbx, rcx
0x18003dbd7  test    edx, edx
0x18003dbd9  jz      short loc_18003DBEB
0x18003dbdb  mov     rcx, [rbx+rdi*8]; pv
0x18003dbdf  call    cs:__imp_CoTaskMemFree
0x18003dbe5  inc     edi
0x18003dbe7  cmp     edi, esi
0x18003dbe9  jb      short loc_18003DBDB
0x18003dbeb  mov     rcx, rbx; pv
0x18003dbee  call    cs:__imp_CoTaskMemFree
0x18003dbf4  mov     rbx, [rsp+28h+arg_0]
0x18003dbf9  mov     rsi, [rsp+28h+arg_8]
0x18003dbfe  add     rsp, 20h
0x18003dc02  pop     rdi
0x18003dc03  retn
```
