# CCscUrlAccessor::GetFileSysInfo(IOfflineFilesFileSysInfo *,tagOFFLINEFILES_ITEM_COPY,_FILETIME,int *)

- ea: `0x18001739c`
- end: `0x1800175e4`
- name: `?GetFileSysInfo@CCscUrlAccessor@@AEAAJPEAUIOfflineFilesFileSysInfo@@W4tagOFFLINEFILES_ITEM_COPY@@U_FILETIME@@PEAH@Z`
- size: `584`
- prototype: `__int64 __fastcall(CCscUrlAccessor *__hidden this, struct IOfflineFilesFileSysInfo *, enum tagOFFLINEFILES_ITEM_COPY, struct _FILETIME, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800179fc`

## callees

- `0x180005210`
- `0x18001739c`
- `0x180018034`
- `0x180035c78`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180017473`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180017473`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCscUrlAccessor::GetFileSysInfo(
        CCscUrlAccessor *this,
        struct IOfflineFilesFileSysInfo *a2,
        unsigned int a3,
        FILETIME a4,
        int *a5)
{
  const FILETIME *v8; // r14
  int v9; // ebx
  int v10; // eax
  unsigned int *v11; // r14
  int v12; // edx
  __int64 v14; // [rsp+40h] [rbp-10h] BYREF
  __int64 v15; // [rsp+48h] [rbp-8h] BYREF
  __int64 v16; // [rsp+80h] [rbp+30h] BYREF
  int v17; // [rsp+88h] [rbp+38h] BYREF
  FILETIME FileTime1; // [rsp+98h] [rbp+48h] BYREF

  FileTime1 = a4;
  v8 = (const FILETIME *)((char *)this + 748);
  v9 = ((__int64 (__fastcall *)(struct IOfflineFilesFileSysInfo *, _QWORD, char *, char *, char *, char *))a2->lpVtbl->GetTimes)(
         a2,
         a3,
         (char *)this + 764,
         (char *)this + 756,
         (char *)this + 748,
         (char *)this + 772);
  if ( v9 >= 0 && *((_BYTE *)this + 788) )
  {
    if ( *v8 )
    {
      v9 = 0;
      --*(_QWORD *)v8;
    }
    else
    {
      v9 = -2147024362;
    }
  }
  v15 = 0;
  if ( v9 >= 0 )
  {
    v10 = ((__int64 (__fastcall *)(struct IOfflineFilesFileSysInfo *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
            a2,
            &GUID_8dfadead_26c2_4eff_8a72_6b50723d9a00,
            &v15);
    v9 = v10;
    if ( v10 < 0 )
    {
      if ( v10 != -2147467262 )
        goto LABEL_29;
    }
    else
    {
      *((_DWORD *)this + 196) = 0;
      if ( !CompareFileTime(&FileTime1, v8) )
      {
        *a5 = 1;
        v9 = -2147467259;
      }
      v14 = 0;
      if ( v9 >= 0 )
      {
        v9 = ((__int64 (__fastcall *)(struct IOfflineFilesFileSysInfo *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
               a2,
               &GUID_5b2b0655_b3fd_497d_adeb_bd156bc8355b,
               &v14);
        if ( v9 >= 0 )
        {
          LODWORD(v16) = 0;
          v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v14 + 24LL))(v14, &v16);
          if ( v9 >= 0 )
          {
            if ( (_DWORD)v16 )
            {
              v17 = 0;
              v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v15 + 64LL))(v15, &v17);
              if ( v9 >= 0 )
              {
                if ( v17 )
                  v9 = -2147216895;
                if ( v9 >= 0 )
                {
                  v16 = 0;
                  v9 = ((__int64 (__fastcall *)(struct IOfflineFilesFileSysInfo *, _QWORD, __int64 *))a2->lpVtbl->GetFileSize)(
                         a2,
                         a3,
                         &v16);
                  if ( v9 >= 0 )
                    *((_QWORD *)this + 92) = v16;
                }
              }
            }
            else
            {
              v9 = -2147216895;
            }
          }
        }
      }
      ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&v14);
      if ( v9 < 0 )
        goto LABEL_29;
    }
    v11 = (unsigned int *)((char *)this + 744);
    v9 = ((__int64 (__fastcall *)(struct IOfflineFilesFileSysInfo *, _QWORD, char *))a2->lpVtbl->GetAttributes)(
           a2,
           a3,
           (char *)this + 744);
    if ( v9 >= 0 )
    {
      if ( !*((_BYTE *)this + 789) && (*v11 & 0x4010) == 0x4000 )
      {
        *((_BYTE *)this + 789) = 1;
        *((_DWORD *)this + 195) = GetPolicyDwordAsBool(L"AllowIndexingEncryptedStoresOrItems", 1);
      }
      v9 = TestAttributes(*v11, v12);
    }
  }
