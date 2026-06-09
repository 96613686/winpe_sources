# CUMRDPListenerVMBus::AcceptControlChannel(_VMBUS_PIPE_CHANNEL_INFO *)

- ea: `0x18006345c`
- end: `0x180063871`
- name: `?AcceptControlChannel@CUMRDPListenerVMBus@@AEAAXPEAU_VMBUS_PIPE_CHANNEL_INFO@@@Z`
- size: `1045`
- prototype: `void __fastcall(CUMRDPListenerVMBus *this, struct _VMBUS_PIPE_CHANNEL_INFO *, __int64, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180063e00`

## callees

- `0x1800014d8`
- `0x1800015f0`
- `0x180009628`
- `0x180012200`
- `0x180033da0`
- `0x18006345c`
- `0x180065280`
- `0x1800655a4`
- `0x180066ba0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800635b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800636bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063783`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800635b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800636bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063783`
- `ntdll!RtlNtStatusToDosError` at `0x18006378b`
- `ntdll!RtlNtStatusToDosError` at `0x18006378b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800636b5`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800636b5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800635ae`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800635ae`
- `api-ms-win-core-kernel32-legacy-l1-1-0!BindIoCompletionCallback` at `0x180063779`
- `api-ms-win-core-kernel32-legacy-l1-1-0!BindIoCompletionCallback` at `0x180063779`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180063499`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180063499`

## string_xrefs

- `0x180063519`: `Failed to open for client side of vmbus control channel.`
- `0x1800635e0`: `Failed in WriteFile to VmBus control channel.`
- `0x1800636e3`: `Failed in ReadFile from VmBus control channel.`
- `0x18006371c`: `Failed: numberOfBytesRead != sizeof(versionResponse) for control channel.`
- `0x1800637b3`: `Failed: BindIoCompletionCallback.`

## pseudocode

```c
void __fastcall CUMRDPListenerVMBus::AcceptControlChannel(
        CUMRDPListenerVMBus *this,
        struct _VMBUS_PIPE_CHANNEL_INFO *a2,
        __int64 a3,
        int a4)
{
  char *v6; // rcx
  HANDLE *v7; // rsi
  signed int v8; // ebx
  int v9; // r8d
  int v10; // r9d
  HANDLE v11; // rcx
  int v12; // r8d
  int v13; // r9d
  signed int LastError; // eax
  int v15; // ecx
  const char *v16; // rax
  char *v17; // rdx
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  HANDLE v21; // rcx
  signed int v22; // eax
  NTSTATUS v23; // eax
  signed int v24; // eax
  int v25; // [rsp+50h] [rbp-39h] BYREF
  const char *v26; // [rsp+58h] [rbp-31h] BYREF
  const char *v27; // [rsp+60h] [rbp-29h] BYREF
  const char *v28; // [rsp+68h] [rbp-21h] BYREF
  const char *v29; // [rsp+70h] [rbp-19h] BYREF
  const char *v30; // [rsp+78h] [rbp-11h] BYREF
  char *v31; // [rsp+80h] [rbp-9h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+88h] [rbp-1h] BYREF
  DWORD NumberOfBytesRead; // [rsp+8Ch] [rbp+3h] BYREF
  _QWORD Buffer[2]; // [rsp+90h] [rbp+7h] BYREF
  __int128 v35; // [rsp+A0h] [rbp+17h] BYREF
  char v36; // [rsp+B0h] [rbp+27h]

  v6 = (char *)this + 96;
  v31 = v6;
  if ( *((_DWORD *)v6 + 2) )
    PAL_System_CritSecEnter(*(_QWORD *)v6, a2, a3);
  if ( *((_DWORD *)this + 131) )
  {
    if ( (unsigned int)dword_1801B76C8 > 3 )
    {
      v26 = "CUMRDPListenerVMBus::AcceptControlChannel ControlPipe is Shutting down";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)v6,
        (unsigned int)byte_18019CA31,
        a3,
        a4,
        (__int64)&v26);
    }
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v31);
    return;
  }
  v7 = (HANDLE *)((char *)this + 512);
  v8 = CUMRDPListenerVMBus::VmbusListenerOpenChannel(this, a2, a3, (void **)this + 64);
  if ( v8 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v27 = "AcceptControlChannel";
      v30 = "Failed to open for client side of vmbus control channel.";
      v25 = 448;
      v29 = "Error HResult failed";
      v28 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpvmconnectlistener.cpp";
      LODWORD(v26) = v8;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        dword_1801B76C8,
        (unsigned int)byte_18019C9DD,
        v9,
        v10,
        (__int64)&v29,
        (__int64)&v26,
        (__int64)&v28,
        (__int64)&v25,
        (__int64)&v27,
        (__int64)&v30);
    }
    goto LABEL_21;
  }
  v11 = *v7;
  Buffer[0] = 1;
  Buffer[1] = 1;
  NumberOfBytesWritten = 0;
  if ( !WriteFile(v11, Buffer, 0x10u, &NumberOfBytesWritten, 0) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_21;
      v16 = "Failed in WriteFile to VmBus control channel.";
      LODWORD(v26) = 464;
      v25 = v8;
      v17 = byte_18019C989;
      goto LABEL_20;
    }
  }
  if ( NumberOfBytesWritten != 16 )
  {
    v15 = -2147467259;
    v8 = -2147467259;
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_21;
    v16 = "Failed: numberOfBytesWritten != sizeof(versionRequest). for control channel";
    LODWORD(v26) = 470;
    v17 = byte_18019C935;
    goto LABEL_19;
  }
  v21 = *v7;
  NumberOfBytesRead = 0;
  v36 = 0;
  v35 = 0;
  if ( ReadFile(v21, &v35, 0x11u, &NumberOfBytesRead, 0) )
    goto LABEL_28;
  v22 = GetLastError();
  v8 = v22;
  if ( v22 > 0 )
    v8 = (unsigned __int16)v22 | 0x80070000;
  if ( v8 >= 0 )
  {
LABEL_28:
    if ( NumberOfBytesRead == 17 )
    {
      if ( v36 == 2 )
      {
        if ( BindIoCompletionCallback(*v7, CUMRDPListenerVMBus::StaticControlIoCompletion, 0) )
          goto LABEL_40;
        v23 = GetLastError();
        v24 = RtlNtStatusToDosError(v23);
        v8 = v24;
        if ( v24 > 0 )
          v8 = (unsigned __int16)v24 | 0x80070000;
        if ( v8 >= 0 )
        {
LABEL_40:
          CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v31);
          CUMRDPListenerVMBus::StartControlReceive(this);
          return;
        }
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_21;
        v16 = "Failed: BindIoCompletionCallback.";
        LODWORD(v26) = 509;
        v25 = v8;
        v17 = byte_18019C7E5;
        goto LABEL_20;
      }
      v15 = -2147467259;
      v8 = -2147467259;
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_21;
      v16 = "Failed: versionResponse.IsAccepted != SYNTHRDP_TRUE_WITH_VERSION_EXCHANGE.";
      LODWORD(v26) = 498;
      v17 = byte_18019C839;
    }
    else
    {
      v15 = -2147467259;
      v8 = -2147467259;
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_21;
      v16 = "Failed: numberOfBytesRead != sizeof(versionResponse) for control channel.";
      LODWORD(v26) = 492;
      v17 = byte_18019C88D;
    }
