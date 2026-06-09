# RmtGenDelete

- ea: `0x100d978a`
- end: `0x100d9867`
- name: `RmtGenDelete`
- size: `221`
- prototype: `int __stdcall(LPCVOID lpAddress, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x100d986d`

## callees

- `0x100aef6e`
- `0x100b0c26`
- `0x100b74ea`
- `0x100d93d5`
- `0x100d978a`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!longjmp` at `0x100d97c6`
- `api-ms-win-crt-private-l1-1-0!longjmp` at `0x100d97c6`

## string_xrefs

- `0x100d97d1`: `DELETE FROM`

## pseudocode

```c
int __fastcall RmtGenDelete(int a1, int a2, LPCVOID lpAddress, int a4)
{
  _DWORD *v5; // esi
  int v6; // eax
  _WORD *v7; // ecx
  int result; // eax
  void *v10; // eax
  int v11; // [esp+Ch] [ebp-8h]

  v5 = (_DWORD *)(a4 + 1048);
  v11 = *(_DWORD *)(a2 + 300);
  v6 = ErrCallocPvHsegREAL(lpAddress, 2, 1);
  if ( v6 < 0 )
    _longjmp(*(int **)(a1 + 24), v6);
  PPRmtStrcat2REAL(L"DELETE FROM", L" ");
  PPAddOwnerTable(*(wchar_t **)(a2 + 272), (void *)(v11 + 48));
  v7 = (_WORD *)*v5;
  while ( *v7++ )
    ;
  *(_WORD *)(a4 + 1052) = ((int)v7 - *v5 - 2) >> 1;
  PPRmtStrcat2REAL(L" WHERE ", *(void **)(a2 + 284));
  result = a1;
  if ( *(_WORD *)(a1 + 136) != 5 )
  {
    v10 = *(void **)(a2 + 296);
    if ( v10 )
      return PPRmtStrcat2REAL(v10, 0);
    else
      return AddAllColsQual(lpAddress, a4, (int)v5);
  }
  return result;
}

```

## disassembly

```asm
0x100d978a  mov     edi, edi
0x100d978c  push    ebp
0x100d978d  mov     ebp, esp
0x100d978f  push    ecx
0x100d9790  push    ecx
0x100d9791  push    ebx
0x100d9792  push    esi
0x100d9793  mov     esi, [ebp+arg_4]
0x100d9796  mov     ebx, edx
0x100d9798  push    edi
0x100d9799  mov     edi, [ebp+lpAddress]
0x100d979c  add     esi, 418h
0x100d97a2  push    esi
0x100d97a3  mov     eax, [ebx+12Ch]
0x100d97a9  push    1
0x100d97ab  push    2
0x100d97ad  mov     [ebp+var_4], ecx
0x100d97b0  mov     ecx, edi
0x100d97b2  pop     edx
0x100d97b3  mov     [ebp+var_8], eax
0x100d97b6  call    _ErrCallocPvHsegREAL@16; ErrCallocPvHsegREAL(x,x,x,x)
0x100d97bb  test    eax, eax
0x100d97bd  jns     short loc_100D97CC
0x100d97bf  push    eax; Value
0x100d97c0  mov     eax, [ebp+var_4]
0x100d97c3  push    dword ptr [eax+18h]; Buf
0x100d97c6  call    ds:__imp__longjmp
0x100d97cc  push    offset asc_1000EE40; " "
0x100d97d1  push    offset aDeleteFrom; "DELETE FROM"
0x100d97d6  mov     edx, esi
0x100d97d8  mov     ecx, edi
0x100d97da  call    _PPRmtStrcat2REAL@16; PPRmtStrcat2REAL(x,x,x,x)
0x100d97df  mov     eax, [ebp+var_8]
0x100d97e2  mov     edx, esi
0x100d97e4  add     eax, 30h ; '0'
0x100d97e7  mov     ecx, edi
0x100d97e9  push    eax; Src
0x100d97ea  push    dword ptr [ebx+110h]; Str
0x100d97f0  call    _PPAddOwnerTable@16; PPAddOwnerTable(x,x,x,x)
0x100d97f5  mov     ecx, [esi]
0x100d97f7  mov     [ebp+var_8], 0
0x100d97fe  lea     edx, [ecx+2]
0x100d9801  mov     ax, [ecx]
0x100d9804  add     ecx, 2
0x100d9807  cmp     ax, word ptr [ebp+var_8]
0x100d980b  jnz     short loc_100D9801
0x100d980d  mov     eax, [ebp+arg_4]
0x100d9810  sub     ecx, edx
0x100d9812  sar     ecx, 1
0x100d9814  mov     edx, esi
0x100d9816  mov     [eax+41Ch], cx
0x100d981d  mov     ecx, edi
0x100d981f  push    dword ptr [ebx+11Ch]; void *
0x100d9825  push    offset aWhere_0; " WHERE "
0x100d982a  call    _PPRmtStrcat2REAL@16; PPRmtStrcat2REAL(x,x,x,x)
0x100d982f  mov     eax, [ebp+var_4]
0x100d9832  cmp     word ptr [eax+88h], 5
0x100d983a  jz      short loc_100D9860
0x100d983c  mov     eax, [ebx+128h]
0x100d9842  test    eax, eax
0x100d9844  jz      short loc_100D9854
0x100d9846  push    0; void *
0x100d9848  push    eax; Src
0x100d9849  mov     edx, esi
0x100d984b  mov     ecx, edi
0x100d984d  call    _PPRmtStrcat2REAL@16; PPRmtStrcat2REAL(x,x,x,x)
0x100d9852  jmp     short loc_100D9860
0x100d9854  push    esi; int
0x100d9855  push    [ebp+arg_4]; int
0x100d9858  mov     edx, ebx
0x100d985a  push    edi; lpAddress
0x100d985b  call    AddAllColsQual
0x100d9860  pop     edi
0x100d9861  pop     esi
0x100d9862  pop     ebx
0x100d9863  leave
0x100d9864  retn    8
```
