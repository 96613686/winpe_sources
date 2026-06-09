# DiscpDiscoverViaStaticTargets

- ea: `0x1800027cc`
- end: `0x180002bb4`
- name: `DiscpDiscoverViaStaticTargets`
- size: `1000`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009358`

## callees

- `0x180001410`
- `0x180001cfe`
- `0x1800027cc`
- `0x180003054`
- `0x180005d2c`
- `0x1800076dc`

## import_xrefs

- `ISCSIUM!DiscpReportEventlogWithStatus` at `0x180002b8b`
- `ISCSIUM!DiscpReportEventlogWithStatus` at `0x180002b8b`
- `ISCSIUM!DiscpAllocMemory` at `0x180002905`
- `ISCSIUM!DiscpAllocMemory` at `0x18000291f`
- `ISCSIUM!DiscpAllocMemory` at `0x180002905`
- `ISCSIUM!DiscpAllocMemory` at `0x18000291f`
- `ISCSIUM!DiscpDecryptBuffer` at `0x1800029a8`
- `ISCSIUM!DiscpDecryptBuffer` at `0x1800029a8`
- `ISCSIUM!DiscpOpenRegistryKey` at `0x180002865`
- `ISCSIUM!DiscpOpenRegistryKey` at `0x180002865`
- `ISCSIUM!DiscpFreeMemory` at `0x180002b1c`
- `ISCSIUM!DiscpFreeMemory` at `0x180002b3f`
- `ISCSIUM!DiscpFreeMemory` at `0x180002b4f`
- `ISCSIUM!DiscpFreeMemory` at `0x180002b1c`
- `ISCSIUM!DiscpFreeMemory` at `0x180002b3f`
- `ISCSIUM!DiscpFreeMemory` at `0x180002b4f`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180002981`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180002981`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800028bc`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800028bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002b62`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002b62`

## pseudocode

