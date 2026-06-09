# EapHostPeerGetResult

- ea: `0x180008cf0`
- end: `0x18000921f`
- name: `EapHostPeerGetResult`
- size: `1327`
- prototype: `DWORD __stdcall(EAP_SESSIONID sessionHandle, EapHostPeerMethodResultReason reason, EapHostPeerMethodResult *ppResult, EAP_ERROR **ppEapError)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001780`
- `0x1800020d6`
- `0x180002106`
- `0x1800030f8`
- `0x180005450`
- `0x180008cf0`
- `0x18000ace0`
- `0x18000aeb8`
- `0x18000af7c`
- `0x18000b824`
- `0x18000bef4`
- `0x18000dec0`
- `0x18000f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008f95`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008f95`
- `ntdll!EtwEventEnabled` at `0x180008dc9`
- `ntdll!EtwEventEnabled` at `0x18000909a`
- `ntdll!EtwEventEnabled` at `0x180008dc9`
- `ntdll!EtwEventEnabled` at `0x18000909a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009080`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009080`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008d47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008d47`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008d59`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008d59`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
DWORD __stdcall EapHostPeerGetResult(
        EAP_SESSIONID sessionHandle,
        EapHostPeerMethodResultReason reason,
        EapHostPeerMethodResult *ppResult,
        EAP_ERROR **ppEapError)
{
  EAP_SESSIONID v6; // r15d
  unsigned __int64 v7; // rbx
  DWORD TickCount; // eax
  __int64 v9; // r8
  unsigned __int64 v10; // r13
  __int64 v11; // r8
  __int64 v12; // rsi
  __int64 v13; // rax
  void *v14; // rcx
  signed int SessionFreeBuffers; // ebx
  EAP_ERROR **v16; // rbx
  char *v17; // rax
  char *v18; // r14
  _OWORD *v19; // rax
  char *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r8
  LPWSTR lpBuffer; // [rsp+20h] [rbp-1108h]
  __int64 nSize; // [rsp+28h] [rbp-1100h]
  va_list *Arguments; // [rsp+30h] [rbp-10F8h]
  char *v27; // [rsp+40h] [rbp-10E8h] BYREF
  EapHost::Peer::ConnectionSessionInfo *v28; // [rsp+48h] [rbp-10E0h] BYREF
  EAP_SESSIONID v29; // [rsp+50h] [rbp-10D8h]
  LPVOID v30; // [rsp+58h] [rbp-10D0h] BYREF
  unsigned __int64 v31; // [rsp+60h] [rbp-10C8h] BYREF
  EAP_ERROR **v32; // [rsp+68h] [rbp-10C0h]
  __int128 v33; // [rsp+70h] [rbp-10B8h] BYREF
  __int128 v34; // [rsp+80h] [rbp-10A8h]
  __int128 v35; // [rsp+90h] [rbp-1098h]
  __int128 v36; // [rsp+A0h] [rbp-1088h]
  EAP_ERROR *v37; // [rsp+B0h] [rbp-1078h]
  _BYTE v38[16]; // [rsp+C0h] [rbp-1068h] BYREF
  char *v39; // [rsp+D0h] [rbp-1058h]
  __int64 v40; // [rsp+D8h] [rbp-1050h]
  char v41[2048]; // [rsp+E0h] [rbp-1048h] BYREF
  WCHAR Buffer[1024]; // [rsp+8E0h] [rbp-848h] BYREF

  v32 = ppEapError;
  LODWORD(v27) = reason;
  v6 = sessionHandle;
  v29 = sessionHandle;
  memset_0(&v33, 0, 0x48u);
  v30 = 0;
  v7 = (unsigned __int64)GetCurrentThreadId() << 32;
  TickCount = GetTickCount();
  v10 = v7 | TickCount;
  v31 = v10;
  if ( Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v28 = (EapHost::Peer::ConnectionSessionInfo *)(v7 | TickCount);
    v39 = (char *)&v28;
    v40 = 8;
    McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)GetResultStart, v9, 2, (__int64)v38);
  }
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v41, 0x800u, "EapHostPeerGetResult Entry:\n Session(%d), reason(%d)", v6, reason) >= 0 )
  {
    v12 = -1;
    if ( Microsoft_Windows_EapHostEnableBits < 0 )
    {
      v13 = -1;
      do
        ++v13;
      while ( v41[v13] );
      v39 = v41;
      v40 = (unsigned int)(v13 + 1);
      McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v11, 2, (__int64)v38);
    }
  }
  else
  {
    v12 = -1;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, v11, v6, (_DWORD)v27);
  v28 = 0;
  if ( !v6 )
    goto LABEL_14;
  SessionFreeBuffers = EapHost::Peer::PeerProxy::FindSessionFreeBuffers((__int64)v14, v6, &v28, &v30, 0);
  if ( SessionFreeBuffers )
    goto LABEL_32;
  if ( ppResult )
  {
    v16 = v32;
    if ( v32 )
      *v32 = 0;
    memset_0(&v33, 0, 0x48u);
    memset_0(ppResult, 0, sizeof(EapHostPeerMethodResult));
    SessionFreeBuffers = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, __int128 *, EAP_ERROR **))(*(_QWORD *)v30 + 48LL))(
                           v30,
                           v6,
                           (unsigned int)v27,
                           &v33,
                           v16);
    if ( SessionFreeBuffers >= 0 )
    {
      try
      {
        v17 = (char *)operator new(0x58u);
        v18 = v17;
        if ( v17 )
        {
          *((_DWORD *)v17 + 2) = 0;
          *(_QWORD *)v17 = &EapHost::PeerMethodResultBuffer::`vftable';
          v19 = v17 + 16;
          if ( v18 == (char *)-16LL )
          {
            *(_DWORD *)_o__errno() = 22;
            invalid_parameter_noinfo();
          }
          else
          {
            *v19 = v33;
            *((_OWORD *)v18 + 2) = v34;
            *((_OWORD *)v18 + 3) = v35;
            *((_OWORD *)v18 + 4) = v36;
            *((_QWORD *)v18 + 10) = v37;
          }
          v27 = v18;
          _InterlockedIncrement((volatile signed __int32 *)v18 + 2);
        }
        else
        {
          v27 = 0;
        }
        EapHost::Peer::ConnectionSessionInfo::AddBuffer(v28, &v27);
        v20 = v27;
        if ( v27 && _InterlockedExchangeAdd((volatile signed __int32 *)v27 + 2, 0xFFFFFFFF) == 1 && v20 )
          (**(void (__fastcall ***)(char *, __int64))v20)(v20, 1);
        *(_OWORD *)&ppResult->fIsSuccess = v33;
        *(_OWORD *)&ppResult->pConnectionData = v34;
        *(_OWORD *)&ppResult->pUserData = v35;
        *(_OWORD *)&ppResult->isolationState = v36;
        ppResult->pEapError = v37;
      }
      catch ( std::bad_alloc )
      {
        LODWORD(v27) = 14;
        v12 = -1;
        SessionFreeBuffers = 14;
        v6 = v29;
        v10 = v31;
      }
    }
  }
  else
  {
LABEL_14:
    SessionFreeBuffers = 160;
  }
