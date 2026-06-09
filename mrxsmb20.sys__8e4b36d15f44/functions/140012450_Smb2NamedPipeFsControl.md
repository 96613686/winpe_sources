# Smb2NamedPipeFsControl

- ea: `0x140012450`
- end: `0x1400126b0`
- name: `Smb2NamedPipeFsControl`
- size: `608`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x14001cc00`

## callees

- `0x140012450`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x140012559`
- `ntoskrnl!ProbeForWrite` at `0x140012559`
- `ntoskrnl!ProbeForRead` at `0x140012536`
- `ntoskrnl!ProbeForRead` at `0x140012536`
- `mrxsmb!SmbCeInitiateExchange` at `0x140012649`
- `mrxsmb!SmbCeInitiateExchange` at `0x140012649`
- `mrxsmb!SmbCeInitializeExchange` at `0x1400125de`
- `mrxsmb!SmbCeInitializeExchange` at `0x1400125de`

## pseudocode

```c
__int64 __fastcall Smb2NamedPipeFsControl(__int64 a1, int a2)
{
  int v4; // ebx
  __int64 v5; // r12
  unsigned int v6; // esi
  _DWORD *v7; // r13
  unsigned int v8; // ecx
  volatile void *v10; // rcx
  SIZE_T v11; // rdx
  unsigned int v12; // ecx
  __int64 v13; // [rsp+48h] [rbp-60h] BYREF
  volatile void *Address; // [rsp+50h] [rbp-58h]
  _DWORD *v15; // [rsp+58h] [rbp-50h]
  volatile void *v16; // [rsp+60h] [rbp-48h]
  __int64 v17; // [rsp+68h] [rbp-40h]
  unsigned int Length; // [rsp+C0h] [rbp+18h]

  v4 = 0;
  v13 = 0;
  v5 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 72) + 40LL) + 40LL);
  v17 = v5;
  if ( a2 == 1114136 )
  {
    v6 = *(_DWORD *)(a1 + 568);
    if ( v6 < 0xE )
      return (unsigned int)-1073741811;
    v7 = *(_DWORD **)(a1 + 552);
    v8 = v7[2];
    if ( v6 < v8 + 14 || v6 < v8 )
      return (unsigned int)-1073741811;
  }
  else
  {
    v7 = 0;
    v6 = 0;
    if ( a2 == 1163287 )
    {
      v7 = *(_DWORD **)(a1 + 552);
      v15 = v7;
      v6 = *(_DWORD *)(a1 + 568);
      v10 = *(volatile void **)(a1 + 560);
      Address = v10;
      v16 = v10;
      v11 = *(unsigned int *)(a1 + 572);
      Length = *(_DWORD *)(a1 + 572);
      if ( *(_BYTE *)(*(_QWORD *)(a1 + 40) + 64LL) )
      {
        if ( v7 )
        {
          ProbeForRead(v7, v6, 1u);
          v10 = Address;
          v11 = Length;
        }
        if ( v10 )
          ProbeForWrite(v10, v11, 1u);
      }
      goto LABEL_14;
    }
    if ( a2 == 1130508 )
    {
      Address = *(volatile void **)(a1 + 560);
      v12 = *(_DWORD *)(a1 + 572);
      Length = v12;
      if ( Address && v12 < 0x10 )
        return (unsigned int)-1073741789;
      goto LABEL_14;
    }
    v4 = -1073741822;
  }
  Length = 0;
  Address = 0;
LABEL_14:
  if ( v4 >= 0 )
  {
    v13 = 0;
    v4 = SmbCeInitializeExchange(&v13, a1, 0, 0, 0, v5, 2616, &FsctlDispatch);
    if ( !v4 )
    {
      _InterlockedOr((volatile signed __int32 *)(v13 + 68), 0x40u);
      *(_DWORD *)(v13 + 2408) = a2;
      *(_QWORD *)(v13 + 2416) = v7;
      *(_DWORD *)(v13 + 2424) = v6;
      *(_QWORD *)(v13 + 2432) = Address;
      *(_DWORD *)(v13 + 2440) = Length;
      return (unsigned int)SmbCeInitiateExchange(v13);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140012450  mov     [rsp+arg_8], edx
0x140012454  mov     [rsp+arg_0], rcx
0x140012459  push    rbx
0x14001245a  push    rsi
0x14001245b  push    rdi
0x14001245c  push    r12
0x14001245e  push    r13
0x140012460  push    r14
0x140012462  push    r15
0x140012464  sub     rsp, 70h
0x140012468  mov     r15d, edx
0x14001246b  mov     rdi, rcx
0x14001246e  xor     r14d, r14d
0x140012471  mov     ebx, r14d
0x140012474  mov     [rsp+0A8h+var_60], r14
0x140012479  mov     rax, [rcx+48h]
0x14001247d  mov     r8, [rax+28h]
0x140012481  mov     r12, [r8+28h]
0x140012485  mov     [rsp+0A8h+var_40], r12
0x14001248a  cmp     edx, 110018h
0x140012490  jnz     short loc_1400124D0
0x140012492  mov     esi, [rcx+238h]
0x140012498  cmp     esi, 0Eh
0x14001249b  jb      short loc_1400124AF
0x14001249d  mov     r13, [rcx+228h]
0x1400124a4  mov     ecx, [r13+8]
0x1400124a8  lea     eax, [rcx+0Eh]
0x1400124ab  cmp     esi, eax
0x1400124ad  jnb     short loc_1400124C7
0x1400124af  mov     ebx, 0C000000Dh
0x1400124b4  mov     eax, ebx
0x1400124b6  add     rsp, 70h
0x1400124ba  pop     r15
0x1400124bc  pop     r14
0x1400124be  pop     r13
0x1400124c0  pop     r12
0x1400124c2  pop     rdi
0x1400124c3  pop     rsi
0x1400124c4  pop     rbx
0x1400124c5  retn
0x1400124c7  cmp     esi, ecx
0x1400124c9  jb      short loc_1400124AF
0x1400124cb  jmp     loc_140012669
0x1400124d0  mov     r13, r14
0x1400124d3  mov     esi, r14d
0x1400124d6  cmp     edx, 11C017h
0x1400124dc  jnz     loc_14001265C
0x1400124e2  mov     r13, [rcx+228h]
0x1400124e9  mov     [rsp+0A8h+var_50], r13
0x1400124ee  mov     esi, [rcx+238h]
0x1400124f4  mov     [rsp+0A8h+arg_18], esi
0x1400124fb  mov     rcx, [rcx+230h]
0x140012502  mov     [rsp+0A8h+Address], rcx
0x140012507  mov     [rsp+0A8h+var_48], rcx
0x14001250c  mov     edx, [rdi+23Ch]
0x140012512  mov     dword ptr [rsp+0A8h+Length], edx
0x140012519  mov     [rsp+0A8h+var_68], edx
0x14001251d  mov     rax, [rdi+28h]
0x140012521  cmp     [rax+40h], bl
0x140012524  jz      short loc_1400125A5
0x140012526  test    r13, r13
0x140012529  jz      short loc_14001254E
0x14001252b  mov     edx, esi; Length
0x14001252d  mov     r8d, 1; Alignment
0x140012533  mov     rcx, r13; Address
0x140012536  call    cs:__imp_ProbeForRead
0x14001253d  nop     dword ptr [rax+rax+00h]
0x140012542  mov     rcx, [rsp+0A8h+Address]; Address
0x140012547  mov     edx, dword ptr [rsp+0A8h+Length]; Length
0x14001254e  test    rcx, rcx
0x140012551  jz      short loc_140012565
0x140012553  mov     r8d, 1; Alignment
0x140012559  call    cs:__imp_ProbeForWrite
0x140012560  nop     dword ptr [rax+rax+00h]
0x140012565  jmp     short loc_1400125A5
0x140012567  mov     ebx, 0C000000Dh
0x14001256c  xor     r14d, r14d
0x14001256f  mov     r15d, [rsp+0A8h+arg_8]
0x140012577  mov     rdi, [rsp+0A8h+arg_0]
0x14001257f  mov     r13, [rsp+0A8h+var_50]
0x140012584  mov     rax, [rsp+0A8h+var_48]
0x140012589  mov     [rsp+0A8h+Address], rax
0x14001258e  mov     esi, [rsp+0A8h+arg_18]
0x140012595  mov     eax, [rsp+0A8h+var_68]
0x140012599  mov     dword ptr [rsp+0A8h+Length], eax
0x1400125a0  mov     r12, [rsp+0A8h+var_40]
0x1400125a5  test    ebx, ebx
0x1400125a7  js      loc_1400124B4
0x1400125ad  mov     [rsp+0A8h+var_60], r14
0x1400125b2  lea     rax, FsctlDispatch
0x1400125b9  mov     [rsp+0A8h+var_70], rax
0x1400125be  mov     [rsp+0A8h+var_78], 0A38h
0x1400125c6  mov     [rsp+0A8h+var_80], r12
0x1400125cb  mov     [rsp+0A8h+var_88], r14
0x1400125d0  xor     r9d, r9d
0x1400125d3  xor     r8d, r8d
0x1400125d6  mov     rdx, rdi
0x1400125d9  lea     rcx, [rsp+0A8h+var_60]
0x1400125de  call    cs:__imp_SmbCeInitializeExchange
0x1400125e5  nop     dword ptr [rax+rax+00h]
0x1400125ea  mov     ebx, eax
0x1400125ec  test    eax, eax
0x1400125ee  jnz     loc_1400124B4
0x1400125f4  mov     rax, [rsp+0A8h+var_60]
0x1400125f9  lock or dword ptr [rax+44h], 40h
0x1400125fe  mov     rax, [rsp+0A8h+var_60]
0x140012603  mov     [rax+968h], r15d
0x14001260a  mov     rax, [rsp+0A8h+var_60]
0x14001260f  mov     [rax+970h], r13
0x140012616  mov     rax, [rsp+0A8h+var_60]
0x14001261b  mov     [rax+978h], esi
0x140012621  mov     rax, [rsp+0A8h+var_60]
0x140012626  mov     rcx, [rsp+0A8h+Address]
0x14001262b  mov     [rax+980h], rcx
0x140012632  mov     rax, [rsp+0A8h+var_60]
0x140012637  mov     ecx, dword ptr [rsp+0A8h+Length]
0x14001263e  mov     [rax+988h], ecx
0x140012644  mov     rcx, [rsp+0A8h+var_60]
0x140012649  call    cs:__imp_SmbCeInitiateExchange
0x140012650  nop     dword ptr [rax+rax+00h]
0x140012655  mov     ebx, eax
0x140012657  jmp     loc_1400124B4
0x14001265c  cmp     edx, 11400Ch
0x140012662  jz      short loc_14001267B
0x140012664  mov     ebx, 0C0000002h
0x140012669  mov     dword ptr [rsp+0A8h+Length], r14d
0x140012671  mov     [rsp+0A8h+Address], r14
0x140012676  jmp     loc_1400125A5
0x14001267b  mov     rax, [rcx+230h]
0x140012682  mov     [rsp+0A8h+Address], rax
0x140012687  mov     ecx, [rcx+23Ch]
0x14001268d  mov     dword ptr [rsp+0A8h+Length], ecx
0x140012694  test    rax, rax
0x140012697  jz      loc_1400125A5
0x14001269d  cmp     ecx, 10h
0x1400126a0  jnb     loc_1400125A5
0x1400126a6  mov     ebx, 0C0000023h
0x1400126ab  jmp     loc_1400124B4
```
