# DdmSetDeviceConfigInfo

- ea: `0x180014270`
- end: `0x180014853`
- name: `DdmSetDeviceConfigInfo`
- size: `1507`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180007c0c`
- `0x180014270`
- `0x18006e4dc`
- `0x18006edc0`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x1800144c8`
- `ADVAPI32!RegSetValueExW` at `0x18001450c`
- `ADVAPI32!RegSetValueExW` at `0x180014547`
- `ADVAPI32!RegSetValueExW` at `0x180014582`
- `ADVAPI32!RegSetValueExW` at `0x1800144c8`
- `ADVAPI32!RegSetValueExW` at `0x18001450c`
- `ADVAPI32!RegSetValueExW` at `0x180014547`
- `ADVAPI32!RegSetValueExW` at `0x180014582`
- `ADVAPI32!RegCloseKey` at `0x18001459b`
- `ADVAPI32!RegCloseKey` at `0x1800147a0`
- `ADVAPI32!RegCloseKey` at `0x18001459b`
- `ADVAPI32!RegCloseKey` at `0x1800147a0`

## string_xrefs

- `0x1800142ee`: `DdmSetDeviceConfigInfo`
- `0x1800146ee`: `RegSetValueEx(EnableForRas) failed with error 0x%x`
- `0x1800146ac`: `RegSetValueEx(EnableForRouting) failed with error 0x%x`
- `0x180014667`: `RegSetValueEx(WanEndPoints) failed with error 0x%x`
- `0x180014615`: `RegSetValueEx(MaxWanEndPoints) failed with error 0x%x`

## pseudocode

