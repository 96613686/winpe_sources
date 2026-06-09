# EapHost::ECPDeviceManager::DeleteECPComponentDevice(ATL::CComPtr<IUMBusPDO> &,ATL::CComPtr<IUMBusPDO> &)

- ea: `0x180012b30`
- end: `0x180012cf1`
- name: `?DeleteECPComponentDevice@ECPDeviceManager@EapHost@@QEAAXAEAV?$CComPtr@UIUMBusPDO@@@ATL@@0@Z`
- size: `449`
- prototype: `_UNKNOWN **__fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f77c`

## callees

- `0x180001f60`
- `0x18000a5ac`
- `0x18000bbd8`
- `0x18000c150`
- `0x18000c1a8`
- `0x18000c39c`
- `0x18000c40c`
- `0x180012b30`
- `0x180017010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180012b98`
- `ntdll!EtwEventEnabled` at `0x180012c69`
- `ntdll!EtwEventEnabled` at `0x180012b98`
- `ntdll!EtwEventEnabled` at `0x180012c69`

## string_xrefs

- `0x180012c76`: `DeleteChild failed 0x%x`
- `0x180012ba2`: `ECP component device deleted`

## pseudocode

```c
_UNKNOWN **__fastcall EapHost::ECPDeviceManager::DeleteECPComponentDevice(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  unsigned int v4; // ebx
  int v5; // r8d
  int v6; // r9d
  __int64 v7; // rax
  _UNKNOWN **result; // rax
  _BYTE v9[16]; // [rsp+30h] [rbp-838h] BYREF
  char *v10; // [rsp+40h] [rbp-828h]
  int v11; // [rsp+48h] [rbp-820h]
  int v12; // [rsp+4Ch] [rbp-81Ch]
  char v13[2048]; // [rsp+50h] [rbp-818h] BYREF

  v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a2 + 104LL))(*a2, *a3);
  if ( v4 > 1 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(v13, 0x800u, "DeleteChild failed 0x%x", v4) >= 0
      && (byte_180020AC1 & 8) != 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugErrorEvent, v13);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids, v4);
    SystemError::Throw<long>((__int64)&byte_180018CBC, v4);
  }
  if ( *a3 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 16LL))(*a3);
    *a3 = 0;
  }
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v13, 0x800u, "ECP component device deleted") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v7 = -1;
    do
      ++v7;
    while ( v13[v7] );
    v12 = 0;
    v11 = v7 + 1;
    v10 = v13;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&eaphost_Context,
      (unsigned int)DebugInfoEvent,
      v5,
      v6,
      (__int64)v9);
  }
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    return (_UNKNOWN **)WPP_SF_(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          30,
                          WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids);
  return result;
}

```

## disassembly

