# CreateCabFromDump(char const *,char const *,ulong)

- ea: `0x180216000`
- end: `0x1802164b8`
- name: `?CreateCabFromDump@@YAJPEBD0K@Z`
- size: `1208`
- prototype: `__int64 __fastcall(const char *, const char *, unsigned int)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800a3a00`
- `0x1801efe20`

## callees

- `0x1800727b8`
- `0x1800793cc`
- `0x18007cf9c`
- `0x18007db58`
- `0x1800804c4`
- `0x18008d550`
- `0x1800a4044`
- `0x1800c12b8`
- `0x1800e8b30`
- `0x1800f0f40`
- `0x180159910`
- `0x180190ecc`
- `0x180190f50`
- `0x1801951ec`
- `0x180216000`
- `0x18021705c`
- `0x1804da4c0`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180216415`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180216415`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameA` at `0x18021622b`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameA` at `0x18021622b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180216330`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180216330`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x18021619e`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x18021619e`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18021631f`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18021631f`
- `dbghelp!SymGetModuleInfoW64` at `0x1802163c6`
- `dbghelp!SymGetModuleInfoW64` at `0x1802163c6`

## string_xrefs

- `0x1802160b7`: `Unable to create CAB, %s\n`
- `0x1802160c8`: `Creating a cab file can take a VERY VERY long time\n.Ctrl-C can only interrupt the command after a file has been added to the cab.\n`
- `0x18021618f`: `Unable to create %hs\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CreateCabFromDump(const char *a1, const char *a2, int a3)
{
  int v6; // r9d
  unsigned int v7; // ebx
  int DumpCab; // eax
  unsigned __int16 *v9; // rax
  TargetInfo *v10; // rsi
  unsigned int i; // edi
  __int64 v12; // rax
  __int64 v13; // rax
  const WCHAR *v14; // rdx
  char *v15; // rcx
  HMODULE v17; // rcx
  __int64 j; // rdi
  __int64 v19; // rdx
  const WCHAR *v20; // rdx
  char *v21; // rcx
  __int64 v22; // rax
  char *v23; // rcx
  char *v24; // rcx
  unsigned int v25; // [rsp+60h] [rbp-A0h] BYREF
  int v26; // [rsp+64h] [rbp-9Ch] BYREF
  LPCVOID lpBaseAddress; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hObject[2]; // [rsp+70h] [rbp-90h] BYREF
  char *Str; // [rsp+80h] [rbp-80h] BYREF
  int v30; // [rsp+8Ch] [rbp-74h]
  const WCHAR *v31; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned int v32; // [rsp+1ACh] [rbp+ACh]
  char v33; // [rsp+1B8h] [rbp+B8h] BYREF
  _DWORD ModuleInfo[820]; // [rsp+350h] [rbp+250h] BYREF
  CHAR Filename[272]; // [rsp+1020h] [rbp+F20h] BYREF

  hObject[1] = (HANDLE)-2LL;
  DbsDeclDynamicString<char,260,1>::DbsDeclDynamicString<char,260,1>(&Str);
  DbsDynamicString<unsigned short>::DbsDynamicString<unsigned short>((unsigned int)&v31, (unsigned int)&v33, 200, v6, 1);
  if ( (g_EngOptions & 0x400000) == 0 )
  {
    DumpCab = CreateDumpCab(a2);
    v7 = DumpCab;
    if ( DumpCab )
    {
      v9 = FormatStatusCode(DumpCab);
      ErrOut(L"Unable to create CAB, %s\n", v9);
      goto LABEL_21;
    }
    WarnOut(
      L"Creating a cab file can take a VERY VERY long time\n"
       ".Ctrl-C can only interrupt the command after a file has been added to the cab.\n");
    if ( a1 )
    {
      if ( !(unsigned int)DumpCabAdd(a1) )
      {
LABEL_18:
        v7 = -2147418113;
LABEL_19:
        CloseDumpCab();
        goto LABEL_20;
      }
    }
    else
    {
      v10 = g_Target;
      for ( i = 0; i < 2; ++i )
      {
        if ( (*(__int64 (__fastcall **)(TargetInfo *, _QWORD))(*(_QWORD *)v10 + 16LL))(v10, i) )
        {
          v12 = (*(__int64 (__fastcall **)(TargetInfo *, _QWORD))(*(_QWORD *)v10 + 16LL))(v10, i);
          if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12) )
          {
            v13 = (*(__int64 (__fastcall **)(TargetInfo *, _QWORD))(*(_QWORD *)v10 + 16LL))(v10, i);
            if ( *(_DWORD *)(v13 + 36) < 2u )
              v14 = 0;
            else
              v14 = *(const WCHAR **)(v13 + 24);
            v7 = DbsDynamicString<char>::CopyStrStatus((DbsDynamicBuffer *)&Str, v14, -1);
            if ( v7 )
              goto LABEL_19;
            v15 = 0;
            if ( v30 )
              v15 = Str;
            if ( !(unsigned int)DumpCabAdd(v15) )
              goto LABEL_18;
          }
        }
      }
    }
    if ( (a3 & 0x40000000) != 0 )
    {
      v17 = (HMODULE)*((_QWORD *)g_Process + 66);
      if ( v17 && GetModuleFileNameA(v17, Filename, 0x104u) )
        DumpCabAdd(Filename);
      for ( j = *((_QWORD *)g_Process + 16); j; j = *(_QWORD *)(j + 8) )
      {
        if ( *(_DWORD *)(j + 980) >= 4u )
        {
          v20 = *(const WCHAR **)(j + 968);
        }
        else
        {
          if ( (a3 & 0x10000000) == 0 )
            goto LABEL_43;
          v26 = 0;
          lpBaseAddress = 0;
          v25 = 0;
          hObject[0] = 0;
          if ( !IMAGE_HEADER_INFO::Update(
                  (IMAGE_HEADER_INFO *)(j + 48),
                  *(struct ProcessInfo **)j,
                  *(_QWORD *)(j + 32),
                  *(void **)(j + 24),
                  0x2DFFu) )
            goto LABEL_43;
          v19 = *(_DWORD *)(j + 548) < 2u ? 0LL : *(_QWORD *)(j + 536);
          if ( (unsigned int)FindImageFile(
                               (__int64)g_Process,
                               v19,
                               *(_DWORD *)(j + 40),
                               *(_DWORD *)(j + 60),
                               *(_DWORD *)(j + 64),
                               1,
                               &v26,
                               (void **)&lpBaseAddress,
                               &v25,
                               hObject,
                               (__int64)&v31) )
            goto LABEL_43;
          UnmapViewOfFile(lpBaseAddress);
          CloseHandle(hObject[0]);
          v20 = 0;
          if ( v32 >= 2 )
            v20 = v31;
        }
        v7 = DbsDynamicString<char>::CopyStrStatus((DbsDynamicBuffer *)&Str, v20, -1);
        if ( !v7 )
        {
          v21 = 0;
          if ( v30 )
            v21 = Str;
          DumpCabAdd(v21);
        }
LABEL_43:
        memset(&ModuleInfo[1], 0, 3268);
        ModuleInfo[0] = 3272;
        ModuleInfo[816] = 1;
        if ( SymGetModuleInfoW64(*((HANDLE *)g_Process + 51), *(_QWORD *)(j + 32), (PIMAGEHLP_MODULEW64)ModuleInfo) )
        {
          if ( LOWORD(ModuleInfo[153]) )
          {
            v22 = -1;
            do
              ++v22;
            while ( *((_WORD *)&ModuleInfo[153] + v22) );
            if ( (unsigned int)v22 > 4
              && !_wcsicmp((const wchar_t *)&ModuleInfo[153] + (unsigned int)(v22 - 4), L".dbg") )
            {
              v7 = DbsDynamicString<char>::CopyStrStatus((DbsDynamicBuffer *)&Str, (LPCWCH)&ModuleInfo[153], -1);
              if ( !v7 )
              {
                v23 = 0;
                if ( v30 )
                  v23 = Str;
                DumpCabAdd(v23);
              }
            }
          }
          if ( LOWORD(ModuleInfo[281]) )
          {
            v7 = DbsDynamicString<char>::CopyStrStatus((DbsDynamicBuffer *)&Str, (LPCWCH)&ModuleInfo[281], -1);
            if ( !v7 )
            {
              v24 = 0;
              if ( v30 )
                v24 = Str;
              DumpCabAdd(v24);
            }
          }
        }
      }
    }
    CloseDumpCab();
    if ( !v7 )
    {
      dprintf(L"Wrote %hs\n", a2);
      goto LABEL_21;
    }
