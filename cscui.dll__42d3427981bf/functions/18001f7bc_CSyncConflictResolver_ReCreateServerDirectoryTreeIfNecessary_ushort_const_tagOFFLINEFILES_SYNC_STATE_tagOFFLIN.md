# CSyncConflictResolver::_ReCreateServerDirectoryTreeIfNecessary(ushort const *,tagOFFLINEFILES_SYNC_STATE,tagOFFLINEFILES_SYNC_CONFLICT_RESOLVE)

- ea: `0x18001f7bc`
- end: `0x18001f987`
- name: `?_ReCreateServerDirectoryTreeIfNecessary@CSyncConflictResolver@@AEAAJPEBGW4tagOFFLINEFILES_SYNC_STATE@@W4tagOFFLINEFILES_SYNC_CONFLICT_RESOLVE@@@Z`
- size: `459`
- prototype: `int(CSyncConflictResolver *__hidden this, const unsigned __int16 *, enum tagOFFLINEFILES_SYNC_STATE, enum tagOFFLINEFILES_SYNC_CONFLICT_RESOLVE)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001dc80`

## callees

- `0x180002810`
- `0x180003c20`
- `0x180005b70`
- `0x18000735c`
- `0x180011364`
- `0x180013d9c`
- `0x180013dfc`
- `0x18001f7bc`
- `0x180032b44`
- `0x18004c670`

## import_xrefs

- `SHELL32!__imp_SHCreateDirectory` at `0x18001f8fb`
- `SHELL32!__imp_SHCreateDirectory` at `0x18001f8fb`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001f89e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001f89e`

## pseudocode

```c
__int64 __fastcall CSyncConflictResolver::_ReCreateServerDirectoryTreeIfNecessary(
        CSyncConflictResolver *this,
        const unsigned __int16 *a2,
        enum tagOFFLINEFILES_SYNC_STATE a3,
        enum tagOFFLINEFILES_SYNC_CONFLICT_RESOLVE a4)
{
  signed int v4; // ebx
  void *v5; // rdx
  const WCHAR *ConstBuffer; // rax
  const unsigned __int16 *v7; // rax
  __int64 v8; // r10
  const WCHAR *v9; // rax
  int v10; // eax
  unsigned int v11; // eax
  __int64 v12; // r10
  void *lpMem; // [rsp+30h] [rbp-D0h] BYREF
  _WORD v15[260]; // [rsp+40h] [rbp-C0h] BYREF
  int v16; // [rsp+248h] [rbp+148h]
  _WORD *v17; // [rsp+250h] [rbp+150h]
  _WORD *v18; // [rsp+258h] [rbp+158h]
  _WORD *v19; // [rsp+260h] [rbp+160h]
  __int64 v20; // [rsp+268h] [rbp+168h]
  __int64 v21; // [rsp+270h] [rbp+170h]

