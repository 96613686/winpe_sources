# NfsSrv4EnumerateOpenFile(_MI_Context *)

- ea: `0x180019edc`
- end: `0x18001a0b6`
- name: `?NfsSrv4EnumerateOpenFile@@YAKPEAU_MI_Context@@@Z`
- size: `474`
- prototype: `unsigned int __fastcall(struct _MI_Context *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800092e0`

## callees

- `0x1800098c4`
- `0x18000bde0`
- `0x18000cd6c`
- `0x180018188`
- `0x180018250`
- `0x180019010`
- `0x180019504`
- `0x180019edc`
- `0x18001a53c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001a086`
- `KERNEL32!HeapFree` at `0x18001a086`
- `KERNEL32!GetLastError` at `0x180019f4a`
- `KERNEL32!GetLastError` at `0x180019fbc`
- `KERNEL32!GetLastError` at `0x180019f4a`
- `KERNEL32!GetLastError` at `0x180019fbc`
- `KERNEL32!CloseHandle` at `0x18001a06d`
- `KERNEL32!CloseHandle` at `0x18001a06d`
- `KERNEL32!HeapAlloc` at `0x180019f73`
- `KERNEL32!HeapAlloc` at `0x180019f73`
- `KERNEL32!GetProcessHeap` at `0x180019f5a`
- `KERNEL32!GetProcessHeap` at `0x18001a078`
- `KERNEL32!GetProcessHeap` at `0x180019f5a`
- `KERNEL32!GetProcessHeap` at `0x18001a078`
- `KERNEL32!CreateFileW` at `0x180019f3b`
- `KERNEL32!CreateFileW` at `0x180019f3b`
- `KERNEL32!DeviceIoControl` at `0x180019fb2`
- `KERNEL32!DeviceIoControl` at `0x180019fb2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NfsSrv4EnumerateOpenFile(struct _MI_Context *a1)
{
  DWORD LastError; // ebx
  HANDLE FileW; // r14
  HANDLE ProcessHeap; // rax
  unsigned int *v4; // rdi
  DWORD v5; // eax
  char *v6; // r15
  __int64 i; // rsi
  HANDLE v8; // rax
  _BYTE v10[16]; // [rsp+40h] [rbp-39h] BYREF
  _BYTE v11[16]; // [rsp+50h] [rbp-29h] BYREF
  __int128 v12; // [rsp+60h] [rbp-19h]
  __int64 v13[2]; // [rsp+70h] [rbp-9h] BYREF
  __int16 v14; // [rsp+80h] [rbp+7h]
  struct _MI_Context *v15; // [rsp+88h] [rbp+Fh]
  int v16; // [rsp+90h] [rbp+17h]
  __int64 v17; // [rsp+94h] [rbp+1Bh]
  DWORD BytesReturned; // [rsp+E0h] [rbp+67h] BYREF

  LastError = 0;
  BytesReturned = 0;
  v13[0] = (__int64)&CWMIContext::`vftable';
  v15 = a1;
  v13[1] = 0;
  v14 = 0;
  v17 = 0;
  v16 = 0;
  FileW = CreateFileW(L"\\\\.\\NfsSvr", 0x80000000, 0, 0, 3u, 0x1000080u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_19;
  }
  ProcessHeap = GetProcessHeap();
  v4 = (unsigned int *)HeapAlloc(ProcessHeap, 8u, 0x1000u);
  if ( v4 )
  {
    if ( !DeviceIoControl(FileW, 0x1000059Cu, 0, 0, v4, 0x1000u, &BytesReturned, 0) )
    {
      v5 = GetLastError();
      LastError = v5;
      if ( v5 == 50 )
      {
        NfsPostNfsv4DisabledError(50, v13);
        goto LABEL_15;
      }
      if ( v5 )
        goto LABEL_15;
    }
    std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(v10);
    std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(v11);
    NfsMapVolPathToMntPointWithSharePrefix(v10);
    v6 = (char *)v4 + v4[2];
    for ( i = 0; (unsigned int)i < *v4; i = (unsigned int)(i + 1) )
    {
      v12 = *(_OWORD *)&v6[20 * i + 4];
      LastError = NfsSrv4EnumeratePerVsOpenFile(FileW, (__int64)v13);
      if ( CWMIContext::IsCanceled((CWMIContext *)v13) )
      {
        LastError = 1223;
        break;
      }
    }
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v11);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v10);
    goto LABEL_15;
  }
  LastError = 8;
