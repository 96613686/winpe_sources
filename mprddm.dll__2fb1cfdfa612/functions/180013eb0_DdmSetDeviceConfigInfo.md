# DdmSetDeviceConfigInfo

- ea: `0x180013eb0`
- end: `0x1800144bc`
- name: `DdmSetDeviceConfigInfo`
- size: `1548`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180007b7c`
- `0x180013eb0`
- `0x18006b9a0`
- `0x18006c1d0`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18001413d`
- `ADVAPI32!RegSetValueExW` at `0x18001417a`
- `ADVAPI32!RegSetValueExW` at `0x1800141ab`
- `ADVAPI32!RegSetValueExW` at `0x1800141dc`
- `ADVAPI32!RegSetValueExW` at `0x18001413d`
- `ADVAPI32!RegSetValueExW` at `0x18001417a`
- `ADVAPI32!RegSetValueExW` at `0x1800141ab`
- `ADVAPI32!RegSetValueExW` at `0x1800141dc`
- `ADVAPI32!RegCloseKey` at `0x1800141eb`
- `ADVAPI32!RegCloseKey` at `0x18001440f`
- `ADVAPI32!RegCloseKey` at `0x1800141eb`
- `ADVAPI32!RegCloseKey` at `0x18001440f`

## string_xrefs

- `0x180013f2d`: `DdmSetDeviceConfigInfo`
- `0x180014351`: `RegSetValueEx(EnableForRas) failed with error 0x%x`
- `0x180014306`: `RegSetValueEx(EnableForRouting) failed with error 0x%x`
- `0x1800142bb`: `RegSetValueEx(WanEndPoints) failed with error 0x%x`
- `0x180014263`: `RegSetValueEx(MaxWanEndPoints) failed with error 0x%x`

## pseudocode

