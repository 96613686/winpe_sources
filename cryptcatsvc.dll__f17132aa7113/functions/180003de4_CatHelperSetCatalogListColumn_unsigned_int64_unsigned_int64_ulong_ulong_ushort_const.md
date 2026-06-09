# CatHelperSetCatalogListColumn(unsigned __int64,unsigned __int64,ulong,ulong,ushort const *)

- ea: `0x180003de4`
- end: `0x180003ee0`
- name: `?CatHelperSetCatalogListColumn@@YAJ_K0KKPEBG@Z`
- size: `252`
- prototype: `__int64 __fastcall(JET_SESID sesid, JET_TABLEID tableid, JET_COLUMNID columnid, JET_GRBIT grbit, LPCWCH lpWideCharStr)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180003570`
- `0x18000392c`

## callees

- `0x1800015b0`
- `0x180003538`
- `0x180003de4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180003e33`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180003e89`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180003e33`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180003e89`
- `ESENT!JetSetColumn` at `0x180003eb0`
- `ESENT!JetSetColumn` at `0x180003eb0`

## pseudocode

```c
__int64 __fastcall CatHelperSetCatalogListColumn(
        JET_SESID sesid,
        JET_TABLEID tableid,
        JET_COLUMNID columnid,
        JET_GRBIT grbit,
        LPCWCH lpWideCharStr)
{
  int v9; // eax
  int cbMultiByte; // edi
  unsigned int v11; // esi
  CHAR *lpMultiByteStr; // rax
  CHAR *v13; // rbx
  unsigned int v14; // edi

  v9 = WideCharToMultiByte(0xFDE9u, 0, lpWideCharStr, -1, 0, 0, 0, 0);
  cbMultiByte = v9;
  v11 = v9 - 1;
  if ( (unsigned int)(v9 - 1) > 0x7FFFFFFD )
    return (unsigned int)-1011;
  lpMultiByteStr = (CHAR *)_CatDBAlloc(v9);
  v13 = lpMultiByteStr;
  if ( !lpMultiByteStr )
    return (unsigned int)-1011;
  if ( !WideCharToMultiByte(0xFDE9u, 0, lpWideCharStr, -1, lpMultiByteStr, cbMultiByte, 0, 0) )
  {
    _CatDBFree(v13);
    return (unsigned int)-1011;
  }
  v14 = JetSetColumn(sesid, tableid, columnid, v13, v11, grbit, 0);
  _CatDBFree(v13);
  return v14;
}

```

## disassembly

```asm
0x180003de4  mov     rax, rsp
0x180003de7  push    rbx
0x180003de8  push    rbp
0x180003de9  push    rsi
0x180003dea  push    rdi
0x180003deb  push    r12
0x180003ded  push    r14
0x180003def  push    r15
0x180003df1  sub     rsp, 40h
0x180003df5  mov     qword ptr [rax-40h], 0
0x180003dfd  mov     ebp, r9d
0x180003e00  mov     qword ptr [rax-48h], 0
0x180003e08  mov     r14d, r8d
0x180003e0b  mov     r8, [rsp+78h+lpWideCharStr]; lpWideCharStr
0x180003e13  mov     r15, rdx
0x180003e16  mov     r12, rcx
0x180003e19  mov     dword ptr [rax-50h], 0
0x180003e20  or      r9d, 0FFFFFFFFh; cchWideChar
0x180003e24  mov     qword ptr [rax-58h], 0
0x180003e2c  xor     edx, edx; dwFlags
0x180003e2e  mov     ecx, 0FDE9h; CodePage
0x180003e33  call    cs:__imp_WideCharToMultiByte
0x180003e39  movsxd  rdi, eax
0x180003e3c  lea     esi, [rdi-1]
0x180003e3f  cmp     esi, 7FFFFFFDh
0x180003e45  ja      loc_180003ED9
0x180003e4b  mov     rcx, rdi; uBytes
0x180003e4e  call    ?_CatDBAlloc@@YAPEAX_K@Z; _CatDBAlloc(unsigned __int64)
0x180003e53  mov     rbx, rax
0x180003e56  test    rax, rax
0x180003e59  jz      short loc_180003ED9
0x180003e5b  mov     r8, [rsp+78h+lpWideCharStr]; lpWideCharStr
0x180003e63  or      r9d, 0FFFFFFFFh; cchWideChar
0x180003e67  mov     [rsp+78h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180003e70  xor     edx, edx; dwFlags
0x180003e72  mov     [rsp+78h+lpDefaultChar], 0; lpDefaultChar
0x180003e7b  mov     ecx, 0FDE9h; CodePage
0x180003e80  mov     [rsp+78h+cbMultiByte], edi; cbMultiByte
0x180003e84  mov     [rsp+78h+lpMultiByteStr], rax; lpMultiByteStr
0x180003e89  call    cs:__imp_WideCharToMultiByte
0x180003e8f  test    eax, eax
0x180003e91  jz      short loc_180003ED1
0x180003e93  mov     [rsp+78h+lpDefaultChar], 0; psetinfo
0x180003e9c  mov     r9, rbx; pvData
0x180003e9f  mov     [rsp+78h+cbMultiByte], ebp; grbit
0x180003ea3  mov     r8d, r14d; columnid
0x180003ea6  mov     rdx, r15; tableid
0x180003ea9  mov     dword ptr [rsp+78h+lpMultiByteStr], esi; cbData
0x180003ead  mov     rcx, r12; sesid
0x180003eb0  call    cs:__imp_JetSetColumn
0x180003eb6  mov     edi, eax
0x180003eb8  mov     rcx, rbx; void *
0x180003ebb  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x180003ec0  mov     eax, edi
0x180003ec2  add     rsp, 40h
0x180003ec6  pop     r15
0x180003ec8  pop     r14
0x180003eca  pop     r12
0x180003ecc  pop     rdi
0x180003ecd  pop     rsi
0x180003ece  pop     rbp
0x180003ecf  pop     rbx
0x180003ed0  retn
0x180003ed1  mov     rcx, rbx; void *
0x180003ed4  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x180003ed9  mov     edi, 0FFFFFC0Dh
0x180003ede  jmp     short loc_180003EC0
```
