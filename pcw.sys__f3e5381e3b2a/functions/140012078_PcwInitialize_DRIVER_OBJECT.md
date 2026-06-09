# PcwInitialize(_DRIVER_OBJECT *)

- ea: `0x140012078`
- end: `0x1400121f9`
- name: `?PcwInitialize@@YAJPEAU_DRIVER_OBJECT@@@Z`
- size: `385`
- prototype: `__int64 __fastcall(struct _DRIVER_OBJECT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140012200`

## callees

- `0x140001370`
- `0x1400017c0`
- `0x14000ad30`
- `0x140012078`

## import_xrefs

- `ntoskrnl!ExRegisterExtension` at `0x1400120f8`
- `ntoskrnl!ExRegisterExtension` at `0x1400120f8`
- `ntoskrnl!RtlInitUnicodeString` at `0x140012185`
- `ntoskrnl!RtlInitUnicodeString` at `0x140012185`
- `ntoskrnl!ObCreateObjectType` at `0x1400121a3`
- `ntoskrnl!ObCreateObjectType` at `0x1400121a3`
- `ntoskrnl!ExUnregisterExtension` at `0x1400121ba`
- `ntoskrnl!ExUnregisterExtension` at `0x1400121ba`

## pseudocode

```c
__int64 __fastcall PcwInitialize(struct _DRIVER_OBJECT *a1)
{
  __int64 v2; // rcx
  int v3; // ebx
  __int64 v4; // r9
  __int64 v6; // [rsp+20h] [rbp-99h] BYREF
  _DWORD v7[2]; // [rsp+28h] [rbp-91h] BYREF
  void *v8; // [rsp+30h] [rbp-89h]
  __int64 v9; // [rsp+38h] [rbp-81h]
  struct _DRIVER_OBJECT *v10; // [rsp+40h] [rbp-79h]
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-71h] BYREF
  _QWORD v12[16]; // [rsp+60h] [rbp-59h] BYREF

  v6 = 0;
  DestinationString = 0;
  memset(v12, 0, 0x78u);
  v7[0] = 65537;
  v8 = &PcwpCallbackTable;
  v7[1] = 327680;
  v9 = 0;
  v10 = a1;
  v3 = ExRegisterExtension(&v6, 65537, v7);
  if ( v3 < 0 )
  {
    if ( (Microsoft_Windows_Diagnosis_PCWEnableBits & 1) == 0 )
      return (unsigned int)v3;
    v4 = 3;
LABEL_4:
    McTemplateU0qq_EtwWriteTransfer(v2, DriverLoadFail, (unsigned int)v3, v4);
    return (unsigned int)v3;
  }
  BYTE2(v12[0]) |= 6u;
  v12[7] = &PcwpOpenObject;
  LOWORD(v12[0]) = 120;
  v12[9] = PcwpDeleteObject;
  LODWORD(v12[1]) = 306;
  v12[8] = PcwpCloseObjectHandle;
  *(struct _GENERIC_MAPPING *)((char *)&v12[1] + 4) = PcwObjectGenericMap;
  HIDWORD(v12[3]) = 983043;
  HIDWORD(v12[4]) = 1;
  LODWORD(v12[5]) = 56;
  RtlInitUnicodeString(&DestinationString, L"PcwObject");
  v3 = ObCreateObjectType(&DestinationString, v12, 0, &PcwObjectType);
  if ( v3 < 0 )
  {
    ExUnregisterExtension(v6);
    if ( (Microsoft_Windows_Diagnosis_PCWEnableBits & 1) == 0 )
      return (unsigned int)v3;
    v4 = 4;
    goto LABEL_4;
  }
  return 0;
}

```

## disassembly

