# Windows::Compat::Inventory::GetMoreData::CaptureAmiCache(void)

- ea: `0x14000dbdc`
- end: `0x14000dc8e`
- name: `?CaptureAmiCache@GetMoreData@Inventory@Compat@Windows@@QEAAJXZ`
- size: `178`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::GetMoreData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000c2f8`

## callees

- `0x1400026d8`
- `0x14000d7bc`
- `0x14000dbdc`
- `0x14000de8c`
- `0x1400151b0`

## string_xrefs

- `0x14000dbe9`: `\nDumping AMI cache\n\n`
- `0x14000dc08`: `GmdDumpCache failed [%#x]`
- `0x14000dc19`: `Windows::Compat::Inventory::GetMoreData::CaptureAmiCache`
- `0x14000dc5d`: `Windows::Compat::Inventory::GetMoreData::CaptureAmiCache`
- `0x14000dc2e`: `GmdDumpCache failed [%#x]\n`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::GetMoreData::CaptureAmiCache(FILE *const *this)
{
  int v2; // eax
  unsigned int v3; // edi
  signed int v4; // eax
  unsigned int v5; // edi

  fwprintf(this[1], L"\nDumping AMI cache\n\n");
  v2 = Windows::Compat::Inventory::GetMoreData::DumpCache(this[1]);
  v3 = v2;
  if ( v2 < 0 )
  {
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::GetMoreData::CaptureAmiCache",
      326,
      "GmdDumpCache failed [%#x]",
      v2);
    fwprintf(this[1], L"GmdDumpCache failed [%#x]\n", v3);
  }
  v4 = Windows::Compat::Inventory::GetMoreData::AddHwReqChk(this[1]);
  v5 = v4;
  if ( v4 < 0 )
  {
    AslLogCallPrintf(3, "Windows::Compat::Inventory::GetMoreData::CaptureAmiCache", 333, "GmdHwReqChk failed [%#x]", v4);
    fwprintf(this[1], L"GmdHwReqChk failed [%#x]\n", v5);
  }
  return 0;
}

```

## disassembly

```asm
0x14000dbdc  mov     [rsp+arg_0], rbx
0x14000dbe1  push    rdi
0x14000dbe2  sub     rsp, 30h
0x14000dbe6  mov     rbx, rcx
0x14000dbe9  lea     rdx, aDumpingAmiCach; "\nDumping AMI cache\n\n"
0x14000dbf0  mov     rcx, [rcx+8]; Stream
0x14000dbf4  call    fwprintf
0x14000dbf9  mov     rcx, [rbx+8]; Stream
0x14000dbfd  call    ?DumpCache@GetMoreData@Inventory@Compat@Windows@@CAJPEAU_iobuf@@@Z; Windows::Compat::Inventory::GetMoreData::DumpCache(_iobuf *)
0x14000dc02  mov     edi, eax
0x14000dc04  test    eax, eax
0x14000dc06  jns     short loc_14000DC3D
0x14000dc08  lea     r9, aGmddumpcacheFa; "GmdDumpCache failed [%#x]"
0x14000dc0f  mov     [rsp+38h+var_18], eax
0x14000dc13  mov     r8d, 146h
0x14000dc19  lea     rdx, aWindowsCompatI_2; "Windows::Compat::Inventory::GetMoreData"...
0x14000dc20  mov     ecx, 3
0x14000dc25  call    AslLogCallPrintf
0x14000dc2a  mov     rcx, [rbx+8]; Stream
0x14000dc2e  lea     rdx, aGmddumpcacheFa_0; "GmdDumpCache failed [%#x]\n"
0x14000dc35  mov     r8d, edi
0x14000dc38  call    fwprintf
0x14000dc3d  mov     rcx, [rbx+8]; Stream
0x14000dc41  call    ?AddHwReqChk@GetMoreData@Inventory@Compat@Windows@@CAJPEAU_iobuf@@@Z; Windows::Compat::Inventory::GetMoreData::AddHwReqChk(_iobuf *)
0x14000dc46  mov     edi, eax
0x14000dc48  test    eax, eax
0x14000dc4a  jns     short loc_14000DC81
0x14000dc4c  lea     r9, aGmdhwreqchkFai; "GmdHwReqChk failed [%#x]"
0x14000dc53  mov     [rsp+38h+var_18], eax
0x14000dc57  mov     r8d, 14Dh
0x14000dc5d  lea     rdx, aWindowsCompatI_2; "Windows::Compat::Inventory::GetMoreData"...
0x14000dc64  mov     ecx, 3
0x14000dc69  call    AslLogCallPrintf
0x14000dc6e  mov     rcx, [rbx+8]; Stream
0x14000dc72  lea     rdx, aGmdhwreqchkFai_0; "GmdHwReqChk failed [%#x]\n"
0x14000dc79  mov     r8d, edi
0x14000dc7c  call    fwprintf
0x14000dc81  mov     rbx, [rsp+38h+arg_0]
0x14000dc86  xor     eax, eax
0x14000dc88  add     rsp, 30h
0x14000dc8c  pop     rdi
0x14000dc8d  retn
```
