# FileUtil::TraverseReparsePoints(ushort const *,FrsStringImpl<ushort,char> &)

- ea: `0x1400c0ecc`
- end: `0x1400c1337`
- name: `?TraverseReparsePoints@FileUtil@@SAPEAVFrsStatus@@PEBGAEAV?$FrsStringImpl@GD@@@Z`
- size: `1131`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, reparse_path`

## callers

- `0x140042db8`

## callees

- `0x14000ee94`
- `0x140010680`
- `0x140019358`
- `0x1400248ac`
- `0x1400248f4`
- `0x1400255c8`
- `0x140028eec`
- `0x14002c548`
- `0x1400bd3e0`
- `0x1400c0ecc`
- `0x1401af7c0`
- `0x1401b3f9c`
- `0x1401b9494`
- `0x1401be5b0`
- `0x1401be698`
- `0x1401be958`
- `0x1401bec48`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400c0f23`
- `KERNEL32!GetCurrentThreadId` at `0x1400c100e`
- `KERNEL32!GetCurrentThreadId` at `0x1400c11cc`
- `KERNEL32!GetCurrentThreadId` at `0x1400c11eb`
- `KERNEL32!GetCurrentThreadId` at `0x1400c12a5`
- `KERNEL32!GetCurrentThreadId` at `0x1400c0f23`
- `KERNEL32!GetCurrentThreadId` at `0x1400c100e`
- `KERNEL32!GetCurrentThreadId` at `0x1400c11cc`
- `KERNEL32!GetCurrentThreadId` at `0x1400c11eb`
- `KERNEL32!GetCurrentThreadId` at `0x1400c12a5`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x1400c0fb2`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x1400c0fe8`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x1400c0fb2`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x1400c0fe8`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x1400c106f`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x1400c113e`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x1400c106f`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x1400c113e`

## string_xrefs

