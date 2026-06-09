# NormalizeNteStatus

- ea: `0x18000c8e0`
- end: `0x18000ca73`
- name: `NormalizeNteStatus`
- size: `403`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `70`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x180006730`
- `0x180008820`
- `0x180009830`
- `0x180009aa0`
- `0x180009cf0`
- `0x18000a3d0`
- `0x18000a7e0`
- `0x18000aa90`
- `0x18000acd0`
- `0x18000adc0`
- `0x18000b050`
- `0x18000b290`
- `0x18000b4f0`
- `0x18000b6c0`
- `0x18000b8a0`
- `0x18000ba30`
- `0x18000bb60`
- `0x18000bcc0`
- `0x18000c270`
- `0x18000c5b0`
- `0x18000c700`
- `0x18000d100`
- `0x18000e170`
- `0x18000e3b0`
- `0x18000ed40`
- `0x18000f290`
- `0x18000fb20`
- `0x1800102c0`
- `0x180010a90`
- `0x180010c90`
- `0x180011310`
- `0x180011470`
- `0x1800116b0`
- `0x180011950`
- `0x180011f00`
- `0x180012120`
- `0x180012a70`
- `0x180012bb0`
- `0x180012e00`
- `0x180013190`
- `0x1800133d0`
- `0x180013630`
- `0x180013790`
- `0x1800140b0`
- `0x1800147a0`
- `0x180015030`
- `0x180015770`
- `0x180015cd0`
- `0x180016350`
- `0x180016620`

## callees

- `0x18000c8e0`

## pseudocode

```c
__int64 __fastcall NormalizeNteStatus(unsigned int a1)
{
  __int64 result; // rax

  if ( (a1 & 0x1FFF0000) == 0x90000 || (a1 & 0x1FFF0000) == 0x100000 || !a1 )
    return a1;
  if ( a1 > 0x216 )
  {
    if ( a1 > 0xC000007B )
    {
      if ( a1 <= 0xC0000135 )
      {
        if ( a1 == -1073741515 )
          return 2148073502LL;
        if ( a1 == -1073741637 )
          return 2148073513LL;
        if ( a1 != -1073741670 )
        {
          if ( a1 != -1073741595 )
            return a1;
          return 2148073517LL;
        }
        return 2148073486LL;
      }
      if ( a1 != -1073741502 && a1 != -1073741511 )
      {
        if ( a1 == -1073700864 )
          return 2148073478LL;
        return a1;
      }
    }
    else if ( a1 != -1073741701 )
    {
      if ( a1 == -1073741816 )
        return 2148073510LL;
      if ( a1 <= 0xC0000008 )
      {
        if ( a1 == -2147023680 )
          return 2147943616LL;
        if ( a1 != 1359 )
        {
          if ( a1 == -2147023673 )
            return 2147943623LL;
          if ( a1 == -2147023496 )
            return 2147943800LL;
          return a1;
        }
        return 2148073517LL;
      }
      if ( a1 == -1073741811 )
        return 2148073511LL;
      if ( a1 != -1073741801 )
      {
        if ( a1 == -1073741789 )
          return 2148073512LL;
        return a1;
      }
      return 2148073486LL;
    }
    return 2148073501LL;
  }
  if ( a1 == 534 )
    return 2147942934LL;
  switch ( a1 )
  {
    case 2u:
    case 3u:
      result = 2148073489LL;
      break;
    case 5u:
      result = 2148073488LL;
      break;
    case 8u:
    case 0xEu:
      return 2148073486LL;
    case 0x57u:
      return 2148073511LL;
    case 0x70u:
      result = 2147942512LL;
      break;
    case 0x7Au:
      return 2148073512LL;
    case 0xB7u:
      result = 2148073487LL;
      break;
    default:
      return a1;
  }
  return result;
}

