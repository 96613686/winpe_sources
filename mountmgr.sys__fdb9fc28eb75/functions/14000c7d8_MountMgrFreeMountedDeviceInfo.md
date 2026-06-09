# MountMgrFreeMountedDeviceInfo

- ea: `0x14000c7d8`
- end: `0x14000c94b`
- name: `MountMgrFreeMountedDeviceInfo`
- size: `371`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x140001bec`
- `0x14000d7a0`

## callees

- `0x14000c7d8`
- `0x140018cd0`

## import_xrefs

- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x14000c924`
- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x14000c924`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c825`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c836`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c86c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c87d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c8b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c8c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c8df`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c8fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c90c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c935`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c825`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c836`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c86c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c87d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c8b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c8c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c8df`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c8fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c90c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c935`

## pseudocode

```c
void __fastcall MountMgrFreeMountedDeviceInfo(PVOID *P, char a2)
{
  void **v3; // rsi
  void *v5; // rdi
  void **v6; // rax
  void **v7; // rsi
  void *v8; // rdi
  void **v9; // rax
  void **v10; // rsi
  void *v11; // rdi
  void **v12; // rax
  PVOID v13; // rcx

  v3 = P + 2;
  while ( 1 )
  {
    v5 = *v3;
    if ( *v3 == v3 )
      break;
    if ( *((void ***)v5 + 1) != v3 || (v6 = *(void ***)v5, *(void **)(*(_QWORD *)v5 + 8LL) != v5) )
LABEL_18:
      __fastfail(3u);
    *v3 = v6;
    v6[1] = v3;
    if ( !a2 )
      GlobalDeleteSymbolicLink((__int64)v5 + 24);
    ExFreePoolWithTag(*((PVOID *)v5 + 4), 0);
    ExFreePoolWithTag(v5, 0);
  }
  v7 = P + 4;
  while ( 1 )
  {
    v8 = *v7;
    if ( *v7 == v7 )
      break;
    if ( *((void ***)v8 + 1) != v7 )
      goto LABEL_18;
    v9 = *(void ***)v8;
    if ( *(void **)(*(_QWORD *)v8 + 8LL) != v8 )
      goto LABEL_18;
    *v7 = v9;
    v9[1] = v7;
    ExFreePoolWithTag(*((PVOID *)v8 + 2), 0);
    ExFreePoolWithTag(v8, 0);
  }
  v10 = P + 6;
  while ( 1 )
  {
    v11 = *v10;
    if ( *v10 == v10 )
      break;
    if ( *((void ***)v11 + 1) != v10 )
      goto LABEL_18;
    v12 = *(void ***)v11;
    if ( *(void **)(*(_QWORD *)v11 + 8LL) != v11 )
      goto LABEL_18;
    *v10 = v12;
    v12[1] = v10;
    ExFreePoolWithTag(*((PVOID *)v11 + 4), 0);
    ExFreePoolWithTag(v11, 0);
  }
  ExFreePoolWithTag(P[9], 0);
  if ( !*((_BYTE *)P + 130) )
    ExFreePoolWithTag(P[12], 0);
  ExFreePoolWithTag(P[11], 0);
  v13 = P[18];
  if ( v13 )
    IoUnregisterPlugPlayNotification(v13);
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x14000c7d8  push    rbx
0x14000c7da  push    rbp
0x14000c7db  push    rsi
0x14000c7dc  push    rdi
0x14000c7dd  sub     rsp, 28h
0x14000c7e1  mov     bpl, dl
0x14000c7e4  lea     rsi, [rcx+10h]
0x14000c7e8  mov     rbx, rcx
0x14000c7eb  mov     rdi, [rsi]
0x14000c7ee  cmp     rdi, rsi
0x14000c7f1  jz      short loc_14000C844
0x14000c7f3  cmp     [rdi+8], rsi
0x14000c7f7  jnz     loc_14000C8D2
0x14000c7fd  mov     rax, [rdi]
0x14000c800  cmp     [rax+8], rdi
0x14000c804  jnz     loc_14000C8D2
0x14000c80a  mov     [rsi], rax
0x14000c80d  mov     [rax+8], rsi
0x14000c811  test    bpl, bpl
0x14000c814  jnz     short loc_14000C81F
0x14000c816  lea     rcx, [rdi+18h]
0x14000c81a  call    GlobalDeleteSymbolicLink
0x14000c81f  mov     rcx, [rdi+20h]; P
0x14000c823  xor     edx, edx; Tag
0x14000c825  call    cs:__imp_ExFreePoolWithTag
0x14000c82c  nop     dword ptr [rax+rax+00h]
0x14000c831  xor     edx, edx; Tag
0x14000c833  mov     rcx, rdi; P
0x14000c836  call    cs:__imp_ExFreePoolWithTag
0x14000c83d  nop     dword ptr [rax+rax+00h]
0x14000c842  jmp     short loc_14000C7EB
0x14000c844  lea     rsi, [rbx+20h]
0x14000c848  mov     rdi, [rsi]
0x14000c84b  cmp     rdi, rsi
0x14000c84e  jz      short loc_14000C88B
0x14000c850  cmp     [rdi+8], rsi
0x14000c854  jnz     short loc_14000C8D2
0x14000c856  mov     rax, [rdi]
0x14000c859  cmp     [rax+8], rdi
0x14000c85d  jnz     short loc_14000C8D2
0x14000c85f  mov     [rsi], rax
0x14000c862  xor     edx, edx; Tag
0x14000c864  mov     [rax+8], rsi
0x14000c868  mov     rcx, [rdi+10h]; P
0x14000c86c  call    cs:__imp_ExFreePoolWithTag
0x14000c873  nop     dword ptr [rax+rax+00h]
0x14000c878  xor     edx, edx; Tag
0x14000c87a  mov     rcx, rdi; P
0x14000c87d  call    cs:__imp_ExFreePoolWithTag
0x14000c884  nop     dword ptr [rax+rax+00h]
0x14000c889  jmp     short loc_14000C848
0x14000c88b  lea     rsi, [rbx+30h]
0x14000c88f  mov     rdi, [rsi]
0x14000c892  cmp     rdi, rsi
0x14000c895  jz      short loc_14000C8D9
0x14000c897  cmp     [rdi+8], rsi
0x14000c89b  jnz     short loc_14000C8D2
0x14000c89d  mov     rax, [rdi]
0x14000c8a0  cmp     [rax+8], rdi
0x14000c8a4  jnz     short loc_14000C8D2
0x14000c8a6  mov     [rsi], rax
0x14000c8a9  xor     edx, edx; Tag
0x14000c8ab  mov     [rax+8], rsi
0x14000c8af  mov     rcx, [rdi+20h]; P
0x14000c8b3  call    cs:__imp_ExFreePoolWithTag
0x14000c8ba  nop     dword ptr [rax+rax+00h]
0x14000c8bf  xor     edx, edx; Tag
0x14000c8c1  mov     rcx, rdi; P
0x14000c8c4  call    cs:__imp_ExFreePoolWithTag
0x14000c8cb  nop     dword ptr [rax+rax+00h]
0x14000c8d0  jmp     short loc_14000C88F
0x14000c8d2  mov     ecx, 3
0x14000c8d7  int     29h; Win8: RtlFailFast(ecx)
0x14000c8d9  mov     rcx, [rbx+48h]; P
0x14000c8dd  xor     edx, edx; Tag
0x14000c8df  call    cs:__imp_ExFreePoolWithTag
0x14000c8e6  nop     dword ptr [rax+rax+00h]
0x14000c8eb  cmp     byte ptr [rbx+82h], 0
0x14000c8f2  jnz     short loc_14000C906
0x14000c8f4  mov     rcx, [rbx+60h]; P
0x14000c8f8  xor     edx, edx; Tag
0x14000c8fa  call    cs:__imp_ExFreePoolWithTag
0x14000c901  nop     dword ptr [rax+rax+00h]
0x14000c906  mov     rcx, [rbx+58h]; P
0x14000c90a  xor     edx, edx; Tag
0x14000c90c  call    cs:__imp_ExFreePoolWithTag
0x14000c913  nop     dword ptr [rax+rax+00h]
0x14000c918  mov     rcx, [rbx+90h]; NotificationEntry
0x14000c91f  test    rcx, rcx
0x14000c922  jz      short loc_14000C930
0x14000c924  call    cs:__imp_IoUnregisterPlugPlayNotification
0x14000c92b  nop     dword ptr [rax+rax+00h]
0x14000c930  xor     edx, edx; Tag
0x14000c932  mov     rcx, rbx; P
0x14000c935  call    cs:__imp_ExFreePoolWithTag
0x14000c93c  nop     dword ptr [rax+rax+00h]
0x14000c941  add     rsp, 28h
0x14000c945  pop     rdi
0x14000c946  pop     rsi
0x14000c947  pop     rbp
0x14000c948  pop     rbx
0x14000c949  retn
```
