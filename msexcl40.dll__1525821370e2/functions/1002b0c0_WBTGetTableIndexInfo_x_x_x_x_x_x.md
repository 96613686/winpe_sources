# WBTGetTableIndexInfo(x,x,x,x,x,x)

- ea: `0x1002b0c0`
- end: `0x1002b243`
- name: `_WBTGetTableIndexInfo@24`
- size: `387`
- prototype: `int __stdcall(int, int, int, void *, size_t Size, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task`

## callees

- `0x1002a7de`
- `0x1002a869`
- `0x1002acaf`
- `0x1002aecf`
- `0x1002af20`
- `0x1002b0c0`
- `0x10035b40`
- `0x1003669c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1002b156`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1002b156`

## pseudocode

```c
int __stdcall WBTGetTableIndexInfo(int a1, int a2, int a3, void *a4, size_t Size, unsigned int a6)
{
  int v7; // eax
  int v8; // ebx
  _DWORD *v9; // eax
  _DWORD *v10; // edi
  DWORD CurrentProcessId; // eax
  int v12; // eax
  int v13; // esi
  int v14; // ecx
  size_t v15; // eax
  size_t v16; // eax
  _DWORD Src[15]; // [esp+4h] [ebp-44h] BYREF
  int v18; // [esp+40h] [ebp-8h]
  int v19; // [esp+44h] [ebp-4h] BYREF

  if ( a6 < 2 )
  {
    v7 = ISAMDBFindCursor(a1, a2);
    if ( v7 )
    {
      v18 = *(_DWORD *)(v7 + 8);
      if ( a3 )
      {
        return -1404;
      }
      else
      {
        v8 = ISAMDBFindSession(a1);
        v9 = (_DWORD *)ISAMDBAddVTDef(v8, 0);
        v10 = v9;
        if ( v9 )
        {
          v9[10] = 0;
          v9[7] = a6;
          v9[8] = 0;
          CurrentProcessId = GetCurrentProcessId();
          v12 = ISAMDBFindTask(CurrentProcessId);
          v13 = (*(int (__thiscall **)(_DWORD, int, int *, _DWORD, int *))(*(_DWORD *)(v12 + 28) + 36))(
                  *(_DWORD *)(*(_DWORD *)(v12 + 28) + 36),
                  a1,
                  &v19,
                  v10[3],
                  &VTEntryPoints);
          if ( v13 )
          {
            ISAMDBDeleteVTDef(v8, v10);
            return v13;
          }
          else
          {
            v14 = v18;
            v10[4] = v19;
            v10[5] = *(_DWORD *)(v14 + 12);
            v10[6] = *(_DWORD *)(v14 + 16);
            Src[1] = v19;
            v15 = Size;
            Src[2] = 0;
            if ( Size > 0x3C )
              v15 = 60;
            Src[3] = 0;
            Src[0] = v15;
            v16 = 60;
            if ( Size < 0x3C )
              v16 = Size;
            Src[4] = 1;
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
            memcpy(a4, Src, v16);
            return Size < 0x3C ? 0x3EE : 0;
          }
        }
        else
        {
          return -1011;
        }
      }
    }
    else
    {
      return -1310;
    }
  }
  else if ( a6 == 2 )
  {
    return -1001;
  }
  else
  {
    return -1003;
  }
}