```c
__int64 __fastcall DdmSetDeviceConfigInfo(__int64 a1, unsigned int a2, unsigned int a3, __int64 a4)
{
  unsigned int v5; // r15d
  __int64 v7; // r8
  char v8; // cl
  unsigned int v9; // ebx
  unsigned int v10; // r14d
  unsigned int v11; // edx
  __int64 *v12; // rbx
  char *v13; // rdi
  int *v14; // r15
  char *v15; // r12
  int *v16; // r13
  unsigned int RestrictedPortCount; // ecx
  unsigned int *v18; // r8
  int v19; // r9d
  unsigned int v20; // edx
  unsigned int v21; // eax
  unsigned int RegKeyFromGuid; // eax
  HKEY v23; // rdi
  int v24; // eax
  __int64 v25; // r8
  __int64 v26; // rax
  __int64 v27; // r8
  __int64 v28; // rax
  BYTE v30[4]; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  int *v32; // [rsp+38h] [rbp-C8h]
  char *v33; // [rsp+40h] [rbp-C0h]
  const BYTE *lpData; // [rsp+48h] [rbp-B8h]
  unsigned int v35; // [rsp+50h] [rbp-B0h]
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v37[16]; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v38; // [rsp+70h] [rbp-90h]
  __int64 v39; // [rsp+78h] [rbp-88h]
  int v40; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v41[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v35 = a2;
  *(_DWORD *)v30 = 0;
  v5 = a2;
  *(_DWORD *)Data = 0;
  hKey = 0;
  v40 = 0;
  memset_0(v41, 0, sizeof(v41));
  v8 = byte_1800C8404;
  LOBYTE(v32) = byte_1800C8404 & 0x10;
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    v39 = 46;
    v38 = L"DdmSetDeviceConfigInfo";
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v7, 2, v37);
    v8 = byte_1800C8404;
  }
  if ( a3 < 472 * v5 || !a4 )
  {
    v9 = 87;
    if ( (v8 & 0x10) != 0 )
    {
      LOWORD(v40) = 0;
      FormatRRASErrorString(&v40, L"Invalid parameter. BufferSize=0x%x, Buffer=0x%x", a3, a4);
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        v28 = -1;
        do
          ++v28;
        while ( *(_WORD *)&v41[2 * v28 - 4] );
        v39 = (unsigned int)(2 * v28 + 2);
        v38 = (const wchar_t *)&v40;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v27, 2, v37);
      }
    }
    return v9;
  }
  v9 = 0;
  v10 = 0;
  if ( !v5 )
    return v9;
  while ( 1 )
  {
    lpData = (const BYTE *)(472LL * v10);
    v11 = *(_DWORD *)&lpData[a4 + 48];
    if ( v11 == 8 )
    {
      v32 = &dword_1800C8FF4;
      v12 = qword_1800C9108;
      v33 = byte_1800C8FF8;
      v14 = &dword_1800C911C;
      v15 = byte_1800C9118;
      v16 = &dword_1800C911C;
    }
    else
    {
      switch ( *(_DWORD *)&lpData[a4 + 48] )
      {
        case 9:
          v32 = &dword_1800C912C;
          v12 = qword_1800C9240;
          v13 = byte_1800C9130;
          v14 = &dword_1800C9254;
          v15 = byte_1800C9250;
          v16 = &dword_1800C9254;
          break;
        case 0xE:
          v32 = &dword_1800C9264;
          v12 = qword_1800C9378;
          v13 = byte_1800C9268;
          v14 = &dword_1800C938C;
          v15 = byte_1800C9388;
          v16 = &dword_1800C938C;
          break;
        case 0xF:
          v32 = &dword_1800C939C;
          v12 = qword_1800C94B0;
          v13 = byte_1800C93A0;
          v14 = &dword_1800C94C4;
          v15 = byte_1800C94C0;
          v16 = &dword_1800C94C4;
          break;
        case 0x10:
          v32 = &dword_1800C94D4;
          v12 = (__int64 *)&qword_1800C95E8;
          v13 = byte_1800C94D8;
          v14 = &dword_1800C95FC;
          v15 = byte_1800C95F8;
          v16 = &dword_1800C95FC;
          break;
        default:
          goto LABEL_30;
      }
      v33 = v13;
    }
    RestrictedPortCount = GetRestrictedPortCount(v11);
    *(_DWORD *)v30 = RestrictedPortCount;
    v20 = *(_DWORD *)&lpData[a4 + 44];
    if ( v20 > RestrictedPortCount )
    {
      v20 = RestrictedPortCount;
    }
    else
    {
      RestrictedPortCount = *(_DWORD *)&lpData[a4 + 44];
      *(_DWORD *)v30 = RestrictedPortCount;
    }
    v21 = *(_DWORD *)&lpData[a4 + 28];
    if ( v21 > v20 )
      v21 = RestrictedPortCount;
    *(_DWORD *)Data = v21;
    RegKeyFromGuid = lrGetRegKeyFromGuid((unsigned __int8 *)v12, &hKey, v18, v19);
    v23 = hKey;
    v9 = RegKeyFromGuid;
    if ( RegKeyFromGuid )
      break;
    v9 = RegSetValueExW(hKey, L"EnableForRas", 0, 4u, &lpData[a4 + 8], 4u);
    if ( v9 )
    {
      if ( (byte_1800C8404 & 8) != 0 )
      {
        LOWORD(v40) = 0;
        FormatRRASErrorString(&v40, L"RegSetValueEx(EnableForRas) failed with error 0x%x", v9);
        if ( (byte_1800C8404 & 8) != 0 )
        {
          v26 = -1;
          do
            ++v26;
          while ( *(_WORD *)&v41[2 * v26 - 4] );
          goto LABEL_56;
        }
      }
      goto LABEL_58;
    }
    lpData += a4 + 12;
    v9 = RegSetValueExW(v23, L"EnableForRouting", 0, 4u, lpData, 4u);
    if ( v9 )
    {
      if ( (byte_1800C8404 & 8) != 0 )
      {
        LOWORD(v40) = 0;
        FormatRRASErrorString(&v40, L"RegSetValueEx(EnableForRouting) failed with error 0x%x", v9);
        if ( (byte_1800C8404 & 8) != 0 )
        {
          v26 = -1;
          do
            ++v26;
          while ( *(_WORD *)&v41[2 * v26 - 4] );
          goto LABEL_56;
        }
      }
      goto LABEL_58;
    }
    v9 = RegSetValueExW(v23, L"WanEndPoints", 0, 4u, Data, 4u);
    if ( v9 )
    {
      if ( (byte_1800C8404 & 8) != 0 )
      {
        LOWORD(v40) = 0;
        FormatRRASErrorString(&v40, L"RegSetValueEx(WanEndPoints) failed with error 0x%x", v9);
        if ( (byte_1800C8404 & 8) != 0 )
        {
          v26 = -1;
          do
            ++v26;
          while ( *(_WORD *)&v41[2 * v26 - 4] );
          goto LABEL_56;
        }
      }
      goto LABEL_58;
    }
    v9 = RegSetValueExW(v23, L"MaxWanEndPoints", 0, 4u, v30, 4u);
    if ( v9 )
    {
      if ( (byte_1800C8404 & 8) != 0 )
      {
        LOWORD(v40) = 0;
        FormatRRASErrorString(&v40, L"RegSetValueEx(MaxWanEndPoints) failed with error 0x%x", v9);
        if ( (byte_1800C8404 & 8) != 0 )
        {
          v26 = -1;
          do
            ++v26;
          while ( *(_WORD *)&v41[2 * v26 - 4] );
          HIDWORD(v39) = 0;
          v38 = (const wchar_t *)&v40;
          goto LABEL_57;
        }
      }
      goto LABEL_58;
    }
    RegCloseKey(v23);
    hKey = 0;
    if ( dword_1800C8654 )
      g_totalPortCount += *(_DWORD *)Data - *v14;
    v24 = *(_DWORD *)v30;
    v5 = v35;
    *v16 = *(_DWORD *)Data;
    *(_DWORD *)v15 = v24;
    *v32 = *(_DWORD *)(472LL * v10 + a4 + 8);
    *(_DWORD *)v33 = *(_DWORD *)lpData;
LABEL_30:
    if ( ++v10 >= v5 )
      return v9;
  }
  if ( (byte_1800C8404 & 8) != 0 )
  {
    LOWORD(v40) = 0;
    FormatRRASErrorString(&v40, L"lrGetRegKeyFromGuid failed with error 0x%x", RegKeyFromGuid);
    if ( (byte_1800C8404 & 8) != 0 )
    {
      v26 = -1;
      do
        ++v26;
      while ( *(_WORD *)&v41[2 * v26 - 4] );
LABEL_56:
      HIDWORD(v39) = 0;
      v38 = (const wchar_t *)&v40;
LABEL_57:
      LODWORD(v39) = 2 * v26 + 2;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v25, 2, v37);
    }
  }
LABEL_58:
  if ( v23 )
    RegCloseKey(v23);
  return v9;
}

```

