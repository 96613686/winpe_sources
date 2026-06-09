# QuerySystemPartitionValue

- ea: `0x180081260`
- end: `0x180081306`
- name: `QuerySystemPartitionValue`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18007b7d0`

## callees

- `0x180081260`

## import_xrefs

- `ntdll!RtlQueryRegistryValuesEx` at `0x1800812db`
- `ntdll!RtlQueryRegistryValuesEx` at `0x1800812db`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x1800812e9`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x1800812e9`

## string_xrefs

- `0x18008127d`: `SystemPartition`
- `0x1800812a3`: `\Registry\Machine\System\Setup`

## pseudocode

```c
__int64 __fastcall QuerySystemPartitionValue(__int64 a1)
{
  NTSTATUS v1; // eax
  unsigned int v2; // ebx
  _QWORD v4[2]; // [rsp+30h] [rbp-29h] BYREF
  __int64 v5; // [rsp+40h] [rbp-19h] BYREF
  int v6; // [rsp+48h] [rbp-11h]
  const wchar_t *v7; // [rsp+50h] [rbp-9h]
  _QWORD *v8; // [rsp+58h] [rbp-1h]
  int v9; // [rsp+60h] [rbp+7h]
  __int64 v10; // [rsp+68h] [rbp+Fh]
  int v11; // [rsp+70h] [rbp+17h]
  __int64 v12; // [rsp+78h] [rbp+1Fh]
  int v13; // [rsp+80h] [rbp+27h]
  __int64 v14; // [rsp+88h] [rbp+2Fh]
  __int64 v15; // [rsp+90h] [rbp+37h]
  int v16; // [rsp+98h] [rbp+3Fh]
  __int64 v17; // [rsp+A0h] [rbp+47h]
  int v18; // [rsp+A8h] [rbp+4Fh]

  v4[1] = a1;
  v4[0] = 34078720;
  v7 = L"SystemPartition";
  v5 = 0;
  v8 = v4;
  v6 = 48;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v1 = RtlQueryRegistryValuesEx(0, L"\\Registry\\Machine\\System\\Setup", &v5, 0, 0);
  v2 = v1;
  if ( v1 < 0 )
    RtlSetLastWin32ErrorAndNtStatusFromNtStatus(v1);
  return v2;
}

```

## disassembly

```asm
0x180081260  mov     [rsp-8+arg_0], rbx
0x180081265  mov     [rsp-8+arg_8], rdi
0x18008126a  push    rbp
0x18008126b  lea     rbp, [rsp-57h]
0x180081270  sub     rsp, 0B0h
0x180081277  xor     edi, edi
0x180081279  mov     [rbp+57h+var_78], rcx
0x18008127d  lea     rax, aSystempartitio; "SystemPartition"
0x180081284  mov     [rbp+57h+var_80], 2080000h
0x18008128c  mov     [rbp+57h+var_60], rax
0x180081290  lea     r8, [rbp+57h+var_70]
0x180081294  lea     rax, [rbp+57h+var_80]
0x180081298  mov     [rbp+57h+var_70], rdi
0x18008129c  xor     r9d, r9d
0x18008129f  mov     [rbp+57h+var_58], rax
0x1800812a3  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\Setup"
0x1800812aa  mov     [rbp+57h+var_68], 30h ; '0'
0x1800812b1  xor     ecx, ecx
0x1800812b3  mov     [rbp+57h+var_50], edi
0x1800812b6  mov     [rbp+57h+var_48], rdi
0x1800812ba  mov     [rbp+57h+var_40], edi
0x1800812bd  mov     [rbp+57h+var_38], rdi
0x1800812c1  mov     [rbp+57h+var_30], edi
0x1800812c4  mov     [rbp+57h+var_28], rdi
0x1800812c8  mov     [rbp+57h+var_20], rdi
0x1800812cc  mov     [rbp+57h+var_18], edi
0x1800812cf  mov     [rbp+57h+var_10], rdi
0x1800812d3  mov     [rbp+57h+var_8], edi
0x1800812d6  mov     [rsp+0B0h+var_90], rdi
0x1800812db  call    cs:__imp_RtlQueryRegistryValuesEx
0x1800812e1  mov     ebx, eax
0x1800812e3  test    eax, eax
0x1800812e5  jns     short loc_1800812EF
0x1800812e7  mov     ecx, eax; Status
0x1800812e9  call    cs:__imp_RtlSetLastWin32ErrorAndNtStatusFromNtStatus
0x1800812ef  lea     r11, [rsp+0B0h+var_s0]
0x1800812f7  mov     eax, ebx
0x1800812f9  mov     rbx, [r11+10h]
0x1800812fd  mov     rdi, [r11+18h]
0x180081301  mov     rsp, r11
0x180081304  pop     rbp
0x180081305  retn
```
