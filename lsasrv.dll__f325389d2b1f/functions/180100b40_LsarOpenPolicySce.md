# LsarOpenPolicySce

- ea: `0x180100b40`
- end: `0x180100e2b`
- name: `LsarOpenPolicySce`
- size: `747`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting`

## callees

- `0x180020920`
- `0x180020948`
- `0x1800ada18`
- `0x1800b86d0`
- `0x180100b40`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180100c80`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180100c80`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180100cf2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180100cf2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180100ca3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180100ca3`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180100d3e`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180100d3e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180100d92`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180100de5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180100d92`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180100de5`
- `ntdll!NtPrivilegeCheck` at `0x180100c06`
- `ntdll!NtPrivilegeCheck` at `0x180100c06`
- `ntdll!RtlAcquireResourceExclusive` at `0x180100d53`
- `ntdll!RtlAcquireResourceExclusive` at `0x180100d53`
- `ntdll!RtlReleaseResource` at `0x180100d7f`
- `ntdll!RtlReleaseResource` at `0x180100dd2`
- `ntdll!RtlReleaseResource` at `0x180100d7f`
- `ntdll!RtlReleaseResource` at `0x180100dd2`
- `ntdll!NtClose` at `0x180100c28`
- `ntdll!NtClose` at `0x180100e05`
- `ntdll!NtClose` at `0x180100c28`
- `ntdll!NtClose` at `0x180100e05`
- `ntdll!NtOpenThreadToken` at `0x180100bc7`
- `ntdll!NtOpenThreadToken` at `0x180100bc7`
- `RPCRT4!RpcRevertToSelf` at `0x180100c3c`
- `RPCRT4!RpcRevertToSelf` at `0x180100c3c`
- `RPCRT4!I_RpcMapWin32Status` at `0x180100b9e`
- `RPCRT4!I_RpcMapWin32Status` at `0x180100c4a`
- `RPCRT4!I_RpcMapWin32Status` at `0x180100b9e`
- `RPCRT4!I_RpcMapWin32Status` at `0x180100c4a`
- `RPCRT4!RpcImpersonateClient` at `0x180100b90`
- `RPCRT4!RpcImpersonateClient` at `0x180100b90`

## string_xrefs

- `0x180100ce8`: `SceOpenPolicy`

## pseudocode

