# _CatDBCloseCachedDatabases(void)

- ea: `0x1800186e8`
- end: `0x1800187e5`
- name: `?_CatDBCloseCachedDatabases@@YAHXZ`
- size: `253`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001c620`

## callees

- `0x1800015b0`
- `0x18000a59c`
- `0x1800186e8`
- `0x1800187ec`
- `0x18001a230`
- `0x18001eeb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018704`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018704`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800187c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800187c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018769`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018769`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800187d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800187d0`

## pseudocode

```c
__int64 _CatDBCloseCachedDatabases(void)
{
  int v0; // r14d
  int v1; // r15d
  DWORD LastError; // ebp
  unsigned int v3; // edx
  unsigned __int16 *v4; // rcx
  _QWORD *v5; // rdi
  unsigned int v6; // ebx
  __int64 v7; // rsi
  unsigned int v8; // eax
  unsigned int v9; // edx
  unsigned __int16 *v10; // rcx
  __int64 v11; // rcx
  int v13; // [rsp+28h] [rbp-40h]

  v0 = 0;
  v1 = 0;
  LastError = 0;
  EnterCriticalSection(&g_CatDirCashCS);
  v5 = (_QWORD *)g_CatalogDBCacheList;
  v6 = 1;
  if ( g_CatalogDBCacheList )
  {
    do
    {
      v7 = v5[1];
      v5 = (_QWORD *)*v5;
      if ( *(_DWORD *)(v7 + 96) )
      {
        LastError = 1003;
        v0 = 1;
        ErrLog_LogError(v4, v3, 0x1246u, 0x3EBu, 0, v13);
      }
      else
      {
        v8 = _CatDBInstanceCount(*(const unsigned __int16 **)(v7 + 88));
        if ( !(unsigned int)_CatDBCloseDatabaseFile((struct _JET_DB_STRUCT *)v7, v8 == 1) )
        {
          v1 = 1;
          LastError = GetLastError();
          ErrLog_LogError(v10, v9, 0x1253u, LastError, 0, v13);
        }
        _CatDBFree(*(void **)v7);
        _CatDBFree(*(void **)(v7 + 88));
        LIST_RemoveElement(v11, v7);
        _CatDBFree((void *)v7);
      }
    }
    while ( v5 );
    if ( v0 )
      goto LABEL_10;
  }
  if ( v1 )
LABEL_10:
    v6 = 0;
  LeaveCriticalSection(&g_CatDirCashCS);
  if ( !v6 )
    SetLastError(LastError);
  return v6;
}

```

## disassembly

```asm
0x1800186e8  push    rbx
0x1800186ea  push    rbp
0x1800186eb  push    rsi
0x1800186ec  push    rdi
0x1800186ed  push    r14
0x1800186ef  push    r15
0x1800186f1  sub     rsp, 38h
0x1800186f5  lea     rcx, ?g_CatDirCashCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800186fc  xor     r14d, r14d
0x1800186ff  xor     r15d, r15d
0x180018702  xor     ebp, ebp
0x180018704  call    cs:__imp_EnterCriticalSection
0x18001870a  mov     rdi, qword ptr cs:?g_CatalogDBCacheList@@3ULIST_@@A; LIST_ g_CatalogDBCacheList
0x180018711  lea     ebx, [rbp+1]
0x180018714  test    rdi, rdi
0x180018717  jz      loc_1800187B6
0x18001871d  mov     rsi, [rdi+8]
0x180018721  mov     rdi, [rdi]
0x180018724  cmp     dword ptr [rsi+60h], 0
0x180018728  jz      short loc_18001874A
0x18001872a  mov     ebp, 3EBh
0x18001872f  mov     [rsp+68h+var_48], 0; int
0x180018737  mov     r9d, ebp; unsigned int
0x18001873a  mov     r8d, 1246h; unsigned int
0x180018740  mov     r14d, ebx
0x180018743  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180018748  jmp     short loc_1800187A8
0x18001874a  mov     rcx, [rsi+58h]; unsigned __int16 *
0x18001874e  call    ?_CatDBInstanceCount@@YAKPEBG@Z; _CatDBInstanceCount(ushort const *)
0x180018753  xor     edx, edx
0x180018755  mov     rcx, rsi; struct _JET_DB_STRUCT *
0x180018758  cmp     eax, ebx
0x18001875a  setz    dl; int
0x18001875d  call    ?_CatDBCloseDatabaseFile@@YAHPEAU_JET_DB_STRUCT@@H@Z; _CatDBCloseDatabaseFile(_JET_DB_STRUCT *,int)
0x180018762  test    eax, eax
0x180018764  jnz     short loc_180018787
0x180018766  mov     r15d, ebx
0x180018769  call    cs:__imp_GetLastError
0x18001876f  mov     r8d, 1253h; unsigned int
0x180018775  mov     [rsp+68h+var_48], 0; int
0x18001877d  mov     r9d, eax; unsigned int
0x180018780  mov     ebp, eax
0x180018782  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180018787  mov     rcx, [rsi]; void *
0x18001878a  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x18001878f  mov     rcx, [rsi+58h]; void *
0x180018793  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x180018798  mov     rdx, rsi
0x18001879b  call    LIST_RemoveElement
0x1800187a0  mov     rcx, rsi; void *
0x1800187a3  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x1800187a8  test    rdi, rdi
0x1800187ab  jnz     loc_18001871D
0x1800187b1  test    r14d, r14d
0x1800187b4  jnz     short loc_1800187BB
0x1800187b6  test    r15d, r15d
0x1800187b9  jz      short loc_1800187BD
0x1800187bb  xor     ebx, ebx
0x1800187bd  lea     rcx, ?g_CatDirCashCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800187c4  call    cs:__imp_LeaveCriticalSection
0x1800187ca  test    ebx, ebx
0x1800187cc  jnz     short loc_1800187D6
0x1800187ce  mov     ecx, ebp; dwErrCode
0x1800187d0  call    cs:__imp_SetLastError
0x1800187d6  mov     eax, ebx
0x1800187d8  add     rsp, 38h
0x1800187dc  pop     r15
0x1800187de  pop     r14
0x1800187e0  pop     rdi
0x1800187e1  pop     rsi
0x1800187e2  pop     rbp
0x1800187e3  pop     rbx
0x1800187e4  retn
```
