# EapHost::ECPDeviceManager::DeleteECPBusEnumerator(ATL::CComPtr<IUMBusPDO> &)

- ea: `0x180012968`
- end: `0x180012b29`
- name: `?DeleteECPBusEnumerator@ECPDeviceManager@EapHost@@QEAAXAEAV?$CComPtr@UIUMBusPDO@@@ATL@@@Z`
- size: `449`
- prototype: `_UNKNOWN **__fastcall(_QWORD *, _QWORD *)`
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
- `0x180012968`
- `0x180017010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x1800129d0`
- `ntdll!EtwEventEnabled` at `0x180012aa1`
- `ntdll!EtwEventEnabled` at `0x1800129d0`
- `ntdll!EtwEventEnabled` at `0x180012aa1`

## string_xrefs

- `0x180012aae`: `DeleteBusEnumerator failed 0x%x`
- `0x1800129da`: `ECP bus enumerator is deleted`

## pseudocode

```c
_UNKNOWN **__fastcall EapHost::ECPDeviceManager::DeleteECPBusEnumerator(_QWORD *a1, _QWORD *a2)
{
  unsigned int v3; // ebx
  int v4; // r8d
  int v5; // r9d
  __int64 v6; // rax
  _UNKNOWN **result; // rax
  _BYTE v8[16]; // [rsp+30h] [rbp-838h] BYREF
  char *v9; // [rsp+40h] [rbp-828h]
  int v10; // [rsp+48h] [rbp-820h]
  int v11; // [rsp+4Ch] [rbp-81Ch]
  char v12[2048]; // [rsp+50h] [rbp-818h] BYREF

  v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a1 + 64LL))(*a1, *a2);
  if ( v3 > 1 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(v12, 0x800u, "DeleteBusEnumerator failed 0x%x", v3) >= 0
      && (byte_180020AC1 & 8) != 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugErrorEvent, v12);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids, v3);
    SystemError::Throw<long>((__int64)&byte_180018CBC, v3);
  }
  if ( *a2 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
    *a2 = 0;
  }
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v12, 0x800u, "ECP bus enumerator is deleted") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v6 = -1;
    do
      ++v6;
    while ( v12[v6] );
    v11 = 0;
    v10 = v6 + 1;
    v9 = v12;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&eaphost_Context,
      (unsigned int)DebugInfoEvent,
      v4,
      v5,
      (__int64)v8);
  }
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    return (_UNKNOWN **)WPP_SF_(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          22,
                          WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids);
  return result;
}

```

## disassembly