```c
__int64 __fastcall LsarOpenPolicySce(__int64 a1, struct _OBJECT_ATTRIBUTES *a2, unsigned int a3, void **a4)
{
  RPC_STATUS v7; // eax
  int v8; // ebx
  RPC_STATUS v9; // eax
  int v10; // eax
  HMODULE Library; // rax
  int v12; // eax
  unsigned __int16 *v13; // rcx
  unsigned __int8 Result[8]; // [rsp+30h] [rbp-40h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-38h] BYREF
  struct _OBJECT_ATTRIBUTES v17; // [rsp+40h] [rbp-30h] BYREF

  TokenHandle = 0;
  if ( !LsapValidateObjectAttributes(a2) || !LsapValidateObjectAttributes(&v17) )
  {
    v8 = -1073741811;
    goto LABEL_30;
  }
  v7 = RpcImpersonateClient(0);
  v8 = I_RpcMapWin32Status(v7);
  if ( v8 >= 0 )
  {
    v8 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
    if ( v8 >= 0 )
    {
      Result[0] = 0;
      v17.RootDirectory = HANDLE_FLAG_INHERIT;
      v17.ObjectName = (PUNICODE_STRING)7;
      v17.Attributes = 0;
      v8 = NtPrivilegeCheck(TokenHandle, (PPRIVILEGE_SET)&v17.RootDirectory, Result);
      if ( v8 >= 0 && !Result[0] )
        v8 = -1073741727;
      NtClose(TokenHandle);
      TokenHandle = 0;
    }
    v9 = RpcRevertToSelf();
    v10 = I_RpcMapWin32Status(v9);
    if ( v8 >= 0 )
    {
      if ( v10 < 0 )
      {
        v8 = v10;
        goto LABEL_30;
      }
      if ( qword_1801A0D60 )
        goto LABEL_22;
      if ( hLibModule )
      {
        FreeLibrary(hLibModule);
        hLibModule = 0;
      }
      Library = LoadLibraryExW(L"SCECLI", 0, 0);
      hLibModule = Library;
      if ( !Library )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x100) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 22, &WPP_a5273d544b883828eaa2592a0f0a6148_Traceguids);
        v8 = -1073741515;
        goto LABEL_30;
      }
      qword_1801A0D60 = (__int64)GetProcAddress(Library, "SceOpenPolicy");
      if ( qword_1801A0D60 )
      {
LABEL_22:
        ResetEvent(hHandle);
        RtlAcquireResourceExclusive((PRTL_RESOURCE)&stru_18019F2D8, 1u);
        v12 = ((__int64 (*)(void))qword_1801A0D60)();
        v8 = v12;
        if ( v12 >= 0 && v12 != 258
          || (RtlReleaseResource((PRTL_RESOURCE)&stru_18019F2D8), SetEvent(hHandle), v8 >= 0) && v8 != 258 )
        {
          v8 = LsapDbOpenPolicy(v13, (struct _LSAPR_OBJECT_ATTRIBUTES *)a2, a3, 0x40000000u, a4, 0);
          if ( v8 < 0 )
          {
            RtlReleaseResource((PRTL_RESOURCE)&stru_18019F2D8);
            SetEvent(hHandle);
          }
        }
      }
      else
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x100) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 23, &WPP_a5273d544b883828eaa2592a0f0a6148_Traceguids);
        v8 = -1073741511;
      }
    }
  }
LABEL_30:
  if ( TokenHandle )
    NtClose(TokenHandle);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180100b40  push    rbp
0x180100b42  push    rbx
0x180100b43  push    rsi
0x180100b44  push    rdi
0x180100b45  push    r14
0x180100b47  mov     rbp, rsp
0x180100b4a  sub     rsp, 70h
0x180100b4e  mov     rax, cs:__security_cookie
0x180100b55  xor     rax, rsp
0x180100b58  mov     [rbp+var_30.SecurityDescriptor], rax
0x180100b5c  mov     rcx, rdx; struct _OBJECT_ATTRIBUTES *
0x180100b5f  mov     [rbp+TokenHandle], 0
0x180100b67  mov     r14, r9
0x180100b6a  mov     esi, r8d
0x180100b6d  mov     rdi, rdx
0x180100b70  call    ?LsapValidateObjectAttributes@@YAEPEAU_OBJECT_ATTRIBUTES@@@Z; LsapValidateObjectAttributes(_OBJECT_ATTRIBUTES *)
0x180100b75  test    al, al
0x180100b77  jz      loc_180100DF7
0x180100b7d  lea     rcx, [rbp+var_30]; struct _OBJECT_ATTRIBUTES *
0x180100b81  call    ?LsapValidateObjectAttributes@@YAEPEAU_OBJECT_ATTRIBUTES@@@Z; LsapValidateObjectAttributes(_OBJECT_ATTRIBUTES *)
0x180100b86  test    al, al
0x180100b88  jz      loc_180100DF7
0x180100b8e  xor     ecx, ecx; BindingHandle
0x180100b90  call    cs:__imp_RpcImpersonateClient
0x180100b97  nop     dword ptr [rax+rax+00h]
0x180100b9c  mov     ecx, eax; Status
0x180100b9e  call    cs:__imp_I_RpcMapWin32Status
0x180100ba5  nop     dword ptr [rax+rax+00h]
0x180100baa  mov     ebx, eax
0x180100bac  test    eax, eax
0x180100bae  js      loc_180100DFC
0x180100bb4  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180100bb8  mov     r8b, 1; OpenAsSelf
0x180100bbb  mov     edx, 8; DesiredAccess
0x180100bc0  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180100bc7  call    cs:__imp_NtOpenThreadToken
0x180100bce  nop     dword ptr [rax+rax+00h]
0x180100bd3  mov     ebx, eax
0x180100bd5  test    eax, eax
0x180100bd7  js      short loc_180100C3C
0x180100bd9  mov     rcx, [rbp+TokenHandle]; ClientToken
0x180100bdd  lea     r8, [rbp+Result]; Result
0x180100be1  lea     rdx, [rbp+var_30.RootDirectory]; RequiredPrivileges
0x180100be5  mov     [rbp+Result], 0
0x180100be9  mov     dword ptr [rbp+var_30.RootDirectory], 1
0x180100bf0  mov     dword ptr [rbp+var_30.RootDirectory+4], 1
0x180100bf7  mov     [rbp+var_30.ObjectName], 7
0x180100bff  mov     [rbp+var_30.Attributes], 0
0x180100c06  call    cs:__imp_NtPrivilegeCheck
0x180100c0d  nop     dword ptr [rax+rax+00h]
0x180100c12  mov     ebx, eax
0x180100c14  test    eax, eax
0x180100c16  js      short loc_180100C24
0x180100c18  cmp     [rbp+Result], 0
0x180100c1c  mov     eax, 0C0000061h
0x180100c21  cmovz   ebx, eax
0x180100c24  mov     rcx, [rbp+TokenHandle]; Handle
0x180100c28  call    cs:__imp_NtClose
0x180100c2f  nop     dword ptr [rax+rax+00h]
0x180100c34  mov     [rbp+TokenHandle], 0
0x180100c3c  call    cs:__imp_RpcRevertToSelf
0x180100c43  nop     dword ptr [rax+rax+00h]
0x180100c48  mov     ecx, eax; Status
0x180100c4a  call    cs:__imp_I_RpcMapWin32Status
0x180100c51  nop     dword ptr [rax+rax+00h]
0x180100c56  test    ebx, ebx
0x180100c58  js      loc_180100DFC
0x180100c5e  test    eax, eax
0x180100c60  js      loc_180100DF3
0x180100c66  cmp     cs:qword_1801A0D60, 0
0x180100c6e  jnz     loc_180100D37
0x180100c74  mov     rcx, cs:hLibModule; hLibModule
0x180100c7b  test    rcx, rcx
0x180100c7e  jz      short loc_180100C97
0x180100c80  call    cs:__imp_FreeLibrary
0x180100c87  nop     dword ptr [rax+rax+00h]
0x180100c8c  mov     cs:hLibModule, 0
0x180100c97  xor     r8d, r8d; dwFlags
0x180100c9a  lea     rcx, aScecli_0; "SCECLI"
0x180100ca1  xor     edx, edx; hFile
0x180100ca3  call    cs:__imp_LoadLibraryExW
0x180100caa  nop     dword ptr [rax+rax+00h]
0x180100caf  mov     cs:hLibModule, rax
0x180100cb6  test    rax, rax
0x180100cb9  jnz     short loc_180100CE8
0x180100cbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180100cc2  test    dword ptr [rcx+6Ch], 100h
0x180100cc9  jz      short loc_180100CDE
0x180100ccb  mov     rcx, [rcx+60h]
0x180100ccf  lea     edx, [rax+16h]
0x180100cd2  lea     r8, WPP_a5273d544b883828eaa2592a0f0a6148_Traceguids
0x180100cd9  call    WPP_SF_
0x180100cde  mov     ebx, 0C0000135h
0x180100ce3  jmp     loc_180100DFC
0x180100ce8  lea     rdx, aSceopenpolicy; "SceOpenPolicy"
0x180100cef  mov     rcx, rax; hModule
0x180100cf2  call    cs:__imp_GetProcAddress
0x180100cf9  nop     dword ptr [rax+rax+00h]
0x180100cfe  mov     cs:qword_1801A0D60, rax
0x180100d05  test    rax, rax
0x180100d08  jnz     short loc_180100D37
0x180100d0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180100d11  test    dword ptr [rcx+6Ch], 100h
0x180100d18  jz      short loc_180100D2D
0x180100d1a  mov     rcx, [rcx+60h]
0x180100d1e  lea     edx, [rax+17h]
0x180100d21  lea     r8, WPP_a5273d544b883828eaa2592a0f0a6148_Traceguids
0x180100d28  call    WPP_SF_
0x180100d2d  mov     ebx, 0C0000139h
0x180100d32  jmp     loc_180100DFC
0x180100d37  mov     rcx, cs:hHandle; hEvent
0x180100d3e  call    cs:__imp_ResetEvent
0x180100d45  nop     dword ptr [rax+rax+00h]
0x180100d4a  mov     dl, 1; Wait
0x180100d4c  lea     rcx, stru_18019F2D8; Resource
0x180100d53  call    cs:__imp_RtlAcquireResourceExclusive
0x180100d5a  nop     dword ptr [rax+rax+00h]
0x180100d5f  mov     rax, cs:qword_1801A0D60
0x180100d66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100d6b  mov     ebx, eax
0x180100d6d  test    eax, eax
0x180100d6f  js      short loc_180100D78
0x180100d71  cmp     eax, 102h
0x180100d76  jnz     short loc_180100DAA
0x180100d78  lea     rcx, stru_18019F2D8; Resource
0x180100d7f  call    cs:__imp_RtlReleaseResource
0x180100d86  nop     dword ptr [rax+rax+00h]
0x180100d8b  mov     rcx, cs:hHandle; hEvent
0x180100d92  call    cs:__imp_SetEvent
0x180100d99  nop     dword ptr [rax+rax+00h]
0x180100d9e  test    ebx, ebx
0x180100da0  js      short loc_180100DFC
0x180100da2  cmp     ebx, 102h
0x180100da8  jz      short loc_180100DFC
0x180100daa  mov     [rsp+70h+var_48], 0; unsigned __int8
0x180100daf  mov     r9d, 40000000h; unsigned int
0x180100db5  mov     r8d, esi; unsigned int
0x180100db8  mov     [rsp+70h+var_50], r14; void **
0x180100dbd  mov     rdx, rdi; struct _LSAPR_OBJECT_ATTRIBUTES *
0x180100dc0  call    ?LsapDbOpenPolicy@@YAJPEAGPEAU_LSAPR_OBJECT_ATTRIBUTES@@KKPEAPEAXE@Z; LsapDbOpenPolicy(ushort *,_LSAPR_OBJECT_ATTRIBUTES *,ulong,ulong,void * *,uchar)
0x180100dc5  mov     ebx, eax
0x180100dc7  test    eax, eax
0x180100dc9  jns     short loc_180100DFC
0x180100dcb  lea     rcx, stru_18019F2D8; Resource
0x180100dd2  call    cs:__imp_RtlReleaseResource
0x180100dd9  nop     dword ptr [rax+rax+00h]
0x180100dde  mov     rcx, cs:hHandle; hEvent
0x180100de5  call    cs:__imp_SetEvent
0x180100dec  nop     dword ptr [rax+rax+00h]
0x180100df1  jmp     short loc_180100DFC
0x180100df3  mov     ebx, eax
0x180100df5  jmp     short loc_180100DFC
0x180100df7  mov     ebx, 0C000000Dh
0x180100dfc  mov     rcx, [rbp+TokenHandle]; Handle
0x180100e00  test    rcx, rcx
0x180100e03  jz      short loc_180100E11
0x180100e05  call    cs:__imp_NtClose
0x180100e0c  nop     dword ptr [rax+rax+00h]
0x180100e11  mov     eax, ebx
0x180100e13  mov     rcx, [rbp+var_30.SecurityDescriptor]
0x180100e17  xor     rcx, rsp; StackCookie
0x180100e1a  call    __security_check_cookie
0x180100e1f  add     rsp, 70h
0x180100e23  pop     r14
0x180100e25  pop     rdi
0x180100e26  pop     rsi
0x180100e27  pop     rbx
0x180100e28  pop     rbp
0x180100e29  retn
```
