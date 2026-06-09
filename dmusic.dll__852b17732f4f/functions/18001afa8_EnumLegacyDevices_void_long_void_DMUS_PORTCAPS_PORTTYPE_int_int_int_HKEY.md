# EnumLegacyDevices(void *,long (*)(void *,_DMUS_PORTCAPS &,PORTTYPE,int,int,int,HKEY__ *))

- ea: `0x18001afa8`
- end: `0x18001b323`
- name: `?EnumLegacyDevices@@YAJPEAXP6AJ0AEAU_DMUS_PORTCAPS@@W4PORTTYPE@@HHHPEAUHKEY__@@@Z@Z`
- size: `891`
- prototype: `__int64 __fastcall(void *, int (__high *)(void *, struct _DMUS_PORTCAPS *, enum PORTTYPE, int, int, int, HKEY))`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013ed4`

## callees

- `0x1800016d0`
- `0x1800021a8`
- `0x1800080c8`
- `0x180012dd0`
- `0x18001afa8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringA` at `0x18001b048`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringA` at `0x18001b048`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001b06d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001b116`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001b22a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001b06d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001b116`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001b22a`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyA` at `0x18001b0a1`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyA` at `0x18001b0a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b2eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b2eb`
- `api-ms-win-mm-mme-l1-1-0!midiInGetDevCapsA` at `0x18001b1fd`
- `api-ms-win-mm-mme-l1-1-0!midiInGetDevCapsA` at `0x18001b1fd`
- `api-ms-win-mm-mme-l1-1-0!midiOutGetNumDevs` at `0x18001b0b3`
- `api-ms-win-mm-mme-l1-1-0!midiOutGetNumDevs` at `0x18001b0b3`
- `api-ms-win-mm-mme-l1-1-0!midiOutGetDevCapsA` at `0x18001b0d4`
- `api-ms-win-mm-mme-l1-1-0!midiOutGetDevCapsA` at `0x18001b0d4`
- `api-ms-win-mm-mme-l1-1-0!midiInGetNumDevs` at `0x18001b1de`
- `api-ms-win-mm-mme-l1-1-0!midiInGetNumDevs` at `0x18001b1de`

## pseudocode

```c
__int64 __fastcall EnumLegacyDevices(
        void *a1,
        int (__high *a2)(void *, struct _DMUS_PORTCAPS *, enum PORTTYPE, int, int, int, HKEY))
{
  int v2; // r14d
  int v3; // edi
  signed int NumDevs; // esi
  int i; // ebx
  __int64 v6; // rcx
  CHAR *v7; // r8
  _WORD *v8; // rax
  __int64 v9; // rdx
  _WORD *v10; // rcx
  bool v11; // zf
  int v12; // eax
  int v13; // eax
  signed int v14; // esi
  signed int j; // ebx
  __int64 v16; // rcx
  CHAR *v17; // r8
  _WORD *v18; // rax
  __int64 v19; // rdx
  _WORD *v20; // rcx
  int v21; // eax
  HKEY v23; // [rsp+30h] [rbp-D0h]
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  tagMIDIOUTCAPSA pmoc; // [rsp+48h] [rbp-B8h] BYREF
  tagMIDIINCAPSA pmic; // [rsp+80h] [rbp-80h] BYREF
  int v27; // [rsp+B0h] [rbp-50h] BYREF
  int v28; // [rsp+B4h] [rbp-4Ch]
  __int64 v29; // [rsp+C8h] [rbp-38h]
  int v30; // [rsp+D4h] [rbp-2Ch]
  _BYTE v31[254]; // [rsp+E4h] [rbp-1Ch] BYREF
  __int16 v32; // [rsp+1E2h] [rbp+E2h]
  WCHAR Buffer[128]; // [rsp+1F0h] [rbp+F0h] BYREF

  v2 = (int)a1;
  phkResult = 0;
  memset(&pmoc, 0, sizeof(pmoc));
  memset(&pmic, 0, sizeof(pmic));
  memset_0(&v27, 0, 0x134u);
  if ( !WideCharStr && LoadStringA(g_hModule, 0x3EAu, (LPSTR)Buffer, 128) )
    MultiByteToWideChar(0, 0, (LPCCH)Buffer, -1, &WideCharStr, 128);
  memset_0(&v27, 0, 0x134u);
  v27 = 308;
  v30 = 1;
  if ( RegCreateKeyA(
         HKEY_LOCAL_MACHINE,
         "System\\CurrentControlSet\\Control\\MediaProperties\\PrivateProperties\\Midi\\Ports",
         &phkResult) )
  {
    phkResult = 0;
  }
  v3 = 0;
  NumDevs = midiOutGetNumDevs();
  for ( i = -1; i < NumDevs; ++i )
  {
    if ( !midiOutGetDevCapsA((unsigned int)i, &pmoc, 0x34u) )
    {
      memset_0(Buffer, 0, sizeof(Buffer));
      MultiByteToWideChar(0, 0, pmoc.szPname, -1, Buffer, 128);
      StringCchCatW(Buffer, 0x80u, &WideCharStr);
      v6 = 127;
      v7 = (CHAR *)Buffer;
      v8 = v31;
      v9 = 128;
      do
      {
        if ( !v6 )
          break;
        if ( !*(_WORD *)v7 )
          break;
        *v8 = *(_WORD *)v7;
        v7 += 2;
        ++v8;
        --v6;
        --v9;
      }
      while ( v9 );
      v10 = v8 - 1;
      if ( v9 )
        v10 = v8;
      v11 = pmoc.wTechnology == 1;
      v12 = 256;
      *v10 = 0;
      v32 = 0;
      if ( v11 )
        v12 = 258;
      v29 = 1;
      v28 = v12;
      v13 = AddDeviceCallback(v2, (unsigned int)&v27, 1, i, -1, -1, (__int64)phkResult);
      if ( v13 < 0 )
      {
        if ( v13 == -2147024882 )
          return 2147942414LL;
      }
      else
      {
        ++v3;
      }
    }
  }
  v14 = midiInGetNumDevs();
  for ( j = 0; j < v14; ++j )
  {
    if ( !midiInGetDevCapsA((unsigned int)j, &pmic, 0x2Cu) )
    {
      MultiByteToWideChar(0, 0, pmic.szPname, -1, Buffer, 128);
      StringCchCatW(Buffer, 0x80u, &WideCharStr);
      v16 = 127;
      v17 = (CHAR *)Buffer;
      v18 = v31;
      v19 = 128;
      do
      {
        if ( !v16 )
          break;
        if ( !*(_WORD *)v17 )
          break;
        *v18 = *(_WORD *)v17;
        v17 += 2;
        ++v18;
        --v16;
        --v19;
      }
      while ( v19 );
      v20 = v18 - 1;
      if ( v19 )
        v20 = v18;
      v23 = phkResult;
      *v20 = 0;
      v32 = 0;
      LODWORD(v29) = 0;
      v28 = 2;
      v21 = AddDeviceCallback(v2, (unsigned int)&v27, 1, j, -1, -1, (__int64)v23);
      if ( v21 < 0 )
      {
        if ( v21 == -2147024882 )
          return 2147942414LL;
      }
      else
      {
        ++v3;
      }
    }
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  return v3 == 0;
}

```

## disassembly

```asm
0x18001afa8  push    rbp
0x18001afaa  push    rbx
0x18001afab  push    rsi
0x18001afac  push    rdi
0x18001afad  push    r12
0x18001afaf  push    r13
0x18001afb1  push    r14
0x18001afb3  push    r15
0x18001afb5  lea     rbp, [rsp-208h]
0x18001afbd  sub     rsp, 308h
0x18001afc4  mov     rax, cs:__security_cookie
0x18001afcb  xor     rax, rsp
0x18001afce  mov     [rbp+240h+var_50], rax
0x18001afd5  xorps   xmm1, xmm1
0x18001afd8  xorps   xmm0, xmm0
0x18001afdb  mov     r14, rcx
0x18001afde  xor     eax, eax
0x18001afe0  movups  xmmword ptr [rbp+240h+pmic.szPname+8], xmm1
0x18001afe4  mov     ebx, 134h
0x18001afe9  mov     [rsp+340h+pmoc.dwSupport], eax
0x18001afed  xor     r15d, r15d
0x18001aff0  lea     rcx, [rbp+240h+var_290]; void *
0x18001aff4  mov     r8d, ebx; Size
0x18001aff7  mov     [rsp+340h+phkResult], r15
0x18001affc  xor     edx, edx; Val
0x18001affe  movups  xmmword ptr [rbp+240h+pmic.szPname+14h], xmm1
0x18001b002  movups  xmmword ptr [rsp+340h+pmoc.wMid], xmm0
0x18001b007  movups  xmmword ptr [rsp+340h+pmoc.szPname+8], xmm0
0x18001b00c  movups  xmmword ptr [rsp+340h+pmoc.szPname+18h], xmm0
0x18001b011  movups  xmmword ptr [rbp+240h+pmic.wMid], xmm1
0x18001b015  call    memset_0
0x18001b01a  or      r13d, 0FFFFFFFFh
0x18001b01e  lea     rdi, WideCharStr
0x18001b025  cmp     cs:WideCharStr, r15w
0x18001b02d  jnz     short loc_18001B073
0x18001b02f  mov     rcx, cs:?g_hModule@@3PEAUHINSTANCE__@@EA; hInstance
0x18001b036  lea     r8, [rbp+240h+Buffer]; lpBuffer
0x18001b03d  mov     r9d, 80h; cchBufferMax
0x18001b043  mov     edx, 3EAh; uID
0x18001b048  call    cs:__imp_LoadStringA
0x18001b04e  test    eax, eax
0x18001b050  jz      short loc_18001B073
0x18001b052  mov     [rsp+340h+cchWideChar], 80h; cchWideChar
0x18001b05a  lea     r8, [rbp+240h+Buffer]; lpMultiByteStr
0x18001b061  mov     r9d, r13d; cbMultiByte
0x18001b064  mov     [rsp+340h+lpWideCharStr], rdi; lpWideCharStr
0x18001b069  xor     edx, edx; dwFlags
0x18001b06b  xor     ecx, ecx; CodePage
0x18001b06d  call    cs:__imp_MultiByteToWideChar
0x18001b073  mov     r8, rbx; Size
0x18001b076  lea     rcx, [rbp+240h+var_290]; void *
0x18001b07a  xor     edx, edx; Val
0x18001b07c  call    memset_0
0x18001b081  mov     r12d, 1
0x18001b087  mov     [rbp+240h+var_290], ebx
0x18001b08a  lea     r8, [rsp+340h+phkResult]; phkResult
0x18001b08f  mov     [rbp+240h+var_26C], r12d
0x18001b093  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Med"...
0x18001b09a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001b0a1  call    cs:__imp_RegCreateKeyA
0x18001b0a7  test    eax, eax
0x18001b0a9  jz      short loc_18001B0B0
0x18001b0ab  mov     [rsp+340h+phkResult], r15
0x18001b0b0  mov     edi, r15d
0x18001b0b3  call    cs:__imp_midiOutGetNumDevs
0x18001b0b9  mov     esi, eax
0x18001b0bb  mov     ebx, r13d
0x18001b0be  cmp     eax, r13d
0x18001b0c1  jle     loc_18001B1DE
0x18001b0c7  mov     ecx, ebx; uDeviceID
0x18001b0c9  lea     rdx, [rsp+340h+pmoc]; pmoc
0x18001b0ce  mov     r8d, 34h ; '4'; cbmoc
0x18001b0d4  call    cs:__imp_midiOutGetDevCapsA
0x18001b0da  test    eax, eax
0x18001b0dc  jnz     loc_18001B1D3
0x18001b0e2  xor     edx, edx; Val
0x18001b0e4  lea     rcx, [rbp+240h+Buffer]; void *
0x18001b0eb  mov     r8d, 100h; Size
0x18001b0f1  call    memset_0
0x18001b0f6  lea     rax, [rbp+240h+Buffer]
0x18001b0fd  mov     [rsp+340h+cchWideChar], 80h; cchWideChar
0x18001b105  mov     r9d, r13d; cbMultiByte
0x18001b108  mov     [rsp+340h+lpWideCharStr], rax; lpWideCharStr
0x18001b10d  lea     r8, [rsp+340h+pmoc.szPname]; lpMultiByteStr
0x18001b112  xor     edx, edx; dwFlags
0x18001b114  xor     ecx, ecx; CodePage
0x18001b116  call    cs:__imp_MultiByteToWideChar
0x18001b11c  lea     r8, WideCharStr; unsigned __int16 *
0x18001b123  mov     edx, 80h; unsigned __int64
0x18001b128  lea     rcx, [rbp+240h+Buffer]; unsigned __int16 *
0x18001b12f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001b134  mov     ecx, 7Fh
0x18001b139  lea     r8, [rbp+240h+Buffer]
0x18001b140  lea     rax, [rbp+240h+var_25C]
0x18001b144  lea     edx, [rcx+1]
0x18001b147  test    rcx, rcx
0x18001b14a  jz      short loc_18001B16A
0x18001b14c  movzx   r9d, word ptr [r8]
0x18001b150  test    r9w, r9w
0x18001b154  jz      short loc_18001B16A
0x18001b156  mov     [rax], r9w
0x18001b15a  add     r8, 2
0x18001b15e  add     rax, 2
0x18001b162  sub     rcx, r12
0x18001b165  sub     rdx, r12
0x18001b168  jnz     short loc_18001B147
0x18001b16a  lea     rcx, [rax-2]
0x18001b16e  test    rdx, rdx
0x18001b171  mov     r9d, ebx
0x18001b174  lea     rdx, [rbp+240h+var_290]
0x18001b178  cmovnz  rcx, rax
0x18001b17c  mov     r8d, r12d
0x18001b17f  cmp     [rsp+340h+pmoc.wTechnology], r12w
0x18001b185  mov     eax, 100h
0x18001b18a  mov     [rcx], r15w
0x18001b18e  lea     ecx, [rax+2]
0x18001b191  mov     [rbp+240h+var_15E], r15w
0x18001b199  cmovz   eax, ecx
0x18001b19c  mov     [rbp+240h+var_278], r12
0x18001b1a0  mov     [rbp+240h+var_28C], eax
0x18001b1a3  mov     rcx, r14
0x18001b1a6  mov     rax, [rsp+340h+phkResult]
0x18001b1ab  mov     [rsp+340h+var_310], rax
0x18001b1b0  mov     [rsp+340h+cchWideChar], r13d
0x18001b1b5  mov     dword ptr [rsp+340h+lpWideCharStr], r13d
0x18001b1ba  call    AddDeviceCallback
0x18001b1bf  test    eax, eax
0x18001b1c1  js      short loc_18001B1C8
0x18001b1c3  add     edi, r12d
0x18001b1c6  jmp     short loc_18001B1D3
0x18001b1c8  cmp     eax, 8007000Eh
0x18001b1cd  jz      loc_18001B31C
0x18001b1d3  add     ebx, r12d
0x18001b1d6  cmp     ebx, esi
0x18001b1d8  jl      loc_18001B0C7
0x18001b1de  call    cs:__imp_midiInGetNumDevs
0x18001b1e4  mov     esi, eax
0x18001b1e6  mov     ebx, r15d
0x18001b1e9  test    eax, eax
0x18001b1eb  jle     loc_18001B2E1
0x18001b1f1  mov     ecx, ebx; uDeviceID
0x18001b1f3  lea     rdx, [rbp+240h+pmic]; pmic
0x18001b1f7  mov     r8d, 2Ch ; ','; cbmic
0x18001b1fd  call    cs:__imp_midiInGetDevCapsA
0x18001b203  test    eax, eax
0x18001b205  jnz     loc_18001B2D6
0x18001b20b  lea     rax, [rbp+240h+Buffer]
0x18001b212  mov     [rsp+340h+cchWideChar], 80h; cchWideChar
0x18001b21a  mov     r9d, r13d; cbMultiByte
0x18001b21d  mov     [rsp+340h+lpWideCharStr], rax; lpWideCharStr
0x18001b222  lea     r8, [rbp+240h+pmic.szPname]; lpMultiByteStr
0x18001b226  xor     edx, edx; dwFlags
0x18001b228  xor     ecx, ecx; CodePage
0x18001b22a  call    cs:__imp_MultiByteToWideChar
0x18001b230  lea     r8, WideCharStr; unsigned __int16 *
0x18001b237  mov     edx, 80h; unsigned __int64
0x18001b23c  lea     rcx, [rbp+240h+Buffer]; unsigned __int16 *
0x18001b243  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001b248  mov     ecx, 7Fh
0x18001b24d  lea     r8, [rbp+240h+Buffer]
0x18001b254  lea     rax, [rbp+240h+var_25C]
0x18001b258  lea     edx, [rcx+1]
0x18001b25b  test    rcx, rcx
0x18001b25e  jz      short loc_18001B27E
0x18001b260  movzx   r9d, word ptr [r8]
0x18001b264  test    r9w, r9w
0x18001b268  jz      short loc_18001B27E
0x18001b26a  mov     [rax], r9w
0x18001b26e  add     r8, 2
0x18001b272  add     rax, 2
0x18001b276  sub     rcx, r12
0x18001b279  sub     rdx, r12
0x18001b27c  jnz     short loc_18001B25B
0x18001b27e  test    rdx, rdx
0x18001b281  lea     rcx, [rax-2]
0x18001b285  mov     r9d, ebx
0x18001b288  lea     rdx, [rbp+240h+var_290]
0x18001b28c  cmovnz  rcx, rax
0x18001b290  mov     r8d, r12d
0x18001b293  mov     rax, [rsp+340h+phkResult]
0x18001b298  mov     [rsp+340h+var_310], rax
0x18001b29d  mov     [rsp+340h+cchWideChar], r13d
0x18001b2a2  mov     [rcx], r15w
0x18001b2a6  mov     rcx, r14
0x18001b2a9  mov     [rbp+240h+var_15E], r15w
0x18001b2b1  mov     dword ptr [rbp+240h+var_278], r15d
0x18001b2b5  mov     [rbp+240h+var_28C], 2
0x18001b2bc  mov     dword ptr [rsp+340h+lpWideCharStr], r13d
0x18001b2c1  call    AddDeviceCallback
0x18001b2c6  test    eax, eax
0x18001b2c8  js      short loc_18001B2CF
0x18001b2ca  add     edi, r12d
0x18001b2cd  jmp     short loc_18001B2D6
0x18001b2cf  cmp     eax, 8007000Eh
0x18001b2d4  jz      short loc_18001B31C
0x18001b2d6  add     ebx, r12d
0x18001b2d9  cmp     ebx, esi
0x18001b2db  jl      loc_18001B1F1
0x18001b2e1  mov     rcx, [rsp+340h+phkResult]; hKey
0x18001b2e6  test    rcx, rcx
0x18001b2e9  jz      short loc_18001B2F1
0x18001b2eb  call    cs:__imp_RegCloseKey
0x18001b2f1  test    edi, edi
0x18001b2f3  mov     eax, r15d
0x18001b2f6  setz    al
0x18001b2f9  mov     rcx, [rbp+240h+var_50]
0x18001b300  xor     rcx, rsp; StackCookie
0x18001b303  call    __security_check_cookie
0x18001b308  add     rsp, 308h
0x18001b30f  pop     r15
0x18001b311  pop     r14
0x18001b313  pop     r13
0x18001b315  pop     r12
0x18001b317  pop     rdi
0x18001b318  pop     rsi
0x18001b319  pop     rbx
0x18001b31a  pop     rbp
0x18001b31b  retn
0x18001b31c  mov     eax, 8007000Eh
0x18001b321  jmp     short loc_18001B2F9
```
