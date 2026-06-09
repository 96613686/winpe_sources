# NtWin32LiveSystemProvider::QueryMiscInformationEx(void *,ulong,ulong *,void *,ulong,ulong *,MISC_EXDATA *)

- ea: `0x180025710`
- end: `0x180025af5`
- name: `?QueryMiscInformationEx@NtWin32LiveSystemProvider@@UEAAJPEAXKPEAK0K1PEAUMISC_EXDATA@@@Z`
- size: `997`
- prototype: `__int64 __fastcall(NtWin32LiveSystemProvider *__hidden this, void *, unsigned int, unsigned int *, void *, unsigned int, unsigned int *, struct MISC_EXDATA *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180021ec0`
- `0x1800256d0`

## callees

- `0x180001710`
- `0x180002194`
- `0x1800021a0`
- `0x1800021f4`
- `0x180005e44`
- `0x180025710`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800257b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025859`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800258da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025923`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800257b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025859`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800258da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025923`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002591b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002591b`

## pseudocode

```c
__int64 __fastcall NtWin32LiveSystemProvider::QueryMiscInformationEx(
        NtWin32LiveSystemProvider *this,
        void *a2,
        __int64 a3,
        unsigned int *a4,
        char *a5,
        unsigned int a6,
        unsigned int *a7,
        struct MISC_EXDATA *a8)
{
  void *v10; // r12
  __int64 (__fastcall *v11)(char *); // rax
  unsigned int v12; // r15d
  int v13; // eax
  unsigned int (__fastcall *v14)(void *, __int64, HANDLE *); // rax
  signed int LastError; // eax
  _QWORD *v16; // rax
  _QWORD *v17; // r12
  __int64 (__fastcall *v18)(_QWORD, _QWORD); // rbx
  _BYTE *v19; // rax
  signed int v20; // eax
  signed int v21; // eax
  __int64 (__fastcall *v22)(void *, __int64, char *); // rax
  int *v23; // rbx
  int v24; // eax
  int v25; // eax
  __int64 v26; // rax
  __int64 v27; // r8
  unsigned int v28; // r8d
  size_t *p_Size; // [rsp+20h] [rbp-E0h]
  size_t Size; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-B8h] BYREF
  void *v33; // [rsp+50h] [rbp-B0h]
  _QWORD v34[7]; // [rsp+60h] [rbp-A0h] BYREF
  int v35; // [rsp+98h] [rbp-68h]
  struct _XSTATE_CONFIGURATION v36; // [rsp+A0h] [rbp-60h] BYREF

  v10 = a2;
  v33 = a2;
  *a4 = 0;
  if ( a7 )
    *a7 = 1364;
  if ( !a5 || a6 < 0x554 )
    return (unsigned int)-2147024662;
  v11 = (__int64 (__fastcall *)(char *))*((_QWORD *)this + 44);
  v12 = -2147467259;
  if ( v11 )
  {
    v13 = v11(a5 + 60);
    *((_DWORD *)a5 + 14) = v13;
    if ( v13 == -1 )
      *((_DWORD *)a5 + 15) = GetLastError();
    else
      *a4 |= 0x40u;
  }
  LODWORD(Size) = 0;
  memset_0(v34, 0, 0x40u);
  v14 = (unsigned int (__fastcall *)(void *, __int64, HANDLE *))*((_QWORD *)this + 125);
  if ( v14 && *((_QWORD *)this + 126) && *((_QWORD *)this + 127) && *((_QWORD *)this + 128) )
  {
    hObject = 0;
    if ( v14(v10, 8, &hObject) )
    {
      p_Size = &Size;
      (*((void (__fastcall **)(HANDLE, __int64, _QWORD))this + 126))(hObject, 25, 0);
      LastError = GetLastError();
      *((_DWORD *)a5 + 11) = LastError;
      if ( LastError == 122 )
      {
        v16 = o_malloc_0((unsigned int)Size);
        v17 = v16;
        if ( v16 )
        {
          if ( (*((unsigned int (__fastcall **)(HANDLE, __int64, _QWORD *, _QWORD, size_t *))this + 126))(
                 hObject,
                 25,
                 v16,
                 (unsigned int)Size,
                 &Size) )
          {
            v18 = (__int64 (__fastcall *)(_QWORD, _QWORD))*((_QWORD *)this + 127);
            v19 = (_BYTE *)(*((__int64 (__fastcall **)(_QWORD))this + 128))(*v17);
            *((_DWORD *)a5 + 11) = *(_DWORD *)v18(*v17, (unsigned __int8)(*v19 - 1));
            *a4 |= 0x10u;
          }
          else
          {
            v20 = GetLastError();
            if ( v20 > 0 )
              v20 = (unsigned __int16)v20 | 0x80070000;
            *((_DWORD *)a5 + 11) = v20;
          }
          free(v17);
        }
        else
        {
          *((_DWORD *)a5 + 11) = -2147024882;
        }
        v10 = v33;
      }
      else
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        *((_DWORD *)a5 + 11) = LastError;
      }
      CloseHandle(hObject);
    }
    else
    {
      v21 = GetLastError();
      if ( v21 > 0 )
        v21 = (unsigned __int16)v21 | 0x80070000;
      *((_DWORD *)a5 + 11) = v21;
    }
  }
  else
  {
    *((_DWORD *)a5 + 11) = -2147467263;
  }
  v22 = (__int64 (__fastcall *)(void *, __int64, char *))*((_QWORD *)this + 107);
  v23 = (int *)(a5 + 48);
  if ( v22 )
  {
    v24 = v22(v10, 34, a5 + 48);
    if ( v24 < 0 )
      *v23 = v24 | 0x10000000;
    else
      *a4 |= 0x20u;
    memset_0(v34, 0, 0x40u);
    v34[0] = 64;
    v25 = (*((__int64 (__fastcall **)(void *, _QWORD, _QWORD *, __int64, size_t *))this + 107))(v10, 0, v34, 64, &Size);
    if ( v25 < 0 )
    {
      *((_DWORD *)a5 + 13) = v25 | 0x10000000;
    }
    else
    {
      *((_DWORD *)a5 + 13) = v35 & 1;
      *a4 |= 0x80u;
    }
    *((_DWORD *)a5 + 340) = 0;
    if ( *((_DWORD *)this + 17) >= 0x1770u
      && (*((int (__fastcall **)(void *, __int64, char *, __int64, size_t *))this + 107))(v10, 36, a5 + 1360, 4, &Size) >= 0 )
    {
      *a4 |= 0x200u;
    }
  }
  else
  {
    *((_DWORD *)a5 + 13) = -2147467263;
    *v23 = -2147467263;
  }
  if ( a8 && (*(_DWORD *)a8 & 0x200000) != 0 )
  {
    memset_0(&v36, 0, 0x358u);
    v26 = *(_QWORD *)this;
    v27 = *((_QWORD *)a8 + 1);
    LODWORD(hObject) = 0;
    LODWORD(p_Size) = 856;
    if ( !(*(unsigned int (__fastcall **)(NtWin32LiveSystemProvider *, void *, __int64, struct _XSTATE_CONFIGURATION *, size_t *, HANDLE *))(v26 + 232))(
            this,
            v10,
            v27,
            &v36,
            p_Size,
            &hObject)
      && (_DWORD)hObject == 856 )
    {
      if ( (v36.EnabledFeatures & 0xE4) != 0 || (v36.EnabledUserVisibleSupervisorFeatures & 0x800) != 0 )
      {
        CopyXStateConfigToMiscInfo(&v36, (struct _XSTATE_CONFIG_FEATURE_MSC_INFO *)(a5 + 832), v28);
        *((_DWORD *)a5 + 209) = *((_DWORD *)a8 + 4);
      }
      return v12;
    }
    return (unsigned int)-2147024662;
  }
  return v12;
}

