# CDynamicDeviceTestServer::Initialize(IMsRdpDeviceCollection *)

- ea: `0x1400597f4`
- end: `0x140059ac5`
- name: `?Initialize@CDynamicDeviceTestServer@@QEAAJPEAUIMsRdpDeviceCollection@@@Z`
- size: `721`
- prototype: `__int64 __fastcall(CDynamicDeviceTestServer *__hidden this, struct IMsRdpDeviceCollection *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140059610`

## callees

- `0x140008a78`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000d078`
- `0x1400597f4`
- `0x140059acc`
- `0x140111220`
- `0x140112010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x140059971`
- `KERNEL32!GetCurrentProcessId` at `0x140059971`
- `ole32!CreateItemMoniker` at `0x1400599a1`
- `ole32!CreateItemMoniker` at `0x1400599a1`
- `ole32!GetRunningObjectTable` at `0x140059927`
- `ole32!GetRunningObjectTable` at `0x140059927`

## string_xrefs

- `0x1400599e2`: `CreateItemMoniker failed`

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
0x1400597f4  mov     [rsp-8+arg_10], rbx
0x1400597f9  mov     [rsp-8+arg_18], rdi
0x1400597fe  push    rbp
0x1400597ff  lea     rbp, [rsp-160h]
0x140059807  sub     rsp, 260h
0x14005980e  mov     rax, cs:__security_cookie
0x140059815  xor     rax, rsp
0x140059818  mov     [rbp+160h+var_10], rax
0x14005981f  mov     rdi, rcx
0x140059822  mov     [rsp+260h+pprot], 0
0x14005982b  add     rcx, 50h ; 'P'; this
0x14005982f  mov     [rsp+260h+ppmk], 0
0x140059838  mov     rbx, rdx
0x14005983b  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x140059840  test    eax, eax
0x140059842  jnz     short loc_14005989D
0x140059844  mov     ebx, 8007000Eh
0x140059849  mov     rcx, cs:WPP_GLOBAL_Control
0x140059850  lea     rax, WPP_GLOBAL_Control
0x140059857  cmp     rcx, rax
0x14005985a  jz      loc_140059A61
0x140059860  test    byte ptr [rcx+1Ch], 1
0x140059864  jz      loc_140059A61
0x14005986a  cmp     byte ptr [rcx+19h], 2
0x14005986e  jb      loc_140059A61
0x140059874  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140059879  mov     rcx, cs:WPP_GLOBAL_Control
0x140059880  lea     r8, WPP_f6ab6a5f89e336dc914ea21753f452a6_Traceguids
0x140059887  mov     edx, 0Ch
0x14005988c  mov     r9d, eax
0x14005988f  mov     rcx, [rcx+10h]
0x140059893  call    WPP_SF_d
0x140059898  jmp     loc_140059A61
0x14005989d  mov     rax, [rbx]
0x1400598a0  lea     r8, [rdi+40h]
0x1400598a4  lea     rdx, IID_IMsRdpDeviceCollection2
0x1400598ab  mov     rcx, rbx
0x1400598ae  mov     rax, [rax]
0x1400598b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400598b6  mov     ebx, eax
0x1400598b8  test    eax, eax
0x1400598ba  jns     short loc_140059920
0x1400598bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400598c3  lea     rax, WPP_GLOBAL_Control
0x1400598ca  cmp     rcx, rax
0x1400598cd  jz      loc_140059A61
0x1400598d3  test    byte ptr [rcx+1Ch], 8
0x1400598d7  jz      loc_140059A61
0x1400598dd  cmp     byte ptr [rcx+19h], 2
0x1400598e1  jb      loc_140059A61
0x1400598e7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400598ec  mov     edx, 0Dh
0x1400598f1  lea     rcx, aQiImsrdpdevice; "QI(IMsRdpDeviceCollection2)"
0x1400598f8  mov     [rsp+260h+var_238], ebx
0x1400598fc  lea     r8, WPP_f6ab6a5f89e336dc914ea21753f452a6_Traceguids
0x140059903  mov     [rsp+260h+var_240], rcx
0x140059908  mov     r9d, eax
0x14005990b  mov     rcx, cs:WPP_GLOBAL_Control
0x140059912  mov     rcx, [rcx+10h]
0x140059916  call    WPP_SF_DsD
0x14005991b  jmp     loc_140059A61
0x140059920  lea     rdx, [rsp+260h+pprot]; pprot
0x140059925  xor     ecx, ecx; reserved
0x140059927  call    cs:__imp_GetRunningObjectTable
0x14005992d  mov     ebx, eax
0x14005992f  test    eax, eax
0x140059931  jns     short loc_140059971
0x140059933  mov     rcx, cs:WPP_GLOBAL_Control
0x14005993a  lea     rax, WPP_GLOBAL_Control
0x140059941  cmp     rcx, rax
0x140059944  jz      loc_140059A61
0x14005994a  test    byte ptr [rcx+1Ch], 8
0x14005994e  jz      loc_140059A61
0x140059954  cmp     byte ptr [rcx+19h], 2
0x140059958  jb      loc_140059A61
0x14005995e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140059963  mov     edx, 0Eh
0x140059968  lea     rcx, aGetrunningobje_0; "GetRunningObjectTable"
0x14005996f  jmp     short loc_1400598F8
0x140059971  call    cs:__imp_GetCurrentProcessId
0x140059977  lea     r8, aDynusbD; "dynusb:%d"
0x14005997e  mov     edx, 104h; unsigned __int64
0x140059983  mov     r9d, eax
0x140059986  lea     rcx, [rsp+260h+szItem]; unsigned __int16 *
0x14005998b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140059990  lea     r8, [rsp+260h+ppmk]; ppmk
0x140059995  lea     rdx, [rsp+260h+szItem]; lpszItem
0x14005999a  lea     rcx, szDelim; "!"
0x1400599a1  call    cs:__imp_CreateItemMoniker
0x1400599a7  mov     ebx, eax
0x1400599a9  test    eax, eax
0x1400599ab  jns     short loc_1400599EE
0x1400599ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400599b4  lea     rax, WPP_GLOBAL_Control
0x1400599bb  cmp     rcx, rax
0x1400599be  jz      loc_140059A61
0x1400599c4  test    byte ptr [rcx+1Ch], 8
0x1400599c8  jz      loc_140059A61
0x1400599ce  cmp     byte ptr [rcx+19h], 2
0x1400599d2  jb      loc_140059A61
0x1400599d8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400599dd  mov     edx, 0Fh
0x1400599e2  lea     rcx, aCreateitemmoni_0; "CreateItemMoniker failed"
0x1400599e9  jmp     loc_1400598F8
0x1400599ee  mov     rcx, [rsp+260h+pprot]
0x1400599f3  lea     rdx, [rdi+8]
0x1400599f7  mov     r9, [rsp+260h+ppmk]
0x1400599fc  lea     r11, [rdi+4Ch]
0x140059a00  mov     rax, rdi
0x140059a03  mov     [rsp+260h+var_240], r11
0x140059a08  neg     rax
0x140059a0b  mov     r10, [rcx]
0x140059a0e  sbb     r8, r8
0x140059a11  and     r8, rdx
0x140059a14  xor     edx, edx
0x140059a16  mov     rax, [r10+18h]
0x140059a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059a1f  mov     ebx, eax
0x140059a21  test    eax, eax
0x140059a23  jns     short loc_140059A5A
0x140059a25  mov     rcx, cs:WPP_GLOBAL_Control
0x140059a2c  lea     rax, WPP_GLOBAL_Control
0x140059a33  cmp     rcx, rax
0x140059a36  jz      short loc_140059A61
0x140059a38  test    byte ptr [rcx+1Ch], 8
0x140059a3c  jz      short loc_140059A61
0x140059a3e  cmp     byte ptr [rcx+19h], 2
0x140059a42  jb      short loc_140059A61
0x140059a44  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140059a49  mov     edx, 10h
0x140059a4e  lea     rcx, aRotRegister; "ROT->Register"
0x140059a55  jmp     loc_1400598F8
0x140059a5a  mov     dword ptr [rdi+48h], 1
0x140059a61  mov     rcx, [rsp+260h+ppmk]
0x140059a66  test    rcx, rcx
0x140059a69  jz      short loc_140059A80
0x140059a6b  mov     [rsp+260h+ppmk], 0
0x140059a74  mov     rax, [rcx]
0x140059a77  mov     rax, [rax+10h]
0x140059a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059a80  mov     rcx, [rsp+260h+pprot]
0x140059a85  test    rcx, rcx
0x140059a88  jz      short loc_140059A9F
0x140059a8a  mov     [rsp+260h+pprot], 0
0x140059a93  mov     rax, [rcx]
0x140059a96  mov     rax, [rax+10h]
0x140059a9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059a9f  mov     eax, ebx
0x140059aa1  mov     rcx, [rbp+160h+var_10]
0x140059aa8  xor     rcx, rsp; StackCookie
0x140059aab  call    __security_check_cookie
0x140059ab0  lea     r11, [rsp+260h+var_s0]
0x140059ab8  mov     rbx, [r11+20h]
0x140059abc  mov     rdi, [r11+28h]
0x140059ac0  mov     rsp, r11
0x140059ac3  pop     rbp
0x140059ac4  retn
```
