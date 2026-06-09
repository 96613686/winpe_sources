# InitDdmDriverHelper(ulong)

- ea: `0x1800298e4`
- end: `0x180029c9b`
- name: `?InitDdmDriverHelper@@YAKK@Z`
- size: `951`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001bf40`

## callees

- `0x180007c0c`
- `0x180029100`
- `0x1800298e4`
- `0x1800755b8`
- `0x180089e3c`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `KERNEL32!CreateThread` at `0x180029b34`
- `KERNEL32!CreateThread` at `0x180029b34`
- `KERNEL32!CreateFileW` at `0x180029a1f`
- `KERNEL32!CreateFileW` at `0x180029a1f`
- `KERNEL32!CreateIoCompletionPort` at `0x180029a96`
- `KERNEL32!CreateIoCompletionPort` at `0x180029a96`
- `KERNEL32!CloseHandle` at `0x180029bcc`
- `KERNEL32!CloseHandle` at `0x180029be7`
- `KERNEL32!CloseHandle` at `0x180029bcc`
- `KERNEL32!CloseHandle` at `0x180029be7`
- `KERNEL32!GetLastError` at `0x180029a37`
- `KERNEL32!GetLastError` at `0x180029aae`
- `KERNEL32!GetLastError` at `0x180029b49`
- `KERNEL32!GetLastError` at `0x180029a37`
- `KERNEL32!GetLastError` at `0x180029aae`
- `KERNEL32!GetLastError` at `0x180029b49`

## string_xrefs

- `0x180029a5a`: `NdisWan CreateFile failed with error 0x%x`
- `0x180029ad1`: `NdisWan CreateIoPort failed with error 0x%x`
- `0x180029b68`: `NdisWan IoPacket thread creation failed with error 0x%x`

## pseudocode

```c
__int64 __fastcall InitDdmDriverHelper(unsigned int a1)
{
  __int64 v2; // r8
  __int64 v3; // rbx
  __int64 v4; // rax
  DWORD v5; // eax
  DWORD v6; // edi
  __int64 v7; // r8
  HANDLE FileW; // rax
  DWORD v9; // eax
  DWORD v10; // eax
  HANDLE v11; // rax
  DWORD LastError; // eax
  __int64 v13; // r8
  DWORD NdproxyVpnPorts; // eax
  DWORD ThreadId; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE v17[16]; // [rsp+50h] [rbp-B8h] BYREF
  const wchar_t *v18; // [rsp+60h] [rbp-A8h]
  int v19; // [rsp+68h] [rbp-A0h]
  int v20; // [rsp+6Ch] [rbp-9Ch]
  int v21; // [rsp+78h] [rbp-90h] BYREF
  char v22[2044]; // [rsp+7Ch] [rbp-8Ch] BYREF

  ThreadId = 0;
  v21 = 0;
  memset_0(v22, 0, sizeof(v22));
  v3 = -1;
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    v4 = -1;
    do
      ++v4;
    while ( aInitddmdriverh[v4] );
    v18 = L"InitDdmDriverHelper";
    v19 = 2 * v4 + 2;
    v20 = 0;
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v2, 2, v17);
  }
  v5 = InitializeNdproxyIoControl((__int64)NdproxyCallback, 0, a1);
  v6 = v5;
  if ( !v5 )
  {
    FileW = CreateFileW(L"\\\\.\\NDISWAN", 0xC0000000, 3u, 0, 3u, 0x40000000u, 0);
    gblDdmDriverInfo = FileW;
    if ( FileW )
    {
      CompletionPort = CreateIoCompletionPort(FileW, 0, 0, 0);
      if ( CompletionPort )
      {
        dword_1800CF8E0 = 0;
        dword_1800CF918 = 1;
        dword_1800CF950 = 3;
        v11 = CreateThread(0, 0, NdiswanRequestThread, 0, 0, &ThreadId);
        if ( !v11 )
        {
          LastError = GetLastError();
          v6 = LastError;
          if ( (byte_1800CF404 & 8) != 0 )
          {
            LOWORD(v21) = 0;
            FormatRRASErrorString(&v21, L"NdisWan IoPacket thread creation failed with error 0x%x", LastError);
            if ( (byte_1800CF404 & 8) != 0 )
            {
              do
                ++v3;
              while ( *(_WORD *)&v22[2 * v3 - 4] );
              v20 = 0;
              v19 = 2 * v3 + 2;
              v18 = (const wchar_t *)&v21;
              McGenEventWrite_EventWriteTransfer(
                &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                RasDdmTraceError,
                v13,
                2,
                v17);
            }
          }
          CloseHandle(CompletionPort);
          CompletionPort = 0;
          return v6;
        }
        CloseHandle(v11);
        NdproxyVpnPorts = GetNdproxyVpnPorts();
        v6 = NdproxyVpnPorts;
        if ( !NdproxyVpnPorts )
          return v6;
        if ( (byte_1800CF404 & 8) == 0 )
          return v6;
        LOWORD(v21) = 0;
        FormatRRASErrorString(&v21, L"NDProxy port enumeration failed with error 0x%x", NdproxyVpnPorts);
        if ( (byte_1800CF404 & 8) == 0 )
          return v6;
        do
          ++v3;
        while ( *(_WORD *)&v22[2 * v3 - 4] );
      }
      else
      {
        v10 = GetLastError();
        v6 = v10;
        if ( (byte_1800CF404 & 8) == 0 )
          return v6;
        LOWORD(v21) = 0;
        FormatRRASErrorString(&v21, L"NdisWan CreateIoPort failed with error 0x%x", v10);
        if ( (byte_1800CF404 & 8) == 0 )
          return v6;
        do
          ++v3;
        while ( *(_WORD *)&v22[2 * v3 - 4] );
      }
    }
    else
    {
      v9 = GetLastError();
      v6 = v9;
      if ( (byte_1800CF404 & 8) == 0 )
        return v6;
      LOWORD(v21) = 0;
      FormatRRASErrorString(&v21, L"NdisWan CreateFile failed with error 0x%x", v9);
      if ( (byte_1800CF404 & 8) == 0 )
        return v6;
      do
        ++v3;
      while ( *(_WORD *)&v22[2 * v3 - 4] );
    }
    v18 = (const wchar_t *)&v21;
LABEL_31:
    v20 = 0;
    v19 = 2 * v3 + 2;
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v7, 2, v17);
    return v6;
  }
  if ( (byte_1800CF404 & 8) != 0 )
  {
    LOWORD(v21) = 0;
    FormatRRASErrorString(&v21, L"NDProxy IO control initialization failed with error 0x%x", v5);
    if ( (byte_1800CF404 & 8) != 0 )
    {
      do
        ++v3;
      while ( *(_WORD *)&v22[2 * v3 - 4] );
      v18 = (const wchar_t *)&v21;
      goto LABEL_31;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1800298e4  mov     rax, rsp
0x1800298e7  mov     [rax+10h], rbx
0x1800298eb  mov     [rax+18h], rsi
0x1800298ef  mov     [rax+20h], rdi
0x1800298f3  push    rbp
0x1800298f4  push    r14
0x1800298f6  push    r15
0x1800298f8  lea     rbp, [rax-798h]
0x1800298ff  sub     rsp, 880h
0x180029906  mov     rax, cs:__security_cookie
0x18002990d  xor     rax, rsp
0x180029910  mov     [rbp+790h+var_20], rax
0x180029917  mov     edi, ecx
0x180029919  xor     esi, esi
0x18002991b  lea     rcx, [rsp+890h+var_81C]; void *
0x180029920  mov     [rsp+890h+ThreadId], esi
0x180029924  xor     edx, edx; Val
0x180029926  mov     [rsp+890h+var_820], esi
0x18002992a  mov     r8d, 7FCh; Size
0x180029930  call    memset_0
0x180029935  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180029939  lea     r14d, [rsi+2]
0x18002993d  test    cs:byte_1800CF404, 10h
0x180029944  lea     r15, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002994b  jz      short loc_180029990
0x18002994d  lea     rcx, aInitddmdriverh; "InitDdmDriverHelper"
0x180029954  mov     rax, rbx
0x180029957  inc     rax
0x18002995a  cmp     [rcx+rax*2], si
0x18002995e  jnz     short loc_180029957
0x180029960  lea     eax, ds:2[rax*2]
0x180029967  mov     [rsp+890h+var_838], rcx
0x18002996c  mov     [rsp+890h+var_830], eax
0x180029970  lea     rdx, RasDdmTraceInfo
0x180029977  lea     rax, [rsp+890h+var_848]
0x18002997c  mov     [rsp+890h+var_82C], esi
0x180029980  mov     r9d, r14d
0x180029983  mov     qword ptr [rsp+890h+dwCreationDisposition], rax
0x180029988  mov     rcx, r15
0x18002998b  call    McGenEventWrite_EventWriteTransfer
0x180029990  mov     r8d, edi
0x180029993  lea     rcx, ?NdproxyCallback@@YAXPEAXK_K111@Z; NdproxyCallback(void *,ulong,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64)
0x18002999a  xor     edx, edx
0x18002999c  call    InitializeNdproxyIoControl
0x1800299a1  mov     edi, eax
0x1800299a3  test    eax, eax
0x1800299a5  jz      short loc_1800299F7
0x1800299a7  test    cs:byte_1800CF404, 8
0x1800299ae  jz      loc_180029C6C
0x1800299b4  mov     r8d, eax
0x1800299b7  mov     word ptr [rsp+890h+var_820], si
0x1800299bc  lea     rdx, aNdproxyIoContr; "NDProxy IO control initialization faile"...
0x1800299c3  lea     rcx, [rsp+890h+var_820]
0x1800299c8  call    FormatRRASErrorString
0x1800299cd  test    cs:byte_1800CF404, 8
0x1800299d4  jz      loc_180029C6C
0x1800299da  lea     rax, [rsp+890h+var_820]
0x1800299df  inc     rbx
0x1800299e2  cmp     [rax+rbx*2], si
0x1800299e6  jnz     short loc_1800299DF
0x1800299e8  lea     rdx, [rsp+890h+var_820]
0x1800299ed  mov     [rsp+890h+var_838], rdx
0x1800299f2  jmp     loc_180029C41
0x1800299f7  mov     edi, 3
0x1800299fc  mov     [rsp+890h+hTemplateFile], rsi; hTemplateFile
0x180029a01  mov     r8d, edi; dwShareMode
0x180029a04  mov     [rsp+890h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x180029a0c  xor     r9d, r9d; lpSecurityAttributes
0x180029a0f  mov     [rsp+890h+dwCreationDisposition], edi; dwCreationDisposition
0x180029a13  mov     edx, 0C0000000h; dwDesiredAccess
0x180029a18  lea     rcx, FileName; "\\\\.\\NDISWAN"
0x180029a1f  call    cs:__imp_CreateFileW
0x180029a26  nop     dword ptr [rax+rax+00h]
0x180029a2b  mov     cs:?gblDdmDriverInfo@@3U_DDM_DRIVER_INFO@@A, rax; _DDM_DRIVER_INFO gblDdmDriverInfo
0x180029a32  test    rax, rax
0x180029a35  jnz     short loc_180029A8B
0x180029a37  call    cs:__imp_GetLastError
0x180029a3e  nop     dword ptr [rax+rax+00h]
0x180029a43  test    cs:byte_1800CF404, 8
0x180029a4a  mov     edi, eax
0x180029a4c  jz      loc_180029C6C
0x180029a52  mov     r8d, eax
0x180029a55  mov     word ptr [rsp+890h+var_820], si
0x180029a5a  lea     rdx, aNdiswanCreatef; "NdisWan CreateFile failed with error 0x"...
0x180029a61  lea     rcx, [rsp+890h+var_820]
0x180029a66  call    FormatRRASErrorString
0x180029a6b  test    cs:byte_1800CF404, 8
0x180029a72  jz      loc_180029C6C
0x180029a78  lea     rax, [rsp+890h+var_820]
0x180029a7d  inc     rbx
0x180029a80  cmp     [rax+rbx*2], si
0x180029a84  jnz     short loc_180029A7D
0x180029a86  jmp     loc_180029C37
0x180029a8b  xor     r9d, r9d; NumberOfConcurrentThreads
0x180029a8e  xor     r8d, r8d; CompletionKey
0x180029a91  xor     edx, edx; ExistingCompletionPort
0x180029a93  mov     rcx, rax; FileHandle
0x180029a96  call    cs:__imp_CreateIoCompletionPort
0x180029a9d  nop     dword ptr [rax+rax+00h]
0x180029aa2  mov     cs:CompletionPort, rax
0x180029aa9  test    rax, rax
0x180029aac  jnz     short loc_180029B02
0x180029aae  call    cs:__imp_GetLastError
0x180029ab5  nop     dword ptr [rax+rax+00h]
0x180029aba  test    cs:byte_1800CF404, 8
0x180029ac1  mov     edi, eax
0x180029ac3  jz      loc_180029C6C
0x180029ac9  mov     r8d, eax
0x180029acc  mov     word ptr [rsp+890h+var_820], si
0x180029ad1  lea     rdx, aNdiswanCreatei; "NdisWan CreateIoPort failed with error "...
0x180029ad8  lea     rcx, [rsp+890h+var_820]
0x180029add  call    FormatRRASErrorString
0x180029ae2  test    cs:byte_1800CF404, 8
0x180029ae9  jz      loc_180029C6C
0x180029aef  lea     rax, [rsp+890h+var_820]
0x180029af4  inc     rbx
0x180029af7  cmp     [rax+rbx*2], si
0x180029afb  jnz     short loc_180029AF4
0x180029afd  jmp     loc_180029C37
0x180029b02  lea     rax, [rsp+890h+ThreadId]
0x180029b07  mov     cs:dword_1800CF8E0, esi
0x180029b0d  mov     qword ptr [rsp+890h+dwFlagsAndAttributes], rax; lpThreadId
0x180029b12  lea     r8, ?NdiswanRequestThread@@YAKPEAX@Z; lpStartAddress
0x180029b19  xor     r9d, r9d; lpParameter
0x180029b1c  mov     [rsp+890h+dwCreationDisposition], esi; dwCreationFlags
0x180029b20  xor     edx, edx; dwStackSize
0x180029b22  mov     cs:dword_1800CF918, 1
0x180029b2c  xor     ecx, ecx; lpThreadAttributes
0x180029b2e  mov     cs:dword_1800CF950, edi
0x180029b34  call    cs:__imp_CreateThread
0x180029b3b  nop     dword ptr [rax+rax+00h]
0x180029b40  test    rax, rax
0x180029b43  jnz     loc_180029BE4
0x180029b49  call    cs:__imp_GetLastError
0x180029b50  nop     dword ptr [rax+rax+00h]
0x180029b55  test    cs:byte_1800CF404, 8
0x180029b5c  mov     edi, eax
0x180029b5e  jz      short loc_180029BC5
0x180029b60  mov     r8d, eax
0x180029b63  mov     word ptr [rsp+890h+var_820], si
0x180029b68  lea     rdx, aNdiswanIopacke; "NdisWan IoPacket thread creation failed"...
0x180029b6f  lea     rcx, [rsp+890h+var_820]
0x180029b74  call    FormatRRASErrorString
0x180029b79  test    cs:byte_1800CF404, 8
0x180029b80  jz      short loc_180029BC5
0x180029b82  lea     rax, [rsp+890h+var_820]
0x180029b87  inc     rbx
0x180029b8a  cmp     [rax+rbx*2], si
0x180029b8e  jnz     short loc_180029B87
0x180029b90  lea     eax, ds:2[rbx*2]
0x180029b97  mov     [rsp+890h+var_82C], esi
0x180029b9b  lea     rcx, [rsp+890h+var_820]
0x180029ba0  mov     [rsp+890h+var_830], eax
0x180029ba4  lea     rax, [rsp+890h+var_848]
0x180029ba9  mov     [rsp+890h+var_838], rcx
0x180029bae  mov     r9d, r14d
0x180029bb1  mov     qword ptr [rsp+890h+dwCreationDisposition], rax
0x180029bb6  lea     rdx, RasDdmTraceError
0x180029bbd  mov     rcx, r15
0x180029bc0  call    McGenEventWrite_EventWriteTransfer
0x180029bc5  mov     rcx, cs:CompletionPort; hObject
0x180029bcc  call    cs:__imp_CloseHandle
0x180029bd3  nop     dword ptr [rax+rax+00h]
0x180029bd8  mov     cs:CompletionPort, rsi
0x180029bdf  jmp     loc_180029C6C
0x180029be4  mov     rcx, rax; hObject
0x180029be7  call    cs:__imp_CloseHandle
0x180029bee  nop     dword ptr [rax+rax+00h]
0x180029bf3  call    ?GetNdproxyVpnPorts@@YAKXZ; GetNdproxyVpnPorts(void)
0x180029bf8  mov     edi, eax
0x180029bfa  test    eax, eax
0x180029bfc  jz      short loc_180029C6C
0x180029bfe  test    cs:byte_1800CF404, 8
0x180029c05  jz      short loc_180029C6C
0x180029c07  mov     r8d, eax
0x180029c0a  mov     word ptr [rsp+890h+var_820], si
0x180029c0f  lea     rdx, aNdproxyPortEnu; "NDProxy port enumeration failed with er"...
0x180029c16  lea     rcx, [rsp+890h+var_820]
0x180029c1b  call    FormatRRASErrorString
0x180029c20  test    cs:byte_1800CF404, 8
0x180029c27  jz      short loc_180029C6C
0x180029c29  lea     rax, [rsp+890h+var_820]
0x180029c2e  inc     rbx
0x180029c31  cmp     [rax+rbx*2], si
0x180029c35  jnz     short loc_180029C2E
0x180029c37  lea     rcx, [rsp+890h+var_820]
0x180029c3c  mov     [rsp+890h+var_838], rcx
0x180029c41  lea     eax, ds:2[rbx*2]
0x180029c48  mov     [rsp+890h+var_82C], esi
0x180029c4c  mov     [rsp+890h+var_830], eax
0x180029c50  lea     rdx, RasDdmTraceError
0x180029c57  lea     rax, [rsp+890h+var_848]
0x180029c5c  mov     r9d, r14d
0x180029c5f  mov     rcx, r15
0x180029c62  mov     qword ptr [rsp+890h+dwCreationDisposition], rax
0x180029c67  call    McGenEventWrite_EventWriteTransfer
0x180029c6c  mov     eax, edi
0x180029c6e  mov     rcx, [rbp+790h+var_20]
0x180029c75  xor     rcx, rsp; StackCookie
0x180029c78  call    __security_check_cookie
0x180029c7d  lea     r11, [rsp+890h+var_10]
0x180029c85  mov     rbx, [r11+28h]
0x180029c89  mov     rsi, [r11+30h]
0x180029c8d  mov     rdi, [r11+38h]
0x180029c91  mov     rsp, r11
0x180029c94  pop     r15
0x180029c96  pop     r14
0x180029c98  pop     rbp
0x180029c99  retn
```
