# CONFIG_XML_DOM::ParseXmlFile(void *,PARSE_ERROR_INFO *,int,int)

- ea: `0x180021500`
- end: `0x180021679`
- name: `?ParseXmlFile@CONFIG_XML_DOM@@UEAAJPEAXPEAVPARSE_ERROR_INFO@@HH@Z`
- size: `377`
- prototype: `__int64 __fastcall(CONFIG_XML_DOM *this, HANDLE hFile, struct PARSE_ERROR_INFO *, int, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callees

- `0x1800100d0`
- `0x1800209b0`
- `0x180021500`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800215b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800215b7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800215c5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800215c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021562`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002156c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021562`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002156c`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180021554`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180021554`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800215f6`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800215f6`

## pseudocode

```c
__int64 __fastcall CONFIG_XML_DOM::ParseXmlFile(
        CONFIG_XML_DOM *this,
        HANDLE hFile,
        struct PARSE_ERROR_INFO *a3,
        int a4,
        int a5)
{
  DWORD FileSize; // eax
  signed int LastError; // eax
  int Dom; // ebx
  unsigned int v11; // ebx
  HANDLE ProcessHeap; // rax
  void *v13; // rax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-38h] BYREF
  _QWORD v16[6]; // [rsp+48h] [rbp-30h] BYREF
  DWORD v17; // [rsp+88h] [rbp+10h] BYREF

  v17 = 0;
  NumberOfBytesRead = 0;
  v16[0] = 0;
  if ( !hFile || !a3 )
    return (unsigned int)-2147024809;
  *((_DWORD *)this + 3) = a4 ^ (*((_DWORD *)this + 3) ^ a4) & 0xFFFFFFFE;
  FileSize = GetFileSize(hFile, &v17);
  *((_DWORD *)this + 7) = FileSize;
  if ( FileSize == -1 && GetLastError() )
    goto LABEL_5;
  if ( v17
    || a5
    && *(_DWORD *)&g_dwMaxWebConfigFileSizeInKb
    && *(_DWORD *)&g_dwMaxWebConfigFileSizeInKb << 10 < *((_DWORD *)this + 7) )
  {
    Dom = -2147024846;
    ((void (__fastcall *)(struct PARSE_ERROR_INFO *, __int64, __int64, __int64, _QWORD *, _DWORD, _QWORD, _QWORD, DWORD))PARSE_ERROR_INFO::SetErrorInfo)(
      a3,
      2147942450LL,
      3,
      3221228260LL,
      v16,
      0,
      0,
      0,
      NumberOfBytesRead);
    return (unsigned int)Dom;
  }
  v11 = *((_DWORD *)this + 7);
  ProcessHeap = GetProcessHeap();
  v13 = HeapAlloc(ProcessHeap, 0, v11);
  *((_QWORD *)this + 4) = v13;
  if ( !v13 )
    return (unsigned int)-2147024888;
  if ( !ReadFile(hFile, v13, *((_DWORD *)this + 7), &NumberOfBytesRead, 0) )
  {
LABEL_5:
    LastError = GetLastError();
    Dom = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    Dom = CONFIG_XML_DOM::GenerateDom(this, a3);
    if ( Dom >= 0 )
      return *((_QWORD *)this + 15) == 0 ? 0x8007000D : 0;
  }
  return (unsigned int)Dom;
}

```

## disassembly

