# CDiskPnpMonitor::Initialize(void)

- ea: `0x180019a98`
- end: `0x180019ca9`
- name: `?Initialize@CDiskPnpMonitor@@QEAAJXZ`
- size: `529`
- prototype: `__int64 __fastcall(CDiskPnpMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180016750`

## callees

- `0x1800031a0`
- `0x1800032f8`
- `0x180006688`
- `0x1800068b4`
- `0x1800136e0`
- `0x180019a98`

## import_xrefs

- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x180019bec`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x180019bec`
- `KERNEL32!CreateEventW` at `0x180019b4e`
- `KERNEL32!CreateEventW` at `0x180019bd9`
- `KERNEL32!CreateEventW` at `0x180019b4e`
- `KERNEL32!CreateEventW` at `0x180019bd9`
- `KERNEL32!GetLastError` at `0x180019b68`
- `KERNEL32!GetLastError` at `0x180019c06`
- `KERNEL32!GetLastError` at `0x180019b68`
- `KERNEL32!GetLastError` at `0x180019c06`

## string_xrefs

- `0x180019ba5`: `Hr = BOOL_HR( nullptr != InitCompleteEvent )`

## pseudocode

```c
__int64 __fastcall CDiskPnpMonitor::Initialize(CDiskPnpMonitor *this)
{
  _QWORD *ThreadLocalStoragePointer; // rax
  USHORT Length; // cx
  __int64 v4; // r8
  USHORT v5; // ax
  signed int v6; // eax
  signed int v7; // ebx
  struct _TP_CLEANUP_GROUP *ThreadpoolCleanupGroup; // rax
  signed int LastError; // eax
  const char *v11; // [rsp+30h] [rbp-28h] BYREF
  signed int v12; // [rsp+38h] [rbp-20h]
  struct _TP_CLEANUP_GROUP *EventW; // [rsp+40h] [rbp-18h] BYREF
  char *v14; // [rsp+48h] [rbp-10h]

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  Length = GlobalIndentString.Length;
  v11 = "CDiskPnpMonitor::Initialize";
  v4 = ThreadLocalStoragePointer[tls_index];
  *(_QWORD *)(v4 + 16) = "CDiskPnpMonitor::Initialize";
  v5 = Length;
  if ( ++*(_WORD *)(v4 + 8) < Length )
  {
    v5 = *(_WORD *)(v4 + 8);
    Length = v5;
  }
  LOWORD(EventW) = v5;
  HIDWORD(EventW) = 0;
  v14 = off_180047060;
  WORD1(EventW) = Length;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CDiskPnpMonitor::Initialize");
  }
  EventW = (struct _TP_CLEANUP_GROUP *)CreateEventW(0, 1, 0, 0);
  LODWORD(v14) = 0;
  BYTE4(v14) = 0;
  if ( EventW )
  {
    *((_QWORD *)this + 1) = CreateEventW(0, 1, 0, 0);
    CHandleT<void *,ObjectHandleTrait>::~CHandleT<void *,ObjectHandleTrait>(&EventW);
    ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
    EventW = ThreadpoolCleanupGroup;
    LODWORD(v14) = 0;
    BYTE4(v14) = 0;
    if ( ThreadpoolCleanupGroup )
    {
      *((_QWORD *)this + 6) = ThreadpoolCleanupGroup;
      *((_QWORD *)this + 7) = 0;
      *((_QWORD *)this + 13) = ThreadpoolCleanupGroup;
      EventW = 0;
      CHandleT<_TP_CLEANUP_GROUP *,ThreadPoolCleanupGroupTrait>::~CHandleT<_TP_CLEANUP_GROUP *,ThreadPoolCleanupGroupTrait>(&EventW);
      v7 = 0;
      v12 = 0;
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( v7 >= 0 )
        v7 = -2147467259;
      v12 = v7;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)&WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids,
          (unsigned int)"Hr = BOOL_HR( nullptr != TpCleanup )",
          v7);
      }
      CHandleT<_TP_CLEANUP_GROUP *,ThreadPoolCleanupGroupTrait>::~CHandleT<_TP_CLEANUP_GROUP *,ThreadPoolCleanupGroupTrait>(&EventW);
    }
  }
  else
  {
    v6 = GetLastError();
    v7 = v6;
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    if ( v7 >= 0 )
      v7 = -2147467259;
    v12 = v7;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)&WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids,
        (unsigned int)"Hr = BOOL_HR( nullptr != InitCompleteEvent )",
        v7);
    }
    CHandleT<void *,ObjectHandleTrait>::~CHandleT<void *,ObjectHandleTrait>(&EventW);
  }
  CHResultImp::~CHResultImp((CHResultImp *)&v11);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180019a98  push    rbp
0x180019a9a  push    rbx
0x180019a9b  push    rsi
0x180019a9c  push    r14
0x180019a9e  mov     rbp, rsp
0x180019aa1  sub     rsp, 58h
0x180019aa5  mov     edx, cs:_tls_index
0x180019aab  lea     r9, aCdiskpnpmonito_2; "CDiskPnpMonitor::Initialize"
0x180019ab2  mov     rax, gs:58h
0x180019abb  mov     rbx, rcx
0x180019abe  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x180019ac5  mov     esi, 1
0x180019aca  mov     [rbp+var_28], r9
0x180019ace  mov     r8, [rax+rdx*8]
0x180019ad2  mov     eax, 10h
0x180019ad7  mov     edx, 8
0x180019adc  mov     [rax+r8], r9
0x180019ae0  movzx   eax, cx
0x180019ae3  add     [rdx+r8], si
0x180019ae8  movzx   edx, word ptr [rdx+r8]
0x180019aed  cmp     dx, cx
0x180019af0  cmovb   ax, dx
0x180019af4  cmovb   cx, dx
0x180019af8  mov     word ptr [rbp+var_18], ax
0x180019afc  xor     eax, eax
0x180019afe  mov     dword ptr [rbp+var_18+4], eax
0x180019b01  mov     rax, cs:off_180047060; "                                       "...
0x180019b08  mov     [rbp+var_10], rax
0x180019b0c  mov     word ptr [rbp+var_18+2], cx
0x180019b10  mov     rcx, cs:WPP_GLOBAL_Control
0x180019b17  lea     r14, WPP_GLOBAL_Control
0x180019b1e  cmp     rcx, r14
0x180019b21  jz      short loc_180019B44
0x180019b23  test    [rcx+1Ch], sil
0x180019b27  jz      short loc_180019B44
0x180019b29  cmp     byte ptr [rcx+19h], 5
0x180019b2d  jb      short loc_180019B44
0x180019b2f  mov     rcx, [rcx+10h]; LoggerHandle
0x180019b33  lea     edx, [rsi+0Ch]
0x180019b36  mov     [rsp+58h+var_38], r9; __int64
0x180019b3b  lea     r9, [rbp+var_18]
0x180019b3f  call    WPP_SF_aZs
0x180019b44  xor     r9d, r9d; lpName
0x180019b47  xor     r8d, r8d; bInitialState
0x180019b4a  mov     edx, esi; bManualReset
0x180019b4c  xor     ecx, ecx; lpEventAttributes
0x180019b4e  call    cs:__imp_CreateEventW
0x180019b54  mov     [rbp+var_18], rax
0x180019b58  mov     dword ptr [rbp+var_10], 0
0x180019b5f  mov     byte ptr [rbp+var_10+4], 0
0x180019b63  test    rax, rax
0x180019b66  jnz     short loc_180019BCF
0x180019b68  call    cs:__imp_GetLastError
0x180019b6e  mov     ebx, eax
0x180019b70  test    eax, eax
0x180019b72  jle     short loc_180019B7D
0x180019b74  movzx   ebx, ax
0x180019b77  or      ebx, 80070000h
0x180019b7d  test    ebx, ebx
0x180019b7f  js      short loc_180019B86
0x180019b81  mov     ebx, 80004005h
0x180019b86  mov     [rbp+var_20], ebx
0x180019b89  mov     rcx, cs:WPP_GLOBAL_Control
0x180019b90  cmp     rcx, r14
0x180019b93  jz      short loc_180019BC1
0x180019b95  test    [rcx+1Ch], sil
0x180019b99  jz      short loc_180019BC1
0x180019b9b  cmp     byte ptr [rcx+19h], 2
0x180019b9f  jb      short loc_180019BC1
0x180019ba1  mov     rcx, [rcx+10h]
0x180019ba5  lea     r9, aHrBoolHrNullpt_0; "Hr = BOOL_HR( nullptr != InitCompleteEv"...
0x180019bac  mov     edx, 0Ah
0x180019bb1  mov     dword ptr [rsp+58h+var_38], ebx
0x180019bb5  lea     r8, WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids
0x180019bbc  call    WPP_SF_sd
0x180019bc1  lea     rcx, [rbp+var_18]
0x180019bc5  call    ??1?$CHandleT@PEAXUObjectHandleTrait@@@@QEAA@XZ; CHandleT<void *,ObjectHandleTrait>::~CHandleT<void *,ObjectHandleTrait>(void)
0x180019bca  jmp     loc_180019C94
0x180019bcf  xor     r9d, r9d; lpName
0x180019bd2  xor     r8d, r8d; bInitialState
0x180019bd5  mov     edx, esi; bManualReset
0x180019bd7  xor     ecx, ecx; lpEventAttributes
0x180019bd9  call    cs:__imp_CreateEventW
0x180019bdf  lea     rcx, [rbp+var_18]
0x180019be3  mov     [rbx+8], rax
0x180019be7  call    ??1?$CHandleT@PEAXUObjectHandleTrait@@@@QEAA@XZ; CHandleT<void *,ObjectHandleTrait>::~CHandleT<void *,ObjectHandleTrait>(void)
0x180019bec  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180019bf2  mov     [rbp+var_18], rax
0x180019bf6  mov     dword ptr [rbp+var_10], 0
0x180019bfd  mov     byte ptr [rbp+var_10+4], 0
0x180019c01  test    rax, rax
0x180019c04  jnz     short loc_180019C6A
0x180019c06  call    cs:__imp_GetLastError
0x180019c0c  mov     ebx, eax
0x180019c0e  test    eax, eax
0x180019c10  jle     short loc_180019C1B
0x180019c12  movzx   ebx, ax
0x180019c15  or      ebx, 80070000h
0x180019c1b  test    ebx, ebx
0x180019c1d  js      short loc_180019C24
0x180019c1f  mov     ebx, 80004005h
0x180019c24  mov     [rbp+var_20], ebx
0x180019c27  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c2e  cmp     rcx, r14
0x180019c31  jz      short loc_180019C5F
0x180019c33  test    [rcx+1Ch], sil
0x180019c37  jz      short loc_180019C5F
0x180019c39  cmp     byte ptr [rcx+19h], 2
0x180019c3d  jb      short loc_180019C5F
0x180019c3f  mov     rcx, [rcx+10h]
0x180019c43  lea     r9, aHrBoolHrNullpt; "Hr = BOOL_HR( nullptr != TpCleanup )"
0x180019c4a  mov     edx, 0Bh
0x180019c4f  mov     dword ptr [rsp+58h+var_38], ebx
0x180019c53  lea     r8, WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids
0x180019c5a  call    WPP_SF_sd
0x180019c5f  lea     rcx, [rbp+var_18]
0x180019c63  call    ??1?$CHandleT@PEAU_TP_CLEANUP_GROUP@@UThreadPoolCleanupGroupTrait@@@@QEAA@XZ; CHandleT<_TP_CLEANUP_GROUP *,ThreadPoolCleanupGroupTrait>::~CHandleT<_TP_CLEANUP_GROUP *,ThreadPoolCleanupGroupTrait>(void)
0x180019c68  jmp     short loc_180019C94
0x180019c6a  mov     [rbx+30h], rax
0x180019c6e  lea     rcx, [rbp+var_18]
0x180019c72  mov     qword ptr [rbx+38h], 0
0x180019c7a  mov     [rbx+68h], rax
0x180019c7e  mov     [rbp+var_18], 0
0x180019c86  call    ??1?$CHandleT@PEAU_TP_CLEANUP_GROUP@@UThreadPoolCleanupGroupTrait@@@@QEAA@XZ; CHandleT<_TP_CLEANUP_GROUP *,ThreadPoolCleanupGroupTrait>::~CHandleT<_TP_CLEANUP_GROUP *,ThreadPoolCleanupGroupTrait>(void)
0x180019c8b  xor     ebx, ebx
0x180019c8d  mov     [rbp+var_20], 0
0x180019c94  lea     rcx, [rbp+var_28]; this
0x180019c98  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x180019c9d  mov     eax, ebx
0x180019c9f  add     rsp, 58h
0x180019ca3  pop     r14
0x180019ca5  pop     rsi
0x180019ca6  pop     rbx
0x180019ca7  pop     rbp
0x180019ca8  retn
```
