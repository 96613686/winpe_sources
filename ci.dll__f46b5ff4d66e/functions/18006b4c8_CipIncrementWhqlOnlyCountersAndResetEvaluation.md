# CipIncrementWhqlOnlyCountersAndResetEvaluation

- ea: `0x18006b4c8`
- end: `0x18006b776`
- name: `CipIncrementWhqlOnlyCountersAndResetEvaluation`
- size: `686`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18006bbfc`
- `0x1800e4cb8`

## callees

- `0x18000f3bc`
- `0x18000fb30`
- `0x18001d3a8`
- `0x18002bef0`
- `0x18006b4c8`
- `0x18006bb28`
- `0x18006bc5c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18006b6a4`
- `ntoskrnl!ZwClose` at `0x18006b6a4`
- `ntoskrnl!ZwSetValueKey` at `0x18006b627`
- `ntoskrnl!ZwSetValueKey` at `0x18006b65e`
- `ntoskrnl!ZwSetValueKey` at `0x18006b627`
- `ntoskrnl!ZwSetValueKey` at `0x18006b65e`
- `ntoskrnl!ZwOpenKey` at `0x18006b5cf`
- `ntoskrnl!ZwOpenKey` at `0x18006b5cf`

## string_xrefs

- `0x18006b4f3`: `\Registry\Machine\System\CurrentControlSet\Control\CI\WhqlOnlyEvaluation`

## pseudocode

```c
NTSTATUS __fastcall CipIncrementWhqlOnlyCountersAndResetEvaluation(char a1, char a2, __int64 a3)
{
  NTSTATUS result; // eax
  int v7; // ebx
  __int64 v8; // rcx
  int v9; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  int v11; // [rsp+40h] [rbp-C0h] BYREF
  int v12; // [rsp+44h] [rbp-BCh] BYREF
  _QWORD v13[2]; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING v15; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING v16; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING v17; // [rsp+88h] [rbp-78h] BYREF
  __int64 Data; // [rsp+98h] [rbp-68h] BYREF
  __int64 v19; // [rsp+A0h] [rbp-60h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-58h] BYREF
  char v21[32]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 *v22; // [rsp+100h] [rbp+0h]
  __int64 v23; // [rsp+108h] [rbp+8h]
  int *v24; // [rsp+110h] [rbp+10h]
  __int64 v25; // [rsp+118h] [rbp+18h]
  int *v26; // [rsp+120h] [rbp+20h]
  __int64 v27; // [rsp+128h] [rbp+28h]
  char *v28; // [rsp+130h] [rbp+30h]
  __int64 v29; // [rsp+138h] [rbp+38h]

  KeyHandle = 0;
  v13[0] = 9568400;
  v13[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\CI\\WhqlOnlyEvaluation";
  *(_QWORD *)&ValueName.Length = 1703960;
  ValueName.Buffer = L"SystemUptime";
  *(_QWORD *)&v15.Length = 2097182;
  v15.Buffer = L"NumBootSessions";
  *(_QWORD *)&v16.Length = 1310738;
  v16.Buffer = L"NumAudits";
  v17.Buffer = L"NumBlocks";
  result = 0;
  *(_QWORD *)&v17.Length = 1310738;
  Data = 0;
  v11 = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( a1 || a2 )
  {
    if ( (unsigned int)Feature_Servicing_WhqlOnlyAllowBlockToasts__private_IsEnabledDeviceUsageNoInline() && a2 )
      CipPublishWhqlOnlyBlockWNF(a3);
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v13;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    result = ZwOpenKey(&KeyHandle, 3u, &ObjectAttributes);
    v7 = result;
    if ( result >= 0 )
    {
      if ( !a1
        || (result = ZwSetValueKey(KeyHandle, &ValueName, 0, 0xBu, &Data, 8u), v7 = result, result >= 0)
        && (result = ZwSetValueKey(KeyHandle, &v15, 0, 4u, &v11, 4u), v7 = result, result >= 0)
        && (result = CipPicrootExceptionsIncrementCounterHelper(KeyHandle, &v16), v7 = result, result >= 0) )
      {
        if ( a2 )
        {
          result = CipPicrootExceptionsIncrementCounterHelper(KeyHandle, &v17);
          v7 = result;
        }
      }
    }
    else if ( result == -1073741772 || result == -1073741766 )
    {
      v7 = 0;
    }
    if ( KeyHandle )
      result = ZwClose(KeyHandle);
    if ( v7 < 0 )
    {
      result = dword_1800480F0;
      if ( (unsigned int)dword_1800480F0 > 5 )
      {
        result = tlgKeywordOn(&dword_1800480F0, 0x800000000000LL);
        if ( (_BYTE)result )
        {
          v19 = 0x1000000;
          v22 = &v19;
          v23 = 8;
          v24 = &v12;
          v12 = v7;
          v26 = &v9;
          v25 = 4;
          v28 = (char *)&v9 + 1;
          LOBYTE(v9) = a1;
          v27 = 1;
          BYTE1(v9) = a2;
          v29 = 1;
          return tlgWriteTransfer_EtwWriteTransfer(v8, &byte_18003FB27, 0, 0, 6, v21, v9);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18006b4c8  push    rbp
0x18006b4ca  push    rbx
0x18006b4cb  push    rsi
0x18006b4cc  push    rdi
0x18006b4cd  lea     rbp, [rsp-58h]
0x18006b4d2  sub     rsp, 158h
0x18006b4d9  mov     rax, cs:__security_cookie
0x18006b4e0  xor     rax, rsp
0x18006b4e3  mov     [rbp+70h+var_30], rax
0x18006b4e7  xorps   xmm0, xmm0
0x18006b4ea  mov     [rsp+170h+KeyHandle], 0
0x18006b4f3  lea     rax, aRegistryMachin_11; "\\Registry\\Machine\\System\\CurrentCon"...
0x18006b4fa  mov     [rsp+170h+var_128], 920090h
0x18006b503  mov     [rsp+170h+var_120], rax
0x18006b508  mov     rbx, r8
0x18006b50b  lea     rax, aSystemuptime; "SystemUptime"
0x18006b512  mov     qword ptr [rsp+170h+ValueName.Length], 1A0018h
0x18006b51b  mov     [rsp+170h+ValueName.Buffer], rax
0x18006b520  mov     dil, dl
0x18006b523  lea     rax, aNumbootsession; "NumBootSessions"
0x18006b52a  mov     qword ptr [rsp+170h+var_108.Length], 20001Eh
0x18006b533  mov     [rsp+170h+var_108.Buffer], rax
0x18006b538  mov     sil, cl
0x18006b53b  lea     rax, aNumaudits; "NumAudits"
0x18006b542  mov     qword ptr [rsp+170h+var_F8.Length], 140012h
0x18006b54b  mov     [rbp+70h+var_F8.Buffer], rax
0x18006b54f  lea     rax, aNumblocks; "NumBlocks"
0x18006b556  mov     [rbp+70h+var_E8.Buffer], rax
0x18006b55a  xor     eax, eax
0x18006b55c  mov     qword ptr [rbp+70h+var_E8.Length], 140012h
0x18006b564  mov     [rbp+70h+var_D8], rax
0x18006b568  mov     [rsp+170h+var_130], eax
0x18006b56c  movups  xmmword ptr [rbp+70h+ObjectAttributes.ObjectName], xmm0
0x18006b570  movups  xmmword ptr [rbp+70h+ObjectAttributes.Length], xmm0
0x18006b574  movups  xmmword ptr [rbp+70h+ObjectAttributes+1Ch], xmm0
0x18006b578  test    cl, cl
0x18006b57a  jnz     short loc_18006B584
0x18006b57c  test    dl, dl
0x18006b57e  jz      loc_18006B75D
0x18006b584  call    Feature_Servicing_WhqlOnlyAllowBlockToasts__private_IsEnabledDeviceUsageNoInline
0x18006b589  test    eax, eax
0x18006b58b  jz      short loc_18006B59A
0x18006b58d  test    dil, dil
0x18006b590  jz      short loc_18006B59A
0x18006b592  mov     rcx, rbx
0x18006b595  call    CipPublishWhqlOnlyBlockWNF
0x18006b59a  lea     rax, [rsp+170h+var_128]
0x18006b59f  mov     [rbp+70h+ObjectAttributes.Length], 30h ; '0'
0x18006b5a6  xorps   xmm0, xmm0
0x18006b5a9  mov     [rbp+70h+ObjectAttributes.ObjectName], rax
0x18006b5ad  lea     r8, [rbp+70h+ObjectAttributes]; ObjectAttributes
0x18006b5b1  mov     [rbp+70h+ObjectAttributes.RootDirectory], 0
0x18006b5b9  mov     edx, 3; DesiredAccess
0x18006b5be  mov     [rbp+70h+ObjectAttributes.Attributes], 240h
0x18006b5c5  lea     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x18006b5ca  movdqu  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006b5cf  call    cs:__imp_ZwOpenKey
0x18006b5d6  nop     dword ptr [rax+rax+00h]
0x18006b5db  mov     ebx, eax
0x18006b5dd  test    eax, eax
0x18006b5df  jns     short loc_18006B5FA
0x18006b5e1  cmp     eax, 0C0000034h
0x18006b5e6  jz      short loc_18006B5F3
0x18006b5e8  cmp     eax, 0C000003Ah
0x18006b5ed  jnz     loc_18006B69A
0x18006b5f3  xor     ebx, ebx
0x18006b5f5  jmp     loc_18006B69A
0x18006b5fa  test    sil, sil
0x18006b5fd  jz      loc_18006B685
0x18006b603  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x18006b608  lea     rax, [rbp+70h+var_D8]
0x18006b60c  mov     [rsp+170h+DataSize], 8; DataSize
0x18006b614  lea     rdx, [rsp+170h+ValueName]; ValueName
0x18006b619  mov     r9d, 0Bh; Type
0x18006b61f  mov     [rsp+170h+Data], rax; Data
0x18006b624  xor     r8d, r8d; TitleIndex
0x18006b627  call    cs:__imp_ZwSetValueKey
0x18006b62e  nop     dword ptr [rax+rax+00h]
0x18006b633  mov     ebx, eax
0x18006b635  test    eax, eax
0x18006b637  js      short loc_18006B69A
0x18006b639  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x18006b63e  lea     rax, [rsp+170h+var_130]
0x18006b643  mov     [rsp+170h+DataSize], 4; DataSize
0x18006b64b  lea     rdx, [rsp+170h+var_108]; ValueName
0x18006b650  mov     r9d, 4; Type
0x18006b656  mov     [rsp+170h+Data], rax; Data
0x18006b65b  xor     r8d, r8d; TitleIndex
0x18006b65e  call    cs:__imp_ZwSetValueKey
0x18006b665  nop     dword ptr [rax+rax+00h]
0x18006b66a  mov     ebx, eax
0x18006b66c  test    eax, eax
0x18006b66e  js      short loc_18006B69A
0x18006b670  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x18006b675  lea     rdx, [rsp+170h+var_F8]; ValueName
0x18006b67a  call    CipPicrootExceptionsIncrementCounterHelper
0x18006b67f  mov     ebx, eax
0x18006b681  test    eax, eax
0x18006b683  js      short loc_18006B69A
0x18006b685  test    dil, dil
0x18006b688  jz      short loc_18006B69A
0x18006b68a  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x18006b68f  lea     rdx, [rbp+70h+var_E8]; ValueName
0x18006b693  call    CipPicrootExceptionsIncrementCounterHelper
0x18006b698  mov     ebx, eax
0x18006b69a  mov     rcx, [rsp+170h+KeyHandle]; Handle
0x18006b69f  test    rcx, rcx
0x18006b6a2  jz      short loc_18006B6B0
0x18006b6a4  call    cs:__imp_ZwClose
0x18006b6ab  nop     dword ptr [rax+rax+00h]
0x18006b6b0  test    ebx, ebx
0x18006b6b2  jns     loc_18006B75D
0x18006b6b8  mov     eax, cs:dword_1800480F0
0x18006b6be  cmp     eax, 5
0x18006b6c1  jbe     loc_18006B75D
0x18006b6c7  mov     rdx, 800000000000h
0x18006b6d1  lea     rcx, dword_1800480F0
0x18006b6d8  call    _tlgKeywordOn
0x18006b6dd  test    al, al
0x18006b6df  jz      short loc_18006B75D
0x18006b6e1  lea     rax, [rbp+70h+var_D0]
0x18006b6e5  mov     [rbp+70h+var_D0], 1000000h
0x18006b6ed  mov     [rbp+70h+var_70], rax
0x18006b6f1  lea     rdx, byte_18003FB27
0x18006b6f8  lea     rax, [rsp+170h+var_12C]
0x18006b6fd  mov     [rbp+70h+var_68], 8
0x18006b705  mov     [rbp+70h+var_60], rax
0x18006b709  xor     r9d, r9d
0x18006b70c  lea     rax, [rsp+170h+var_140]
0x18006b711  mov     [rsp+170h+var_12C], ebx
0x18006b715  mov     [rbp+70h+var_50], rax
0x18006b719  xor     r8d, r8d
0x18006b71c  lea     rax, [rsp+170h+var_13F]
0x18006b721  mov     [rbp+70h+var_58], 4
0x18006b729  mov     [rbp+70h+var_40], rax
0x18006b72d  lea     rax, [rbp+70h+var_90]
0x18006b731  mov     qword ptr [rsp+170h+DataSize], rax
0x18006b736  mov     dword ptr [rsp+170h+Data], 6
0x18006b73e  mov     [rsp+170h+var_140], sil
0x18006b743  mov     [rbp+70h+var_48], 1
0x18006b74b  mov     [rsp+170h+var_13F], dil
0x18006b750  mov     [rbp+70h+var_38], 1
0x18006b758  call    _tlgWriteTransfer_EtwWriteTransfer
0x18006b75d  mov     rcx, [rbp+70h+var_30]
0x18006b761  xor     rcx, rsp; StackCookie
0x18006b764  call    __security_check_cookie
0x18006b769  add     rsp, 158h
0x18006b770  pop     rdi
0x18006b771  pop     rsi
0x18006b772  pop     rbx
0x18006b773  pop     rbp
0x18006b774  retn
```
