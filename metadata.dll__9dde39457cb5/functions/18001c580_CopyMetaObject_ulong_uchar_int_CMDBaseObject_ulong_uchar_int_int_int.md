# CopyMetaObject(ulong,uchar *,int,CMDBaseObject *,ulong,uchar *,int,int,int)

- ea: `0x18001c580`
- end: `0x18001ca34`
- name: `?CopyMetaObject@@YAJKPEAEHPEAVCMDBaseObject@@K0HHH@Z`
- size: `1204`
- prototype: `int(unsigned int, unsigned __int8 *, int, struct CMDBaseObject *, unsigned int, unsigned __int8 *, int, int, int)`
- caller_count: `3`
- callee_count: `21`
- tags: ``

## callers

- `0x180016ad0`
- `0x180016b30`
- `0x180018ae0`

## callees

- `0x180002d60`
- `0x180003850`
- `0x180003d30`
- `0x180004690`
- `0x180005690`
- `0x180007810`
- `0x1800147a4`
- `0x180015430`
- `0x1800154b8`
- `0x180015560`
- `0x180015808`
- `0x18001a0d0`
- `0x18001ade0`
- `0x18001c580`
- `0x18001ca3c`
- `0x18001da80`
- `0x1800209e8`
- `0x180020be8`
- `0x180022ff0`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001ca02`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001ca02`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001c69f`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001c69f`

## pseudocode

