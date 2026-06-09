# ErrREPRenameTableCheck(x,x,x,x)

- ea: `0x10113c9c`
- end: `0x10113e44`
- name: `_ErrREPRenameTableCheck@16`
- size: `424`
- prototype: `int __thiscall(int, void *Src, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1001bed0`

## callees

- `0x1003e820`
- `0x1003e870`
- `0x10043090`
- `0x10043840`
- `0x10043ad0`
- `0x10044460`
- `0x10044b20`
- `0x10044b90`
- `0x10113c9c`
- `0x1011b210`
- `0x1011cda3`
- `0x10121449`

## string_xrefs

- `0x10113d60`: `+SideTable`
- `0x10113d48`: `SideTable`
- `0x10113d72`: `SideTable`
- `0x10113d86`: `SideTable`
- `0x10113d17`: `MSysSideTables`

## pseudocode

```c
int __fastcall ErrREPRenameTableCheck(int a1, int a2, unsigned __int16 *Src, _DWORD *a4)
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
        Index = ErrDispMakeKey(a1, v11, Src, 2 * wcslen(Src), 1);
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
0x10113c9c  mov     edi, edi
0x10113c9e  push    ebp
0x10113c9f  mov     ebp, esp
0x10113ca1  push    ecx
0x10113ca2  mov     eax, [ebp+arg_4]
0x10113ca5  push    ebx
0x10113ca6  push    esi
0x10113ca7  mov     esi, edx
0x10113ca9  mov     dword ptr [eax], 0
0x10113caf  push    edi
0x10113cb0  mov     edi, ecx
0x10113cb2  mov     eax, _rgrepdbinfo[esi*4]
0x10113cb9  mov     [ebp+var_4], eax
0x10113cbc  mov     eax, [eax+0E4h]
0x10113cc2  test    al, 10h
0x10113cc4  jnz     short loc_10113D3B
0x10113cc6  test    al, 1
0x10113cc8  jz      short loc_10113D3B
0x10113cca  mov     ebx, [ebp+Src]
0x10113ccd  mov     ecx, ebx
0x10113ccf  call    _FTableRepSystem@4; FTableRepSystem(x)
0x10113cd4  test    eax, eax
0x10113cd6  jz      short loc_10113CF2
0x10113cd8  xor     eax, eax
0x10113cda  push    eax; int
0x10113cdb  push    eax; int
0x10113cdc  push    eax; int
0x10113cdd  push    0FFFFDDD9h; int
0x10113ce2  push    eax; void *
0x10113ce3  push    eax; void *
0x10113ce4  push    ebx; Src
0x10113ce5  push    edi; int
0x10113ce6  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x10113ceb  mov     eax, 0FFFFB137h
0x10113cf0  jmp     short loc_10113D3D
0x10113cf2  push    [ebp+arg_4]
0x10113cf5  push    ebx
0x10113cf6  push    offset _wszTcObject; "Tables"
0x10113cfb  push    esi
0x10113cfc  push    edi
0x10113cfd  call    _ErrFObjectReplicable@20; ErrFObjectReplicable(x,x,x,x,x)
0x10113d02  test    eax, eax
0x10113d04  js      short loc_10113D3D
0x10113d06  mov     eax, [ebp+arg_4]
0x10113d09  cmp     dword ptr [eax], 0
0x10113d0c  jnz     loc_10113DFC
0x10113d12  push    80400000h
0x10113d17  push    offset _WZMSysSideTables; "MSysSideTables"
0x10113d1c  lea     eax, [ebp+var_4]
0x10113d1f  mov     [ebp+var_4], 0FFFFFFFFh
0x10113d26  push    eax
0x10113d27  push    esi
0x10113d28  push    edi
0x10113d29  call    _ErrDispOpenTable@20; ErrDispOpenTable(x,x,x,x,x)
0x10113d2e  cmp     eax, 0FFFFFAE7h
0x10113d33  jnz     short loc_10113D44
0x10113d35  push    edi
0x10113d36  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x10113d3b  xor     eax, eax
0x10113d3d  pop     edi
0x10113d3e  pop     esi
0x10113d3f  pop     ebx
0x10113d40  leave
0x10113d41  retn    8
0x10113d44  test    eax, eax
0x10113d46  js      short loc_10113D3D
0x10113d48  push    offset _WZSideTable; "SideTable"
0x10113d4d  push    [ebp+var_4]
0x10113d50  push    edi
0x10113d51  call    _ErrDispSetCurrentIndex@12; ErrDispSetCurrentIndex(x,x,x)
0x10113d56  mov     esi, eax
0x10113d58  cmp     esi, 0FFFFFA84h
0x10113d5e  jnz     short loc_10113D96
0x10113d60  mov     esi, offset _WZSideTablekey; "+SideTable"
0x10113d65  mov     ecx, esi
0x10113d67  call    _CbDoubleNullLen@4; CbDoubleNullLen(x)
0x10113d6c  xor     ecx, ecx
0x10113d6e  push    ecx
0x10113d6f  push    eax
0x10113d70  push    esi
0x10113d71  push    ecx
0x10113d72  push    offset _WZSideTable; "SideTable"
0x10113d77  push    [ebp+var_4]
0x10113d7a  push    edi
0x10113d7b  call    _ErrDispCreateIndex@28; ErrDispCreateIndex(x,x,x,x,x,x,x)
0x10113d80  mov     esi, eax
0x10113d82  test    esi, esi
0x10113d84  js      short loc_10113DE6
0x10113d86  push    offset _WZSideTable; "SideTable"
0x10113d8b  push    [ebp+var_4]
0x10113d8e  push    edi
0x10113d8f  call    _ErrDispSetCurrentIndex@12; ErrDispSetCurrentIndex(x,x,x)
0x10113d94  mov     esi, eax
0x10113d96  test    esi, esi
0x10113d98  js      short loc_10113DE6
0x10113d9a  mov     ecx, ebx
0x10113d9c  xor     esi, esi
0x10113d9e  lea     edx, [ecx+2]
0x10113da1  mov     ax, [ecx]
0x10113da4  add     ecx, 2
0x10113da7  cmp     ax, si
0x10113daa  jnz     short loc_10113DA1
0x10113dac  sub     ecx, edx
0x10113dae  sar     ecx, 1
0x10113db0  push    1
0x10113db2  lea     eax, [ecx+ecx]
0x10113db5  push    eax
0x10113db6  push    ebx
0x10113db7  push    [ebp+var_4]
0x10113dba  push    edi
0x10113dbb  call    _ErrDispMakeKey@20; ErrDispMakeKey(x,x,x,x,x)
0x10113dc0  mov     esi, eax
0x10113dc2  test    esi, esi
0x10113dc4  js      short loc_10113DE6
0x10113dc6  xor     ebx, ebx
0x10113dc8  inc     ebx
0x10113dc9  push    ebx
0x10113dca  push    [ebp+var_4]
0x10113dcd  push    edi
0x10113dce  call    _ErrDispSeek@12; ErrDispSeek(x,x,x)
0x10113dd3  mov     esi, eax
0x10113dd5  cmp     esi, 0FFFFF9BFh
0x10113ddb  jnz     short loc_10113DE1
0x10113ddd  xor     esi, esi
0x10113ddf  jmp     short loc_10113DE6
0x10113de1  mov     eax, [ebp+arg_4]
0x10113de4  mov     [eax], ebx
0x10113de6  cmp     [ebp+var_4], 0FFFFFFFFh
0x10113dea  jz      short loc_10113DF5
0x10113dec  push    [ebp+var_4]
0x10113def  push    edi
0x10113df0  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x10113df5  mov     eax, esi
0x10113df7  jmp     loc_10113D3D
0x10113dfc  mov     eax, [ebp+var_4]
0x10113dff  mov     eax, [eax+0E4h]
0x10113e05  test    al, 2
0x10113e07  jnz     short loc_10113E13
0x10113e09  mov     eax, 0FFFFB1DDh
0x10113e0e  jmp     loc_10113D3D
0x10113e13  test    eax, 80000h
0x10113e18  jz      short loc_10113E24
0x10113e1a  mov     eax, 0FFFFB0ABh
0x10113e1f  jmp     loc_10113D3D
0x10113e24  mov     eax, _rgrepdbinfo[esi*4]
0x10113e2b  mov     eax, [eax+0CCh]
0x10113e31  and     eax, 10000h
0x10113e36  neg     eax
0x10113e38  sbb     eax, eax
0x10113e3a  and     eax, 0FFFFB0A4h
0x10113e3f  jmp     loc_10113D3D
```
