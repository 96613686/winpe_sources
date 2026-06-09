# EapHost::Peer::ConnectionSessionInfo::CreateInstance(EapHost::Peer::ConnectionSessionInfoPtr &,ulong)

- ea: `0x18000bac0`
- end: `0x18000bd2a`
- name: `?CreateInstance@ConnectionSessionInfo@Peer@EapHost@@SAJAEAVConnectionSessionInfoPtr@23@K@Z`
- size: `618`
- prototype: `static int(struct EapHost::Peer::ConnectionSessionInfoPtr *, unsigned int)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006100`
- `0x180007d40`
- `0x1800080c0`

## callees

- `0x180001780`
- `0x1800030f8`
- `0x18000ace0`
- `0x18000ade4`
- `0x18000bac0`
- `0x18000c6e0`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000bc56`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000bc56`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000bbc4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000bbf6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000bbc4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000bbf6`

## string_xrefs

- `0x18000bc6b`: `CoCreateInstance(IEapHostPeerSessionApis)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EapHost::Peer::ConnectionSessionInfo::CreateInstance(
        EapHost::Peer::ConnectionSessionInfo **a1,
        DWORD a2)
{
  char *v4; // rax
  char *v5; // rbx
  _QWORD *v6; // rax
  HRESULT Instance; // edi
  int v8; // r8d
  __int64 v9; // rax
  char v11[16]; // [rsp+40h] [rbp-858h] BYREF
  const char *v12; // [rsp+50h] [rbp-848h]
  __int64 v13; // [rsp+58h] [rbp-840h]
  WCHAR *v14; // [rsp+60h] [rbp-838h]
  int v15; // [rsp+68h] [rbp-830h]
  int v16; // [rsp+6Ch] [rbp-82Ch]
  WCHAR Buffer[1024]; // [rsp+70h] [rbp-828h] BYREF

  v4 = (char *)operator new(0xC8u);
  v5 = v4;
  if ( v4 )
  {
    *(_DWORD *)v4 = 0;
    *(GUID *)(v4 + 4) = GUID_NULL;
    *((_QWORD *)v4 + 13) = &ObjectHandle::`vftable';
    *((_QWORD *)v4 + 14) = 0;
    *((_QWORD *)v4 + 15) = &ObjectHandle::`vftable';
    *((_QWORD *)v4 + 16) = 0;
    *((_QWORD *)v4 + 17) = 0;
    *((_QWORD *)v4 + 18) = 0;
    *((_QWORD *)v4 + 19) = 0;
    *((_QWORD *)v4 + 20) = 0;
    v6 = operator new(0x18u);
    *v6 = v6;
    v6[1] = v6;
    *((_QWORD *)v5 + 19) = v6;
    *((_DWORD *)v5 + 42) = 1;
    *((_DWORD *)v5 + 43) = 1;
    *((_QWORD *)v5 + 22) = 0;
    *((_QWORD *)v5 + 23) = 0;
    *((_DWORD *)v5 + 48) = a2;
    *((_DWORD *)v5 + 49) = 0;
    *((_WORD *)v5 + 10) = 0;
  }
  else
  {
    v5 = 0;
  }
  if ( *a1 )
    EapHost::Peer::ConnectionSessionInfo::ReduceRefCount(*a1);
  *a1 = (EapHost::Peer::ConnectionSessionInfo *)v5;
  Instance = CoCreateInstance(
               &GUID_8c482dce_2644_4419_aeff_189219f916b9,
               0,
               a2,
               &GUID_09dbbc77_588f_4517_a485_74a29759f54c,
               (LPVOID *)v5 + 22);
  if ( Instance < 0
    || (Instance = CoCreateInstance(
                     &CLSID_StdGlobalInterfaceTable,
                     0,
                     1u,
                     &GUID_00000146_0000_0000_c000_000000000046,
                     (LPVOID *)v5 + 23),
        Instance < 0)
    || (Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, char *))(**((_QWORD **)v5 + 23) + 24LL))(
                     *((_QWORD *)v5 + 23),
                     *((_QWORD *)v5 + 22),
                     &GUID_09dbbc77_588f_4517_a485_74a29759f54c,
                     v5 + 196),
        Instance < 0) )
  {
    FormatMessageW(0x1200u, 0, Instance, 0, Buffer, 0x400u, 0);
    if ( (Microsoft_Windows_EapHostEnableBits & 0x10) != 0 )
    {
      v12 = "CoCreateInstance(IEapHostPeerSessionApis)";
      v13 = 42;
      v9 = -1;
      do
        ++v9;
      while ( Buffer[v9] );
      v14 = Buffer;
      v15 = 2 * v9 + 2;
      v16 = 0;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&eaphost_Context,
        (unsigned int)PeerCOMAPIFailure,
        v8,
        3,
        (__int64)v11);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids,
        (unsigned int)Instance);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000bac0  mov     [rsp+arg_10], rbx
