# InitializeDemandDial

- ea: `0x180011374`
- end: `0x180011781`
- name: `InitializeDemandDial`
- size: `1037`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180020238`
- `0x1800208c4`

## callees

- `0x18000ac60`
- `0x18000eb50`
- `0x18000ec98`
- `0x180011374`
- `0x180011914`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlStringFromGUID` at `0x1800116c9`
- `ntdll!RtlStringFromGUID` at `0x1800116c9`
- `ntdll!NtDeviceIoControlFile` at `0x180011619`
- `ntdll!NtDeviceIoControlFile` at `0x180011619`
- `KERNEL32!CreateFileA` at `0x18001145f`
- `KERNEL32!CreateFileA` at `0x18001151f`
- `KERNEL32!CreateFileA` at `0x18001145f`
- `KERNEL32!CreateFileA` at `0x18001151f`
- `KERNEL32!Sleep` at `0x18001147b`
- `KERNEL32!Sleep` at `0x18001147b`
- `KERNEL32!CloseHandle` at `0x180011531`
- `KERNEL32!CloseHandle` at `0x180011666`
- `KERNEL32!CloseHandle` at `0x18001166f`
- `KERNEL32!CloseHandle` at `0x180011531`
- `KERNEL32!CloseHandle` at `0x180011666`
- `KERNEL32!CloseHandle` at `0x18001166f`
- `KERNEL32!GetLastError` at `0x180011485`
- `KERNEL32!GetLastError` at `0x180011537`
- `KERNEL32!GetLastError` at `0x180011485`
- `KERNEL32!GetLastError` at `0x180011537`
- `KERNEL32!HeapFree` at `0x180011643`
- `KERNEL32!HeapFree` at `0x18001164e`
- `KERNEL32!HeapFree` at `0x180011721`
- `KERNEL32!HeapFree` at `0x180011643`
- `KERNEL32!HeapFree` at `0x18001164e`
- `KERNEL32!HeapFree` at `0x180011721`
- `KERNEL32!HeapAlloc` at `0x1800115d1`
- `KERNEL32!HeapAlloc` at `0x1800115d1`

## string_xrefs

- `0x1800114a4`: `InitializeDemandDial: Could not open WANARP for read - %d`
- `0x180011556`: `InitializeDemandDial: Could not open WANARP for write - %d`

## pseudocode

