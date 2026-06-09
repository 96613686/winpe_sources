# TerminateReadLog

- ea: `0x18000d8c0`
- end: `0x18000d939`
- name: `TerminateReadLog`
- size: `121`
- prototype: `BOOL __stdcall(PVOID pvCursorContext)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000aec0`

## callees

- `0x18000d8c0`
- `0x1800101c8`
- `0x180013058`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d90c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d924`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d90c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d924`

## pseudocode

```c
BOOL __stdcall TerminateReadLog(PVOID pvCursorContext)
{
  volatile signed __int32 *v1; // rbx

  if ( pvCursorContext
    && *((_DWORD *)pvCursorContext + 4) == -1040322545
    && *((_DWORD *)pvCursorContext + 5) == 224
    && (*((_BYTE *)pvCursorContext + 28) & 0x14) != 0 )
  {
    v1 = (volatile signed __int32 *)*((_QWORD *)pvCursorContext + 24);
    _InterlockedIncrement(v1 + 27);
    if ( v1 == *((volatile signed __int32 **)pvCursorContext + 24) )
      CClfsMarshallingContext::FreeIocb((CClfsMarshallingContext *)v1, (struct CLogIocb *)pvCursorContext);
    CClfsMarshallingContext::Release((CClfsMarshallingContext *)v1);
    SetLastError(0);
    return 1;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x18000d8c0  push    rbx
0x18000d8c2  sub     rsp, 20h
0x18000d8c6  test    rcx, rcx
0x18000d8c9  jz      short loc_18000D91F
0x18000d8cb  cmp     dword ptr [rcx+10h], 0C1FDF00Fh
0x18000d8d2  jnz     short loc_18000D91F
0x18000d8d4  cmp     dword ptr [rcx+14h], 0E0h
0x18000d8db  jnz     short loc_18000D91F
0x18000d8dd  test    byte ptr [rcx+1Ch], 14h
0x18000d8e1  jz      short loc_18000D91F
0x18000d8e3  mov     rbx, [rcx+0C0h]
0x18000d8ea  lock inc dword ptr [rbx+6Ch]
0x18000d8ee  cmp     rbx, [rcx+0C0h]
0x18000d8f5  jnz     short loc_18000D902
0x18000d8f7  mov     rdx, rcx; struct CLogIocb *
0x18000d8fa  mov     rcx, rbx; this
0x18000d8fd  call    ?FreeIocb@CClfsMarshallingContext@@AEAAXPEAVCLogIocb@@@Z; CClfsMarshallingContext::FreeIocb(CLogIocb *)
0x18000d902  mov     rcx, rbx; this
0x18000d905  call    ?Release@CClfsMarshallingContext@@QEAAKXZ; CClfsMarshallingContext::Release(void)
0x18000d90a  xor     ecx, ecx; dwErrCode
0x18000d90c  call    cs:__imp_SetLastError
0x18000d913  nop     dword ptr [rax+rax+00h]
0x18000d918  mov     eax, 1
0x18000d91d  jmp     short loc_18000D932
0x18000d91f  mov     ecx, 57h ; 'W'; dwErrCode
0x18000d924  call    cs:__imp_SetLastError
0x18000d92b  nop     dword ptr [rax+rax+00h]
0x18000d930  xor     eax, eax
0x18000d932  add     rsp, 20h
0x18000d936  pop     rbx
0x18000d937  retn
```
