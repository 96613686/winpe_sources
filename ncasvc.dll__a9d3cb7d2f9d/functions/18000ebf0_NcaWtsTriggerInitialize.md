# NcaWtsTriggerInitialize

- ea: `0x18000ebf0`
- end: `0x18000edb4`
- name: `NcaWtsTriggerInitialize`
- size: `452`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004e54`
- `0x180004f04`
- `0x180004f34`
- `0x180006544`
- `0x1800065c8`
- `0x18000b488`
- `0x18000ebf0`
- `0x18000edc0`
- `0x18001cc3e`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ec6f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ec6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec89`

## pseudocode

```c
__int64 NcaWtsTriggerInitialize()
{
  PVOID v0; // rcx
  unsigned int v1; // ebx
  DWORD LastError; // eax
  int v3; // edi
  PVOID v4; // rcx
  int v5; // eax
  unsigned int v6; // eax

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_4f36e67baeb930cfe336c8f232ca1ef1_Traceguids);
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer((__int64)v0, (const EVENT_DESCRIPTOR *)ModuleInitializeStart, L"WtsTrigger");
  memset_0(&gNcaWtsTriggerComp, 0, 0x58u);
  dword_180028E58 = 2;
  qword_180028E60 = CreateEventW(0, 1, 0, 0);
  if ( !qword_180028E60 )
  {
    v1 = 0;
    LastError = GetLastError();
    v3 = LastError;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_4f36e67baeb930cfe336c8f232ca1ef1_Traceguids, LastError);
    goto LABEL_10;
  }
  v5 = NcaSyncedListCreate((__int64)&stru_180028E18);
  v1 = v5;
  if ( v5 >= 0 )
  {
    v6 = NcaServiceAcceptWtsSessionChange();
    v3 = v6;
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_4f36e67baeb930cfe336c8f232ca1ef1_Traceguids, v6);
        NcaWtsTriggerShutdown();
LABEL_12:
        if ( v3 > 0 )
          v1 = (unsigned __int16)v3 | 0x80070000;
        else
          v1 = v3;
        goto LABEL_24;
      }
LABEL_11:
      NcaWtsTriggerShutdown();
      if ( !v3 )
        goto LABEL_24;
      goto LABEL_12;
    }
LABEL_10:
    if ( !v3 )
      goto LABEL_24;
    goto LABEL_11;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_4f36e67baeb930cfe336c8f232ca1ef1_Traceguids, (unsigned int)v5);
  NcaWtsTriggerShutdown();
LABEL_24:
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0zx_EventWriteTransfer(
      (__int64)v4,
      (const EVENT_DESCRIPTOR *)ModuleInitializeEnd,
      L"WtsTrigger",
      (int)v1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_4f36e67baeb930cfe336c8f232ca1ef1_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x18000ebf0  push    rbx
0x18000ebf2  push    rbp
0x18000ebf3  push    rdi
0x18000ebf4  push    r14
0x18000ebf6  sub     rsp, 28h
0x18000ebfa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec01  lea     rbp, WPP_GLOBAL_Control
0x18000ec08  lea     r14, WPP_4f36e67baeb930cfe336c8f232ca1ef1_Traceguids
0x18000ec0f  cmp     rcx, rbp
0x18000ec12  jz      short loc_18000EC2B
0x18000ec14  test    byte ptr [rcx+1Ch], 8
0x18000ec18  jz      short loc_18000EC2B
0x18000ec1a  mov     rcx, [rcx+10h]
0x18000ec1e  mov     edx, 0Ch
0x18000ec23  mov     r8, r14
0x18000ec26  call    WPP_SF_
0x18000ec2b  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x18000ec32  jz      short loc_18000EC47
0x18000ec34  lea     r8, aWtstrigger; "WtsTrigger"
0x18000ec3b  lea     rdx, ModuleInitializeStart
0x18000ec42  call    McTemplateU0z_EventWriteTransfer
0x18000ec47  xor     edx, edx; Val
0x18000ec49  lea     rcx, ?gNcaWtsTriggerComp@@3UNCA_WTS_TRIGGER_COMP_@@A; void *
0x18000ec50  lea     r8d, [rdx+58h]; Size
0x18000ec54  call    memset_0
0x18000ec59  xor     r9d, r9d; lpName
0x18000ec5c  mov     cs:dword_180028E58, 2
0x18000ec66  xor     r8d, r8d; bInitialState
0x18000ec69  xor     ecx, ecx; lpEventAttributes
0x18000ec6b  lea     edx, [r9+1]; bManualReset
0x18000ec6f  call    cs:__imp_CreateEventW
0x18000ec76  nop     dword ptr [rax+rax+00h]
0x18000ec7b  mov     cs:qword_180028E60, rax
0x18000ec82  test    rax, rax
0x18000ec85  jnz     short loc_18000ECDF
0x18000ec87  xor     ebx, ebx
0x18000ec89  call    cs:__imp_GetLastError
0x18000ec90  nop     dword ptr [rax+rax+00h]
0x18000ec95  mov     edi, eax
0x18000ec97  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec9e  cmp     rcx, rbp
0x18000eca1  jz      short loc_18000ECBB
0x18000eca3  test    byte ptr [rcx+1Ch], 1
0x18000eca7  jz      short loc_18000ECBB
0x18000eca9  mov     rcx, [rcx+10h]
0x18000ecad  lea     edx, [rbx+0Dh]
0x18000ecb0  mov     r9d, eax
0x18000ecb3  mov     r8, r14
0x18000ecb6  call    WPP_SF_d
0x18000ecbb  test    edi, edi
0x18000ecbd  jz      loc_18000ED62
0x18000ecc3  call    NcaWtsTriggerShutdown
0x18000ecc8  test    edi, edi
0x18000ecca  jz      loc_18000ED62
0x18000ecd0  test    edi, edi
0x18000ecd2  jg      loc_18000ED59
0x18000ecd8  mov     ebx, edi
0x18000ecda  jmp     loc_18000ED62
0x18000ecdf  lea     rcx, stru_180028E18
0x18000ece6  call    NcaSyncedListCreate
0x18000eceb  mov     ebx, eax
0x18000eced  test    eax, eax
0x18000ecef  jns     short loc_18000ED1E
0x18000ecf1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ecf8  cmp     rcx, rbp
0x18000ecfb  jz      short loc_18000ED17
0x18000ecfd  test    byte ptr [rcx+1Ch], 1
0x18000ed01  jz      short loc_18000ED17
0x18000ed03  mov     rcx, [rcx+10h]
0x18000ed07  mov     edx, 0Eh
0x18000ed0c  mov     r9d, eax
0x18000ed0f  mov     r8, r14
0x18000ed12  call    WPP_SF_d
0x18000ed17  call    NcaWtsTriggerShutdown
0x18000ed1c  jmp     short loc_18000ED62
0x18000ed1e  call    NcaServiceAcceptWtsSessionChange
0x18000ed23  mov     edi, eax
0x18000ed25  test    eax, eax
0x18000ed27  jz      short loc_18000ECBB
0x18000ed29  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed30  cmp     rcx, rbp
0x18000ed33  jz      short loc_18000ECC3
0x18000ed35  test    byte ptr [rcx+1Ch], 1
0x18000ed39  jz      short loc_18000ECC3
0x18000ed3b  mov     rcx, [rcx+10h]
0x18000ed3f  mov     edx, 0Fh
0x18000ed44  mov     r9d, eax
0x18000ed47  mov     r8, r14
0x18000ed4a  call    WPP_SF_d
0x18000ed4f  call    NcaWtsTriggerShutdown
0x18000ed54  jmp     loc_18000ECD0
0x18000ed59  movzx   ebx, di
0x18000ed5c  or      ebx, 80070000h
0x18000ed62  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x18000ed69  jz      short loc_18000ED81
0x18000ed6b  movsxd  r9, ebx
0x18000ed6e  lea     r8, aWtstrigger; "WtsTrigger"
0x18000ed75  lea     rdx, ModuleInitializeEnd
0x18000ed7c  call    McTemplateU0zx_EventWriteTransfer
0x18000ed81  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed88  cmp     rcx, rbp
0x18000ed8b  jz      short loc_18000EDA7
0x18000ed8d  test    byte ptr [rcx+1Ch], 8
0x18000ed91  jz      short loc_18000EDA7
0x18000ed93  mov     rcx, [rcx+10h]
0x18000ed97  mov     edx, 10h
0x18000ed9c  mov     r9d, ebx
0x18000ed9f  mov     r8, r14
0x18000eda2  call    WPP_SF_d
0x18000eda7  mov     eax, ebx
0x18000eda9  add     rsp, 28h
0x18000edad  pop     r14
0x18000edaf  pop     rdi
0x18000edb0  pop     rbp
0x18000edb1  pop     rbx
0x18000edb2  retn
```