## disassembly

```asm
0x180013eb0  mov     [rsp-8+arg_0], rbx
0x180013eb5  push    rbp
0x180013eb6  push    rsi
0x180013eb7  push    rdi
0x180013eb8  push    r12
0x180013eba  push    r13
0x180013ebc  push    r14
0x180013ebe  push    r15
0x180013ec0  lea     rbp, [rsp-790h]
0x180013ec8  sub     rsp, 890h
0x180013ecf  mov     rax, cs:__security_cookie
0x180013ed6  xor     rax, rsp
0x180013ed9  mov     [rbp+7C0h+var_40], rax
0x180013ee0  xor     r12d, r12d
0x180013ee3  mov     [rsp+8C0h+var_870], edx
0x180013ee7  mov     edi, r8d
0x180013eea  mov     dword ptr [rsp+8C0h+var_890], r12d
0x180013eef  mov     r15d, edx
0x180013ef2  mov     dword ptr [rsp+8C0h+Data], r12d
0x180013ef7  xor     edx, edx; Val
0x180013ef9  mov     [rsp+8C0h+hKey], r12
0x180013efe  mov     r8d, 7FCh; Size
0x180013f04  mov     [rbp+7C0h+var_840], r12d
0x180013f08  lea     rcx, [rbp+7C0h+var_83C]; void *
0x180013f0c  mov     rsi, r9
0x180013f0f  call    memset_0
0x180013f14  mov     cl, cs:byte_1800C8404
0x180013f1a  lea     r13d, [r12+2]
0x180013f1f  mov     al, cl
0x180013f21  mov     r14b, 10h
0x180013f24  and     al, r14b
0x180013f27  mov     byte ptr [rsp+8C0h+var_888], al
0x180013f2b  jz      short loc_180013F68
0x180013f2d  lea     rax, aDdmsetdeviceco; "DdmSetDeviceConfigInfo"
0x180013f34  mov     [rsp+8C0h+var_848], 2Eh ; '.'
0x180013f3d  mov     [rsp+8C0h+var_850], rax
0x180013f42  lea     rdx, RasDdmTraceInfo
0x180013f49  lea     rax, [rsp+8C0h+var_860]
0x180013f4e  mov     r9d, r13d
0x180013f51  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180013f58  mov     [rsp+8C0h+lpData], rax
0x180013f5d  call    McGenEventWrite_EventWriteTransfer
0x180013f62  mov     cl, cs:byte_1800C8404
0x180013f68  imul    eax, r15d, 1D8h
0x180013f6f  cmp     edi, eax
0x180013f71  jb      loc_180014417
0x180013f77  test    rsi, rsi
0x180013f7a  jz      loc_180014417
0x180013f80  mov     ebx, r12d
0x180013f83  mov     r14d, r12d
0x180013f86  test    r15d, r15d
0x180013f89  jz      loc_180014490
0x180013f8f  mov     eax, r14d
0x180013f92  imul    rax, 1D8h
0x180013f99  mov     [rsp+8C0h+var_878], rax
0x180013f9e  mov     edx, [rax+rsi+30h]
0x180013fa2  mov     ecx, edx
0x180013fa4  sub     ecx, 8
0x180013fa7  jz      loc_180014095
0x180013fad  sub     ecx, 1
0x180013fb0  jz      loc_18001405F
0x180013fb6  sub     ecx, 5
0x180013fb9  jz      short loc_18001402E
0x180013fbb  sub     ecx, 1
0x180013fbe  jz      short loc_180013FFD
0x180013fc0  cmp     ecx, 1
0x180013fc3  jnz     loc_180014243
0x180013fc9  lea     rdi, dword_1800C94D4
0x180013fd0  mov     [rsp+8C0h+var_888], rdi
0x180013fd5  lea     rbx, qword_1800C95E8
0x180013fdc  lea     rdi, byte_1800C94D8
0x180013fe3  lea     r15, dword_1800C95FC
0x180013fea  lea     r12, byte_1800C95F8
0x180013ff1  lea     r13, dword_1800C95FC
0x180013ff8  jmp     loc_18001408E
0x180013ffd  lea     rdi, dword_1800C939C
0x180014004  mov     [rsp+8C0h+var_888], rdi
0x180014009  lea     rbx, qword_1800C94B0
0x180014010  lea     rdi, byte_1800C93A0
0x180014017  lea     r15, dword_1800C94C4
0x18001401e  lea     r12, byte_1800C94C0
0x180014025  lea     r13, dword_1800C94C4
0x18001402c  jmp     short loc_18001408E
0x18001402e  lea     rdi, dword_1800C9264
0x180014035  mov     [rsp+8C0h+var_888], rdi
0x18001403a  lea     rbx, qword_1800C9378
0x180014041  lea     rdi, byte_1800C9268
0x180014048  lea     r15, dword_1800C938C
0x18001404f  lea     r12, byte_1800C9388
0x180014056  lea     r13, dword_1800C938C
0x18001405d  jmp     short loc_18001408E
0x18001405f  lea     rdi, dword_1800C912C
0x180014066  mov     [rsp+8C0h+var_888], rdi
0x18001406b  lea     rbx, qword_1800C9240
0x180014072  lea     rdi, byte_1800C9130
0x180014079  lea     r15, dword_1800C9254
0x180014080  lea     r12, byte_1800C9250
0x180014087  lea     r13, dword_1800C9254
0x18001408e  mov     [rsp+8C0h+var_880], rdi
0x180014093  jmp     short loc_1800140C9
0x180014095  lea     rax, dword_1800C8FF4
0x18001409c  mov     [rsp+8C0h+var_888], rax
0x1800140a1  lea     rbx, qword_1800C9108
0x1800140a8  lea     rax, byte_1800C8FF8
0x1800140af  mov     [rsp+8C0h+var_880], rax
0x1800140b4  lea     r15, dword_1800C911C
0x1800140bb  lea     r12, byte_1800C9118
0x1800140c2  lea     r13, dword_1800C911C
0x1800140c9  mov     ecx, edx
0x1800140cb  call    GetRestrictedPortCount
0x1800140d0  mov     ecx, eax
0x1800140d2  mov     dword ptr [rsp+8C0h+var_890], eax
0x1800140d6  mov     rax, [rsp+8C0h+var_878]
0x1800140db  mov     edx, [rax+rsi+2Ch]
0x1800140df  cmp     edx, ecx
0x1800140e1  ja      short loc_1800140EB
0x1800140e3  mov     ecx, edx
0x1800140e5  mov     dword ptr [rsp+8C0h+var_890], edx
0x1800140e9  jmp     short loc_1800140ED
0x1800140eb  mov     edx, ecx
0x1800140ed  mov     eax, [rax+rsi+1Ch]
0x1800140f1  cmp     eax, edx
0x1800140f3  lea     rdx, [rsp+8C0h+hKey]; HKEY *
0x1800140f8  cmova   eax, ecx
0x1800140fb  mov     rcx, rbx; unsigned __int8 *
0x1800140fe  mov     dword ptr [rsp+8C0h+Data], eax
0x180014102  call    ?lrGetRegKeyFromGuid@@YAJPEAEPEAPEAUHKEY__@@PEAKH@Z; lrGetRegKeyFromGuid(uchar *,HKEY__ * *,ulong *,int)
0x180014107  mov     rdi, [rsp+8C0h+hKey]
0x18001410c  mov     ebx, eax
0x18001410e  test    eax, eax
0x180014110  jnz     loc_18001438A
0x180014116  mov     rax, [rsp+8C0h+var_878]
0x18001411b  lea     r9d, [rbx+4]; dwType
0x18001411f  add     rax, 8
0x180014123  mov     [rsp+8C0h+cbData], r9d; cbData
0x180014128  add     rax, rsi
0x18001412b  lea     rdx, aEnableforras; "EnableForRas"
0x180014132  xor     r8d, r8d; Reserved
0x180014135  mov     [rsp+8C0h+lpData], rax; lpData
0x18001413a  mov     rcx, rdi; hKey
0x18001413d  call    cs:__imp_RegSetValueExW
0x180014143  mov     ebx, eax
0x180014145  test    eax, eax
0x180014147  jnz     loc_180014342
0x18001414d  mov     rax, [rsp+8C0h+var_878]
0x180014152  lea     ecx, [rbx+4]
0x180014155  mov     [rsp+8C0h+cbData], ecx; cbData
0x180014159  lea     rdx, aEnableforrouti; "EnableForRouting"
0x180014160  add     rax, 0Ch
0x180014164  mov     r9d, ecx; dwType
0x180014167  add     rax, rsi
0x18001416a  xor     r8d, r8d; Reserved
0x18001416d  mov     rcx, rdi; hKey
0x180014170  mov     [rsp+8C0h+var_878], rax
0x180014175  mov     [rsp+8C0h+lpData], rax; lpData
0x18001417a  call    cs:__imp_RegSetValueExW
0x180014180  mov     ebx, eax
0x180014182  test    eax, eax
0x180014184  jnz     loc_1800142F7
0x18001418a  lea     ecx, [rax+4]
0x18001418d  xor     r8d, r8d; Reserved
0x180014190  mov     [rsp+8C0h+cbData], ecx; cbData
0x180014194  lea     rax, [rsp+8C0h+Data]
0x180014199  mov     r9d, ecx; dwType
0x18001419c  mov     [rsp+8C0h+lpData], rax; lpData
0x1800141a1  mov     rcx, rdi; hKey
0x1800141a4  lea     rdx, aWanendpoints_0; "WanEndPoints"
0x1800141ab  call    cs:__imp_RegSetValueExW
0x1800141b1  mov     ebx, eax
0x1800141b3  test    eax, eax
0x1800141b5  jnz     loc_1800142AC
0x1800141bb  lea     ecx, [rax+4]
0x1800141be  xor     r8d, r8d; Reserved
0x1800141c1  mov     [rsp+8C0h+cbData], ecx; cbData
0x1800141c5  lea     rax, [rsp+8C0h+var_890]
0x1800141ca  mov     r9d, ecx; dwType
0x1800141cd  mov     [rsp+8C0h+lpData], rax; lpData
0x1800141d2  mov     rcx, rdi; hKey
0x1800141d5  lea     rdx, aMaxwanendpoint; "MaxWanEndPoints"
0x1800141dc  call    cs:__imp_RegSetValueExW
0x1800141e2  mov     ebx, eax
0x1800141e4  test    eax, eax
0x1800141e6  jnz     short loc_180014254
0x1800141e8  mov     rcx, rdi; hKey
0x1800141eb  call    cs:__imp_RegCloseKey
0x1800141f1  mov     ecx, dword ptr [rsp+8C0h+Data]
0x1800141f5  xor     eax, eax
0x1800141f7  cmp     cs:dword_1800C8654, eax
0x1800141fd  mov     [rsp+8C0h+hKey], rax
0x180014202  jz      short loc_18001420F
0x180014204  mov     eax, ecx
0x180014206  sub     eax, [r15]
0x180014209  add     cs:g_totalPortCount, eax
0x18001420f  mov     eax, dword ptr [rsp+8C0h+var_890]
0x180014213  mov     r15d, [rsp+8C0h+var_870]
0x180014218  mov     [r13+0], ecx
0x18001421c  mov     [r12], eax
0x180014220  mov     eax, r14d
0x180014223  imul    rcx, rax, 1D8h
0x18001422a  mov     eax, [rcx+rsi+8]
0x18001422e  mov     rcx, [rsp+8C0h+var_888]
0x180014233  mov     [rcx], eax
0x180014235  mov     rax, [rsp+8C0h+var_878]
0x18001423a  mov     rcx, [rsp+8C0h+var_880]
0x18001423f  mov     eax, [rax]
0x180014241  mov     [rcx], eax
0x180014243  inc     r14d
0x180014246  cmp     r14d, r15d
0x180014249  jb      loc_180013F8F
0x18001424f  jmp     loc_180014490
0x180014254  test    cs:byte_1800C8404, 8
0x18001425b  jz      loc_180014403
0x180014261  xor     eax, eax
0x180014263  lea     rdx, aRegsetvalueexM; "RegSetValueEx(MaxWanEndPoints) failed w"...
0x18001426a  mov     r8d, ebx
0x18001426d  mov     word ptr [rbp+7C0h+var_840], ax
0x180014271  lea     rcx, [rbp+7C0h+var_840]
0x180014275  call    FormatRRASErrorString
0x18001427a  test    cs:byte_1800C8404, 8
0x180014281  jz      loc_180014403
0x180014287  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001428b  lea     rdx, [rbp+7C0h+var_840]
0x18001428f  xor     ecx, ecx
0x180014291  inc     rax
0x180014294  cmp     [rdx+rax*2], cx
0x180014298  jnz     short loc_180014291
0x18001429a  lea     rdx, [rbp+7C0h+var_840]
0x18001429e  mov     dword ptr [rsp+8C0h+var_848+4], ecx
0x1800142a2  mov     [rsp+8C0h+var_850], rdx
0x1800142a7  jmp     loc_1800143D5
0x1800142ac  test    cs:byte_1800C8404, 8
0x1800142b3  jz      loc_180014403
0x1800142b9  xor     eax, eax
0x1800142bb  lea     rdx, aRegsetvalueexW; "RegSetValueEx(WanEndPoints) failed with"...
0x1800142c2  mov     r8d, ebx
0x1800142c5  mov     word ptr [rbp+7C0h+var_840], ax
0x1800142c9  lea     rcx, [rbp+7C0h+var_840]
0x1800142cd  call    FormatRRASErrorString
0x1800142d2  test    cs:byte_1800C8404, 8
0x1800142d9  jz      loc_180014403
0x1800142df  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800142e3  lea     rcx, [rbp+7C0h+var_840]
0x1800142e7  xor     edx, edx
0x1800142e9  inc     rax
0x1800142ec  cmp     [rcx+rax*2], dx
0x1800142f0  jnz     short loc_1800142E9
0x1800142f2  jmp     loc_1800143C8
0x1800142f7  test    cs:byte_1800C8404, 8
0x1800142fe  jz      loc_180014403
0x180014304  xor     eax, eax
0x180014306  lea     rdx, aRegsetvalueexE; "RegSetValueEx(EnableForRouting) failed "...
0x18001430d  mov     r8d, ebx
0x180014310  mov     word ptr [rbp+7C0h+var_840], ax
0x180014314  lea     rcx, [rbp+7C0h+var_840]
0x180014318  call    FormatRRASErrorString
0x18001431d  test    cs:byte_1800C8404, 8
0x180014324  jz      loc_180014403
0x18001432a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001432e  lea     rcx, [rbp+7C0h+var_840]
0x180014332  xor     edx, edx
0x180014334  inc     rax
0x180014337  cmp     [rcx+rax*2], dx
0x18001433b  jnz     short loc_180014334
0x18001433d  jmp     loc_1800143C8
0x180014342  test    cs:byte_1800C8404, 8
0x180014349  jz      loc_180014403
0x18001434f  xor     eax, eax
0x180014351  lea     rdx, aRegsetvalueexE_0; "RegSetValueEx(EnableForRas) failed with"...
0x180014358  mov     r8d, ebx
0x18001435b  mov     word ptr [rbp+7C0h+var_840], ax
0x18001435f  lea     rcx, [rbp+7C0h+var_840]
0x180014363  call    FormatRRASErrorString
0x180014368  test    cs:byte_1800C8404, 8
0x18001436f  jz      loc_180014403
0x180014375  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014379  lea     rcx, [rbp+7C0h+var_840]
0x18001437d  xor     edx, edx
0x18001437f  inc     rax
0x180014382  cmp     [rcx+rax*2], dx
0x180014386  jnz     short loc_18001437F
0x180014388  jmp     short loc_1800143C8
0x18001438a  test    cs:byte_1800C8404, 8
0x180014391  jz      short loc_180014403
0x180014393  xor     eax, eax
0x180014395  lea     rdx, aLrgetregkeyfro; "lrGetRegKeyFromGuid failed with error 0"...
0x18001439c  mov     r8d, ebx
0x18001439f  mov     word ptr [rbp+7C0h+var_840], ax
0x1800143a3  lea     rcx, [rbp+7C0h+var_840]
0x1800143a7  call    FormatRRASErrorString
0x1800143ac  test    cs:byte_1800C8404, 8
0x1800143b3  jz      short loc_180014403
0x1800143b5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800143b9  lea     rcx, [rbp+7C0h+var_840]
0x1800143bd  xor     edx, edx
0x1800143bf  inc     rax
0x1800143c2  cmp     [rcx+rax*2], dx
0x1800143c6  jnz     short loc_1800143BF
0x1800143c8  lea     rcx, [rbp+7C0h+var_840]
0x1800143cc  mov     dword ptr [rsp+8C0h+var_848+4], edx
0x1800143d0  mov     [rsp+8C0h+var_850], rcx
  ... truncated ...
```
