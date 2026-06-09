# PerflibFindCounterFile

- ea: `0x1800113b0`
- end: `0x18001155f`
- name: `PerflibFindCounterFile`
- size: `431`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180011180`

## callees

- `0x180007740`
- `0x180008042`
- `0x18000fea0`
- `0x1800102c0`
- `0x180010328`
- `0x1800113b0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180011501`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180011501`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180011527`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180011527`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x18001141b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x18001141b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800114d4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800114d4`

## pseudocode

```c
unsigned __int64 __fastcall PerflibFindCounterFile(LPCWSTR lpFileName, char a2, const WCHAR *a3, unsigned __int16 *a4)
{
  int v8; // edi
  HANDLE FirstFile; // r14
  __int64 v10; // rax
  unsigned int LangIdFromSzLang; // eax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v14[4]; // [rsp+280h] [rbp+180h] BYREF
  __int16 v15; // [rsp+288h] [rbp+188h]
  WCHAR String1[4]; // [rsp+290h] [rbp+190h] BYREF
  __int16 v17; // [rsp+298h] [rbp+198h]

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v8 = 0;
  FirstFile = FindFirstFileExW(lpFileName, FindExInfoStandard, &FindFileData, FindExSearchNameMatch, 0, 0);
  *(_QWORD *)a4 = 0;
  a4[4] = 0;
  if ( FirstFile != (HANDLE)-1LL )
  {
    if ( a2 )
    {
      do
      {
        v10 = -1;
        do
          ++v10;
        while ( FindFileData.cFileName[v10] );
        if ( (_DWORD)v10 == 12 )
        {
          *(_QWORD *)v14 = 0;
          v15 = 0;
          *(_QWORD *)String1 = 0;
          v17 = 0;
          StringCchCopyW(v14, 5u, &FindFileData.cFileName[4]);
          LangIdFromSzLang = GetLangIdFromSzLang(v14);
          if ( LangIdFromSzLang )
          {
            PerfGetLangId(LangIdFromSzLang & 0x3FF, 1u, String1, 5u);
            if ( CompareStringOrdinal(String1, -1, a3, -1, 1) == 2 )
            {
              v8 = 1;
              StringCchCopyW(a4, 5u, v14);
            }
            else
            {
              v8 = 0;
            }
          }
        }
      }
      while ( FindNextFileW(FirstFile, &FindFileData) );
    }
    else
    {
      v8 = 1;
      StringCchCopyW(a4, 5u, a3);
    }
    FindClose(FirstFile);
  }
  return (unsigned __int64)a4 & -(__int64)(v8 != 0);
}