LABEL_19:
    v25 = -2147467259;
LABEL_20:
    v29 = v16;
    v30 = "Error HResult failed";
    v27 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpvmconnectlistener.cpp";
    v28 = "AcceptControlChannel";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v15,
      (_DWORD)v17,
      v12,
      v13,
      (__int64)&v30,
      (__int64)&v25,
      (__int64)&v27,
      (__int64)&v26,
      (__int64)&v28,
      (__int64)&v29);
    goto LABEL_21;
  }
  if ( (unsigned int)dword_1801B76C8 > 2 )
  {
    v16 = "Failed in ReadFile from VmBus control channel.";
    LODWORD(v26) = 486;
    v25 = v8;
    v17 = byte_18019C8E1;
    goto LABEL_20;
  }
LABEL_21:
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v31);
  if ( (unsigned int)dword_1801B76C8 > 2 )
  {
    v29 = "AcceptControlChannel";
    v27 = "CUMRDPListenerVMBus::AcceptControlChannel Error";
    LODWORD(v26) = 524;
    v28 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpvmconnectlistener.cpp";
    v25 = v8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v18,
      (unsigned int)byte_18019C799,
      v19,
      v20,
      (__int64)&v27,
      (__int64)&v25,
      (__int64)&v28,
      (__int64)&v26,
      (__int64)&v29);
  }
  CUMRDPListenerVMBus::ResetControlChannel(this);
}

