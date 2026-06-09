# ParseGrantCreateUserGroup(x,x,x)

- ea: `0x100cb7d2`
- end: `0x100cbb00`
- name: `_ParseGrantCreateUserGroup@12`
- size: `814`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x100cb5b5`

## callees

- `0x1003ea00`
- `0x100929d2`
- `0x100b8ba0`
- `0x100cb7d2`
- `0x100cf3d5`
- `0x100cf4a9`
- `0x10123110`
- `0x10123130`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x100cb980`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x100cb980`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x100cb977`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x100cb977`
- `api-ms-win-crt-private-l1-1-0!longjmp` at `0x100cb833`
- `api-ms-win-crt-private-l1-1-0!longjmp` at `0x100cb833`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x100cb96b`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x100cb96b`

## pseudocode

```c
int __fastcall ParseGrantCreateUserGroup(const void *a1, int a2, int *a3)
{
  int v4; // ebx
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int Token; // eax
  int v9; // eax
  int v10; // eax
  unsigned int i; // ebx
  unsigned int v12; // eax
  int v13; // eax
  int result; // eax
  int v15; // [esp+Ch] [ebp-B0h]
  int v17; // [esp+14h] [ebp-A8h]
  GUID pguid; // [esp+18h] [ebp-A4h] BYREF
  wchar_t Destination[24]; // [esp+28h] [ebp-94h] BYREF
  wchar_t v20[24]; // [esp+58h] [ebp-64h] BYREF
  wchar_t v21[24]; // [esp+88h] [ebp-34h] BYREF

  v15 = 1;
  v4 = 0;
  v17 = 0;
  if ( (unsigned int)a3[9] < 0x5C )
  {
    UtilSetErrorInfoReal(*a3, 0, 0, 0, -8136, (a3[5] - a3[2]) >> 1, a3[7], 0);
    _longjmp(*(int **)(a2 + 4), -3500);
  }
  v5 = TknGetToken(a3) - 305;
  if ( v5 )
  {
    if ( v5 == 61 )
      goto LABEL_8;
    UtilSetErrorInfoReal(*a3, 0, 0, 0, -8905, (a3[5] - a3[2]) >> 1, a3[7], 0);
LABEL_6:
    _longjmp(*(int **)(a2 + 4), -3565);
  }
  v4 = 1;
  v17 = 1;
  do
  {
LABEL_8:
    v21[0] = 0;
    v20[0] = 0;
    Destination[0] = 0;
    v6 = ParseSecurityId((int)a3, Destination, 20);
    if ( v6 == -3565 )
    {
      UtilSetErrorInfoReal(*a3, 0, 0, 0, -8903, (a3[5] - a3[2]) >> 1, a3[7], 0);
      goto LABEL_6;
    }
    if ( v6 == -1002 )
    {
      UtilSetErrorInfoReal(*a3, 0, 0, 0, -8275, (a3[5] - a3[2]) >> 1, a3[7], 0);
      _longjmp(*(int **)(a2 + 4), -1903);
    }
    if ( !v4 )
    {
      v7 = ParseSecurityId((int)a3, v20, 20);
      if ( v7 == -3565 )
      {
        Token = TknGetToken(a3);
        if ( Token != 22 && Token != 44 && Token != 59 )
        {
          UtilSetErrorInfoReal(*a3, 0, 0, 0, -8907, (a3[5] - a3[2]) >> 1, a3[7], 0);
          goto LABEL_6;
        }
        a3[3] = a3[5];
        v20[0] = 0;
      }
      else if ( v7 == -1002 )
      {
        _longjmp(*(int **)(a2 + 4), -1905);
      }
    }
    v9 = ParseSecurityId((int)a3, v21, 20);
    if ( v9 == -3565 )
    {
      v10 = TknGetToken(a3);
      if ( v10 != 22 && v10 != 44 && v10 != 59 )
      {
        UtilSetErrorInfoReal(*a3, 0, 0, 0, -8917, (a3[5] - a3[2]) >> 1, a3[7], 0);
        goto LABEL_6;
      }
      a3[3] = a3[5];
      CoCreateGuid(&pguid);
      __o_srand(pguid.Data1);
      for ( i = 0; i < 0xA; ++i )
        v21[i] = _rand() % 223 + 32;
      v12 = i;
      if ( 2 * i >= 0x2E )
        __report_rangecheckfailure(223);
      v4 = v17;
      v21[v12] = 0;
    }
    else if ( v9 == -1002 )
    {
      UtilSetErrorInfoReal(*a3, 0, 0, 0, -8917, (a3[5] - a3[2]) >> 1, a3[7], 0);
      _longjmp(*(int **)(a2 + 4), -1910);
    }
    v13 = TknGetToken(a3);
    if ( v13 != 22 )
    {
      if ( v13 == 44 )
        goto LABEL_32;
      if ( v13 != 59 )
      {
        UtilSetErrorInfoReal(*a3, 0, 0, 0, -8036, (a3[5] - a3[2]) >> 1, a3[7], 0);
        _longjmp(*(int **)(a2 + 4), -3516);
      }
    }
    v15 = 0;
    a3[3] = a3[5];
LABEL_32:
    if ( v4 )
      DDLQueueCreateGroup(a1, Destination, v21);
    else
      DDLQueueCreateUser(a1, Destination, v20, v21);
  }
  while ( v15 == 1 );
  result = TknGetToken(a3);
  if ( result == 59 )
    result = TknGetToken(a3);
  if ( result != 22 )
  {
    UtilSetErrorInfoReal(*a3, 0, 0, 0, -8214, (a3[5] - a3[2]) >> 1, a3[7], 0);
    goto LABEL_6;
  }
  return result;
}

