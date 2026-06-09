# WBDBGetIndexInfo(x,x,x,x,x,x)

- ea: `0x1002b250`
- end: `0x1002b3ad`
- name: `_WBDBGetIndexInfo@24`
- size: `349`
- prototype: `int __stdcall(int, int, int, int, unsigned int *, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task`

## callees

- `0x1002a7de`
- `0x1002a869`
- `0x1002aaa4`
- `0x1002aecf`
- `0x1002af20`
- `0x1002b250`
- `0x10035b40`
- `0x1003669c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1002b2be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1002b2be`

## pseudocode

```c
int __stdcall WBDBGetIndexInfo(int a1, int a2, int a3, int a4, unsigned int *a5, int a6)
{
  int v7; // ebx
  _DWORD *v8; // edi
  DWORD CurrentProcessId; // eax
  int v10; // eax
  int v11; // esi
  int v12; // ecx
  unsigned int v13; // esi
  bool v14; // cf
  bool v15; // cc
  int v16; // eax
  size_t v17; // eax
  void *v18; // [esp-18h] [ebp-5Ch]
  _DWORD Src[15]; // [esp+0h] [ebp-44h] BYREF
  int v20; // [esp+3Ch] [ebp-8h]
  int v21; // [esp+40h] [ebp-4h] BYREF

  v20 = ISAMDBFindDatabaseUser(a1, a2);
  if ( !v20 )
    return -1010;
  if ( a4 )
    return -1404;
  v7 = ISAMDBFindSession(a1);
  v8 = (_DWORD *)ISAMDBAddVTDef(v7, 0);
  if ( !v8 )
    return -1011;
  v8[10] = 0;
  v8[7] = a6;
  v8[8] = 0;
  CurrentProcessId = GetCurrentProcessId();
  v10 = ISAMDBFindTask(CurrentProcessId);
  v11 = (*(int (__thiscall **)(_DWORD, int, int *, _DWORD, int *))(*(_DWORD *)(v10 + 28) + 36))(
          *(_DWORD *)(*(_DWORD *)(v10 + 28) + 36),
          a1,
          &v21,
          v8[3],
          &VTEntryPoints);
  if ( v11 )
  {
    ISAMDBDeleteVTDef(v7, v8);
    return v11;
  }
  else
  {
    v12 = v20;
    v8[4] = v21;
    v8[5] = *(_DWORD *)(v12 + 12);
    v8[6] = *(_DWORD *)(v12 + 16);
    v13 = *a5;
    v14 = *a5 < 0x3C;
    v15 = *a5 <= 0x3C;
    Src[1] = v21;
    v16 = v13;
    if ( !v15 )
      v16 = 60;
    Src[2] = 0;
    Src[0] = v16;
    v17 = 60;
    if ( v14 )
      v17 = v13;
    Src[3] = 0;
    Src[4] = 1;
    v18 = (void *)a5[3];
    Src[5] = 2;
    Src[6] = 3;
    Src[7] = 4;
    Src[8] = 5;
    Src[9] = 6;
    Src[10] = 7;
    Src[11] = 8;
    Src[12] = 9;
    Src[13] = 10;
    Src[14] = 11;
    memcpy(v18, Src, v17);
    return v13 < 0x3C ? 0x3EE : 0;
  }
}

```

## disassembly