```c
__int64 __fastcall CopyMetaObject(
        unsigned int a1,
        char *a2,
        int a3,
        struct CMDBaseObject *a4,
        unsigned int a5,
        char *a6,
        int a7,
        int a8,
        int a9)
{
  int TreeCopyWithPath; // ebx
  int v13; // r9d
  int v14; // eax
  int ObjectFromPath; // eax
  unsigned int v16; // edx
  struct CMDHandle *HandleObject; // r12
  int ObjectFromPathWithHandle; // eax
  CMDBaseObject *v19; // rdi
  CMDBaseObject *i; // rax
  int v21; // eax
  CMDBaseObject *v22; // r13
  char *Name; // rax
  char *v24; // rax
  struct CMDBaseObject *Child; // rax
  CMDBaseObject *v26; // rcx
  struct CMDBaseObject *v27; // r15
  CMDHandle *v28; // rax
  void (__fastcall **v29)(struct CMDBaseObject *, __int64); // rax
  struct CMDBaseObject *v30; // rcx
  int v32; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v33; // [rsp+34h] [rbp-CCh]
  unsigned int v34; // [rsp+38h] [rbp-C8h]
  char *v35; // [rsp+40h] [rbp-C0h] BYREF
  struct CMDBaseObject *v36; // [rsp+48h] [rbp-B8h] BYREF
  struct CMDBaseObject *v37; // [rsp+50h] [rbp-B0h] BYREF
  CMDBaseObject *v38; // [rsp+58h] [rbp-A8h] BYREF
  char *v39; // [rsp+60h] [rbp-A0h] BYREF
  char *v40; // [rsp+68h] [rbp-98h]
  char v41[512]; // [rsp+70h] [rbp-90h] BYREF

  v33 = a5;
  v34 = a1;
  v40 = a6;
  v39 = a2;
  v36 = 0;
  v38 = 0;
  v37 = 0;
  v32 = 0;
  if ( g_dwInitialized )
  {
    if ( !a6 )
      return (unsigned int)-2147024809;
    v35 = a6;
    TreeCopyWithPath = 0;
    SkipPathDelimeter(&v35, a9);
    if ( a3 )
    {
      v14 = ExtractNameFromPath(&v35, v41, a9);
      v13 = 0;
      TreeCopyWithPath = v14;
      if ( v14 < 0 )
        TreeCopyWithPath = -2147024809;
    }
    if ( a8 == v13 )
    {
      v35 = a2;
      SkipPathDelimeter(&v35, a9);
      TreeCopyWithPath = ExtractNameFromPath(&v35, v41, a9);
      if ( TreeCopyWithPath < 0 )
        return (unsigned int)-2147024809;
    }
    else if ( TreeCopyWithPath < 0 )
    {
      return (unsigned int)TreeCopyWithPath;
    }
    CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&g_LockMasterResource);
    if ( a3 )
    {
      ObjectFromPath = GetObjectFromPath(&v36, v34, 2 - (a8 != 0), (const CHAR **)&v39, a9);
      a4 = v36;
      TreeCopyWithPath = ObjectFromPath;
    }
    if ( TreeCopyWithPath < 0 )
    {
LABEL_62:
      CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
      return (unsigned int)TreeCopyWithPath;
    }
    v36 = (struct CMDBaseObject *)a6;
    HandleObject = GetHandleObject(v33);
    if ( !HandleObject )
    {
      TreeCopyWithPath = -2147024890;
      goto LABEL_62;
    }
    ObjectFromPathWithHandle = GetObjectFromPathWithHandle(&v38, v16, HandleObject, 2u, (char **)&v36, a9);
    v19 = v38;
    TreeCopyWithPath = ObjectFromPathWithHandle;
    if ( ObjectFromPathWithHandle < 0 )
    {
      if ( ObjectFromPathWithHandle != -2147024893 || !v38 )
        goto LABEL_62;
    }
    else if ( !v38 || !a4 )
    {
      TreeCopyWithPath = -2147467259;
      goto LABEL_62;
    }
    for ( i = v38; i; i = (CMDBaseObject *)*((_QWORD *)i + 23) )
    {
      if ( i == a4 )
      {
        TreeCopyWithPath = -2147024809;
        goto LABEL_62;
      }
    }
    if ( TreeCopyWithPath < 0 )
    {
      if ( TreeCopyWithPath != -2147024893 )
        goto LABEL_62;
      TreeCopyWithPath = MakeTreeCopyWithPath(a4, &v37, (char *)v36, a9);
      if ( TreeCopyWithPath < 0 )
        goto LABEL_62;
      v27 = v37;
      TreeCopyWithPath = CMDBaseObject::InsertChildObject(v19, v37);
      if ( TreeCopyWithPath < 0 )
      {
        if ( !v27 )
          goto LABEL_62;
        v29 = *(void (__fastcall ***)(struct CMDBaseObject *, __int64))v27;
        v30 = v27;
LABEL_60:
        (*v29)(v30, 1);
        goto LABEL_62;
      }
      ++*(_DWORD *)&g_dwSystemChangeNumber;
      INCREMENT_SCHEMA_CHANGE_NUMBER(v33, HandleObject, a6, a9);
    }
    else
    {
      if ( v38 == a4 )
      {
LABEL_54:
        if ( a8 )
          goto LABEL_62;
        CMDBaseObject::RemoveChildObject(*((CMDBaseObject **)a4 + 23), a4);
        v28 = GetHandleObject(v34);
        if ( !CMDHandle::SetChangeData(v28, a4, 1u, 0, 0) || !a4 )
          goto LABEL_62;
        v29 = *(void (__fastcall ***)(struct CMDBaseObject *, __int64))a4;
        v30 = a4;
        goto LABEL_60;
      }
      if ( !a7 )
      {
        TreeCopyWithPath = CopyTree(HandleObject, v38, a4, &v32);
        if ( v32 )
        {
          ++*(_DWORD *)&g_dwSystemChangeNumber;
          INCREMENT_SCHEMA_CHANGE_NUMBER(v33, HandleObject, a6, a9);
        }
LABEL_53:
        if ( TreeCopyWithPath < 0 )
          goto LABEL_62;
        goto LABEL_54;
      }
      if ( !CMDBaseObject::GetName(v38, a9, 0) )
      {
        TreeCopyWithPath = -2147024882;
        goto LABEL_62;
      }
      if ( v19 == g_pboMasterRoot )
      {
        v21 = ReplaceMasterRoot(a4, HandleObject);
LABEL_52:
        TreeCopyWithPath = v21;
        goto LABEL_53;
      }
      v22 = (CMDBaseObject *)*((_QWORD *)v19 + 23);
      Name = CMDBaseObject::GetName(v19, a9, 0);
      TreeCopyWithPath = MakeTreeCopy(a4, &v37, Name, a9);
      if ( TreeCopyWithPath < 0 )
        goto LABEL_62;
      v24 = CMDBaseObject::GetName(v19, a9, 0);
      v32 = 0;
      Child = CMDBaseObject::FindChild(v22, v24, -1, a9, &v32);
      if ( v32 >= 0 && Child )
      {
        CMDBaseObject::RemoveChildObjectFromHash(v26, Child);
        CMDBaseObject::SetLastChangeTime(v22, 0);
      }
      v27 = v37;
      TreeCopyWithPath = CMDBaseObject::InsertChildObject(v22, v37);
      if ( TreeCopyWithPath < 0 )
      {
        if ( v27 )
          (**(void (__fastcall ***)(struct CMDBaseObject *, __int64))v27)(v27, 1);
        CMDBaseObject::InsertChildObject(v22, v19);
        goto LABEL_62;
      }
      ++*(_DWORD *)&g_dwSystemChangeNumber;
      INCREMENT_SCHEMA_CHANGE_NUMBER(v33, HandleObject, v40, a9);
      if ( CMDHandle::SetChangeData(HandleObject, v19, 1u, 0, 0) && v19 )
        (**(void (__fastcall ***)(CMDBaseObject *, __int64))v19)(v19, 1);
    }
    v21 = AddNewChangeData(HandleObject, v27);
    goto LABEL_52;
  }
  return (unsigned int)-2146646016;
}

```

