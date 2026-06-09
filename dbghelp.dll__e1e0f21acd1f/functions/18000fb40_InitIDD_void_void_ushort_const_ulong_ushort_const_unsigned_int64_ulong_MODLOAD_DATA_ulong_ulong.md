# InitIDD(void *,void *,ushort const *,ulong,ushort const *,unsigned __int64,ulong,_MODLOAD_DATA *,ulong,ulong)

- ea: `0x18000fb40`
- end: `0x18000fe4b`
- name: `?InitIDD@@YAPEAU_IMGHLP_DEBUG_DATA@@PEAX0PEBGK1_KKPEAU_MODLOAD_DATA@@KK@Z`
- size: `779`
- prototype: `struct _IMGHLP_DEBUG_DATA *__usercall@<rax>(void *@<rcx>, HANDLE hFile@<rdx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, wchar_t *Source, unsigned __int64, unsigned int, struct _MODLOAD_DATA *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `10`
- tags: `reparse_path`

## callers

- `0x1800091a0`
- `0x18000f380`

## callees

- `0x1800089f0`
- `0x180008a38`
- `0x180008ad0`
- `0x18000aeec`
- `0x18000fb40`
- `0x1800102e4`
- `0x180012e6c`
- `0x180027430`
- `0x180169408`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18000fd34`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18000fd34`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000fd6b`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000fd6b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fbab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fbd2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fbab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fbd2`

## pseudocode

```c
struct _IMGHLP_DEBUG_DATA *__fastcall InitIDD(
        void *a1,
        char *hFile,
        const unsigned __int16 *a3,
        int a4,
        wchar_t *Source,
        unsigned __int64 a6,
        unsigned int a7,
        struct _MODLOAD_DATA *a8,
        unsigned int a9)
{
  __int64 v13; // rax
  __int64 v14; // rbx
  _OWORD *v15; // rax
  __int64 *v16; // rcx
  __int64 v17; // rdx
  int v18; // eax
  WCHAR *p_szFilePath; // r8
  wchar_t Drive[8]; // [rsp+60h] [rbp-458h] BYREF
  WCHAR szFilePath; // [rsp+70h] [rbp-448h] BYREF
  unsigned __int16 v23; // [rsp+78h] [rbp-440h] BYREF
  wchar_t Dir[256]; // [rsp+280h] [rbp-238h] BYREF

  if ( (a9 & 1) == 0 && !hFile && (!a3 || !*a3) )
    return 0;
  SetLastError(0);
  v13 = pMemAlloc(0x1318u);
  v14 = v13;
  if ( !v13 )
  {
LABEL_7:
    dword_1802AF9D0 = 5;
    SetLastError(0xEu);
    return 0;
  }
  memset_0((void *)(v13 + 4), 0, 0x1314u);
  *(_DWORD *)v14 = 4888;
  v15 = (_OWORD *)pMemAlloc(0x150u);
  *(_QWORD *)(v14 + 4232) = v15;
  if ( !v15 )
  {
    FreeIt((void *)v14);
    goto LABEL_7;
  }
  v16 = qword_1802B29C0;
  v17 = 2;
  do
  {
    *v15 = *(_OWORD *)v16;
    v15[1] = *((_OWORD *)v16 + 1);
    v15[2] = *((_OWORD *)v16 + 2);
    v15[3] = *((_OWORD *)v16 + 3);
    v15[4] = *((_OWORD *)v16 + 4);
    v15[5] = *((_OWORD *)v16 + 5);
    v15[6] = *((_OWORD *)v16 + 6);
    v15[7] = *((_OWORD *)v16 + 7);
    v15 += 8;
    v16 += 16;
    --v17;
  }
  while ( v17 );
  *v15 = *(_OWORD *)v16;
  v15[1] = *((_OWORD *)v16 + 1);
  v15[2] = *((_OWORD *)v16 + 2);
  v15[3] = *((_OWORD *)v16 + 3);
  v15[4] = *((_OWORD *)v16 + 4);
  *(_QWORD *)(v14 + 8) = FindProcessEntry(a1);
  *(_DWORD *)(v14 + 4224) = 0;
  *(_QWORD *)(v14 + 1104) = hFile;
  *(_QWORD *)(v14 + 1112) = hFile;
  *(_DWORD *)(v14 + 40) = a7;
  *(_DWORD *)(v14 + 4276) = a9;
  if ( a3 )
    wcscpy_s_ex((unsigned __int16 *)(v14 + 58), 0x105u, a3);
  if ( (unsigned __int64)(hFile - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( a3 )
    {
      if ( *a3 )
      {
        _wsplitpath_s(a3, Drive, 3u, Dir, 0x100u, 0, 0, 0, 0);
        if ( !Drive[0] && !Dir[0] )
        {
          memset_0(&szFilePath, 0, 0x20Au);
          if ( GetFinalPathNameByHandleW(hFile, &szFilePath, 0x105u, 0) - 1 <= 0x103 )
          {
            v18 = wcsncmp_0(&szFilePath, L"\\\\?\\", 4u);
            p_szFilePath = &szFilePath;
            if ( !v18 )
              p_szFilePath = &v23;
            wcscpy_s_ex((unsigned __int16 *)(v14 + 58), 0x105u, p_szFilePath);
          }
        }
      }
    }
  }
  *(_QWORD *)(v14 + 24) = a6;
  *(_QWORD *)(v14 + 3592) = a1;
  *(_QWORD *)(v14 + 4264) = a8;
  *(_DWORD *)(v14 + 3600) = a4;
  if ( a3 )
    wcscpy_s_ex((unsigned __int16 *)(v14 + 3604), 0x105u, a3);
  if ( Source )
    *(_QWORD *)(v14 + 16) = StringDup(Source);
  return (struct _IMGHLP_DEBUG_DATA *)v14;
}

```

## disassembly

```asm
0x18000fb40  mov     [rsp+arg_0], rbx
0x18000fb45  mov     [rsp+arg_18], rsi
0x18000fb4a  push    rdi
0x18000fb4b  push    r12
0x18000fb4d  push    r13
0x18000fb4f  push    r14
0x18000fb51  push    r15
0x18000fb53  sub     rsp, 490h
0x18000fb5a  mov     rax, cs:__security_cookie
0x18000fb61  xor     rax, rsp
0x18000fb64  mov     [rsp+4B8h+var_38], rax
0x18000fb6c  mov     [rsp+4B8h+var_468], r9d
0x18000fb71  mov     rsi, r8
0x18000fb74  mov     r15, rdx
0x18000fb77  mov     r13, rcx
0x18000fb7a  mov     r12, [rsp+4B8h+Source]
0x18000fb82  mov     r14d, [rsp+4B8h+arg_40]
0x18000fb8a  xor     edi, edi
0x18000fb8c  test    r14b, 1
0x18000fb90  jnz     short loc_18000FBA9
0x18000fb92  test    rdx, rdx
0x18000fb95  jnz     short loc_18000FBA9
0x18000fb97  test    r8, r8
0x18000fb9a  jz      short loc_18000FBA2
0x18000fb9c  cmp     [r8], di
0x18000fba0  jnz     short loc_18000FBA9
0x18000fba2  xor     eax, eax
0x18000fba4  jmp     loc_18000FE1E
0x18000fba9  xor     ecx, ecx; dwErrCode
0x18000fbab  call    cs:__imp_SetLastError
0x18000fbb1  mov     ecx, 1318h; dwBytes
0x18000fbb6  call    pMemAlloc
0x18000fbbb  mov     rbx, rax
0x18000fbbe  test    rax, rax
0x18000fbc1  jnz     short loc_18000FBDA
0x18000fbc3  mov     cs:dword_1802AF9D0, 5
0x18000fbcd  mov     ecx, 0Eh; dwErrCode
0x18000fbd2  call    cs:__imp_SetLastError
0x18000fbd8  jmp     short loc_18000FBA2
0x18000fbda  lea     rcx, [rax+4]; void *
0x18000fbde  xor     edx, edx; Val
0x18000fbe0  mov     r8d, 1314h; Size
0x18000fbe6  call    memset_0
0x18000fbeb  mov     dword ptr [rbx], 1318h
0x18000fbf1  mov     ecx, 150h; dwBytes
0x18000fbf6  call    pMemAlloc
0x18000fbfb  mov     [rbx+1088h], rax
0x18000fc02  test    rax, rax
0x18000fc05  jnz     short loc_18000FC11
0x18000fc07  mov     rcx, rbx; lpMem
0x18000fc0a  call    ?FreeIt@@YAXPEAX@Z; FreeIt(void *)
0x18000fc0f  jmp     short loc_18000FBC3
0x18000fc11  mov     [rsp+4B8h+lpMem], rbx
0x18000fc16  lea     rcx, qword_1802B29C0
0x18000fc1d  mov     edx, 2
0x18000fc22  lea     r8d, [rdx+7Eh]
0x18000fc26  movups  xmm0, xmmword ptr [rcx]
0x18000fc29  movups  xmmword ptr [rax], xmm0
0x18000fc2c  movups  xmm1, xmmword ptr [rcx+10h]
0x18000fc30  movups  xmmword ptr [rax+10h], xmm1
0x18000fc34  movups  xmm0, xmmword ptr [rcx+20h]
0x18000fc38  movups  xmmword ptr [rax+20h], xmm0
0x18000fc3c  movups  xmm1, xmmword ptr [rcx+30h]
0x18000fc40  movups  xmmword ptr [rax+30h], xmm1
0x18000fc44  movups  xmm0, xmmword ptr [rcx+40h]
0x18000fc48  movups  xmmword ptr [rax+40h], xmm0
0x18000fc4c  movups  xmm1, xmmword ptr [rcx+50h]
0x18000fc50  movups  xmmword ptr [rax+50h], xmm1
0x18000fc54  movups  xmm0, xmmword ptr [rcx+60h]
0x18000fc58  movups  xmmword ptr [rax+60h], xmm0
0x18000fc5c  movups  xmm1, xmmword ptr [rcx+70h]
0x18000fc60  movups  xmmword ptr [rax+70h], xmm1
0x18000fc64  add     rax, r8
0x18000fc67  add     rcx, r8
0x18000fc6a  sub     rdx, 1
0x18000fc6e  jnz     short loc_18000FC26
0x18000fc70  movups  xmm0, xmmword ptr [rcx]
0x18000fc73  movups  xmmword ptr [rax], xmm0
0x18000fc76  movups  xmm1, xmmword ptr [rcx+10h]
0x18000fc7a  movups  xmmword ptr [rax+10h], xmm1
0x18000fc7e  movups  xmm0, xmmword ptr [rcx+20h]
0x18000fc82  movups  xmmword ptr [rax+20h], xmm0
0x18000fc86  movups  xmm1, xmmword ptr [rcx+30h]
0x18000fc8a  movups  xmmword ptr [rax+30h], xmm1
0x18000fc8e  movups  xmm0, xmmword ptr [rcx+40h]
0x18000fc92  movups  xmmword ptr [rax+40h], xmm0
0x18000fc96  mov     rcx, r13; void *
0x18000fc99  call    ?FindProcessEntry@@YAPEAU_PROCESS_ENTRY@@PEAX@Z; FindProcessEntry(void *)
0x18000fc9e  mov     [rbx+8], rax
0x18000fca2  mov     [rbx+1080h], edi
0x18000fca8  mov     [rbx+450h], r15
0x18000fcaf  mov     [rbx+458h], r15
0x18000fcb6  mov     eax, [rsp+4B8h+arg_30]
0x18000fcbd  mov     [rbx+28h], eax
0x18000fcc0  mov     [rbx+10B4h], r14d
0x18000fcc7  mov     r14d, 105h
0x18000fccd  test    rsi, rsi
0x18000fcd0  jz      short loc_18000FCE1
0x18000fcd2  lea     rcx, [rbx+3Ah]; unsigned __int16 *
0x18000fcd6  mov     r8, rsi; unsigned __int16 *
0x18000fcd9  mov     edx, r14d; unsigned __int64
0x18000fcdc  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x18000fce1  lea     rax, [r15-1]
0x18000fce5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000fce9  ja      loc_18000FDAE
0x18000fcef  test    rsi, rsi
0x18000fcf2  jz      loc_18000FDAE
0x18000fcf8  cmp     [rsi], di
0x18000fcfb  jz      loc_18000FDAE
0x18000fd01  mov     [rsp+4B8h+ExtCount], rdi; ExtCount
0x18000fd06  mov     [rsp+4B8h+Ext], rdi; Ext
0x18000fd0b  mov     [rsp+4B8h+FilenameCount], rdi; FilenameCount
0x18000fd10  mov     [rsp+4B8h+Filename], rdi; Filename
0x18000fd15  mov     [rsp+4B8h+DirCount], 100h; DirCount
0x18000fd1e  lea     r9, [rsp+4B8h+Dir]; Dir
0x18000fd26  mov     r8d, 3; DriveCount
0x18000fd2c  lea     rdx, [rsp+4B8h+Drive]; Drive
0x18000fd31  mov     rcx, rsi; FullPath
0x18000fd34  call    cs:__imp__wsplitpath_s
0x18000fd3a  cmp     [rsp+4B8h+Drive], di
0x18000fd3f  jnz     short loc_18000FDAE
0x18000fd41  cmp     [rsp+4B8h+Dir], di
0x18000fd49  jnz     short loc_18000FDAE
0x18000fd4b  xor     edx, edx; Val
0x18000fd4d  mov     r8d, 20Ah; Size
0x18000fd53  lea     rcx, [rsp+4B8h+szFilePath]; void *
0x18000fd58  call    memset_0
0x18000fd5d  xor     r9d, r9d; dwFlags
0x18000fd60  mov     r8d, r14d; cchFilePath
0x18000fd63  lea     rdx, [rsp+4B8h+szFilePath]; lpszFilePath
0x18000fd68  mov     rcx, r15; hFile
0x18000fd6b  call    cs:__imp_GetFinalPathNameByHandleW
0x18000fd71  dec     eax
0x18000fd73  cmp     eax, 103h
0x18000fd78  ja      short loc_18000FDAE
0x18000fd7a  mov     r8d, 4; MaxCount
0x18000fd80  lea     rdx, asc_180254988; "\\\\?\\"
0x18000fd87  lea     rcx, [rsp+4B8h+szFilePath]; String1
0x18000fd8c  call    wcsncmp_0
0x18000fd91  lea     r8, [rsp+4B8h+szFilePath]
0x18000fd96  lea     rcx, [rsp+4B8h+var_440]
0x18000fd9b  test    eax, eax
0x18000fd9d  cmovz   r8, rcx; unsigned __int16 *
0x18000fda1  lea     rcx, [rbx+3Ah]; unsigned __int16 *
0x18000fda5  mov     rdx, r14; unsigned __int64
0x18000fda8  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x18000fdad  nop
0x18000fdae  mov     rax, [rsp+4B8h+arg_28]
0x18000fdb6  mov     [rbx+18h], rax
0x18000fdba  mov     [rbx+0E08h], r13
0x18000fdc1  mov     rax, [rsp+4B8h+arg_38]
0x18000fdc9  mov     [rbx+10A8h], rax
0x18000fdd0  mov     eax, [rsp+4B8h+var_468]
0x18000fdd4  mov     [rbx+0E10h], eax
0x18000fdda  test    rsi, rsi
0x18000fddd  jz      short loc_18000FDF1
0x18000fddf  lea     rcx, [rbx+0E14h]; unsigned __int16 *
0x18000fde6  mov     r8, rsi; unsigned __int16 *
0x18000fde9  mov     rdx, r14; unsigned __int64
0x18000fdec  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x18000fdf1  test    r12, r12
0x18000fdf4  jz      short loc_18000FE02
0x18000fdf6  mov     rcx, r12; Source
0x18000fdf9  call    ?StringDup@@YAPEAGPEBG@Z; StringDup(ushort const *)
0x18000fdfe  mov     [rbx+10h], rax
0x18000fe02  jmp     short loc_18000FE1B
0x18000fe04  mov     rbx, [rsp+4B8h+lpMem]
0x18000fe09  test    rbx, rbx
0x18000fe0c  jz      short loc_18000FE1B
0x18000fe0e  or      edx, 0FFFFFFFFh; unsigned int
0x18000fe11  mov     rcx, rbx; lpMem
0x18000fe14  call    ?ReleaseDebugData@@YAXPEAU_IMGHLP_DEBUG_DATA@@K@Z; ReleaseDebugData(_IMGHLP_DEBUG_DATA *,ulong)
0x18000fe19  xor     ebx, ebx
0x18000fe1b  mov     rax, rbx
0x18000fe1e  mov     rcx, [rsp+4B8h+var_38]
0x18000fe26  xor     rcx, rsp; StackCookie
0x18000fe29  call    __security_check_cookie
0x18000fe2e  lea     r11, [rsp+4B8h+var_28]
0x18000fe36  mov     rbx, [r11+30h]
0x18000fe3a  mov     rsi, [r11+48h]
0x18000fe3e  mov     rsp, r11
0x18000fe41  pop     r15
0x18000fe43  pop     r14
0x18000fe45  pop     r13
0x18000fe47  pop     r12
0x18000fe49  pop     rdi
0x18000fe4a  retn
```