```asm
0x180012968  mov     [rsp+arg_10], rbx
0x18001296d  push    rdi
0x18001296e  sub     rsp, 860h
0x180012975  mov     rax, cs:__security_cookie
0x18001297c  xor     rax, rsp
0x18001297f  mov     [rsp+868h+var_18], rax
0x180012987  mov     rcx, [rcx]
0x18001298a  mov     rdi, rdx
0x18001298d  mov     rdx, [rdx]
0x180012990  mov     rax, [rcx]
0x180012993  mov     rax, [rax+40h]
0x180012997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001299c  mov     ebx, eax
0x18001299e  cmp     eax, 1
0x1800129a1  ja      loc_180012A93
0x1800129a7  mov     rcx, [rdi]
0x1800129aa  test    rcx, rcx
0x1800129ad  jz      short loc_1800129C2
0x1800129af  mov     rax, [rcx]
0x1800129b2  mov     rax, [rax+10h]
0x1800129b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129bb  mov     qword ptr [rdi], 0
0x1800129c2  mov     rcx, cs:eaphost_Context
0x1800129c9  lea     rdx, DebugInfoEvent
0x1800129d0  call    cs:__imp_EtwEventEnabled
0x1800129d6  test    al, al
0x1800129d8  jz      short loc_180012A44
0x1800129da  lea     r8, aEcpBusEnumerat_0; "ECP bus enumerator is deleted"
0x1800129e1  mov     edx, 800h; unsigned __int64
0x1800129e6  lea     rcx, [rsp+868h+var_818]; char *
0x1800129eb  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800129f0  test    eax, eax
0x1800129f2  js      short loc_180012A44
0x1800129f4  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x1800129fb  jge     short loc_180012A44
0x1800129fd  lea     rcx, [rsp+868h+var_818]
0x180012a02  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012a06  inc     rax
0x180012a09  cmp     byte ptr [rcx+rax], 0
0x180012a0d  jnz     short loc_180012A06
0x180012a0f  inc     eax
0x180012a11  mov     [rsp+868h+var_81C], 0
0x180012a19  lea     rcx, [rsp+868h+var_818]
0x180012a1e  mov     [rsp+868h+var_820], eax
0x180012a22  lea     rax, [rsp+868h+var_838]
0x180012a27  mov     [rsp+868h+var_828], rcx
0x180012a2c  lea     rdx, DebugInfoEvent
0x180012a33  mov     [rsp+868h+var_848], rax
0x180012a38  lea     rcx, eaphost_Context
0x180012a3f  call    McGenEventWrite_EtwEventWriteTransfer
0x180012a44  mov     rcx, cs:WPP_GLOBAL_Control
0x180012a4b  lea     rax, WPP_GLOBAL_Control
0x180012a52  cmp     rcx, rax
0x180012a55  jz      short loc_180012A72
0x180012a57  test    byte ptr [rcx+1Ch], 4
0x180012a5b  jz      short loc_180012A72
0x180012a5d  mov     rcx, [rcx+10h]
0x180012a61  lea     r8, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids
0x180012a68  mov     edx, 16h
0x180012a6d  call    WPP_SF_
0x180012a72  mov     rcx, [rsp+868h+var_18]
0x180012a7a  xor     rcx, rsp; StackCookie
0x180012a7d  call    __security_check_cookie
0x180012a82  mov     rbx, [rsp+868h+arg_10]
0x180012a8a  add     rsp, 860h
0x180012a91  pop     rdi
0x180012a92  retn
0x180012a93  mov     rcx, cs:eaphost_Context
0x180012a9a  lea     rdx, DebugErrorEvent
0x180012aa1  call    cs:__imp_EtwEventEnabled
0x180012aa7  test    al, al
0x180012aa9  jz      short loc_180012AE9
0x180012aab  mov     r9d, ebx
0x180012aae  lea     r8, aDeletebusenume; "DeleteBusEnumerator failed 0x%x"
0x180012ab5  mov     edx, 800h; unsigned __int64
0x180012aba  lea     rcx, [rsp+868h+var_818]; char *
0x180012abf  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180012ac4  test    eax, eax
0x180012ac6  js      short loc_180012AE9
0x180012ac8  test    cs:byte_180020AC1, 8
0x180012acf  jz      short loc_180012AE9
0x180012ad1  lea     r8, [rsp+868h+var_818]
0x180012ad6  lea     rdx, DebugErrorEvent
0x180012add  lea     rcx, eaphost_Context
0x180012ae4  call    McTemplateU0s_EtwEventWriteTransfer
0x180012ae9  mov     rcx, cs:WPP_GLOBAL_Control
0x180012af0  lea     rax, WPP_GLOBAL_Control
0x180012af7  cmp     rcx, rax
0x180012afa  jz      short loc_180012B1A
0x180012afc  test    byte ptr [rcx+1Ch], 1
0x180012b00  jz      short loc_180012B1A
0x180012b02  mov     rcx, [rcx+10h]
0x180012b06  lea     r8, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids
0x180012b0d  mov     edx, 15h
0x180012b12  mov     r9d, ebx
0x180012b15  call    WPP_SF_d
0x180012b1a  mov     edx, ebx
0x180012b1c  lea     rcx, byte_180018CBC
0x180012b23  call    ??$Throw@J@SystemError@@SAXPEB_WJ@Z; SystemError::Throw<long>(wchar_t const *,long)
```
