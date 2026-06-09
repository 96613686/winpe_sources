# CClfsRequest::ReadArchiveMetadata(void)

- ea: `0x1400419cc`
- end: `0x140041b4a`
- name: `?ReadArchiveMetadata@CClfsRequest@@AEAAJXZ`
- size: `382`
- prototype: `__int64 __fastcall(CClfsRequest *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14006c874`

## callees

- `0x14000c2f0`
- `0x1400419cc`
- `0x140047388`
- `0x140059e80`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140041b07`
- `ntoskrnl!KeSetEvent` at `0x14007ec5f`
- `ntoskrnl!KeSetEvent` at `0x140041b07`
- `ntoskrnl!KeSetEvent` at `0x14007ec5f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140041ab1`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140041ab1`

## pseudocode

```c
__int64 __fastcall CClfsRequest::ReadArchiveMetadata(CClfsRequest *this)
{
  CClfsLogCcb *v2; // rdi
  char *v3; // r14
  __int64 v4; // rax
  __int64 v5; // rcx
  unsigned int v6; // ebx
  unsigned int v7; // r15d
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rcx
  unsigned __int8 *v11; // rax
  struct _KEVENT *v12; // rcx
  unsigned int v14; // [rsp+88h] [rbp+10h] BYREF
  char *v15; // [rsp+90h] [rbp+18h]

  v2 = 0;
  v14 = 0;
  v3 = (char *)this + 48;
  v15 = (char *)this + 48;
  v4 = *((_QWORD *)this + 6);
  v5 = *(_QWORD *)(v4 + 184);
  if ( *(_DWORD *)(v5 + 16) >= 4u )
  {
    v7 = **(_DWORD **)(v4 + 24);
    v8 = *(_DWORD *)(v5 + 8);
    if ( v8 )
    {
      v2 = *(CClfsLogCcb **)(*(_QWORD *)(v5 + 48) + 32LL);
      CClfsLogCcb::AddRef(v2);
      v10 = *(_QWORD *)(*(_QWORD *)v9 + 8LL);
      if ( (*(_BYTE *)(v10 + 10) & 5) != 0 )
        v11 = *(unsigned __int8 **)(v10 + 24);
      else
        v11 = (unsigned __int8 *)MmMapLockedPagesSpecifyCache((PMDL)v10, 0, MmCached, 0, 0, 0x40000010u);
      if ( v11 )
        v6 = CClfsLogCcb::ReadArchiveMetadata(v2, v7, v8, v11, &v14);
      else
        v6 = -1073741670;
    }
    else
    {
      v6 = -1073741789;
    }
  }
  else
  {
    v6 = -1073741306;
  }
  if ( (*((_BYTE *)this + 16) & 1) != 0 )
  {
    v12 = *(struct _KEVENT **)(*(_QWORD *)v3 + 80LL);
    if ( v12 )
      KeSetEvent(v12, 0, 0);
  }
  if ( (*((_DWORD *)this + 4) & 4) == 0 )
  {
    *(_DWORD *)(*(_QWORD *)v3 + 48LL) = v6;
    *(_QWORD *)(*(_QWORD *)v3 + 56LL) = v14;
  }
  if ( v2 )
    CClfsLogCcb::Release(v2);
  return v6;
}

```

## disassembly

