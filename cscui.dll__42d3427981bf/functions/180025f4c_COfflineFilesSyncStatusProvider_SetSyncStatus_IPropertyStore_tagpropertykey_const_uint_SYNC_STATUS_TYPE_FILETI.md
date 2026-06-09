# COfflineFilesSyncStatusProvider::_SetSyncStatus(IPropertyStore *,_tagpropertykey const *,uint,_SYNC_STATUS_TYPE,_FILETIME *)

- ea: `0x180025f4c`
- end: `0x18002620b`
- name: `?_SetSyncStatus@COfflineFilesSyncStatusProvider@@AEAAJPEAUIPropertyStore@@PEBU_tagpropertykey@@IW4_SYNC_STATUS_TYPE@@PEAU_FILETIME@@@Z`
- size: `703`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800251a0`
- `0x180025ba4`

## callees

- `0x180003a90`
- `0x180003c20`
- `0x18000ca18`
- `0x180024c44`
- `0x180025f4c`
- `0x180032204`
- `0x1800482d4`
- `0x18004c636`
- `0x18004c670`
- `0x18004d010`

## import_xrefs

- `SHLWAPI!__imp_SHFormatDateTimeW` at `0x18002606c`
- `SHLWAPI!__imp_SHFormatDateTimeW` at `0x18002606c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180025fcf`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180025fcf`

## pseudocode

