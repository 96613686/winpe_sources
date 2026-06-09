# CCOMComponentRegistrar::SelfRegisterDLLs(int,ulong)

- ea: `0x180031050`
- end: `0x18003156d`
- name: `?SelfRegisterDLLs@CCOMComponentRegistrar@@EEAAJHK@Z`
- size: `1309`
- prototype: `__int64 __fastcall(CCOMComponentRegistrar *__hidden this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001e60`
- `0x180005944`
- `0x180009f84`
- `0x18000e05c`
- `0x180031050`
- `0x180055880`
- `0x180057010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003140a`
- `msvcrt!_wcsicmp` at `0x18003140a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031541`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031541`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800310b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800310b4`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x1800311dd`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x1800311dd`
- `MfcSubs!??0CString@@QEAA@XZ` at `0x180031189`
- `MfcSubs!??0CString@@QEAA@XZ` at `0x180031189`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripPathW` at `0x1800313f1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripPathW` at `0x1800313f1`
- `OLEAUT32!__imp_RegisterTypeLib` at `0x1800311d0`
- `OLEAUT32!__imp_RegisterTypeLib` at `0x1800311d0`

## string_xrefs

- `0x1800313a2`: `comsvcs.dll`
- `0x1800313ae`: `catsrv.dll`
- `0x1800313ba`: `eventcls.dll`
- `0x1800314db`: `com\complus\src\comcat\registrar\comcomponentregistrar.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCOMComponentRegistrar::SelfRegisterDLLs(CCOMComponentRegistrar *this, __int64 a2, unsigned int a3)
{
  unsigned int v3; // r12d
  int v5; // r13d
  int *v6; // rsi
  int v8; // edi
  int v9; // r8d
  __int64 v10; // r9
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // r14
  _DWORD *v15; // r8
  int v16; // edx
  unsigned int v17; // r15d
  int v18; // r13d
  int j; // edx
  _DWORD *v20; // r8
  __int64 v21; // rax
  BOOL v22; // r15d
  __int64 v23; // rdx
  int v24; // eax
  bool v25; // zf
  __int64 v26; // rax
  int v27; // ecx
  int v28; // eax
  unsigned int v29; // r12d
  int i; // edi
  int v31; // eax
  int v32; // [rsp+30h] [rbp-D0h] BYREF
  int v33; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v34; // [rsp+38h] [rbp-C8h]
  unsigned int v35; // [rsp+3Ch] [rbp-C4h] BYREF
  int v36; // [rsp+40h] [rbp-C0h]
  int v37; // [rsp+44h] [rbp-BCh]
  unsigned int v38; // [rsp+48h] [rbp-B8h] BYREF
  LPCOLESTR szFullPath; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *String1; // [rsp+58h] [rbp-A8h] BYREF
  const wchar_t *v41; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v42; // [rsp+68h] [rbp-98h]
  __int64 v43; // [rsp+70h] [rbp-90h]
  __int64 v44; // [rsp+78h] [rbp-88h]
  int v45; // [rsp+80h] [rbp-80h]
  int v46; // [rsp+84h] [rbp-7Ch]
  WCHAR pszPath[264]; // [rsp+90h] [rbp-70h] BYREF

  v3 = a3;
  v34 = a3;
  v37 = *((_DWORD *)this + 22);
  v5 = v37;
  PrepareSelfRegKey(1);
  v6 = (int *)CoTaskMemAlloc(saturated_mul(v37, 4u));
  if ( !v6 )
    return 2147942414LL;
  v8 = 0;
  v9 = v37 - 1;
  v10 = 0;
  v11 = 0;
  if ( v37 > 0 )
  {
    do
    {
      if ( (*(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 10) + 8 * v11) + 12LL) & 8) != 0 )
      {
        v12 = (int)v10;
        v10 = (unsigned int)(v10 + 1);
      }
      else
      {
        v12 = v9--;
      }
      v6[v12] = v11;
      v11 = (unsigned int)(v11 + 1);
    }
    while ( (int)v11 < v5 );
    v13 = 0;
    v36 = 0;
    do
    {
      v14 = (unsigned int)v13;
      v15 = *(_DWORD **)(*((_QWORD *)this + 10) + 8LL * v6[v13]);
      v16 = v15[3];
      if ( (v16 & 0x840780) == 0 && (v16 & 0x22) != 0 || !v15[2] )
      {
        v8 = (*(__int64 (__fastcall **)(CCOMComponentRegistrar *, _QWORD, _DWORD *, __int64))(*(_QWORD *)this + 88LL))(
               this,
               (unsigned int)v6[(unsigned int)v13],
               v15,
               v10);
        if ( v8 == 1 )
        {
          v21 = *(_QWORD *)&GUID_DefaultAppPartition.Data1 - *((_QWORD *)this + 18);
          if ( *(_QWORD *)&GUID_DefaultAppPartition.Data1 == *((_QWORD *)this + 18) )
            v21 = *(_QWORD *)GUID_DefaultAppPartition.Data4 - *((_QWORD *)this + 19);
          v22 = v21 == 0;
          v35 = 0;
          v32 = -2147467259;
          v8 = CCOMComponentRegistrar::TestUserDll(
                 this,
                 *(struct FileInfo1 **)(*((_QWORD *)this + 10) + 8LL * v6[v14]),
                 0xFu,
                 &v35,
                 &v32);
          if ( v8 < 0 )
            break;
          if ( (v35 & 1) == 0 )
          {
            if ( !v22 || (v23 = *(_QWORD *)(*((_QWORD *)this + 10) + 8LL * v6[v14]), *(_DWORD *)(v23 + 8)) )
            {
              v24 = v32;
            }
            else
            {
              v24 = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 1) + 48LL))(
                      (char *)this + 8,
                      *(_QWORD *)v23);
              v32 = v24;
            }
            v25 = v24 == 0;
            v26 = *(_QWORD *)(*((_QWORD *)this + 10) + 8LL * v6[v14]);
            if ( v25 )
            {
              *(_DWORD *)(v26 + 12) &= ~0x100u;
            }
            else
            {
              *(_DWORD *)(v26 + 12) |= 0x80u;
              (*(void (__fastcall **)(CCOMComponentRegistrar *, __int64, _QWORD))(*(_QWORD *)this + 136LL))(
                this,
                2148598813LL,
                (unsigned int)v6[v14]);
            }
            v32 = 0;
            goto LABEL_65;
          }
          v10 = v3;
          if ( v32 < 0 )
            v8 = v32;
          v27 = (32 * v22 + 16) | 0x40;
          if ( (v3 & 0x2000) == 0 )
            v27 = 32 * v22 + 16;
          v28 = v27 | 0x80;
          if ( (v3 & 0x8000) == 0 )
            v28 = v27;
          v29 = v28 | 0x200;
          if ( (v10 & 0x10000) == 0 )
            v29 = v28;
          if ( (v35 & 2) != 0 )
          {
            v33 = 0;
            String1 = (wchar_t *)L"comsvcs.dll";
            v41 = L"catsrv.dll";
            v42 = L"eventcls.dll";
            v8 = StringCchCopyW(pszPath, 0x104u, **(const unsigned __int16 ***)(*((_QWORD *)this + 10) + 8LL * v6[v14]));
            if ( v8 < 0 )
              break;
            PathStripPathW(pszPath);
            for ( i = 0; i < 3; ++i )
            {
              if ( !_wcsicmp((&String1)[i], pszPath) )
                goto LABEL_57;
            }
            v38 = 0;
            v8 = CCOMComponentRegistrar::TestUserDll(
                   this,
                   *(struct FileInfo1 **)(*((_QWORD *)this + 10) + 8LL * v6[v14]),
                   v29,
                   &v38,
                   &v33);
            if ( v8 < 0 )
              break;
            if ( v33 )
            {
              if ( v22 )
              {
LABEL_57:
                v31 = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 1) + 48LL))(
                        (char *)this + 8,
                        **(_QWORD **)(*((_QWORD *)this + 10) + 8LL * v6[v14]));
                v8 = v31;
                if ( v33 )
                {
                  if ( !v31 )
                  {
                    LODWORD(String1) = 0;
                    WORD2(String1) = 22;
                    LODWORD(v41) = -2147479189;
                    v42 = **(const unsigned __int16 ***)(*((_QWORD *)this + 10) + 8LL * v6[v14]);
                    v43 = 0;
                    v44 = 0;
                    v45 = 0;
                    v46 = 1;
                    CError::WriteToLog(
                      (CError *)&String1,
                      L"com\\complus\\src\\comcat\\registrar\\comcomponentregistrar.cpp",
                      0x328u,
                      v42);
LABEL_64:
                    v3 = v34;
                    goto LABEL_65;
                  }
LABEL_63:
                  *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 10) + 8LL * v6[v14]) + 12LL) |= 0x8000u;
                  (*(void (__fastcall **)(CCOMComponentRegistrar *, __int64, _QWORD))(*(_QWORD *)this + 136LL))(
                    this,
                    2148598810LL,
                    (unsigned int)v6[v14]);
                  v8 = 0;
                  goto LABEL_64;
                }
              }
              else
              {
                if ( v8 )
                  goto LABEL_63;
                v8 = v33;
              }
            }
          }
          if ( !v8 )
            goto LABEL_64;
          goto LABEL_63;
        }
      }
      else if ( (v16 & 0x840590) == 0x10 )
      {
        v17 = 0;
        if ( (int)v15[8] > 0 )
        {
          v18 = v15[8];
          while ( 1 )
          {
            if ( **(_QWORD **)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 10) + 8LL * v6[v14]) + 24LL) + 16LL * v17 + 8) )
            {
              CString::CString((CString *)&szFullPath);
              v8 = (*(__int64 (__fastcall **)(CCOMComponentRegistrar *, _QWORD, _QWORD, LPCOLESTR *))(*(_QWORD *)this + 96LL))(
                     this,
                     (unsigned int)v6[v14],
                     v17,
                     &szFullPath);
              if ( v8 >= 0 )
                v8 = RegisterTypeLib(
                       **(ITypeLib ***)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 10) + 8LL * v6[v14]) + 24LL)
                                      + 16LL * v17
                                      + 8),
                       szFullPath,
                       0);
              CString::~CString((CString *)&szFullPath);
              if ( !v8 )
                goto LABEL_25;
            }
            else
            {
              v8 = -2147418113;
            }
            *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 10) + 8LL * v6[v14]) + 12LL) |= 0x10000u;
            for ( j = 0; j < *((_DWORD *)this + 30); ++j )
            {
              v20 = *(_DWORD **)(*((_QWORD *)this + 14) + 8LL * j);
              if ( v20[6] == v6[v14] && v20[7] == v17 )
                v20[18] = -2146368464;
            }
