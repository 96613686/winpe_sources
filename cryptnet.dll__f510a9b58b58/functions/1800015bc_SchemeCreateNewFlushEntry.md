# SchemeCreateNewFlushEntry

- ea: `0x1800015bc`
- end: `0x180001791`
- name: `SchemeCreateNewFlushEntry`
- size: `469`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000b090`

## callees

- `0x1800015bc`
- `0x180001798`
- `0x18000195c`
- `0x180002810`
- `0x180002a90`
- `0x180005900`
- `0x18000a990`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180001738`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180001738`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000170d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001721`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000170d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001721`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000164b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800016f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000164b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800016f0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800016e1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800016e1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000163c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000163c`

## pseudocode

```c
__int64 __fastcall SchemeCreateNewFlushEntry(const void *a1, __int64 a2)
{
  WCHAR *v4; // rbp
  void *v5; // rbx
  unsigned __int16 *CryptnetFlushCacheDir; // r14
  unsigned int v7; // edi
  const WCHAR *CacheFileName; // rax
  DWORD LastError; // eax
  __int64 v11; // rsi
  HANDLE FileW; // rax
  DWORD v13; // eax
  __int128 v14; // [rsp+40h] [rbp-98h] BYREF
  _BYTE v15[80]; // [rsp+50h] [rbp-88h] BYREF

  v4 = 0;
  v5 = 0;
  CryptnetFlushCacheDir = I_SchemeGetCryptnetFlushCacheDir();
  if ( !CryptnetFlushCacheDir )
    goto LABEL_17;
  I_UrlCacheGetUrlFileName(a1, v15);
  v7 = 1;
  CacheFileName = (const WCHAR *)I_UrlCacheGetCacheFileName(CryptnetFlushCacheDir, L"MetaData", 0, 1);
  v4 = (WCHAR *)CacheFileName;
  if ( !CacheFileName )
    goto LABEL_17;
  if ( GetFileAttributesW(CacheFileName) != -1 )
  {
    SetLastError(0x50u);
LABEL_17:
    v7 = 0;
    goto LABEL_7;
  }
  LastError = GetLastError();
  if ( (LastError & 0xFFFFFFFC) != 0 || LastError == 1 )
    goto LABEL_17;
  if ( a2 )
  {
    v11 = 0;
    v14 = 0;
    while ( 1 )
    {
      FileW = CreateFileW(v4, 0xC0000000, 0, 0, 4u, 4u, 0);
      v5 = FileW;
      if ( FileW != (HANDLE)-1LL )
        break;
      v13 = GetLastError();
      if ( v13 != 32 || (unsigned int)v11 >= 6 )
      {
        if ( v13 != 5 )
        {
          if ( v13 == 3 )
            v13 = 2;
LABEL_16:
          SetLastError(v13);
          v5 = 0;
          goto LABEL_17;
        }
        if ( (_DWORD)v11 )
          goto LABEL_16;
      }
      Sleep(*((_DWORD *)qword_18002BA20 + v11));
      v11 = (unsigned int)(v11 + 1);
    }
    if ( !FileW || !(unsigned int)I_UrlCacheWriteCryptBlobArray2(a1, FileW, 0, &v14, a2, 0, 0) )
      goto LABEL_17;
  }
LABEL_7:
  operator delete(CryptnetFlushCacheDir);
  operator delete(v4);
  if ( v5 )
    I_UrlCacheCloseHandle(v5);
  return v7;
}

```

## disassembly