```c
__int64 __fastcall DdmSetDeviceConfigInfo(__int64 a1, unsigned int a2, unsigned int a3, __int64 a4)
{
  unsigned int v5; // r15d
  unsigned int RegKeyFromGuid; // edi
  __int64 v8; // r8
  char v9; // cl
  __int64 v10; // rbx
  __int64 v11; // rax
  unsigned int v12; // edx
  unsigned int *i; // rsi
  __int64 *v14; // rdi
  int *v15; // r14
  char *v16; // r15
  int *v17; // r12
  char *v18; // r13
  unsigned int RestrictedPortCount; // ecx
  unsigned int *v20; // r8
  int v21; // r9d
  unsigned int v22; // edx
  unsigned int v23; // eax
  int v24; // ecx
  __int64 v25; // r8
  __int64 v26; // r8
  BYTE lpData[8]; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[4]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v31; // [rsp+44h] [rbp-BCh]
  unsigned int v32; // [rsp+48h] [rbp-B8h]
  __int64 v33; // [rsp+50h] [rbp-B0h]
  __int64 v34; // [rsp+58h] [rbp-A8h]
  _BYTE v35[16]; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v36; // [rsp+70h] [rbp-90h]
  int v37; // [rsp+78h] [rbp-88h]
  int v38; // [rsp+7Ch] [rbp-84h]
  int v39; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v40[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v32 = a2;
  *(_DWORD *)lpData = 0;
  v5 = a2;
  *(_DWORD *)Data = 0;
  hKey = 0;
  v39 = 0;
  v33 = a4;
  RegKeyFromGuid = 0;
  memset_0(v40, 0, sizeof(v40));
  v9 = byte_1800CF404;
  v10 = -1;
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    v11 = -1;
    do
      ++v11;
    while ( aDdmsetdeviceco[v11] );
    v36 = L"DdmSetDeviceConfigInfo";
    v37 = 2 * v11 + 2;
    v38 = 0;
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v8, 2, v35);
    v9 = byte_1800CF404;
  }
  if ( a3 < 472 * v5 || !a4 )
  {
    RegKeyFromGuid = 87;
    if ( (v9 & 0x10) != 0 )
    {
      LOWORD(v39) = 0;
      FormatRRASErrorString(&v39, L"Invalid parameter. BufferSize=0x%x, Buffer=0x%x", a3, a4);
      if ( (byte_1800CF404 & 0x10) != 0 )
      {
        do
          ++v10;
        while ( *(_WORD *)&v40[2 * v10 - 4] );
        v38 = 0;
        v37 = 2 * v10 + 2;
        v36 = (const wchar_t *)&v39;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v26, 2, v35);
      }
    }
    return RegKeyFromGuid;
  }
  v12 = 0;
  v31 = 0;
  if ( !v5 )
    return RegKeyFromGuid;
  for ( i = (unsigned int *)(a4 + 44); ; i += 118 )
  {
    switch ( i[1] )
    {
      case 8u:
        v14 = qword_1800D0108;
        v15 = &dword_1800D011C;
        v16 = byte_1800D0118;
        v17 = &dword_1800CFFF4;
        v18 = byte_1800CFFF8;
        break;
      case 9u:
        v14 = qword_1800D0240;
        v15 = &dword_1800D0254;
        v16 = byte_1800D0250;
        v17 = &dword_1800D012C;
        v18 = byte_1800D0130;
        break;
      case 0xEu:
        v14 = qword_1800D0378;
        v15 = &dword_1800D038C;
        v16 = byte_1800D0388;
        v17 = &dword_1800D0264;
        v18 = byte_1800D0268;
        break;
      case 0xFu:
        v14 = qword_1800D04B0;
        v15 = &dword_1800D04C4;
        v16 = byte_1800D04C0;
        v17 = &dword_1800D039C;
        v18 = byte_1800D03A0;
        break;
      case 0x10u:
        v14 = (__int64 *)&qword_1800D05E8;
        v15 = &dword_1800D05FC;
        v16 = byte_1800D05F8;
        v17 = &dword_1800D04D4;
        v18 = byte_1800D04D8;
        break;
      default:
        goto LABEL_31;
    }
    RestrictedPortCount = GetRestrictedPortCount(i[1]);
    *(_DWORD *)lpData = RestrictedPortCount;
    v22 = RestrictedPortCount;
    if ( *i <= RestrictedPortCount )
    {
      RestrictedPortCount = *i;
      v22 = *i;
      *(_DWORD *)lpData = *i;
    }
    v23 = *(i - 4);
    if ( v23 > v22 )
      v23 = RestrictedPortCount;
    *(_DWORD *)Data = v23;
    RegKeyFromGuid = lrGetRegKeyFromGuid((unsigned __int8 *)v14, &hKey, v20, v21);
    if ( RegKeyFromGuid )
      break;
    v34 = 472LL * v31;
    RegKeyFromGuid = RegSetValueExW(hKey, L"EnableForRas", 0, 4u, (const BYTE *)(v34 + v33 + 8), 4u);
    if ( RegKeyFromGuid )
    {
      if ( (byte_1800CF404 & 8) != 0 )
      {
        LOWORD(v39) = 0;
        FormatRRASErrorString(&v39, L"RegSetValueEx(EnableForRas) failed with error 0x%x", RegKeyFromGuid);
        if ( (byte_1800CF404 & 8) != 0 )
        {
          do
            ++v10;
          while ( *(_WORD *)&v40[2 * v10 - 4] );
          goto LABEL_52;
        }
      }
      goto LABEL_54;
    }
    RegKeyFromGuid = RegSetValueExW(hKey, L"EnableForRouting", 0, 4u, (const BYTE *)(v34 + v33 + 12), 4u);
    if ( RegKeyFromGuid )
    {
      if ( (byte_1800CF404 & 8) != 0 )
      {
        LOWORD(v39) = 0;
        FormatRRASErrorString(&v39, L"RegSetValueEx(EnableForRouting) failed with error 0x%x", RegKeyFromGuid);
        if ( (byte_1800CF404 & 8) != 0 )
        {
          do
            ++v10;
          while ( *(_WORD *)&v40[2 * v10 - 4] );
          goto LABEL_52;
        }
      }
      goto LABEL_54;
    }
    RegKeyFromGuid = RegSetValueExW(hKey, L"WanEndPoints", 0, 4u, Data, 4u);
    if ( RegKeyFromGuid )
    {
      if ( (byte_1800CF404 & 8) != 0 )
      {
        LOWORD(v39) = 0;
        FormatRRASErrorString(&v39, L"RegSetValueEx(WanEndPoints) failed with error 0x%x", RegKeyFromGuid);
        if ( (byte_1800CF404 & 8) != 0 )
        {
          do
            ++v10;
          while ( *(_WORD *)&v40[2 * v10 - 4] );
          goto LABEL_52;
        }
      }
      goto LABEL_54;
    }
    RegKeyFromGuid = RegSetValueExW(hKey, L"MaxWanEndPoints", 0, 4u, lpData, 4u);
    if ( RegKeyFromGuid )
    {
      if ( (byte_1800CF404 & 8) != 0 )
      {
        LOWORD(v39) = 0;
        FormatRRASErrorString(&v39, L"RegSetValueEx(MaxWanEndPoints) failed with error 0x%x", RegKeyFromGuid);
        if ( (byte_1800CF404 & 8) != 0 )
        {
          do
            ++v10;
          while ( *(_WORD *)&v40[2 * v10 - 4] );
          v38 = 0;
          v36 = (const wchar_t *)&v39;
          goto LABEL_53;
        }
      }
      goto LABEL_54;
    }
    RegCloseKey(hKey);
    v24 = *(_DWORD *)Data;
    hKey = 0;
    if ( dword_1800CF654 )
      g_totalPortCount += *(_DWORD *)Data - *v15;
    v12 = v31;
    *(_DWORD *)v16 = *(_DWORD *)lpData;
    v5 = v32;
    *v15 = v24;
    *v17 = *(i - 9);
    *(_DWORD *)v18 = *(i - 8);
LABEL_31:
    v31 = ++v12;
    if ( v12 >= v5 )
      return RegKeyFromGuid;
  }
  if ( (byte_1800CF404 & 8) != 0 )
  {
    LOWORD(v39) = 0;
    FormatRRASErrorString(&v39, L"lrGetRegKeyFromGuid failed with error 0x%x", RegKeyFromGuid);
    if ( (byte_1800CF404 & 8) != 0 )
    {
      do
        ++v10;
      while ( *(_WORD *)&v40[2 * v10 - 4] );
LABEL_52:
      v38 = 0;
      v36 = (const wchar_t *)&v39;
LABEL_53:
      v37 = 2 * v10 + 2;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v25, 2, v35);
    }
  }
LABEL_54:
  if ( hKey )
    RegCloseKey(hKey);
  return RegKeyFromGuid;
}

```

