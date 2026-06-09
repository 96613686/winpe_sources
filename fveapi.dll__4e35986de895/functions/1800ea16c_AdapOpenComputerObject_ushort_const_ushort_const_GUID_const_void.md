# AdapOpenComputerObject(ushort const *,ushort const *,_GUID const &,void * *)

- ea: `0x1800ea16c`
- end: `0x1800ea4a3`
- name: `?AdapOpenComputerObject@@YAJPEBG0AEBU_GUID@@PEAPEAX@Z`
- size: `823`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x1800e8f2c`

## callees

- `0x1800090c0`
- `0x1800600c0`
- `0x1800e9b4c`
- `0x1800ea16c`
- `0x180129010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800ea376`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800ea46f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800ea483`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800ea376`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800ea46f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800ea483`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ea1c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ea25d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ea2a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ea1c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ea25d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ea2a0`
- `ext-ms-win-secur32-translatename-l1-1-0!GetComputerObjectNameW` at `0x1800ea1af`
- `ext-ms-win-secur32-translatename-l1-1-0!GetComputerObjectNameW` at `0x1800ea249`
- `ext-ms-win-secur32-translatename-l1-1-0!GetComputerObjectNameW` at `0x1800ea1af`
- `ext-ms-win-secur32-translatename-l1-1-0!GetComputerObjectNameW` at `0x1800ea249`
- `ext-ms-win-adsi-activeds-l1-1-0!ADsOpenObject` at `0x1800ea358`
- `ext-ms-win-adsi-activeds-l1-1-0!ADsOpenObject` at `0x1800ea3f7`
- `ext-ms-win-adsi-activeds-l1-1-0!ADsOpenObject` at `0x1800ea358`
- `ext-ms-win-adsi-activeds-l1-1-0!ADsOpenObject` at `0x1800ea3f7`

## pseudocode

```c
__int64 __fastcall AdapOpenComputerObject(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        void **a4)
{
  WCHAR *v4; // rsi
  WCHAR *v6; // r14
  unsigned __int64 v7; // rax
  WCHAR *v8; // rax
  int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  signed int v12; // eax
  signed int LastError; // eax
  unsigned int ComputerObjectPath; // eax
  unsigned int v15; // eax
  void *ppObject; // [rsp+60h] [rbp+30h] BYREF
  LPCWSTR lpszPathName; // [rsp+68h] [rbp+38h] BYREF
  ULONG nSize; // [rsp+70h] [rbp+40h] BYREF
  int v20; // [rsp+74h] [rbp+44h]

  v20 = HIDWORD(a3);
  v4 = 0;
  ppObject = 0;
  lpszPathName = 0;
  nSize = 0;
  v6 = 0;
  if ( GetComputerObjectNameW(NameSamCompatible, 0, &nSize) )
    goto LABEL_21;
  if ( GetLastError() != 122 )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      v11 = 62;
      goto LABEL_9;
    }
    goto LABEL_42;
  }
  v7 = 2LL * nSize;
  if ( !is_mul_ok(nSize, 2u) )
    v7 = -1;
  v8 = (WCHAR *)operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v8;
  if ( !v8 )
  {
    v9 = -2147024882;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      v11 = 60;
LABEL_9:
      WPP_SF_d(v10[2], v11, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids, (unsigned int)v9);
      goto LABEL_42;
    }
    goto LABEL_42;
  }
  if ( GetComputerObjectNameW(NameSamCompatible, v8, &nSize) )
  {
LABEL_21:
    ComputerObjectPath = AdapGetComputerObjectPath((unsigned __int16 **)&lpszPathName, 0);
    v9 = ComputerObjectPath;
    if ( ComputerObjectPath )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          63,
          WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids,
          ComputerObjectPath);
      if ( v9 < 0 )
        goto LABEL_34;
    }
    v4 = (WCHAR *)lpszPathName;
    v9 = ADsOpenObject(lpszPathName, v6, 0, 0x2C1u, &IID_IDirectoryObject, &ppObject);
    if ( v9 < 0 )
    {
      if ( v4 )
      {
        operator delete[](v4);
        lpszPathName = 0;
      }
      v15 = AdapGetComputerObjectPath((unsigned __int16 **)&lpszPathName, 1u);
      v9 = v15;
      if ( v15 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids, v15);
        if ( v9 < 0 )
        {
LABEL_34:
          v4 = (WCHAR *)lpszPathName;
          goto LABEL_42;
        }
      }
      v4 = (WCHAR *)lpszPathName;
      v9 = ADsOpenObject(lpszPathName, v6, 0, 0x2C1u, &IID_IDirectoryObject, &ppObject);
      if ( v9 < 0 )
        goto LABEL_38;
    }
    if ( v9 )
    {
LABEL_38:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          65,
          WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids,
          (unsigned int)v9);
      if ( v9 < 0 )
        goto LABEL_42;
    }
    *a4 = ppObject;
    ppObject = 0;
    goto LABEL_42;
  }
  v12 = GetLastError();
  v9 = v12;
  if ( v12 > 0 )
    v9 = (unsigned __int16)v12 | 0x80070000;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    v11 = 61;
    goto LABEL_9;
  }