```asm
0x1800015bc  mov     [rsp+arg_10], rbx
0x1800015c1  mov     [rsp+arg_18], rbp
0x1800015c6  push    rsi
0x1800015c7  push    rdi
0x1800015c8  push    r12
0x1800015ca  push    r14
0x1800015cc  push    r15
0x1800015ce  sub     rsp, 0B0h
0x1800015d5  mov     rax, cs:__security_cookie
0x1800015dc  xor     rax, rsp
0x1800015df  mov     [rsp+0D8h+var_38], rax
0x1800015e7  mov     r15, rdx
0x1800015ea  mov     r12, rcx
0x1800015ed  xor     ebp, ebp
0x1800015ef  xor     ebx, ebx
0x1800015f1  call    ?I_SchemeGetCryptnetFlushCacheDir@@YAPEAGXZ; I_SchemeGetCryptnetFlushCacheDir(void)
0x1800015f6  mov     r14, rax
0x1800015f9  test    rax, rax
0x1800015fc  jz      loc_180001715
0x180001602  lea     rdx, [rsp+0D8h+var_88]
0x180001607  mov     rcx, r12
0x18000160a  call    I_UrlCacheGetUrlFileName
0x18000160f  lea     edi, [rbp+1]
0x180001612  xor     r8d, r8d; void *
0x180001615  lea     r9, [rsp+0D8h+var_88]
0x18000161a  mov     [rsp+0D8h+dwCreationDisposition], edi; int
0x18000161e  lea     rdx, aMetadata; "MetaData"
0x180001625  mov     rcx, r14; Src
0x180001628  call    I_UrlCacheGetCacheFileName
0x18000162d  mov     rbp, rax
0x180001630  test    rax, rax
0x180001633  jz      loc_180001715
0x180001639  mov     rcx, rax; lpFileName
0x18000163c  call    cs:__imp_GetFileAttributesW
0x180001642  cmp     eax, 0FFFFFFFFh
0x180001645  jnz     loc_18000171C
0x18000164b  call    cs:__imp_GetLastError
0x180001651  test    eax, 0FFFFFFFCh
0x180001656  jnz     loc_180001715
0x18000165c  cmp     eax, edi
0x18000165e  jz      loc_180001715
0x180001664  test    r15, r15
0x180001667  jnz     short loc_1800016B0
0x180001669  mov     rcx, r14; hMem
0x18000166c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001671  mov     rcx, rbp; hMem
0x180001674  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001679  test    rbx, rbx
0x18000167c  jnz     loc_180001784
0x180001682  mov     eax, edi
0x180001684  mov     rcx, [rsp+0D8h+var_38]
0x18000168c  xor     rcx, rsp; StackCookie
0x18000168f  call    __security_check_cookie
0x180001694  lea     r11, [rsp+0D8h+var_28]
0x18000169c  mov     rbx, [r11+40h]
0x1800016a0  mov     rbp, [r11+48h]
0x1800016a4  mov     rsp, r11
0x1800016a7  pop     r15
0x1800016a9  pop     r14
0x1800016ab  pop     r12
0x1800016ad  pop     rdi
0x1800016ae  pop     rsi
0x1800016af  retn
0x1800016b0  xorps   xmm0, xmm0
0x1800016b3  xor     esi, esi
0x1800016b5  movups  [rsp+0D8h+var_98], xmm0
0x1800016ba  mov     [rsp+0D8h+hTemplateFile], 0; hTemplateFile
0x1800016c3  xor     r9d, r9d; lpSecurityAttributes
0x1800016c6  mov     [rsp+0D8h+dwFlagsAndAttributes], 4; dwFlagsAndAttributes
0x1800016ce  xor     r8d, r8d; dwShareMode
0x1800016d1  mov     edx, 0C0000000h; dwDesiredAccess
0x1800016d6  mov     [rsp+0D8h+dwCreationDisposition], 4; dwCreationDisposition
0x1800016de  mov     rcx, rbp; lpFileName
0x1800016e1  call    cs:__imp_CreateFileW
0x1800016e7  mov     rbx, rax
0x1800016ea  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800016ee  jnz     short loc_18000174B
0x1800016f0  call    cs:__imp_GetLastError
0x1800016f6  cmp     eax, 20h ; ' '
0x1800016f9  jz      short loc_180001729
0x1800016fb  cmp     eax, 5
0x1800016fe  jz      short loc_180001745
0x180001700  cmp     eax, 3
0x180001703  mov     ecx, 2
0x180001708  cmovz   eax, ecx
0x18000170b  mov     ecx, eax; dwErrCode
0x18000170d  call    cs:__imp_SetLastError
0x180001713  xor     ebx, ebx
0x180001715  xor     edi, edi
0x180001717  jmp     loc_180001669
0x18000171c  mov     ecx, 50h ; 'P'; dwErrCode
0x180001721  call    cs:__imp_SetLastError
0x180001727  jmp     short loc_180001715
0x180001729  cmp     esi, 6
0x18000172c  jnb     short loc_1800016FB
0x18000172e  lea     rax, qword_18002BA20
0x180001735  mov     ecx, [rax+rsi*4]; dwMilliseconds
0x180001738  call    cs:__imp_Sleep
0x18000173e  add     esi, edi
0x180001740  jmp     loc_1800016BA
0x180001745  cmp     esi, edi
0x180001747  jb      short loc_18000172E
0x180001749  jmp     short loc_18000170B
0x18000174b  test    rax, rax
0x18000174e  jz      short loc_180001715
0x180001750  mov     [rsp+0D8h+hTemplateFile], 0
0x180001759  lea     r9, [rsp+0D8h+var_98]
0x18000175e  mov     qword ptr [rsp+0D8h+dwFlagsAndAttributes], 0
0x180001767  xor     r8d, r8d
0x18000176a  mov     rdx, rax
0x18000176d  mov     qword ptr [rsp+0D8h+dwCreationDisposition], r15
0x180001772  mov     rcx, r12
0x180001775  call    I_UrlCacheWriteCryptBlobArray2
0x18000177a  test    eax, eax
0x18000177c  jnz     loc_180001669
0x180001782  jmp     short loc_180001715
0x180001784  mov     rcx, rbx; hObject
0x180001787  call    I_UrlCacheCloseHandle
0x18000178c  jmp     loc_180001682
```
