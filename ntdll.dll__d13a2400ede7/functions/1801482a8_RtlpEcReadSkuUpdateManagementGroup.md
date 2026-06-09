# RtlpEcReadSkuUpdateManagementGroup

- ea: `0x1801482a8`
- end: `0x18014832c`
- name: `RtlpEcReadSkuUpdateManagementGroup`
- size: `132`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180148180`

## callees

- `0x1801482a8`
- `0x1801616d0`

## string_xrefs

- `0x1801482b5`: `UpdatePolicy-UpdateManagementGroup`

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
0x1801482a8  mov     [rsp-8+arg_0], rbx
0x1801482ad  push    rbp
0x1801482ae  mov     rbp, rsp
0x1801482b1  sub     rsp, 40h
0x1801482b5  lea     rax, aUpdatepolicyUp; "UpdatePolicy-UpdateManagementGroup"
0x1801482bc  mov     [rbp+arg_18], 0
0x1801482c3  mov     [rbp+var_8], rax
0x1801482c7  lea     r8, [rbp+arg_18]
0x1801482cb  lea     rax, [rbp+arg_8]
0x1801482cf  mov     [rbp+arg_10], 0
0x1801482d6  mov     rbx, rcx
0x1801482d9  mov     [rsp+40h+var_20], rax
0x1801482de  mov     r9d, 4
0x1801482e4  mov     [rbp+arg_8], 0
0x1801482eb  lea     rdx, [rbp+arg_10]
0x1801482ef  mov     [rbp+var_10], 460044h
0x1801482f7  lea     rcx, [rbp+var_10]
0x1801482fb  call    ZwQueryLicenseValue
0x180148300  test    eax, eax
0x180148302  js      short loc_180148320
0x180148304  cmp     [rbp+arg_8], 4
0x180148308  jnz     short loc_18014831B
0x18014830a  cmp     [rbp+arg_10], 4
0x18014830e  jnz     short loc_18014831B
0x180148310  cmp     [rbp+arg_18], 0
0x180148314  setz    cl
0x180148317  mov     [rbx], cl
0x180148319  jmp     short loc_180148320
0x18014831b  mov     eax, 0C0000024h
0x180148320  mov     rbx, [rsp+40h+arg_0]
0x180148325  add     rsp, 40h
0x180148329  pop     rbp
0x18014832a  retn
```