```

## disassembly

```asm
0x180025710  mov     [rsp-8+arg_10], rbx
0x180025715  push    rbp
0x180025716  push    rsi
0x180025717  push    rdi
0x180025718  push    r12
0x18002571a  push    r13
0x18002571c  push    r14
0x18002571e  push    r15
0x180025720  lea     rbp, [rsp-310h]
0x180025728  sub     rsp, 410h
0x18002572f  mov     rax, cs:__security_cookie
0x180025736  xor     rax, rsp
0x180025739  mov     [rbp+340h+var_40], rax
0x180025740  mov     rax, [rbp+340h+arg_30]
0x180025747  mov     rsi, rcx
0x18002574a  mov     r13, [rbp+340h+arg_38]
0x180025751  mov     r14, r9
0x180025754  mov     rdi, [rbp+340h+arg_20]
0x18002575b  mov     r12, rdx
0x18002575e  mov     [rsp+440h+var_3F0], rdx
0x180025763  mov     ecx, 554h
0x180025768  mov     dword ptr [r9], 0
0x18002576f  test    rax, rax
0x180025772  jz      short loc_180025776
0x180025774  mov     [rax], ecx
0x180025776  test    rdi, rdi
0x180025779  jz      loc_180025AC2
0x18002577f  cmp     [rbp+340h+arg_28], ecx
0x180025785  jb      loc_180025AC2
0x18002578b  mov     rax, [rsi+160h]
0x180025792  mov     r15d, 80004005h
0x180025798  test    rax, rax
0x18002579b  jz      short loc_1800257BD
0x18002579d  lea     rcx, [rdi+3Ch]
0x1800257a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800257a6  mov     [rdi+38h], eax
0x1800257a9  cmp     eax, 0FFFFFFFFh
0x1800257ac  jz      short loc_1800257B4
0x1800257ae  or      dword ptr [r14], 40h
0x1800257b2  jmp     short loc_1800257BD
0x1800257b4  call    cs:__imp_GetLastError
0x1800257ba  mov     [rdi+3Ch], eax
0x1800257bd  xor     edx, edx; Val
0x1800257bf  mov     dword ptr [rsp+440h+Size], 0
0x1800257c7  lea     rcx, [rsp+440h+var_3E0]; void *
0x1800257cc  lea     r8d, [rdx+40h]; Size
0x1800257d0  call    memset_0
0x1800257d5  mov     rax, [rsi+3E8h]
0x1800257dc  test    rax, rax
0x1800257df  jz      loc_18002593A
0x1800257e5  cmp     qword ptr [rsi+3F0h], 0
0x1800257ed  jz      loc_18002593A
0x1800257f3  cmp     qword ptr [rsi+3F8h], 0
0x1800257fb  jz      loc_18002593A
0x180025801  cmp     qword ptr [rsi+400h], 0
0x180025809  jz      loc_18002593A
0x18002580f  lea     r8, [rsp+440h+hObject]
0x180025814  mov     [rsp+440h+hObject], 0
0x18002581d  mov     edx, 8
0x180025822  mov     rcx, r12
0x180025825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002582a  test    eax, eax
0x18002582c  jz      loc_180025923
0x180025832  mov     rcx, [rsp+440h+hObject]
0x180025837  lea     rax, [rsp+440h+Size]
0x18002583c  xor     r9d, r9d
0x18002583f  mov     [rsp+440h+var_420], rax
0x180025844  mov     rax, [rsi+3F0h]
0x18002584b  xor     r8d, r8d
0x18002584e  lea     ebx, [r9+19h]
0x180025852  mov     edx, ebx
0x180025854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025859  call    cs:__imp_GetLastError
0x18002585f  mov     [rdi+2Ch], eax
0x180025862  cmp     eax, 7Ah ; 'z'
0x180025865  jnz     loc_180025907
0x18002586b  mov     ecx, dword ptr [rsp+440h+Size]; Size
0x18002586f  call    _o_malloc_0
0x180025874  mov     r12, rax
0x180025877  test    rax, rax
0x18002587a  jz      short loc_1800258F9
0x18002587c  mov     r9d, dword ptr [rsp+440h+Size]
0x180025881  lea     rax, [rsp+440h+Size]
0x180025886  mov     rcx, [rsp+440h+hObject]
0x18002588b  mov     r8, r12
0x18002588e  mov     [rsp+440h+var_420], rax
0x180025893  mov     edx, ebx
0x180025895  mov     rax, [rsi+3F0h]
0x18002589c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258a1  test    eax, eax
0x1800258a3  jz      short loc_1800258DA
0x1800258a5  mov     rcx, [r12]
0x1800258a9  mov     rax, [rsi+400h]
0x1800258b0  mov     rbx, [rsi+3F8h]
0x1800258b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258bc  mov     cl, [rax]
0x1800258be  mov     rax, rbx
0x1800258c1  dec     cl
0x1800258c3  movzx   edx, cl
0x1800258c6  mov     rcx, [r12]
0x1800258ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258cf  mov     ecx, [rax]
0x1800258d1  mov     [rdi+2Ch], ecx
0x1800258d4  or      dword ptr [r14], 10h
0x1800258d8  jmp     short loc_1800258EF
0x1800258da  call    cs:__imp_GetLastError
0x1800258e0  test    eax, eax
0x1800258e2  jle     short loc_1800258EC
0x1800258e4  movzx   eax, ax
0x1800258e7  or      eax, 80070000h
0x1800258ec  mov     [rdi+2Ch], eax
0x1800258ef  mov     rcx, r12; Block
0x1800258f2  call    free
0x1800258f7  jmp     short loc_180025900
0x1800258f9  mov     dword ptr [rdi+2Ch], 8007000Eh
0x180025900  mov     r12, [rsp+440h+var_3F0]
0x180025905  jmp     short loc_180025916
0x180025907  test    eax, eax
0x180025909  jle     short loc_180025913
0x18002590b  movzx   eax, ax
0x18002590e  or      eax, 80070000h
0x180025913  mov     [rdi+2Ch], eax
0x180025916  mov     rcx, [rsp+440h+hObject]; hObject
0x18002591b  call    cs:__imp_CloseHandle
0x180025921  jmp     short loc_180025941
0x180025923  call    cs:__imp_GetLastError
0x180025929  test    eax, eax
0x18002592b  jle     short loc_180025935
0x18002592d  movzx   eax, ax
0x180025930  or      eax, 80070000h
0x180025935  mov     [rdi+2Ch], eax
0x180025938  jmp     short loc_180025941
0x18002593a  mov     dword ptr [rdi+2Ch], 80004001h
0x180025941  mov     rax, [rsi+358h]
0x180025948  lea     rbx, [rdi+30h]
0x18002594c  test    rax, rax
0x18002594f  jz      loc_180025A1F
0x180025955  mov     r9d, 4
0x18002595b  lea     rcx, [rsp+440h+Size]
0x180025960  mov     [rsp+440h+var_420], rcx
0x180025965  mov     r8, rbx
0x180025968  mov     rcx, r12
0x18002596b  lea     edx, [r9+1Eh]
0x18002596f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025974  test    eax, eax
0x180025976  js      short loc_18002597E
0x180025978  or      dword ptr [r14], 20h
0x18002597c  jmp     short loc_180025984
0x18002597e  bts     eax, 1Ch
0x180025982  mov     [rbx], eax
0x180025984  mov     ebx, 40h ; '@'
0x180025989  lea     rcx, [rsp+440h+var_3E0]; void *
0x18002598e  mov     r8d, ebx; Size
0x180025991  xor     edx, edx; Val
0x180025993  call    memset_0
0x180025998  lea     rax, [rsp+440h+Size]
0x18002599d  mov     [rsp+440h+var_3E0], rbx
0x1800259a2  mov     [rsp+440h+var_420], rax
0x1800259a7  lea     r8, [rsp+440h+var_3E0]
0x1800259ac  mov     rax, [rsi+358h]
0x1800259b3  mov     r9d, ebx
0x1800259b6  xor     edx, edx
0x1800259b8  mov     rcx, r12
0x1800259bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800259c0  test    eax, eax
0x1800259c2  js      short loc_1800259D4
0x1800259c4  mov     eax, [rbp+340h+var_3A8]
0x1800259c7  and     eax, 1
0x1800259ca  mov     [rdi+34h], eax
0x1800259cd  bts     dword ptr [r14], 7
0x1800259d2  jmp     short loc_1800259DB
0x1800259d4  bts     eax, 1Ch
0x1800259d8  mov     [rdi+34h], eax
0x1800259db  lea     r8, [rdi+550h]
0x1800259e2  mov     dword ptr [r8], 0
0x1800259e9  cmp     dword ptr [rsi+44h], 1770h
0x1800259f0  jb      short loc_180025A2C
0x1800259f2  mov     edx, 24h ; '$'
0x1800259f7  lea     rax, [rsp+440h+Size]
0x1800259fc  mov     [rsp+440h+var_420], rax
0x180025a01  mov     rcx, r12
0x180025a04  mov     rax, [rsi+358h]
0x180025a0b  lea     r9d, [rdx-20h]
0x180025a0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a14  test    eax, eax
0x180025a16  js      short loc_180025A2C
0x180025a18  bts     dword ptr [r14], 9
0x180025a1d  jmp     short loc_180025A2C
0x180025a1f  mov     dword ptr [rdi+34h], 80004001h
0x180025a26  mov     dword ptr [rbx], 80004001h
0x180025a2c  test    r13, r13
0x180025a2f  jz      loc_180025AC8
0x180025a35  test    dword ptr [r13+0], 200000h
0x180025a3d  jz      loc_180025AC8
0x180025a43  mov     ebx, 358h
0x180025a48  lea     rcx, [rbp+340h+var_3A0]; void *
0x180025a4c  mov     r8d, ebx; Size
0x180025a4f  xor     edx, edx; Val
0x180025a51  call    memset_0
0x180025a56  mov     rax, [rsi]
0x180025a59  lea     rcx, [rsp+440h+hObject]
0x180025a5e  mov     r8, [r13+8]
0x180025a62  lea     r9, [rbp+340h+var_3A0]
0x180025a66  mov     [rsp+440h+var_418], rcx
0x180025a6b  mov     rdx, r12
0x180025a6e  mov     rcx, rsi
0x180025a71  mov     dword ptr [rsp+440h+hObject], 0
0x180025a79  mov     rax, [rax+0E8h]
0x180025a80  mov     dword ptr [rsp+440h+var_420], ebx
0x180025a84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a89  test    eax, eax
0x180025a8b  jnz     short loc_180025AC2
0x180025a8d  cmp     dword ptr [rsp+440h+hObject], ebx
0x180025a91  jnz     short loc_180025AC2
0x180025a93  test    byte ptr [rbp+340h+var_3A0.EnabledFeatures], 0E4h
0x180025a97  jnz     short loc_180025AA6
0x180025a99  test    [rbp+340h+var_3A0.EnabledUserVisibleSupervisorFeatures], 800h
0x180025aa4  jz      short loc_180025AC8
0x180025aa6  lea     rdx, [rdi+340h]; struct _XSTATE_CONFIG_FEATURE_MSC_INFO *
0x180025aad  lea     rcx, [rbp+340h+var_3A0]; struct _XSTATE_CONFIGURATION *
0x180025ab1  call    ?CopyXStateConfigToMiscInfo@@YAXPEAU_XSTATE_CONFIGURATION@@PEAU_XSTATE_CONFIG_FEATURE_MSC_INFO@@K@Z; CopyXStateConfigToMiscInfo(_XSTATE_CONFIGURATION *,_XSTATE_CONFIG_FEATURE_MSC_INFO *,ulong)
0x180025ab6  mov     eax, [r13+10h]
0x180025aba  mov     [rdi+344h], eax
0x180025ac0  jmp     short loc_180025AC8
0x180025ac2  mov     r15d, 800700EAh
0x180025ac8  mov     eax, r15d
0x180025acb  mov     rcx, [rbp+340h+var_40]
0x180025ad2  xor     rcx, rsp; StackCookie
0x180025ad5  call    __security_check_cookie
0x180025ada  mov     rbx, [rsp+440h+arg_10]
0x180025ae2  add     rsp, 410h
0x180025ae9  pop     r15
0x180025aeb  pop     r14
0x180025aed  pop     r13
0x180025aef  pop     r12
0x180025af1  pop     rdi
0x180025af2  pop     rsi
0x180025af3  pop     rbp
0x180025af4  retn
```