LABEL_42:
  if ( ppObject )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppObject + 16LL))(ppObject);
    ppObject = 0;
  }
  if ( v4 )
    operator delete[](v4);
  if ( v6 )
    operator delete[](v6);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800ea16c  mov     rax, rsp
0x1800ea16f  mov     [rax+20h], rbx
0x1800ea173  mov     [rax+18h], r8
0x1800ea177  mov     [rax+10h], rdx
0x1800ea17b  mov     [rax+8], rcx
0x1800ea17f  push    rbp
0x1800ea180  push    rsi
0x1800ea181  push    rdi
0x1800ea182  push    r14
0x1800ea184  push    r15
0x1800ea186  mov     rbp, rsp
0x1800ea189  sub     rsp, 30h
0x1800ea18d  xor     esi, esi
0x1800ea18f  mov     [rbp+arg_0], 0
0x1800ea197  lea     r8, [rbp+nSize]; nSize
0x1800ea19b  mov     [rbp+lpszPathName], rsi
0x1800ea19f  xor     edx, edx; lpNameBuffer
0x1800ea1a1  mov     [rbp+nSize], esi
0x1800ea1a4  mov     r15, r9
0x1800ea1a7  xor     r14d, r14d
0x1800ea1aa  lea     ebx, [rsi+2]
0x1800ea1ad  mov     ecx, ebx; NameFormat
0x1800ea1af  call    cs:__imp_GetComputerObjectNameW
0x1800ea1b6  nop     dword ptr [rax+rax+00h]
0x1800ea1bb  test    al, al
0x1800ea1bd  jnz     loc_1800EA2E6
0x1800ea1c3  call    cs:__imp_GetLastError
0x1800ea1ca  nop     dword ptr [rax+rax+00h]
0x1800ea1cf  cmp     eax, 7Ah ; 'z'
0x1800ea1d2  jnz     loc_1800EA2A0
0x1800ea1d8  mov     ecx, [rbp+nSize]
0x1800ea1db  mov     eax, ebx
0x1800ea1dd  mul     rcx
0x1800ea1e0  lea     rcx, [rsi-1]
0x1800ea1e4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800ea1eb  cmovb   rax, rcx
0x1800ea1ef  mov     rcx, rax; unsigned __int64
0x1800ea1f2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800ea1f7  mov     r14, rax
0x1800ea1fa  test    rax, rax
0x1800ea1fd  jnz     short loc_1800EA240
0x1800ea1ff  mov     ebx, 8007000Eh
0x1800ea204  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ea20b  lea     rdi, WPP_GLOBAL_Control
0x1800ea212  cmp     rcx, rdi
0x1800ea215  jz      loc_1800EA44A
0x1800ea21b  test    byte ptr [rcx+1Ch], 40h
0x1800ea21f  jz      loc_1800EA44A
0x1800ea225  lea     edx, [rsi+3Ch]
0x1800ea228  mov     rcx, [rcx+10h]
0x1800ea22c  lea     r8, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids
0x1800ea233  mov     r9d, ebx
0x1800ea236  call    WPP_SF_d
0x1800ea23b  jmp     loc_1800EA44A
0x1800ea240  lea     r8, [rbp+nSize]; nSize
0x1800ea244  mov     rdx, rax; lpNameBuffer
0x1800ea247  mov     ecx, ebx; NameFormat
0x1800ea249  call    cs:__imp_GetComputerObjectNameW
0x1800ea250  nop     dword ptr [rax+rax+00h]
0x1800ea255  test    al, al
0x1800ea257  jnz     loc_1800EA2E6
0x1800ea25d  call    cs:__imp_GetLastError
0x1800ea264  nop     dword ptr [rax+rax+00h]
0x1800ea269  mov     ebx, eax
0x1800ea26b  test    eax, eax
0x1800ea26d  jle     short loc_1800EA278
0x1800ea26f  movzx   ebx, ax
0x1800ea272  or      ebx, 80070000h
0x1800ea278  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ea27f  lea     rdi, WPP_GLOBAL_Control
0x1800ea286  cmp     rcx, rdi
0x1800ea289  jz      loc_1800EA44A
0x1800ea28f  test    byte ptr [rcx+1Ch], 40h
0x1800ea293  jz      loc_1800EA44A
0x1800ea299  mov     edx, 3Dh ; '='
0x1800ea29e  jmp     short loc_1800EA228
0x1800ea2a0  call    cs:__imp_GetLastError
0x1800ea2a7  nop     dword ptr [rax+rax+00h]
0x1800ea2ac  mov     ebx, eax
0x1800ea2ae  test    eax, eax
0x1800ea2b0  jle     short loc_1800EA2BB
0x1800ea2b2  movzx   ebx, ax
0x1800ea2b5  or      ebx, 80070000h
0x1800ea2bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ea2c2  lea     rdi, WPP_GLOBAL_Control
0x1800ea2c9  cmp     rcx, rdi
0x1800ea2cc  jz      loc_1800EA44A
0x1800ea2d2  test    byte ptr [rcx+1Ch], 40h
0x1800ea2d6  jz      loc_1800EA44A
0x1800ea2dc  mov     edx, 3Eh ; '>'
0x1800ea2e1  jmp     loc_1800EA228
0x1800ea2e6  xor     edx, edx; bool
0x1800ea2e8  lea     rcx, [rbp+lpszPathName]; unsigned __int16 **
0x1800ea2ec  call    ?AdapGetComputerObjectPath@@YAJPEAPEAG_N@Z; AdapGetComputerObjectPath(ushort * *,bool)
0x1800ea2f1  lea     rdi, WPP_GLOBAL_Control
0x1800ea2f8  mov     ebx, eax
0x1800ea2fa  test    eax, eax
0x1800ea2fc  jz      short loc_1800EA330
0x1800ea2fe  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ea305  cmp     rcx, rdi
0x1800ea308  jz      short loc_1800EA328
0x1800ea30a  test    byte ptr [rcx+1Ch], 40h
0x1800ea30e  jz      short loc_1800EA328
0x1800ea310  mov     rcx, [rcx+10h]
0x1800ea314  lea     r8, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids
0x1800ea31b  mov     edx, 3Fh ; '?'
0x1800ea320  mov     r9d, eax
0x1800ea323  call    WPP_SF_d
0x1800ea328  test    ebx, ebx
0x1800ea32a  js      loc_1800EA3C9
0x1800ea330  mov     rsi, [rbp+lpszPathName]
0x1800ea334  lea     rax, [rbp+arg_0]
0x1800ea338  mov     [rsp+30h+ppObject], rax; ppObject
0x1800ea33d  mov     r9d, 2C1h; dwReserved
0x1800ea343  lea     rax, IID_IDirectoryObject
0x1800ea34a  xor     r8d, r8d; lpszPassword
0x1800ea34d  mov     rdx, r14; lpszUserName
0x1800ea350  mov     [rsp+30h+riid], rax; riid
0x1800ea355  mov     rcx, rsi; lpszPathName
0x1800ea358  call    cs:__imp_ADsOpenObject
0x1800ea35f  nop     dword ptr [rax+rax+00h]
0x1800ea364  mov     ebx, eax
0x1800ea366  test    eax, eax
0x1800ea368  jns     loc_1800EA409
0x1800ea36e  test    rsi, rsi
0x1800ea371  jz      short loc_1800EA38A
0x1800ea373  mov     rcx, rsi
0x1800ea376  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800ea37d  nop     dword ptr [rax+rax+00h]
0x1800ea382  mov     [rbp+lpszPathName], 0
0x1800ea38a  mov     dl, 1; bool
0x1800ea38c  lea     rcx, [rbp+lpszPathName]; unsigned __int16 **
0x1800ea390  call    ?AdapGetComputerObjectPath@@YAJPEAPEAG_N@Z; AdapGetComputerObjectPath(ushort * *,bool)
0x1800ea395  mov     ebx, eax
0x1800ea397  test    eax, eax
0x1800ea399  jz      short loc_1800EA3CF
0x1800ea39b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ea3a2  cmp     rcx, rdi
0x1800ea3a5  jz      short loc_1800EA3C5
0x1800ea3a7  test    byte ptr [rcx+1Ch], 40h
0x1800ea3ab  jz      short loc_1800EA3C5
0x1800ea3ad  mov     rcx, [rcx+10h]
0x1800ea3b1  lea     r8, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids
0x1800ea3b8  mov     edx, 40h ; '@'
0x1800ea3bd  mov     r9d, eax
0x1800ea3c0  call    WPP_SF_d
0x1800ea3c5  test    ebx, ebx
0x1800ea3c7  jns     short loc_1800EA3CF
0x1800ea3c9  mov     rsi, [rbp+lpszPathName]
0x1800ea3cd  jmp     short loc_1800EA44A
0x1800ea3cf  mov     rsi, [rbp+lpszPathName]
0x1800ea3d3  lea     rax, [rbp+arg_0]
0x1800ea3d7  mov     [rsp+30h+ppObject], rax; ppObject
0x1800ea3dc  mov     r9d, 2C1h; dwReserved
0x1800ea3e2  lea     rax, IID_IDirectoryObject
0x1800ea3e9  xor     r8d, r8d; lpszPassword
0x1800ea3ec  mov     rdx, r14; lpszUserName
0x1800ea3ef  mov     [rsp+30h+riid], rax; riid
0x1800ea3f4  mov     rcx, rsi; lpszPathName
0x1800ea3f7  call    cs:__imp_ADsOpenObject
0x1800ea3fe  nop     dword ptr [rax+rax+00h]
0x1800ea403  mov     ebx, eax
0x1800ea405  test    eax, eax
0x1800ea407  js      short loc_1800EA40D
0x1800ea409  test    ebx, ebx
0x1800ea40b  jz      short loc_1800EA43B
0x1800ea40d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ea414  cmp     rcx, rdi
0x1800ea417  jz      short loc_1800EA437
0x1800ea419  test    byte ptr [rcx+1Ch], 40h
0x1800ea41d  jz      short loc_1800EA437
0x1800ea41f  mov     rcx, [rcx+10h]
0x1800ea423  lea     r8, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids
0x1800ea42a  mov     edx, 41h ; 'A'
0x1800ea42f  mov     r9d, ebx
0x1800ea432  call    WPP_SF_d
0x1800ea437  test    ebx, ebx
0x1800ea439  js      short loc_1800EA44A
0x1800ea43b  mov     rax, [rbp+arg_0]
0x1800ea43f  mov     [r15], rax
0x1800ea442  mov     [rbp+arg_0], 0
0x1800ea44a  mov     rcx, [rbp+arg_0]
0x1800ea44e  test    rcx, rcx
0x1800ea451  jz      short loc_1800EA467
0x1800ea453  mov     rax, [rcx]
0x1800ea456  mov     rax, [rax+10h]
0x1800ea45a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ea45f  mov     [rbp+arg_0], 0
0x1800ea467  test    rsi, rsi
0x1800ea46a  jz      short loc_1800EA47B
0x1800ea46c  mov     rcx, rsi
0x1800ea46f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800ea476  nop     dword ptr [rax+rax+00h]
0x1800ea47b  test    r14, r14
0x1800ea47e  jz      short loc_1800EA48F
0x1800ea480  mov     rcx, r14
0x1800ea483  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800ea48a  nop     dword ptr [rax+rax+00h]
0x1800ea48f  mov     eax, ebx
0x1800ea491  mov     rbx, [rsp+30h+arg_18]
0x1800ea496  add     rsp, 30h
0x1800ea49a  pop     r15
0x1800ea49c  pop     r14
0x1800ea49e  pop     rdi
0x1800ea49f  pop     rsi
0x1800ea4a0  pop     rbp
0x1800ea4a1  retn
```
