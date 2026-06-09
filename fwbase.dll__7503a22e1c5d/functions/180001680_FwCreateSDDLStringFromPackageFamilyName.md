# FwCreateSDDLStringFromPackageFamilyName

- ea: `0x180001680`
- end: `0x180001716`
- name: `FwCreateSDDLStringFromPackageFamilyName`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001680`
- `0x180002c10`
- `0x1800047e0`

## string_xrefs

- `0x180001708`: `FwCreateSDDLStringFromPackageFamilyName`

## pseudocode

```c
__int64 __fastcall FwCreateSDDLStringFromPackageFamilyName(__int64 a1, _QWORD *a2)
{
  unsigned int v5; // eax

  *a2 = 0;
  if ( (int)FwStringBuild(a2, L"O:SYG:SYD:(XA;;CC;;;WD;(WIN://SYSAPPID Contains \"", a1, L"\"))") < 0 )
  {
    v5 = FwStringBuild(a2, L"O:SYG:SYD:(XA;;CC;;;WD;(WIN://SYSAPPID Contains \"", a1, L"\"))");
    FwReportReturnError("FwCreateSDDLStringFromPackageFamilyName", v5);
  }
  return 0;
}

```

## disassembly

```asm
0x180001680  mov     rax, rsp
0x180001683  mov     [rax+8], rbx
0x180001687  mov     [rax+10h], rbp
0x18000168b  push    rdi
0x18000168c  sub     rsp, 30h
0x180001690  mov     rbx, rdx
0x180001693  mov     qword ptr [rdx], 0
0x18000169a  mov     rdi, rcx
0x18000169d  mov     qword ptr [rax-10h], 0
0x1800016a5  mov     r8, rcx
0x1800016a8  lea     rbp, aACcS11531ACcS1; "(A;;CC;;;S-1-15-3-1)(A;;CC;;;S-1-15-3-2"...
0x1800016af  mov     rcx, rbx
0x1800016b2  mov     [rax-18h], rbp
0x1800016b6  lea     r9, asc_1800327E0; "\"))"
0x1800016bd  lea     rdx, aOSygSydXaCcWdW; "O:SYG:SYD:(XA;;CC;;;WD;(WIN://SYSAPPID "...
0x1800016c4  call    FwStringBuild
0x1800016c9  test    eax, eax
0x1800016cb  js      short loc_1800016DF
0x1800016cd  mov     rbx, [rsp+38h+arg_0]
0x1800016d2  xor     eax, eax
0x1800016d4  mov     rbp, [rsp+38h+arg_8]
0x1800016d9  add     rsp, 30h
0x1800016dd  pop     rdi
0x1800016de  retn
0x1800016df  mov     [rsp+38h+var_10], 0
0x1800016e8  lea     r9, asc_1800327E0; "\"))"
0x1800016ef  mov     r8, rdi
0x1800016f2  mov     [rsp+38h+var_18], rbp
0x1800016f7  lea     rdx, aOSygSydXaCcWdW; "O:SYG:SYD:(XA;;CC;;;WD;(WIN://SYSAPPID "...
0x1800016fe  mov     rcx, rbx
0x180001701  call    FwStringBuild
0x180001706  mov     edx, eax
0x180001708  lea     rcx, aFwcreatesddlst_1; "FwCreateSDDLStringFromPackageFamilyName"
0x18000170f  call    FwReportReturnError
0x180001714  jmp     short loc_1800016CD
```