LABEL_25:
            if ( (int)++v17 >= v18 )
            {
              v5 = v37;
              goto LABEL_64;
            }
          }
        }
      }
LABEL_65:
      v13 = (unsigned int)(v36 + 1);
      v36 = v13;
    }
    while ( (int)v13 < v5 );
  }
  CoTaskMemFree(v6);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180031050  push    rbp
0x180031052  push    rbx
0x180031053  push    rsi
0x180031054  push    rdi
0x180031055  push    r12
0x180031057  push    r13
0x180031059  push    r14
0x18003105b  push    r15
0x18003105d  lea     rbp, [rsp-1B8h]
0x180031065  sub     rsp, 2B8h
0x18003106c  mov     rax, cs:__security_cookie
0x180031073  xor     rax, rsp
0x180031076  mov     [rbp+1F0h+var_50], rax
0x18003107d  mov     r12d, r8d
0x180031080  mov     [rsp+2F0h+var_2B8], r8d
0x180031085  mov     rbx, rcx
0x180031088  movsxd  r13, dword ptr [rcx+58h]
0x18003108c  mov     [rsp+2F0h+var_2AC], r13d
0x180031091  mov     r14d, 1
0x180031097  mov     ecx, r14d
0x18003109a  call    PrepareSelfRegKey
0x18003109f  lea     eax, [r14+3]
0x1800310a3  mul     r13
0x1800310a6  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800310ad  cmovb   rax, rcx
0x1800310b1  mov     rcx, rax; cb
0x1800310b4  call    cs:__imp_CoTaskMemAlloc
0x1800310ba  mov     rsi, rax
0x1800310bd  test    rax, rax
0x1800310c0  jnz     short loc_1800310CC
0x1800310c2  mov     eax, 8007000Eh
0x1800310c7  jmp     loc_18003154A
0x1800310cc  xor     edi, edi
0x1800310ce  lea     r8d, [r13-1]
0x1800310d2  xor     r9d, r9d
0x1800310d5  xor     edx, edx
0x1800310d7  test    r13d, r13d
0x1800310da  jle     loc_18003153E
0x1800310e0  mov     rax, [rbx+50h]
0x1800310e4  mov     rcx, [rax+rdx*8]
0x1800310e8  test    byte ptr [rcx+0Ch], 8
0x1800310ec  jz      short loc_1800310F6
0x1800310ee  movsxd  rax, r9d
0x1800310f1  add     r9d, r14d
0x1800310f4  jmp     short loc_1800310FC
0x1800310f6  movsxd  rax, r8d
0x1800310f9  sub     r8d, r14d
0x1800310fc  mov     [rsi+rax*4], edx
0x1800310ff  add     edx, r14d
0x180031102  cmp     edx, r13d
0x180031105  jl      short loc_1800310E0
0x180031107  xor     eax, eax
0x180031109  mov     [rsp+2F0h+var_2B0], eax
0x18003110d  mov     r14d, eax
0x180031110  movsxd  rcx, dword ptr [rsi+rax*4]
0x180031114  mov     rax, [rbx+50h]
0x180031118  mov     r8, [rax+rcx*8]
0x18003111c  mov     edx, [r8+0Ch]
0x180031120  test    edx, 840780h
0x180031126  setz    cl
0x180031129  test    dl, 22h
0x18003112c  setnz   al
0x18003112f  test    al, cl
0x180031131  jnz     loc_180031246
0x180031137  cmp     dword ptr [r8+8], 0
0x18003113c  jz      loc_180031246
0x180031142  and     edx, 840590h
0x180031148  cmp     edx, 10h
0x18003114b  jnz     loc_18003152B
0x180031151  mov     eax, [r8+20h]
0x180031155  xor     r15d, r15d
0x180031158  test    eax, eax
0x18003115a  jle     loc_18003152B
0x180031160  mov     r13d, eax
0x180031163  mov     r12d, r15d
0x180031166  add     r12, r12
0x180031169  movsxd  rcx, dword ptr [rsi+r14*4]
0x18003116d  mov     rax, [rbx+50h]
0x180031171  mov     rcx, [rax+rcx*8]
0x180031175  mov     rax, [rcx+18h]
0x180031179  mov     rcx, [rax+r12*8+8]
0x18003117e  cmp     qword ptr [rcx], 0
0x180031182  jz      short loc_1800311E9
0x180031184  lea     rcx, [rsp+2F0h+szFullPath]
0x180031189  call    cs:__imp_??0CString@@QEAA@XZ; CString::CString(void)
0x18003118f  mov     rax, [rbx]
0x180031192  lea     r9, [rsp+2F0h+szFullPath]
0x180031197  mov     r8d, r15d
0x18003119a  mov     edx, [rsi+r14*4]
0x18003119e  mov     rcx, rbx
0x1800311a1  mov     rax, [rax+60h]
0x1800311a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800311aa  mov     edi, eax
0x1800311ac  test    eax, eax
0x1800311ae  js      short loc_1800311D8
0x1800311b0  movsxd  rcx, dword ptr [rsi+r14*4]
0x1800311b4  mov     rax, [rbx+50h]
0x1800311b8  mov     rcx, [rax+rcx*8]
0x1800311bc  mov     rax, [rcx+18h]
0x1800311c0  mov     rcx, [rax+r12*8+8]
0x1800311c5  xor     r8d, r8d; szHelpDir
0x1800311c8  mov     rdx, [rsp+2F0h+szFullPath]; szFullPath
0x1800311cd  mov     rcx, [rcx]; ptlib
0x1800311d0  call    cs:__imp_RegisterTypeLib
0x1800311d6  mov     edi, eax
0x1800311d8  lea     rcx, [rsp+2F0h+szFullPath]
0x1800311dd  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x1800311e3  test    edi, edi
0x1800311e5  jz      short loc_180031230
0x1800311e7  jmp     short loc_1800311EE
0x1800311e9  mov     edi, 8000FFFFh
0x1800311ee  movsxd  rcx, dword ptr [rsi+r14*4]
0x1800311f2  mov     rax, [rbx+50h]
0x1800311f6  mov     rdx, [rax+rcx*8]
0x1800311fa  bts     dword ptr [rdx+0Ch], 10h
0x1800311ff  xor     edx, edx
0x180031201  cmp     [rbx+78h], edx
0x180031204  jle     short loc_180031230
0x180031206  movsxd  rcx, edx
0x180031209  mov     rax, [rbx+70h]
0x18003120d  mov     r8, [rax+rcx*8]
0x180031211  mov     eax, [rsi+r14*4]
0x180031215  cmp     [r8+18h], eax
0x180031219  jnz     short loc_180031229
0x18003121b  cmp     [r8+1Ch], r15d
0x18003121f  jnz     short loc_180031229
0x180031221  mov     dword ptr [r8+48h], 80110430h
0x180031229  inc     edx
0x18003122b  cmp     edx, [rbx+78h]
0x18003122e  jl      short loc_180031206
0x180031230  inc     r15d
0x180031233  cmp     r15d, r13d
0x180031236  jl      loc_180031163
0x18003123c  mov     r13d, [rsp+2F0h+var_2AC]
0x180031241  jmp     loc_180031526
0x180031246  mov     rax, [rbx]
0x180031249  mov     edx, [rsi+r14*4]
0x18003124d  mov     rcx, rbx
0x180031250  mov     rax, [rax+58h]
0x180031254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031259  mov     edi, eax
0x18003125b  cmp     eax, 1
0x18003125e  jnz     loc_18003152B
0x180031264  mov     rax, qword ptr cs:GUID_DefaultAppPartition.Data1
0x18003126b  sub     rax, [rbx+90h]
0x180031272  jnz     short loc_180031282
0x180031274  mov     rax, qword ptr cs:GUID_DefaultAppPartition.Data4
0x18003127b  sub     rax, [rbx+98h]
0x180031282  xor     r15d, r15d
0x180031285  test    rax, rax
0x180031288  setz    r15b
0x18003128c  mov     [rsp+2F0h+var_2B4], 0
0x180031294  mov     [rsp+2F0h+var_2C0], 80004005h
0x18003129c  movsxd  rax, dword ptr [rsi+r14*4]
0x1800312a0  mov     rdx, [rbx+50h]
0x1800312a4  lea     rcx, [rsp+2F0h+var_2C0]
0x1800312a9  mov     [rsp+2F0h+var_2D0], rcx; int *
0x1800312ae  lea     r9, [rsp+2F0h+var_2B4]; unsigned int *
0x1800312b3  mov     r8d, 0Fh; unsigned int
0x1800312b9  mov     rdx, [rdx+rax*8]; struct FileInfo1 *
0x1800312bd  mov     rcx, rbx; this
0x1800312c0  call    ?TestUserDll@CCOMComponentRegistrar@@AEAAJPEAUFileInfo1@@KPEAKPEAJ@Z; CCOMComponentRegistrar::TestUserDll(FileInfo1 *,ulong,ulong *,long *)
0x1800312c5  mov     edi, eax
0x1800312c7  test    eax, eax
0x1800312c9  js      loc_18003153E
0x1800312cf  test    byte ptr [rsp+2F0h+var_2B4], 1
0x1800312d4  jnz     short loc_18003134E
0x1800312d6  test    r15d, r15d
0x1800312d9  jz      short loc_180031306
0x1800312db  movsxd  rcx, dword ptr [rsi+r14*4]
0x1800312df  mov     rax, [rbx+50h]
0x1800312e3  mov     rdx, [rax+rcx*8]
0x1800312e7  cmp     dword ptr [rdx+8], 0
0x1800312eb  jnz     short loc_180031306
0x1800312ed  lea     rcx, [rbx+8]
0x1800312f1  mov     rax, [rcx]
0x1800312f4  mov     rdx, [rdx]
0x1800312f7  mov     rax, [rax+30h]
0x1800312fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031300  mov     [rsp+2F0h+var_2C0], eax
0x180031304  jmp     short loc_18003130A
0x180031306  mov     eax, [rsp+2F0h+var_2C0]
0x18003130a  movsxd  rcx, dword ptr [rsi+r14*4]
0x18003130e  mov     rdx, [rbx+50h]
0x180031312  test    eax, eax
0x180031314  mov     rax, [rdx+rcx*8]
0x180031318  jz      short loc_18003133C
0x18003131a  bts     dword ptr [rax+0Ch], 7
0x18003131f  mov     rax, [rbx]
0x180031322  mov     r8d, [rsi+r14*4]
0x180031326  mov     edx, 8011041Dh
0x18003132b  mov     rcx, rbx
0x18003132e  mov     rax, [rax+88h]
0x180031335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003133a  jmp     short loc_180031341
0x18003133c  btr     dword ptr [rax+0Ch], 8
0x180031341  mov     [rsp+2F0h+var_2C0], 0
0x180031349  jmp     loc_18003152B
0x18003134e  mov     r9d, r12d
0x180031351  mov     eax, [rsp+2F0h+var_2C0]
0x180031355  test    eax, eax
0x180031357  cmovs   edi, eax
0x18003135a  mov     eax, r15d
0x18003135d  shl     eax, 5
0x180031360  add     eax, 10h
0x180031363  mov     ecx, eax
0x180031365  or      ecx, 40h
0x180031368  bt      r12d, 0Dh
0x18003136d  cmovnb  ecx, eax
0x180031370  mov     eax, ecx
0x180031372  bts     eax, 7
0x180031376  bt      r12d, 0Fh
0x18003137b  cmovnb  eax, ecx
0x18003137e  mov     r12d, eax
0x180031381  bts     r12d, 9
0x180031386  bt      r9d, 10h
0x18003138b  cmovnb  r12d, eax
0x18003138f  test    byte ptr [rsp+2F0h+var_2B4], 2
0x180031394  jz      loc_1800314F4
0x18003139a  mov     [rsp+2F0h+var_2BC], 0
0x1800313a2  lea     rax, ModuleName; "comsvcs.dll"
0x1800313a9  mov     [rsp+2F0h+String1], rax
0x1800313ae  lea     rax, aCatsrvDll_0; "catsrv.dll"
0x1800313b5  mov     [rsp+2F0h+var_290], rax
0x1800313ba  lea     rax, aEventclsDll; "eventcls.dll"
0x1800313c1  mov     [rsp+2F0h+var_288], rax
0x1800313c6  movsxd  r8, dword ptr [rsi+r14*4]
0x1800313ca  mov     rax, [rbx+50h]
0x1800313ce  mov     r8, [rax+r8*8]
0x1800313d2  mov     r8, [r8]; unsigned __int16 *
0x1800313d5  mov     edx, 104h; unsigned __int64
0x1800313da  lea     rcx, [rbp+1F0h+pszPath]; unsigned __int16 *
0x1800313de  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800313e3  mov     edi, eax
0x1800313e5  test    eax, eax
0x1800313e7  js      loc_18003153E
0x1800313ed  lea     rcx, [rbp+1F0h+pszPath]; pszPath
0x1800313f1  call    cs:__imp_PathStripPathW
0x1800313f7  xor     edi, edi
0x1800313f9  cmp     edi, 3
0x1800313fc  jge     short loc_180031418
0x1800313fe  movsxd  rcx, edi
0x180031401  lea     rdx, [rbp+1F0h+pszPath]; String2
0x180031405  mov     rcx, [rsp+rcx*8+2F0h+String1]; String1
0x18003140a  call    cs:__imp__wcsicmp
0x180031410  test    eax, eax
0x180031412  jz      short loc_180031465
0x180031414  inc     edi
0x180031416  jmp     short loc_1800313F9
0x180031418  mov     [rsp+2F0h+var_2A8], 0
0x180031420  movsxd  rax, dword ptr [rsi+r14*4]
0x180031424  mov     rdx, [rbx+50h]
0x180031428  lea     rcx, [rsp+2F0h+var_2BC]
0x18003142d  mov     [rsp+2F0h+var_2D0], rcx; int *
0x180031432  lea     r9, [rsp+2F0h+var_2A8]; unsigned int *
0x180031437  mov     r8d, r12d; unsigned int
0x18003143a  mov     rdx, [rdx+rax*8]; struct FileInfo1 *
0x18003143e  mov     rcx, rbx; this
0x180031441  call    ?TestUserDll@CCOMComponentRegistrar@@AEAAJPEAUFileInfo1@@KPEAKPEAJ@Z; CCOMComponentRegistrar::TestUserDll(FileInfo1 *,ulong,ulong *,long *)
0x180031446  mov     edi, eax
0x180031448  test    eax, eax
0x18003144a  js      loc_18003153E
0x180031450  mov     eax, [rsp+2F0h+var_2BC]
0x180031454  test    eax, eax
0x180031456  jz      loc_1800314F4
0x18003145c  test    r15d, r15d
0x18003145f  jz      loc_1800314EE
0x180031465  lea     rcx, [rbx+8]
0x180031469  mov     r8, [rcx]
0x18003146c  movsxd  rdx, dword ptr [rsi+r14*4]
0x180031470  mov     rax, [rbx+50h]
0x180031474  mov     rdx, [rax+rdx*8]
0x180031478  mov     rdx, [rdx]
0x18003147b  mov     rax, [r8+30h]
0x18003147f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031484  mov     edi, eax
0x180031486  cmp     [rsp+2F0h+var_2BC], 0
0x18003148b  jz      short loc_1800314F4
0x18003148d  test    eax, eax
0x18003148f  jnz     short loc_1800314F8
0x180031491  mov     dword ptr [rsp+2F0h+String1], eax
0x180031495  lea     eax, [rdi+16h]
0x180031498  mov     word ptr [rsp+2F0h+String1+4], ax
0x18003149d  mov     dword ptr [rsp+2F0h+var_290], 8000116Bh
0x1800314a5  movsxd  rcx, dword ptr [rsi+r14*4]
0x1800314a9  mov     rax, [rbx+50h]
0x1800314ad  mov     rcx, [rax+rcx*8]
0x1800314b1  mov     r9, [rcx]; unsigned __int16 *
0x1800314b4  mov     [rsp+2F0h+var_288], r9
0x1800314b9  mov     [rsp+2F0h+var_280], 0
0x1800314c2  mov     [rsp+2F0h+var_278], 0
0x1800314cb  mov     [rbp+1F0h+var_270], edi
0x1800314ce  mov     [rbp+1F0h+var_26C], 1
0x1800314d5  mov     r8d, 328h; unsigned int
0x1800314db  lea     rdx, aComComplusSrcC_3; "com\\complus\\src\\comcat\\registrar\\c"...
0x1800314e2  lea     rcx, [rsp+2F0h+String1]; this
0x1800314e7  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x1800314ec  jmp     short loc_180031526
0x1800314ee  test    edi, edi
0x1800314f0  jnz     short loc_1800314F8
  ... truncated ...
```
