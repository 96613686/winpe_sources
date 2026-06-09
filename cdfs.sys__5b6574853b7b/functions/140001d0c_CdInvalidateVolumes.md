# CdInvalidateVolumes

- ea: `0x140001d0c`
- end: `0x140001fca`
- name: `CdInvalidateVolumes`
- size: `702`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140014e4c`

## callees

- `0x140001160`
- `0x140001d0c`
- `0x1400024e0`
- `0x140003300`
- `0x14000bcf8`
- `0x1400181a4`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140001e5d`
- `ntoskrnl!ExAcquireFastMutex` at `0x140001e5d`
- `ntoskrnl!ExReleaseFastMutex` at `0x140001f10`
- `ntoskrnl!ExReleaseFastMutex` at `0x140001f73`
- `ntoskrnl!ExReleaseFastMutex` at `0x140001f10`
- `ntoskrnl!ExReleaseFastMutex` at `0x140001f73`
- `ntoskrnl!ExReleaseResourceLite` at `0x140001f57`
- `ntoskrnl!ExReleaseResourceLite` at `0x140001f9e`
- `ntoskrnl!ExReleaseResourceLite` at `0x140001f57`
- `ntoskrnl!ExReleaseResourceLite` at `0x140001f9e`
- `ntoskrnl!ObfDereferenceObject` at `0x140001e03`
- `ntoskrnl!ObfDereferenceObject` at `0x140001e03`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140001e24`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140001e24`
- `ntoskrnl!IoAcquireVpbSpinLock` at `0x140001e8f`
- `ntoskrnl!IoAcquireVpbSpinLock` at `0x140001e8f`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x140001ee9`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x140001ee9`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x140001d72`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x140001d72`
- `ntoskrnl!IoIs32bitProcess` at `0x140001d92`
- `ntoskrnl!IoIs32bitProcess` at `0x140001d92`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140001de8`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140001de8`
- `ntoskrnl!IoFileObjectType` at `0x140001dc6`

## pseudocode

```c
__int64 __fastcall CdInvalidateVolumes(_DWORD *a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  IRP *v3; // rdi
  _DWORD *v4; // rsi
  int v5; // ebx
  BOOLEAN v7; // al
  ULONG Options; // ecx
  void *v9; // rcx
  __int64 v10; // r15
  __int64 *v11; // r14
  __int64 v12; // rbp
  _DWORD *v13; // rbx
  PVOID Object; // [rsp+30h] [rbp-48h] BYREF
  IRP *v15; // [rsp+88h] [rbp+10h]
  KIRQL Irql; // [rsp+90h] [rbp+18h] BYREF
  LUID PrivilegeValue; // [rsp+98h] [rbp+20h]

  v15 = a2;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v3 = a2;
  Irql = 0;
  v4 = a1;
  Object = 0;
  PrivilegeValue = (LUID)7LL;
  if ( CurrentStackLocation->DeviceObject != DeviceObject )
  {
    v5 = -1073741808;
LABEL_3:
    CdCompleteRequest(a1, a2, v5);
    return (unsigned int)v5;
  }
  if ( !SeSinglePrivilegeCheck(PrivilegeValue, a2->RequestorMode) )
  {
    v5 = -1073741727;
LABEL_6:
    a2 = v3;
    a1 = v4;
    goto LABEL_3;
  }
  v7 = IoIs32bitProcess(v3);
  Options = CurrentStackLocation->Parameters.Create.Options;
  if ( v7 )
  {
    if ( Options == 4 )
    {
      v9 = (void *)*(int *)v3->AssociatedIrp.MasterIrp;
      goto LABEL_13;
    }
LABEL_11:
    v5 = -1073741811;
    goto LABEL_6;
  }
  if ( Options != 8 )
    goto LABEL_11;
  v9 = *(void **)v3->AssociatedIrp.MasterIrp;
LABEL_13:
  v5 = ObReferenceObjectByHandle(v9, 0, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
  if ( v5 < 0 )
    goto LABEL_6;
  v10 = *((_QWORD *)Object + 1);
  ObfDereferenceObject(Object);
  v4[8] = v4[8] & 0xFFFFFFF3 | 4;
  ExAcquireResourceExclusiveLite(&Resource, 1u);
  v11 = (__int64 *)qword_1400072F0;
  if ( (__int64 *)qword_1400072F0 != &qword_1400072F0 )
  {
    do
    {
      v12 = (__int64)(v11 - 4);
      v11 = (__int64 *)*v11;
      ExAcquireFastMutex((PFAST_MUTEX)(v12 + 336));
      *(_QWORD *)(v12 + 392) = KeGetCurrentThread();
      if ( *(_QWORD *)(*(_QWORD *)(v12 + 8) + 16LL) == v10 )
      {
        IoAcquireVpbSpinLock(&Irql);
        if ( *(_QWORD *)(v10 + 56) == *(_QWORD *)(v12 + 8) )
        {
          v13 = *(_DWORD **)(v12 + 560);
          memset(v13, 0, 0x60u);
          *v13 = 6291466;
          *((_QWORD *)v13 + 2) = v10;
          *((_WORD *)v13 + 2) = *(_WORD *)(*(_QWORD *)(v10 + 56) + 4LL) & 8;
          *(_QWORD *)(v10 + 56) = v13;
          *(_QWORD *)(v12 + 560) = 0;
        }
        IoReleaseVpbSpinLock(Irql);
        if ( *(_DWORD *)(v12 + 52) != 4 )
          *(_DWORD *)(v12 + 52) = 3;
        *(_QWORD *)(v12 + 392) = 0;
        ExReleaseFastMutex((PFAST_MUTEX)(v12 + 336));
        CdAcquireResource(v4, v12 + 128, 0, 0);
        CdPurgeVolume((__int64)v4, v12, 0);
        if ( (unsigned __int8)CdCheckForDismount(v4, v12, 0) )
          ExReleaseResourceLite((PERESOURCE)(v12 + 128));
      }
      else
      {
        *(_QWORD *)(v12 + 392) = 0;
        ExReleaseFastMutex((PFAST_MUTEX)(v12 + 336));
      }
    }
    while ( v11 != &qword_1400072F0 );
    v3 = v15;
  }
  ExReleaseResourceLite(&Resource);
  CdCompleteRequest(v4, v3, 0);
  return 0;
}

```