- `0x1400c1259`: `FileUtil::TraverseReparsePoints`
- `0x1400c0f40`: `FileUtil::TraverseReparsePoints`
- `0x1400c0fcb`: `FileUtil::TraverseReparsePoints`
- `0x1400c1290`: `Supplied Path = %ws, Traversed Path = %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall FileUtil::TraverseReparsePoints(__int64 a1, __int64 a2)
{
  __int64 v3; // rdi
  struct FrsStatus *v4; // rsi
  const unsigned __int16 *v5; // rdx
  DWORD v6; // eax
  __int64 v7; // rcx
  unsigned __int16 *v8; // rax
  wchar_t *v9; // rbx
  size_t v10; // rax
  __int64 v11; // rcx
  wchar_t *v12; // r15
  __int64 v13; // rcx
  __int64 v14; // rax
  wchar_t *v15; // r15
  _WORD *v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  unsigned __int16 *v19; // r15
  unsigned __int64 v20; // r15
  __int64 v21; // rcx
  __int64 v22; // rcx
  DWORD v23; // eax
  __int64 v24; // rcx
  DWORD CurrentThreadId; // [rsp+38h] [rbp-51h]
  DWORD v27; // [rsp+38h] [rbp-51h]
  DWORD v28; // [rsp+38h] [rbp-51h]
  wchar_t *Context; // [rsp+50h] [rbp-39h] BYREF
  __int64 v30; // [rsp+58h] [rbp-31h]
  void **v31; // [rsp+60h] [rbp-29h] BYREF
  __int64 v32; // [rsp+68h] [rbp-21h] BYREF
  void **v33; // [rsp+70h] [rbp-19h] BYREF
  __int64 v34; // [rsp+78h] [rbp-11h] BYREF
  void **v35; // [rsp+80h] [rbp-9h] BYREF
  _BYTE v36[8]; // [rsp+88h] [rbp-1h] BYREF
  const wchar_t *v37; // [rsp+90h] [rbp+7h] BYREF
  int v38; // [rsp+98h] [rbp+Fh]
  int v39; // [rsp+9Ch] [rbp+13h]
  const wchar_t *v40; // [rsp+A0h] [rbp+17h]
  __int64 v41; // [rsp+F0h] [rbp+67h] BYREF
  __int64 v42; // [rsp+100h] [rbp+77h] BYREF
  wchar_t *v43; // [rsp+108h] [rbp+7Fh] BYREF

  v41 = a1;
  v3 = 0;
  v4 = 0;
  Context = 0;
  v43 = 0;
  v30 = 0;
  FilePath::FilePath((FilePath *)&v35);
  FilePath::FilePath((FilePath *)&v33);
  if ( v5 )
  {
    FilePath::FilePath((FilePath *)&v31, v5);
    FilePath::AppendTrailingBackslash((FilePath *)&v31);
    v8 = WStringDup((const unsigned __int16 *)(v32 + 18));
    v9 = 0;
    if ( v8 )
      v9 = v8;
    v43 = v9;
LABEL_6:
    FrsStringImpl<unsigned short,char>::SetEmpty(a2);
    LODWORD(v42) = 0;
    v10 = wcscspn(v9, L":");
    v11 = -1;
    do
      ++v11;
    while ( v9[v11] );
    if ( v10 == v11 )
    {
      v10 = wcscspn(v9, L"}");
      if ( v9[v10] != 125 || (v12 = &v9[v10 + 1], *v12 != 92) )
      {
        CurrentThreadId = GetCurrentThreadId();
        v14 = FrsStatusList::PushNewError(
                v13,
                87,
                0,
                1,
                "base\\fs\\remotefs\\frs\\src\\fs\\fileutil.cpp",
                "FileUtil::TraverseReparsePoints",
                1917,
                CurrentThreadId,
                0);
        goto LABEL_40;
      }
    }
    else if ( v9[v10] != 58 || (v12 = &v9[v10 + 1], *v12 != 92) )
    {
      v28 = GetCurrentThreadId();
      v14 = FrsStatusList::PushNewError(
              v22,
              87,
              0,
              1,
              "base\\fs\\remotefs\\frs\\src\\fs\\fileutil.cpp",
              "FileUtil::TraverseReparsePoints",
              1933,
              v28,
              0);
LABEL_40:
      v4 = (struct FrsStatus *)v14;
      if ( v14 )
      {
LABEL_41:
        FrsStringImpl<unsigned short,char>::SetEmpty(a2);
LABEL_46:
        v23 = GetCurrentThreadId();
        v3 = FrsStatusList::PushNewError(
               v24,
               *((unsigned int *)v4 + 1),
               *((unsigned int *)v4 + 2),
               *(unsigned int *)v4,
               "base\\fs\\remotefs\\frs\\src\\fs\\fileutil.cpp",
               "FileUtil::TraverseReparsePoints",
               2036,
               v23,
               v4);
LABEL_47:
        v31 = &FilePath::`vftable';
        FrsStringImpl<char,unsigned short>::ReleaseBody(&v32);
        goto LABEL_48;
      }
      goto LABEL_42;
    }
    FrsStringImpl<unsigned short,char>::Set(a2, v9, v10 + 2);
    v15 = wcstok(v12, L"\\", &Context);
    if ( v15 )
    {
      while ( 1 )
      {
        if ( *(_WORD *)(*(_QWORD *)a2 + 2LL * *(_QWORD *)(*(_QWORD *)a2 + 8LL) + 16) != 92 )
          FrsStringImpl<unsigned short,char>::Append(a2, L"\\");
        FrsStringImpl<unsigned short,char>::Append(a2, v15);
        v4 = FileUtil::ChaseSymbolicLink(
               (const unsigned __int16 *)(*(_QWORD *)a2 + 18LL),
               (struct FilePath *)&v35,
               (struct FilePath *)&v33,
               (int *)&v42);
        if ( v4 )
          goto LABEL_41;
        if ( (_DWORD)v42 )
        {
          FrsStringImpl<unsigned short,char>::Set(a2, v34 + 18);
          v16 = *(_WORD **)a2;
          if ( *(_WORD *)(*(_QWORD *)a2 + 18LL) == 92 && v16[10] == 63 && v16[11] == 63 && v16[12] == 92 )
          {
            v17 = FrsStringImpl<unsigned short,char>::PLock(a2);
            if ( v17 )
            {
              *(_WORD *)(v17 + 2) = 92;
              FrsStringImpl<unsigned short,char>::ReleaseWritePointer(a2, *(_QWORD *)(*(_QWORD *)a2 + 8LL));
            }
          }
        }
        v15 = wcstok(0, L"\\", &Context);
        if ( !v15 )
        {
          v18 = -1;
          do
            ++v18;
          while ( *(_WORD *)(v41 + 2 * v18) );
          if ( *(_WORD *)(v41 + 2 * v18 - 2) == 92 )
            FrsStringImpl<unsigned short,char>::Append(a2, L"\\");
          v19 = WStringDup((const unsigned __int16 *)(*(_QWORD *)a2 + 18LL));
          if ( v9 != v19 )
          {
            if ( v9 )
              operator delete[](v9);
            v9 = v19;
            v43 = v19;
          }
          v20 = ++v30;
          if ( (_DWORD)v42 )
          {
            if ( v20 < 0x64 )
              goto LABEL_6;
          }
          else if ( v20 < 0x64 )
          {
            break;
          }
          v27 = GetCurrentThreadId();
          v14 = FrsStatusList::PushNewError(
                  v21,
                  87,
                  0,
                  1,
                  "base\\fs\\remotefs\\frs\\src\\fs\\fileutil.cpp",
                  "FileUtil::TraverseReparsePoints",
                  2016,
                  v27,
                  0);
          goto LABEL_40;
        }
      }
    }
