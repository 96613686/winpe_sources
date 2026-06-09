# NtLmGetContextToken

- ea: `0x14002fba0`
- end: `0x14002fd53`
- name: `NtLmGetContextToken`
- size: `435`
- prototype: `__int64 __fastcall(PVOID P, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140010240`
- `0x14002fba0`

## import_xrefs

- `ntoskrnl!ZwSetInformationObject` at `0x14002fd05`
- `ntoskrnl!ZwSetInformationObject` at `0x14002fd05`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fc89`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fcce`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fc89`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fcce`
- `ntoskrnl!ZwClose` at `0x14002fd15`
- `ntoskrnl!ZwClose` at `0x14002fd15`
- `ntoskrnl!ExGetPreviousMode` at `0x14002fc05`
- `ntoskrnl!ExGetPreviousMode` at `0x14002fc05`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002fc35`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002fc35`
- `ntoskrnl!ObfDereferenceObject` at `0x14002fd30`
- `ntoskrnl!ObfDereferenceObject` at `0x14002fd30`
- `cng!BCryptDestroyKey` at `0x14002fca7`
- `cng!BCryptDestroyKey` at `0x14002fd3e`
- `cng!BCryptDestroyKey` at `0x14002fca7`
- `cng!BCryptDestroyKey` at `0x14002fd3e`

## pseudocode

```c
__int64 __fastcall NtLmGetContextToken(PVOID P, _QWORD *a2, _QWORD *a3)
{
  __int64 result; // rax
  NTSTATUS v7; // ebp
  __int64 v8; // rcx
  KPROCESSOR_MODE PreviousMode; // al
  void *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  __int16 ObjectInformation; // [rsp+30h] [rbp-28h] BYREF
  PVOID Object; // [rsp+38h] [rbp-20h] BYREF
  char v18; // [rsp+78h] [rbp+20h] BYREF

  result = (*((__int64 (__fastcall **)(PVOID, __int64, _QWORD))LsaKernelFunctions + 4))(P, 1296847950, 0);
  v7 = result;
  if ( (int)result >= 0 )
  {
    v8 = *((_QWORD *)P + 7);
    if ( v8 )
    {
      if ( a2 )
        *a2 = v8;
      if ( a3 )
      {
        if ( !*((_QWORD *)P + 7)
          || *((_QWORD *)P + 8)
          || (PreviousMode = ExGetPreviousMode(),
              v10 = (void *)*((_QWORD *)P + 7),
              Object = 0,
              v7 = ObReferenceObjectByHandle(v10, 0xCu, 0, PreviousMode, &Object, 0),
              *((_QWORD *)P + 8) = Object,
              v7 >= 0) )
        {
          *a3 = *((_QWORD *)P + 8);
        }
      }
    }
    else
    {
      v7 = -2146893045;
    }
    v18 = 0;
    (*((void (__fastcall **)(PVOID, char *))LsaKernelFunctions + 5))(P, &v18);
    if ( v18 )
    {
      v11 = (void *)*((_QWORD *)P + 16);
      if ( v11 )
        ExFreePoolWithTag(v11, 0);
      v12 = (void *)*((_QWORD *)P + 7);
      if ( v12 )
      {
        ObjectInformation = 0;
        ZwSetInformationObject(v12, ObjectHandleFlagInformation, &ObjectInformation, 2u);
        ZwClose(*((HANDLE *)P + 7));
      }
      v13 = (void *)*((_QWORD *)P + 13);
      if ( v13 )
      {
        BCryptDestroyKey(v13);
        *((_QWORD *)P + 13) = 0;
      }
      v14 = (void *)*((_QWORD *)P + 14);
      if ( v14 )
      {
        BCryptDestroyKey(v14);
        *((_QWORD *)P + 14) = 0;
      }
      v15 = (void *)*((_QWORD *)P + 8);
      if ( v15 )
        ObfDereferenceObject(v15);
      ExFreePoolWithTag(P, 0);
    }
    return (unsigned int)v7;
  }
  return result;
}

```

## disassembly

