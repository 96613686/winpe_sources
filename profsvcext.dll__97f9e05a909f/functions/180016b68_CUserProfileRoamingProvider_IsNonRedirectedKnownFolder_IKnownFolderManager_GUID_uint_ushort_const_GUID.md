# CUserProfileRoamingProvider::_IsNonRedirectedKnownFolder(IKnownFolderManager *,_GUID *,uint,ushort const *,_GUID *)

- ea: `0x180016b68`
- end: `0x180016def`
- name: `?_IsNonRedirectedKnownFolder@CUserProfileRoamingProvider@@AEAA_NPEAUIKnownFolderManager@@PEAU_GUID@@IPEBG1@Z`
- size: `647`
- prototype: `char __fastcall(CUserProfileRoamingProvider *this, struct IKnownFolderManager *, struct _GUID *, unsigned int, unsigned __int16 *, struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180007bd0`

## callees

- `0x18000a520`
- `0x18000aef8`
- `0x18001134c`
- `0x180011498`
- `0x180015534`
- `0x180016b68`
- `0x18001e574`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016d55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016d5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016d69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016d73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016d7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016d87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016d91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016d9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016d55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016d5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016d69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016d73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016d7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016d87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016d91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016d9b`
- `SHELL32!SHGetKnownFolderPath` at `0x180016ccb`
- `SHELL32!SHGetKnownFolderPath` at `0x180016d13`
- `SHELL32!SHGetKnownFolderPath` at `0x180016ccb`
- `SHELL32!SHGetKnownFolderPath` at `0x180016d13`

## pseudocode

```c
char __fastcall CUserProfileRoamingProvider::_IsNonRedirectedKnownFolder(
        CUserProfileRoamingProvider *this,
        struct IKnownFolderManager *a2,
        struct _GUID *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        struct _GUID *a6)
{
  struct _GUID *v6; // rsi
  char v8; // r15
  char v9; // dl
  __int64 v10; // rcx
  int v11; // ebx
  HRESULT (__stdcall *GetFolder)(IKnownFolderManager *, const KNOWNFOLDERID *const, IKnownFolder **); // r14
  const KNOWNFOLDERID *v13; // rsi
  CUserProfileRoamingProvider *v14; // r14
  void *v15; // rax
  void *v16; // rax
  char v18; // [rsp+20h] [rbp-A9h]
  __int64 v19; // [rsp+28h] [rbp-A1h] BYREF
  PWSTR ppszPath; // [rsp+30h] [rbp-99h] BYREF
  unsigned int v21; // [rsp+38h] [rbp-91h]
  PWSTR v22; // [rsp+40h] [rbp-89h] BYREF
  CUserProfileRoamingProvider *v23; // [rsp+48h] [rbp-81h]
  struct _GUID *v24; // [rsp+50h] [rbp-79h]
  int v25; // [rsp+60h] [rbp-69h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-61h]
  LPVOID v27; // [rsp+70h] [rbp-59h]
  _BYTE Buf1[16]; // [rsp+78h] [rbp-51h] BYREF
  LPVOID v29; // [rsp+88h] [rbp-41h]
  LPVOID v30; // [rsp+90h] [rbp-39h]
  LPVOID v31; // [rsp+98h] [rbp-31h]
  LPVOID v32; // [rsp+A0h] [rbp-29h]
  LPVOID v33; // [rsp+A8h] [rbp-21h]
  LPVOID v34; // [rsp+B0h] [rbp-19h]

  v21 = a4;
  v6 = a3;
  v24 = a3;
  v23 = this;
  v8 = 0;
  if ( a2 && a3 && a5 && *a5 && a6 )
  {
    v9 = 0;
    v18 = 0;
    v10 = 0;
    v19 = 0;
    v11 = 0;
    if ( a4 )
    {
      while ( !v9 )
      {
        GetFolder = a2->lpVtbl->GetFolder;
        v19 = 0;
        if ( v10 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        v13 = &v6[v11];
        if ( ((int (__fastcall *)(struct IKnownFolderManager *, const KNOWNFOLDERID *, __int64 *))GetFolder)(
               a2,
               v13,
               &v19) >= 0 )
        {
          memset_0(&v25, 0, 0x70u);
          if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v19 + 88LL))(v19, &v25) >= 0 )
          {
            if ( v25 == 4 && !memcmp_0(Buf1, &FOLDERID_Profile, 0x10u) )
            {
              ppszPath = 0;
              v14 = v23;
              v15 = (void *)(***((__int64 (__fastcall ****)(_QWORD))v23 + 1))(*((_QWORD *)v23 + 1));
              if ( SHGetKnownFolderPath(v13, 0x4600u, v15, &ppszPath) >= 0 && StringIsEqual(ppszPath, a5) )
              {
                v18 = 1;
                v22 = 0;
                v16 = (void *)(***((__int64 (__fastcall ****)(_QWORD))v14 + 1))(*((_QWORD *)v14 + 1));
                if ( SHGetKnownFolderPath(v13, 0x4000u, v16, &v22) >= 0 && StringIsEqual(ppszPath, v22) )
                {
                  v8 = 1;
                  *a6 = *v13;
                }
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v22);
              }
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&ppszPath);
            }
            CoTaskMemFree(pv);
            CoTaskMemFree(v27);
            CoTaskMemFree(v29);
            CoTaskMemFree(v30);
            CoTaskMemFree(v31);
            CoTaskMemFree(v32);
            CoTaskMemFree(v33);
            CoTaskMemFree(v34);
          }
        }
        if ( ++v11 >= v21 )
          break;
        v10 = v19;
        v9 = v18;
        v6 = v24;
      }
    }
    wil::com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>::~com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>(&v19);
  }
  return v8;
}

