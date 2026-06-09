# PwrshPlugInMediator::CreateMgdPluginFileName(int,int,ushort *,ushort * *)

- ea: `0x1800025d0`
- end: `0x18000297a`
- name: `?CreateMgdPluginFileName@PwrshPlugInMediator@@AEAAIHHPEAGPEAPEAG@Z`
- size: `938`
- prototype: `__int64 __fastcall(PwrshPlugInMediator *this, int, int, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003158`

## callees

- `0x180001318`
- `0x1800025d0`
- `0x180004228`
- `0x180007c2c`

## import_xrefs

- `msvcrt!_itow_s` at `0x180002644`
- `msvcrt!_itow_s` at `0x180002660`
- `msvcrt!_itow_s` at `0x180002644`
- `msvcrt!_itow_s` at `0x180002660`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000271a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000272a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000294a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000295a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000271a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000272a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000294a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000295a`

## string_xrefs

- `0x18000274a`: `PSPluginWkrModuleName`
- `0x1800027c8`: `pspluginwkr.dll`
- `0x18000291f`: `pspluginwkr.dll`

## pseudocode

```c
__int64 __fastcall PwrshPlugInMediator::CreateMgdPluginFileName(
        PwrshPlugInMediator *this,
        int a2,
        int a3,
        unsigned __int16 *a4,
        unsigned __int16 **a5)
{
  PwrshPlugInMediator *v5; // rsi
  wchar_t *v9; // rbp
  unsigned __int16 *v10; // r14
  __int64 v11; // r15
  __int64 v12; // rdx
  wchar_t *v13; // rax
  __int64 v14; // rcx
  unsigned __int16 *v15; // rax
  unsigned int RegistryInfo; // ebx
  unsigned __int64 v17; // rsi
  unsigned __int16 *v18; // rax
  unsigned __int16 *v19; // rdi
  NativeMsh::PwrshCommon *v20; // rcx
  unsigned __int16 **v21; // rsi
  unsigned __int16 *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  const unsigned __int16 *v25; // rax
  unsigned __int64 v26; // rdi
  unsigned __int16 *v27; // rax
  unsigned __int16 *v28; // r10
  __int64 v29; // rcx
  wchar_t *v30; // rdx
  unsigned __int64 v31; // r8
  unsigned __int16 *v32; // rcx
  unsigned __int64 v33; // r9
  unsigned __int16 *v34; // rcx
  unsigned __int16 *v36; // [rsp+40h] [rbp-48h] BYREF
  unsigned __int16 *v37; // [rsp+48h] [rbp-40h] BYREF
  int v39; // [rsp+98h] [rbp+10h] BYREF

  *((_DWORD *)this + 19) = a2;
  v5 = this;
  v39 = a2;
  v36 = 0;
  v37 = 0;
  v9 = (wchar_t *)operator new[](0x14u);
  v10 = (unsigned __int16 *)operator new[](0x14u);
  v11 = 2147483646;
  if ( a2 >= 0 && a3 >= 0 && !_itow_s(a2, v9, 0xAu, 10) && !_itow_s(a3, v10, 0xAu, 10) && v9 )
  {
    v12 = 10;
    v13 = v9;
    do
    {
      if ( !*v13 )
        break;
      ++v13;
      --v12;
    }
    while ( v12 );
    if ( v12 && v10 )
    {
      v14 = 10;
      v15 = v10;
      do
      {
        if ( !*v15 )
          break;
        ++v15;
        --v14;
      }
      while ( v14 );
      RegistryInfo = 0;
      if ( v14 )
      {
        v17 = ((10 - v14) & ((unsigned __int128)-(__int128)(unsigned __int64)v14 >> 64))
            + ((10 - v12) & -(__int64)(v12 != 0))
            + 2;
        v18 = (unsigned __int16 *)operator new[](saturated_mul(v17, 2u));
        v36 = v18;
        v19 = v18;
        if ( v18 )
        {
          *v18 = 0;
          if ( v17 - 1 > 0x7FFFFFFE )
            goto LABEL_44;
          v29 = 2147483646;
          v30 = v9;
          v31 = v17;
          do
          {
            if ( !v29 )
              break;
            if ( !*v30 )
              break;
            *v18++ = *v30++;
            --v29;
            --v31;
          }
          while ( v31 );
          v32 = v18 - 1;
          if ( v31 )
            v32 = v18;
          *v32 = 0;
          if ( !v31 || (int)StringCchCatW(v19, v17, L".") < 0 || (int)StringCchCatW(v19, v17, v10) < 0 )
LABEL_44:
            RegistryInfo = 100;
        }
        else
        {
          RegistryInfo = 8;
        }
        v5 = this;
        goto LABEL_18;
      }
    }
  }
  RegistryInfo = 100;
  if ( v9 )
LABEL_18:
    operator delete[](v9);
  if ( v10 )
    operator delete[](v10);
  if ( !RegistryInfo )
  {
    v20 = (PwrshPlugInMediator *)((char *)v5 + 160);
    v21 = a5;
    RegistryInfo = NativeMsh::PwrshCommon::GetRegistryInfo(v20, &v36, &v39, a3, &v37, L"PSPluginWkrModuleName", a5);
    if ( !*v21 )
    {
      if ( !a4 )
        goto LABEL_58;
      v22 = a4;
      v23 = 0x7FFFFFFF;
      do
      {
        if ( !*v22 )
          break;
        ++v22;
        --v23;
      }
      while ( v23 );
      if ( !v23 )
        goto LABEL_58;
      v24 = 0x7FFFFFFF;
      v25 = L"pspluginwkr.dll";
      do
      {
        if ( !*v25 )
          break;
        ++v25;
        --v24;
      }
      while ( v24 );
      if ( v24 )
      {
        v26 = ((0x7FFFFFFF - v24) & ((unsigned __int128)-(__int128)(unsigned __int64)v24 >> 64))
            + ((0x7FFFFFFF - v23) & -(__int64)(v23 != 0))
            + 2;
        v27 = (unsigned __int16 *)operator new[](saturated_mul(v26, 2u));
        *v21 = v27;
        v28 = v27;
        if ( v27 )
        {
          *v27 = 0;
          if ( v26 - 1 > 0x7FFFFFFE )
            goto LABEL_57;
          v33 = v26;
          do
          {
            if ( !v11 )
              break;
            if ( !*a4 )
              break;
            *v27++ = *a4++;
            --v11;
            --v33;
          }
          while ( v33 );
          v34 = v27 - 1;
          if ( v33 )
            v34 = v27;
          *v34 = 0;
          if ( !v33
            || (int)StringCchCatW(v28, v26, L"\\") < 0
            || (RegistryInfo = 0, (int)StringCchCatW(*v21, v26, L"pspluginwkr.dll") < 0) )
          {
LABEL_57:
            RegistryInfo = 1103;
          }
        }
        else
        {
          RegistryInfo = -2147024882;
        }
      }
      else
      {
LABEL_58:
        RegistryInfo = -2141977622;
      }
    }
  }
  if ( v36 )
    operator delete[](v36);
  if ( v37 )
    operator delete[](v37);
  return RegistryInfo;
}