```c
__int64 DiscpDiscoverViaStaticTargets()
{
  unsigned int inserted; // ebx
  DWORD v1; // ecx
  BYTE *v2; // rdi
  WCHAR *v3; // rsi
  DWORD v4; // r14d
  DWORD v5; // edx
  BYTE *v6; // rcx
  int *v7; // rdx
  __int128 *v8; // rax
  char *v9; // rcx
  __int64 v10; // r8
  __int128 v11; // xmm0
  int *v12; // rax
  __int64 v13; // rdx
  int lpcbMaxClassLen; // [rsp+30h] [rbp-D0h]
  DWORD cbMaxValueNameLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbData; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cbMaxValueLen; // [rsp+68h] [rbp-98h] BYREF
  DWORD v19; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD cValues; // [rsp+70h] [rbp-90h] BYREF
  BYTE *v21; // [rsp+78h] [rbp-88h] BYREF
  DWORD cchValueName; // [rsp+80h] [rbp-80h] BYREF
  DWORD Type; // [rsp+84h] [rbp-7Ch] BYREF
  HKEY hKey; // [rsp+88h] [rbp-78h] BYREF
  int *v25; // [rsp+90h] [rbp-70h] BYREF
  _DWORD *v26; // [rsp+98h] [rbp-68h] BYREF
  const wchar_t *v27; // [rsp+A0h] [rbp-60h] BYREF
  const wchar_t *v28; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v29; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v30[64]; // [rsp+C0h] [rbp-40h] BYREF
  int v31; // [rsp+100h] [rbp+0h] BYREF
  char v32; // [rsp+104h] [rbp+4h]
  char v33; // [rsp+108h] [rbp+8h] BYREF

  hKey = 0;
  cValues = 0;
  v19 = 0;
  cbMaxValueLen = 0;
  Type = 0;
  cbMaxValueNameLen = 0;
  v21 = 0;
  v29 = 0;
  memset_0(&v31, 0, 0x40Cu);
  cchValueName = 0;
  v26 = 0;
  v28 = 0;
  v27 = 0;
  memset_0(v30, 0, sizeof(v30));
  cbData = 0;
  inserted = DiscpOpenRegistryKey(
               &hKey,
               L"Software\\Microsoft\\Windows NT\\CurrentVersion\\iSCSI\\Discovery\\Static Targets",
               131097);
  if ( inserted )
    goto LABEL_38;
  inserted = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  if ( inserted )
    goto LABEL_37;
  v1 = cbMaxValueNameLen + 1;
  if ( cbMaxValueNameLen + 1 < cbMaxValueNameLen )
  {
    v1 = -1;
    inserted = 534;
  }
  if ( 2 * (unsigned __int64)v1 > 0xFFFFFFFF )
  {
    inserted = 534;
    cbMaxValueNameLen = -1;
  }
  else
  {
    cbMaxValueNameLen = 2 * v1;
    if ( inserted )
      goto LABEL_37;
    v2 = (BYTE *)DiscpAllocMemory(cbMaxValueLen);
    if ( !v2 )
    {
      inserted = 8;
      goto LABEL_37;
    }
    v3 = (WCHAR *)DiscpAllocMemory(cbMaxValueNameLen);
    if ( v3 )
    {
      v4 = 0;
      if ( cValues )
      {
        while ( 1 )
        {
          if ( inserted )
            goto LABEL_33;
          cbData = cbMaxValueLen;
          cchValueName = cbMaxValueNameLen;
          inserted = RegEnumValueW(hKey, v4, v3, &cchValueName, 0, &Type, v2, &cbData);
          if ( inserted )
          {
            if ( inserted == 259 )
              inserted = 0;
            goto LABEL_32;
          }
          if ( *v3 != 42 )
            break;
          inserted = DiscpDecryptBuffer(cbData, v2, &v19, &v21);
          if ( !inserted )
          {
            v5 = v19;
            v6 = v21;
            goto LABEL_17;
          }
LABEL_32:
          if ( ++v4 >= cValues )
            goto LABEL_33;
        }
        v5 = cbData;
        v6 = v2;
        v21 = v2;
        v19 = cbData;
LABEL_17:
        if ( Type == 3 && v5 >= 0x1C )
        {
          v25 = 0;
          DiscpUnbuildStaticTarget(
            (_DWORD)v6,
            v5,
            (unsigned int)&v28,
            (unsigned int)&v27,
            (__int64)&v26,
            (__int64)v30,
            (__int64)&v25);
          v7 = v25;
          if ( v25 )
          {
            v31 = 1;
            v8 = (__int128 *)(v25 + 1);
            v32 = 0;
            v9 = &v33;
            v10 = 8;
            do
            {
              v11 = *v8;
              v8 += 8;
              *(_OWORD *)v9 = v11;
              v9 += 128;
              *((_OWORD *)v9 - 7) = *(v8 - 7);
              *((_OWORD *)v9 - 6) = *(v8 - 6);
              *((_OWORD *)v9 - 5) = *(v8 - 5);
              *((_OWORD *)v9 - 4) = *(v8 - 4);
              *((_OWORD *)v9 - 3) = *(v8 - 3);
              *((_OWORD *)v9 - 2) = *(v8 - 2);
              *((_OWORD *)v9 - 1) = *(v8 - 1);
              --v10;
            }
            while ( v10 );
            *(_WORD *)v9 = *(_WORD *)v8;
            v12 = &v31;
          }
          else
          {
            v12 = 0;
          }
          v25 = v12;
          inserted = DiscpCreateTarget(
                       v28,
                       v27,
                       0,
                       v26,
                       (unsigned __int64)v30 & -(__int64)(*((_DWORD *)v21 + 3) != 0),
                       *((_DWORD *)v21 + 2),
                       v7 != 0,
                       (__int64)&v25,
                       2,
                       2,
                       &v29);
          if ( !inserted )
          {
            LOBYTE(v13) = 1;
            inserted = DiscpInsertTarget(v29, v13);
          }
          v6 = v21;
        }
        else
        {
          inserted = 11;
        }
        if ( v6 != v2 )
          DiscpFreeMemory(v6);
        goto LABEL_32;
      }
LABEL_33:
      DiscpFreeMemory(v3);
    }
    else
    {
      inserted = 8;
    }
    DiscpFreeMemory(v2);
  }
LABEL_37:
  RegCloseKey(hKey);
  if ( inserted )
  {
LABEL_38:
    LOWORD(lpcbMaxClassLen) = 0;
    DiscpReportEventlogWithStatus(111, 2, 0, inserted, 0, 0, lpcbMaxClassLen);
  }
  return inserted;
}

```