LABEL_32:
  FormatMessageW(0x1200u, 0, SessionFreeBuffers, 0, Buffer, 0x400u, 0);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent) )
  {
    LODWORD(Arguments) = DWORD1(v33);
    LODWORD(nSize) = v33;
    LODWORD(lpBuffer) = v6;
    if ( (int)StringCchPrintfA(
                v41,
                0x800u,
                "EapHostPeerGetResult Exit:\n %ws\n Returned session(%d), result( isSuccess=%d, failure reason=%d)",
                Buffer,
                lpBuffer,
                nSize,
                Arguments) >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      do
        ++v12;
      while ( v41[v12] );
      v39 = v41;
      v40 = (unsigned int)(v12 + 1);
      McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v22, 2, (__int64)v38);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_Dddd(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, v22, (unsigned int)SessionFreeBuffers, v6, v33, DWORD1(v33));
  if ( v28 )
    _InterlockedCompareExchange((volatile signed __int32 *)v28 + 43, 0, *((_DWORD *)v28 + 43));
  if ( Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v31 = v10;
    v39 = (char *)&v31;
    v40 = 8;
    McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)GetResultEnd, v22, 2, (__int64)v38);
  }
  if ( v30 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v30 + 16LL))(v30);
  return SessionFreeBuffers;
}

