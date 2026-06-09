# EapLm::Peer::LegacyEapMethodConfig::QueryUIBlobFromInteractiveUIInputFields(uint,uint,ConstBuffer const &,_EAP_INTERACTIVE_UI_DATA const *,TempBuffer<0> &)

- ea: `0x18001aab0`
- end: `0x18001ae5a`
- name: `?QueryUIBlobFromInteractiveUIInputFields@LegacyEapMethodConfig@Peer@EapLm@@UEAAXIIAEBUConstBuffer@@PEBU_EAP_INTERACTIVE_UI_DATA@@AEAV?$TempBuffer@$0A@@@@Z`
- size: `938`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180004ec0`
- `0x180005894`
- `0x18000bf94`
- `0x1800126f8`
- `0x18001549c`
- `0x180016400`
- `0x18001aab0`
- `0x18001b154`
- `0x18001b1dc`
- `0x18001b2d4`
- `0x18002e494`
- `0x180034010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18001ab08`
- `ntdll!EtwEventEnabled` at `0x18001acbe`
- `ntdll!EtwEventEnabled` at `0x18001adaf`
- `ntdll!EtwEventEnabled` at `0x18001ab08`
- `ntdll!EtwEventEnabled` at `0x18001acbe`
- `ntdll!EtwEventEnabled` at `0x18001adaf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_UNKNOWN **__fastcall EapLm::Peer::LegacyEapMethodConfig::QueryUIBlobFromInteractiveUIInputFields(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        __int64 *a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v8; // rax
  __int64 (__fastcall *v9)(_QWORD, _QWORD, _QWORD, _QWORD, __int64, __int64, unsigned int *, const void **); // r15
  void (__fastcall *v10)(const void *); // r12
  __int64 v11; // rbx
  unsigned int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // r8
  _UNKNOWN **result; // rax
  unsigned int v16; // [rsp+50h] [rbp-898h] BYREF
  const void *v17; // [rsp+58h] [rbp-890h] BYREF
  unsigned int v18; // [rsp+60h] [rbp-888h]
  unsigned int v19; // [rsp+64h] [rbp-884h]
  void **v20; // [rsp+68h] [rbp-880h] BYREF
  char v21; // [rsp+70h] [rbp-878h]
  __int64 v22; // [rsp+74h] [rbp-874h]
  int v23; // [rsp+80h] [rbp-868h]
  __int64 v24; // [rsp+88h] [rbp-860h]
  void (__fastcall *v25)(const void *); // [rsp+90h] [rbp-858h]
  char v26[2048]; // [rsp+A0h] [rbp-848h] BYREF

  v18 = a3;
  v19 = a2;
  v24 = a5;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(
              v26,
              0x800u,
              "RasEapQueryUIBlobFromInteractiveUIInputFields Entry:\n Context data(%Id) bytes",
              a4[1]) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v26);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_P(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids, a4[1]);
  EapLm::DelayLoadModule::LoadIfNeeded(*(EapLm::DelayLoadModule **)(a1 + 168), 1);
  v8 = *(_QWORD *)(a1 + 168);
  v9 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, __int64, __int64, unsigned int *, const void **))(v8 + 216);
  if ( !v9 )
  {
    if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
      McTemplateU0s_EtwEventWriteTransfer(
        &eaphost_Context,
        (__int64)PeerFunctionNotSupported,
        "QueryUIBlobFromInteractiveUIInputFields");
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids);
    v21 = *(_BYTE *)(a1 + 16);
    v22 = *(_QWORD *)(a1 + 20);
    if ( v21 != -2 )
      v22 = 0;
    v20 = &EapHost::EapMethodType::`vftable';
    v23 = *(_DWORD *)(a1 + 28);
    EapHost::EapException::Throw(0x80420020, (const struct EapHost::EapMethodType *)&v20, 0x80420020);
  }
  v10 = *(void (__fastcall **)(const void *))(v8 + 232);
  v25 = v10;
  v16 = 0;
  v17 = 0;
  v11 = *a4;
  v12 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(a4[1]);
  v13 = v9(*(unsigned __int8 *)(a1 + 16), v19, v18, v12, v11, v24, &v16, &v17);
  if ( v13 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(v26, 0x800u, "RasEapQueryUIBlobFromInteractiveUIInputFields failed %d", v13) >= 0
      && (byte_18004AF81 & 8) != 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugErrorEvent, v26);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids, v13);
    v21 = *(_BYTE *)(a1 + 16);
    v22 = *(_QWORD *)(a1 + 20);
    if ( v21 != -2 )
      v22 = 0;
    v20 = &EapHost::EapMethodType::`vftable';
    v23 = *(_DWORD *)(a1 + 28);
    EapHost::EapException::Throw(v13, (const struct EapHost::EapMethodType *)&v20, v13);
  }
  try
  {
    TempBuffer<0>::Assign(a6, v16, v17);
  }
  catch ( std::bad_alloc )
  {
    v25(v17);
    throw;
  }
  v10(v17);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(
              v26,
              0x800u,
              "RasEapQueryUIBlobFromInteractiveUIInputFields Exit:\n context data(%Id) bytes, returned(%d) bytes data",
              a4[1],
              v16) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v26);
  }
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    return (_UNKNOWN **)WPP_SF_Pd(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, v14, a4[1], v16);
  return result;
}