```

## disassembly

```asm
0x100cb7d2  mov     edi, edi
0x100cb7d4  push    ebp
0x100cb7d5  mov     ebp, esp
0x100cb7d7  sub     esp, 0B0h
0x100cb7dd  mov     eax, ___security_cookie
0x100cb7e2  xor     eax, ebp
0x100cb7e4  mov     [ebp+var_4], eax
0x100cb7e7  push    ebx
0x100cb7e8  push    esi
0x100cb7e9  mov     esi, [ebp+arg_0]
0x100cb7ec  mov     [ebp+lpAddress], ecx
0x100cb7f2  xor     ecx, ecx
0x100cb7f4  push    edi
0x100cb7f5  mov     edi, edx
0x100cb7f7  mov     [ebp+var_B0], 1
0x100cb801  cmp     dword ptr [esi+24h], 5Ch ; '\'
0x100cb805  mov     ebx, ecx
0x100cb807  mov     [ebp+var_A8], ecx
0x100cb80d  jnb     short loc_100CB839
0x100cb80f  mov     eax, [esi+14h]
0x100cb812  sub     eax, [esi+8]
0x100cb815  push    ecx; int
0x100cb816  push    dword ptr [esi+1Ch]; int
0x100cb819  sar     eax, 1
0x100cb81b  push    eax; int
0x100cb81c  push    0FFFFE038h; int
0x100cb821  push    ecx; void *
0x100cb822  push    ecx; void *
0x100cb823  push    ecx; Src
0x100cb824  push    dword ptr [esi]; int
0x100cb826  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x100cb82b  push    0FFFFF254h; Value
0x100cb830  push    dword ptr [edi+4]; Buf
0x100cb833  call    ds:__imp__longjmp
0x100cb839  mov     ecx, esi
0x100cb83b  call    _TknGetToken@4; TknGetToken(x)
0x100cb840  sub     eax, 131h
0x100cb845  jz      short loc_100CB871
0x100cb847  sub     eax, 3Dh ; '='
0x100cb84a  jz      short loc_100CB87A
0x100cb84c  mov     eax, [esi+14h]
0x100cb84f  xor     ecx, ecx
0x100cb851  sub     eax, [esi+8]
0x100cb854  push    ecx; int
0x100cb855  push    dword ptr [esi+1Ch]; int
0x100cb858  sar     eax, 1
0x100cb85a  push    eax; int
0x100cb85b  push    0FFFFDD37h; int
0x100cb860  push    ecx; void *
0x100cb861  push    ecx; void *
0x100cb862  push    ecx; Src
0x100cb863  push    dword ptr [esi]; int
0x100cb865  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x100cb86a  push    0FFFFF213h
0x100cb86f  jmp     short loc_100CB830
0x100cb871  xor     ebx, ebx
0x100cb873  inc     ebx
0x100cb874  mov     [ebp+var_A8], ebx
0x100cb87a  xor     eax, eax
0x100cb87c  mov     [ebp+var_34], ax
0x100cb880  mov     [ebp+var_64], ax
0x100cb884  mov     [ebp+Destination], ax
0x100cb88b  lea     eax, [ebp+Destination]
0x100cb891  push    14h; int
0x100cb893  push    eax; Destination
0x100cb894  push    esi; int
0x100cb895  call    _ParseSecurityId@20; ParseSecurityId(x,x,x,x,x)
0x100cb89a  cmp     eax, 0FFFFF213h
0x100cb89f  jz      loc_100CBAD1
0x100cb8a5  cmp     eax, 0FFFFFC16h
0x100cb8aa  jz      loc_100CBAA9
0x100cb8b0  test    ebx, ebx
0x100cb8b2  jnz     short loc_100CB8FE
0x100cb8b4  push    14h; int
0x100cb8b6  lea     eax, [ebp+var_64]
0x100cb8b9  push    eax; Destination
0x100cb8ba  push    esi; int
0x100cb8bb  call    _ParseSecurityId@20; ParseSecurityId(x,x,x,x,x)
0x100cb8c0  cmp     eax, 0FFFFF213h
0x100cb8c5  jz      short loc_100CB8D8
0x100cb8c7  cmp     eax, 0FFFFFC16h
0x100cb8cc  jnz     short loc_100CB8FE
0x100cb8ce  push    0FFFFF88Fh
0x100cb8d3  jmp     loc_100CB830
0x100cb8d8  mov     ecx, esi
0x100cb8da  call    _TknGetToken@4; TknGetToken(x)
0x100cb8df  cmp     eax, 16h
0x100cb8e2  jz      short loc_100CB8F2
0x100cb8e4  cmp     eax, 2Ch ; ','
0x100cb8e7  jz      short loc_100CB8F2
0x100cb8e9  cmp     eax, 3Bh ; ';'
0x100cb8ec  jnz     loc_100CBA4F
0x100cb8f2  mov     eax, [esi+14h]
0x100cb8f5  mov     [esi+0Ch], eax
0x100cb8f8  xor     eax, eax
0x100cb8fa  mov     [ebp+var_64], ax
0x100cb8fe  push    14h; int
0x100cb900  lea     eax, [ebp+var_34]
0x100cb903  push    eax; Destination
0x100cb904  push    esi; int
0x100cb905  call    _ParseSecurityId@20; ParseSecurityId(x,x,x,x,x)
0x100cb90a  cmp     eax, 0FFFFF213h
0x100cb90f  jz      short loc_100CB944
0x100cb911  cmp     eax, 0FFFFFC16h
0x100cb916  jnz     loc_100CB9B5
0x100cb91c  mov     eax, [esi+14h]
0x100cb91f  xor     ecx, ecx
0x100cb921  sub     eax, [esi+8]
0x100cb924  push    ecx; int
0x100cb925  push    dword ptr [esi+1Ch]; int
0x100cb928  sar     eax, 1
0x100cb92a  push    eax; int
0x100cb92b  push    0FFFFDD2Bh; int
0x100cb930  push    ecx; void *
0x100cb931  push    ecx; void *
0x100cb932  push    ecx; Src
0x100cb933  push    dword ptr [esi]; int
0x100cb935  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x100cb93a  push    0FFFFF88Ah
0x100cb93f  jmp     loc_100CB830
0x100cb944  mov     ecx, esi
0x100cb946  call    _TknGetToken@4; TknGetToken(x)
0x100cb94b  cmp     eax, 16h
0x100cb94e  jz      short loc_100CB95E
0x100cb950  cmp     eax, 2Ch ; ','
0x100cb953  jz      short loc_100CB95E
0x100cb955  cmp     eax, 3Bh ; ';'
0x100cb958  jnz     loc_100CBA68
0x100cb95e  mov     eax, [esi+14h]
0x100cb961  mov     [esi+0Ch], eax
0x100cb964  lea     eax, [ebp+pguid]
0x100cb96a  push    eax; pguid
0x100cb96b  call    ds:__imp__CoCreateGuid@4; CoCreateGuid(x)
0x100cb971  push    [ebp+pguid.Data1]
0x100cb977  call    ds:__imp___o_srand
0x100cb97d  pop     ecx
0x100cb97e  xor     ebx, ebx
0x100cb980  call    ds:__imp__rand
0x100cb986  cdq
0x100cb987  mov     ecx, 0DFh
0x100cb98c  idiv    ecx
0x100cb98e  add     edx, 20h ; ' '
0x100cb991  mov     [ebp+ebx*2+var_34], dx
0x100cb996  inc     ebx
0x100cb997  cmp     ebx, 0Ah
0x100cb99a  jb      short loc_100CB980
0x100cb99c  lea     eax, [ebx+ebx]
0x100cb99f  cmp     eax, 2Eh ; '.'
0x100cb9a2  jnb     loc_100CBAFB
0x100cb9a8  mov     ebx, [ebp+var_A8]
0x100cb9ae  xor     ecx, ecx
0x100cb9b0  mov     [ebp+eax+var_34], cx
0x100cb9b5  mov     ecx, esi
0x100cb9b7  call    _TknGetToken@4; TknGetToken(x)
0x100cb9bc  cmp     eax, 16h
0x100cb9bf  jz      short loc_100CB9CF
0x100cb9c1  cmp     eax, 2Ch ; ','
0x100cb9c4  jz      short loc_100CB9DF
0x100cb9c6  cmp     eax, 3Bh ; ';'
0x100cb9c9  jnz     loc_100CBA81
0x100cb9cf  mov     eax, [esi+14h]
0x100cb9d2  mov     [ebp+var_B0], 0
0x100cb9dc  mov     [esi+0Ch], eax
0x100cb9df  mov     ecx, [ebp+lpAddress]; lpAddress
0x100cb9e5  lea     eax, [ebp+var_34]
0x100cb9e8  mov     edx, edi
0x100cb9ea  push    eax; void *
0x100cb9eb  test    ebx, ebx
0x100cb9ed  jnz     short loc_100CBA01
0x100cb9ef  lea     eax, [ebp+var_64]
0x100cb9f2  push    eax; void *
0x100cb9f3  lea     eax, [ebp+Destination]
0x100cb9f9  push    eax; Src
0x100cb9fa  call    DDLQueueCreateUser
0x100cb9ff  jmp     short loc_100CBA0D
0x100cba01  lea     eax, [ebp+Destination]
0x100cba07  push    eax; Src
0x100cba08  call    DDLQueueCreateGroup
0x100cba0d  cmp     [ebp+var_B0], 1
0x100cba14  jz      loc_100CB87A
0x100cba1a  mov     ecx, esi
0x100cba1c  call    _TknGetToken@4; TknGetToken(x)
0x100cba21  cmp     eax, 3Bh ; ';'
0x100cba24  jnz     short loc_100CBA2D
0x100cba26  mov     ecx, esi
0x100cba28  call    _TknGetToken@4; TknGetToken(x)
0x100cba2d  cmp     eax, 16h
0x100cba30  jz      loc_100CBAEA
0x100cba36  mov     eax, [esi+14h]
0x100cba39  xor     ecx, ecx
0x100cba3b  sub     eax, [esi+8]
0x100cba3e  push    ecx
0x100cba3f  push    dword ptr [esi+1Ch]
0x100cba42  sar     eax, 1
0x100cba44  push    eax
0x100cba45  push    0FFFFDFEAh
0x100cba4a  jmp     loc_100CB860
0x100cba4f  mov     eax, [esi+14h]
0x100cba52  xor     ecx, ecx
0x100cba54  sub     eax, [esi+8]
0x100cba57  push    ecx
0x100cba58  push    dword ptr [esi+1Ch]
0x100cba5b  sar     eax, 1
0x100cba5d  push    eax
0x100cba5e  push    0FFFFDD35h
0x100cba63  jmp     loc_100CB860
0x100cba68  mov     eax, [esi+14h]
0x100cba6b  xor     ecx, ecx
0x100cba6d  sub     eax, [esi+8]
0x100cba70  push    ecx
0x100cba71  push    dword ptr [esi+1Ch]
0x100cba74  sar     eax, 1
0x100cba76  push    eax
0x100cba77  push    0FFFFDD2Bh
0x100cba7c  jmp     loc_100CB860
0x100cba81  mov     eax, [esi+14h]
0x100cba84  xor     ecx, ecx
0x100cba86  sub     eax, [esi+8]
0x100cba89  push    ecx; int
0x100cba8a  push    dword ptr [esi+1Ch]; int
0x100cba8d  sar     eax, 1
0x100cba8f  push    eax; int
0x100cba90  push    0FFFFE09Ch; int
0x100cba95  push    ecx; void *
0x100cba96  push    ecx; void *
0x100cba97  push    ecx; Src
0x100cba98  push    dword ptr [esi]; int
0x100cba9a  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x100cba9f  push    0FFFFF244h
0x100cbaa4  jmp     loc_100CB830
0x100cbaa9  mov     eax, [esi+14h]
0x100cbaac  xor     ecx, ecx
0x100cbaae  sub     eax, [esi+8]
0x100cbab1  push    ecx; int
0x100cbab2  push    dword ptr [esi+1Ch]; int
0x100cbab5  sar     eax, 1
0x100cbab7  push    eax; int
0x100cbab8  push    0FFFFDFADh; int
0x100cbabd  push    ecx; void *
0x100cbabe  push    ecx; void *
0x100cbabf  push    ecx; Src
0x100cbac0  push    dword ptr [esi]; int
0x100cbac2  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x100cbac7  push    0FFFFF891h
0x100cbacc  jmp     loc_100CB830
0x100cbad1  mov     eax, [esi+14h]
0x100cbad4  xor     ecx, ecx
0x100cbad6  sub     eax, [esi+8]
0x100cbad9  push    ecx
0x100cbada  push    dword ptr [esi+1Ch]
0x100cbadd  sar     eax, 1
0x100cbadf  push    eax
0x100cbae0  push    0FFFFDD39h
0x100cbae5  jmp     loc_100CB860
0x100cbaea  mov     ecx, [ebp+var_4]
0x100cbaed  pop     edi
0x100cbaee  pop     esi
0x100cbaef  xor     ecx, ebp; StackCookie
0x100cbaf1  pop     ebx
0x100cbaf2  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100cbaf7  leave
0x100cbaf8  retn    4
0x100cbafb  call    ___report_rangecheckfailure
```