## disassembly

```asm
0x18001c580  mov     [rsp-8+arg_10], rbx
0x18001c585  push    rbp
0x18001c586  push    rsi
0x18001c587  push    rdi
0x18001c588  push    r12
0x18001c58a  push    r13
0x18001c58c  push    r14
0x18001c58e  push    r15
0x18001c590  lea     rbp, [rsp-180h]
0x18001c598  sub     rsp, 280h
0x18001c59f  mov     rax, cs:__security_cookie
0x18001c5a6  xor     rax, rsp
0x18001c5a9  mov     [rbp+1B0h+var_40], rax
0x18001c5b0  mov     eax, [rbp+1B0h+arg_20]
0x18001c5b6  mov     rsi, r9
0x18001c5b9  mov     r13, [rbp+1B0h+arg_28]
0x18001c5c0  xor     r9d, r9d
0x18001c5c3  mov     r14d, [rbp+1B0h+arg_40]
0x18001c5ca  mov     edi, r8d
0x18001c5cd  mov     [rsp+2B0h+var_27C], eax
0x18001c5d1  mov     r12, rdx
0x18001c5d4  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x18001c5da  mov     [rsp+2B0h+var_278], ecx
0x18001c5de  mov     [rsp+2B0h+var_248], r13
0x18001c5e3  mov     [rsp+2B0h+var_250], rdx
0x18001c5e8  mov     [rsp+2B0h+var_268], r9
0x18001c5ed  mov     [rsp+2B0h+var_258], r9
0x18001c5f2  mov     [rsp+2B0h+var_260], r9
0x18001c5f7  mov     [rsp+2B0h+var_280], r9d
0x18001c5fc  test    eax, eax
0x18001c5fe  jnz     short loc_18001C60A
0x18001c600  mov     ebx, 800CC800h
0x18001c605  jmp     loc_18001CA08
0x18001c60a  test    r13, r13
0x18001c60d  jnz     short loc_18001C619
0x18001c60f  mov     ebx, 80070057h
0x18001c614  jmp     loc_18001CA08
0x18001c619  mov     edx, r14d; int
0x18001c61c  mov     [rsp+2B0h+var_270], r13
0x18001c621  lea     rcx, [rsp+2B0h+var_270]; char **
0x18001c626  mov     ebx, r9d
0x18001c629  call    ?SkipPathDelimeter@@YAXAEAPEADH@Z; SkipPathDelimeter(char * &,int)
0x18001c62e  mov     r15d, 80070057h
0x18001c634  test    edi, edi
0x18001c636  jz      short loc_18001C655
0x18001c638  mov     r8d, r14d; int
0x18001c63b  lea     rdx, [rsp+2B0h+var_240]; char *
0x18001c640  lea     rcx, [rsp+2B0h+var_270]; char **
0x18001c645  call    ?ExtractNameFromPath@@YAJAEAPEADPEADH@Z; ExtractNameFromPath(char * &,char *,int)
0x18001c64a  xor     r9d, r9d
0x18001c64d  mov     ebx, eax
0x18001c64f  test    eax, eax
0x18001c651  cmovs   ebx, r15d
0x18001c655  cmp     [rbp+1B0h+arg_38], r9d
0x18001c65c  jnz     short loc_18001C690
0x18001c65e  mov     edx, r14d; int
0x18001c661  mov     [rsp+2B0h+var_270], r12
0x18001c666  lea     rcx, [rsp+2B0h+var_270]; char **
0x18001c66b  call    ?SkipPathDelimeter@@YAXAEAPEADH@Z; SkipPathDelimeter(char * &,int)
0x18001c670  mov     r8d, r14d; int
0x18001c673  lea     rdx, [rsp+2B0h+var_240]; char *
0x18001c678  lea     rcx, [rsp+2B0h+var_270]; char **
0x18001c67d  call    ?ExtractNameFromPath@@YAJAEAPEADPEADH@Z; ExtractNameFromPath(char * &,char *,int)
0x18001c682  mov     ebx, eax
0x18001c684  test    eax, eax
0x18001c686  jns     short loc_18001C698
0x18001c688  mov     ebx, r15d
0x18001c68b  jmp     loc_18001CA08
0x18001c690  test    ebx, ebx
0x18001c692  js      loc_18001CA08
0x18001c698  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x18001c69f  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18001c6a5  test    edi, edi
0x18001c6a7  jz      short loc_18001C6D7
0x18001c6a9  mov     eax, [rbp+1B0h+arg_38]
0x18001c6af  lea     r9, [rsp+2B0h+var_250]; char **
0x18001c6b4  mov     edx, [rsp+2B0h+var_278]; unsigned int
0x18001c6b8  lea     rcx, [rsp+2B0h+var_268]; struct CMDBaseObject **
0x18001c6bd  neg     eax
0x18001c6bf  mov     dword ptr [rsp+2B0h+var_290], r14d; int
0x18001c6c4  sbb     r8d, r8d
0x18001c6c7  add     r8d, 2; unsigned int
0x18001c6cb  call    ?GetObjectFromPath@@YAJAEAPEAVCMDBaseObject@@KKAEAPEADH@Z; GetObjectFromPath(CMDBaseObject * &,ulong,ulong,char * &,int)
0x18001c6d0  mov     rsi, [rsp+2B0h+var_268]
0x18001c6d5  mov     ebx, eax
0x18001c6d7  test    ebx, ebx
0x18001c6d9  js      loc_18001C9FB
0x18001c6df  mov     ecx, [rsp+2B0h+var_27C]; unsigned int
0x18001c6e3  mov     [rsp+2B0h+var_268], r13
0x18001c6e8  call    ?GetHandleObject@@YAPEAVCMDHandle@@K@Z; GetHandleObject(ulong)
0x18001c6ed  mov     r12, rax
0x18001c6f0  test    rax, rax
0x18001c6f3  jz      loc_18001C9F6
0x18001c6f9  lea     rax, [rsp+2B0h+var_268]
0x18001c6fe  mov     [rsp+2B0h+var_288], r14d; int
0x18001c703  mov     r9d, 2; unsigned int
0x18001c709  mov     [rsp+2B0h+var_290], rax; char **
0x18001c70e  mov     r8, r12; struct CMDHandle *
0x18001c711  lea     rcx, [rsp+2B0h+var_258]; struct CMDBaseObject **
0x18001c716  call    ?GetObjectFromPathWithHandle@@YAJAEAPEAVCMDBaseObject@@KPEAVCMDHandle@@KAEAPEADH@Z; GetObjectFromPathWithHandle(CMDBaseObject * &,ulong,CMDHandle *,ulong,char * &,int)
0x18001c71b  mov     rdi, [rsp+2B0h+var_258]
0x18001c720  mov     ebx, eax
0x18001c722  mov     ecx, 80070003h
0x18001c727  test    eax, eax
0x18001c729  js      short loc_18001C73F
0x18001c72b  test    rdi, rdi
0x18001c72e  jz      short loc_18001C735
0x18001c730  test    rsi, rsi
0x18001c733  jnz     short loc_18001C750
0x18001c735  mov     ebx, 80004005h
0x18001c73a  jmp     loc_18001C9FB
0x18001c73f  cmp     ebx, ecx
0x18001c741  jnz     loc_18001C9FB
0x18001c747  test    rdi, rdi
0x18001c74a  jz      loc_18001C9FB
0x18001c750  mov     rax, rdi
0x18001c753  test    rax, rax
0x18001c756  jz      short loc_18001C76E
0x18001c758  cmp     rax, rsi
0x18001c75b  jz      short loc_18001C766
0x18001c75d  mov     rax, [rax+0B8h]
0x18001c764  jmp     short loc_18001C753
0x18001c766  mov     ebx, r15d
0x18001c769  jmp     loc_18001C9FB
0x18001c76e  test    ebx, ebx
0x18001c770  js      loc_18001C91B
0x18001c776  cmp     rdi, rsi
0x18001c779  jz      loc_18001C98A
0x18001c77f  cmp     [rbp+1B0h+arg_30], 0
0x18001c786  jz      loc_18001C8E1
0x18001c78c  xor     r8d, r8d; unsigned int *
0x18001c78f  mov     edx, r14d; int
0x18001c792  mov     rcx, rdi; this
0x18001c795  call    ?GetName@CMDBaseObject@@QEAAPEADHPEAK@Z; CMDBaseObject::GetName(int,ulong *)
0x18001c79a  test    rax, rax
0x18001c79d  jnz     short loc_18001C7A9
0x18001c79f  mov     ebx, 8007000Eh
0x18001c7a4  jmp     loc_18001C9FB
0x18001c7a9  cmp     rdi, cs:?g_pboMasterRoot@@3PEAVCMDBaseObject@@EA; CMDBaseObject * g_pboMasterRoot
0x18001c7b0  jnz     short loc_18001C7C2
0x18001c7b2  mov     rdx, r12; struct CMDHandle *
0x18001c7b5  mov     rcx, rsi; struct CMDBaseObject *
0x18001c7b8  call    ?ReplaceMasterRoot@@YAJPEAVCMDBaseObject@@PEAVCMDHandle@@@Z; ReplaceMasterRoot(CMDBaseObject *,CMDHandle *)
0x18001c7bd  jmp     loc_18001C984
0x18001c7c2  mov     r13, [rdi+0B8h]
0x18001c7c9  xor     r8d, r8d; unsigned int *
0x18001c7cc  mov     edx, r14d; int
0x18001c7cf  mov     rcx, rdi; this
0x18001c7d2  call    ?GetName@CMDBaseObject@@QEAAPEADHPEAK@Z; CMDBaseObject::GetName(int,ulong *)
0x18001c7d7  mov     r9d, r14d; int
0x18001c7da  lea     rdx, [rsp+2B0h+var_260]; struct CMDBaseObject **
0x18001c7df  mov     r8, rax; char *
0x18001c7e2  mov     rcx, rsi; struct CMDBaseObject *
0x18001c7e5  call    ?MakeTreeCopy@@YAJPEAVCMDBaseObject@@AEAPEAV1@PEADH@Z; MakeTreeCopy(CMDBaseObject *,CMDBaseObject * &,char *,int)
0x18001c7ea  mov     ebx, eax
0x18001c7ec  test    eax, eax
0x18001c7ee  js      loc_18001C9FB
0x18001c7f4  xor     r8d, r8d; unsigned int *
0x18001c7f7  mov     edx, r14d; int
0x18001c7fa  mov     rcx, rdi; this
0x18001c7fd  call    ?GetName@CMDBaseObject@@QEAAPEADHPEAK@Z; CMDBaseObject::GetName(int,ulong *)
0x18001c802  lea     rcx, [rsp+2B0h+var_280]
0x18001c807  mov     [rsp+2B0h+var_280], 0
0x18001c80f  mov     [rsp+2B0h+var_290], rcx; int *
0x18001c814  mov     r9d, r14d; int
0x18001c817  mov     rcx, r13; this
0x18001c81a  or      r8d, 0FFFFFFFFh; int
0x18001c81e  mov     rdx, rax; char *
0x18001c821  call    ?FindChild@CMDBaseObject@@AEAAPEAV1@PEADHHPEAJ@Z; CMDBaseObject::FindChild(char *,int,int,long *)
0x18001c826  cmp     [rsp+2B0h+var_280], 0
0x18001c82b  jl      short loc_18001C844
0x18001c82d  test    rax, rax
0x18001c830  jz      short loc_18001C844
0x18001c832  mov     rdx, rax; struct CMDBaseObject *
0x18001c835  call    ?RemoveChildObjectFromHash@CMDBaseObject@@QEAAXPEAV1@@Z; CMDBaseObject::RemoveChildObjectFromHash(CMDBaseObject *)
0x18001c83a  xor     edx, edx; struct _FILETIME *
0x18001c83c  mov     rcx, r13; this
0x18001c83f  call    ?SetLastChangeTime@CMDBaseObject@@QEAAXPEAU_FILETIME@@@Z; CMDBaseObject::SetLastChangeTime(_FILETIME *)
0x18001c844  mov     r15, [rsp+2B0h+var_260]
0x18001c849  mov     rcx, r13; this
0x18001c84c  mov     rdx, r15; struct CMDBaseObject *
0x18001c84f  call    ?InsertChildObject@CMDBaseObject@@QEAAJPEAV1@@Z; CMDBaseObject::InsertChildObject(CMDBaseObject *)
0x18001c854  mov     ebx, eax
0x18001c856  test    eax, eax
0x18001c858  js      short loc_18001C8B9
0x18001c85a  mov     r8, [rsp+2B0h+var_248]; char *
0x18001c85f  mov     ebx, 1
0x18001c864  mov     ecx, [rsp+2B0h+var_27C]; unsigned int
0x18001c868  mov     r9d, r14d; int
0x18001c86b  add     cs:?g_dwSystemChangeNumber@@3KA, ebx; ulong g_dwSystemChangeNumber
0x18001c871  mov     rdx, r12; struct CMDHandle *
0x18001c874  call    ?INCREMENT_SCHEMA_CHANGE_NUMBER@@YAXKPEAVCMDHandle@@PEADH@Z; INCREMENT_SCHEMA_CHANGE_NUMBER(ulong,CMDHandle *,char *,int)
0x18001c879  xor     r9d, r9d; unsigned int
0x18001c87c  mov     [rsp+2B0h+var_290], 0; unsigned __int16 *
0x18001c885  mov     r8d, ebx; unsigned int
0x18001c888  mov     rdx, rdi; struct CMDBaseObject *
0x18001c88b  mov     rcx, r12; this
0x18001c88e  call    ?SetChangeData@CMDHandle@@QEAAJPEAVCMDBaseObject@@KKPEAG@Z; CMDHandle::SetChangeData(CMDBaseObject *,ulong,ulong,ushort *)
0x18001c893  test    eax, eax
0x18001c895  jz      loc_18001C979
0x18001c89b  test    rdi, rdi
0x18001c89e  jz      loc_18001C979
0x18001c8a4  mov     rax, [rdi]
0x18001c8a7  mov     edx, ebx
0x18001c8a9  mov     rcx, rdi
0x18001c8ac  mov     rax, [rax]
0x18001c8af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8b4  jmp     loc_18001C979
0x18001c8b9  test    r15, r15
0x18001c8bc  jz      short loc_18001C8D1
0x18001c8be  mov     rax, [r15]
0x18001c8c1  mov     edx, 1
0x18001c8c6  mov     rcx, r15
0x18001c8c9  mov     rax, [rax]
0x18001c8cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8d1  mov     rdx, rdi; struct CMDBaseObject *
0x18001c8d4  mov     rcx, r13; this
0x18001c8d7  call    ?InsertChildObject@CMDBaseObject@@QEAAJPEAV1@@Z; CMDBaseObject::InsertChildObject(CMDBaseObject *)
0x18001c8dc  jmp     loc_18001C9FB
0x18001c8e1  lea     r9, [rsp+2B0h+var_280]; int *
0x18001c8e6  mov     r8, rsi; struct CMDBaseObject *
0x18001c8e9  mov     rdx, rdi; struct CMDBaseObject *
0x18001c8ec  mov     rcx, r12; struct CMDHandle *
0x18001c8ef  call    ?CopyTree@@YAJPEAVCMDHandle@@PEAVCMDBaseObject@@1AEAH@Z; CopyTree(CMDHandle *,CMDBaseObject *,CMDBaseObject *,int &)
0x18001c8f4  cmp     [rsp+2B0h+var_280], 0
0x18001c8f9  mov     ebx, eax
0x18001c8fb  jz      loc_18001C986
0x18001c901  inc     cs:?g_dwSystemChangeNumber@@3KA; ulong g_dwSystemChangeNumber
0x18001c907  mov     r9d, r14d; int
0x18001c90a  mov     ecx, [rsp+2B0h+var_27C]; unsigned int
0x18001c90e  mov     r8, r13; char *
0x18001c911  mov     rdx, r12; struct CMDHandle *
0x18001c914  call    ?INCREMENT_SCHEMA_CHANGE_NUMBER@@YAXKPEAVCMDHandle@@PEADH@Z; INCREMENT_SCHEMA_CHANGE_NUMBER(ulong,CMDHandle *,char *,int)
0x18001c919  jmp     short loc_18001C986
0x18001c91b  cmp     ebx, ecx
0x18001c91d  jnz     loc_18001C9FB
0x18001c923  test    rdi, rdi
0x18001c926  jz      loc_18001C9FB
0x18001c92c  mov     r8, [rsp+2B0h+var_268]; char *
0x18001c931  lea     rdx, [rsp+2B0h+var_260]; struct CMDBaseObject **
0x18001c936  mov     r9d, r14d; int
0x18001c939  mov     rcx, rsi; struct CMDBaseObject *
0x18001c93c  call    ?MakeTreeCopyWithPath@@YAJPEAVCMDBaseObject@@AEAPEAV1@PEADH@Z; MakeTreeCopyWithPath(CMDBaseObject *,CMDBaseObject * &,char *,int)
0x18001c941  mov     ebx, eax
0x18001c943  test    eax, eax
0x18001c945  js      loc_18001C9FB
0x18001c94b  mov     r15, [rsp+2B0h+var_260]
0x18001c950  mov     rcx, rdi; this
0x18001c953  mov     rdx, r15; struct CMDBaseObject *
0x18001c956  call    ?InsertChildObject@CMDBaseObject@@QEAAJPEAV1@@Z; CMDBaseObject::InsertChildObject(CMDBaseObject *)
0x18001c95b  mov     ebx, eax
0x18001c95d  test    eax, eax
0x18001c95f  js      short loc_18001C9DC
0x18001c961  inc     cs:?g_dwSystemChangeNumber@@3KA; ulong g_dwSystemChangeNumber
0x18001c967  mov     r9d, r14d; int
0x18001c96a  mov     ecx, [rsp+2B0h+var_27C]; unsigned int
0x18001c96e  mov     r8, r13; char *
0x18001c971  mov     rdx, r12; struct CMDHandle *
0x18001c974  call    ?INCREMENT_SCHEMA_CHANGE_NUMBER@@YAXKPEAVCMDHandle@@PEADH@Z; INCREMENT_SCHEMA_CHANGE_NUMBER(ulong,CMDHandle *,char *,int)
0x18001c979  mov     rdx, r15; struct CMDBaseObject *
0x18001c97c  mov     rcx, r12; struct CMDHandle *
0x18001c97f  call    ?AddNewChangeData@@YAJPEAVCMDHandle@@PEAVCMDBaseObject@@@Z; AddNewChangeData(CMDHandle *,CMDBaseObject *)
0x18001c984  mov     ebx, eax
0x18001c986  test    ebx, ebx
0x18001c988  js      short loc_18001C9FB
0x18001c98a  cmp     [rbp+1B0h+arg_38], 0
0x18001c991  jnz     short loc_18001C9FB
0x18001c993  mov     rcx, [rsi+0B8h]; this
0x18001c99a  mov     rdx, rsi; struct CMDBaseObject *
0x18001c99d  call    ?RemoveChildObject@CMDBaseObject@@QEAAJPEAV1@@Z; CMDBaseObject::RemoveChildObject(CMDBaseObject *)
0x18001c9a2  mov     ecx, [rsp+2B0h+var_278]; unsigned int
0x18001c9a6  call    ?GetHandleObject@@YAPEAVCMDHandle@@K@Z; GetHandleObject(ulong)
0x18001c9ab  xor     r9d, r9d; unsigned int
0x18001c9ae  mov     [rsp+2B0h+var_290], 0; unsigned __int16 *
0x18001c9b7  mov     rdx, rsi; struct CMDBaseObject *
0x18001c9ba  mov     rcx, rax; this
0x18001c9bd  lea     edi, [r9+1]
0x18001c9c1  mov     r8d, edi; unsigned int
0x18001c9c4  call    ?SetChangeData@CMDHandle@@QEAAJPEAVCMDBaseObject@@KKPEAG@Z; CMDHandle::SetChangeData(CMDBaseObject *,ulong,ulong,ushort *)
0x18001c9c9  test    eax, eax
0x18001c9cb  jz      short loc_18001C9FB
0x18001c9cd  test    rsi, rsi
0x18001c9d0  jz      short loc_18001C9FB
0x18001c9d2  mov     rax, [rsi]
0x18001c9d5  mov     edx, edi
0x18001c9d7  mov     rcx, rsi
0x18001c9da  jmp     short loc_18001C9EC
0x18001c9dc  test    r15, r15
0x18001c9df  jz      short loc_18001C9FB
0x18001c9e1  mov     rax, [r15]
0x18001c9e4  mov     edx, 1
0x18001c9e9  mov     rcx, r15
0x18001c9ec  mov     rax, [rax]
0x18001c9ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c9f4  jmp     short loc_18001C9FB
0x18001c9f6  mov     ebx, 80070006h
0x18001c9fb  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x18001ca02  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18001ca08  mov     eax, ebx
0x18001ca0a  mov     rcx, [rbp+1B0h+var_40]
  ... truncated ...
```
