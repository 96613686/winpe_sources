# CscRebootRenameAddEntry

- ea: `0x1400522a4`
- end: `0x14005246a`
- name: `CscRebootRenameAddEntry`
- size: `454`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x140019abc`

## callees

- `0x1400179f8`
- `0x1400190ec`
- `0x1400235b0`
- `0x1400522a4`
- `0x1400526cc`
- `0x140052e44`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14005240c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005240c`
- `ntoskrnl!ZwClose` at `0x1400523b0`
- `ntoskrnl!ZwClose` at `0x1400523f7`
- `ntoskrnl!ZwClose` at `0x1400523b0`
- `ntoskrnl!ZwClose` at `0x1400523f7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400523c2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400523c2`
- `ntoskrnl!ZwDeleteKey` at `0x1400523a0`
- `ntoskrnl!ZwDeleteKey` at `0x1400523a0`

## string_xrefs

- `0x1400522d3`: `\Registry\Machine\System\CurrentControlSet\Services\CSC\Parameters`
- `0x14005236c`: `\Registry\Machine\System\CurrentControlSet\Services\CSC\Parameters\FailedRebootRename`
- `0x1400522bd`: `\Registry\Machine\System\CurrentControlSet\Services\CSC\Parameters\RebootRename`

## pseudocode

```c
__int64 __fastcall CscRebootRenameAddEntry(struct _ERESOURCE *a1, __int64 a2, __int64 a3)
{
  char v6; // r15
  int IsValidRename; // ebx
  int v8; // edi
  HANDLE Handle; // [rsp+30h] [rbp-40h] BYREF
  struct _UNICODE_STRING v11; // [rsp+38h] [rbp-38h] BYREF
  struct _UNICODE_STRING v12; // [rsp+48h] [rbp-28h] BYREF
  _QWORD v13[3]; // [rsp+58h] [rbp-18h] BYREF
  HANDLE KeyHandle; // [rsp+B8h] [rbp+48h] BYREF

  v13[0] = 10485918;
  v13[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\CSC\\Parameters\\RebootRename";
  Handle = 0;
  v11.Buffer = (PWSTR)L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\CSC\\Parameters";
  *(_QWORD *)&v11.Length = 8781956;
  v6 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_ZZ(
      WPP_GLOBAL_Control->AttachedDevice,
      21,
      (unsigned int)WPP_ff5744e1daca33e6b91278fb9c763f73_Traceguids,
      a2,
      a3);
  IsValidRename = CscStoreRebootRenameIsValidRename(a2, a3);
  if ( IsValidRename >= 0 )
  {
    IsValidRename = CscRebootRenamepOpenKey(&Handle, &v11, 1, 0);
    if ( IsValidRename >= 0 )
    {
      *(_QWORD *)&v12.Length = 11272362;
      v8 = 0;
      v12.Buffer = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\CSC\\Parameters\\FailedRebootRename";
      KeyHandle = 0;
      if ( (int)CscRebootRenamepOpenKey(&KeyHandle, &v12, 0, 0) >= 0 )
      {
        ZwDeleteKey(KeyHandle);
        ZwClose(KeyHandle);
      }
      ExAcquireResourceExclusiveLite(a1 + 1, 1u);
      v6 = 1;
      IsValidRename = CscRebootRenamepAddToKey((unsigned int)v13, 0, 0, a2, a3, 0);
    }
    else
    {
      v8 = 1428;
    }
  }
  else
  {
    v8 = 1419;
  }
  if ( Handle )
    ZwClose(Handle);
  if ( v6 )
    ExReleaseResourceLite(a1 + 1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      22,
      WPP_ff5744e1daca33e6b91278fb9c763f73_Traceguids,
      (unsigned int)IsValidRename,
      v8);
  return (unsigned int)IsValidRename;
}

```

## disassembly