```asm
0x1002b250  mov     edi, edi
0x1002b252  push    ebp
0x1002b253  mov     ebp, esp
0x1002b255  sub     esp, 44h
0x1002b258  mov     ecx, [ebp+arg_0]
0x1002b25b  mov     edx, [ebp+arg_4]
0x1002b25e  call    _ISAMDBFindDatabaseUser@8; ISAMDBFindDatabaseUser(x,x)
0x1002b263  mov     [ebp+var_8], eax
0x1002b266  test    eax, eax
0x1002b268  jnz     short loc_1002B274
0x1002b26a  mov     eax, 0FFFFFC0Eh
0x1002b26f  jmp     locret_1002B3A9
0x1002b274  cmp     [ebp+arg_C], 0
0x1002b278  jz      short loc_1002B284
0x1002b27a  mov     eax, 0FFFFFA84h
0x1002b27f  jmp     locret_1002B3A9
0x1002b284  mov     ecx, [ebp+arg_0]
0x1002b287  push    ebx
0x1002b288  push    edi
0x1002b289  call    _ISAMDBFindSession@4; ISAMDBFindSession(x)
0x1002b28e  mov     ebx, eax
0x1002b290  xor     edx, edx
0x1002b292  mov     ecx, ebx
0x1002b294  call    _ISAMDBAddVTDef@8; ISAMDBAddVTDef(x,x)
0x1002b299  mov     edi, eax
0x1002b29b  test    edi, edi
0x1002b29d  jnz     short loc_1002B2A9
0x1002b29f  mov     eax, 0FFFFFC0Dh
0x1002b2a4  jmp     loc_1002B3A7
0x1002b2a9  mov     eax, [ebp+arg_14]
0x1002b2ac  push    esi
0x1002b2ad  mov     dword ptr [edi+28h], 0
0x1002b2b4  mov     [edi+1Ch], eax
0x1002b2b7  mov     dword ptr [edi+20h], 0
0x1002b2be  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x1002b2c4  mov     ecx, eax
0x1002b2c6  call    _ISAMDBFindTask@4; ISAMDBFindTask(x)
0x1002b2cb  push    offset _VTEntryPoints
0x1002b2d0  push    dword ptr [edi+0Ch]
0x1002b2d3  mov     esi, [eax+1Ch]
0x1002b2d6  lea     eax, [ebp+var_4]
0x1002b2d9  push    eax
0x1002b2da  push    [ebp+arg_0]
0x1002b2dd  mov     esi, [esi+24h]
0x1002b2e0  mov     ecx, esi
0x1002b2e2  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1002b2e8  call    esi
0x1002b2ea  mov     esi, eax
0x1002b2ec  test    esi, esi
0x1002b2ee  jz      short loc_1002B300
0x1002b2f0  mov     edx, edi
0x1002b2f2  mov     ecx, ebx
0x1002b2f4  call    _ISAMDBDeleteVTDef@8; ISAMDBDeleteVTDef(x,x)
0x1002b2f9  mov     eax, esi
0x1002b2fb  jmp     loc_1002B3A6
0x1002b300  mov     ecx, [ebp+var_8]
0x1002b303  mov     eax, [ebp+var_4]
0x1002b306  mov     [edi+10h], eax
0x1002b309  push    3Ch ; '<'
0x1002b30b  mov     eax, [ecx+0Ch]
0x1002b30e  mov     [edi+14h], eax
0x1002b311  mov     eax, [ecx+10h]
0x1002b314  mov     ecx, [ebp+arg_10]
0x1002b317  mov     [edi+18h], eax
0x1002b31a  mov     eax, [ebp+var_4]
0x1002b31d  pop     edi
0x1002b31e  mov     esi, [ecx]
0x1002b320  cmp     esi, edi
0x1002b322  mov     [ebp+var_40], eax
0x1002b325  mov     eax, esi
0x1002b327  cmova   eax, edi
0x1002b32a  mov     [ebp+var_3C], 0
0x1002b331  mov     [ebp+Src], eax
0x1002b334  mov     eax, edi
0x1002b336  cmovb   eax, esi
0x1002b339  mov     [ebp+var_38], 0
0x1002b340  push    eax; Size
0x1002b341  lea     eax, [ebp+Src]
0x1002b344  mov     [ebp+var_34], 1
0x1002b34b  push    eax; Src
0x1002b34c  push    dword ptr [ecx+0Ch]; void *
0x1002b34f  mov     [ebp+var_30], 2
0x1002b356  mov     [ebp+var_2C], 3
0x1002b35d  mov     [ebp+var_28], 4
0x1002b364  mov     [ebp+var_24], 5
0x1002b36b  mov     [ebp+var_20], 6
0x1002b372  mov     [ebp+var_1C], 7
0x1002b379  mov     [ebp+var_18], 8
0x1002b380  mov     [ebp+var_14], 9
0x1002b387  mov     [ebp+var_10], 0Ah
0x1002b38e  mov     [ebp+var_C], 0Bh
0x1002b395  call    _memcpy
0x1002b39a  add     esp, 0Ch
0x1002b39d  cmp     esi, edi
0x1002b39f  sbb     eax, eax
0x1002b3a1  and     eax, 3EEh
0x1002b3a6  pop     esi
0x1002b3a7  pop     edi
0x1002b3a8  pop     ebx
0x1002b3a9  leave
0x1002b3aa  retn    18h
```
