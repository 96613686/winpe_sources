# CKSThunkDevice::CheckIrpForStackAdjustmentNative(_IRP *,_IRP_STATUS,long *)

- ea: `0x140001ba0`
- end: `0x140001d8a`
- name: `?CheckIrpForStackAdjustmentNative@CKSThunkDevice@@AEAA?AW4_IRP_DISPOSITION@@PEAU_IRP@@W4_IRP_STATUS@@PEAJ@Z`
- size: `490`
- prototype: `__int64 __fastcall(__int64, __int64, int, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140002160`

## callees

- `0x1400010f4`
- `0x140001ba0`
- `0x1400036c0`
- `0x140003770`
- `0x14000a5e0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140001d07`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001d07`
- `ntoskrnl!KeReleaseMutex` at `0x140001d3d`
- `ntoskrnl!KeReleaseMutex` at `0x140001d3d`

## pseudocode

```c
__int64 __fastcall CKSThunkDevice::CheckIrpForStackAdjustmentNative(__int64 a1, __int64 a2, int a3, int *a4)
{
  __int64 v7; // rsi
  unsigned int v8; // edi
  __int64 v9; // r13
  char v10; // r12
  void *v11; // rdx
  unsigned __int64 v12; // rcx
  int v13; // eax
  void *v14; // rdx
  int v15; // eax
  char v16; // dl
  __int128 v18; // [rsp+30h] [rbp-68h] BYREF
  __int64 v19; // [rsp+40h] [rbp-58h]
  _QWORD v20[2]; // [rsp+48h] [rbp-50h] BYREF
  __int64 v21; // [rsp+58h] [rbp-40h]
  __int64 v22; // [rsp+60h] [rbp-38h]
  int v23; // [rsp+B0h] [rbp+18h] BYREF
  int *v24; // [rsp+B8h] [rbp+20h]

  v24 = a4;
  v23 = a3;
  v7 = *(_QWORD *)(a2 + 184);
  v8 = 1;
  v18 = 0;
  v19 = 0;
  v23 = 0;
  v9 = *(_QWORD *)(a1 + 56);
  v10 = *(_BYTE *)(v9 + 76);
  if ( *(_DWORD *)(v7 + 16) >= 0x18u )
  {
    v11 = *(void **)(v7 + 32);
    if ( *(_BYTE *)(a2 + 64) )
      RtlCopyFromUser(&v18, v11, 0x18u);
    else
      RtlCopyVolatileMemory(&v18, v11, 0x18u);
    v12 = v18;
    if ( v18 == *(_OWORD *)&GUID_2f2c8ddd_4198_4fac_ba29_61bb05b7de06 && !(_DWORD)v19 && (v19 & 0x200000000LL) != 0 )
    {
      if ( *(_BYTE *)(a2 + 64) )
      {
        v13 = -1073741808;
      }
      else
      {
        v20[0] = 0;
        v20[1] = v9;
        v21 = *(_QWORD *)(v7 + 48);
        v22 = v21;
        v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD *))(*(_QWORD *)(v7 + 32) + 56LL))(
                **(unsigned int **)(a2 + 112),
                0,
                v20);
        v12 = v18;
      }
      *a4 = v13;
      v8 = 0;
    }
    if ( __PAIR128__(*((unsigned __int64 *)&v18 + 1), v12) == *(_OWORD *)&GUID_1d58c920_ac9b_11cf_a5d6_28db04c10000
      && !(_DWORD)v19
      && (v19 & 0x200000000LL) != 0
      && *(_DWORD *)(v7 + 8) >= 4u )
    {
      v14 = *(void **)(a2 + 112);
      if ( *(_BYTE *)(a2 + 64) )
        RtlCopyFromUser(&v23, v14, 4u);
      else
        RtlCopyVolatileMemory(&v23, v14, 4u);
      KeWaitForSingleObject((PVOID)(a1 + 72), Executive, 0, 0, 0);
      v15 = CKernelFilterDevice::SynchronousForwardIrp((CKernelFilterDevice *)a1, (struct _IRP *)a2);
      *a4 = v15;
      if ( v15 >= 0 )
      {
        v16 = *(_BYTE *)(v9 + 76);
        if ( v10 != v16 )
          *(_BYTE *)(*(_QWORD *)(a1 + 40) + 76LL) = v16 + 1;
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
0x140001bc9  mov     rsi, [rdx+0B8h]
0x140001bd0  mov     edi, 1
0x140001bd5  xorps   xmm0, xmm0
0x140001bd8  xor     eax, eax
0x140001bda  movups  [rsp+98h+var_68], xmm0
0x140001bdf  mov     [r11-58h], rax
0x140001be3  mov     [r11+18h], eax
0x140001be7  mov     r13, [rcx+38h]
0x140001beb  mov     r12b, [r13+4Ch]
0x140001bef  lea     r8d, [rdi+17h]; Size
0x140001bf3  cmp     [rsi+10h], r8d
0x140001bf7  jb      loc_140001D6D
0x140001bfd  mov     rdx, [rsi+20h]; Src
0x140001c01  lea     rcx, [r11-68h]; void *
0x140001c05  cmp     [rbx+40h], al
0x140001c08  jz      short loc_140001C11
0x140001c0a  call    RtlCopyFromUser
0x140001c0f  jmp     short loc_140001C17
0x140001c11  call    RtlCopyVolatileMemory
0x140001c16  nop
0x140001c17  mov     rcx, qword ptr [rsp+98h+var_68]
0x140001c1c  cmp     rcx, qword ptr cs:_GUID_2f2c8ddd_4198_4fac_ba29_61bb05b7de06.Data1
0x140001c23  jnz     short loc_140001C8E
0x140001c25  mov     rax, qword ptr cs:_GUID_2f2c8ddd_4198_4fac_ba29_61bb05b7de06.Data4
0x140001c2c  cmp     qword ptr [rsp+98h+var_68+8], rax
0x140001c31  jnz     short loc_140001C8E
0x140001c33  cmp     [rsp+98h+var_58], 0
0x140001c38  jnz     short loc_140001C8E
0x140001c3a  test    [rsp+98h+var_54], 2
0x140001c3f  jz      short loc_140001C8E
0x140001c41  cmp     byte ptr [rbx+40h], 0
0x140001c45  jnz     short loc_140001C84
0x140001c47  mov     [rsp+98h+var_50], 0
0x140001c50  mov     [rsp+98h+var_48], r13
0x140001c55  mov     rax, [rsi+30h]
0x140001c59  mov     [rsp+98h+var_40], rax
0x140001c5e  mov     [rsp+98h+var_38], rax
0x140001c63  mov     rax, [rsi+20h]
0x140001c67  mov     rcx, [rbx+70h]
0x140001c6b  mov     rax, [rax+38h]
0x140001c6f  lea     r8, [rsp+98h+var_50]
0x140001c74  xor     edx, edx
0x140001c76  mov     ecx, [rcx]
0x140001c78  call    _guard_dispatch_icall
0x140001c7d  mov     rcx, qword ptr [rsp+98h+var_68]
0x140001c82  jmp     short loc_140001C89
0x140001c84  mov     eax, 0C0000010h
0x140001c89  mov     [r15], eax
0x140001c8c  xor     edi, edi
0x140001c8e  cmp     rcx, qword ptr cs:_GUID_1d58c920_ac9b_11cf_a5d6_28db04c10000.Data1
0x140001c95  jnz     loc_140001D6D
0x140001c9b  mov     rax, qword ptr cs:_GUID_1d58c920_ac9b_11cf_a5d6_28db04c10000.Data4
0x140001ca2  cmp     qword ptr [rsp+98h+var_68+8], rax
0x140001ca7  jnz     loc_140001D6D
0x140001cad  cmp     [rsp+98h+var_58], 0
0x140001cb2  jnz     loc_140001D6D
0x140001cb8  test    [rsp+98h+var_54], 2
0x140001cbd  jz      loc_140001D6D
0x140001cc3  mov     r8d, 4; Size
0x140001cc9  cmp     [rsi+8], r8d
0x140001ccd  jb      loc_140001D6D
0x140001cd3  mov     rdx, [rbx+70h]; Src
0x140001cd7  lea     rcx, [rsp+98h+arg_10]; void *
0x140001cdf  cmp     byte ptr [rbx+40h], 0
0x140001ce3  jz      short loc_140001CEC
0x140001ce5  call    RtlCopyFromUser
0x140001cea  jmp     short loc_140001CF2
0x140001cec  call    RtlCopyVolatileMemory
0x140001cf1  nop
0x140001cf2  mov     [rsp+98h+Timeout], 0; Timeout
0x140001cfb  xor     r9d, r9d; Alertable
0x140001cfe  xor     r8d, r8d; WaitMode
0x140001d01  xor     edx, edx; WaitReason
0x140001d03  lea     rcx, [r14+48h]; Object
0x140001d07  call    cs:__imp_KeWaitForSingleObject
0x140001d0e  nop     dword ptr [rax+rax+00h]
0x140001d13  mov     rdx, rbx; struct _IRP *
0x140001d16  mov     rcx, r14; this
0x140001d19  call    ?SynchronousForwardIrp@CKernelFilterDevice@@QEAAJPEAU_IRP@@@Z; CKernelFilterDevice::SynchronousForwardIrp(_IRP *)
0x140001d1e  mov     [r15], eax
0x140001d21  test    eax, eax
0x140001d23  js      short loc_140001D37
0x140001d25  mov     dl, [r13+4Ch]
0x140001d29  cmp     r12b, dl
0x140001d2c  jz      short loc_140001D37
0x140001d2e  inc     dl
0x140001d30  mov     rax, [r14+28h]
0x140001d34  mov     [rax+4Ch], dl
0x140001d37  xor     edx, edx; Wait
0x140001d39  lea     rcx, [r14+48h]; Mutex
0x140001d3d  call    cs:__imp_KeReleaseMutex
0x140001d44  nop     dword ptr [rax+rax+00h]
0x140001d49  xor     edi, edi
0x140001d4b  jmp     short loc_140001D6D
0x140001d4d  mov     ecx, eax
0x140001d4f  mov     rax, [rsp+98h+arg_18]
0x140001d57  mov     [rax], ecx
0x140001d59  xor     eax, eax
0x140001d5b  jmp     short loc_140001D6F
0x140001d5d  mov     ecx, eax
0x140001d5f  mov     rax, [rsp+98h+arg_18]
0x140001d67  mov     [rax], ecx
0x140001d69  xor     eax, eax
0x140001d6b  jmp     short loc_140001D6F
0x140001d6d  mov     eax, edi
0x140001d6f  lea     r11, [rsp+98h+var_28]
0x140001d74  mov     rbx, [r11+30h]
0x140001d78  mov     rsi, [r11+38h]
0x140001d7c  mov     rsp, r11
0x140001d7f  pop     r15
0x140001d81  pop     r14
0x140001d83  pop     r13
0x140001d85  pop     r12
0x140001d87  pop     rdi
0x140001d88  retn
```
