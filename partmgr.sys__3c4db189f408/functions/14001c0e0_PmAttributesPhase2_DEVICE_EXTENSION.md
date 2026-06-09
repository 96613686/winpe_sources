# PmAttributesPhase2(_DEVICE_EXTENSION *)

- ea: `0x14001c0e0`
- end: `0x14001c203`
- name: `?PmAttributesPhase2@@YAJPEAU_DEVICE_EXTENSION@@@Z`
- size: `291`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400068b0`
- `0x140007674`

## callees

- `0x14000ab3c`
- `0x14000ae88`
- `0x14001c0e0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001c15a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001c15a`
- `ntoskrnl!KeReleaseMutex` at `0x14001c1d5`
- `ntoskrnl!KeReleaseMutex` at `0x14001c1d5`

## pseudocode

```c
__int64 __fastcall PmAttributesPhase2(struct _DEVICE_EXTENSION *a1)
{
  unsigned int *v1; // rbp
  char *DeviceExtension; // rdi
  unsigned int v4; // edx
  int v5; // eax
  _QWORD v7[3]; // [rsp+30h] [rbp-58h] BYREF
  __int128 v8; // [rsp+48h] [rbp-40h]

  v1 = (unsigned int *)((char *)a1 + 516);
  memset((char *)v7 + 4, 0, 12);
  LODWORD(v7[0]) = 40;
  DeviceExtension = (char *)PmControlObject->DeviceExtension;
  v8 = 0;
  v7[2] = -1;
  if ( (ScReadNoFence((unsigned int *)a1 + 129) & 0x4000) == 0 )
  {
    KeWaitForSingleObject(DeviceExtension + 16, Executive, 0, 0, 0);
    if ( *((_DWORD *)DeviceExtension + 40) == 2 )
    {
      if ( (*(_DWORD *)(*((_QWORD *)a1 + 1) + 52LL) & 1) != 0 )
        goto LABEL_14;
      v4 = *(_DWORD *)(*((_QWORD *)a1 + 29) + 28LL);
      if ( v4 > 0x10 )
        goto LABEL_14;
      v5 = 67138;
      if ( !_bittest(&v5, v4) || (ScReadNoFence(v1) & 0x400) != 0 && DeviceExtension[168] )
        goto LABEL_14;
    }
    else if ( *((_DWORD *)DeviceExtension + 40) != 3
           && (*((_DWORD *)DeviceExtension + 40) != 4 || (*(_DWORD *)(*((_QWORD *)a1 + 1) + 52LL) & 0x40000) != 0) )
    {
      goto LABEL_14;
    }
    v7[1] = 3;
LABEL_14:
    KeReleaseMutex((PRKMUTEX)(DeviceExtension + 16), 0);
    BYTE4(v7[0]) = 1;
    return PmSetDiskAttributes((__int64)a1, (__int64)v7, 1);
  }
  v7[1] = 4;
  return PmSetDiskAttributes((__int64)a1, (__int64)v7, 1);
}

```

## disassembly

```asm
0x14001c0e0  push    rbx
0x14001c0e2  push    rbp
0x14001c0e3  push    rsi
0x14001c0e4  push    rdi
0x14001c0e5  sub     rsp, 68h
0x14001c0e9  mov     rax, cs:?PmControlObject@@3PEAU_DEVICE_OBJECT@@EA; _DEVICE_OBJECT * PmControlObject
0x14001c0f0  lea     rbp, [rcx+204h]
0x14001c0f7  mov     rbx, rcx
0x14001c0fa  mov     [rsp+88h+var_54], 0
0x14001c103  xorps   xmm0, xmm0
0x14001c106  mov     [rsp+88h+var_4C], 0
0x14001c10e  mov     rcx, rbp; unsigned int *
0x14001c111  mov     [rsp+88h+var_58], 28h ; '('
0x14001c119  mov     rdi, [rax+40h]
0x14001c11d  movdqu  [rsp+88h+var_40], xmm0
0x14001c123  mov     [rsp+88h+var_48], 0FFFFFFFFFFFFFFFFh
0x14001c12c  call    ?ScReadNoFence@@YAKPEAK@Z; ScReadNoFence(ulong *)
0x14001c131  bt      eax, 0Eh
0x14001c135  jnb     short loc_14001C145
0x14001c137  mov     [rsp+88h+var_54+4], 4
0x14001c140  jmp     loc_14001C1E6
0x14001c145  xor     r9d, r9d; Alertable
0x14001c148  mov     [rsp+88h+Timeout], 0; Timeout
0x14001c151  xor     r8d, r8d; WaitMode
0x14001c154  lea     rcx, [rdi+10h]; Object
0x14001c158  xor     edx, edx; WaitReason
0x14001c15a  call    cs:__imp_KeWaitForSingleObject
0x14001c161  nop     dword ptr [rax+rax+00h]
0x14001c166  mov     ecx, [rdi+0A0h]
0x14001c16c  sub     ecx, 2
0x14001c16f  jz      short loc_14001C18A
0x14001c171  sub     ecx, 1
0x14001c174  jz      short loc_14001C1C6
0x14001c176  cmp     ecx, 1
0x14001c179  jnz     short loc_14001C1CF
0x14001c17b  mov     rax, [rbx+8]
0x14001c17f  test    dword ptr [rax+34h], 40000h
0x14001c186  jnz     short loc_14001C1CF
0x14001c188  jmp     short loc_14001C1C6
0x14001c18a  mov     rax, [rbx+8]
0x14001c18e  mov     edx, [rax+34h]
0x14001c191  test    dl, 1
0x14001c194  jnz     short loc_14001C1CF
0x14001c196  mov     rax, [rbx+0E8h]
0x14001c19d  mov     edx, [rax+1Ch]
0x14001c1a0  cmp     edx, 10h
0x14001c1a3  ja      short loc_14001C1CF
0x14001c1a5  mov     eax, 10642h
0x14001c1aa  bt      eax, edx
0x14001c1ad  jnb     short loc_14001C1CF
0x14001c1af  mov     rcx, rbp; unsigned int *
0x14001c1b2  call    ?ScReadNoFence@@YAKPEAK@Z; ScReadNoFence(ulong *)
0x14001c1b7  bt      eax, 0Ah
0x14001c1bb  jnb     short loc_14001C1C6
0x14001c1bd  cmp     byte ptr [rdi+0A8h], 0
0x14001c1c4  jnz     short loc_14001C1CF
0x14001c1c6  mov     [rsp+88h+var_54+4], 3
0x14001c1cf  xor     edx, edx; Wait
0x14001c1d1  lea     rcx, [rdi+10h]; Mutex
0x14001c1d5  call    cs:__imp_KeReleaseMutex
0x14001c1dc  nop     dword ptr [rax+rax+00h]
0x14001c1e1  mov     byte ptr [rsp+88h+var_54], 1
0x14001c1e6  mov     r8d, 1
0x14001c1ec  lea     rdx, [rsp+88h+var_58]
0x14001c1f1  mov     rcx, rbx
0x14001c1f4  call    ?PmSetDiskAttributes@@YAJPEAU_DEVICE_EXTENSION@@PEAU_SET_DISK_ATTRIBUTES@@W4_DISK_OFFLINE_REASON@@@Z; PmSetDiskAttributes(_DEVICE_EXTENSION *,_SET_DISK_ATTRIBUTES *,_DISK_OFFLINE_REASON)
0x14001c1f9  add     rsp, 68h
0x14001c1fd  pop     rdi
0x14001c1fe  pop     rsi
0x14001c1ff  pop     rbp
0x14001c200  pop     rbx
0x14001c201  retn
```
