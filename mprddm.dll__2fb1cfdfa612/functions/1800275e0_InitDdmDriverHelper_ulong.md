# InitDdmDriverHelper(ulong)

- ea: `0x1800275e0`
- end: `0x180027959`
- name: `?InitDdmDriverHelper@@YAKK@Z`
- size: `889`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001b570`

## callees

- `0x180007b7c`
- `0x180026e38`
- `0x1800275e0`
- `0x180071cec`
- `0x180083f84`
- `0x18008c5f2`
- `0x18008c630`

## import_xrefs

- `KERNEL32!CreateThread` at `0x180027808`
- `KERNEL32!CreateThread` at `0x180027808`
- `KERNEL32!CreateFileW` at `0x180027703`
- `KERNEL32!CreateFileW` at `0x180027703`
- `KERNEL32!CreateIoCompletionPort` at `0x180027772`
- `KERNEL32!CreateIoCompletionPort` at `0x180027772`
- `KERNEL32!CloseHandle` at `0x180027898`
- `KERNEL32!CloseHandle` at `0x1800278ad`
- `KERNEL32!CloseHandle` at `0x180027898`
- `KERNEL32!CloseHandle` at `0x1800278ad`
- `KERNEL32!GetLastError` at `0x180027715`
- `KERNEL32!GetLastError` at `0x180027784`
- `KERNEL32!GetLastError` at `0x180027817`
- `KERNEL32!GetLastError` at `0x180027715`
- `KERNEL32!GetLastError` at `0x180027784`
- `KERNEL32!GetLastError` at `0x180027817`

## string_xrefs

- `0x180027732`: `NdisWan CreateFile failed with error 0x%x`
- `0x1800277a1`: `NdisWan CreateIoPort failed with error 0x%x`
- `0x180027830`: `NdisWan IoPacket thread creation failed with error 0x%x`

## pseudocode

```c
__int64 __fastcall InitDdmDriverHelper(unsigned int a1)
{
  __int64 v2; // r8
  DWORD v3; // eax
  DWORD v4; // ebx
  __int64 v5; // r8
  __int64 v6; // rax
  HANDLE FileW; // rax
  DWORD v8; // eax
  DWORD v9; // eax
  HANDLE v10; // rax
  DWORD LastError; // eax
  __int64 v12; // r8
  __int64 v13; // rax
  unsigned int NdproxyVpnPorts; // eax
  DWORD ThreadId; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v17[16]; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v18; // [rsp+58h] [rbp-A8h]
  __int64 v19; // [rsp+60h] [rbp-A0h]
  int v20; // [rsp+70h] [rbp-90h] BYREF
  char v21[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  ThreadId = 0;
  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    v19 = 40;
    v18 = L"InitDdmDriverHelper";
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v2, 2, v17);
  }
  v3 = InitializeNdproxyIoControl((__int64)NdproxyCallback, 0, a1);
  v4 = v3;
  if ( !v3 )
  {
    FileW = CreateFileW(L"\\\\.\\NDISWAN", 0xC0000000, 3u, 0, 3u, 0x40000000u, 0);
    gblDdmDriverInfo = FileW;
    if ( FileW )
    {
      CompletionPort = CreateIoCompletionPort(FileW, 0, 0, 0);
      if ( CompletionPort )
      {
        dword_1800C88E0 = 0;
        dword_1800C8918 = 1;
        dword_1800C8950 = 3;
        v10 = CreateThread(0, 0, NdiswanRequestThread, 0, 0, &ThreadId);
        if ( !v10 )
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( (byte_1800C8404 & 8) != 0 )
          {
            LOWORD(v20) = 0;
            FormatRRASErrorString(&v20, L"NdisWan IoPacket thread creation failed with error 0x%x", LastError);
            if ( (byte_1800C8404 & 8) != 0 )
            {
              v13 = -1;
              do
                ++v13;
              while ( *(_WORD *)&v21[2 * v13 - 4] );
              v19 = (unsigned int)(2 * v13 + 2);
              v18 = (const wchar_t *)&v20;
              McGenEventWrite_EventWriteTransfer(
                &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                RasDdmTraceError,
                v12,
                2,
                v17);
            }
          }
          CloseHandle(CompletionPort);
          CompletionPort = 0;
          return v4;
        }
        CloseHandle(v10);
        NdproxyVpnPorts = GetNdproxyVpnPorts();
        v4 = NdproxyVpnPorts;
        if ( !NdproxyVpnPorts )
          return v4;
        if ( (byte_1800C8404 & 8) == 0 )
          return v4;
        LOWORD(v20) = 0;
        FormatRRASErrorString(&v20, L"NDProxy port enumeration failed with error 0x%x", NdproxyVpnPorts);
        if ( (byte_1800C8404 & 8) == 0 )
          return v4;
        v6 = -1;
        do
          ++v6;
        while ( *(_WORD *)&v21[2 * v6 - 4] );
      }
      else
      {
        v9 = GetLastError();
        v4 = v9;
        if ( (byte_1800C8404 & 8) == 0 )
          return v4;
        LOWORD(v20) = 0;
        FormatRRASErrorString(&v20, L"NdisWan CreateIoPort failed with error 0x%x", v9);
        if ( (byte_1800C8404 & 8) == 0 )
          return v4;
        v6 = -1;
        do
          ++v6;
        while ( *(_WORD *)&v21[2 * v6 - 4] );
      }
    }
    else
    {
      v8 = GetLastError();
      v4 = v8;
      if ( (byte_1800C8404 & 8) == 0 )
        return v4;
      LOWORD(v20) = 0;
      FormatRRASErrorString(&v20, L"NdisWan CreateFile failed with error 0x%x", v8);
      if ( (byte_1800C8404 & 8) == 0 )
        return v4;
      v6 = -1;
      do
        ++v6;
      while ( *(_WORD *)&v21[2 * v6 - 4] );
    }
    v18 = (const wchar_t *)&v20;
