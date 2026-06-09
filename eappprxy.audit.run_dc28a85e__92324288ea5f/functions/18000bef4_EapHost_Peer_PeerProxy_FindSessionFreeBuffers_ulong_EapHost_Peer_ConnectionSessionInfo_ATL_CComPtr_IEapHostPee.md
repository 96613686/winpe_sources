# EapHost::Peer::PeerProxy::FindSessionFreeBuffers(ulong,EapHost::Peer::ConnectionSessionInfo * &,ATL::CComPtr<IEapHostPeerSessionApis> &,int)

- ea: `0x18000bef4`
- end: `0x18000c158`
- name: `?FindSessionFreeBuffers@PeerProxy@Peer@EapHost@@QEAAKKAEAPEAVConnectionSessionInfo@23@AEAV?$CComPtr@UIEapHostPeerSessionApis@@@ATL@@H@Z`
- size: `612`
- prototype: ``
- caller_count: `10`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180006d20`
- `0x1800075c0`
- `0x180007a80`
- `0x180008850`
- `0x180008cf0`
- `0x180009230`
- `0x1800096e0`
- `0x180009e10`
- `0x18000a1b0`
- `0x18000a550`

## callees

- `0x180001780`
- `0x18000ace0`
- `0x18000ade4`
- `0x18000bef4`
- `0x18000c160`
- `0x18000c204`
- `0x18000cdfc`
- `0x18000ce34`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000c07b`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000c07b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c042`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c042`

## string_xrefs