```asm
0x1400522a4  mov     [rsp-28h+arg_0], rbx
0x1400522a9  mov     [rsp-28h+arg_8], rsi
0x1400522ae  push    rbp
0x1400522af  push    rdi
0x1400522b0  push    r13
0x1400522b2  push    r14
0x1400522b4  push    r15
0x1400522b6  mov     rbp, rsp
0x1400522b9  sub     rsp, 70h
0x1400522bd  lea     rax, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400522c4  mov     [rbp+var_18], 0A0009Eh
0x1400522cc  mov     [rbp+var_10], rax
0x1400522d0  mov     rsi, r8
0x1400522d3  lea     rax, SourceString; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400522da  mov     [rbp+Handle], 0
0x1400522e2  mov     [rbp+var_30], rax
0x1400522e6  mov     r14, rdx
0x1400522e9  mov     r13, rcx
0x1400522ec  mov     [rbp+var_38], 860084h
0x1400522f4  xor     r15b, r15b
0x1400522f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400522fe  lea     rax, WPP_GLOBAL_Control
0x140052305  cmp     rcx, rax
0x140052308  jz      short loc_14005232E
0x14005230a  mov     eax, [rcx+2Ch]
0x14005230d  test    al, 40h
0x14005230f  jz      short loc_14005232E
0x140052311  mov     rcx, [rcx+18h]
0x140052315  mov     edx, 15h
0x14005231a  mov     [rsp+70h+var_50], r8
0x14005231f  mov     r9, r14
0x140052322  lea     r8, WPP_ff5744e1daca33e6b91278fb9c763f73_Traceguids
0x140052329  call    WPP_SF_ZZ
0x14005232e  mov     rdx, rsi
0x140052331  mov     rcx, r14
0x140052334  call    CscStoreRebootRenameIsValidRename
0x140052339  mov     ebx, eax
0x14005233b  test    eax, eax
0x14005233d  jns     short loc_140052349
0x14005233f  mov     edi, 58Bh
0x140052344  jmp     loc_1400523EE
0x140052349  xor     r9d, r9d
0x14005234c  lea     rdx, [rbp+var_38]
0x140052350  mov     r8b, 1
0x140052353  lea     rcx, [rbp+Handle]; KeyHandle
0x140052357  call    CscRebootRenamepOpenKey
0x14005235c  mov     ebx, eax
0x14005235e  test    eax, eax
0x140052360  jns     short loc_14005236C
0x140052362  mov     edi, 594h
0x140052367  jmp     loc_1400523EE
0x14005236c  lea     rax, aRegistryMachin_1; "\\Registry\\Machine\\System\\CurrentCon"...
0x140052373  mov     [rbp+var_28], 0AC00AAh
0x14005237b  xor     edi, edi
0x14005237d  mov     [rbp+var_20], rax
0x140052381  xor     r9d, r9d
0x140052384  mov     [rbp+KeyHandle], rdi
0x140052388  xor     r8d, r8d
0x14005238b  lea     rdx, [rbp+var_28]
0x14005238f  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140052393  call    CscRebootRenamepOpenKey
0x140052398  test    eax, eax
0x14005239a  js      short loc_1400523BC
0x14005239c  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1400523a0  call    cs:__imp_ZwDeleteKey
0x1400523a7  nop     dword ptr [rax+rax+00h]
0x1400523ac  mov     rcx, [rbp+KeyHandle]; Handle
0x1400523b0  call    cs:__imp_ZwClose
0x1400523b7  nop     dword ptr [rax+rax+00h]
0x1400523bc  lea     rcx, [r13+68h]; Resource
0x1400523c0  mov     dl, 1; Wait
0x1400523c2  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400523c9  nop     dword ptr [rax+rax+00h]
0x1400523ce  mov     r9, r14
0x1400523d1  mov     [rsp+70h+var_48], rdi
0x1400523d6  xor     r8d, r8d
0x1400523d9  mov     [rsp+70h+var_50], rsi
0x1400523de  xor     edx, edx
0x1400523e0  lea     rcx, [rbp+var_18]
0x1400523e4  mov     r15b, 1
0x1400523e7  call    CscRebootRenamepAddToKey
0x1400523ec  mov     ebx, eax
0x1400523ee  mov     rcx, [rbp+Handle]; Handle
0x1400523f2  test    rcx, rcx
0x1400523f5  jz      short loc_140052403
0x1400523f7  call    cs:__imp_ZwClose
0x1400523fe  nop     dword ptr [rax+rax+00h]
0x140052403  test    r15b, r15b
0x140052406  jz      short loc_140052418
0x140052408  lea     rcx, [r13+68h]; Resource
0x14005240c  call    cs:__imp_ExReleaseResourceLite
0x140052413  nop     dword ptr [rax+rax+00h]
0x140052418  mov     rcx, cs:WPP_GLOBAL_Control
0x14005241f  lea     rax, WPP_GLOBAL_Control
0x140052426  cmp     rcx, rax
0x140052429  jz      short loc_14005244E
0x14005242b  mov     eax, [rcx+2Ch]
0x14005242e  test    al, 40h
0x140052430  jz      short loc_14005244E
0x140052432  mov     rcx, [rcx+18h]
0x140052436  lea     r8, WPP_ff5744e1daca33e6b91278fb9c763f73_Traceguids
0x14005243d  mov     edx, 16h
0x140052442  mov     dword ptr [rsp+70h+var_50], edi
0x140052446  mov     r9d, ebx
0x140052449  call    WPP_SF_Dd
0x14005244e  lea     r11, [rsp+70h+var_s0]
0x140052453  mov     eax, ebx
0x140052455  mov     rbx, [r11+30h]
0x140052459  mov     rsi, [r11+38h]
0x14005245d  mov     rsp, r11
0x140052460  pop     r15
0x140052462  pop     r14
0x140052464  pop     r13
0x140052466  pop     rdi
0x140052467  pop     rbp
0x140052468  retn
```
