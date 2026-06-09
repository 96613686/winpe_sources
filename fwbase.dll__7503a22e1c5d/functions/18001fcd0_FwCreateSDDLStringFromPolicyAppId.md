# FwCreateSDDLStringFromPolicyAppId

- ea: `0x18001fcd0`
- end: `0x18001fd64`
- name: `FwCreateSDDLStringFromPolicyAppId`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800209e0`

## callees

- `0x180002c10`
- `0x1800047e0`
- `0x18001fcd0`

## string_xrefs

- `0x18001fd46`: `FwCreateSDDLStringFromPolicyAppId`

## pseudocode

```c
__int64 __fastcall FwCreateSDDLStringFromPolicyAppId(__int64 a1, _QWORD *a2)
{
  unsigned int v4; // eax

  *a2 = 0;
  if ( (int)FwStringBuild(a2, L"O:SYG:SYD:(XA;;CC;;;WD;(Exists POLICYAPPID://", a1, L"))") < 0 )
  {
    v4 = FwStringBuild(a2, L"O:SYG:SYD:(XA;;CC;;;WD;(Exists POLICYAPPID://", a1, L"))");
    FwReportReturnError("FwCreateSDDLStringFromPolicyAppId", v4);
  }
  return 0;
}

```

## disassembly

```asm
0x18001fcd0  mov     rax, rsp
0x18001fcd3  mov     [rax+8], rbx
0x18001fcd7  mov     [rax+10h], rbp
0x18001fcdb  push    rdi
0x18001fcdc  sub     rsp, 30h
0x18001fce0  mov     rbx, rdx
0x18001fce3  mov     qword ptr [rdx], 0
0x18001fcea  mov     rdi, rcx
0x18001fced  mov     qword ptr [rax-10h], 0
0x18001fcf5  mov     r8, rcx
0x18001fcf8  lea     rbp, aACcS11531ACcS1; "(A;;CC;;;S-1-15-3-1)(A;;CC;;;S-1-15-3-2"...
0x18001fcff  mov     rcx, rbx
0x18001fd02  mov     [rax-18h], rbp
0x18001fd06  lea     r9, asc_180033F44; "))"
0x18001fd0d  lea     rdx, aOSygSydXaCcWdE; "O:SYG:SYD:(XA;;CC;;;WD;(Exists POLICYAP"...
0x18001fd14  call    FwStringBuild
0x18001fd19  test    eax, eax
0x18001fd1b  jns     short loc_18001FD52
0x18001fd1d  mov     [rsp+38h+var_10], 0
0x18001fd26  lea     r9, asc_180033F44; "))"
0x18001fd2d  mov     r8, rdi
0x18001fd30  mov     [rsp+38h+var_18], rbp
0x18001fd35  lea     rdx, aOSygSydXaCcWdE; "O:SYG:SYD:(XA;;CC;;;WD;(Exists POLICYAP"...
0x18001fd3c  mov     rcx, rbx
0x18001fd3f  call    FwStringBuild
0x18001fd44  mov     edx, eax
0x18001fd46  lea     rcx, aFwcreatesddlst_2; "FwCreateSDDLStringFromPolicyAppId"
0x18001fd4d  call    FwReportReturnError
0x18001fd52  mov     rbx, [rsp+38h+arg_0]
0x18001fd57  xor     eax, eax
0x18001fd59  mov     rbp, [rsp+38h+arg_8]
0x18001fd5e  add     rsp, 30h
0x18001fd62  pop     rdi
0x18001fd63  retn
```
