# FileStream::Stat(tagSTATSTG *,ulong)

- ea: `0x1800e17f0`
- end: `0x1800e19b3`
- name: `?Stat@FileStream@@UEAAJPEAUtagSTATSTG@@K@Z`
- size: `451`
- prototype: `__int64 __fastcall(FileStream *__hidden this, struct tagSTATSTG *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800849a8`
- `0x18008c194`
- `0x1800e17f0`
- `0x180105d40`
- `0x18010673c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e183d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e183d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e18b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e18b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e1896`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e1896`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e1950`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e1950`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e1972`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e1972`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800e1886`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800e1886`

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
0x1800e17f0  mov     [rsp-8+arg_10], rbx
0x1800e17f5  push    rbp
0x1800e17f6  push    rsi
0x1800e17f7  push    rdi
0x1800e17f8  push    r14
0x1800e17fa  push    r15
0x1800e17fc  lea     rbp, [rsp-37h]
0x1800e1801  sub     rsp, 0B0h
0x1800e1808  mov     rax, cs:__security_cookie
0x1800e180f  xor     rax, rsp
0x1800e1812  mov     [rbp+57h+var_28], rax
0x1800e1816  xorps   xmm0, xmm0
0x1800e1819  mov     rsi, rcx
0x1800e181c  xor     eax, eax
0x1800e181e  xor     edi, edi
0x1800e1820  add     rcx, 8; lpCriticalSection
0x1800e1824  mov     [rbp+57h+FileInformation.nFileIndexLow], eax
0x1800e1827  movups  xmmword ptr [rbp+57h+FileInformation.dwFileAttributes], xmm0
0x1800e182b  mov     [rbp+57h+pv], rdi
0x1800e182f  mov     ebx, r8d
0x1800e1832  movups  xmmword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x1800e1836  mov     r14, rdx
0x1800e1839  movups  xmmword ptr [rbp+57h+FileInformation.nFileSizeHigh], xmm0
0x1800e183d  call    cs:__imp_EnterCriticalSection
0x1800e1844  nop     dword ptr [rax+rax+00h]
0x1800e1849  cmp     qword ptr [rsi+48h], 0FFFFFFFFFFFFFFFFh
0x1800e184e  jz      loc_1800E193F
0x1800e1854  xor     edx, edx; Val
0x1800e1856  lea     r8d, [rdi+50h]; Size
0x1800e185a  lea     rcx, [rbp+57h+pv]; void *
0x1800e185e  call    memset_0
0x1800e1863  test    bl, 1
0x1800e1866  jz      loc_1800E1961
0x1800e186c  mov     rdi, [rbp+57h+pv]
0x1800e1870  mov     rcx, [rsi+48h]; hFile
0x1800e1874  lea     rdx, [rbp+57h+FileInformation]; lpFileInformation
0x1800e1878  mov     dword ptr [rbp+57h+pv+8], 2
0x1800e187f  mov     dword ptr [rbp+57h+var_80+4], 6
0x1800e1886  call    cs:__imp_GetFileInformationByHandle
0x1800e188d  nop     dword ptr [rax+rax+00h]
0x1800e1892  test    eax, eax
0x1800e1894  jnz     short loc_1800E18EA
0x1800e1896  call    cs:__imp_GetLastError
0x1800e189d  nop     dword ptr [rax+rax+00h]
0x1800e18a2  mov     ebx, eax
0x1800e18a4  test    eax, eax
0x1800e18a6  jg      loc_1800E19A5
0x1800e18ac  test    ebx, ebx
0x1800e18ae  js      loc_1800E1944
0x1800e18b4  lea     rcx, [rsi+8]; lpCriticalSection
0x1800e18b8  call    cs:__imp_LeaveCriticalSection
0x1800e18bf  nop     dword ptr [rax+rax+00h]
0x1800e18c4  mov     eax, ebx
0x1800e18c6  mov     rcx, [rbp+57h+var_28]
0x1800e18ca  xor     rcx, rsp; StackCookie
0x1800e18cd  call    __security_check_cookie
0x1800e18d2  mov     rbx, [rsp+0D0h+arg_10]
0x1800e18da  add     rsp, 0B0h
0x1800e18e1  pop     r15
0x1800e18e3  pop     r14
0x1800e18e5  pop     rdi
0x1800e18e6  pop     rsi
0x1800e18e7  pop     rbp
0x1800e18e8  retn
0x1800e18ea  mov     eax, [rbp+57h+FileInformation.nFileSizeLow]
0x1800e18ed  xor     ebx, ebx
0x1800e18ef  movaps  xmm0, xmmword ptr [rbp+57h+pv]
0x1800e18f3  mov     dword ptr [rbp+57h+var_A0], eax
0x1800e18f6  mov     eax, [rbp+57h+FileInformation.nFileSizeHigh]
0x1800e18f9  mov     dword ptr [rbp+57h+var_A0+4], eax
0x1800e18fc  mov     eax, [rsi+40h]
0x1800e18ff  movups  xmmword ptr [r14], xmm0
0x1800e1903  mov     qword ptr [rbp+57h+var_A0+8], rbx
0x1800e1907  btr     eax, 0Ch
0x1800e190b  movaps  xmm1, [rbp+57h+var_A0]
0x1800e190f  movups  xmmword ptr [r14+10h], xmm1
0x1800e1914  mov     qword ptr [rbp+57h+var_90], rbx
0x1800e1918  mov     qword ptr [rbp+57h+var_90+8], rbx
0x1800e191c  movaps  xmm0, [rbp+57h+var_90]
0x1800e1920  movups  xmmword ptr [r14+20h], xmm0
0x1800e1925  mov     dword ptr [rbp+57h+var_80], eax
0x1800e1928  movaps  xmm1, [rbp+57h+var_80]
0x1800e192c  movaps  xmm0, [rbp+57h+var_70]
0x1800e1930  movups  xmmword ptr [r14+30h], xmm1
0x1800e1935  movups  xmmword ptr [r14+40h], xmm0
0x1800e193a  jmp     loc_1800E18B4
0x1800e193f  mov     ebx, 80030102h
0x1800e1944  test    rdi, rdi
0x1800e1947  jz      loc_1800E18B4
0x1800e194d  mov     rcx, rdi; pv
0x1800e1950  call    cs:__imp_CoTaskMemFree
0x1800e1957  nop     dword ptr [rax+rax+00h]
0x1800e195c  jmp     loc_1800E18B4
0x1800e1961  mov     rcx, [rsi+38h]; this
0x1800e1965  call    ?UnicodeStringLength@GpRuntime@@YA_KPEBG@Z; GpRuntime::UnicodeStringLength(ushort const *)
0x1800e196a  lea     rbx, [rax+1]
0x1800e196e  lea     rcx, [rbx+rbx]; cb
0x1800e1972  call    cs:__imp_CoTaskMemAlloc
0x1800e1979  nop     dword ptr [rax+rax+00h]
0x1800e197e  mov     [rbp+57h+pv], rax
0x1800e1982  mov     rdi, rax
0x1800e1985  test    rax, rax
0x1800e1988  jnz     short loc_1800E1991
0x1800e198a  mov     ebx, 80030008h
0x1800e198f  jmp     short loc_1800E1944
0x1800e1991  mov     rdx, [rsi+38h]; unsigned __int16 *
0x1800e1995  mov     r8, rbx; unsigned __int16 *
0x1800e1998  mov     rcx, rax; this
0x1800e199b  call    ?UnicodeStringCopyCount@GpRuntime@@YAXPEAGPEBG_K@Z; GpRuntime::UnicodeStringCopyCount(ushort *,ushort const *,unsigned __int64)
0x1800e19a0  jmp     loc_1800E1870
0x1800e19a5  movzx   ebx, ax
0x1800e19a8  or      ebx, 80070000h
0x1800e19ae  jmp     loc_1800E18AC
```
