# Microsoft::HostGuardian::Client::Plugin::CimUtilities::HRESULT_FROM_MIRESULT(_MI_Result)

- ea: `0x180009f44`
- end: `0x18000a067`
- name: `?HRESULT_FROM_MIRESULT@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YAJW4_MI_Result@@@Z`
- size: `291`
- prototype: `__int64 __fastcall(Microsoft::HostGuardian::Client::Plugin::CimUtilities *__hidden this, enum _MI_Result)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007a10`
- `0x180009070`
- `0x1800092fc`
- `0x1800096ec`
- `0x180009cfc`
- `0x18000a070`
- `0x18000a550`

## callees

- `0x180009f44`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::Plugin::CimUtilities::HRESULT_FROM_MIRESULT(
        Microsoft::HostGuardian::Client::Plugin::CimUtilities *this,
        enum _MI_Result a2)
{
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx

  if ( (int)this <= 13 )
  {
    if ( (_DWORD)this == 13 )
      return 2147749893LL;
    if ( (int)this <= 6 )
    {
      if ( (_DWORD)this == 6 )
        return 2147749890LL;
      if ( !(_DWORD)this )
        return 0;
      v2 = (_DWORD)this - 1;
      if ( !v2 )
        return 2147749889LL;
      v3 = v2 - 1;
      if ( !v3 )
        return 2147749891LL;
      v4 = v3 - 1;
      if ( !v4 )
        return 2147749902LL;
      v5 = v4 - 1;
      if ( v5 )
      {
        if ( v5 == 1 )
          return 2147749904LL;
        return 2147749889LL;
      }
      return 2147749896LL;
    }
    v7 = (_DWORD)this - 7;
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( !v8 )
        return 2147749925LL;
      v9 = v8 - 1;
      if ( !v9 )
        return 2147749926LL;
      v10 = v9 - 1;
      if ( !v10 )
        return 2147749901LL;
      v11 = v10 - 1;
      if ( !v11 )
        return 2147749913LL;
      if ( v11 == 1 )
        return 2147749937LL;
      return 2147749889LL;
    }
    return 2147749900LL;
  }
  if ( (int)this <= 22 )
  {
    if ( (_DWORD)this != 22 )
    {
      v12 = (_DWORD)this - 14;
      if ( !v12 )
        return 2147749912LL;
      v13 = v12 - 1;
      if ( !v13 )
        return 2147749911LL;
      v14 = v13 - 1;
      if ( !v14 )
        return 2147749973LL;
      v15 = v14 - 1;
      if ( !v15 )
        return 2147749934LL;
      if ( v15 == 4 )
        return 2147749895LL;
      return 2147749889LL;
    }
    return 2147749896LL;
  }
  v16 = (_DWORD)this - 23;
  if ( v16 )
  {
    v17 = v16 - 1;
    if ( v17 )
    {
      v18 = v17 - 1;
      if ( v18 )
      {
        v19 = v18 - 1;
        if ( v19 )
        {
          v20 = v19 - 1;
          if ( !v20 )
            return 2147749996LL;
          if ( v20 == 1 )
            return 2147749939LL;
          return 2147749889LL;
        }
      }
      return 2147749900LL;
    }
  }
  return 2147749889LL;
}

```

## disassembly

```asm
0x180009f44  cmp     ecx, 0Dh
0x180009f47  jg      loc_180009FE8
0x180009f4d  jz      loc_180009FE2
0x180009f53  cmp     ecx, 6
0x180009f56  jg      short loc_180009F9E
0x180009f58  jz      short loc_180009F98
0x180009f5a  test    ecx, ecx
0x180009f5c  jz      short loc_180009F95
0x180009f5e  sub     ecx, 1
0x180009f61  jz      loc_18000A061
0x180009f67  sub     ecx, 1
0x180009f6a  jz      short loc_180009F8F
0x180009f6c  sub     ecx, 1
0x180009f6f  jz      short loc_180009F89
0x180009f71  sub     ecx, 1
0x180009f74  jz      loc_18000A02B
0x180009f7a  cmp     ecx, 1
0x180009f7d  jnz     loc_18000A061
0x180009f83  mov     eax, 80041010h
0x180009f88  retn
0x180009f89  mov     eax, 8004100Eh
0x180009f8e  retn
0x180009f8f  mov     eax, 80041003h
0x180009f94  retn
0x180009f95  xor     eax, eax
0x180009f97  retn
0x180009f98  mov     eax, 80041002h
0x180009f9d  retn
0x180009f9e  sub     ecx, 7
0x180009fa1  jz      loc_18000A05B
0x180009fa7  sub     ecx, 1
0x180009faa  jz      short loc_180009FDC
0x180009fac  sub     ecx, 1
0x180009faf  jz      short loc_180009FD6
0x180009fb1  sub     ecx, 1
0x180009fb4  jz      short loc_180009FD0
0x180009fb6  sub     ecx, 1
0x180009fb9  jz      short loc_180009FCA
0x180009fbb  cmp     ecx, 1
0x180009fbe  jnz     loc_18000A061
0x180009fc4  mov     eax, 80041031h
0x180009fc9  retn
0x180009fca  mov     eax, 80041019h
0x180009fcf  retn
0x180009fd0  mov     eax, 8004100Dh
0x180009fd5  retn
0x180009fd6  mov     eax, 80041026h
0x180009fdb  retn
0x180009fdc  mov     eax, 80041025h
0x180009fe1  retn
0x180009fe2  mov     eax, 80041005h
0x180009fe7  retn
0x180009fe8  cmp     ecx, 16h
0x180009feb  jg      short loc_18000A031
0x180009fed  jz      short loc_18000A02B
0x180009fef  sub     ecx, 0Eh
0x180009ff2  jz      short loc_18000A025
0x180009ff4  sub     ecx, 1
0x180009ff7  jz      short loc_18000A01F
0x180009ff9  sub     ecx, 1
0x180009ffc  jz      short loc_18000A019
0x180009ffe  sub     ecx, 1
0x18000a001  jz      short loc_18000A013
0x18000a003  sub     ecx, 3
0x18000a006  jz      short loc_18000A061
0x18000a008  cmp     ecx, 1
0x18000a00b  jnz     short loc_18000A061
0x18000a00d  mov     eax, 80041007h
0x18000a012  retn
0x18000a013  mov     eax, 8004102Eh
0x18000a018  retn
0x18000a019  mov     eax, 80041055h
0x18000a01e  retn
0x18000a01f  mov     eax, 80041017h
0x18000a024  retn
0x18000a025  mov     eax, 80041018h
0x18000a02a  retn
0x18000a02b  mov     eax, 80041008h
0x18000a030  retn
0x18000a031  sub     ecx, 17h
0x18000a034  jz      short loc_18000A061
0x18000a036  sub     ecx, 1
0x18000a039  jz      short loc_18000A061
0x18000a03b  sub     ecx, 1
0x18000a03e  jz      short loc_18000A05B
0x18000a040  sub     ecx, 1
0x18000a043  jz      short loc_18000A05B
0x18000a045  sub     ecx, 1
0x18000a048  jz      short loc_18000A055
0x18000a04a  cmp     ecx, 1
0x18000a04d  jnz     short loc_18000A061
0x18000a04f  mov     eax, 80041033h
0x18000a054  retn
0x18000a055  mov     eax, 8004106Ch
0x18000a05a  retn
0x18000a05b  mov     eax, 8004100Ch
0x18000a060  retn
0x18000a061  mov     eax, 80041001h
0x18000a066  retn
```
