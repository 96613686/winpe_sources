# CServerVCChannel::IssueARead(void)

- ea: `0x140026abc`
- end: `0x140026c84`
- name: `?IssueARead@CServerVCChannel@@AEAAJXZ`
- size: `456`
- prototype: `__int64 __fastcall(CServerVCChannel *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140026dd0`
- `0x1400276e0`

## callees

- `0x140004b1c`
- `0x140005704`
- `0x140005750`
- `0x1400081ac`
- `0x1400081d0`
- `0x14000d350`
- `0x14000efb8`
- `0x140026abc`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026b3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026b3e`
- `api-ms-win-core-file-l1-1-0!ReadFileEx` at `0x140026b36`
- `api-ms-win-core-file-l1-1-0!ReadFileEx` at `0x140026b36`

## string_xrefs

- `0x140026bc6`: `ReadFileEx Failed`

## pseudocode

```c
__int64 __fastcall CServerVCChannel::IssueARead(CServerVCChannel *this)
{
  __int64 v2; // rbx
  signed int LastError; // esi
  DWORD v4; // r8d
  void *v5; // rdx
  void *v6; // rcx
  BOOL File; // edi
  PVOID *v8; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  bool v10; // sf
  unsigned int v11; // eax
  __int64 *v12; // rdi
  signed int v14; // [rsp+28h] [rbp-20h]
  __int64 v15; // [rsp+50h] [rbp+8h] BYREF
  char *v16; // [rsp+58h] [rbp+10h] BYREF

  v2 = 0;
  v15 = 0;
  v16 = (char *)this + 56;
  CTSCriticalSection::Lock((CServerVCChannel *)((char *)this + 56));
  if ( (*((_BYTE *)this + 36) & 4) != 0 )
  {
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v16);
    LastError = -2147024220;
    goto LABEL_24;
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 8LL))(*((_QWORD *)this + 5));
  v4 = *((_DWORD *)this + 94);
  v5 = (void *)*((_QWORD *)this + 46);
  v6 = (void *)*((_QWORD *)this + 43);
  *((_QWORD *)this + 54) = this;
  File = ReadFileEx(v6, v5, v4, (LPOVERLAPPED)((char *)this + 408), CServerVCChannel::static_ReadCompletionRoutine);
  LastError = GetLastError();
  if ( File )
  {
    LastError = 0;
    goto LABEL_22;
  }
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
      CurrentThreadActivityIdPrefix,
      LastError);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  v10 = LastError < 0;
  if ( LastError > 0 )
  {
    LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = LastError < 0;
  }
  if ( v10 )
  {
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 && *((_BYTE *)v8 + 25) >= 2u )
    {
      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
      v14 = LastError;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        (unsigned int)WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
        v11,
        (__int64)"ReadFileEx Failed",
        v14);
    }
    goto LABEL_17;
  }
  if ( LastError )
  {
LABEL_17:
    v12 = (__int64 *)((char *)this + 72);
    if ( *((_QWORD *)this + 9) )
    {
      TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v15);
      v2 = *v12;
      v15 = *v12;
      TCntPtr<IRdrVirtualChannel>::SafeAddRef(&v15);
    }
    if ( *v12 )
    {
      TCntPtr<IRdpHintApiEventSink>::SafeRelease((char *)this + 72);
      *v12 = 0;
      TCntPtr<IRdrVirtualChannel>::SafeAddRef((char *)this + 72);
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 16LL))(*((_QWORD *)this + 5));
  }
LABEL_22:
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v16);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 32LL))(v2);
LABEL_24:
  TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v15);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140026abc  mov     [rsp+arg_10], rbx
