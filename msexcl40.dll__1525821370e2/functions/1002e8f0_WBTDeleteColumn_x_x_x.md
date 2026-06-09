# WBTDeleteColumn(x,x,x)

- ea: `0x1002e8f0`
- end: `0x1002e9e2`
- name: `_WBTDeleteColumn@12`
- size: `242`
- prototype: `int __stdcall(int, int, wchar_t *String2)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x1001a630`
- `0x1001e4b0`
- `0x100246ef`
- `0x10025ab7`
- `0x1002acaf`
- `0x1002ae15`
- `0x1002aea1`
- `0x1002e56d`
- `0x1002e8f0`
- `0x10035510`

## pseudocode

```c
int __stdcall WBTDeleteColumn(int a1, int a2, wchar_t *String2)
{
  int v3; // eax
  int v4; // esi
  int result; // eax
  int v6; // ebx
  int v7; // eax
  int v8; // edx
  _DWORD *v9; // ecx
  _DWORD *v10; // edi
  int v11; // eax
  UINT CodePage; // [esp+8h] [ebp-208h] BYREF
  wchar_t String1[256]; // [esp+Ch] [ebp-204h] BYREF

  v3 = ISAMDBFindCursor(a1, a2);
  v4 = v3;
  if ( !v3 )
    return -1310;
  result = ColumnOperationOK(v3);
  if ( !result )
  {
    v6 = *(_DWORD *)(v4 + 4);
    WorkbookCodePage(*(_DWORD *)(*(_DWORD *)(v6 + 4) + 12), &CodePage);
    if ( WorkbookMakeValidColumnName(String2, String1, 256, CodePage) )
    {
      v7 = ISAMDBLocateColumn(v6, String1);
      v8 = v7;
      if ( v7 )
      {
        if ( *(_DWORD *)(v7 + 16) == 12 )
        {
          v9 = *(_DWORD **)(v4 + 52);
          v10 = 0;
          while ( v9 )
          {
            v11 = *v9;
            if ( v9[1] == v8 )
            {
              if ( v10 )
                *v10 = v11;
              else
                *(_DWORD *)(v4 + 52) = v11;
              MemFree(v9);
              break;
            }
            v10 = v9;
            v9 = (_DWORD *)*v9;
          }
        }
        ISAMDBDeleteColumn(v6, String1);
        return 0;
      }
      else
      {
        return -1507;
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
0x1002e8f0  mov     edi, edi
0x1002e8f2  push    ebp
0x1002e8f3  mov     ebp, esp
0x1002e8f5  sub     esp, 208h
0x1002e8fb  mov     eax, ___security_cookie
0x1002e900  xor     eax, ebp
0x1002e902  mov     [ebp+var_4], eax
0x1002e905  mov     ecx, [ebp+arg_0]
0x1002e908  mov     edx, [ebp+arg_4]
0x1002e90b  push    esi
0x1002e90c  push    edi
0x1002e90d  mov     edi, [ebp+String2]
0x1002e910  call    _ISAMDBFindCursor@8; ISAMDBFindCursor(x,x)
0x1002e915  mov     esi, eax
0x1002e917  test    esi, esi
0x1002e919  jnz     short loc_1002E925
0x1002e91b  mov     eax, 0FFFFFAE2h
0x1002e920  jmp     loc_1002E9D2
0x1002e925  mov     ecx, esi
0x1002e927  call    ColumnOperationOK
0x1002e92c  test    eax, eax
0x1002e92e  jnz     loc_1002E9D2
0x1002e934  push    ebx
0x1002e935  mov     ebx, [esi+4]
0x1002e938  lea     edx, [ebp+CodePage]
0x1002e93e  mov     ecx, [ebx+4]
0x1002e941  mov     ecx, [ecx+0Ch]
0x1002e944  call    _WorkbookCodePage@8; WorkbookCodePage(x,x)
0x1002e949  push    [ebp+CodePage]; CodePage
0x1002e94f  lea     edx, [ebp+String1]; String1
0x1002e955  mov     ecx, edi; String2
0x1002e957  push    100h; int
0x1002e95c  call    _WorkbookMakeValidColumnName@16; WorkbookMakeValidColumnName(x,x,x,x)
0x1002e961  test    eax, eax
0x1002e963  jnz     short loc_1002E97A
0x1002e965  push    1
0x1002e967  mov     edx, edi
0x1002e969  mov     ecx, 0FFFFDFFAh
0x1002e96e  call    _ErrorSetExtendedInfoSz1@12; ErrorSetExtendedInfoSz1(x,x,x)
0x1002e973  mov     eax, 0FFFFFC16h
0x1002e978  jmp     short loc_1002E9D1
0x1002e97a  lea     edx, [ebp+String1]
0x1002e980  mov     ecx, ebx
0x1002e982  call    _ISAMDBLocateColumn@8; ISAMDBLocateColumn(x,x)
0x1002e987  mov     edx, eax
0x1002e989  test    edx, edx
0x1002e98b  jnz     short loc_1002E994
0x1002e98d  mov     eax, 0FFFFFA1Dh
0x1002e992  jmp     short loc_1002E9D1
0x1002e994  cmp     dword ptr [edx+10h], 0Ch
0x1002e998  jnz     short loc_1002E9C2
0x1002e99a  mov     ecx, [esi+34h]
0x1002e99d  xor     edi, edi
0x1002e99f  jmp     short loc_1002E9AC
0x1002e9a1  mov     eax, [ecx]
0x1002e9a3  cmp     [ecx+4], edx
0x1002e9a6  jz      short loc_1002E9B2
0x1002e9a8  mov     edi, ecx
0x1002e9aa  mov     ecx, eax
0x1002e9ac  test    ecx, ecx
0x1002e9ae  jnz     short loc_1002E9A1
0x1002e9b0  jmp     short loc_1002E9C2
0x1002e9b2  test    edi, edi
0x1002e9b4  jnz     short loc_1002E9BB
0x1002e9b6  mov     [esi+34h], eax
0x1002e9b9  jmp     short loc_1002E9BD
0x1002e9bb  mov     [edi], eax
0x1002e9bd  call    _MemFree@4; MemFree(x)
0x1002e9c2  lea     edx, [ebp+String1]
0x1002e9c8  mov     ecx, ebx
0x1002e9ca  call    _ISAMDBDeleteColumn@8; ISAMDBDeleteColumn(x,x)
0x1002e9cf  xor     eax, eax
0x1002e9d1  pop     ebx
0x1002e9d2  mov     ecx, [ebp+var_4]
0x1002e9d5  pop     edi
0x1002e9d6  xor     ecx, ebp; StackCookie
0x1002e9d8  pop     esi
0x1002e9d9  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002e9de  leave
0x1002e9df  retn    0Ch
```