## disassembly

```asm
0x1800027cc  push    rbp
0x1800027ce  push    rbx
0x1800027cf  push    rsi
0x1800027d0  push    rdi
0x1800027d1  push    r13
0x1800027d3  push    r14
0x1800027d5  push    r15
0x1800027d7  lea     rbp, [rsp-420h]
0x1800027df  sub     rsp, 520h
0x1800027e6  mov     rax, cs:__security_cookie
0x1800027ed  xor     rax, rsp
0x1800027f0  mov     [rbp+450h+var_40], rax
0x1800027f7  xor     r15d, r15d
0x1800027fa  lea     rcx, [rbp+450h+var_450]; void *
0x1800027fe  xor     edx, edx; Val
0x180002800  mov     [rbp+450h+hKey], r15
0x180002804  mov     r8d, 40Ch; Size
0x18000280a  mov     [rsp+550h+cValues], r15d
0x18000280f  mov     [rsp+550h+var_4E4], r15d
0x180002814  mov     [rsp+550h+cbMaxValueLen], r15d
0x180002819  mov     [rbp+450h+Type], r15d
0x18000281d  mov     [rsp+550h+cbMaxValueNameLen], r15d
0x180002822  mov     [rsp+550h+var_4D8], r15
0x180002827  mov     [rbp+450h+var_4A0], r15
0x18000282b  call    memset_0
0x180002830  xor     edx, edx; Val
0x180002832  mov     [rbp+450h+cchValueName], r15d
0x180002836  lea     r8d, [r15+40h]; Size
0x18000283a  mov     [rbp+450h+var_4B8], r15
0x18000283e  lea     rcx, [rbp+450h+var_490]; void *
0x180002842  mov     [rbp+450h+var_4A8], r15
0x180002846  mov     [rbp+450h+var_4B0], r15
0x18000284a  call    memset_0
0x18000284f  mov     r8d, 20019h
0x180002855  mov     [rsp+550h+cbData], r15d
0x18000285a  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows NT\\Curren"...
0x180002861  lea     rcx, [rbp+450h+hKey]
0x180002865  call    cs:__imp_DiscpOpenRegistryKey
0x18000286b  lea     r13d, [r15+2]
0x18000286f  mov     ebx, eax
0x180002871  test    eax, eax
0x180002873  jnz     loc_180002B6C
0x180002879  mov     rcx, [rbp+450h+hKey]; hKey
0x18000287d  lea     rax, [rsp+550h+cbMaxValueLen]
0x180002882  mov     [rsp+550h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180002887  xor     r9d, r9d; lpReserved
0x18000288a  mov     [rsp+550h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000288f  xor     r8d, r8d; lpcchClass
0x180002892  mov     [rsp+550h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180002897  xor     edx, edx; lpClass
0x180002899  lea     rax, [rsp+550h+cbMaxValueNameLen]
0x18000289e  mov     [rsp+550h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800028a3  lea     rax, [rsp+550h+cValues]
0x1800028a8  mov     [rsp+550h+lpcValues], rax; lpcValues
0x1800028ad  mov     [rsp+550h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800028b2  mov     [rsp+550h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800028b7  mov     [rsp+550h+lpcSubKeys], r15; lpcSubKeys
0x1800028bc  call    cs:__imp_RegQueryInfoKeyW
0x1800028c2  mov     ebx, eax
0x1800028c4  test    eax, eax
0x1800028c6  jnz     loc_180002B5E
0x1800028cc  mov     eax, [rsp+550h+cbMaxValueNameLen]
0x1800028d0  mov     edx, 0FFFFFFFFh
0x1800028d5  mov     r8d, 216h
0x1800028db  lea     ecx, [rax+1]
0x1800028de  cmp     ecx, eax
0x1800028e0  jnb     short loc_1800028E7
0x1800028e2  mov     ecx, edx
0x1800028e4  mov     ebx, r8d
0x1800028e7  mov     eax, ecx
0x1800028e9  add     rax, rax
0x1800028ec  cmp     rax, rdx
0x1800028ef  ja      loc_180002B57
0x1800028f5  mov     [rsp+550h+cbMaxValueNameLen], eax
0x1800028f9  test    ebx, ebx
0x1800028fb  jnz     loc_180002B5E
0x180002901  mov     ecx, [rsp+550h+cbMaxValueLen]
0x180002905  call    cs:__imp_DiscpAllocMemory
0x18000290b  mov     rdi, rax
0x18000290e  test    rax, rax
0x180002911  jnz     short loc_18000291B
0x180002913  lea     ebx, [rax+8]
0x180002916  jmp     loc_180002B5E
0x18000291b  mov     ecx, [rsp+550h+cbMaxValueNameLen]
0x18000291f  call    cs:__imp_DiscpAllocMemory
0x180002925  mov     rsi, rax
0x180002928  test    rax, rax
0x18000292b  jz      loc_180002B47
0x180002931  mov     r14d, r15d
0x180002934  cmp     [rsp+550h+cValues], r15d
0x180002939  jbe     loc_180002B3C
0x18000293f  test    ebx, ebx
0x180002941  jnz     loc_180002B3C
0x180002947  mov     eax, [rsp+550h+cbMaxValueLen]
0x18000294b  lea     r9, [rbp+450h+cchValueName]; lpcchValueName
0x18000294f  mov     rcx, [rbp+450h+hKey]; hKey
0x180002953  mov     r8, rsi; lpValueName
0x180002956  mov     [rsp+550h+cbData], eax
0x18000295a  mov     edx, r14d; dwIndex
0x18000295d  mov     eax, [rsp+550h+cbMaxValueNameLen]
0x180002961  mov     [rbp+450h+cchValueName], eax
0x180002964  lea     rax, [rsp+550h+cbData]
0x180002969  mov     [rsp+550h+lpcValues], rax; lpcbData
0x18000296e  lea     rax, [rbp+450h+Type]
0x180002972  mov     [rsp+550h+lpcbMaxClassLen], rdi; lpData
0x180002977  mov     [rsp+550h+lpcbMaxSubKeyLen], rax; lpType
0x18000297c  mov     [rsp+550h+lpcSubKeys], r15; lpReserved
0x180002981  call    cs:__imp_RegEnumValueW
0x180002987  mov     ebx, eax
0x180002989  test    eax, eax
0x18000298b  jnz     loc_180002B24
0x180002991  cmp     word ptr [rsi], 2Ah ; '*'
0x180002995  jnz     short loc_1800029C3
0x180002997  mov     ecx, [rsp+550h+cbData]
0x18000299b  lea     r9, [rsp+550h+var_4D8]
0x1800029a0  lea     r8, [rsp+550h+var_4E4]
0x1800029a5  mov     rdx, rdi
0x1800029a8  call    cs:__imp_DiscpDecryptBuffer
0x1800029ae  mov     ebx, eax
0x1800029b0  test    eax, eax
0x1800029b2  jnz     loc_180002B2E
0x1800029b8  mov     edx, [rsp+550h+var_4E4]
0x1800029bc  mov     rcx, [rsp+550h+var_4D8]
0x1800029c1  jmp     short loc_1800029D3
0x1800029c3  mov     edx, [rsp+550h+cbData]
0x1800029c7  mov     rcx, rdi
0x1800029ca  mov     [rsp+550h+var_4D8], rcx
0x1800029cf  mov     [rsp+550h+var_4E4], edx
0x1800029d3  cmp     [rbp+450h+Type], 3
0x1800029d7  jnz     loc_180002B12
0x1800029dd  cmp     edx, 1Ch
0x1800029e0  jb      loc_180002B12
0x1800029e6  lea     rax, [rbp+450h+var_4C0]
0x1800029ea  mov     [rbp+450h+var_4C0], r15
0x1800029ee  mov     [rsp+550h+lpcbMaxClassLen], rax
0x1800029f3  lea     r9, [rbp+450h+var_4B0]
0x1800029f7  lea     rax, [rbp+450h+var_490]
0x1800029fb  mov     [rsp+550h+lpcbMaxSubKeyLen], rax
0x180002a00  lea     r8, [rbp+450h+var_4A8]
0x180002a04  lea     rax, [rbp+450h+var_4B8]
0x180002a08  mov     [rsp+550h+lpcSubKeys], rax
0x180002a0d  call    DiscpUnbuildStaticTarget
0x180002a12  mov     rdx, [rbp+450h+var_4C0]
0x180002a16  test    rdx, rdx
0x180002a19  jz      short loc_180002A92
0x180002a1b  mov     [rbp+450h+var_450], 1
0x180002a22  lea     rax, [rdx+4]
0x180002a26  mov     [rbp+450h+var_44C], r15b
0x180002a2a  lea     rcx, [rbp+450h+var_448]
0x180002a2e  mov     r8d, 8
0x180002a34  movups  xmm0, xmmword ptr [rax]
0x180002a37  lea     rax, [rax+80h]
0x180002a3e  movups  xmmword ptr [rcx], xmm0
0x180002a41  lea     rcx, [rcx+80h]
0x180002a48  movups  xmm1, xmmword ptr [rax-70h]
0x180002a4c  movups  xmmword ptr [rcx-70h], xmm1
0x180002a50  movups  xmm0, xmmword ptr [rax-60h]
0x180002a54  movups  xmmword ptr [rcx-60h], xmm0
0x180002a58  movups  xmm1, xmmword ptr [rax-50h]
0x180002a5c  movups  xmmword ptr [rcx-50h], xmm1
0x180002a60  movups  xmm0, xmmword ptr [rax-40h]
0x180002a64  movups  xmmword ptr [rcx-40h], xmm0
0x180002a68  movups  xmm1, xmmword ptr [rax-30h]
0x180002a6c  movups  xmmword ptr [rcx-30h], xmm1
0x180002a70  movups  xmm0, xmmword ptr [rax-20h]
0x180002a74  movups  xmmword ptr [rcx-20h], xmm0
0x180002a78  movups  xmm1, xmmword ptr [rax-10h]
0x180002a7c  movups  xmmword ptr [rcx-10h], xmm1
0x180002a80  sub     r8, 1
0x180002a84  jnz     short loc_180002A34
0x180002a86  movzx   eax, word ptr [rax]
0x180002a89  mov     [rcx], ax
0x180002a8c  lea     rax, [rbp+450h+var_450]
0x180002a90  jmp     short loc_180002A95
0x180002a92  mov     rax, r15
0x180002a95  mov     r9, [rbp+450h+var_4B8]
0x180002a99  test    rdx, rdx
0x180002a9c  mov     rdx, [rsp+550h+var_4D8]
0x180002aa1  mov     r8d, r15d
0x180002aa4  mov     [rbp+450h+var_4C0], rax
0x180002aa8  setnz   r8b
0x180002aac  mov     eax, [rdx+0Ch]
0x180002aaf  neg     eax
0x180002ab1  lea     rax, [rbp+450h+var_490]
0x180002ab5  sbb     rcx, rcx
0x180002ab8  and     rcx, rax
0x180002abb  lea     rax, [rbp+450h+var_4A0]
0x180002abf  mov     [rsp+550h+lpcbSecurityDescriptor], rax
0x180002ac4  lea     rax, [rbp+450h+var_4C0]
0x180002ac8  mov     dword ptr [rsp+550h+lpcbMaxValueLen], r13d
0x180002acd  mov     dword ptr [rsp+550h+lpcbMaxValueNameLen], r13d
0x180002ad2  mov     [rsp+550h+lpcValues], rax
0x180002ad7  mov     eax, [rdx+8]
0x180002ada  mov     rdx, [rbp+450h+var_4B0]
0x180002ade  mov     dword ptr [rsp+550h+lpcbMaxClassLen], r8d
0x180002ae3  xor     r8d, r8d
0x180002ae6  mov     dword ptr [rsp+550h+lpcbMaxSubKeyLen], eax
0x180002aea  mov     [rsp+550h+lpcSubKeys], rcx
0x180002aef  mov     rcx, [rbp+450h+var_4A8]
0x180002af3  call    DiscpCreateTarget
0x180002af8  mov     ebx, eax
0x180002afa  test    eax, eax
0x180002afc  jnz     short loc_180002B0B
0x180002afe  mov     rcx, [rbp+450h+var_4A0]
0x180002b02  mov     dl, 1
0x180002b04  call    DiscpInsertTarget
0x180002b09  mov     ebx, eax
0x180002b0b  mov     rcx, [rsp+550h+var_4D8]
0x180002b10  jmp     short loc_180002B17
0x180002b12  mov     ebx, 0Bh
0x180002b17  cmp     rcx, rdi
0x180002b1a  jz      short loc_180002B2E
0x180002b1c  call    cs:__imp_DiscpFreeMemory
0x180002b22  jmp     short loc_180002B2E
0x180002b24  cmp     ebx, 103h
0x180002b2a  cmovz   ebx, r15d
0x180002b2e  inc     r14d
0x180002b31  cmp     r14d, [rsp+550h+cValues]
0x180002b36  jb      loc_18000293F
0x180002b3c  mov     rcx, rsi
0x180002b3f  call    cs:__imp_DiscpFreeMemory
0x180002b45  jmp     short loc_180002B4C
0x180002b47  mov     ebx, 8
0x180002b4c  mov     rcx, rdi
0x180002b4f  call    cs:__imp_DiscpFreeMemory
0x180002b55  jmp     short loc_180002B5E
0x180002b57  mov     ebx, r8d
0x180002b5a  mov     [rsp+550h+cbMaxValueNameLen], edx
0x180002b5e  mov     rcx, [rbp+450h+hKey]; hKey
0x180002b62  call    cs:__imp_RegCloseKey
0x180002b68  test    ebx, ebx
0x180002b6a  jz      short loc_180002B91
0x180002b6c  mov     word ptr [rsp+550h+lpcbMaxClassLen], r15w
0x180002b72  mov     r9d, ebx
0x180002b75  mov     [rsp+550h+lpcbMaxSubKeyLen], r15
0x180002b7a  mov     edx, r13d
0x180002b7d  movzx   r8d, r15w
0x180002b81  mov     ecx, 6Fh ; 'o'
0x180002b86  mov     [rsp+550h+lpcSubKeys], r15
0x180002b8b  call    cs:__imp_DiscpReportEventlogWithStatus
0x180002b91  mov     eax, ebx
0x180002b93  mov     rcx, [rbp+450h+var_40]
0x180002b9a  xor     rcx, rsp; StackCookie
0x180002b9d  call    __security_check_cookie
0x180002ba2  add     rsp, 520h
0x180002ba9  pop     r15
0x180002bab  pop     r14
0x180002bad  pop     r13
0x180002baf  pop     rdi
0x180002bb0  pop     rsi
0x180002bb1  pop     rbx
0x180002bb2  pop     rbp
0x180002bb3  retn
```
