# CDynamicDeviceTestServer::Initialize(IMsRdpDeviceCollection *)

- ea: `0x14005b964`
- end: `0x14005bc35`
- name: `?Initialize@CDynamicDeviceTestServer@@QEAAJPEAUIMsRdpDeviceCollection@@@Z`
- size: `721`
- prototype: `__int64 __fastcall(CDynamicDeviceTestServer *__hidden this, struct IMsRdpDeviceCollection *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005b780`

## callees

- `0x140008a78`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000d078`
- `0x14005b964`
- `0x14005bc3c`
- `0x140113390`
- `0x140114010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x14005bae1`
- `KERNEL32!GetCurrentProcessId` at `0x14005bae1`
- `ole32!CreateItemMoniker` at `0x14005bb11`
- `ole32!CreateItemMoniker` at `0x14005bb11`
- `ole32!GetRunningObjectTable` at `0x14005ba97`
- `ole32!GetRunningObjectTable` at `0x14005ba97`

## string_xrefs

- `0x14005bb52`: `CreateItemMoniker failed`

## pseudocode

```c
__int64 __fastcall CDynamicDeviceTestServer::Initialize(
        CDynamicDeviceTestServer *this,
        struct IMsRdpDeviceCollection *a2)
{
  HRESULT RunningObjectTable; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v6; // eax
  int v7; // edx
  const char *v8; // rcx
  DWORD CurrentProcessId; // eax
  LPMONIKER v10; // rcx
  LPRUNNINGOBJECTTABLE v11; // rcx
  LPMONIKER ppmk; // [rsp+30h] [rbp-D0h] BYREF
  LPRUNNINGOBJECTTABLE pprot; // [rsp+38h] [rbp-C8h] BYREF
  OLECHAR szItem[264]; // [rsp+40h] [rbp-C0h] BYREF

  pprot = 0;
  ppmk = 0;
  if ( !(unsigned int)CTSCriticalSection::Initialize((CDynamicDeviceTestServer *)((char *)this + 80)) )
  {
    RunningObjectTable = -2147024882;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_f6ab6a5f89e336dc914ea21753f452a6_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
    goto LABEL_28;
  }
  RunningObjectTable = (**(__int64 (__fastcall ***)(struct IMsRdpDeviceCollection *, GUID *, char *))a2)(
                         a2,
                         &IID_IMsRdpDeviceCollection2,
                         (char *)this + 64);
  if ( RunningObjectTable < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_28;
    }
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 13;
    v8 = "QI(IMsRdpDeviceCollection2)";
    goto LABEL_11;
  }
  RunningObjectTable = GetRunningObjectTable(0, &pprot);
  if ( RunningObjectTable < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_28;
    }
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 14;
    v8 = "GetRunningObjectTable";
    goto LABEL_11;
  }
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(szItem, 0x104u, L"dynusb:%d", CurrentProcessId);
  RunningObjectTable = CreateItemMoniker(L"!", szItem, &ppmk);
  if ( RunningObjectTable < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_28;
    }
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 15;
    v8 = "CreateItemMoniker failed";
LABEL_11:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      (unsigned int)WPP_f6ab6a5f89e336dc914ea21753f452a6_Traceguids,
      v6,
      (__int64)v8,
      RunningObjectTable);
    goto LABEL_28;
  }
  RunningObjectTable = ((__int64 (__fastcall *)(LPRUNNINGOBJECTTABLE, _QWORD, unsigned __int64, LPMONIKER, char *))pprot->lpVtbl->Register)(
                         pprot,
                         0,
                         ((unsigned __int64)this + 8) & -(__int64)(this != 0),
                         ppmk,
                         (char *)this + 76);
  if ( RunningObjectTable >= 0 )
  {
    *((_DWORD *)this + 18) = 1;
    goto LABEL_28;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 16;
    v8 = "ROT->Register";
    goto LABEL_11;
  }
LABEL_28:
  v10 = ppmk;
  if ( ppmk )
  {
    ppmk = 0;
    ((void (__fastcall *)(LPMONIKER))v10->lpVtbl->Release)(v10);
  }
  v11 = pprot;
  if ( pprot )
  {
    pprot = 0;
    ((void (__fastcall *)(LPRUNNINGOBJECTTABLE))v11->lpVtbl->Release)(v11);
  }
  return (unsigned int)RunningObjectTable;
}