```

## disassembly

```asm
0x1002b0c0  mov     edi, edi
0x1002b0c2  push    ebp
0x1002b0c3  mov     ebp, esp
0x1002b0c5  sub     esp, 44h
0x1002b0c8  push    esi
0x1002b0c9  mov     esi, [ebp+arg_14]
0x1002b0cc  mov     eax, esi
0x1002b0ce  sub     eax, 0
0x1002b0d1  jz      short loc_1002B0F1
0x1002b0d3  sub     eax, 1
0x1002b0d6  jz      short loc_1002B0F1
0x1002b0d8  sub     eax, 1
0x1002b0db  jz      short loc_1002B0E7
0x1002b0dd  mov     eax, 0FFFFFC15h
0x1002b0e2  jmp     loc_1002B23E
0x1002b0e7  mov     eax, 0FFFFFC17h
0x1002b0ec  jmp     loc_1002B23E
0x1002b0f1  mov     edx, [ebp+arg_4]
0x1002b0f4  mov     ecx, [ebp+arg_0]
0x1002b0f7  call    _ISAMDBFindCursor@8; ISAMDBFindCursor(x,x)
0x1002b0fc  test    eax, eax
0x1002b0fe  jnz     short loc_1002B10A
0x1002b100  mov     eax, 0FFFFFAE2h
0x1002b105  jmp     loc_1002B23E
0x1002b10a  cmp     [ebp+arg_8], 0
0x1002b10e  mov     eax, [eax+8]
0x1002b111  mov     [ebp+var_8], eax
0x1002b114  jz      short loc_1002B120
0x1002b116  mov     eax, 0FFFFFA84h
0x1002b11b  jmp     loc_1002B23E
0x1002b120  mov     ecx, [ebp+arg_0]
0x1002b123  push    ebx
0x1002b124  push    edi
0x1002b125  call    _ISAMDBFindSession@4; ISAMDBFindSession(x)
0x1002b12a  mov     ebx, eax
0x1002b12c  xor     edx, edx
0x1002b12e  mov     ecx, ebx
0x1002b130  call    _ISAMDBAddVTDef@8; ISAMDBAddVTDef(x,x)
0x1002b135  mov     edi, eax
0x1002b137  test    edi, edi
0x1002b139  jnz     short loc_1002B145
0x1002b13b  mov     eax, 0FFFFFC0Dh
0x1002b140  jmp     loc_1002B23C
0x1002b145  mov     dword ptr [edi+28h], 0
0x1002b14c  mov     [edi+1Ch], esi
0x1002b14f  mov     dword ptr [edi+20h], 0
0x1002b156  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x1002b15c  mov     ecx, eax
0x1002b15e  call    _ISAMDBFindTask@4; ISAMDBFindTask(x)
0x1002b163  push    offset _VTEntryPoints
0x1002b168  push    dword ptr [edi+0Ch]
0x1002b16b  mov     esi, [eax+1Ch]
0x1002b16e  lea     eax, [ebp+var_4]
0x1002b171  push    eax
0x1002b172  push    [ebp+arg_0]
0x1002b175  mov     esi, [esi+24h]
0x1002b178  mov     ecx, esi
0x1002b17a  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1002b180  call    esi
0x1002b182  mov     esi, eax
0x1002b184  test    esi, esi
0x1002b186  jz      short loc_1002B198
0x1002b188  mov     edx, edi
0x1002b18a  mov     ecx, ebx
0x1002b18c  call    _ISAMDBDeleteVTDef@8; ISAMDBDeleteVTDef(x,x)
0x1002b191  mov     eax, esi
0x1002b193  jmp     loc_1002B23C
0x1002b198  mov     ecx, [ebp+var_8]
0x1002b19b  mov     eax, [ebp+var_4]
0x1002b19e  mov     esi, [ebp+Size]
0x1002b1a1  mov     [edi+10h], eax
0x1002b1a4  mov     eax, [ecx+0Ch]
0x1002b1a7  mov     [edi+14h], eax
0x1002b1aa  mov     eax, [ecx+10h]
0x1002b1ad  mov     [edi+18h], eax
0x1002b1b0  mov     eax, [ebp+var_4]
0x1002b1b3  push    3Ch ; '<'
0x1002b1b5  pop     edi
0x1002b1b6  mov     [ebp+var_40], eax
0x1002b1b9  cmp     esi, edi
0x1002b1bb  mov     eax, esi
0x1002b1bd  mov     [ebp+var_3C], 0
0x1002b1c4  cmova   eax, edi
0x1002b1c7  mov     [ebp+var_38], 0
0x1002b1ce  mov     [ebp+Src], eax
0x1002b1d1  mov     eax, edi
0x1002b1d3  cmovb   eax, esi
0x1002b1d6  mov     [ebp+var_34], 1
0x1002b1dd  push    eax; Size
0x1002b1de  lea     eax, [ebp+Src]
0x1002b1e1  mov     [ebp+var_30], 2
0x1002b1e8  push    eax; Src
0x1002b1e9  push    [ebp+arg_C]; void *
0x1002b1ec  mov     [ebp+var_2C], 3
0x1002b1f3  mov     [ebp+var_28], 4
0x1002b1fa  mov     [ebp+var_24], 5
0x1002b201  mov     [ebp+var_20], 6
0x1002b208  mov     [ebp+var_1C], 7
0x1002b20f  mov     [ebp+var_18], 8
0x1002b216  mov     [ebp+var_14], 9
0x1002b21d  mov     [ebp+var_10], 0Ah
0x1002b224  mov     [ebp+var_C], 0Bh
0x1002b22b  call    _memcpy
0x1002b230  add     esp, 0Ch
0x1002b233  cmp     esi, edi
0x1002b235  sbb     eax, eax
0x1002b237  and     eax, 3EEh
0x1002b23c  pop     edi
0x1002b23d  pop     ebx
0x1002b23e  pop     esi
0x1002b23f  leave
0x1002b240  retn    18h
```
