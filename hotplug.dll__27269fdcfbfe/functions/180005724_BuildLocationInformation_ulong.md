# BuildLocationInformation(ulong)

- ea: `0x180005724`
- end: `0x180005b26`
- name: `?BuildLocationInformation@@YAPEAGK@Z`
- size: `1026`
- prototype: `unsigned __int16 *__fastcall(DEVINST dnDevInst)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000312c`

## callees

- `0x180003048`
- `0x180005610`
- `0x180005724`
- `0x180006004`
- `0x180008760`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180005af6`
- `KERNEL32!LocalFree` at `0x180005af6`
- `KERNEL32!LocalAlloc` at `0x180005a2b`
- `KERNEL32!LocalAlloc` at `0x180005acc`
- `KERNEL32!LocalAlloc` at `0x180005a2b`
- `KERNEL32!LocalAlloc` at `0x180005acc`
- `ADVAPI32!RegQueryValueExW` at `0x1800057cc`
- `ADVAPI32!RegQueryValueExW` at `0x1800057cc`
- `ADVAPI32!RegCloseKey` at `0x1800057e1`
- `ADVAPI32!RegCloseKey` at `0x1800057e1`
- `USER32!LoadStringW` at `0x1800058f3`
- `USER32!LoadStringW` at `0x18000591b`
- `USER32!LoadStringW` at `0x1800059f8`
- `USER32!LoadStringW` at `0x180005aa2`
- `USER32!LoadStringW` at `0x1800058f3`
- `USER32!LoadStringW` at `0x18000591b`
- `USER32!LoadStringW` at `0x1800059f8`
- `USER32!LoadStringW` at `0x180005aa2`
- `CFGMGR32!CM_Get_Parent_Ex` at `0x180005894`
- `CFGMGR32!CM_Get_Parent_Ex` at `0x180005a6a`
- `CFGMGR32!CM_Get_Parent_Ex` at `0x180005894`
- `CFGMGR32!CM_Get_Parent_Ex` at `0x180005a6a`
- `CFGMGR32!CM_Open_DevNode_Key_Ex` at `0x18000579a`
- `CFGMGR32!CM_Open_DevNode_Key_Ex` at `0x18000579a`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x180005819`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x18000585e`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x1800058c9`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x180005819`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x18000585e`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x1800058c9`

## pseudocode

```c
unsigned __int16 *__fastcall BuildLocationInformation(DEVINST dnDevInst)
{
  unsigned __int16 *v2; // rdi
  __int64 v3; // rdx
  WCHAR *v4; // rax
  __int64 v5; // r8
  __int64 v6; // rcx
  WCHAR *v7; // rax
  WCHAR *v8; // rdx
  __int64 v9; // rbx
  WCHAR *v10; // rcx
  __int64 v11; // rax
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // rsi
  __int64 v14; // rax
  unsigned __int16 *v15; // rax
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DEVNODE pdnDevInst; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int Buffer; // [rsp+48h] [rbp-B8h] BYREF
  DWORD Type; // [rsp+4Ch] [rbp-B4h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v23; // [rsp+266h] [rbp+166h]
  WCHAR Source[264]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR v25[264]; // [rsp+480h] [rbp+380h] BYREF

  cbData = 520;
  Buffer = 0;
  pdnDevInst = 0;
  hKey = 0;
  Type = 1;
  *(_WORD *)Data = 0;
  if ( !CM_Open_DevNode_Key_Ex(dnDevInst, 0x20019u, 0, 1u, &hKey, 1u, 0) )
  {
    if ( RegQueryValueExW(hKey, L"LocationInformationOverride", 0, &Type, Data, &cbData) )
      *(_WORD *)Data = 0;
    RegCloseKey(hKey);
  }
  if ( !*(_WORD *)Data )
  {
    cbData = 520;
    if ( CM_Get_DevNode_Registry_Property_ExW(dnDevInst, 0xEu, 0, Data, &cbData, 0, 0) )
      *(_WORD *)Data = 0;
    v23 = 0;
  }
  cbData = 4;
  v2 = 0;
  if ( CM_Get_DevNode_Registry_Property_ExW(dnDevInst, 0x11u, 0, &Buffer, &cbData, 0, 0) || cbData != 4 )
  {
    if ( *(_WORD *)Data )
    {
      if ( LoadStringW(hHotPlug, 0x3EEu, Source, 260) )
      {
        v11 = -1;
        do
          ++v11;
        while ( *(_WORD *)&Data[2 * v11] );
        cbData = 2 * v11 + 522;
        v12 = (unsigned __int16 *)LocalAlloc(0x40u, cbData);
        v2 = v12;
        if ( v12 )
          StringCchPrintfW(v12, (unsigned __int64)cbData >> 1, Source, Data);
      }
    }
    else if ( !CM_Get_Parent_Ex(&pdnDevInst, dnDevInst, 0, 0) )
    {
      v13 = BuildFriendlyName(pdnDevInst);
      if ( v13 )
      {
        if ( LoadStringW(hHotPlug, 0x3F1u, Source, 260) )
        {
          v14 = -1;
          do
            ++v14;
          while ( v13[v14] );
          cbData = 2 * v14 + 522;
          v15 = (unsigned __int16 *)LocalAlloc(0x40u, cbData);
          v2 = v15;
          if ( v15 )
            StringCchPrintfW(v15, (unsigned __int64)cbData >> 1, Source, v13);
        }
        LocalFree(v13);
      }
    }
  }
  else
  {
    v25[0] = 0;
    cbData = 520;
    if ( (CM_Get_Parent_Ex(&pdnDevInst, dnDevInst, 0, 0)
       || CM_Get_DevNode_Registry_Property_ExW(pdnDevInst, 0x1Eu, 0, v25, &cbData, 0, 0)
       || !v25[0])
      && !LoadStringW(hHotPlug, 0x3F3u, v25, 260) )
    {
      v25[0] = 0;
    }
    if ( LoadStringW(hHotPlug, 0x3F4u, Source, 260) && v25[0] )
    {
      v3 = 260;
      v4 = Source;
      do
      {
        if ( !*v4 )
          break;
        ++v4;
        --v3;
      }
      while ( v3 );
      v5 = (260 - v3) & -(__int64)(v3 != 0);
      if ( v3 )
      {
        v6 = 2147483646;
        v7 = &Source[v5];
        v8 = v25;
        v9 = 260 - v5;
        if ( 260 != v5 )
        {
          do
          {
            if ( !v6 )
              break;
            if ( !*v8 )
              break;
            *v7++ = *v8++;
            --v6;
            --v9;
          }
          while ( v9 );
        }
        v10 = v7 - 1;
        if ( v9 )
          v10 = v7;
        *v10 = 0;
        if ( v9 )
          return FormatString(Source, Buffer);
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180005724  mov     [rsp-8+arg_8], rbx
0x180005729  mov     [rsp-8+arg_10], rsi
0x18000572e  push    rbp
0x18000572f  push    rdi
0x180005730  push    r14
0x180005732  lea     rbp, [rsp-5A0h]
0x18000573a  sub     rsp, 6A0h
0x180005741  mov     rax, cs:__security_cookie
0x180005748  xor     rax, rsp
0x18000574b  mov     [rbp+5B0h+var_20], rax
0x180005752  xor     r14d, r14d
0x180005755  mov     [rsp+6B0h+cbData], 208h
0x18000575d  mov     [rsp+6B0h+hMachine], r14; hMachine
0x180005762  lea     rax, [rsp+6B0h+hKey]
0x180005767  xor     r8d, r8d; ulHardwareProfile
0x18000576a  mov     [rsp+6B0h+Buffer], r14d
0x18000576f  mov     edx, 20019h; samDesired
0x180005774  mov     [rsp+6B0h+pdnDevInst], r14d
0x180005779  lea     esi, [r14+1]
0x18000577d  mov     [rsp+6B0h+hKey], r14
0x180005782  mov     [rsp+6B0h+ulFlags], esi; ulFlags
0x180005786  mov     r9d, esi; Disposition
0x180005789  mov     [rsp+6B0h+phkDevice], rax; phkDevice
0x18000578e  mov     ebx, ecx
0x180005790  mov     [rsp+6B0h+Type], esi
0x180005794  mov     word ptr [rsp+6B0h+Data], r14w
0x18000579a  call    cs:__imp_CM_Open_DevNode_Key_Ex
0x1800057a0  test    eax, eax
0x1800057a2  jnz     short loc_1800057E7
0x1800057a4  mov     rcx, [rsp+6B0h+hKey]; hKey
0x1800057a9  lea     rax, [rsp+6B0h+cbData]
0x1800057ae  mov     qword ptr [rsp+6B0h+ulFlags], rax; lpcbData
0x1800057b3  lea     r9, [rsp+6B0h+Type]; lpType
0x1800057b8  lea     rax, [rsp+6B0h+Data]
0x1800057bd  xor     r8d, r8d; lpReserved
0x1800057c0  lea     rdx, ValueName; "LocationInformationOverride"
0x1800057c7  mov     [rsp+6B0h+phkDevice], rax; lpData
0x1800057cc  call    cs:__imp_RegQueryValueExW
0x1800057d2  test    eax, eax
0x1800057d4  jz      short loc_1800057DC
0x1800057d6  mov     word ptr [rsp+6B0h+Data], r14w
0x1800057dc  mov     rcx, [rsp+6B0h+hKey]; hKey
0x1800057e1  call    cs:__imp_RegCloseKey
0x1800057e7  cmp     word ptr [rsp+6B0h+Data], r14w
0x1800057ed  jnz     short loc_180005831
0x1800057ef  xor     r8d, r8d; pulRegDataType
0x1800057f2  mov     [rsp+6B0h+hMachine], r14; hMachine
0x1800057f7  lea     rax, [rsp+6B0h+cbData]
0x1800057fc  mov     [rsp+6B0h+ulFlags], r14d; ulFlags
0x180005801  lea     r9, [rsp+6B0h+Data]; Buffer
0x180005806  mov     [rsp+6B0h+cbData], 208h
0x18000580e  mov     ecx, ebx; dnDevInst
0x180005810  mov     [rsp+6B0h+phkDevice], rax; pulLength
0x180005815  lea     edx, [r8+0Eh]; ulProperty
0x180005819  call    cs:__imp_CM_Get_DevNode_Registry_Property_ExW
0x18000581f  test    eax, eax
0x180005821  jz      short loc_180005829
0x180005823  mov     word ptr [rsp+6B0h+Data], r14w
0x180005829  mov     [rbp+5B0h+var_44A], r14w
0x180005831  xor     r8d, r8d; pulRegDataType
0x180005834  mov     [rsp+6B0h+hMachine], r14; hMachine
0x180005839  lea     rax, [rsp+6B0h+cbData]
0x18000583e  mov     [rsp+6B0h+ulFlags], r14d; ulFlags
0x180005843  lea     r9, [rsp+6B0h+Buffer]; Buffer
0x180005848  mov     [rsp+6B0h+cbData], 4
0x180005850  mov     ecx, ebx; dnDevInst
0x180005852  mov     [rsp+6B0h+phkDevice], rax; pulLength
0x180005857  lea     edx, [r8+11h]; ulProperty
0x18000585b  mov     rdi, r14
0x18000585e  call    cs:__imp_CM_Get_DevNode_Registry_Property_ExW
0x180005864  test    eax, eax
0x180005866  jnz     loc_1800059D7
0x18000586c  cmp     [rsp+6B0h+cbData], 4
0x180005871  jnz     loc_1800059D7
0x180005877  xor     r9d, r9d; hMachine
0x18000587a  mov     [rbp+5B0h+var_230], r14w
0x180005882  xor     r8d, r8d; ulFlags
0x180005885  mov     [rsp+6B0h+cbData], 208h
0x18000588d  mov     edx, ebx; dnDevInst
0x18000588f  lea     rcx, [rsp+6B0h+pdnDevInst]; pdnDevInst
0x180005894  call    cs:__imp_CM_Get_Parent_Ex
0x18000589a  mov     ebx, 104h
0x18000589f  test    eax, eax
0x1800058a1  jnz     short loc_1800058DD
0x1800058a3  mov     ecx, [rsp+6B0h+pdnDevInst]; dnDevInst
0x1800058a7  lea     rax, [rsp+6B0h+cbData]
0x1800058ac  xor     r8d, r8d; pulRegDataType
0x1800058af  mov     [rsp+6B0h+hMachine], r14; hMachine
0x1800058b4  mov     [rsp+6B0h+ulFlags], r14d; ulFlags
0x1800058b9  lea     r9, [rbp+5B0h+var_230]; Buffer
0x1800058c0  mov     [rsp+6B0h+phkDevice], rax; pulLength
0x1800058c5  lea     edx, [r8+1Eh]; ulProperty
0x1800058c9  call    cs:__imp_CM_Get_DevNode_Registry_Property_ExW
0x1800058cf  test    eax, eax
0x1800058d1  jnz     short loc_1800058DD
0x1800058d3  cmp     [rbp+5B0h+var_230], r14w
0x1800058db  jnz     short loc_180005905
0x1800058dd  mov     rcx, cs:?hHotPlug@@3PEAUHINSTANCE__@@EA; hInstance
0x1800058e4  lea     r8, [rbp+5B0h+var_230]; lpBuffer
0x1800058eb  mov     r9d, ebx; cchBufferMax
0x1800058ee  mov     edx, 3F3h; uID
0x1800058f3  call    cs:__imp_LoadStringW
0x1800058f9  test    eax, eax
0x1800058fb  jnz     short loc_180005905
0x1800058fd  mov     [rbp+5B0h+var_230], r14w
0x180005905  mov     rcx, cs:?hHotPlug@@3PEAUHINSTANCE__@@EA; hInstance
0x18000590c  lea     r8, [rbp+5B0h+Source]; lpBuffer
0x180005913  mov     r9d, ebx; cchBufferMax
0x180005916  mov     edx, 3F4h; uID
0x18000591b  call    cs:__imp_LoadStringW
0x180005921  test    eax, eax
0x180005923  jz      loc_180005AFC
0x180005929  cmp     [rbp+5B0h+var_230], r14w
0x180005931  jz      loc_180005AFC
0x180005937  mov     rdx, rbx
0x18000593a  lea     rax, [rbp+5B0h+Source]
0x180005941  cmp     [rax], r14w
0x180005945  jz      short loc_180005950
0x180005947  add     rax, 2
0x18000594b  sub     rdx, rsi
0x18000594e  jnz     short loc_180005941
0x180005950  mov     rcx, rbx
0x180005953  mov     rax, rdx
0x180005956  sub     rcx, rdx
0x180005959  neg     rax
0x18000595c  sbb     r8, r8
0x18000595f  and     r8, rcx
0x180005962  test    rdx, rdx
0x180005965  jz      loc_180005AFC
0x18000596b  lea     rax, [rbp+5B0h+Source]
0x180005972  mov     ecx, 7FFFFFFEh
0x180005977  lea     rax, [rax+r8*2]
0x18000597b  lea     rdx, [rbp+5B0h+var_230]
0x180005982  sub     rbx, r8
0x180005985  jz      short loc_1800059AA
0x180005987  test    rcx, rcx
0x18000598a  jz      short loc_1800059AA
0x18000598c  movzx   r8d, word ptr [rdx]
0x180005990  test    r8w, r8w
0x180005994  jz      short loc_1800059AA
0x180005996  mov     [rax], r8w
0x18000599a  add     rdx, 2
0x18000599e  add     rax, 2
0x1800059a2  sub     rcx, rsi
0x1800059a5  sub     rbx, rsi
0x1800059a8  jnz     short loc_180005987
0x1800059aa  test    rbx, rbx
0x1800059ad  lea     rcx, [rax-2]
0x1800059b1  cmovnz  rcx, rax
0x1800059b5  mov     [rcx], r14w
0x1800059b9  jz      loc_180005AFC
0x1800059bf  mov     edx, [rsp+6B0h+Buffer]
0x1800059c3  lea     rcx, [rbp+5B0h+Source]; lpSource
0x1800059ca  call    ?FormatString@@YAPEAGPEBGZZ; FormatString(ushort const *,...)
0x1800059cf  mov     rdi, rax
0x1800059d2  jmp     loc_180005AFC
0x1800059d7  cmp     word ptr [rsp+6B0h+Data], r14w
0x1800059dd  jz      short loc_180005A5D
0x1800059df  mov     rcx, cs:?hHotPlug@@3PEAUHINSTANCE__@@EA; hInstance
0x1800059e6  lea     r8, [rbp+5B0h+Source]; lpBuffer
0x1800059ed  mov     r9d, 104h; cchBufferMax
0x1800059f3  mov     edx, 3EEh; uID
0x1800059f8  call    cs:__imp_LoadStringW
0x1800059fe  test    eax, eax
0x180005a00  jz      loc_180005AFC
0x180005a06  lea     rcx, [rsp+6B0h+Data]
0x180005a0b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005a0f  inc     rax
0x180005a12  cmp     [rcx+rax*2], r14w
0x180005a17  jnz     short loc_180005A0F
0x180005a19  lea     eax, ds:20Ah[rax*2]
0x180005a20  mov     ecx, 40h ; '@'; uFlags
0x180005a25  mov     edx, eax; uBytes
0x180005a27  mov     [rsp+6B0h+cbData], eax
0x180005a2b  call    cs:__imp_LocalAlloc
0x180005a31  mov     rdi, rax
0x180005a34  test    rax, rax
0x180005a37  jz      loc_180005AFC
0x180005a3d  mov     edx, [rsp+6B0h+cbData]
0x180005a41  lea     r9, [rsp+6B0h+Data]
0x180005a46  shr     rdx, 1; unsigned __int64
0x180005a49  lea     r8, [rbp+5B0h+Source]; unsigned __int16 *
0x180005a50  mov     rcx, rax; unsigned __int16 *
0x180005a53  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005a58  jmp     loc_180005AFC
0x180005a5d  xor     r9d, r9d; hMachine
0x180005a60  lea     rcx, [rsp+6B0h+pdnDevInst]; pdnDevInst
0x180005a65  xor     r8d, r8d; ulFlags
0x180005a68  mov     edx, ebx; dnDevInst
0x180005a6a  call    cs:__imp_CM_Get_Parent_Ex
0x180005a70  test    eax, eax
0x180005a72  jnz     loc_180005AFC
0x180005a78  mov     ecx, [rsp+6B0h+pdnDevInst]; dnDevInst
0x180005a7c  call    ?BuildFriendlyName@@YAPEAGK@Z; BuildFriendlyName(ulong)
0x180005a81  mov     rsi, rax
0x180005a84  test    rax, rax
0x180005a87  jz      short loc_180005AFC
0x180005a89  mov     rcx, cs:?hHotPlug@@3PEAUHINSTANCE__@@EA; hInstance
0x180005a90  lea     r8, [rbp+5B0h+Source]; lpBuffer
0x180005a97  mov     r9d, 104h; cchBufferMax
0x180005a9d  mov     edx, 3F1h; uID
0x180005aa2  call    cs:__imp_LoadStringW
0x180005aa8  test    eax, eax
0x180005aaa  jz      short loc_180005AF3
0x180005aac  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005ab0  inc     rax
0x180005ab3  cmp     [rsi+rax*2], r14w
0x180005ab8  jnz     short loc_180005AB0
0x180005aba  lea     eax, ds:20Ah[rax*2]
0x180005ac1  mov     ecx, 40h ; '@'; uFlags
0x180005ac6  mov     edx, eax; uBytes
0x180005ac8  mov     [rsp+6B0h+cbData], eax
0x180005acc  call    cs:__imp_LocalAlloc
0x180005ad2  mov     rdi, rax
0x180005ad5  test    rax, rax
0x180005ad8  jz      short loc_180005AF3
0x180005ada  mov     edx, [rsp+6B0h+cbData]
0x180005ade  lea     r8, [rbp+5B0h+Source]; unsigned __int16 *
0x180005ae5  shr     rdx, 1; unsigned __int64
0x180005ae8  mov     r9, rsi
0x180005aeb  mov     rcx, rax; unsigned __int16 *
0x180005aee  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005af3  mov     rcx, rsi; hMem
0x180005af6  call    cs:__imp_LocalFree
0x180005afc  mov     rax, rdi
0x180005aff  mov     rcx, [rbp+5B0h+var_20]
0x180005b06  xor     rcx, rsp; StackCookie
0x180005b09  call    __security_check_cookie
0x180005b0e  lea     r11, [rsp+6B0h+var_10]
0x180005b16  mov     rbx, [r11+28h]
0x180005b1a  mov     rsi, [r11+30h]
0x180005b1e  mov     rsp, r11
0x180005b21  pop     r14
0x180005b23  pop     rdi
0x180005b24  pop     rbp
0x180005b25  retn
```
