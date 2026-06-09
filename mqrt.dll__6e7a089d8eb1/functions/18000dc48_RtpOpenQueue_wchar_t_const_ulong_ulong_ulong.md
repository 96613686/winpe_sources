# RtpOpenQueue(wchar_t const *,ulong,ulong,ulong *)

- ea: `0x18000dc48`
- end: `0x18000e1f6`
- name: `?RtpOpenQueue@@YAJPEB_WKKPEAK@Z`
- size: `1454`
- prototype: `__int64 __fastcall(const wchar_t *, unsigned int, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000fb60`

## callees

- `0x1800056e8`
- `0x18000a4d8`
- `0x18000a4f4`
- `0x18000a6c4`
- `0x18000da78`
- `0x18000db78`
- `0x18000dc48`
- `0x180013c74`
- `0x1800165d0`
- `0x180017ce0`
- `0x180021760`
- `0x180023ca0`

## import_xrefs

- `msvcrt!free` at `0x18000dd2c`
- `msvcrt!free` at `0x18000dd79`
- `msvcrt!free` at `0x18000de06`
- `msvcrt!free` at `0x18000ded3`
- `msvcrt!free` at `0x18000df55`
- `msvcrt!free` at `0x18000dff4`
- `msvcrt!free` at `0x18000e057`
- `msvcrt!free` at `0x18000e103`
- `msvcrt!free` at `0x18000e143`
- `msvcrt!free` at `0x18000e177`
- `msvcrt!free` at `0x18000e1ab`
- `msvcrt!free` at `0x18000dd2c`
- `msvcrt!free` at `0x18000dd79`
- `msvcrt!free` at `0x18000de06`
- `msvcrt!free` at `0x18000ded3`
- `msvcrt!free` at `0x18000df55`
- `msvcrt!free` at `0x18000dff4`
- `msvcrt!free` at `0x18000e057`
- `msvcrt!free` at `0x18000e103`
- `msvcrt!free` at `0x18000e143`
- `msvcrt!free` at `0x18000e177`
- `msvcrt!free` at `0x18000e1ab`
- `ntdll!NtDeviceIoControlFile` at `0x18000e0b4`
- `ntdll!NtDeviceIoControlFile` at `0x18000e0b4`
- `RPCRT4!UuidCreate` at `0x18000ddbf`
- `RPCRT4!UuidCreate` at `0x18000ddbf`
- `KERNEL32!CancelIo` at `0x18000df96`
- `KERNEL32!CancelIo` at `0x18000df96`
- `KERNEL32!GetOverlappedResult` at `0x18000dfba`
- `KERNEL32!GetOverlappedResult` at `0x18000dfba`
- `KERNEL32!GetLastError` at `0x18000de74`
- `KERNEL32!GetLastError` at `0x18000e007`
- `KERNEL32!GetLastError` at `0x18000de74`
- `KERNEL32!GetLastError` at `0x18000e007`
- `KERNEL32!CreateFileW` at `0x18000de68`
- `KERNEL32!CreateFileW` at `0x18000de68`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall RtpOpenQueue(wchar_t *a1, unsigned int a2, unsigned int a3, unsigned int *a4)
{
  void *v6; // rdi
  int v7; // esi
  unsigned __int16 v8; // r8
  int v9; // ebx
  unsigned int v10; // ebx
  bool v11; // zf
  void *v12; // rbx
  unsigned int v13; // edi
  RPC_STATUS v15; // eax
  int v16; // eax
  unsigned int v17; // r15d
  int v18; // r8d
  int v19; // edx
  HANDLE FileW; // rax
  signed int LastError; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // r14d
  BOOL OverlappedResult; // eax
  signed int v27; // eax
  int v28; // eax
  void *v29; // rcx
  NTSTATUS v30; // eax
  int v31; // eax
  unsigned int v32; // esi
  int v33; // eax
  HANDLE hTemplateFile; // [rsp+30h] [rbp-D8h]
  unsigned int v35; // [rsp+50h] [rbp-B8h]
  HANDLE v36; // [rsp+58h] [rbp-B0h] BYREF
  void *Block; // [rsp+60h] [rbp-A8h]
  _QWORD v38[2]; // [rsp+68h] [rbp-A0h] BYREF
  struct InternalSecurityContext *SecurityContext; // [rsp+78h] [rbp-90h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+80h] [rbp-88h] BYREF
  unsigned int *v41; // [rsp+88h] [rbp-80h]
  struct _OVERLAPPED Overlapped; // [rsp+90h] [rbp-78h] BYREF
  const bad_hresult *v43; // [rsp+B0h] [rbp-58h] BYREF
  UUID Uuid; // [rsp+B8h] [rbp-50h] BYREF

  v41 = a4;
  v6 = 0;
  *a4 = 0;
  if ( (a2 & 0xA7) == 0 || (a2 & 0xFFFFFF58) != 0 )
  {
    v8 = 1101;
    goto LABEL_47;
  }
  v7 = a2 & 2;
  if ( a2 == 2 )
  {
    v9 = 2;
  }
  else
  {
    if ( (a2 & 2) != 0 )
    {
      v8 = 1102;
LABEL_47:
      v10 = -1072824251;
      LogMsgHR(-1072824251, (wchar_t *)L"rt/queue", v8);
      return v10;
    }
    v9 = 0;
  }
  if ( (a3 & 1) != 0 && (a2 & 2) != 0 )
  {
    v8 = 1103;
    goto LABEL_47;
  }
  Block = 0;
  v38[0] = 0;
  v38[1] = 0;
  if ( !(unsigned int)FnMqfToQueueFormats(a1) )
  {
    v10 = -1072824290;
    LogMsgHR(-1072824290, (wchar_t *)L"rt/queue", 0x28u);
    AP<AP<wchar_t>>::~AP<AP<wchar_t>>(v38);
    free(Block);
    return v10;
  }
  v11 = v9 == 0;
  v12 = Block;
  if ( v11 && *(_BYTE *)Block == 6 )
  {
    v13 = -1072824288;
    LogMsgHR(-1072824288, (wchar_t *)L"rt/queue", 0x2Du);
    AP<AP<wchar_t>>::~AP<AP<wchar_t>>(v38);
    free(Block);
    return v13;
  }
  v36 = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  GetThreadEvent(&Overlapped.hEvent);
  Uuid = 0;
  v15 = UuidCreate(&Uuid);
  v16 = RTpConvertToMQCode(v15, 1u);
  v17 = v16;
  if ( v16 < 0 )
  {
    LogMsgHR(v16, (wchar_t *)L"rt/queue", 0x30u);
    CHandle::~CHandle((CHandle *)&v36);
    AP<AP<wchar_t>>::~AP<AP<wchar_t>>(v38);
    free(v12);
    return v17;
  }
  v18 = ((a2 & 0x25) != 0) | 0x10000;
  if ( (a2 & 1) == 0 )
    v18 = (a2 & 0x25) != 0;
  v19 = v18 | 2;
  if ( !v7 )
    v19 = v18;
  FileW = CreateFileW(&g_wzDeviceName, v19 & 0xFFFEFFFF, 3u, 0, 2u, 0x40000080u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v6 = FileW;
    v36 = FileW;
    LastError = 0;
  }
  v22 = RTpConvertToMQCode(LastError, 1u);
  v17 = v22;
  if ( v22 < 0 )
  {
    LogMsgHR(v22, (wchar_t *)L"rt/queue", 0x2Fu);
    CHandle::~CHandle((CHandle *)&v36);
    AP<AP<wchar_t>>::~AP<AP<wchar_t>>(v38);
    free(v12);
    return v17;
  }
  v23 = MQpDeviceIoControl(v6, 0x19650117u, &Uuid, 0x10u, 0, 0, &Overlapped);
  if ( (unsigned int)RTpConvertToMQCode(v23, 1u) != 1074659334 )
  {
    v13 = -1072824319;
    LogMsgHR(-1072824319, (wchar_t *)L"rt/queue", 0x2Eu);
    CHandle::~CHandle((CHandle *)&v36);
    AP<AP<wchar_t>>::~AP<AP<wchar_t>>(v38);
    free(v12);
    return v13;
  }
  v24 = IssueOpenQueue(0, (struct QUEUE_FORMAT *const)Block, &Uuid, a2, a3);
  v25 = RTpConvertToMQCode(v24, 1u);
  if ( v25 < 0 )
    CancelIo(v6);
  NumberOfBytesTransferred = 0;
  OverlappedResult = GetOverlappedResult(v6, &Overlapped, &NumberOfBytesTransferred, 1);
  if ( v25 < 0 )
  {
    LogMsgHR(v25, (wchar_t *)L"rt/queue", 0x450u);
    CHandle::~CHandle((CHandle *)&v36);
    AP<AP<wchar_t>>::~AP<AP<wchar_t>>(v38);
    free(v12);
    return (unsigned int)v25;
  }
  if ( !OverlappedResult )
  {
    v27 = GetLastError();
    if ( v27 > 0 )
      v27 = (unsigned __int16)v27 | 0x80070000;
    v28 = RTpConvertToMQCode(v27, 1u);
    v13 = v28;
    if ( v28 < 0 )
      LogMsgHR(v28, (wchar_t *)L"rt/queue", 0x451u);
    CHandle::~CHandle((CHandle *)&v36);
    AP<AP<wchar_t>>::~AP<AP<wchar_t>>(v38);
    free(v12);
    return v13;
  }
  if ( v7 )
  {
    SecurityContext = 0;
    try
    {
      SecurityContext = InternalSecurityContext::CreateSecurityContext();
      hTemplateFile = (char *)SecurityContext + 8;
      v29 = v6;
    }
    catch ( std::bad_alloc )
    {
      LogMsgHR(-1072824281, (wchar_t *)L"rt/queue", 0x37u);
      P<InternalSecurityContext>::~P<InternalSecurityContext>(&SecurityContext);
      CHandle::~CHandle((CHandle *)&v36);
      AP<AP<wchar_t>>::~AP<AP<wchar_t>>(v38);
      free(Block);
      return 3222143015LL;
    }
    catch ( const bad_hresult *v43 )
    {
      v33 = (*(__int64 (__fastcall **)(const bad_hresult *))(*(_QWORD *)v43 + 16LL))(v43);
      v35 = v33;
      if ( v33 < 0 )
        LogMsgHR(v33, (wchar_t *)L"rt/queue", 0x39u);
      P<InternalSecurityContext>::~P<InternalSecurityContext>(&SecurityContext);
      CHandle::~CHandle((CHandle *)&v36);
      AP<AP<wchar_t>>::~AP<AP<wchar_t>>(v38);
      free(Block);
      return v35;
    }
    v30 = NtDeviceIoControlFile(v29, 0, 0, 0, &`MQpDeviceIoControl'::`2'::Iosb, 0x1965015Fu, hTemplateFile, 0x40u, 0, 0);
    v31 = RTpConvertToMQCode(v30, 1u);
    v32 = v31;
    if ( v31 < 0 )
    {
      LogMsgHR(v31, (wchar_t *)L"rt/queue", 0x3Cu);
      P<InternalSecurityContext>::~P<InternalSecurityContext>(&SecurityContext);
      CHandle::~CHandle((CHandle *)&v36);
      AP<AP<wchar_t>>::~AP<AP<wchar_t>>(v38);
      free(v12);
      return v32;
    }
    P<InternalSecurityContext>::~P<InternalSecurityContext>(&SecurityContext);
  }
  v36 = 0;
  *v41 = (unsigned int)v6;
  CHandle::~CHandle((CHandle *)&v36);
  AP<AP<wchar_t>>::~AP<AP<wchar_t>>(v38);
  free(v12);
  return 0;
}

```

## disassembly

```asm
0x18000dc48  push    rbx
0x18000dc4a  push    rsi
0x18000dc4b  push    rdi
0x18000dc4c  push    r12
0x18000dc4e  push    r13
0x18000dc50  push    r14
0x18000dc52  push    r15
0x18000dc54  sub     rsp, 0D0h
0x18000dc5b  mov     rax, cs:__security_cookie
0x18000dc62  xor     rax, rsp
0x18000dc65  mov     [rsp+108h+var_40], rax
0x18000dc6d  mov     [rsp+108h+var_80], r9
0x18000dc75  mov     r13d, r8d
0x18000dc78  mov     r14d, edx
0x18000dc7b  mov     r10, rcx
0x18000dc7e  xor     edi, edi
0x18000dc80  mov     [r9], edi
0x18000dc83  test    dl, 0A7h
0x18000dc86  setnz   cl
0x18000dc89  test    edx, 0FFFFFF58h
0x18000dc8f  setz    al
0x18000dc92  test    al, cl
0x18000dc94  jz      loc_18000E1B8
0x18000dc9a  mov     esi, edx
0x18000dc9c  and     esi, 2
0x18000dc9f  cmp     edx, 2
0x18000dca2  jz      short loc_18000DCB7
0x18000dca4  test    esi, esi
0x18000dca6  jz      short loc_18000DCB3
0x18000dca8  mov     r8d, 44Eh
0x18000dcae  jmp     loc_18000E1BE
0x18000dcb3  mov     ebx, edi
0x18000dcb5  jmp     short loc_18000DCB9
0x18000dcb7  mov     ebx, esi
0x18000dcb9  test    r13b, 1
0x18000dcbd  setnz   cl
0x18000dcc0  test    r14b, 2
0x18000dcc4  setnz   al
0x18000dcc7  test    al, cl
0x18000dcc9  jz      short loc_18000DCD6
0x18000dccb  mov     r8d, 44Fh
0x18000dcd1  jmp     loc_18000E1BE
0x18000dcd6  mov     [rsp+108h+Block], rdi
0x18000dcdb  mov     [rsp+108h+var_B8], edi
0x18000dcdf  mov     [rsp+108h+var_A0], rdi
0x18000dce4  mov     [rsp+108h+var_98], rdi
0x18000dce9  lea     r9, [rsp+108h+var_A0]
0x18000dcee  lea     r8, [rsp+108h+var_B8]
0x18000dcf3  lea     rdx, [rsp+108h+Block]
0x18000dcf8  mov     rcx, r10; wchar_t *
0x18000dcfb  call    ?FnMqfToQueueFormats@@YAHPEB_WAEAV?$AP@UQUEUE_FORMAT@@@@PEAKAEAVCStringsToFree@@@Z; FnMqfToQueueFormats(wchar_t const *,AP<QUEUE_FORMAT> &,ulong *,CStringsToFree &)
0x18000dd00  test    eax, eax
0x18000dd02  jnz     short loc_18000DD38
0x18000dd04  lea     r8d, [rax+28h]; unsigned __int16
0x18000dd08  lea     rdx, aRtQueue; "rt/queue"
0x18000dd0f  mov     ebx, 0C00E001Eh
0x18000dd14  mov     ecx, ebx; int
0x18000dd16  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18000dd1b  nop
0x18000dd1c  lea     rcx, [rsp+108h+var_A0]
0x18000dd21  call    ??1?$AP@V?$AP@_W@@@@QEAA@XZ; AP<AP<wchar_t>>::~AP<AP<wchar_t>>(void)
0x18000dd26  nop
0x18000dd27  mov     rcx, [rsp+108h+Block]; Block
0x18000dd2c  call    cs:__imp_free
0x18000dd32  nop
0x18000dd33  jmp     loc_18000E1D1
0x18000dd38  mov     r12d, [rsp+108h+var_B8]
0x18000dd3d  test    ebx, ebx
0x18000dd3f  mov     rbx, [rsp+108h+Block]
0x18000dd44  jnz     short loc_18000DD87
0x18000dd46  cmp     r12d, 1
0x18000dd4a  ja      short loc_18000DD51
0x18000dd4c  cmp     byte ptr [rbx], 6
0x18000dd4f  jnz     short loc_18000DD87
0x18000dd51  mov     r8d, 2Dh ; '-'; unsigned __int16
0x18000dd57  lea     rdx, aRtQueue; "rt/queue"
0x18000dd5e  mov     edi, 0C00E0020h
0x18000dd63  mov     ecx, edi; int
0x18000dd65  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18000dd6a  nop
0x18000dd6b  lea     rcx, [rsp+108h+var_A0]
0x18000dd70  call    ??1?$AP@V?$AP@_W@@@@QEAA@XZ; AP<AP<wchar_t>>::~AP<AP<wchar_t>>(void)
0x18000dd75  nop
0x18000dd76  mov     rcx, rbx; Block
0x18000dd79  call    cs:__imp_free
0x18000dd7f  nop
0x18000dd80  mov     eax, edi
0x18000dd82  jmp     loc_18000E1D3
0x18000dd87  mov     [rsp+108h+var_B0], rdi
0x18000dd8c  xorps   xmm0, xmm0
0x18000dd8f  movups  xmmword ptr [rsp+108h+Overlapped.Internal], xmm0
0x18000dd97  movups  xmmword ptr [rsp+108h+Overlapped.10h], xmm0
0x18000dd9f  lea     rcx, [rsp+108h+Overlapped.hEvent]; void **
0x18000dda7  call    ?GetThreadEvent@@YAJAEAPEAX@Z; GetThreadEvent(void * &)
0x18000ddac  xorps   xmm0, xmm0
0x18000ddaf  movups  xmmword ptr [rsp+108h+Uuid.Data1], xmm0
0x18000ddb7  lea     rcx, [rsp+108h+Uuid]; Uuid
0x18000ddbf  call    cs:__imp_UuidCreate
0x18000ddc5  mov     edx, 1; unsigned int
0x18000ddca  mov     ecx, eax; int
0x18000ddcc  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000ddd1  mov     r15d, eax
0x18000ddd4  test    eax, eax
0x18000ddd6  jns     short loc_18000DE15
0x18000ddd8  mov     r8d, 30h ; '0'; unsigned __int16
0x18000ddde  lea     rdx, aRtQueue; "rt/queue"
0x18000dde5  mov     ecx, eax; int
0x18000dde7  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18000ddec  nop
0x18000dded  lea     rcx, [rsp+108h+var_B0]; this
0x18000ddf2  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18000ddf7  nop
0x18000ddf8  lea     rcx, [rsp+108h+var_A0]
0x18000ddfd  call    ??1?$AP@V?$AP@_W@@@@QEAA@XZ; AP<AP<wchar_t>>::~AP<AP<wchar_t>>(void)
0x18000de02  nop
0x18000de03  mov     rcx, rbx; Block
0x18000de06  call    cs:__imp_free
0x18000de0c  nop
0x18000de0d  mov     eax, r15d
0x18000de10  jmp     loc_18000E1D3
0x18000de15  test    r14b, 25h
0x18000de19  mov     ecx, 0
0x18000de1e  setnz   cl
0x18000de21  mov     r8d, ecx
0x18000de24  bts     r8d, 10h
0x18000de29  test    r14b, 1
0x18000de2d  cmovz   r8d, ecx
0x18000de31  mov     edx, r8d
0x18000de34  or      edx, 2
0x18000de37  test    esi, esi
0x18000de39  cmovz   edx, r8d
0x18000de3d  btr     edx, 10h; dwDesiredAccess
0x18000de41  mov     [rsp+108h+hTemplateFile], 0; hTemplateFile
0x18000de4a  mov     [rsp+108h+dwFlagsAndAttributes], 40000080h; dwFlagsAndAttributes
0x18000de52  mov     [rsp+108h+dwCreationDisposition], 2; dwCreationDisposition
0x18000de5a  xor     r9d, r9d; lpSecurityAttributes
0x18000de5d  lea     r8d, [r9+3]; dwShareMode
0x18000de61  lea     rcx, ?g_wzDeviceName@@3PA_WA; lpFileName
0x18000de68  call    cs:__imp_CreateFileW
0x18000de6e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000de72  jnz     short loc_18000DE88
0x18000de74  call    cs:__imp_GetLastError
0x18000de7a  test    eax, eax
0x18000de7c  jle     short loc_18000DE92
0x18000de7e  movzx   eax, ax
0x18000de81  or      eax, 80070000h
0x18000de86  jmp     short loc_18000DE92
0x18000de88  mov     rdi, rax
0x18000de8b  mov     [rsp+108h+var_B0], rax
0x18000de90  xor     eax, eax
0x18000de92  mov     edx, 1; unsigned int
0x18000de97  mov     ecx, eax; int
0x18000de99  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000de9e  mov     r15d, eax
0x18000dea1  test    eax, eax
0x18000dea3  jns     short loc_18000DEDF
0x18000dea5  mov     r8d, 2Fh ; '/'; unsigned __int16
0x18000deab  lea     rdx, aRtQueue; "rt/queue"
0x18000deb2  mov     ecx, eax; int
0x18000deb4  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18000deb9  nop
0x18000deba  lea     rcx, [rsp+108h+var_B0]; this
0x18000debf  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18000dec4  nop
0x18000dec5  lea     rcx, [rsp+108h+var_A0]
0x18000deca  call    ??1?$AP@V?$AP@_W@@@@QEAA@XZ; AP<AP<wchar_t>>::~AP<AP<wchar_t>>(void)
0x18000decf  nop
0x18000ded0  mov     rcx, rbx; Block
0x18000ded3  call    cs:__imp_free
0x18000ded9  nop
0x18000deda  jmp     loc_18000DE0D
0x18000dedf  lea     rax, [rsp+108h+Overlapped]
0x18000dee7  mov     [rsp+108h+hTemplateFile], rax; struct _OVERLAPPED *
0x18000deec  xor     r15d, r15d
0x18000deef  mov     [rsp+108h+dwFlagsAndAttributes], r15d; unsigned int
0x18000def4  mov     qword ptr [rsp+108h+dwCreationDisposition], r15; void *
0x18000def9  lea     r9d, [r15+10h]; unsigned int
0x18000defd  lea     r8, [rsp+108h+Uuid]; void *
0x18000df05  mov     edx, 19650117h; unsigned int
0x18000df0a  mov     rcx, rdi; void *
0x18000df0d  call    ?MQpDeviceIoControl@@YAJPEAXK0K0KPEAU_OVERLAPPED@@@Z; MQpDeviceIoControl(void *,ulong,void *,ulong,void *,ulong,_OVERLAPPED *)
0x18000df12  lea     edx, [r15+1]; unsigned int
0x18000df16  mov     ecx, eax; int
0x18000df18  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000df1d  cmp     eax, 400E0006h
0x18000df22  jz      short loc_18000DF61
0x18000df24  lea     r8d, [r15+2Eh]; unsigned __int16
0x18000df28  lea     rdx, aRtQueue; "rt/queue"
0x18000df2f  mov     edi, 0C00E0001h
0x18000df34  mov     ecx, edi; int
0x18000df36  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18000df3b  nop
0x18000df3c  lea     rcx, [rsp+108h+var_B0]; this
0x18000df41  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18000df46  nop
0x18000df47  lea     rcx, [rsp+108h+var_A0]
0x18000df4c  call    ??1?$AP@V?$AP@_W@@@@QEAA@XZ; AP<AP<wchar_t>>::~AP<AP<wchar_t>>(void)
0x18000df51  nop
0x18000df52  mov     rcx, rbx; Block
0x18000df55  call    cs:__imp_free
0x18000df5b  nop
0x18000df5c  jmp     loc_18000DD80
0x18000df61  mov     [rsp+108h+dwCreationDisposition], r13d; unsigned int
0x18000df66  mov     r9d, r14d; unsigned int
0x18000df69  lea     r8, [rsp+108h+Uuid]; struct _GUID *
0x18000df71  mov     rdx, rbx; struct QUEUE_FORMAT *
0x18000df74  mov     ecx, r12d; unsigned int
0x18000df77  call    ?IssueOpenQueue@@YAJKQEAUQUEUE_FORMAT@@AEBU_GUID@@KK@Z; IssueOpenQueue(ulong,QUEUE_FORMAT * const,_GUID const &,ulong,ulong)
0x18000df7c  mov     r12d, 1
0x18000df82  mov     edx, r12d; unsigned int
0x18000df85  mov     ecx, eax; int
0x18000df87  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000df8c  mov     r14d, eax
0x18000df8f  test    eax, eax
0x18000df91  jns     short loc_18000DF9C
0x18000df93  mov     rcx, rdi; hFile
0x18000df96  call    cs:__imp_CancelIo
0x18000df9c  mov     [rsp+108h+NumberOfBytesTransferred], r15d
0x18000dfa4  mov     r9d, r12d; bWait
0x18000dfa7  lea     r8, [rsp+108h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18000dfaf  lea     rdx, [rsp+108h+Overlapped]; lpOverlapped
0x18000dfb7  mov     rcx, rdi; hFile
0x18000dfba  call    cs:__imp_GetOverlappedResult
0x18000dfc0  test    r14d, r14d
0x18000dfc3  jns     short loc_18000E003
0x18000dfc5  mov     r8d, 450h; unsigned __int16
0x18000dfcb  lea     rdx, aRtQueue; "rt/queue"
0x18000dfd2  mov     ecx, r14d; int
0x18000dfd5  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18000dfda  nop
0x18000dfdb  lea     rcx, [rsp+108h+var_B0]; this
0x18000dfe0  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18000dfe5  nop
0x18000dfe6  lea     rcx, [rsp+108h+var_A0]
0x18000dfeb  call    ??1?$AP@V?$AP@_W@@@@QEAA@XZ; AP<AP<wchar_t>>::~AP<AP<wchar_t>>(void)
0x18000dff0  nop
0x18000dff1  mov     rcx, rbx; Block
0x18000dff4  call    cs:__imp_free
0x18000dffa  nop
0x18000dffb  mov     eax, r14d
0x18000dffe  jmp     loc_18000E1D3
0x18000e003  test    eax, eax
0x18000e005  jnz     short loc_18000E063
0x18000e007  call    cs:__imp_GetLastError
0x18000e00d  test    eax, eax
0x18000e00f  jle     short loc_18000E019
0x18000e011  movzx   eax, ax
0x18000e014  or      eax, 80070000h
0x18000e019  mov     edx, r12d; unsigned int
0x18000e01c  mov     ecx, eax; int
0x18000e01e  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000e023  mov     edi, eax
0x18000e025  test    eax, eax
0x18000e027  jns     short loc_18000E03E
0x18000e029  mov     r8d, 451h; unsigned __int16
0x18000e02f  lea     rdx, aRtQueue; "rt/queue"
0x18000e036  mov     ecx, eax; int
0x18000e038  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18000e03d  nop
0x18000e03e  lea     rcx, [rsp+108h+var_B0]; this
0x18000e043  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18000e048  nop
0x18000e049  lea     rcx, [rsp+108h+var_A0]
0x18000e04e  call    ??1?$AP@V?$AP@_W@@@@QEAA@XZ; AP<AP<wchar_t>>::~AP<AP<wchar_t>>(void)
0x18000e053  nop
0x18000e054  mov     rcx, rbx; Block
0x18000e057  call    cs:__imp_free
0x18000e05d  nop
0x18000e05e  jmp     loc_18000DD80
0x18000e063  test    esi, esi
0x18000e065  jz      loc_18000E11B
0x18000e06b  mov     [rsp+108h+var_90], r15
0x18000e070  call    ?CreateSecurityContext@InternalSecurityContext@@SAPEAV1@XZ; InternalSecurityContext::CreateSecurityContext(void)
0x18000e075  mov     [rsp+108h+var_90], rax
0x18000e07a  add     rax, 8
0x18000e07e  mov     [rsp+108h+OutputBufferLength], r15d; OutputBufferLength
0x18000e083  mov     [rsp+108h+OutputBuffer], r15; OutputBuffer
0x18000e088  mov     [rsp+108h+InputBufferLength], 40h ; '@'; InputBufferLength
0x18000e090  mov     [rsp+108h+hTemplateFile], rax; InputBuffer
0x18000e095  mov     [rsp+108h+dwFlagsAndAttributes], 1965015Fh; IoControlCode
0x18000e09d  lea     rax, ?Iosb@?1??MQpDeviceIoControl@@YAJPEAXK0K0K@Z@4U_IO_STATUS_BLOCK@@A; _IO_STATUS_BLOCK `MQpDeviceIoControl(void *,ulong,void *,ulong,void *,ulong)'::`2'::Iosb
0x18000e0a4  mov     qword ptr [rsp+108h+dwCreationDisposition], rax; IoStatusBlock
0x18000e0a9  xor     r9d, r9d; ApcContext
0x18000e0ac  xor     r8d, r8d; ApcRoutine
0x18000e0af  xor     edx, edx; Event
0x18000e0b1  mov     rcx, rdi; FileHandle
0x18000e0b4  call    cs:__imp_NtDeviceIoControlFile
0x18000e0ba  mov     edx, r12d; unsigned int
0x18000e0bd  mov     ecx, eax; int
0x18000e0bf  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000e0c4  mov     esi, eax
0x18000e0c6  test    eax, eax
0x18000e0c8  jns     short loc_18000E111
0x18000e0ca  mov     r8d, 3Ch ; '<'; unsigned __int16
0x18000e0d0  lea     rdx, aRtQueue; "rt/queue"
0x18000e0d7  mov     ecx, eax; int
0x18000e0d9  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18000e0de  nop
0x18000e0df  lea     rcx, [rsp+108h+var_90]
0x18000e0e4  call    ??1?$P@VInternalSecurityContext@@@@QEAA@XZ; P<InternalSecurityContext>::~P<InternalSecurityContext>(void)
  ... truncated ...
```
