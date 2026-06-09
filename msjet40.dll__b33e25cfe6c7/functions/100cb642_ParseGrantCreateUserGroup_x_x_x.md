# ParseGrantCreateUserGroup(x,x,x)

- ea: `0x100cb642`
- end: `0x100cb970`
- name: `_ParseGrantCreateUserGroup@12`
- size: `814`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x100cb425`

## callees

- `0x1003e870`
- `0x10092842`
- `0x100b8a10`
- `0x100cb642`
- `0x100cf245`
- `0x100cf319`
- `0x10122f60`
- `0x10122f80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x100cb7f0`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x100cb7f0`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x100cb7e7`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x100cb7e7`
- `api-ms-win-crt-private-l1-1-0!longjmp` at `0x100cb6a3`
- `api-ms-win-crt-private-l1-1-0!longjmp` at `0x100cb6a3`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x100cb7db`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x100cb7db`

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
        __report_rangecheckfailure();
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
0x100cb642  mov     edi, edi
0x100cb644  push    ebp
0x100cb645  mov     ebp, esp
0x100cb647  sub     esp, 0B0h
0x100cb64d  mov     eax, ___security_cookie
0x100cb652  xor     eax, ebp
0x100cb654  mov     [ebp+var_4], eax
0x100cb657  push    ebx
0x100cb658  push    esi
0x100cb659  mov     esi, [ebp+arg_0]
0x100cb65c  mov     [ebp+lpAddress], ecx
0x100cb662  xor     ecx, ecx
0x100cb664  push    edi
0x100cb665  mov     edi, edx
0x100cb667  mov     [ebp+var_B0], 1
0x100cb671  cmp     dword ptr [esi+24h], 5Ch ; '\'
0x100cb675  mov     ebx, ecx
0x100cb677  mov     [ebp+var_A8], ecx
0x100cb67d  jnb     short loc_100CB6A9
0x100cb67f  mov     eax, [esi+14h]
0x100cb682  sub     eax, [esi+8]
0x100cb685  push    ecx; int
0x100cb686  push    dword ptr [esi+1Ch]; int
0x100cb689  sar     eax, 1
0x100cb68b  push    eax; int
0x100cb68c  push    0FFFFE038h; int
0x100cb691  push    ecx; void *
0x100cb692  push    ecx; void *
0x100cb693  push    ecx; Src
0x100cb694  push    dword ptr [esi]; int
0x100cb696  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x100cb69b  push    0FFFFF254h; Value
0x100cb6a0  push    dword ptr [edi+4]; Buf
0x100cb6a3  call    ds:__imp__longjmp
0x100cb6a9  mov     ecx, esi
0x100cb6ab  call    _TknGetToken@4; TknGetToken(x)
0x100cb6b0  sub     eax, 131h
0x100cb6b5  jz      short loc_100CB6E1
0x100cb6b7  sub     eax, 3Dh ; '='
0x100cb6ba  jz      short loc_100CB6EA
0x100cb6bc  mov     eax, [esi+14h]
0x100cb6bf  xor     ecx, ecx
0x100cb6c1  sub     eax, [esi+8]
0x100cb6c4  push    ecx; int
0x100cb6c5  push    dword ptr [esi+1Ch]; int
0x100cb6c8  sar     eax, 1
0x100cb6ca  push    eax; int
0x100cb6cb  push    0FFFFDD37h; int
0x100cb6d0  push    ecx; void *
0x100cb6d1  push    ecx; void *
0x100cb6d2  push    ecx; Src
0x100cb6d3  push    dword ptr [esi]; int
0x100cb6d5  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x100cb6da  push    0FFFFF213h
0x100cb6df  jmp     short loc_100CB6A0
0x100cb6e1  xor     ebx, ebx
0x100cb6e3  inc     ebx
0x100cb6e4  mov     [ebp+var_A8], ebx
0x100cb6ea  xor     eax, eax
0x100cb6ec  mov     [ebp+var_34], ax
0x100cb6f0  mov     [ebp+var_64], ax
0x100cb6f4  mov     [ebp+Destination], ax
0x100cb6fb  lea     eax, [ebp+Destination]
0x100cb701  push    14h; int
0x100cb703  push    eax; Destination
0x100cb704  push    esi; int
0x100cb705  call    _ParseSecurityId@20; ParseSecurityId(x,x,x,x,x)
0x100cb70a  cmp     eax, 0FFFFF213h
0x100cb70f  jz      loc_100CB941
0x100cb715  cmp     eax, 0FFFFFC16h
0x100cb71a  jz      loc_100CB919
0x100cb720  test    ebx, ebx
0x100cb722  jnz     short loc_100CB76E
0x100cb724  push    14h; int
0x100cb726  lea     eax, [ebp+var_64]
0x100cb729  push    eax; Destination
0x100cb72a  push    esi; int
0x100cb72b  call    _ParseSecurityId@20; ParseSecurityId(x,x,x,x,x)
0x100cb730  cmp     eax, 0FFFFF213h
0x100cb735  jz      short loc_100CB748
0x100cb737  cmp     eax, 0FFFFFC16h
0x100cb73c  jnz     short loc_100CB76E
0x100cb73e  push    0FFFFF88Fh
0x100cb743  jmp     loc_100CB6A0
0x100cb748  mov     ecx, esi
0x100cb74a  call    _TknGetToken@4; TknGetToken(x)
0x100cb74f  cmp     eax, 16h
0x100cb752  jz      short loc_100CB762
0x100cb754  cmp     eax, 2Ch ; ','
0x100cb757  jz      short loc_100CB762
0x100cb759  cmp     eax, 3Bh ; ';'
0x100cb75c  jnz     loc_100CB8BF
0x100cb762  mov     eax, [esi+14h]
0x100cb765  mov     [esi+0Ch], eax
0x100cb768  xor     eax, eax
0x100cb76a  mov     [ebp+var_64], ax
0x100cb76e  push    14h; int
0x100cb770  lea     eax, [ebp+var_34]
0x100cb773  push    eax; Destination
0x100cb774  push    esi; int
0x100cb775  call    _ParseSecurityId@20; ParseSecurityId(x,x,x,x,x)
0x100cb77a  cmp     eax, 0FFFFF213h
0x100cb77f  jz      short loc_100CB7B4
0x100cb781  cmp     eax, 0FFFFFC16h
0x100cb786  jnz     loc_100CB825
0x100cb78c  mov     eax, [esi+14h]
0x100cb78f  xor     ecx, ecx
0x100cb791  sub     eax, [esi+8]
0x100cb794  push    ecx; int
0x100cb795  push    dword ptr [esi+1Ch]; int
0x100cb798  sar     eax, 1
0x100cb79a  push    eax; int
0x100cb79b  push    0FFFFDD2Bh; int
0x100cb7a0  push    ecx; void *
0x100cb7a1  push    ecx; void *
0x100cb7a2  push    ecx; Src
0x100cb7a3  push    dword ptr [esi]; int
0x100cb7a5  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x100cb7aa  push    0FFFFF88Ah
0x100cb7af  jmp     loc_100CB6A0
0x100cb7b4  mov     ecx, esi
0x100cb7b6  call    _TknGetToken@4; TknGetToken(x)
0x100cb7bb  cmp     eax, 16h
0x100cb7be  jz      short loc_100CB7CE
0x100cb7c0  cmp     eax, 2Ch ; ','
0x100cb7c3  jz      short loc_100CB7CE
0x100cb7c5  cmp     eax, 3Bh ; ';'
0x100cb7c8  jnz     loc_100CB8D8
0x100cb7ce  mov     eax, [esi+14h]
0x100cb7d1  mov     [esi+0Ch], eax
0x100cb7d4  lea     eax, [ebp+pguid]
0x100cb7da  push    eax; pguid
0x100cb7db  call    ds:__imp__CoCreateGuid@4; CoCreateGuid(x)
0x100cb7e1  push    [ebp+pguid.Data1]
0x100cb7e7  call    ds:__imp___o_srand
0x100cb7ed  pop     ecx
0x100cb7ee  xor     ebx, ebx
0x100cb7f0  call    ds:__imp__rand
0x100cb7f6  cdq
0x100cb7f7  mov     ecx, 0DFh
0x100cb7fc  idiv    ecx
0x100cb7fe  add     edx, 20h ; ' '
0x100cb801  mov     [ebp+ebx*2+var_34], dx
0x100cb806  inc     ebx
0x100cb807  cmp     ebx, 0Ah
0x100cb80a  jb      short loc_100CB7F0
0x100cb80c  lea     eax, [ebx+ebx]
0x100cb80f  cmp     eax, 2Eh ; '.'
0x100cb812  jnb     loc_100CB96B
0x100cb818  mov     ebx, [ebp+var_A8]
0x100cb81e  xor     ecx, ecx
0x100cb820  mov     [ebp+eax+var_34], cx
0x100cb825  mov     ecx, esi
0x100cb827  call    _TknGetToken@4; TknGetToken(x)
0x100cb82c  cmp     eax, 16h
0x100cb82f  jz      short loc_100CB83F
0x100cb831  cmp     eax, 2Ch ; ','
0x100cb834  jz      short loc_100CB84F
0x100cb836  cmp     eax, 3Bh ; ';'
0x100cb839  jnz     loc_100CB8F1
0x100cb83f  mov     eax, [esi+14h]
0x100cb842  mov     [ebp+var_B0], 0
0x100cb84c  mov     [esi+0Ch], eax
0x100cb84f  mov     ecx, [ebp+lpAddress]; lpAddress
0x100cb855  lea     eax, [ebp+var_34]
0x100cb858  mov     edx, edi
0x100cb85a  push    eax; void *
0x100cb85b  test    ebx, ebx
0x100cb85d  jnz     short loc_100CB871
0x100cb85f  lea     eax, [ebp+var_64]
0x100cb862  push    eax; void *
0x100cb863  lea     eax, [ebp+Destination]
0x100cb869  push    eax; Src
0x100cb86a  call    DDLQueueCreateUser
0x100cb86f  jmp     short loc_100CB87D
0x100cb871  lea     eax, [ebp+Destination]
0x100cb877  push    eax; Src
0x100cb878  call    DDLQueueCreateGroup
0x100cb87d  cmp     [ebp+var_B0], 1
0x100cb884  jz      loc_100CB6EA
0x100cb88a  mov     ecx, esi
0x100cb88c  call    _TknGetToken@4; TknGetToken(x)
0x100cb891  cmp     eax, 3Bh ; ';'
0x100cb894  jnz     short loc_100CB89D
0x100cb896  mov     ecx, esi
0x100cb898  call    _TknGetToken@4; TknGetToken(x)
0x100cb89d  cmp     eax, 16h
0x100cb8a0  jz      loc_100CB95A
0x100cb8a6  mov     eax, [esi+14h]
0x100cb8a9  xor     ecx, ecx
0x100cb8ab  sub     eax, [esi+8]
0x100cb8ae  push    ecx
0x100cb8af  push    dword ptr [esi+1Ch]
0x100cb8b2  sar     eax, 1
0x100cb8b4  push    eax
0x100cb8b5  push    0FFFFDFEAh
0x100cb8ba  jmp     loc_100CB6D0
0x100cb8bf  mov     eax, [esi+14h]
0x100cb8c2  xor     ecx, ecx
0x100cb8c4  sub     eax, [esi+8]
0x100cb8c7  push    ecx
0x100cb8c8  push    dword ptr [esi+1Ch]
0x100cb8cb  sar     eax, 1
0x100cb8cd  push    eax
0x100cb8ce  push    0FFFFDD35h
0x100cb8d3  jmp     loc_100CB6D0
0x100cb8d8  mov     eax, [esi+14h]
0x100cb8db  xor     ecx, ecx
0x100cb8dd  sub     eax, [esi+8]
0x100cb8e0  push    ecx
0x100cb8e1  push    dword ptr [esi+1Ch]
0x100cb8e4  sar     eax, 1
0x100cb8e6  push    eax
0x100cb8e7  push    0FFFFDD2Bh
0x100cb8ec  jmp     loc_100CB6D0
0x100cb8f1  mov     eax, [esi+14h]
0x100cb8f4  xor     ecx, ecx
0x100cb8f6  sub     eax, [esi+8]
0x100cb8f9  push    ecx; int
0x100cb8fa  push    dword ptr [esi+1Ch]; int
0x100cb8fd  sar     eax, 1
0x100cb8ff  push    eax; int
0x100cb900  push    0FFFFE09Ch; int
0x100cb905  push    ecx; void *
0x100cb906  push    ecx; void *
0x100cb907  push    ecx; Src
0x100cb908  push    dword ptr [esi]; int
0x100cb90a  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x100cb90f  push    0FFFFF244h
0x100cb914  jmp     loc_100CB6A0
0x100cb919  mov     eax, [esi+14h]
0x100cb91c  xor     ecx, ecx
0x100cb91e  sub     eax, [esi+8]
0x100cb921  push    ecx; int
0x100cb922  push    dword ptr [esi+1Ch]; int
0x100cb925  sar     eax, 1
0x100cb927  push    eax; int
0x100cb928  push    0FFFFDFADh; int
0x100cb92d  push    ecx; void *
0x100cb92e  push    ecx; void *
0x100cb92f  push    ecx; Src
0x100cb930  push    dword ptr [esi]; int
0x100cb932  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x100cb937  push    0FFFFF891h
0x100cb93c  jmp     loc_100CB6A0
0x100cb941  mov     eax, [esi+14h]
0x100cb944  xor     ecx, ecx
0x100cb946  sub     eax, [esi+8]
0x100cb949  push    ecx
0x100cb94a  push    dword ptr [esi+1Ch]
0x100cb94d  sar     eax, 1
0x100cb94f  push    eax
0x100cb950  push    0FFFFDD39h
0x100cb955  jmp     loc_100CB6D0
0x100cb95a  mov     ecx, [ebp+var_4]
0x100cb95d  pop     edi
0x100cb95e  pop     esi
0x100cb95f  xor     ecx, ebp; StackCookie
0x100cb961  pop     ebx
0x100cb962  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100cb967  leave
0x100cb968  retn    4
0x100cb96b  call    ___report_rangecheckfailure
```
