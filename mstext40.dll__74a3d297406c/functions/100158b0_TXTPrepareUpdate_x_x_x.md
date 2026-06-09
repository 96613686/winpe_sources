# TXTPrepareUpdate(x,x,x)

- ea: `0x100158b0`
- end: `0x1001593e`
- name: `_TXTPrepareUpdate@12`
- size: `142`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x1000ed90`
- `0x1000fe70`
- `0x10014460`
- `0x100158b0`
- `0x100168a0`

## pseudocode

```c
int __stdcall TXTPrepareUpdate(int a1, int a2, int a3)
{
  int v3; // eax
  int v4; // esi
  int result; // eax
  int v6; // eax

  v3 = ISAMDBFindCursor(a1, a2);
  v4 = v3;
  if ( !v3 )
    return -1310;
  if ( *(_BYTE *)(v3 + 28) == 1 )
    return -1809;
  v6 = *(_DWORD *)(v3 + 4);
  if ( *(_DWORD *)(v6 + 880) != 1 || (result = CreateTableWithColumns((const wchar_t *)v6, v4)) == 0 )
  {
    result = EstablishAsCurrentCursor(v4);
    if ( !result )
    {
      switch ( a3 )
      {
        case 0:
          CopyBufferRelease(v4);
          *(_DWORD *)(v4 + 76) = 1;
          result = 0;
          break;
        case 1:
        case 2:
        case 4:
        case 5:
          result = -5409;
          break;
        case 3:
          CopyBufferRelease(v4);
          result = 0;
          break;
        default:
          result = -1003;
          break;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x100158b0  push    esi
0x100158b1  push    [esp+4+arg_4]
0x100158b5  push    [esp+8+arg_0]
0x100158b9  call    _ISAMDBFindCursor@8; ISAMDBFindCursor(x,x)
0x100158be  mov     esi, eax
0x100158c0  test    esi, esi
0x100158c2  jnz     short loc_100158CD
0x100158c4  mov     eax, 0FFFFFAE2h
0x100158c9  pop     esi
0x100158ca  retn    0Ch
0x100158cd  cmp     byte ptr [esi+1Ch], 1
0x100158d1  jnz     short loc_100158DC
0x100158d3  mov     eax, 0FFFFF8EFh
0x100158d8  pop     esi
0x100158d9  retn    0Ch
0x100158dc  mov     eax, [esi+4]
0x100158df  cmp     dword ptr [eax+370h], 1
0x100158e6  jnz     short loc_100158F3
0x100158e8  push    esi
0x100158e9  push    eax
0x100158ea  call    _CreateTableWithColumns@8; CreateTableWithColumns(x,x)
0x100158ef  test    eax, eax
0x100158f1  jnz     short loc_1001593A
0x100158f3  push    esi
0x100158f4  call    _EstablishAsCurrentCursor@4; EstablishAsCurrentCursor(x)
0x100158f9  test    eax, eax
0x100158fb  jnz     short loc_1001593A
0x100158fd  mov     eax, [esp+4+arg_8]
0x10015901  cmp     eax, 5; switch 6 cases
0x10015904  ja      short def_10015906; jumptable 10015906 default case
0x10015906  jmp     ds:jpt_10015906[eax*4]; switch jump
0x1001590d  push    esi; jumptable 10015906 case 3
0x1001590e  call    _CopyBufferRelease@4; CopyBufferRelease(x)
0x10015913  xor     eax, eax
0x10015915  pop     esi
0x10015916  retn    0Ch
0x10015919  push    esi; jumptable 10015906 case 0
0x1001591a  call    _CopyBufferRelease@4; CopyBufferRelease(x)
0x1001591f  mov     dword ptr [esi+4Ch], 1
0x10015926  xor     eax, eax
0x10015928  pop     esi
0x10015929  retn    0Ch
0x1001592c  mov     eax, 0FFFFEADFh; jumptable 10015906 cases 1,2,4,5
0x10015931  pop     esi
0x10015932  retn    0Ch
0x10015935  mov     eax, 0FFFFFC15h; jumptable 10015906 default case
0x1001593a  pop     esi
0x1001593b  retn    0Ch
```