LABEL_20:
    ErrOut(L"Unable to create %hs\n", a2);
    DeleteFileA(a2);
    goto LABEL_21;
  }
  ErrOut(
    L"This dump file contains sensitive data.\n"
     "Gathering a dump of this data has been disabled and your dump could not be saved.\n");
  v7 = -2147467259;
LABEL_21:
  DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&v31);
  DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&Str);
  return v7;
}

```

## disassembly

```asm
0x180216000  push    rbp
0x180216002  push    rdi
0x180216003  push    r12
0x180216005  push    r14
0x180216007  push    r15
0x180216009  lea     rbp, [rsp-1040h]
0x180216011  mov     eax, 1140h
0x180216016  call    _alloca_probe
0x18021601b  sub     rsp, rax
0x18021601e  mov     [rsp+1160h+var_10E8], 0FFFFFFFFFFFFFFFEh
0x180216027  mov     [rsp+1160h+arg_10], rbx
0x18021602f  mov     [rsp+1160h+arg_18], rsi
0x180216037  mov     rax, cs:__security_cookie
0x18021603e  xor     rax, rsp
0x180216041  mov     [rbp+1060h+var_30], rax
0x180216048  mov     r15d, r8d
0x18021604b  mov     r14, rdx
0x18021604e  mov     rdi, rcx
0x180216051  lea     rcx, [rbp+1060h+Str]
0x180216055  call    ??0?$DbsDeclDynamicString@D$0BAE@$00@@QEAA@XZ; DbsDeclDynamicString<char,260,1>::DbsDeclDynamicString<char,260,1>(void)
0x18021605a  nop
0x18021605b  mov     byte ptr [rsp+1160h+var_1140], 1
0x180216060  mov     r8d, 0C8h
0x180216066  lea     rdx, [rbp+1060h+var_FA8]
0x18021606d  lea     rcx, [rbp+1060h+var_FC0]
0x180216074  call    ??0?$DbsDynamicString@G@@QEAA@PEAGK_N1@Z; DbsDynamicString<ushort>::DbsDynamicString<ushort>(ushort *,ulong,bool,bool)
0x180216079  nop
0x18021607a  test    cs:?g_EngOptions@@3KA, 400000h; ulong g_EngOptions
0x180216084  jz      short loc_18021609C
0x180216086  lea     rcx, aThisDumpFileCo; "This dump file contains sensitive data."...
0x18021608d  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x180216092  mov     ebx, 80004005h
0x180216097  jmp     loc_1802161AB
0x18021609c  mov     rcx, r14; char *
0x18021609f  call    ?CreateDumpCab@@YAJPEBD@Z; CreateDumpCab(char const *)
0x1802160a4  mov     ebx, eax
0x1802160a6  xor     r12d, r12d
0x1802160a9  test    eax, eax
0x1802160ab  jz      short loc_1802160C8
0x1802160ad  mov     ecx, eax; int
0x1802160af  call    ?FormatStatusCode@@YAPEAGJ@Z; FormatStatusCode(long)
0x1802160b4  mov     rdx, rax
0x1802160b7  lea     rcx, aUnableToCreate_9; "Unable to create CAB, %s\n"
0x1802160be  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1802160c3  jmp     loc_1802161AB
0x1802160c8  lea     rcx, aCreatingACabFi; "Creating a cab file can take a VERY VER"...
0x1802160cf  call    ?WarnOut@@YAXPEBGZZ; WarnOut(ushort const *,...)
0x1802160d4  or      esi, 0FFFFFFFFh
0x1802160d7  test    rdi, rdi
0x1802160da  jnz     loc_1802161EF
0x1802160e0  mov     rsi, cs:?g_Target@@3PEAVTargetInfo@@EA; TargetInfo * g_Target
0x1802160e7  mov     edi, r12d
0x1802160ea  cmp     edi, 2
0x1802160ed  jnb     loc_1802161FD
0x1802160f3  mov     rax, [rsi]
0x1802160f6  mov     edx, edi
0x1802160f8  mov     rcx, rsi
0x1802160fb  mov     rax, [rax+10h]
0x1802160ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180216104  test    rax, rax
0x180216107  jz      short loc_18021617B
0x180216109  mov     rax, [rsi]
0x18021610c  mov     edx, edi
0x18021610e  mov     rcx, rsi
0x180216111  mov     rax, [rax+10h]
0x180216115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021611a  mov     rdx, rax
0x18021611d  mov     rcx, [rax]
0x180216120  mov     rax, [rcx+10h]
0x180216124  mov     rcx, rdx
0x180216127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021612c  test    al, al
0x18021612e  jz      short loc_18021617B
0x180216130  mov     rax, [rsi]
0x180216133  mov     edx, edi
0x180216135  mov     rcx, rsi
0x180216138  mov     rax, [rax+10h]
0x18021613c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180216141  cmp     dword ptr [rax+24h], 2
0x180216145  jb      short loc_18021614D
0x180216147  mov     rdx, [rax+18h]
0x18021614b  jmp     short loc_180216150
0x18021614d  mov     rdx, r12; lpWideCharStr
0x180216150  xor     r9d, r9d
0x180216153  or      r8d, 0FFFFFFFFh; cchWideChar
0x180216157  lea     rcx, [rbp+1060h+Str]; this
0x18021615b  call    ?CopyStrStatus@?$DbsDynamicString@D@@QEAAJPEBGKPEAPEAD@Z; DbsDynamicString<char>::CopyStrStatus(ushort const *,ulong,char * *)
0x180216160  mov     ebx, eax
0x180216162  test    eax, eax
0x180216164  jnz     short loc_180216187
0x180216166  mov     rcx, r12
0x180216169  cmp     [rbp+1060h+var_10D4], 1
0x18021616d  cmovnb  rcx, [rbp+1060h+Str]; Str
0x180216172  call    ?DumpCabAdd@@YAHPEBD@Z; DumpCabAdd(char const *)
0x180216177  test    eax, eax
0x180216179  jz      short loc_180216182
0x18021617b  inc     edi
0x18021617d  jmp     loc_1802160EA
0x180216182  mov     ebx, 8000FFFFh
0x180216187  call    ?CloseDumpCab@@YAXXZ; CloseDumpCab(void)
0x18021618c  mov     rdx, r14
0x18021618f  lea     rcx, aUnableToCreate_6; "Unable to create %hs\n"
0x180216196  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x18021619b  mov     rcx, r14; lpFileName
0x18021619e  call    cs:__imp_DeleteFileA
0x1802161a5  nop     dword ptr [rax+rax+00h]
0x1802161aa  nop
0x1802161ab  lea     rcx, [rbp+1060h+var_FC0]
0x1802161b2  call    ??1?$DbsDynamicArray@UCODE_CHUNK@@@@QEAA@XZ; DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(void)
0x1802161b7  nop
0x1802161b8  lea     rcx, [rbp+1060h+Str]
0x1802161bc  call    ??1?$DbsDynamicArray@UCODE_CHUNK@@@@QEAA@XZ; DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(void)
0x1802161c1  mov     eax, ebx
0x1802161c3  mov     rcx, [rbp+1060h+var_30]
0x1802161ca  xor     rcx, rsp; StackCookie
0x1802161cd  call    __security_check_cookie
0x1802161d2  lea     r11, [rsp+1160h+var_20]
0x1802161da  mov     rbx, [r11+40h]
0x1802161de  mov     rsi, [r11+48h]
0x1802161e2  mov     rsp, r11
0x1802161e5  pop     r15
0x1802161e7  pop     r14
0x1802161e9  pop     r12
0x1802161eb  pop     rdi
0x1802161ec  pop     rbp
0x1802161ed  retn
0x1802161ef  mov     rcx, rdi; Str
0x1802161f2  call    ?DumpCabAdd@@YAHPEBD@Z; DumpCabAdd(char const *)
0x1802161f7  test    eax, eax
0x1802161f9  jnz     short loc_180216200
0x1802161fb  jmp     short loc_180216182
0x1802161fd  or      esi, 0FFFFFFFFh
0x180216200  bt      r15d, 1Eh
0x180216205  jnb     loc_180216496
0x18021620b  mov     rax, cs:?g_Process@@3PEAVProcessInfo@@EA; ProcessInfo * g_Process
0x180216212  mov     rcx, [rax+210h]; hModule
0x180216219  test    rcx, rcx
0x18021621c  jz      short loc_180216247
0x18021621e  mov     r8d, 104h; nSize
0x180216224  lea     rdx, [rbp+1060h+Filename]; lpFilename
0x18021622b  call    cs:__imp_GetModuleFileNameA
0x180216232  nop     dword ptr [rax+rax+00h]
0x180216237  test    eax, eax
0x180216239  jz      short loc_180216247
0x18021623b  lea     rcx, [rbp+1060h+Filename]; Str
0x180216242  call    ?DumpCabAdd@@YAHPEBD@Z; DumpCabAdd(char const *)
0x180216247  mov     rax, cs:?g_Process@@3PEAVProcessInfo@@EA; ProcessInfo * g_Process
0x18021624e  mov     rdi, [rax+80h]
0x180216255  jmp     loc_18021648D
0x18021625a  cmp     dword ptr [rdi+3D4h], 4
0x180216261  jnb     loc_180216350
0x180216267  bt      r15d, 1Ch
0x18021626c  jnb     loc_18021637D
0x180216272  mov     [rsp+1160h+var_10FC], r12d
0x180216277  mov     [rsp+1160h+lpBaseAddress], r12
0x18021627c  mov     [rsp+1160h+var_1100], r12d
0x180216281  mov     [rsp+1160h+hObject], r12
0x180216286  lea     rcx, [rdi+30h]; this
0x18021628a  mov     [rsp+1160h+var_1140], 2DFFh; unsigned int
0x180216292  mov     r9, [rdi+18h]; void *
0x180216296  mov     r8, [rdi+20h]; unsigned __int64
0x18021629a  mov     rdx, [rdi]; struct ProcessInfo *
0x18021629d  call    ?Update@IMAGE_HEADER_INFO@@QEAAKPEAVProcessInfo@@_KPEAXK@Z; IMAGE_HEADER_INFO::Update(ProcessInfo *,unsigned __int64,void *,ulong)
0x1802162a2  test    eax, eax
0x1802162a4  jz      loc_18021637D
0x1802162aa  mov     eax, [rdi+40h]
0x1802162ad  cmp     dword ptr [rdi+224h], 2
0x1802162b4  jb      short loc_1802162BF
0x1802162b6  mov     rdx, [rdi+218h]
0x1802162bd  jmp     short loc_1802162C2
0x1802162bf  mov     rdx, r12
0x1802162c2  lea     rcx, [rbp+1060h+var_FC0]
0x1802162c9  mov     [rsp+1160h+var_1110], rcx
0x1802162ce  lea     rcx, [rsp+1160h+hObject]
0x1802162d3  mov     [rsp+1160h+var_1118], rcx
0x1802162d8  lea     rcx, [rsp+1160h+var_1100]
0x1802162dd  mov     [rsp+1160h+var_1120], rcx
0x1802162e2  lea     rcx, [rsp+1160h+lpBaseAddress]
0x1802162e7  mov     [rsp+1160h+var_1128], rcx
0x1802162ec  lea     rcx, [rsp+1160h+var_10FC]
0x1802162f1  mov     [rsp+1160h+var_1130], rcx
0x1802162f6  mov     [rsp+1160h+var_1138], 1
0x1802162fe  mov     [rsp+1160h+var_1140], eax
0x180216302  mov     r9d, [rdi+3Ch]
0x180216306  mov     r8d, [rdi+28h]
0x18021630a  mov     rcx, cs:?g_Process@@3PEAVProcessInfo@@EA; ProcessInfo * g_Process
0x180216311  call    ?FindImageFile@@YAJPEAVProcessInfo@@PEBGKKKKPEAW4FOUND_IMAGE@@PEAPEAXPEAK3PEAV?$DbsDynamicString@G@@@Z; FindImageFile(ProcessInfo *,ushort const *,ulong,ulong,ulong,ulong,FOUND_IMAGE *,void * *,ulong *,void * *,DbsDynamicString<ushort> *)
0x180216316  test    eax, eax
0x180216318  jnz     short loc_18021637D
0x18021631a  mov     rcx, [rsp+1160h+lpBaseAddress]; lpBaseAddress
0x18021631f  call    cs:__imp_UnmapViewOfFile
0x180216326  nop     dword ptr [rax+rax+00h]
0x18021632b  mov     rcx, [rsp+1160h+hObject]; hObject
0x180216330  call    cs:__imp_CloseHandle
0x180216337  nop     dword ptr [rax+rax+00h]
0x18021633c  mov     rdx, r12
0x18021633f  cmp     [rbp+1060h+var_FB4], 2
0x180216346  cmovnb  rdx, [rbp+1060h+var_FC0]
0x18021634e  jmp     short loc_180216357
0x180216350  mov     rdx, [rdi+3C8h]; lpWideCharStr
0x180216357  xor     r9d, r9d
0x18021635a  mov     r8d, esi; cchWideChar
0x18021635d  lea     rcx, [rbp+1060h+Str]; this
0x180216361  call    ?CopyStrStatus@?$DbsDynamicString@D@@QEAAJPEBGKPEAPEAD@Z; DbsDynamicString<char>::CopyStrStatus(ushort const *,ulong,char * *)
0x180216366  test    eax, eax
0x180216368  mov     ebx, eax
0x18021636a  jnz     short loc_18021637D
0x18021636c  mov     rcx, r12
0x18021636f  cmp     [rbp+1060h+var_10D4], 1
0x180216373  cmovnb  rcx, [rbp+1060h+Str]; Str
0x180216378  call    ?DumpCabAdd@@YAHPEBD@Z; DumpCabAdd(char const *)
0x18021637d  xor     eax, eax
0x18021637f  mov     dword ptr [rbp+1060h+ModuleInfo+4], eax
0x180216385  xor     edx, edx; Val
0x180216387  mov     r8d, 0CC0h; Size
0x18021638d  lea     rcx, [rbp+1060h+ModuleInfo.BaseOfImage]; void *
0x180216394  call    memset
0x180216399  mov     [rbp+1060h+ModuleInfo.SizeOfStruct], 0CC8h
0x1802163a3  mov     [rbp+1060h+var_150], 1
0x1802163ad  lea     r8, [rbp+1060h+ModuleInfo]; ModuleInfo
0x1802163b4  mov     rdx, [rdi+20h]; qwAddr
0x1802163b8  mov     rcx, cs:?g_Process@@3PEAVProcessInfo@@EA; ProcessInfo * g_Process
0x1802163bf  mov     rcx, [rcx+198h]; hProcess
0x1802163c6  call    cs:__imp_SymGetModuleInfoW64
0x1802163cd  nop     dword ptr [rax+rax+00h]
0x1802163d2  test    eax, eax
0x1802163d4  jz      loc_180216489
0x1802163da  cmp     [rbp+1060h+ModuleInfo.LoadedImageName], r12w
0x1802163e2  jz      short loc_180216452
0x1802163e4  lea     rcx, [rbp+1060h+ModuleInfo.LoadedImageName]
0x1802163eb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1802163ef  inc     rax
0x1802163f2  cmp     [rcx+rax*2], r12w
0x1802163f7  jnz     short loc_1802163EF
0x1802163f9  cmp     eax, 4
0x1802163fc  jbe     short loc_180216452
0x1802163fe  add     eax, 0FFFFFFFCh
0x180216401  mov     ecx, eax
0x180216403  lea     rax, [rbp+1060h+ModuleInfo.LoadedImageName]
0x18021640a  lea     rcx, [rax+rcx*2]; String1
0x18021640e  lea     rdx, aDbg_1; ".dbg"
0x180216415  call    cs:__imp__wcsicmp
0x18021641c  nop     dword ptr [rax+rax+00h]
0x180216421  test    eax, eax
0x180216423  jnz     short loc_180216452
0x180216425  xor     r9d, r9d
0x180216428  mov     r8d, esi; cchWideChar
0x18021642b  lea     rdx, [rbp+1060h+ModuleInfo.LoadedImageName]; lpWideCharStr
0x180216432  lea     rcx, [rbp+1060h+Str]; this
0x180216436  call    ?CopyStrStatus@?$DbsDynamicString@D@@QEAAJPEBGKPEAPEAD@Z; DbsDynamicString<char>::CopyStrStatus(ushort const *,ulong,char * *)
0x18021643b  mov     ebx, eax
0x18021643d  test    eax, eax
0x18021643f  jnz     short loc_180216452
0x180216441  mov     rcx, r12
0x180216444  cmp     [rbp+1060h+var_10D4], 1
0x180216448  cmovnb  rcx, [rbp+1060h+Str]; Str
0x18021644d  call    ?DumpCabAdd@@YAHPEBD@Z; DumpCabAdd(char const *)
0x180216452  cmp     [rbp+1060h+ModuleInfo.LoadedPdbName], r12w
0x18021645a  jz      short loc_180216489
0x18021645c  xor     r9d, r9d
0x18021645f  mov     r8d, esi; cchWideChar
0x180216462  lea     rdx, [rbp+1060h+ModuleInfo.LoadedPdbName]; lpWideCharStr
0x180216469  lea     rcx, [rbp+1060h+Str]; this
0x18021646d  call    ?CopyStrStatus@?$DbsDynamicString@D@@QEAAJPEBGKPEAPEAD@Z; DbsDynamicString<char>::CopyStrStatus(ushort const *,ulong,char * *)
0x180216472  mov     ebx, eax
0x180216474  test    eax, eax
0x180216476  jnz     short loc_180216489
0x180216478  mov     rcx, r12
0x18021647b  cmp     [rbp+1060h+var_10D4], 1
0x18021647f  cmovnb  rcx, [rbp+1060h+Str]; Str
0x180216484  call    ?DumpCabAdd@@YAHPEBD@Z; DumpCabAdd(char const *)
0x180216489  mov     rdi, [rdi+8]
0x18021648d  test    rdi, rdi
0x180216490  jnz     loc_18021625A
0x180216496  call    ?CloseDumpCab@@YAXXZ; CloseDumpCab(void)
0x18021649b  test    ebx, ebx
0x18021649d  jnz     loc_18021618C
0x1802164a3  mov     rdx, r14
0x1802164a6  lea     rcx, aWroteHs; "Wrote %hs\n"
0x1802164ad  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1802164b2  jmp     loc_1802161AB
```
