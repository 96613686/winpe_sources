# ndisReadMiniportMediaSpecificPortAuthStates(_NDIS_MINIPORT_BLOCK *)

- ea: `0x14004d9b0`
- end: `0x14004dc51`
- name: `?ndisReadMiniportMediaSpecificPortAuthStates@@YAHPEAU_NDIS_MINIPORT_BLOCK@@@Z`
- size: `673`
- prototype: `__int64 __fastcall(struct _NDIS_MINIPORT_BLOCK *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14004d400`

## callees

- `0x1400110b0`
- `0x1400114b0`
- `0x14004be80`
- `0x14004d9b0`
- `0x14004dc60`
- `0x1400663c0`
- `0x1400eb380`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14004db2b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14004db2b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004db3f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004db53`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004db67`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004db3f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004db53`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004db67`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x14004da7b`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x14004da9e`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x14004da7b`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x14004da9e`
- `ntoskrnl!RtlCheckRegistryKey` at `0x14004db7c`
- `ntoskrnl!RtlCheckRegistryKey` at `0x14004db7c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004dabd`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004dad4`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004dabd`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004dad4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004dbe5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004dbe5`
- `ntoskrnl!ExAllocatePool2` at `0x14004db0a`
- `ntoskrnl!ExAllocatePool2` at `0x14004db0a`

## pseudocode

```c
__int64 __fastcall ndisReadMiniportMediaSpecificPortAuthStates(struct _NDIS_MINIPORT_BLOCK *a1)
{
  int v2; // edx
  unsigned int MiniportSpecificPortAuthStates; // esi
  struct _UNICODE_STRING Destination; // [rsp+48h] [rbp-79h] BYREF
  NTSTATUS v6; // [rsp+58h] [rbp-69h] BYREF
  struct _UNICODE_STRING String; // [rsp+60h] [rbp-61h] BYREF
  UNICODE_STRING v8; // [rsp+70h] [rbp-51h] BYREF
  NDIS_HANDLE ConfigurationHandle; // [rsp+80h] [rbp-41h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-39h] BYREF
  UNICODE_STRING Source; // [rsp+98h] [rbp-29h] BYREF
  char v12; // [rsp+A8h] [rbp-19h] BYREF
  char v13; // [rsp+D0h] [rbp+Fh] BYREF

  *(_QWORD *)&Destination.Length = 0;
  Destination.Buffer = 0;
  ConfigurationHandle = 0;
  String = 0;
  v8 = 0;
  DestinationString = 0;
  Source = 0;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      4,
      13,
      62,
      (struct _GUID *)&WPP_901e3e1acd0b36a9ab86c452924f7c21_Traceguids,
      (char)a1);
  *(_DWORD *)&String.Length = 2621440;
  String.Buffer = (wchar_t *)&v12;
  *(_DWORD *)&v8.Length = 2621440;
  v8.Buffer = (wchar_t *)&v13;
  if ( RtlIntegerToUnicodeString(a1->IfBlock->ifType, 0xAu, &String)
    || RtlIntegerToUnicodeString(a1->PhysicalMediumType, 0xAu, &v8)
    || (RtlInitUnicodeString(&DestinationString, L"Ndis\\IfTypes\\"),
        RtlInitUnicodeString(&Source, L"\\"),
        Destination.Length = 0,
        Destination.MaximumLength = String.Length + v8.Length + DestinationString.Length + Source.Length + 4,
        (Destination.Buffer = (wchar_t *)ExAllocatePool2(64, Destination.MaximumLength, 538985550)) == 0) )
  {
    MiniportSpecificPortAuthStates = -1073741670;
  }
  else
  {
    RtlCopyUnicodeString(&Destination, &DestinationString);
    RtlAppendUnicodeStringToString(&Destination, &String);
    RtlAppendUnicodeStringToString(&Destination, &Source);
    RtlAppendUnicodeStringToString(&Destination, &v8);
    v6 = RtlCheckRegistryKey(1u, Destination.Buffer);
    MiniportSpecificPortAuthStates = v6;
    if ( !v6 )
    {
      NdisOpenProtocolConfiguration(&v6, &ConfigurationHandle, &Destination);
      MiniportSpecificPortAuthStates = v6;
      if ( !v6 )
      {
        MiniportSpecificPortAuthStates = ndisReadMiniportSpecificPortAuthStates(a1, ConfigurationHandle);
        NdisCloseConfiguration(ConfigurationHandle);
        if ( !MiniportSpecificPortAuthStates )
          a1->FilterPnPFlags |= 0x10u;
      }
    }
  }
  if ( Destination.Buffer )
    ExFreePoolWithTag(Destination.Buffer, 0);
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v2) = 4;
    WPP_RECORDER_SF_qL(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v2,
      13,
      63,
      (struct _GUID *)&WPP_901e3e1acd0b36a9ab86c452924f7c21_Traceguids,
      (char)a1,
      MiniportSpecificPortAuthStates);
  }
  return MiniportSpecificPortAuthStates;
}