```c
__int64 __fastcall InitializeDemandDial(unsigned int a1)
{
  unsigned int v2; // r12d
  const CHAR *v3; // rdi
  int v4; // ebx
  HANDLE FileA; // rsi
  DWORD LastError; // eax
  char v7; // cl
  DWORD v8; // ebx
  HANDLE v10; // r14
  DWORD v11; // eax
  char v12; // cl
  unsigned int v13; // edi
  int v14; // r15d
  ULONG OutputBufferLength; // r15d
  _DWORD *OutputBuffer; // rax
  _DWORD *v17; // rbx
  NTSTATUS v18; // eax
  unsigned int i; // esi
  __int64 v20; // rdi
  __int64 v21; // rdx
  __int64 v22; // [rsp+50h] [rbp-868h] BYREF
  _UNICODE_STRING GuidString; // [rsp+58h] [rbp-860h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-850h] BYREF
  int v25; // [rsp+80h] [rbp-838h] BYREF
  int v26; // [rsp+84h] [rbp-834h] BYREF

  v2 = 0;
  v25 = 0;
  IoStatusBlock = 0;
  memset_0(&v26, 0, 0x7FCu);
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v25) = 0;
    FormatRRASErrorString(&v25, L"Entered: %ws", L"InitializeDemandDial");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v25);
  }
  v3 = "\\\\.\\WANARP";
  v4 = 10;
  if ( !a1 )
    v3 = "\\\\.\\WANARPV6";
  while ( 1 )
  {
    FileA = CreateFileA(v3, 0x80000000, 3u, 0, 3u, 0x40000000u, 0);
    if ( FileA != (HANDLE)-1LL )
      break;
    if ( !v4 )
    {
      LastError = GetLastError();
      v7 = Microsoft_Windows_RRASEnableBits;
      v8 = LastError;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v25) = 0;
        FormatRRASErrorString(&v25, L"InitializeDemandDial: Could not open WANARP for read - %d", LastError);
        v7 = Microsoft_Windows_RRASEnableBits;
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v25);
          v7 = Microsoft_Windows_RRASEnableBits;
        }
      }
      if ( v7 < 0 )
        goto LABEL_13;
      return v8;
    }
    Sleep(0x1F4u);
    --v4;
  }
  v10 = CreateFileA(v3, 0xC0000000, 3u, 0, 3u, 0x40000000u, 0);
  if ( v10 == (HANDLE)-1LL )
  {
    CloseHandle(FileA);
    v11 = GetLastError();
    v12 = Microsoft_Windows_RRASEnableBits;
    v8 = v11;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v25) = 0;
      FormatRRASErrorString(&v25, L"InitializeDemandDial: Could not open WANARP for write - %d", v11);
      v12 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v25);
        v12 = Microsoft_Windows_RRASEnableBits;
      }
    }
    if ( v12 < 0 )
LABEL_13:
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: InitializeDemandDial");
    return v8;
  }
  v13 = -1073741811;
  v14 = 5;
  while ( v2 < 3 )
  {
    OutputBufferLength = 32 * v14 + 8;
    OutputBuffer = HeapAlloc(IPRouterHeap, 0, OutputBufferLength);
    v17 = OutputBuffer;
    if ( !OutputBuffer )
    {
      v13 = 8;
      goto LABEL_30;
    }
    *OutputBuffer = 1;
    v18 = NtDeviceIoControlFile(
            v10,
            0,
            0,
            0,
            &IoStatusBlock,
            0x90018018,
            OutputBuffer,
            0x28u,
            OutputBuffer,
            OutputBufferLength);
    v13 = v18;
    if ( !v18 )
      goto LABEL_31;
    if ( v18 != 261 )
    {
      HeapFree(IPRouterHeap, 0, v17);
LABEL_30:
      CloseHandle(FileA);
      CloseHandle(v10);
      return v13;
    }
    ++v2;
    v14 = v17[1] + 5 * v2;
    HeapFree(IPRouterHeap, 0, v17);
  }
  v17 = 0;
  if ( v13 )
    goto LABEL_30;
LABEL_31:
  if ( a1 )
  {
    g_hWanarpRead = FileA;
    g_hWanarpWrite = v10;
  }
  else
  {
    g_hWanarpReadV6 = (__int64)FileA;
    g_hWanarpWriteV6 = (__int64)v10;
  }
  for ( i = 0; i < v17[1]; ++i )
  {
    v20 = 8LL * i;
    GuidString = 0;
    v22 = 0;
    if ( !RtlStringFromGUID((const GUID *const)&v17[v20 + 2], &GuidString) )
    {
      v21 = (unsigned int)v17[v20 + 6];
      if ( a1 )
        CreateDialOutInterfaceV4(
          GuidString.Buffer,
          v21,
          (unsigned int)v17[v20 + 7],
          (unsigned int)v17[v20 + 8],
          v17[v20 + 9],
          &v22);
      else
        CreateDialOutInterfaceV6(GuidString.Buffer, v21, &v22);
    }
  }
  HeapFree(IPRouterHeap, 0, v17);
  PostIoctlForDemandDialNotification(a1);
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"Leaving: InitializeDemandDial");
  return 0;
}

```

## disassembly

