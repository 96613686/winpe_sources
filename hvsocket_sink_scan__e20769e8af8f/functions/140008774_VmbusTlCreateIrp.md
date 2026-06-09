# VmbusTlCreateIrp

- ea: `0x140008774`
- end: `0x140008856`
- name: `VmbusTlCreateIrp`
- size: `226`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1400085c8`
- `0x140025610`
- `0x140026330`

## callees

- `0x140001350`
- `0x140008774`
- `0x140009cf8`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14000881c`
- `ntoskrnl!IoFreeIrp` at `0x14000881c`
- `ntoskrnl!IoAllocateIrp` at `0x140008794`
- `ntoskrnl!IoAllocateIrp` at `0x140008794`

## string_xrefs

- `0x1400087fe`: `Failed to create IRP.`
- `0x1400087c9`: `VmbusTlCreateIrp`
- `0x14000880d`: `VmbusTlCreateIrp`

## pseudocode

```c
__int64 __fastcall VmbusTlCreateIrp(__int64 a1, _QWORD *a2)
{
  CCHAR v2; // cl
  PIRP Irp; // rax
  IRP *v5; // rdi
  int v6; // ebx
  __int64 v7; // rax
  __int64 v9; // [rsp+30h] [rbp+8h] BYREF

  v2 = *(_BYTE *)(a1 + 76);
  v9 = 0;
  Irp = IoAllocateIrp(v2, 0);
  v5 = Irp;
  if ( Irp )
  {
    Irp->RequestorMode = 0;
    v6 = VmbusTlCreateObject(3u, 104, &v9);
    if ( v6 >= 0 )
    {
      v7 = v9;
      *a2 = v9;
      v6 = 0;
      *(_QWORD *)(v7 + 80) = VmbusTlIrpDestructor;
      *(_QWORD *)(v7 + 96) = v5;
    }
    else
    {
      if ( (unsigned int)dword_140013058 > 2 )
        HvsocketTraceError("VmbusTlCreateIrp", 70, (unsigned int)v6, "Failed to create IRP.");
      IoFreeIrp(v5);
    }
  }
  else
  {
    v6 = -1073741670;
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceError("VmbusTlCreateIrp", 61, 3221225626LL, "Failed to allocated IRP.");
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140008774  mov     [rsp+arg_8], rbx
0x140008779  mov     [rsp+arg_10], rsi
0x14000877e  push    rdi
0x14000877f  sub     rsp, 20h
0x140008783  mov     cl, [rcx+4Ch]; StackSize
0x140008786  mov     rsi, rdx
0x140008789  xor     edx, edx; ChargeQuota
0x14000878b  mov     [rsp+28h+arg_0], 0
0x140008794  call    cs:__imp_IoAllocateIrp
0x14000879b  nop     dword ptr [rax+rax+00h]
0x1400087a0  mov     rdi, rax
0x1400087a3  test    rax, rax
0x1400087a6  jnz     short loc_1400087D7
0x1400087a8  mov     eax, cs:dword_140013058
0x1400087ae  mov     ebx, 0C000009Ah
0x1400087b3  cmp     eax, 2
0x1400087b6  jbe     loc_140008843
0x1400087bc  lea     r9, aFailedToAlloca; "Failed to allocated IRP."
0x1400087c3  mov     r8d, ebx
0x1400087c6  lea     edx, [rdi+3Dh]
0x1400087c9  lea     rcx, aVmbustlcreatei; "VmbusTlCreateIrp"
0x1400087d0  call    HvsocketTraceError
0x1400087d5  jmp     short loc_140008843
0x1400087d7  mov     edx, 68h ; 'h'
0x1400087dc  mov     byte ptr [rax+40h], 0
0x1400087e0  lea     r8, [rsp+28h+arg_0]
0x1400087e5  lea     ecx, [rdx-65h]
0x1400087e8  call    VmbusTlCreateObject
0x1400087ed  mov     ebx, eax
0x1400087ef  test    eax, eax
0x1400087f1  jns     short loc_14000882A
0x1400087f3  mov     eax, cs:dword_140013058
0x1400087f9  cmp     eax, 2
0x1400087fc  jbe     short loc_140008819
0x1400087fe  lea     r9, aFailedToCreate; "Failed to create IRP."
0x140008805  mov     r8d, ebx
0x140008808  mov     edx, 46h ; 'F'
0x14000880d  lea     rcx, aVmbustlcreatei; "VmbusTlCreateIrp"
0x140008814  call    HvsocketTraceError
0x140008819  mov     rcx, rdi; Irp
0x14000881c  call    cs:__imp_IoFreeIrp
0x140008823  nop     dword ptr [rax+rax+00h]
0x140008828  jmp     short loc_140008843
0x14000882a  mov     rax, [rsp+28h+arg_0]
0x14000882f  lea     rcx, VmbusTlIrpDestructor
0x140008836  mov     [rsi], rax
0x140008839  xor     ebx, ebx
0x14000883b  mov     [rax+50h], rcx
0x14000883f  mov     [rax+60h], rdi
0x140008843  mov     rsi, [rsp+28h+arg_10]
0x140008848  mov     eax, ebx
0x14000884a  mov     rbx, [rsp+28h+arg_8]
0x14000884f  add     rsp, 20h
0x140008853  pop     rdi
0x140008854  retn
```
