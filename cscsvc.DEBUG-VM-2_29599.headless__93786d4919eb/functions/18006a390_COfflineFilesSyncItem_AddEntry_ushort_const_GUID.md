# COfflineFilesSyncItem::AddEntry(ushort const *,_GUID *)

- ea: `0x18006a390`
- end: `0x18006a5a6`
- name: `?AddEntry@COfflineFilesSyncItem@@UEAAJPEBGPEAU_GUID@@@Z`
- size: `534`
- prototype: `int(COfflineFilesSyncItem *__hidden this, const unsigned __int16 *, struct _GUID *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180018e50`
- `0x180019204`
- `0x18001a0c0`
- `0x18001b4e0`
- `0x18001ba60`
- `0x1800333c4`
- `0x180036128`
- `0x180039610`
- `0x180039fb4`
- `0x18006a390`
- `0x18006abe8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a537`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a567`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a537`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a567`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18006a55c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18006a55c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18006a4d7`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18006a4d7`

## pseudocode

```c
__int64 __fastcall COfflineFilesSyncItem::AddEntry(COfflineFilesSyncItem *this, unsigned __int16 *a2, struct _GUID *a3)
{
  COfflineFilesSyncItem *v3; // rsi
  int EntryByPath; // ebx
  COfflineFilesSyncItem *v7; // rcx
  int v8; // edi
  const unsigned __int16 *ConstBuffer; // rax
  COfflineFilesSyncItem *v10; // rcx
  const unsigned __int16 *v11; // rax
  COfflineFilesSyncItem *v12; // rcx
  GUID v13; // xmm0
  const WCHAR *v14; // rax
  HKEY v16; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  _OWORD v18[8]; // [rsp+40h] [rbp-C0h] BYREF
  GUID pguid; // [rsp+C0h] [rbp-40h] BYREF
  _WORD v20[260]; // [rsp+D0h] [rbp-30h] BYREF
  int v21; // [rsp+2D8h] [rbp+1D8h]
  COfflineFilesSyncItem *v22; // [rsp+2E0h] [rbp+1E0h]
  COfflineFilesSyncItem *v23; // [rsp+2E8h] [rbp+1E8h]
  COfflineFilesSyncItem *v24; // [rsp+2F0h] [rbp+1F0h]
  __int64 v25; // [rsp+2F8h] [rbp+1F8h]
  __int64 v26; // [rsp+300h] [rbp+200h]

  v3 = (COfflineFilesSyncItem *)((char *)this - 24);
  EntryByPath = COfflineFilesSyncItem::_WaitOnMutex((COfflineFilesSyncItem *)((char *)this - 24), (int *)a2);
  if ( EntryByPath >= 0 )
  {
    v20[0] = 0;
    v25 = 520;
    v23 = (COfflineFilesSyncItem *)v20;
    v26 = 520;
    v24 = (COfflineFilesSyncItem *)v20;
    v21 = 34078720;
    v22 = (COfflineFilesSyncItem *)v20;
    EntryByPath = CPath::Copy((CPath *)v20, a2);
    if ( EntryByPath < 0 )
      goto LABEL_26;
    v7 = v22;
    if ( v23 != v24 )
      v7 = v23;
    while ( *(_WORD *)v7 )
    {
      if ( *(_WORD *)v7 == 92 )
        *(_WORD *)v7 = 47;
      v7 = (COfflineFilesSyncItem *)((char *)v7 + 2);
    }
    v16 = 0;
    EntryByPath = COfflineFilesSyncItem::_OpenRootKey(v7, &v16, 0);
    if ( EntryByPath < 0 )
      goto LABEL_26;
    hKey = 0;
    v8 = 0;
    pguid = 0;
    memset_0(v18, 0, 0x74u);
    ConstBuffer = CPath::_GetConstBuffer((CPath *)v20);
    EntryByPath = COfflineFilesSyncItem::_FindEntryByPath(v10, v16, ConstBuffer, &hKey, (struct _SYNC_ITEM_DATA *)v18);
    if ( EntryByPath == -2147024894 )
    {
      EntryByPath = CoCreateGuid(&pguid);
      if ( EntryByPath < 0 )
      {
LABEL_20:
        if ( hKey )
          RegCloseKey(hKey);
        if ( EntryByPath < 0 && v8 )
        {
          v14 = CPath::_GetConstBuffer((CPath *)v20);
          RegDeleteKeyExW(v16, v14, 0, 0);
        }
        RegCloseKey(v16);
LABEL_26:
        COfflineFilesSyncItem::_ReleaseMutex(v3);
        CPath::~CPath((CPath *)v20);
        return (unsigned int)EntryByPath;
      }
      v11 = CPath::_GetConstBuffer((CPath *)v20);
      EntryByPath = COfflineFilesSyncItem::_CreateEntry(v12, v16, v11, (const BYTE *)&pguid, &hKey);
      if ( EntryByPath < 0 )
        v13 = (GUID)v18[0];
      else
        v13 = pguid;
      v8 = 1;
    }
    else
    {
      v13 = (GUID)v18[0];
    }
    if ( EntryByPath >= 0 )
      *a3 = v13;
    goto LABEL_20;
  }
  return (unsigned int)EntryByPath;
}

