# MountMgrNotify

- ea: `0x1400019c0`
- end: `0x140001ad0`
- name: `MountMgrNotify`
- size: `272`
- prototype: `__int64 **__fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000be4c`
- `0x14000db54`
- `0x140018560`

## callees

- `0x1400019c0`

## import_xrefs

- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400019ed`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400019ed`
- `ntoskrnl!IofCompleteRequest` at `0x140001ab4`
- `ntoskrnl!IofCompleteRequest` at `0x140001ab4`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140001a5a`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140001a5a`

## pseudocode

```c
__int64 **__fastcall MountMgrNotify(__int64 a1)
{
  __int64 ****v2; // rax
  __int64 ***v3; // rdx
  __int64 **v4; // rcx
  _QWORD *v5; // r8
  __int64 *v6; // rcx
  __int64 **result; // rax
  __int64 *v8; // rax
  __int64 *v9; // rcx
  __int64 *v10; // [rsp+20h] [rbp-18h] BYREF
  __int64 **v11; // [rsp+28h] [rbp-10h]
  KIRQL Irql; // [rsp+40h] [rbp+8h] BYREF

  ++*(_DWORD *)(a1 + 168);
  v11 = &v10;
  Irql = 0;
  v10 = (__int64 *)&v10;
  IoAcquireCancelSpinLock(&Irql);
  v2 = (__int64 ****)(a1 + 152);
  while ( 1 )
  {
    v3 = *v2;
    if ( *v2 == (__int64 ***)v2 )
      break;
    if ( v3[1] != (__int64 **)v2
      || (v4 = *v3, (*v3)[1] != (__int64 *)v3)
      || (*v2 = (__int64 ***)v4,
          v4[1] = (__int64 *)v2,
          _InterlockedExchange64((volatile __int64 *)v3 - 8, 0),
          v5 = v11,
          *v11 != (__int64 *)&v10) )
    {
LABEL_12:
      __fastfail(3u);
    }
    v3[1] = v11;
    *v3 = &v10;
    *v5 = v3;
    v11 = (__int64 **)v3;
  }
  IoReleaseCancelSpinLock(Irql);
  while ( 1 )
  {
    v6 = v10;
    result = &v10;
    if ( v10 == (__int64 *)&v10 )
      return result;
    if ( (__int64 **)v10[1] != &v10 )
      goto LABEL_12;
    v8 = (__int64 *)*v10;
    if ( *(__int64 **)(*v10 + 8) != v10 )
      goto LABEL_12;
    v10 = (__int64 *)*v10;
    v8[1] = (__int64)&v10;
    v9 = v6 - 21;
    *(_DWORD *)v9[3] = *(_DWORD *)(a1 + 168);
    v9[7] = 4;
    IofCompleteRequest((PIRP)v9, 0);
  }
}

```

## disassembly

```asm
0x1400019c0  push    rbx
0x1400019c2  sub     rsp, 30h
0x1400019c6  inc     dword ptr [rcx+0A8h]
0x1400019cc  lea     rax, [rsp+38h+var_18]
0x1400019d1  mov     [rsp+38h+var_10], rax
0x1400019d6  mov     rbx, rcx
0x1400019d9  lea     rax, [rsp+38h+var_18]
0x1400019de  mov     [rsp+38h+Irql], 0
0x1400019e3  lea     rcx, [rsp+38h+Irql]; Irql
0x1400019e8  mov     [rsp+38h+var_18], rax
0x1400019ed  call    cs:__imp_IoAcquireCancelSpinLock
0x1400019f4  nop     dword ptr [rax+rax+00h]
0x1400019f9  lea     rax, [rbx+98h]
0x140001a00  mov     rdx, [rax]
0x140001a03  cmp     rdx, rax
0x140001a06  jz      short loc_140001A55
0x140001a08  cmp     [rdx+8], rax
0x140001a0c  jnz     loc_140001AC2
0x140001a12  mov     rcx, [rdx]
0x140001a15  cmp     [rcx+8], rdx
0x140001a19  jnz     loc_140001AC2
0x140001a1f  mov     [rax], rcx
0x140001a22  mov     [rcx+8], rax
0x140001a26  xor     ecx, ecx
0x140001a28  xchg    rcx, [rdx-40h]
0x140001a2c  mov     r8, [rsp+38h+var_10]
0x140001a31  lea     rcx, [rsp+38h+var_18]
0x140001a36  cmp     [r8], rcx
0x140001a39  jnz     loc_140001AC2
0x140001a3f  mov     [rdx+8], r8
0x140001a43  lea     rcx, [rsp+38h+var_18]
0x140001a48  mov     [rdx], rcx
0x140001a4b  mov     [r8], rdx
0x140001a4e  mov     [rsp+38h+var_10], rdx
0x140001a53  jmp     short loc_140001A00
0x140001a55  movzx   ecx, [rsp+38h+Irql]; Irql
0x140001a5a  call    cs:__imp_IoReleaseCancelSpinLock
0x140001a61  nop     dword ptr [rax+rax+00h]
0x140001a66  mov     rcx, [rsp+38h+var_18]
0x140001a6b  lea     rax, [rsp+38h+var_18]
0x140001a70  cmp     rcx, rax
0x140001a73  jz      short loc_140001AC9
0x140001a75  lea     rax, [rsp+38h+var_18]
0x140001a7a  cmp     [rcx+8], rax
0x140001a7e  jnz     short loc_140001AC2
0x140001a80  mov     rax, [rcx]
0x140001a83  cmp     [rax+8], rcx
0x140001a87  jnz     short loc_140001AC2
0x140001a89  mov     [rsp+38h+var_18], rax
0x140001a8e  lea     rdx, [rsp+38h+var_18]
0x140001a93  mov     [rax+8], rdx
0x140001a97  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x140001a9e  mov     eax, [rbx+0A8h]
0x140001aa4  mov     rdx, [rcx+18h]
0x140001aa8  mov     [rdx], eax
0x140001aaa  xor     edx, edx; PriorityBoost
0x140001aac  mov     qword ptr [rcx+38h], 4
0x140001ab4  call    cs:__imp_IofCompleteRequest
0x140001abb  nop     dword ptr [rax+rax+00h]
0x140001ac0  jmp     short loc_140001A66
0x140001ac2  mov     ecx, 3
0x140001ac7  int     29h; Win8: RtlFailFast(ecx)
0x140001ac9  add     rsp, 30h
0x140001acd  pop     rbx
0x140001ace  retn
```