```asm
0x140012078  push    rbp
0x14001207a  push    rbx
0x14001207b  push    rsi
0x14001207c  push    rdi
0x14001207d  lea     rbp, [rsp-3Fh]
0x140012082  sub     rsp, 0F8h
0x140012089  mov     rax, cs:__security_cookie
0x140012090  xor     rax, rsp
0x140012093  mov     [rbp+57h+var_30], rax
0x140012097  mov     rbx, rcx
0x14001209a  mov     [rsp+110h+var_F0], 0
0x1400120a3  xorps   xmm0, xmm0
0x1400120a6  lea     rcx, [rbp+57h+var_B0]; void *
0x1400120aa  mov     esi, 78h ; 'x'
0x1400120af  xor     edx, edx; Val
0x1400120b1  mov     r8d, esi; Size
0x1400120b4  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400120b8  call    memset
0x1400120bd  lea     rax, ?PcwpCallbackTable@@3U_PCW_CALLBACK_TABLE@@A; _PCW_CALLBACK_TABLE PcwpCallbackTable
0x1400120c4  mov     [rsp+110h+var_E8], 10001h
0x1400120cc  lea     r8, [rsp+110h+var_E8]
0x1400120d1  mov     [rsp+110h+var_E0], rax
0x1400120d6  mov     edx, 10001h
0x1400120db  mov     [rsp+110h+var_E4], 50000h
0x1400120e3  lea     rcx, [rsp+110h+var_F0]
0x1400120e8  mov     [rsp+110h+var_D8], 0
0x1400120f1  lea     edi, [rsi-77h]
0x1400120f4  mov     [rbp+57h+var_D0], rbx
0x1400120f8  call    cs:__imp_ExRegisterExtension
0x1400120ff  nop     dword ptr [rax+rax+00h]
0x140012104  mov     ebx, eax
0x140012106  test    eax, eax
0x140012108  jns     short loc_14001212D
0x14001210a  test    byte ptr cs:Microsoft_Windows_Diagnosis_PCWEnableBits, dil
0x140012111  jz      short loc_140012126
0x140012113  lea     r9d, [rsi-75h]
0x140012117  mov     r8d, ebx
0x14001211a  lea     rdx, DriverLoadFail
0x140012121  call    McTemplateU0qq_EtwWriteTransfer
0x140012126  mov     eax, ebx
0x140012128  jmp     loc_1400121E0
0x14001212d  movups  xmm0, cs:?PcwObjectGenericMap@@3U_GENERIC_MAPPING@@A; _GENERIC_MAPPING PcwObjectGenericMap
0x140012134  or      [rbp+57h+var_AE], 6
0x140012138  lea     rax, ?PcwpOpenObject@@YAJW4_OB_OPEN_REASON@@DPEAU_EPROCESS@@PEAXPEAKK@Z; PcwpOpenObject(_OB_OPEN_REASON,char,_EPROCESS *,void *,ulong *,ulong)
0x14001213f  mov     [rbp+57h+var_78], rax
0x140012143  lea     rdx, aPcwobject; "PcwObject"
0x14001214a  lea     rax, ?PcwpDeleteObject@@YAXPEAX@Z; PcwpDeleteObject(void *)
0x140012151  mov     [rbp+57h+var_B0], si
0x140012155  mov     [rbp+57h+var_68], rax
0x140012159  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001215d  lea     rax, ?PcwpCloseObjectHandle@@YAXPEAU_EPROCESS@@PEAX_K2@Z; PcwpCloseObjectHandle(_EPROCESS *,void *,unsigned __int64,unsigned __int64)
0x140012164  mov     [rbp+57h+var_A8], 132h
0x14001216b  mov     [rbp+57h+var_70], rax
0x14001216f  movdqu  [rbp+57h+var_A4], xmm0
0x140012174  mov     [rbp+57h+var_94], 0F0003h
0x14001217b  mov     [rbp+57h+var_8C], edi
0x14001217e  mov     [rbp+57h+var_88], 38h ; '8'
0x140012185  call    cs:__imp_RtlInitUnicodeString
0x14001218c  nop     dword ptr [rax+rax+00h]
0x140012191  lea     r9, ?PcwObjectType@@3PEAU_OBJECT_TYPE@@EA; _OBJECT_TYPE * PcwObjectType
0x140012198  xor     r8d, r8d
0x14001219b  lea     rdx, [rbp+57h+var_B0]
0x14001219f  lea     rcx, [rbp+57h+DestinationString]
0x1400121a3  call    cs:__imp_ObCreateObjectType
0x1400121aa  nop     dword ptr [rax+rax+00h]
0x1400121af  mov     ebx, eax
0x1400121b1  test    eax, eax
0x1400121b3  jns     short loc_1400121DE
0x1400121b5  mov     rcx, [rsp+110h+var_F0]
0x1400121ba  call    cs:__imp_ExUnregisterExtension
0x1400121c1  nop     dword ptr [rax+rax+00h]
0x1400121c6  test    byte ptr cs:Microsoft_Windows_Diagnosis_PCWEnableBits, dil
0x1400121cd  jz      loc_140012126
0x1400121d3  mov     r9d, 4
0x1400121d9  jmp     loc_140012117
0x1400121de  xor     eax, eax
0x1400121e0  mov     rcx, [rbp+57h+var_30]
0x1400121e4  xor     rcx, rsp; StackCookie
0x1400121e7  call    __security_check_cookie
0x1400121ec  add     rsp, 0F8h
0x1400121f3  pop     rdi
0x1400121f4  pop     rsi
0x1400121f5  pop     rbx
0x1400121f6  pop     rbp
0x1400121f7  retn
```