```

## disassembly

```asm
0x180008cf0  push    rbx
0x180008cf2  push    rsi
0x180008cf3  push    rdi
0x180008cf4  push    r12
0x180008cf6  push    r13
0x180008cf8  push    r14
0x180008cfa  push    r15
0x180008cfc  mov     eax, 10F0h
0x180008d01  call    _alloca_probe
0x180008d06  sub     rsp, rax
0x180008d09  mov     rax, cs:__security_cookie
0x180008d10  xor     rax, rsp
0x180008d13  mov     [rsp+1128h+var_48], rax
0x180008d1b  mov     [rsp+1128h+var_10C0], r9
0x180008d20  mov     r12, r8
0x180008d23  mov     esi, edx
0x180008d25  mov     dword ptr [rsp+1128h+var_10E8], edx
0x180008d29  mov     r15d, ecx
0x180008d2c  mov     [rsp+1128h+var_10D8], ecx
0x180008d30  xor     edx, edx; Val
0x180008d32  lea     r8d, [rdx+48h]; Size
0x180008d36  lea     rcx, [rsp+1128h+var_10B8]; void *
0x180008d3b  call    memset_0
0x180008d40  xor     edi, edi
0x180008d42  mov     [rsp+1128h+var_10D0], rdi
0x180008d47  call    cs:__imp_GetCurrentThreadId
0x180008d4e  nop     dword ptr [rax+rax+00h]
0x180008d53  mov     ebx, eax
0x180008d55  shl     rbx, 20h
0x180008d59  call    cs:__imp_GetTickCount
0x180008d60  nop     dword ptr [rax+rax+00h]
0x180008d65  mov     r13d, eax
0x180008d68  or      r13, rbx
0x180008d6b  mov     [rsp+1128h+var_10C8], r13
0x180008d70  cmp     cs:Microsoft_Windows_EapHostEnableBits, dil
0x180008d77  jge     short loc_180008DBB
0x180008d79  mov     [rsp+1128h+var_10E0], r13
0x180008d7e  lea     rax, [rsp+1128h+var_10E0]
0x180008d83  mov     [rsp+1128h+var_1058], rax
0x180008d8b  mov     [rsp+1128h+var_1050], 8
0x180008d97  lea     rax, [rsp+1128h+var_1068]
0x180008d9f  mov     [rsp+1128h+lpBuffer], rax
0x180008da4  lea     r9d, [rdi+2]
0x180008da8  lea     rdx, GetResultStart
0x180008daf  lea     rcx, eaphost_Context
0x180008db6  call    McGenEventWrite_EtwEventWriteTransfer
0x180008dbb  lea     rdx, DebugInfoEvent
0x180008dc2  mov     rcx, cs:eaphost_Context
0x180008dc9  call    cs:__imp_EtwEventEnabled
0x180008dd0  nop     dword ptr [rax+rax+00h]
0x180008dd5  test    al, al
0x180008dd7  jz      loc_180008E6A
0x180008ddd  mov     dword ptr [rsp+1128h+lpBuffer], esi
0x180008de1  mov     r9d, r15d
0x180008de4  lea     r8, aEaphostpeerget_17; "EapHostPeerGetResult Entry:\n Session(%"...
0x180008deb  mov     edx, 800h; unsigned __int64
0x180008df0  lea     rcx, [rsp+1128h+var_1048]; char *
0x180008df8  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180008dfd  test    eax, eax
0x180008dff  js      short loc_180008E6A
0x180008e01  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180008e05  cmp     cs:Microsoft_Windows_EapHostEnableBits, dil
0x180008e0c  jge     short loc_180008E6E
0x180008e0e  lea     rcx, [rsp+1128h+var_1048]
0x180008e16  mov     rax, rsi
0x180008e19  inc     rax
0x180008e1c  cmp     [rcx+rax], dil
0x180008e20  jnz     short loc_180008E19
0x180008e22  inc     eax
0x180008e24  lea     rcx, [rsp+1128h+var_1048]
0x180008e2c  mov     [rsp+1128h+var_1058], rcx
0x180008e34  mov     dword ptr [rsp+1128h+var_1050], eax
0x180008e3b  mov     dword ptr [rsp+1128h+var_1050+4], edi
0x180008e42  lea     rax, [rsp+1128h+var_1068]
0x180008e4a  mov     [rsp+1128h+lpBuffer], rax
0x180008e4f  mov     r9d, 2
0x180008e55  lea     rdx, DebugInfoEvent
0x180008e5c  lea     rcx, eaphost_Context
0x180008e63  call    McGenEventWrite_EtwEventWriteTransfer
0x180008e68  jmp     short loc_180008E6E
0x180008e6a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180008e6e  lea     r14, WPP_GLOBAL_Control
0x180008e75  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e7c  cmp     rcx, r14
0x180008e7f  jz      short loc_180008EA0
0x180008e81  test    byte ptr [rcx+1Ch], 4
0x180008e85  jz      short loc_180008EA0
0x180008e87  mov     edx, 22h ; '"'
0x180008e8c  mov     eax, dword ptr [rsp+1128h+var_10E8]
0x180008e90  mov     dword ptr [rsp+1128h+lpBuffer], eax
0x180008e94  mov     r9d, r15d
0x180008e97  mov     rcx, [rcx+10h]
0x180008e9b  call    WPP_SF_Dd
0x180008ea0  mov     [rsp+1128h+var_10E0], rdi
0x180008ea5  test    r15d, r15d
0x180008ea8  jnz     short loc_180008EB4
0x180008eaa  mov     ebx, 0A0h
0x180008eaf  jmp     loc_180009059
0x180008eb4  mov     dword ptr [rsp+1128h+lpBuffer], edi
0x180008eb8  lea     r9, [rsp+1128h+var_10D0]
0x180008ebd  lea     r8, [rsp+1128h+var_10E0]
0x180008ec2  mov     edx, r15d
0x180008ec5  call    ?FindSessionFreeBuffers@PeerProxy@Peer@EapHost@@QEAAKKAEAPEAVConnectionSessionInfo@23@AEAV?$CComPtr@UIEapHostPeerSessionApis@@@ATL@@H@Z; EapHost::Peer::PeerProxy::FindSessionFreeBuffers(ulong,EapHost::Peer::ConnectionSessionInfo * &,ATL::CComPtr<IEapHostPeerSessionApis> &,int)
0x180008eca  mov     ebx, eax
0x180008ecc  test    eax, eax
0x180008ece  jnz     loc_180009059
0x180008ed4  test    r12, r12
0x180008ed7  jz      short loc_180008EAA
0x180008ed9  mov     rbx, [rsp+1128h+var_10C0]
0x180008ede  test    rbx, rbx
0x180008ee1  jz      short loc_180008EE6
0x180008ee3  mov     [rbx], rdi
0x180008ee6  xor     edx, edx; Val
0x180008ee8  lea     r8d, [rdx+48h]; Size
0x180008eec  lea     rcx, [rsp+1128h+var_10B8]; void *
0x180008ef1  call    memset_0
0x180008ef6  xor     edx, edx; Val
0x180008ef8  lea     r8d, [rdx+48h]; Size
0x180008efc  mov     rcx, r12; void *
0x180008eff  call    memset_0
0x180008f04  mov     rcx, [rsp+1128h+var_10D0]
0x180008f09  mov     rax, [rcx]
0x180008f0c  mov     [rsp+1128h+lpBuffer], rbx
0x180008f11  lea     r9, [rsp+1128h+var_10B8]
0x180008f16  mov     r8d, dword ptr [rsp+1128h+var_10E8]
0x180008f1b  mov     edx, r15d
0x180008f1e  mov     rax, [rax+30h]
0x180008f22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f27  mov     ebx, eax
0x180008f29  test    eax, eax
0x180008f2b  js      loc_180009059
0x180008f31  mov     ecx, 58h ; 'X'; dwBytes
0x180008f36  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008f3b  mov     r14, rax
0x180008f3e  test    rax, rax
0x180008f41  jz      short loc_180008FB8
0x180008f43  mov     [rax+8], edi
0x180008f46  lea     rax, ??_7PeerMethodResultBuffer@EapHost@@6B@; const EapHost::PeerMethodResultBuffer::`vftable'
0x180008f4d  mov     [r14], rax
0x180008f50  lea     rax, [r14+10h]
0x180008f54  test    rax, rax
0x180008f57  jz      short loc_180008F95
0x180008f59  movaps  xmm0, [rsp+1128h+var_10B8]
0x180008f5e  movups  xmmword ptr [rax], xmm0
0x180008f61  movaps  xmm1, [rsp+1128h+var_10A8]
0x180008f69  movups  xmmword ptr [rax+10h], xmm1
0x180008f6d  movaps  xmm0, [rsp+1128h+var_1098]
0x180008f75  movups  xmmword ptr [rax+20h], xmm0
0x180008f79  movaps  xmm1, [rsp+1128h+var_1088]
0x180008f81  movups  xmmword ptr [rax+30h], xmm1
0x180008f85  movsd   xmm0, [rsp+1128h+var_1078]
0x180008f8e  movsd   qword ptr [rax+40h], xmm0
0x180008f93  jmp     short loc_180008FAC
0x180008f95  call    cs:__imp__o__errno
0x180008f9c  nop     dword ptr [rax+rax+00h]
0x180008fa1  mov     dword ptr [rax], 16h
0x180008fa7  call    _invalid_parameter_noinfo
0x180008fac  mov     [rsp+1128h+var_10E8], r14
0x180008fb1  lock inc dword ptr [r14+8]
0x180008fb6  jmp     short loc_180008FBD
0x180008fb8  mov     [rsp+1128h+var_10E8], rdi
0x180008fbd  lea     rdx, [rsp+1128h+var_10E8]
0x180008fc2  mov     rcx, [rsp+1128h+var_10E0]
0x180008fc7  call    ?AddBuffer@ConnectionSessionInfo@Peer@EapHost@@QEAAXAEBV?$SmartPointer@VReferenceCounted@@@@@Z; EapHost::Peer::ConnectionSessionInfo::AddBuffer(SmartPointer<ReferenceCounted> const &)
0x180008fcc  nop
0x180008fcd  mov     rcx, [rsp+1128h+var_10E8]
0x180008fd2  test    rcx, rcx
0x180008fd5  jz      short loc_180008FF8
0x180008fd7  mov     eax, esi
0x180008fd9  lock xadd [rcx+8], eax
0x180008fde  add     eax, esi
0x180008fe0  jnz     short loc_180008FF8
0x180008fe2  test    rcx, rcx
0x180008fe5  jz      short loc_180008FF8
0x180008fe7  mov     rax, [rcx]
0x180008fea  mov     edx, 1
0x180008fef  mov     rax, [rax]
0x180008ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ff7  nop
0x180008ff8  movaps  xmm0, [rsp+1128h+var_10B8]
0x180008ffd  movups  xmmword ptr [r12], xmm0
0x180009002  movaps  xmm1, [rsp+1128h+var_10A8]
0x18000900a  movups  xmmword ptr [r12+10h], xmm1
0x180009010  movaps  xmm0, [rsp+1128h+var_1098]
0x180009018  movups  xmmword ptr [r12+20h], xmm0
0x18000901e  movaps  xmm1, [rsp+1128h+var_1088]
0x180009026  movups  xmmword ptr [r12+30h], xmm1
0x18000902c  movsd   xmm0, [rsp+1128h+var_1078]
0x180009035  movsd   qword ptr [r12+40h], xmm0
0x18000903c  jmp     short loc_180009052
0x18000903e  xor     edi, edi
0x180009040  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180009044  mov     ebx, dword ptr [rsp+1128h+var_10E8]
0x180009048  mov     r15d, [rsp+1128h+var_10D8]
0x18000904d  mov     r13, [rsp+1128h+var_10C8]
0x180009052  lea     r14, WPP_GLOBAL_Control
0x180009059  mov     [rsp+1128h+Arguments], rdi; Arguments
0x18000905e  mov     dword ptr [rsp+1128h+nSize], 400h; nSize
0x180009066  lea     rax, [rsp+1128h+Buffer]
0x18000906e  mov     [rsp+1128h+lpBuffer], rax; lpBuffer
0x180009073  xor     r9d, r9d; dwLanguageId
0x180009076  mov     r8d, ebx; dwMessageId
0x180009079  xor     edx, edx; lpSource
0x18000907b  mov     ecx, 1200h; dwFlags
0x180009080  call    cs:__imp_FormatMessageW
0x180009087  nop     dword ptr [rax+rax+00h]
0x18000908c  lea     rdx, DebugInfoEvent
0x180009093  mov     rcx, cs:eaphost_Context
0x18000909a  call    cs:__imp_EtwEventEnabled
0x1800090a1  nop     dword ptr [rax+rax+00h]
0x1800090a6  test    al, al
0x1800090a8  jz      loc_180009149
0x1800090ae  mov     eax, dword ptr [rsp+1128h+var_10B8+4]
0x1800090b2  mov     dword ptr [rsp+1128h+Arguments], eax
0x1800090b6  mov     eax, dword ptr [rsp+1128h+var_10B8]
0x1800090ba  mov     dword ptr [rsp+1128h+nSize], eax
0x1800090be  mov     dword ptr [rsp+1128h+lpBuffer], r15d
0x1800090c3  lea     r9, [rsp+1128h+Buffer]
0x1800090cb  lea     r8, aEaphostpeerget_10; "EapHostPeerGetResult Exit:\n %ws\n Retu"...
0x1800090d2  mov     edx, 800h; unsigned __int64
0x1800090d7  lea     rcx, [rsp+1128h+var_1048]; char *
0x1800090df  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800090e4  test    eax, eax
0x1800090e6  js      short loc_180009149
0x1800090e8  cmp     cs:Microsoft_Windows_EapHostEnableBits, dil
0x1800090ef  jge     short loc_180009149
0x1800090f1  lea     rax, [rsp+1128h+var_1048]
0x1800090f9  inc     rsi
0x1800090fc  cmp     [rax+rsi], dil
0x180009100  jnz     short loc_1800090F9
0x180009102  lea     eax, [rsi+1]
0x180009105  lea     rcx, [rsp+1128h+var_1048]
0x18000910d  mov     [rsp+1128h+var_1058], rcx
0x180009115  mov     dword ptr [rsp+1128h+var_1050], eax
0x18000911c  mov     dword ptr [rsp+1128h+var_1050+4], edi
0x180009123  lea     rax, [rsp+1128h+var_1068]
0x18000912b  mov     [rsp+1128h+lpBuffer], rax
0x180009130  mov     r9d, 2
0x180009136  lea     rdx, DebugInfoEvent
0x18000913d  lea     rcx, eaphost_Context
0x180009144  call    McGenEventWrite_EtwEventWriteTransfer
0x180009149  mov     rcx, cs:WPP_GLOBAL_Control
0x180009150  cmp     rcx, r14
0x180009153  jz      short loc_18000917C
0x180009155  test    byte ptr [rcx+1Ch], 4
0x180009159  jz      short loc_18000917C
0x18000915b  mov     eax, dword ptr [rsp+1128h+var_10B8+4]
0x18000915f  mov     dword ptr [rsp+1128h+Arguments], eax
0x180009163  mov     eax, dword ptr [rsp+1128h+var_10B8]
0x180009167  mov     dword ptr [rsp+1128h+nSize], eax
0x18000916b  mov     dword ptr [rsp+1128h+lpBuffer], r15d
0x180009170  mov     r9d, ebx
0x180009173  mov     rcx, [rcx+10h]
0x180009177  call    WPP_SF_Dddd
0x18000917c  mov     rcx, [rsp+1128h+var_10E0]
0x180009181  test    rcx, rcx
0x180009184  jz      short loc_180009194
0x180009186  mov     eax, [rcx+0ACh]
0x18000918c  lock cmpxchg [rcx+0ACh], edi
0x180009194  cmp     cs:Microsoft_Windows_EapHostEnableBits, dil
0x18000919b  jge     short loc_1800091E2
0x18000919d  mov     [rsp+1128h+var_10C8], r13
0x1800091a2  lea     rax, [rsp+1128h+var_10C8]
0x1800091a7  mov     [rsp+1128h+var_1058], rax
0x1800091af  mov     [rsp+1128h+var_1050], 8
0x1800091bb  lea     rax, [rsp+1128h+var_1068]
0x1800091c3  mov     [rsp+1128h+lpBuffer], rax
0x1800091c8  mov     r9d, 2
0x1800091ce  lea     rdx, GetResultEnd
0x1800091d5  lea     rcx, eaphost_Context
0x1800091dc  call    McGenEventWrite_EtwEventWriteTransfer
0x1800091e1  nop
0x1800091e2  mov     rcx, [rsp+1128h+var_10D0]
0x1800091e7  test    rcx, rcx
0x1800091ea  jz      short loc_1800091F9
0x1800091ec  mov     rax, [rcx]
0x1800091ef  mov     rax, [rax+10h]
0x1800091f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091f8  nop
0x1800091f9  mov     eax, ebx
0x1800091fb  mov     rcx, [rsp+1128h+var_48]
0x180009203  xor     rcx, rsp; StackCookie
0x180009206  call    __security_check_cookie
0x18000920b  add     rsp, 10F0h
0x180009212  pop     r15
0x180009214  pop     r14
0x180009216  pop     r13
0x180009218  pop     r12
0x18000921a  pop     rdi
0x18000921b  pop     rsi
0x18000921c  pop     rbx
0x18000921d  retn
```