LABEL_29:
  ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&v15);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001739c  mov     r11, rsp
0x18001739f  mov     [r11+18h], rbx
0x1800173a3  mov     [r11+20h], r9
0x1800173a7  push    rbp
0x1800173a8  push    rsi
0x1800173a9  push    rdi
0x1800173aa  push    r14
0x1800173ac  push    r15
0x1800173ae  mov     rbp, rsp
0x1800173b1  sub     rsp, 50h
0x1800173b5  mov     r15d, r8d
0x1800173b8  mov     rsi, rdx
0x1800173bb  mov     rdi, rcx
0x1800173be  lea     r14, [rcx+2ECh]
0x1800173c5  mov     rax, [rdx]
0x1800173c8  lea     r10, [rcx+304h]
0x1800173cf  lea     r9, [rcx+2F4h]
0x1800173d6  lea     r8, [rcx+2FCh]
0x1800173dd  mov     [r11-50h], r10
0x1800173e1  mov     [r11-58h], r14
0x1800173e5  mov     edx, r15d
0x1800173e8  mov     rcx, rsi
0x1800173eb  mov     rax, [rax+20h]
0x1800173ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173f4  mov     ebx, eax
0x1800173f6  test    eax, eax
0x1800173f8  js      short loc_18001742F
0x1800173fa  cmp     byte ptr [rdi+314h], 0
0x180017401  jz      short loc_18001742F
0x180017403  mov     ecx, [r14+4]
0x180017407  shl     rcx, 20h
0x18001740b  mov     eax, [r14]
0x18001740e  or      rcx, rax
0x180017411  cmp     rcx, 1
0x180017415  jb      short loc_18001742A
0x180017417  lea     rax, [rcx-1]
0x18001741b  xor     ebx, ebx
0x18001741d  mov     [r14], eax
0x180017420  shr     rax, 20h
0x180017424  mov     [r14+4], eax
0x180017428  jmp     short loc_18001742F
0x18001742a  mov     ebx, 80070216h
0x18001742f  mov     [rbp+var_8], 0
0x180017437  test    ebx, ebx
0x180017439  js      loc_1800175C5
0x18001743f  mov     rax, [rsi]
0x180017442  lea     r8, [rbp+var_8]
0x180017446  lea     rdx, _GUID_8dfadead_26c2_4eff_8a72_6b50723d9a00
0x18001744d  mov     rcx, rsi
0x180017450  mov     rax, [rax]
0x180017453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017458  mov     ebx, eax
0x18001745a  test    eax, eax
0x18001745c  js      loc_18001755C
0x180017462  mov     dword ptr [rdi+310h], 0
0x18001746c  mov     rdx, r14; lpFileTime2
0x18001746f  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x180017473  call    cs:__imp_CompareFileTime
0x180017479  test    eax, eax
0x18001747b  jnz     short loc_18001748C
0x18001747d  mov     rax, [rbp+arg_20]
0x180017481  mov     dword ptr [rax], 1
0x180017487  mov     ebx, 80004005h
0x18001748c  mov     [rbp+var_10], 0
0x180017494  test    ebx, ebx
0x180017496  js      loc_18001754D
0x18001749c  mov     rax, [rsi]
0x18001749f  lea     r8, [rbp+var_10]
0x1800174a3  lea     rdx, _GUID_5b2b0655_b3fd_497d_adeb_bd156bc8355b
0x1800174aa  mov     rcx, rsi
0x1800174ad  mov     rax, [rax]
0x1800174b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174b5  mov     ebx, eax
0x1800174b7  test    eax, eax
0x1800174b9  js      loc_18001754D
0x1800174bf  mov     dword ptr [rbp+arg_0], 0
0x1800174c6  mov     rcx, [rbp+var_10]
0x1800174ca  mov     rax, [rcx]
0x1800174cd  lea     rdx, [rbp+arg_0]
0x1800174d1  mov     rax, [rax+18h]
0x1800174d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174da  mov     ebx, eax
0x1800174dc  test    eax, eax
0x1800174de  js      short loc_18001754D
0x1800174e0  cmp     dword ptr [rbp+arg_0], 0
0x1800174e4  jz      short loc_180017548
0x1800174e6  mov     [rbp+arg_8], 0
0x1800174ed  mov     rcx, [rbp+var_8]
0x1800174f1  mov     rax, [rcx]
0x1800174f4  lea     rdx, [rbp+arg_8]
0x1800174f8  mov     rax, [rax+40h]
0x1800174fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017501  mov     ebx, eax
0x180017503  test    eax, eax
0x180017505  js      short loc_18001754D
0x180017507  mov     eax, 80041201h
0x18001750c  cmp     [rbp+arg_8], 0
0x180017510  cmovnz  ebx, eax
0x180017513  test    ebx, ebx
0x180017515  js      short loc_18001754D
0x180017517  mov     [rbp+arg_0], 0
0x18001751f  mov     rax, [rsi]
0x180017522  lea     r8, [rbp+arg_0]
0x180017526  mov     edx, r15d
0x180017529  mov     rcx, rsi
0x18001752c  mov     rax, [rax+28h]
0x180017530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017535  mov     ebx, eax
0x180017537  test    eax, eax
0x180017539  js      short loc_18001754D
0x18001753b  mov     rax, [rbp+arg_0]
0x18001753f  mov     [rdi+2E0h], rax
0x180017546  jmp     short loc_18001754D
0x180017548  mov     ebx, 80041201h
0x18001754d  lea     rcx, [rbp+var_10]
0x180017551  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x180017556  test    ebx, ebx
0x180017558  jns     short loc_180017563
0x18001755a  jmp     short loc_1800175C5
0x18001755c  cmp     eax, 80004002h
0x180017561  jnz     short loc_1800175C5
0x180017563  lea     r14, [rdi+2E8h]
0x18001756a  mov     rax, [rsi]
0x18001756d  mov     r8, r14
0x180017570  mov     edx, r15d
0x180017573  mov     rcx, rsi
0x180017576  mov     rax, [rax+18h]
0x18001757a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001757f  mov     ebx, eax
0x180017581  test    eax, eax
0x180017583  js      short loc_1800175C5
0x180017585  cmp     byte ptr [rdi+315h], 0
0x18001758c  jnz     short loc_1800175BB
0x18001758e  mov     eax, [r14]
0x180017591  and     eax, 4010h
0x180017596  cmp     eax, 4000h
0x18001759b  jnz     short loc_1800175BB
0x18001759d  mov     byte ptr [rdi+315h], 1
0x1800175a4  mov     edx, 1; int
0x1800175a9  lea     rcx, aAllowindexinge; "AllowIndexingEncryptedStoresOrItems"
0x1800175b0  call    ?GetPolicyDwordAsBool@@YAHPEB_WH@Z; GetPolicyDwordAsBool(wchar_t const *,int)
0x1800175b5  mov     [rdi+30Ch], eax
0x1800175bb  mov     ecx, [r14]; unsigned int
0x1800175be  call    ?TestAttributes@@YAJKH@Z; TestAttributes(ulong,int)
0x1800175c3  mov     ebx, eax
0x1800175c5  lea     rcx, [rbp+var_8]
0x1800175c9  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x1800175ce  mov     eax, ebx
0x1800175d0  mov     rbx, [rsp+50h+arg_10]
0x1800175d8  add     rsp, 50h
0x1800175dc  pop     r15
0x1800175de  pop     r14
0x1800175e0  pop     rdi
0x1800175e1  pop     rsi
0x1800175e2  pop     rbp
0x1800175e3  retn
```
