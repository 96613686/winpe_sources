# CBackupSession::LogFilePermissionFailure(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)

- ea: `0x18001a7d0`
- end: `0x18001ac34`
- name: `?LogFilePermissionFailure@CBackupSession@@AEAAXV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `1124`
- prototype: `void __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001cb74`
- `0x18001eaf0`

## callees

- `0x180002c24`
- `0x1800062d0`
- `0x180008fa0`
- `0x1800091a4`
- `0x1800093a8`
- `0x180009920`
- `0x1800127b0`
- `0x180018c6c`
- `0x180018da0`
- `0x18001a7d0`
- `0x18001f63c`
- `0x180021e6c`
- `0x1800220a4`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18001a90c`
- `msvcrt!_wcsnicmp` at `0x18001a90c`
- `KERNEL32!GetLastError` at `0x18001a9db`
- `KERNEL32!GetLastError` at `0x18001a9db`
- `KERNEL32!CloseHandle` at `0x18001ab2d`
- `KERNEL32!CloseHandle` at `0x18001ab2d`
- `KERNEL32!GetFileAttributesW` at `0x18001aaaf`
- `KERNEL32!GetFileAttributesW` at `0x18001aaaf`
- `KERNEL32!CreateFileW` at `0x18001a9c8`
- `KERNEL32!CreateFileW` at `0x18001a9c8`

## string_xrefs

- `0x18001aa6b`: `Unexpected error on folder open`

## pseudocode

