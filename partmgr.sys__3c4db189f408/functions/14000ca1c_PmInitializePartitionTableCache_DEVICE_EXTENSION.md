# PmInitializePartitionTableCache(_DEVICE_EXTENSION *)

- ea: `0x14000ca1c`
- end: `0x14000cb2d`
- name: `?PmInitializePartitionTableCache@@YAJPEAU_DEVICE_EXTENSION@@@Z`
- size: `273`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140007674`

## callees

- `0x14000ca1c`
- `0x14001fda0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000cb0a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cb0a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000caf0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000caf0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000cacb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000cacb`

## string_xrefs

- `0x14000ca42`: `PartitionTableCache`

## pseudocode

```c
__int64 __fastcall PmInitializePartitionTableCache(struct _DEVICE_EXTENSION *a1)
{
  signed int DeviceParameterBinary; // edi
  _DWORD *v3; // r8
  __int64 v4; // r9
  unsigned int v5; // ecx
  unsigned int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rcx
  KIRQL v9; // al
  unsigned int v11; // [rsp+48h] [rbp+28h] BYREF
  PVOID P; // [rsp+50h] [rbp+30h] BYREF

  P = 0;
  v11 = 0;
  DeviceParameterBinary = PmGetDeviceParameterBinary(a1, L"PartitionTableCache", &P, &v11);
  if ( DeviceParameterBinary < 0 )
  {
LABEL_12:
    v3 = P;
    goto LABEL_13;
  }
  v3 = P;
  if ( v11 < 0x30 )
  {
LABEL_3:
    DeviceParameterBinary = -1073741820;
    goto LABEL_13;
  }
  v4 = *((unsigned int *)P + 1);
  v5 = -1;
  if ( (unsigned __int64)(144 * v4) > 0xFFFFFFFF )
  {
    DeviceParameterBinary = -1073741675;
  }
  else
  {
    v6 = 144 * v4 + 48;
    if ( v6 >= 0x30 )
      v5 = 144 * v4 + 48;
    DeviceParameterBinary = (unsigned int)(144 * v4) >= 0xFFFFFFD0 ? 0xC0000095 : 0;
    if ( v6 >= 0x30 )
    {
      if ( v11 < v5 )
        goto LABEL_3;
      v7 = 0;
      if ( (_DWORD)v4 )
      {
        do
        {
          v8 = 9 * v7;
          v7 = (unsigned int)(v7 + 1);
          v3[4 * v8 + 18] = 0;
          v3 = P;
        }
        while ( (unsigned int)v7 < *((_DWORD *)P + 1) );
      }
      v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 14);
      *((_QWORD *)a1 + 138) = P;
      P = 0;
      KeReleaseSpinLock((PKSPIN_LOCK)a1 + 14, v9);
      goto LABEL_12;
    }
  }
LABEL_13:
  if ( v3 )
    ExFreePoolWithTag(v3, 0);
  return (unsigned int)DeviceParameterBinary;
}

```

## disassembly

```asm
0x14000ca1c  mov     [rsp-18h+arg_0], rbx
0x14000ca21  push    rbp
0x14000ca22  push    rsi
0x14000ca23  push    rdi
0x14000ca24  mov     rbp, rsp
0x14000ca27  sub     rsp, 20h
0x14000ca2b  lea     r9, [rbp+arg_8]; unsigned int *
0x14000ca2f  mov     [rbp+P], 0
0x14000ca37  lea     r8, [rbp+P]; void **
0x14000ca3b  mov     [rbp+arg_8], 0
0x14000ca42  lea     rdx, aPartitiontable; "PartitionTableCache"
0x14000ca49  mov     rsi, rcx
0x14000ca4c  call    ?PmGetDeviceParameterBinary@@YAJPEAU_DEVICE_EXTENSION@@PEAGPEAPEAXPEAK@Z; PmGetDeviceParameterBinary(_DEVICE_EXTENSION *,ushort *,void * *,ulong *)
0x14000ca51  mov     edi, eax
0x14000ca53  test    eax, eax
0x14000ca55  js      loc_14000CAFC
0x14000ca5b  cmp     [rbp+arg_8], 30h ; '0'
0x14000ca5f  mov     r8, [rbp+P]
0x14000ca63  jnb     short loc_14000CA6F
0x14000ca65  mov     edi, 0C0000004h
0x14000ca6a  jmp     loc_14000CB00
0x14000ca6f  mov     r9d, [r8+4]
0x14000ca73  mov     ecx, 0FFFFFFFFh
0x14000ca78  lea     rax, [r9+r9*8]
0x14000ca7c  shl     rax, 4
0x14000ca80  cmp     rax, rcx
0x14000ca83  ja      loc_14000CB26
0x14000ca89  add     eax, 30h ; '0'
0x14000ca8c  cmp     eax, 30h ; '0'
0x14000ca8f  cmovnb  ecx, eax
0x14000ca92  sbb     edi, edi
0x14000ca94  and     edi, 0C0000095h
0x14000ca9a  cmp     eax, 30h ; '0'
0x14000ca9d  jb      short loc_14000CB00
0x14000ca9f  cmp     [rbp+arg_8], ecx
0x14000caa2  jb      short loc_14000CA65
0x14000caa4  xor     edx, edx
0x14000caa6  test    r9d, r9d
0x14000caa9  jz      short loc_14000CAC7
0x14000caab  lea     rcx, [rdx+rdx*8]
0x14000caaf  inc     edx
0x14000cab1  add     rcx, rcx
0x14000cab4  mov     dword ptr [r8+rcx*8+48h], 0
0x14000cabd  mov     r8, [rbp+P]
0x14000cac1  cmp     edx, [r8+4]
0x14000cac5  jb      short loc_14000CAAB
0x14000cac7  lea     rcx, [rsi+70h]; SpinLock
0x14000cacb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000cad2  nop     dword ptr [rax+rax+00h]
0x14000cad7  mov     rdx, [rbp+P]
0x14000cadb  lea     rcx, [rsi+70h]; SpinLock
0x14000cadf  mov     [rsi+450h], rdx
0x14000cae6  mov     dl, al; NewIrql
0x14000cae8  mov     [rbp+P], 0
0x14000caf0  call    cs:__imp_KeReleaseSpinLock
0x14000caf7  nop     dword ptr [rax+rax+00h]
0x14000cafc  mov     r8, [rbp+P]
0x14000cb00  test    r8, r8
0x14000cb03  jz      short loc_14000CB16
0x14000cb05  xor     edx, edx; Tag
0x14000cb07  mov     rcx, r8; P
0x14000cb0a  call    cs:__imp_ExFreePoolWithTag
0x14000cb11  nop     dword ptr [rax+rax+00h]
0x14000cb16  mov     rbx, [rsp+20h+arg_0]
0x14000cb1b  mov     eax, edi
0x14000cb1d  add     rsp, 20h
0x14000cb21  pop     rdi
0x14000cb22  pop     rsi
0x14000cb23  pop     rbp
0x14000cb24  retn
0x14000cb26  mov     edi, 0C0000095h
0x14000cb2b  jmp     short loc_14000CB00
```