```

## disassembly

```asm
0x18006345c  mov     [rsp-8+arg_10], rbx
0x180063461  push    rbp
0x180063462  push    rsi
0x180063463  push    rdi
0x180063464  push    r12
0x180063466  push    r13
0x180063468  lea     rbp, [rsp-37h]
0x18006346d  sub     rsp, 0C0h
0x180063474  mov     rax, cs:__security_cookie
0x18006347b  xor     rax, rsp
0x18006347e  mov     [rbp+57h+var_28], rax
0x180063482  mov     rdi, rcx
0x180063485  mov     rbx, rdx
0x180063488  add     rcx, 60h ; '`'
0x18006348c  mov     [rbp+57h+var_60], rcx
0x180063490  cmp     dword ptr [rcx+8], 0
0x180063494  jz      short loc_18006349F
0x180063496  mov     rcx, [rcx]
0x180063499  call    cs:__imp_PAL_System_CritSecEnter
0x18006349f  cmp     dword ptr [rdi+20Ch], 0
0x1800634a6  jz      short loc_1800634E1
0x1800634a8  mov     eax, cs:dword_1801B76C8
0x1800634ae  cmp     eax, 3
0x1800634b1  jbe     short loc_1800634D3
0x1800634b3  lea     rax, aCumrdplistener_30; "CUMRDPListenerVMBus::AcceptControlChann"...
0x1800634ba  mov     [rbp+57h+var_88], rax
0x1800634be  lea     rdx, byte_18019CA31
0x1800634c5  lea     rax, [rbp+57h+var_88]
0x1800634c9  mov     [rsp+0E0h+lpOverlapped], rax
0x1800634ce  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800634d3  lea     rcx, [rbp+57h+var_60]; this
0x1800634d7  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1800634dc  jmp     loc_18006384E
0x1800634e1  lea     rsi, [rdi+200h]
0x1800634e8  mov     rdx, rbx; struct _VMBUS_PIPE_CHANNEL_INFO *
0x1800634eb  mov     r9, rsi; void **
0x1800634ee  mov     rcx, rdi; this
0x1800634f1  call    ?VmbusListenerOpenChannel@CUMRDPListenerVMBus@@AEAAJPEAU_VMBUS_PIPE_CHANNEL_INFO@@IPEAPEAX@Z; CUMRDPListenerVMBus::VmbusListenerOpenChannel(_VMBUS_PIPE_CHANNEL_INFO *,uint,void * *)
0x1800634f6  lea     r12, aAcceptcontrolc; "AcceptControlChannel"
0x1800634fd  mov     ebx, eax
0x1800634ff  lea     r13, aClientcoreTerm_3; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x180063506  test    eax, eax
0x180063508  jns     short loc_18006357E
0x18006350a  mov     ecx, cs:dword_1801B76C8
0x180063510  cmp     ecx, 2
0x180063513  jbe     loc_180063680
0x180063519  lea     rax, aFailedToOpenFo; "Failed to open for client side of vmbus"...
0x180063520  mov     [rbp+57h+var_80], r12
0x180063524  mov     [rbp+57h+var_68], rax
0x180063528  lea     rdx, byte_18019C9DD
0x18006352f  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180063536  mov     [rbp+57h+var_90], 1C0h
0x18006353d  mov     [rbp+57h+var_70], rax
0x180063541  lea     rax, [rbp+57h+var_68]
0x180063545  mov     [rsp+0E0h+var_98], rax
0x18006354a  lea     rax, [rbp+57h+var_80]
0x18006354e  mov     [rsp+0E0h+var_A0], rax
0x180063553  lea     rax, [rbp+57h+var_90]
0x180063557  mov     [rsp+0E0h+var_A8], rax
0x18006355c  lea     rax, [rbp+57h+var_78]
0x180063560  mov     [rsp+0E0h+var_B0], rax
0x180063565  lea     rax, [rbp+57h+var_88]
0x180063569  mov     [rsp+0E0h+var_B8], rax
0x18006356e  lea     rax, [rbp+57h+var_70]
0x180063572  mov     [rbp+57h+var_78], r13
0x180063576  mov     dword ptr [rbp+57h+var_88], ebx
0x180063579  jmp     loc_180063676
0x18006357e  mov     rcx, [rsi]; hFile
0x180063581  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180063585  mov     eax, 1
0x18006358a  mov     [rbp+57h+Buffer], 1
0x180063592  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x180063596  mov     [rbp+57h+var_48], rax
0x18006359a  mov     [rbp+57h+NumberOfBytesWritten], 0
0x1800635a1  mov     [rsp+0E0h+lpOverlapped], 0; lpOverlapped
0x1800635aa  lea     r8d, [rax+0Fh]; nNumberOfBytesToWrite
0x1800635ae  call    cs:__imp_WriteFile
0x1800635b4  test    eax, eax
0x1800635b6  jnz     short loc_1800635FA
0x1800635b8  call    cs:__imp_GetLastError
0x1800635be  mov     ebx, eax
0x1800635c0  test    eax, eax
0x1800635c2  jle     short loc_1800635CD
0x1800635c4  movzx   ebx, ax
0x1800635c7  or      ebx, 80070000h
0x1800635cd  test    ebx, ebx
0x1800635cf  jns     short loc_1800635FA
0x1800635d1  mov     eax, cs:dword_1801B76C8
0x1800635d7  cmp     eax, 2
0x1800635da  jbe     loc_180063680
0x1800635e0  lea     rax, aFailedInWritef; "Failed in WriteFile to VmBus control ch"...
0x1800635e7  mov     dword ptr [rbp+57h+var_88], 1D0h
0x1800635ee  mov     [rbp+57h+var_90], ebx
0x1800635f1  lea     rdx, byte_18019C989
0x1800635f8  jmp     short loc_18006362E
0x1800635fa  cmp     [rbp+57h+NumberOfBytesWritten], 10h
0x1800635fe  jz      loc_18006368E
0x180063604  mov     eax, cs:dword_1801B76C8
0x18006360a  mov     ecx, 80004005h
0x18006360f  mov     ebx, ecx
0x180063611  cmp     eax, 2
0x180063614  jbe     short loc_180063680
0x180063616  lea     rax, aFailedNumberof; "Failed: numberOfBytesWritten != sizeof("...
0x18006361d  mov     dword ptr [rbp+57h+var_88], 1D6h
0x180063624  lea     rdx, byte_18019C935
0x18006362b  mov     [rbp+57h+var_90], ecx
0x18006362e  mov     [rbp+57h+var_70], rax
0x180063632  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180063639  mov     [rbp+57h+var_68], rax
0x18006363d  lea     rax, [rbp+57h+var_70]
0x180063641  mov     [rsp+0E0h+var_98], rax
0x180063646  lea     rax, [rbp+57h+var_78]
0x18006364a  mov     [rsp+0E0h+var_A0], rax
0x18006364f  lea     rax, [rbp+57h+var_88]
0x180063653  mov     [rsp+0E0h+var_A8], rax
0x180063658  lea     rax, [rbp+57h+var_80]
0x18006365c  mov     [rsp+0E0h+var_B0], rax
0x180063661  lea     rax, [rbp+57h+var_90]
0x180063665  mov     [rsp+0E0h+var_B8], rax
0x18006366a  lea     rax, [rbp+57h+var_68]
0x18006366e  mov     [rbp+57h+var_80], r13
0x180063672  mov     [rbp+57h+var_78], r12
0x180063676  mov     [rsp+0E0h+lpOverlapped], rax
0x18006367b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180063680  lea     rcx, [rbp+57h+var_60]; this
0x180063684  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180063689  jmp     loc_1800637E5
0x18006368e  mov     rcx, [rsi]; hFile
0x180063691  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180063695  xor     eax, eax
0x180063697  mov     [rbp+57h+NumberOfBytesRead], 0
0x18006369e  xorps   xmm0, xmm0
0x1800636a1  mov     [rbp+57h+var_30], al
0x1800636a4  lea     rdx, [rbp+57h+var_40]; lpBuffer
0x1800636a8  mov     [rsp+0E0h+lpOverlapped], rax; lpOverlapped
0x1800636ad  movups  [rbp+57h+var_40], xmm0
0x1800636b1  lea     r8d, [rax+11h]; nNumberOfBytesToRead
0x1800636b5  call    cs:__imp_ReadFile
0x1800636bb  test    eax, eax
0x1800636bd  jnz     short loc_180063700
0x1800636bf  call    cs:__imp_GetLastError
0x1800636c5  mov     ebx, eax
0x1800636c7  test    eax, eax
0x1800636c9  jle     short loc_1800636D4
0x1800636cb  movzx   ebx, ax
0x1800636ce  or      ebx, 80070000h
0x1800636d4  test    ebx, ebx
0x1800636d6  jns     short loc_180063700
0x1800636d8  mov     eax, cs:dword_1801B76C8
0x1800636de  cmp     eax, 2
0x1800636e1  jbe     short loc_180063680
0x1800636e3  lea     rax, aFailedInReadfi; "Failed in ReadFile from VmBus control c"...
0x1800636ea  mov     dword ptr [rbp+57h+var_88], 1E6h
0x1800636f1  mov     [rbp+57h+var_90], ebx
0x1800636f4  lea     rdx, byte_18019C8E1
0x1800636fb  jmp     loc_18006362E
0x180063700  cmp     [rbp+57h+NumberOfBytesRead], 11h
0x180063704  jz      short loc_180063736
0x180063706  mov     eax, cs:dword_1801B76C8
0x18006370c  mov     ecx, 80004005h
0x180063711  mov     ebx, ecx
0x180063713  cmp     eax, 2
0x180063716  jbe     loc_180063680
0x18006371c  lea     rax, aFailedNumberof_0; "Failed: numberOfBytesRead != sizeof(ver"...
0x180063723  mov     dword ptr [rbp+57h+var_88], 1ECh
0x18006372a  lea     rdx, byte_18019C88D
0x180063731  jmp     loc_18006362B
0x180063736  cmp     [rbp+57h+var_30], 2
0x18006373a  jz      short loc_18006376C
0x18006373c  mov     eax, cs:dword_1801B76C8
0x180063742  mov     ecx, 80004005h
0x180063747  mov     ebx, ecx
0x180063749  cmp     eax, 2
0x18006374c  jbe     loc_180063680
0x180063752  lea     rax, aFailedVersionr; "Failed: versionResponse.IsAccepted != S"...
0x180063759  mov     dword ptr [rbp+57h+var_88], 1F2h
0x180063760  lea     rdx, byte_18019C839
0x180063767  jmp     loc_18006362B
0x18006376c  mov     rcx, [rsi]; FileHandle
0x18006376f  lea     rdx, ?StaticControlIoCompletion@CUMRDPListenerVMBus@@CAXKKPEAX@Z; Function
0x180063776  xor     r8d, r8d; Flags
0x180063779  call    cs:__imp_BindIoCompletionCallback
0x18006377f  test    eax, eax
0x180063781  jnz     short loc_1800637D0
0x180063783  call    cs:__imp_GetLastError
0x180063789  mov     ecx, eax; Status
0x18006378b  call    cs:__imp_RtlNtStatusToDosError
0x180063791  mov     ebx, eax
0x180063793  test    eax, eax
0x180063795  jle     short loc_1800637A0
0x180063797  movzx   ebx, ax
0x18006379a  or      ebx, 80070000h
0x1800637a0  test    ebx, ebx
0x1800637a2  jns     short loc_1800637D0
0x1800637a4  mov     eax, cs:dword_1801B76C8
0x1800637aa  cmp     eax, 2
0x1800637ad  jbe     loc_180063680
0x1800637b3  lea     rax, aFailedBindioco; "Failed: BindIoCompletionCallback."
0x1800637ba  mov     dword ptr [rbp+57h+var_88], 1FDh
0x1800637c1  mov     [rbp+57h+var_90], ebx
0x1800637c4  lea     rdx, byte_18019C7E5
0x1800637cb  jmp     loc_18006362E
0x1800637d0  lea     rcx, [rbp+57h+var_60]; this
0x1800637d4  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1800637d9  mov     rcx, rdi; this
0x1800637dc  call    ?StartControlReceive@CUMRDPListenerVMBus@@AEAAJXZ; CUMRDPListenerVMBus::StartControlReceive(void)
0x1800637e1  test    ebx, ebx
0x1800637e3  jns     short loc_18006384E
0x1800637e5  mov     eax, cs:dword_1801B76C8
0x1800637eb  cmp     eax, 2
0x1800637ee  jbe     short loc_180063846
0x1800637f0  lea     rax, aCumrdplistener_27; "CUMRDPListenerVMBus::AcceptControlChann"...
0x1800637f7  mov     [rbp+57h+var_70], r12
0x1800637fb  mov     [rbp+57h+var_80], rax
0x1800637ff  lea     rdx, byte_18019C799
0x180063806  lea     rax, [rbp+57h+var_70]
0x18006380a  mov     dword ptr [rbp+57h+var_88], 20Ch
0x180063811  mov     [rsp+0E0h+var_A0], rax
0x180063816  lea     rax, [rbp+57h+var_88]
0x18006381a  mov     [rsp+0E0h+var_A8], rax
0x18006381f  lea     rax, [rbp+57h+var_78]
0x180063823  mov     [rsp+0E0h+var_B0], rax
0x180063828  lea     rax, [rbp+57h+var_90]
0x18006382c  mov     [rsp+0E0h+var_B8], rax
0x180063831  lea     rax, [rbp+57h+var_80]
0x180063835  mov     [rsp+0E0h+lpOverlapped], rax
0x18006383a  mov     [rbp+57h+var_78], r13
0x18006383e  mov     [rbp+57h+var_90], ebx
0x180063841  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180063846  mov     rcx, rdi; this
0x180063849  call    ?ResetControlChannel@CUMRDPListenerVMBus@@AEAAXXZ; CUMRDPListenerVMBus::ResetControlChannel(void)
0x18006384e  mov     rcx, [rbp+57h+var_28]
0x180063852  xor     rcx, rsp; StackCookie
0x180063855  call    __security_check_cookie
0x18006385a  mov     rbx, [rsp+0E0h+arg_10]
0x180063862  add     rsp, 0C0h
0x180063869  pop     r13
0x18006386b  pop     r12
0x18006386d  pop     rdi
0x18006386e  pop     rsi
0x18006386f  pop     rbp
0x180063870  retn
```
