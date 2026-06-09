# CacheFontLinkingData(void)

- ea: `0x180026240`
- end: `0x180026634`
- name: `?CacheFontLinkingData@@YAXXZ`
- size: `1012`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001ef8`

## callees

- `0x180009d00`
- `0x18000a090`
- `0x180026240`
- `0x180026640`
- `0x18007ac50`
- `0x18007ba0c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002656c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026600`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002656c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026600`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180026415`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180026415`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800262fa`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800262fa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800262ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800262ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026373`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026373`
- `GDI32!SelectObject` at `0x180026490`
- `GDI32!SelectObject` at `0x180026525`
- `GDI32!SelectObject` at `0x180026490`
- `GDI32!SelectObject` at `0x180026525`
- `GDI32!DeleteObject` at `0x18002652e`
- `GDI32!DeleteObject` at `0x18002652e`
- `ntdll!wcsnlen` at `0x1800265b4`
- `ntdll!wcsnlen` at `0x1800265b4`
- `USER32!ReleaseDC` at `0x18002657c`
- `USER32!ReleaseDC` at `0x18002657c`
- `USER32!GetDC` at `0x180026339`
- `USER32!GetDC` at `0x180026339`
- `win32u!NtGdiGetTextFaceW` at `0x1800264b8`
- `win32u!NtGdiGetTextFaceW` at `0x1800264f2`
- `win32u!NtGdiGetTextFaceW` at `0x1800264b8`
- `win32u!NtGdiGetTextFaceW` at `0x1800264f2`

## string_xrefs

- `0x18002629f`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\FontLink\SystemLink`

## pseudocode

