# IdentifyTargetFromConfigFile(ushort const *,ushort const *,TargetInfo * *)

- ea: `0x1802ced34`
- end: `0x1802cf1db`
- name: `?IdentifyTargetFromConfigFile@@YAJPEBG0PEAPEAVTargetInfo@@@Z`
- size: `1191`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWCH, struct TargetInfo **)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x1802cf1e4`

## callees

- `0x1800727b8`
- `0x180098ccc`
- `0x1800bac94`
- `0x1800e5b60`
- `0x1800f0f40`
- `0x1800f16fc`
- `0x180162548`
- `0x1801aa5f8`
- `0x1802ced34`
- `0x1802d1e38`
- `0x180418074`
- `0x1804da4c0`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1802cf068`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1802cf068`
- `api-ms-win-crt-filesystem-l1-1-0!_wsplitpath_s` at `0x1802cee0e`
- `api-ms-win-crt-filesystem-l1-1-0!_wsplitpath_s` at `0x1802cee0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802cf00d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802cf14b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802cf00d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802cf14b`

## string_xrefs

- `0x1802cee29`: `\nLoading User-mode Dump Configuration File [%ws,%ws,%ws]\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IdentifyTargetFromConfigFile(const unsigned __int16 *a1, LPCWCH a2, struct TargetInfo **a3)
{
  struct TargetInfo **v3; // r13
  char *v6; // rax
  char *v7; // rbx
  int v8; // edi
  char *v9; // r15
  const unsigned __int16 *v10; // rcx
  const unsigned __int16 *v11; // r8
  const unsigned __int16 *v12; // rcx
  const unsigned __int16 *v13; // r8
  const unsigned __int16 *v14; // rcx
  const unsigned __int16 *v15; // r8
  unsigned int v16; // r9d
  bool v17; // zf
  unsigned int v18; // r12d
  __int64 v19; // rsi
  const WCHAR *v20; // r13
  const wchar_t *v21; // r14
  unsigned int v22; // r15d
  unsigned int v23; // r9d
  unsigned int DirCount; // [rsp+28h] [rbp-E0h]
  unsigned int DirCounta; // [rsp+28h] [rbp-E0h]
  unsigned int DirCountb; // [rsp+28h] [rbp-E0h]
  unsigned int DirCountc; // [rsp+28h] [rbp-E0h]
  HANDLE hObject; // [rsp+58h] [rbp-B0h] BYREF
  LPCWCH v30; // [rsp+60h] [rbp-A8h]
  struct TargetInfo **v31; // [rsp+68h] [rbp-A0h]
  __int64 v32; // [rsp+70h] [rbp-98h]
  wchar_t Dir[264]; // [rsp+78h] [rbp-90h] BYREF
  wchar_t Drive[264]; // [rsp+288h] [rbp+180h] BYREF
  wchar_t v35[264]; // [rsp+498h] [rbp+390h] BYREF
  wchar_t v36[784]; // [rsp+6A8h] [rbp+5A0h] BYREF

  v32 = -2;
  v3 = a3;
  v31 = a3;
  v30 = a2;
  if ( a1
    && a3
    && (*a3 = 0, DbgGetPrivateProfileStringW(a1, L"default", (const unsigned __int16 *)a3, v35, DirCount, a1)) )
  {
    memset(Drive, 0, 0x208u);
    memset(Dir, 0, 0x208u);
    _wsplitpath_s(a1, Drive, 0x104u, Dir, 0x104u, 0, 0, 0, 0);
    dprintf(L"\nLoading User-mode Dump Configuration File [%ws,%ws,%ws]\n", a1, Drive, Dir);
    dprintf(L"\tdefault dump: [%ws]\n", v35);
    v6 = (char *)operator new(0x2A28u, (const struct std::nothrow_t *)&std::nothrow);
    v7 = v6;
    hObject = v6;
    if ( v6 )
    {
      UserMiniDumpTargetInfo::UserMiniDumpTargetInfo((UserMiniDumpTargetInfo *)v6, 1);
      *(_QWORD *)v7 = &UserMultiDumpTargetInfo::`vftable';
      *(_OWORD *)(v7 + 8680) = 0;
      *(_OWORD *)(v7 + 8696) = 0;
      memset(v7 + 8712, 0, 0x820u);
    }
    else
    {
      v7 = 0;
    }
    if ( v7 )
    {
      v9 = v7 + 8712;
      StringCchCopyW((wchar_t *)v7 + 4356, 0x104u, v35);
      if ( DbgGetPrivateProfileStringW(v10, L"handle", v11, (unsigned __int16 *)v7 + 4876, DirCounta, a1) )
        dprintf(L"\thandle dump: [%ws]\n", v7 + 9752);
      else
        *((_WORD *)v7 + 4876) = 0;
      if ( DbgGetPrivateProfileStringW(v12, L"memory", v13, (unsigned __int16 *)v7 + 4616, DirCountb, a1) )
        dprintf(L"\tmemory dump: [%ws]\n", v7 + 9232);
      else
        *((_WORD *)v7 + 4616) = 0;
      if ( DbgGetPrivateProfileStringW(v14, L"module", v15, (unsigned __int16 *)v7 + 5136, DirCountc, a1) )
        dprintf(L"\tmodule list dump: [%ws]\n", v7 + 10272);
      else
        *((_WORD *)v7 + 5136) = 0;
      memset(v36, 0, 0x618u);
      hObject = 0;
      if ( (unsigned int)QueryDumpNameFromCab((LPCWCH)v7 + 4356, a2, v36, v16, &hObject) )
        StringCchPrintfW(v36, 0x30Cu, L"%ws%ws%ws", Drive, Dir, v7 + 8712);
      v8 = FileInitialize(v36, 0, 0, 0, 0, (struct TargetInfo **)v7 + 1085, 0);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      v17 = v8 == 0;
      if ( v8 >= 0 )
      {
        TargetInfo::Unlink(*((TargetInfo **)v7 + 1085));
        v18 = 1;
        v19 = 1;
        v20 = v30;
        do
        {
          v21 = (const wchar_t *)&v9[520 * v19];
          if ( *v21 )
          {
            v22 = 0;
            do
            {
              if ( !_wcsicmp(v21, (const wchar_t *)&v7[520 * v22 + 8712]) )
              {
                *(_QWORD *)&v7[8 * v19 + 8680] = *(_QWORD *)&v7[8 * v22 + 8680];
                goto LABEL_36;
              }
              ++v22;
            }
            while ( v22 < v18 );
            memset(v36, 0, 0x618u);
            hObject = 0;
            v8 = QueryDumpNameFromCab(v21, v20, v36, v23, &hObject);
            if ( v8 )
            {
              StringCchPrintfW(v36, 0x30Cu, L"%ws%ws%ws", Drive, Dir, v21);
              v8 = 0;
            }
            if ( (unsigned int)FileInitialize(v36, 0, 0, 0, 0, (struct TargetInfo **)&v7[8 * v19 + 8680], 0) )
              *(_QWORD *)&v7[8 * v19 + 8680] = 0;
            else
              TargetInfo::Unlink(*(TargetInfo **)&v7[8 * v19 + 8680]);
            if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              CloseHandle(hObject);
LABEL_36:
            v9 = v7 + 8712;
          }
          ++v18;
          ++v19;
        }
        while ( v18 < 4 );
        v3 = v31;
        v17 = v8 == 0;
      }
      if ( v17 )
        *v3 = (struct TargetInfo *)v7;
      else
        (**(void (__fastcall ***)(void *, __int64))v7)(v7, 1);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1802ced34  mov     rax, rsp
0x1802ced37  push    rbp
0x1802ced38  push    rsi
0x1802ced39  push    rdi
0x1802ced3a  push    r12
0x1802ced3c  push    r13
0x1802ced3e  push    r14
0x1802ced40  push    r15
0x1802ced42  lea     rbp, [rax-0C08h]
0x1802ced49  sub     rsp, 0CD0h
0x1802ced50  mov     [rsp+0D00h+var_C98], 0FFFFFFFFFFFFFFFEh
0x1802ced59  mov     [rax+20h], rbx
0x1802ced5d  mov     rax, cs:__security_cookie
0x1802ced64  xor     rax, rsp
0x1802ced67  mov     [rbp+0C00h+var_40], rax
0x1802ced6e  mov     r13, r8
0x1802ced71  mov     [rsp+0D00h+var_CA0], r8
0x1802ced76  mov     r14, rdx
0x1802ced79  mov     [rsp+0D00h+var_CA8], rdx
0x1802ced7e  mov     rdi, rcx
0x1802ced81  xor     r12d, r12d
0x1802ced84  test    rcx, rcx
0x1802ced87  jz      loc_1802CF1A9
0x1802ced8d  test    r8, r8
0x1802ced90  jz      loc_1802CF1A9
0x1802ced96  mov     [r8], r12
0x1802ced99  mov     [rsp+0D00h+Filename], rcx; unsigned __int16 *
0x1802ced9e  lea     r9, [rbp+0C00h+var_870]; unsigned __int16 *
0x1802ceda5  lea     rdx, aDefault; "default"
0x1802cedac  call    ?DbgGetPrivateProfileStringW@@YAKPEBG00PEAGK0@Z; DbgGetPrivateProfileStringW(ushort const *,ushort const *,ushort const *,ushort *,ulong,ushort const *)
0x1802cedb1  test    eax, eax
0x1802cedb3  jz      loc_1802CF1A9
0x1802cedb9  mov     ebx, 208h
0x1802cedbe  mov     r8d, ebx; Size
0x1802cedc1  xor     edx, edx; Val
0x1802cedc3  lea     rcx, [rbp+0C00h+Drive]; void *
0x1802cedca  call    memset
0x1802cedcf  mov     r8d, ebx; Size
0x1802cedd2  xor     edx, edx; Val
0x1802cedd4  lea     rcx, [rsp+0D00h+Dir]; void *
0x1802cedd9  call    memset
0x1802cedde  mov     [rsp+40h], r12; ExtCount
0x1802cede3  mov     [rsp+0D00h+Ext], r12; Ext
0x1802cede8  mov     [rsp+0D00h+FilenameCount], r12; FilenameCount
0x1802ceded  mov     [rsp+0D00h+Filename], r12; Filename
0x1802cedf2  mov     esi, 104h
0x1802cedf7  mov     [rsp+0D00h+DirCount], rsi; unsigned int
0x1802cedfc  lea     r9, [rsp+0D00h+Dir]; Dir
0x1802cee01  mov     r8d, esi; DriveCount
0x1802cee04  lea     rdx, [rbp+0C00h+Drive]; Drive
0x1802cee0b  mov     rcx, rdi; FullPath
0x1802cee0e  call    cs:__imp__wsplitpath_s
0x1802cee15  nop     dword ptr [rax+rax+00h]
0x1802cee1a  lea     r9, [rsp+0D00h+Dir]
0x1802cee1f  lea     r8, [rbp+0C00h+Drive]
0x1802cee26  mov     rdx, rdi
0x1802cee29  lea     rcx, aLoadingUserMod; "\nLoading User-mode Dump Configuration "...
0x1802cee30  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1802cee35  lea     rdx, [rbp+0C00h+var_870]
0x1802cee3c  lea     rcx, aDefaultDumpWs; "\tdefault dump: [%ws]\n"
0x1802cee43  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1802cee48  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1802cee4f  mov     ecx, 2A28h; unsigned __int64
0x1802cee54  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1802cee59  mov     rbx, rax
0x1802cee5c  mov     [rsp+0D00h+hObject], rax
0x1802cee61  test    rax, rax
0x1802cee64  jz      short loc_1802CEEA4
0x1802cee66  lea     edx, [r12+1]; int
0x1802cee6b  mov     rcx, rax; this
0x1802cee6e  call    ??0UserMiniDumpTargetInfo@@QEAA@H@Z; UserMiniDumpTargetInfo::UserMiniDumpTargetInfo(int)
0x1802cee73  lea     rax, ??_7UserMultiDumpTargetInfo@@6B@; const UserMultiDumpTargetInfo::`vftable'
0x1802cee7a  mov     [rbx], rax
0x1802cee7d  xorps   xmm0, xmm0
0x1802cee80  movups  xmmword ptr [rbx+21E8h], xmm0
0x1802cee87  movups  xmmword ptr [rbx+21F8h], xmm0
0x1802cee8e  lea     rcx, [rbx+2208h]; void *
0x1802cee95  xor     edx, edx; Val
0x1802cee97  mov     r8d, 820h; Size
0x1802cee9d  call    memset
0x1802ceea2  jmp     short loc_1802CEEA7
0x1802ceea4  mov     rbx, r12
0x1802ceea7  test    rbx, rbx
0x1802ceeaa  jnz     short loc_1802CEEB6
0x1802ceeac  mov     edi, 8007000Eh
0x1802ceeb1  jmp     loc_1802CF1AE
0x1802ceeb6  lea     r15, [rbx+2208h]
0x1802ceebd  lea     r8, [rbp+0C00h+var_870]; wchar_t *
0x1802ceec4  mov     rdx, rsi; unsigned __int64
0x1802ceec7  mov     rcx, r15; wchar_t *
0x1802ceeca  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1802ceecf  lea     rsi, [rbx+2618h]
0x1802ceed6  mov     [rsp+0D00h+Filename], rdi; unsigned __int16 *
0x1802ceedb  mov     r9, rsi; unsigned __int16 *
0x1802ceede  lea     rdx, aHandle_1; "handle"
0x1802ceee5  call    ?DbgGetPrivateProfileStringW@@YAKPEBG00PEAGK0@Z; DbgGetPrivateProfileStringW(ushort const *,ushort const *,ushort const *,ushort *,ulong,ushort const *)
0x1802ceeea  test    eax, eax
0x1802ceeec  jnz     short loc_1802CEEF4
0x1802ceeee  mov     [rsi], r12w
0x1802ceef2  jmp     short loc_1802CEF03
0x1802ceef4  mov     rdx, rsi
0x1802ceef7  lea     rcx, aHandleDumpWs; "\thandle dump: [%ws]\n"
0x1802ceefe  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1802cef03  lea     rsi, [rbx+2410h]
0x1802cef0a  mov     [rsp+0D00h+Filename], rdi; unsigned __int16 *
0x1802cef0f  mov     r9, rsi; unsigned __int16 *
0x1802cef12  lea     rdx, aMemory; "memory"
0x1802cef19  call    ?DbgGetPrivateProfileStringW@@YAKPEBG00PEAGK0@Z; DbgGetPrivateProfileStringW(ushort const *,ushort const *,ushort const *,ushort *,ulong,ushort const *)
0x1802cef1e  test    eax, eax
0x1802cef20  jnz     short loc_1802CEF28
0x1802cef22  mov     [rsi], r12w
0x1802cef26  jmp     short loc_1802CEF37
0x1802cef28  mov     rdx, rsi
0x1802cef2b  lea     rcx, aMemoryDumpWs; "\tmemory dump: [%ws]\n"
0x1802cef32  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1802cef37  lea     rsi, [rbx+2820h]
0x1802cef3e  mov     [rsp+0D00h+Filename], rdi; unsigned __int16 *
0x1802cef43  mov     r9, rsi; unsigned __int16 *
0x1802cef46  lea     rdx, aModule_0; "module"
0x1802cef4d  call    ?DbgGetPrivateProfileStringW@@YAKPEBG00PEAGK0@Z; DbgGetPrivateProfileStringW(ushort const *,ushort const *,ushort const *,ushort *,ulong,ushort const *)
0x1802cef52  test    eax, eax
0x1802cef54  jnz     short loc_1802CEF5C
0x1802cef56  mov     [rsi], r12w
0x1802cef5a  jmp     short loc_1802CEF6B
0x1802cef5c  mov     rdx, rsi
0x1802cef5f  lea     rcx, aModuleListDump; "\tmodule list dump: [%ws]\n"
0x1802cef66  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1802cef6b  xor     edx, edx; Val
0x1802cef6d  mov     r8d, 618h; Size
0x1802cef73  lea     rcx, [rbp+0C00h+var_660]; void *
0x1802cef7a  call    memset
0x1802cef7f  mov     [rsp+0D00h+hObject], r12
0x1802cef84  lea     rax, [rsp+0D00h+hObject]
0x1802cef89  mov     [rsp+0D00h+DirCount], rax; void **
0x1802cef8e  lea     r8, [rbp+0C00h+var_660]; wchar_t *
0x1802cef95  mov     rdx, r14; LPCWCH
0x1802cef98  mov     rcx, r15; lpWideCharStr
0x1802cef9b  call    ?QueryDumpNameFromCab@@YAJPEBG0PEAGKPEAPEAX@Z; QueryDumpNameFromCab(ushort const *,ushort const *,ushort *,ulong,void * *)
0x1802cefa0  test    eax, eax
0x1802cefa2  jz      short loc_1802CEFD2
0x1802cefa4  mov     [rsp+0D00h+Filename], r15
0x1802cefa9  lea     rax, [rsp+0D00h+Dir]
0x1802cefae  mov     [rsp+0D00h+DirCount], rax
0x1802cefb3  lea     r9, [rbp+0C00h+Drive]
0x1802cefba  lea     r8, aWsWsWs; "%ws%ws%ws"
0x1802cefc1  mov     edx, 30Ch; unsigned __int64
0x1802cefc6  lea     rcx, [rbp+0C00h+var_660]; unsigned __int16 *
0x1802cefcd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1802cefd2  lea     rsi, [rbx+21E8h]
0x1802cefd9  mov     dword ptr [rsp+0D00h+FilenameCount], r12d; char
0x1802cefde  mov     [rsp+0D00h+Filename], rsi; struct TargetInfo **
0x1802cefe3  mov     dword ptr [rsp+0D00h+DirCount], r12d; char
0x1802cefe8  xor     r9d, r9d; void *
0x1802cefeb  xor     r8d, r8d; unsigned __int16 *
0x1802cefee  xor     edx, edx; unsigned __int64
0x1802ceff0  lea     rcx, [rbp+0C00h+var_660]; unsigned __int16 *
0x1802ceff7  call    ?FileInitialize@@YAJPEBG_K0PEAXKPEAPEAVTargetInfo@@K@Z; FileInitialize(ushort const *,unsigned __int64,ushort const *,void *,ulong,TargetInfo * *,ulong)
0x1802ceffc  mov     edi, eax
0x1802ceffe  mov     rcx, [rsp+0D00h+hObject]; hObject
0x1802cf003  lea     rdx, [rcx-1]
0x1802cf007  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1802cf00b  ja      short loc_1802CF019
0x1802cf00d  call    cs:__imp_CloseHandle
0x1802cf014  nop     dword ptr [rax+rax+00h]
0x1802cf019  test    edi, edi
0x1802cf01b  js      loc_1802CF18C
0x1802cf021  mov     rcx, [rsi]; this
0x1802cf024  call    ?Unlink@TargetInfo@@QEAAXXZ; TargetInfo::Unlink(void)
0x1802cf029  mov     eax, 1
0x1802cf02e  mov     r12d, eax
0x1802cf031  mov     esi, eax
0x1802cf033  mov     r13, [rsp+0D00h+var_CA8]
0x1802cf038  xor     eax, eax
0x1802cf03a  imul    r14, rsi, 208h
0x1802cf041  add     r14, r15
0x1802cf044  cmp     [r14], ax
0x1802cf048  jz      loc_1802CF175
0x1802cf04e  mov     r15d, eax
0x1802cf051  mov     eax, r15d
0x1802cf054  imul    rdx, rax, 208h
0x1802cf05b  lea     rax, [rbx+2208h]
0x1802cf062  add     rdx, rax; String2
0x1802cf065  mov     rcx, r14; String1
0x1802cf068  call    cs:__imp__wcsicmp
0x1802cf06f  nop     dword ptr [rax+rax+00h]
0x1802cf074  test    eax, eax
0x1802cf076  jz      loc_1802CF159
0x1802cf07c  inc     r15d
0x1802cf07f  cmp     r15d, r12d
0x1802cf082  jb      short loc_1802CF051
0x1802cf084  xor     edx, edx; Val
0x1802cf086  mov     r8d, 618h; Size
0x1802cf08c  lea     rcx, [rbp+0C00h+var_660]; void *
0x1802cf093  call    memset
0x1802cf098  xor     r15d, r15d
0x1802cf09b  mov     [rsp+0D00h+hObject], r15
0x1802cf0a0  lea     rax, [rsp+0D00h+hObject]
0x1802cf0a5  mov     [rsp+0D00h+DirCount], rax; void **
0x1802cf0aa  lea     r8, [rbp+0C00h+var_660]; wchar_t *
0x1802cf0b1  mov     rdx, r13; LPCWCH
0x1802cf0b4  mov     rcx, r14; lpWideCharStr
0x1802cf0b7  call    ?QueryDumpNameFromCab@@YAJPEBG0PEAGKPEAPEAX@Z; QueryDumpNameFromCab(ushort const *,ushort const *,ushort *,ulong,void * *)
0x1802cf0bc  mov     edi, eax
0x1802cf0be  test    eax, eax
0x1802cf0c0  jz      short loc_1802CF0F3
0x1802cf0c2  mov     [rsp+0D00h+Filename], r14
0x1802cf0c7  lea     rax, [rsp+0D00h+Dir]
0x1802cf0cc  mov     [rsp+0D00h+DirCount], rax
0x1802cf0d1  lea     r9, [rbp+0C00h+Drive]
0x1802cf0d8  lea     r8, aWsWsWs; "%ws%ws%ws"
0x1802cf0df  mov     edx, 30Ch; unsigned __int64
0x1802cf0e4  lea     rcx, [rbp+0C00h+var_660]; unsigned __int16 *
0x1802cf0eb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1802cf0f0  mov     edi, r15d
0x1802cf0f3  lea     rax, [rsi+43Dh]
0x1802cf0fa  lea     rax, [rbx+rax*8]
0x1802cf0fe  mov     dword ptr [rsp+0D00h+FilenameCount], r15d; char
0x1802cf103  mov     [rsp+0D00h+Filename], rax; struct TargetInfo **
0x1802cf108  mov     dword ptr [rsp+0D00h+DirCount], r15d; char
0x1802cf10d  xor     r9d, r9d; void *
0x1802cf110  xor     r8d, r8d; unsigned __int16 *
0x1802cf113  xor     edx, edx; unsigned __int64
0x1802cf115  lea     rcx, [rbp+0C00h+var_660]; unsigned __int16 *
0x1802cf11c  call    ?FileInitialize@@YAJPEBG_K0PEAXKPEAPEAVTargetInfo@@K@Z; FileInitialize(ushort const *,unsigned __int64,ushort const *,void *,ulong,TargetInfo * *,ulong)
0x1802cf121  test    eax, eax
0x1802cf123  jnz     short loc_1802CF134
0x1802cf125  mov     rcx, [rbx+rsi*8+21E8h]; this
0x1802cf12d  call    ?Unlink@TargetInfo@@QEAAXXZ; TargetInfo::Unlink(void)
0x1802cf132  jmp     short loc_1802CF13C
0x1802cf134  mov     [rbx+rsi*8+21E8h], r15
0x1802cf13c  mov     rcx, [rsp+0D00h+hObject]; hObject
0x1802cf141  lea     rax, [rcx-1]
0x1802cf145  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1802cf149  ja      short loc_1802CF16C
0x1802cf14b  call    cs:__imp_CloseHandle
0x1802cf152  nop     dword ptr [rax+rax+00h]
0x1802cf157  jmp     short loc_1802CF16C
0x1802cf159  mov     eax, r15d
0x1802cf15c  mov     rcx, [rbx+rax*8+21E8h]
0x1802cf164  mov     [rbx+rsi*8+21E8h], rcx
0x1802cf16c  lea     r15, [rbx+2208h]
0x1802cf173  xor     eax, eax
0x1802cf175  inc     r12d
0x1802cf178  inc     rsi
0x1802cf17b  cmp     r12d, 4
0x1802cf17f  jb      loc_1802CF03A
0x1802cf185  mov     r13, [rsp+0D00h+var_CA0]
0x1802cf18a  test    edi, edi
0x1802cf18c  jnz     short loc_1802CF194
0x1802cf18e  mov     [r13+0], rbx
0x1802cf192  jmp     short loc_1802CF1AE
0x1802cf194  mov     rax, [rbx]
0x1802cf197  mov     edx, 1
0x1802cf19c  mov     rcx, rbx
0x1802cf19f  mov     rax, [rax]
0x1802cf1a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802cf1a7  jmp     short loc_1802CF1AE
0x1802cf1a9  mov     edi, 80070057h
0x1802cf1ae  mov     eax, edi
0x1802cf1b0  mov     rcx, [rbp+0C00h+var_40]
0x1802cf1b7  xor     rcx, rsp; StackCookie
0x1802cf1ba  call    __security_check_cookie
0x1802cf1bf  mov     rbx, [rsp+0D00h+arg_18]
0x1802cf1c7  add     rsp, 0CD0h
0x1802cf1ce  pop     r15
0x1802cf1d0  pop     r14
0x1802cf1d2  pop     r13
0x1802cf1d4  pop     r12
0x1802cf1d6  pop     rdi
0x1802cf1d7  pop     rsi
0x1802cf1d8  pop     rbp
0x1802cf1d9  retn
```
