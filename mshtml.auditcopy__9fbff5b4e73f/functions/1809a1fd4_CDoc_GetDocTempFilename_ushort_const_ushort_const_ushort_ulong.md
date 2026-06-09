# CDoc::GetDocTempFilename(ushort const *,ushort const *,ushort *,ulong)

- ea: `0x1809a1fd4`
- end: `0x1809a2342`
- name: `?GetDocTempFilename@CDoc@@QEAAHPEBG0PEAGK@Z`
- size: `878`
- prototype: `int(CDoc *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `12`
- callee_count: `6`
- tags: `file_ops, reparse_path, service_task, broker_com_uri`

## callers

- `0x18076a6e0`
- `0x180802a18`
- `0x1808ce504`
- `0x1809c1668`
- `0x180e5ba04`
- `0x180e5d00c`
- `0x180e6107c`
- `0x180e76560`
- `0x180e793a8`
- `0x180e82760`
- `0x180ebd240`
- `0x180f01a00`

## callees

- `0x18005d080`
- `0x18040ac58`
- `0x180745a1c`
- `0x18083bda8`
- `0x1809a1fd4`
- `0x1810f65c0`

## import_xrefs

- `KERNEL32!GetTempPath2W` at `0x1809a2067`
- `KERNEL32!GetTempPath2W` at `0x1809a2067`
- `KERNEL32!GetFileAttributesW` at `0x1809a2263`
- `KERNEL32!GetFileAttributesW` at `0x1809a2263`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFileExistsW` at `0x1809a209b`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFileExistsW` at `0x1809a209b`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1809a2080`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1809a2080`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1809a2100`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1809a2100`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1809a2113`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1809a2113`
- `SHELL32!SHGetKnownFolderPath` at `0x1809a20c1`
- `SHELL32!SHGetKnownFolderPath` at `0x1809a20c1`
- `ADVAPI32!CryptAcquireContextA` at `0x1809a2142`
- `ADVAPI32!CryptAcquireContextA` at `0x1809a2142`
- `ADVAPI32!CryptGenRandom` at `0x1809a2171`
- `ADVAPI32!CryptGenRandom` at `0x1809a2171`
- `ADVAPI32!CryptReleaseContext` at `0x1809a2303`
- `ADVAPI32!CryptReleaseContext` at `0x1809a2303`

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
  int v11; // ebx
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
                StringCchCatW(FileName, 260, v25);
                StringCchCatW(FileName, 260, L".");
                StringCchCatW(FileName, 260, a3);
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
                      v20 = (unsigned __int16 *)MemoryProtection::HeapAlloc<0>(
                                                  (MemoryProtection *)g_hProcessHeap,
                                                  0x210u);
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
0x1809a1fd4  mov     [rsp-8+arg_0], rbx
0x1809a1fd9  push    rbp
0x1809a1fda  push    rsi
0x1809a1fdb  push    rdi
0x1809a1fdc  push    r12
0x1809a1fde  push    r13
0x1809a1fe0  push    r14
0x1809a1fe2  push    r15
0x1809a1fe4  lea     rbp, [rsp-370h]
0x1809a1fec  sub     rsp, 470h
0x1809a1ff3  mov     rax, cs:__security_cookie
0x1809a1ffa  xor     rax, rsp
0x1809a1ffd  mov     [rbp+3A0h+var_40], rax
0x1809a2004  xor     r12d, r12d
0x1809a2007  mov     rsi, r9
0x1809a200a  mov     [rsp+4A0h+phProv], r12
0x1809a200f  mov     r15, r8
0x1809a2012  mov     r14, rdx
0x1809a2015  mov     edi, r12d
0x1809a2018  test    r9, r9
0x1809a201b  jz      loc_1809A230F
0x1809a2021  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1809a2025  mov     rax, rcx
0x1809a2028  inc     rax
0x1809a202b  cmp     [rdx+rax*2], r12w
0x1809a2030  jnz     short loc_1809A2028
0x1809a2032  cmp     rax, 4
0x1809a2036  ja      loc_1809A230F
0x1809a203c  mov     rax, rcx
0x1809a203f  inc     rax
0x1809a2042  cmp     [r8+rax*2], r12w
0x1809a2047  jnz     short loc_1809A203F
0x1809a2049  cmp     rax, 3
0x1809a204d  ja      loc_1809A230F
0x1809a2053  mov     r13d, 0F7h
0x1809a2059  mov     [r9], r12w
0x1809a205d  mov     ecx, r13d
0x1809a2060  lea     rdx, [rbp+3A0h+pszPath]
0x1809a2067  call    cs:__imp_GetTempPath2W
0x1809a206e  nop     dword ptr [rax+rax+00h]
0x1809a2073  dec     eax
0x1809a2075  cmp     eax, 0F6h
0x1809a207a  ja      loc_1809A22F7
0x1809a2080  call    cs:__imp_?IsProtectedModeProcess@@YAJXZ; IsProtectedModeProcess(void)
0x1809a2087  nop     dword ptr [rax+rax+00h]
0x1809a208c  test    eax, eax
0x1809a208e  jnz     loc_1809A2127
0x1809a2094  lea     rcx, [rbp+3A0h+pszPath]; pszPath
0x1809a209b  call    cs:__imp_PathFileExistsW
0x1809a20a2  nop     dword ptr [rax+rax+00h]
0x1809a20a7  test    eax, eax
0x1809a20a9  jnz     short loc_1809A2127
0x1809a20ab  lea     r9, [rsp+4A0h+ppszPath]; ppszPath
0x1809a20b0  mov     [rsp+4A0h+ppszPath], r12
0x1809a20b5  xor     r8d, r8d; hToken
0x1809a20b8  lea     rcx, FOLDERID_LocalAppDataLow; rfid
0x1809a20bf  xor     edx, edx; dwFlags
0x1809a20c1  call    cs:__imp_SHGetKnownFolderPath
0x1809a20c8  nop     dword ptr [rax+rax+00h]
0x1809a20cd  test    eax, eax
0x1809a20cf  jnz     loc_1809A22F7
0x1809a20d5  mov     r8, [rsp+4A0h+ppszPath]; unsigned __int16 *
0x1809a20da  lea     rcx, [rbp+3A0h+pszPath]; unsigned __int16 *
0x1809a20e1  mov     edx, r13d; unsigned __int64
0x1809a20e4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1809a20e9  mov     ebx, eax
0x1809a20eb  test    eax, eax
0x1809a20ed  jnz     short loc_1809A210E
0x1809a20ef  lea     r8, pszMore; "Microsoft\\Internet Explorer\\"
0x1809a20f6  mov     edx, r13d; cchPath
0x1809a20f9  lea     rcx, [rbp+3A0h+pszPath]; pszPath
0x1809a2100  call    cs:__imp_PathCchAppend
0x1809a2107  nop     dword ptr [rax+rax+00h]
0x1809a210c  mov     ebx, eax
0x1809a210e  mov     rcx, [rsp+4A0h+ppszPath]; pv
0x1809a2113  call    cs:__imp_CoTaskMemFree
0x1809a211a  nop     dword ptr [rax+rax+00h]
0x1809a211f  test    ebx, ebx
0x1809a2121  jnz     loc_1809A22F7
0x1809a2127  mov     r13d, 1
0x1809a212d  mov     [rsp+4A0h+dwFlags], 0F0000000h; dwFlags
0x1809a2135  mov     r9d, r13d; dwProvType
0x1809a2138  lea     rcx, [rsp+4A0h+phProv]; phProv
0x1809a213d  xor     r8d, r8d; szProvider
0x1809a2140  xor     edx, edx; szContainer
0x1809a2142  call    cs:__imp_CryptAcquireContextA
0x1809a2149  nop     dword ptr [rax+rax+00h]
0x1809a214e  test    eax, eax
0x1809a2150  jz      loc_1809A230F
0x1809a2156  lea     ebx, [r13+63h]
0x1809a215a  test    ebx, ebx
0x1809a215c  jz      loc_1809A22F7
0x1809a2162  mov     rcx, [rsp+4A0h+phProv]; hProv
0x1809a2167  lea     r8, [rsp+4A0h+ppszPath]; pbBuffer
0x1809a216c  mov     edx, 8; dwLen
0x1809a2171  call    cs:__imp_CryptGenRandom
0x1809a2178  nop     dword ptr [rax+rax+00h]
0x1809a217d  test    eax, eax
0x1809a217f  jz      loc_1809A22F7
0x1809a2185  or      rax, 0FFFFFFFFFFFFFFFFh
0x1809a2189  inc     rax
0x1809a218c  cmp     [r14+rax*2], r12w
0x1809a2191  jnz     short loc_1809A2189
0x1809a2193  mov     r9d, 8
0x1809a2199  mov     r10d, r12d
0x1809a219c  sub     r9d, eax
0x1809a219f  test    r9d, r9d
0x1809a21a2  jle     short loc_1809A21E1
0x1809a21a4  mov     r8d, r10d
0x1809a21a7  mov     eax, 38E38E39h
0x1809a21ac  movzx   ecx, byte ptr [rsp+r8+4A0h+ppszPath]
0x1809a21b2  mul     ecx
0x1809a21b4  shr     edx, 3
0x1809a21b7  lea     eax, [rdx+rdx*8]
0x1809a21ba  shl     eax, 2
0x1809a21bd  sub     ecx, eax
0x1809a21bf  movzx   ecx, cl
0x1809a21c2  cmp     cl, 1Ah
0x1809a21c5  sbb     ax, ax
0x1809a21c8  add     r10d, r13d
0x1809a21cb  and     ax, 2Bh
0x1809a21cf  add     ax, 16h
0x1809a21d3  add     ax, cx
0x1809a21d6  mov     [rsp+r8*2+4A0h+var_460], ax
0x1809a21dc  cmp     r10d, r9d
0x1809a21df  jl      short loc_1809A21A4
0x1809a21e1  movsxd  rax, r9d
0x1809a21e4  lea     rcx, [rax+rax]
0x1809a21e8  cmp     rcx, 12h
0x1809a21ec  jnb     loc_1809A233C
0x1809a21f2  mov     [rsp+rcx+4A0h+var_460], r12w
0x1809a21f8  lea     r8, [rbp+3A0h+pszPath]; unsigned __int16 *
0x1809a21ff  mov     r11d, 104h
0x1809a2205  lea     rcx, [rsp+4A0h+FileName]; unsigned __int16 *
0x1809a220a  mov     edx, r11d; unsigned __int64
0x1809a220d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1809a2212  mov     r8, r14; unsigned __int16 *
0x1809a2215  lea     rcx, [rsp+4A0h+FileName]; unsigned __int16 *
0x1809a221a  mov     edx, r11d; unsigned __int64
0x1809a221d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1809a2222  lea     r8, [rsp+4A0h+var_460]; unsigned __int16 *
0x1809a2227  mov     edx, 104h; unsigned __int64
0x1809a222c  lea     rcx, [rsp+4A0h+FileName]; unsigned __int16 *
0x1809a2231  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1809a2236  lea     r8, asc_181401BB0; "."
0x1809a223d  mov     edx, 104h; unsigned __int64
0x1809a2242  lea     rcx, [rsp+4A0h+FileName]; unsigned __int16 *
0x1809a2247  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1809a224c  mov     r8, r15; unsigned __int16 *
0x1809a224f  lea     rcx, [rsp+4A0h+FileName]; unsigned __int16 *
0x1809a2254  mov     edx, 104h; unsigned __int64
0x1809a2259  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1809a225e  lea     rcx, [rsp+4A0h+FileName]; lpFileName
0x1809a2263  call    cs:__imp_GetFileAttributesW
0x1809a226a  nop     dword ptr [rax+rax+00h]
0x1809a226f  cmp     eax, 0FFFFFFFFh
0x1809a2272  jz      short loc_1809A227C
0x1809a2274  sub     ebx, r13d
0x1809a2277  jmp     loc_1809A215A
0x1809a227c  mov     edx, [rbp+3A0h+arg_20]; unsigned __int64
0x1809a2282  lea     r8, [rsp+4A0h+FileName]; unsigned __int16 *
0x1809a2287  mov     rcx, rsi; unsigned __int16 *
0x1809a228a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1809a228f  mov     rax, gs:58h
0x1809a2298  mov     r11d, cs:_tls_index
0x1809a229f  mov     ecx, 10h
0x1809a22a4  mov     rax, [rax+r11*8]
0x1809a22a8  mov     rcx, [rax+rcx]
0x1809a22ac  mov     rdi, [rcx+2C8h]
0x1809a22b3  test    rdi, rdi
0x1809a22b6  jz      short loc_1809A22F4
0x1809a22b8  cmp     [rdi+8], r12d
0x1809a22bc  jz      short loc_1809A22F4
0x1809a22be  mov     rcx, cs:g_hProcessHeap
0x1809a22c5  mov     edx, 210h
0x1809a22ca  call    ??$HeapAlloc@$0A@@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<0>(void *,unsigned __int64)
0x1809a22cf  mov     rbx, rax
0x1809a22d2  test    rax, rax
0x1809a22d5  jz      short loc_1809A22F4
0x1809a22d7  mov     r8, rsi; unsigned __int16 *
0x1809a22da  mov     edx, 104h; unsigned __int64
0x1809a22df  mov     rcx, rax; unsigned __int16 *
0x1809a22e2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1809a22e7  mov     r11, [rdi]
0x1809a22ea  mov     [rbx+208h], r11
0x1809a22f1  mov     [rdi], rbx
0x1809a22f4  mov     edi, r13d
0x1809a22f7  mov     rcx, [rsp+4A0h+phProv]; hProv
0x1809a22fc  test    rcx, rcx
0x1809a22ff  jz      short loc_1809A230F
0x1809a2301  xor     edx, edx; dwFlags
0x1809a2303  call    cs:__imp_CryptReleaseContext
0x1809a230a  nop     dword ptr [rax+rax+00h]
0x1809a230f  mov     eax, edi
0x1809a2311  mov     rcx, [rbp+3A0h+var_40]
0x1809a2318  xor     rcx, rsp; StackCookie
0x1809a231b  call    __security_check_cookie
0x1809a2320  mov     rbx, [rsp+4A0h+arg_0]
0x1809a2328  add     rsp, 470h
0x1809a232f  pop     r15
0x1809a2331  pop     r14
0x1809a2333  pop     r13
0x1809a2335  pop     r12
0x1809a2337  pop     rdi
0x1809a2338  pop     rsi
0x1809a2339  pop     rbp
0x1809a233a  retn
0x1809a233c  call    __report_rangecheckfailure
```