```c
void CacheFontLinkingData(void)
{
  int v0; // r13d
  LSTATUS v1; // r12d
  DWORD v2; // ecx
  signed int v3; // r14d
  HDC DC; // rdi
  signed int v5; // ebx
  _WORD *v6; // rsi
  DWORD v7; // edx
  int v8; // r15d
  WCHAR *v9; // rbx
  DWORD v10; // edx
  void *v11; // rax
  void *v12; // r13
  wchar_t *v13; // rax
  int v14; // ecx
  int v15; // edx
  wchar_t *v16; // rax
  signed __int64 v17; // rbx
  int v18; // ecx
  int v19; // edx
  int v20; // ebx
  int v21; // edx
  DWORD cbMaxValueNameLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cValues; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cchValueName; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  int v26; // [rsp+78h] [rbp-88h]
  DWORD v27; // [rsp+7Ch] [rbp-84h]
  void *v28; // [rsp+80h] [rbp-80h]
  HGDIOBJ h; // [rsp+88h] [rbp-78h]
  __m128i si128; // [rsp+90h] [rbp-70h] BYREF
  int v31; // [rsp+A0h] [rbp-60h]
  int v32; // [rsp+A4h] [rbp-5Ch]
  __int16 v33; // [rsp+A8h] [rbp-58h]
  wchar_t Destination[2]; // [rsp+AAh] [rbp-56h] BYREF
  __int128 v35; // [rsp+AEh] [rbp-52h]
  __int128 v36; // [rsp+BEh] [rbp-42h]
  _BYTE v37[30]; // [rsp+CEh] [rbp-32h] BYREF
  wchar_t Source[40]; // [rsp+F0h] [rbp-10h] BYREF

  v0 = 0;
  hKey = 0;
  cValues = 0;
  cchValueName = 0;
  cbMaxValueNameLen = 0;
  if ( gFontLinkingData != (wchar_t *)-1LL )
    return;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\FontLink\\SystemLink",
         0,
         0x109u,
         &hKey) )
  {
LABEL_44:
    gFontLinkingData = 0;
    return;
  }
  v1 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
  if ( v1 || cValues > 0x64 )
  {
    RegCloseKey(hKey);
    goto LABEL_44;
  }
  v2 = cbMaxValueNameLen;
  if ( cbMaxValueNameLen >= 0x1F )
  {
    v2 = 31;
    cbMaxValueNameLen = 31;
  }
  v3 = cValues * (v2 + 2) + 1;
  DC = GetDC(0);
  if ( DC )
    v5 = 2 * v3 + 66 * cValues;
  else
    v5 = 2 * v3;
  if ( v5 >= 0 && (unsigned int)CheckInitUspMemory() && (v6 = HeapAlloc(ghHeap, 0, v5)) != 0 )
  {
    v7 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v8 = 0;
    v31 = 400;
    memset(v37, 0, sizeof(v37));
    v32 = 0x1000000;
    v33 = 0;
    *(_DWORD *)Destination = 0;
    v35 = 0;
    v36 = 0;
    while ( 1 )
    {
      v27 = v7;
      if ( v1 )
      {
        if ( v1 != 122 )
          break;
      }
      cchValueName = cbMaxValueNameLen + 1;
      v9 = &v6[v8 + 1];
      v1 = RegEnumValueW(hKey, v7, v9, &cchValueName, 0, 0, 0, 0);
      if ( !v1 && cchValueName <= cbMaxValueNameLen )
      {
        v26 = ++v0;
        v6[v8] = cchValueName;
        v10 = v8 + cchValueName + 1;
        v8 = v10 + 1;
        v6[v10] = 0;
        if ( DC )
        {
          wcscpy_s(&Destination[1], 0x20u, v9);
          v11 = (void *)CreateFontIndirectWImpl(&si128);
          v28 = v11;
          v12 = v11;
          if ( v11 )
          {
            h = SelectObject(DC, v11);
            if ( h )
            {
              Source[32] = 0;
              if ( (unsigned int)NtGdiGetTextFaceW(DC, 32, Source, 1) )
              {
                v13 = Source;
                do
                {
                  v14 = *(wchar_t *)((char *)v13 + (char *)v9 - (char *)Source);
                  v15 = *v13 - v14;
                  if ( v15 )
                    break;
                  ++v13;
                }
                while ( v14 );
                if ( !v15 && (unsigned int)NtGdiGetTextFaceW(DC, 32, Source, 0) )
                {
                  v16 = Source;
                  v17 = (char *)v9 - (char *)Source;
                  do
                  {
                    v18 = *(wchar_t *)((char *)v16 + v17);
                    v19 = *v16 - v18;
                    if ( v19 )
                      break;
                    ++v16;
                  }
                  while ( v18 );
                  if ( v19 )
                  {
                    if ( v8 + 1 < v3 )
                    {
                      v20 = wcsnlen(Source, 0x21u);
                      v6[v8] = v20;
                      wcscpy_s(&v6[v8 + 1], v3 - v8 - 1, Source);
                      v21 = v8 + v20 + 1;
                      v8 = v21 + 1;
                      v6[v21] = 0;
                    }
                    v12 = v28;
                  }
                }
              }
              SelectObject(DC, h);
            }
            DeleteObject(v12);
          }
          v0 = v26;
        }
      }
      v7 = v27 + 1;
    }
    v6[v8] = 0;
    if ( !v0 )
    {
      UspFreeMem(v6);
      v6 = 0;
    }
    gFontLinkingData = v6;
  }
  else
  {
    gFontLinkingData = 0;
  }
  RegCloseKey(hKey);
  if ( DC )
    ReleaseDC(0, DC);
}

```

## disassembly

