# WBTRenameColumn(x,x,x,x)

- ea: `0x1002e9f0`
- end: `0x1002eb13`
- name: `_WBTRenameColumn@16`
- size: `291`
- prototype: `int __stdcall(int, int, int, wchar_t *String2)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x10006400`
- `0x1001a630`
- `0x1001e4b0`
- `0x100246ef`
- `0x1002acaf`
- `0x1002aea1`
- `0x1002e56d`
- `0x1002e9f0`
- `0x10035510`

## pseudocode

```c
int __stdcall WBTRenameColumn(int a1, int a2, wchar_t *a3, wchar_t *String2)
{
  int v4; // eax
  int v5; // esi
  int result; // eax
  int v7; // esi
  int v8; // ecx
  int ValidColumnName; // ebx
  int v10; // eax
  UINT CodePage; // [esp+Ch] [ebp-408h] BYREF
  wchar_t v12[256]; // [esp+10h] [ebp-404h] BYREF
  wchar_t String1[256]; // [esp+210h] [ebp-204h] BYREF

  v4 = ISAMDBFindCursor(a1, a2);
  v5 = v4;
  if ( !v4 )
    return -1310;
  result = ColumnOperationOK(v4);
  if ( !result )
  {
    v7 = *(_DWORD *)(v5 + 4);
    v8 = *(_DWORD *)(v7 + 4);
    *(_DWORD *)(v7 + 80) = 0;
    WorkbookCodePage(*(_DWORD *)(v8 + 12), &CodePage);
    ValidColumnName = WorkbookMakeValidColumnName(String2, String1, 256, CodePage);
    if ( ValidColumnName )
    {
      WorkbookCodePage(*(_DWORD *)(*(_DWORD *)(v7 + 4) + 12), &CodePage);
      WorkbookMakeValidColumnName(a3, v12, 256, CodePage);
      if ( ISAMDBLocateColumn(v7, String1) )
      {
        return -1508;
      }
      else
      {
        v10 = ISAMDBLocateColumn(v7, v12);
        if ( v10 )
        {
          WCSCPY2((_WORD *)(v10 + 42), String1, 0x100u);
          result = 0;
          if ( ValidColumnName == 2 )
            return 5011;
        }
        else
        {
          return -1507;
        }
      }
    }
    else
    {
      ErrorSetExtendedInfoSz1(1);
      return -1002;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1002e9f0  mov     edi, edi
0x1002e9f2  push    ebp
0x1002e9f3  mov     ebp, esp
0x1002e9f5  sub     esp, 40Ch
0x1002e9fb  mov     eax, ___security_cookie
0x1002ea00  xor     eax, ebp
0x1002ea02  mov     [ebp+var_4], eax
0x1002ea05  mov     eax, [ebp+arg_8]
0x1002ea08  mov     ecx, [ebp+arg_0]
0x1002ea0b  mov     edx, [ebp+arg_4]
0x1002ea0e  push    esi
0x1002ea0f  push    edi
0x1002ea10  mov     edi, [ebp+String2]
0x1002ea13  mov     [ebp+var_40C], eax
0x1002ea19  call    _ISAMDBFindCursor@8; ISAMDBFindCursor(x,x)
0x1002ea1e  mov     esi, eax
0x1002ea20  test    esi, esi
0x1002ea22  jnz     short loc_1002EA2E
0x1002ea24  mov     eax, 0FFFFFAE2h
0x1002ea29  jmp     loc_1002EB03
0x1002ea2e  mov     ecx, esi
0x1002ea30  call    ColumnOperationOK
0x1002ea35  test    eax, eax
0x1002ea37  jnz     loc_1002EB03
0x1002ea3d  mov     esi, [esi+4]
0x1002ea40  lea     edx, [ebp+CodePage]
0x1002ea46  push    ebx
0x1002ea47  mov     ecx, [esi+4]
0x1002ea4a  mov     [esi+50h], eax
0x1002ea4d  mov     ecx, [ecx+0Ch]
0x1002ea50  call    _WorkbookCodePage@8; WorkbookCodePage(x,x)
0x1002ea55  push    [ebp+CodePage]; CodePage
0x1002ea5b  lea     edx, [ebp+String1]; String1
0x1002ea61  mov     ecx, edi; String2
0x1002ea63  push    100h; int
0x1002ea68  call    _WorkbookMakeValidColumnName@16; WorkbookMakeValidColumnName(x,x,x,x)
0x1002ea6d  mov     ebx, eax
0x1002ea6f  test    ebx, ebx
0x1002ea71  jnz     short loc_1002EA88
0x1002ea73  push    1
0x1002ea75  mov     edx, edi
0x1002ea77  mov     ecx, 0FFFFDFFAh
0x1002ea7c  call    _ErrorSetExtendedInfoSz1@12; ErrorSetExtendedInfoSz1(x,x,x)
0x1002ea81  mov     eax, 0FFFFFC16h
0x1002ea86  jmp     short loc_1002EB02
0x1002ea88  mov     ecx, [esi+4]
0x1002ea8b  lea     edx, [ebp+CodePage]
0x1002ea91  mov     ecx, [ecx+0Ch]
0x1002ea94  call    _WorkbookCodePage@8; WorkbookCodePage(x,x)
0x1002ea99  push    [ebp+CodePage]; CodePage
0x1002ea9f  mov     ecx, [ebp+var_40C]; String2
0x1002eaa5  lea     edx, [ebp+var_404]; String1
0x1002eaab  mov     edi, 100h
0x1002eab0  push    edi; int
0x1002eab1  call    _WorkbookMakeValidColumnName@16; WorkbookMakeValidColumnName(x,x,x,x)
0x1002eab6  lea     edx, [ebp+String1]
0x1002eabc  mov     ecx, esi
0x1002eabe  call    _ISAMDBLocateColumn@8; ISAMDBLocateColumn(x,x)
0x1002eac3  test    eax, eax
0x1002eac5  jz      short loc_1002EACE
0x1002eac7  mov     eax, 0FFFFFA1Ch
0x1002eacc  jmp     short loc_1002EB02
0x1002eace  lea     edx, [ebp+var_404]
0x1002ead4  mov     ecx, esi
0x1002ead6  call    _ISAMDBLocateColumn@8; ISAMDBLocateColumn(x,x)
0x1002eadb  test    eax, eax
0x1002eadd  jnz     short loc_1002EAE6
0x1002eadf  mov     eax, 0FFFFFA1Dh
0x1002eae4  jmp     short loc_1002EB02
0x1002eae6  push    edi
0x1002eae7  lea     ecx, [eax+2Ah]
0x1002eaea  lea     edx, [ebp+String1]
0x1002eaf0  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1002eaf5  xor     eax, eax
0x1002eaf7  mov     ecx, 1393h
0x1002eafc  cmp     ebx, 2
0x1002eaff  cmovz   eax, ecx
0x1002eb02  pop     ebx
0x1002eb03  mov     ecx, [ebp+var_4]
0x1002eb06  pop     edi
0x1002eb07  xor     ecx, ebp; StackCookie
0x1002eb09  pop     esi
0x1002eb0a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002eb0f  leave
0x1002eb10  retn    10h
```
