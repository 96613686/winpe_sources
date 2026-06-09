# FileStream::Stat(tagSTATSTG *,ulong)

- ea: `0x1800db200`
- end: `0x1800db39e`
- name: `?Stat@FileStream@@UEAAJPEAUtagSTATSTG@@K@Z`
- size: `414`
- prototype: `__int64 __fastcall(FileStream *__hidden this, struct tagSTATSTG *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800386f0`
- `0x1800a492c`
- `0x1800db200`
- `0x1800fe680`
- `0x1800ff04c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800db24d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800db24d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800db2b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800db2b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db29a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db29a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800db347`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800db347`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800db363`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800db363`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800db290`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800db290`

## pseudocode

```c
__int64 __fastcall FileStream::Stat(FileStream *this, struct tagSTATSTG *a2, char a3)
{
  void *v4; // rdi
  const unsigned __int16 *v7; // rdx
  void *v8; // rcx
  signed int LastError; // eax
  signed int v10; // ebx
  int v12; // eax
  __int128 v13; // xmm0
  const unsigned __int16 *v14; // rbx
  void *v15; // rax
  unsigned __int64 v16; // r9
  LPVOID pv[2]; // [rsp+20h] [rbp-59h] BYREF
  unsigned __int64 v18; // [rsp+30h] [rbp-49h]
  __int64 v19; // [rsp+38h] [rbp-41h]
  __int128 v20; // [rsp+40h] [rbp-39h]
  __int128 v21; // [rsp+50h] [rbp-29h]
  __int128 v22; // [rsp+60h] [rbp-19h]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+70h] [rbp-9h] BYREF

  v4 = 0;
  memset(&FileInformation, 0, sizeof(FileInformation));
  pv[0] = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( *((_QWORD *)this + 9) == -1 )
  {
    v10 = -2147286782;
    goto LABEL_11;
  }
  memset_0(pv, 0, 0x50u);
  if ( (a3 & 1) != 0 )
  {
    v4 = pv[0];
    goto LABEL_4;
  }
  v14 = (const unsigned __int16 *)(GpRuntime::UnicodeStringLength(*((GpRuntime **)this + 7), v7) + 1);
  v15 = CoTaskMemAlloc(2LL * (_QWORD)v14);
  pv[0] = v15;
  v4 = v15;
  if ( !v15 )
  {
    v10 = -2147287032;
LABEL_11:
    if ( v4 )
      CoTaskMemFree(v4);
    goto LABEL_8;
  }
  GpRuntime::UnicodeStringCopyCount((GpRuntime *)v15, *((unsigned __int16 **)this + 7), v14, v16);
LABEL_4:
  v8 = (void *)*((_QWORD *)this + 9);
  LODWORD(pv[1]) = 2;
  DWORD1(v21) = 6;
  if ( GetFileInformationByHandle(v8, &FileInformation) )
  {
    v10 = 0;
    v18 = __PAIR64__(FileInformation.nFileSizeHigh, FileInformation.nFileSizeLow);
    v12 = *((_DWORD *)this + 16);
    *(_OWORD *)a2 = *(_OWORD *)pv;
    v19 = 0;
    *((_OWORD *)a2 + 1) = v18;
    v20 = 0u;
    *((_OWORD *)a2 + 2) = 0u;
    LODWORD(v21) = v12 & 0xFFFFEFFF;
    v13 = v22;
    *((_OWORD *)a2 + 3) = v21;
    *((_OWORD *)a2 + 4) = v13;
    goto LABEL_8;
  }
  LastError = GetLastError();
  v10 = LastError;
  if ( LastError > 0 )
    v10 = (unsigned __int16)LastError | 0x80070000;
  if ( v10 < 0 )
    goto LABEL_11;
LABEL_8:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800db200  mov     [rsp-8+arg_10], rbx
0x1800db205  push    rbp
0x1800db206  push    rsi
0x1800db207  push    rdi
0x1800db208  push    r14
0x1800db20a  push    r15
0x1800db20c  lea     rbp, [rsp-37h]
0x1800db211  sub     rsp, 0B0h
0x1800db218  mov     rax, cs:__security_cookie
0x1800db21f  xor     rax, rsp
0x1800db222  mov     [rbp+57h+var_28], rax
0x1800db226  xorps   xmm0, xmm0
0x1800db229  mov     rsi, rcx
0x1800db22c  xor     eax, eax
0x1800db22e  xor     edi, edi
0x1800db230  add     rcx, 8; lpCriticalSection
0x1800db234  mov     [rbp+57h+FileInformation.nFileIndexLow], eax
0x1800db237  movups  xmmword ptr [rbp+57h+FileInformation.dwFileAttributes], xmm0
0x1800db23b  mov     [rbp+57h+pv], rdi
0x1800db23f  mov     ebx, r8d
0x1800db242  movups  xmmword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x1800db246  mov     r14, rdx
0x1800db249  movups  xmmword ptr [rbp+57h+FileInformation.nFileSizeHigh], xmm0
0x1800db24d  call    cs:__imp_EnterCriticalSection
0x1800db253  cmp     qword ptr [rsi+48h], 0FFFFFFFFFFFFFFFFh
0x1800db258  jz      loc_1800DB336
0x1800db25e  xor     edx, edx; Val
0x1800db260  lea     r8d, [rdi+50h]; Size
0x1800db264  lea     rcx, [rbp+57h+pv]; void *
0x1800db268  call    memset_0
0x1800db26d  test    bl, 1
0x1800db270  jz      loc_1800DB352
0x1800db276  mov     rdi, [rbp+57h+pv]
0x1800db27a  mov     rcx, [rsi+48h]; hFile
0x1800db27e  lea     rdx, [rbp+57h+FileInformation]; lpFileInformation
0x1800db282  mov     dword ptr [rbp+57h+pv+8], 2
0x1800db289  mov     dword ptr [rbp+57h+var_80+4], 6
0x1800db290  call    cs:__imp_GetFileInformationByHandle
0x1800db296  test    eax, eax
0x1800db298  jnz     short loc_1800DB2E1
0x1800db29a  call    cs:__imp_GetLastError
0x1800db2a0  mov     ebx, eax
0x1800db2a2  test    eax, eax
0x1800db2a4  jg      loc_1800DB390
0x1800db2aa  test    ebx, ebx
0x1800db2ac  js      loc_1800DB33B
0x1800db2b2  lea     rcx, [rsi+8]; lpCriticalSection
0x1800db2b6  call    cs:__imp_LeaveCriticalSection
0x1800db2bc  mov     eax, ebx
0x1800db2be  mov     rcx, [rbp+57h+var_28]
0x1800db2c2  xor     rcx, rsp; StackCookie
0x1800db2c5  call    __security_check_cookie
0x1800db2ca  mov     rbx, [rsp+0D0h+arg_10]
0x1800db2d2  add     rsp, 0B0h
0x1800db2d9  pop     r15
0x1800db2db  pop     r14
0x1800db2dd  pop     rdi
0x1800db2de  pop     rsi
0x1800db2df  pop     rbp
0x1800db2e0  retn
0x1800db2e1  mov     eax, [rbp+57h+FileInformation.nFileSizeLow]
0x1800db2e4  xor     ebx, ebx
0x1800db2e6  movaps  xmm0, xmmword ptr [rbp+57h+pv]
0x1800db2ea  mov     dword ptr [rbp+57h+var_A0], eax
0x1800db2ed  mov     eax, [rbp+57h+FileInformation.nFileSizeHigh]
0x1800db2f0  mov     dword ptr [rbp+57h+var_A0+4], eax
0x1800db2f3  mov     eax, [rsi+40h]
0x1800db2f6  movups  xmmword ptr [r14], xmm0
0x1800db2fa  mov     qword ptr [rbp+57h+var_A0+8], rbx
0x1800db2fe  btr     eax, 0Ch
0x1800db302  movaps  xmm1, [rbp+57h+var_A0]
0x1800db306  movups  xmmword ptr [r14+10h], xmm1
0x1800db30b  mov     qword ptr [rbp+57h+var_90], rbx
0x1800db30f  mov     qword ptr [rbp+57h+var_90+8], rbx
0x1800db313  movaps  xmm0, [rbp+57h+var_90]
0x1800db317  movups  xmmword ptr [r14+20h], xmm0
0x1800db31c  mov     dword ptr [rbp+57h+var_80], eax
0x1800db31f  movaps  xmm1, [rbp+57h+var_80]
0x1800db323  movaps  xmm0, [rbp+57h+var_70]
0x1800db327  movups  xmmword ptr [r14+30h], xmm1
0x1800db32c  movups  xmmword ptr [r14+40h], xmm0
0x1800db331  jmp     loc_1800DB2B2
0x1800db336  mov     ebx, 80030102h
0x1800db33b  test    rdi, rdi
0x1800db33e  jz      loc_1800DB2B2
0x1800db344  mov     rcx, rdi; pv
0x1800db347  call    cs:__imp_CoTaskMemFree
0x1800db34d  jmp     loc_1800DB2B2
0x1800db352  mov     rcx, [rsi+38h]; this
0x1800db356  call    ?UnicodeStringLength@GpRuntime@@YA_KPEBG@Z; GpRuntime::UnicodeStringLength(ushort const *)
0x1800db35b  lea     rbx, [rax+1]
0x1800db35f  lea     rcx, [rbx+rbx]; cb
0x1800db363  call    cs:__imp_CoTaskMemAlloc
0x1800db369  mov     [rbp+57h+pv], rax
0x1800db36d  mov     rdi, rax
0x1800db370  test    rax, rax
0x1800db373  jnz     short loc_1800DB37C
0x1800db375  mov     ebx, 80030008h
0x1800db37a  jmp     short loc_1800DB33B
0x1800db37c  mov     rdx, [rsi+38h]; unsigned __int16 *
0x1800db380  mov     r8, rbx; unsigned __int16 *
0x1800db383  mov     rcx, rax; this
0x1800db386  call    ?UnicodeStringCopyCount@GpRuntime@@YAXPEAGPEBG_K@Z; GpRuntime::UnicodeStringCopyCount(ushort *,ushort const *,unsigned __int64)
0x1800db38b  jmp     loc_1800DB27A
0x1800db390  movzx   ebx, ax
0x1800db393  or      ebx, 80070000h
0x1800db399  jmp     loc_1800DB2AA
```
