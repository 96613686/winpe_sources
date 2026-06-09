# OpenIMEXSpec

- ea: `0x1001ba80`
- end: `0x1001bae1`
- name: `OpenIMEXSpec`
- size: `97`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1001c060`
- `0x1001c250`

## callees

- `0x1000a1d0`
- `0x1001ba80`
- `0x1002b620`
- `0x1002b626`

## pseudocode

```c
int __stdcall OpenIMEXSpec(int a1, JET_TABLEID *a2, int a3)
{
  if ( JetOpenTable(*(_DWORD *)(a1 + 40), *(_DWORD *)(a1 + 44), (int)L"MSysIMEXSpecs", 0, 0, 4, (int)a2) )
    goto LABEL_4;
  if ( JetOpenTable(*(_DWORD *)(a1 + 40), *(_DWORD *)(a1 + 44), (int)L"MSysIMEXColumns", 0, 0, 4, a3) )
  {
    JetCloseTable(*(_DWORD *)(a1 + 40), *a2);
LABEL_4:
    ErrorClearExtendedInfo();
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1001ba80  push    esi
0x1001ba81  mov     esi, [esp+4+arg_0]
0x1001ba85  push    edi
0x1001ba86  mov     edi, [esp+8+arg_4]
0x1001ba8a  push    edi
0x1001ba8b  push    4
0x1001ba8d  push    0
0x1001ba8f  push    0
0x1001ba91  push    offset aMsysimexspecs; "MSysIMEXSpecs"
0x1001ba96  push    dword ptr [esi+2Ch]
0x1001ba99  push    dword ptr [esi+28h]
0x1001ba9c  call    _JetOpenTable@28; JetOpenTable(x,x,x,x,x,x,x)
0x1001baa1  test    eax, eax
0x1001baa3  jnz     short loc_1001BACB
0x1001baa5  push    [esp+8+arg_8]
0x1001baa9  push    4
0x1001baab  push    eax
0x1001baac  push    eax
0x1001baad  push    offset aMsysimexcolumn; "MSysIMEXColumns"
0x1001bab2  push    dword ptr [esi+2Ch]
0x1001bab5  push    dword ptr [esi+28h]
0x1001bab8  call    _JetOpenTable@28; JetOpenTable(x,x,x,x,x,x,x)
0x1001babd  test    eax, eax
0x1001babf  jz      short loc_1001BAD7
0x1001bac1  push    dword ptr [edi]; tableid
0x1001bac3  push    dword ptr [esi+28h]; sesid
0x1001bac6  call    _JetCloseTable@8; JetCloseTable(x,x)
0x1001bacb  call    _ErrorClearExtendedInfo@0; ErrorClearExtendedInfo()
0x1001bad0  pop     edi
0x1001bad1  xor     eax, eax
0x1001bad3  pop     esi
0x1001bad4  retn    0Ch
0x1001bad7  pop     edi
0x1001bad8  mov     eax, 1
0x1001badd  pop     esi
0x1001bade  retn    0Ch
```