```

## disassembly

```asm
0x18000c8e0  mov     eax, ecx
0x18000c8e2  and     eax, 1FFF0000h
0x18000c8e7  cmp     eax, 90000h
0x18000c8ec  jz      short def_18000C92F; jumptable 000000018000C92F default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000c8ee  cmp     eax, 100000h
0x18000c8f3  jz      short def_18000C92F; jumptable 000000018000C92F default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000c8f5  test    ecx, ecx
0x18000c8f7  jnz     short loc_18000C8FC
0x18000c8f9  mov     eax, ecx; jumptable 000000018000C92F default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000c8fb  retn
0x18000c8fc  cmp     ecx, 216h
0x18000c902  ja      short loc_18000C939
0x18000c904  jz      loc_18000C9FB
0x18000c90a  lea     eax, [rcx-2]; switch 182 cases
0x18000c90d  cmp     eax, 0B5h
0x18000c912  ja      short def_18000C92F; jumptable 000000018000C92F default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000c914  lea     r8, __ImageBase
0x18000c91b  movzx   eax, ds:(byte_18000CA94 - 180000000h)[r8+rax]
0x18000c924  mov     edx, ds:(jpt_18000C92F - 180000000h)[r8+rax*4]
0x18000c92c  add     rdx, r8
0x18000c92f  jmp     rdx; switch jump
0x18000c931  mov     ecx, 80090027h; jumptable 000000018000C92F case 87
0x18000c936  mov     eax, ecx
0x18000c938  retn
0x18000c939  cmp     ecx, 0C000007Bh
0x18000c93f  ja      short loc_18000C98D
0x18000c941  jz      loc_18000CA33
0x18000c947  cmp     ecx, 0C0000008h
0x18000c94d  jz      loc_18000C9DB
0x18000c953  ja      loc_18000CA3B
0x18000c959  cmp     ecx, 800704C0h
0x18000c95f  jz      short loc_18000C9D3
0x18000c961  cmp     ecx, 54Fh
0x18000c967  jz      loc_18000CA13
0x18000c96d  cmp     ecx, 800704C7h
0x18000c973  jz      loc_18000CA1B
0x18000c979  cmp     ecx, 80070578h
0x18000c97f  jnz     def_18000C92F; jumptable 000000018000C92F default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000c985  mov     ecx, 80070578h
0x18000c98a  mov     eax, ecx
0x18000c98c  retn
0x18000c98d  cmp     ecx, 0C0000135h
0x18000c993  ja      short loc_18000C9AF
0x18000c995  jz      loc_18000CA23
0x18000c99b  cmp     ecx, 0C00000BBh
0x18000c9a1  jnz     loc_18000CA5D
0x18000c9a7  mov     ecx, 80090029h
0x18000c9ac  mov     eax, ecx
0x18000c9ae  retn
0x18000c9af  cmp     ecx, 0C0000142h
0x18000c9b5  jz      short loc_18000CA33
0x18000c9b7  cmp     ecx, 0C0000139h
0x18000c9bd  jz      short loc_18000CA33
0x18000c9bf  cmp     ecx, 0C000A000h
0x18000c9c5  jnz     def_18000C92F; jumptable 000000018000C92F default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000c9cb  mov     ecx, 80090006h
0x18000c9d0  mov     eax, ecx
0x18000c9d2  retn
0x18000c9d3  mov     ecx, 800704C0h
0x18000c9d8  mov     eax, ecx
0x18000c9da  retn
0x18000c9db  mov     ecx, 80090026h
0x18000c9e0  mov     eax, ecx
0x18000c9e2  retn
0x18000c9e3  mov     ecx, 80090028h; jumptable 000000018000C92F case 122
0x18000c9e8  mov     eax, ecx
0x18000c9ea  retn
0x18000c9eb  mov     ecx, 80090011h; jumptable 000000018000C92F cases 2,3
0x18000c9f0  mov     eax, ecx
0x18000c9f2  retn
0x18000c9f3  mov     ecx, 80070070h; jumptable 000000018000C92F case 112
0x18000c9f8  mov     eax, ecx
0x18000c9fa  retn
0x18000c9fb  mov     ecx, 80070216h
0x18000ca00  mov     eax, ecx
0x18000ca02  retn
0x18000ca03  mov     ecx, 80090010h; jumptable 000000018000C92F case 5
0x18000ca08  mov     eax, ecx
0x18000ca0a  retn
0x18000ca0b  mov     ecx, 8009000Fh; jumptable 000000018000C92F case 183
0x18000ca10  mov     eax, ecx
0x18000ca12  retn
0x18000ca13  mov     ecx, 8009002Dh
0x18000ca18  mov     eax, ecx
0x18000ca1a  retn
0x18000ca1b  mov     ecx, 800704C7h
0x18000ca20  mov     eax, ecx
0x18000ca22  retn
0x18000ca23  mov     ecx, 8009001Eh
0x18000ca28  mov     eax, ecx
0x18000ca2a  retn
0x18000ca2b  mov     ecx, 8009000Eh; jumptable 000000018000C92F cases 8,14
0x18000ca30  mov     eax, ecx
0x18000ca32  retn
0x18000ca33  mov     ecx, 8009001Dh
0x18000ca38  mov     eax, ecx
0x18000ca3a  retn
0x18000ca3b  cmp     ecx, 0C000000Dh
0x18000ca41  jz      loc_18000C931; jumptable 000000018000C92F case 87
0x18000ca47  cmp     ecx, 0C0000017h
0x18000ca4d  jz      short loc_18000CA2B; jumptable 000000018000C92F cases 8,14
0x18000ca4f  cmp     ecx, 0C0000023h
0x18000ca55  jnz     def_18000C92F; jumptable 000000018000C92F default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000ca5b  jmp     short loc_18000C9E3; jumptable 000000018000C92F case 122
0x18000ca5d  cmp     ecx, 0C000009Ah
0x18000ca63  jz      short loc_18000CA2B; jumptable 000000018000C92F cases 8,14
0x18000ca65  cmp     ecx, 0C00000E5h
0x18000ca6b  jnz     def_18000C92F; jumptable 000000018000C92F default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000ca71  jmp     short loc_18000CA13
```