```asm
0x180012b30  mov     [rsp+arg_0], rbx
0x180012b35  push    rdi
0x180012b36  sub     rsp, 860h
0x180012b3d  mov     rax, cs:__security_cookie
0x180012b44  xor     rax, rsp
0x180012b47  mov     [rsp+868h+var_18], rax
0x180012b4f  mov     rcx, [rdx]
0x180012b52  mov     rdi, r8
0x180012b55  mov     rdx, [r8]
0x180012b58  mov     rax, [rcx]
0x180012b5b  mov     rax, [rax+68h]
0x180012b5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b64  mov     ebx, eax
0x180012b66  cmp     eax, 1
0x180012b69  ja      loc_180012C5B
0x180012b6f  mov     rcx, [rdi]
0x180012b72  test    rcx, rcx
0x180012b75  jz      short loc_180012B8A
0x180012b77  mov     rax, [rcx]
0x180012b7a  mov     rax, [rax+10h]
0x180012b7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b83  mov     qword ptr [rdi], 0
0x180012b8a  mov     rcx, cs:eaphost_Context
0x180012b91  lea     rdx, DebugInfoEvent
0x180012b98  call    cs:__imp_EtwEventEnabled
0x180012b9e  test    al, al
0x180012ba0  jz      short loc_180012C0C
0x180012ba2  lea     r8, aEcpComponentDe_0; "ECP component device deleted"
0x180012ba9  mov     edx, 800h; unsigned __int64
0x180012bae  lea     rcx, [rsp+868h+var_818]; char *
0x180012bb3  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180012bb8  test    eax, eax
0x180012bba  js      short loc_180012C0C
0x180012bbc  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180012bc3  jge     short loc_180012C0C
0x180012bc5  lea     rcx, [rsp+868h+var_818]
0x180012bca  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012bce  inc     rax
0x180012bd1  cmp     byte ptr [rcx+rax], 0
0x180012bd5  jnz     short loc_180012BCE
0x180012bd7  inc     eax
0x180012bd9  mov     [rsp+868h+var_81C], 0
0x180012be1  lea     rcx, [rsp+868h+var_818]
0x180012be6  mov     [rsp+868h+var_820], eax
0x180012bea  lea     rax, [rsp+868h+var_838]
0x180012bef  mov     [rsp+868h+var_828], rcx
0x180012bf4  lea     rdx, DebugInfoEvent
0x180012bfb  mov     [rsp+868h+var_848], rax
0x180012c00  lea     rcx, eaphost_Context
0x180012c07  call    McGenEventWrite_EtwEventWriteTransfer
0x180012c0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c13  lea     rax, WPP_GLOBAL_Control
0x180012c1a  cmp     rcx, rax
0x180012c1d  jz      short loc_180012C3A
0x180012c1f  test    byte ptr [rcx+1Ch], 4
0x180012c23  jz      short loc_180012C3A
0x180012c25  mov     rcx, [rcx+10h]
0x180012c29  lea     r8, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids
0x180012c30  mov     edx, 1Eh
0x180012c35  call    WPP_SF_
0x180012c3a  mov     rcx, [rsp+868h+var_18]
0x180012c42  xor     rcx, rsp; StackCookie
0x180012c45  call    __security_check_cookie
0x180012c4a  mov     rbx, [rsp+868h+arg_0]
0x180012c52  add     rsp, 860h
0x180012c59  pop     rdi
0x180012c5a  retn
0x180012c5b  mov     rcx, cs:eaphost_Context
0x180012c62  lea     rdx, DebugErrorEvent
0x180012c69  call    cs:__imp_EtwEventEnabled
0x180012c6f  test    al, al
0x180012c71  jz      short loc_180012CB1
0x180012c73  mov     r9d, ebx
0x180012c76  lea     r8, aDeletechildFai; "DeleteChild failed 0x%x"
0x180012c7d  mov     edx, 800h; unsigned __int64
0x180012c82  lea     rcx, [rsp+868h+var_818]; char *
0x180012c87  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180012c8c  test    eax, eax
0x180012c8e  js      short loc_180012CB1
0x180012c90  test    cs:byte_180020AC1, 8
0x180012c97  jz      short loc_180012CB1
0x180012c99  lea     r8, [rsp+868h+var_818]
0x180012c9e  lea     rdx, DebugErrorEvent
0x180012ca5  lea     rcx, eaphost_Context
0x180012cac  call    McTemplateU0s_EtwEventWriteTransfer
0x180012cb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180012cb8  lea     rax, WPP_GLOBAL_Control
0x180012cbf  cmp     rcx, rax
0x180012cc2  jz      short loc_180012CE2
0x180012cc4  test    byte ptr [rcx+1Ch], 1
0x180012cc8  jz      short loc_180012CE2
0x180012cca  mov     rcx, [rcx+10h]
0x180012cce  lea     r8, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids
0x180012cd5  mov     edx, 1Dh
0x180012cda  mov     r9d, ebx
0x180012cdd  call    WPP_SF_d
0x180012ce2  mov     edx, ebx
0x180012ce4  lea     rcx, byte_180018CBC
0x180012ceb  call    ??$Throw@J@SystemError@@SAXPEB_WJ@Z; SystemError::Throw<long>(wchar_t const *,long)
```