```

## disassembly

```asm
0x14004d9b0  mov     r11, rsp
0x14004d9b3  push    rbp
0x14004d9b4  push    rbx
0x14004d9b5  push    r15
0x14004d9b7  lea     rbp, [r11-5Fh]
0x14004d9bb  sub     rsp, 100h
0x14004d9c2  mov     rax, cs:__security_cookie
0x14004d9c9  xor     rax, rsp
0x14004d9cc  mov     [rbp+57h+var_20], rax
0x14004d9d0  xorps   xmm0, xmm0
0x14004d9d3  mov     [r11+18h], rdi
0x14004d9d7  xor     edi, edi
0x14004d9d9  mov     [r11+20h], r14
0x14004d9dd  xorps   xmm1, xmm1
0x14004d9e0  mov     qword ptr [rbp+57h+Destination.Length], rdi
0x14004d9e4  mov     [rbp+57h+Destination.Buffer], rdi
0x14004d9e8  mov     rbx, rcx
0x14004d9eb  mov     [rbp+57h+ConfigurationHandle], rdi
0x14004d9ef  movups  xmmword ptr [rbp+57h+String.Length], xmm0
0x14004d9f3  movups  xmmword ptr [rbp+57h+var_A8.Length], xmm1
0x14004d9f7  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14004d9fb  movups  xmmword ptr [rbp+57h+Source.Length], xmm0
0x14004d9ff  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14004da06  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14004da0d  lea     r15, WPP_901e3e1acd0b36a9ab86c452924f7c21_Traceguids
0x14004da14  jz      short loc_14004DA3E
0x14004da16  mov     qword ptr [rsp+110h+var_E8], rcx; char
0x14004da1b  mov     r9d, 3Eh ; '>'; int
0x14004da21  mov     rcx, cs:WPP_GLOBAL_Control
0x14004da28  mov     r8d, 0Dh; int
0x14004da2e  mov     dl, 4; int
0x14004da30  mov     [rsp+110h+var_F0], r15; struct _GUID *
0x14004da35  mov     rcx, [rcx+40h]; int
0x14004da39  call    WPP_RECORDER_SF_q
0x14004da3e  lea     rax, [rbp+57h+var_70]
0x14004da42  mov     dword ptr [rbp+57h+String.Length], 280000h
0x14004da49  mov     [rbp+57h+String.Buffer], rax
0x14004da4d  lea     r8, [rbp+57h+String]; String
0x14004da51  lea     rax, [rbp+57h+var_48]
0x14004da55  mov     dword ptr [rbp+57h+var_A8.Length], 280000h
0x14004da5c  mov     [rbp+57h+var_A8.Buffer], rax
0x14004da60  mov     edx, 0Ah; Base
0x14004da65  mov     rax, [rbx+0FC8h]
0x14004da6c  mov     [rsp+110h+arg_8], rsi
0x14004da74  movzx   ecx, word ptr [rax+20Ch]; Value
0x14004da7b  call    cs:__imp_RtlIntegerToUnicodeString
0x14004da82  nop     dword ptr [rax+rax+00h]
0x14004da87  test    eax, eax
0x14004da89  jnz     loc_14004DBCD
0x14004da8f  mov     ecx, [rbx+728h]; Value
0x14004da95  lea     r8, [rbp+57h+var_A8]; String
0x14004da99  mov     edx, 0Ah; Base
0x14004da9e  call    cs:__imp_RtlIntegerToUnicodeString
0x14004daa5  nop     dword ptr [rax+rax+00h]
0x14004daaa  test    eax, eax
0x14004daac  jnz     loc_14004DBCD
0x14004dab2  lea     rdx, SourceString; "Ndis\\IfTypes\\"
0x14004dab9  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14004dabd  call    cs:__imp_RtlInitUnicodeString
0x14004dac4  nop     dword ptr [rax+rax+00h]
0x14004dac9  lea     rdx, asc_1400FB840; "\\"
0x14004dad0  lea     rcx, [rbp+57h+Source]; DestinationString
0x14004dad4  call    cs:__imp_RtlInitUnicodeString
0x14004dadb  nop     dword ptr [rax+rax+00h]
0x14004dae0  movzx   eax, [rbp+57h+Source.Length]
0x14004dae4  mov     ecx, 40h ; '@'
0x14004dae9  add     ax, 4
0x14004daed  mov     [rbp+57h+Destination.Length], di
0x14004daf1  add     ax, [rbp+57h+DestinationString.Length]
0x14004daf5  mov     r8d, 2020444Eh
0x14004dafb  add     ax, [rbp+57h+var_A8.Length]
0x14004daff  add     ax, [rbp+57h+String.Length]
0x14004db03  movzx   edx, ax
0x14004db06  mov     [rbp+57h+Destination.MaximumLength], dx
0x14004db0a  call    cs:__imp_ExAllocatePool2
0x14004db11  nop     dword ptr [rax+rax+00h]
0x14004db16  mov     [rbp+57h+Destination.Buffer], rax
0x14004db1a  test    rax, rax
0x14004db1d  jz      loc_14004DBCD
0x14004db23  lea     rdx, [rbp+57h+DestinationString]; SourceString
0x14004db27  lea     rcx, [rbp+57h+Destination]; DestinationString
0x14004db2b  call    cs:__imp_RtlCopyUnicodeString
0x14004db32  nop     dword ptr [rax+rax+00h]
0x14004db37  lea     rdx, [rbp+57h+String]; Source
0x14004db3b  lea     rcx, [rbp+57h+Destination]; Destination
0x14004db3f  call    cs:__imp_RtlAppendUnicodeStringToString
0x14004db46  nop     dword ptr [rax+rax+00h]
0x14004db4b  lea     rdx, [rbp+57h+Source]; Source
0x14004db4f  lea     rcx, [rbp+57h+Destination]; Destination
0x14004db53  call    cs:__imp_RtlAppendUnicodeStringToString
0x14004db5a  nop     dword ptr [rax+rax+00h]
0x14004db5f  lea     rdx, [rbp+57h+var_A8]; Source
0x14004db63  lea     rcx, [rbp+57h+Destination]; Destination
0x14004db67  call    cs:__imp_RtlAppendUnicodeStringToString
0x14004db6e  nop     dword ptr [rax+rax+00h]
0x14004db73  mov     rdx, [rbp+57h+Destination.Buffer]; Path
0x14004db77  mov     ecx, 1; RelativeTo
0x14004db7c  call    cs:__imp_RtlCheckRegistryKey
0x14004db83  nop     dword ptr [rax+rax+00h]
0x14004db88  mov     [rbp+57h+var_C0], eax
0x14004db8b  mov     esi, eax
0x14004db8d  test    eax, eax
0x14004db8f  jnz     short loc_14004DBD2
0x14004db91  lea     r8, [rbp+57h+Destination]
0x14004db95  lea     rdx, [rbp+57h+ConfigurationHandle]
0x14004db99  lea     rcx, [rbp+57h+var_C0]
0x14004db9d  call    NdisOpenProtocolConfiguration
0x14004dba2  mov     esi, [rbp+57h+var_C0]
0x14004dba5  test    esi, esi
0x14004dba7  jnz     short loc_14004DBD2
0x14004dba9  mov     rdx, [rbp+57h+ConfigurationHandle]; ConfigurationHandle
0x14004dbad  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14004dbb0  call    ?ndisReadMiniportSpecificPortAuthStates@@YAHPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_CONFIGURATION_HANDLE@@@Z; ndisReadMiniportSpecificPortAuthStates(_NDIS_MINIPORT_BLOCK *,_NDIS_CONFIGURATION_HANDLE *)
0x14004dbb5  mov     rcx, [rbp+57h+ConfigurationHandle]; ConfigurationHandle
0x14004dbb9  mov     esi, eax
0x14004dbbb  call    NdisCloseConfiguration
0x14004dbc0  test    esi, esi
0x14004dbc2  jnz     short loc_14004DBD2
0x14004dbc4  or      dword ptr [rbx+0A7Ch], 10h
0x14004dbcb  jmp     short loc_14004DBD2
0x14004dbcd  mov     esi, 0C000009Ah
0x14004dbd2  mov     rcx, [rbp+57h+Destination.Buffer]; P
0x14004dbd6  mov     rdi, [rsp+110h+arg_10]
0x14004dbde  test    rcx, rcx
0x14004dbe1  jz      short loc_14004DBF1
0x14004dbe3  xor     edx, edx; Tag
0x14004dbe5  call    cs:__imp_ExFreePoolWithTag
0x14004dbec  nop     dword ptr [rax+rax+00h]
0x14004dbf1  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14004dbf8  mov     r14, [rsp+110h+arg_18]
0x14004dc00  jz      short loc_14004DC2E
0x14004dc02  mov     rcx, cs:WPP_GLOBAL_Control
0x14004dc09  mov     r9d, 3Fh ; '?'; int
0x14004dc0f  mov     [rsp+30h], esi; char
0x14004dc13  mov     r8d, 0Dh; int
0x14004dc19  mov     qword ptr [rsp+110h+var_E8], rbx; char
0x14004dc1e  mov     dl, 4; int
0x14004dc20  mov     [rsp+110h+var_F0], r15; struct _GUID *
0x14004dc25  mov     rcx, [rcx+40h]; int
0x14004dc29  call    WPP_RECORDER_SF_qL
0x14004dc2e  mov     eax, esi
0x14004dc30  mov     rsi, [rsp+110h+arg_8]
0x14004dc38  mov     rcx, [rbp+57h+var_20]
0x14004dc3c  xor     rcx, rsp; StackCookie
0x14004dc3f  call    __security_check_cookie
0x14004dc44  add     rsp, 100h
0x14004dc4b  pop     r15
0x14004dc4d  pop     rbx
0x14004dc4e  pop     rbp
0x14004dc4f  retn
```