```asm
0x180021500  mov     r11, rsp
0x180021503  push    rbx
0x180021504  push    rbp
0x180021505  push    rsi
0x180021506  push    rdi
0x180021507  sub     rsp, 58h
0x18002150b  mov     dword ptr [r11+10h], 0
0x180021513  mov     rsi, r8
0x180021516  mov     [rsp+78h+NumberOfBytesRead], 0
0x18002151e  mov     rbp, rdx
0x180021521  mov     qword ptr [r11-30h], 0
0x180021529  mov     rdi, rcx
0x18002152c  test    rdx, rdx
0x18002152f  jz      loc_180021669
0x180021535  test    r8, r8
0x180021538  jz      loc_180021669
0x18002153e  mov     eax, r9d
0x180021541  lea     rdx, [r11+10h]; lpFileSizeHigh
0x180021545  xor     eax, [rcx+0Ch]
0x180021548  and     eax, 0FFFFFFFEh
0x18002154b  xor     eax, r9d
0x18002154e  mov     [rcx+0Ch], eax
0x180021551  mov     rcx, rbp; hFile
0x180021554  call    cs:__imp_GetFileSize
0x18002155a  mov     [rdi+1Ch], eax
0x18002155d  cmp     eax, 0FFFFFFFFh
0x180021560  jnz     short loc_18002158A
0x180021562  call    cs:__imp_GetLastError
0x180021568  test    eax, eax
0x18002156a  jz      short loc_18002158A
0x18002156c  call    cs:__imp_GetLastError
0x180021572  mov     ebx, eax
0x180021574  test    eax, eax
0x180021576  jle     loc_18002166E
0x18002157c  movzx   ebx, ax
0x18002157f  or      ebx, 80070000h
0x180021585  jmp     loc_18002166E
0x18002158a  cmp     [rsp+78h+arg_8], 0
0x180021592  jnz     loc_180021628
0x180021598  cmp     [rsp+78h+arg_20], 0
0x1800215a0  jz      short loc_1800215B4
0x1800215a2  mov     eax, cs:?g_dwMaxWebConfigFileSizeInKb@@3KA; ulong g_dwMaxWebConfigFileSizeInKb
0x1800215a8  test    eax, eax
0x1800215aa  jz      short loc_1800215B4
0x1800215ac  shl     eax, 0Ah
0x1800215af  cmp     eax, [rdi+1Ch]
0x1800215b2  jb      short loc_180021628
0x1800215b4  mov     ebx, [rdi+1Ch]
0x1800215b7  call    cs:__imp_GetProcessHeap
0x1800215bd  mov     r8d, ebx; dwBytes
0x1800215c0  xor     edx, edx; dwFlags
0x1800215c2  mov     rcx, rax; hHeap
0x1800215c5  call    cs:__imp_HeapAlloc
0x1800215cb  mov     [rdi+20h], rax
0x1800215cf  test    rax, rax
0x1800215d2  jnz     short loc_1800215DE
0x1800215d4  mov     ebx, 80070008h
0x1800215d9  jmp     loc_18002166E
0x1800215de  mov     r8d, [rdi+1Ch]; nNumberOfBytesToRead
0x1800215e2  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800215e7  mov     rdx, rax; lpBuffer
0x1800215ea  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x1800215f3  mov     rcx, rbp; hFile
0x1800215f6  call    cs:__imp_ReadFile
0x1800215fc  test    eax, eax
0x1800215fe  jz      loc_18002156C
0x180021604  mov     rdx, rsi; struct PARSE_ERROR_INFO *
0x180021607  mov     rcx, rdi; this
0x18002160a  call    ?GenerateDom@CONFIG_XML_DOM@@AEAAJPEAVPARSE_ERROR_INFO@@@Z; CONFIG_XML_DOM::GenerateDom(PARSE_ERROR_INFO *)
0x18002160f  mov     ebx, eax
0x180021611  test    eax, eax
0x180021613  js      short loc_18002166E
0x180021615  mov     rax, [rdi+78h]
0x180021619  neg     rax
0x18002161c  sbb     ebx, ebx
0x18002161e  not     ebx
0x180021620  and     ebx, 8007000Dh
0x180021626  jmp     short loc_18002166E
0x180021628  mov     [rsp+78h+var_40], 0
0x180021631  lea     rax, [rsp+78h+var_30]
0x180021636  mov     [rsp+78h+var_48], 0
0x18002163f  mov     ebx, 80070032h
0x180021644  mov     [rsp+78h+var_50], 0
0x18002164c  mov     edx, ebx
0x18002164e  mov     r9d, 0C0000AE4h
0x180021654  mov     [rsp+78h+lpOverlapped], rax
0x180021659  mov     r8d, 3
0x18002165f  mov     rcx, rsi
0x180021662  call    ?SetErrorInfo@PARSE_ERROR_INFO@@QEAAJJW4PARSE_ERROR_TYPE@@KQEAPEBDKPEAVIConfigDom@@PEAVIConfigDomNode@@@Z; PARSE_ERROR_INFO::SetErrorInfo(long,PARSE_ERROR_TYPE,ulong,char const * * const,ulong,IConfigDom *,IConfigDomNode *)
0x180021667  jmp     short loc_18002166E
0x180021669  mov     ebx, 80070057h
0x18002166e  mov     eax, ebx
0x180021670  add     rsp, 58h
0x180021674  pop     rdi
0x180021675  pop     rsi
0x180021676  pop     rbp
0x180021677  pop     rbx
0x180021678  retn
```
