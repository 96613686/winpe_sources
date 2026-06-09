# RmtGenDelete

- ea: `0x100d991a`
- end: `0x100d99f7`
- name: `RmtGenDelete`
- size: `221`
- prototype: `int __stdcall(LPCVOID lpAddress, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x100d99fd`

## callees

- `0x100af0fe`
- `0x100b0db5`
- `0x100b767a`
- `0x100d9565`
- `0x100d991a`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!longjmp` at `0x100d9956`
- `api-ms-win-crt-private-l1-1-0!longjmp` at `0x100d9956`

## string_xrefs

- `0x100d9961`: `DELETE FROM`

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
0x100d991a  mov     edi, edi
0x100d991c  push    ebp
0x100d991d  mov     ebp, esp
0x100d991f  push    ecx
0x100d9920  push    ecx
0x100d9921  push    ebx
0x100d9922  push    esi
0x100d9923  mov     esi, [ebp+arg_4]
0x100d9926  mov     ebx, edx
0x100d9928  push    edi
0x100d9929  mov     edi, [ebp+lpAddress]
0x100d992c  add     esi, 418h
0x100d9932  push    esi
0x100d9933  mov     eax, [ebx+12Ch]
0x100d9939  push    1
0x100d993b  push    2
0x100d993d  mov     [ebp+var_4], ecx
0x100d9940  mov     ecx, edi
0x100d9942  pop     edx
0x100d9943  mov     [ebp+var_8], eax
0x100d9946  call    _ErrCallocPvHsegREAL@16; ErrCallocPvHsegREAL(x,x,x,x)
0x100d994b  test    eax, eax
0x100d994d  jns     short loc_100D995C
0x100d994f  push    eax; Value
0x100d9950  mov     eax, [ebp+var_4]
0x100d9953  push    dword ptr [eax+18h]; Buf
0x100d9956  call    ds:__imp__longjmp
0x100d995c  push    offset asc_1000EF38; " "
0x100d9961  push    offset aDeleteFrom; "DELETE FROM"
0x100d9966  mov     edx, esi
0x100d9968  mov     ecx, edi
0x100d996a  call    _PPRmtStrcat2REAL@16; PPRmtStrcat2REAL(x,x,x,x)
0x100d996f  mov     eax, [ebp+var_8]
0x100d9972  mov     edx, esi
0x100d9974  add     eax, 30h ; '0'
0x100d9977  mov     ecx, edi
0x100d9979  push    eax; Src
0x100d997a  push    dword ptr [ebx+110h]; Str
0x100d9980  call    _PPAddOwnerTable@16; PPAddOwnerTable(x,x,x,x)
0x100d9985  mov     ecx, [esi]
0x100d9987  mov     [ebp+var_8], 0
0x100d998e  lea     edx, [ecx+2]
0x100d9991  mov     ax, [ecx]
0x100d9994  add     ecx, 2
0x100d9997  cmp     ax, word ptr [ebp+var_8]
0x100d999b  jnz     short loc_100D9991
0x100d999d  mov     eax, [ebp+arg_4]
0x100d99a0  sub     ecx, edx
0x100d99a2  sar     ecx, 1
0x100d99a4  mov     edx, esi
0x100d99a6  mov     [eax+41Ch], cx
0x100d99ad  mov     ecx, edi
0x100d99af  push    dword ptr [ebx+11Ch]; void *
0x100d99b5  push    offset aWhere_0; " WHERE "
0x100d99ba  call    _PPRmtStrcat2REAL@16; PPRmtStrcat2REAL(x,x,x,x)
0x100d99bf  mov     eax, [ebp+var_4]
0x100d99c2  cmp     word ptr [eax+88h], 5
0x100d99ca  jz      short loc_100D99F0
0x100d99cc  mov     eax, [ebx+128h]
0x100d99d2  test    eax, eax
0x100d99d4  jz      short loc_100D99E4
0x100d99d6  push    0; void *
0x100d99d8  push    eax; Src
0x100d99d9  mov     edx, esi
0x100d99db  mov     ecx, edi
0x100d99dd  call    _PPRmtStrcat2REAL@16; PPRmtStrcat2REAL(x,x,x,x)
0x100d99e2  jmp     short loc_100D99F0
0x100d99e4  push    esi; int
0x100d99e5  push    [ebp+arg_4]; int
0x100d99e8  mov     edx, ebx
0x100d99ea  push    edi; lpAddress
0x100d99eb  call    AddAllColsQual
0x100d99f0  pop     edi
0x100d99f1  pop     esi
0x100d99f2  pop     ebx
0x100d99f3  leave
0x100d99f4  retn    8
```
