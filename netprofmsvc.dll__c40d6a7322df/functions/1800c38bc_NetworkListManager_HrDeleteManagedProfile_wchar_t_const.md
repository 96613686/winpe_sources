# NetworkListManager::HrDeleteManagedProfile(wchar_t const *)

- ea: `0x1800c38bc`
- end: `0x1800c3af2`
- name: `?HrDeleteManagedProfile@NetworkListManager@@AEAAJPEB_W@Z`
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
- `0x180035728`
- `0x180037820`
- `0x180073420`
- `0x1800a88a0`
- `0x1800a9738`
- `0x1800c38bc`
- `0x1800cb1a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800c393b`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800c393b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c3a0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c3a7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c3a0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c3a7d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800c3a63`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800c3a63`

## pseudocode

```c
__int64 __fastcall NetworkListManager::HrDeleteManagedProfile(NetworkListManager *this, const wchar_t *a2)
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 138, &WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids);
  IIDFromString(a2, &iid);
  v15 = -1;
  v16 = 0;
  memset_0(v17, 0, 0x68u);
  v17[0] = iid;
  v14 = 1059;
  do
  {
    v4 = (const wchar_t *)&qword_1801C7180;
    if ( (unsigned __int64)qword_1801C7198 > 7 )
      v4 = qword_1801C7180;
    v5 = HrOpenKey(v3, v4, 0x2001Fu, &hKey);
    if ( v5 )
      break;
    v9 = 0;
    v5 = HrNextManagedSignature(hKey, a2, &v9, (struct tagNLA_SIGNATURE *)v12);
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, &WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x1800c38bc  push    rbp
0x1800c38be  push    rbx
0x1800c38bf  push    rdi
0x1800c38c0  push    r14
0x1800c38c2  lea     rbp, [rsp-18h]
0x1800c38c7  sub     rsp, 118h
0x1800c38ce  mov     rax, cs:__security_cookie
0x1800c38d5  xor     rax, rsp
0x1800c38d8  mov     [rbp+30h+var_30], rax
0x1800c38dc  xorps   xmm0, xmm0
0x1800c38df  mov     [rsp+130h+hKey], 0
0x1800c38e8  xor     eax, eax
0x1800c38ea  mov     rdi, rdx
0x1800c38ed  movups  xmmword ptr [rsp+130h+var_F0], xmm0
0x1800c38f2  mov     [rsp+130h+var_C0], eax
0x1800c38f6  movups  xmmword ptr [rsp+130h+var_F0+10h], xmm0
0x1800c38fb  movups  xmmword ptr [rsp+130h+var_F0+20h], xmm0
0x1800c3900  movups  xmmword ptr [rsp+130h+iid.Data1], xmm0
0x1800c3905  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c390c  lea     r14, WPP_GLOBAL_Control
0x1800c3913  cmp     rcx, r14
0x1800c3916  jz      short loc_1800C3933
0x1800c3918  test    byte ptr [rcx+1Ch], 8
0x1800c391c  jz      short loc_1800C3933
0x1800c391e  mov     rcx, [rcx+10h]
0x1800c3922  lea     r8, WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids
0x1800c3929  mov     edx, 8Ah
0x1800c392e  call    WPP_SF_
0x1800c3933  lea     rdx, [rsp+130h+iid]; lpiid
0x1800c3938  mov     rcx, rdi; lpsz
0x1800c393b  call    cs:__imp_IIDFromString
0x1800c3941  xor     edx, edx; Val
0x1800c3943  mov     [rbp+30h+var_A8], 0FFFFFFFFh
0x1800c394a  lea     rcx, [rbp+30h+var_A0]; void *
0x1800c394e  mov     [rbp+30h+var_A4], 0
0x1800c3955  lea     r8d, [rdx+68h]; Size
0x1800c3959  call    memset_0
0x1800c395e  mov     rax, qword ptr [rsp+130h+iid.Data1]
0x1800c3963  mov     [rbp+30h+var_A0], rax
0x1800c3967  mov     rax, qword ptr [rsp+130h+iid.Data4]
0x1800c396c  mov     [rbp+30h+var_98], rax
0x1800c3970  mov     [rbp+30h+var_B0], 423h
0x1800c3978  cmp     cs:qword_1801C7198, 7
0x1800c3980  lea     rdx, qword_1801C7180
0x1800c3987  lea     r9, [rsp+130h+hKey]; HKEY *
0x1800c398c  mov     r8d, 2001Fh; unsigned int
0x1800c3992  cmova   rdx, cs:qword_1801C7180; wchar_t *
0x1800c399a  call    ?HrOpenKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@@Z; HrOpenKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *)
0x1800c399f  mov     ebx, eax
0x1800c39a1  test    eax, eax
0x1800c39a3  jnz     short loc_1800C3A1C
0x1800c39a5  mov     rcx, [rsp+130h+hKey]; HKEY
0x1800c39aa  lea     r9, [rsp+130h+var_F0]; struct tagNLA_SIGNATURE *
0x1800c39af  lea     r8, [rsp+130h+var_110]; unsigned int *
0x1800c39b4  mov     [rsp+130h+var_110], eax
0x1800c39b8  mov     rdx, rdi; wchar_t *
0x1800c39bb  call    ?HrNextManagedSignature@@YAJPEAUHKEY__@@PEB_WPEAKPEAUtagNLA_SIGNATURE@@@Z; HrNextManagedSignature(HKEY__ *,wchar_t const *,ulong *,tagNLA_SIGNATURE *)
0x1800c39c0  mov     ebx, eax
0x1800c39c2  test    eax, eax
0x1800c39c4  jnz     short loc_1800C3A09
0x1800c39c6  mov     rcx, [rsp+130h+hKey]; hKey
0x1800c39cb  lea     rdx, [rsp+130h+var_F0]; unsigned __int8 (*)[48]
0x1800c39d0  call    ?HrDeleteSignature@@YAJPEAUHKEY__@@PEBUtagNLA_SIGNATURE@@@Z; HrDeleteSignature(HKEY__ *,tagNLA_SIGNATURE const *)
0x1800c39d5  mov     ebx, eax
0x1800c39d7  test    eax, eax
0x1800c39d9  jnz     short loc_1800C3A09
0x1800c39db  movups  xmm0, xmmword ptr [rsp+130h+var_F0]
0x1800c39e0  mov     eax, [rsp+130h+var_C0]
0x1800c39e4  lea     edx, [rbx+1]; int
0x1800c39e7  movups  xmm1, xmmword ptr [rsp+130h+var_F0+10h]
0x1800c39ec  lea     rcx, [rbp+30h+var_B0]; struct NP_EVENT_INFO *
0x1800c39f0  mov     [rbp+30h+var_60], eax
0x1800c39f3  movaps  [rbp+30h+var_90], xmm0
0x1800c39f7  movups  xmm0, xmmword ptr [rsp+130h+var_F0+20h]
0x1800c39fc  movaps  [rbp+30h+var_80], xmm1
0x1800c3a00  movaps  [rbp+30h+var_70], xmm0
0x1800c3a04  call    ?PostEventToEventMgr@NetworkListManager@@SAJPEAUNP_EVENT_INFO@@H@Z; NetworkListManager::PostEventToEventMgr(NP_EVENT_INFO *,int)
0x1800c3a09  mov     rcx, [rsp+130h+hKey]; hKey
0x1800c3a0e  call    cs:__imp_RegCloseKey
0x1800c3a14  test    ebx, ebx
0x1800c3a16  jz      loc_1800C3978
0x1800c3a1c  cmp     ebx, 80070103h
0x1800c3a22  jnz     loc_1800C3AAD
0x1800c3a28  cmp     cs:qword_1801C7158, 7
0x1800c3a30  lea     rdx, qword_1801C7140
0x1800c3a37  lea     r9, [rsp+130h+hKey]; HKEY *
0x1800c3a3c  mov     r8d, 2001Fh; unsigned int
0x1800c3a42  cmova   rdx, cs:qword_1801C7140; wchar_t *
0x1800c3a4a  call    ?HrOpenKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@@Z; HrOpenKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *)
0x1800c3a4f  mov     ebx, eax
0x1800c3a51  test    eax, eax
0x1800c3a53  jnz     short loc_1800C3AAD
0x1800c3a55  mov     rcx, [rsp+130h+hKey]; hKey
0x1800c3a5a  xor     r9d, r9d; Reserved
0x1800c3a5d  xor     r8d, r8d; samDesired
0x1800c3a60  mov     rdx, rdi; lpSubKey
0x1800c3a63  call    cs:__imp_RegDeleteKeyExW
0x1800c3a69  mov     ebx, eax
0x1800c3a6b  test    eax, eax
0x1800c3a6d  jle     short loc_1800C3A78
0x1800c3a6f  movzx   ebx, ax
0x1800c3a72  or      ebx, 80070000h
0x1800c3a78  mov     rcx, [rsp+130h+hKey]; hKey
0x1800c3a7d  call    cs:__imp_RegCloseKey
0x1800c3a83  test    ebx, ebx
0x1800c3a85  jnz     short loc_1800C3AAD
0x1800c3a87  mov     rax, qword ptr [rsp+130h+iid.Data1]
0x1800c3a8c  lea     edx, [rbx+1]; int
0x1800c3a8f  mov     [rbp+30h+var_A0], rax
0x1800c3a93  lea     rcx, [rbp+30h+var_B0]; struct NP_EVENT_INFO *
0x1800c3a97  mov     rax, qword ptr [rsp+130h+iid.Data4]
0x1800c3a9c  mov     [rbp+30h+var_98], rax
0x1800c3aa0  mov     [rbp+30h+var_B0], 413h
0x1800c3aa8  call    ?PostEventToEventMgr@NetworkListManager@@SAJPEAUNP_EVENT_INFO@@H@Z; NetworkListManager::PostEventToEventMgr(NP_EVENT_INFO *,int)
0x1800c3aad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3ab4  cmp     rcx, r14
0x1800c3ab7  jz      short loc_1800C3AD7
0x1800c3ab9  test    byte ptr [rcx+1Ch], 8
0x1800c3abd  jz      short loc_1800C3AD7
0x1800c3abf  mov     rcx, [rcx+10h]
0x1800c3ac3  lea     r8, WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids
0x1800c3aca  mov     edx, 8Bh
0x1800c3acf  mov     r9d, ebx
0x1800c3ad2  call    WPP_SF_d
0x1800c3ad7  mov     eax, ebx
0x1800c3ad9  mov     rcx, [rbp+30h+var_30]
0x1800c3add  xor     rcx, rsp; StackCookie
0x1800c3ae0  call    __security_check_cookie
0x1800c3ae5  add     rsp, 118h
0x1800c3aec  pop     r14
0x1800c3aee  pop     rdi
0x1800c3aef  pop     rbx
0x1800c3af0  pop     rbp
0x1800c3af1  retn
```
