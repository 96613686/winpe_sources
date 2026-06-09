# FwReplacePolicyAppIdInSDDLString

- ea: `0x1800209e0`
- end: `0x180020b08`
- name: `FwReplacePolicyAppIdInSDDLString`
- size: `296`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x1800047e0`
- `0x180004840`
- `0x180012b10`
- `0x18001fcd0`
- `0x1800201a0`
- `0x1800207f0`
- `0x1800209e0`

## string_xrefs

- `0x180020a28`: `FwReplacePolicyAppIdInSDDLString`
- `0x180020a68`: `FwReplacePolicyAppIdInSDDLString`
- `0x180020ad7`: `FwReplacePolicyAppIdInSDDLString`

## pseudocode

```c
__int64 __fastcall FwReplacePolicyAppIdInSDDLString(__int64 a1, void *a2, _QWORD *a3)
{
  void *v4; // rbx
  unsigned int PolicyAppIdFromSDDLString; // eax
  __int64 v8; // r14
  unsigned int v9; // eax
  unsigned int SDDLStringFromPolicyAppId; // eax
  void *v11; // rdx
  __int64 v13; // [rsp+50h] [rbp+18h] BYREF
  void *v14; // [rsp+58h] [rbp+20h]

  v4 = 0;
  v14 = 0;
  v13 = 0;
  *a3 = 0;
  if ( (int)FwGetPolicyAppIdFromSDDLString(a2, &v13) >= 0 )
  {
    v8 = v13;
    if ( v13 )
    {
      if ( (int)FwRemovePolicyAppIdFromSDDLString(a2) < 0 )
      {
        v9 = FwRemovePolicyAppIdFromSDDLString(a2);
        FwReportReturnError("FwReplacePolicyAppIdInSDDLString", v9);
        v4 = v14;
        goto LABEL_15;
      }
      v4 = v14;
      if ( !v14 )
      {
        if ( (int)FwCreateSDDLStringFromPolicyAppId(a1, a3) >= 0 )
          goto LABEL_15;
        SDDLStringFromPolicyAppId = FwCreateSDDLStringFromPolicyAppId(a1, a3);
LABEL_14:
        FwReportReturnError("FwReplacePolicyAppIdInSDDLString", SDDLStringFromPolicyAppId);
        goto LABEL_15;
      }
      if ( (int)FwModifySDDLStringWithPolicyAppId(a1, v14, a3) >= 0 )
        goto LABEL_15;
      v11 = v4;
    }
    else
    {
      if ( (int)FwModifySDDLStringWithPolicyAppId(a1, a2, a3) >= 0 )
        goto LABEL_15;
      v11 = a2;
    }
    SDDLStringFromPolicyAppId = FwModifySDDLStringWithPolicyAppId(a1, v11, a3);
    goto LABEL_14;
  }
  PolicyAppIdFromSDDLString = FwGetPolicyAppIdFromSDDLString(a2, &v13);
  FwReportReturnError("FwReplacePolicyAppIdInSDDLString", PolicyAppIdFromSDDLString);
  v8 = v13;
LABEL_15:
  FwFree(v4);
  FwFree(v8);
  return 0;
}

