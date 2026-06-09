# CRunningJITDebugger::Publish(_GUID const &,IDebugRuntimeJITServerProvider2 *,IStream * *,void * *)

- ea: `0x14000bb50`
- end: `0x14000bdca`
- name: `?Publish@CRunningJITDebugger@@CAJAEBU_GUID@@PEAUIDebugRuntimeJITServerProvider2@@PEAPEAUIStream@@PEAPEAX@Z`
- size: `634`
- prototype: `static int(const struct _GUID *, struct IDebugRuntimeJITServerProvider2 *, struct IStream **, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000b9e8`

## callees

- `0x140001020`
- `0x140001040`
- `0x140002140`
- `0x14000bb50`
- `0x14000be38`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x14000bc7e`
- `KERNEL32!GlobalFree` at `0x14000bc7e`
- `KERNEL32!GlobalAlloc` at `0x14000bb9d`
- `KERNEL32!GlobalAlloc` at `0x14000bb9d`
- `KERNEL32!UnmapViewOfFile` at `0x14000bd77`
- `KERNEL32!UnmapViewOfFile` at `0x14000bd77`
- `KERNEL32!GlobalUnlock` at `0x14000bd41`
- `KERNEL32!GlobalUnlock` at `0x14000bd41`
- `KERNEL32!GlobalLock` at `0x14000bceb`
- `KERNEL32!GlobalLock` at `0x14000bceb`
- `KERNEL32!CloseHandle` at `0x14000bd6e`
- `KERNEL32!CloseHandle` at `0x14000bd6e`
- `KERNEL32!GetLastError` at `0x14000bc95`
- `KERNEL32!GetLastError` at `0x14000bd49`
- `KERNEL32!GetLastError` at `0x14000bc95`
- `KERNEL32!GetLastError` at `0x14000bd49`
- `ole32!CoMarshalInterface` at `0x14000bbeb`
- `ole32!CoMarshalInterface` at `0x14000bbeb`
- `ole32!CreateStreamOnHGlobal` at `0x14000bbbd`
- `ole32!CreateStreamOnHGlobal` at `0x14000bbbd`
- `ole32!CoReleaseMarshalData` at `0x14000bc70`
- `ole32!CoReleaseMarshalData` at `0x14000bd8c`
- `ole32!CoReleaseMarshalData` at `0x14000bc70`
- `ole32!CoReleaseMarshalData` at `0x14000bd8c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRunningJITDebugger::Publish(const struct _GUID *a1, IUnknown *a2, struct IStream **a3, void **a4)
{
  LPSTREAM v6; // rbx
  void *v7; // r15
  unsigned int v8; // r14d
  HGLOBAL v9; // rax
  void *v10; // rsi
  HRESULT v11; // edi
  LPSTREAM v12; // rcx
  signed int LastError; // eax
  signed int v14; // ecx
  SIZE_T v15; // rcx
  const void *v16; // rax
  char *v17; // rsi
  struct IStream *v18; // rax
  void *v19; // r14
  signed int v20; // eax
  signed int v21; // ecx
  void *v23; // [rsp+30h] [rbp-59h] BYREF
  LPCVOID lpBaseAddress; // [rsp+38h] [rbp-51h] BYREF
  void **v25; // [rsp+40h] [rbp-49h]
  LPSTREAM ppstm; // [rsp+48h] [rbp-41h] BYREF
  _BYTE v27[16]; // [rsp+50h] [rbp-39h] BYREF
  unsigned int v28; // [rsp+60h] [rbp-29h]
  int v29; // [rsp+64h] [rbp-25h]

  v25 = a4;
  *a3 = 0;
  *a4 = 0;
  v6 = 0;
  lpBaseAddress = 0;
  v7 = 0;
  v8 = 0;
  v9 = GlobalAlloc(2u, 0);
  v10 = v9;
  if ( v9 )
  {
    ppstm = 0;
    v11 = CreateStreamOnHGlobal(v9, 1, &ppstm);
    if ( v11 < 0 )
    {
      _mm_lfence();
      GlobalFree(v10);
    }
    else
    {
      v11 = CoMarshalInterface(ppstm, &GUID_e7f35f78_362c_4d8a_8f76_3a7dbae0a237, a2, 0, 0, 1u);
      v12 = ppstm;
      if ( v11 < 0 )
        goto LABEL_13;
      v23 = 0;
      ((void (__fastcall *)(LPSTREAM, _QWORD, _QWORD, _QWORD))ppstm->lpVtbl->Seek)(ppstm, 0, 0, 0);
      memset_0(v27, 0, 0x50u);
      v11 = ((__int64 (__fastcall *)(LPSTREAM, _BYTE *, __int64))ppstm->lpVtbl->Stat)(ppstm, v27, 1);
      if ( v11 >= 0 )
      {
        if ( !v29 && v28 )
        {
          v6 = ppstm;
          v12 = 0;
          ppstm = 0;
          lpBaseAddress = v6;
          v7 = v10;
          v8 = v28;
          goto LABEL_13;
        }
        v11 = -2147467259;
      }
      v12 = ppstm;
      if ( !ppstm )
      {
LABEL_13:
        if ( v12 )
          ((void (__fastcall *)(LPSTREAM))v12->lpVtbl->Release)(v12);
        goto LABEL_19;
      }
      CoReleaseMarshalData(ppstm);
    }
    v12 = ppstm;
    goto LABEL_13;
  }
  LastError = GetLastError();
  v14 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    v14 = LastError;
  v11 = -2147467259;
  if ( v14 < 0 )
    v11 = v14;
LABEL_19:
  if ( v11 >= 0 )
  {
    v15 = v8 + 24;
    if ( (unsigned int)v15 > 0x4000 )
    {
      v11 = -2147418113;
    }
    else
    {
      _mm_lfence();
      v11 = CRunningJITDebugger::CreateSharedMemory(v15, &v23, (struct JIT_DEUBUGGER_SHARED_MEMORY **)&lpBaseAddress);
      if ( v11 >= 0 )
      {
        _mm_lfence();
        v16 = GlobalLock(v7);
        v17 = (char *)lpBaseAddress;
        if ( v16 )
        {
          _mm_lfence();
          *(_DWORD *)lpBaseAddress = 0;
          *(GUID *)(v17 + 4) = GUID_NULL;
          *((_DWORD *)v17 + 5) = v8;
          memcpy_0(v17 + 24, v16, v8);
          *(_DWORD *)v17 = 1246319672;
          v18 = v6;
          v6 = 0;
          *a3 = v18;
          *v25 = v23;
          v19 = 0;
          v11 = 0;
          GlobalUnlock(v7);
        }
        else
        {
          v20 = GetLastError();
          v21 = (unsigned __int16)v20 | 0x80070000;
          if ( v20 <= 0 )
            v21 = v20;
          v11 = -2147467259;
          if ( v21 < 0 )
            v11 = v21;
          v19 = v23;
        }
        CloseHandle(v19);
        UnmapViewOfFile(v17);
      }
    }
    if ( v6 )
      CoReleaseMarshalData(v6);
  }
  if ( v6 )
    ((void (__fastcall *)(LPSTREAM))v6->lpVtbl->Release)(v6);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14000bb50  mov     [rsp-8+arg_0], rbx
0x14000bb55  push    rbp
0x14000bb56  push    rsi
0x14000bb57  push    rdi
0x14000bb58  push    r12
0x14000bb5a  push    r13
0x14000bb5c  push    r14
0x14000bb5e  push    r15
0x14000bb60  lea     rbp, [rsp-27h]
0x14000bb65  sub     rsp, 0B0h
0x14000bb6c  mov     rax, cs:__security_cookie
0x14000bb73  xor     rax, rsp
0x14000bb76  mov     [rbp+57h+var_40], rax
0x14000bb7a  mov     [rbp+57h+var_A0], r9
0x14000bb7e  mov     r13, r8
0x14000bb81  mov     r12, rdx
0x14000bb84  xor     edi, edi
0x14000bb86  mov     [r8], rdi
0x14000bb89  mov     [r9], rdi
0x14000bb8c  mov     ebx, edi
0x14000bb8e  mov     [rbp+57h+lpBaseAddress], rbx
0x14000bb92  mov     r15d, edi
0x14000bb95  mov     r14d, edi
0x14000bb98  xor     edx, edx; dwBytes
0x14000bb9a  lea     ecx, [rdi+2]; uFlags
0x14000bb9d  call    cs:__imp_GlobalAlloc
0x14000bba3  mov     rsi, rax
0x14000bba6  test    rax, rax
0x14000bba9  jz      loc_14000BC95
0x14000bbaf  mov     [rbp+57h+ppstm], rdi
0x14000bbb3  lea     r8, [rbp+57h+ppstm]; ppstm
0x14000bbb7  lea     edx, [rdi+1]; fDeleteOnRelease
0x14000bbba  mov     rcx, rax; hGlobal
0x14000bbbd  call    cs:__imp_CreateStreamOnHGlobal
0x14000bbc3  mov     edi, eax
0x14000bbc5  test    eax, eax
0x14000bbc7  js      loc_14000BC78
0x14000bbcd  mov     [rsp+0E0h+mshlflags], 1; mshlflags
0x14000bbd5  and     [rsp+0E0h+var_C0], r15
0x14000bbda  xor     r9d, r9d; dwDestContext
0x14000bbdd  mov     r8, r12; pUnk
0x14000bbe0  lea     rdx, _GUID_e7f35f78_362c_4d8a_8f76_3a7dbae0a237; riid
0x14000bbe7  mov     rcx, [rbp+57h+ppstm]; pStm
0x14000bbeb  call    cs:__imp_CoMarshalInterface
0x14000bbf1  mov     edi, eax
0x14000bbf3  mov     rcx, [rbp+57h+ppstm]
0x14000bbf7  test    eax, eax
0x14000bbf9  js      loc_14000BC88
0x14000bbff  and     dword ptr [rbp+57h+var_B0], r15d
0x14000bc03  xor     eax, eax
0x14000bc05  mov     dword ptr [rbp+57h+var_B0+4], eax
0x14000bc08  mov     rax, [rcx]
0x14000bc0b  xor     r9d, r9d
0x14000bc0e  xor     r8d, r8d
0x14000bc11  mov     rdx, [rbp+57h+var_B0]
0x14000bc15  call    qword ptr [rax+28h]
0x14000bc18  xor     edx, edx; Val
0x14000bc1a  lea     r8d, [r15+50h]; Size
0x14000bc1e  lea     rcx, [rbp+57h+var_90]; void *
0x14000bc22  call    memset_0
0x14000bc27  mov     rcx, [rbp+57h+ppstm]
0x14000bc2b  mov     rax, [rcx]
0x14000bc2e  lea     r8d, [r15+1]
0x14000bc32  lea     rdx, [rbp+57h+var_90]
0x14000bc36  call    qword ptr [rax+60h]
0x14000bc39  mov     edi, eax
0x14000bc3b  test    eax, eax
0x14000bc3d  js      short loc_14000BC67
0x14000bc3f  cmp     [rbp+57h+var_7C], r15d
0x14000bc43  jnz     short loc_14000BC62
0x14000bc45  mov     eax, [rbp+57h+var_80]
0x14000bc48  test    eax, eax
0x14000bc4a  jz      short loc_14000BC62
0x14000bc4c  mov     rbx, [rbp+57h+ppstm]
0x14000bc50  xor     ecx, ecx
0x14000bc52  mov     [rbp+57h+ppstm], rcx
0x14000bc56  mov     [rbp+57h+lpBaseAddress], rbx
0x14000bc5a  mov     r15, rsi
0x14000bc5d  mov     r14d, eax
0x14000bc60  jmp     short loc_14000BC88
0x14000bc62  mov     edi, 80004005h
0x14000bc67  mov     rcx, [rbp+57h+ppstm]; pStm
0x14000bc6b  test    rcx, rcx
0x14000bc6e  jz      short loc_14000BC88
0x14000bc70  call    cs:__imp_CoReleaseMarshalData
0x14000bc76  jmp     short loc_14000BC84
0x14000bc78  lfence
0x14000bc7b  mov     rcx, rsi; hMem
0x14000bc7e  call    cs:__imp_GlobalFree
0x14000bc84  mov     rcx, [rbp+57h+ppstm]
0x14000bc88  test    rcx, rcx
0x14000bc8b  jz      short loc_14000BCB3
0x14000bc8d  mov     rax, [rcx]
0x14000bc90  call    qword ptr [rax+10h]
0x14000bc93  jmp     short loc_14000BCB3
0x14000bc95  call    cs:__imp_GetLastError
0x14000bc9b  movzx   ecx, ax
0x14000bc9e  or      ecx, 80070000h
0x14000bca4  test    eax, eax
0x14000bca6  cmovle  ecx, eax
0x14000bca9  mov     edi, 80004005h
0x14000bcae  test    ecx, ecx
0x14000bcb0  cmovs   edi, ecx
0x14000bcb3  test    edi, edi
0x14000bcb5  js      loc_14000BD93
0x14000bcbb  lea     ecx, [r14+18h]; dwNumberOfBytesToMap
0x14000bcbf  cmp     ecx, 4000h
0x14000bcc5  ja      loc_14000BD7F
0x14000bccb  lfence
0x14000bcce  lea     r8, [rbp+57h+lpBaseAddress]; struct JIT_DEUBUGGER_SHARED_MEMORY **
0x14000bcd2  lea     rdx, [rbp+57h+var_B0]; void **
0x14000bcd6  call    ?CreateSharedMemory@CRunningJITDebugger@@CAJKPEAPEAXPEAPEAUJIT_DEUBUGGER_SHARED_MEMORY@@@Z; CRunningJITDebugger::CreateSharedMemory(ulong,void * *,JIT_DEUBUGGER_SHARED_MEMORY * *)
0x14000bcdb  mov     edi, eax
0x14000bcdd  test    eax, eax
0x14000bcdf  js      loc_14000BD84
0x14000bce5  lfence
0x14000bce8  mov     rcx, r15; hMem
0x14000bceb  call    cs:__imp_GlobalLock
0x14000bcf1  mov     rsi, [rbp+57h+lpBaseAddress]
0x14000bcf5  test    rax, rax
0x14000bcf8  jz      short loc_14000BD49
0x14000bcfa  lfence
0x14000bcfd  and     dword ptr [rsi], 0
0x14000bd00  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14000bd07  movdqu  xmmword ptr [rsi+4], xmm0
0x14000bd0c  mov     [rsi+14h], r14d
0x14000bd10  mov     r8d, r14d; Size
0x14000bd13  lea     rcx, [rsi+18h]; void *
0x14000bd17  mov     rdx, rax; Src
0x14000bd1a  call    memcpy_0
0x14000bd1f  mov     dword ptr [rsi], 4A495438h
0x14000bd25  mov     rax, rbx
0x14000bd28  xor     ebx, ebx
0x14000bd2a  mov     [r13+0], rax
0x14000bd2e  mov     rax, [rbp+57h+var_B0]
0x14000bd32  mov     rcx, [rbp+57h+var_A0]
0x14000bd36  mov     [rcx], rax
0x14000bd39  xor     r14d, r14d
0x14000bd3c  xor     edi, edi
0x14000bd3e  mov     rcx, r15; hMem
0x14000bd41  call    cs:__imp_GlobalUnlock
0x14000bd47  jmp     short loc_14000BD6B
0x14000bd49  call    cs:__imp_GetLastError
0x14000bd4f  movzx   ecx, ax
0x14000bd52  or      ecx, 80070000h
0x14000bd58  test    eax, eax
0x14000bd5a  cmovle  ecx, eax
0x14000bd5d  mov     edi, 80004005h
0x14000bd62  test    ecx, ecx
0x14000bd64  cmovs   edi, ecx
0x14000bd67  mov     r14, [rbp+57h+var_B0]
0x14000bd6b  mov     rcx, r14; hObject
0x14000bd6e  call    cs:__imp_CloseHandle
0x14000bd74  mov     rcx, rsi; lpBaseAddress
0x14000bd77  call    cs:__imp_UnmapViewOfFile
0x14000bd7d  jmp     short loc_14000BD84
0x14000bd7f  mov     edi, 8000FFFFh
0x14000bd84  test    rbx, rbx
0x14000bd87  jz      short loc_14000BD93
0x14000bd89  mov     rcx, rbx; pStm
0x14000bd8c  call    cs:__imp_CoReleaseMarshalData
0x14000bd92  nop
0x14000bd93  test    rbx, rbx
0x14000bd96  jz      short loc_14000BDA1
0x14000bd98  mov     rax, [rbx]
0x14000bd9b  mov     rcx, rbx
0x14000bd9e  call    qword ptr [rax+10h]
0x14000bda1  mov     eax, edi
0x14000bda3  mov     rcx, [rbp+57h+var_40]
0x14000bda7  xor     rcx, rsp; StackCookie
0x14000bdaa  call    __security_check_cookie
0x14000bdaf  mov     rbx, [rsp+0E0h+arg_0]
0x14000bdb7  add     rsp, 0B0h
0x14000bdbe  pop     r15
0x14000bdc0  pop     r14
0x14000bdc2  pop     r13
0x14000bdc4  pop     r12
0x14000bdc6  pop     rdi
0x14000bdc7  pop     rsi
0x14000bdc8  pop     rbp
0x14000bdc9  retn
```
