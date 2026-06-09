# CMakeAvailableCmdStateHandler::_CanAllFilesBePinned(IDataObject *)

- ea: `0x18002b290`
- end: `0x18002b552`
- name: `?_CanAllFilesBePinned@CMakeAvailableCmdStateHandler@@AEAAJPEAUIDataObject@@@Z`
- size: `706`
- prototype: `int(CMakeAvailableCmdStateHandler *__hidden this, struct IDataObject *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180027ea0`

## callees

- `0x180003d60`
- `0x180010ff4`
- `0x18001101c`
- `0x180013d9c`
- `0x18002b290`
- `0x18003ae4c`
- `0x18003ae7c`
- `0x18003d4c0`
- `0x18003f0c8`
- `0x18003f81c`
- `0x18003f848`
- `0x18004c670`

## import_xrefs

- `SHLWAPI!PathAddBackslashW` at `0x18002b3b7`
- `SHLWAPI!PathAddBackslashW` at `0x18002b3b7`
- `USER32!LoadCursorW` at `0x18002b31d`
- `USER32!LoadCursorW` at `0x18002b31d`
- `USER32!SetCursor` at `0x18002b326`
- `USER32!SetCursor` at `0x18002b4e4`
- `USER32!SetCursor` at `0x18002b326`
- `USER32!SetCursor` at `0x18002b4e4`

## pseudocode