```c
void __fastcall CBackupSession::LogFilePermissionFailure(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // r12
  __int64 v3; // r15
  volatile signed __int32 *v4; // rcx
  wchar_t *v5; // rbx
  int *v6; // rdi
  volatile signed __int32 *v7; // rbx
  char v8; // r13
  int v9; // eax
  volatile signed __int32 *v10; // rdi
  __int64 *Prefix; // r14
  __int64 v12; // r9
  volatile signed __int32 *v13; // rcx
  const wchar_t *v14; // rdx
  int *v15; // r14
  volatile signed __int32 *v16; // r15
  ATL::CStringData *v17; // r14
  volatile signed __int32 *v18; // rcx
  int *v19; // r14
  volatile signed __int32 *v20; // rdi
  HANDLE FileW; // r15
  DWORD LastError; // eax
  volatile signed __int32 *v23; // rcx
  int *v24; // r14
  volatile signed __int32 *v25; // rdi
  DWORD FileAttributesW; // eax
  volatile signed __int32 *v27; // rcx
  int *v28; // r14
  volatile signed __int32 *v29; // rdi
  int v30; // eax
  __int64 v31; // rax
  int v32; // [rsp+40h] [rbp-58h] BYREF
  wchar_t *String1; // [rsp+48h] [rbp-50h] BYREF
  wchar_t *String2[9]; // [rsp+50h] [rbp-48h] BYREF
  int v37; // [rsp+B0h] [rbp+18h]
  int v38; // [rsp+B0h] [rbp+18h]
  volatile signed __int32 *v39; // [rsp+B8h] [rbp+20h] BYREF

  v2 = a2;
  v3 = a1;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&String1);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v39);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v4 = (volatile signed __int32 *)(*v2 - 24LL);
    v5 = String1;
    v6 = (int *)(String1 - 12);
    if ( v4 != (volatile signed __int32 *)(String1 - 12) )
    {
      if ( v6[4] >= 0 && *(_QWORD *)v4 == *(_QWORD *)v6 )
      {
        v7 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v4);
        ATL::CStringData::Release((ATL::CStringData *)v6);
        v5 = (wchar_t *)(v7 + 6);
        String1 = v5;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(&String1, *v2, *(unsigned int *)(*v2 - 16LL));
        v5 = String1;
      }
    }
    v8 = 0;
    v9 = 0;
    v10 = v39;
    while ( 1 )
    {
      v37 = v9;
      if ( *((int *)v5 - 4) <= 6 )
        break;
      if ( v9 )
      {
        FileW = CreateFileW(v5, 0x80000000, 7u, 0, 3u, 0x2000000u, 0);
        if ( FileW == (HANDLE)-1LL )
        {
          LastError = GetLastError();
          if ( LastError == 5 )
          {
            v23 = (volatile signed __int32 *)(v5 - 12);
            v24 = (int *)(v10 - 6);
            if ( v5 - 12 != (wchar_t *)(v10 - 6) )
            {
              if ( v24[4] >= 0 && *(_QWORD *)v23 == *(_QWORD *)v24 )
              {
                v25 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v23);
                ATL::CStringData::Release((ATL::CStringData *)v24);
                v10 = v25 + 6;
                v39 = v10;
              }
              else
              {
                ATL::CSimpleStringT<unsigned short,0>::SetString(&v39, v5, *((unsigned int *)v5 - 4));
                v10 = v39;
              }
            }
            v8 = 1;
          }
          else
          {
            if ( LastError - 2 <= 1 )
              goto LABEL_55;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_ss(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                214,
                (unsigned int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                (unsigned int)"FALSE",
                (__int64)"Unexpected error on folder open");
          }
        }
        else
        {
          FileAttributesW = GetFileAttributesW(v5);
          if ( FileAttributesW != -1 && (FileAttributesW & 0x4000) != 0 && !*(_DWORD *)(a1 + 368) )
          {
            v27 = (volatile signed __int32 *)(v5 - 12);
            v28 = (int *)(v10 - 6);
            if ( v5 - 12 != (wchar_t *)(v10 - 6) )
            {
              if ( v28[4] >= 0 && *(_QWORD *)v27 == *(_QWORD *)v28 )
              {
                v29 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v27);
                ATL::CStringData::Release((ATL::CStringData *)v28);
                v10 = v29 + 6;
                v39 = v10;
              }
              else
              {
                ATL::CSimpleStringT<unsigned short,0>::SetString(&v39, v5, *((unsigned int *)v5 - 4));
                v10 = v39;
              }
            }
            v8 = 1;
          }
          CloseHandle(FileW);
        }
      }
      else
      {
        Prefix = (__int64 *)ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,bool,CRevOrderCaseInsensitiveCStringWTraits,ATL::CElementTraits<bool>>::FindPrefix(
                              v3 + 512,
                              v5);
        if ( Prefix )
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)String2);
          v12 = *Prefix;
          v13 = (volatile signed __int32 *)(*Prefix - 24);
          v14 = String2[0];
          v15 = (int *)(String2[0] - 12);
          if ( v13 != (volatile signed __int32 *)String2[0] - 6 )
          {
            if ( v15[4] >= 0 && *(_QWORD *)v13 == *(_QWORD *)v15 )
            {
              v16 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v13);
              ATL::CStringData::Release((ATL::CStringData *)v15);
              v14 = (const wchar_t *)(v16 + 6);
              String2[0] = (wchar_t *)(v16 + 6);
            }
            else
            {
              ATL::CSimpleStringT<unsigned short,0>::SetString(String2, v12, *(unsigned int *)(v12 - 16));
              v14 = String2[0];
            }
          }
          v17 = (ATL::CStringData *)(v14 - 12);
          if ( !_wcsnicmp(v5, v14, *((int *)v14 - 4)) )
          {
            ATL::CStringData::Release(v17);
            ATL::CStringData::Release((ATL::CStringData *)(v10 - 6));
            ATL::CStringData::Release((ATL::CStringData *)(v5 - 12));
            goto LABEL_70;
          }
          ATL::CStringData::Release(v17);
        }
        v18 = (volatile signed __int32 *)(v5 - 12);
        v19 = (int *)(v10 - 6);
        if ( v5 - 12 != (wchar_t *)(v10 - 6) )
        {
          if ( v19[4] >= 0 && *(_QWORD *)v18 == *(_QWORD *)v19 )
          {
            v20 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v18);
            ATL::CStringData::Release((ATL::CStringData *)v19);
            v10 = v20 + 6;
            v39 = v10;
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(&v39, v5, *((unsigned int *)v5 - 4));
            v10 = v39;
          }
        }
      }
      v30 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::ReverseFind(
              &String1,
              92);
      if ( v30 < 0 )
      {
        v3 = a1;
        break;
      }
      ATL::CSimpleStringT<unsigned short,0>::Truncate(&String1, (unsigned int)v30);
      v9 = v37 + 1;
      v5 = String1;
      v3 = a1;
    }
    if ( (Microsoft_Windows_FileHistory_EngineEnableBits & 2) != 0 )
      McTemplateU0z_EventWriteTransfer(v4, FileFailure_NoPermission, v10);
    if ( v8 )
    {
      v31 = ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,bool,CRevOrderCaseInsensitiveCStringWTraits,ATL::CElementTraits<bool>>::Find(
              v3 + 512,
              v10);
      if ( v31 )
        *(_BYTE *)(v31 + 8) = 1;
      else
        ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,bool,CRevOrderCaseInsensitiveCStringWTraits,ATL::CElementTraits<bool>>::RBInsert(
          v3 + 512,
          v10);
    }
LABEL_55:
    ATL::CStringData::Release((ATL::CStringData *)(v10 - 6));
    ATL::CStringData::Release((ATL::CStringData *)(v5 - 12));
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', (ATL::CAtlException *)&v32) )
    {
      v38 = v32;
      if ( v32 >= 0 )
      {
        __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18001ABD2);
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            215,
            (unsigned int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
            *a2,
            v32);
        __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18001ABD0);
      }
      if ( v38 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          216,
          &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
          "SUCCEEDED(hr)");
      v2 = a2;
    }
  }
LABEL_70:
  ATL::CStringData::Release((ATL::CStringData *)(*v2 - 24LL));
}

```