```

## disassembly

```asm
0x1800113b0  mov     [rsp-8+arg_8], rbx
0x1800113b5  push    rbp
0x1800113b6  push    rsi
0x1800113b7  push    rdi
0x1800113b8  push    r12
0x1800113ba  push    r13
0x1800113bc  push    r14
0x1800113be  push    r15
0x1800113c0  lea     rbp, [rsp-1B0h]
0x1800113c8  sub     rsp, 2B0h
0x1800113cf  mov     rax, cs:__security_cookie
0x1800113d6  xor     rax, rsp
0x1800113d9  mov     [rbp+1E0h+var_40], rax
0x1800113e0  mov     r12, r8
0x1800113e3  mov     r15b, dl
0x1800113e6  mov     rbx, rcx
0x1800113e9  xor     edx, edx; Val
0x1800113eb  mov     r8d, 250h; Size
0x1800113f1  lea     rcx, [rsp+2E0h+FindFileData]; void *
0x1800113f6  mov     rsi, r9
0x1800113f9  call    memset_0
0x1800113fe  xor     r13d, r13d
0x180011401  lea     r8, [rsp+2E0h+FindFileData]; lpFindFileData
0x180011406  mov     [rsp+2E0h+dwAdditionalFlags], r13d; dwAdditionalFlags
0x18001140b  xor     r9d, r9d; fSearchOp
0x18001140e  xor     edx, edx; fInfoLevelId
0x180011410  mov     [rsp+2E0h+lpSearchFilter], r13; lpSearchFilter
0x180011415  mov     rcx, rbx; lpFileName
0x180011418  mov     edi, r13d
0x18001141b  call    cs:__imp_FindFirstFileExW
0x180011421  mov     r14, rax
0x180011424  xor     eax, eax
0x180011426  mov     [rsi], rax
0x180011429  mov     [rsi+8], ax
0x18001142d  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180011431  jz      loc_18001152D
0x180011437  test    r15b, r15b
0x18001143a  jz      loc_180011511
0x180011440  lea     ebx, [rax+5]
0x180011443  lea     rcx, [rsp+2E0h+var_284]
0x180011448  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001144c  inc     rax
0x18001144f  cmp     [rcx+rax*2], r13w
0x180011454  jnz     short loc_18001144C
0x180011456  cmp     eax, 0Ch
0x180011459  jnz     loc_1800114F9
0x18001145f  xor     eax, eax
0x180011461  lea     r8, [rsp+2E0h+var_27C]; unsigned __int16 *
0x180011466  mov     rdx, rbx; unsigned __int64
0x180011469  mov     qword ptr [rbp+1E0h+var_60], rax
0x180011470  lea     rcx, [rbp+1E0h+var_60]; unsigned __int16 *
0x180011477  mov     [rbp+1E0h+var_58], ax
0x18001147e  mov     qword ptr [rbp+1E0h+String1], rax
0x180011485  mov     [rbp+1E0h+var_48], ax
0x18001148c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180011491  lea     rcx, [rbp+1E0h+var_60]; unsigned __int16 *
0x180011498  call    ?GetLangIdFromSzLang@@YAKPEBG@Z; GetLangIdFromSzLang(ushort const *)
0x18001149d  test    eax, eax
0x18001149f  jz      short loc_1800114F9
0x1800114a1  movzx   ecx, ax
0x1800114a4  lea     r8, [rbp+1E0h+String1]; unsigned __int16 *
0x1800114ab  and     ecx, 3FFh; unsigned int
0x1800114b1  mov     r9d, ebx; unsigned int
0x1800114b4  mov     dl, 1; unsigned __int8
0x1800114b6  call    ?PerfGetLangId@@YAXKEPEAGK@Z; PerfGetLangId(ulong,uchar,ushort *,ulong)
0x1800114bb  or      r9d, 0FFFFFFFFh; cchCount2
0x1800114bf  mov     dword ptr [rsp+2E0h+lpSearchFilter], 1; bIgnoreCase
0x1800114c7  or      edx, r9d; cchCount1
0x1800114ca  lea     rcx, [rbp+1E0h+String1]; lpString1
0x1800114d1  mov     r8, r12; lpString2
0x1800114d4  call    cs:__imp_CompareStringOrdinal
0x1800114da  cmp     eax, 2
0x1800114dd  jnz     short loc_1800114F6
0x1800114df  lea     r8, [rbp+1E0h+var_60]; unsigned __int16 *
0x1800114e6  mov     rdx, rbx; unsigned __int64
0x1800114e9  mov     rcx, rsi; unsigned __int16 *
0x1800114ec  lea     edi, [rax-1]
0x1800114ef  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800114f4  jmp     short loc_1800114F9
0x1800114f6  mov     edi, r13d
0x1800114f9  lea     rdx, [rsp+2E0h+FindFileData]; lpFindFileData
0x1800114fe  mov     rcx, r14; hFindFile
0x180011501  call    cs:__imp_FindNextFileW
0x180011507  test    eax, eax
0x180011509  jnz     loc_180011443
0x18001150f  jmp     short loc_180011524
0x180011511  mov     edi, 1
0x180011516  mov     r8, r12; unsigned __int16 *
0x180011519  mov     rcx, rsi; unsigned __int16 *
0x18001151c  lea     edx, [rdi+4]; unsigned __int64
0x18001151f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180011524  mov     rcx, r14; hFindFile
0x180011527  call    cs:__imp_FindClose
0x18001152d  neg     edi
0x18001152f  sbb     rax, rax
0x180011532  and     rax, rsi
0x180011535  mov     rcx, [rbp+1E0h+var_40]
0x18001153c  xor     rcx, rsp; StackCookie
0x18001153f  call    __security_check_cookie
0x180011544  mov     rbx, [rsp+2E0h+arg_8]
0x18001154c  add     rsp, 2B0h
0x180011553  pop     r15
0x180011555  pop     r14
0x180011557  pop     r13
0x180011559  pop     r12
0x18001155b  pop     rdi
0x18001155c  pop     rsi
0x18001155d  pop     rbp
0x18001155e  retn
```
