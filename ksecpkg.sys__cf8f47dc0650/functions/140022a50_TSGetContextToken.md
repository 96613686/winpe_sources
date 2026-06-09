# TSGetContextToken

- ea: `0x140022a50`
- end: `0x140022af0`
- name: `TSGetContextToken`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140022a50`

## import_xrefs

- `ntoskrnl!ExGetPreviousMode` at `0x140022a90`
- `ntoskrnl!ExGetPreviousMode` at `0x140022a90`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140022ac6`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140022ac6`

## pseudocode

```c
__int64 __fastcall TSGetContextToken(__int64 a1, _QWORD *a2, PVOID *a3)
{
  __int64 v6; // rax
  NTSTATUS v7; // ecx
  KPROCESSOR_MODE PreviousMode; // al
  PVOID Object; // [rsp+40h] [rbp+8h] BYREF

  if ( !a1 )
    return 3221225480LL;
  v6 = *(_QWORD *)(a1 + 40);
  if ( v6 )
  {
    if ( a2 )
      *a2 = v6;
    if ( !a3 )
      return 0;
    if ( !*(_QWORD *)(a1 + 40) )
      return 0;
    PreviousMode = ExGetPreviousMode();
    Object = 0;
    v7 = ObReferenceObjectByHandle(*(HANDLE *)(a1 + 40), 4u, 0, PreviousMode, &Object, 0);
    *a3 = Object;
    if ( v7 >= 0 )
      return 0;
  }
  else
  {
    return (unsigned int)-2146893045;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140022a50  mov     [rsp+arg_8], rbx
0x140022a55  push    rdi
0x140022a56  sub     rsp, 30h
0x140022a5a  mov     rdi, r8
0x140022a5d  mov     rbx, rcx
0x140022a60  test    rcx, rcx
0x140022a63  jnz     short loc_140022A6C
0x140022a65  mov     eax, 0C0000008h
0x140022a6a  jmp     short loc_140022AE4
0x140022a6c  mov     rax, [rcx+28h]
0x140022a70  test    rax, rax
0x140022a73  jnz     short loc_140022A7C
0x140022a75  mov     ecx, 8009030Bh
0x140022a7a  jmp     short loc_140022AE2
0x140022a7c  test    rdx, rdx
0x140022a7f  jz      short loc_140022A84
0x140022a81  mov     [rdx], rax
0x140022a84  test    rdi, rdi
0x140022a87  jz      short loc_140022AE0
0x140022a89  cmp     qword ptr [rcx+28h], 0
0x140022a8e  jz      short loc_140022AE0
0x140022a90  call    cs:__imp_ExGetPreviousMode
0x140022a97  nop     dword ptr [rax+rax+00h]
0x140022a9c  xor     r8d, r8d; ObjectType
0x140022a9f  mov     [rsp+38h+HandleInformation], 0; HandleInformation
0x140022aa8  lea     rcx, [rsp+38h+arg_0]
0x140022aad  mov     [rsp+38h+arg_0], 0
0x140022ab6  mov     [rsp+38h+Object], rcx; Object
0x140022abb  mov     r9b, al; AccessMode
0x140022abe  mov     rcx, [rbx+28h]; Handle
0x140022ac2  lea     edx, [r8+4]; DesiredAccess
0x140022ac6  call    cs:__imp_ObReferenceObjectByHandle
0x140022acd  nop     dword ptr [rax+rax+00h]
0x140022ad2  mov     ecx, eax
0x140022ad4  mov     rax, [rsp+38h+arg_0]
0x140022ad9  mov     [rdi], rax
0x140022adc  test    ecx, ecx
0x140022ade  js      short loc_140022AE2
0x140022ae0  xor     ecx, ecx
0x140022ae2  mov     eax, ecx
0x140022ae4  mov     rbx, [rsp+38h+arg_8]
0x140022ae9  add     rsp, 30h
0x140022aed  pop     rdi
0x140022aee  retn
```
