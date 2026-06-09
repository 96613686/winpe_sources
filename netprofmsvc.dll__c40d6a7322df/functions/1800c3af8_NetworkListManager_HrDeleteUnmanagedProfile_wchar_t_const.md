# NetworkListManager::HrDeleteUnmanagedProfile(wchar_t const *)

- ea: `0x1800c3af8`
- end: `0x1800c3d2e`
- name: `?HrDeleteUnmanagedProfile@NetworkListManager@@AEAAJPEB_W@Z`
- size: `566`
- prototype: `int(NetworkListManager *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a4e30`

## callees

- `0x18000fab0`
- `0x180010340`
- `0x180035810`
- `0x180037820`
- `0x180073420`
- `0x1800a88a0`
- `0x1800a9738`
- `0x1800c3af8`
- `0x1800cb1a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800c3b77`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800c3b77`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c3c4a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c3cb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c3c4a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c3cb9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800c3c9f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800c3c9f`

## pseudocode

```c
__int64 __fastcall NetworkListManager::HrDeleteUnmanagedProfile(NetworkListManager *this, const wchar_t *a2)
{
  HKEY v3; // rcx
  const wchar_t *v4; // rdx
  unsigned int v5; // ebx
  const wchar_t *v6; // rdx
  LSTATUS v7; // eax
  unsigned int v9; // [rsp+20h] [rbp-E0h] BYREF
  HKEY hKey; // [rsp+28h] [rbp-D8h] BYREF
  GUID iid; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int8 v12[48]; // [rsp+40h] [rbp-C0h] BYREF
  int v13; // [rsp+70h] [rbp-90h]
  __int64 v14; // [rsp+80h] [rbp-80h] BYREF
  int v15; // [rsp+88h] [rbp-78h]
  int v16; // [rsp+8Ch] [rbp-74h]
  GUID v17[4]; // [rsp+90h] [rbp-70h] BYREF
  int v18; // [rsp+D0h] [rbp-30h]

  hKey = 0;
  memset(v12, 0, sizeof(v12));
  v13 = 0;
  iid = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 140, &WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids);
  IIDFromString(a2, &iid);
  v15 = -1;
  v16 = 0;
  memset_0(v17, 0, 0x68u);
  v17[0] = iid;
  v14 = 1059;
  do
  {
    v4 = (const wchar_t *)&qword_1801C7160;
    if ( (unsigned __int64)qword_1801C7178 > 7 )
      v4 = qword_1801C7160;
    v5 = HrOpenKey(v3, v4, 0x2001Fu, &hKey);
    if ( v5 )
      break;
    v9 = 0;
    v5 = HrNextUnmanagedSignature(hKey, a2, &v9, (struct tagNLA_SIGNATURE *)v12);
    if ( !v5 )
    {
      v5 = HrDeleteSignature(hKey, (unsigned __int8 (*)[48])v12);
      if ( !v5 )
      {
        v18 = v13;
        v17[1] = *(GUID *)v12;
        v17[2] = *(GUID *)&v12[16];
        v17[3] = *(GUID *)&v12[32];
        NetworkListManager::PostEventToEventMgr((struct NP_EVENT_INFO *)&v14, 1);
      }
    }
    RegCloseKey(hKey);
  }
  while ( !v5 );
  if ( v5 == -2147024637 )
  {
    v6 = (const wchar_t *)&qword_1801C7140;
    if ( (unsigned __int64)qword_1801C7158 > 7 )
      v6 = qword_1801C7140;
    v5 = HrOpenKey(v3, v6, 0x2001Fu, &hKey);
    if ( !v5 )
    {
      v7 = RegDeleteKeyExW(hKey, a2, 0, 0);
      v5 = v7;
      if ( v7 > 0 )
        v5 = (unsigned __int16)v7 | 0x80070000;
      RegCloseKey(hKey);
      if ( !v5 )
      {
        v17[0] = iid;
        v14 = 1043;
        NetworkListManager::PostEventToEventMgr((struct NP_EVENT_INFO *)&v14, 1);
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 141, &WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x1800c3af8  push    rbp
0x1800c3afa  push    rbx
0x1800c3afb  push    rdi
0x1800c3afc  push    r14
0x1800c3afe  lea     rbp, [rsp-18h]
0x1800c3b03  sub     rsp, 118h
0x1800c3b0a  mov     rax, cs:__security_cookie
0x1800c3b11  xor     rax, rsp
0x1800c3b14  mov     [rbp+30h+var_30], rax
0x1800c3b18  xorps   xmm0, xmm0
0x1800c3b1b  mov     [rsp+130h+hKey], 0
0x1800c3b24  xor     eax, eax
0x1800c3b26  mov     rdi, rdx
0x1800c3b29  movups  xmmword ptr [rsp+130h+var_F0], xmm0
0x1800c3b2e  mov     [rsp+130h+var_C0], eax
0x1800c3b32  movups  xmmword ptr [rsp+130h+var_F0+10h], xmm0
0x1800c3b37  movups  xmmword ptr [rsp+130h+var_F0+20h], xmm0
0x1800c3b3c  movups  xmmword ptr [rsp+130h+iid.Data1], xmm0
0x1800c3b41  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3b48  lea     r14, WPP_GLOBAL_Control
0x1800c3b4f  cmp     rcx, r14
0x1800c3b52  jz      short loc_1800C3B6F
0x1800c3b54  test    byte ptr [rcx+1Ch], 8
0x1800c3b58  jz      short loc_1800C3B6F
0x1800c3b5a  mov     rcx, [rcx+10h]
0x1800c3b5e  lea     r8, WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids
0x1800c3b65  mov     edx, 8Ch
0x1800c3b6a  call    WPP_SF_
0x1800c3b6f  lea     rdx, [rsp+130h+iid]; lpiid
0x1800c3b74  mov     rcx, rdi; lpsz
0x1800c3b77  call    cs:__imp_IIDFromString
0x1800c3b7d  xor     edx, edx; Val
0x1800c3b7f  mov     [rbp+30h+var_A8], 0FFFFFFFFh
0x1800c3b86  lea     rcx, [rbp+30h+var_A0]; void *
0x1800c3b8a  mov     [rbp+30h+var_A4], 0
0x1800c3b91  lea     r8d, [rdx+68h]; Size
0x1800c3b95  call    memset_0
0x1800c3b9a  mov     rax, qword ptr [rsp+130h+iid.Data1]
0x1800c3b9f  mov     [rbp+30h+var_A0], rax
0x1800c3ba3  mov     rax, qword ptr [rsp+130h+iid.Data4]
0x1800c3ba8  mov     [rbp+30h+var_98], rax
0x1800c3bac  mov     [rbp+30h+var_B0], 423h
0x1800c3bb4  cmp     cs:qword_1801C7178, 7
0x1800c3bbc  lea     rdx, qword_1801C7160
0x1800c3bc3  lea     r9, [rsp+130h+hKey]; HKEY *
0x1800c3bc8  mov     r8d, 2001Fh; unsigned int
0x1800c3bce  cmova   rdx, cs:qword_1801C7160; wchar_t *
0x1800c3bd6  call    ?HrOpenKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@@Z; HrOpenKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *)
0x1800c3bdb  mov     ebx, eax
0x1800c3bdd  test    eax, eax
0x1800c3bdf  jnz     short loc_1800C3C58
0x1800c3be1  mov     rcx, [rsp+130h+hKey]; HKEY
0x1800c3be6  lea     r9, [rsp+130h+var_F0]; struct tagNLA_SIGNATURE *
0x1800c3beb  lea     r8, [rsp+130h+var_110]; unsigned int *
0x1800c3bf0  mov     [rsp+130h+var_110], eax
0x1800c3bf4  mov     rdx, rdi; wchar_t *
0x1800c3bf7  call    ?HrNextUnmanagedSignature@@YAJPEAUHKEY__@@PEB_WPEAKPEAUtagNLA_SIGNATURE@@@Z; HrNextUnmanagedSignature(HKEY__ *,wchar_t const *,ulong *,tagNLA_SIGNATURE *)
0x1800c3bfc  mov     ebx, eax
0x1800c3bfe  test    eax, eax
0x1800c3c00  jnz     short loc_1800C3C45
0x1800c3c02  mov     rcx, [rsp+130h+hKey]; hKey
0x1800c3c07  lea     rdx, [rsp+130h+var_F0]; unsigned __int8 (*)[48]
0x1800c3c0c  call    ?HrDeleteSignature@@YAJPEAUHKEY__@@PEBUtagNLA_SIGNATURE@@@Z; HrDeleteSignature(HKEY__ *,tagNLA_SIGNATURE const *)
0x1800c3c11  mov     ebx, eax
0x1800c3c13  test    eax, eax
0x1800c3c15  jnz     short loc_1800C3C45
0x1800c3c17  movups  xmm0, xmmword ptr [rsp+130h+var_F0]
0x1800c3c1c  mov     eax, [rsp+130h+var_C0]
0x1800c3c20  lea     edx, [rbx+1]; int
0x1800c3c23  movups  xmm1, xmmword ptr [rsp+130h+var_F0+10h]
0x1800c3c28  lea     rcx, [rbp+30h+var_B0]; struct NP_EVENT_INFO *
0x1800c3c2c  mov     [rbp+30h+var_60], eax
0x1800c3c2f  movaps  [rbp+30h+var_90], xmm0
0x1800c3c33  movups  xmm0, xmmword ptr [rsp+130h+var_F0+20h]
0x1800c3c38  movaps  [rbp+30h+var_80], xmm1
0x1800c3c3c  movaps  [rbp+30h+var_70], xmm0
0x1800c3c40  call    ?PostEventToEventMgr@NetworkListManager@@SAJPEAUNP_EVENT_INFO@@H@Z; NetworkListManager::PostEventToEventMgr(NP_EVENT_INFO *,int)
0x1800c3c45  mov     rcx, [rsp+130h+hKey]; hKey
0x1800c3c4a  call    cs:__imp_RegCloseKey
0x1800c3c50  test    ebx, ebx
0x1800c3c52  jz      loc_1800C3BB4
0x1800c3c58  cmp     ebx, 80070103h
0x1800c3c5e  jnz     loc_1800C3CE9
0x1800c3c64  cmp     cs:qword_1801C7158, 7
0x1800c3c6c  lea     rdx, qword_1801C7140
0x1800c3c73  lea     r9, [rsp+130h+hKey]; HKEY *
0x1800c3c78  mov     r8d, 2001Fh; unsigned int
0x1800c3c7e  cmova   rdx, cs:qword_1801C7140; wchar_t *
0x1800c3c86  call    ?HrOpenKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@@Z; HrOpenKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *)
0x1800c3c8b  mov     ebx, eax
0x1800c3c8d  test    eax, eax
0x1800c3c8f  jnz     short loc_1800C3CE9
0x1800c3c91  mov     rcx, [rsp+130h+hKey]; hKey
0x1800c3c96  xor     r9d, r9d; Reserved
0x1800c3c99  xor     r8d, r8d; samDesired
0x1800c3c9c  mov     rdx, rdi; lpSubKey
0x1800c3c9f  call    cs:__imp_RegDeleteKeyExW
0x1800c3ca5  mov     ebx, eax
0x1800c3ca7  test    eax, eax
0x1800c3ca9  jle     short loc_1800C3CB4
0x1800c3cab  movzx   ebx, ax
0x1800c3cae  or      ebx, 80070000h
0x1800c3cb4  mov     rcx, [rsp+130h+hKey]; hKey
0x1800c3cb9  call    cs:__imp_RegCloseKey
0x1800c3cbf  test    ebx, ebx
0x1800c3cc1  jnz     short loc_1800C3CE9
0x1800c3cc3  mov     rax, qword ptr [rsp+130h+iid.Data1]
0x1800c3cc8  lea     edx, [rbx+1]; int
0x1800c3ccb  mov     [rbp+30h+var_A0], rax
0x1800c3ccf  lea     rcx, [rbp+30h+var_B0]; struct NP_EVENT_INFO *
0x1800c3cd3  mov     rax, qword ptr [rsp+130h+iid.Data4]
0x1800c3cd8  mov     [rbp+30h+var_98], rax
0x1800c3cdc  mov     [rbp+30h+var_B0], 413h
0x1800c3ce4  call    ?PostEventToEventMgr@NetworkListManager@@SAJPEAUNP_EVENT_INFO@@H@Z; NetworkListManager::PostEventToEventMgr(NP_EVENT_INFO *,int)
0x1800c3ce9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3cf0  cmp     rcx, r14
0x1800c3cf3  jz      short loc_1800C3D13
0x1800c3cf5  test    byte ptr [rcx+1Ch], 8
0x1800c3cf9  jz      short loc_1800C3D13
0x1800c3cfb  mov     rcx, [rcx+10h]
0x1800c3cff  lea     r8, WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids
0x1800c3d06  mov     edx, 8Dh
0x1800c3d0b  mov     r9d, ebx
0x1800c3d0e  call    WPP_SF_d
0x1800c3d13  mov     eax, ebx
0x1800c3d15  mov     rcx, [rbp+30h+var_30]
0x1800c3d19  xor     rcx, rsp; StackCookie
0x1800c3d1c  call    __security_check_cookie
0x1800c3d21  add     rsp, 118h
0x1800c3d28  pop     r14
0x1800c3d2a  pop     rdi
0x1800c3d2b  pop     rbx
0x1800c3d2c  pop     rbp
0x1800c3d2d  retn
```
