# ConflictStore_XsdSchemaTextFromHtmlResource(uint,char * *)

- ea: `0x180044044`
- end: `0x180044292`
- name: `?ConflictStore_XsdSchemaTextFromHtmlResource@@YAJIPEAPEAD@Z`
- size: `590`
- prototype: `__int64 __fastcall(unsigned int, char **)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1800349d0`

## callees

- `0x18000d640`
- `0x18001be00`
- `0x180029dd0`
- `0x18002f078`
- `0x18002f10c`
- `0x180036394`
- `0x18003c4e8`
- `0x18003e928`
- `0x180044044`
- `0x180087608`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18004408f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18004408f`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x1800440ef`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x1800440ef`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180044144`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180044144`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18004419b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18004419b`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x1800441d0`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x1800441d0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180044241`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180044241`

## string_xrefs

- `0x18004406d`: `%systemroot%\system32\cscsvc.dll`

## pseudocode

```c
__int64 __fastcall ConflictStore_XsdSchemaTextFromHtmlResource(__int64 a1, char **a2)
{
  int v3; // ebx
  HMODULE LibraryW; // rax
  HMODULE v5; // rdi
  int Error; // eax
  void *v7; // rdx
  HRSRC ResourceW; // rax
  HRSRC v9; // r14
  int v10; // eax
  DWORD v11; // eax
  void *v12; // rsi
  size_t v13; // r13
  void *v14; // r9
  int v15; // eax
  HGLOBAL Resource; // rax
  void *v17; // rdx
  CObjectMonitor *v18; // rcx
  __int64 v19; // rdx
  const void *v20; // rax
  LPCWSTR lpLibFileName; // [rsp+68h] [rbp+10h] BYREF
  SIZE_T dwBytes; // [rsp+70h] [rbp+18h] BYREF
  void *v24; // [rsp+78h] [rbp+20h] BYREF

  *a2 = 0;
  lpLibFileName = 0;
  v3 = CscUtil_ExpandEnvironmentStringsAlloc(L"%systemroot%\\system32\\cscsvc.dll", (unsigned __int16 **)&lpLibFileName);
  if ( v3 >= 0 )
  {
    LibraryW = LoadLibraryW(lpLibFileName);
    v5 = LibraryW;
    if ( !LibraryW )
    {
      Error = ResultFromLastError();
      v3 = Error;
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          46,
          (unsigned int)WPP_02028e3dddf63d5a7432d80ff826e539_Traceguids,
          (_DWORD)lpLibFileName,
          Error);
      goto LABEL_25;
    }
    ResourceW = FindResourceW(LibraryW, (LPCWSTR)0x65, (LPCWSTR)0x17);
    v9 = ResourceW;
    if ( !ResourceW )
    {
      v10 = ResultFromLastError();
      v3 = v10;
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_02028e3dddf63d5a7432d80ff826e539_Traceguids, 101, v10);
      goto LABEL_24;
    }
    v11 = SizeofResource(v5, ResourceW);
    v12 = 0;
    v13 = v11;
    v24 = 0;
    dwBytes = 0;
    v3 = ULongLongMult(v11 + 1, 1u, &dwBytes);
    if ( v3 >= 0 )
    {
      v15 = CscUtil_HeapAlloc(dwBytes, (int)v14, &v24, v14);
      v12 = v24;
      v3 = v15;
    }
    if ( v3 < 0 )
      goto LABEL_24;
    Resource = LoadResource(v5, v9);
    if ( Resource )
    {
      v20 = LockResource(Resource);
      if ( v20 )
      {
        memcpy_0(v12, v20, v13);
        *a2 = (char *)v12;
        v12 = 0;
        goto LABEL_23;
      }
      v3 = ResultFromLastError();
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_23;
      v19 = 49;
    }
    else
    {
      v3 = ResultFromLastError();
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_23;
      v19 = 48;
    }
    WPP_SF_dd(*((_QWORD *)v18 + 2), v19, WPP_02028e3dddf63d5a7432d80ff826e539_Traceguids, 101, v3);
LABEL_23:
    CscUtil_HeapFree(v12, v17);