```asm
0x14002fba0  mov     [rsp+arg_8], rbx
0x14002fba5  push    rbp
0x14002fba6  push    rsi
0x14002fba7  push    rdi
0x14002fba8  sub     rsp, 40h
0x14002fbac  mov     rax, cs:?LsaKernelFunctions@@3PEAU_SECPKG_KERNEL_FUNCTIONS@@EA; _SECPKG_KERNEL_FUNCTIONS * LsaKernelFunctions
0x14002fbb3  mov     rdi, r8
0x14002fbb6  mov     rsi, rdx
0x14002fbb9  xor     r8d, r8d
0x14002fbbc  mov     edx, 4D4C544Eh
0x14002fbc1  mov     rbx, rcx
0x14002fbc4  mov     rax, [rax+20h]
0x14002fbc8  call    _guard_dispatch_icall
0x14002fbcd  mov     ebp, eax
0x14002fbcf  test    eax, eax
0x14002fbd1  js      loc_14002FCE1
0x14002fbd7  mov     rcx, [rbx+38h]
0x14002fbdb  mov     [rsp+58h+arg_0], r14
0x14002fbe0  xor     r14d, r14d
0x14002fbe3  test    rcx, rcx
0x14002fbe6  jz      loc_14002FD26
0x14002fbec  test    rsi, rsi
0x14002fbef  jz      short loc_14002FBF4
0x14002fbf1  mov     [rsi], rcx
0x14002fbf4  test    rdi, rdi
0x14002fbf7  jz      short loc_14002FC57
0x14002fbf9  cmp     [rbx+38h], r14
0x14002fbfd  jz      short loc_14002FC50
0x14002fbff  cmp     [rbx+40h], r14
0x14002fc03  jnz     short loc_14002FC50
0x14002fc05  call    cs:__imp_ExGetPreviousMode
0x14002fc0c  nop     dword ptr [rax+rax+00h]
0x14002fc11  lea     rcx, [rsp+58h+var_20]
0x14002fc16  mov     [rsp+58h+HandleInformation], r14; HandleInformation
0x14002fc1b  mov     [rsp+58h+Object], rcx; Object
0x14002fc20  movzx   r9d, al; AccessMode
0x14002fc24  mov     rcx, [rbx+38h]; Handle
0x14002fc28  xor     r8d, r8d; ObjectType
0x14002fc2b  mov     edx, 0Ch; DesiredAccess
0x14002fc30  mov     [rsp+58h+var_20], r14
0x14002fc35  call    cs:__imp_ObReferenceObjectByHandle
0x14002fc3c  nop     dword ptr [rax+rax+00h]
0x14002fc41  mov     ebp, eax
0x14002fc43  mov     rax, [rsp+58h+var_20]
0x14002fc48  mov     [rbx+40h], rax
0x14002fc4c  test    ebp, ebp
0x14002fc4e  js      short loc_14002FC57
0x14002fc50  mov     rax, [rbx+40h]
0x14002fc54  mov     [rdi], rax
0x14002fc57  mov     rax, cs:?LsaKernelFunctions@@3PEAU_SECPKG_KERNEL_FUNCTIONS@@EA; _SECPKG_KERNEL_FUNCTIONS * LsaKernelFunctions
0x14002fc5e  lea     rdx, [rsp+58h+arg_18]
0x14002fc63  mov     rcx, rbx
0x14002fc66  mov     [rsp+58h+arg_18], r14b
0x14002fc6b  mov     rax, [rax+28h]
0x14002fc6f  call    _guard_dispatch_icall
0x14002fc74  cmp     [rsp+58h+arg_18], r14b
0x14002fc79  jz      short loc_14002FCDA
0x14002fc7b  mov     rcx, [rbx+80h]; P
0x14002fc82  test    rcx, rcx
0x14002fc85  jz      short loc_14002FC95
0x14002fc87  xor     edx, edx; Tag
0x14002fc89  call    cs:__imp_ExFreePoolWithTag
0x14002fc90  nop     dword ptr [rax+rax+00h]
0x14002fc95  mov     rcx, [rbx+38h]; ObjectHandle
0x14002fc99  test    rcx, rcx
0x14002fc9c  jnz     short loc_14002FCEF
0x14002fc9e  mov     rcx, [rbx+68h]; hKey
0x14002fca2  test    rcx, rcx
0x14002fca5  jz      short loc_14002FCB7
0x14002fca7  call    cs:__imp_BCryptDestroyKey
0x14002fcae  nop     dword ptr [rax+rax+00h]
0x14002fcb3  mov     [rbx+68h], r14
0x14002fcb7  mov     rcx, [rbx+70h]; hKey
0x14002fcbb  test    rcx, rcx
0x14002fcbe  jnz     short loc_14002FD3E
0x14002fcc0  mov     rcx, [rbx+40h]; Object
0x14002fcc4  test    rcx, rcx
0x14002fcc7  jnz     short loc_14002FD30
0x14002fcc9  xor     edx, edx; Tag
0x14002fccb  mov     rcx, rbx; P
0x14002fcce  call    cs:__imp_ExFreePoolWithTag
0x14002fcd5  nop     dword ptr [rax+rax+00h]
0x14002fcda  mov     r14, [rsp+58h+arg_0]
0x14002fcdf  mov     eax, ebp
0x14002fce1  mov     rbx, [rsp+58h+arg_8]
0x14002fce6  add     rsp, 40h
0x14002fcea  pop     rdi
0x14002fceb  pop     rsi
0x14002fcec  pop     rbp
0x14002fced  retn
0x14002fcef  mov     r9d, 2; Length
0x14002fcf5  mov     [rsp+58h+ObjectInformation], r14w
0x14002fcfb  lea     r8, [rsp+58h+ObjectInformation]; ObjectInformation
0x14002fd00  mov     edx, 4; ObjectInformationClass
0x14002fd05  call    cs:__imp_ZwSetInformationObject
0x14002fd0c  nop     dword ptr [rax+rax+00h]
0x14002fd11  mov     rcx, [rbx+38h]; Handle
0x14002fd15  call    cs:__imp_ZwClose
0x14002fd1c  nop     dword ptr [rax+rax+00h]
0x14002fd21  jmp     loc_14002FC9E
0x14002fd26  mov     ebp, 8009030Bh
0x14002fd2b  jmp     loc_14002FC57
0x14002fd30  call    cs:__imp_ObfDereferenceObject
0x14002fd37  nop     dword ptr [rax+rax+00h]
0x14002fd3c  jmp     short loc_14002FCC9
0x14002fd3e  call    cs:__imp_BCryptDestroyKey
0x14002fd45  nop     dword ptr [rax+rax+00h]
0x14002fd4a  mov     [rbx+70h], r14
0x14002fd4e  jmp     loc_14002FCC0
```
