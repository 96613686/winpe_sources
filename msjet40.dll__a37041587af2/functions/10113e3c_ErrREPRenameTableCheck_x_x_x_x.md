# ErrREPRenameTableCheck(x,x,x,x)

- ea: `0x10113e3c`
- end: `0x10113fe4`
- name: `_ErrREPRenameTableCheck@16`
- size: `424`
- prototype: `int __thiscall(int, void *Src, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1001c020`

## callees

- `0x1003e9b0`
- `0x1003ea00`
- `0x10043220`
- `0x100439d0`
- `0x10043c60`
- `0x100445e0`
- `0x10044ca0`
- `0x10044d10`
- `0x10113e3c`
- `0x1011b3c0`
- `0x1011cf53`
- `0x101215f9`

## string_xrefs

- `0x10113f00`: `+SideTable`
- `0x10113ee8`: `SideTable`
- `0x10113f12`: `SideTable`
- `0x10113f26`: `SideTable`
- `0x10113eb7`: `MSysSideTables`

## pseudocode

```c
int __fastcall ErrREPRenameTableCheck(int a1, int a2, void *Src, _DWORD *a4)
{
  int v6; // eax
  int result; // eax
  int Index; // esi
  int v9; // eax
  int v10; // eax
  int v11; // [esp+Ch] [ebp-4h] BYREF

  *a4 = 0;
  v11 = (int)*(&rgrepdbinfo + a2);
  v6 = *(_DWORD *)(v11 + 228);
  if ( (v6 & 0x10) != 0 || (v6 & 1) == 0 )
    return 0;
  if ( FTableRepSystem(Src) )
  {
    UtilSetErrorInfoReal(a1, Src, 0, 0, -8743, 0, 0, 0);
    return -20169;
  }
  result = ErrFObjectReplicable(a1, a2, L"Tables", Src, a4);
  if ( result >= 0 )
  {
    if ( *a4 )
    {
      v10 = *(_DWORD *)(v11 + 228);
      if ( (v10 & 2) == 0 )
        return -20003;
      if ( (v10 & 0x80000) != 0 )
        return -20309;
      return (*((_DWORD *)*(&rgrepdbinfo + a2) + 51) & 0x10000) != 0 ? 0xFFFFB0A4 : 0;
    }
    v11 = -1;
    result = ErrDispOpenTable(a1, a2, &v11, L"MSysSideTables", -2143289344);
    if ( result == -1305 )
    {
      ClearErrorInfo(a1);
      return 0;
    }
    if ( result >= 0 )
    {
      Index = ErrDispSetCurrentIndex(a1, v11, L"SideTable");
      if ( Index == -1404 )
      {
        v9 = CbDoubleNullLen(L"+SideTable");
        Index = ErrDispCreateIndex(a1, v11, L"SideTable", 0, L"+SideTable", v9, 0);
        if ( Index < 0 )
        {
LABEL_20:
          if ( v11 != -1 )
            ErrDispCloseTable(a1, v11);
          return Index;
        }
        Index = ErrDispSetCurrentIndex(a1, v11, L"SideTable");
      }
      if ( Index >= 0 )
      {
        Index = ErrDispMakeKey(a1, v11, Src, 2 * wcslen((const unsigned __int16 *)Src), 1);
        if ( Index >= 0 )
        {
          Index = ErrDispSeek(a1, v11, 1);
          if ( Index == -1601 )
            Index = 0;
          else
            *a4 = 1;
        }
      }
      goto LABEL_20;
    }
  }
  return result;
}

```

## disassembly

