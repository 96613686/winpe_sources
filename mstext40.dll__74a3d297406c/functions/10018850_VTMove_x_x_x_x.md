# VTMove(x,x,x,x)

- ea: `0x10018850`
- end: `0x10018933`
- name: `_VTMove@16`
- size: `227`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x10014650`
- `0x10014780`
- `0x10018850`
- `0x10018a20`

## pseudocode

```c
int __stdcall VTMove(int a1, int a2, int a3, int a4)
{
  int v4; // eax
  int result; // eax
  int v6; // eax
  int v7; // esi
  int v8; // eax
  char v9; // dl

  v4 = ISAMDBFindSession(a1);
  if ( !v4 )
    return -1104;
  v6 = ISAMDBLocateVTDef(v4, a2);
  v7 = v6;
  if ( !v6 )
    return -1310;
  if ( a4 )
    return -1312;
  if ( !*(_DWORD *)(v6 + 32) )
    return -1603;
  if ( a3 )
  {
    switch ( a3 )
    {
      case -2147483648:
        v8 = 2;
        break;
      case 2147483647:
        v8 = 3;
        break;
      case 1:
        v8 = 0;
        break;
      case -1:
        v8 = 1;
        break;
      default:
        v8 = (a3 <= 0) + 4;
        break;
    }
    v9 = *(_BYTE *)(v7 + 36);
    if ( v9 || v8 )
    {
      if ( v9 == 1 && v8 == 1 )
        v8 = 3;
    }
    else
    {
      v8 = 2;
    }
    switch ( *(_DWORD *)(v7 + 8) )
    {
      case 0:
      case 1:
      case 2:
      case 3:
        XVTMove(v7, v7 + 560, v8, a3);
        break;
      default:
        break;
    }
  }
  result = -1603;
  if ( *(_BYTE *)(v7 + 36) == 2 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x10018850  push    [esp+arg_0]
0x10018854  call    _ISAMDBFindSession@4; ISAMDBFindSession(x)
0x10018859  test    eax, eax
0x1001885b  jnz     short loc_10018865
0x1001885d  mov     eax, 0FFFFFBB0h
0x10018862  retn    10h
0x10018865  push    esi
0x10018866  push    [esp+4+arg_4]
0x1001886a  push    eax
0x1001886b  call    _ISAMDBLocateVTDef@8; ISAMDBLocateVTDef(x,x)
0x10018870  mov     esi, eax
0x10018872  test    esi, esi
0x10018874  jnz     short loc_1001887F
0x10018876  mov     eax, 0FFFFFAE2h
0x1001887b  pop     esi
0x1001887c  retn    10h
0x1001887f  cmp     [esp+4+arg_C], 0
0x10018884  jz      short loc_1001888F
0x10018886  mov     eax, 0FFFFFAE0h
0x1001888b  pop     esi
0x1001888c  retn    10h
0x1001888f  cmp     dword ptr [esi+20h], 0
0x10018893  jnz     short loc_1001889E
0x10018895  mov     eax, 0FFFFF9BDh
0x1001889a  pop     esi
0x1001889b  retn    10h
0x1001889e  mov     ecx, [esp+4+arg_8]
0x100188a2  test    ecx, ecx
0x100188a4  jz      short def_1001890B; jumptable 1001890B default case
0x100188a6  cmp     ecx, 80000000h
0x100188ac  jnz     short loc_100188B5
0x100188ae  mov     eax, 2
0x100188b3  jmp     short loc_100188E1
0x100188b5  cmp     ecx, 7FFFFFFFh
0x100188bb  jnz     short loc_100188C4
0x100188bd  mov     eax, 3
0x100188c2  jmp     short loc_100188E1
0x100188c4  cmp     ecx, 1
0x100188c7  jnz     short loc_100188CD
0x100188c9  xor     eax, eax
0x100188cb  jmp     short loc_100188E1
0x100188cd  cmp     ecx, 0FFFFFFFFh
0x100188d0  jnz     short loc_100188D7
0x100188d2  lea     eax, [ecx+2]
0x100188d5  jmp     short loc_100188E1
0x100188d7  xor     eax, eax
0x100188d9  test    ecx, ecx
0x100188db  setle   al
0x100188de  add     eax, 4
0x100188e1  mov     dl, [esi+24h]
0x100188e4  test    dl, dl
0x100188e6  jnz     short loc_100188F3
0x100188e8  test    eax, eax
0x100188ea  jnz     short loc_100188F3
0x100188ec  mov     eax, 2
0x100188f1  jmp     short loc_10018903
0x100188f3  cmp     dl, 1
0x100188f6  jnz     short loc_10018903
0x100188f8  cmp     eax, 1
0x100188fb  mov     edx, 3
0x10018900  cmovz   eax, edx
0x10018903  mov     edx, [esi+8]
0x10018906  cmp     edx, 3; switch 4 cases
0x10018909  ja      short def_1001890B; jumptable 1001890B default case
0x1001890b  jmp     ds:jpt_1001890B[edx*4]; switch jump
0x10018912  push    ecx; jumptable 1001890B cases 0-3
0x10018913  push    eax
0x10018914  lea     eax, [esi+230h]
0x1001891a  push    eax
0x1001891b  push    esi
0x1001891c  call    XVTMove
0x10018921  xor     ecx, ecx; jumptable 1001890B default case
0x10018923  mov     eax, 0FFFFF9BDh
0x10018928  cmp     byte ptr [esi+24h], 2
0x1001892c  pop     esi
0x1001892d  cmovz   eax, ecx
0x10018930  retn    10h
```