## disassembly

```asm
0x18001a7d0  mov     [rsp+arg_8], rdx
0x18001a7d5  mov     [rsp+arg_0], rcx
0x18001a7da  push    rbx
0x18001a7db  push    rdi
0x18001a7dc  push    r12
0x18001a7de  push    r13
0x18001a7e0  push    r14
0x18001a7e2  push    r15
0x18001a7e4  sub     rsp, 68h
0x18001a7e8  mov     r12, rdx
0x18001a7eb  mov     r15, rcx
0x18001a7ee  lea     rcx, [rsp+98h+String1]
0x18001a7f3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001a7f8  nop
0x18001a7f9  lea     rcx, [rsp+98h+arg_18]
0x18001a801  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001a806  nop
0x18001a807  mov     rdx, [r12]
0x18001a80b  lea     rcx, [rdx-18h]
0x18001a80f  mov     rbx, [rsp+98h+String1]
0x18001a814  lea     rdi, [rbx-18h]
0x18001a818  cmp     rcx, rdi
0x18001a81b  jz      short loc_18001A859
0x18001a81d  cmp     dword ptr [rdi+10h], 0
0x18001a821  jl      short loc_18001A846
0x18001a823  mov     rax, [rdi]
0x18001a826  cmp     [rcx], rax
0x18001a829  jnz     short loc_18001A846
0x18001a82b  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18001a830  mov     rbx, rax
0x18001a833  mov     rcx, rdi; this
0x18001a836  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001a83b  add     rbx, 18h
0x18001a83f  mov     [rsp+98h+String1], rbx
0x18001a844  jmp     short loc_18001A859
0x18001a846  mov     r8d, [rdx-10h]
0x18001a84a  lea     rcx, [rsp+98h+String1]
0x18001a84f  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001a854  mov     rbx, [rsp+98h+String1]
0x18001a859  xor     r13b, r13b
0x18001a85c  xor     eax, eax
0x18001a85e  mov     rdi, [rsp+98h+arg_18]
0x18001a866  lea     r14, WPP_GLOBAL_Control
0x18001a86d  mov     [rsp+98h+arg_10], eax
0x18001a874  cmp     dword ptr [rbx-10h], 6
0x18001a878  jle     loc_18001AB75
0x18001a87e  test    eax, eax
0x18001a880  jnz     loc_18001A9A0
0x18001a886  lea     rcx, [r15+200h]
0x18001a88d  mov     rdx, rbx
0x18001a890  call    ?FindPrefix@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_NVCRevOrderCaseInsensitiveCStringWTraits@@V?$CElementTraits@_N@2@@ATL@@IEBAPEAVCNode@12@PEBG@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,bool,CRevOrderCaseInsensitiveCStringWTraits,ATL::CElementTraits<bool>>::FindPrefix(ushort const *)
0x18001a895  mov     r14, rax
0x18001a898  test    rax, rax
0x18001a89b  jz      loc_18001A93E
0x18001a8a1  lea     rcx, [rsp+98h+String2]
0x18001a8a6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001a8ab  nop
0x18001a8ac  mov     r9, [r14]
0x18001a8af  lea     rcx, [r9-18h]
0x18001a8b3  mov     rdx, [rsp+98h+String2]
0x18001a8b8  lea     r14, [rdx-18h]
0x18001a8bc  cmp     rcx, r14
0x18001a8bf  jz      short loc_18001A901
0x18001a8c1  cmp     dword ptr [r14+10h], 0
0x18001a8c6  jl      short loc_18001A8EB
0x18001a8c8  mov     rax, [r14]
0x18001a8cb  cmp     [rcx], rax
0x18001a8ce  jnz     short loc_18001A8EB
0x18001a8d0  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18001a8d5  mov     r15, rax
0x18001a8d8  mov     rcx, r14; this
0x18001a8db  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001a8e0  lea     rdx, [r15+18h]
0x18001a8e4  mov     [rsp+98h+String2], rdx
0x18001a8e9  jmp     short loc_18001A901
0x18001a8eb  mov     r8d, [r9-10h]
0x18001a8ef  mov     rdx, r9
0x18001a8f2  lea     rcx, [rsp+98h+String2]
0x18001a8f7  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001a8fc  mov     rdx, [rsp+98h+String2]; String2
0x18001a901  lea     r14, [rdx-18h]
0x18001a905  movsxd  r8, dword ptr [r14+8]; MaxCount
0x18001a909  mov     rcx, rbx; String1
0x18001a90c  call    cs:__imp__wcsnicmp
0x18001a912  nop
0x18001a913  mov     rcx, r14; this
0x18001a916  test    eax, eax
0x18001a918  jnz     short loc_18001A939
0x18001a91a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001a91f  nop
0x18001a920  lea     rcx, [rdi-18h]; this
0x18001a924  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001a929  nop
0x18001a92a  lea     rcx, [rbx-18h]; this
0x18001a92e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001a933  nop
0x18001a934  jmp     loc_18001AC19
0x18001a939  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001a93e  lea     rcx, [rbx-18h]
0x18001a942  lea     r14, [rdi-18h]
0x18001a946  cmp     rcx, r14
0x18001a949  jz      loc_18001AB33
0x18001a94f  cmp     dword ptr [r14+10h], 0
0x18001a954  jl      short loc_18001A97F
0x18001a956  mov     rax, [r14]
0x18001a959  cmp     [rcx], rax
0x18001a95c  jnz     short loc_18001A97F
0x18001a95e  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18001a963  mov     rdi, rax
0x18001a966  mov     rcx, r14; this
0x18001a969  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001a96e  add     rdi, 18h
0x18001a972  mov     [rsp+98h+arg_18], rdi
0x18001a97a  jmp     loc_18001AB33
0x18001a97f  mov     r8d, [rbx-10h]
0x18001a983  mov     rdx, rbx
0x18001a986  lea     rcx, [rsp+98h+arg_18]
0x18001a98e  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001a993  mov     rdi, [rsp+98h+arg_18]
0x18001a99b  jmp     loc_18001AB33
0x18001a9a0  mov     [rsp+98h+hTemplateFile], 0; hTemplateFile
0x18001a9a9  mov     [rsp+98h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18001a9b1  mov     [rsp+98h+dwCreationDisposition], 3; dwCreationDisposition
0x18001a9b9  xor     r9d, r9d; lpSecurityAttributes
0x18001a9bc  mov     edx, 80000000h; dwDesiredAccess
0x18001a9c1  lea     r8d, [r9+7]; dwShareMode
0x18001a9c5  mov     rcx, rbx; lpFileName
0x18001a9c8  call    cs:__imp_CreateFileW
0x18001a9ce  mov     r15, rax
0x18001a9d1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001a9d5  jnz     loc_18001AAAC
0x18001a9db  call    cs:__imp_GetLastError
0x18001a9e1  cmp     eax, 5
0x18001a9e4  jnz     short loc_18001AA44
0x18001a9e6  lea     rcx, [rbx-18h]
0x18001a9ea  lea     r14, [rdi-18h]
0x18001a9ee  cmp     rcx, r14
0x18001a9f1  jz      short loc_18001AA3C
0x18001a9f3  cmp     dword ptr [r14+10h], 0
0x18001a9f8  jl      short loc_18001AA20
0x18001a9fa  mov     rax, [r14]
0x18001a9fd  cmp     [rcx], rax
0x18001aa00  jnz     short loc_18001AA20
0x18001aa02  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18001aa07  mov     rdi, rax
0x18001aa0a  mov     rcx, r14; this
0x18001aa0d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001aa12  add     rdi, 18h
0x18001aa16  mov     [rsp+98h+arg_18], rdi
0x18001aa1e  jmp     short loc_18001AA3C
0x18001aa20  mov     r8d, [rbx-10h]
0x18001aa24  mov     rdx, rbx
0x18001aa27  lea     rcx, [rsp+98h+arg_18]
0x18001aa2f  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001aa34  mov     rdi, [rsp+98h+arg_18]
0x18001aa3c  mov     r13b, 1
0x18001aa3f  jmp     loc_18001AB33
0x18001aa44  add     eax, 0FFFFFFFEh
0x18001aa47  cmp     eax, 1
0x18001aa4a  jbe     short loc_18001AA93
0x18001aa4c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa53  cmp     rcx, r14
0x18001aa56  jz      loc_18001AB33
0x18001aa5c  test    byte ptr [rcx+1Ch], 4
0x18001aa60  jz      loc_18001AB33
0x18001aa66  mov     edx, 0D6h
0x18001aa6b  lea     rax, aUnexpectedErro_0; "Unexpected error on folder open"
0x18001aa72  mov     qword ptr [rsp+98h+dwCreationDisposition], rax
0x18001aa77  lea     r9, aFalse; "FALSE"
0x18001aa7e  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x18001aa85  mov     rcx, [rcx+10h]
0x18001aa89  call    WPP_SF_ss
0x18001aa8e  jmp     loc_18001AB33
0x18001aa93  lea     rcx, [rdi-18h]; this
0x18001aa97  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001aa9c  nop
0x18001aa9d  lea     rcx, [rbx-18h]; this
0x18001aaa1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001aaa6  nop
0x18001aaa7  jmp     loc_18001AC19
0x18001aaac  mov     rcx, rbx; lpFileName
0x18001aaaf  call    cs:__imp_GetFileAttributesW
0x18001aab5  cmp     eax, 0FFFFFFFFh
0x18001aab8  jz      short loc_18001AB2A
0x18001aaba  bt      eax, 0Eh
0x18001aabe  jnb     short loc_18001AB2A
0x18001aac0  mov     rax, [rsp+98h+arg_0]
0x18001aac8  cmp     dword ptr [rax+170h], 0
0x18001aacf  jnz     short loc_18001AB2A
0x18001aad1  lea     rcx, [rbx-18h]
0x18001aad5  lea     r14, [rdi-18h]
0x18001aad9  cmp     rcx, r14
0x18001aadc  jz      short loc_18001AB27
0x18001aade  cmp     dword ptr [r14+10h], 0
0x18001aae3  jl      short loc_18001AB0B
0x18001aae5  mov     rax, [r14]
0x18001aae8  cmp     [rcx], rax
0x18001aaeb  jnz     short loc_18001AB0B
0x18001aaed  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18001aaf2  mov     rdi, rax
0x18001aaf5  mov     rcx, r14; this
0x18001aaf8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001aafd  add     rdi, 18h
0x18001ab01  mov     [rsp+98h+arg_18], rdi
0x18001ab09  jmp     short loc_18001AB27
0x18001ab0b  mov     r8d, [rbx-10h]
0x18001ab0f  mov     rdx, rbx
0x18001ab12  lea     rcx, [rsp+98h+arg_18]
0x18001ab1a  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001ab1f  mov     rdi, [rsp+98h+arg_18]
0x18001ab27  mov     r13b, 1
0x18001ab2a  mov     rcx, r15; hObject
0x18001ab2d  call    cs:__imp_CloseHandle
0x18001ab33  mov     edx, 5Ch ; '\'
0x18001ab38  lea     rcx, [rsp+98h+String1]
0x18001ab3d  call    ?ReverseFind@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::ReverseFind(ushort)
0x18001ab42  test    eax, eax
0x18001ab44  js      short loc_18001AB6D
0x18001ab46  mov     edx, eax
0x18001ab48  lea     rcx, [rsp+98h+String1]
0x18001ab4d  call    ?Truncate@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Truncate(int)
0x18001ab52  mov     eax, [rsp+98h+arg_10]
0x18001ab59  inc     eax
0x18001ab5b  mov     rbx, [rsp+98h+String1]
0x18001ab60  mov     r15, [rsp+98h+arg_0]
0x18001ab68  jmp     loc_18001A866
0x18001ab6d  mov     r15, [rsp+98h+arg_0]
0x18001ab75  test    cs:Microsoft_Windows_FileHistory_EngineEnableBits, 2
0x18001ab7c  jz      short loc_18001AB8D
0x18001ab7e  mov     r8, rdi
0x18001ab81  lea     rdx, FileFailure_NoPermission
0x18001ab88  call    McTemplateU0z_EventWriteTransfer
0x18001ab8d  test    r13b, r13b
0x18001ab90  jz      short loc_18001ABBA
0x18001ab92  lea     r14, [r15+200h]
0x18001ab99  mov     rdx, rdi
0x18001ab9c  mov     rcx, r14
0x18001ab9f  call    ?Find@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_NVCRevOrderCaseInsensitiveCStringWTraits@@V?$CElementTraits@_N@2@@ATL@@IEBAPEAVCNode@12@PEBG@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,bool,CRevOrderCaseInsensitiveCStringWTraits,ATL::CElementTraits<bool>>::Find(ushort const *)
0x18001aba4  test    rax, rax
0x18001aba7  jnz     short loc_18001ABB6
0x18001aba9  mov     rdx, rdi
0x18001abac  mov     rcx, r14
0x18001abaf  call    ?RBInsert@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_NVCRevOrderCaseInsensitiveCStringWTraits@@V?$CElementTraits@_N@2@@ATL@@IEAAPEAVCNode@12@PEBG_N@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,bool,CRevOrderCaseInsensitiveCStringWTraits,ATL::CElementTraits<bool>>::RBInsert(ushort const *,bool)
0x18001abb4  jmp     short loc_18001ABBA
0x18001abb6  mov     byte ptr [rax+8], 1
0x18001abba  lea     rcx, [rdi-18h]; this
0x18001abbe  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001abc3  nop
0x18001abc4  lea     rcx, [rbx-18h]; this
0x18001abc8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001abcd  nop
0x18001abce  jmp     short loc_18001AC19
0x18001abd0  jmp     short $+2
0x18001abd2  cmp     [rsp+98h+arg_10], 0
0x18001abda  jge     short loc_18001AC11
0x18001abdc  lea     rax, WPP_GLOBAL_Control
0x18001abe3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001abea  cmp     rcx, rax
0x18001abed  jz      short loc_18001AC11
0x18001abef  test    byte ptr [rcx+1Ch], 4
0x18001abf3  jz      short loc_18001AC11
0x18001abf5  mov     edx, 0D8h
0x18001abfa  lea     r9, aSucceededHr; "SUCCEEDED(hr)"
0x18001ac01  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x18001ac08  mov     rcx, [rcx+10h]
0x18001ac0c  call    WPP_SF_s
0x18001ac11  mov     r12, [rsp+98h+arg_8]
0x18001ac19  mov     rcx, [r12]
0x18001ac1d  sub     rcx, 18h; this
0x18001ac21  add     rsp, 68h
0x18001ac25  pop     r15
0x18001ac27  pop     r14
0x18001ac29  pop     r13
0x18001ac2b  pop     r12
0x18001ac2d  pop     rdi
0x18001ac2e  pop     rbx
0x18001ac2f  jmp     ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
```
