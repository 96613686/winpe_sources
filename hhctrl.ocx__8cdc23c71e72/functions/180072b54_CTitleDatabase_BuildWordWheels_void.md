# CTitleDatabase::BuildWordWheels(void)

- ea: `0x180072b54`
- end: `0x18007312d`
- name: `?BuildWordWheels@CTitleDatabase@@QEAAHXZ`
- size: `1497`
- prototype: `__int64 __fastcall(CTitleDatabase *__hidden this)`
- caller_count: `1`
- callee_count: `31`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800756e0`

## callees

- `0x180001728`
- `0x18000b3f0`
- `0x18000baf0`
- `0x1800276ec`
- `0x180027714`
- `0x18002a830`
- `0x18002ae50`
- `0x18002aee0`
- `0x18002b1ec`
- `0x18003b90c`
- `0x18003b9e4`
- `0x180043cb0`
- `0x18004f538`
- `0x18006080c`
- `0x18006a7ac`
- `0x1800729c8`
- `0x1800729f0`
- `0x180072b54`
- `0x1800737c8`
- `0x180073808`
- `0x180073870`
- `0x180074284`
- `0x1800743d4`
- `0x180074538`
- `0x18007455c`
- `0x180074580`
- `0x180074e14`
- `0x1800757c8`
- `0x180075a18`
- `0x180075c90`
- `0x180078010`

## import_xrefs

- `KERNEL32!DeleteFileA` at `0x180072b98`
- `KERNEL32!DeleteFileA` at `0x180072b98`
- `KERNEL32!lstrlenW` at `0x180072e58`
- `KERNEL32!lstrlenW` at `0x180072e80`
- `KERNEL32!lstrlenW` at `0x180072e58`
- `KERNEL32!lstrlenW` at `0x180072e80`
- `KERNEL32!Sleep` at `0x180072cc5`
- `KERNEL32!Sleep` at `0x180072e1f`
- `KERNEL32!Sleep` at `0x180072f5f`
- `KERNEL32!Sleep` at `0x180072cc5`
- `KERNEL32!Sleep` at `0x180072e1f`
- `KERNEL32!Sleep` at `0x180072f5f`

## string_xrefs

- `0x180072bed`: `AssociativeLinks`
- `0x180072be2`: `KeywordLinks`

## pseudocode

```c
__int64 __fastcall CTitleDatabase::BuildWordWheels(CTitleDatabase *this)
{
  __int64 v2; // rbx
  signed int v3; // r13d
  CSubFileSystem *v4; // rax
  CWordWheelCompiler *v5; // rbx
  unsigned int v6; // edx
  CSubFileSystem *v7; // r15
  struct CWordWheel *KeywordLinks; // rsi
  signed int v9; // edi
  signed int v10; // r15d
  struct CTitleMapEntry *v11; // r13
  _DWORD *v12; // rdi
  const char *IndexFileName; // rax
  unsigned int v14; // edx
  unsigned int v15; // edx
  int v16; // r12d
  __int64 v17; // rax
  signed int Count; // eax
  signed int i; // r15d
  int v20; // eax
  int v21; // esi
  int v22; // r10d
  int j; // edx
  __int64 v24; // r8
  unsigned int v25; // edx
  CFileSystem *v26; // rax
  CFileSystem *v27; // rsi
  int (*v28)(const void *, const void *); // rdx
  CSubFileSystem *v29; // rax
  const char *v30; // rdx
  CSubFileSystem *v31; // rdi
  unsigned int v32; // edx
  signed int k; // r15d
  const char *ShortName; // r12
  unsigned int Language; // eax
  __int64 v36; // rbx
  unsigned int v37; // edx
  __int16 v39; // [rsp+30h] [rbp-D0h] BYREF
  CSubFileSystem *v40; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v41; // [rsp+40h] [rbp-C0h] BYREF
  signed int v42; // [rsp+44h] [rbp-BCh]
  int v43; // [rsp+48h] [rbp-B8h]
  __int64 v44; // [rsp+50h] [rbp-B0h]
  struct CWordWheel *v45; // [rsp+58h] [rbp-A8h]
  _DWORD *v46; // [rsp+60h] [rbp-A0h]
  WCHAR String[2]; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v48[253]; // [rsp+7Ch] [rbp-84h]

  if ( (unsigned int)IsFile(*((const char **)this + 2)) )
    DeleteFileA(*((LPCSTR *)this + 2));
  v2 = *((_QWORD *)this + 40);
  if ( !v2 )
    return 0;
  CTitleMap::Init(*((CTitleMap **)this + 40));
  v3 = *(_DWORD *)(v2 + 16);
  v41 = v3;
  v4 = (CSubFileSystem *)operator new(0x178u);
  v40 = v4;
  v5 = v4;
  if ( !v4 )
    return 0;
  *((_QWORD *)v4 + 4) = *((_QWORD *)this + 2);
  *((_QWORD *)v4 + 5) = L"KeywordLinks";
  *((_QWORD *)v4 + 6) = L"AssociativeLinks";
  *((_DWORD *)v4 + 6) = 0;
  *((_QWORD *)v4 + 40) = 0;
  *((_QWORD *)v4 + 41) = 0;
  *((_QWORD *)v4 + 42) = 0;
  *(_QWORD *)v4 = 0;
  *((_QWORD *)v4 + 1) = 0;
  *((_QWORD *)v4 + 2) = 0;
  *((_QWORD *)v4 + 43) = 0;
  *((_QWORD *)v4 + 44) = 0;
  *((_QWORD *)v4 + 45) = 0;
  *((_QWORD *)v4 + 46) = 0;
  *((_DWORD *)v4 + 14) = -1;
  if ( (unsigned int)CWordWheelCompiler::Initialize(v4) )
  {
LABEL_6:
    CWordWheelCompiler::`scalar deleting destructor'(v5, v6);
    return 0;
  }
  v7 = (CSubFileSystem *)*((_QWORD *)v5 + 2);
  v44 = 0;
  v40 = v7;
  (*(void (__fastcall **)(CSubFileSystem *, __int64, _QWORD))(*(_QWORD *)v7 + 88LL))(v7, 1, 0);
  (*(void (__fastcall **)(CSubFileSystem *, __int64, _QWORD))(*(_QWORD *)v7 + 80LL))(v7, 100, 0);
  KeywordLinks = 0;
  v45 = 0;
  v9 = 0;
LABEL_8:
  v42 = v9;
  if ( v9 < v3 )
  {
    NextAnimation();
    Sleep(0);
    v10 = v9 + 1;
    v11 = CTitleMap::GetAt(*((CTitleMap **)this + 40), v9);
    v43 = v9 + 1;
    *(_DWORD *)v11 = v9 + 1;
    v46 = operator new(0x158u);
    v12 = v46;
    if ( !v46 )
      goto LABEL_6;
    IndexFileName = CExTitle::GetIndexFileName(*((CExTitle **)v11 + 1));
    *v46 = 0;
    *((_QWORD *)v12 + 38) = 0;
    *((_QWORD *)v12 + 1) = 0;
    v12[78] = 0;
    *((_QWORD *)v12 + 40) = 0;
    *((_QWORD *)v12 + 41) = 0;
    *((_QWORD *)v12 + 42) = 0;
    *((_QWORD *)v12 + 36) = 0;
    *((_QWORD *)v12 + 37) = 0;
    *((_QWORD *)v12 + 2) = IndexFileName;
    if ( !(unsigned int)CTitleDatabase::Initialize((CTitleDatabase *)v12, 0) )
    {
      CTitleDatabase::`scalar deleting destructor'((CTitleDatabase *)v12, v14);
      goto LABEL_35;
    }
    *((_QWORD *)v11 + 2) = v12;
    *((_QWORD *)v11 + 4) = CTitleDatabase::GetKeywordLinks((CTitleDatabase *)v12);
    CTitleDatabase::Init((CTitleDatabase *)v12);
    v16 = 1;
    *((_QWORD *)v11 + 5) = *((_QWORD *)v12 + 42);
    while ( 1 )
    {
      if ( v16 > 2 )
      {
        CTitleDatabase::`scalar deleting destructor'((CTitleDatabase *)v12, v15);
        v10 = v43;
        *((_QWORD *)v11 + 2) = 0;
LABEL_35:
        v3 = v41;
        v9 = v10;
        goto LABEL_8;
      }
      if ( v16 == 1 )
      {
        KeywordLinks = CTitleDatabase::GetKeywordLinks((CTitleDatabase *)v12);
        v45 = KeywordLinks;
        v17 = *(_QWORD *)v5;
      }
      else
      {
        if ( v16 != 2 )
          goto LABEL_19;
        CTitleDatabase::Init((CTitleDatabase *)v12);
        KeywordLinks = (struct CWordWheel *)*((_QWORD *)v12 + 42);
        v17 = *((_QWORD *)v5 + 1);
        v45 = KeywordLinks;
      }
      v44 = v17;
LABEL_19:
      if ( KeywordLinks )
      {
        Count = CWordWheel::GetCount(KeywordLinks);
        LODWORD(v46) = Count;
        for ( i = 0; i < Count; ++i )
        {
          if ( i == 200 * (i / 200) )
          {
            NextAnimation();
            Sleep(0);
          }
          CWordWheel::Init(KeywordLinks);
          if ( (*(int (__fastcall **)(_QWORD, _QWORD, WCHAR *, __int64))(**((_QWORD **)KeywordLinks + 5) + 80LL))(
                 *((_QWORD *)KeywordLinks + 5),
                 (unsigned int)i,
                 String,
                 1016) >= 0 )
          {
            v20 = 2 * lstrlenW(String) + 2;
            v21 = v20 + 16;
            if ( (*((_BYTE *)String + v20) & 2) != 0 )
            {
              v21 += 2 * lstrlenW((WCHAR *)((char *)String + v21)) + 2;
            }
            else
            {
              v22 = *(_DWORD *)((char *)v48 + v20);
              for ( j = 0; j < v22; ++j )
              {
                v24 = v21;
                if ( (unsigned __int64)v21 >= 0x3F8 )
                  OOM();
                v21 += 4;
                *(_DWORD *)((char *)String + v24) = *(_DWORD *)((char *)&String[2 * j + 8] + v20)
                                                  + (v42 << 20)
                                                  + 0x100000;
              }
            }
            (*(void (__fastcall **)(CSubFileSystem *, __int64, WCHAR *, _QWORD, int))(*(_QWORD *)v40 + 80LL))(
              v40,
              100,
              String,
              (unsigned int)v21,
              2);
            (*(void (__fastcall **)(__int64, const wchar_t *, CSubFileSystem *))(*(_QWORD *)v44 + 40LL))(
              v44,
              L"OCC",
              v40);
            KeywordLinks = v45;
          }
          Count = (int)v46;
        }
      }
      ++v16;
    }
  }
  (*(void (__fastcall **)(CSubFileSystem *))(*(_QWORD *)v40 + 112LL))(v40);
  NextAnimation();
  Sleep(0);
  CWordWheelCompiler::Build(v5);
  CWordWheelCompiler::`scalar deleting destructor'(v5, v25);
  v26 = (CFileSystem *)operator new(0x118u);
  v40 = v26;
  v27 = v26;
  if ( !v26
    || (*(_QWORD *)v26 = 0, *((_QWORD *)v26 + 1) = 0, *((_BYTE *)v26 + 16) = 0, (int)CFileSystem::Init(v26) < 0)
    || CFileSystem::Open(v27, *((const char **)this + 2), 0x12u) < 0 )
  {
LABEL_48:
    StopAnimation();
    SetBusy(0);
    return 0;
  }
  CTitleMap::Sort(*((CTitleMap **)this + 40), v28);
  v29 = (CSubFileSystem *)operator new(0x120u);
  v40 = v29;
  v31 = v29;
  if ( !v29 )
  {
    CFileSystem::`scalar deleting destructor'(v27, (unsigned int)v30);
    goto LABEL_48;
  }
  *(_QWORD *)v29 = v27;
  *((_QWORD *)v29 + 1) = 0;
  *((_QWORD *)v29 + 2) = 0;
  *((_BYTE *)v29 + 24) = 0;
  CSubFileSystem::CreateSub(v29, v30);
  v39 = v3;
  CSubFileSystem::WriteSub(v31, &v39, 2);
  for ( k = 0; k < v3; ++k )
  {
    v36 = (__int64)CTitleMap::GetAt(*((CTitleMap **)this + 40), k);
    ShortName = CTitleMapEntry::GetShortName((CTitleMapEntry *)v36);
    CTitleMapEntry::GetFileTime((CTitleMapEntry *)v36);
    Language = CTitleMapEntry::GetLanguage((CTitleMapEntry *)v36);
    LODWORD(v36) = 0;
    v41 = Language;
    if ( ShortName )
    {
      v36 = -1;
      do
        ++v36;
      while ( ShortName[v36] );
    }
    v39 = v36;
    CSubFileSystem::WriteSub(v31, &v39, 2);
    CSubFileSystem::WriteSub(v31, ShortName, v36);
    CSubFileSystem::WriteSub(v31, &v40, 8);
    CSubFileSystem::WriteSub(v31, &v41, 4);
  }
  CSubFileSystem::`scalar deleting destructor'(v31, v32);
  CFileSystem::`scalar deleting destructor'(v27, v37);
  return 1;
}

```

## disassembly

```asm
0x180072b54  push    rbp
0x180072b56  push    rbx
0x180072b57  push    rsi
0x180072b58  push    rdi
0x180072b59  push    r12
0x180072b5b  push    r13
0x180072b5d  push    r14
0x180072b5f  push    r15
0x180072b61  lea     rbp, [rsp-388h]
0x180072b69  sub     rsp, 488h
0x180072b70  mov     rax, cs:__security_cookie
0x180072b77  xor     rax, rsp
0x180072b7a  mov     [rbp+3C0h+var_50], rax
0x180072b81  mov     r14, rcx
0x180072b84  mov     rcx, [rcx+10h]; char *
0x180072b88  call    ?IsFile@@YAHPEBD@Z; IsFile(char const *)
0x180072b8d  xor     r12d, r12d
0x180072b90  test    eax, eax
0x180072b92  jz      short loc_180072B9E
0x180072b94  mov     rcx, [r14+10h]; lpFileName
0x180072b98  call    cs:__imp_DeleteFileA
0x180072b9e  mov     rbx, [r14+140h]
0x180072ba5  test    rbx, rbx
0x180072ba8  jz      loc_180073108
0x180072bae  mov     rcx, rbx; this
0x180072bb1  call    ?Init@CTitleMap@@AEAAHXZ; CTitleMap::Init(void)
0x180072bb6  mov     r13d, [rbx+10h]
0x180072bba  mov     ecx, 178h; Size
0x180072bbf  mov     [rsp+4C0h+var_480], r13d
0x180072bc4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180072bc9  mov     [rsp+4C0h+var_488], rax
0x180072bce  mov     rbx, rax
0x180072bd1  test    rax, rax
0x180072bd4  jz      loc_180073108
0x180072bda  mov     rax, [r14+10h]
0x180072bde  mov     [rbx+20h], rax
0x180072be2  lea     rax, aKeywordlinks; "KeywordLinks"
0x180072be9  mov     [rbx+28h], rax
0x180072bed  lea     rax, aAssociativelin; "AssociativeLinks"
0x180072bf4  mov     [rbx+30h], rax
0x180072bf8  mov     [rbx+18h], r12d
0x180072bfc  mov     [rbx+140h], r12
0x180072c03  mov     [rbx+148h], r12
0x180072c0a  mov     [rbx+150h], r12
0x180072c11  mov     [rbx], r12
0x180072c14  mov     [rbx+8], r12
0x180072c18  mov     [rbx+10h], r12
0x180072c1c  mov     [rbx+158h], r12
0x180072c23  mov     [rbx+160h], r12
0x180072c2a  mov     [rbx+168h], r12
0x180072c31  mov     [rbx+170h], r12
0x180072c38  mov     dword ptr [rbx+38h], 0FFFFFFFFh
0x180072c3f  test    rbx, rbx
0x180072c42  jz      loc_180073108
0x180072c48  mov     rcx, rbx; this
0x180072c4b  call    ?Initialize@CWordWheelCompiler@@QEAAJXZ; CWordWheelCompiler::Initialize(void)
0x180072c50  test    eax, eax
0x180072c52  jz      short loc_180072C61
0x180072c54  mov     rcx, rbx; this
0x180072c57  call    ??_GCWordWheelCompiler@@QEAAPEAXI@Z; CWordWheelCompiler::`scalar deleting destructor'(uint)
0x180072c5c  jmp     loc_180073108
0x180072c61  mov     r15, [rbx+10h]
0x180072c65  xor     r9d, r9d
0x180072c68  xor     r8d, r8d
0x180072c6b  mov     [rsp+4C0h+var_470], r12
0x180072c70  mov     rcx, r15
0x180072c73  mov     [rsp+4C0h+var_488], r15
0x180072c78  mov     rax, [r15]
0x180072c7b  lea     edx, [r9+1]
0x180072c7f  mov     rax, [rax+58h]
0x180072c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072c88  mov     rax, [r15]
0x180072c8b  xor     r9d, r9d
0x180072c8e  xor     r8d, r8d
0x180072c91  mov     [rsp+4C0h+var_4A0], r12d
0x180072c96  mov     rcx, r15
0x180072c99  mov     rax, [rax+50h]
0x180072c9d  lea     edx, [r9+64h]
0x180072ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072ca6  mov     rsi, r12
0x180072ca9  mov     [rsp+4C0h+var_468], r12
0x180072cae  mov     edi, r12d
0x180072cb1  mov     [rsp+4C0h+var_47C], edi
0x180072cb5  cmp     edi, r13d
0x180072cb8  jge     loc_180072F47
0x180072cbe  call    ?NextAnimation@@YAXXZ; NextAnimation(void)
0x180072cc3  xor     ecx, ecx; dwMilliseconds
0x180072cc5  call    cs:__imp_Sleep
0x180072ccb  mov     rcx, [r14+140h]; this
0x180072cd2  mov     edx, edi; unsigned int
0x180072cd4  call    ?GetAt@CTitleMap@@QEAAPEAVCTitleMapEntry@@K@Z; CTitleMap::GetAt(ulong)
0x180072cd9  lea     r15d, [rdi+1]
0x180072cdd  mov     ecx, 158h; Size
0x180072ce2  mov     r13, rax
0x180072ce5  mov     [rsp+4C0h+var_478], r15d
0x180072cea  mov     [rax], r15d
0x180072ced  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180072cf2  mov     [rsp+4C0h+var_460], rax
0x180072cf7  mov     rdi, rax
0x180072cfa  test    rax, rax
0x180072cfd  jz      loc_180072C54
0x180072d03  mov     rcx, [r13+8]; this
0x180072d07  call    ?GetIndexFileName@CExTitle@@QEAAPEBDXZ; CExTitle::GetIndexFileName(void)
0x180072d0c  mov     [rdi], r12d
0x180072d0f  mov     [rdi+130h], r12
0x180072d16  mov     [rdi+8], r12
0x180072d1a  mov     [rdi+138h], r12d
0x180072d21  mov     [rdi+140h], r12
0x180072d28  mov     [rdi+148h], r12
0x180072d2f  mov     [rdi+150h], r12
0x180072d36  mov     [rdi+120h], r12
0x180072d3d  mov     [rdi+128h], r12
0x180072d44  mov     [rdi+10h], rax
0x180072d48  test    rdi, rdi
0x180072d4b  jz      loc_180072C54
0x180072d51  xor     edx, edx; char *
0x180072d53  mov     rcx, rdi; this
0x180072d56  call    ?Initialize@CTitleDatabase@@QEAAHPEBD@Z; CTitleDatabase::Initialize(char const *)
0x180072d5b  mov     rcx, rdi; this
0x180072d5e  test    eax, eax
0x180072d60  jnz     short loc_180072D6C
0x180072d62  call    ??_GCTitleDatabase@@QEAAPEAXI@Z; CTitleDatabase::`scalar deleting destructor'(uint)
0x180072d67  jmp     loc_180072F34
0x180072d6c  mov     [r13+10h], rdi
0x180072d70  call    ?GetKeywordLinks@CTitleDatabase@@QEAAPEAVCWordWheel@@XZ; CTitleDatabase::GetKeywordLinks(void)
0x180072d75  mov     rcx, rdi; this
0x180072d78  mov     [r13+20h], rax
0x180072d7c  call    ?Init@CTitleDatabase@@AEAAHXZ; CTitleDatabase::Init(void)
0x180072d81  mov     rax, [rdi+150h]
0x180072d88  mov     r12d, 1
0x180072d8e  mov     [r13+28h], rax
0x180072d92  cmp     r12d, 2
0x180072d96  jg      loc_180072F20
0x180072d9c  cmp     r12d, 1
0x180072da0  jnz     short loc_180072DB7
0x180072da2  mov     rcx, rdi; this
0x180072da5  call    ?GetKeywordLinks@CTitleDatabase@@QEAAPEAVCWordWheel@@XZ; CTitleDatabase::GetKeywordLinks(void)
0x180072daa  mov     rsi, rax
0x180072dad  mov     [rsp+4C0h+var_468], rax
0x180072db2  mov     rax, [rbx]
0x180072db5  jmp     short loc_180072DD5
0x180072db7  cmp     r12d, 2
0x180072dbb  jnz     short loc_180072DDA
0x180072dbd  mov     rcx, rdi; this
0x180072dc0  call    ?Init@CTitleDatabase@@AEAAHXZ; CTitleDatabase::Init(void)
0x180072dc5  mov     rsi, [rdi+150h]
0x180072dcc  mov     rax, [rbx+8]
0x180072dd0  mov     [rsp+4C0h+var_468], rsi
0x180072dd5  mov     [rsp+4C0h+var_470], rax
0x180072dda  test    rsi, rsi
0x180072ddd  jz      loc_180072F18
0x180072de3  mov     rcx, rsi; this
0x180072de6  call    ?GetCount@CWordWheel@@QEAAKXZ; CWordWheel::GetCount(void)
0x180072deb  mov     dword ptr [rsp+4C0h+var_460], eax
0x180072def  xor     r15d, r15d
0x180072df2  cmp     r15d, eax
0x180072df5  jge     loc_180072F18
0x180072dfb  mov     eax, 51EB851Fh
0x180072e00  imul    r15d
0x180072e03  sar     edx, 6
0x180072e06  mov     eax, edx
0x180072e08  shr     eax, 1Fh
0x180072e0b  add     edx, eax
0x180072e0d  imul    ecx, edx, 0C8h
0x180072e13  cmp     r15d, ecx
0x180072e16  jnz     short loc_180072E25
0x180072e18  call    ?NextAnimation@@YAXXZ; NextAnimation(void)
0x180072e1d  xor     ecx, ecx; dwMilliseconds
0x180072e1f  call    cs:__imp_Sleep
0x180072e25  mov     rcx, rsi; this
0x180072e28  call    ?Init@CWordWheel@@AEAAHXZ; CWordWheel::Init(void)
0x180072e2d  mov     rcx, [rsi+28h]
0x180072e31  lea     r8, [rsp+4C0h+String]
0x180072e36  mov     r9d, 3F8h
0x180072e3c  mov     edx, r15d
0x180072e3f  mov     rax, [rcx]
0x180072e42  mov     rax, [rax+50h]
0x180072e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072e4b  test    eax, eax
0x180072e4d  js      loc_180072ED4
0x180072e53  lea     rcx, [rsp+4C0h+String]; lpString
0x180072e58  call    cs:__imp_lstrlenW
0x180072e5e  lea     r9, [rsp+4C0h+String]
0x180072e63  lea     eax, ds:2[rax*2]
0x180072e6a  movsxd  rdx, eax
0x180072e6d  lea     esi, [rax+10h]
0x180072e70  movsxd  rax, esi
0x180072e73  add     r9, rax
0x180072e76  test    byte ptr [rsp+rdx+4C0h+String], 2
0x180072e7b  jz      short loc_180072EE0
0x180072e7d  mov     rcx, r9; lpString
0x180072e80  call    cs:__imp_lstrlenW
0x180072e86  lea     esi, [rsi+rax*2]
0x180072e89  add     esi, 2
0x180072e8c  mov     rcx, [rsp+4C0h+var_488]
0x180072e91  lea     r8, [rsp+4C0h+String]
0x180072e96  mov     r9d, esi
0x180072e99  mov     [rsp+4C0h+var_4A0], 2
0x180072ea1  mov     edx, 64h ; 'd'
0x180072ea6  mov     rax, [rcx]
0x180072ea9  mov     rax, [rax+50h]
0x180072ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072eb2  mov     rcx, [rsp+4C0h+var_470]
0x180072eb7  lea     rdx, aOcc; "OCC"
0x180072ebe  mov     r8, [rsp+4C0h+var_488]
0x180072ec3  mov     rax, [rcx]
0x180072ec6  mov     rax, [rax+28h]
0x180072eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072ecf  mov     rsi, [rsp+4C0h+var_468]
0x180072ed4  mov     eax, dword ptr [rsp+4C0h+var_460]
0x180072ed8  inc     r15d
0x180072edb  jmp     loc_180072DF2
0x180072ee0  mov     r10d, [rsp+rdx+4C0h+var_444]
0x180072ee5  xor     edx, edx
0x180072ee7  cmp     edx, r10d
0x180072eea  jge     short loc_180072E8C
0x180072eec  movsxd  r8, esi
0x180072eef  cmp     r8, 3F8h
0x180072ef6  jnb     short loc_180072F41
0x180072ef8  mov     ecx, [rsp+4C0h+var_47C]
0x180072efc  add     esi, 4
0x180072eff  shl     ecx, 14h
0x180072f02  movsxd  rax, edx
0x180072f05  add     ecx, 100000h
0x180072f0b  add     ecx, [r9+rax*4]
0x180072f0f  mov     dword ptr [rsp+r8+4C0h+String], ecx
0x180072f14  inc     edx
0x180072f16  jmp     short loc_180072EE7
0x180072f18  inc     r12d
0x180072f1b  jmp     loc_180072D92
0x180072f20  mov     rcx, rdi; this
0x180072f23  call    ??_GCTitleDatabase@@QEAAPEAXI@Z; CTitleDatabase::`scalar deleting destructor'(uint)
0x180072f28  mov     r15d, [rsp+4C0h+var_478]
0x180072f2d  xor     r12d, r12d
0x180072f30  mov     [r13+10h], r12
0x180072f34  mov     r13d, [rsp+4C0h+var_480]
0x180072f39  mov     edi, r15d
0x180072f3c  jmp     loc_180072CB1
0x180072f41  call    ?OOM@@YAXXZ; OOM(void)
0x180072f47  mov     rcx, [rsp+4C0h+var_488]
0x180072f4c  mov     rax, [rcx]
0x180072f4f  mov     rax, [rax+70h]
0x180072f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072f58  call    ?NextAnimation@@YAXXZ; NextAnimation(void)
0x180072f5d  xor     ecx, ecx; dwMilliseconds
0x180072f5f  call    cs:__imp_Sleep
0x180072f65  mov     rcx, rbx; this
0x180072f68  call    ?Build@CWordWheelCompiler@@QEAAJXZ; CWordWheelCompiler::Build(void)
0x180072f6d  mov     rcx, rbx; this
0x180072f70  call    ??_GCWordWheelCompiler@@QEAAPEAXI@Z; CWordWheelCompiler::`scalar deleting destructor'(uint)
0x180072f75  mov     ecx, 118h; Size
0x180072f7a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180072f7f  mov     [rsp+4C0h+var_488], rax
0x180072f84  mov     rsi, rax
0x180072f87  test    rax, rax
0x180072f8a  jz      loc_1800730FC
0x180072f90  mov     [rax], r12
0x180072f93  mov     [rax+8], r12
0x180072f97  mov     [rax+10h], r12b
0x180072f9b  test    rax, rax
0x180072f9e  jz      loc_1800730FC
0x180072fa4  mov     rcx, rax; this
0x180072fa7  call    ?Init@CFileSystem@@QEAAJXZ; CFileSystem::Init(void)
0x180072fac  test    eax, eax
0x180072fae  js      loc_1800730FC
0x180072fb4  mov     rdx, [r14+10h]; char *
0x180072fb8  mov     r8d, 12h; unsigned int
0x180072fbe  mov     rcx, rsi; this
0x180072fc1  call    ?Open@CFileSystem@@QEAAJPEBDK@Z; CFileSystem::Open(char const *,ulong)
0x180072fc6  test    eax, eax
0x180072fc8  js      loc_1800730FC
0x180072fce  mov     rcx, [r14+140h]; this
0x180072fd5  call    ?Sort@CTitleMap@@QEAAXP6AHPEBX0@Z@Z; CTitleMap::Sort(int (*)(void const *,void const *))
0x180072fda  mov     ecx, 120h; Size
0x180072fdf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180072fe4  mov     [rsp+4C0h+var_488], rax
0x180072fe9  mov     rdi, rax
0x180072fec  test    rax, rax
0x180072fef  jz      loc_1800730F4
0x180072ff5  mov     [rax], rsi
0x180072ff8  mov     [rax+8], r12
0x180072ffc  mov     [rax+10h], r12
0x180073000  mov     [rax+18h], r12b
0x180073004  test    rax, rax
0x180073007  jz      loc_1800730F4
0x18007300d  mov     rcx, rax; this
0x180073010  call    ?CreateSub@CSubFileSystem@@QEAAJPEBD@Z; CSubFileSystem::CreateSub(char const *)
0x180073015  mov     r8d, 2; int
0x18007301b  mov     [rsp+4C0h+var_490], r13w
0x180073021  lea     rdx, [rsp+4C0h+var_490]; void *
0x180073026  mov     rcx, rdi; this
0x180073029  call    ?WriteSub@CSubFileSystem@@QEAAKPEBXH@Z; CSubFileSystem::WriteSub(void const *,int)
0x18007302e  mov     r15d, r12d
0x180073031  test    r13d, r13d
0x180073034  jle     loc_1800730DD
0x18007303a  mov     rcx, [r14+140h]; this
0x180073041  mov     edx, r15d; unsigned int
0x180073044  call    ?GetAt@CTitleMap@@QEAAPEAVCTitleMapEntry@@K@Z; CTitleMap::GetAt(ulong)
0x180073049  mov     rcx, rax; this
0x18007304c  mov     rbx, rax
  ... truncated ...
```