```

## disassembly

```asm
0x1800025d0  mov     r11, rsp
0x1800025d3  mov     [r11+18h], rbx
0x1800025d7  mov     [r11+8], rcx
0x1800025db  push    rbp
0x1800025dc  push    rsi
0x1800025dd  push    rdi
0x1800025de  push    r12
0x1800025e0  push    r13
0x1800025e2  push    r14
0x1800025e4  push    r15
0x1800025e6  sub     rsp, 50h
0x1800025ea  xor     eax, eax
0x1800025ec  mov     [rcx+4Ch], edx
0x1800025ef  mov     rsi, rcx
0x1800025f2  mov     [r11+10h], edx
0x1800025f6  mov     r12, r9
0x1800025f9  mov     [r11-48h], rax
0x1800025fd  mov     r13d, r8d
0x180002600  mov     [r11-40h], rax
0x180002604  lea     ebx, [rax+14h]
0x180002607  mov     edi, edx
0x180002609  mov     ecx, ebx; unsigned __int64
0x18000260b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180002610  mov     ecx, ebx; unsigned __int64
0x180002612  mov     rbp, rax
0x180002615  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000261a  mov     r14, rax
0x18000261d  mov     r15d, 7FFFFFFEh
0x180002623  test    edi, edi
0x180002625  js      loc_1800028B0
0x18000262b  test    r13d, r13d
0x18000262e  js      loc_1800028B0
0x180002634  mov     ebx, 0Ah
0x180002639  mov     rdx, rbp; Buffer
0x18000263c  mov     r9d, ebx; Radix
0x18000263f  mov     r8d, ebx; BufferCount
0x180002642  mov     ecx, edi; Value
0x180002644  call    cs:__imp__itow_s
0x18000264a  xor     edi, edi
0x18000264c  test    eax, eax
0x18000264e  jnz     loc_1800028B0
0x180002654  mov     r9d, ebx; Radix
0x180002657  mov     r8d, ebx; BufferCount
0x18000265a  mov     rdx, r14; Buffer
0x18000265d  mov     ecx, r13d; Value
0x180002660  call    cs:__imp__itow_s
0x180002666  test    eax, eax
0x180002668  jnz     loc_1800028B0
0x18000266e  test    rbp, rbp
0x180002671  jz      loc_1800028B0
0x180002677  mov     edx, ebx
0x180002679  mov     rax, rbp
0x18000267c  cmp     [rax], di
0x18000267f  jz      short loc_18000268B
0x180002681  add     rax, 2
0x180002685  sub     rdx, 1
0x180002689  jnz     short loc_18000267C
0x18000268b  mov     rcx, rbx
0x18000268e  mov     rax, rdx
0x180002691  sub     rcx, rdx
0x180002694  neg     rax
0x180002697  sbb     r8, r8
0x18000269a  and     r8, rcx
0x18000269d  test    rdx, rdx
0x1800026a0  jz      loc_1800028B0
0x1800026a6  test    r14, r14
0x1800026a9  jz      loc_1800028B0
0x1800026af  mov     rcx, rbx
0x1800026b2  mov     rax, r14
0x1800026b5  cmp     [rax], di
0x1800026b8  jz      short loc_1800026C4
0x1800026ba  add     rax, 2
0x1800026be  sub     rcx, 1
0x1800026c2  jnz     short loc_1800026B5
0x1800026c4  sub     rbx, rcx
0x1800026c7  mov     rax, rcx
0x1800026ca  neg     rax
0x1800026cd  sbb     rdx, rdx
0x1800026d0  and     rdx, rbx
0x1800026d3  xor     ebx, ebx
0x1800026d5  test    rcx, rcx
0x1800026d8  jz      loc_1800028B0
0x1800026de  lea     rsi, [r8+2]
0x1800026e2  add     rsi, rdx
0x1800026e5  lea     rcx, [rbx-1]
0x1800026e9  lea     eax, [rbx+2]
0x1800026ec  mul     rsi
0x1800026ef  cmovb   rax, rcx
0x1800026f3  mov     rcx, rax; unsigned __int64
0x1800026f6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800026fb  mov     [rsp+88h+var_48], rax
0x180002700  mov     rdi, rax
0x180002703  test    rax, rax
0x180002706  jnz     loc_18000282E
0x18000270c  lea     ebx, [rax+8]
0x18000270f  mov     rsi, [rsp+88h+arg_0]
0x180002717  mov     rcx, rbp
0x18000271a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180002720  xor     ebp, ebp
0x180002722  test    r14, r14
0x180002725  jz      short loc_180002730
0x180002727  mov     rcx, r14
0x18000272a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180002730  test    ebx, ebx
0x180002732  jnz     loc_180002940
0x180002738  lea     rcx, [rsi+0A0h]; this
0x18000273f  mov     r9d, r13d; int
0x180002742  mov     rsi, [rsp+88h+arg_20]
0x18000274a  lea     rax, aPspluginwkrmod; "PSPluginWkrModuleName"
0x180002751  mov     [rsp+88h+var_58], rsi; unsigned __int16 **
0x180002756  lea     r8, [rsp+88h+arg_8]; int *
0x18000275e  mov     [rsp+88h+var_60], rax; unsigned __int16 *
0x180002763  lea     rdx, [rsp+88h+var_48]; unsigned __int16 **
0x180002768  lea     rax, [rsp+88h+var_40]
0x18000276d  mov     [rsp+88h+var_68], rax; unsigned __int16 **
0x180002772  call    ?GetRegistryInfo@PwrshCommon@NativeMsh@@QEAAIPEAPEAGPEAHH0PEBG0@Z; NativeMsh::PwrshCommon::GetRegistryInfo(ushort * *,int *,int,ushort * *,ushort const *,ushort * *)
0x180002777  mov     ebx, eax
0x180002779  cmp     [rsi], rbp
0x18000277c  jnz     loc_180002940
0x180002782  test    r12, r12
0x180002785  jz      loc_18000293B
0x18000278b  mov     r8d, 7FFFFFFFh
0x180002791  mov     rax, r12
0x180002794  mov     edx, r8d
0x180002797  mov     ebx, 2
0x18000279c  cmp     [rax], bp
0x18000279f  jz      short loc_1800027AA
0x1800027a1  add     rax, rbx
0x1800027a4  sub     rdx, 1
0x1800027a8  jnz     short loc_18000279C
0x1800027aa  mov     rcx, r8
0x1800027ad  mov     rax, rdx
0x1800027b0  sub     rcx, rdx
0x1800027b3  neg     rax
0x1800027b6  sbb     r9, r9
0x1800027b9  and     r9, rcx
0x1800027bc  test    rdx, rdx
0x1800027bf  jz      loc_18000293B
0x1800027c5  mov     rcx, r8
0x1800027c8  lea     rax, aPspluginwkrDll; "pspluginwkr.dll"
0x1800027cf  cmp     [rax], bp
0x1800027d2  jz      short loc_1800027DD
0x1800027d4  add     rax, rbx
0x1800027d7  sub     rcx, 1
0x1800027db  jnz     short loc_1800027CF
0x1800027dd  sub     r8, rcx
0x1800027e0  mov     rax, rcx
0x1800027e3  neg     rax
0x1800027e6  sbb     rdx, rdx
0x1800027e9  and     rdx, r8
0x1800027ec  test    rcx, rcx
0x1800027ef  jz      loc_18000293B
0x1800027f5  lea     rdi, [r9+2]
0x1800027f9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180002800  add     rdi, rdx
0x180002803  mov     rax, rbx
0x180002806  mul     rdi
0x180002809  cmovb   rax, rcx
0x18000280d  mov     rcx, rax; unsigned __int64
0x180002810  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180002815  mov     [rsi], rax
0x180002818  mov     r10, rax
0x18000281b  test    rax, rax
0x18000281e  jnz     loc_1800028C3
0x180002824  mov     ebx, 8007000Eh
0x180002829  jmp     loc_180002940
0x18000282e  mov     [rax], bx
0x180002831  lea     rax, [rsi-1]
0x180002835  cmp     rax, r15
0x180002838  ja      short loc_1800028A6
0x18000283a  mov     rcx, r15
0x18000283d  mov     rdx, rbp
0x180002840  mov     r8, rsi
0x180002843  mov     rax, rdi
0x180002846  test    rcx, rcx
0x180002849  jz      short loc_18000286A
0x18000284b  movzx   r9d, word ptr [rdx]
0x18000284f  test    r9w, r9w
0x180002853  jz      short loc_18000286A
0x180002855  mov     [rax], r9w
0x180002859  add     rdx, 2
0x18000285d  add     rax, 2
0x180002861  dec     rcx
0x180002864  sub     r8, 1
0x180002868  jnz     short loc_180002846
0x18000286a  test    r8, r8
0x18000286d  lea     rcx, [rax-2]
0x180002871  cmovnz  rcx, rax
0x180002875  mov     [rcx], bx
0x180002878  jz      short loc_1800028A6
0x18000287a  lea     r8, asc_18000E338; "."
0x180002881  mov     rdx, rsi; unsigned __int64
0x180002884  mov     rcx, rdi; unsigned __int16 *
0x180002887  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000288c  test    eax, eax
0x18000288e  js      short loc_1800028A6
0x180002890  mov     r8, r14; unsigned __int16 *
0x180002893  mov     rdx, rsi; unsigned __int64
0x180002896  mov     rcx, rdi; unsigned __int16 *
0x180002899  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000289e  test    eax, eax
0x1800028a0  jns     loc_18000270F
0x1800028a6  mov     ebx, 64h ; 'd'
0x1800028ab  jmp     loc_18000270F
0x1800028b0  mov     ebx, 64h ; 'd'
0x1800028b5  test    rbp, rbp
0x1800028b8  jz      loc_180002720
0x1800028be  jmp     loc_180002717
0x1800028c3  mov     [rax], bp
0x1800028c6  lea     rax, [rdi-1]
0x1800028ca  cmp     rax, r15
0x1800028cd  ja      short loc_180002934
0x1800028cf  mov     r9, rdi
0x1800028d2  mov     rax, r10
0x1800028d5  test    r15, r15
0x1800028d8  jz      short loc_1800028F6
0x1800028da  movzx   ecx, word ptr [r12]
0x1800028df  test    cx, cx
0x1800028e2  jz      short loc_1800028F6
0x1800028e4  mov     [rax], cx
0x1800028e7  add     r12, rbx
0x1800028ea  add     rax, rbx
0x1800028ed  dec     r15
0x1800028f0  sub     r9, 1
0x1800028f4  jnz     short loc_1800028D5
0x1800028f6  test    r9, r9
0x1800028f9  lea     rcx, [rax-2]
0x1800028fd  cmovnz  rcx, rax
0x180002901  mov     [rcx], bp
0x180002904  jz      short loc_180002934
0x180002906  lea     r8, asc_18000E20C; "\\"
0x18000290d  mov     rdx, rdi; unsigned __int64
0x180002910  mov     rcx, r10; unsigned __int16 *
0x180002913  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180002918  test    eax, eax
0x18000291a  js      short loc_180002934
0x18000291c  mov     rcx, [rsi]; unsigned __int16 *
0x18000291f  lea     r8, aPspluginwkrDll; "pspluginwkr.dll"
0x180002926  mov     rdx, rdi; unsigned __int64
0x180002929  mov     ebx, ebp
0x18000292b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180002930  test    eax, eax
0x180002932  jns     short loc_180002940
0x180002934  mov     ebx, 44Fh
0x180002939  jmp     short loc_180002940
0x18000293b  mov     ebx, 805403EAh
0x180002940  mov     rcx, [rsp+88h+var_48]
0x180002945  test    rcx, rcx
0x180002948  jz      short loc_180002950
0x18000294a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180002950  mov     rcx, [rsp+88h+var_40]
0x180002955  test    rcx, rcx
0x180002958  jz      short loc_180002960
0x18000295a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180002960  mov     eax, ebx
0x180002962  mov     rbx, [rsp+88h+arg_10]
0x18000296a  add     rsp, 50h
0x18000296e  pop     r15
0x180002970  pop     r14
0x180002972  pop     r13
0x180002974  pop     r12
0x180002976  pop     rdi
0x180002977  pop     rsi
0x180002978  pop     rbp
0x180002979  retn
```