## disassembly

```asm
0x140001d0c  mov     rax, rsp
0x140001d0f  mov     [rax+10h], rdx
0x140001d13  push    rbx
0x140001d14  push    rbp
0x140001d15  push    rsi
0x140001d16  push    rdi
0x140001d17  push    r12
0x140001d19  push    r14
0x140001d1b  push    r15
0x140001d1d  sub     rsp, 40h
0x140001d21  mov     rbx, [rdx+0B8h]
0x140001d28  mov     rdi, rdx
0x140001d2b  mov     byte ptr [rax+18h], 0
0x140001d2f  mov     rsi, rcx
0x140001d32  mov     qword ptr [rax-48h], 0
0x140001d3a  mov     rax, cs:DeviceObject
0x140001d41  mov     qword ptr [rsp+78h+PrivilegeValue.LowPart], 7
0x140001d4d  cmp     [rbx+28h], rax
0x140001d51  jz      short loc_140001D67
0x140001d53  mov     ebx, 0C0000010h
0x140001d58  mov     r8d, ebx
0x140001d5b  call    CdCompleteRequest
0x140001d60  mov     eax, ebx
0x140001d62  jmp     loc_140001FBA
0x140001d67  mov     dl, [rdx+40h]; PreviousMode
0x140001d6a  mov     rcx, qword ptr [rsp+78h+PrivilegeValue.LowPart]; PrivilegeValue
0x140001d72  call    cs:__imp_SeSinglePrivilegeCheck
0x140001d79  nop     dword ptr [rax+rax+00h]
0x140001d7e  test    al, al
0x140001d80  jnz     short loc_140001D8F
0x140001d82  mov     ebx, 0C0000061h
0x140001d87  mov     rdx, rdi
0x140001d8a  mov     rcx, rsi
0x140001d8d  jmp     short loc_140001D58
0x140001d8f  mov     rcx, rdi; Irp
0x140001d92  call    cs:__imp_IoIs32bitProcess
0x140001d99  nop     dword ptr [rax+rax+00h]
0x140001d9e  mov     ecx, [rbx+10h]
0x140001da1  test    al, al
0x140001da3  jz      short loc_140001DB3
0x140001da5  cmp     ecx, 4
0x140001da8  jnz     short loc_140001DB8
0x140001daa  mov     rax, [rdi+18h]
0x140001dae  movsxd  rcx, dword ptr [rax]
0x140001db1  jmp     short loc_140001DC6
0x140001db3  cmp     ecx, 8
0x140001db6  jz      short loc_140001DBF
0x140001db8  mov     ebx, 0C000000Dh
0x140001dbd  jmp     short loc_140001D87
0x140001dbf  mov     rax, [rdi+18h]
0x140001dc3  mov     rcx, [rax]; Handle
0x140001dc6  mov     r8, cs:__imp_IoFileObjectType
0x140001dcd  lea     rax, [rsp+78h+var_48]
0x140001dd2  mov     [rsp+78h+HandleInformation], 0; HandleInformation
0x140001ddb  xor     r9d, r9d; AccessMode
0x140001dde  xor     edx, edx; DesiredAccess
0x140001de0  mov     [rsp+78h+Object], rax; Object
0x140001de5  mov     r8, [r8]; ObjectType
0x140001de8  call    cs:__imp_ObReferenceObjectByHandle
0x140001def  nop     dword ptr [rax+rax+00h]
0x140001df4  mov     ebx, eax
0x140001df6  test    eax, eax
0x140001df8  js      short loc_140001D87
0x140001dfa  mov     rcx, [rsp+78h+var_48]; Object
0x140001dff  mov     r15, [rcx+8]
0x140001e03  call    cs:__imp_ObfDereferenceObject
0x140001e0a  nop     dword ptr [rax+rax+00h]
0x140001e0f  mov     eax, [rsi+20h]
0x140001e12  lea     rcx, Resource; Resource
0x140001e19  and     eax, 0FFFFFFF7h
0x140001e1c  mov     dl, 1; Wait
0x140001e1e  or      eax, 4
0x140001e21  mov     [rsi+20h], eax
0x140001e24  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140001e2b  nop     dword ptr [rax+rax+00h]
0x140001e30  mov     r14, cs:qword_1400072F0
0x140001e37  lea     rax, qword_1400072F0
0x140001e3e  cmp     r14, rax
0x140001e41  jz      loc_140001F97
0x140001e47  mov     edi, 8
0x140001e4c  lea     rbp, [r14-20h]
0x140001e50  mov     r14, [r14]
0x140001e53  lea     r12, [rbp+150h]
0x140001e5a  mov     rcx, r12; FastMutex
0x140001e5d  call    cs:__imp_ExAcquireFastMutex
0x140001e64  nop     dword ptr [rax+rax+00h]
0x140001e69  mov     rax, gs:188h
0x140001e72  mov     [rbp+188h], rax
0x140001e79  mov     rax, [rbp+8]
0x140001e7d  cmp     [rax+10h], r15
0x140001e81  jnz     loc_140001F65
0x140001e87  lea     rcx, [rsp+78h+Irql]; Irql
0x140001e8f  call    cs:__imp_IoAcquireVpbSpinLock
0x140001e96  nop     dword ptr [rax+rax+00h]
0x140001e9b  mov     rax, [rbp+8]
0x140001e9f  cmp     [r15+38h], rax
0x140001ea3  jnz     short loc_140001EE2
0x140001ea5  mov     rbx, [rbp+230h]
0x140001eac  xor     edx, edx; Val
0x140001eae  mov     rcx, rbx; void *
0x140001eb1  lea     r8d, [rdx+60h]; Size
0x140001eb5  call    memset
0x140001eba  mov     dword ptr [rbx], 60000Ah
0x140001ec0  mov     [rbx+10h], r15
0x140001ec4  mov     rax, [r15+38h]
0x140001ec8  movzx   ecx, word ptr [rax+4]
0x140001ecc  and     cx, di
0x140001ecf  mov     [rbx+4], cx
0x140001ed3  mov     [r15+38h], rbx
0x140001ed7  mov     qword ptr [rbp+230h], 0
0x140001ee2  mov     cl, [rsp+78h+Irql]; Irql
0x140001ee9  call    cs:__imp_IoReleaseVpbSpinLock
0x140001ef0  nop     dword ptr [rax+rax+00h]
0x140001ef5  cmp     dword ptr [rbp+34h], 4
0x140001ef9  jz      short loc_140001F02
0x140001efb  mov     dword ptr [rbp+34h], 3
0x140001f02  mov     rcx, r12; FastMutex
0x140001f05  mov     qword ptr [rbp+188h], 0
0x140001f10  call    cs:__imp_ExReleaseFastMutex
0x140001f17  nop     dword ptr [rax+rax+00h]
0x140001f1c  lea     rbx, [rbp+80h]
0x140001f23  xor     r9d, r9d
0x140001f26  mov     rdx, rbx
0x140001f29  xor     r8d, r8d
0x140001f2c  mov     rcx, rsi
0x140001f2f  call    CdAcquireResource
0x140001f34  xor     r8d, r8d
0x140001f37  mov     rdx, rbp
0x140001f3a  mov     rcx, rsi
0x140001f3d  call    CdPurgeVolume
0x140001f42  xor     r8d, r8d
0x140001f45  mov     rdx, rbp
0x140001f48  mov     rcx, rsi
0x140001f4b  call    CdCheckForDismount
0x140001f50  test    al, al
0x140001f52  jz      short loc_140001F7F
0x140001f54  mov     rcx, rbx; Resource
0x140001f57  call    cs:__imp_ExReleaseResourceLite
0x140001f5e  nop     dword ptr [rax+rax+00h]
0x140001f63  jmp     short loc_140001F7F
0x140001f65  mov     rcx, r12; FastMutex
0x140001f68  mov     qword ptr [rbp+188h], 0
0x140001f73  call    cs:__imp_ExReleaseFastMutex
0x140001f7a  nop     dword ptr [rax+rax+00h]
0x140001f7f  lea     rax, qword_1400072F0
0x140001f86  cmp     r14, rax
0x140001f89  jnz     loc_140001E4C
0x140001f8f  mov     rdi, [rsp+78h+arg_8]
0x140001f97  lea     rcx, Resource; Resource
0x140001f9e  call    cs:__imp_ExReleaseResourceLite
0x140001fa5  nop     dword ptr [rax+rax+00h]
0x140001faa  xor     r8d, r8d
0x140001fad  mov     rdx, rdi
0x140001fb0  mov     rcx, rsi
0x140001fb3  call    CdCompleteRequest
0x140001fb8  xor     eax, eax
0x140001fba  add     rsp, 40h
0x140001fbe  pop     r15
0x140001fc0  pop     r14
0x140001fc2  pop     r12
0x140001fc4  pop     rdi
0x140001fc5  pop     rsi
0x140001fc6  pop     rbp
0x140001fc7  pop     rbx
0x140001fc8  retn
```
