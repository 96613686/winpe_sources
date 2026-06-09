# CKSThunkDevice::CheckIrpForStackAdjustmentNative(_IRP *,_IRP_STATUS,long *)

- ea: `0x140001ba0`
- end: `0x140001e06`
- name: `?CheckIrpForStackAdjustmentNative@CKSThunkDevice@@AEAA?AW4_IRP_DISPOSITION@@PEAU_IRP@@W4_IRP_STATUS@@PEAJ@Z`
- size: `614`
- prototype: `__int64 __fastcall(__int64, struct _IRP *, int, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1400021e0`

## callees

- `0x1400010f4`
- `0x140001ba0`
- `0x1400022cc`
- `0x140004140`
- `0x1400041f0`
- `0x14000b5e0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140001d83`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001d83`
- `ntoskrnl!ProbeForRead` at `0x140001c35`
- `ntoskrnl!ProbeForRead` at `0x140001d55`
- `ntoskrnl!ProbeForRead` at `0x140001c35`
- `ntoskrnl!ProbeForRead` at `0x140001d55`
- `ntoskrnl!KeReleaseMutex` at `0x140001db9`
- `ntoskrnl!KeReleaseMutex` at `0x140001db9`

## pseudocode

```c
__int64 __fastcall CKSThunkDevice::CheckIrpForStackAdjustmentNative(__int64 a1, struct _IRP *a2, int a3, int *a4)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  unsigned int v8; // esi
  __int64 v9; // r13
  char v10; // r12
  int IsEnabledDeviceUsageNoInline; // eax
  KPROCESSOR_MODE RequestorMode; // cl
  PNAMED_PIPE_CREATE_PARAMETERS Parameters; // rdx
  PNAMED_PIPE_CREATE_PARAMETERS v14; // rax
  unsigned __int64 v15; // rcx
  int v16; // eax
  int v17; // eax
  KPROCESSOR_MODE v18; // cl
  PVOID UserBuffer; // rdx
  int v20; // eax
  char v21; // dl
  __int128 v23; // [rsp+30h] [rbp-68h] BYREF
  __int64 v24; // [rsp+40h] [rbp-58h]
  _QWORD v25[2]; // [rsp+48h] [rbp-50h] BYREF
  PFILE_OBJECT FileObject; // [rsp+58h] [rbp-40h]
  PFILE_OBJECT v27; // [rsp+60h] [rbp-38h]
  int v28; // [rsp+B0h] [rbp+18h] BYREF
  int *v29; // [rsp+B8h] [rbp+20h]

  v29 = a4;
  v28 = a3;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v8 = 1;
  v23 = 0;
  v24 = 0;
  v28 = 0;
  v9 = *(_QWORD *)(a1 + 56);
  v10 = *(_BYTE *)(v9 + 76);
  if ( CurrentStackLocation->Parameters.Create.Options >= 0x18 )
  {
    IsEnabledDeviceUsageNoInline = Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline();
    RequestorMode = a2->RequestorMode;
    if ( IsEnabledDeviceUsageNoInline )
    {
      Parameters = CurrentStackLocation->Parameters.CreatePipe.Parameters;
      if ( RequestorMode )
        RtlCopyFromUser(&v23, Parameters, 0x18u);
      else
        RtlCopyVolatileMemory(&v23, Parameters, 0x18u);
    }
    else
    {
      if ( RequestorMode )
        ProbeForRead(
          CurrentStackLocation->Parameters.CreatePipe.Parameters,
          CurrentStackLocation->Parameters.Create.Options,
          1u);
      v14 = CurrentStackLocation->Parameters.CreatePipe.Parameters;
      v23 = *(_OWORD *)&v14->NamedPipeType;
      v24 = *(_QWORD *)&v14->InboundQuota;
    }
    v15 = v23;
    if ( v23 == *(_OWORD *)&GUID_2f2c8ddd_4198_4fac_ba29_61bb05b7de06 && !(_DWORD)v24 && (v24 & 0x200000000LL) != 0 )
    {
      if ( a2->RequestorMode )
      {
        v16 = -1073741808;
      }
      else
      {
        v25[0] = 0;
        v25[1] = v9;
        FileObject = CurrentStackLocation->FileObject;
        v27 = FileObject;
        v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD *))&CurrentStackLocation->Parameters.CreatePipe.Parameters[1].InboundQuota)(
                *(unsigned int *)a2->UserBuffer,
                0,
                v25);
        v15 = v23;
      }
      *a4 = v16;
      v8 = 0;
    }
    if ( __PAIR128__(*((unsigned __int64 *)&v23 + 1), v15) == *(_OWORD *)&GUID_1d58c920_ac9b_11cf_a5d6_28db04c10000
      && !(_DWORD)v24
      && (v24 & 0x200000000LL) != 0
      && CurrentStackLocation->Parameters.Read.Length >= 4 )
    {
      v17 = Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline();
      v18 = a2->RequestorMode;
      if ( v17 )
      {
        UserBuffer = a2->UserBuffer;
        if ( v18 )
          RtlCopyFromUser(&v28, UserBuffer, 4u);
        else
          RtlCopyVolatileMemory(&v28, UserBuffer, 4u);
      }
      else
      {
        if ( v18 )
          ProbeForRead(a2->UserBuffer, 4u, 1u);
        v28 = *(_DWORD *)a2->UserBuffer;
      }
      KeWaitForSingleObject((PVOID)(a1 + 72), Executive, 0, 0, 0);
      v20 = CKernelFilterDevice::SynchronousForwardIrp((CKernelFilterDevice *)a1, a2);
      *a4 = v20;
      if ( v20 >= 0 )
      {
        v21 = *(_BYTE *)(v9 + 76);
        if ( v10 != v21 )
          *(_BYTE *)(*(_QWORD *)(a1 + 40) + 76LL) = v21 + 1;
      }
      KeReleaseMutex((PRKMUTEX)(a1 + 72), 0);
      return 0;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x140001ba0  mov     r11, rsp
0x140001ba3  mov     [r11+8], rbx
0x140001ba7  mov     [r11+10h], rsi
0x140001bab  mov     [r11+20h], r9
0x140001baf  mov     [r11+18h], r8d
0x140001bb3  push    rdi
0x140001bb4  push    r12
0x140001bb6  push    r13
0x140001bb8  push    r14
0x140001bba  push    r15
0x140001bbc  sub     rsp, 70h
0x140001bc0  mov     r15, r9
0x140001bc3  mov     rbx, rdx
0x140001bc6  mov     r14, rcx
0x140001bc9  mov     rdi, [rdx+0B8h]
0x140001bd0  mov     esi, 1
0x140001bd5  xorps   xmm0, xmm0
0x140001bd8  xor     eax, eax
0x140001bda  movups  [rsp+98h+var_68], xmm0
0x140001bdf  mov     [r11-58h], rax
0x140001be3  mov     [r11+18h], eax
0x140001be7  mov     r13, [rcx+38h]
0x140001beb  mov     r12b, [r13+4Ch]
0x140001bef  cmp     dword ptr [rdi+10h], 18h
0x140001bf3  jb      loc_140001DE9
0x140001bf9  call    Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline
0x140001bfe  mov     cl, [rbx+40h]
0x140001c01  test    eax, eax
0x140001c03  jz      short loc_140001C24
0x140001c05  mov     rdx, [rdi+20h]; Src
0x140001c09  lea     r8d, [rsi+17h]; Size
0x140001c0d  test    cl, cl
0x140001c0f  lea     rcx, [rsp+98h+var_68]; void *
0x140001c14  jz      short loc_140001C1D
0x140001c16  call    RtlCopyFromUser
0x140001c1b  jmp     short loc_140001C58
0x140001c1d  call    RtlCopyVolatileMemory
0x140001c22  jmp     short loc_140001C58
0x140001c24  test    cl, cl
0x140001c26  jz      short loc_140001C41
0x140001c28  mov     edx, [rdi+10h]; Length
0x140001c2b  mov     r8d, 1; Alignment
0x140001c31  mov     rcx, [rdi+20h]; Address
0x140001c35  call    cs:__imp_ProbeForRead
0x140001c3c  nop     dword ptr [rax+rax+00h]
0x140001c41  mov     rax, [rdi+20h]
0x140001c45  movups  xmm0, xmmword ptr [rax]
0x140001c48  movups  [rsp+98h+var_68], xmm0
0x140001c4d  movsd   xmm1, qword ptr [rax+10h]
0x140001c52  movsd   [rsp+98h+var_58], xmm1
0x140001c58  mov     rcx, qword ptr [rsp+98h+var_68]
0x140001c5d  cmp     rcx, qword ptr cs:_GUID_2f2c8ddd_4198_4fac_ba29_61bb05b7de06.Data1
0x140001c64  jnz     short loc_140001CD5
0x140001c66  mov     rax, qword ptr cs:_GUID_2f2c8ddd_4198_4fac_ba29_61bb05b7de06.Data4
0x140001c6d  cmp     qword ptr [rsp+98h+var_68+8], rax
0x140001c72  jnz     short loc_140001CD5
0x140001c74  cmp     dword ptr [rsp+98h+var_58], 0
0x140001c79  jnz     short loc_140001CD5
0x140001c7b  mov     rax, [rsp+98h+var_58]
0x140001c80  shr     rax, 20h
0x140001c84  test    al, 2
0x140001c86  jz      short loc_140001CD5
0x140001c88  cmp     byte ptr [rbx+40h], 0
0x140001c8c  jnz     short loc_140001CCB
0x140001c8e  mov     [rsp+98h+var_50], 0
0x140001c97  mov     [rsp+98h+var_48], r13
0x140001c9c  mov     rax, [rdi+30h]
0x140001ca0  mov     [rsp+98h+var_40], rax
0x140001ca5  mov     [rsp+98h+var_38], rax
0x140001caa  mov     rax, [rdi+20h]
0x140001cae  mov     rcx, [rbx+70h]
0x140001cb2  mov     rax, [rax+38h]
0x140001cb6  lea     r8, [rsp+98h+var_50]
0x140001cbb  xor     edx, edx
0x140001cbd  mov     ecx, [rcx]
0x140001cbf  call    _guard_dispatch_icall
0x140001cc4  mov     rcx, qword ptr [rsp+98h+var_68]
0x140001cc9  jmp     short loc_140001CD0
0x140001ccb  mov     eax, 0C0000010h
0x140001cd0  mov     [r15], eax
0x140001cd3  xor     esi, esi
0x140001cd5  cmp     rcx, qword ptr cs:_GUID_1d58c920_ac9b_11cf_a5d6_28db04c10000.Data1
0x140001cdc  jnz     loc_140001DE9
0x140001ce2  mov     rax, qword ptr cs:_GUID_1d58c920_ac9b_11cf_a5d6_28db04c10000.Data4
0x140001ce9  cmp     qword ptr [rsp+98h+var_68+8], rax
0x140001cee  jnz     loc_140001DE9
0x140001cf4  cmp     dword ptr [rsp+98h+var_58], 0
0x140001cf9  jnz     loc_140001DE9
0x140001cff  test    byte ptr [rsp+98h+var_58+4], 2
0x140001d04  jz      loc_140001DE9
0x140001d0a  cmp     dword ptr [rdi+8], 4
0x140001d0e  jb      loc_140001DE9
0x140001d14  call    Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline
0x140001d19  mov     cl, [rbx+40h]
0x140001d1c  test    eax, eax
0x140001d1e  jz      short loc_140001D44
0x140001d20  mov     rdx, [rbx+70h]; Src
0x140001d24  mov     r8d, 4; Size
0x140001d2a  test    cl, cl
0x140001d2c  lea     rcx, [rsp+98h+arg_10]; void *
0x140001d34  jz      short loc_140001D3D
0x140001d36  call    RtlCopyFromUser
0x140001d3b  jmp     short loc_140001D6E
0x140001d3d  call    RtlCopyVolatileMemory
0x140001d42  jmp     short loc_140001D6E
0x140001d44  test    cl, cl
0x140001d46  jz      short loc_140001D61
0x140001d48  mov     edx, 4; Length
0x140001d4d  lea     r8d, [rdx-3]; Alignment
0x140001d51  mov     rcx, [rbx+70h]; Address
0x140001d55  call    cs:__imp_ProbeForRead
0x140001d5c  nop     dword ptr [rax+rax+00h]
0x140001d61  mov     rax, [rbx+70h]
0x140001d65  mov     ecx, [rax]
0x140001d67  mov     [rsp+98h+arg_10], ecx
0x140001d6e  mov     [rsp+98h+Timeout], 0; Timeout
0x140001d77  xor     r9d, r9d; Alertable
0x140001d7a  xor     r8d, r8d; WaitMode
0x140001d7d  xor     edx, edx; WaitReason
0x140001d7f  lea     rcx, [r14+48h]; Object
0x140001d83  call    cs:__imp_KeWaitForSingleObject
0x140001d8a  nop     dword ptr [rax+rax+00h]
0x140001d8f  mov     rdx, rbx; struct _IRP *
0x140001d92  mov     rcx, r14; this
0x140001d95  call    ?SynchronousForwardIrp@CKernelFilterDevice@@QEAAJPEAU_IRP@@@Z; CKernelFilterDevice::SynchronousForwardIrp(_IRP *)
0x140001d9a  mov     [r15], eax
0x140001d9d  test    eax, eax
0x140001d9f  js      short loc_140001DB3
0x140001da1  mov     dl, [r13+4Ch]
0x140001da5  cmp     r12b, dl
0x140001da8  jz      short loc_140001DB3
0x140001daa  inc     dl
0x140001dac  mov     rax, [r14+28h]
0x140001db0  mov     [rax+4Ch], dl
0x140001db3  xor     edx, edx; Wait
0x140001db5  lea     rcx, [r14+48h]; Mutex
0x140001db9  call    cs:__imp_KeReleaseMutex
0x140001dc0  nop     dword ptr [rax+rax+00h]
0x140001dc5  xor     esi, esi
0x140001dc7  jmp     short loc_140001DE9
0x140001dc9  mov     ecx, eax
0x140001dcb  mov     rax, [rsp+98h+arg_18]
0x140001dd3  mov     [rax], ecx
0x140001dd5  xor     eax, eax
0x140001dd7  jmp     short loc_140001DEB
0x140001dd9  mov     ecx, eax
0x140001ddb  mov     rax, [rsp+98h+arg_18]
0x140001de3  mov     [rax], ecx
0x140001de5  xor     eax, eax
0x140001de7  jmp     short loc_140001DEB
0x140001de9  mov     eax, esi
0x140001deb  lea     r11, [rsp+98h+var_28]
0x140001df0  mov     rbx, [r11+30h]
0x140001df4  mov     rsi, [r11+38h]
0x140001df8  mov     rsp, r11
0x140001dfb  pop     r15
0x140001dfd  pop     r14
0x140001dff  pop     r13
0x140001e01  pop     r12
0x140001e03  pop     rdi
0x140001e04  retn
```
