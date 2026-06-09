# HbEvtpLogSecFwStatus

- ea: `0x1400129f4`
- end: `0x140012ab5`
- name: `HbEvtpLogSecFwStatus`
- size: `193`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000ecd0`
- `0x1400115a0`

## callees

- `0x140002254`
- `0x14000234c`
- `0x1400129f4`
- `0x1400130f8`

## import_xrefs

- `winhvr!WinHvGetSystemInformation` at `0x140012a27`
- `winhvr!WinHvGetSystemInformation` at `0x140012a79`
- `winhvr!WinHvGetSystemInformation` at `0x140012a27`
- `winhvr!WinHvGetSystemInformation` at `0x140012a79`

## pseudocode

```c
__int64 HbEvtpLogSecFwStatus()
{
  __int64 result; // rax
  __int64 v1; // rdx
  __int64 v2; // rcx
  __int64 v3; // r8
  int v4; // edi
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // rbx
  int v9; // [rsp+40h] [rbp+8h] BYREF
  __int64 v10; // [rsp+48h] [rbp+10h] BYREF

  v9 = 15;
  v10 = 0;
  result = WinHvGetSystemInformation(3, &v9, 4, &v10, 8, 0);
  if ( (int)result >= 0 )
  {
    v4 = v10;
    if ( (_DWORD)v10 )
    {
      if ( (Microsoft_Windows_Hyper_V_HypervisorEnableBits & 0x10) != 0 )
        McTemplateK0q_EtwWriteTransfer(v2, v1, v3, (unsigned int)v10);
      v9 = 14;
      result = WinHvGetSystemInformation(3, &v9, 4, &v10, 8, 0);
      if ( (int)result >= 0 )
      {
        v8 = v10;
        if ( (Microsoft_Windows_Hyper_V_HypervisorEnableBits & 0x10) != 0 )
          McTemplateK0x_EtwWriteTransfer(v6, v5, v7, v10);
        return HbEvtpSecFwUpdateRegistry(v4, v8);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400129f4  mov     rax, rsp
0x1400129f7  mov     [rax+18h], rbx
0x1400129fb  push    rdi
0x1400129fc  sub     rsp, 30h
0x140012a00  xor     ebx, ebx
0x140012a02  mov     dword ptr [rax+8], 0Fh
0x140012a09  mov     [rax-10h], rbx
0x140012a0d  lea     r9, [rax+10h]
0x140012a11  lea     rdx, [rax+8]
0x140012a15  mov     [rax+10h], rbx
0x140012a19  mov     dword ptr [rax-18h], 8
0x140012a20  lea     r8d, [rbx+4]
0x140012a24  lea     ecx, [rbx+3]
0x140012a27  call    cs:__imp_WinHvGetSystemInformation
0x140012a2e  nop     dword ptr [rax+rax+00h]
0x140012a33  test    eax, eax
0x140012a35  js      short loc_140012AA9
0x140012a37  mov     edi, dword ptr [rsp+38h+arg_8]
0x140012a3b  test    edi, edi
0x140012a3d  jz      short loc_140012AA9
0x140012a3f  test    cs:Microsoft_Windows_Hyper_V_HypervisorEnableBits, 10h
0x140012a46  jz      short loc_140012A50
0x140012a48  mov     r9d, edi
0x140012a4b  call    McTemplateK0q_EtwWriteTransfer
0x140012a50  mov     r8d, 4
0x140012a56  mov     [rsp+38h+var_10], rbx
0x140012a5b  lea     r9, [rsp+38h+arg_8]
0x140012a60  mov     [rsp+38h+arg_0], 0Eh
0x140012a68  lea     rdx, [rsp+38h+arg_0]
0x140012a6d  mov     [rsp+38h+var_18], 8
0x140012a75  lea     ecx, [r8-1]
0x140012a79  call    cs:__imp_WinHvGetSystemInformation
0x140012a80  nop     dword ptr [rax+rax+00h]
0x140012a85  test    eax, eax
0x140012a87  js      short loc_140012AA9
0x140012a89  test    cs:Microsoft_Windows_Hyper_V_HypervisorEnableBits, 10h
0x140012a90  mov     rbx, [rsp+38h+arg_8]
0x140012a95  jz      short loc_140012A9F
0x140012a97  mov     r9, rbx
0x140012a9a  call    McTemplateK0x_EtwWriteTransfer
0x140012a9f  mov     rdx, rbx
0x140012aa2  mov     ecx, edi
0x140012aa4  call    HbEvtpSecFwUpdateRegistry
0x140012aa9  mov     rbx, [rsp+38h+arg_10]
0x140012aae  add     rsp, 30h
0x140012ab2  pop     rdi
0x140012ab3  retn
```
