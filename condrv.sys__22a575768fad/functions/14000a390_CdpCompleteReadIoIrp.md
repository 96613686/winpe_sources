# CdpCompleteReadIoIrp

- ea: `0x14000a390`
- end: `0x14000a5ce`
- name: `CdpCompleteReadIoIrp`
- size: `574`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400095c0`

## callees

- `0x14000a390`
- `0x14000aa00`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000a558`
- `ntoskrnl!IofCompleteRequest` at `0x14000a5b9`
- `ntoskrnl!IofCompleteRequest` at `0x14000a558`
- `ntoskrnl!IofCompleteRequest` at `0x14000a5b9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000a3d7`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000a3d7`

## pseudocode

```c
__int64 __fastcall CdpCompleteReadIoIrp(__int64 a1, IRP *a2, char a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  PMDL MdlAddress; // rcx
  _OWORD *MappedSystemVa; // rdx
  __int64 Length; // r9
  int v10; // ecx
  _QWORD *v11; // rbx
  __int64 v12; // r8
  __int64 *i; // rax
  __int64 *v14; // rax
  unsigned int j; // ecx
  __int128 v16; // xmm1
  __int64 v17; // r8
  __int64 v18; // xmm0_8
  int v19; // ebp
  __int64 v20; // rax
  _QWORD *v21; // rcx
  __int64 *v22; // rcx
  __int64 v23; // rax
  char *v25; // [rsp+30h] [rbp-68h] BYREF
  int v26; // [rsp+38h] [rbp-60h]
  int v27; // [rsp+3Ch] [rbp-5Ch]
  __int128 v28; // [rsp+40h] [rbp-58h]
  __int128 v29; // [rsp+50h] [rbp-48h]
  __int64 v30; // [rsp+60h] [rbp-38h]
  __int64 v31; // [rsp+A8h] [rbp+10h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  MdlAddress = a2->MdlAddress;
  if ( (MdlAddress->MdlFlags & 5) != 0 )
    MappedSystemVa = MdlAddress->MappedSystemVa;
  else
    MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u);
  if ( MappedSystemVa )
  {
    Length = CurrentStackLocation->Parameters.Read.Length;
    v10 = 0;
    v11 = *(_QWORD **)(a1 + 24);
    HIDWORD(v30) = 0;
    v12 = v11[2];
    *(_QWORD *)&v28 = *(v11 - 4);
    *((_QWORD *)&v28 + 1) = *(v11 - 6);
    *(_QWORD *)&v29 = *(_QWORD *)(v12 + 16);
    DWORD2(v29) = *(unsigned __int8 *)(v12 + 1);
    for ( i = *(__int64 **)(v12 + 32); i; i = (__int64 *)*i )
      v10 += *((_DWORD *)i + 10);
    v14 = *(__int64 **)(v12 + 24);
    LODWORD(v30) = v10;
    for ( j = 0; v14; v14 = (__int64 *)*v14 )
      j += *((_DWORD *)v14 + 10);
    HIDWORD(v29) = j;
    v16 = v29;
    v17 = j;
    *MappedSystemVa = v28;
    v18 = v30;
    MappedSystemVa[1] = v16;
    *((_QWORD *)MappedSystemVa + 4) = v18;
    if ( j >= (unsigned __int64)(Length - 40) )
    {
      v17 = Length - 40;
      v31 = Length - 40;
    }
    else
    {
      v31 = j;
    }
    if ( !v17 )
      goto LABEL_13;
    v26 = v17;
    v25 = (char *)MappedSystemVa + 40;
    v27 = 0;
    v19 = CdpReadIoInput(v11 - 21, 0, &v25, &v31);
    if ( v19 >= 0 )
    {
      v17 = v31;
LABEL_13:
      v20 = *v11;
      if ( *(_QWORD **)(*v11 + 8LL) != v11
        || (v21 = (_QWORD *)v11[1], (_QWORD *)*v21 != v11)
        || (*v21 = v20,
            *(_QWORD *)(v20 + 8) = v21,
            v22 = (__int64 *)(a1 + 16LL * (*((_DWORD *)v11 - 8) % 5u) + 40),
            v23 = *v22,
            *(__int64 **)(*v22 + 8) != v22) )
      {
        __fastfail(3u);
      }
      *v11 = v23;
      v11[1] = v22;
      *(_QWORD *)(v23 + 8) = v11;
      *v22 = (__int64)v11;
      a2->IoStatus.Information = v17 + 40;
      a2->IoStatus.Status = 0;
      IofCompleteRequest(a2, 0);
      return 0;
    }
  }
  else
  {
    v19 = -1073741670;
  }
  if ( a3 )
  {
    a2->IoStatus.Status = v19;
    a2->IoStatus.Information = 0;
    IofCompleteRequest(a2, 0);
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x14000a390  push    rbx
0x14000a392  push    rdi
0x14000a393  push    r12
0x14000a395  push    r14
0x14000a397  push    r15
0x14000a399  sub     rsp, 70h
0x14000a39d  mov     rbx, [rdx+0B8h]
0x14000a3a4  mov     r14, rcx
0x14000a3a7  mov     rcx, [rdx+8]; MemoryDescriptorList
0x14000a3ab  xor     r12d, r12d
0x14000a3ae  movzx   r15d, r8b
0x14000a3b2  mov     rdi, rdx
0x14000a3b5  test    byte ptr [rcx+0Ah], 5
0x14000a3b9  jnz     loc_14000A584
0x14000a3bf  mov     [rsp+98h+Priority], 40000010h; Priority
0x14000a3c7  xor     r9d, r9d; RequestedAddress
0x14000a3ca  xor     edx, edx; AccessMode
0x14000a3cc  mov     [rsp+98h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x14000a3d1  mov     r8d, 1; CacheType
0x14000a3d7  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000a3de  nop     dword ptr [rax+rax+00h]
0x14000a3e3  mov     rdx, rax
0x14000a3e6  mov     [rsp+98h+arg_0], rbp
0x14000a3ee  mov     [rsp+98h+arg_10], rsi
0x14000a3f6  test    rdx, rdx
0x14000a3f9  jz      loc_14000A5A6
0x14000a3ff  mov     r9d, [rbx+8]
0x14000a403  mov     ecx, r12d
0x14000a406  mov     rbx, [r14+18h]
0x14000a40a  mov     dword ptr [rsp+98h+var_38+4], r12d
0x14000a40f  mov     r8, [rbx+10h]
0x14000a413  mov     rax, [rbx-20h]
0x14000a417  mov     qword ptr [rsp+98h+var_58], rax
0x14000a41c  mov     rax, [rbx-30h]
0x14000a420  mov     qword ptr [rsp+98h+var_58+8], rax
0x14000a425  mov     rax, [r8+10h]
0x14000a429  mov     qword ptr [rsp+98h+var_48], rax
0x14000a42e  movzx   eax, byte ptr [r8+1]
0x14000a433  mov     dword ptr [rsp+98h+var_48+8], eax
0x14000a437  mov     rax, [r8+20h]
0x14000a43b  test    rax, rax
0x14000a43e  jz      short loc_14000A44B
0x14000a440  add     ecx, [rax+28h]
0x14000a443  mov     rax, [rax]
0x14000a446  test    rax, rax
0x14000a449  jnz     short loc_14000A440
0x14000a44b  mov     rax, [r8+18h]
0x14000a44f  mov     dword ptr [rsp+98h+var_38], ecx
0x14000a453  mov     ecx, r12d
0x14000a456  test    rax, rax
0x14000a459  jz      short loc_14000A466
0x14000a45b  add     ecx, [rax+28h]
0x14000a45e  mov     rax, [rax]
0x14000a461  test    rax, rax
0x14000a464  jnz     short loc_14000A45B
0x14000a466  movups  xmm0, [rsp+98h+var_58]
0x14000a46b  mov     dword ptr [rsp+98h+var_48+0Ch], ecx
0x14000a46f  lea     rax, [r9-28h]
0x14000a473  movups  xmm1, [rsp+98h+var_48]
0x14000a478  mov     r8d, ecx
0x14000a47b  movups  xmmword ptr [rdx], xmm0
0x14000a47e  movsd   xmm0, [rsp+98h+var_38]
0x14000a484  movups  xmmword ptr [rdx+10h], xmm1
0x14000a488  movsd   qword ptr [rdx+20h], xmm0
0x14000a48d  cmp     r8, rax
0x14000a490  jnb     loc_14000A58D
0x14000a496  mov     [rsp+98h+arg_8], r8
0x14000a49e  test    r8, r8
0x14000a4a1  jz      short loc_14000A4E3
0x14000a4a3  lea     rax, [rdx+28h]
0x14000a4a7  mov     [rsp+98h+var_60], r8d
0x14000a4ac  lea     r8, [rsp+98h+var_68]
0x14000a4b1  mov     [rsp+98h+var_68], rax
0x14000a4b6  xor     edx, edx
0x14000a4b8  mov     [rsp+98h+var_5C], r12d
0x14000a4bd  lea     r9, [rsp+98h+arg_8]
0x14000a4c5  lea     rcx, [rbx-0A8h]
0x14000a4cc  call    CdpReadIoInput
0x14000a4d1  mov     ebp, eax
0x14000a4d3  test    eax, eax
0x14000a4d5  js      loc_14000A59D
0x14000a4db  mov     r8, [rsp+98h+arg_8]
0x14000a4e3  mov     rax, [rbx]
0x14000a4e6  cmp     [rax+8], rbx
0x14000a4ea  jnz     loc_14000A5C7
0x14000a4f0  mov     rcx, [rbx+8]
0x14000a4f4  cmp     [rcx], rbx
0x14000a4f7  jnz     loc_14000A5C7
0x14000a4fd  mov     [rcx], rax
0x14000a500  mov     [rax+8], rcx
0x14000a504  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000a50e  mov     ecx, [rbx-20h]
0x14000a511  mul     rcx
0x14000a514  shr     rdx, 2
0x14000a518  lea     rax, [rdx+rdx*4]
0x14000a51c  sub     rcx, rax
0x14000a51f  mov     ecx, ecx
0x14000a521  shl     rcx, 4
0x14000a525  add     rcx, 28h ; '('
0x14000a529  add     rcx, r14
0x14000a52c  mov     rax, [rcx]
0x14000a52f  cmp     [rax+8], rcx
0x14000a533  jnz     loc_14000A5C7
0x14000a539  mov     [rbx], rax
0x14000a53c  xor     edx, edx; PriorityBoost
0x14000a53e  mov     [rbx+8], rcx
0x14000a542  mov     [rax+8], rbx
0x14000a546  lea     rax, [r8+28h]
0x14000a54a  mov     [rcx], rbx
0x14000a54d  mov     rcx, rdi; Irp
0x14000a550  mov     [rdi+38h], rax
0x14000a554  mov     [rdi+30h], r12d
0x14000a558  call    cs:__imp_IofCompleteRequest
0x14000a55f  nop     dword ptr [rax+rax+00h]
0x14000a564  xor     eax, eax
0x14000a566  mov     rsi, [rsp+98h+arg_10]
0x14000a56e  mov     rbp, [rsp+98h+arg_0]
0x14000a576  add     rsp, 70h
0x14000a57a  pop     r15
0x14000a57c  pop     r14
0x14000a57e  pop     r12
0x14000a580  pop     rdi
0x14000a581  pop     rbx
0x14000a582  retn
0x14000a584  mov     rdx, [rcx+18h]
0x14000a588  jmp     loc_14000A3E6
0x14000a58d  mov     r8, rax
0x14000a590  mov     [rsp+98h+arg_8], rax
0x14000a598  jmp     loc_14000A49E
0x14000a59d  test    r15b, r15b
0x14000a5a0  jnz     short loc_14000A5AD
0x14000a5a2  mov     eax, ebp
0x14000a5a4  jmp     short loc_14000A566
0x14000a5a6  mov     ebp, 0C000009Ah
0x14000a5ab  jmp     short loc_14000A59D
0x14000a5ad  xor     edx, edx; PriorityBoost
0x14000a5af  mov     [rdi+30h], ebp
0x14000a5b2  mov     rcx, rdi; Irp
0x14000a5b5  mov     [rdi+38h], r12
0x14000a5b9  call    cs:__imp_IofCompleteRequest
0x14000a5c0  nop     dword ptr [rax+rax+00h]
0x14000a5c5  jmp     short loc_14000A5A2
0x14000a5c7  mov     ecx, 3
0x14000a5cc  int     29h; Win8: RtlFailFast(ecx)
```