```

## disassembly

```asm
0x18001aab0  push    rbx
0x18001aab2  push    rsi
0x18001aab3  push    rdi
0x18001aab4  push    r12
0x18001aab6  push    r13
0x18001aab8  push    r15
0x18001aaba  sub     rsp, 8B8h
0x18001aac1  mov     rax, cs:__security_cookie
0x18001aac8  xor     rax, rsp
0x18001aacb  mov     [rsp+8E8h+var_48], rax
0x18001aad3  mov     rsi, r9
0x18001aad6  mov     [rsp+8E8h+var_888], r8d
0x18001aadb  mov     [rsp+8E8h+var_884], edx
0x18001aadf  mov     rdi, rcx
0x18001aae2  mov     rax, [rsp+8E8h+arg_20]
0x18001aaea  mov     [rsp+8E8h+var_860], rax
0x18001aaf2  mov     r13, [rsp+8E8h+arg_28]
0x18001aafa  lea     rdx, DebugInfoEvent
0x18001ab01  mov     rcx, cs:eaphost_Context
0x18001ab08  call    cs:__imp_EtwEventEnabled
0x18001ab0e  xor     ebx, ebx
0x18001ab10  test    al, al
0x18001ab12  jz      short loc_18001AB58
0x18001ab14  mov     r9, [rsi+8]
0x18001ab18  lea     r8, aRaseapqueryuib_1; "RasEapQueryUIBlobFromInteractiveUIInput"...
0x18001ab1f  mov     edx, 800h; unsigned __int64
0x18001ab24  lea     rcx, [rsp+8E8h+var_848]; char *
0x18001ab2c  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001ab31  test    eax, eax
0x18001ab33  js      short loc_18001AB58
0x18001ab35  cmp     cs:Microsoft_Windows_EapHostEnableBits, bl
0x18001ab3b  jge     short loc_18001AB58
0x18001ab3d  lea     r8, [rsp+8E8h+var_848]
0x18001ab45  lea     rdx, DebugInfoEvent
0x18001ab4c  lea     rcx, eaphost_Context
0x18001ab53  call    McTemplateU0s_EtwEventWriteTransfer
0x18001ab58  lea     r12, WPP_GLOBAL_Control
0x18001ab5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab66  cmp     rcx, r12
0x18001ab69  jz      short loc_18001AB8A
0x18001ab6b  test    byte ptr [rcx+1Ch], 4
0x18001ab6f  jz      short loc_18001AB8A
0x18001ab71  mov     edx, 20h ; ' '
0x18001ab76  mov     r9, [rsi+8]
0x18001ab7a  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x18001ab81  mov     rcx, [rcx+10h]
0x18001ab85  call    WPP_SF_P
0x18001ab8a  mov     dl, 1; bool
0x18001ab8c  mov     rcx, [rdi+0A8h]; this
0x18001ab93  call    ?LoadIfNeeded@DelayLoadModule@EapLm@@QEAA_N_N@Z; EapLm::DelayLoadModule::LoadIfNeeded(bool)
0x18001ab98  mov     rax, [rdi+0A8h]
0x18001ab9f  mov     r15, [rax+0D8h]
0x18001aba6  test    r15, r15
0x18001aba9  jnz     loc_18001AC41
0x18001abaf  test    cs:Microsoft_Windows_EapHostEnableBits, 20h
0x18001abb6  jz      short loc_18001ABD2
0x18001abb8  lea     r8, aQueryuiblobfro; "QueryUIBlobFromInteractiveUIInputFields"
0x18001abbf  lea     rdx, PeerFunctionNotSupported
0x18001abc6  lea     rcx, eaphost_Context
0x18001abcd  call    McTemplateU0s_EtwEventWriteTransfer
0x18001abd2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001abd9  cmp     rcx, r12
0x18001abdc  jz      short loc_18001ABF9
0x18001abde  test    byte ptr [rcx+1Ch], 1
0x18001abe2  jz      short loc_18001ABF9
0x18001abe4  mov     edx, 21h ; '!'
0x18001abe9  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x18001abf0  mov     rcx, [rcx+10h]
0x18001abf4  call    WPP_SF_
0x18001abf9  mov     cl, [rdi+10h]
0x18001abfc  mov     [rsp+8E8h+var_878], cl
0x18001ac00  mov     eax, [rdi+14h]
0x18001ac03  mov     dword ptr [rsp+8E8h+var_874], eax
0x18001ac07  mov     eax, [rdi+18h]
0x18001ac0a  mov     dword ptr [rsp+8E8h+var_874+4], eax
0x18001ac0e  cmp     cl, 0FEh
0x18001ac11  jz      short loc_18001AC18
0x18001ac13  mov     [rsp+8E8h+var_874], rbx
0x18001ac18  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18001ac1f  mov     [rsp+8E8h+var_880], rax
0x18001ac24  mov     eax, [rdi+1Ch]
0x18001ac27  mov     [rsp+8E8h+var_868], eax
0x18001ac2e  mov     ecx, 80420020h; unsigned int
0x18001ac33  mov     r8d, ecx; unsigned int
0x18001ac36  lea     rdx, [rsp+8E8h+var_880]; struct EapHost::EapMethodType *
0x18001ac3b  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
0x18001ac41  mov     r12, [rax+0E8h]
0x18001ac48  mov     [rsp+8E8h+var_858], r12
0x18001ac50  mov     [rsp+8E8h+var_898], ebx
0x18001ac54  mov     [rsp+8E8h+var_890], rbx
0x18001ac59  mov     rbx, [rsi]
0x18001ac5c  mov     rcx, [rsi+8]
0x18001ac60  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001ac65  movzx   ecx, byte ptr [rdi+10h]
0x18001ac69  lea     rdx, [rsp+8E8h+var_890]
0x18001ac6e  mov     [rsp+8E8h+var_8B0], rdx
0x18001ac73  lea     rdx, [rsp+8E8h+var_898]
0x18001ac78  mov     [rsp+8E8h+var_8B8], rdx
0x18001ac7d  mov     rdx, [rsp+8E8h+var_860]
0x18001ac85  mov     [rsp+8E8h+var_8C0], rdx
0x18001ac8a  mov     [rsp+8E8h+var_8C8], rbx
0x18001ac8f  mov     r9d, eax
0x18001ac92  mov     r8d, [rsp+8E8h+var_888]
0x18001ac97  mov     edx, [rsp+8E8h+var_884]
0x18001ac9b  mov     rax, r15
0x18001ac9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aca3  mov     ebx, eax
0x18001aca5  xor     r15d, r15d
0x18001aca8  test    eax, eax
0x18001acaa  jz      loc_18001AD82
0x18001acb0  lea     rdx, DebugErrorEvent
0x18001acb7  mov     rcx, cs:eaphost_Context
0x18001acbe  call    cs:__imp_EtwEventEnabled
0x18001acc4  test    al, al
0x18001acc6  jz      short loc_18001AD0C
0x18001acc8  mov     r9d, ebx
0x18001accb  lea     r8, aRaseapqueryuib; "RasEapQueryUIBlobFromInteractiveUIInput"...
0x18001acd2  mov     edx, 800h; unsigned __int64
0x18001acd7  lea     rcx, [rsp+8E8h+var_848]; char *
0x18001acdf  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001ace4  test    eax, eax
0x18001ace6  js      short loc_18001AD0C
0x18001ace8  test    cs:byte_18004AF81, 8
0x18001acef  jz      short loc_18001AD0C
0x18001acf1  lea     r8, [rsp+8E8h+var_848]
0x18001acf9  lea     rdx, DebugErrorEvent
0x18001ad00  lea     rcx, eaphost_Context
0x18001ad07  call    McTemplateU0s_EtwEventWriteTransfer
0x18001ad0c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ad13  lea     rax, WPP_GLOBAL_Control
0x18001ad1a  cmp     rcx, rax
0x18001ad1d  jz      short loc_18001AD3D
0x18001ad1f  test    byte ptr [rcx+1Ch], 1
0x18001ad23  jz      short loc_18001AD3D
0x18001ad25  mov     edx, 22h ; '"'
0x18001ad2a  mov     r9d, ebx
0x18001ad2d  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x18001ad34  mov     rcx, [rcx+10h]
0x18001ad38  call    WPP_SF_d
0x18001ad3d  mov     cl, [rdi+10h]
0x18001ad40  mov     [rsp+8E8h+var_878], cl
0x18001ad44  mov     eax, [rdi+14h]
0x18001ad47  mov     dword ptr [rsp+8E8h+var_874], eax
0x18001ad4b  mov     eax, [rdi+18h]
0x18001ad4e  mov     dword ptr [rsp+8E8h+var_874+4], eax
0x18001ad52  cmp     cl, 0FEh
0x18001ad55  jz      short loc_18001AD5C
0x18001ad57  mov     [rsp+8E8h+var_874], r15
0x18001ad5c  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18001ad63  mov     [rsp+8E8h+var_880], rax
0x18001ad68  mov     eax, [rdi+1Ch]
0x18001ad6b  mov     [rsp+8E8h+var_868], eax
0x18001ad72  mov     r8d, ebx; unsigned int
0x18001ad75  lea     rdx, [rsp+8E8h+var_880]; struct EapHost::EapMethodType *
0x18001ad7a  mov     ecx, ebx; unsigned int
0x18001ad7c  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
0x18001ad82  mov     edx, [rsp+8E8h+var_898]
0x18001ad86  mov     r8, [rsp+8E8h+var_890]
0x18001ad8b  mov     rcx, r13
0x18001ad8e  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18001ad93  nop
0x18001ad94  mov     rcx, [rsp+8E8h+var_890]
0x18001ad99  mov     rax, r12
0x18001ad9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ada1  lea     rdx, DebugInfoEvent
0x18001ada8  mov     rcx, cs:eaphost_Context
0x18001adaf  call    cs:__imp_EtwEventEnabled
0x18001adb5  test    al, al
0x18001adb7  jz      short loc_18001AE06
0x18001adb9  mov     eax, [rsp+8E8h+var_898]
0x18001adbd  mov     dword ptr [rsp+8E8h+var_8C8], eax
0x18001adc1  mov     r9, [rsi+8]
0x18001adc5  lea     r8, aRaseapqueryuib_0; "RasEapQueryUIBlobFromInteractiveUIInput"...
0x18001adcc  mov     edx, 800h; unsigned __int64
0x18001add1  lea     rcx, [rsp+8E8h+var_848]; char *
0x18001add9  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001adde  test    eax, eax
0x18001ade0  js      short loc_18001AE06
0x18001ade2  cmp     cs:Microsoft_Windows_EapHostEnableBits, r15b
0x18001ade9  jge     short loc_18001AE06
0x18001adeb  lea     r8, [rsp+8E8h+var_848]
0x18001adf3  lea     rdx, DebugInfoEvent
0x18001adfa  lea     rcx, eaphost_Context
0x18001ae01  call    McTemplateU0s_EtwEventWriteTransfer
0x18001ae06  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ae0d  lea     rax, WPP_GLOBAL_Control
0x18001ae14  cmp     rcx, rax
0x18001ae17  jz      short loc_18001AE39
0x18001ae19  test    byte ptr [rcx+1Ch], 4
0x18001ae1d  jz      short loc_18001AE39
0x18001ae1f  mov     edx, 23h ; '#'
0x18001ae24  mov     eax, [rsp+8E8h+var_898]
0x18001ae28  mov     dword ptr [rsp+8E8h+var_8C8], eax
0x18001ae2c  mov     r9, [rsi+8]
0x18001ae30  mov     rcx, [rcx+10h]
0x18001ae34  call    WPP_SF_Pd
0x18001ae39  mov     rcx, [rsp+8E8h+var_48]
0x18001ae41  xor     rcx, rsp; StackCookie
0x18001ae44  call    __security_check_cookie
0x18001ae49  add     rsp, 8B8h
0x18001ae50  pop     r15
0x18001ae52  pop     r13
0x18001ae54  pop     r12
0x18001ae56  pop     rdi
0x18001ae57  pop     rsi
0x18001ae58  pop     rbx
0x18001ae59  retn
```
