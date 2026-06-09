# GetNdproxyVpnPorts(void)

- ea: `0x180029100`
- end: `0x180029894`
- name: `?GetNdproxyVpnPorts@@YAKXZ`
- size: `1940`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800298e4`

## callees

- `0x180007c0c`
- `0x180029100`
- `0x18006e4dc`
- `0x18006e6fc`
- `0x18006edc0`
- `0x1800755b8`
- `0x18008ba58`
- `0x18008cb84`
- `0x18008db88`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800294e7`
- `ADVAPI32!RegCloseKey` at `0x1800294e7`

## string_xrefs

- `0x180029259`: `LineOpen for deviceId(%d) failed with error 0x%x`
- `0x18002980e`: `Device type %d created. MaxPorts=%d, Ras=%d, Routing=%d`

## pseudocode

```c
__int64 GetNdproxyVpnPorts(void)
{
  unsigned int v0; // ebx
  __int64 v1; // r8
  __int64 v2; // rax
  unsigned int v3; // esi
  unsigned int v4; // eax
  int v5; // edx
  __int64 v6; // r8
  __int64 v7; // rax
  unsigned int ID; // eax
  unsigned int *v10; // r8
  int v11; // r9d
  int v12; // edi
  HKEY v13; // rbx
  int v14; // edi
  int v15; // edi
  int v16; // edi
  int v17; // edi
  unsigned int v18; // ebx
  char *v19; // r14
  int *v20; // r15
  char *v21; // r12
  __int64 *v22; // rax
  int *v23; // r13
  int *v24; // rdi
  unsigned int RestrictedPortCount; // eax
  unsigned int v26; // ecx
  int v27; // r9d
  int v28; // eax
  __int128 v29; // xmm0
  int v30; // edx
  int v31; // r8d
  __int128 v32; // xmm1
  int *v33; // rcx
  bool v34; // zf
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  __int128 v39; // xmm0
  __int64 v40; // r8
  __int64 v41; // rax
  DWORD v42; // [rsp+38h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-CCh] BYREF
  int v44; // [rsp+40h] [rbp-C8h] BYREF
  unsigned __int8 v45[4]; // [rsp+44h] [rbp-C4h] BYREF
  unsigned __int8 v46[8]; // [rsp+48h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B8h] BYREF
  unsigned __int8 v48[8]; // [rsp+58h] [rbp-B0h] BYREF
  int *v49; // [rsp+60h] [rbp-A8h]
  char *v50; // [rsp+68h] [rbp-A0h]
  char *v51; // [rsp+70h] [rbp-98h]
  int *v52; // [rsp+78h] [rbp-90h]
  _BYTE v53[16]; // [rsp+80h] [rbp-88h] BYREF
  const wchar_t *v54; // [rsp+90h] [rbp-78h]
  int v55; // [rsp+98h] [rbp-70h]
  int v56; // [rsp+9Ch] [rbp-6Ch]
  _DWORD v57[5]; // [rsp+A8h] [rbp-60h] BYREF
  unsigned int v58; // [rsp+BCh] [rbp-4Ch]
  unsigned __int8 v59[16]; // [rsp+3C8h] [rbp+2C0h] BYREF
  __int128 v60; // [rsp+3D8h] [rbp+2D0h]
  __int128 v61; // [rsp+3E8h] [rbp+2E0h]
  __int128 v62; // [rsp+3F8h] [rbp+2F0h]
  __int128 v63; // [rsp+408h] [rbp+300h]
  __int128 v64; // [rsp+418h] [rbp+310h]
  __int128 v65; // [rsp+428h] [rbp+320h]
  __int128 v66; // [rsp+438h] [rbp+330h]
  unsigned __int8 v67[112]; // [rsp+4D8h] [rbp+3D0h] BYREF
  int v68; // [rsp+548h] [rbp+440h] BYREF
  char v69[2044]; // [rsp+54Ch] [rbp+444h] BYREF

  v0 = 0;
  v44 = 0;
  memset_0(v57, 0, 0x320u);
  Type = 4;
  v42 = 4;
  memset_0(v59, 0, 0x102u);
  *(_DWORD *)v45 = 0;
  *(_DWORD *)v46 = 0;
  memset(v48, 0, sizeof(v48));
  v68 = 0;
  memset_0(v69, 0, sizeof(v69));
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    v2 = -1;
    do
      ++v2;
    while ( aGetndproxyvpnp[v2] );
    v54 = L"GetNdproxyVpnPorts";
    v55 = 2 * v2 + 2;
    v56 = 0;
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v1, 2, v53);
    v0 = v44;
  }
  v3 = 0;
  if ( g_dwNumNDProxyLines )
  {
    while ( 1 )
    {
      if ( v0 )
      {
        RasLineClose(v0);
        v44 = 0;
      }
      v4 = RasLineOpen(v3, 4, 258, v3, (__int64)&v44);
      if ( v4 )
        break;
      v57[0] = 800;
      ID = RasLineGetID(v44, v5, 0, 1, (wchar_t *)L"LineGuid", v57);
      if ( ID )
      {
        if ( (byte_1800CF404 & 8) == 0 )
          goto LABEL_14;
        LOWORD(v68) = 0;
        FormatRRASErrorString(&v68, L"LineGetId for deviceId(%d) failed with error 0x%x", v3, ID);
        if ( (byte_1800CF404 & 8) == 0 )
          goto LABEL_14;
        v7 = -1;
        do
          ++v7;
        while ( *(_WORD *)&v69[2 * v7 - 4] );
LABEL_13:
        v56 = 0;
        v55 = 2 * v7 + 2;
        v54 = (const wchar_t *)&v68;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v6, 2, v53);
        goto LABEL_14;
      }
      hKey = 0;
      *(_OWORD *)v67 = *(_OWORD *)((char *)v57 + v58);
      v12 = *(_DWORD *)((char *)&v57[4] + v58);
      if ( !(unsigned int)lrGetRegKeyFromGuid(v67, &hKey, v10, v11) )
      {
        v13 = hKey;
        *(_DWORD *)v45 = 0;
        Type = 4;
        v42 = 4;
        lrRegQueryValueEx(hKey, L"MaxWanEndpoints", &Type, v45, &v42);
        *(_DWORD *)v46 = 0;
        Type = 4;
        v42 = 4;
        lrRegQueryValueEx(v13, L"WanEndpoints", &Type, v46, &v42);
        *(_DWORD *)v48 = 0;
        Type = 4;
        v42 = 4;
        lrRegQueryValueEx(v13, L"EnableForRas", &Type, v48, &v42);
        *(_DWORD *)&v48[4] = 0;
        Type = 4;
        v42 = 4;
        lrRegQueryValueEx(v13, L"EnableForRouting", &Type, &v48[4], &v42);
        Type = 1;
        v42 = 258;
        memset_0(v59, 0, 0x102u);
        lrRegQueryValueEx(v13, L"DriverDesc", &Type, v59, &v42);
        RegCloseKey(v13);
        v14 = v12 - 8;
        if ( !v14 )
        {
          v18 = 8;
          v49 = &dword_1800CFFF4;
          v19 = (char *)&gblVpnDeviceTable;
          v50 = byte_1800CFFF8;
          v20 = &dword_1800CFFFC;
          v51 = byte_1800D0000;
          v21 = byte_1800D0118;
          v52 = &dword_1800D0124;
          v23 = &dword_1800D011C;
          v22 = qword_1800D0108;
          v24 = &dword_1800D0004;
          goto LABEL_36;
        }
        v15 = v14 - 1;
        if ( !v15 )
        {
          v18 = 9;
          v49 = &dword_1800D012C;
          v19 = byte_1800D0128;
          v50 = byte_1800D0130;
          v20 = &dword_1800D0134;
          v51 = byte_1800D0138;
          v21 = byte_1800D0250;
          v52 = &dword_1800D025C;
          v23 = &dword_1800D0254;
          v22 = qword_1800D0240;
          v24 = &dword_1800D013C;
          goto LABEL_36;
        }
        v16 = v15 - 4;
        if ( !v16 )
        {
          v18 = 14;
          v49 = &dword_1800D0264;
          v19 = byte_1800D0260;
          v50 = byte_1800D0268;
          v20 = &dword_1800D026C;
          v51 = byte_1800D0270;
          v21 = byte_1800D0388;
          v52 = &dword_1800D0394;
          v23 = &dword_1800D038C;
          v22 = qword_1800D0378;
          v24 = &dword_1800D0274;
          goto LABEL_36;
        }
        v17 = v16 - 1;
        if ( !v17 )
        {
          v18 = 15;
          v49 = &dword_1800D039C;
          v19 = byte_1800D0398;
          v50 = byte_1800D03A0;
          v20 = &dword_1800D03A4;
          v51 = byte_1800D03A8;
          v21 = byte_1800D04C0;
          v52 = &dword_1800D04CC;
          v23 = &dword_1800D04C4;
          v22 = qword_1800D04B0;
          v24 = &dword_1800D03AC;
          goto LABEL_36;
        }
        if ( v17 == 1 )
        {
          v49 = &dword_1800D04D4;
          v18 = 16;
          v50 = byte_1800D04D8;
          v19 = byte_1800D04D0;
          v51 = byte_1800D04E0;
          v20 = &dword_1800D04DC;
          v52 = &dword_1800D0604;
          v21 = byte_1800D05F8;
          v22 = (__int64 *)&qword_1800D05E8;
          v23 = &dword_1800D05FC;
          v24 = &dword_1800D04E4;
LABEL_36:
          hKey = (HKEY)v22;
          RestrictedPortCount = GetRestrictedPortCount(v18);
          v26 = *(_DWORD *)v45;
          if ( *(_DWORD *)v45 > RestrictedPortCount )
          {
            v26 = RestrictedPortCount;
            *(_DWORD *)v45 = RestrictedPortCount;
          }
          v27 = *(_DWORD *)v46;
          if ( *(_DWORD *)v46 > v26 )
          {
            v27 = v26;
            *(_DWORD *)v46 = v26;
          }
          g_totalPortCount += v27;
          v28 = v44;
          v29 = *(_OWORD *)v67;
          v30 = *(_DWORD *)v48;
          v31 = *(_DWORD *)&v48[4];
          *(_OWORD *)v24 = *(_OWORD *)v59;
          *v20 = v28;
          v32 = v61;
          *(_DWORD *)v21 = v26;
          v33 = v49;
          *(_DWORD *)v19 = 1;
          *v23 = v27;
          *v33 = v30 != 0;
          v34 = (byte_1800CF404 & 0x10) == 0;
          *(_DWORD *)v50 = v31 != 0;
          *(_DWORD *)v51 = v3;
          *v52 = v18;
          *(_OWORD *)hKey = v29;
          *((_OWORD *)v24 + 1) = v60;
          v35 = v62;
          *((_OWORD *)v24 + 2) = v32;
          v36 = v63;
          *((_OWORD *)v24 + 3) = v35;
          v37 = v64;
          *((_OWORD *)v24 + 4) = v36;
          v38 = v65;
          *((_OWORD *)v24 + 5) = v37;
          v39 = v66;
          *((_OWORD *)v24 + 6) = v38;
          *((_OWORD *)v24 + 7) = v39;
          if ( !v34 )
          {
            LOWORD(v68) = 0;
            FormatRRASErrorString(&v68, L"Device type %d created. MaxPorts=%d, Ras=%d, Routing=%d", v18);
            if ( (byte_1800CF404 & 0x10) != 0 )
            {
              v41 = -1;
              do
                ++v41;
              while ( *(_WORD *)&v69[2 * v41 - 4] );
              v56 = 0;
              v55 = 2 * v41 + 2;
              v54 = (const wchar_t *)&v68;
              McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v40, 2, v53);
            }
          }
          v0 = 0;
          v44 = 0;
          goto LABEL_15;
        }
      }
LABEL_14:
      v0 = v44;
LABEL_15:
      if ( ++v3 >= g_dwNumNDProxyLines )
        goto LABEL_16;
    }
    if ( (byte_1800CF404 & 8) == 0 )
      goto LABEL_14;
    LOWORD(v68) = 0;
    FormatRRASErrorString(&v68, L"LineOpen for deviceId(%d) failed with error 0x%x", v3, v4);
    if ( (byte_1800CF404 & 8) == 0 )
      goto LABEL_14;
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)&v69[2 * v7 - 4] );
    goto LABEL_13;
  }
LABEL_16:
  if ( v0 )
    RasLineClose(v0);
  return 0;
}

```