```c
__int64 __fastcall CMakeAvailableCmdStateHandler::_CanAllFilesBePinned(
        CMakeAvailableCmdStateHandler *this,
        struct IDataObject *a2)
{
  CNoPinList *v4; // r15
  unsigned int v5; // esi
  int v6; // edi
  HCURSOR CursorW; // rax
  HCURSOR v8; // r12
  __int64 v9; // rbx
  __int64 v10; // r9
  const unsigned __int16 *v11; // rax
  int v12; // r9d
  unsigned __int64 v13; // rbx
  unsigned __int16 *v14; // r14
  __int64 v15; // rax
  WCHAR *i; // rcx
  int v18[2]; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v19[2]; // [rsp+28h] [rbp-D8h] BYREF
  char v20; // [rsp+38h] [rbp-C8h]
  HCURSOR v21; // [rsp+40h] [rbp-C0h]
  __int64 v22; // [rsp+48h] [rbp-B8h] BYREF
  int v23; // [rsp+50h] [rbp-B0h]
  _QWORD *v24; // [rsp+58h] [rbp-A8h] BYREF
  int v25; // [rsp+60h] [rbp-A0h]
  _BYTE v26[2]; // [rsp+6Eh] [rbp-92h] BYREF
  WCHAR pszPath[264]; // [rsp+70h] [rbp-90h] BYREF

  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_d6b627e249a03c7d4470f53aabba48a7_Traceguids);
  }
  v4 = (CMakeAvailableCmdStateHandler *)((char *)this + 112);
  v5 = 0;
  if ( (unsigned int)CNoPinList::IsAnyPinDisallowed((CMakeAvailableCmdStateHandler *)((char *)this + 112)) == 1 )
  {
    v6 = 0;
  }
  else
  {
    CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
    v19[0] = 0;
    v21 = SetCursor(CursorW);
    v19[1] = 0;
    v8 = v21;
    v20 = 1;
    v18[0] = 0;
    v6 = SyncContext_BuildFileListFromShellItemIDs(a2, (struct CscFilenameList *)v19, v18);
    if ( v6 >= 0 )
    {
      v25 = 0;
      v24 = v19;
      v6 = 0;
      *(_QWORD *)v18 = 0;
      while ( CscFilenameList::ShareIter::Next(
                (CscFilenameList::ShareIter *)&v24,
                (struct CscFilenameList::HSHARE *)v18) )
      {
        v9 = *(_QWORD *)v18;
        if ( (int)StringCchCopyW(pszPath, 0x104u, *(const unsigned __int16 **)(*(_QWORD *)v18 + 16LL)) < 0
          || !PathAddBackslashW(pszPath) )
        {
          v6 = -2147024690;
          break;
        }
        v6 = 0;
        v10 = -1;
        do
          ++v10;
        while ( pszPath[v10] );
        v22 = v9;
        v23 = 0;
        v11 = CscFilenameList::FileIter::Next((CscFilenameList::FileIter *)&v22);
        if ( v11 )
        {
          v13 = 260LL - v12;
          v14 = &pszPath[v12];
          do
          {
            if ( (int)StringCchCopyW(v14, v13, v11) >= 0 )
            {
              v6 = 0;
              v15 = -1;
              do
                ++v15;
              while ( pszPath[v15] );
              for ( i = (WCHAR *)&v26[2 * v15]; i > pszPath && (*i == 92 || *i == 42); --i )
                *i = 0;
              if ( CNoPinList::IsPinAllowed(v4, pszPath) == 1 )
              {
                if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
                {
                  WPP_SF_S(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    30,
                    WPP_d6b627e249a03c7d4470f53aabba48a7_Traceguids,
                    pszPath);
                }
                v5 = 1;
              }
            }
            else
            {
              v6 = -2147024690;
            }
            v11 = CscFilenameList::FileIter::Next((CscFilenameList::FileIter *)&v22);
          }
          while ( v11 );
          v8 = v21;
          if ( v6 )
            break;
        }
      }
    }
    SetCursor(v8);
    CscFilenameList::~CscFilenameList((CscFilenameList *)v19);
  }
  if ( v6 < 0 )
    v5 = v6;
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_d6b627e249a03c7d4470f53aabba48a7_Traceguids, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x18002b290  mov     [rsp-8+arg_10], rbx
0x18002b295  push    rbp
0x18002b296  push    rsi
0x18002b297  push    rdi
0x18002b298  push    r12
0x18002b29a  push    r13
0x18002b29c  push    r14
0x18002b29e  push    r15
0x18002b2a0  lea     rbp, [rsp-190h]
0x18002b2a8  sub     rsp, 290h
0x18002b2af  mov     rax, cs:__security_cookie
0x18002b2b6  xor     rax, rsp
0x18002b2b9  mov     [rbp+1C0h+var_40], rax
0x18002b2c0  mov     rdi, rdx
0x18002b2c3  mov     rbx, rcx
0x18002b2c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b2cd  lea     r14, WPP_GLOBAL_Control
0x18002b2d4  cmp     rcx, r14
0x18002b2d7  jz      short loc_18002B2F7
0x18002b2d9  test    dword ptr [rcx+1Ch], 4000000h
0x18002b2e0  jz      short loc_18002B2F7
0x18002b2e2  mov     rcx, [rcx+10h]
0x18002b2e6  lea     r8, WPP_d6b627e249a03c7d4470f53aabba48a7_Traceguids
0x18002b2ed  mov     edx, 1Dh
0x18002b2f2  call    WPP_SF_
0x18002b2f7  lea     r15, [rbx+70h]
0x18002b2fb  xor     r13d, r13d
0x18002b2fe  mov     rcx, r15; this
0x18002b301  mov     esi, r13d
0x18002b304  call    ?IsAnyPinDisallowed@CNoPinList@@QEAAJXZ; CNoPinList::IsAnyPinDisallowed(void)
0x18002b309  cmp     eax, 1
0x18002b30c  jnz     short loc_18002B316
0x18002b30e  mov     edi, r13d
0x18002b311  jmp     loc_18002B4F4
0x18002b316  mov     edx, 7F02h; lpCursorName
0x18002b31b  xor     ecx, ecx; hInstance
0x18002b31d  call    cs:__imp_LoadCursorW
0x18002b323  mov     rcx, rax; hCursor
0x18002b326  call    cs:__imp_SetCursor
0x18002b32c  lea     r8, [rsp+2C0h+var_2A0]; int *
0x18002b331  mov     [rsp+2C0h+var_298], r13
0x18002b336  lea     rdx, [rsp+2C0h+var_298]; this
0x18002b33b  mov     [rsp+2C0h+var_280], rax
0x18002b340  mov     rcx, rdi; struct IDataObject *
0x18002b343  mov     [rsp+2C0h+var_290], r13
0x18002b348  mov     r12, rax
0x18002b34b  mov     [rsp+2C0h+var_288], 1
0x18002b350  mov     [rsp+2C0h+var_2A0], r13d
0x18002b355  call    ?SyncContext_BuildFileListFromShellItemIDs@@YAJPEAUIDataObject@@PEAVCscFilenameList@@PEAH@Z; SyncContext_BuildFileListFromShellItemIDs(IDataObject *,CscFilenameList *,int *)
0x18002b35a  mov     edi, eax
0x18002b35c  test    eax, eax
0x18002b35e  js      loc_18002B4E1
0x18002b364  lea     rax, [rsp+2C0h+var_298]
0x18002b369  mov     [rsp+2C0h+var_260], r13d
0x18002b36e  mov     [rsp+2C0h+var_268], rax
0x18002b373  mov     edi, r13d
0x18002b376  mov     qword ptr [rsp+2C0h+var_2A0], r13
0x18002b37b  lea     rdx, [rsp+2C0h+var_2A0]; struct CscFilenameList::HSHARE *
0x18002b380  lea     rcx, [rsp+2C0h+var_268]; this
0x18002b385  call    ?Next@ShareIter@CscFilenameList@@QEAA_NPEAVHSHARE@2@@Z; CscFilenameList::ShareIter::Next(CscFilenameList::HSHARE *)
0x18002b38a  test    al, al
0x18002b38c  jz      loc_18002B4DA
0x18002b392  mov     rbx, qword ptr [rsp+2C0h+var_2A0]
0x18002b397  lea     rcx, [rsp+2C0h+pszPath]; unsigned __int16 *
0x18002b39c  mov     edx, 104h; unsigned __int64
0x18002b3a1  mov     r8, [rbx+10h]; unsigned __int16 *
0x18002b3a5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002b3aa  test    eax, eax
0x18002b3ac  js      loc_18002B4D5
0x18002b3b2  lea     rcx, [rsp+2C0h+pszPath]; pszPath
0x18002b3b7  call    cs:__imp_PathAddBackslashW
0x18002b3bd  test    rax, rax
0x18002b3c0  jz      loc_18002B4D5
0x18002b3c6  mov     edi, r13d
0x18002b3c9  lea     rax, [rsp+2C0h+pszPath]
0x18002b3ce  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002b3d2  inc     r9
0x18002b3d5  cmp     [rax+r9*2], r13w
0x18002b3da  jnz     short loc_18002B3D2
0x18002b3dc  lea     rcx, [rsp+2C0h+var_278]; this
0x18002b3e1  mov     [rsp+2C0h+var_278], rbx
0x18002b3e6  mov     [rsp+2C0h+var_270], r13d
0x18002b3eb  call    ?Next@FileIter@CscFilenameList@@QEAAPEBGXZ; CscFilenameList::FileIter::Next(void)
0x18002b3f0  test    rax, rax
0x18002b3f3  jz      short loc_18002B37B
0x18002b3f5  movsxd  rcx, r9d
0x18002b3f8  lea     r14, [rsp+2C0h+pszPath]
0x18002b3fd  mov     ebx, 104h
0x18002b402  lea     r12, WPP_GLOBAL_Control
0x18002b409  sub     rbx, rcx
0x18002b40c  lea     r14, [r14+rcx*2]
0x18002b410  mov     r8, rax; unsigned __int16 *
0x18002b413  mov     rdx, rbx; unsigned __int64
0x18002b416  mov     rcx, r14; unsigned __int16 *
0x18002b419  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002b41e  test    eax, eax
0x18002b420  jns     short loc_18002B42C
0x18002b422  mov     edi, 800700CEh
0x18002b427  jmp     loc_18002B4B3
0x18002b42c  mov     edi, r13d
0x18002b42f  lea     rcx, [rsp+2C0h+pszPath]
0x18002b434  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b438  inc     rax
0x18002b43b  cmp     [rcx+rax*2], r13w
0x18002b440  jnz     short loc_18002B438
0x18002b442  lea     rcx, [rsp+rax*2+2C0h+var_252]
0x18002b447  jmp     short loc_18002B465
0x18002b449  mov     eax, 5Ch ; '\'
0x18002b44e  cmp     ax, [rcx]
0x18002b451  jz      short loc_18002B45D
0x18002b453  mov     eax, 2Ah ; '*'
0x18002b458  cmp     ax, [rcx]
0x18002b45b  jnz     short loc_18002B46F
0x18002b45d  mov     [rcx], r13w
0x18002b461  sub     rcx, 2
0x18002b465  lea     rax, [rsp+2C0h+pszPath]
0x18002b46a  cmp     rcx, rax
0x18002b46d  ja      short loc_18002B449
0x18002b46f  lea     rdx, [rsp+2C0h+pszPath]; unsigned __int16 *
0x18002b474  mov     rcx, r15; this
0x18002b477  call    ?IsPinAllowed@CNoPinList@@QEAAJPEBG@Z; CNoPinList::IsPinAllowed(ushort const *)
0x18002b47c  cmp     eax, 1
0x18002b47f  jnz     short loc_18002B4B3
0x18002b481  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b488  cmp     rcx, r12
0x18002b48b  jz      short loc_18002B4AE
0x18002b48d  test    dword ptr [rcx+1Ch], 4000000h
0x18002b494  jz      short loc_18002B4AE
0x18002b496  mov     rcx, [rcx+10h]
0x18002b49a  lea     edx, [rax+1Dh]
0x18002b49d  lea     r9, [rsp+2C0h+pszPath]
0x18002b4a2  lea     r8, WPP_d6b627e249a03c7d4470f53aabba48a7_Traceguids
0x18002b4a9  call    WPP_SF_S
0x18002b4ae  mov     esi, 1
0x18002b4b3  lea     rcx, [rsp+2C0h+var_278]; this
0x18002b4b8  call    ?Next@FileIter@CscFilenameList@@QEAAPEBGXZ; CscFilenameList::FileIter::Next(void)
0x18002b4bd  test    rax, rax
0x18002b4c0  jnz     loc_18002B410
0x18002b4c6  mov     r12, [rsp+2C0h+var_280]
0x18002b4cb  test    edi, edi
0x18002b4cd  jz      loc_18002B37B
0x18002b4d3  jmp     short loc_18002B4DA
0x18002b4d5  mov     edi, 800700CEh
0x18002b4da  lea     r14, WPP_GLOBAL_Control
0x18002b4e1  mov     rcx, r12; hCursor
0x18002b4e4  call    cs:__imp_SetCursor
0x18002b4ea  lea     rcx, [rsp+2C0h+var_298]; this
0x18002b4ef  call    ??1CscFilenameList@@QEAA@XZ; CscFilenameList::~CscFilenameList(void)
0x18002b4f4  test    edi, edi
0x18002b4f6  cmovs   esi, edi
0x18002b4f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b500  cmp     rcx, r14
0x18002b503  jz      short loc_18002B526
0x18002b505  test    dword ptr [rcx+1Ch], 4000000h
0x18002b50c  jz      short loc_18002B526
0x18002b50e  mov     rcx, [rcx+10h]
0x18002b512  lea     r8, WPP_d6b627e249a03c7d4470f53aabba48a7_Traceguids
0x18002b519  mov     edx, 1Fh
0x18002b51e  mov     r9d, esi
0x18002b521  call    WPP_SF_d
0x18002b526  mov     eax, esi
0x18002b528  mov     rcx, [rbp+1C0h+var_40]
0x18002b52f  xor     rcx, rsp; StackCookie
0x18002b532  call    __security_check_cookie
0x18002b537  mov     rbx, [rsp+2C0h+arg_10]
0x18002b53f  add     rsp, 290h
0x18002b546  pop     r15
0x18002b548  pop     r14
0x18002b54a  pop     r13
0x18002b54c  pop     r12
0x18002b54e  pop     rdi
0x18002b54f  pop     rsi
0x18002b550  pop     rbp
0x18002b551  retn
```
