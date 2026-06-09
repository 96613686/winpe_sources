# SepBuildCapPolicyTable

- ea: `0x1406353dc`
- end: `0x140635570`
- name: `SepBuildCapPolicyTable`
- size: `404`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1407cced0`

## callees

- `0x14048c680`
- `0x1406353dc`
- `0x1406dd5c0`
- `0x1406f7380`
- `0x1407304cc`
- `0x1407cc11c`
- `0x1407cc468`
- `0x140a53d14`
- `0x140bb1410`
- `0x140bb19f0`

## string_xrefs

- `0x140635422`: `\Registry\Machine\System\CurrentControlSet\Control\Lsa\CentralizedAccessPolicies`
- `0x140635446`: `\Registry\Machine\System\CurrentControlSet\Control\Lsa\CentralizedAccessPolicies\CAPEs`
- `0x14063545c`: `\Registry\Machine\System\CurrentControlSet\Control\Lsa\CentralizedAccessPolicies\CAPs`

## pseudocode

```c
__int64 __fastcall SepBuildCapPolicyTable(__int64 a1, _QWORD *a2)
{
  unsigned int v2; // ebx
  HANDLE Handle; // [rsp+20h] [rbp-20h] BYREF
  HANDLE v5; // [rsp+28h] [rbp-18h] BYREF
  HANDLE KeyHandle; // [rsp+30h] [rbp-10h] BYREF

  *a2 = 0;
  KeyHandle = 0;
  v5 = 0;
  Handle = 0;
  if ( (int)SepRegOpenKey(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Lsa\\CentralizedAccessPolicies",
              0x201u,
              &KeyHandle) < 0
    || (int)SepRegOpenKey(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Lsa\\CentralizedAccessPolicies\\CAPEs",
              0x201u,
              &v5) < 0
    || (int)SepRegOpenKey(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Lsa\\CentralizedAccessPolicies\\CAPs",
              0x201u,
              &Handle) < 0 )
  {
    v2 = 0;
  }
  else
  {
    v2 = SepReadAndPopulateCapes(v5);
  }
  if ( Handle )
    ZwClose(Handle);
  if ( v5 )
    ZwClose(v5);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return v2;
}

