# SepBuildCapPolicyTable

- ea: `0x14062f85c`
- end: `0x14062f9f0`
- name: `SepBuildCapPolicyTable`
- size: `404`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1407ca050`

## callees

- `0x14047c640`
- `0x14062f85c`
- `0x1406daa70`
- `0x1406f4880`
- `0x14072be9c`
- `0x1407c929c`
- `0x1407c95e8`
- `0x140a4c4e4`
- `0x140bae410`
- `0x140bae8e0`

## string_xrefs

- `0x14062f8a2`: `\Registry\Machine\System\CurrentControlSet\Control\Lsa\CentralizedAccessPolicies`
- `0x14062f8dc`: `\Registry\Machine\System\CurrentControlSet\Control\Lsa\CentralizedAccessPolicies\CAPs`
- `0x14062f8c6`: `\Registry\Machine\System\CurrentControlSet\Control\Lsa\CentralizedAccessPolicies\CAPEs`

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
0x14062f85c  push    rbp
0x14062f85e  push    rbx
0x14062f85f  push    rsi
0x14062f860  push    rdi
0x14062f861  push    r14
0x14062f863  mov     rbp, rsp
0x14062f866  sub     rsp, 40h
0x14062f86a  mov     rsi, rdx
0x14062f86d  mov     qword ptr [rdx], 0
0x14062f874  mov     r14d, ecx
0x14062f877  mov     [rbp+KeyHandle], 0
0x14062f87f  mov     ebx, 201h
0x14062f884  mov     [rbp+var_18], 0
0x14062f88c  mov     edx, ebx; DesiredAccess
0x14062f88e  mov     [rbp+Handle], 0
0x14062f896  lea     r8, [rbp+KeyHandle]; KeyHandle
0x14062f89a  mov     [rbp+P], 0
0x14062f8a2  lea     rcx, aRegistryMachin_244; "\\Registry\\Machine\\System\\CurrentCon"...
0x14062f8a9  mov     [rbp+arg_8], 0
0x14062f8b0  call    SepRegOpenKey
0x14062f8b5  test    eax, eax
0x14062f8b7  jns     short loc_14062F8C0
0x14062f8b9  xor     ebx, ebx
0x14062f8bb  jmp     loc_14062F954
0x14062f8c0  lea     r8, [rbp+var_18]; KeyHandle
0x14062f8c4  mov     edx, ebx; DesiredAccess
0x14062f8c6  lea     rcx, aRegistryMachin_44; "\\Registry\\Machine\\System\\CurrentCon"...
0x14062f8cd  call    SepRegOpenKey
0x14062f8d2  test    eax, eax
0x14062f8d4  js      short loc_14062F8B9
0x14062f8d6  lea     r8, [rbp+Handle]; KeyHandle
0x14062f8da  mov     edx, ebx; DesiredAccess
0x14062f8dc  lea     rcx, aRegistryMachin_93; "\\Registry\\Machine\\System\\CurrentCon"...
0x14062f8e3  call    SepRegOpenKey
0x14062f8e8  test    eax, eax
0x14062f8ea  js      short loc_14062F8B9
0x14062f8ec  mov     rcx, [rbp+var_18]; KeyHandle
0x14062f8f0  lea     r9, [rbp+P]
0x14062f8f4  lea     r8, [rbp+arg_8]
0x14062f8f8  mov     edx, r14d
0x14062f8fb  call    SepReadAndPopulateCapes
0x14062f900  mov     ebx, eax
0x14062f902  test    eax, eax
0x14062f904  js      short loc_14062F941
0x14062f906  cmp     [rbp+arg_8], 0
0x14062f90a  jz      short loc_14062F954
0x14062f90c  mov     ebx, 40h ; '@'
0x14062f911  mov     r8d, 70536553h
0x14062f917  mov     edx, ebx
0x14062f919  mov     ecx, 100h
0x14062f91e  call    ExAllocatePool2
0x14062f923  mov     [rbp+arg_18], rax
0x14062f927  mov     rdi, rax
0x14062f92a  test    rax, rax
0x14062f92d  jnz     short loc_14062F98C
0x14062f92f  mov     ebx, 0C000009Ah
0x14062f934  test    rdi, rdi
0x14062f937  jz      short loc_14062F941
0x14062f939  mov     rcx, rdi; P
0x14062f93c  call    SepRmDestroyCapTable
0x14062f941  mov     rcx, [rbp+P]; P
0x14062f945  test    rcx, rcx
0x14062f948  jz      short loc_14062F954
0x14062f94a  mov     edx, 70536553h; Tag
0x14062f94f  call    ExFreePoolWithTag
0x14062f954  mov     rcx, [rbp+Handle]; Handle
0x14062f958  test    rcx, rcx
0x14062f95b  jz      short loc_14062F962
0x14062f95d  call    ZwClose
0x14062f962  mov     rcx, [rbp+var_18]; Handle
0x14062f966  test    rcx, rcx
0x14062f969  jz      short loc_14062F970
0x14062f96b  call    ZwClose
0x14062f970  mov     rcx, [rbp+KeyHandle]; Handle
0x14062f974  test    rcx, rcx
0x14062f977  jz      short loc_14062F97E
0x14062f979  call    ZwClose
0x14062f97e  mov     eax, ebx
0x14062f980  add     rsp, 40h
0x14062f984  pop     r14
0x14062f986  pop     rdi
0x14062f987  pop     rsi
0x14062f988  pop     rbx
0x14062f989  pop     rbp
0x14062f98a  retn
0x14062f98c  mov     r8, rbx; Size
0x14062f98f  xor     edx, edx; Val
0x14062f991  mov     rcx, rdi; void *
0x14062f994  call    memset_0
0x14062f999  mov     eax, [rbp+arg_8]
0x14062f99c  lea     rcx, [rbp+arg_18]
0x14062f9a0  mov     [rdi+30h], eax
0x14062f9a3  xor     r9d, r9d
0x14062f9a6  mov     rax, [rbp+P]
0x14062f9aa  xor     r8d, r8d
0x14062f9ad  mov     [rdi+38h], rax
0x14062f9b1  mov     edx, 80h
0x14062f9b6  mov     [rbp+P], 0
0x14062f9be  call    RtlpCreateHashTable
0x14062f9c3  mov     rdi, [rbp+arg_18]
0x14062f9c7  test    al, al
0x14062f9c9  jz      loc_14062F92F
0x14062f9cf  mov     rcx, [rbp+Handle]; KeyHandle
0x14062f9d3  mov     r8, rdi
0x14062f9d6  mov     edx, r14d
0x14062f9d9  call    SepReadAndInsertCaps
0x14062f9de  mov     ebx, eax
0x14062f9e0  test    eax, eax
0x14062f9e2  js      loc_14062F934
0x14062f9e8  mov     [rsi], rdi
0x14062f9eb  jmp     loc_14062F954
```
