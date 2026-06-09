# EapHost::ECPDeviceManager::GetECPBusEnumerator(ATL::CComPtr<IUMBusPDO> &,bool &)

- ea: `0x1800133a8`
- end: `0x18001356f`
- name: `?GetECPBusEnumerator@ECPDeviceManager@EapHost@@QEAAXAEAV?$CComPtr@UIUMBusPDO@@@ATL@@AEA_N@Z`
- size: `455`
- prototype: `_UNKNOWN **__fastcall(_QWORD *, __int64, _BYTE *)`
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
- `0x1800133a8`
- `0x180017010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18001342a`
- `ntdll!EtwEventEnabled` at `0x180013518`
- `ntdll!EtwEventEnabled` at `0x18001342a`
- `ntdll!EtwEventEnabled` at `0x180013518`

## pseudocode

```c
_UNKNOWN **__fastcall EapHost::ECPDeviceManager::GetECPBusEnumerator(_QWORD *a1, __int64 a2, _BYTE *a3)
{
  _UNKNOWN **result; // rax
  int v5; // ebx
  int v6; // r8d
  int v7; // r9d
  __int64 v8; // rax
  _BYTE v9[16]; // [rsp+30h] [rbp-838h] BYREF
  char *v10; // [rsp+40h] [rbp-828h]
  int v11; // [rsp+48h] [rbp-820h]
  int v12; // [rsp+4Ch] [rbp-81Ch]
  char v13[2048]; // [rsp+50h] [rbp-818h] BYREF

  *a3 = 1;
  result = (_UNKNOWN **)(*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64))(*(_QWORD *)*a1 + 40LL))(
                          *a1,
                          L"ECP_ROOT_BUS",
                          a2);
  v5 = (int)result;
  if ( (_DWORD)result )
  {
    if ( (_DWORD)result != -2147020584 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids,
          (unsigned int)result);
      if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
        && (int)StringCchPrintfA(
                  v13,
                  0x800u,
                  "FindEnumByIdentity failed while trying to get the ECP bus enumerator, 0x%x",
                  v5) >= 0
        && (byte_180020AC1 & 8) != 0 )
      {
        McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugErrorEvent, v13);
      }
      SystemError::Throw<long>((__int64)&byte_180018CBC, v5);
    }
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
      && (int)StringCchPrintfA(v13, 0x800u, "ECPBusEnumerator was not found") >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      v8 = -1;
      do
        ++v8;
      while ( v13[v8] );
      v12 = 0;
      v11 = v8 + 1;
      v10 = v13;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&eaphost_Context,
        (unsigned int)DebugInfoEvent,
        v6,
        v7,
        (__int64)v9);
    }
    result = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      return (_UNKNOWN **)WPP_SF_(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            12,
                            WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids);
  }
  else
  {
    *a3 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800133a8  mov     [rsp+arg_18], rbx
0x1800133ad  push    rdi
0x1800133ae  sub     rsp, 860h
0x1800133b5  mov     rax, cs:__security_cookie
0x1800133bc  xor     rax, rsp
0x1800133bf  mov     [rsp+868h+var_18], rax
0x1800133c7  mov     byte ptr [r8], 1
0x1800133cb  mov     rdi, r8
0x1800133ce  mov     rcx, [rcx]
0x1800133d1  mov     r8, rdx
0x1800133d4  lea     rdx, aEcpRootBus; "ECP_ROOT_BUS"
0x1800133db  mov     rax, [rcx]
0x1800133de  mov     rax, [rax+28h]
0x1800133e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133e7  mov     ebx, eax
0x1800133e9  test    eax, eax
0x1800133eb  jnz     short loc_180013410
0x1800133ed  mov     [rdi], al
0x1800133ef  mov     rcx, [rsp+868h+var_18]
0x1800133f7  xor     rcx, rsp; StackCookie
0x1800133fa  call    __security_check_cookie
0x1800133ff  mov     rbx, [rsp+868h+arg_18]
0x180013407  add     rsp, 860h
0x18001340e  pop     rdi
0x18001340f  retn
0x180013410  cmp     ebx, 800710D8h
0x180013416  jnz     loc_1800134D9
0x18001341c  mov     rcx, cs:eaphost_Context
0x180013423  lea     rdx, DebugInfoEvent
0x18001342a  call    cs:__imp_EtwEventEnabled
0x180013430  test    al, al
0x180013432  jz      short loc_18001349E
0x180013434  lea     r8, aEcpbusenumerat; "ECPBusEnumerator was not found"
0x18001343b  mov     edx, 800h; unsigned __int64
0x180013440  lea     rcx, [rsp+868h+var_818]; char *
0x180013445  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001344a  test    eax, eax
0x18001344c  js      short loc_18001349E
0x18001344e  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180013455  jge     short loc_18001349E
0x180013457  lea     rcx, [rsp+868h+var_818]
0x18001345c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013460  inc     rax
0x180013463  cmp     byte ptr [rcx+rax], 0
0x180013467  jnz     short loc_180013460
0x180013469  inc     eax
0x18001346b  mov     [rsp+868h+var_81C], 0
0x180013473  lea     rcx, [rsp+868h+var_818]
0x180013478  mov     [rsp+868h+var_820], eax
0x18001347c  lea     rax, [rsp+868h+var_838]
0x180013481  mov     [rsp+868h+var_828], rcx
0x180013486  lea     rdx, DebugInfoEvent
0x18001348d  mov     [rsp+868h+var_848], rax
0x180013492  lea     rcx, eaphost_Context
0x180013499  call    McGenEventWrite_EtwEventWriteTransfer
0x18001349e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800134a5  lea     rax, WPP_GLOBAL_Control
0x1800134ac  cmp     rcx, rax
0x1800134af  jz      loc_1800133EF
0x1800134b5  test    byte ptr [rcx+1Ch], 4
0x1800134b9  jz      loc_1800133EF
0x1800134bf  mov     rcx, [rcx+10h]
0x1800134c3  lea     r8, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids
0x1800134ca  mov     edx, 0Ch
0x1800134cf  call    WPP_SF_
0x1800134d4  jmp     loc_1800133EF
0x1800134d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800134e0  lea     rax, WPP_GLOBAL_Control
0x1800134e7  cmp     rcx, rax
0x1800134ea  jz      short loc_18001350A
0x1800134ec  test    byte ptr [rcx+1Ch], 1
0x1800134f0  jz      short loc_18001350A
0x1800134f2  mov     rcx, [rcx+10h]
0x1800134f6  lea     r8, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids
0x1800134fd  mov     edx, 0Dh
0x180013502  mov     r9d, ebx
0x180013505  call    WPP_SF_d
0x18001350a  mov     rcx, cs:eaphost_Context
0x180013511  lea     rdx, DebugErrorEvent
0x180013518  call    cs:__imp_EtwEventEnabled
0x18001351e  test    al, al
0x180013520  jz      short loc_180013560
0x180013522  mov     r9d, ebx
0x180013525  lea     r8, aFindenumbyiden; "FindEnumByIdentity failed while trying "...
0x18001352c  mov     edx, 800h; unsigned __int64
0x180013531  lea     rcx, [rsp+868h+var_818]; char *
0x180013536  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001353b  test    eax, eax
0x18001353d  js      short loc_180013560
0x18001353f  test    cs:byte_180020AC1, 8
0x180013546  jz      short loc_180013560
0x180013548  lea     r8, [rsp+868h+var_818]
0x18001354d  lea     rdx, DebugErrorEvent
0x180013554  lea     rcx, eaphost_Context
0x18001355b  call    McTemplateU0s_EtwEventWriteTransfer
0x180013560  mov     edx, ebx
0x180013562  lea     rcx, byte_180018CBC
0x180013569  call    ??$Throw@J@SystemError@@SAXPEB_WJ@Z; SystemError::Throw<long>(wchar_t const *,long)
```
