# COOBEExpeditedUpdateUSOCallback::UpdateProgressUpdated(IMoUsoUpdate *,tagMoUpdateState)

- ea: `0x18007b220`
- end: `0x18007b44e`
- name: `?UpdateProgressUpdated@COOBEExpeditedUpdateUSOCallback@@UEAAJPEAUIMoUsoUpdate@@UtagMoUpdateState@@@Z`
- size: `558`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18007b460`

## callees

- `0x180008544`
- `0x18001d004`
- `0x18002f39c`
- `0x18007b220`
- `0x1800b8834`
- `0x1800bd978`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007b311`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007b311`

## string_xrefs

- `0x18007b340`: `DownloadInstallProgress`
- `0x18007b3fa`: `ExpeditedUpdateStatus`
- `0x18007b3bd`: `UpdateId`
- `0x18007b264`: `shell\oobe\machine\plugins\adapters\inc\expeditedupdateusocallbacks.h`
- `0x18007b2a2`: `shell\oobe\machine\plugins\adapters\inc\expeditedupdateusocallbacks.h`
- `0x18007b35a`: `shell\oobe\machine\plugins\adapters\inc\expeditedupdateusocallbacks.h`
- `0x18007b2da`: `ExpeditedUpdateTask USO progress update - Title: [%s], Action: [%s], ActionClass: [%d], Progress: [%d]`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall COOBEExpeditedUpdateUSOCallback::UpdateProgressUpdated(__int64 a1, __int64 a2, __int64 a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  int v9; // r15d
  int v10; // ebx
  int v11; // ebx
  int v12; // esi
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v19; // [rsp+20h] [rbp-30h]
  int v20; // [rsp+20h] [rbp-30h]
  __int64 v21; // [rsp+30h] [rbp-20h] BYREF
  __int128 v22; // [rsp+38h] [rbp-18h] BYREF
  __int64 v23; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  __int64 v25; // [rsp+88h] [rbp+38h] BYREF
  __int64 v26; // [rsp+98h] [rbp+48h] BYREF

  v21 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 24LL))(a2, &v21);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v25 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 112LL))(a2, &v25);
    v7 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4F,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\inc\\expeditedupdateusocallbacks.h",
        (const char *)(unsigned int)v8,
        v19);
LABEL_5:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v25);
      goto LABEL_23;
    }
    v9 = *(_DWORD *)(a3 + 16);
    v10 = *(_DWORD *)(a3 + 8);
    v20 = v10;
    UnattendLogW(
      0,
      L"ExpeditedUpdateTask USO progress update - Title: [%s], Action: [%s], ActionClass: [%d], Progress: [%d]",
      v21,
      *(_QWORD *)a3);
    if ( !*(_BYTE *)(a1 + 88) )
      *(_BYTE *)(a1 + 88) = 1;
    v11 = v10 - 1;
    if ( v11 )
    {
      if ( v11 != 1 )
        goto LABEL_22;
      v12 = 11;
    }
    else
    {
      v12 = 7;
    }
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 40));
    v26 = a1 + 40;
    v13 = *(_QWORD *)(a1 + 48);
    v22 = 0;
    v23 = 0;
    LOWORD(v22) = 19;
    DWORD2(v22) = v9;
    v14 = (*(__int64 (__fastcall **)(__int64, const WCHAR *, __int128 *))(*(_QWORD *)v13 + 32LL))(
            v13,
            L"DownloadInstallProgress",
            &v22);
    v7 = v14;
    if ( v14 < 0 )
    {
      v15 = 114;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\inc\\expeditedupdateusocallbacks.h",
        (const char *)(unsigned int)v14,
        v20);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v26);
      goto LABEL_5;
    }
    v16 = *(_QWORD *)(a1 + 48);
    v22 = 0;
    v23 = 0;
    LOWORD(v22) = 19;
    DWORD2(v22) = 0;
    v14 = (*(__int64 (__fastcall **)(__int64, const WCHAR *, __int128 *))(*(_QWORD *)v16 + 32LL))(
            v16,
            L"DownloadSubPhase",
            &v22);
    v7 = v14;
    if ( v14 < 0 )
    {
      v15 = 115;
      goto LABEL_14;
    }
    v14 = INamedPropertyStore_SetString(*(_QWORD *)(a1 + 48), L"UpdateId", v25);
    v7 = v14;
    if ( v14 < 0 )
    {
      v15 = 116;
      goto LABEL_14;
    }
    v17 = *(_QWORD *)(a1 + 48);
    v22 = 0;
    v23 = 0;
    LOWORD(v22) = 19;
    DWORD2(v22) = v12;
    v14 = (*(__int64 (__fastcall **)(__int64, const WCHAR *, __int128 *))(*(_QWORD *)v17 + 32LL))(
            v17,
            L"ExpeditedUpdateStatus",
            &v22);
    v7 = v14;
    if ( v14 < 0 )
    {
      v15 = 117;
      goto LABEL_14;
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v26);
LABEL_22:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v25);
    v7 = 0;
    goto LABEL_23;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4C,
    (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\inc\\expeditedupdateusocallbacks.h",
    (const char *)(unsigned int)v6,
    v19);
LABEL_23:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v21);
  return v7;
}

```