```asm
0x180026240  push    rbp
0x180026242  push    rbx
0x180026243  push    rsi
0x180026244  push    rdi
0x180026245  push    r12
0x180026247  push    r13
0x180026249  push    r14
0x18002624b  push    r15
0x18002624d  lea     rbp, [rsp-58h]
0x180026252  sub     rsp, 158h
0x180026259  mov     rax, cs:__security_cookie
0x180026260  xor     rax, rsp
0x180026263  mov     [rbp+90h+var_50], rax
0x180026267  xor     r13d, r13d
0x18002626a  cmp     cs:?gFontLinkingData@@3PEA_WEA, 0FFFFFFFFFFFFFFFFh; wchar_t * gFontLinkingData
0x180026272  mov     [rsp+190h+hKey], r13
0x180026277  mov     [rsp+190h+cValues], r13d
0x18002627c  mov     [rsp+190h+cchValueName], r13d
0x180026281  mov     [rsp+190h+cbMaxValueNameLen], r13d
0x180026286  jnz     loc_180026582
0x18002628c  lea     rax, [rsp+190h+hKey]
0x180026291  mov     r9d, 109h; samDesired
0x180026297  xor     r8d, r8d; ulOptions
0x18002629a  mov     [rsp+190h+phkResult], rax; phkResult
0x18002629f  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800262a6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800262ad  call    cs:__imp_RegOpenKeyExW
0x1800262b3  test    eax, eax
0x1800262b5  jnz     loc_180026606
0x1800262bb  mov     rcx, [rsp+190h+hKey]; hKey
0x1800262c0  lea     rax, [rsp+190h+cbMaxValueNameLen]
0x1800262c5  mov     [rsp+190h+lpftLastWriteTime], r13; lpftLastWriteTime
0x1800262ca  xor     r9d, r9d; lpReserved
0x1800262cd  mov     [rsp+190h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x1800262d2  xor     r8d, r8d; lpcchClass
0x1800262d5  mov     [rsp+190h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x1800262da  xor     edx, edx; lpClass
0x1800262dc  mov     [rsp+190h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800262e1  lea     rax, [rsp+190h+cValues]
0x1800262e6  mov     [rsp+190h+lpcValues], rax; lpcValues
0x1800262eb  mov     [rsp+190h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x1800262f0  mov     [rsp+190h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x1800262f5  mov     [rsp+190h+phkResult], r13; lpcSubKeys
0x1800262fa  call    cs:__imp_RegQueryInfoKeyW
0x180026300  mov     r12d, eax
0x180026303  test    eax, eax
0x180026305  jnz     loc_1800265FB
0x18002630b  cmp     [rsp+190h+cValues], 64h ; 'd'
0x180026310  ja      loc_1800265FB
0x180026316  mov     ecx, [rsp+190h+cbMaxValueNameLen]
0x18002631a  cmp     ecx, 1Fh
0x18002631d  jb      short loc_180026326
0x18002631f  lea     ecx, [rax+1Fh]
0x180026322  mov     [rsp+190h+cbMaxValueNameLen], ecx
0x180026326  lea     r14d, [rcx+2]
0x18002632a  xor     ecx, ecx; hWnd
0x18002632c  imul    r14d, [rsp+190h+cValues]
0x180026332  inc     r14d
0x180026335  lea     esi, [r14+r14]
0x180026339  call    cs:__imp_GetDC
0x18002633f  mov     rdi, rax
0x180026342  test    rax, rax
0x180026345  jz      loc_18002661E
0x18002634b  imul    ebx, [rsp+190h+cValues], 42h ; 'B'
0x180026350  add     ebx, esi
0x180026352  test    ebx, ebx
0x180026354  js      loc_180026612
0x18002635a  call    ?CheckInitUspMemory@@YAHXZ; CheckInitUspMemory(void)
0x18002635f  test    eax, eax
0x180026361  jz      loc_180026612
0x180026367  mov     rcx, cs:?ghHeap@@3PEAXEA; hHeap
0x18002636e  xor     edx, edx; dwFlags
0x180026370  movsxd  r8, ebx; dwBytes
0x180026373  call    cs:__imp_HeapAlloc
0x180026379  mov     rsi, rax
0x18002637c  test    rax, rax
0x18002637f  jz      loc_180026612
0x180026385  movdqa  xmm0, cs:__xmm@000000000000000000000000fffffff4
0x18002638d  mov     edx, r13d; dwIndex
0x180026390  movdqa  [rbp+90h+var_100], xmm0
0x180026395  mov     r15d, r13d
0x180026398  xorps   xmm0, xmm0
0x18002639b  mov     [rbp+90h+var_F0], 190h
0x1800263a2  movups  xmmword ptr [rbp+90h+var_C2], xmm0
0x1800263a6  mov     [rbp+90h+var_EC], 1000000h
0x1800263ad  movups  xmmword ptr [rbp+90h+var_C2+0Eh], xmm0
0x1800263b1  mov     [rbp+90h+var_E8], r13w
0x1800263b6  mov     dword ptr [rbp+90h+Destination], r13d
0x1800263ba  movups  [rbp+90h+var_E2], xmm0
0x1800263be  movups  [rbp+90h+var_D2], xmm0
0x1800263c2  mov     [rsp+190h+var_114], edx
0x1800263c6  test    r12d, r12d
0x1800263c9  jnz     loc_180026544
0x1800263cf  mov     eax, [rsp+190h+cbMaxValueNameLen]
0x1800263d3  lea     r9, [rsp+190h+cchValueName]; lpcchValueName
0x1800263d8  inc     eax
0x1800263da  mov     [rsp+190h+lpcValues], 0; lpcbData
0x1800263e3  mov     [rsp+190h+cchValueName], eax
0x1800263e7  lea     eax, [r15+1]
0x1800263eb  movsxd  rcx, eax
0x1800263ee  mov     [rsp+190h+lpcbMaxClassLen], 0; lpData
0x1800263f7  mov     [rsp+190h+lpcbMaxSubKeyLen], 0; lpType
0x180026400  mov     [rsp+190h+phkResult], 0; lpReserved
0x180026409  lea     rbx, [rsi+rcx*2]
0x18002640d  mov     rcx, [rsp+190h+hKey]; hKey
0x180026412  mov     r8, rbx; lpValueName
0x180026415  call    cs:__imp_RegEnumValueW
0x18002641b  mov     r12d, eax
0x18002641e  test    eax, eax
0x180026420  jnz     loc_180026539
0x180026426  mov     ecx, [rsp+190h+cchValueName]
0x18002642a  cmp     ecx, [rsp+190h+cbMaxValueNameLen]
0x18002642e  ja      loc_180026539
0x180026434  movsxd  rax, r15d
0x180026437  inc     r13d
0x18002643a  mov     [rsp+190h+var_118], r13d
0x18002643f  mov     [rsi+rax*2], cx
0x180026443  xor     eax, eax
0x180026445  mov     edx, [rsp+190h+cchValueName]
0x180026449  inc     edx
0x18002644b  add     edx, r15d
0x18002644e  movsxd  rcx, edx
0x180026451  lea     r15d, [rdx+1]
0x180026455  mov     [rsi+rcx*2], ax
0x180026459  test    rdi, rdi
0x18002645c  jz      loc_180026539
0x180026462  mov     r8, rbx; Source
0x180026465  lea     edx, [rax+20h]; SizeInWords
0x180026468  lea     rcx, [rbp+90h+Destination+2]; Destination
0x18002646c  call    wcscpy_s
0x180026471  lea     rcx, [rbp+90h+var_100]
0x180026475  call    CreateFontIndirectWImpl
0x18002647a  mov     [rbp+90h+var_110], rax
0x18002647e  mov     r13, rax
0x180026481  test    rax, rax
0x180026484  jz      loc_180026534
0x18002648a  mov     rdx, rax; h
0x18002648d  mov     rcx, rdi; hdc
0x180026490  call    cs:__imp_SelectObject
0x180026496  mov     [rbp+90h+h], rax
0x18002649a  test    rax, rax
0x18002649d  jz      loc_18002652B
0x1800264a3  xor     ecx, ecx
0x1800264a5  lea     r9d, [r12+1]
0x1800264aa  mov     [rbp+90h+var_60], cx
0x1800264ae  lea     r8, [rbp+90h+Source]
0x1800264b2  lea     edx, [rcx+20h]
0x1800264b5  mov     rcx, rdi
0x1800264b8  call    cs:__imp_NtGdiGetTextFaceW
0x1800264be  test    eax, eax
0x1800264c0  jz      short loc_18002651E
0x1800264c2  lea     rax, [rbp+90h+Source]
0x1800264c6  mov     r8, rbx
0x1800264c9  sub     r8, rax
0x1800264cc  movzx   edx, word ptr [rax]
0x1800264cf  movzx   ecx, word ptr [rax+r8]
0x1800264d4  sub     edx, ecx
0x1800264d6  jnz     short loc_1800264E0
0x1800264d8  add     rax, 2
0x1800264dc  test    ecx, ecx
0x1800264de  jnz     short loc_1800264CC
0x1800264e0  test    edx, edx
0x1800264e2  jnz     short loc_18002651E
0x1800264e4  xor     r9d, r9d
0x1800264e7  lea     r8, [rbp+90h+Source]
0x1800264eb  mov     rcx, rdi
0x1800264ee  lea     edx, [r9+20h]
0x1800264f2  call    cs:__imp_NtGdiGetTextFaceW
0x1800264f8  test    eax, eax
0x1800264fa  jz      short loc_18002651E
0x1800264fc  lea     rax, [rbp+90h+Source]
0x180026500  sub     rbx, rax
0x180026503  movzx   edx, word ptr [rax]
0x180026506  movzx   ecx, word ptr [rax+rbx]
0x18002650a  sub     edx, ecx
0x18002650c  jnz     short loc_180026516
0x18002650e  add     rax, 2
0x180026512  test    ecx, ecx
0x180026514  jnz     short loc_180026503
0x180026516  test    edx, edx
0x180026518  jnz     loc_1800265A2
0x18002651e  mov     rdx, [rbp+90h+h]; h
0x180026522  mov     rcx, rdi; hdc
0x180026525  call    cs:__imp_SelectObject
0x18002652b  mov     rcx, r13; ho
0x18002652e  call    cs:__imp_DeleteObject
0x180026534  mov     r13d, [rsp+190h+var_118]
0x180026539  mov     edx, [rsp+190h+var_114]
0x18002653d  inc     edx
0x18002653f  jmp     loc_1800263C2
0x180026544  cmp     r12d, 7Ah ; 'z'
0x180026548  jz      loc_1800263CF
0x18002654e  xor     eax, eax
0x180026550  movsxd  rcx, r15d
0x180026553  mov     [rsi+rcx*2], ax
0x180026557  test    r13d, r13d
0x18002655a  jz      loc_180026625
0x180026560  mov     cs:?gFontLinkingData@@3PEA_WEA, rsi; wchar_t * gFontLinkingData
0x180026567  mov     rcx, [rsp+190h+hKey]; hKey
0x18002656c  call    cs:__imp_RegCloseKey
0x180026572  test    rdi, rdi
0x180026575  jz      short loc_180026582
0x180026577  mov     rdx, rdi; hDC
0x18002657a  xor     ecx, ecx; hWnd
0x18002657c  call    cs:__imp_ReleaseDC
0x180026582  mov     rcx, [rbp+90h+var_50]
0x180026586  xor     rcx, rsp; StackCookie
0x180026589  call    __security_check_cookie
0x18002658e  add     rsp, 158h
0x180026595  pop     r15
0x180026597  pop     r14
0x180026599  pop     r13
0x18002659b  pop     r12
0x18002659d  pop     rdi
0x18002659e  pop     rsi
0x18002659f  pop     rbx
0x1800265a0  pop     rbp
0x1800265a1  retn
0x1800265a2  lea     r13d, [r15+1]
0x1800265a6  cmp     r13d, r14d
0x1800265a9  jge     short loc_1800265F2
0x1800265ab  mov     edx, 21h ; '!'; MaxCount
0x1800265b0  lea     rcx, [rbp+90h+Source]; Source
0x1800265b4  call    cs:__imp_wcsnlen
0x1800265ba  movsxd  rcx, r15d
0x1800265bd  lea     r8, [rbp+90h+Source]; Source
0x1800265c1  mov     rbx, rax
0x1800265c4  mov     [rsi+rcx*2], bx
0x1800265c8  mov     ecx, r14d
0x1800265cb  sub     ecx, r15d
0x1800265ce  dec     ecx
0x1800265d0  movsxd  rdx, ecx; SizeInWords
0x1800265d3  movsxd  rcx, r13d
0x1800265d6  lea     rcx, [rsi+rcx*2]; Destination
0x1800265da  call    wcscpy_s
0x1800265df  lea     edx, [rbx+1]
0x1800265e2  add     edx, r15d
0x1800265e5  movsxd  rcx, edx
0x1800265e8  xor     eax, eax
0x1800265ea  lea     r15d, [rdx+1]
0x1800265ee  mov     [rsi+rcx*2], ax
0x1800265f2  mov     r13, [rbp+90h+var_110]
0x1800265f6  jmp     loc_18002651E
0x1800265fb  mov     rcx, [rsp+190h+hKey]; hKey
0x180026600  call    cs:__imp_RegCloseKey
0x180026606  mov     cs:?gFontLinkingData@@3PEA_WEA, r13; wchar_t * gFontLinkingData
0x18002660d  jmp     loc_180026582
0x180026612  mov     cs:?gFontLinkingData@@3PEA_WEA, r13; wchar_t * gFontLinkingData
0x180026619  jmp     loc_180026567
0x18002661e  mov     ebx, esi
0x180026620  jmp     loc_180026352
0x180026625  mov     rcx, rsi; lpMem
0x180026628  call    UspFreeMem
0x18002662d  xor     esi, esi
0x18002662f  jmp     loc_180026560
```
