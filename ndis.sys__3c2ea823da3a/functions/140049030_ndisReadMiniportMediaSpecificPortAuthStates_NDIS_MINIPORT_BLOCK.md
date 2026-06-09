# ndisReadMiniportMediaSpecificPortAuthStates(_NDIS_MINIPORT_BLOCK *)

- ea: `0x140049030`
- end: `0x1400492d1`
- name: `?ndisReadMiniportMediaSpecificPortAuthStates@@YAHPEAU_NDIS_MINIPORT_BLOCK@@@Z`
- size: `673`
- prototype: `__int64 __fastcall(struct _NDIS_MINIPORT_BLOCK *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140048a80`

## callees

- `0x14001cf50`
- `0x14001d350`
- `0x140047500`
- `0x140049030`
- `0x1400492e0`
- `0x140061340`
- `0x1400e6160`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400491ab`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400491ab`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400491bf`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400491d3`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400491e7`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400491bf`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400491d3`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400491e7`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x1400490fb`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x14004911e`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x1400490fb`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x14004911e`
- `ntoskrnl!RtlCheckRegistryKey` at `0x1400491fc`
- `ntoskrnl!RtlCheckRegistryKey` at `0x1400491fc`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004913d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140049154`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004913d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140049154`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049265`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049265`
- `ntoskrnl!ExAllocatePool2` at `0x14004918a`
- `ntoskrnl!ExAllocatePool2` at `0x14004918a`

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
0x140049030  mov     r11, rsp
0x140049033  push    rbp
0x140049034  push    rbx
0x140049035  push    r15
0x140049037  lea     rbp, [r11-5Fh]
0x14004903b  sub     rsp, 100h
0x140049042  mov     rax, cs:__security_cookie
0x140049049  xor     rax, rsp
0x14004904c  mov     [rbp+57h+var_20], rax
0x140049050  xorps   xmm0, xmm0
0x140049053  mov     [r11+18h], rdi
0x140049057  xor     edi, edi
0x140049059  mov     [r11+20h], r14
0x14004905d  xorps   xmm1, xmm1
0x140049060  mov     qword ptr [rbp+57h+Destination.Length], rdi
0x140049064  mov     [rbp+57h+Destination.Buffer], rdi
0x140049068  mov     rbx, rcx
0x14004906b  mov     [rbp+57h+ConfigurationHandle], rdi
0x14004906f  movups  xmmword ptr [rbp+57h+String.Length], xmm0
0x140049073  movups  xmmword ptr [rbp+57h+var_A8.Length], xmm1
0x140049077  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14004907b  movups  xmmword ptr [rbp+57h+Source.Length], xmm0
0x14004907f  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140049086  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14004908d  lea     r15, WPP_901e3e1acd0b36a9ab86c452924f7c21_Traceguids
0x140049094  jz      short loc_1400490BE
0x140049096  mov     qword ptr [rsp+110h+var_E8], rcx; char
0x14004909b  mov     r9d, 3Eh ; '>'; int
0x1400490a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400490a8  mov     r8d, 0Dh; int
0x1400490ae  mov     dl, 4; int
0x1400490b0  mov     [rsp+110h+var_F0], r15; struct _GUID *
0x1400490b5  mov     rcx, [rcx+40h]; int
0x1400490b9  call    WPP_RECORDER_SF_q
0x1400490be  lea     rax, [rbp+57h+var_70]
0x1400490c2  mov     dword ptr [rbp+57h+String.Length], 280000h
0x1400490c9  mov     [rbp+57h+String.Buffer], rax
0x1400490cd  lea     r8, [rbp+57h+String]; String
0x1400490d1  lea     rax, [rbp+57h+var_48]
0x1400490d5  mov     dword ptr [rbp+57h+var_A8.Length], 280000h
0x1400490dc  mov     [rbp+57h+var_A8.Buffer], rax
0x1400490e0  mov     edx, 0Ah; Base
0x1400490e5  mov     rax, [rbx+0FC8h]
0x1400490ec  mov     [rsp+110h+arg_8], rsi
0x1400490f4  movzx   ecx, word ptr [rax+20Ch]; Value
0x1400490fb  call    cs:__imp_RtlIntegerToUnicodeString
0x140049102  nop     dword ptr [rax+rax+00h]
0x140049107  test    eax, eax
0x140049109  jnz     loc_14004924D
0x14004910f  mov     ecx, [rbx+728h]; Value
0x140049115  lea     r8, [rbp+57h+var_A8]; String
0x140049119  mov     edx, 0Ah; Base
0x14004911e  call    cs:__imp_RtlIntegerToUnicodeString
0x140049125  nop     dword ptr [rax+rax+00h]
0x14004912a  test    eax, eax
0x14004912c  jnz     loc_14004924D
0x140049132  lea     rdx, aNdisIftypes; "Ndis\\IfTypes\\"
0x140049139  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14004913d  call    cs:__imp_RtlInitUnicodeString
0x140049144  nop     dword ptr [rax+rax+00h]
0x140049149  lea     rdx, asc_1400F6810; "\\"
0x140049150  lea     rcx, [rbp+57h+Source]; DestinationString
0x140049154  call    cs:__imp_RtlInitUnicodeString
0x14004915b  nop     dword ptr [rax+rax+00h]
0x140049160  movzx   eax, [rbp+57h+Source.Length]
0x140049164  mov     ecx, 40h ; '@'
0x140049169  add     ax, 4
0x14004916d  mov     [rbp+57h+Destination.Length], di
0x140049171  add     ax, [rbp+57h+DestinationString.Length]
0x140049175  mov     r8d, 2020444Eh
0x14004917b  add     ax, [rbp+57h+var_A8.Length]
0x14004917f  add     ax, [rbp+57h+String.Length]
0x140049183  movzx   edx, ax
0x140049186  mov     [rbp+57h+Destination.MaximumLength], dx
0x14004918a  call    cs:__imp_ExAllocatePool2
0x140049191  nop     dword ptr [rax+rax+00h]
0x140049196  mov     [rbp+57h+Destination.Buffer], rax
0x14004919a  test    rax, rax
0x14004919d  jz      loc_14004924D
0x1400491a3  lea     rdx, [rbp+57h+DestinationString]; SourceString
0x1400491a7  lea     rcx, [rbp+57h+Destination]; DestinationString
0x1400491ab  call    cs:__imp_RtlCopyUnicodeString
0x1400491b2  nop     dword ptr [rax+rax+00h]
0x1400491b7  lea     rdx, [rbp+57h+String]; Source
0x1400491bb  lea     rcx, [rbp+57h+Destination]; Destination
0x1400491bf  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400491c6  nop     dword ptr [rax+rax+00h]
0x1400491cb  lea     rdx, [rbp+57h+Source]; Source
0x1400491cf  lea     rcx, [rbp+57h+Destination]; Destination
0x1400491d3  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400491da  nop     dword ptr [rax+rax+00h]
0x1400491df  lea     rdx, [rbp+57h+var_A8]; Source
0x1400491e3  lea     rcx, [rbp+57h+Destination]; Destination
0x1400491e7  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400491ee  nop     dword ptr [rax+rax+00h]
0x1400491f3  mov     rdx, [rbp+57h+Destination.Buffer]; Path
0x1400491f7  mov     ecx, 1; RelativeTo
0x1400491fc  call    cs:__imp_RtlCheckRegistryKey
0x140049203  nop     dword ptr [rax+rax+00h]
0x140049208  mov     [rbp+57h+var_C0], eax
0x14004920b  mov     esi, eax
0x14004920d  test    eax, eax
0x14004920f  jnz     short loc_140049252
0x140049211  lea     r8, [rbp+57h+Destination]
0x140049215  lea     rdx, [rbp+57h+ConfigurationHandle]
0x140049219  lea     rcx, [rbp+57h+var_C0]
0x14004921d  call    NdisOpenProtocolConfiguration
0x140049222  mov     esi, [rbp+57h+var_C0]
0x140049225  test    esi, esi
0x140049227  jnz     short loc_140049252
0x140049229  mov     rdx, [rbp+57h+ConfigurationHandle]; ConfigurationHandle
0x14004922d  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140049230  call    ?ndisReadMiniportSpecificPortAuthStates@@YAHPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_CONFIGURATION_HANDLE@@@Z; ndisReadMiniportSpecificPortAuthStates(_NDIS_MINIPORT_BLOCK *,_NDIS_CONFIGURATION_HANDLE *)
0x140049235  mov     rcx, [rbp+57h+ConfigurationHandle]; ConfigurationHandle
0x140049239  mov     esi, eax
0x14004923b  call    NdisCloseConfiguration
0x140049240  test    esi, esi
0x140049242  jnz     short loc_140049252
0x140049244  or      dword ptr [rbx+0A7Ch], 10h
0x14004924b  jmp     short loc_140049252
0x14004924d  mov     esi, 0C000009Ah
0x140049252  mov     rcx, [rbp+57h+Destination.Buffer]; P
0x140049256  mov     rdi, [rsp+110h+arg_10]
0x14004925e  test    rcx, rcx
0x140049261  jz      short loc_140049271
0x140049263  xor     edx, edx; Tag
0x140049265  call    cs:__imp_ExFreePoolWithTag
0x14004926c  nop     dword ptr [rax+rax+00h]
0x140049271  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140049278  mov     r14, [rsp+110h+arg_18]
0x140049280  jz      short loc_1400492AE
0x140049282  mov     rcx, cs:WPP_GLOBAL_Control
0x140049289  mov     r9d, 3Fh ; '?'; int
0x14004928f  mov     [rsp+30h], esi; char
0x140049293  mov     r8d, 0Dh; int
0x140049299  mov     qword ptr [rsp+110h+var_E8], rbx; char
0x14004929e  mov     dl, 4; int
0x1400492a0  mov     [rsp+110h+var_F0], r15; struct _GUID *
0x1400492a5  mov     rcx, [rcx+40h]; int
0x1400492a9  call    WPP_RECORDER_SF_qL
0x1400492ae  mov     eax, esi
0x1400492b0  mov     rsi, [rsp+110h+arg_8]
0x1400492b8  mov     rcx, [rbp+57h+var_20]
0x1400492bc  xor     rcx, rsp; StackCookie
0x1400492bf  call    __security_check_cookie
0x1400492c4  add     rsp, 100h
0x1400492cb  pop     r15
0x1400492cd  pop     rbx
0x1400492ce  pop     rbp
0x1400492cf  retn
```