LABEL_15:
  if ( FileW != (HANDLE)-1LL )
    CloseHandle(FileW);
  if ( v4 )
  {
    v8 = GetProcessHeap();
    HeapFree(v8, 0, v4);
  }
LABEL_19:
  LODWORD(v17) = LastError;
  CWMIContext::PostResult((CWMIContext *)v13, MI_RESULT_OK);
  CWMIContext::~CWMIContext((CWMIContext *)v13);
  return LastError;
}

```

## disassembly

```asm
0x180019edc  push    rbp
0x180019ede  push    rbx
0x180019edf  push    rsi
0x180019ee0  push    rdi
0x180019ee1  push    r14
0x180019ee3  push    r15
0x180019ee5  lea     rbp, [rsp-2Fh]
0x180019eea  sub     rsp, 0A8h
0x180019ef1  xor     ebx, ebx
0x180019ef3  mov     [rbp+57h+BytesReturned], ebx
0x180019ef6  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x180019efd  mov     [rbp+57h+var_60], rax
0x180019f01  mov     [rbp+57h+var_48], rcx
0x180019f05  mov     [rbp+57h+var_58], rbx
0x180019f09  mov     [rbp+57h+var_50], bx
0x180019f0d  mov     [rbp+57h+var_3C], rbx
0x180019f11  mov     [rbp+57h+var_40], ebx
0x180019f14  mov     [rsp+0D0h+hTemplateFile], rbx; hTemplateFile
0x180019f19  mov     [rsp+0D0h+dwFlagsAndAttributes], 1000080h; dwFlagsAndAttributes
0x180019f21  mov     [rsp+0D0h+dwCreationDisposition], 3; dwCreationDisposition
0x180019f29  xor     r9d, r9d; lpSecurityAttributes
0x180019f2c  xor     r8d, r8d; dwShareMode
0x180019f2f  mov     edx, 80000000h; dwDesiredAccess
0x180019f34  lea     rcx, aNfssvr; "\\\\.\\NfsSvr"
0x180019f3b  call    cs:__imp_CreateFileW
0x180019f41  mov     r14, rax
0x180019f44  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180019f48  jnz     short loc_180019F5A
0x180019f4a  call    cs:__imp_GetLastError
0x180019f50  mov     ebx, eax
0x180019f52  test    eax, eax
0x180019f54  jnz     loc_18001A08C
0x180019f5a  call    cs:__imp_GetProcessHeap
0x180019f60  mov     rcx, rax; hHeap
0x180019f63  mov     r15d, 1000h
0x180019f69  mov     r8d, r15d; dwBytes
0x180019f6c  mov     esi, 8
0x180019f71  mov     edx, esi; dwFlags
0x180019f73  call    cs:__imp_HeapAlloc
0x180019f79  mov     rdi, rax
0x180019f7c  test    rax, rax
0x180019f7f  jnz     short loc_180019F88
0x180019f81  mov     ebx, esi
0x180019f83  jmp     loc_18001A064
0x180019f88  mov     [rsp+0D0h+lpOverlapped], 0; lpOverlapped
0x180019f91  lea     rax, [rbp+57h+BytesReturned]
0x180019f95  mov     [rsp+0D0h+hTemplateFile], rax; lpBytesReturned
0x180019f9a  mov     [rsp+0D0h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x180019f9f  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rdi; lpOutBuffer
0x180019fa4  xor     r9d, r9d; nInBufferSize
0x180019fa7  xor     r8d, r8d; lpInBuffer
0x180019faa  mov     edx, 1000059Ch; dwIoControlCode
0x180019faf  mov     rcx, r14; hDevice
0x180019fb2  call    cs:__imp_DeviceIoControl
0x180019fb8  test    eax, eax
0x180019fba  jnz     short loc_180019FE3
0x180019fbc  call    cs:__imp_GetLastError
0x180019fc2  mov     ebx, eax
0x180019fc4  mov     ecx, 32h ; '2'
0x180019fc9  cmp     eax, ecx
0x180019fcb  jnz     short loc_180019FDB
0x180019fcd  lea     rdx, [rbp+57h+var_60]
0x180019fd1  call    NfsPostNfsv4DisabledError
0x180019fd6  jmp     loc_18001A064
0x180019fdb  test    eax, eax
0x180019fdd  jnz     loc_18001A064
0x180019fe3  lea     rcx, [rbp+57h+var_90]
0x180019fe7  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(void)
0x180019fec  nop
0x180019fed  lea     rcx, [rbp+57h+var_80]
0x180019ff1  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(void)
0x180019ff6  nop
0x180019ff7  lea     rcx, [rbp+57h+var_90]
0x180019ffb  call    NfsMapVolPathToMntPointWithSharePrefix
0x18001a000  mov     r15d, [rdi+8]
0x18001a004  add     r15, rdi
0x18001a007  xor     esi, esi
0x18001a009  cmp     esi, [rdi]
0x18001a00b  jnb     short loc_18001A051
0x18001a00d  lea     rcx, [rsi+rsi*4]
0x18001a011  movups  xmm0, xmmword ptr [r15+rcx*4+4]
0x18001a017  movdqu  [rbp+57h+var_70], xmm0
0x18001a01c  lea     rax, [rbp+57h+var_60]
0x18001a020  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax; __int64
0x18001a025  lea     r9, [rbp+57h+var_80]
0x18001a029  lea     r8, [rbp+57h+var_90]
0x18001a02d  lea     rdx, [rbp+57h+var_70]
0x18001a031  mov     rcx, r14; hDevice
0x18001a034  call    NfsSrv4EnumeratePerVsOpenFile
0x18001a039  mov     ebx, eax
0x18001a03b  lea     rcx, [rbp+57h+var_60]; this
0x18001a03f  call    ?IsCanceled@CWMIContext@@UEAA_NXZ; CWMIContext::IsCanceled(void)
0x18001a044  test    al, al
0x18001a046  jnz     short loc_18001A04C
0x18001a048  inc     esi
0x18001a04a  jmp     short loc_18001A009
0x18001a04c  mov     ebx, 4C7h
0x18001a051  lea     rcx, [rbp+57h+var_80]
0x18001a055  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18001a05a  nop
0x18001a05b  lea     rcx, [rbp+57h+var_90]
0x18001a05f  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18001a064  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18001a068  jz      short loc_18001A073
0x18001a06a  mov     rcx, r14; hObject
0x18001a06d  call    cs:__imp_CloseHandle
0x18001a073  test    rdi, rdi
0x18001a076  jz      short loc_18001A08C
0x18001a078  call    cs:__imp_GetProcessHeap
0x18001a07e  mov     rcx, rax; hHeap
0x18001a081  mov     r8, rdi; lpMem
0x18001a084  xor     edx, edx; dwFlags
0x18001a086  call    cs:__imp_HeapFree
0x18001a08c  mov     dword ptr [rbp+57h+var_3C], ebx
0x18001a08f  xor     edx, edx; enum _MI_Result
0x18001a091  lea     rcx, [rbp+57h+var_60]; this
0x18001a095  call    ?PostResult@CWMIContext@@QEAAXW4_MI_Result@@@Z; CWMIContext::PostResult(_MI_Result)
0x18001a09a  nop
0x18001a09b  lea     rcx, [rbp+57h+var_60]; this
0x18001a09f  call    ??1CWMIContext@@UEAA@XZ; CWMIContext::~CWMIContext(void)
0x18001a0a4  mov     eax, ebx
0x18001a0a6  add     rsp, 0A8h
0x18001a0ad  pop     r15
0x18001a0af  pop     r14
0x18001a0b1  pop     rdi
0x18001a0b2  pop     rsi
0x18001a0b3  pop     rbx
0x18001a0b4  pop     rbp
0x18001a0b5  retn
```
