# CServerVCChannel::IssueARead(void)

- ea: `0x18002081c`
- end: `0x1800209e4`
- name: `?IssueARead@CServerVCChannel@@AEAAJXZ`
- size: `456`
- prototype: `__int64 __fastcall(CServerVCChannel *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180020b30`
- `0x180021430`

## callees

- `0x18000f068`
- `0x18000f08c`
- `0x180012e60`
- `0x1800144c8`
- `0x18001d04c`
- `0x18001d114`
- `0x18001ef44`
- `0x18002081c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002089e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002089e`
- `api-ms-win-core-file-l1-1-0!ReadFileEx` at `0x180020896`
- `api-ms-win-core-file-l1-1-0!ReadFileEx` at `0x180020896`

## string_xrefs

- `0x180020926`: `ReadFileEx Failed`

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
  _BYTE *v8; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  bool v10; // sf
  unsigned int v11; // eax
  __int64 *v12; // rdi
  signed int v14; // [rsp+28h] [rbp-20h]
  __int64 v15; // [rsp+50h] [rbp+8h] BYREF
  CTSCriticalSection *v16; // [rsp+58h] [rbp+10h] BYREF

  v2 = 0;
  v15 = 0;
  v16 = (CServerVCChannel *)((char *)this + 56);
  CTSCriticalSection::Lock((CServerVCChannel *)((char *)this + 56));
  if ( (*((_BYTE *)this + 36) & 4) != 0 )
  {
    CTSAutoLock::~CTSAutoLock(&v16);
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
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      &WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
      CurrentThreadActivityIdPrefix,
      LastError);
    v8 = WPP_GLOBAL_Control;
  }
  v10 = LastError < 0;
  if ( LastError > 0 )
  {
    LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = LastError < 0;
  }
  if ( v10 )
  {
    if ( v8 != (_BYTE *)&WPP_GLOBAL_Control && (v8[28] & 8) != 0 && v8[25] >= 2u )
    {
      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
      v14 = LastError;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        (unsigned int)&WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
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
      TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v15);
      v2 = *v12;
      v15 = *v12;
      TCntPtr<ITSAsyncCallback>::SafeAddRef(&v15);
    }
    if ( *v12 )
    {
      TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease((char *)this + 72);
      *v12 = 0;
      TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 72);
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 16LL))(*((_QWORD *)this + 5));
  }
LABEL_22:
  CTSAutoLock::~CTSAutoLock(&v16);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 32LL))(v2);
LABEL_24:
  TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v15);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18002081c  mov     [rsp+arg_10], rbx
