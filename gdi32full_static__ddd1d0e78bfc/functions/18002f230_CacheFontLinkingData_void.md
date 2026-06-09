# CacheFontLinkingData(void)

- ea: `0x18002f230`
- end: `0x18002f679`
- name: `?CacheFontLinkingData@@YAXXZ`
- size: `1097`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180052b50`

## callees

- `0x18000d040`
- `0x18000d410`
- `0x18002f230`
- `0x18002f680`
- `0x18007f800`
- `0x1800805ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f598`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f63f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f598`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f63f`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002f41d`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002f41d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002f2f0`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002f2f0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f29d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f29d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002f375`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002f375`
- `GDI32!SelectObject` at `0x18002f49e`
- `GDI32!SelectObject` at `0x18002f545`
- `GDI32!SelectObject` at `0x18002f49e`
- `GDI32!SelectObject` at `0x18002f545`
- `GDI32!DeleteObject` at `0x18002f554`
- `GDI32!DeleteObject` at `0x18002f554`
- `ntdll!wcsnlen` at `0x18002f5ed`
- `ntdll!wcsnlen` at `0x18002f5ed`
- `USER32!ReleaseDC` at `0x18002f5ae`
- `USER32!ReleaseDC` at `0x18002f5ae`
- `USER32!GetDC` at `0x18002f335`
- `USER32!GetDC` at `0x18002f335`
- `win32u!NtGdiGetTextFaceW` at `0x18002f4cc`
- `win32u!NtGdiGetTextFaceW` at `0x18002f50c`
- `win32u!NtGdiGetTextFaceW` at `0x18002f4cc`
- `win32u!NtGdiGetTextFaceW` at `0x18002f50c`

## string_xrefs

- `0x18002f28f`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\FontLink\SystemLink`

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
              if ( (unsigned int)NtGdiGetTextFaceW(DC, 32, Source) )
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
                if ( !v15 && (unsigned int)NtGdiGetTextFaceW(DC, 32, Source) )
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
0x18002f230  push    rbp
0x18002f232  push    rbx
0x18002f233  push    rsi
0x18002f234  push    rdi
0x18002f235  push    r12
0x18002f237  push    r13
0x18002f239  push    r14
0x18002f23b  push    r15
0x18002f23d  lea     rbp, [rsp-58h]
0x18002f242  sub     rsp, 158h
0x18002f249  mov     rax, cs:__security_cookie
0x18002f250  xor     rax, rsp
0x18002f253  mov     [rbp+90h+var_50], rax
0x18002f257  xor     r13d, r13d
0x18002f25a  cmp     cs:?gFontLinkingData@@3PEA_WEA, 0FFFFFFFFFFFFFFFFh; wchar_t * gFontLinkingData
0x18002f262  mov     [rsp+190h+hKey], r13
0x18002f267  mov     [rsp+190h+cValues], r13d
0x18002f26c  mov     [rsp+190h+cchValueName], r13d
0x18002f271  mov     [rsp+190h+cbMaxValueNameLen], r13d
0x18002f276  jnz     loc_18002F5BA
0x18002f27c  lea     rax, [rsp+190h+hKey]
0x18002f281  mov     r9d, 109h; samDesired
0x18002f287  xor     r8d, r8d; ulOptions
0x18002f28a  mov     [rsp+190h+phkResult], rax; phkResult
0x18002f28f  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002f296  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002f29d  call    cs:__imp_RegOpenKeyExW
0x18002f2a4  nop     dword ptr [rax+rax+00h]
0x18002f2a9  test    eax, eax
0x18002f2ab  jnz     loc_18002F64B
0x18002f2b1  mov     rcx, [rsp+190h+hKey]; hKey
0x18002f2b6  lea     rax, [rsp+190h+cbMaxValueNameLen]
0x18002f2bb  mov     [rsp+190h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18002f2c0  xor     r9d, r9d; lpReserved
0x18002f2c3  mov     [rsp+190h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18002f2c8  xor     r8d, r8d; lpcchClass
0x18002f2cb  mov     [rsp+190h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18002f2d0  xor     edx, edx; lpClass
0x18002f2d2  mov     [rsp+190h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18002f2d7  lea     rax, [rsp+190h+cValues]
0x18002f2dc  mov     [rsp+190h+lpcValues], rax; lpcValues
0x18002f2e1  mov     [rsp+190h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18002f2e6  mov     [rsp+190h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x18002f2eb  mov     [rsp+190h+phkResult], r13; lpcSubKeys
0x18002f2f0  call    cs:__imp_RegQueryInfoKeyW
0x18002f2f7  nop     dword ptr [rax+rax+00h]
0x18002f2fc  mov     r12d, eax
0x18002f2ff  test    eax, eax
0x18002f301  jnz     loc_18002F63A
0x18002f307  cmp     [rsp+190h+cValues], 64h ; 'd'
0x18002f30c  ja      loc_18002F63A
0x18002f312  mov     ecx, [rsp+190h+cbMaxValueNameLen]
0x18002f316  cmp     ecx, 1Fh
0x18002f319  jb      short loc_18002F322
0x18002f31b  lea     ecx, [rax+1Fh]
0x18002f31e  mov     [rsp+190h+cbMaxValueNameLen], ecx
0x18002f322  lea     r14d, [rcx+2]
0x18002f326  xor     ecx, ecx; hWnd
0x18002f328  imul    r14d, [rsp+190h+cValues]
0x18002f32e  inc     r14d
0x18002f331  lea     esi, [r14+r14]
0x18002f335  call    cs:__imp_GetDC
0x18002f33c  nop     dword ptr [rax+rax+00h]
0x18002f341  mov     rdi, rax
0x18002f344  test    rax, rax
0x18002f347  jz      loc_18002F663
0x18002f34d  imul    ebx, [rsp+190h+cValues], 42h ; 'B'
0x18002f352  add     ebx, esi
0x18002f354  test    ebx, ebx
0x18002f356  js      loc_18002F657
0x18002f35c  call    ?CheckInitUspMemory@@YAHXZ; CheckInitUspMemory(void)
0x18002f361  test    eax, eax
0x18002f363  jz      loc_18002F657
0x18002f369  mov     rcx, cs:?ghHeap@@3PEAXEA; hHeap
0x18002f370  xor     edx, edx; dwFlags
0x18002f372  movsxd  r8, ebx; dwBytes
0x18002f375  call    cs:__imp_HeapAlloc
0x18002f37c  nop     dword ptr [rax+rax+00h]
0x18002f381  mov     rsi, rax
0x18002f384  test    rax, rax
0x18002f387  jz      loc_18002F657
0x18002f38d  movdqa  xmm0, cs:__xmm@000000000000000000000000fffffff4
0x18002f395  mov     edx, r13d; dwIndex
0x18002f398  movdqa  [rbp+90h+var_100], xmm0
0x18002f39d  mov     r15d, r13d
0x18002f3a0  xorps   xmm0, xmm0
0x18002f3a3  mov     [rbp+90h+var_F0], 190h
0x18002f3aa  movups  xmmword ptr [rbp+90h+var_C2], xmm0
0x18002f3ae  mov     [rbp+90h+var_EC], 1000000h
0x18002f3b5  movups  xmmword ptr [rbp+90h+var_C2+0Eh], xmm0
0x18002f3b9  mov     [rbp+90h+var_E8], r13w
0x18002f3be  mov     dword ptr [rbp+90h+Destination], r13d
0x18002f3c2  movups  [rbp+90h+var_E2], xmm0
0x18002f3c6  movups  [rbp+90h+var_D2], xmm0
0x18002f3ca  mov     [rsp+190h+var_114], edx
0x18002f3ce  test    r12d, r12d
0x18002f3d1  jnz     loc_18002F570
0x18002f3d7  mov     eax, [rsp+190h+cbMaxValueNameLen]
0x18002f3db  lea     r9, [rsp+190h+cchValueName]; lpcchValueName
0x18002f3e0  inc     eax
0x18002f3e2  mov     [rsp+190h+lpcValues], 0; lpcbData
0x18002f3eb  mov     [rsp+190h+cchValueName], eax
0x18002f3ef  lea     eax, [r15+1]
0x18002f3f3  movsxd  rcx, eax
0x18002f3f6  mov     [rsp+190h+lpcbMaxClassLen], 0; lpData
0x18002f3ff  mov     [rsp+190h+lpcbMaxSubKeyLen], 0; lpType
0x18002f408  mov     [rsp+190h+phkResult], 0; lpReserved
0x18002f411  lea     rbx, [rsi+rcx*2]
0x18002f415  mov     rcx, [rsp+190h+hKey]; hKey
0x18002f41a  mov     r8, rbx; lpValueName
0x18002f41d  call    cs:__imp_RegEnumValueW
0x18002f424  nop     dword ptr [rax+rax+00h]
0x18002f429  mov     r12d, eax
0x18002f42c  test    eax, eax
0x18002f42e  jnz     loc_18002F565
0x18002f434  mov     ecx, [rsp+190h+cchValueName]
0x18002f438  cmp     ecx, [rsp+190h+cbMaxValueNameLen]
0x18002f43c  ja      loc_18002F565
0x18002f442  movsxd  rax, r15d
0x18002f445  inc     r13d
0x18002f448  mov     [rsp+190h+var_118], r13d
0x18002f44d  mov     [rsi+rax*2], cx
0x18002f451  xor     eax, eax
0x18002f453  mov     edx, [rsp+190h+cchValueName]
0x18002f457  inc     edx
0x18002f459  add     edx, r15d
0x18002f45c  movsxd  rcx, edx
0x18002f45f  lea     r15d, [rdx+1]
0x18002f463  mov     [rsi+rcx*2], ax
0x18002f467  test    rdi, rdi
0x18002f46a  jz      loc_18002F565
0x18002f470  mov     r8, rbx; Source
0x18002f473  lea     edx, [rax+20h]; SizeInWords
0x18002f476  lea     rcx, [rbp+90h+Destination+2]; Destination
0x18002f47a  call    wcscpy_s
0x18002f47f  lea     rcx, [rbp+90h+var_100]
0x18002f483  call    CreateFontIndirectWImpl
0x18002f488  mov     [rbp+90h+var_110], rax
0x18002f48c  mov     r13, rax
0x18002f48f  test    rax, rax
0x18002f492  jz      loc_18002F560
0x18002f498  mov     rdx, rax; h
0x18002f49b  mov     rcx, rdi; hdc
0x18002f49e  call    cs:__imp_SelectObject
0x18002f4a5  nop     dword ptr [rax+rax+00h]
0x18002f4aa  mov     [rbp+90h+h], rax
0x18002f4ae  test    rax, rax
0x18002f4b1  jz      loc_18002F551
0x18002f4b7  xor     ecx, ecx
0x18002f4b9  lea     r9d, [r12+1]
0x18002f4be  mov     [rbp+90h+var_60], cx
0x18002f4c2  lea     r8, [rbp+90h+Source]
0x18002f4c6  lea     edx, [rcx+20h]
0x18002f4c9  mov     rcx, rdi
0x18002f4cc  call    cs:__imp_NtGdiGetTextFaceW
0x18002f4d3  nop     dword ptr [rax+rax+00h]
0x18002f4d8  test    eax, eax
0x18002f4da  jz      short loc_18002F53E
0x18002f4dc  lea     rax, [rbp+90h+Source]
0x18002f4e0  mov     r8, rbx
0x18002f4e3  sub     r8, rax
0x18002f4e6  movzx   edx, word ptr [rax]
0x18002f4e9  movzx   ecx, word ptr [rax+r8]
0x18002f4ee  sub     edx, ecx
0x18002f4f0  jnz     short loc_18002F4FA
0x18002f4f2  add     rax, 2
0x18002f4f6  test    ecx, ecx
0x18002f4f8  jnz     short loc_18002F4E6
0x18002f4fa  test    edx, edx
0x18002f4fc  jnz     short loc_18002F53E
0x18002f4fe  xor     r9d, r9d
0x18002f501  lea     r8, [rbp+90h+Source]
0x18002f505  mov     rcx, rdi
0x18002f508  lea     edx, [r9+20h]
0x18002f50c  call    cs:__imp_NtGdiGetTextFaceW
0x18002f513  nop     dword ptr [rax+rax+00h]
0x18002f518  test    eax, eax
0x18002f51a  jz      short loc_18002F53E
0x18002f51c  lea     rax, [rbp+90h+Source]
0x18002f520  sub     rbx, rax
0x18002f523  movzx   edx, word ptr [rax]
0x18002f526  movzx   ecx, word ptr [rax+rbx]
0x18002f52a  sub     edx, ecx
0x18002f52c  jnz     short loc_18002F536
0x18002f52e  add     rax, 2
0x18002f532  test    ecx, ecx
0x18002f534  jnz     short loc_18002F523
0x18002f536  test    edx, edx
0x18002f538  jnz     loc_18002F5DB
0x18002f53e  mov     rdx, [rbp+90h+h]; h
0x18002f542  mov     rcx, rdi; hdc
0x18002f545  call    cs:__imp_SelectObject
0x18002f54c  nop     dword ptr [rax+rax+00h]
0x18002f551  mov     rcx, r13; ho
0x18002f554  call    cs:__imp_DeleteObject
0x18002f55b  nop     dword ptr [rax+rax+00h]
0x18002f560  mov     r13d, [rsp+190h+var_118]
0x18002f565  mov     edx, [rsp+190h+var_114]
0x18002f569  inc     edx
0x18002f56b  jmp     loc_18002F3CA
0x18002f570  cmp     r12d, 7Ah ; 'z'
0x18002f574  jz      loc_18002F3D7
0x18002f57a  xor     eax, eax
0x18002f57c  movsxd  rcx, r15d
0x18002f57f  mov     [rsi+rcx*2], ax
0x18002f583  test    r13d, r13d
0x18002f586  jz      loc_18002F66A
0x18002f58c  mov     cs:?gFontLinkingData@@3PEA_WEA, rsi; wchar_t * gFontLinkingData
0x18002f593  mov     rcx, [rsp+190h+hKey]; hKey
0x18002f598  call    cs:__imp_RegCloseKey
0x18002f59f  nop     dword ptr [rax+rax+00h]
0x18002f5a4  test    rdi, rdi
0x18002f5a7  jz      short loc_18002F5BA
0x18002f5a9  mov     rdx, rdi; hDC
0x18002f5ac  xor     ecx, ecx; hWnd
0x18002f5ae  call    cs:__imp_ReleaseDC
0x18002f5b5  nop     dword ptr [rax+rax+00h]
0x18002f5ba  mov     rcx, [rbp+90h+var_50]
0x18002f5be  xor     rcx, rsp; StackCookie
0x18002f5c1  call    __security_check_cookie
0x18002f5c6  add     rsp, 158h
0x18002f5cd  pop     r15
0x18002f5cf  pop     r14
0x18002f5d1  pop     r13
0x18002f5d3  pop     r12
0x18002f5d5  pop     rdi
0x18002f5d6  pop     rsi
0x18002f5d7  pop     rbx
0x18002f5d8  pop     rbp
0x18002f5d9  retn
0x18002f5db  lea     r13d, [r15+1]
0x18002f5df  cmp     r13d, r14d
0x18002f5e2  jge     short loc_18002F631
0x18002f5e4  mov     edx, 21h ; '!'; MaxCount
0x18002f5e9  lea     rcx, [rbp+90h+Source]; Source
0x18002f5ed  call    cs:__imp_wcsnlen
0x18002f5f4  nop     dword ptr [rax+rax+00h]
0x18002f5f9  movsxd  rcx, r15d
0x18002f5fc  lea     r8, [rbp+90h+Source]; Source
0x18002f600  mov     rbx, rax
0x18002f603  mov     [rsi+rcx*2], bx
0x18002f607  mov     ecx, r14d
0x18002f60a  sub     ecx, r15d
0x18002f60d  dec     ecx
0x18002f60f  movsxd  rdx, ecx; SizeInWords
0x18002f612  movsxd  rcx, r13d
0x18002f615  lea     rcx, [rsi+rcx*2]; Destination
0x18002f619  call    wcscpy_s
0x18002f61e  lea     edx, [rbx+1]
0x18002f621  add     edx, r15d
0x18002f624  movsxd  rcx, edx
0x18002f627  xor     eax, eax
0x18002f629  lea     r15d, [rdx+1]
0x18002f62d  mov     [rsi+rcx*2], ax
0x18002f631  mov     r13, [rbp+90h+var_110]
0x18002f635  jmp     loc_18002F53E
0x18002f63a  mov     rcx, [rsp+190h+hKey]; hKey
0x18002f63f  call    cs:__imp_RegCloseKey
0x18002f646  nop     dword ptr [rax+rax+00h]
0x18002f64b  mov     cs:?gFontLinkingData@@3PEA_WEA, r13; wchar_t * gFontLinkingData
0x18002f652  jmp     loc_18002F5BA
0x18002f657  mov     cs:?gFontLinkingData@@3PEA_WEA, r13; wchar_t * gFontLinkingData
0x18002f65e  jmp     loc_18002F593
0x18002f663  mov     ebx, esi
0x18002f665  jmp     loc_18002F354
0x18002f66a  mov     rcx, rsi; lpMem
0x18002f66d  call    UspFreeMem
0x18002f672  xor     esi, esi
0x18002f674  jmp     loc_18002F58C
```