## disassembly

```asm
0x18007b220  mov     [rsp-28h+arg_0], rbx
0x18007b225  push    rbp
0x18007b226  push    rsi
0x18007b227  push    rdi
0x18007b228  push    r14
0x18007b22a  push    r15
0x18007b22c  mov     rbp, rsp
0x18007b22f  sub     rsp, 50h
0x18007b233  mov     r14, r8
0x18007b236  mov     rsi, rdx
0x18007b239  mov     rdi, rcx
0x18007b23c  mov     [rbp+var_20], 0
0x18007b244  mov     rax, [rdx]
0x18007b247  lea     rdx, [rbp+var_20]
0x18007b24b  mov     rcx, rsi
0x18007b24e  mov     rax, [rax+18h]
0x18007b252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b257  mov     ebx, eax
0x18007b259  test    eax, eax
0x18007b25b  jns     short loc_18007B27A
0x18007b25d  mov     rcx, [rbp+28h]; this
0x18007b261  mov     r9d, eax; char *
0x18007b264  lea     r8, aShellOobeMachi_23; "shell\\oobe\\machine\\plugins\\adapters"...
0x18007b26b  mov     edx, 4Ch ; 'L'; void *
0x18007b270  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b275  jmp     loc_18007B42F
0x18007b27a  mov     [rbp+arg_8], 0
0x18007b282  mov     rax, [rsi]
0x18007b285  lea     rdx, [rbp+arg_8]
0x18007b289  mov     rcx, rsi
0x18007b28c  mov     rax, [rax+70h]
0x18007b290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b295  mov     ebx, eax
0x18007b297  test    eax, eax
0x18007b299  jns     short loc_18007B2C2
0x18007b29b  mov     rcx, [rbp+28h]; this
0x18007b29f  mov     r9d, eax; char *
0x18007b2a2  lea     r8, aShellOobeMachi_23; "shell\\oobe\\machine\\plugins\\adapters"...
0x18007b2a9  mov     edx, 4Fh ; 'O'; void *
0x18007b2ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b2b3  nop
0x18007b2b4  lea     rcx, [rbp+arg_8]
0x18007b2b8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007b2bd  jmp     loc_18007B42F
0x18007b2c2  mov     r15d, [r14+10h]
0x18007b2c6  mov     ebx, [r14+8]
0x18007b2ca  mov     [rsp+50h+var_28], r15d
0x18007b2cf  mov     [rsp+50h+var_30], ebx; int
0x18007b2d3  mov     r9, [r14]
0x18007b2d6  mov     r8, [rbp+var_20]
0x18007b2da  lea     rdx, aExpeditedupdat_17; "ExpeditedUpdateTask USO progress update"...
0x18007b2e1  xor     ecx, ecx
0x18007b2e3  call    UnattendLogW
0x18007b2e8  cmp     byte ptr [rdi+58h], 0
0x18007b2ec  jnz     short loc_18007B2F2
0x18007b2ee  mov     byte ptr [rdi+58h], 1
0x18007b2f2  sub     ebx, 1
0x18007b2f5  jz      short loc_18007B305
0x18007b2f7  cmp     ebx, 1
0x18007b2fa  jnz     loc_18007B424
0x18007b300  lea     esi, [rbx+0Ah]
0x18007b303  jmp     short loc_18007B30A
0x18007b305  mov     esi, 7
0x18007b30a  lea     rbx, [rdi+28h]
0x18007b30e  mov     rcx, rbx; SRWLock
0x18007b311  call    cs:__imp_AcquireSRWLockExclusive
0x18007b317  mov     [rbp+arg_18], rbx
0x18007b31b  mov     rcx, [rdi+30h]
0x18007b31f  xorps   xmm0, xmm0
0x18007b322  xor     eax, eax
0x18007b324  movups  [rbp+var_18], xmm0
0x18007b328  mov     [rbp+var_8], rax
0x18007b32c  lea     r14d, [rax+13h]
0x18007b330  mov     word ptr [rbp+var_18], r14w
0x18007b335  mov     dword ptr [rbp+var_18+8], r15d
0x18007b339  mov     rax, [rcx]
0x18007b33c  lea     r8, [rbp+var_18]
0x18007b340  lea     rdx, aDownloadinstal; "DownloadInstallProgress"
0x18007b347  mov     rax, [rax+20h]
0x18007b34b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b350  mov     ebx, eax
0x18007b352  test    eax, eax
0x18007b354  jns     short loc_18007B37C
0x18007b356  lea     edx, [r14+5Fh]; void *
0x18007b35a  lea     r8, aShellOobeMachi_23; "shell\\oobe\\machine\\plugins\\adapters"...
0x18007b361  mov     r9d, eax; char *
0x18007b364  mov     rcx, [rbp+28h]; this
0x18007b368  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b36d  nop
0x18007b36e  lea     rcx, [rbp+arg_18]
0x18007b372  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18007b377  jmp     loc_18007B2B4
0x18007b37c  mov     rcx, [rdi+30h]
0x18007b380  xorps   xmm0, xmm0
0x18007b383  xor     eax, eax
0x18007b385  movups  [rbp+var_18], xmm0
0x18007b389  mov     [rbp+var_8], rax
0x18007b38d  mov     word ptr [rbp+var_18], r14w
0x18007b392  mov     dword ptr [rbp+var_18+8], eax
0x18007b395  mov     rax, [rcx]
0x18007b398  lea     r8, [rbp+var_18]
0x18007b39c  lea     rdx, aDownloadsubpha; "DownloadSubPhase"
0x18007b3a3  mov     rax, [rax+20h]
0x18007b3a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b3ac  mov     ebx, eax
0x18007b3ae  test    eax, eax
0x18007b3b0  jns     short loc_18007B3B9
0x18007b3b2  mov     edx, 73h ; 's'
0x18007b3b7  jmp     short loc_18007B35A
0x18007b3b9  mov     r8, [rbp+arg_8]
0x18007b3bd  lea     rdx, aUpdateid; "UpdateId"
0x18007b3c4  mov     rcx, [rdi+30h]
0x18007b3c8  call    INamedPropertyStore_SetString
0x18007b3cd  mov     ebx, eax
0x18007b3cf  test    eax, eax
0x18007b3d1  jns     short loc_18007B3DA
0x18007b3d3  mov     edx, 74h ; 't'
0x18007b3d8  jmp     short loc_18007B35A
0x18007b3da  mov     rcx, [rdi+30h]
0x18007b3de  xorps   xmm0, xmm0
0x18007b3e1  xor     eax, eax
0x18007b3e3  movups  [rbp+var_18], xmm0
0x18007b3e7  mov     [rbp+var_8], rax
0x18007b3eb  mov     word ptr [rbp+var_18], r14w
0x18007b3f0  mov     dword ptr [rbp+var_18+8], esi
0x18007b3f3  mov     rax, [rcx]
0x18007b3f6  lea     r8, [rbp+var_18]
0x18007b3fa  lea     rdx, aExpeditedupdat_15; "ExpeditedUpdateStatus"
0x18007b401  mov     rax, [rax+20h]
0x18007b405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b40a  mov     ebx, eax
0x18007b40c  test    eax, eax
0x18007b40e  jns     short loc_18007B41A
0x18007b410  mov     edx, 75h ; 'u'
0x18007b415  jmp     loc_18007B35A
0x18007b41a  lea     rcx, [rbp+arg_18]
0x18007b41e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18007b423  nop
0x18007b424  lea     rcx, [rbp+arg_8]
0x18007b428  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007b42d  xor     ebx, ebx
0x18007b42f  lea     rcx, [rbp+var_20]
0x18007b433  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007b438  mov     eax, ebx
0x18007b43a  mov     rbx, [rsp+50h+arg_0]
0x18007b442  add     rsp, 50h
0x18007b446  pop     r15
0x18007b448  pop     r14
0x18007b44a  pop     rdi
0x18007b44b  pop     rsi
0x18007b44c  pop     rbp
0x18007b44d  retn
```
