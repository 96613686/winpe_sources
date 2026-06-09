# LuafvReadSettings

- ea: `0x140028714`
- end: `0x1400289f2`
- name: `LuafvReadSettings`
- size: `734`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x1400291a8`

## callees

- `0x140005f30`
- `0x1400143e8`
- `0x140014b1c`
- `0x140028714`
- `0x140029784`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x140028999`
- `ntoskrnl!EtwWrite` at `0x140028999`
- `ntoskrnl!ZwClose` at `0x14002878b`
- `ntoskrnl!ZwClose` at `0x1400289ba`
- `ntoskrnl!ZwClose` at `0x1400289d0`
- `ntoskrnl!ZwClose` at `0x14002a280`
- `ntoskrnl!ZwClose` at `0x14002a296`
- `ntoskrnl!ZwClose` at `0x14002878b`
- `ntoskrnl!ZwClose` at `0x1400289ba`
- `ntoskrnl!ZwClose` at `0x1400289d0`
- `ntoskrnl!ZwClose` at `0x14002a280`
- `ntoskrnl!ZwClose` at `0x14002a296`

## pseudocode

```c
__int64 __fastcall LuafvReadSettings(struct _UNICODE_STRING *a1)
{
  NTSTATUS v1; // ebx
  int FileTable; // eax
  int v4; // [rsp+30h] [rbp-48h] BYREF
  NTSTATUS v5; // [rsp+38h] [rbp-40h]
  HANDLE KeyHandle; // [rsp+40h] [rbp-38h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-30h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-28h] BYREF

  v4 = 0;
  Handle = 0;
  KeyHandle = 0;
  v1 = LuafvOpenKey(0, a1, &Handle);
  v5 = v1;
  if ( v1 < 0 )
  {
    Handle = 0;
    goto LABEL_30;
  }
  v1 = LuafvOpenKey(Handle, (struct _UNICODE_STRING *)&LuafvSettingsKeyName, &KeyHandle);
  v5 = v1;
  ZwClose(Handle);
  Handle = 0;
  if ( v1 < 0 )
  {
    KeyHandle = 0;
    goto LABEL_30;
  }
  v5 = LuafvReadDwordValue(KeyHandle, (struct _UNICODE_STRING *)LuafvAccessDeniedMaskValueName, &v4);
  if ( v5 >= 0 )
  {
    if ( (v4 & 0xFFF2FEA9) != 0 )
      goto LABEL_29;
    dword_14000F110 = v4;
  }
  else
  {
    dword_14000F110 = 786774;
  }
  v5 = LuafvReadDwordValue(KeyHandle, (struct _UNICODE_STRING *)LuafvEnableDelayedVirtualizationValueName, &v4);
  byte_14000F11C = v5 < 0 || v4 != 0;
  v5 = LuafvReadDwordValue(KeyHandle, (struct _UNICODE_STRING *)LuafvEnableExtensionBasedExclusionValueName, &v4);
  byte_14000F11D = v5 < 0 || v4 != 0;
  v5 = LuafvReadDwordValue(KeyHandle, (struct _UNICODE_STRING *)LuafvDisableStaticInclusionValueName, &v4);
  if ( v5 >= 0 )
    byte_14000F11E = v4 != 0;
  v5 = LuafvReadDwordValue(KeyHandle, (struct _UNICODE_STRING *)LuafvPoolAllocationLimitValueName, &v4);
  if ( v5 >= 0 )
  {
    if ( v4 < 0x40000 )
      goto LABEL_29;
    dword_14000F300 = v4;
  }
  else
  {
    dword_14000F300 = 0x400000;
  }
  v5 = LuafvReadDwordValue(KeyHandle, (struct _UNICODE_STRING *)&LuafvCallControlValueName, &v4);
  if ( v5 < 0 )
    goto LABEL_24;
  if ( (v4 & 0xFFFFFFF8) != 0 )
  {
LABEL_29:
    v1 = -1073741811;
    v5 = -1073741811;
    goto LABEL_30;
  }
  dword_14000F114 = v4;
LABEL_24:
  v5 = LuafvReadDwordValue(KeyHandle, (struct _UNICODE_STRING *)&LuafvLogControlValueName, &v4);
  if ( v5 >= 0 )
    dword_14000F118 = v4;
  else
    dword_14000F118 = 7;
  FileTable = LuafvReadFileTable(KeyHandle);
  v1 = FileTable;
  v5 = FileTable;
  if ( FileTable < 0 )
  {
    v4 = FileTable;
    UserData.Ptr = (ULONGLONG)&v4;
    *(_QWORD *)&UserData.Size = 4;
    EtwWrite(qword_14000F120, &LuafvReadFileListFailed, 0, 1u, &UserData);
  }
LABEL_30:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140028714  push    rbx
0x140028716  sub     rsp, 70h
0x14002871a  mov     rax, cs:__security_cookie
0x140028721  xor     rax, rsp
0x140028724  mov     [rsp+78h+var_18], rax
0x140028729  mov     [rsp+78h+var_48], 0
0x140028731  mov     [rsp+78h+Handle], 0
0x14002873a  mov     [rsp+78h+KeyHandle], 0
0x140028743  lea     r8, [rsp+78h+Handle]
0x140028748  mov     rdx, rcx
0x14002874b  xor     ecx, ecx
0x14002874d  call    LuafvOpenKey
0x140028752  mov     ebx, eax
0x140028754  mov     [rsp+78h+var_40], eax
0x140028758  test    eax, eax
0x14002875a  jns     short loc_14002876A
0x14002875c  mov     [rsp+78h+Handle], 0
0x140028765  jmp     loc_1400289B0
0x14002876a  lea     r8, [rsp+78h+KeyHandle]
0x14002876f  lea     rdx, LuafvSettingsKeyName
0x140028776  mov     rcx, [rsp+78h+Handle]
0x14002877b  call    LuafvOpenKey
0x140028780  mov     ebx, eax
0x140028782  mov     [rsp+78h+var_40], eax
0x140028786  mov     rcx, [rsp+78h+Handle]; Handle
0x14002878b  call    cs:__imp_ZwClose
0x140028792  nop     dword ptr [rax+rax+00h]
0x140028797  mov     [rsp+78h+Handle], 0
0x1400287a0  test    ebx, ebx
0x1400287a2  jns     short loc_1400287B2
0x1400287a4  mov     [rsp+78h+KeyHandle], 0
0x1400287ad  jmp     loc_1400289B0
0x1400287b2  lea     r8, [rsp+78h+var_48]
0x1400287b7  lea     rdx, LuafvAccessDeniedMaskValueName; " \""
0x1400287be  mov     rcx, [rsp+78h+KeyHandle]
0x1400287c3  call    LuafvReadDwordValue
0x1400287c8  mov     [rsp+78h+var_40], eax
0x1400287cc  test    eax, eax
0x1400287ce  jns     short loc_1400287DC
0x1400287d0  mov     cs:dword_14000F110, 0C0156h
0x1400287da  jmp     short loc_1400287F1
0x1400287dc  mov     eax, [rsp+78h+var_48]
0x1400287e0  test    eax, 0FFF2FEA9h
0x1400287e5  jnz     loc_1400289A7
0x1400287eb  mov     cs:dword_14000F110, eax
0x1400287f1  lea     r8, [rsp+78h+var_48]
0x1400287f6  lea     rdx, LuafvEnableDelayedVirtualizationValueName; "68"
0x1400287fd  mov     rcx, [rsp+78h+KeyHandle]
0x140028802  call    LuafvReadDwordValue
0x140028807  mov     [rsp+78h+var_40], eax
0x14002880b  test    eax, eax
0x14002880d  js      short loc_14002881D
0x14002880f  cmp     [rsp+78h+var_48], 0
0x140028814  setnz   cs:byte_14000F11C
0x14002881b  jmp     short loc_140028824
0x14002881d  mov     cs:byte_14000F11C, 1
0x140028824  lea     r8, [rsp+78h+var_48]
0x140028829  lea     rdx, LuafvEnableExtensionBasedExclusionValueName; ":<"
0x140028830  mov     rcx, [rsp+78h+KeyHandle]
0x140028835  call    LuafvReadDwordValue
0x14002883a  mov     [rsp+78h+var_40], eax
0x14002883e  test    eax, eax
0x140028840  js      short loc_140028850
0x140028842  cmp     [rsp+78h+var_48], 0
0x140028847  setnz   cs:byte_14000F11D
0x14002884e  jmp     short loc_140028857
0x140028850  mov     cs:byte_14000F11D, 1
0x140028857  lea     r8, [rsp+78h+var_48]
0x14002885c  lea     rdx, LuafvDisableStaticInclusionValueName; ",."
0x140028863  mov     rcx, [rsp+78h+KeyHandle]
0x140028868  call    LuafvReadDwordValue
0x14002886d  mov     [rsp+78h+var_40], eax
0x140028871  test    eax, eax
0x140028873  js      short loc_140028881
0x140028875  cmp     [rsp+78h+var_48], 0
0x14002887a  setnz   cs:byte_14000F11E
0x140028881  lea     r8, [rsp+78h+var_48]
0x140028886  lea     rdx, LuafvPoolAllocationLimitValueName; "&("
0x14002888d  mov     rcx, [rsp+78h+KeyHandle]
0x140028892  call    LuafvReadDwordValue
0x140028897  mov     [rsp+78h+var_40], eax
0x14002889b  test    eax, eax
0x14002889d  jns     short loc_1400288AB
0x14002889f  mov     cs:dword_14000F300, 400000h
0x1400288a9  jmp     short loc_1400288C0
0x1400288ab  mov     eax, [rsp+78h+var_48]
0x1400288af  cmp     eax, 40000h
0x1400288b4  jl      loc_1400289A7
0x1400288ba  mov     cs:dword_14000F300, eax
0x1400288c0  lea     r8, [rsp+78h+var_48]
0x1400288c5  lea     rdx, LuafvCallControlValueName
0x1400288cc  mov     rcx, [rsp+78h+KeyHandle]
0x1400288d1  call    LuafvReadDwordValue
0x1400288d6  mov     [rsp+78h+var_40], eax
0x1400288da  test    eax, eax
0x1400288dc  js      short loc_1400288F3
0x1400288de  mov     eax, [rsp+78h+var_48]
0x1400288e2  test    eax, 0FFFFFFF8h
0x1400288e7  jnz     loc_1400289A7
0x1400288ed  mov     cs:dword_14000F114, eax
0x1400288f3  lea     r8, [rsp+78h+var_48]
0x1400288f8  lea     rdx, LuafvLogControlValueName
0x1400288ff  mov     rcx, [rsp+78h+KeyHandle]
0x140028904  call    LuafvReadDwordValue
0x140028909  mov     [rsp+78h+var_40], eax
0x14002890d  test    eax, eax
0x14002890f  jns     short loc_14002893B
0x140028911  mov     cs:dword_14000F118, 0
0x14002891b  mov     cs:dword_14000F118, 1
0x140028925  mov     cs:dword_14000F118, 3
0x14002892f  mov     cs:dword_14000F118, 7
0x140028939  jmp     short loc_140028945
0x14002893b  mov     eax, [rsp+78h+var_48]
0x14002893f  mov     cs:dword_14000F118, eax
0x140028945  mov     rcx, [rsp+78h+KeyHandle]; KeyHandle
0x14002894a  call    LuafvReadFileTable
0x14002894f  mov     ebx, eax
0x140028951  mov     [rsp+78h+var_40], eax
0x140028955  test    eax, eax
0x140028957  jns     short loc_1400289B0
0x140028959  mov     [rsp+78h+var_48], eax
0x14002895d  xorps   xmm0, xmm0
0x140028960  movups  xmmword ptr [rsp+78h+var_28.Ptr], xmm0
0x140028965  lea     rax, [rsp+78h+var_48]
0x14002896a  mov     [rsp+78h+var_28.Ptr], rax
0x14002896f  mov     qword ptr [rsp+78h+var_28.Size], 4
0x140028978  lea     rax, [rsp+78h+var_28]
0x14002897d  mov     [rsp+78h+UserData], rax; UserData
0x140028982  mov     r9d, 1; UserDataCount
0x140028988  xor     r8d, r8d; ActivityId
0x14002898b  lea     rdx, LuafvReadFileListFailed; EventDescriptor
0x140028992  mov     rcx, cs:qword_14000F120; RegHandle
0x140028999  call    cs:__imp_EtwWrite
0x1400289a0  nop     dword ptr [rax+rax+00h]
0x1400289a5  jmp     short loc_1400289B0
0x1400289a7  mov     ebx, 0C000000Dh
0x1400289ac  mov     [rsp+78h+var_40], ebx
0x1400289b0  mov     rcx, [rsp+78h+KeyHandle]; Handle
0x1400289b5  test    rcx, rcx
0x1400289b8  jz      short loc_1400289C6
0x1400289ba  call    cs:__imp_ZwClose
0x1400289c1  nop     dword ptr [rax+rax+00h]
0x1400289c6  mov     rcx, [rsp+78h+Handle]; Handle
0x1400289cb  test    rcx, rcx
0x1400289ce  jz      short loc_1400289DC
0x1400289d0  call    cs:__imp_ZwClose
0x1400289d7  nop     dword ptr [rax+rax+00h]
0x1400289dc  mov     eax, ebx
0x1400289de  mov     rcx, [rsp+78h+var_18]
0x1400289e3  xor     rcx, rsp; StackCookie
0x1400289e6  call    __security_check_cookie
0x1400289eb  add     rsp, 70h
0x1400289ef  pop     rbx
0x1400289f0  retn
0x14002a26e  push    rbp
0x14002a270  sub     rsp, 30h
0x14002a274  mov     rbp, rdx
0x14002a277  mov     rcx, [rbp+40h]; Handle
0x14002a27b  test    rcx, rcx
0x14002a27e  jz      short loc_14002A28D
0x14002a280  call    cs:__imp_ZwClose
0x14002a287  nop     dword ptr [rax+rax+00h]
0x14002a28c  nop
0x14002a28d  mov     rcx, [rbp+48h]; Handle
0x14002a291  test    rcx, rcx
0x14002a294  jz      short loc_14002A2A3
0x14002a296  call    cs:__imp_ZwClose
0x14002a29d  nop     dword ptr [rax+rax+00h]
0x14002a2a2  nop
0x14002a2a3  add     rsp, 30h
0x14002a2a7  pop     rbp
0x14002a2a8  retn
```
