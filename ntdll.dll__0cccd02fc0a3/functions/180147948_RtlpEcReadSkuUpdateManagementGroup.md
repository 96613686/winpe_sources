# RtlpEcReadSkuUpdateManagementGroup

- ea: `0x180147948`
- end: `0x1801479cc`
- name: `RtlpEcReadSkuUpdateManagementGroup`
- size: `132`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180147820`

## callees

- `0x180147948`
- `0x180160ec0`

## string_xrefs

- `0x180147955`: `UpdatePolicy-UpdateManagementGroup`

## pseudocode

```c
__int64 __fastcall RtlpEcReadSkuUpdateManagementGroup(bool *a1)
{
  __int64 result; // rax
  _QWORD v3[2]; // [rsp+30h] [rbp-10h] BYREF
  int v4; // [rsp+58h] [rbp+18h] BYREF
  int v5; // [rsp+60h] [rbp+20h] BYREF
  int v6; // [rsp+68h] [rbp+28h] BYREF

  v6 = 0;
  v3[1] = L"UpdatePolicy-UpdateManagementGroup";
  v5 = 0;
  v4 = 0;
  v3[0] = 4587588;
  result = ZwQueryLicenseValue(v3, &v5, &v6, 4, &v4);
  if ( (int)result >= 0 )
  {
    if ( v4 == 4 && v5 == 4 )
      *a1 = v6 == 0;
    else
      return 3221225508LL;
  }
  return result;
}

```

## disassembly

```asm
0x180147948  mov     [rsp-8+arg_0], rbx
0x18014794d  push    rbp
0x18014794e  mov     rbp, rsp
0x180147951  sub     rsp, 40h
0x180147955  lea     rax, aUpdatepolicyUp; "UpdatePolicy-UpdateManagementGroup"
0x18014795c  mov     [rbp+arg_18], 0
0x180147963  mov     [rbp+var_8], rax
0x180147967  lea     r8, [rbp+arg_18]
0x18014796b  lea     rax, [rbp+arg_8]
0x18014796f  mov     [rbp+arg_10], 0
0x180147976  mov     rbx, rcx
0x180147979  mov     [rsp+40h+var_20], rax
0x18014797e  mov     r9d, 4
0x180147984  mov     [rbp+arg_8], 0
0x18014798b  lea     rdx, [rbp+arg_10]
0x18014798f  mov     [rbp+var_10], 460044h
0x180147997  lea     rcx, [rbp+var_10]
0x18014799b  call    ZwQueryLicenseValue
0x1801479a0  test    eax, eax
0x1801479a2  js      short loc_1801479C0
0x1801479a4  cmp     [rbp+arg_8], 4
0x1801479a8  jnz     short loc_1801479BB
0x1801479aa  cmp     [rbp+arg_10], 4
0x1801479ae  jnz     short loc_1801479BB
0x1801479b0  cmp     [rbp+arg_18], 0
0x1801479b4  setz    cl
0x1801479b7  mov     [rbx], cl
0x1801479b9  jmp     short loc_1801479C0
0x1801479bb  mov     eax, 0C0000024h
0x1801479c0  mov     rbx, [rsp+40h+arg_0]
0x1801479c5  add     rsp, 40h
0x1801479c9  pop     rbp
0x1801479ca  retn
```
