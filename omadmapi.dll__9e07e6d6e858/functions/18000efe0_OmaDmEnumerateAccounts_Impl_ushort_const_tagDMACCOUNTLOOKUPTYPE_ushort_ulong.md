# OmaDmEnumerateAccounts_Impl(ushort const *,tagDMACCOUNTLOOKUPTYPE,ushort * * *,ulong *)

- ea: `0x18000efe0`
- end: `0x18000f473`
- name: `?OmaDmEnumerateAccounts_Impl@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@PEAPEAPEAGPEAK@Z`
- size: `1171`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180016bf0`
- `0x1800170f0`

## callees

- `0x180003db8`
- `0x1800075f0`
- `0x180007930`
- `0x18000efe0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f312`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f331`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f3fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f412`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f428`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f437`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f312`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f331`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f3fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f412`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f428`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f437`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f14d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f19b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f28e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f14d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f19b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f28e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f07b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f447`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f07b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f447`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f0b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f0b2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000f11a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000f11a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000f1f9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000f1f9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f275`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f2d1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f275`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f2d1`
- `DMCmnUtils!CopyString` at `0x18000f21f`
- `DMCmnUtils!CopyString` at `0x18000f2f6`
- `DMCmnUtils!CopyString` at `0x18000f21f`
- `DMCmnUtils!CopyString` at `0x18000f2f6`

## pseudocode

```c
__int64 __fastcall OmaDmEnumerateAccounts_Impl(const WCHAR *a1, int a2, HLOCAL **a3, _DWORD *a4)
{
  WCHAR *v4; // rsi
  HLOCAL v5; // rdi
  const WCHAR *v6; // r12
  signed int v7; // ebx
  HLOCAL *v8; // r14
  __int64 v9; // r15
  LSTATUS v10; // eax
  unsigned __int64 v11; // rax
  HLOCAL *v12; // rax
  signed int v13; // r13d
  DWORD v14; // r12d
  LSTATUS v15; // eax
  LSTATUS ValueW; // eax
  __int64 i; // r12
  size_t Size; // [rsp+68h] [rbp-19h] BYREF
  DWORD cchName; // [rsp+70h] [rbp-11h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+74h] [rbp-Dh] BYREF
  int v22; // [rsp+78h] [rbp-9h]
  HKEY hKey; // [rsp+80h] [rbp-1h] BYREF
  HANDLE hObject; // [rsp+88h] [rbp+7h] BYREF

  v4 = 0;
  hObject = 0;
  v5 = 0;
  hKey = 0;
  cbMaxSubKeyLen = 0;
  v6 = a1;
  cchName = 0;
  Size = 0;
  if ( a3 && a4 )
  {
    v7 = AcquireOmaDmMutex(&hObject);
    if ( v7 >= 0 )
    {
      v8 = 0;
      v22 = 0;
      v9 = 0;
      do
      {
        if ( hKey )
        {
          RegCloseKey(hKey);
          hKey = 0;
        }
        if ( !RegOpenKeyExW((HKEY)qword_18002A528[(int)v5], v6, 0, 0x20119u, &hKey) )
        {
          v10 = RegQueryInfoKeyW(hKey, 0, 0, 0, (LPDWORD)&Size + 1, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
          if ( v10 )
          {
            if ( v10 > 0 )
              v7 = (unsigned __int16)v10 | 0x80070000;
            else
              v7 = v10;
            goto LABEL_49;
          }
          if ( HIDWORD(Size) )
          {
            v11 = 8LL * HIDWORD(Size);
            if ( v11 > 0xFFFFFFFF )
            {
              LODWORD(Size) = -1;
              v7 = -2147024362;
              v4 = 0;
              v5 = 0;
              goto LABEL_52;
            }
            LODWORD(Size) = 8 * HIDWORD(Size);
            v12 = (HLOCAL *)LocalAlloc(0, (unsigned int)v11);
            v8 = v12;
            if ( !v12 )
            {
              v7 = -2147024882;
              goto LABEL_43;
            }
            memset_0(v12, 0, (unsigned int)Size);
            v13 = cbMaxSubKeyLen + 1;
            if ( cbMaxSubKeyLen + 1 < cbMaxSubKeyLen )
            {
              v4 = 0;
              v7 = -2147024362;
              v5 = 0;
              goto LABEL_53;
            }
            LODWORD(Size) = 2 * v13;
            if ( v13 < 0 )
            {
              v7 = -2102788093;
              v4 = 0;
              goto LABEL_39;
            }
            v4 = (WCHAR *)LocalAlloc(0, (unsigned int)(2 * v13));
            if ( !v4 )
            {
              v7 = -2147024882;
LABEL_39:
              v5 = 0;
LABEL_53:
              for ( i = 0; (unsigned int)i < HIDWORD(Size); i = (unsigned int)(i + 1) )
                LocalFree(v8[i]);
              LocalFree(v8);
              goto LABEL_57;
            }
            v14 = 0;
            v7 = 0;
            if ( HIDWORD(Size) )
            {
              while ( 1 )
              {
                cchName = v13;
                v15 = RegEnumKeyExW(hKey, v14, v4, &cchName, 0, 0, 0, 0);
                if ( v15 )
                {
                  if ( v15 > 0 )
                    v7 = (unsigned __int16)v15 | 0x80070000;
                  else
                    v7 = v15;
                  goto LABEL_50;
                }
                if ( a2 == 1 )
                {
                  v7 = CopyString(v4, cchName, (unsigned __int16 **)&v8[v9]);
                  if ( v7 < 0 )
                    goto LABEL_39;
                  v9 = (unsigned int)(v9 + 1);
                }
                else if ( a2 == 2 && !RegGetValueW(hKey, v4, L"AcctUId", 2u, 0, 0, (LPDWORD)&Size) )
                {
                  v5 = LocalAlloc(0, (unsigned int)Size);
                  if ( !v5 )
                  {
                    v7 = -2147024882;
                    goto LABEL_53;
                  }
                  ValueW = RegGetValueW(hKey, v4, L"AcctUId", 2u, 0, v5, (LPDWORD)&Size);
                  v7 = ValueW;
                  if ( ValueW )
                  {
                    if ( ValueW > 0 )
                      v7 = (unsigned __int16)ValueW | 0x80070000;
                    goto LABEL_51;
                  }
                  cchName = (unsigned int)Size >> 1;
                  v7 = CopyString((const unsigned __int16 *)v5, (unsigned int)Size >> 1, (unsigned __int16 **)&v8[v9]);
                  if ( v7 < 0 )
                    goto LABEL_52;
                  v9 = (unsigned int)(v9 + 1);
                  LocalFree(v5);
                }
                if ( ++v14 >= HIDWORD(Size) )
                {
                  LODWORD(v5) = v22;
                  break;
                }
              }
            }
            LocalFree(v4);
            v6 = a1;
          }
        }
        LODWORD(v5) = (_DWORD)v5 + 1;
        v22 = (int)v5;
      }
      while ( (unsigned int)v5 < 2 );
      *a4 = v9;
      *a3 = v8;
      if ( !(_DWORD)v9 )
      {
        v7 = -2147023728;
LABEL_43:
        v4 = 0;
        v5 = 0;
        goto LABEL_57;
      }
      v8 = 0;
LABEL_49:
      v4 = 0;
LABEL_50:
      v5 = 0;
LABEL_51:
      if ( v7 < 0 )
      {
LABEL_52:
        if ( !v8 )
          goto LABEL_57;
        goto LABEL_53;
      }
    }
  }
  else
  {
    v7 = -2147467261;
  }
LABEL_57:
  LocalFree(v4);
  LocalFree(v5);
  RegCloseKey(hKey);
  ReleaseOmaDmMutex(hObject);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000efe0  mov     rax, rsp
0x18000efe3  mov     [rax+20h], r9
0x18000efe7  mov     [rax+18h], r8
0x18000efeb  mov     [rax+10h], edx
0x18000efee  mov     [rax+8], rcx
0x18000eff2  push    rbp
0x18000eff3  push    rbx
0x18000eff4  push    rsi
0x18000eff5  push    rdi
0x18000eff6  push    r12
0x18000eff8  push    r13
0x18000effa  push    r14
0x18000effc  push    r15
0x18000effe  lea     rbp, [rax-5Fh]
0x18000f002  sub     rsp, 98h
0x18000f009  xor     esi, esi
0x18000f00b  mov     [rbp+57h+hObject], 0
0x18000f013  xor     edi, edi
0x18000f015  mov     [rbp+57h+hKey], 0
0x18000f01d  mov     dword ptr [rbp+57h+Size+4], 0
0x18000f024  mov     rax, r9
0x18000f027  mov     [rbp+57h+cbMaxSubKeyLen], 0
0x18000f02e  mov     r12, rcx
0x18000f031  mov     [rbp+57h+cchName], 0
0x18000f038  mov     dword ptr [rbp+57h+Size], 0
0x18000f03f  test    r8, r8
0x18000f042  jz      loc_18000F420
0x18000f048  test    rax, rax
0x18000f04b  jz      loc_18000F420
0x18000f051  lea     rcx, [rbp+57h+hObject]; void **
0x18000f055  call    ?AcquireOmaDmMutex@@YAJPEAPEAX@Z; AcquireOmaDmMutex(void * *)
0x18000f05a  mov     ebx, eax
0x18000f05c  test    eax, eax
0x18000f05e  js      loc_18000F425
0x18000f064  xor     r14d, r14d
0x18000f067  mov     [rbp+57h+var_60], edi
0x18000f06a  xor     r15d, r15d
0x18000f06d  mov     esi, 0FFFFFFFFh
0x18000f072  mov     rcx, [rbp+57h+hKey]; hKey
0x18000f076  test    rcx, rcx
0x18000f079  jz      short loc_18000F08F
0x18000f07b  call    cs:__imp_RegCloseKey
0x18000f082  nop     dword ptr [rax+rax+00h]
0x18000f087  mov     [rbp+57h+hKey], 0
0x18000f08f  lea     r10, qword_18002A528
0x18000f096  movsxd  rcx, edi
0x18000f099  lea     rax, [rbp+57h+hKey]
0x18000f09d  mov     r9d, 20119h; samDesired
0x18000f0a3  xor     r8d, r8d; ulOptions
0x18000f0a6  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18000f0ab  mov     rdx, r12; lpSubKey
0x18000f0ae  mov     rcx, [r10+rcx*8]; hKey
0x18000f0b2  call    cs:__imp_RegOpenKeyExW
0x18000f0b9  nop     dword ptr [rax+rax+00h]
0x18000f0be  test    eax, eax
0x18000f0c0  jnz     loc_18000F346
0x18000f0c6  mov     rcx, [rbp+57h+hKey]; hKey
0x18000f0ca  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x18000f0ce  mov     qword ptr [rsp+58h], 0; lpftLastWriteTime
0x18000f0d7  xor     r9d, r9d; lpReserved
0x18000f0da  mov     [rsp+0D0h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x18000f0e3  xor     r8d, r8d; lpcchClass
0x18000f0e6  mov     [rsp+0D0h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x18000f0ef  xor     edx, edx; lpClass
0x18000f0f1  mov     [rsp+0D0h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x18000f0fa  mov     [rsp+0D0h+lpcValues], 0; lpcValues
0x18000f103  mov     [rsp+0D0h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x18000f10c  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18000f111  lea     rax, [rbp+57h+Size+4]
0x18000f115  mov     [rsp+0D0h+phkResult], rax; lpcSubKeys
0x18000f11a  call    cs:__imp_RegQueryInfoKeyW
0x18000f121  nop     dword ptr [rax+rax+00h]
0x18000f126  test    eax, eax
0x18000f128  jnz     loc_18000F3C9
0x18000f12e  mov     eax, dword ptr [rbp+57h+Size+4]
0x18000f131  test    eax, eax
0x18000f133  jz      loc_18000F346
0x18000f139  shl     rax, 3
0x18000f13d  cmp     rax, rsi
0x18000f140  ja      loc_18000F3BB
0x18000f146  mov     edx, eax; uBytes
0x18000f148  xor     ecx, ecx; uFlags
0x18000f14a  mov     dword ptr [rbp+57h+Size], edx
0x18000f14d  call    cs:__imp_LocalAlloc
0x18000f154  nop     dword ptr [rax+rax+00h]
0x18000f159  mov     r14, rax
0x18000f15c  test    rax, rax
0x18000f15f  jz      loc_18000F3B0
0x18000f165  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x18000f169  xor     edx, edx; Val
0x18000f16b  mov     rcx, rax; void *
0x18000f16e  call    memset_0
0x18000f173  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18000f176  lea     r13d, [rax+1]
0x18000f17a  cmp     r13d, eax
0x18000f17d  jb      loc_18000F3A5
0x18000f183  lea     eax, ds:0[r13*2]
0x18000f18b  mov     dword ptr [rbp+57h+Size], eax
0x18000f18e  test    r13d, r13d
0x18000f191  js      loc_18000F39C
0x18000f197  mov     edx, eax; uBytes
0x18000f199  xor     ecx, ecx; uFlags
0x18000f19b  call    cs:__imp_LocalAlloc
0x18000f1a2  nop     dword ptr [rax+rax+00h]
0x18000f1a7  mov     rsi, rax
0x18000f1aa  test    rax, rax
0x18000f1ad  jz      loc_18000F393
0x18000f1b3  xor     eax, eax
0x18000f1b5  xor     r12d, r12d
0x18000f1b8  xor     ebx, ebx
0x18000f1ba  cmp     dword ptr [rbp+57h+Size+4], eax
0x18000f1bd  jbe     loc_18000F32E
0x18000f1c3  mov     rcx, [rbp+57h+hKey]; hKey
0x18000f1c7  lea     r9, [rbp+57h+cchName]; lpcchName
0x18000f1cb  mov     [rsp+0D0h+lpcValues], 0; lpftLastWriteTime
0x18000f1d4  mov     r8, rsi; lpName
0x18000f1d7  mov     [rsp+0D0h+lpcbMaxClassLen], 0; lpcchClass
0x18000f1e0  mov     edx, r12d; dwIndex
0x18000f1e3  mov     [rsp+0D0h+lpcbMaxSubKeyLen], 0; lpClass
0x18000f1ec  mov     [rsp+0D0h+phkResult], 0; lpReserved
0x18000f1f5  mov     [rbp+57h+cchName], r13d
0x18000f1f9  call    cs:__imp_RegEnumKeyExW
0x18000f200  nop     dword ptr [rax+rax+00h]
0x18000f205  test    eax, eax
0x18000f207  jnz     loc_18000F382
0x18000f20d  mov     eax, [rbp+57h+arg_8]
0x18000f210  cmp     eax, 1
0x18000f213  jnz     short loc_18000F23D
0x18000f215  mov     edx, [rbp+57h+cchName]
0x18000f218  lea     r8, [r14+r15*8]
0x18000f21c  mov     rcx, rsi
0x18000f21f  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18000f226  nop     dword ptr [rax+rax+00h]
0x18000f22b  mov     ebx, eax
0x18000f22d  test    eax, eax
0x18000f22f  js      loc_18000F398
0x18000f235  inc     r15d
0x18000f238  jmp     loc_18000F31E
0x18000f23d  cmp     eax, 2
0x18000f240  jnz     loc_18000F31E
0x18000f246  mov     rcx, [rbp+57h+hKey]; hkey
0x18000f24a  lea     rax, [rbp+57h+Size]
0x18000f24e  mov     [rsp+0D0h+lpcbMaxClassLen], rax; pcbData
0x18000f253  lea     r8, Value; "AcctUId"
0x18000f25a  mov     [rsp+0D0h+lpcbMaxSubKeyLen], 0; pvData
0x18000f263  mov     r9d, 2; dwFlags
0x18000f269  mov     rdx, rsi; lpSubKey
0x18000f26c  mov     [rsp+0D0h+phkResult], 0; pdwType
0x18000f275  call    cs:__imp_RegGetValueW
0x18000f27c  nop     dword ptr [rax+rax+00h]
0x18000f281  test    eax, eax
0x18000f283  jnz     loc_18000F31E
0x18000f289  mov     edx, dword ptr [rbp+57h+Size]; uBytes
0x18000f28c  xor     ecx, ecx; uFlags
0x18000f28e  call    cs:__imp_LocalAlloc
0x18000f295  nop     dword ptr [rax+rax+00h]
0x18000f29a  mov     rdi, rax
0x18000f29d  test    rax, rax
0x18000f2a0  jz      loc_18000F37B
0x18000f2a6  mov     rcx, [rbp+57h+hKey]; hkey
0x18000f2aa  lea     rax, [rbp+57h+Size]
0x18000f2ae  mov     [rsp+0D0h+lpcbMaxClassLen], rax; pcbData
0x18000f2b3  lea     r8, Value; "AcctUId"
0x18000f2ba  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rdi; pvData
0x18000f2bf  mov     r9d, 2; dwFlags
0x18000f2c5  mov     rdx, rsi; lpSubKey
0x18000f2c8  mov     [rsp+0D0h+phkResult], 0; pdwType
0x18000f2d1  call    cs:__imp_RegGetValueW
0x18000f2d8  nop     dword ptr [rax+rax+00h]
0x18000f2dd  mov     ebx, eax
0x18000f2df  test    eax, eax
0x18000f2e1  jnz     loc_18000F36E
0x18000f2e7  mov     edx, dword ptr [rbp+57h+Size]
0x18000f2ea  lea     r8, [r14+r15*8]
0x18000f2ee  shr     edx, 1
0x18000f2f0  mov     rcx, rdi
0x18000f2f3  mov     [rbp+57h+cchName], edx
0x18000f2f6  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18000f2fd  nop     dword ptr [rax+rax+00h]
0x18000f302  mov     ebx, eax
0x18000f304  test    eax, eax
0x18000f306  js      loc_18000F3E5
0x18000f30c  inc     r15d
0x18000f30f  mov     rcx, rdi; hMem
0x18000f312  call    cs:__imp_LocalFree
0x18000f319  nop     dword ptr [rax+rax+00h]
0x18000f31e  inc     r12d
0x18000f321  cmp     r12d, dword ptr [rbp+57h+Size+4]
0x18000f325  jb      loc_18000F1C3
0x18000f32b  mov     edi, [rbp+57h+var_60]
0x18000f32e  mov     rcx, rsi; hMem
0x18000f331  call    cs:__imp_LocalFree
0x18000f338  nop     dword ptr [rax+rax+00h]
0x18000f33d  mov     r12, [rbp+57h+arg_0]
0x18000f341  mov     esi, 0FFFFFFFFh
0x18000f346  inc     edi
0x18000f348  mov     [rbp+57h+var_60], edi
0x18000f34b  cmp     edi, 2
0x18000f34e  jb      loc_18000F072
0x18000f354  mov     rax, [rbp+57h+arg_18]
0x18000f358  mov     [rax], r15d
0x18000f35b  mov     rax, [rbp+57h+arg_10]
0x18000f35f  mov     [rax], r14
0x18000f362  test    r15d, r15d
0x18000f365  jnz     short loc_18000F3DA
0x18000f367  mov     ebx, 80070490h
0x18000f36c  jmp     short loc_18000F3B5
0x18000f36e  jle     short loc_18000F3E1
0x18000f370  movzx   ebx, ax
0x18000f373  or      ebx, 80070000h
0x18000f379  jmp     short loc_18000F3E1
0x18000f37b  mov     ebx, 8007000Eh
0x18000f380  jmp     short loc_18000F3EA
0x18000f382  jg      short loc_18000F388
0x18000f384  mov     ebx, eax
0x18000f386  jmp     short loc_18000F3DF
0x18000f388  movzx   ebx, ax
0x18000f38b  or      ebx, 80070000h
0x18000f391  jmp     short loc_18000F3DF
0x18000f393  mov     ebx, 8007000Eh
0x18000f398  xor     edi, edi
0x18000f39a  jmp     short loc_18000F3EA
0x18000f39c  mov     ebx, 82AA0003h
0x18000f3a1  xor     esi, esi
0x18000f3a3  jmp     short loc_18000F398
0x18000f3a5  xor     esi, esi
0x18000f3a7  mov     ebx, 80070216h
0x18000f3ac  xor     edi, edi
0x18000f3ae  jmp     short loc_18000F3EA
0x18000f3b0  mov     ebx, 8007000Eh
0x18000f3b5  xor     esi, esi
0x18000f3b7  xor     edi, edi
0x18000f3b9  jmp     short loc_18000F425
0x18000f3bb  mov     dword ptr [rbp+57h+Size], esi
0x18000f3be  mov     ebx, 80070216h
0x18000f3c3  xor     esi, esi
0x18000f3c5  xor     edi, edi
0x18000f3c7  jmp     short loc_18000F3E5
0x18000f3c9  jg      short loc_18000F3CF
0x18000f3cb  mov     ebx, eax
0x18000f3cd  jmp     short loc_18000F3DD
0x18000f3cf  movzx   ebx, ax
0x18000f3d2  or      ebx, 80070000h
0x18000f3d8  jmp     short loc_18000F3DD
0x18000f3da  xor     r14d, r14d
0x18000f3dd  xor     esi, esi
0x18000f3df  xor     edi, edi
0x18000f3e1  test    ebx, ebx
0x18000f3e3  jns     short loc_18000F425
0x18000f3e5  test    r14, r14
0x18000f3e8  jz      short loc_18000F425
0x18000f3ea  xor     r12d, r12d
0x18000f3ed  mov     r15, r14
0x18000f3f0  cmp     dword ptr [rbp+57h+Size+4], r12d
0x18000f3f4  jbe     short loc_18000F40F
0x18000f3f6  mov     rcx, [r15+r12*8]; hMem
0x18000f3fa  call    cs:__imp_LocalFree
0x18000f401  nop     dword ptr [rax+rax+00h]
0x18000f406  inc     r12d
0x18000f409  cmp     r12d, dword ptr [rbp+57h+Size+4]
0x18000f40d  jb      short loc_18000F3F6
0x18000f40f  mov     rcx, r14; hMem
0x18000f412  call    cs:__imp_LocalFree
0x18000f419  nop     dword ptr [rax+rax+00h]
0x18000f41e  jmp     short loc_18000F425
0x18000f420  mov     ebx, 80004003h
0x18000f425  mov     rcx, rsi; hMem
0x18000f428  call    cs:__imp_LocalFree
0x18000f42f  nop     dword ptr [rax+rax+00h]
0x18000f434  mov     rcx, rdi; hMem
0x18000f437  call    cs:__imp_LocalFree
0x18000f43e  nop     dword ptr [rax+rax+00h]
0x18000f443  mov     rcx, [rbp+57h+hKey]; hKey
0x18000f447  call    cs:__imp_RegCloseKey
0x18000f44e  nop     dword ptr [rax+rax+00h]
0x18000f453  mov     rcx, [rbp+57h+hObject]; hObject
0x18000f457  call    ?ReleaseOmaDmMutex@@YAXPEAX@Z; ReleaseOmaDmMutex(void *)
0x18000f45c  mov     eax, ebx
0x18000f45e  add     rsp, 98h
0x18000f465  pop     r15
0x18000f467  pop     r14
0x18000f469  pop     r13
0x18000f46b  pop     r12
0x18000f46d  pop     rdi
0x18000f46e  pop     rsi
0x18000f46f  pop     rbx
0x18000f470  pop     rbp
0x18000f471  retn
```