```

## disassembly

```asm
0x1800209e0  mov     rax, rsp
0x1800209e3  mov     [rax+8], rbx
0x1800209e7  mov     [rax+10h], rbp
0x1800209eb  push    rsi
0x1800209ec  push    rdi
0x1800209ed  push    r14
0x1800209ef  sub     rsp, 20h
0x1800209f3  mov     rsi, rdx
0x1800209f6  xor     ebx, ebx
0x1800209f8  mov     rbp, rcx
0x1800209fb  mov     [rax+20h], rbx
0x1800209ff  mov     rcx, rsi
0x180020a02  mov     [rax+18h], rbx
0x180020a06  lea     rdx, [rax+18h]
0x180020a0a  mov     [r8], rbx
0x180020a0d  mov     rdi, r8
0x180020a10  call    FwGetPolicyAppIdFromSDDLString
0x180020a15  test    eax, eax
0x180020a17  jns     short loc_180020A3E
0x180020a19  lea     rdx, [rsp+38h+arg_10]
0x180020a1e  mov     rcx, rsi
0x180020a21  call    FwGetPolicyAppIdFromSDDLString
0x180020a26  mov     edx, eax
0x180020a28  lea     rcx, aFwreplacepolic_0; "FwReplacePolicyAppIdInSDDLString"
0x180020a2f  call    FwReportReturnError
0x180020a34  mov     r14, [rsp+38h+arg_10]
0x180020a39  jmp     loc_180020AE3
0x180020a3e  mov     r14, [rsp+38h+arg_10]
0x180020a43  test    r14, r14
0x180020a46  jz      short loc_180020AB5
0x180020a48  lea     rdx, [rsp+38h+arg_18]
0x180020a4d  mov     rcx, rsi; Src
0x180020a50  call    FwRemovePolicyAppIdFromSDDLString
0x180020a55  test    eax, eax
0x180020a57  jns     short loc_180020A7B
0x180020a59  lea     rdx, [rsp+38h+arg_18]
0x180020a5e  mov     rcx, rsi; Src
0x180020a61  call    FwRemovePolicyAppIdFromSDDLString
0x180020a66  mov     edx, eax
0x180020a68  lea     rcx, aFwreplacepolic_0; "FwReplacePolicyAppIdInSDDLString"
0x180020a6f  call    FwReportReturnError
0x180020a74  mov     rbx, [rsp+38h+arg_18]
0x180020a79  jmp     short loc_180020AE3
0x180020a7b  mov     rbx, [rsp+38h+arg_18]
0x180020a80  mov     rcx, rbp
0x180020a83  test    rbx, rbx
0x180020a86  jnz     short loc_180020AA1
0x180020a88  mov     rdx, rdi
0x180020a8b  call    FwCreateSDDLStringFromPolicyAppId
0x180020a90  test    eax, eax
0x180020a92  jns     short loc_180020AE3
0x180020a94  mov     rdx, rdi
0x180020a97  mov     rcx, rbp
0x180020a9a  call    FwCreateSDDLStringFromPolicyAppId
0x180020a9f  jmp     short loc_180020AD5
0x180020aa1  mov     r8, rdi
0x180020aa4  mov     rdx, rbx
0x180020aa7  call    FwModifySDDLStringWithPolicyAppId
0x180020aac  test    eax, eax
0x180020aae  jns     short loc_180020AE3
0x180020ab0  mov     rdx, rbx
0x180020ab3  jmp     short loc_180020ACA
0x180020ab5  mov     r8, rdi
0x180020ab8  mov     rdx, rsi
0x180020abb  mov     rcx, rbp
0x180020abe  call    FwModifySDDLStringWithPolicyAppId
0x180020ac3  test    eax, eax
0x180020ac5  jns     short loc_180020AE3
0x180020ac7  mov     rdx, rsi
0x180020aca  mov     r8, rdi
0x180020acd  mov     rcx, rbp
0x180020ad0  call    FwModifySDDLStringWithPolicyAppId
0x180020ad5  mov     edx, eax
0x180020ad7  lea     rcx, aFwreplacepolic_0; "FwReplacePolicyAppIdInSDDLString"
0x180020ade  call    FwReportReturnError
0x180020ae3  mov     rcx, rbx
0x180020ae6  call    FwFree
0x180020aeb  mov     rcx, r14
0x180020aee  call    FwFree
0x180020af3  mov     rbx, [rsp+38h+arg_0]
0x180020af8  xor     eax, eax
0x180020afa  mov     rbp, [rsp+38h+arg_8]
0x180020aff  add     rsp, 20h
0x180020b03  pop     r14
0x180020b05  pop     rdi
0x180020b06  pop     rsi
0x180020b07  retn
```