```asm
0x180011374  mov     r11, rsp
0x180011377  mov     [r11+10h], rbx
0x18001137b  mov     [r11+18h], rsi
0x18001137f  push    rdi
0x180011380  push    r12
0x180011382  push    r13
0x180011384  push    r14
0x180011386  push    r15
0x180011388  sub     rsp, 890h
0x18001138f  mov     rax, cs:__security_cookie
0x180011396  xor     rax, rsp
0x180011399  mov     [rsp+8B8h+var_38], rax
0x1800113a1  mov     r13d, ecx
0x1800113a4  xorps   xmm0, xmm0
0x1800113a7  xor     r12d, r12d
0x1800113aa  lea     rcx, [r11-834h]; void *
0x1800113b1  xor     edx, edx; Val
0x1800113b3  mov     [r11-838h], r12d
0x1800113ba  mov     r8d, 7FCh; Size
0x1800113c0  movups  xmmword ptr [rsp+8B8h+IoStatusBlock], xmm0
0x1800113c5  call    memset_0
0x1800113ca  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x1800113d1  lea     r15, RasRtrmgrTraceInfo
0x1800113d8  lea     r14, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800113df  jge     short loc_180011421
0x1800113e1  lea     r8, aInitializedema_0; "InitializeDemandDial"
0x1800113e8  mov     word ptr [rsp+8B8h+var_838], r12w
0x1800113f1  lea     rdx, aEnteredWs; "Entered: %ws"
0x1800113f8  lea     rcx, [rsp+8B8h+var_838]
0x180011400  call    FormatRRASErrorString
0x180011405  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18001140c  jge     short loc_180011421
0x18001140e  lea     r8, [rsp+8B8h+var_838]
0x180011416  mov     rdx, r15
0x180011419  mov     rcx, r14
0x18001141c  call    McTemplateU0z_EventWriteTransfer
0x180011421  test    r13d, r13d
0x180011424  lea     rax, FileName; "\\\\.\\WANARPV6"
0x18001142b  lea     rdi, aWanarp; "\\\\.\\WANARP"
0x180011432  mov     ebx, 0Ah
0x180011437  cmovz   rdi, rax
0x18001143b  xor     r9d, r9d; lpSecurityAttributes
0x18001143e  mov     [rsp+8B8h+hTemplateFile], r12; hTemplateFile
0x180011443  mov     [rsp+8B8h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x18001144b  mov     edx, 80000000h; dwDesiredAccess
0x180011450  mov     rcx, rdi; lpFileName
0x180011453  mov     [rsp+8B8h+dwCreationDisposition], 3; dwCreationDisposition
0x18001145b  lea     r8d, [r9+3]; dwShareMode
0x18001145f  call    cs:__imp_CreateFileA
0x180011465  mov     rsi, rax
0x180011468  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001146c  jnz     loc_1800114FB
0x180011472  test    ebx, ebx
0x180011474  jz      short loc_180011485
0x180011476  mov     ecx, 1F4h; dwMilliseconds
0x18001147b  call    cs:__imp_Sleep
0x180011481  dec     ebx
0x180011483  jmp     short loc_18001143B
0x180011485  call    cs:__imp_GetLastError
0x18001148b  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180011492  mov     ebx, eax
0x180011494  test    cl, cl
0x180011496  jns     short loc_1800114DD
0x180011498  mov     r8d, eax
0x18001149b  mov     word ptr [rsp+8B8h+var_838], r12w
0x1800114a4  lea     rdx, aInitializedema_1; "InitializeDemandDial: Could not open WA"...
0x1800114ab  lea     rcx, [rsp+8B8h+var_838]
0x1800114b3  call    FormatRRASErrorString
0x1800114b8  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x1800114bf  test    cl, cl
0x1800114c1  jns     short loc_1800114DD
0x1800114c3  lea     r8, [rsp+8B8h+var_838]
0x1800114cb  mov     rdx, r15
0x1800114ce  mov     rcx, r14
0x1800114d1  call    McTemplateU0z_EventWriteTransfer
0x1800114d6  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x1800114dd  test    cl, 80h
0x1800114e0  jz      short loc_1800114F4
0x1800114e2  mov     rcx, r14
0x1800114e5  mov     rdx, r15
0x1800114e8  lea     r8, aLeavingInitial_1; "Leaving: InitializeDemandDial"
0x1800114ef  call    McTemplateU0z_EventWriteTransfer
0x1800114f4  mov     eax, ebx
0x1800114f6  jmp     loc_180011754
0x1800114fb  xor     r9d, r9d; lpSecurityAttributes
0x1800114fe  mov     [rsp+8B8h+hTemplateFile], r12; hTemplateFile
0x180011503  mov     [rsp+8B8h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x18001150b  mov     edx, 0C0000000h; dwDesiredAccess
0x180011510  mov     rcx, rdi; lpFileName
0x180011513  mov     [rsp+8B8h+dwCreationDisposition], 3; dwCreationDisposition
0x18001151b  lea     r8d, [r9+3]; dwShareMode
0x18001151f  call    cs:__imp_CreateFileA
0x180011525  mov     r14, rax
0x180011528  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001152c  jnz     short loc_1800115A8
0x18001152e  mov     rcx, rsi; hObject
0x180011531  call    cs:__imp_CloseHandle
0x180011537  call    cs:__imp_GetLastError
0x18001153d  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180011544  mov     ebx, eax
0x180011546  test    cl, cl
0x180011548  jns     short loc_180011593
0x18001154a  mov     r8d, eax
0x18001154d  mov     word ptr [rsp+8B8h+var_838], r12w
0x180011556  lea     rdx, aInitializedema; "InitializeDemandDial: Could not open WA"...
0x18001155d  lea     rcx, [rsp+8B8h+var_838]
0x180011565  call    FormatRRASErrorString
0x18001156a  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180011571  test    cl, cl
0x180011573  jns     short loc_180011593
0x180011575  lea     r8, [rsp+8B8h+var_838]
0x18001157d  mov     rdx, r15
0x180011580  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180011587  call    McTemplateU0z_EventWriteTransfer
0x18001158c  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180011593  test    cl, 80h
0x180011596  jz      loc_1800114F4
0x18001159c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800115a3  jmp     loc_1800114E5
0x1800115a8  mov     edi, 0C000000Dh
0x1800115ad  mov     r15d, 5
0x1800115b3  cmp     r12d, 3
0x1800115b7  jnb     loc_18001165D
0x1800115bd  mov     rcx, cs:IPRouterHeap; hHeap
0x1800115c4  xor     edx, edx; dwFlags
0x1800115c6  shl     r15d, 5
0x1800115ca  add     r15d, 8
0x1800115ce  mov     r8d, r15d; dwBytes
0x1800115d1  call    cs:__imp_HeapAlloc
0x1800115d7  mov     rbx, rax
0x1800115da  test    rax, rax
0x1800115dd  jz      short loc_180011656
0x1800115df  mov     [rsp+8B8h+OutputBufferLength], r15d; OutputBufferLength
0x1800115e4  xor     r9d, r9d; ApcContext
0x1800115e7  mov     [rsp+8B8h+OutputBuffer], rax; OutputBuffer
0x1800115ec  xor     r8d, r8d; ApcRoutine
0x1800115ef  mov     [rsp+8B8h+InputBufferLength], 28h ; '('; InputBufferLength
0x1800115f7  xor     edx, edx; Event
0x1800115f9  mov     [rsp+8B8h+hTemplateFile], rax; InputBuffer
0x1800115fe  mov     rcx, r14; FileHandle
0x180011601  mov     dword ptr [rax], 1
0x180011607  lea     rax, [rsp+8B8h+IoStatusBlock]
0x18001160c  mov     [rsp+8B8h+dwFlagsAndAttributes], 90018018h; IoControlCode
0x180011614  mov     qword ptr [rsp+8B8h+dwCreationDisposition], rax; IoStatusBlock
0x180011619  call    cs:__imp_NtDeviceIoControlFile
0x18001161f  mov     edi, eax
0x180011621  test    eax, eax
0x180011623  jz      short loc_18001167C
0x180011625  mov     rcx, cs:IPRouterHeap; hHeap
0x18001162c  xor     edx, edx; dwFlags
0x18001162e  mov     r8, rbx; lpMem
0x180011631  cmp     eax, 105h
0x180011636  jnz     short loc_18001164E
0x180011638  inc     r12d
0x18001163b  lea     r15d, [r12+r12*4]
0x18001163f  add     r15d, [rbx+4]
0x180011643  call    cs:__imp_HeapFree
0x180011649  jmp     loc_1800115B3
0x18001164e  call    cs:__imp_HeapFree
0x180011654  jmp     short loc_180011663
0x180011656  mov     edi, 8
0x18001165b  jmp     short loc_180011663
0x18001165d  xor     ebx, ebx
0x18001165f  test    edi, edi
0x180011661  jz      short loc_18001167C
0x180011663  mov     rcx, rsi; hObject
0x180011666  call    cs:__imp_CloseHandle
0x18001166c  mov     rcx, r14; hObject
0x18001166f  call    cs:__imp_CloseHandle
0x180011675  mov     eax, edi
0x180011677  jmp     loc_180011754
0x18001167c  test    r13d, r13d
0x18001167f  jz      short loc_180011691
0x180011681  mov     cs:g_hWanarpRead, rsi
0x180011688  mov     cs:g_hWanarpWrite, r14
0x18001168f  jmp     short loc_18001169F
0x180011691  mov     cs:g_hWanarpReadV6, rsi
0x180011698  mov     cs:g_hWanarpWriteV6, r14
0x18001169f  xor     esi, esi
0x1800116a1  cmp     [rbx+4], esi
0x1800116a4  jbe     short loc_180011715
0x1800116a6  xorps   xmm0, xmm0
0x1800116a9  mov     edi, esi
0x1800116ab  shl     rdi, 5
0x1800116af  lea     rdx, [rsp+8B8h+GuidString]; GuidString
0x1800116b4  movups  xmmword ptr [rsp+8B8h+GuidString.Length], xmm0
0x1800116b9  mov     [rsp+8B8h+var_868], 0
0x1800116c2  lea     rcx, [rdi+8]
0x1800116c6  add     rcx, rbx; Guid
0x1800116c9  call    cs:__imp_RtlStringFromGUID
0x1800116cf  test    eax, eax
0x1800116d1  jnz     short loc_18001170E
0x1800116d3  mov     edx, [rdi+rbx+18h]
0x1800116d7  mov     rcx, [rsp+8B8h+GuidString.Buffer]
0x1800116dc  test    r13d, r13d
0x1800116df  jz      short loc_180011704
0x1800116e1  mov     r9d, [rdi+rbx+20h]
0x1800116e6  lea     rax, [rsp+8B8h+var_868]
0x1800116eb  mov     r8d, [rdi+rbx+1Ch]
0x1800116f0  mov     qword ptr [rsp+8B8h+dwFlagsAndAttributes], rax
0x1800116f5  mov     eax, [rdi+rbx+24h]
0x1800116f9  mov     [rsp+8B8h+dwCreationDisposition], eax
0x1800116fd  call    CreateDialOutInterfaceV4
0x180011702  jmp     short loc_18001170E
0x180011704  lea     r8, [rsp+8B8h+var_868]
0x180011709  call    CreateDialOutInterfaceV6
0x18001170e  inc     esi
0x180011710  cmp     esi, [rbx+4]
0x180011713  jb      short loc_1800116A6
0x180011715  mov     rcx, cs:IPRouterHeap; hHeap
0x18001171c  mov     r8, rbx; lpMem
0x18001171f  xor     edx, edx; dwFlags
0x180011721  call    cs:__imp_HeapFree
0x180011727  mov     ecx, r13d
0x18001172a  call    PostIoctlForDemandDialNotification
0x18001172f  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180011736  jz      short loc_180011752
0x180011738  lea     r8, aLeavingInitial_1; "Leaving: InitializeDemandDial"
0x18001173f  lea     rdx, RasRtrmgrTraceInfo
0x180011746  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001174d  call    McTemplateU0z_EventWriteTransfer
0x180011752  xor     eax, eax
0x180011754  mov     rcx, [rsp+8B8h+var_38]
0x18001175c  xor     rcx, rsp; StackCookie
0x18001175f  call    __security_check_cookie
0x180011764  lea     r11, [rsp+8B8h+var_28]
0x18001176c  mov     rbx, [r11+38h]
0x180011770  mov     rsi, [r11+40h]
0x180011774  mov     rsp, r11
0x180011777  pop     r15
0x180011779  pop     r14
0x18001177b  pop     r13
0x18001177d  pop     r12
0x18001177f  pop     rdi
0x180011780  retn
```
