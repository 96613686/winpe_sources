# CDoc::GetDocTempFilename(ushort const *,ushort const *,ushort *,ulong)

- ea: `0x1809934c0`
- end: `0x1809937ed`
- name: `?GetDocTempFilename@CDoc@@QEAAHPEBG0PEAGK@Z`
- size: `813`
- prototype: `int(CDoc *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `12`
- callee_count: `6`
- tags: `file_ops, reparse_path, service_task, broker_com_uri`

## callers

- `0x18075ee20`
- `0x1807f7e90`
- `0x1808c4db8`
- `0x1809b1fb0`
- `0x180e36bac`
- `0x180e381cc`
- `0x180e3c134`
- `0x180e508f0`
- `0x180e533b8`
- `0x180e5c650`
- `0x180e96b70`
- `0x180eda510`

## callees

- `0x1801bf528`
- `0x1802e5024`
- `0x18073d694`
- `0x180839298`
- `0x1809934c0`
- `0x1810c2d60`

## import_xrefs

- `KERNEL32!GetTempPath2W` at `0x180993553`
- `KERNEL32!GetTempPath2W` at `0x180993553`
- `KERNEL32!GetFileAttributesW` at `0x18099371b`
- `KERNEL32!GetFileAttributesW` at `0x18099371b`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFileExistsW` at `0x180993577`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFileExistsW` at `0x180993577`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x180993566`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x180993566`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1809935d0`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1809935d0`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1809935dd`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1809935dd`
- `SHELL32!SHGetKnownFolderPath` at `0x180993597`
- `SHELL32!SHGetKnownFolderPath` at `0x180993597`
- `ADVAPI32!CryptAcquireContextA` at `0x180993606`
- `ADVAPI32!CryptAcquireContextA` at `0x180993606`
- `ADVAPI32!CryptGenRandom` at `0x18099362f`
- `ADVAPI32!CryptGenRandom` at `0x18099362f`
- `ADVAPI32!CryptReleaseContext` at `0x1809937b5`
- `ADVAPI32!CryptReleaseContext` at `0x1809937b5`

## pseudocode

```c
__int64 __fastcall CDoc::GetDocTempFilename(
        CDoc *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5)
{
  unsigned int v8; // edi
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rax
  HRESULT v11; // ebx
  int i; // ebx
  __int64 v13; // rax
  unsigned int v14; // r10d
  int j; // r9d
  __int64 v16; // r8
  __int16 v17; // cx
  unsigned int v18; // r11d
  __int64 v19; // rdi
  unsigned __int16 *v20; // rax
  unsigned __int16 *v21; // rbx
  HCRYPTPROV phProv; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR ppszPath; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v25[16]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR FileName[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszPath[248]; // [rsp+270h] [rbp+170h] BYREF

  phProv = 0;
  v8 = 0;
  if ( a4 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a2[v9] );
    if ( v9 <= 4 )
    {
      v10 = -1;
      do
        ++v10;
      while ( a3[v10] );
      if ( v10 <= 3 )
      {
        *a4 = 0;
        if ( (unsigned int)GetTempPath2W(247, pszPath) - 1 <= 0xF6 )
        {
          if ( IsProtectedModeProcess() || PathFileExistsW(pszPath) )
            goto LABEL_15;
          ppszPath = 0;
          if ( !SHGetKnownFolderPath(&FOLDERID_LocalAppDataLow, 0, 0, &ppszPath) )
          {
            v11 = StringCchCopyW(pszPath, 0xF7u, ppszPath);
            if ( !v11 )
              v11 = PathCchAppend(pszPath, 0xF7u, L"Microsoft\\Internet Explorer\\");
            CoTaskMemFree(ppszPath);
            if ( !v11 )
            {
LABEL_15:
              if ( !CryptAcquireContextA(&phProv, 0, 0, 1u, 0xF0000000) )
                return v8;
              for ( i = 100; i && CryptGenRandom(phProv, 8u, (BYTE *)&ppszPath); --i )
              {
                v13 = -1;
                do
                  ++v13;
                while ( a2[v13] );
                v14 = 0;
                for ( j = 8 - v13; (int)v14 < j; v25[v16] = v17 + ((unsigned __int8)v17 < 0x1Au ? 65 : 22) )
                {
                  v16 = v14;
                  v17 = *((_BYTE *)&v25[-4] + v14++) % 0x24u;
                }
                if ( (unsigned __int64)(2LL * j) >= 0x12 )
                  _report_rangecheckfailure();
                v25[j] = 0;
                StringCchCopyW(FileName, 0x104u, pszPath);
                StringCchCatW(FileName, v18, a2);
                StringCchCatW(FileName, 0x104u, v25);
                StringCchCatW(FileName, 0x104u, L".");
                StringCchCatW(FileName, 0x104u, a3);
                if ( GetFileAttributesW(FileName) == -1 )
                {
                  StringCchCopyW(a4, a5, FileName);
                  v19 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                + (unsigned int)tls_index)
                                              + 16LL)
                                  + 712LL);
                  if ( v19 )
                  {
                    if ( *(_DWORD *)(v19 + 8) )
                    {
                      v20 = (unsigned __int16 *)MemoryProtection::HeapAlloc<0>(g_hProcessHeap, 528);
                      v21 = v20;
                      if ( v20 )
                      {
                        StringCchCopyW(v20, 0x104u, a4);
                        *((_QWORD *)v21 + 65) = *(_QWORD *)v19;
                        *(_QWORD *)v19 = v21;
                      }
                    }
                  }
                  v8 = 1;
                  break;
                }
              }
            }
          }
        }
        if ( phProv )
          CryptReleaseContext(phProv, 0);
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1809934c0  mov     [rsp-8+arg_0], rbx
0x1809934c5  push    rbp
0x1809934c6  push    rsi
0x1809934c7  push    rdi
0x1809934c8  push    r12
0x1809934ca  push    r13
0x1809934cc  push    r14
0x1809934ce  push    r15
0x1809934d0  lea     rbp, [rsp-370h]
0x1809934d8  sub     rsp, 470h
0x1809934df  mov     rax, cs:__security_cookie
0x1809934e6  xor     rax, rsp
0x1809934e9  mov     [rbp+3A0h+var_40], rax
0x1809934f0  xor     r12d, r12d
0x1809934f3  mov     rsi, r9
0x1809934f6  mov     [rsp+4A0h+phProv], r12
0x1809934fb  mov     r15, r8
0x1809934fe  mov     r14, rdx
0x180993501  mov     edi, r12d
0x180993504  test    r9, r9
0x180993507  jz      loc_1809937BB
0x18099350d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180993511  mov     rax, rcx
0x180993514  inc     rax
0x180993517  cmp     [rdx+rax*2], r12w
0x18099351c  jnz     short loc_180993514
0x18099351e  cmp     rax, 4
0x180993522  ja      loc_1809937BB
0x180993528  mov     rax, rcx
0x18099352b  inc     rax
0x18099352e  cmp     [r8+rax*2], r12w
0x180993533  jnz     short loc_18099352B
0x180993535  cmp     rax, 3
0x180993539  ja      loc_1809937BB
0x18099353f  mov     r13d, 0F7h
0x180993545  mov     [r9], r12w
0x180993549  mov     ecx, r13d
0x18099354c  lea     rdx, [rbp+3A0h+pszPath]
0x180993553  call    cs:__imp_GetTempPath2W
0x180993559  dec     eax
0x18099355b  cmp     eax, 0F6h
0x180993560  ja      loc_1809937A9
0x180993566  call    cs:__imp_?IsProtectedModeProcess@@YAJXZ; IsProtectedModeProcess(void)
0x18099356c  test    eax, eax
0x18099356e  jnz     short loc_1809935EB
0x180993570  lea     rcx, [rbp+3A0h+pszPath]; pszPath
0x180993577  call    cs:__imp_PathFileExistsW
0x18099357d  test    eax, eax
0x18099357f  jnz     short loc_1809935EB
0x180993581  lea     r9, [rsp+4A0h+ppszPath]; ppszPath
0x180993586  mov     [rsp+4A0h+ppszPath], r12
0x18099358b  xor     r8d, r8d; hToken
0x18099358e  lea     rcx, FOLDERID_LocalAppDataLow; rfid
0x180993595  xor     edx, edx; dwFlags
0x180993597  call    cs:__imp_SHGetKnownFolderPath
0x18099359d  test    eax, eax
0x18099359f  jnz     loc_1809937A9
0x1809935a5  mov     r8, [rsp+4A0h+ppszPath]; unsigned __int16 *
0x1809935aa  lea     rcx, [rbp+3A0h+pszPath]; unsigned __int16 *
0x1809935b1  mov     edx, r13d; unsigned __int64
0x1809935b4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1809935b9  mov     ebx, eax
0x1809935bb  test    eax, eax
0x1809935bd  jnz     short loc_1809935D8
0x1809935bf  lea     r8, pszMore; "Microsoft\\Internet Explorer\\"
0x1809935c6  mov     edx, r13d; cchPath
0x1809935c9  lea     rcx, [rbp+3A0h+pszPath]; pszPath
0x1809935d0  call    cs:__imp_PathCchAppend
0x1809935d6  mov     ebx, eax
0x1809935d8  mov     rcx, [rsp+4A0h+ppszPath]; pv
0x1809935dd  call    cs:__imp_CoTaskMemFree
0x1809935e3  test    ebx, ebx
0x1809935e5  jnz     loc_1809937A9
0x1809935eb  mov     r13d, 1
0x1809935f1  mov     [rsp+4A0h+dwFlags], 0F0000000h; dwFlags
0x1809935f9  mov     r9d, r13d; dwProvType
0x1809935fc  lea     rcx, [rsp+4A0h+phProv]; phProv
0x180993601  xor     r8d, r8d; szProvider
0x180993604  xor     edx, edx; szContainer
0x180993606  call    cs:__imp_CryptAcquireContextA
0x18099360c  test    eax, eax
0x18099360e  jz      loc_1809937BB
0x180993614  lea     ebx, [r13+63h]
0x180993618  test    ebx, ebx
0x18099361a  jz      loc_1809937A9
0x180993620  mov     rcx, [rsp+4A0h+phProv]; hProv
0x180993625  lea     r8, [rsp+4A0h+ppszPath]; pbBuffer
0x18099362a  mov     edx, 8; dwLen
0x18099362f  call    cs:__imp_CryptGenRandom
0x180993635  test    eax, eax
0x180993637  jz      loc_1809937A9
0x18099363d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180993641  inc     rax
0x180993644  cmp     [r14+rax*2], r12w
0x180993649  jnz     short loc_180993641
0x18099364b  mov     r9d, 8
0x180993651  mov     r10d, r12d
0x180993654  sub     r9d, eax
0x180993657  test    r9d, r9d
0x18099365a  jle     short loc_180993699
0x18099365c  mov     r8d, r10d
0x18099365f  mov     eax, 38E38E39h
0x180993664  movzx   ecx, byte ptr [rsp+r8+4A0h+ppszPath]
0x18099366a  mul     ecx
0x18099366c  shr     edx, 3
0x18099366f  lea     eax, [rdx+rdx*8]
0x180993672  shl     eax, 2
0x180993675  sub     ecx, eax
0x180993677  movzx   ecx, cl
0x18099367a  cmp     cl, 1Ah
0x18099367d  sbb     ax, ax
0x180993680  add     r10d, r13d
0x180993683  and     ax, 2Bh
0x180993687  add     ax, 16h
0x18099368b  add     ax, cx
0x18099368e  mov     [rsp+r8*2+4A0h+var_460], ax
0x180993694  cmp     r10d, r9d
0x180993697  jl      short loc_18099365C
0x180993699  movsxd  rax, r9d
0x18099369c  lea     rcx, [rax+rax]
0x1809936a0  cmp     rcx, 12h
0x1809936a4  jnb     loc_1809937E7
0x1809936aa  mov     [rsp+rcx+4A0h+var_460], r12w
0x1809936b0  lea     r8, [rbp+3A0h+pszPath]; unsigned __int16 *
0x1809936b7  mov     r11d, 104h
0x1809936bd  lea     rcx, [rsp+4A0h+FileName]; unsigned __int16 *
0x1809936c2  mov     edx, r11d; unsigned __int64
0x1809936c5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1809936ca  mov     r8, r14; unsigned __int16 *
0x1809936cd  lea     rcx, [rsp+4A0h+FileName]; unsigned __int16 *
0x1809936d2  mov     edx, r11d; unsigned __int64
0x1809936d5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1809936da  lea     r8, [rsp+4A0h+var_460]; unsigned __int16 *
0x1809936df  mov     edx, 104h; unsigned __int64
0x1809936e4  lea     rcx, [rsp+4A0h+FileName]; unsigned __int16 *
0x1809936e9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1809936ee  lea     r8, asc_1813D2FB8; "."
0x1809936f5  mov     edx, 104h; unsigned __int64
0x1809936fa  lea     rcx, [rsp+4A0h+FileName]; unsigned __int16 *
0x1809936ff  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180993704  mov     r8, r15; unsigned __int16 *
0x180993707  lea     rcx, [rsp+4A0h+FileName]; unsigned __int16 *
0x18099370c  mov     edx, 104h; unsigned __int64
0x180993711  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180993716  lea     rcx, [rsp+4A0h+FileName]; lpFileName
0x18099371b  call    cs:__imp_GetFileAttributesW
0x180993721  cmp     eax, 0FFFFFFFFh
0x180993724  jz      short loc_18099372E
0x180993726  sub     ebx, r13d
0x180993729  jmp     loc_180993618
0x18099372e  mov     edx, [rbp+3A0h+arg_20]; unsigned __int64
0x180993734  lea     r8, [rsp+4A0h+FileName]; unsigned __int16 *
0x180993739  mov     rcx, rsi; unsigned __int16 *
0x18099373c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180993741  mov     rax, gs:58h
0x18099374a  mov     r11d, cs:_tls_index
0x180993751  mov     ecx, 10h
0x180993756  mov     rax, [rax+r11*8]
0x18099375a  mov     rcx, [rax+rcx]
0x18099375e  mov     rdi, [rcx+2C8h]
0x180993765  test    rdi, rdi
0x180993768  jz      short loc_1809937A6
0x18099376a  cmp     [rdi+8], r12d
0x18099376e  jz      short loc_1809937A6
0x180993770  mov     rcx, cs:g_hProcessHeap
0x180993777  mov     edx, 210h
0x18099377c  call    ??$HeapAlloc@$0A@@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<0>(void *,unsigned __int64)
0x180993781  mov     rbx, rax
0x180993784  test    rax, rax
0x180993787  jz      short loc_1809937A6
0x180993789  mov     r8, rsi; unsigned __int16 *
0x18099378c  mov     edx, 104h; unsigned __int64
0x180993791  mov     rcx, rax; unsigned __int16 *
0x180993794  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180993799  mov     r11, [rdi]
0x18099379c  mov     [rbx+208h], r11
0x1809937a3  mov     [rdi], rbx
0x1809937a6  mov     edi, r13d
0x1809937a9  mov     rcx, [rsp+4A0h+phProv]; hProv
0x1809937ae  test    rcx, rcx
0x1809937b1  jz      short loc_1809937BB
0x1809937b3  xor     edx, edx; dwFlags
0x1809937b5  call    cs:__imp_CryptReleaseContext
0x1809937bb  mov     eax, edi
0x1809937bd  mov     rcx, [rbp+3A0h+var_40]
0x1809937c4  xor     rcx, rsp; StackCookie
0x1809937c7  call    __security_check_cookie
0x1809937cc  mov     rbx, [rsp+4A0h+arg_0]
0x1809937d4  add     rsp, 470h
0x1809937db  pop     r15
0x1809937dd  pop     r14
0x1809937df  pop     r13
0x1809937e1  pop     r12
0x1809937e3  pop     rdi
0x1809937e4  pop     rsi
0x1809937e5  pop     rbp
0x1809937e6  retn
0x1809937e7  call    __report_rangecheckfailure
```
