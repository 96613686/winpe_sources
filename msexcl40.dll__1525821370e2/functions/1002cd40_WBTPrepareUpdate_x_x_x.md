# WBTPrepareUpdate(x,x,x)

- ea: `0x1002cd40`
- end: `0x1002ce17`
- name: `_WBTPrepareUpdate@12`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x1002acaf`
- `0x1002c918`
- `0x1002cc39`
- `0x1002cd40`
- `0x1002db68`
- `0x10031f44`

## pseudocode

```c
int __stdcall WBTPrepareUpdate(int a1, int a2, int a3)
{
  int v3; // eax
  _DWORD *v4; // esi
  int result; // eax
  _DWORD *v6; // ecx

  v3 = ISAMDBFindCursor(a1, a2);
  v4 = (_DWORD *)v3;
  if ( !v3 )
    return -1310;
  if ( *(_BYTE *)(v3 + 28) == 1 )
    return -1809;
  *(_DWORD *)(*(_DWORD *)(v3 + 4) + 80) = 0;
  v6 = *(_DWORD **)(v3 + 4);
  if ( v6[14] != 1 || (result = CreateTableWithColumns(v6, v3)) == 0 )
  {
    if ( a3 )
    {
      if ( a3 == 1 )
        return -1001;
      if ( a3 != 2 )
      {
        if ( a3 == 3 )
        {
          CopyBufferClear(v4);
          return 0;
        }
        if ( a3 != 4 )
        {
          if ( a3 != 5 )
            return -1003;
          return -1001;
        }
      }
      if ( (*((_BYTE *)&ISAMLimits + 2 * *(_DWORD *)(*(_DWORD *)(v4[1] + 4) + 16)) & 8) != 0 )
      {
        CopyBufferClear(v4);
        result = CopyCurrentRecord(v4);
        if ( !result )
          v4[12] = 3;
      }
      else
      {
        return -1048;
      }
    }
    else
    {
      CopyBufferClear(v4);
      return PrepareRecordInsert(v4);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1002cd40  mov     edi, edi
0x1002cd42  push    ebp
0x1002cd43  mov     ebp, esp
0x1002cd45  and     esp, 0FFFFFFF8h
0x1002cd48  push    ecx
0x1002cd49  mov     edx, [ebp+arg_4]
0x1002cd4c  mov     ecx, [ebp+arg_0]
0x1002cd4f  push    esi
0x1002cd50  call    _ISAMDBFindCursor@8; ISAMDBFindCursor(x,x)
0x1002cd55  mov     esi, eax
0x1002cd57  test    esi, esi
0x1002cd59  jnz     short loc_1002CD65
0x1002cd5b  mov     eax, 0FFFFFAE2h
0x1002cd60  jmp     loc_1002CE10
0x1002cd65  cmp     byte ptr [esi+1Ch], 1
0x1002cd69  jnz     short loc_1002CD75
0x1002cd6b  mov     eax, 0FFFFF8EFh
0x1002cd70  jmp     loc_1002CE10
0x1002cd75  mov     eax, [esi+4]
0x1002cd78  mov     dword ptr [eax+50h], 0
0x1002cd7f  mov     ecx, [esi+4]
0x1002cd82  cmp     dword ptr [ecx+38h], 1
0x1002cd86  jnz     short loc_1002CD93
0x1002cd88  mov     edx, esi
0x1002cd8a  call    _CreateTableWithColumns@8; CreateTableWithColumns(x,x)
0x1002cd8f  test    eax, eax
0x1002cd91  jnz     short loc_1002CE10
0x1002cd93  mov     eax, [ebp+arg_8]
0x1002cd96  sub     eax, 0
0x1002cd99  jz      short loc_1002CE02
0x1002cd9b  sub     eax, 1
0x1002cd9e  jz      short loc_1002CDFB
0x1002cda0  sub     eax, 1
0x1002cda3  jz      short loc_1002CDC6
0x1002cda5  sub     eax, 1
0x1002cda8  jz      short loc_1002CDBB
0x1002cdaa  sub     eax, 1
0x1002cdad  jz      short loc_1002CDC6
0x1002cdaf  sub     eax, 1
0x1002cdb2  jz      short loc_1002CDFB
0x1002cdb4  mov     eax, 0FFFFFC15h
0x1002cdb9  jmp     short loc_1002CE10
0x1002cdbb  mov     ecx, esi
0x1002cdbd  call    _CopyBufferClear@4; CopyBufferClear(x)
0x1002cdc2  xor     eax, eax
0x1002cdc4  jmp     short loc_1002CE10
0x1002cdc6  mov     eax, [esi+4]
0x1002cdc9  mov     eax, [eax+4]
0x1002cdcc  mov     eax, [eax+10h]
0x1002cdcf  test    byte ptr _ISAMLimits[eax*2], 8
0x1002cdd7  jnz     short loc_1002CDE0
0x1002cdd9  mov     eax, 0FFFFFBE8h
0x1002cdde  jmp     short loc_1002CE10
0x1002cde0  mov     ecx, esi
0x1002cde2  call    _CopyBufferClear@4; CopyBufferClear(x)
0x1002cde7  mov     ecx, esi
0x1002cde9  call    CopyCurrentRecord
0x1002cdee  test    eax, eax
0x1002cdf0  jnz     short loc_1002CE10
0x1002cdf2  mov     dword ptr [esi+30h], 3
0x1002cdf9  jmp     short loc_1002CE10
0x1002cdfb  mov     eax, 0FFFFFC17h
0x1002ce00  jmp     short loc_1002CE10
0x1002ce02  mov     ecx, esi
0x1002ce04  call    _CopyBufferClear@4; CopyBufferClear(x)
0x1002ce09  mov     ecx, esi
0x1002ce0b  call    PrepareRecordInsert
0x1002ce10  pop     esi
0x1002ce11  mov     esp, ebp
0x1002ce13  pop     ebp
0x1002ce14  retn    0Ch
```