- `0x18000c090`: `CoCreateInstance(IEapHostPeerSessionApis)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EapHost::Peer::PeerProxy::FindSessionFreeBuffers(
        __int64 a1,
        int a2,
        EapHost::Peer::ConnectionSessionInfo **a3,
        LPVOID *a4,
        int a5)
{
  volatile signed __int32 *v8; // rdi
  _QWORD *i; // rax
  _QWORD *HostApis; // rax
  void *v11; // rdi
  HRESULT Instance; // ebx
  int v13; // r8d
  __int64 v14; // rax
  __int64 v16; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+48h] [rbp-B8h]
  _BYTE v18[16]; // [rsp+50h] [rbp-B0h] BYREF
  const char *v19; // [rsp+60h] [rbp-A0h]
  __int64 v20; // [rsp+68h] [rbp-98h]
  WCHAR *v21; // [rsp+70h] [rbp-90h]
  int v22; // [rsp+78h] [rbp-88h]
  int v23; // [rsp+7Ch] [rbp-84h]
  WCHAR Buffer[1024]; // [rsp+80h] [rbp-80h] BYREF

  v8 = 0;
  v16 = 0;
  v17 = 0;
  EapNs::EapCriticalSection::AttachAndEnter((EapNs::EapCriticalSection *)&v16, &CriticalSection);
  if ( a2 )
  {
    for ( i = *(_QWORD **)peerProxy; i != (_QWORD *)peerProxy; i = (_QWORD *)*i )
    {
      if ( a2 == *(_DWORD *)i[2] )
      {
        v8 = (volatile signed __int32 *)i[2];
        break;
      }
    }
  }
  EapNs::EapCriticalSection::~EapCriticalSection((EapNs::EapCriticalSection *)&v16);
  *a3 = (EapHost::Peer::ConnectionSessionInfo *)v8;
  if ( v8 )
  {
    if ( _InterlockedCompareExchange(v8 + 43, 1, 0) )
    {
      return 1237;
    }
    else
    {
      EapHost::Peer::ConnectionSessionInfo::FreeBuffers(*a3);
      HostApis = (_QWORD *)EapHost::Peer::ConnectionSessionInfo::GetHostApis(*a3, &v16);
      v11 = (void *)*HostApis;
      if ( *a4 != (LPVOID)*HostApis && a4 )
      {
        if ( v11 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v11 + 8LL))(*HostApis);
        if ( *a4 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)*a4 + 16LL))(*a4);
        *a4 = v11;
      }
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      return *a4 == 0 ? 0x490u : 0;
    }
  }
  else if ( a5 )
  {
    Instance = CoCreateInstance(
                 &GUID_8c482dce_2644_4419_aeff_189219f916b9,
                 0,
                 HIDWORD(qword_180015528),
                 &GUID_09dbbc77_588f_4517_a485_74a29759f54c,
                 a4);
    if ( Instance < 0 )
    {
      FormatMessageW(0x1200u, 0, Instance, 0, Buffer, 0x400u, 0);
      if ( (Microsoft_Windows_EapHostEnableBits & 0x10) != 0 )
      {
        v19 = "CoCreateInstance(IEapHostPeerSessionApis)";
        v20 = 42;
        v14 = -1;
        do
          ++v14;
        while ( Buffer[v14] );
        v21 = Buffer;
        v22 = 2 * v14 + 2;
        v23 = 0;
        McGenEventWrite_EtwEventWriteTransfer(
          (unsigned int)&eaphost_Context,
          (unsigned int)PeerCOMAPIFailure,
          v13,
          3,
          (__int64)v18);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids,
          (unsigned int)Instance);
    }
  }
  else
  {
    return 1168;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000bef4  mov     [rsp-8+arg_0], rbx
0x18000bef9  push    rbp
0x18000befa  push    rsi
0x18000befb  push    rdi
0x18000befc  push    r14
0x18000befe  push    r15
0x18000bf00  lea     rbp, [rsp-790h]
0x18000bf08  sub     rsp, 890h
0x18000bf0f  mov     rax, cs:__security_cookie
0x18000bf16  xor     rax, rsp
0x18000bf19  mov     [rbp+7B0h+var_30], rax
0x18000bf20  mov     rbx, r9
0x18000bf23  mov     rsi, r8
0x18000bf26  mov     r14d, edx
0x18000bf29  xor     r15d, r15d
0x18000bf2c  mov     edi, r15d
0x18000bf2f  mov     [rsp+8B0h+var_870], r15
0x18000bf34  mov     [rsp+8B0h+var_868], r15d
0x18000bf39  lea     rdx, CriticalSection; struct _RTL_CRITICAL_SECTION *
0x18000bf40  lea     rcx, [rsp+8B0h+var_870]; this
0x18000bf45  call    ?AttachAndEnter@EapCriticalSection@EapNs@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; EapNs::EapCriticalSection::AttachAndEnter(_RTL_CRITICAL_SECTION *)
0x18000bf4a  test    r14d, r14d
0x18000bf4d  jz      short loc_18000BF6F
0x18000bf4f  mov     rdx, cs:?peerProxy@@3VPeerProxy@Peer@EapHost@@A; EapHost::Peer::PeerProxy peerProxy
0x18000bf56  mov     rax, [rdx]
0x18000bf59  cmp     rax, rdx
0x18000bf5c  jz      short loc_18000BF6F
0x18000bf5e  mov     rcx, [rax+10h]
0x18000bf62  cmp     r14d, [rcx]
0x18000bf65  jz      short loc_18000BF6C
0x18000bf67  mov     rax, [rax]
0x18000bf6a  jmp     short loc_18000BF59
0x18000bf6c  mov     rdi, rcx
0x18000bf6f  lea     rcx, [rsp+8B0h+var_870]; this
0x18000bf74  call    ??1EapCriticalSection@EapNs@@QEAA@XZ; EapNs::EapCriticalSection::~EapCriticalSection(void)
0x18000bf79  mov     [rsi], rdi
0x18000bf7c  test    rdi, rdi
0x18000bf7f  jz      loc_18000C019
0x18000bf85  mov     edx, 1
0x18000bf8a  xor     eax, eax
0x18000bf8c  lock cmpxchg [rdi+0ACh], edx
0x18000bf94  jnz     short loc_18000C00F
0x18000bf96  mov     rcx, [rsi]; this
0x18000bf99  call    ?FreeBuffers@ConnectionSessionInfo@Peer@EapHost@@QEAAXXZ; EapHost::Peer::ConnectionSessionInfo::FreeBuffers(void)
0x18000bf9e  lea     rdx, [rsp+8B0h+var_870]
0x18000bfa3  mov     rcx, [rsi]
0x18000bfa6  call    ?GetHostApis@ConnectionSessionInfo@Peer@EapHost@@QEAA?AV?$CComPtr@UIEapHostPeerSessionApis@@@ATL@@XZ; EapHost::Peer::ConnectionSessionInfo::GetHostApis(void)
0x18000bfab  mov     rdi, [rax]
0x18000bfae  cmp     [rbx], rdi
0x18000bfb1  jz      short loc_18000BFE3
0x18000bfb3  test    rbx, rbx
0x18000bfb6  jz      short loc_18000BFE3
0x18000bfb8  test    rdi, rdi
0x18000bfbb  jz      short loc_18000BFCC
0x18000bfbd  mov     rax, [rdi]
0x18000bfc0  mov     rcx, rdi
0x18000bfc3  mov     rax, [rax+8]
0x18000bfc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfcc  mov     rcx, [rbx]
0x18000bfcf  test    rcx, rcx
0x18000bfd2  jz      short loc_18000BFE0
0x18000bfd4  mov     rax, [rcx]
0x18000bfd7  mov     rax, [rax+10h]
0x18000bfdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfe0  mov     [rbx], rdi
0x18000bfe3  mov     rcx, [rsp+8B0h+var_870]
0x18000bfe8  test    rcx, rcx
0x18000bfeb  jz      short loc_18000BFFA
0x18000bfed  mov     rax, [rcx]
0x18000bff0  mov     rax, [rax+10h]
0x18000bff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bff9  nop
0x18000bffa  mov     rax, [rbx]
0x18000bffd  neg     rax
0x18000c000  sbb     ebx, ebx
0x18000c002  not     ebx
0x18000c004  and     ebx, 490h
0x18000c00a  jmp     loc_18000C12F
0x18000c00f  mov     ebx, 4D5h
0x18000c014  jmp     loc_18000C12F
0x18000c019  cmp     [rbp+7B0h+arg_20], r15d
0x18000c020  jz      loc_18000C12A
0x18000c026  mov     [rsp+8B0h+ppv], rbx; ppv
0x18000c02b  lea     r9, _GUID_09dbbc77_588f_4517_a485_74a29759f54c; riid
0x18000c032  mov     r8d, dword ptr cs:qword_180015528+4; dwClsContext
0x18000c039  xor     edx, edx; pUnkOuter
0x18000c03b  lea     rcx, _GUID_8c482dce_2644_4419_aeff_189219f916b9; rclsid
0x18000c042  call    cs:__imp_CoCreateInstance
0x18000c049  nop     dword ptr [rax+rax+00h]
0x18000c04e  mov     ebx, eax
0x18000c050  test    eax, eax
0x18000c052  jns     loc_18000C12F
0x18000c058  mov     [rsp+8B0h+Arguments], r15; Arguments
0x18000c05d  mov     [rsp+8B0h+nSize], 400h; nSize
0x18000c065  lea     rax, [rbp+7B0h+Buffer]
0x18000c069  mov     [rsp+8B0h+ppv], rax; lpBuffer
0x18000c06e  xor     r9d, r9d; dwLanguageId
0x18000c071  mov     r8d, ebx; dwMessageId
0x18000c074  xor     edx, edx; lpSource
0x18000c076  mov     ecx, 1200h; dwFlags
0x18000c07b  call    cs:__imp_FormatMessageW
0x18000c082  nop     dword ptr [rax+rax+00h]
0x18000c087  test    cs:Microsoft_Windows_EapHostEnableBits, 10h
0x18000c08e  jz      short loc_18000C0F3
0x18000c090  lea     rax, aCocreateinstan_0; "CoCreateInstance(IEapHostPeerSessionApi"...
0x18000c097  mov     [rsp+8B0h+var_850], rax
0x18000c09c  mov     [rsp+8B0h+var_848], 2Ah ; '*'
0x18000c0a5  lea     rcx, [rbp+7B0h+Buffer]
0x18000c0a9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c0ad  inc     rax
0x18000c0b0  cmp     [rcx+rax*2], r15w
0x18000c0b5  jnz     short loc_18000C0AD
0x18000c0b7  lea     eax, ds:2[rax*2]
0x18000c0be  lea     rcx, [rbp+7B0h+Buffer]
0x18000c0c2  mov     [rsp+8B0h+var_840], rcx
0x18000c0c7  mov     [rsp+8B0h+var_838], eax
0x18000c0cb  mov     [rsp+8B0h+var_834], r15d
0x18000c0d0  lea     rax, [rsp+8B0h+var_860]
0x18000c0d5  mov     [rsp+8B0h+ppv], rax
0x18000c0da  mov     r9d, 3
0x18000c0e0  lea     rdx, PeerCOMAPIFailure
0x18000c0e7  lea     rcx, eaphost_Context
0x18000c0ee  call    McGenEventWrite_EtwEventWriteTransfer
0x18000c0f3  lea     rax, WPP_GLOBAL_Control
0x18000c0fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c101  cmp     rcx, rax
0x18000c104  jz      short loc_18000C12F
0x18000c106  mov     edx, 1
0x18000c10b  test    [rcx+1Ch], dl
0x18000c10e  jz      short loc_18000C12F
0x18000c110  mov     edx, 13h
0x18000c115  mov     r9d, ebx
0x18000c118  lea     r8, WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids
0x18000c11f  mov     rcx, [rcx+10h]
0x18000c123  call    WPP_SF_d
0x18000c128  jmp     short loc_18000C12F
0x18000c12a  mov     ebx, 490h
0x18000c12f  mov     eax, ebx
0x18000c131  mov     rcx, [rbp+7B0h+var_30]
0x18000c138  xor     rcx, rsp; StackCookie
0x18000c13b  call    __security_check_cookie
0x18000c140  mov     rbx, [rsp+8B0h+arg_0]
0x18000c148  add     rsp, 890h
0x18000c14f  pop     r15
0x18000c151  pop     r14
0x18000c153  pop     rdi
0x18000c154  pop     rsi
0x18000c155  pop     rbp
0x18000c156  retn
```