0x180020821  push    rbp
0x180020822  push    rsi
0x180020823  push    rdi
0x180020824  sub     rsp, 30h
0x180020828  mov     rbp, rcx
0x18002082b  xor     ebx, ebx
0x18002082d  add     rcx, 38h ; '8'; this
0x180020831  mov     [rsp+48h+arg_0], rbx
0x180020836  mov     [rsp+48h+arg_8], rcx
0x18002083b  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180020840  test    byte ptr [rbp+24h], 4
0x180020844  jz      short loc_18002085A
0x180020846  lea     rcx, [rsp+48h+arg_8]; this
0x18002084b  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180020850  mov     esi, 800702A4h
0x180020855  jmp     loc_1800209CB
0x18002085a  mov     rcx, [rbp+28h]
0x18002085e  mov     rax, [rcx]
0x180020861  mov     rax, [rax+8]
0x180020865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002086a  mov     r8d, [rbp+178h]; nNumberOfBytesToRead
0x180020871  lea     r9, [rbp+198h]; lpOverlapped
0x180020878  mov     rdx, [rbp+170h]; lpBuffer
0x18002087f  lea     rax, ?static_ReadCompletionRoutine@CServerVCChannel@@CAXKKPEAU_OVERLAPPED@@@Z; CServerVCChannel::static_ReadCompletionRoutine(ulong,ulong,_OVERLAPPED *)
0x180020886  mov     rcx, [rbp+158h]; hFile
0x18002088d  mov     [r9+18h], rbp
0x180020891  mov     [rsp+48h+lpCompletionRoutine], rax; lpCompletionRoutine
0x180020896  call    cs:__imp_ReadFileEx
0x18002089c  mov     edi, eax
0x18002089e  call    cs:__imp_GetLastError
0x1800208a4  mov     esi, eax
0x1800208a6  test    edi, edi
0x1800208a8  jz      short loc_1800208B1
0x1800208aa  xor     esi, esi
0x1800208ac  jmp     loc_1800209AD
0x1800208b1  mov     rax, cs:WPP_GLOBAL_Control
0x1800208b8  lea     rdi, WPP_GLOBAL_Control
0x1800208bf  cmp     rax, rdi
0x1800208c2  jz      short loc_1800208FF
0x1800208c4  test    byte ptr [rax+1Ch], 1
0x1800208c8  jz      short loc_1800208FF
0x1800208ca  cmp     byte ptr [rax+19h], 2
0x1800208ce  jb      short loc_1800208FF
0x1800208d0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800208d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800208dc  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x1800208e3  mov     edx, 0Fh
0x1800208e8  mov     dword ptr [rsp+48h+lpCompletionRoutine], esi
0x1800208ec  mov     r9d, eax
0x1800208ef  mov     rcx, [rcx+10h]
0x1800208f3  call    WPP_SF_Dd
0x1800208f8  mov     rax, cs:WPP_GLOBAL_Control
0x1800208ff  test    esi, esi
0x180020901  jle     short loc_18002090E
0x180020903  movzx   esi, si
0x180020906  or      esi, 80070000h
0x18002090c  test    esi, esi
0x18002090e  jns     short loc_180020957
0x180020910  cmp     rax, rdi
0x180020913  jz      short loc_18002095B
0x180020915  test    byte ptr [rax+1Ch], 8
0x180020919  jz      short loc_18002095B
0x18002091b  cmp     byte ptr [rax+19h], 2
0x18002091f  jb      short loc_18002095B
0x180020921  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180020926  lea     rcx, aReadfileexFail; "ReadFileEx Failed"
0x18002092d  mov     [rsp+48h+var_20], esi
0x180020931  mov     [rsp+48h+lpCompletionRoutine], rcx
0x180020936  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x18002093d  mov     rcx, cs:WPP_GLOBAL_Control
0x180020944  mov     edx, 10h
0x180020949  mov     r9d, eax
0x18002094c  mov     rcx, [rcx+10h]
0x180020950  call    WPP_SF_DsD
0x180020955  jmp     short loc_18002095B
0x180020957  test    esi, esi
0x180020959  jz      short loc_1800209AD
0x18002095b  lea     rdi, [rbp+48h]
0x18002095f  cmp     [rdi], rbx
0x180020962  jz      short loc_180020980
0x180020964  lea     rcx, [rsp+48h+arg_0]
0x180020969  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x18002096e  mov     rbx, [rdi]
0x180020971  lea     rcx, [rsp+48h+arg_0]
0x180020976  mov     [rsp+48h+arg_0], rbx
0x18002097b  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180020980  cmp     qword ptr [rdi], 0
0x180020984  jz      short loc_18002099D
0x180020986  mov     rcx, rdi
0x180020989  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x18002098e  mov     rcx, rdi
0x180020991  mov     qword ptr [rdi], 0
0x180020998  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18002099d  mov     rcx, [rbp+28h]
0x1800209a1  mov     rax, [rcx]
0x1800209a4  mov     rax, [rax+10h]
0x1800209a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209ad  lea     rcx, [rsp+48h+arg_8]; this
0x1800209b2  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1800209b7  test    rbx, rbx
0x1800209ba  jz      short loc_1800209CB
0x1800209bc  mov     rcx, [rbx]
0x1800209bf  mov     rax, [rcx+20h]
0x1800209c3  mov     rcx, rbx
0x1800209c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209cb  lea     rcx, [rsp+48h+arg_0]
0x1800209d0  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x1800209d5  mov     rbx, [rsp+48h+arg_10]
0x1800209da  mov     eax, esi
0x1800209dc  add     rsp, 30h
0x1800209e0  pop     rdi
0x1800209e1  pop     rsi
0x1800209e2  pop     rbp
0x1800209e3  retn
```