```asm
0x1400419cc  mov     rax, rsp
0x1400419cf  mov     [rax+8], rcx
0x1400419d3  push    rbx
0x1400419d4  push    rsi
0x1400419d5  push    rdi
0x1400419d6  push    r14
0x1400419d8  push    r15
0x1400419da  sub     rsp, 50h
0x1400419de  mov     rsi, rcx
0x1400419e1  xor     ebx, ebx
0x1400419e3  mov     [rax-48h], ebx
0x1400419e6  xor     edi, edi
0x1400419e8  mov     [rax-40h], rdi
0x1400419ec  mov     [rax+10h], ebx
0x1400419ef  mov     [rax-44h], ebx
0x1400419f2  lea     rdx, [rcx+30h]
0x1400419f6  mov     r14, rdx
0x1400419f9  mov     [rsp+78h+arg_10], rdx
0x140041a01  mov     rax, [rdx]
0x140041a04  mov     rcx, [rax+0B8h]
0x140041a0b  mov     [rsp+78h+var_38], rcx
0x140041a10  cmp     dword ptr [rcx+10h], 4
0x140041a14  jnb     short loc_140041A24
0x140041a16  mov     ebx, 0C0000206h
0x140041a1b  mov     [rsp+78h+var_48], ebx
0x140041a1f  jmp     loc_140041AF0
0x140041a24  mov     rax, [rax+18h]
0x140041a28  mov     r15d, [rax]
0x140041a2b  mov     [rsp+78h+var_44], r15d
0x140041a30  jmp     short loc_140041A5A
0x140041a32  mov     ebx, eax
0x140041a34  mov     [rsp+78h+var_48], eax
0x140041a38  mov     rsi, [rsp+78h+arg_0]
0x140041a40  mov     rdi, [rsp+78h+var_40]
0x140041a45  mov     r15d, [rsp+78h+var_44]
0x140041a4a  mov     r14, [rsp+78h+arg_10]
0x140041a52  mov     rdx, r14
0x140041a55  mov     rcx, [rsp+78h+var_38]
0x140041a5a  test    ebx, ebx
0x140041a5c  jnz     loc_140041AF0
0x140041a62  mov     ebx, [rcx+8]
0x140041a65  test    ebx, ebx
0x140041a67  jnz     short loc_140041A70
0x140041a69  mov     ebx, 0C0000023h
0x140041a6e  jmp     short loc_140041A1B
0x140041a70  mov     rax, [rcx+30h]
0x140041a74  mov     rdi, [rax+20h]
0x140041a78  mov     [rsp+78h+var_40], rdi
0x140041a7d  mov     rcx, rdi; this
0x140041a80  call    ?AddRef@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::AddRef(void)
0x140041a85  mov     rcx, [rdx]
0x140041a88  mov     rcx, [rcx+8]; MemoryDescriptorList
0x140041a8c  test    byte ptr [rcx+0Ah], 5
0x140041a90  jz      short loc_140041A98
0x140041a92  mov     rax, [rcx+18h]
0x140041a96  jmp     short loc_140041ABD
0x140041a98  mov     [rsp+78h+Priority], 40000010h; Priority
0x140041aa0  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140041aa8  xor     r9d, r9d; RequestedAddress
0x140041aab  xor     edx, edx; AccessMode
0x140041aad  lea     r8d, [r9+1]; CacheType
0x140041ab1  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140041ab8  nop     dword ptr [rax+rax+00h]
0x140041abd  test    rax, rax
0x140041ac0  jnz     short loc_140041ACC
0x140041ac2  mov     ebx, 0C000009Ah
0x140041ac7  jmp     loc_140041A1B
0x140041acc  lea     rcx, [rsp+78h+arg_8]
0x140041ad4  mov     qword ptr [rsp+78h+BugCheckOnFailure], rcx; unsigned int *
0x140041ad9  mov     r9, rax; unsigned __int8 *
0x140041adc  mov     r8d, ebx; unsigned int
0x140041adf  mov     edx, r15d; unsigned int
0x140041ae2  mov     rcx, rdi; this
0x140041ae5  call    ?ReadArchiveMetadata@CClfsLogCcb@@QEAAJKKPEAEAEAK@Z; CClfsLogCcb::ReadArchiveMetadata(ulong,ulong,uchar *,ulong &)
0x140041aea  mov     ebx, eax
0x140041aec  mov     [rsp+78h+var_48], eax
0x140041af0  test    byte ptr [rsi+10h], 1
0x140041af4  jz      short loc_140041B13
0x140041af6  mov     rax, [r14]
0x140041af9  mov     rcx, [rax+50h]; Event
0x140041afd  test    rcx, rcx
0x140041b00  jz      short loc_140041B13
0x140041b02  xor     r8d, r8d; Wait
0x140041b05  xor     edx, edx; Increment
0x140041b07  call    cs:__imp_KeSetEvent
0x140041b0e  nop     dword ptr [rax+rax+00h]
0x140041b13  mov     eax, [rsi+10h]
0x140041b16  test    al, 4
0x140041b18  jnz     short loc_140041B2E
0x140041b1a  mov     rax, [r14]
0x140041b1d  mov     [rax+30h], ebx
0x140041b20  mov     edx, [rsp+78h+arg_8]
0x140041b27  mov     rax, [r14]
0x140041b2a  mov     [rax+38h], rdx
0x140041b2e  test    rdi, rdi
0x140041b31  jz      short loc_140041B3B
0x140041b33  mov     rcx, rdi; Entry
0x140041b36  call    ?Release@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::Release(void)
0x140041b3b  mov     eax, ebx
0x140041b3d  add     rsp, 50h
0x140041b41  pop     r15
0x140041b43  pop     r14
0x140041b45  pop     rdi
0x140041b46  pop     rsi
0x140041b47  pop     rbx
0x140041b48  retn
0x14007ec25  push    rbx
0x14007ec27  push    rbp
0x14007ec28  sub     rsp, 38h
0x14007ec2c  mov     rbp, rdx
0x14007ec2f  xor     cl, cl
0x14007ec31  mov     rbx, [rbp+80h]
0x14007ec38  test    byte ptr [rbx+10h], 1
0x14007ec3c  movzx   eax, cl
0x14007ec3f  mov     ecx, 1
0x14007ec44  cmovnz  eax, ecx
0x14007ec47  test    al, al
0x14007ec49  jz      short loc_14007EC6C
0x14007ec4b  mov     rax, [rbx+30h]
0x14007ec4f  cmp     qword ptr [rax+50h], 0
0x14007ec54  jz      short loc_14007EC6C
0x14007ec56  xor     r8d, r8d; Wait
0x14007ec59  xor     edx, edx; Increment
0x14007ec5b  mov     rcx, [rax+50h]; Event
0x14007ec5f  call    cs:__imp_KeSetEvent
0x14007ec66  nop     dword ptr [rax+rax+00h]
0x14007ec6b  nop
0x14007ec6c  xor     cl, cl
0x14007ec6e  test    byte ptr [rbx+10h], 4
0x14007ec72  movzx   eax, cl
0x14007ec75  mov     ecx, 1
0x14007ec7a  cmovnz  eax, ecx
0x14007ec7d  test    al, al
0x14007ec7f  jnz     short loc_14007EC99
0x14007ec81  mov     rcx, [rbx+30h]
0x14007ec85  mov     eax, [rbp+30h]
0x14007ec88  mov     [rcx+30h], eax
0x14007ec8b  mov     ecx, [rbp+88h]
0x14007ec91  mov     rax, [rbx+30h]
0x14007ec95  mov     [rax+38h], rcx
0x14007ec99  mov     rcx, [rbp+38h]; Entry
0x14007ec9d  test    rcx, rcx
0x14007eca0  jz      short loc_14007ECAF
0x14007eca2  call    ?Release@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::Release(void)
0x14007eca7  mov     qword ptr [rbp+38h], 0
0x14007ecaf  add     rsp, 38h
0x14007ecb3  pop     rbp
0x14007ecb4  pop     rbx
0x14007ecb5  retn
```