```asm
0x10113e3c  mov     edi, edi
0x10113e3e  push    ebp
0x10113e3f  mov     ebp, esp
0x10113e41  push    ecx
0x10113e42  mov     eax, [ebp+arg_4]
0x10113e45  push    ebx
0x10113e46  push    esi
0x10113e47  mov     esi, edx
0x10113e49  mov     dword ptr [eax], 0
0x10113e4f  push    edi
0x10113e50  mov     edi, ecx
0x10113e52  mov     eax, _rgrepdbinfo[esi*4]
0x10113e59  mov     [ebp+var_4], eax
0x10113e5c  mov     eax, [eax+0E4h]
0x10113e62  test    al, 10h
0x10113e64  jnz     short loc_10113EDB
0x10113e66  test    al, 1
0x10113e68  jz      short loc_10113EDB
0x10113e6a  mov     ebx, [ebp+Src]
0x10113e6d  mov     ecx, ebx
0x10113e6f  call    _FTableRepSystem@4; FTableRepSystem(x)
0x10113e74  test    eax, eax
0x10113e76  jz      short loc_10113E92
0x10113e78  xor     eax, eax
0x10113e7a  push    eax; int
0x10113e7b  push    eax; int
0x10113e7c  push    eax; int
0x10113e7d  push    0FFFFDDD9h; int
0x10113e82  push    eax; void *
0x10113e83  push    eax; void *
0x10113e84  push    ebx; Src
0x10113e85  push    edi; int
0x10113e86  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x10113e8b  mov     eax, 0FFFFB137h
0x10113e90  jmp     short loc_10113EDD
0x10113e92  push    [ebp+arg_4]
0x10113e95  push    ebx
0x10113e96  push    offset _wszTcObject; "Tables"
0x10113e9b  push    esi
0x10113e9c  push    edi
0x10113e9d  call    _ErrFObjectReplicable@20; ErrFObjectReplicable(x,x,x,x,x)
0x10113ea2  test    eax, eax
0x10113ea4  js      short loc_10113EDD
0x10113ea6  mov     eax, [ebp+arg_4]
0x10113ea9  cmp     dword ptr [eax], 0
0x10113eac  jnz     loc_10113F9C
0x10113eb2  push    80400000h
0x10113eb7  push    offset _WZMSysSideTables; "MSysSideTables"
0x10113ebc  lea     eax, [ebp+var_4]
0x10113ebf  mov     [ebp+var_4], 0FFFFFFFFh
0x10113ec6  push    eax
0x10113ec7  push    esi
0x10113ec8  push    edi
0x10113ec9  call    _ErrDispOpenTable@20; ErrDispOpenTable(x,x,x,x,x)
0x10113ece  cmp     eax, 0FFFFFAE7h
0x10113ed3  jnz     short loc_10113EE4
0x10113ed5  push    edi
0x10113ed6  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x10113edb  xor     eax, eax
0x10113edd  pop     edi
0x10113ede  pop     esi
0x10113edf  pop     ebx
0x10113ee0  leave
0x10113ee1  retn    8
0x10113ee4  test    eax, eax
0x10113ee6  js      short loc_10113EDD
0x10113ee8  push    offset _WZSideTable; "SideTable"
0x10113eed  push    [ebp+var_4]
0x10113ef0  push    edi
0x10113ef1  call    _ErrDispSetCurrentIndex@12; ErrDispSetCurrentIndex(x,x,x)
0x10113ef6  mov     esi, eax
0x10113ef8  cmp     esi, 0FFFFFA84h
0x10113efe  jnz     short loc_10113F36
0x10113f00  mov     esi, offset _WZSideTablekey; "+SideTable"
0x10113f05  mov     ecx, esi
0x10113f07  call    _CbDoubleNullLen@4; CbDoubleNullLen(x)
0x10113f0c  xor     ecx, ecx
0x10113f0e  push    ecx
0x10113f0f  push    eax
0x10113f10  push    esi
0x10113f11  push    ecx
0x10113f12  push    offset _WZSideTable; "SideTable"
0x10113f17  push    [ebp+var_4]
0x10113f1a  push    edi
0x10113f1b  call    _ErrDispCreateIndex@28; ErrDispCreateIndex(x,x,x,x,x,x,x)
0x10113f20  mov     esi, eax
0x10113f22  test    esi, esi
0x10113f24  js      short loc_10113F86
0x10113f26  push    offset _WZSideTable; "SideTable"
0x10113f2b  push    [ebp+var_4]
0x10113f2e  push    edi
0x10113f2f  call    _ErrDispSetCurrentIndex@12; ErrDispSetCurrentIndex(x,x,x)
0x10113f34  mov     esi, eax
0x10113f36  test    esi, esi
0x10113f38  js      short loc_10113F86
0x10113f3a  mov     ecx, ebx
0x10113f3c  xor     esi, esi
0x10113f3e  lea     edx, [ecx+2]
0x10113f41  mov     ax, [ecx]
0x10113f44  add     ecx, 2
0x10113f47  cmp     ax, si
0x10113f4a  jnz     short loc_10113F41
0x10113f4c  sub     ecx, edx
0x10113f4e  sar     ecx, 1
0x10113f50  push    1
0x10113f52  lea     eax, [ecx+ecx]
0x10113f55  push    eax
0x10113f56  push    ebx
0x10113f57  push    [ebp+var_4]
0x10113f5a  push    edi
0x10113f5b  call    _ErrDispMakeKey@20; ErrDispMakeKey(x,x,x,x,x)
0x10113f60  mov     esi, eax
0x10113f62  test    esi, esi
0x10113f64  js      short loc_10113F86
0x10113f66  xor     ebx, ebx
0x10113f68  inc     ebx
0x10113f69  push    ebx
0x10113f6a  push    [ebp+var_4]
0x10113f6d  push    edi
0x10113f6e  call    _ErrDispSeek@12; ErrDispSeek(x,x,x)
0x10113f73  mov     esi, eax
0x10113f75  cmp     esi, 0FFFFF9BFh
0x10113f7b  jnz     short loc_10113F81
0x10113f7d  xor     esi, esi
0x10113f7f  jmp     short loc_10113F86
0x10113f81  mov     eax, [ebp+arg_4]
0x10113f84  mov     [eax], ebx
0x10113f86  cmp     [ebp+var_4], 0FFFFFFFFh
0x10113f8a  jz      short loc_10113F95
0x10113f8c  push    [ebp+var_4]
0x10113f8f  push    edi
0x10113f90  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x10113f95  mov     eax, esi
0x10113f97  jmp     loc_10113EDD
0x10113f9c  mov     eax, [ebp+var_4]
0x10113f9f  mov     eax, [eax+0E4h]
0x10113fa5  test    al, 2
0x10113fa7  jnz     short loc_10113FB3
0x10113fa9  mov     eax, 0FFFFB1DDh
0x10113fae  jmp     loc_10113EDD
0x10113fb3  test    eax, 80000h
0x10113fb8  jz      short loc_10113FC4
0x10113fba  mov     eax, 0FFFFB0ABh
0x10113fbf  jmp     loc_10113EDD
0x10113fc4  mov     eax, _rgrepdbinfo[esi*4]
0x10113fcb  mov     eax, [eax+0CCh]
0x10113fd1  and     eax, 10000h
0x10113fd6  neg     eax
0x10113fd8  sbb     eax, eax
0x10113fda  and     eax, 0FFFFB0A4h
0x10113fdf  jmp     loc_10113EDD
```