LABEL_24:
    FreeLibrary(v5);
LABEL_25:
    CscUtil_HeapFree((void *)lpLibFileName, v7);
  }
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_02028e3dddf63d5a7432d80ff826e539_Traceguids, (unsigned int)v3);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180044044  mov     [rsp+arg_0], rbx
0x180044049  push    rsi
0x18004404a  push    rdi
0x18004404b  push    r13
0x18004404d  push    r14
0x18004404f  push    r15
0x180044051  sub     rsp, 30h
0x180044055  mov     r15, rdx
0x180044058  mov     qword ptr [rdx], 0
0x18004405f  lea     rdx, [rsp+58h+lpLibFileName]; unsigned __int16 **
0x180044064  mov     [rsp+58h+lpLibFileName], 0
0x18004406d  lea     rcx, aSystemrootSyst; "%systemroot%\\system32\\cscsvc.dll"
0x180044074  call    ?CscUtil_ExpandEnvironmentStringsAlloc@@YAJPEBGPEAPEAG@Z; CscUtil_ExpandEnvironmentStringsAlloc(ushort const *,ushort * *)
0x180044079  lea     rsi, WPP_GLOBAL_Control
0x180044080  mov     ebx, eax
0x180044082  test    eax, eax
0x180044084  js      loc_180044251
0x18004408a  mov     rcx, [rsp+58h+lpLibFileName]; lpLibFileName
0x18004408f  call    cs:__imp_LoadLibraryW
0x180044095  mov     rdi, rax
0x180044098  test    rax, rax
0x18004409b  jnz     short loc_1800440DF
0x18004409d  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800440a2  mov     ebx, eax
0x1800440a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800440ab  cmp     rcx, rsi
0x1800440ae  jz      loc_180044247
0x1800440b4  test    byte ptr [rcx+1Ch], 2
0x1800440b8  jz      loc_180044247
0x1800440be  mov     r9, [rsp+58h+lpLibFileName]
0x1800440c3  lea     edx, [rdi+2Eh]
0x1800440c6  mov     rcx, [rcx+10h]
0x1800440ca  lea     r8, WPP_02028e3dddf63d5a7432d80ff826e539_Traceguids
0x1800440d1  mov     [rsp+58h+var_38], eax
0x1800440d5  call    WPP_SF_Sd
0x1800440da  jmp     loc_180044247
0x1800440df  mov     r8d, 17h; lpType
0x1800440e5  mov     rcx, rdi; hModule
0x1800440e8  lea     r13d, [r8+4Eh]
0x1800440ec  mov     edx, r13d; lpName
0x1800440ef  call    cs:__imp_FindResourceW
0x1800440f5  mov     r14, rax
0x1800440f8  test    rax, rax
0x1800440fb  jnz     short loc_18004413E
0x1800440fd  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180044102  mov     ebx, eax
0x180044104  mov     rcx, cs:WPP_GLOBAL_Control
0x18004410b  cmp     rcx, rsi
0x18004410e  jz      loc_18004423E
0x180044114  test    byte ptr [rcx+1Ch], 2
0x180044118  jz      loc_18004423E
0x18004411e  mov     rcx, [rcx+10h]
0x180044122  lea     edx, [r13-36h]
0x180044126  mov     r9d, r13d
0x180044129  mov     [rsp+58h+var_38], eax
0x18004412d  lea     r8, WPP_02028e3dddf63d5a7432d80ff826e539_Traceguids
0x180044134  call    WPP_SF_dd
0x180044139  jmp     loc_18004423E
0x18004413e  mov     rdx, r14; hResInfo
0x180044141  mov     rcx, rdi; hModule
0x180044144  call    cs:__imp_SizeofResource
0x18004414a  xor     esi, esi
0x18004414c  mov     r13d, eax
0x18004414f  lea     r8, [rsp+58h+dwBytes]; unsigned __int64 *
0x180044154  mov     [rsp+58h+arg_18], rsi
0x180044159  mov     [rsp+58h+dwBytes], rsi
0x18004415e  lea     r9d, [rsi+1]
0x180044162  lea     ecx, [r13+1]; unsigned __int64
0x180044166  mov     edx, r9d; unsigned __int64
0x180044169  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18004416e  mov     ebx, eax
0x180044170  test    eax, eax
0x180044172  js      short loc_18004418D
0x180044174  mov     rcx, [rsp+58h+dwBytes]; dwBytes
0x180044179  lea     r8, [rsp+58h+arg_18]; void **
0x18004417e  mov     edx, r9d; int
0x180044181  call    ?CscUtil_HeapAlloc@@YAJ_KHPEAPEAXPEAX@Z; CscUtil_HeapAlloc(unsigned __int64,int,void * *,void *)
0x180044186  mov     rsi, [rsp+58h+arg_18]
0x18004418b  mov     ebx, eax
0x18004418d  test    ebx, ebx
0x18004418f  js      loc_180044237
0x180044195  mov     rdx, r14; hResInfo
0x180044198  mov     rcx, rdi; hModule
0x18004419b  call    cs:__imp_LoadResource
0x1800441a1  test    rax, rax
0x1800441a4  jnz     short loc_1800441CD
0x1800441a6  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800441ab  mov     ebx, eax
0x1800441ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800441b4  lea     rax, WPP_GLOBAL_Control
0x1800441bb  cmp     rcx, rax
0x1800441be  jz      short loc_18004422F
0x1800441c0  test    byte ptr [rcx+1Ch], 2
0x1800441c4  jz      short loc_18004422F
0x1800441c6  mov     edx, 30h ; '0'
0x1800441cb  jmp     short loc_180044200
0x1800441cd  mov     rcx, rax; hResData
0x1800441d0  call    cs:__imp_LockResource
0x1800441d6  test    rax, rax
0x1800441d9  jnz     short loc_18004421C
0x1800441db  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800441e0  mov     ebx, eax
0x1800441e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800441e9  lea     rax, WPP_GLOBAL_Control
0x1800441f0  cmp     rcx, rax
0x1800441f3  jz      short loc_18004422F
0x1800441f5  test    byte ptr [rcx+1Ch], 2
0x1800441f9  jz      short loc_18004422F
0x1800441fb  mov     edx, 31h ; '1'
0x180044200  mov     rcx, [rcx+10h]
0x180044204  lea     r8, WPP_02028e3dddf63d5a7432d80ff826e539_Traceguids
0x18004420b  mov     r9d, 65h ; 'e'
0x180044211  mov     [rsp+58h+var_38], ebx
0x180044215  call    WPP_SF_dd
0x18004421a  jmp     short loc_18004422F
0x18004421c  mov     r8, r13; Size
0x18004421f  mov     rdx, rax; Src
0x180044222  mov     rcx, rsi; void *
0x180044225  call    memcpy_0
0x18004422a  mov     [r15], rsi
0x18004422d  xor     esi, esi
0x18004422f  mov     rcx, rsi; lpMem
0x180044232  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x180044237  lea     rsi, WPP_GLOBAL_Control
0x18004423e  mov     rcx, rdi; hLibModule
0x180044241  call    cs:__imp_FreeLibrary
0x180044247  mov     rcx, [rsp+58h+lpLibFileName]; lpMem
0x18004424c  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x180044251  mov     rcx, cs:WPP_GLOBAL_Control
0x180044258  cmp     rcx, rsi
0x18004425b  jz      short loc_18004427E
0x18004425d  test    dword ptr [rcx+1Ch], 800000h
0x180044264  jz      short loc_18004427E
0x180044266  mov     rcx, [rcx+10h]
0x18004426a  lea     r8, WPP_02028e3dddf63d5a7432d80ff826e539_Traceguids
0x180044271  mov     edx, 32h ; '2'
0x180044276  mov     r9d, ebx
0x180044279  call    WPP_SF_d
0x18004427e  mov     eax, ebx
0x180044280  mov     rbx, [rsp+58h+arg_0]
0x180044285  add     rsp, 30h
0x180044289  pop     r15
0x18004428b  pop     r14
0x18004428d  pop     r13
0x18004428f  pop     rdi
0x180044290  pop     rsi
0x180044291  retn
```
