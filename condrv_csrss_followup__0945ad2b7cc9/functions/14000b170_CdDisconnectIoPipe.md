# CdDisconnectIoPipe

- ea: `0x14000b170`
- end: `0x14000b38b`
- name: `CdDisconnectIoPipe`
- size: `539`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000b020`
- `0x14000c330`
- `0x14000c870`

## callees

- `0x14000b170`
- `0x14000c3d0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b1a2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b1a2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b230`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b230`
- `ntoskrnl!IofCompleteRequest` at `0x14000b291`
- `ntoskrnl!IofCompleteRequest` at `0x14000b291`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000b192`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000b192`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000b1ca`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000b1ca`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000b21f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000b21f`

## pseudocode

```c
__int64 **__fastcall CdDisconnectIoPipe(_QWORD *a1)
{
  char v2; // r15
  __int64 v3; // rcx
  unsigned int i; // edi
  __int64 ****v5; // rbx
  __int64 ***v6; // rsi
  __int64 ****v7; // rbx
  __int64 ***v8; // rdi
  __int64 *v9; // rcx
  __int64 **result; // rax
  __int64 *v11; // rax
  IRP *v12; // rcx
  _QWORD *v13; // rax
  _QWORD *v14; // rax
  __int64 **v15; // rcx
  __int64 ***v16; // rax
  __int64 *v17; // [rsp+20h] [rbp-28h] BYREF
  __int64 **v18; // [rsp+28h] [rbp-20h]

  v18 = &v17;
  v2 = 0;
  v17 = (__int64 *)&v17;
  if ( KeGetCurrentIrql() <= 1u )
  {
    KeEnterCriticalRegion();
    v2 = 1;
  }
  ExAcquirePushLockExclusiveEx(*a1, 0);
  v3 = a1[2];
  *((_BYTE *)a1 + 8) = 0;
  if ( v3 && _InterlockedExchange64((volatile __int64 *)(v3 + 104), 0) )
  {
    v15 = v18;
    if ( *v18 != (__int64 *)&v17 )
LABEL_26:
      __fastfail(3u);
    v16 = (__int64 ***)(a1[2] + 168LL);
    *v16 = &v17;
    v16[1] = v15;
    *v15 = (__int64 *)v16;
    v18 = (__int64 **)v16;
    a1[2] = 0;
  }
  for ( i = 0; i < 5; ++i )
  {
    v5 = (__int64 ****)&a1[2 * i + 5];
    while ( 1 )
    {
      v6 = *v5;
      if ( *v5 == (__int64 ***)v5 )
        break;
      if ( (unsigned __int8)CdpPrepareIoCompletion(v6 - 21, 0) )
      {
        v13 = v18;
        if ( *v18 != (__int64 *)&v17 )
          goto LABEL_26;
        v6[1] = v18;
        *v6 = &v17;
        *v13 = v6;
        v18 = (__int64 **)v6;
      }
    }
  }
  v7 = (__int64 ****)(a1 + 3);
  while ( 1 )
  {
    v8 = *v7;
    if ( *v7 == (__int64 ***)v7 )
      break;
    if ( (unsigned __int8)CdpPrepareIoCompletion(v8 - 21, 0) )
    {
      v14 = v18;
      if ( *v18 != (__int64 *)&v17 )
        goto LABEL_26;
      v8[1] = v18;
      *v8 = &v17;
      *v14 = v8;
      v18 = (__int64 **)v8;
    }
  }
  ExReleasePushLockExclusiveEx(*a1, 0);
  if ( v2 )
    KeLeaveCriticalRegion();
  while ( 1 )
  {
    v9 = v17;
    result = &v17;
    if ( v17 == (__int64 *)&v17 )
      return result;
    if ( (__int64 **)v17[1] != &v17 )
      goto LABEL_26;
    v11 = (__int64 *)*v17;
    if ( *(__int64 **)(*v17 + 8) != v17 )
      goto LABEL_26;
    v17 = (__int64 *)*v17;
    v11[1] = (__int64)&v17;
    v12 = (IRP *)(v9 - 21);
    v12->IoStatus.Status = -1073741648;
    v12->IoStatus.Information = 0;
    IofCompleteRequest(v12, 0);
  }
}

