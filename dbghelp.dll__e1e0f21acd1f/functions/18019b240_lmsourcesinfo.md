# lmsourcesinfo

- ea: `0x18019b240`
- end: `0x18019b58c`
- name: `lmsourcesinfo`
- size: `844`
- prototype: `__int64 __fastcall(int, int, int, int, PCSTR Expression)`
- caller_count: `0`
- callee_count: `18`
- tags: `loader_planting`

## callees

- `0x18000aeec`
- `0x18000af48`
- `0x180014958`
- `0x18018b378`
- `0x180193914`
- `0x180193d84`
- `0x180196290`
- `0x180196300`
- `0x180196638`
- `0x18019667c`
- `0x18019a460`
- `0x18019a480`
- `0x18019b240`
- `0x18019f648`
- `0x1801acd3c`
- `0x1801bf2e4`
- `0x1801d6350`
- `0x180205010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__splitpath_s` at `0x18019b387`
- `api-ms-win-crt-private-l1-1-0!_o__splitpath_s` at `0x18019b387`
- `api-ms-win-crt-private-l1-1-0!_o__strlwr` at `0x18019b2b6`
- `api-ms-win-crt-private-l1-1-0!_o__strlwr` at `0x18019b2b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019b330`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019b561`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019b330`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019b561`

## string_xrefs

- `0x18019b4f4`: `Failed to read SourceLink (V1/legacy and V2) information.\n`
- `0x18019b543`: `Module uses SourceLink V1 (legacy) information or explicit SourceLink V2 information.\n`

## pseudocode

```c
void __fastcall lmsourcesinfo(__int64 a1, __int64 a2, __int64 a3, __int64 a4, PCSTR Expression)
{
  const CHAR *v5; // rcx
  struct _PROCESS_ENTRY *ProcessEntry; // rdi
  DWORD v7; // ecx
  void *v8; // rcx
  int v9; // r9d
  struct _MODULE_ENTRY *Image; // rbx
  __int64 v11; // rdi
  unsigned int v12; // r9d
  __int64 v13; // rcx
  const CHAR *v14; // rcx
  unsigned int v15; // [rsp+50h] [rbp-B0h] BYREF
  ULONG64 Value; // [rsp+58h] [rbp-A8h] BYREF
  void *hp; // [rsp+60h] [rbp-A0h] BYREF
  void **v18; // [rsp+68h] [rbp-98h] BYREF
  char v19; // [rsp+70h] [rbp-90h]
  __int64 v20; // [rsp+78h] [rbp-88h] BYREF
  int v21; // [rsp+80h] [rbp-80h]
  __int64 v22; // [rsp+88h] [rbp-78h]
  CHAR MultiByteStr[272]; // [rsp+90h] [rbp-70h] BYREF
  char v24[272]; // [rsp+1A0h] [rbp+A0h] BYREF
  char Ext[272]; // [rsp+2B0h] [rbp+1B0h] BYREF
  char String[1024]; // [rsp+3C0h] [rbp+2C0h] BYREF

  Value = 0;
  hp = 0;
  if ( !*Expression )
  {
    v5 = "You must specify a module\n";
LABEL_3:
    ExtensionApis.lpOutputRoutine(v5);
    return;
  }
  strcpy_s_ex(String, 0x400u, Expression);
  _strlwr(String);
  TruncateArgs(String);
  ExtensionApis.lpOutputRoutine("Loaded Module Sources Information: [%s] ", String);
  GetCurrentProcessHandle(&hp);
  if ( !hp )
  {
    v5 = "couldn't get process handle\n";
    goto LABEL_3;
  }
  ProcessEntry = FindProcessEntry(hp);
  if ( !ProcessEntry )
  {
    ExtensionApis.lpOutputRoutine("Couldn't find process 0x%x while looking for %s\n", hp, String);
    v7 = 6;
LABEL_8:
    SetLastError(v7);
    return;
  }
  ExtensionApis.lpOutputRoutine("\n");
  MultiByteStr[0] = 0;
  _splitpath_s(String, 0, 0, 0, 0, MultiByteStr, 0x105u, Ext, 0x105u);
  strcpy_s_ex(v24, 0x105u, MultiByteStr);
  strcat_s_ex(v24, 0x105u, Ext);
  Image = aFindImage(v8, ProcessEntry, v24, v9);
  if ( !Image )
  {
    Image = aFindModule(hp, ProcessEntry, MultiByteStr, 1, 0);
    if ( !Image )
    {
      if ( !GetExpressionEx(Expression, &Value, 0) )
      {
        ExtensionApis.lpOutputRoutine("%s not found\n", String);
        v7 = 126;
        goto LABEL_8;
      }
      Image = GetModuleForPC(ProcessEntry, Value, 0, 1, 1, 1);
      if ( !Image )
      {
        ExtensionApis.lpOutputRoutine("%I64lx is not a valid address\n", Value);
        return;
      }
    }
  }
  srcsrvLoadModule(ProcessEntry, Image, 0, 0);
  v19 = 1;
  v11 = 0;
  v18 = &ModuleSourceInfoLogger::`vftable';
  v21 = 0;
  v20 = 0;
  v22 = 0;
  Value = 0;
  v15 = 0;
  if ( !(unsigned int)diaReadSourceV2ServerData(
                        Image,
                        (struct SrcSrvStreamCollectionContainer *)&v20,
                        (struct IModuleSourceInfoLogger *)&v18)
    || (v11 = v22) == 0 )
  {
    diaReadSourceServerData(Image, (struct IModuleSourceInfoLogger *)&v18, (unsigned __int8 **)&Value, &v15);
    v12 = v15;
    if ( v15 )
      goto LABEL_20;
    ExtensionApis.lpOutputRoutine("Failed to read SourceLink (V1/legacy and V2) information.\n");
  }
  v12 = v15;
LABEL_20:
  v13 = *((int *)Image + 4956);
  if ( (int)v13 <= 1 )
  {
    v14 = "Error: Missing souces information.\n";
    goto LABEL_27;
  }
  if ( v13 != v11 )
  {
    if ( (_DWORD)v13 == v12 )
    {
      ModuleSourceInfoLogger::LogStream((ModuleSourceInfoLogger *)&v18, Image, (const unsigned __int8 *)Value, v12);
      goto LABEL_28;
    }
    v14 = "Module uses SourceLink V1 (legacy) information or explicit SourceLink V2 information.\n";
LABEL_27:
    ExtensionApis.lpOutputRoutine(v14);
    goto LABEL_28;
  }
  ModuleSourceInfoLogger::LogStreamCollection(
    (ModuleSourceInfoLogger *)&v18,
    Image,
    (const struct SrcSrvStreamCollectionT *)&v20);
LABEL_28:
  SetLastError(0);
  SrcSrvStreamCollectionContainer::Clear((SrcSrvStreamCollectionContainer *)&v20);
}

```

## disassembly

```asm
0x18019b240  push    rbp
0x18019b242  push    rbx
0x18019b243  push    rsi
0x18019b244  push    rdi
0x18019b245  lea     rbp, [rsp-6D8h]
0x18019b24d  sub     rsp, 7D8h
0x18019b254  mov     rax, cs:__security_cookie
0x18019b25b  xor     rax, rsp
0x18019b25e  mov     [rbp+6F0h+var_30], rax
0x18019b265  mov     rsi, [rbp+6F0h+Expression]
0x18019b26c  mov     [rsp+7F0h+Value], 0
0x18019b275  mov     [rsp+7F0h+hp], 0
0x18019b27e  cmp     byte ptr [rsi], 0
0x18019b281  jnz     short loc_18019B29B
0x18019b283  lea     rcx, aYouMustSpecify; "You must specify a module\n"
0x18019b28a  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x18019b291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b296  jmp     loc_18019B571
0x18019b29b  mov     r8, rsi; char *
0x18019b29e  lea     rcx, [rbp+6F0h+String]; char *
0x18019b2a5  mov     edx, 400h; unsigned __int64
0x18019b2aa  call    ?strcpy_s_ex@@YAHPEAD_KPEBD@Z; strcpy_s_ex(char *,unsigned __int64,char const *)
0x18019b2af  lea     rcx, [rbp+6F0h+String]; String
0x18019b2b6  call    cs:__imp__strlwr
0x18019b2bc  lea     rcx, [rbp+6F0h+String]; char *
0x18019b2c3  call    ?TruncateArgs@@YAXPEAD@Z; TruncateArgs(char *)
0x18019b2c8  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x18019b2cf  lea     rdx, [rbp+6F0h+String]
0x18019b2d6  lea     rcx, aLoadedModuleSo; "Loaded Module Sources Information: [%s]"...
0x18019b2dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b2e2  lea     rcx, [rsp+7F0h+hp]; hp
0x18019b2e7  call    GetCurrentProcessHandle
0x18019b2ec  mov     rcx, [rsp+7F0h+hp]; void *
0x18019b2f1  test    rcx, rcx
0x18019b2f4  jnz     short loc_18019B2FF
0x18019b2f6  lea     rcx, aCouldnTGetProc_0; "couldn't get process handle\n"
0x18019b2fd  jmp     short loc_18019B28A
0x18019b2ff  call    ?FindProcessEntry@@YAPEAU_PROCESS_ENTRY@@PEAX@Z; FindProcessEntry(void *)
0x18019b304  mov     rdi, rax
0x18019b307  test    rax, rax
0x18019b30a  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x18019b311  jnz     short loc_18019B33B
0x18019b313  mov     rdx, [rsp+7F0h+hp]
0x18019b318  lea     r8, [rbp+6F0h+String]
0x18019b31f  lea     rcx, aCouldnTFindPro_1; "Couldn't find process 0x%x while lookin"...
0x18019b326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b32b  mov     ecx, 6; dwErrCode
0x18019b330  call    cs:__imp_SetLastError
0x18019b336  jmp     loc_18019B571
0x18019b33b  lea     rcx, asc_18022B9A8; "\n"
0x18019b342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b347  mov     ebx, 105h
0x18019b34c  mov     [rbp+6F0h+MultiByteStr], 0
0x18019b350  mov     [rsp+7F0h+ExtCount], rbx; ExtCount
0x18019b355  lea     rax, [rbp+6F0h+var_540]
0x18019b35c  mov     [rsp+7F0h+Ext], rax; Ext
0x18019b361  lea     rcx, [rbp+6F0h+String]; FullPath
0x18019b368  lea     rax, [rbp+6F0h+MultiByteStr]
0x18019b36c  mov     [rsp+7F0h+FilenameCount], rbx; FilenameCount
0x18019b371  mov     [rsp+7F0h+Filename], rax; Filename
0x18019b376  xor     r9d, r9d; Dir
0x18019b379  xor     r8d, r8d; DriveCount
0x18019b37c  mov     [rsp+7F0h+DirCount], 0; DirCount
0x18019b385  xor     edx, edx; Drive
0x18019b387  call    cs:__imp__splitpath_s
0x18019b38d  lea     r8, [rbp+6F0h+MultiByteStr]; char *
0x18019b391  mov     edx, ebx; unsigned __int64
0x18019b393  lea     rcx, [rbp+6F0h+var_650]; char *
0x18019b39a  call    ?strcpy_s_ex@@YAHPEAD_KPEBD@Z; strcpy_s_ex(char *,unsigned __int64,char const *)
0x18019b39f  lea     r8, [rbp+6F0h+var_540]; char *
0x18019b3a6  mov     edx, ebx; unsigned __int64
0x18019b3a8  lea     rcx, [rbp+6F0h+var_650]; char *
0x18019b3af  call    ?strcat_s_ex@@YAHPEAD_KPEBD@Z; strcat_s_ex(char *,unsigned __int64,char const *)
0x18019b3b4  lea     r8, [rbp+6F0h+var_650]; char *
0x18019b3bb  mov     rdx, rdi; struct _PROCESS_ENTRY *
0x18019b3be  call    ?aFindImage@@YAPEAU_MODULE_ENTRY@@PEAXPEAU_PROCESS_ENTRY@@PEBDH@Z; aFindImage(void *,_PROCESS_ENTRY *,char const *,int)
0x18019b3c3  mov     rbx, rax
0x18019b3c6  test    rax, rax
0x18019b3c9  jnz     loc_18019B468
0x18019b3cf  mov     rcx, [rsp+7F0h+hp]; void *
0x18019b3d4  lea     r9d, [rax+1]; int
0x18019b3d8  lea     r8, [rbp+6F0h+MultiByteStr]; lpMultiByteStr
0x18019b3dc  mov     dword ptr [rsp+7F0h+DirCount], eax; int
0x18019b3e0  mov     rdx, rdi; struct _PROCESS_ENTRY *
0x18019b3e3  call    ?aFindModule@@YAPEAU_MODULE_ENTRY@@PEAXPEAU_PROCESS_ENTRY@@PEBDHH@Z; aFindModule(void *,_PROCESS_ENTRY *,char const *,int,int)
0x18019b3e8  mov     rbx, rax
0x18019b3eb  test    rax, rax
0x18019b3ee  jnz     short loc_18019B468
0x18019b3f0  xor     r8d, r8d; Remainder
0x18019b3f3  lea     rdx, [rsp+7F0h+Value]; Value
0x18019b3f8  mov     rcx, rsi; Expression
0x18019b3fb  call    GetExpressionEx
0x18019b400  test    eax, eax
0x18019b402  jnz     short loc_18019B426
0x18019b404  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x18019b40b  lea     rdx, [rbp+6F0h+String]
0x18019b412  lea     rcx, aSNotFound; "%s not found\n"
0x18019b419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b41e  lea     ecx, [rbx+7Eh]
0x18019b421  jmp     loc_18019B330
0x18019b426  mov     rdx, [rsp+7F0h+Value]; unsigned __int64
0x18019b42b  mov     r9b, 1; bool
0x18019b42e  mov     byte ptr [rsp+7F0h+Filename], 1; bool
0x18019b433  xor     r8d, r8d; bool
0x18019b436  mov     rcx, rdi; struct _PROCESS_ENTRY *
0x18019b439  mov     byte ptr [rsp+7F0h+DirCount], 1; bool
0x18019b43e  call    ?GetModuleForPC@@YAPEAU_MODULE_ENTRY@@PEAU_PROCESS_ENTRY@@_K_N222@Z; GetModuleForPC(_PROCESS_ENTRY *,unsigned __int64,bool,bool,bool,bool)
0x18019b443  mov     rbx, rax
0x18019b446  test    rax, rax
0x18019b449  jnz     short loc_18019B468
0x18019b44b  mov     rdx, [rsp+7F0h+Value]
0x18019b450  lea     rcx, aI64lxIsNotAVal; "%I64lx is not a valid address\n"
0x18019b457  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x18019b45e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b463  jmp     loc_18019B571
0x18019b468  xor     r9d, r9d; unsigned __int64
0x18019b46b  xor     r8d, r8d; unsigned __int8 *
0x18019b46e  mov     rdx, rbx; struct _MODULE_ENTRY *
0x18019b471  mov     rcx, rdi; struct _PROCESS_ENTRY *
0x18019b474  call    ?srcsrvLoadModule@@YAHPEAU_PROCESS_ENTRY@@PEAU_MODULE_ENTRY@@PEAE_K@Z; srcsrvLoadModule(_PROCESS_ENTRY *,_MODULE_ENTRY *,uchar *,unsigned __int64)
0x18019b479  lea     rax, ??_7ModuleSourceInfoLogger@@6B@; const ModuleSourceInfoLogger::`vftable'
0x18019b480  mov     [rsp+7F0h+var_780], 1
0x18019b485  xor     edi, edi
0x18019b487  mov     [rsp+7F0h+var_788], rax
0x18019b48c  lea     r8, [rsp+7F0h+var_788]; struct IModuleSourceInfoLogger *
0x18019b491  mov     [rbp+6F0h+var_770], 0
0x18019b498  lea     rdx, [rsp+7F0h+var_778]; struct SrcSrvStreamCollectionContainer *
0x18019b49d  mov     [rsp+7F0h+var_778], 0
0x18019b4a6  mov     rcx, rbx; struct _MODULE_ENTRY *
0x18019b4a9  mov     [rbp+6F0h+var_768], 0
0x18019b4b1  mov     [rsp+7F0h+Value], rdi
0x18019b4b6  mov     [rsp+7F0h+var_7A0], edi
0x18019b4ba  call    ?diaReadSourceV2ServerData@@YAHPEAU_MODULE_ENTRY@@PEAVSrcSrvStreamCollectionContainer@@PEAVIModuleSourceInfoLogger@@@Z; diaReadSourceV2ServerData(_MODULE_ENTRY *,SrcSrvStreamCollectionContainer *,IModuleSourceInfoLogger *)
0x18019b4bf  test    eax, eax
0x18019b4c1  jz      short loc_18019B4CC
0x18019b4c3  mov     rdi, [rbp+6F0h+var_768]
0x18019b4c7  test    rdi, rdi
0x18019b4ca  jnz     short loc_18019B500
0x18019b4cc  lea     r9, [rsp+7F0h+var_7A0]; unsigned int *
0x18019b4d1  mov     rcx, rbx; struct _MODULE_ENTRY *
0x18019b4d4  lea     r8, [rsp+7F0h+Value]; unsigned __int8 **
0x18019b4d9  lea     rdx, [rsp+7F0h+var_788]; struct IModuleSourceInfoLogger *
0x18019b4de  call    ?diaReadSourceServerData@@YAHPEAU_MODULE_ENTRY@@PEAVIModuleSourceInfoLogger@@PEAPEAEPEAK@Z; diaReadSourceServerData(_MODULE_ENTRY *,IModuleSourceInfoLogger *,uchar * *,ulong *)
0x18019b4e3  mov     r9d, [rsp+7F0h+var_7A0]
0x18019b4e8  test    r9d, r9d
0x18019b4eb  jnz     short loc_18019B505
0x18019b4ed  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x18019b4f4  lea     rcx, aFailedToReadSo; "Failed to read SourceLink (V1/legacy an"...
0x18019b4fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b500  mov     r9d, [rsp+7F0h+var_7A0]; unsigned int
0x18019b505  movsxd  rcx, dword ptr [rbx+4D70h]
0x18019b50c  cmp     ecx, 1
0x18019b50f  jle     short loc_18019B54C
0x18019b511  cmp     rcx, rdi
0x18019b514  jnz     short loc_18019B52A
0x18019b516  lea     r8, [rsp+7F0h+var_778]; struct SrcSrvStreamCollectionT *
0x18019b51b  mov     rdx, rbx; struct _MODULE_ENTRY *
0x18019b51e  lea     rcx, [rsp+7F0h+var_788]; this
0x18019b523  call    ?LogStreamCollection@ModuleSourceInfoLogger@@UEAAXPEAU_MODULE_ENTRY@@AEBUSrcSrvStreamCollectionT@@@Z; ModuleSourceInfoLogger::LogStreamCollection(_MODULE_ENTRY *,SrcSrvStreamCollectionT const &)
0x18019b528  jmp     short loc_18019B55F
0x18019b52a  cmp     ecx, r9d
0x18019b52d  jnz     short loc_18019B543
0x18019b52f  mov     r8, [rsp+7F0h+Value]; unsigned __int8 *
0x18019b534  lea     rcx, [rsp+7F0h+var_788]; this
0x18019b539  mov     rdx, rbx; struct _MODULE_ENTRY *
0x18019b53c  call    ?LogStream@ModuleSourceInfoLogger@@UEAAXPEAU_MODULE_ENTRY@@PEBEI@Z; ModuleSourceInfoLogger::LogStream(_MODULE_ENTRY *,uchar const *,uint)
0x18019b541  jmp     short loc_18019B55F
0x18019b543  lea     rcx, aModuleUsesSour; "Module uses SourceLink V1 (legacy) info"...
0x18019b54a  jmp     short loc_18019B553
0x18019b54c  lea     rcx, aErrorMissingSo; "Error: Missing souces information.\n"
0x18019b553  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x18019b55a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b55f  xor     ecx, ecx; dwErrCode
0x18019b561  call    cs:__imp_SetLastError
0x18019b567  lea     rcx, [rsp+7F0h+var_778]; this
0x18019b56c  call    ?Clear@SrcSrvStreamCollectionContainer@@QEAAXXZ; SrcSrvStreamCollectionContainer::Clear(void)
0x18019b571  mov     rcx, [rbp+6F0h+var_30]
0x18019b578  xor     rcx, rsp; StackCookie
0x18019b57b  call    __security_check_cookie
0x18019b580  add     rsp, 7D8h
0x18019b587  pop     rdi
0x18019b588  pop     rsi
0x18019b589  pop     rbx
0x18019b58a  pop     rbp
0x18019b58b  retn
```
