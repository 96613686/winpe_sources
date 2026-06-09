# VTCloseTable(x,x)

- ea: `0x1002bff0`
- end: `0x1002c05f`
- name: `_VTCloseTable@8`
- size: `111`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task`

## callees

- `0x1002a7de`
- `0x1002a869`
- `0x1002af20`
- `0x1002bff0`
- `0x10035b40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1002c031`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1002c031`

## pseudocode

```c
int __stdcall VTCloseTable(int a1, int a2)
{
  int v2; // eax
  int v3; // ebx
  _DWORD *v5; // edi
  DWORD CurrentProcessId; // eax
  int v7; // eax

  v2 = ISAMDBFindSession(a1);
  v3 = v2;
  if ( !v2 )
    return -1104;
  v5 = *(_DWORD **)(v2 + 8);
  if ( !v5 )
    return -1310;
  while ( v5[3] != a2 )
  {
    v5 = (_DWORD *)*v5;
    if ( !v5 )
      return -1310;
  }
  CurrentProcessId = GetCurrentProcessId();
  v7 = ISAMDBFindTask(CurrentProcessId);
  (*(void (__thiscall **)(_DWORD, _DWORD))(*(_DWORD *)(v7 + 28) + 68))(*(_DWORD *)(*(_DWORD *)(v7 + 28) + 68), v5[4]);
  ISAMDBDeleteVTDef(v3, v5);
  return 0;
}

```

## disassembly

```asm
0x1002bff0  mov     edi, edi
0x1002bff2  push    ebp
0x1002bff3  mov     ebp, esp
0x1002bff5  mov     ecx, [ebp+arg_0]
0x1002bff8  push    ebx
0x1002bff9  call    _ISAMDBFindSession@4; ISAMDBFindSession(x)
0x1002bffe  mov     ebx, eax
0x1002c000  test    ebx, ebx
0x1002c002  jnz     short loc_1002C00B
0x1002c004  mov     eax, 0FFFFFBB0h
0x1002c009  jmp     short loc_1002C027
0x1002c00b  push    edi
0x1002c00c  mov     edi, [ebx+8]
0x1002c00f  test    edi, edi
0x1002c011  jz      short loc_1002C021
0x1002c013  mov     eax, [ebp+arg_4]
0x1002c016  cmp     [edi+0Ch], eax
0x1002c019  jz      short loc_1002C02C
0x1002c01b  mov     edi, [edi]
0x1002c01d  test    edi, edi
0x1002c01f  jnz     short loc_1002C016
0x1002c021  mov     eax, 0FFFFFAE2h
0x1002c026  pop     edi
0x1002c027  pop     ebx
0x1002c028  pop     ebp
0x1002c029  retn    8
0x1002c02c  test    edi, edi
0x1002c02e  jz      short loc_1002C021
0x1002c030  push    esi
0x1002c031  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x1002c037  mov     ecx, eax
0x1002c039  call    _ISAMDBFindTask@4; ISAMDBFindTask(x)
0x1002c03e  push    dword ptr [edi+10h]
0x1002c041  mov     eax, [eax+1Ch]
0x1002c044  mov     esi, [eax+44h]
0x1002c047  mov     ecx, esi
0x1002c049  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1002c04f  call    esi
0x1002c051  mov     edx, edi
0x1002c053  mov     ecx, ebx
0x1002c055  call    _ISAMDBDeleteVTDef@8; ISAMDBDeleteVTDef(x,x)
0x1002c05a  xor     eax, eax
0x1002c05c  pop     esi
0x1002c05d  jmp     short loc_1002C026
```