  v4 = 0;
  if ( a3 == OFFLINEFILES_SYNC_STATE_FileChangedOnClient_DeletedOnServer
    && a4 == OFFLINEFILES_SYNC_CONFLICT_RESOLVE_KEEPLOCAL )
  {
    lpMem = 0;
    v4 = CscUtil_PathToServerPath(a2, (unsigned __int16 **)&lpMem);
    if ( v4 >= 0 )
    {
      v18 = v15;
      v20 = 520;
      v19 = v15;
      v17 = v15;
      v21 = 520;
      v15[0] = 0;
      v16 = 34078720;
      v4 = CPath::Copy((CPath *)v15, (const unsigned __int16 *)lpMem);
      if ( v4 >= 0 )
      {
        v4 = CPath::RemoveFileSpecAndBackslash((CPath *)v15);
        if ( v4 >= 0 )
        {
          ConstBuffer = CPath::_GetConstBuffer((CPath *)v15);
          if ( GetFileAttributesW(ConstBuffer) == -1 )
          {
            if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
            {
              v7 = CPath::_GetConstBuffer((CPath *)v15);
              WPP_SF_S(*(_QWORD *)(v8 + 16), 48, WPP_bafd4961db7d3885dd5128069fc3a0ad_Traceguids, v7);
            }
            v9 = CPath::_GetConstBuffer((CPath *)v15);
            v10 = SHCreateDirectory(0, v9);
            if ( v10 )
            {
              if ( v10 > 0 )
                v4 = (unsigned __int16)v10 | 0x80070000;
              else
                v4 = v10;
              if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v11 = (unsigned int)CPath::_GetConstBuffer((CPath *)v15);
                WPP_SF_Sd(
                  *(_QWORD *)(v12 + 16),
                  49,
                  (unsigned int)WPP_bafd4961db7d3885dd5128069fc3a0ad_Traceguids,
                  v11,
                  v4);
              }
            }
          }
        }
      }
      CscUtil_HeapFree(lpMem, v5);
      CPath::~CPath((CPath *)v15);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001f7bc  mov     [rsp-8+arg_0], rbx
0x18001f7c1  mov     [rsp-8+arg_10], rdi
0x18001f7c6  push    rbp
0x18001f7c7  lea     rbp, [rsp-190h]
0x18001f7cf  sub     rsp, 290h
0x18001f7d6  mov     rax, cs:__security_cookie
0x18001f7dd  xor     rax, rsp
0x18001f7e0  mov     [rbp+190h+var_10], rax
0x18001f7e7  xor     ebx, ebx
0x18001f7e9  mov     rax, rdx
0x18001f7ec  cmp     r8d, 0Fh
0x18001f7f0  jnz     loc_18001F961
0x18001f7f6  cmp     r9d, 1
0x18001f7fa  jnz     loc_18001F961
0x18001f800  lea     rdx, [rsp+290h+lpMem]; unsigned __int16 **
0x18001f805  mov     [rsp+290h+lpMem], rbx
0x18001f80a  mov     rcx, rax; unsigned __int16 *
0x18001f80d  call    ?CscUtil_PathToServerPath@@YAJPEBGPEAPEAG@Z; CscUtil_PathToServerPath(ushort const *,ushort * *)
0x18001f812  mov     ebx, eax
0x18001f814  test    eax, eax
0x18001f816  js      loc_18001F961
0x18001f81c  mov     rdx, [rsp+290h+lpMem]; unsigned __int16 *
0x18001f821  lea     rax, [rsp+290h+var_250]
0x18001f826  mov     [rbp+190h+var_38], rax
0x18001f82d  mov     ecx, 208h
0x18001f832  lea     rax, [rsp+290h+var_250]
0x18001f837  mov     [rbp+190h+var_28], rcx
0x18001f83e  mov     [rbp+190h+var_30], rax
0x18001f845  lea     rax, [rsp+290h+var_250]
0x18001f84a  mov     [rbp+190h+var_40], rax
0x18001f851  xor     eax, eax
0x18001f853  mov     [rbp+190h+var_20], rcx
0x18001f85a  lea     rcx, [rsp+290h+var_250]; this
0x18001f85f  mov     [rsp+290h+var_250], ax
0x18001f864  mov     [rbp+190h+var_48], 2080000h
0x18001f86e  call    ?Copy@CPath@@QEAAJPEBG@Z; CPath::Copy(ushort const *)
0x18001f873  mov     ebx, eax
0x18001f875  test    eax, eax
0x18001f877  js      loc_18001F94D
0x18001f87d  lea     rcx, [rsp+290h+var_250]; this
0x18001f882  call    ?RemoveFileSpecAndBackslash@CPath@@QEAAJXZ; CPath::RemoveFileSpecAndBackslash(void)
0x18001f887  mov     ebx, eax
0x18001f889  test    eax, eax
0x18001f88b  js      loc_18001F94D
0x18001f891  lea     rcx, [rsp+290h+var_250]; this
0x18001f896  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18001f89b  mov     rcx, rax; lpFileName
0x18001f89e  call    cs:__imp_GetFileAttributesW
0x18001f8a4  cmp     eax, 0FFFFFFFFh
0x18001f8a7  jnz     loc_18001F94D
0x18001f8ad  mov     r10, cs:WPP_GLOBAL_Control
0x18001f8b4  lea     rdi, WPP_GLOBAL_Control
0x18001f8bb  cmp     r10, rdi
0x18001f8be  jz      short loc_18001F8EC
0x18001f8c0  test    dword ptr [r10+1Ch], 200000h
0x18001f8c8  jz      short loc_18001F8EC
0x18001f8ca  lea     rcx, [rsp+290h+var_250]; this
0x18001f8cf  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18001f8d4  mov     rcx, [r10+10h]
0x18001f8d8  lea     r8, WPP_bafd4961db7d3885dd5128069fc3a0ad_Traceguids
0x18001f8df  mov     r9, rax
0x18001f8e2  mov     edx, 30h ; '0'
0x18001f8e7  call    WPP_SF_S
0x18001f8ec  lea     rcx, [rsp+290h+var_250]; this
0x18001f8f1  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18001f8f6  mov     rdx, rax; pszPath
0x18001f8f9  xor     ecx, ecx; hwnd
0x18001f8fb  call    cs:__imp_SHCreateDirectory
0x18001f901  test    eax, eax
0x18001f903  jz      short loc_18001F94D
0x18001f905  jg      short loc_18001F90B
0x18001f907  mov     ebx, eax
0x18001f909  jmp     short loc_18001F914
0x18001f90b  movzx   ebx, ax
0x18001f90e  or      ebx, 80070000h
0x18001f914  mov     r10, cs:WPP_GLOBAL_Control
0x18001f91b  cmp     r10, rdi
0x18001f91e  jz      short loc_18001F94D
0x18001f920  test    byte ptr [r10+1Ch], 2
0x18001f925  jz      short loc_18001F94D
0x18001f927  lea     rcx, [rsp+290h+var_250]; this
0x18001f92c  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18001f931  mov     rcx, [r10+10h]
0x18001f935  lea     r8, WPP_bafd4961db7d3885dd5128069fc3a0ad_Traceguids
0x18001f93c  mov     r9, rax
0x18001f93f  mov     [rsp+290h+var_270], ebx
0x18001f943  mov     edx, 31h ; '1'
0x18001f948  call    WPP_SF_Sd
0x18001f94d  mov     rcx, [rsp+290h+lpMem]; lpMem
0x18001f952  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x18001f957  lea     rcx, [rsp+290h+var_250]; this
0x18001f95c  call    ??1CPath@@QEAA@XZ; CPath::~CPath(void)
0x18001f961  mov     eax, ebx
0x18001f963  mov     rcx, [rbp+190h+var_10]
0x18001f96a  xor     rcx, rsp; StackCookie
0x18001f96d  call    __security_check_cookie
0x18001f972  lea     r11, [rsp+290h+var_s0]
0x18001f97a  mov     rbx, [r11+10h]
0x18001f97e  mov     rdi, [r11+20h]
0x18001f982  mov     rsp, r11
0x18001f985  pop     rbp
0x18001f986  retn
```