```

## disassembly

```asm
0x14000b170  push    r14
0x14000b172  push    r15
0x14000b174  sub     rsp, 38h
0x14000b178  lea     rax, [rsp+48h+var_28]
0x14000b17d  mov     r14, rcx
0x14000b180  mov     [rsp+48h+var_20], rax
0x14000b185  xor     r15b, r15b
0x14000b188  lea     rax, [rsp+48h+var_28]
0x14000b18d  mov     [rsp+48h+var_28], rax
0x14000b192  call    cs:__imp_KeGetCurrentIrql
0x14000b199  nop     dword ptr [rax+rax+00h]
0x14000b19e  cmp     al, 1
0x14000b1a0  ja      short loc_14000B1B1
0x14000b1a2  call    cs:__imp_KeEnterCriticalRegion
0x14000b1a9  nop     dword ptr [rax+rax+00h]
0x14000b1ae  mov     r15b, 1
0x14000b1b1  mov     rcx, [r14]
0x14000b1b4  xor     edx, edx
0x14000b1b6  mov     [rsp+48h+arg_0], rbx
0x14000b1bb  mov     [rsp+48h+arg_8], rbp
0x14000b1c0  mov     [rsp+48h+arg_10], rsi
0x14000b1c5  mov     [rsp+48h+var_18], rdi
0x14000b1ca  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000b1d1  nop     dword ptr [rax+rax+00h]
0x14000b1d6  mov     rcx, [r14+10h]
0x14000b1da  mov     byte ptr [r14+8], 0
0x14000b1df  test    rcx, rcx
0x14000b1e2  jnz     loc_14000B33B
0x14000b1e8  xor     edi, edi
0x14000b1ea  lea     rbp, [r14+28h]
0x14000b1ee  mov     ebx, edi
0x14000b1f0  shl     rbx, 4
0x14000b1f4  add     rbx, rbp
0x14000b1f7  mov     rsi, [rbx]
0x14000b1fa  cmp     rsi, rbx
0x14000b1fd  jnz     loc_14000B29F
0x14000b203  inc     edi
0x14000b205  cmp     edi, 5
0x14000b208  jb      short loc_14000B1EE
0x14000b20a  lea     rbx, [r14+18h]
0x14000b20e  mov     rdi, [rbx]
0x14000b211  xor     edx, edx
0x14000b213  cmp     rdi, rbx
0x14000b216  jnz     loc_14000B2FF
0x14000b21c  mov     rcx, [r14]
0x14000b21f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000b226  nop     dword ptr [rax+rax+00h]
0x14000b22b  test    r15b, r15b
0x14000b22e  jz      short loc_14000B23C
0x14000b230  call    cs:__imp_KeLeaveCriticalRegion
0x14000b237  nop     dword ptr [rax+rax+00h]
0x14000b23c  mov     rcx, [rsp+48h+var_28]
0x14000b241  lea     rax, [rsp+48h+var_28]
0x14000b246  cmp     rcx, rax
0x14000b249  jz      loc_14000B2E1
0x14000b24f  lea     rax, [rsp+48h+var_28]
0x14000b254  cmp     [rcx+8], rax
0x14000b258  jnz     loc_14000B384
0x14000b25e  mov     rax, [rcx]
0x14000b261  cmp     [rax+8], rcx
0x14000b265  jnz     loc_14000B384
0x14000b26b  mov     [rsp+48h+var_28], rax
0x14000b270  lea     rdx, [rsp+48h+var_28]
0x14000b275  mov     [rax+8], rdx
0x14000b279  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x14000b280  xor     edx, edx; PriorityBoost
0x14000b282  mov     dword ptr [rcx+30h], 0C00000B0h
0x14000b289  mov     qword ptr [rcx+38h], 0
0x14000b291  call    cs:__imp_IofCompleteRequest
0x14000b298  nop     dword ptr [rax+rax+00h]
0x14000b29d  jmp     short loc_14000B23C
0x14000b29f  lea     rcx, [rsi-0A8h]
0x14000b2a6  xor     edx, edx
0x14000b2a8  call    CdpPrepareIoCompletion
0x14000b2ad  test    al, al
0x14000b2af  jz      loc_14000B1F7
0x14000b2b5  mov     rax, [rsp+48h+var_20]
0x14000b2ba  lea     rcx, [rsp+48h+var_28]
0x14000b2bf  cmp     [rax], rcx
0x14000b2c2  jnz     loc_14000B384
0x14000b2c8  mov     [rsi+8], rax
0x14000b2cc  lea     rcx, [rsp+48h+var_28]
0x14000b2d1  mov     [rsi], rcx
0x14000b2d4  mov     [rax], rsi
0x14000b2d7  mov     [rsp+48h+var_20], rsi
0x14000b2dc  jmp     loc_14000B1F7
0x14000b2e1  mov     rdi, [rsp+48h+var_18]
0x14000b2e6  mov     rsi, [rsp+48h+arg_10]
0x14000b2eb  mov     rbp, [rsp+48h+arg_8]
0x14000b2f0  mov     rbx, [rsp+48h+arg_0]
0x14000b2f5  add     rsp, 38h
0x14000b2f9  pop     r15
0x14000b2fb  pop     r14
0x14000b2fd  retn
0x14000b2ff  lea     rcx, [rdi-0A8h]
0x14000b306  call    CdpPrepareIoCompletion
0x14000b30b  test    al, al
0x14000b30d  jz      loc_14000B20E
0x14000b313  mov     rax, [rsp+48h+var_20]
0x14000b318  lea     rcx, [rsp+48h+var_28]
0x14000b31d  cmp     [rax], rcx
0x14000b320  jnz     short loc_14000B384
0x14000b322  mov     [rdi+8], rax
0x14000b326  lea     rcx, [rsp+48h+var_28]
0x14000b32b  mov     [rdi], rcx
0x14000b32e  mov     [rax], rdi
0x14000b331  mov     [rsp+48h+var_20], rdi
0x14000b336  jmp     loc_14000B20E
0x14000b33b  xor     eax, eax
0x14000b33d  xchg    rax, [rcx+68h]
0x14000b341  test    rax, rax
0x14000b344  jz      loc_14000B1E8
0x14000b34a  mov     rcx, [rsp+48h+var_20]
0x14000b34f  lea     rax, [rsp+48h+var_28]
0x14000b354  cmp     [rcx], rax
0x14000b357  jnz     short loc_14000B384
0x14000b359  mov     rax, [r14+10h]
0x14000b35d  lea     rdx, [rsp+48h+var_28]
0x14000b362  add     rax, 0A8h
0x14000b368  mov     [rax], rdx
0x14000b36b  mov     [rax+8], rcx
0x14000b36f  mov     [rcx], rax
0x14000b372  mov     [rsp+48h+var_20], rax
0x14000b377  mov     qword ptr [r14+10h], 0
0x14000b37f  jmp     loc_14000B1E8
0x14000b384  mov     ecx, 3
0x14000b389  int     29h; Win8: RtlFailFast(ecx)
```