## disassembly

```asm
0x180029100  mov     rax, rsp
0x180029103  mov     [rax+8], rbx
0x180029107  mov     [rax+10h], rsi
0x18002910b  mov     [rax+18h], rdi
0x18002910f  push    rbp
0x180029110  push    r12
0x180029112  push    r13
0x180029114  push    r14
0x180029116  push    r15
0x180029118  lea     rbp, [rax-0C78h]
0x18002911f  sub     rsp, 0D50h
0x180029126  mov     rax, cs:__security_cookie
0x18002912d  xor     rax, rsp
0x180029130  mov     [rbp+0C70h+var_30], rax
0x180029137  xor     r14d, r14d
0x18002913a  lea     rcx, [rbp+0C70h+var_CD0]; void *
0x18002913e  mov     ebx, r14d
0x180029141  xor     edx, edx; Val
0x180029143  mov     r8d, 320h; Size
0x180029149  mov     [rsp+0D70h+var_D38], ebx
0x18002914d  call    memset_0
0x180029152  lea     r15d, [r14+4]
0x180029156  mov     r12d, 102h
0x18002915c  mov     r8d, r12d; Size
0x18002915f  mov     [rsp+0D70h+Type], r15d
0x180029164  xor     edx, edx; Val
0x180029166  mov     [rsp+0D70h+var_D40], r15d
0x18002916b  lea     rcx, [rbp+0C70h+var_9B0]; void *
0x180029172  call    memset_0
0x180029177  xor     edx, edx; Val
0x180029179  mov     dword ptr [rsp+0D70h+var_D34], r14d
0x18002917e  mov     r8d, 7FCh; Size
0x180029184  mov     dword ptr [rsp+0D70h+var_D30], r14d
0x180029189  lea     rcx, [rbp+0C70h+var_82C]; void *
0x180029190  mov     dword ptr [rsp+0D70h+var_D20], r14d
0x180029195  mov     dword ptr [rsp+0D70h+var_D20+4], r14d
0x18002919a  mov     [rbp+0C70h+var_830], r14d
0x1800291a1  call    memset_0
0x1800291a6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800291aa  test    cs:byte_1800CF404, 10h
0x1800291b1  jz      short loc_180029200
0x1800291b3  lea     rcx, aGetndproxyvpnp; "GetNdproxyVpnPorts"
0x1800291ba  mov     rax, rdi
0x1800291bd  inc     rax
0x1800291c0  cmp     [rcx+rax*2], r14w
0x1800291c5  jnz     short loc_1800291BD
0x1800291c7  lea     eax, ds:2[rax*2]
0x1800291ce  mov     [rbp+0C70h+var_CE8], rcx
0x1800291d2  mov     [rbp+0C70h+var_CE0], eax
0x1800291d5  lea     rdx, RasDdmTraceInfo
0x1800291dc  lea     rax, [rsp+0D70h+var_CF8]
0x1800291e1  mov     [rbp+0C70h+var_CDC], r14d
0x1800291e5  mov     r9d, 2
0x1800291eb  mov     [rsp+0D70h+var_D50], rax
0x1800291f0  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800291f7  call    McGenEventWrite_EventWriteTransfer
0x1800291fc  mov     ebx, [rsp+0D70h+var_D38]
0x180029200  cmp     cs:g_dwNumNDProxyLines, r14d
0x180029207  mov     esi, r14d
0x18002920a  jbe     loc_1800292DE
0x180029210  test    ebx, ebx
0x180029212  jz      short loc_180029220
0x180029214  mov     ecx, ebx
0x180029216  call    RasLineClose
0x18002921b  mov     [rsp+0D70h+var_D38], r14d
0x180029220  lea     rax, [rsp+0D70h+var_D38]
0x180029225  mov     r9d, esi
0x180029228  mov     r8d, r12d
0x18002922b  mov     [rsp+0D70h+var_D50], rax
0x180029230  mov     edx, r15d
0x180029233  mov     ecx, esi
0x180029235  call    RasLineOpen
0x18002923a  test    eax, eax
0x18002923c  jz      loc_18002931C
0x180029242  test    cs:byte_1800CF404, 8
0x180029249  jz      short loc_1800292C5
0x18002924b  mov     r9d, eax
0x18002924e  mov     word ptr [rbp+0C70h+var_830], r14w
0x180029256  mov     r8d, esi
0x180029259  lea     rdx, aLineopenForDev; "LineOpen for deviceId(%d) failed with e"...
0x180029260  lea     rcx, [rbp+0C70h+var_830]
0x180029267  call    FormatRRASErrorString
0x18002926c  test    cs:byte_1800CF404, 8
0x180029273  jz      short loc_1800292C5
0x180029275  lea     rcx, [rbp+0C70h+var_830]
0x18002927c  mov     rax, rdi
0x18002927f  inc     rax
0x180029282  cmp     [rcx+rax*2], r14w
0x180029287  jnz     short loc_18002927F
0x180029289  lea     eax, ds:2[rax*2]
0x180029290  mov     [rbp+0C70h+var_CDC], r14d
0x180029294  lea     rcx, [rbp+0C70h+var_830]
0x18002929b  mov     [rbp+0C70h+var_CE0], eax
0x18002929e  lea     rax, [rsp+0D70h+var_CF8]
0x1800292a3  mov     [rbp+0C70h+var_CE8], rcx
0x1800292a7  mov     r9d, 2
0x1800292ad  mov     [rsp+0D70h+var_D50], rax
0x1800292b2  lea     rdx, RasDdmTraceError
0x1800292b9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800292c0  call    McGenEventWrite_EventWriteTransfer
0x1800292c5  mov     ebx, [rsp+0D70h+var_D38]
0x1800292c9  inc     esi
0x1800292cb  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x1800292d2  cmp     esi, cs:g_dwNumNDProxyLines
0x1800292d8  jb      loc_180029210
0x1800292de  test    ebx, ebx
0x1800292e0  jz      short loc_1800292E9
0x1800292e2  mov     ecx, ebx
0x1800292e4  call    RasLineClose
0x1800292e9  xor     eax, eax
0x1800292eb  mov     rcx, [rbp+0C70h+var_30]
0x1800292f2  xor     rcx, rsp; StackCookie
0x1800292f5  call    __security_check_cookie
0x1800292fa  lea     r11, [rsp+0D70h+var_20]
0x180029302  mov     rbx, [r11+30h]
0x180029306  mov     rsi, [r11+38h]
0x18002930a  mov     rdi, [r11+40h]
0x18002930e  mov     rsp, r11
0x180029311  pop     r15
0x180029313  pop     r14
0x180029315  pop     r13
0x180029317  pop     r12
0x180029319  pop     rbp
0x18002931a  retn
0x18002931c  mov     ecx, [rsp+0D70h+var_D38]; int
0x180029320  lea     rax, [rbp+0C70h+var_CD0]
0x180029324  mov     [rsp+0D70h+var_D48], rax; void *
0x180029329  mov     r9d, 1; int
0x18002932f  lea     rax, aLineguid; "LineGuid"
0x180029336  mov     dword ptr [rbp+0C70h+var_CD0], 320h
0x18002933d  xor     r8d, r8d; int
0x180029340  mov     [rsp+0D70h+var_D50], rax; String1
0x180029345  call    RasLineGetID
0x18002934a  test    eax, eax
0x18002934c  jz      short loc_1800293A2
0x18002934e  test    cs:byte_1800CF404, 8
0x180029355  jz      loc_1800292C5
0x18002935b  mov     r9d, eax
0x18002935e  mov     word ptr [rbp+0C70h+var_830], r14w
0x180029366  mov     r8d, esi
0x180029369  lea     rdx, aLinegetidForDe; "LineGetId for deviceId(%d) failed with "...
0x180029370  lea     rcx, [rbp+0C70h+var_830]
0x180029377  call    FormatRRASErrorString
0x18002937c  test    cs:byte_1800CF404, 8
0x180029383  jz      loc_1800292C5
0x180029389  lea     rcx, [rbp+0C70h+var_830]
0x180029390  mov     rax, rdi
0x180029393  inc     rax
0x180029396  cmp     [rcx+rax*2], r14w
0x18002939b  jnz     short loc_180029393
0x18002939d  jmp     loc_180029289
0x1800293a2  mov     eax, [rbp+0C70h+var_CBC]
0x1800293a5  lea     rdx, [rsp+0D70h+hKey]; HKEY *
0x1800293aa  lea     rcx, [rbp+0C70h+var_8A0]; unsigned __int8 *
0x1800293b1  mov     [rsp+0D70h+hKey], r14
0x1800293b6  movups  xmm0, [rbp+rax+0C70h+var_CD0]
0x1800293bb  movdqu  xmmword ptr [rbp+0C70h+var_8A0], xmm0
0x1800293c3  mov     edi, [rbp+rax+0C70h+var_CC0]
0x1800293c7  call    ?lrGetRegKeyFromGuid@@YAJPEAEPEAPEAUHKEY__@@PEAKH@Z; lrGetRegKeyFromGuid(uchar *,HKEY__ * *,ulong *,int)
0x1800293cc  test    eax, eax
0x1800293ce  jnz     loc_1800292C5
0x1800293d4  mov     rbx, [rsp+0D70h+hKey]
0x1800293d9  lea     rax, [rsp+0D70h+var_D40]
0x1800293de  mov     rcx, rbx; hKey
0x1800293e1  mov     dword ptr [rsp+0D70h+var_D34], r14d
0x1800293e6  lea     r9, [rsp+0D70h+var_D34]; unsigned __int8 *
0x1800293eb  mov     [rsp+0D70h+Type], r15d
0x1800293f0  lea     r8, [rsp+0D70h+Type]; lpType
0x1800293f5  mov     [rsp+0D70h+var_D40], r15d
0x1800293fa  lea     rdx, aMaxwanendpoint_0; "MaxWanEndpoints"
0x180029401  mov     [rsp+0D70h+var_D50], rax; LPDWORD
0x180029406  call    ?lrRegQueryValueEx@@YAJPEAUHKEY__@@PEBGPEAKPEAE2@Z; lrRegQueryValueEx(HKEY__ *,ushort const *,ulong *,uchar *,ulong *)
0x18002940b  lea     rax, [rsp+0D70h+var_D40]
0x180029410  mov     dword ptr [rsp+0D70h+var_D30], r14d
0x180029415  lea     r9, [rsp+0D70h+var_D30]; unsigned __int8 *
0x18002941a  mov     [rsp+0D70h+var_D50], rax; LPDWORD
0x18002941f  lea     r8, [rsp+0D70h+Type]; lpType
0x180029424  mov     [rsp+0D70h+Type], r15d
0x180029429  lea     rdx, aWanendpoints; "WanEndpoints"
0x180029430  mov     [rsp+0D70h+var_D40], r15d
0x180029435  mov     rcx, rbx; hKey
0x180029438  call    ?lrRegQueryValueEx@@YAJPEAUHKEY__@@PEBGPEAKPEAE2@Z; lrRegQueryValueEx(HKEY__ *,ushort const *,ulong *,uchar *,ulong *)
0x18002943d  lea     rax, [rsp+0D70h+var_D40]
0x180029442  mov     dword ptr [rsp+0D70h+var_D20], r14d
0x180029447  lea     r9, [rsp+0D70h+var_D20]; unsigned __int8 *
0x18002944c  mov     [rsp+0D70h+var_D50], rax; LPDWORD
0x180029451  lea     r8, [rsp+0D70h+Type]; lpType
0x180029456  mov     [rsp+0D70h+Type], r15d
0x18002945b  lea     rdx, aEnableforras; "EnableForRas"
0x180029462  mov     [rsp+0D70h+var_D40], r15d
0x180029467  mov     rcx, rbx; hKey
0x18002946a  call    ?lrRegQueryValueEx@@YAJPEAUHKEY__@@PEBGPEAKPEAE2@Z; lrRegQueryValueEx(HKEY__ *,ushort const *,ulong *,uchar *,ulong *)
0x18002946f  lea     rax, [rsp+0D70h+var_D40]
0x180029474  mov     dword ptr [rsp+0D70h+var_D20+4], r14d
0x180029479  lea     r9, [rsp+0D70h+var_D20+4]; unsigned __int8 *
0x18002947e  mov     [rsp+0D70h+var_D50], rax; LPDWORD
0x180029483  lea     r8, [rsp+0D70h+Type]; lpType
0x180029488  mov     [rsp+0D70h+Type], r15d
0x18002948d  lea     rdx, aEnableforrouti; "EnableForRouting"
0x180029494  mov     [rsp+0D70h+var_D40], r15d
0x180029499  mov     rcx, rbx; hKey
0x18002949c  call    ?lrRegQueryValueEx@@YAJPEAUHKEY__@@PEBGPEAKPEAE2@Z; lrRegQueryValueEx(HKEY__ *,ushort const *,ulong *,uchar *,ulong *)
0x1800294a1  mov     r8, r12; Size
0x1800294a4  mov     [rsp+0D70h+Type], 1
0x1800294ac  xor     edx, edx; Val
0x1800294ae  mov     [rsp+0D70h+var_D40], r12d
0x1800294b3  lea     rcx, [rbp+0C70h+var_9B0]; void *
0x1800294ba  call    memset_0
0x1800294bf  lea     rax, [rsp+0D70h+var_D40]
0x1800294c4  mov     rcx, rbx; hKey
0x1800294c7  lea     r9, [rbp+0C70h+var_9B0]; unsigned __int8 *
0x1800294ce  mov     [rsp+0D70h+var_D50], rax; LPDWORD
0x1800294d3  lea     r8, [rsp+0D70h+Type]; lpType
0x1800294d8  lea     rdx, aDriverdesc; "DriverDesc"
0x1800294df  call    ?lrRegQueryValueEx@@YAJPEAUHKEY__@@PEBGPEAKPEAE2@Z; lrRegQueryValueEx(HKEY__ *,ushort const *,ulong *,uchar *,ulong *)
0x1800294e4  mov     rcx, rbx; hKey
0x1800294e7  call    cs:__imp_RegCloseKey
0x1800294ee  nop     dword ptr [rax+rax+00h]
0x1800294f3  sub     edi, 8
0x1800294f6  jz      loc_1800296A7
0x1800294fc  sub     edi, 1
0x1800294ff  jz      loc_180029646
0x180029505  sub     edi, r15d
0x180029508  jz      loc_1800295E2
0x18002950e  sub     edi, 1
0x180029511  jz      short loc_18002957E
0x180029513  cmp     edi, 1
0x180029516  jnz     loc_1800292C5
0x18002951c  lea     rax, dword_1800D04D4
0x180029523  mov     [rsp+0D70h+var_D18], rax
0x180029528  lea     ebx, [rdi+0Fh]
0x18002952b  lea     rax, byte_1800D04D8
0x180029532  mov     [rsp+0D70h+var_D10], rax
0x180029537  lea     r14, byte_1800D04D0
0x18002953e  lea     rax, byte_1800D04E0
0x180029545  mov     [rsp+0D70h+var_D08], rax
0x18002954a  lea     r15, dword_1800D04DC
0x180029551  lea     rax, dword_1800D0604
0x180029558  mov     [rsp+0D70h+var_D00], rax
0x18002955d  lea     r12, byte_1800D05F8
0x180029564  lea     rax, qword_1800D05E8
0x18002956b  lea     r13, dword_1800D05FC
0x180029572  lea     rdi, dword_1800D04E4
0x180029579  jmp     loc_180029706
0x18002957e  lea     rax, dword_1800D039C
0x180029585  mov     ebx, 0Fh
0x18002958a  mov     [rsp+0D70h+var_D18], rax
0x18002958f  lea     r14, byte_1800D0398
0x180029596  lea     rax, byte_1800D03A0
0x18002959d  mov     [rsp+0D70h+var_D10], rax
0x1800295a2  lea     r15, dword_1800D03A4
0x1800295a9  lea     rax, byte_1800D03A8
0x1800295b0  mov     [rsp+0D70h+var_D08], rax
0x1800295b5  lea     r12, byte_1800D04C0
0x1800295bc  lea     rax, dword_1800D04CC
0x1800295c3  mov     [rsp+0D70h+var_D00], rax
0x1800295c8  lea     r13, dword_1800D04C4
0x1800295cf  lea     rax, qword_1800D04B0
0x1800295d6  lea     rdi, dword_1800D03AC
0x1800295dd  jmp     loc_180029706
0x1800295e2  lea     rax, dword_1800D0264
0x1800295e9  mov     ebx, 0Eh
0x1800295ee  mov     [rsp+0D70h+var_D18], rax
0x1800295f3  lea     r14, byte_1800D0260
0x1800295fa  lea     rax, byte_1800D0268
0x180029601  mov     [rsp+0D70h+var_D10], rax
0x180029606  lea     r15, dword_1800D026C
0x18002960d  lea     rax, byte_1800D0270
0x180029614  mov     [rsp+0D70h+var_D08], rax
0x180029619  lea     r12, byte_1800D0388
0x180029620  lea     rax, dword_1800D0394
0x180029627  mov     [rsp+0D70h+var_D00], rax
0x18002962c  lea     r13, dword_1800D038C
0x180029633  lea     rax, qword_1800D0378
0x18002963a  lea     rdi, dword_1800D0274
0x180029641  jmp     loc_180029706
0x180029646  lea     rax, dword_1800D012C
0x18002964d  mov     ebx, 9
0x180029652  mov     [rsp+0D70h+var_D18], rax
0x180029657  lea     r14, byte_1800D0128
0x18002965e  lea     rax, byte_1800D0130
0x180029665  mov     [rsp+0D70h+var_D10], rax
0x18002966a  lea     r15, dword_1800D0134
0x180029671  lea     rax, byte_1800D0138
0x180029678  mov     [rsp+0D70h+var_D08], rax
0x18002967d  lea     r12, byte_1800D0250
0x180029684  lea     rax, dword_1800D025C
0x18002968b  mov     [rsp+0D70h+var_D00], rax
0x180029690  lea     r13, dword_1800D0254
0x180029697  lea     rax, qword_1800D0240
0x18002969e  lea     rdi, dword_1800D013C
0x1800296a5  jmp     short loc_180029706
0x1800296a7  lea     rax, dword_1800CFFF4
0x1800296ae  mov     ebx, 8
0x1800296b3  mov     [rsp+0D70h+var_D18], rax
0x1800296b8  lea     r14, ?gblVpnDeviceTable@@3PAU_VPN_DEVICE@@A; _VPN_DEVICE near * gblVpnDeviceTable
0x1800296bf  lea     rax, byte_1800CFFF8
0x1800296c6  mov     [rsp+0D70h+var_D10], rax
0x1800296cb  lea     r15, dword_1800CFFFC
0x1800296d2  lea     rax, byte_1800D0000
  ... truncated ...
```