```

## disassembly

```asm
0x180016b68  mov     [rsp-8+arg_18], rbx
0x180016b6d  push    rbp
0x180016b6e  push    rsi
0x180016b6f  push    rdi
0x180016b70  push    r12
0x180016b72  push    r13
0x180016b74  push    r14
0x180016b76  push    r15
0x180016b78  lea     rbp, [rsp-17h]
0x180016b7d  sub     rsp, 0E0h
0x180016b84  mov     rax, cs:__security_cookie
0x180016b8b  xor     rax, rsp
0x180016b8e  mov     [rbp+47h+var_40], rax
0x180016b92  mov     eax, r9d
0x180016b95  mov     [rsp+110h+var_D8], eax
0x180016b99  mov     rsi, r8
0x180016b9c  mov     [rbp+47h+var_C0], r8
0x180016ba0  mov     r12, rdx
0x180016ba3  mov     [rsp+110h+var_C8], rcx
0x180016ba8  mov     rdi, [rbp+47h+arg_20]
0x180016bac  mov     r13, [rbp+47h+arg_28]
0x180016bb0  xor     r14d, r14d
0x180016bb3  mov     r15b, r14b
0x180016bb6  test    rdx, rdx
0x180016bb9  jz      loc_180016DC5
0x180016bbf  test    r8, r8
0x180016bc2  jz      loc_180016DC5
0x180016bc8  test    rdi, rdi
0x180016bcb  jz      loc_180016DC5
0x180016bd1  cmp     [rdi], r14w
0x180016bd5  jz      loc_180016DC5
0x180016bdb  test    r13, r13
0x180016bde  jz      loc_180016DC5
0x180016be4  mov     dl, r14b
0x180016be7  mov     [rsp+110h+var_F0], dl
0x180016beb  mov     ecx, r14d
0x180016bee  mov     [rsp+110h+var_E8], rcx
0x180016bf3  mov     ebx, r14d
0x180016bf6  test    eax, eax
0x180016bf8  jz      loc_180016DBB
0x180016bfe  test    dl, dl
0x180016c00  jnz     loc_180016DBB
0x180016c06  mov     rax, [r12]
0x180016c0a  mov     r14, [rax+30h]
0x180016c0e  mov     [rsp+110h+var_E8], 0
0x180016c17  test    rcx, rcx
0x180016c1a  jz      short loc_180016C29
0x180016c1c  mov     rax, [rcx]
0x180016c1f  mov     rax, [rax+10h]
0x180016c23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c28  nop
0x180016c29  mov     eax, ebx
0x180016c2b  shl     rax, 4
0x180016c2f  add     rsi, rax
0x180016c32  lea     r8, [rsp+110h+var_E8]
0x180016c37  mov     rdx, rsi
0x180016c3a  mov     rcx, r12
0x180016c3d  mov     rax, r14
0x180016c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c45  xor     r14d, r14d
0x180016c48  test    eax, eax
0x180016c4a  js      loc_180016DA1
0x180016c50  xor     edx, edx; Val
0x180016c52  lea     r8d, [r14+70h]; Size
0x180016c56  lea     rcx, [rbp+47h+var_B0]; void *
0x180016c5a  call    memset_0
0x180016c5f  mov     rcx, [rsp+110h+var_E8]
0x180016c64  mov     rax, [rcx]
0x180016c67  lea     rdx, [rbp+47h+var_B0]
0x180016c6b  mov     rax, [rax+58h]
0x180016c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c74  test    eax, eax
0x180016c76  js      loc_180016DA1
0x180016c7c  cmp     [rbp+47h+var_B0], 4
0x180016c80  jnz     loc_180016D51
0x180016c86  lea     r8d, [r14+10h]; Size
0x180016c8a  lea     rdx, FOLDERID_Profile; Buf2
0x180016c91  lea     rcx, [rbp+47h+Buf1]; Buf1
0x180016c95  call    memcmp_0
0x180016c9a  test    eax, eax
0x180016c9c  jnz     loc_180016D51
0x180016ca2  mov     [rsp+110h+ppszPath], r14
0x180016ca7  mov     r14, [rsp+110h+var_C8]
0x180016cac  mov     rcx, [r14+8]
0x180016cb0  mov     rax, [rcx]
0x180016cb3  mov     rax, [rax]
0x180016cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cbb  lea     r9, [rsp+110h+ppszPath]; ppszPath
0x180016cc0  mov     r8, rax; hToken
0x180016cc3  mov     edx, 4600h; dwFlags
0x180016cc8  mov     rcx, rsi; rfid
0x180016ccb  call    cs:__imp_SHGetKnownFolderPath
0x180016cd1  test    eax, eax
0x180016cd3  js      short loc_180016D47
0x180016cd5  mov     rdx, rdi; unsigned __int16 *
0x180016cd8  mov     rcx, [rsp+110h+ppszPath]; unsigned __int16 *
0x180016cdd  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x180016ce2  test    eax, eax
0x180016ce4  jz      short loc_180016D47
0x180016ce6  mov     [rsp+110h+var_F0], 1
0x180016ceb  mov     [rsp+110h+var_D0], 0
0x180016cf4  mov     rcx, [r14+8]
0x180016cf8  mov     rax, [rcx]
0x180016cfb  mov     rax, [rax]
0x180016cfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d03  lea     r9, [rsp+110h+var_D0]; ppszPath
0x180016d08  mov     r8, rax; hToken
0x180016d0b  mov     edx, 4000h; dwFlags
0x180016d10  mov     rcx, rsi; rfid
0x180016d13  call    cs:__imp_SHGetKnownFolderPath
0x180016d19  test    eax, eax
0x180016d1b  js      short loc_180016D3C
0x180016d1d  mov     rdx, [rsp+110h+var_D0]; unsigned __int16 *
0x180016d22  mov     rcx, [rsp+110h+ppszPath]; unsigned __int16 *
0x180016d27  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x180016d2c  test    eax, eax
0x180016d2e  jz      short loc_180016D3C
0x180016d30  mov     r15b, 1
0x180016d33  movups  xmm0, xmmword ptr [rsi]
0x180016d36  movdqu  xmmword ptr [r13+0], xmm0
0x180016d3c  lea     rcx, [rsp+110h+var_D0]
0x180016d41  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180016d46  nop
0x180016d47  lea     rcx, [rsp+110h+ppszPath]
0x180016d4c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180016d51  mov     rcx, [rbp+47h+pv]; pv
0x180016d55  call    cs:__imp_CoTaskMemFree
0x180016d5b  mov     rcx, [rbp+47h+var_A0]; pv
0x180016d5f  call    cs:__imp_CoTaskMemFree
0x180016d65  mov     rcx, [rbp+47h+var_88]; pv
0x180016d69  call    cs:__imp_CoTaskMemFree
0x180016d6f  mov     rcx, [rbp+47h+var_80]; pv
0x180016d73  call    cs:__imp_CoTaskMemFree
0x180016d79  mov     rcx, [rbp+47h+var_78]; pv
0x180016d7d  call    cs:__imp_CoTaskMemFree
0x180016d83  mov     rcx, [rbp+47h+var_70]; pv
0x180016d87  call    cs:__imp_CoTaskMemFree
0x180016d8d  mov     rcx, [rbp+47h+var_68]; pv
0x180016d91  call    cs:__imp_CoTaskMemFree
0x180016d97  mov     rcx, [rbp+47h+var_60]; pv
0x180016d9b  call    cs:__imp_CoTaskMemFree
0x180016da1  inc     ebx
0x180016da3  cmp     ebx, [rsp+110h+var_D8]
0x180016da7  jnb     short loc_180016DBB
0x180016da9  mov     rcx, [rsp+110h+var_E8]
0x180016dae  mov     dl, [rsp+110h+var_F0]
0x180016db2  mov     rsi, [rbp+47h+var_C0]
0x180016db6  jmp     loc_180016BFE
0x180016dbb  lea     rcx, [rsp+110h+var_E8]
0x180016dc0  call    ??1?$com_ptr_t@UIOfflineFilesCache@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>::~com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>(void)
0x180016dc5  mov     al, r15b
0x180016dc8  mov     rcx, [rbp+47h+var_40]
0x180016dcc  xor     rcx, rsp; StackCookie
0x180016dcf  call    __security_check_cookie
0x180016dd4  mov     rbx, [rsp+110h+arg_18]
0x180016ddc  add     rsp, 0E0h
0x180016de3  pop     r15
0x180016de5  pop     r14
0x180016de7  pop     r13
0x180016de9  pop     r12
0x180016deb  pop     rdi
0x180016dec  pop     rsi
0x180016ded  pop     rbp
0x180016dee  retn
```
