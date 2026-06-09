# SxCompressLogFile(ushort const *)

- ea: `0x180043530`
- end: `0x18004369c`
- name: `?SxCompressLogFile@@YAJPEBG@Z`
- size: `364`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180067544`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001a630`
- `0x180038c3c`
- `0x180043530`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800435c7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800435c7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180043646`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180043646`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043676`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043676`

## string_xrefs

- `0x18004357e`: `SxCompressLogFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SxCompressLogFile(LPCWSTR lpFileName)
{
  __int64 v2; // rdx
  char *FileW; // rdi
  __int64 v4; // r8
  __int64 v5; // r9
  unsigned int LastFailureAsHRESULT; // ebx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-60h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-60h]
  unsigned int v14; // [rsp+40h] [rbp-40h] BYREF
  __int16 v15; // [rsp+44h] [rbp-3Ch]
  __int16 v16; // [rsp+46h] [rbp-3Ah]
  __int16 InBuffer; // [rsp+98h] [rbp+18h] BYREF
  DWORD BytesReturned; // [rsp+A0h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids);
  }
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v14, "SxCompressLogFile", 0xF7u, 1u);
  InBuffer = 1;
  BytesReturned = 0;
  FileW = (char *)CreateFileW(lpFileName, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v14 = 0;
    v15 = 261;
    if ( DeviceIoControl(FileW, 0x9C040u, &InBuffer, 2u, 0, 0, &BytesReturned, 0) )
    {
      LastFailureAsHRESULT = 0;
      v14 = 0;
      v15 = 270;
    }
    else
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v8, v7, v9, v10, *(_QWORD *)dwCreationDispositiona);
      v14 = LastFailureAsHRESULT;
      v16 = 270;
    }
    goto LABEL_11;
  }
  LastFailureAsHRESULT = GetLastFailureAsHRESULT(FileW + 1, v2, v4, v5, *(_QWORD *)dwCreationDisposition);
  v14 = LastFailureAsHRESULT;
  v16 = 261;
  if ( FileW != (char *)-1LL && FileW )
LABEL_11:
    CloseHandle(FileW);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v14);
  return LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x180043530  mov     [rsp-8+arg_0], rbx
0x180043535  mov     [rsp-8+arg_18], rdi
0x18004353a  push    rbp
0x18004353b  mov     rbp, rsp
0x18004353e  sub     rsp, 80h
0x180043545  mov     rbx, rcx
0x180043548  mov     rcx, cs:WPP_GLOBAL_Control
0x18004354f  lea     rax, WPP_GLOBAL_Control
0x180043556  cmp     rcx, rax
0x180043559  jz      short loc_180043579
0x18004355b  test    dword ptr [rcx+1Ch], 20000000h
0x180043562  jz      short loc_180043579
0x180043564  mov     rcx, [rcx+10h]
0x180043568  lea     r8, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids
0x18004356f  mov     edx, 0Eh
0x180043574  call    WPP_SF_
0x180043579  mov     edi, 1
0x18004357e  lea     rdx, aSxcompresslogf; "SxCompressLogFile"
0x180043585  mov     r9d, edi; unsigned __int16
0x180043588  lea     rcx, [rbp+var_40]; this
0x18004358c  mov     r8d, 0F7h; unsigned __int16
0x180043592  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180043597  lea     r8d, [rdi+2]; dwShareMode
0x18004359b  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x1800435a4  mov     [rsp+80h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800435ac  xor     r9d, r9d; lpSecurityAttributes
0x1800435af  mov     edx, 0C0000000h; dwDesiredAccess
0x1800435b4  mov     [rsp+80h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800435b9  mov     rcx, rbx; lpFileName
0x1800435bc  mov     [rbp+InBuffer], di
0x1800435c0  mov     [rbp+BytesReturned], 0
0x1800435c7  call    cs:__imp_CreateFileW
0x1800435cd  mov     rdi, rax
0x1800435d0  lea     rcx, [rax+1]
0x1800435d4  test    rcx, 0FFFFFFFFFFFFFFFEh
0x1800435db  jnz     short loc_180043601
0x1800435dd  call    GetLastFailureAsHRESULT
0x1800435e2  mov     ebx, eax
0x1800435e4  mov     [rbp+var_40], eax
0x1800435e7  mov     eax, 105h
0x1800435ec  mov     [rbp+var_3A], ax
0x1800435f0  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800435f4  jz      loc_18004367C
0x1800435fa  test    rdi, rdi
0x1800435fd  jz      short loc_18004367C
0x1800435ff  jmp     short loc_180043673
0x180043601  mov     [rsp+80h+lpOverlapped], 0; lpOverlapped
0x18004360a  lea     r8, [rbp+InBuffer]; lpInBuffer
0x18004360e  mov     eax, 105h
0x180043613  mov     [rbp+var_40], 0
0x18004361a  mov     [rbp+var_3C], ax
0x18004361e  mov     r9d, 2; nInBufferSize
0x180043624  lea     rax, [rbp+BytesReturned]
0x180043628  mov     edx, 9C040h; dwIoControlCode
0x18004362d  mov     [rsp+80h+hTemplateFile], rax; lpBytesReturned
0x180043632  mov     rcx, rdi; hDevice
0x180043635  mov     [rsp+80h+dwFlagsAndAttributes], 0; nOutBufferSize
0x18004363d  mov     qword ptr [rsp+80h+dwCreationDisposition], 0; lpOutBuffer
0x180043646  call    cs:__imp_DeviceIoControl
0x18004364c  test    eax, eax
0x18004364e  jnz     short loc_180043665
0x180043650  call    GetLastFailureAsHRESULT
0x180043655  mov     ebx, eax
0x180043657  mov     [rbp+var_40], eax
0x18004365a  mov     eax, 10Eh
0x18004365f  mov     [rbp+var_3A], ax
0x180043663  jmp     short loc_180043673
0x180043665  xor     ebx, ebx
0x180043667  mov     eax, 10Eh
0x18004366c  mov     [rbp+var_40], ebx
0x18004366f  mov     [rbp+var_3C], ax
0x180043673  mov     rcx, rdi; hObject
0x180043676  call    cs:__imp_CloseHandle
0x18004367c  lea     rcx, [rbp+var_40]; this
0x180043680  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180043685  lea     r11, [rsp+80h+var_s0]
0x18004368d  mov     eax, ebx
0x18004368f  mov     rbx, [r11+10h]
0x180043693  mov     rdi, [r11+28h]
0x180043697  mov     rsp, r11
0x18004369a  pop     rbp
0x18004369b  retn
```