```

## disassembly

```asm
0x18006a390  mov     [rsp-8+arg_18], rbx
0x18006a395  push    rbp
0x18006a396  push    rsi
0x18006a397  push    rdi
0x18006a398  push    r14
0x18006a39a  push    r15
0x18006a39c  lea     rbp, [rsp-220h]
0x18006a3a4  sub     rsp, 320h
0x18006a3ab  mov     rax, cs:__security_cookie
0x18006a3b2  xor     rax, rsp
0x18006a3b5  mov     [rbp+240h+var_30], rax
0x18006a3bc  lea     rsi, [rcx-18h]
0x18006a3c0  mov     r14, r8
0x18006a3c3  mov     rcx, rsi; this
0x18006a3c6  mov     rdi, rdx
0x18006a3c9  call    ?_WaitOnMutex@COfflineFilesSyncItem@@AEAAJPEAH@Z; COfflineFilesSyncItem::_WaitOnMutex(int *)
0x18006a3ce  xor     r15d, r15d
0x18006a3d1  mov     ebx, eax
0x18006a3d3  test    eax, eax
0x18006a3d5  js      loc_18006A57E
0x18006a3db  mov     ecx, 208h
0x18006a3e0  mov     [rbp+240h+var_270], r15w
0x18006a3e5  lea     rax, [rbp+240h+var_270]
0x18006a3e9  mov     [rbp+240h+var_48], rcx
0x18006a3f0  mov     [rbp+240h+var_58], rax
0x18006a3f7  mov     rdx, rdi; unsigned __int16 *
0x18006a3fa  lea     rax, [rbp+240h+var_270]
0x18006a3fe  mov     [rbp+240h+var_40], rcx
0x18006a405  mov     [rbp+240h+var_50], rax
0x18006a40c  lea     rcx, [rbp+240h+var_270]; this
0x18006a410  lea     rax, [rbp+240h+var_270]
0x18006a414  mov     [rbp+240h+var_68], 2080000h
0x18006a41e  mov     [rbp+240h+var_60], rax
0x18006a425  call    ?Copy@CPath@@QEAAJPEBG@Z; CPath::Copy(ushort const *)
0x18006a42a  mov     ebx, eax
0x18006a42c  test    eax, eax
0x18006a42e  js      loc_18006A56D
0x18006a434  mov     rax, [rbp+240h+var_58]
0x18006a43b  cmp     rax, [rbp+240h+var_50]
0x18006a442  mov     rcx, [rbp+240h+var_60]
0x18006a449  cmovnz  rcx, rax
0x18006a44d  jmp     short loc_18006A462
0x18006a44f  mov     edx, 5Ch ; '\'
0x18006a454  cmp     dx, ax
0x18006a457  jnz     short loc_18006A45E
0x18006a459  mov     word ptr [rcx], 2Fh ; '/'
0x18006a45e  add     rcx, 2; this
0x18006a462  movzx   eax, word ptr [rcx]
0x18006a465  test    ax, ax
0x18006a468  jnz     short loc_18006A44F
0x18006a46a  xor     r8d, r8d; unsigned __int16 *
0x18006a46d  mov     [rsp+340h+var_310], r15
0x18006a472  lea     rdx, [rsp+340h+var_310]; HKEY *
0x18006a477  call    ?_OpenRootKey@COfflineFilesSyncItem@@AEAAJPEAPEAUHKEY__@@PEBG@Z; COfflineFilesSyncItem::_OpenRootKey(HKEY__ * *,ushort const *)
0x18006a47c  mov     ebx, eax
0x18006a47e  test    eax, eax
0x18006a480  js      loc_18006A56D
0x18006a486  xor     edx, edx; Val
0x18006a488  mov     [rsp+340h+hKey], r15
0x18006a48d  xorps   xmm0, xmm0
0x18006a490  lea     rcx, [rsp+340h+var_300]; void *
0x18006a495  mov     edi, r15d
0x18006a498  movups  xmmword ptr [rbp+240h+pguid.Data1], xmm0
0x18006a49c  lea     r8d, [rdx+74h]; Size
0x18006a4a0  call    memset_0
0x18006a4a5  lea     rcx, [rbp+240h+var_270]; this
0x18006a4a9  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18006a4ae  mov     rdx, [rsp+340h+var_310]; HKEY
0x18006a4b3  lea     r9, [rsp+340h+hKey]; HKEY *
0x18006a4b8  mov     r8, rax; unsigned __int16 *
0x18006a4bb  lea     rax, [rsp+340h+var_300]
0x18006a4c0  mov     [rsp+340h+var_320], rax; struct _SYNC_ITEM_DATA *
0x18006a4c5  call    ?_FindEntryByPath@COfflineFilesSyncItem@@AEAAJPEAUHKEY__@@PEBGPEAPEAU2@PEAU_SYNC_ITEM_DATA@@@Z; COfflineFilesSyncItem::_FindEntryByPath(HKEY__ *,ushort const *,HKEY__ * *,_SYNC_ITEM_DATA *)
0x18006a4ca  mov     ebx, eax
0x18006a4cc  cmp     eax, 80070002h
0x18006a4d1  jnz     short loc_18006A51F
0x18006a4d3  lea     rcx, [rbp+240h+pguid]; pguid
0x18006a4d7  call    cs:__imp_CoCreateGuid
0x18006a4dd  mov     ebx, eax
0x18006a4df  test    eax, eax
0x18006a4e1  js      short loc_18006A52D
0x18006a4e3  lea     rcx, [rbp+240h+var_270]; this
0x18006a4e7  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18006a4ec  mov     rdx, [rsp+340h+var_310]; HKEY
0x18006a4f1  lea     r9, [rbp+240h+pguid]; struct _GUID *
0x18006a4f5  mov     r8, rax; unsigned __int16 *
0x18006a4f8  lea     rax, [rsp+340h+hKey]
0x18006a4fd  mov     [rsp+340h+var_320], rax; HKEY *
0x18006a502  call    ?_CreateEntry@COfflineFilesSyncItem@@AEAAJPEAUHKEY__@@PEBGAEBU_GUID@@PEAPEAU2@@Z; COfflineFilesSyncItem::_CreateEntry(HKEY__ *,ushort const *,_GUID const &,HKEY__ * *)
0x18006a507  mov     ebx, eax
0x18006a509  test    eax, eax
0x18006a50b  js      short loc_18006A513
0x18006a50d  movups  xmm0, xmmword ptr [rbp+240h+pguid.Data1]
0x18006a511  jmp     short loc_18006A518
0x18006a513  movaps  xmm0, [rsp+340h+var_300]
0x18006a518  mov     edi, 1
0x18006a51d  jmp     short loc_18006A524
0x18006a51f  movaps  xmm0, [rsp+340h+var_300]
0x18006a524  test    ebx, ebx
0x18006a526  js      short loc_18006A52D
0x18006a528  movdqu  xmmword ptr [r14], xmm0
0x18006a52d  mov     rcx, [rsp+340h+hKey]; hKey
0x18006a532  test    rcx, rcx
0x18006a535  jz      short loc_18006A53D
0x18006a537  call    cs:__imp_RegCloseKey
0x18006a53d  test    ebx, ebx
0x18006a53f  jns     short loc_18006A562
0x18006a541  test    edi, edi
0x18006a543  jz      short loc_18006A562
0x18006a545  lea     rcx, [rbp+240h+var_270]; this
0x18006a549  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18006a54e  mov     rcx, [rsp+340h+var_310]; hKey
0x18006a553  mov     rdx, rax; lpSubKey
0x18006a556  xor     r9d, r9d; Reserved
0x18006a559  xor     r8d, r8d; samDesired
0x18006a55c  call    cs:__imp_RegDeleteKeyExW
0x18006a562  mov     rcx, [rsp+340h+var_310]; hKey
0x18006a567  call    cs:__imp_RegCloseKey
0x18006a56d  mov     rcx, rsi; this
0x18006a570  call    ?_ReleaseMutex@COfflineFilesSyncItem@@AEAAXXZ; COfflineFilesSyncItem::_ReleaseMutex(void)
0x18006a575  lea     rcx, [rbp+240h+var_270]; this
0x18006a579  call    ??1CPath@@QEAA@XZ; CPath::~CPath(void)
0x18006a57e  mov     eax, ebx
0x18006a580  mov     rcx, [rbp+240h+var_30]
0x18006a587  xor     rcx, rsp; StackCookie
0x18006a58a  call    __security_check_cookie
0x18006a58f  mov     rbx, [rsp+340h+arg_18]
0x18006a597  add     rsp, 320h
0x18006a59e  pop     r15
0x18006a5a0  pop     r14
0x18006a5a2  pop     rdi
0x18006a5a3  pop     rsi
0x18006a5a4  pop     rbp
0x18006a5a5  retn
```