LABEL_42:
    if ( !g_DebugLog )
      goto LABEL_47;
    if ( !LODWORD(g_DebugLog[1].LockSemaphore) )
      goto LABEL_47;
    if ( SLODWORD(g_DebugLog[1].OwningThread) < 5 )
      goto LABEL_47;
    v37 = L"FileUtil::TraverseReparsePoints";
    v38 = 2032;
    v39 = 5;
    v40 = L"FUTL";
    v42 = *(_QWORD *)a2 + 18LL;
    dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned short *>(
      &v37,
      L"Supplied Path = %ws, Traversed Path = %ws",
      &v41,
      &v42);
    if ( !v4 )
      goto LABEL_47;
    goto LABEL_46;
  }
  v6 = GetCurrentThreadId();
  v3 = FrsStatusList::PushNewError(
         v7,
         87,
         0,
         1,
         "base\\fs\\remotefs\\frs\\src\\fs\\fileutil.cpp",
         "FileUtil::TraverseReparsePoints",
         1875,
         v6,
         0);
LABEL_48:
  v33 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v34);
  v35 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(v36);
  scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(&v43);
  return v3;
}

```

## disassembly

```asm
0x1400c0ecc  mov     [rsp-8+arg_8], rbx
0x1400c0ed1  mov     [rsp-8+arg_0], rcx
0x1400c0ed6  push    rbp
0x1400c0ed7  push    rsi
0x1400c0ed8  push    rdi
0x1400c0ed9  push    r12
0x1400c0edb  push    r13
0x1400c0edd  push    r14
0x1400c0edf  push    r15
0x1400c0ee1  lea     rbp, [rsp-27h]
0x1400c0ee6  sub     rsp, 0B0h
0x1400c0eed  mov     r14, rdx
0x1400c0ef0  mov     rdx, rcx
0x1400c0ef3  xor     edi, edi
0x1400c0ef5  mov     esi, edi
0x1400c0ef7  mov     [rbp+57h+Context], rdi
0x1400c0efb  mov     [rbp+57h+arg_18], rdi
0x1400c0eff  mov     [rbp+57h+var_88], rdi
0x1400c0f03  lea     rcx, [rbp+57h+var_60]; this
0x1400c0f07  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x1400c0f0c  nop
0x1400c0f0d  lea     rcx, [rbp+57h+var_70]; this
0x1400c0f11  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x1400c0f16  nop
0x1400c0f17  lea     rbx, ??_7FilePath@@6B@; const FilePath::`vftable'
0x1400c0f1e  test    rdx, rdx
0x1400c0f21  jnz     short loc_1400C0F6F
0x1400c0f23  call    cs:__imp_GetCurrentThreadId
0x1400c0f2a  nop     dword ptr [rax+rax+00h]
0x1400c0f2f  mov     [rsp+0E0h+var_A0], rdi
0x1400c0f34  mov     [rsp+0E0h+var_A8], eax
0x1400c0f38  mov     [rsp+0E0h+var_B0], 753h
0x1400c0f40  lea     r12, aFileutilTraver; "FileUtil::TraverseReparsePoints"
0x1400c0f47  mov     [rsp+0E0h+var_B8], r12
0x1400c0f4c  lea     r13, aBaseFsRemotefs_24; "base\\fs\\remotefs\\frs\\src\\fs\\fileu"...
0x1400c0f53  mov     [rsp+0E0h+var_C0], r13
0x1400c0f58  lea     r9d, [rdi+1]
0x1400c0f5c  xor     r8d, r8d
0x1400c0f5f  lea     edx, [rdi+57h]
0x1400c0f62  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400c0f67  mov     rdi, rax
0x1400c0f6a  jmp     loc_1400C12F3
0x1400c0f6f  lea     rcx, [rbp+57h+var_80]; this
0x1400c0f73  call    ??0FilePath@@QEAA@PEBG@Z; FilePath::FilePath(ushort const *)
0x1400c0f78  nop
0x1400c0f79  lea     rcx, [rbp+57h+var_80]; this
0x1400c0f7d  call    ?AppendTrailingBackslash@FilePath@@QEAAXXZ; FilePath::AppendTrailingBackslash(void)
0x1400c0f82  mov     rcx, [rbp+57h+var_78]
0x1400c0f86  add     rcx, 12h; unsigned __int16 *
0x1400c0f8a  call    ?WStringDup@@YAPEAGPEBG@Z; WStringDup(ushort const *)
0x1400c0f8f  mov     rbx, rdi
0x1400c0f92  test    rax, rax
0x1400c0f95  cmovnz  rbx, rax
0x1400c0f99  mov     [rbp+57h+arg_18], rbx
0x1400c0f9d  mov     rcx, r14
0x1400c0fa0  call    ?SetEmpty@?$FrsStringImpl@GD@@QEAAXXZ; FrsStringImpl<ushort,char>::SetEmpty(void)
0x1400c0fa5  mov     dword ptr [rbp+57h+arg_10], edi
0x1400c0fa8  lea     rdx, Control; ":"
0x1400c0faf  mov     rcx, rbx; String
0x1400c0fb2  call    cs:__imp_wcscspn
0x1400c0fb9  nop     dword ptr [rax+rax+00h]
0x1400c0fbe  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400c0fc2  inc     rcx
0x1400c0fc5  cmp     [rbx+rcx*2], di
0x1400c0fc9  jnz     short loc_1400C0FC2
0x1400c0fcb  lea     r12, aFileutilTraver; "FileUtil::TraverseReparsePoints"
0x1400c0fd2  lea     r13, aBaseFsRemotefs_24; "base\\fs\\remotefs\\frs\\src\\fs\\fileu"...
0x1400c0fd9  cmp     rax, rcx
0x1400c0fdc  jnz     short loc_1400C1030
0x1400c0fde  lea     rdx, asc_140244B84; "}"
0x1400c0fe5  mov     rcx, rbx; String
0x1400c0fe8  call    cs:__imp_wcscspn
0x1400c0fef  nop     dword ptr [rax+rax+00h]
0x1400c0ff4  cmp     word ptr [rbx+rax*2], 7Dh ; '}'
0x1400c0ff9  jnz     short loc_1400C100E
0x1400c0ffb  lea     r15, [rax+1]
0x1400c0fff  lea     r15, [rbx+r15*2]
0x1400c1003  mov     ecx, 5Ch ; '\'
0x1400c1008  cmp     [r15], cx
0x1400c100c  jz      short loc_1400C1052
0x1400c100e  call    cs:__imp_GetCurrentThreadId
0x1400c1015  nop     dword ptr [rax+rax+00h]
0x1400c101a  mov     [rsp+0E0h+var_A0], rdi
0x1400c101f  mov     [rsp+0E0h+var_A8], eax
0x1400c1023  mov     [rsp+0E0h+var_B0], 77Dh
0x1400c102b  jmp     loc_1400C1208
0x1400c1030  cmp     word ptr [rbx+rax*2], 3Ah ; ':'
0x1400c1035  jnz     loc_1400C11EB
0x1400c103b  lea     r15, [rax+1]
0x1400c103f  lea     r15, [rbx+r15*2]
0x1400c1043  mov     ecx, 5Ch ; '\'
0x1400c1048  cmp     [r15], cx
0x1400c104c  jnz     loc_1400C11EB
0x1400c1052  lea     r8, [rax+2]
0x1400c1056  mov     rdx, rbx
0x1400c1059  mov     rcx, r14
0x1400c105c  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG_K@Z; FrsStringImpl<ushort,char>::Set(ushort const *,unsigned __int64)
0x1400c1061  lea     r8, [rbp+57h+Context]; Context
0x1400c1065  lea     rdx, Delimiter; "\\"
0x1400c106c  mov     rcx, r15; String
0x1400c106f  call    cs:__imp_wcstok
0x1400c1076  nop     dword ptr [rax+rax+00h]
0x1400c107b  mov     r15, rax
0x1400c107e  test    rax, rax
0x1400c1081  jz      loc_1400C1236
0x1400c1087  mov     rcx, [r14]
0x1400c108a  mov     rax, [rcx+8]
0x1400c108e  mov     edx, 5Ch ; '\'
0x1400c1093  cmp     [rcx+rax*2+10h], dx
0x1400c1098  jz      short loc_1400C10A9
0x1400c109a  lea     rdx, Delimiter; "\\"
0x1400c10a1  mov     rcx, r14
0x1400c10a4  call    ?Append@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Append(ushort const *)
0x1400c10a9  mov     rdx, r15
0x1400c10ac  mov     rcx, r14
0x1400c10af  call    ?Append@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Append(ushort const *)
0x1400c10b4  mov     rcx, [r14]
0x1400c10b7  add     rcx, 12h; unsigned __int16 *
0x1400c10bb  lea     r9, [rbp+57h+arg_10]; int *
0x1400c10bf  lea     r8, [rbp+57h+var_70]; struct FilePath *
0x1400c10c3  lea     rdx, [rbp+57h+var_60]; this
0x1400c10c7  call    ?ChaseSymbolicLink@FileUtil@@SAPEAVFrsStatus@@PEBGAEAVFilePath@@1AEAH@Z; FileUtil::ChaseSymbolicLink(ushort const *,FilePath &,FilePath &,int &)
0x1400c10cc  mov     rsi, rax
0x1400c10cf  test    rax, rax
0x1400c10d2  jnz     loc_1400C122C
0x1400c10d8  cmp     dword ptr [rbp+57h+arg_10], edi
0x1400c10db  jz      short loc_1400C1131
0x1400c10dd  mov     rdx, [rbp+57h+var_68]
0x1400c10e1  add     rdx, 12h
0x1400c10e5  mov     rcx, r14
0x1400c10e8  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x1400c10ed  mov     rax, [r14]
0x1400c10f0  lea     r15d, [rsi+5Ch]
0x1400c10f4  cmp     [rax+12h], r15w
0x1400c10f9  jnz     short loc_1400C1131
0x1400c10fb  cmp     word ptr [rax+14h], 3Fh ; '?'
0x1400c1100  jnz     short loc_1400C1131
0x1400c1102  cmp     word ptr [rax+16h], 3Fh ; '?'
0x1400c1107  jnz     short loc_1400C1131
0x1400c1109  cmp     [rax+18h], r15w
0x1400c110e  jnz     short loc_1400C1131
0x1400c1110  mov     rcx, r14
0x1400c1113  call    ?PLock@?$FrsStringImpl@GD@@QEAAPEAGXZ; FrsStringImpl<ushort,char>::PLock(void)
0x1400c1118  test    rax, rax
0x1400c111b  jz      short loc_1400C1131
0x1400c111d  mov     [rax+2], r15w
0x1400c1122  mov     rax, [r14]
0x1400c1125  mov     rdx, [rax+8]
0x1400c1129  mov     rcx, r14
0x1400c112c  call    ?ReleaseWritePointer@?$FrsStringImpl@GD@@QEAAX_K@Z; FrsStringImpl<ushort,char>::ReleaseWritePointer(unsigned __int64)
0x1400c1131  lea     r8, [rbp+57h+Context]; Context
0x1400c1135  lea     rdx, Delimiter; "\\"
0x1400c113c  xor     ecx, ecx; String
0x1400c113e  call    cs:__imp_wcstok
0x1400c1145  nop     dword ptr [rax+rax+00h]
0x1400c114a  mov     r15, rax
0x1400c114d  test    rax, rax
0x1400c1150  jnz     loc_1400C1087
0x1400c1156  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400c115a  mov     rcx, [rbp+57h+arg_0]
0x1400c115e  inc     rax
0x1400c1161  cmp     [rcx+rax*2], di
0x1400c1165  jnz     short loc_1400C115E
0x1400c1167  mov     edx, 5Ch ; '\'
0x1400c116c  cmp     [rcx+rax*2-2], dx
0x1400c1171  jnz     short loc_1400C1182
0x1400c1173  lea     rdx, Delimiter; "\\"
0x1400c117a  mov     rcx, r14
0x1400c117d  call    ?Append@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Append(ushort const *)
0x1400c1182  mov     rcx, [r14]
0x1400c1185  add     rcx, 12h; unsigned __int16 *
0x1400c1189  call    ?WStringDup@@YAPEAGPEBG@Z; WStringDup(ushort const *)
0x1400c118e  mov     r15, rax
0x1400c1191  cmp     rbx, rax
0x1400c1194  jz      short loc_1400C11AA
0x1400c1196  test    rbx, rbx
0x1400c1199  jz      short loc_1400C11A3
0x1400c119b  mov     rcx, rbx; Block
0x1400c119e  call    ??_V@YAXPEAXAEBUZeroFill@@@Z; operator delete[](void *,ZeroFill const &)
0x1400c11a3  mov     rbx, r15
0x1400c11a6  mov     [rbp+57h+arg_18], rbx
0x1400c11aa  mov     r15, [rbp+57h+var_88]
0x1400c11ae  inc     r15
0x1400c11b1  mov     [rbp+57h+var_88], r15
0x1400c11b5  cmp     dword ptr [rbp+57h+arg_10], edi
0x1400c11b8  jz      short loc_1400C11C6
0x1400c11ba  cmp     r15, 64h ; 'd'
0x1400c11be  jb      loc_1400C0F9D
0x1400c11c4  jmp     short loc_1400C11CC
0x1400c11c6  cmp     r15, 64h ; 'd'
0x1400c11ca  jb      short loc_1400C1236
0x1400c11cc  call    cs:__imp_GetCurrentThreadId
0x1400c11d3  nop     dword ptr [rax+rax+00h]
0x1400c11d8  mov     [rsp+0E0h+var_A0], rdi
0x1400c11dd  mov     [rsp+0E0h+var_A8], eax
0x1400c11e1  mov     [rsp+0E0h+var_B0], 7E0h
0x1400c11e9  jmp     short loc_1400C1208
0x1400c11eb  call    cs:__imp_GetCurrentThreadId
0x1400c11f2  nop     dword ptr [rax+rax+00h]
0x1400c11f7  mov     [rsp+0E0h+var_A0], rdi
0x1400c11fc  mov     [rsp+0E0h+var_A8], eax
0x1400c1200  mov     [rsp+0E0h+var_B0], 78Dh
0x1400c1208  mov     [rsp+0E0h+var_B8], r12
0x1400c120d  mov     [rsp+0E0h+var_C0], r13
0x1400c1212  mov     r9d, 1
0x1400c1218  xor     r8d, r8d
0x1400c121b  lea     edx, [r9+56h]
0x1400c121f  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400c1224  mov     rsi, rax
0x1400c1227  test    rax, rax
0x1400c122a  jz      short loc_1400C1236
0x1400c122c  mov     rcx, r14
0x1400c122f  call    ?SetEmpty@?$FrsStringImpl@GD@@QEAAXXZ; FrsStringImpl<ushort,char>::SetEmpty(void)
0x1400c1234  jmp     short loc_1400C12A5
0x1400c1236  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400c123d  test    rax, rax
0x1400c1240  jz      loc_1400C12DE
0x1400c1246  cmp     [rax+40h], edi
0x1400c1249  jz      loc_1400C12DE
0x1400c124f  cmp     dword ptr [rax+38h], 5
0x1400c1253  jl      loc_1400C12DE
0x1400c1259  lea     rax, aFileutilTraver_0; "FileUtil::TraverseReparsePoints"
0x1400c1260  mov     [rbp+57h+var_50], rax
0x1400c1264  mov     [rbp+57h+var_48], 7F0h
0x1400c126b  mov     [rbp+57h+var_44], 5
0x1400c1272  lea     rax, aFutl; "FUTL"
0x1400c1279  mov     [rbp+57h+var_40], rax
0x1400c127d  mov     rax, [r14]
0x1400c1280  add     rax, 12h
0x1400c1284  mov     [rbp+57h+arg_10], rax
0x1400c1288  lea     r9, [rbp+57h+arg_10]
0x1400c128c  lea     r8, [rbp+57h+arg_0]
0x1400c1290  lea     rdx, aSuppliedPathWs; "Supplied Path = %ws, Traversed Path = %"...
0x1400c1297  lea     rcx, [rbp+57h+var_50]
0x1400c129b  call    ??$DbgPrint@GPEBGPEAG@dbgobj@@QEAA_KPEBGAEBQEBGAEBQEAG@Z; dbgobj::DbgPrint<ushort,ushort const *,ushort *>(ushort const *,ushort const * const &,ushort * const &)
0x1400c12a0  test    rsi, rsi
0x1400c12a3  jz      short loc_1400C12DE
0x1400c12a5  call    cs:__imp_GetCurrentThreadId
0x1400c12ac  nop     dword ptr [rax+rax+00h]
0x1400c12b1  mov     [rsp+0E0h+var_A0], rsi
0x1400c12b6  mov     [rsp+0E0h+var_A8], eax
0x1400c12ba  mov     [rsp+0E0h+var_B0], 7F4h
0x1400c12c2  mov     [rsp+0E0h+var_B8], r12
0x1400c12c7  mov     [rsp+0E0h+var_C0], r13
0x1400c12cc  mov     r9d, [rsi]
0x1400c12cf  mov     r8d, [rsi+8]
0x1400c12d3  mov     edx, [rsi+4]
0x1400c12d6  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400c12db  mov     rdi, rax
0x1400c12de  lea     rbx, ??_7FilePath@@6B@; const FilePath::`vftable'
0x1400c12e5  mov     [rbp+57h+var_80], rbx
0x1400c12e9  lea     rcx, [rbp+57h+var_78]
0x1400c12ed  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1400c12f2  nop
0x1400c12f3  mov     [rbp+57h+var_70], rbx
0x1400c12f7  lea     rcx, [rbp+57h+var_68]
0x1400c12fb  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1400c1300  nop
0x1400c1301  mov     [rbp+57h+var_60], rbx
0x1400c1305  lea     rcx, [rbp+57h+var_58]
0x1400c1309  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1400c130e  nop
0x1400c130f  lea     rcx, [rbp+57h+arg_18]
0x1400c1313  call    ??1?$scoped_any@PEAU_FRS_RDC_SOURCE_NEED@@Uclose_delete_array@@Unull_t@@$0A@@@QEAA@XZ; scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(void)
0x1400c1318  mov     rax, rdi
0x1400c131b  mov     rbx, [rsp+0E0h+arg_8]
0x1400c1323  add     rsp, 0B0h
0x1400c132a  pop     r15
0x1400c132c  pop     r14
0x1400c132e  pop     r13
0x1400c1330  pop     r12
0x1400c1332  pop     rdi
0x1400c1333  pop     rsi
0x1400c1334  pop     rbp
0x1400c1335  retn
```