```c
__int64 __fastcall COfflineFilesSyncStatusProvider::_SetSyncStatus(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        FILETIME *lpFileTime2)
{
  void *v7; // rdx
  int v8; // ebx
  int v9; // eax
  int v10; // eax
  void *v11; // r8
  unsigned int v12; // r14d
  __int64 v13; // rdi
  __int64 v14; // r15
  __int64 v15; // rcx
  __int128 *v16; // rdx
  __int64 v17; // rcx
  __int128 *v18; // rdx
  void *v19; // r8
  int v20; // eax
  __int64 v21; // rcx
  __int128 *v22; // rcx
  void *v23; // rdx
  void *v24; // rdx
  WCHAR Buffer[4]; // [rsp+20h] [rbp-E0h] BYREF
  void *lpMem; // [rsp+28h] [rbp-D8h] BYREF
  unsigned int v28; // [rsp+30h] [rbp-D0h]
  unsigned __int16 *v29; // [rsp+38h] [rbp-C8h] BYREF
  FILETIME FileTime1; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v31; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v32; // [rsp+58h] [rbp-A8h]
  __int64 v33; // [rsp+60h] [rbp-A0h]
  WCHAR pszBuf; // [rsp+70h] [rbp-90h] BYREF
  char v35[526]; // [rsp+72h] [rbp-8Eh] BYREF

  v33 = a3;
  v29 = 0;
  lpMem = 0;
  *(_QWORD *)Buffer = 0;
  pszBuf = 0;
  v28 = a4;
  memset_0(v35, 0, 0x206u);
  FileTime1 = 0;
  if ( !CompareFileTime(&FileTime1, lpFileTime2) )
  {
    v8 = CscUtil_FormatStringID(
           Buffer,
           g_hInstance,
           *((unsigned __int16 *)&COfflineFilesSyncStatusProvider::s_SyncStatusInfo + 8 * a5 - 6));
    if ( v8 < 0 )
      goto LABEL_12;
    v9 = CscUtil_FormatStringID(
           (LPWSTR)&lpMem,
           g_hInstance,
           *((unsigned __int16 *)&COfflineFilesSyncStatusProvider::s_SyncStatusInfo + 8 * a5 - 5));
    goto LABEL_11;
  }
  v8 = CscUtil_FormatStringID(
         Buffer,
         g_hInstance,
         *((unsigned __int16 *)&COfflineFilesSyncStatusProvider::s_SyncStatusInfo + 8 * a5 + 2));
  if ( v8 >= 0 )
  {
    v8 = CscUtil_FormatStringID(
           (LPWSTR)&lpMem,
           g_hInstance,
           *((unsigned __int16 *)&COfflineFilesSyncStatusProvider::s_SyncStatusInfo + 8 * a5 + 3));
    if ( v8 >= 0 )
    {
      if ( a5 != 1 )
        goto LABEL_13;
      if ( !lpFileTime2 )
        goto LABEL_13;
      v10 = SHFormatDateTimeW(lpFileTime2, 0, &pszBuf, 0x104u);
      if ( !v10 )
        goto LABEL_13;
      if ( (unsigned __int64)(2LL * v10) >= 0x208 )
        _report_rangecheckfailure();
      v11 = *(void **)Buffer;
      *(_WORD *)&v35[2 * v10 - 2] = 0;
      v9 = CscUtil_FormatString(&v29, L"%1 %2", v11, &pszBuf);
LABEL_11:
      v8 = v9;
    }
  }
LABEL_12:
  if ( v8 >= 0 )
  {
LABEL_13:
    v12 = v28;
    v13 = 0;
    v14 = v33;
    while ( 1 )
    {
      if ( (unsigned int)v13 >= v12 )
        goto LABEL_29;
      if ( (unsigned int)operator==(v14 + 20 * v13, &PKEY_Sync_ItemState) )
        break;
      if ( (unsigned int)operator==(v15, &PKEY_Sync_ItemStatusText) )
      {
        v18 = &PKEY_Sync_ItemStatusText;
        v19 = *(void **)Buffer;
        if ( v29 )
          v19 = v29;
      }
      else if ( (unsigned int)operator==(v17, &PKEY_Sync_ItemStatusDescription) )
      {
        v19 = lpMem;
        v18 = &PKEY_Sync_ItemStatusDescription;
      }
      else
      {
        if ( !(unsigned int)operator==(v21, &PKEY_Sync_ItemStatusAction) )
        {
          v31 = 0;
          v32 = 0;
          v16 = v22;
          goto LABEL_27;
        }
        v18 = &PKEY_Sync_ItemStatusAction;
        v19 = (void *)*((_QWORD *)&COfflineFilesSyncStatusProvider::s_SyncStatusInfo + 2 * a5 + 1);
      }
      v20 = IPropertyStore_SetString(a2, v18, v19);
LABEL_28:
      v13 = (unsigned int)(v13 + 1);
      v8 = v20;
      if ( v20 < 0 )
        goto LABEL_29;
    }
    v16 = &PKEY_Sync_ItemState;
    v32 = 0;
    v31 = 0;
    LOWORD(v31) = 19;
    DWORD2(v31) = *((_DWORD *)&COfflineFilesSyncStatusProvider::s_SyncStatusInfo + 4 * a5);
LABEL_27:
    v20 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int128 *))(*(_QWORD *)a2 + 48LL))(a2, v16, &v31);
    goto LABEL_28;
  }
LABEL_29:
  CscUtil_HeapFree(lpMem, v7);
  CscUtil_HeapFree(v29, v23);
  CscUtil_HeapFree(*(void **)Buffer, v24);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180025f4c  mov     [rsp-8+arg_0], rbx
0x180025f51  push    rbp
0x180025f52  push    rsi
0x180025f53  push    rdi
0x180025f54  push    r12
0x180025f56  push    r13
0x180025f58  push    r14
0x180025f5a  push    r15
0x180025f5c  lea     rbp, [rsp-190h]
0x180025f64  sub     rsp, 290h
0x180025f6b  mov     rax, cs:__security_cookie
0x180025f72  xor     rax, rsp
0x180025f75  mov     [rbp+1C0h+var_40], rax
0x180025f7c  movsxd  r15, [rbp+1C0h+arg_20]
0x180025f83  lea     rcx, [rsp+2C0h+var_24E]; void *
0x180025f88  mov     r14, [rbp+1C0h+lpFileTime2]
0x180025f8f  xor     ebx, ebx
0x180025f91  mov     [rsp+2C0h+var_260], r8
0x180025f96  mov     r12, rdx
0x180025f99  xor     edx, edx; Val
0x180025f9b  mov     [rsp+2C0h+var_288], rbx
0x180025fa0  mov     r8d, 206h; Size
0x180025fa6  mov     [rsp+2C0h+lpMem], rbx
0x180025fab  mov     qword ptr [rsp+2C0h+Buffer], rbx
0x180025fb0  mov     [rsp+2C0h+pszBuf], bx
0x180025fb5  mov     [rsp+2C0h+var_290], r9d
0x180025fba  call    memset_0
0x180025fbf  mov     rdx, r14; lpFileTime2
0x180025fc2  mov     qword ptr [rsp+2C0h+FileTime1.dwLowDateTime], rbx
0x180025fc7  lea     rcx, [rsp+2C0h+FileTime1]; lpFileTime1
0x180025fcc  mov     r13, r15
0x180025fcf  call    cs:__imp_CompareFileTime
0x180025fd5  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180025fdc  lea     rsi, ?s_SyncStatusInfo@COfflineFilesSyncStatusProvider@@0QBUSYNCSTATUSINFO@1@B; COfflineFilesSyncStatusProvider::SYNCSTATUSINFO const near * const COfflineFilesSyncStatusProvider::s_SyncStatusInfo
0x180025fe3  mov     rdi, r15
0x180025fe6  lea     rcx, [rsp+2C0h+Buffer]; lpBuffer
0x180025feb  add     rdi, rdi
0x180025fee  test    eax, eax
0x180025ff0  jnz     short loc_180026023
0x180025ff2  movzx   r8d, word ptr [rsi+rdi*8-0Ch]; uID
0x180025ff8  call    ?CscUtil_FormatStringID@@YAJPEAPEAGPEAUHINSTANCE__@@IZZ; CscUtil_FormatStringID(ushort * *,HINSTANCE__ *,uint,...)
0x180025ffd  mov     ebx, eax
0x180025fff  test    eax, eax
0x180026001  js      loc_1800260AD
0x180026007  movzx   r8d, word ptr [rsi+rdi*8-0Ah]; uID
0x18002600d  lea     rcx, [rsp+2C0h+lpMem]; lpBuffer
0x180026012  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180026019  call    ?CscUtil_FormatStringID@@YAJPEAPEAGPEAUHINSTANCE__@@IZZ; CscUtil_FormatStringID(ushort * *,HINSTANCE__ *,uint,...)
0x18002601e  jmp     loc_1800260AB
0x180026023  movzx   r8d, word ptr [rsi+rdi*8+4]; uID
0x180026029  call    ?CscUtil_FormatStringID@@YAJPEAPEAGPEAUHINSTANCE__@@IZZ; CscUtil_FormatStringID(ushort * *,HINSTANCE__ *,uint,...)
0x18002602e  mov     ebx, eax
0x180026030  test    eax, eax
0x180026032  js      short loc_1800260AD
0x180026034  movzx   r8d, word ptr [rsi+rdi*8+6]; uID
0x18002603a  lea     rcx, [rsp+2C0h+lpMem]; lpBuffer
0x18002603f  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180026046  call    ?CscUtil_FormatStringID@@YAJPEAPEAGPEAUHINSTANCE__@@IZZ; CscUtil_FormatStringID(ushort * *,HINSTANCE__ *,uint,...)
0x18002604b  mov     ebx, eax
0x18002604d  test    eax, eax
0x18002604f  js      short loc_1800260AD
0x180026051  cmp     r15d, 1
0x180026055  jnz     short loc_1800260B5
0x180026057  test    r14, r14
0x18002605a  jz      short loc_1800260B5
0x18002605c  mov     r9d, 104h; cchBuf
0x180026062  lea     r8, [rsp+2C0h+pszBuf]; pszBuf
0x180026067  xor     edx, edx; pdwFlags
0x180026069  mov     rcx, r14; pft
0x18002606c  call    cs:__imp_SHFormatDateTimeW
0x180026072  test    eax, eax
0x180026074  jz      short loc_1800260B5
0x180026076  cdqe
0x180026078  lea     rcx, [rax+rax]
0x18002607c  cmp     rcx, 208h
0x180026083  jnb     loc_180026114
0x180026089  mov     r8, qword ptr [rsp+2C0h+Buffer]
0x18002608e  lea     r9, [rsp+2C0h+pszBuf]
0x180026093  xor     eax, eax
0x180026095  lea     rdx, a12_0; "%1 %2"
0x18002609c  mov     [rsp+rcx+2C0h+pszBuf], ax
0x1800260a1  lea     rcx, [rsp+2C0h+var_288]; unsigned __int16 **
0x1800260a6  call    ?CscUtil_FormatString@@YAJPEAPEAGPEBGZZ; CscUtil_FormatString(ushort * *,ushort const *,...)
0x1800260ab  mov     ebx, eax
0x1800260ad  test    ebx, ebx
0x1800260af  js      loc_1800261C1
0x1800260b5  mov     r14d, [rsp+2C0h+var_290]
0x1800260ba  xor     edi, edi
0x1800260bc  mov     r15, [rsp+2C0h+var_260]
0x1800260c1  cmp     edi, r14d
0x1800260c4  jnb     loc_1800261C1
0x1800260ca  lea     rcx, [rdi+rdi*4]
0x1800260ce  lea     rcx, [r15+rcx*4]
0x1800260d2  lea     rdx, PKEY_Sync_ItemState
0x1800260d9  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x1800260de  test    eax, eax
0x1800260e0  jz      short loc_18002611A
0x1800260e2  xor     eax, eax
0x1800260e4  lea     rdx, PKEY_Sync_ItemState
0x1800260eb  mov     [rsp+2C0h+var_268], rax
0x1800260f0  xorps   xmm0, xmm0
0x1800260f3  mov     eax, 13h
0x1800260f8  movups  [rsp+2C0h+var_278], xmm0
0x1800260fd  mov     word ptr [rsp+2C0h+var_278], ax
0x180026102  mov     rax, r13
0x180026105  add     rax, rax
0x180026108  mov     eax, [rsi+rax*8]
0x18002610b  mov     dword ptr [rsp+2C0h+var_278+8], eax
0x18002610f  jmp     loc_1800261A0
0x180026114  call    __report_rangecheckfailure
0x18002611a  lea     rdx, PKEY_Sync_ItemStatusText
0x180026121  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x180026126  test    eax, eax
0x180026128  jz      short loc_18002614C
0x18002612a  mov     rax, [rsp+2C0h+var_288]
0x18002612f  lea     rdx, PKEY_Sync_ItemStatusText
0x180026136  mov     r8, qword ptr [rsp+2C0h+Buffer]
0x18002613b  test    rax, rax
0x18002613e  cmovnz  r8, rax
0x180026142  mov     rcx, r12
0x180026145  call    IPropertyStore_SetString
0x18002614a  jmp     short loc_1800261B5
0x18002614c  lea     rdx, PKEY_Sync_ItemStatusDescription
0x180026153  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x180026158  test    eax, eax
0x18002615a  jz      short loc_18002616A
0x18002615c  mov     r8, [rsp+2C0h+lpMem]
0x180026161  lea     rdx, PKEY_Sync_ItemStatusDescription
0x180026168  jmp     short loc_180026142
0x18002616a  lea     rdx, PKEY_Sync_ItemStatusAction
0x180026171  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x180026176  test    eax, eax
0x180026178  jz      short loc_18002618E
0x18002617a  mov     r8, r13
0x18002617d  lea     rdx, PKEY_Sync_ItemStatusAction
0x180026184  add     r8, r8
0x180026187  mov     r8, [rsi+r8*8+8]
0x18002618c  jmp     short loc_180026142
0x18002618e  xorps   xmm0, xmm0
0x180026191  xor     eax, eax
0x180026193  movups  [rsp+2C0h+var_278], xmm0
0x180026198  mov     [rsp+2C0h+var_268], rax
0x18002619d  mov     rdx, rcx
0x1800261a0  mov     rax, [r12]
0x1800261a4  lea     r8, [rsp+2C0h+var_278]
0x1800261a9  mov     rcx, r12
0x1800261ac  mov     rax, [rax+30h]
0x1800261b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800261b5  inc     edi
0x1800261b7  mov     ebx, eax
0x1800261b9  test    eax, eax
0x1800261bb  jns     loc_1800260C1
0x1800261c1  mov     rcx, [rsp+2C0h+lpMem]; lpMem
0x1800261c6  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x1800261cb  mov     rcx, [rsp+2C0h+var_288]; lpMem
0x1800261d0  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x1800261d5  mov     rcx, qword ptr [rsp+2C0h+Buffer]; lpMem
0x1800261da  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x1800261df  mov     eax, ebx
0x1800261e1  mov     rcx, [rbp+1C0h+var_40]
0x1800261e8  xor     rcx, rsp; StackCookie
0x1800261eb  call    __security_check_cookie
0x1800261f0  mov     rbx, [rsp+2C0h+arg_0]
0x1800261f8  add     rsp, 290h
0x1800261ff  pop     r15
0x180026201  pop     r14
0x180026203  pop     r13
0x180026205  pop     r12
0x180026207  pop     rdi
0x180026208  pop     rsi
0x180026209  pop     rbp
0x18002620a  retn
```