LABEL_34:
    v19 = (unsigned int)(2 * v6 + 2);
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v5, 2, v17);
    return v4;
  }
  if ( (byte_1800C8404 & 8) != 0 )
  {
    LOWORD(v20) = 0;
    FormatRRASErrorString(&v20, L"NDProxy IO control initialization failed with error 0x%x", v3);
    if ( (byte_1800C8404 & 8) != 0 )
    {
      v6 = -1;
      do
        ++v6;
      while ( *(_WORD *)&v21[2 * v6 - 4] );
      v18 = (const wchar_t *)&v20;
      goto LABEL_34;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800275e0  mov     [rsp-8+arg_8], rbx
0x1800275e5  mov     [rsp-8+arg_10], rsi
0x1800275ea  push    rbp
0x1800275eb  push    rdi
0x1800275ec  push    r14
0x1800275ee  lea     rbp, [rsp-780h]
0x1800275f6  sub     rsp, 880h
0x1800275fd  mov     rax, cs:__security_cookie
0x180027604  xor     rax, rsp
0x180027607  mov     [rbp+790h+var_20], rax
0x18002760e  mov     ebx, ecx
0x180027610  xor     edi, edi
0x180027612  lea     rcx, [rsp+890h+var_81C]; void *
0x180027617  mov     [rsp+890h+ThreadId], edi
0x18002761b  xor     edx, edx; Val
0x18002761d  mov     [rsp+890h+var_820], edi
0x180027621  mov     r8d, 7FCh; Size
0x180027627  call    memset_0
0x18002762c  test    cs:byte_1800C8404, 10h
0x180027633  lea     esi, [rdi+2]
0x180027636  lea     r14, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002763d  jz      short loc_180027670
0x18002763f  lea     rax, aInitddmdriverh; "InitDdmDriverHelper"
0x180027646  mov     [rsp+890h+var_830], 28h ; '('
0x18002764f  mov     [rsp+890h+var_838], rax
0x180027654  lea     rdx, RasDdmTraceInfo
0x18002765b  lea     rax, [rsp+890h+var_848]
0x180027660  mov     r9d, esi
0x180027663  mov     rcx, r14
0x180027666  mov     qword ptr [rsp+890h+dwCreationDisposition], rax
0x18002766b  call    McGenEventWrite_EventWriteTransfer
0x180027670  mov     r8d, ebx
0x180027673  lea     rcx, ?NdproxyCallback@@YAXPEAXK_K111@Z; NdproxyCallback(void *,ulong,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64)
0x18002767a  xor     edx, edx
0x18002767c  call    InitializeNdproxyIoControl
0x180027681  mov     ebx, eax
0x180027683  test    eax, eax
0x180027685  jz      short loc_1800276DB
0x180027687  test    cs:byte_1800C8404, 8
0x18002768e  jz      loc_180027930
0x180027694  mov     r8d, eax
0x180027697  mov     word ptr [rsp+890h+var_820], di
0x18002769c  lea     rdx, aNdproxyIoContr; "NDProxy IO control initialization faile"...
0x1800276a3  lea     rcx, [rsp+890h+var_820]
0x1800276a8  call    FormatRRASErrorString
0x1800276ad  test    cs:byte_1800C8404, 8
0x1800276b4  jz      loc_180027930
0x1800276ba  lea     rcx, [rsp+890h+var_820]
0x1800276bf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800276c3  inc     rax
0x1800276c6  cmp     [rcx+rax*2], di
0x1800276ca  jnz     short loc_1800276C3
0x1800276cc  lea     rdx, [rsp+890h+var_820]
0x1800276d1  mov     [rsp+890h+var_838], rdx
0x1800276d6  jmp     loc_180027905
0x1800276db  mov     ebx, 3
0x1800276e0  mov     [rsp+890h+hTemplateFile], rdi; hTemplateFile
0x1800276e5  mov     r8d, ebx; dwShareMode
0x1800276e8  mov     [rsp+890h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x1800276f0  xor     r9d, r9d; lpSecurityAttributes
0x1800276f3  mov     [rsp+890h+dwCreationDisposition], ebx; dwCreationDisposition
0x1800276f7  mov     edx, 0C0000000h; dwDesiredAccess
0x1800276fc  lea     rcx, FileName; "\\\\.\\NDISWAN"
0x180027703  call    cs:__imp_CreateFileW
0x180027709  mov     cs:?gblDdmDriverInfo@@3U_DDM_DRIVER_INFO@@A, rax; _DDM_DRIVER_INFO gblDdmDriverInfo
0x180027710  test    rax, rax
0x180027713  jnz     short loc_180027767
0x180027715  call    cs:__imp_GetLastError
0x18002771b  test    cs:byte_1800C8404, 8
0x180027722  mov     ebx, eax
0x180027724  jz      loc_180027930
0x18002772a  mov     r8d, eax
0x18002772d  mov     word ptr [rsp+890h+var_820], di
0x180027732  lea     rdx, aNdiswanCreatef; "NdisWan CreateFile failed with error 0x"...
0x180027739  lea     rcx, [rsp+890h+var_820]
0x18002773e  call    FormatRRASErrorString
0x180027743  test    cs:byte_1800C8404, 8
0x18002774a  jz      loc_180027930
0x180027750  lea     rcx, [rsp+890h+var_820]
0x180027755  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027759  inc     rax
0x18002775c  cmp     [rcx+rax*2], di
0x180027760  jnz     short loc_180027759
0x180027762  jmp     loc_1800278FB
0x180027767  xor     r9d, r9d; NumberOfConcurrentThreads
0x18002776a  xor     r8d, r8d; CompletionKey
0x18002776d  xor     edx, edx; ExistingCompletionPort
0x18002776f  mov     rcx, rax; FileHandle
0x180027772  call    cs:__imp_CreateIoCompletionPort
0x180027778  mov     cs:CompletionPort, rax
0x18002777f  test    rax, rax
0x180027782  jnz     short loc_1800277D6
0x180027784  call    cs:__imp_GetLastError
0x18002778a  test    cs:byte_1800C8404, 8
0x180027791  mov     ebx, eax
0x180027793  jz      loc_180027930
0x180027799  mov     r8d, eax
0x18002779c  mov     word ptr [rsp+890h+var_820], di
0x1800277a1  lea     rdx, aNdiswanCreatei; "NdisWan CreateIoPort failed with error "...
0x1800277a8  lea     rcx, [rsp+890h+var_820]
0x1800277ad  call    FormatRRASErrorString
0x1800277b2  test    cs:byte_1800C8404, 8
0x1800277b9  jz      loc_180027930
0x1800277bf  lea     rcx, [rsp+890h+var_820]
0x1800277c4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800277c8  inc     rax
0x1800277cb  cmp     [rcx+rax*2], di
0x1800277cf  jnz     short loc_1800277C8
0x1800277d1  jmp     loc_1800278FB
0x1800277d6  lea     rax, [rsp+890h+ThreadId]
0x1800277db  mov     cs:dword_1800C88E0, edi
0x1800277e1  mov     qword ptr [rsp+890h+dwFlagsAndAttributes], rax; lpThreadId
0x1800277e6  lea     r8, ?NdiswanRequestThread@@YAKPEAX@Z; lpStartAddress
0x1800277ed  xor     r9d, r9d; lpParameter
0x1800277f0  mov     [rsp+890h+dwCreationDisposition], edi; dwCreationFlags
0x1800277f4  xor     edx, edx; dwStackSize
0x1800277f6  mov     cs:dword_1800C8918, 1
0x180027800  xor     ecx, ecx; lpThreadAttributes
0x180027802  mov     cs:dword_1800C8950, ebx
0x180027808  call    cs:__imp_CreateThread
0x18002780e  test    rax, rax
0x180027811  jnz     loc_1800278AA
0x180027817  call    cs:__imp_GetLastError
0x18002781d  test    cs:byte_1800C8404, 8
0x180027824  mov     ebx, eax
0x180027826  jz      short loc_180027891
0x180027828  mov     r8d, eax
0x18002782b  mov     word ptr [rsp+890h+var_820], di
0x180027830  lea     rdx, aNdiswanIopacke; "NdisWan IoPacket thread creation failed"...
0x180027837  lea     rcx, [rsp+890h+var_820]
0x18002783c  call    FormatRRASErrorString
0x180027841  test    cs:byte_1800C8404, 8
0x180027848  jz      short loc_180027891
0x18002784a  lea     rcx, [rsp+890h+var_820]
0x18002784f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027853  inc     rax
0x180027856  cmp     [rcx+rax*2], di
0x18002785a  jnz     short loc_180027853
0x18002785c  lea     eax, ds:2[rax*2]
0x180027863  mov     dword ptr [rsp+890h+var_830+4], edi
0x180027867  lea     rcx, [rsp+890h+var_820]
0x18002786c  mov     dword ptr [rsp+890h+var_830], eax
0x180027870  lea     rax, [rsp+890h+var_848]
0x180027875  mov     [rsp+890h+var_838], rcx
0x18002787a  mov     r9d, esi
0x18002787d  mov     qword ptr [rsp+890h+dwCreationDisposition], rax
0x180027882  lea     rdx, RasDdmTraceError
0x180027889  mov     rcx, r14
0x18002788c  call    McGenEventWrite_EventWriteTransfer
0x180027891  mov     rcx, cs:CompletionPort; hObject
0x180027898  call    cs:__imp_CloseHandle
0x18002789e  mov     cs:CompletionPort, rdi
0x1800278a5  jmp     loc_180027930
0x1800278aa  mov     rcx, rax; hObject
0x1800278ad  call    cs:__imp_CloseHandle
0x1800278b3  call    ?GetNdproxyVpnPorts@@YAKXZ; GetNdproxyVpnPorts(void)
0x1800278b8  mov     ebx, eax
0x1800278ba  test    eax, eax
0x1800278bc  jz      short loc_180027930
0x1800278be  test    cs:byte_1800C8404, 8
0x1800278c5  jz      short loc_180027930
0x1800278c7  mov     r8d, eax
0x1800278ca  mov     word ptr [rsp+890h+var_820], di
0x1800278cf  lea     rdx, aNdproxyPortEnu; "NDProxy port enumeration failed with er"...
0x1800278d6  lea     rcx, [rsp+890h+var_820]
0x1800278db  call    FormatRRASErrorString
0x1800278e0  test    cs:byte_1800C8404, 8
0x1800278e7  jz      short loc_180027930
0x1800278e9  lea     rcx, [rsp+890h+var_820]
0x1800278ee  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800278f2  inc     rax
0x1800278f5  cmp     [rcx+rax*2], di
0x1800278f9  jnz     short loc_1800278F2
0x1800278fb  lea     rcx, [rsp+890h+var_820]
0x180027900  mov     [rsp+890h+var_838], rcx
0x180027905  lea     eax, ds:2[rax*2]
0x18002790c  mov     dword ptr [rsp+890h+var_830+4], edi
0x180027910  mov     dword ptr [rsp+890h+var_830], eax
0x180027914  lea     rdx, RasDdmTraceError
0x18002791b  lea     rax, [rsp+890h+var_848]
0x180027920  mov     r9d, esi
0x180027923  mov     rcx, r14
0x180027926  mov     qword ptr [rsp+890h+dwCreationDisposition], rax
0x18002792b  call    McGenEventWrite_EventWriteTransfer
0x180027930  mov     eax, ebx
0x180027932  mov     rcx, [rbp+790h+var_20]
0x180027939  xor     rcx, rsp; StackCookie
0x18002793c  call    __security_check_cookie
0x180027941  lea     r11, [rsp+890h+var_10]
0x180027949  mov     rbx, [r11+28h]
0x18002794d  mov     rsi, [r11+30h]
0x180027951  mov     rsp, r11
0x180027954  pop     r14
0x180027956  pop     rdi
0x180027957  pop     rbp
0x180027958  retn
```