```

## disassembly

```asm
0x14005b964  mov     [rsp-8+arg_10], rbx
0x14005b969  mov     [rsp-8+arg_18], rdi
0x14005b96e  push    rbp
0x14005b96f  lea     rbp, [rsp-160h]
0x14005b977  sub     rsp, 260h
0x14005b97e  mov     rax, cs:__security_cookie
0x14005b985  xor     rax, rsp
0x14005b988  mov     [rbp+160h+var_10], rax
0x14005b98f  mov     rdi, rcx
0x14005b992  mov     [rsp+260h+pprot], 0
0x14005b99b  add     rcx, 50h ; 'P'; this
0x14005b99f  mov     [rsp+260h+ppmk], 0
0x14005b9a8  mov     rbx, rdx
0x14005b9ab  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x14005b9b0  test    eax, eax
0x14005b9b2  jnz     short loc_14005BA0D
0x14005b9b4  mov     ebx, 8007000Eh
0x14005b9b9  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b9c0  lea     rax, WPP_GLOBAL_Control
0x14005b9c7  cmp     rcx, rax
0x14005b9ca  jz      loc_14005BBD1
0x14005b9d0  test    byte ptr [rcx+1Ch], 1
0x14005b9d4  jz      loc_14005BBD1
0x14005b9da  cmp     byte ptr [rcx+19h], 2
0x14005b9de  jb      loc_14005BBD1
0x14005b9e4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005b9e9  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b9f0  lea     r8, WPP_f6ab6a5f89e336dc914ea21753f452a6_Traceguids
0x14005b9f7  mov     edx, 0Ch
0x14005b9fc  mov     r9d, eax
0x14005b9ff  mov     rcx, [rcx+10h]
0x14005ba03  call    WPP_SF_d
0x14005ba08  jmp     loc_14005BBD1
0x14005ba0d  mov     rax, [rbx]
0x14005ba10  lea     r8, [rdi+40h]
0x14005ba14  lea     rdx, IID_IMsRdpDeviceCollection2
0x14005ba1b  mov     rcx, rbx
0x14005ba1e  mov     rax, [rax]
0x14005ba21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005ba26  mov     ebx, eax
0x14005ba28  test    eax, eax
0x14005ba2a  jns     short loc_14005BA90
0x14005ba2c  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ba33  lea     rax, WPP_GLOBAL_Control
0x14005ba3a  cmp     rcx, rax
0x14005ba3d  jz      loc_14005BBD1
0x14005ba43  test    byte ptr [rcx+1Ch], 8
0x14005ba47  jz      loc_14005BBD1
0x14005ba4d  cmp     byte ptr [rcx+19h], 2
0x14005ba51  jb      loc_14005BBD1
0x14005ba57  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005ba5c  mov     edx, 0Dh
0x14005ba61  lea     rcx, aQiImsrdpdevice; "QI(IMsRdpDeviceCollection2)"
0x14005ba68  mov     [rsp+260h+var_238], ebx
0x14005ba6c  lea     r8, WPP_f6ab6a5f89e336dc914ea21753f452a6_Traceguids
0x14005ba73  mov     [rsp+260h+var_240], rcx
0x14005ba78  mov     r9d, eax
0x14005ba7b  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ba82  mov     rcx, [rcx+10h]
0x14005ba86  call    WPP_SF_DsD
0x14005ba8b  jmp     loc_14005BBD1
0x14005ba90  lea     rdx, [rsp+260h+pprot]; pprot
0x14005ba95  xor     ecx, ecx; reserved
0x14005ba97  call    cs:__imp_GetRunningObjectTable
0x14005ba9d  mov     ebx, eax
0x14005ba9f  test    eax, eax
0x14005baa1  jns     short loc_14005BAE1
0x14005baa3  mov     rcx, cs:WPP_GLOBAL_Control
0x14005baaa  lea     rax, WPP_GLOBAL_Control
0x14005bab1  cmp     rcx, rax
0x14005bab4  jz      loc_14005BBD1
0x14005baba  test    byte ptr [rcx+1Ch], 8
0x14005babe  jz      loc_14005BBD1
0x14005bac4  cmp     byte ptr [rcx+19h], 2
0x14005bac8  jb      loc_14005BBD1
0x14005bace  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005bad3  mov     edx, 0Eh
0x14005bad8  lea     rcx, aGetrunningobje_0; "GetRunningObjectTable"
0x14005badf  jmp     short loc_14005BA68
0x14005bae1  call    cs:__imp_GetCurrentProcessId
0x14005bae7  lea     r8, aDynusbD; "dynusb:%d"
0x14005baee  mov     edx, 104h; unsigned __int64
0x14005baf3  mov     r9d, eax
0x14005baf6  lea     rcx, [rsp+260h+szItem]; unsigned __int16 *
0x14005bafb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14005bb00  lea     r8, [rsp+260h+ppmk]; ppmk
0x14005bb05  lea     rdx, [rsp+260h+szItem]; lpszItem
0x14005bb0a  lea     rcx, szDelim; "!"
0x14005bb11  call    cs:__imp_CreateItemMoniker
0x14005bb17  mov     ebx, eax
0x14005bb19  test    eax, eax
0x14005bb1b  jns     short loc_14005BB5E
0x14005bb1d  mov     rcx, cs:WPP_GLOBAL_Control
0x14005bb24  lea     rax, WPP_GLOBAL_Control
0x14005bb2b  cmp     rcx, rax
0x14005bb2e  jz      loc_14005BBD1
0x14005bb34  test    byte ptr [rcx+1Ch], 8
0x14005bb38  jz      loc_14005BBD1
0x14005bb3e  cmp     byte ptr [rcx+19h], 2
0x14005bb42  jb      loc_14005BBD1
0x14005bb48  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005bb4d  mov     edx, 0Fh
0x14005bb52  lea     rcx, aCreateitemmoni_0; "CreateItemMoniker failed"
0x14005bb59  jmp     loc_14005BA68
0x14005bb5e  mov     rcx, [rsp+260h+pprot]
0x14005bb63  lea     rdx, [rdi+8]
0x14005bb67  mov     r9, [rsp+260h+ppmk]
0x14005bb6c  lea     r11, [rdi+4Ch]
0x14005bb70  mov     rax, rdi
0x14005bb73  mov     [rsp+260h+var_240], r11
0x14005bb78  neg     rax
0x14005bb7b  mov     r10, [rcx]
0x14005bb7e  sbb     r8, r8
0x14005bb81  and     r8, rdx
0x14005bb84  xor     edx, edx
0x14005bb86  mov     rax, [r10+18h]
0x14005bb8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005bb8f  mov     ebx, eax
0x14005bb91  test    eax, eax
0x14005bb93  jns     short loc_14005BBCA
0x14005bb95  mov     rcx, cs:WPP_GLOBAL_Control
0x14005bb9c  lea     rax, WPP_GLOBAL_Control
0x14005bba3  cmp     rcx, rax
0x14005bba6  jz      short loc_14005BBD1
0x14005bba8  test    byte ptr [rcx+1Ch], 8
0x14005bbac  jz      short loc_14005BBD1
0x14005bbae  cmp     byte ptr [rcx+19h], 2
0x14005bbb2  jb      short loc_14005BBD1
0x14005bbb4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005bbb9  mov     edx, 10h
0x14005bbbe  lea     rcx, aRotRegister; "ROT->Register"
0x14005bbc5  jmp     loc_14005BA68
0x14005bbca  mov     dword ptr [rdi+48h], 1
0x14005bbd1  mov     rcx, [rsp+260h+ppmk]
0x14005bbd6  test    rcx, rcx
0x14005bbd9  jz      short loc_14005BBF0
0x14005bbdb  mov     [rsp+260h+ppmk], 0
0x14005bbe4  mov     rax, [rcx]
0x14005bbe7  mov     rax, [rax+10h]
0x14005bbeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005bbf0  mov     rcx, [rsp+260h+pprot]
0x14005bbf5  test    rcx, rcx
0x14005bbf8  jz      short loc_14005BC0F
0x14005bbfa  mov     [rsp+260h+pprot], 0
0x14005bc03  mov     rax, [rcx]
0x14005bc06  mov     rax, [rax+10h]
0x14005bc0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005bc0f  mov     eax, ebx
0x14005bc11  mov     rcx, [rbp+160h+var_10]
0x14005bc18  xor     rcx, rsp; StackCookie
0x14005bc1b  call    __security_check_cookie
0x14005bc20  lea     r11, [rsp+260h+var_s0]
0x14005bc28  mov     rbx, [r11+20h]
0x14005bc2c  mov     rdi, [r11+28h]
0x14005bc30  mov     rsp, r11
0x14005bc33  pop     rbp
0x14005bc34  retn
```