0x18000bac5  mov     [rsp+arg_18], rbp
0x18000baca  push    rsi
0x18000bacb  push    rdi
0x18000bacc  push    r14
0x18000bace  sub     rsp, 880h
0x18000bad5  mov     rax, cs:__security_cookie
0x18000badc  xor     rax, rsp
0x18000badf  mov     [rsp+898h+var_28], rax
0x18000bae7  mov     esi, edx
0x18000bae9  mov     rdi, rcx
0x18000baec  mov     ecx, 0C8h; dwBytes
0x18000baf1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000baf6  mov     rbx, rax
0x18000baf9  xor     ebp, ebp
0x18000bafb  test    rax, rax
0x18000bafe  jz      loc_18000BB92
0x18000bb04  mov     [rax], ebp
0x18000bb06  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000bb0d  movdqu  xmmword ptr [rax+4], xmm0
0x18000bb12  lea     rax, ??_7ObjectHandle@@6B@; const ObjectHandle::`vftable'
0x18000bb19  mov     [rbx+68h], rax
0x18000bb1d  mov     [rbx+70h], rbp
0x18000bb21  mov     [rbx+78h], rax
0x18000bb25  mov     [rbx+80h], rbp
0x18000bb2c  mov     [rbx+88h], rbp
0x18000bb33  mov     [rbx+90h], rbp
0x18000bb3a  mov     [rbx+98h], rbp
0x18000bb41  mov     [rbx+0A0h], rbp
0x18000bb48  lea     ecx, [rbp+18h]; dwBytes
0x18000bb4b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bb50  mov     [rax], rax
0x18000bb53  mov     [rax+8], rax
0x18000bb57  mov     [rbx+98h], rax
0x18000bb5e  mov     dword ptr [rbx+0A8h], 1
0x18000bb68  mov     dword ptr [rbx+0ACh], 1
0x18000bb72  mov     [rbx+0B0h], rbp
0x18000bb79  mov     [rbx+0B8h], rbp
0x18000bb80  mov     [rbx+0C0h], esi
0x18000bb86  mov     [rbx+0C4h], ebp
0x18000bb8c  mov     [rbx+14h], bp
0x18000bb90  jmp     short loc_18000BB95
0x18000bb92  mov     rbx, rbp
0x18000bb95  mov     rcx, [rdi]; this
0x18000bb98  test    rcx, rcx
0x18000bb9b  jz      short loc_18000BBA2
0x18000bb9d  call    ?ReduceRefCount@ConnectionSessionInfo@Peer@EapHost@@QEAAXXZ; EapHost::Peer::ConnectionSessionInfo::ReduceRefCount(void)
0x18000bba2  mov     [rdi], rbx
0x18000bba5  lea     r14, [rbx+0B0h]
0x18000bbac  mov     [rsp+898h+ppv], r14; ppv
0x18000bbb1  lea     r9, _GUID_09dbbc77_588f_4517_a485_74a29759f54c; riid
0x18000bbb8  mov     r8d, esi; dwClsContext
0x18000bbbb  xor     edx, edx; pUnkOuter
0x18000bbbd  lea     rcx, _GUID_8c482dce_2644_4419_aeff_189219f916b9; rclsid
0x18000bbc4  call    cs:__imp_CoCreateInstance
0x18000bbcb  nop     dword ptr [rax+rax+00h]
0x18000bbd0  mov     edi, eax
0x18000bbd2  test    eax, eax
0x18000bbd4  js      short loc_18000BC32
0x18000bbd6  lea     rsi, [rbx+0B8h]
0x18000bbdd  mov     [rsp+898h+ppv], rsi; ppv
0x18000bbe2  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000bbe9  xor     edx, edx; pUnkOuter
0x18000bbeb  lea     r8d, [rdx+1]; dwClsContext
0x18000bbef  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000bbf6  call    cs:__imp_CoCreateInstance
0x18000bbfd  nop     dword ptr [rax+rax+00h]
0x18000bc02  mov     edi, eax
0x18000bc04  test    eax, eax
0x18000bc06  js      short loc_18000BC32
0x18000bc08  mov     rcx, [rsi]
0x18000bc0b  mov     rax, [rcx]
0x18000bc0e  lea     r9, [rbx+0C4h]
0x18000bc15  lea     r8, _GUID_09dbbc77_588f_4517_a485_74a29759f54c
0x18000bc1c  mov     rdx, [r14]
0x18000bc1f  mov     rax, [rax+18h]
0x18000bc23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc28  mov     edi, eax
0x18000bc2a  test    eax, eax
0x18000bc2c  jns     loc_18000BCFF
0x18000bc32  mov     [rsp+898h+Arguments], rbp; Arguments
0x18000bc37  mov     [rsp+898h+nSize], 400h; nSize
0x18000bc3f  lea     rax, [rsp+898h+Buffer]
0x18000bc44  mov     [rsp+898h+ppv], rax; lpBuffer
0x18000bc49  xor     r9d, r9d; dwLanguageId
0x18000bc4c  mov     r8d, edi; dwMessageId
0x18000bc4f  xor     edx, edx; lpSource
0x18000bc51  mov     ecx, 1200h; dwFlags
0x18000bc56  call    cs:__imp_FormatMessageW
0x18000bc5d  nop     dword ptr [rax+rax+00h]
0x18000bc62  test    cs:Microsoft_Windows_EapHostEnableBits, 10h
0x18000bc69  jz      short loc_18000BCCE
0x18000bc6b  lea     rax, aCocreateinstan_0; "CoCreateInstance(IEapHostPeerSessionApi"...
0x18000bc72  mov     [rsp+898h+var_848], rax
0x18000bc77  mov     [rsp+898h+var_840], 2Ah ; '*'
0x18000bc80  lea     rcx, [rsp+898h+Buffer]
0x18000bc85  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000bc89  inc     rax
0x18000bc8c  cmp     [rcx+rax*2], bp
0x18000bc90  jnz     short loc_18000BC89
0x18000bc92  lea     eax, ds:2[rax*2]
0x18000bc99  lea     rcx, [rsp+898h+Buffer]
0x18000bc9e  mov     [rsp+898h+var_838], rcx
0x18000bca3  mov     [rsp+898h+var_830], eax
0x18000bca7  mov     [rsp+898h+var_82C], ebp
0x18000bcab  lea     rax, [rsp+898h+var_858]
0x18000bcb0  mov     [rsp+898h+ppv], rax
0x18000bcb5  mov     r9d, 3
0x18000bcbb  lea     rdx, PeerCOMAPIFailure
0x18000bcc2  lea     rcx, eaphost_Context
0x18000bcc9  call    McGenEventWrite_EtwEventWriteTransfer
0x18000bcce  lea     rax, WPP_GLOBAL_Control
0x18000bcd5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bcdc  cmp     rcx, rax
0x18000bcdf  jz      short loc_18000BCFF
0x18000bce1  test    byte ptr [rcx+1Ch], 1
0x18000bce5  jz      short loc_18000BCFF
0x18000bce7  mov     edx, 0Bh
0x18000bcec  mov     r9d, edi
0x18000bcef  lea     r8, WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids
0x18000bcf6  mov     rcx, [rcx+10h]
0x18000bcfa  call    WPP_SF_d
0x18000bcff  mov     eax, edi
0x18000bd01  mov     rcx, [rsp+898h+var_28]
0x18000bd09  xor     rcx, rsp; StackCookie
0x18000bd0c  call    __security_check_cookie
0x18000bd11  lea     r11, [rsp+898h+var_18]
0x18000bd19  mov     rbx, [r11+30h]
0x18000bd1d  mov     rbp, [r11+38h]
0x18000bd21  mov     rsp, r11
0x18000bd24  pop     r14
0x18000bd26  pop     rdi
0x18000bd27  pop     rsi
0x18000bd28  retn
```
