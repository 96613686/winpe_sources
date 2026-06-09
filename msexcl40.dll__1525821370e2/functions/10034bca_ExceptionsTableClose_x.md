# ExceptionsTableClose(x)

- ea: `0x10034bca`
- end: `0x10034c15`
- name: `_ExceptionsTableClose@4`
- size: `75`
- prototype: `int __thiscall(_DWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callers

- `0x10029068`
- `0x10029730`
- `0x10029b60`
- `0x10034b1c`

## callees

- `0x10025ab7`
- `0x1002a7de`
- `0x10034bca`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x10034bdc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x10034bdc`
- `msjet40!__imp__JetCloseTable@8` at `0x10034c03`
- `msjet40!__imp__JetCloseTable@8` at `0x10034c03`
- `msjet40!__imp__JetSetSystemParameter@20` at `0x10034bf8`
- `msjet40!__imp__JetSetSystemParameter@20` at `0x10034bf8`

## pseudocode

```c
int __thiscall ExceptionsTableClose(JET_SESID *this)
{
  JET_SESID v2; // edi
  DWORD CurrentProcessId; // eax
  int v4; // eax

  if ( this )
  {
    if ( this[2] )
    {
      v2 = *this;
      CurrentProcessId = GetCurrentProcessId();
      v4 = ISAMDBFindTask(CurrentProcessId);
      if ( v4 )
        JetSetSystemParameter(v4 + 32, v2, 67, 0, 0);
      JetCloseTable(*this, this[2]);
    }
    MemFree(this);
  }
  return 0;
}

```

## disassembly

```asm
0x10034bca  mov     edi, edi
0x10034bcc  push    esi
0x10034bcd  mov     esi, ecx
0x10034bcf  test    esi, esi
0x10034bd1  jz      short loc_10034C11
0x10034bd3  cmp     dword ptr [esi+8], 0
0x10034bd7  jz      short loc_10034C0A
0x10034bd9  push    edi
0x10034bda  mov     edi, [esi]
0x10034bdc  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x10034be2  mov     ecx, eax
0x10034be4  call    _ISAMDBFindTask@4; ISAMDBFindTask(x)
0x10034be9  test    eax, eax
0x10034beb  jz      short loc_10034BFE
0x10034bed  push    0
0x10034bef  push    0
0x10034bf1  push    43h ; 'C'
0x10034bf3  push    edi
0x10034bf4  add     eax, 20h ; ' '
0x10034bf7  push    eax
0x10034bf8  call    ds:__imp__JetSetSystemParameter@20; JetSetSystemParameter(x,x,x,x,x)
0x10034bfe  push    dword ptr [esi+8]; tableid
0x10034c01  push    dword ptr [esi]; sesid
0x10034c03  call    ds:__imp__JetCloseTable@8; JetCloseTable(x,x)
0x10034c09  pop     edi
0x10034c0a  mov     ecx, esi
0x10034c0c  call    _MemFree@4; MemFree(x)
0x10034c11  xor     eax, eax
0x10034c13  pop     esi
0x10034c14  retn
```