## disassembly

```asm
0x180014270  mov     [rsp-8+arg_0], rbx
0x180014275  push    rbp
0x180014276  push    rsi
0x180014277  push    rdi
0x180014278  push    r12
0x18001427a  push    r13
0x18001427c  push    r14
0x18001427e  push    r15
0x180014280  lea     rbp, [rsp-790h]
0x180014288  sub     rsp, 890h
0x18001428f  mov     rax, cs:__security_cookie
0x180014296  xor     rax, rsp
0x180014299  mov     [rbp+7C0h+var_40], rax
0x1800142a0  xor     r12d, r12d
0x1800142a3  mov     [rsp+8C0h+var_878], edx
0x1800142a7  mov     esi, r8d
0x1800142aa  mov     dword ptr [rsp+8C0h+var_890], r12d
0x1800142af  mov     r15d, edx
0x1800142b2  mov     dword ptr [rsp+8C0h+Data], r12d
0x1800142b7  xor     edx, edx; Val
0x1800142b9  mov     [rsp+8C0h+hKey], r12
0x1800142be  mov     r8d, 7FCh; Size
0x1800142c4  mov     [rbp+7C0h+var_840], r12d
0x1800142c8  lea     rcx, [rbp+7C0h+var_83C]; void *
0x1800142cc  mov     [rsp+8C0h+var_870], r9
0x1800142d1  mov     edi, r12d
0x1800142d4  mov     r14, r9
0x1800142d7  call    memset_0
0x1800142dc  mov     cl, cs:byte_1800CF404
0x1800142e2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800142e6  mov     r13b, 10h
0x1800142e9  test    r13b, cl
0x1800142ec  jz      short loc_180014340
0x1800142ee  lea     rcx, aDdmsetdeviceco; "DdmSetDeviceConfigInfo"
0x1800142f5  mov     rax, rbx
0x1800142f8  inc     rax
0x1800142fb  cmp     [rcx+rax*2], r12w
0x180014300  jnz     short loc_1800142F8
0x180014302  lea     eax, ds:2[rax*2]
0x180014309  mov     [rsp+8C0h+var_850], rcx
0x18001430e  mov     [rsp+8C0h+var_848], eax
0x180014312  lea     rdx, RasDdmTraceInfo
0x180014319  lea     rax, [rsp+8C0h+var_860]
0x18001431e  mov     [rsp+8C0h+var_844], r12d
0x180014323  mov     r9d, 2
0x180014329  mov     [rsp+8C0h+lpData], rax
0x18001432e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180014335  call    McGenEventWrite_EventWriteTransfer
0x18001433a  mov     cl, cs:byte_1800CF404
0x180014340  imul    eax, r15d, 1D8h
0x180014347  cmp     esi, eax
0x180014349  jb      loc_1800147AE
0x18001434f  test    r14, r14
0x180014352  jz      loc_1800147AE
0x180014358  mov     edx, r12d
0x18001435b  mov     [rsp+8C0h+var_87C], edx
0x18001435f  test    r15d, r15d
0x180014362  jz      loc_180014826
0x180014368  lea     rsi, [r14+2Ch]
0x18001436c  mov     ecx, [rsi+4]
0x18001436f  sub     ecx, 8
0x180014372  jz      loc_18001442B
0x180014378  sub     ecx, 1
0x18001437b  jz      loc_180014406
0x180014381  sub     ecx, 5
0x180014384  jz      short loc_1800143E1
0x180014386  sub     ecx, 1
0x180014389  jz      short loc_1800143BC
0x18001438b  cmp     ecx, 1
0x18001438e  jnz     loc_1800145E6
0x180014394  lea     rdi, qword_1800D05E8
0x18001439b  lea     r14, dword_1800D05FC
0x1800143a2  lea     r15, byte_1800D05F8
0x1800143a9  lea     r12, dword_1800D04D4
0x1800143b0  lea     r13, byte_1800D04D8
0x1800143b7  jmp     loc_18001444E
0x1800143bc  lea     rdi, qword_1800D04B0
0x1800143c3  lea     r14, dword_1800D04C4
0x1800143ca  lea     r15, byte_1800D04C0
0x1800143d1  lea     r12, dword_1800D039C
0x1800143d8  lea     r13, byte_1800D03A0
0x1800143df  jmp     short loc_18001444E
0x1800143e1  lea     rdi, qword_1800D0378
0x1800143e8  lea     r14, dword_1800D038C
0x1800143ef  lea     r15, byte_1800D0388
0x1800143f6  lea     r12, dword_1800D0264
0x1800143fd  lea     r13, byte_1800D0268
0x180014404  jmp     short loc_18001444E
0x180014406  lea     rdi, qword_1800D0240
0x18001440d  lea     r14, dword_1800D0254
0x180014414  lea     r15, byte_1800D0250
0x18001441b  lea     r12, dword_1800D012C
0x180014422  lea     r13, byte_1800D0130
0x180014429  jmp     short loc_18001444E
0x18001442b  lea     rdi, qword_1800D0108
0x180014432  lea     r14, dword_1800D011C
0x180014439  lea     r15, byte_1800D0118
0x180014440  lea     r12, dword_1800CFFF4
0x180014447  lea     r13, byte_1800CFFF8
0x18001444e  mov     ecx, [rsi+4]
0x180014451  call    GetRestrictedPortCount
0x180014456  mov     ecx, eax
0x180014458  mov     dword ptr [rsp+8C0h+var_890], eax
0x18001445c  mov     edx, eax
0x18001445e  cmp     [rsi], eax
0x180014460  ja      short loc_18001446A
0x180014462  mov     ecx, [rsi]
0x180014464  mov     edx, ecx
0x180014466  mov     dword ptr [rsp+8C0h+var_890], ecx
0x18001446a  mov     eax, [rsi-10h]
0x18001446d  cmp     eax, edx
0x18001446f  lea     rdx, [rsp+8C0h+hKey]; HKEY *
0x180014474  cmova   eax, ecx
0x180014477  mov     rcx, rdi; unsigned __int8 *
0x18001447a  mov     dword ptr [rsp+8C0h+Data], eax
0x18001447e  call    ?lrGetRegKeyFromGuid@@YAJPEAEPEAPEAUHKEY__@@PEAKH@Z; lrGetRegKeyFromGuid(uchar *,HKEY__ * *,ulong *,int)
0x180014483  mov     edi, eax
0x180014485  xor     eax, eax
0x180014487  test    edi, edi
0x180014489  jnz     loc_18001471C
0x18001448f  mov     eax, [rsp+8C0h+var_87C]
0x180014493  lea     r9d, [rdi+4]; dwType
0x180014497  imul    rcx, rax, 1D8h
0x18001449e  mov     rax, [rsp+8C0h+var_870]
0x1800144a3  lea     rdx, aEnableforras; "EnableForRas"
0x1800144aa  add     rax, 8
0x1800144ae  mov     [rsp+8C0h+var_868], rcx
0x1800144b3  add     rax, rcx
0x1800144b6  mov     [rsp+8C0h+cbData], r9d; cbData
0x1800144bb  mov     rcx, [rsp+8C0h+hKey]; hKey
0x1800144c0  xor     r8d, r8d; Reserved
0x1800144c3  mov     [rsp+8C0h+lpData], rax; lpData
0x1800144c8  call    cs:__imp_RegSetValueExW
0x1800144cf  nop     dword ptr [rax+rax+00h]
0x1800144d4  mov     edi, eax
0x1800144d6  xor     eax, eax
0x1800144d8  test    edi, edi
0x1800144da  jnz     loc_1800146DA
0x1800144e0  mov     rax, [rsp+8C0h+var_870]
0x1800144e5  lea     ecx, [rdi+4]
0x1800144e8  mov     [rsp+8C0h+cbData], ecx; cbData
0x1800144ec  lea     rdx, aEnableforrouti; "EnableForRouting"
0x1800144f3  add     rax, 0Ch
0x1800144f7  mov     r9d, ecx; dwType
0x1800144fa  add     rax, [rsp+8C0h+var_868]
0x1800144ff  xor     r8d, r8d; Reserved
0x180014502  mov     rcx, [rsp+8C0h+hKey]; hKey
0x180014507  mov     [rsp+8C0h+lpData], rax; lpData
0x18001450c  call    cs:__imp_RegSetValueExW
0x180014513  nop     dword ptr [rax+rax+00h]
0x180014518  mov     edi, eax
0x18001451a  xor     eax, eax
0x18001451c  test    edi, edi
0x18001451e  jnz     loc_180014698
0x180014524  lea     ecx, [rax+4]
0x180014527  xor     r8d, r8d; Reserved
0x18001452a  mov     [rsp+8C0h+cbData], ecx; cbData
0x18001452e  lea     rax, [rsp+8C0h+Data]
0x180014533  mov     r9d, ecx; dwType
0x180014536  mov     [rsp+8C0h+lpData], rax; lpData
0x18001453b  mov     rcx, [rsp+8C0h+hKey]; hKey
0x180014540  lea     rdx, aWanendpoints_0; "WanEndPoints"
0x180014547  call    cs:__imp_RegSetValueExW
0x18001454e  nop     dword ptr [rax+rax+00h]
0x180014553  mov     edi, eax
0x180014555  xor     eax, eax
0x180014557  test    edi, edi
0x180014559  jnz     loc_180014653
0x18001455f  lea     ecx, [rax+4]
0x180014562  xor     r8d, r8d; Reserved
0x180014565  mov     [rsp+8C0h+cbData], ecx; cbData
0x180014569  lea     rax, [rsp+8C0h+var_890]
0x18001456e  mov     r9d, ecx; dwType
0x180014571  mov     [rsp+8C0h+lpData], rax; lpData
0x180014576  mov     rcx, [rsp+8C0h+hKey]; hKey
0x18001457b  lea     rdx, aMaxwanendpoint; "MaxWanEndPoints"
0x180014582  call    cs:__imp_RegSetValueExW
0x180014589  nop     dword ptr [rax+rax+00h]
0x18001458e  mov     edi, eax
0x180014590  xor     eax, eax
0x180014592  test    edi, edi
0x180014594  jnz     short loc_180014601
0x180014596  mov     rcx, [rsp+8C0h+hKey]; hKey
0x18001459b  call    cs:__imp_RegCloseKey
0x1800145a2  nop     dword ptr [rax+rax+00h]
0x1800145a7  mov     ecx, dword ptr [rsp+8C0h+Data]
0x1800145ab  xor     eax, eax
0x1800145ad  cmp     cs:dword_1800CF654, eax
0x1800145b3  mov     [rsp+8C0h+hKey], rax
0x1800145b8  jz      short loc_1800145C5
0x1800145ba  mov     eax, ecx
0x1800145bc  sub     eax, [r14]
0x1800145bf  add     cs:g_totalPortCount, eax
0x1800145c5  mov     eax, dword ptr [rsp+8C0h+var_890]
0x1800145c9  mov     edx, [rsp+8C0h+var_87C]
0x1800145cd  mov     [r15], eax
0x1800145d0  mov     r15d, [rsp+8C0h+var_878]
0x1800145d5  mov     [r14], ecx
0x1800145d8  mov     eax, [rsi-24h]
0x1800145db  mov     [r12], eax
0x1800145df  mov     eax, [rsi-20h]
0x1800145e2  mov     [r13+0], eax
0x1800145e6  inc     edx
0x1800145e8  add     rsi, 1D8h
0x1800145ef  mov     [rsp+8C0h+var_87C], edx
0x1800145f3  cmp     edx, r15d
0x1800145f6  jb      loc_18001436C
0x1800145fc  jmp     loc_180014826
0x180014601  test    cs:byte_1800CF404, 8
0x180014608  jz      loc_18001478F
0x18001460e  mov     r8d, edi
0x180014611  mov     word ptr [rbp+7C0h+var_840], ax
0x180014615  lea     rdx, aRegsetvalueexM; "RegSetValueEx(MaxWanEndPoints) failed w"...
0x18001461c  lea     rcx, [rbp+7C0h+var_840]
0x180014620  call    FormatRRASErrorString
0x180014625  test    cs:byte_1800CF404, 8
0x18001462c  jz      loc_18001478F
0x180014632  lea     rax, [rbp+7C0h+var_840]
0x180014636  xor     ecx, ecx
0x180014638  inc     rbx
0x18001463b  cmp     [rax+rbx*2], cx
0x18001463f  jnz     short loc_180014638
0x180014641  lea     rdx, [rbp+7C0h+var_840]
0x180014645  mov     [rsp+8C0h+var_844], ecx
0x180014649  mov     [rsp+8C0h+var_850], rdx
0x18001464e  jmp     loc_180014761
0x180014653  test    cs:byte_1800CF404, 8
0x18001465a  jz      loc_18001478F
0x180014660  mov     r8d, edi
0x180014663  mov     word ptr [rbp+7C0h+var_840], ax
0x180014667  lea     rdx, aRegsetvalueexW; "RegSetValueEx(WanEndPoints) failed with"...
0x18001466e  lea     rcx, [rbp+7C0h+var_840]
0x180014672  call    FormatRRASErrorString
0x180014677  test    cs:byte_1800CF404, 8
0x18001467e  jz      loc_18001478F
0x180014684  lea     rax, [rbp+7C0h+var_840]
0x180014688  xor     edx, edx
0x18001468a  inc     rbx
0x18001468d  cmp     [rax+rbx*2], dx
0x180014691  jnz     short loc_18001468A
0x180014693  jmp     loc_180014754
0x180014698  test    cs:byte_1800CF404, 8
0x18001469f  jz      loc_18001478F
0x1800146a5  mov     r8d, edi
0x1800146a8  mov     word ptr [rbp+7C0h+var_840], ax
0x1800146ac  lea     rdx, aRegsetvalueexE; "RegSetValueEx(EnableForRouting) failed "...
0x1800146b3  lea     rcx, [rbp+7C0h+var_840]
0x1800146b7  call    FormatRRASErrorString
0x1800146bc  test    cs:byte_1800CF404, 8
0x1800146c3  jz      loc_18001478F
0x1800146c9  lea     rax, [rbp+7C0h+var_840]
0x1800146cd  xor     edx, edx
0x1800146cf  inc     rbx
0x1800146d2  cmp     [rax+rbx*2], dx
0x1800146d6  jnz     short loc_1800146CF
0x1800146d8  jmp     short loc_180014754
0x1800146da  test    cs:byte_1800CF404, 8
0x1800146e1  jz      loc_18001478F
0x1800146e7  mov     r8d, edi
0x1800146ea  mov     word ptr [rbp+7C0h+var_840], ax
0x1800146ee  lea     rdx, aRegsetvalueexE_0; "RegSetValueEx(EnableForRas) failed with"...
0x1800146f5  lea     rcx, [rbp+7C0h+var_840]
0x1800146f9  call    FormatRRASErrorString
0x1800146fe  test    cs:byte_1800CF404, 8
0x180014705  jz      loc_18001478F
0x18001470b  lea     rax, [rbp+7C0h+var_840]
0x18001470f  xor     edx, edx
0x180014711  inc     rbx
0x180014714  cmp     [rax+rbx*2], dx
0x180014718  jnz     short loc_180014711
0x18001471a  jmp     short loc_180014754
0x18001471c  test    cs:byte_1800CF404, 8
0x180014723  jz      short loc_18001478F
0x180014725  mov     r8d, edi
0x180014728  mov     word ptr [rbp+7C0h+var_840], ax
0x18001472c  lea     rdx, aLrgetregkeyfro; "lrGetRegKeyFromGuid failed with error 0"...
0x180014733  lea     rcx, [rbp+7C0h+var_840]
0x180014737  call    FormatRRASErrorString
0x18001473c  test    cs:byte_1800CF404, 8
0x180014743  jz      short loc_18001478F
0x180014745  lea     rax, [rbp+7C0h+var_840]
0x180014749  xor     edx, edx
0x18001474b  inc     rbx
0x18001474e  cmp     [rax+rbx*2], dx
0x180014752  jnz     short loc_18001474B
0x180014754  lea     rcx, [rbp+7C0h+var_840]
0x180014758  mov     [rsp+8C0h+var_844], edx
0x18001475c  mov     [rsp+8C0h+var_850], rcx
0x180014761  lea     eax, ds:2[rbx*2]
0x180014768  mov     r9d, 2
0x18001476e  mov     [rsp+8C0h+var_848], eax
0x180014772  lea     rdx, RasDdmTraceError
0x180014779  lea     rax, [rsp+8C0h+var_860]
0x18001477e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180014785  mov     [rsp+8C0h+lpData], rax
0x18001478a  call    McGenEventWrite_EventWriteTransfer
0x18001478f  mov     rbx, [rsp+8C0h+hKey]
0x180014794  test    rbx, rbx
0x180014797  jz      loc_180014826
0x18001479d  mov     rcx, rbx; hKey
  ... truncated ...
```