```

## disassembly

```asm
0x1406353dc  push    rbp
0x1406353de  push    rbx
0x1406353df  push    rsi
0x1406353e0  push    rdi
0x1406353e1  push    r14
0x1406353e3  mov     rbp, rsp
0x1406353e6  sub     rsp, 40h
0x1406353ea  mov     rsi, rdx
0x1406353ed  mov     qword ptr [rdx], 0
0x1406353f4  mov     r14d, ecx
0x1406353f7  mov     [rbp+KeyHandle], 0
0x1406353ff  mov     ebx, 201h
0x140635404  mov     [rbp+var_18], 0
0x14063540c  mov     edx, ebx; DesiredAccess
0x14063540e  mov     [rbp+Handle], 0
0x140635416  lea     r8, [rbp+KeyHandle]; KeyHandle
0x14063541a  mov     [rbp+P], 0
0x140635422  lea     rcx, aRegistryMachin_243; "\\Registry\\Machine\\System\\CurrentCon"...
0x140635429  mov     [rbp+arg_8], 0
0x140635430  call    SepRegOpenKey
0x140635435  test    eax, eax
0x140635437  jns     short loc_140635440
0x140635439  xor     ebx, ebx
0x14063543b  jmp     loc_1406354D4
0x140635440  lea     r8, [rbp+var_18]; KeyHandle
0x140635444  mov     edx, ebx; DesiredAccess
0x140635446  lea     rcx, aRegistryMachin_44; "\\Registry\\Machine\\System\\CurrentCon"...
0x14063544d  call    SepRegOpenKey
0x140635452  test    eax, eax
0x140635454  js      short loc_140635439
0x140635456  lea     r8, [rbp+Handle]; KeyHandle
0x14063545a  mov     edx, ebx; DesiredAccess
0x14063545c  lea     rcx, aRegistryMachin_93; "\\Registry\\Machine\\System\\CurrentCon"...
0x140635463  call    SepRegOpenKey
0x140635468  test    eax, eax
0x14063546a  js      short loc_140635439
0x14063546c  mov     rcx, [rbp+var_18]; KeyHandle
0x140635470  lea     r9, [rbp+P]
0x140635474  lea     r8, [rbp+arg_8]
0x140635478  mov     edx, r14d
0x14063547b  call    SepReadAndPopulateCapes
0x140635480  mov     ebx, eax
0x140635482  test    eax, eax
0x140635484  js      short loc_1406354C1
0x140635486  cmp     [rbp+arg_8], 0
0x14063548a  jz      short loc_1406354D4
0x14063548c  mov     ebx, 40h ; '@'
0x140635491  mov     r8d, 70536553h
0x140635497  mov     edx, ebx
0x140635499  mov     ecx, 100h
0x14063549e  call    ExAllocatePool2
0x1406354a3  mov     [rbp+arg_18], rax
0x1406354a7  mov     rdi, rax
0x1406354aa  test    rax, rax
0x1406354ad  jnz     short loc_14063550C
0x1406354af  mov     ebx, 0C000009Ah
0x1406354b4  test    rdi, rdi
0x1406354b7  jz      short loc_1406354C1
0x1406354b9  mov     rcx, rdi; P
0x1406354bc  call    SepRmDestroyCapTable
0x1406354c1  mov     rcx, [rbp+P]; P
0x1406354c5  test    rcx, rcx
0x1406354c8  jz      short loc_1406354D4
0x1406354ca  mov     edx, 70536553h; Tag
0x1406354cf  call    ExFreePoolWithTag
0x1406354d4  mov     rcx, [rbp+Handle]; Handle
0x1406354d8  test    rcx, rcx
0x1406354db  jz      short loc_1406354E2
0x1406354dd  call    ZwClose
0x1406354e2  mov     rcx, [rbp+var_18]; Handle
0x1406354e6  test    rcx, rcx
0x1406354e9  jz      short loc_1406354F0
0x1406354eb  call    ZwClose
0x1406354f0  mov     rcx, [rbp+KeyHandle]; Handle
0x1406354f4  test    rcx, rcx
0x1406354f7  jz      short loc_1406354FE
0x1406354f9  call    ZwClose
0x1406354fe  mov     eax, ebx
0x140635500  add     rsp, 40h
0x140635504  pop     r14
0x140635506  pop     rdi
0x140635507  pop     rsi
0x140635508  pop     rbx
0x140635509  pop     rbp
0x14063550a  retn
0x14063550c  mov     r8, rbx; Size
0x14063550f  xor     edx, edx; Val
0x140635511  mov     rcx, rdi; void *
0x140635514  call    memset_0
0x140635519  mov     eax, [rbp+arg_8]
0x14063551c  lea     rcx, [rbp+arg_18]
0x140635520  mov     [rdi+30h], eax
0x140635523  xor     r9d, r9d
0x140635526  mov     rax, [rbp+P]
0x14063552a  xor     r8d, r8d
0x14063552d  mov     [rdi+38h], rax
0x140635531  mov     edx, 80h
0x140635536  mov     [rbp+P], 0
0x14063553e  call    RtlpCreateHashTable
0x140635543  mov     rdi, [rbp+arg_18]
0x140635547  test    al, al
0x140635549  jz      loc_1406354AF
0x14063554f  mov     rcx, [rbp+Handle]; KeyHandle
0x140635553  mov     r8, rdi
0x140635556  mov     edx, r14d
0x140635559  call    SepReadAndInsertCaps
0x14063555e  mov     ebx, eax
0x140635560  test    eax, eax
0x140635562  js      loc_1406354B4
0x140635568  mov     [rsi], rdi
0x14063556b  jmp     loc_1406354D4
```