0x140026ac1  push    rbp
0x140026ac2  push    rsi
0x140026ac3  push    rdi
0x140026ac4  sub     rsp, 30h
0x140026ac8  mov     rbp, rcx
0x140026acb  xor     ebx, ebx
0x140026acd  add     rcx, 38h ; '8'; this
0x140026ad1  mov     [rsp+48h+arg_0], rbx
0x140026ad6  mov     [rsp+48h+arg_8], rcx
0x140026adb  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x140026ae0  test    byte ptr [rbp+24h], 4
0x140026ae4  jz      short loc_140026AFA
0x140026ae6  lea     rcx, [rsp+48h+arg_8]; this
0x140026aeb  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x140026af0  mov     esi, 800702A4h
0x140026af5  jmp     loc_140026C6B
0x140026afa  mov     rcx, [rbp+28h]
0x140026afe  mov     rax, [rcx]
0x140026b01  mov     rax, [rax+8]
0x140026b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026b0a  mov     r8d, [rbp+178h]; nNumberOfBytesToRead
0x140026b11  lea     r9, [rbp+198h]; lpOverlapped
0x140026b18  mov     rdx, [rbp+170h]; lpBuffer
0x140026b1f  lea     rax, ?static_ReadCompletionRoutine@CServerVCChannel@@CAXKKPEAU_OVERLAPPED@@@Z; CServerVCChannel::static_ReadCompletionRoutine(ulong,ulong,_OVERLAPPED *)
0x140026b26  mov     rcx, [rbp+158h]; hFile
0x140026b2d  mov     [r9+18h], rbp
0x140026b31  mov     [rsp+48h+lpCompletionRoutine], rax; lpCompletionRoutine
0x140026b36  call    cs:__imp_ReadFileEx
0x140026b3c  mov     edi, eax
0x140026b3e  call    cs:__imp_GetLastError
0x140026b44  mov     esi, eax
0x140026b46  test    edi, edi
0x140026b48  jz      short loc_140026B51
0x140026b4a  xor     esi, esi
0x140026b4c  jmp     loc_140026C4D
0x140026b51  mov     rax, cs:WPP_GLOBAL_Control
0x140026b58  lea     rdi, WPP_GLOBAL_Control
0x140026b5f  cmp     rax, rdi
0x140026b62  jz      short loc_140026B9F
0x140026b64  test    byte ptr [rax+1Ch], 1
0x140026b68  jz      short loc_140026B9F
0x140026b6a  cmp     byte ptr [rax+19h], 2
0x140026b6e  jb      short loc_140026B9F
0x140026b70  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140026b75  mov     rcx, cs:WPP_GLOBAL_Control
0x140026b7c  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x140026b83  mov     edx, 0Fh
0x140026b88  mov     dword ptr [rsp+48h+lpCompletionRoutine], esi
0x140026b8c  mov     r9d, eax
0x140026b8f  mov     rcx, [rcx+10h]
0x140026b93  call    WPP_SF_Dd
0x140026b98  mov     rax, cs:WPP_GLOBAL_Control
0x140026b9f  test    esi, esi
0x140026ba1  jle     short loc_140026BAE
0x140026ba3  movzx   esi, si
0x140026ba6  or      esi, 80070000h
0x140026bac  test    esi, esi
0x140026bae  jns     short loc_140026BF7
0x140026bb0  cmp     rax, rdi
0x140026bb3  jz      short loc_140026BFB
0x140026bb5  test    byte ptr [rax+1Ch], 8
0x140026bb9  jz      short loc_140026BFB
0x140026bbb  cmp     byte ptr [rax+19h], 2
0x140026bbf  jb      short loc_140026BFB
0x140026bc1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140026bc6  lea     rcx, aReadfileexFail; "ReadFileEx Failed"
0x140026bcd  mov     [rsp+48h+var_20], esi
0x140026bd1  mov     [rsp+48h+lpCompletionRoutine], rcx
0x140026bd6  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x140026bdd  mov     rcx, cs:WPP_GLOBAL_Control
0x140026be4  mov     edx, 10h
0x140026be9  mov     r9d, eax
0x140026bec  mov     rcx, [rcx+10h]
0x140026bf0  call    WPP_SF_DsD
0x140026bf5  jmp     short loc_140026BFB
0x140026bf7  test    esi, esi
0x140026bf9  jz      short loc_140026C4D
0x140026bfb  lea     rdi, [rbp+48h]
0x140026bff  cmp     [rdi], rbx
0x140026c02  jz      short loc_140026C20
0x140026c04  lea     rcx, [rsp+48h+arg_0]
0x140026c09  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x140026c0e  mov     rbx, [rdi]
0x140026c11  lea     rcx, [rsp+48h+arg_0]
0x140026c16  mov     [rsp+48h+arg_0], rbx
0x140026c1b  call    ?SafeAddRef@?$TCntPtr@VIRdrVirtualChannel@@@@AEAAXXZ; TCntPtr<IRdrVirtualChannel>::SafeAddRef(void)
0x140026c20  cmp     qword ptr [rdi], 0
0x140026c24  jz      short loc_140026C3D
0x140026c26  mov     rcx, rdi
0x140026c29  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x140026c2e  mov     rcx, rdi
0x140026c31  mov     qword ptr [rdi], 0
0x140026c38  call    ?SafeAddRef@?$TCntPtr@VIRdrVirtualChannel@@@@AEAAXXZ; TCntPtr<IRdrVirtualChannel>::SafeAddRef(void)
0x140026c3d  mov     rcx, [rbp+28h]
0x140026c41  mov     rax, [rcx]
0x140026c44  mov     rax, [rax+10h]
0x140026c48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026c4d  lea     rcx, [rsp+48h+arg_8]; this
0x140026c52  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x140026c57  test    rbx, rbx
0x140026c5a  jz      short loc_140026C6B
0x140026c5c  mov     rcx, [rbx]
0x140026c5f  mov     rax, [rcx+20h]
0x140026c63  mov     rcx, rbx
0x140026c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026c6b  lea     rcx, [rsp+48h+arg_0]
0x140026c70  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x140026c75  mov     rbx, [rsp+48h+arg_10]
0x140026c7a  mov     eax, esi
0x140026c7c  add     rsp, 30h
0x140026c80  pop     rdi
0x140026c81  pop     rsi
0x140026c82  pop     rbp
0x140026c83  retn
```
