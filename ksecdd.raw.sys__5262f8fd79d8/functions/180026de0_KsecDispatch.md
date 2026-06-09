# KsecDispatch

- ea: `0x180026de0`
- end: `0x180026fb0`
- name: `KsecDispatch`
- size: `464`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007bd8`
- `0x18000b79c`
- `0x180026de0`
- `0x180026fb8`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x180026ea8`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x180026ea8`
- `ntoskrnl!IofCompleteRequest` at `0x180026ee6`
- `ntoskrnl!IofCompleteRequest` at `0x180026ee6`

## pseudocode

```c
__int64 __fastcall KsecDispatch(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  int v4; // ebx
  _DWORD *v5; // r8
  unsigned int v6; // ebx
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rax
  int v11; // [rsp+68h] [rbp+10h] BYREF

  v2 = *(_QWORD *)(a2 + 184);
  switch ( *(_BYTE *)v2 )
  {
    case 0:
    case 2:
      *(_QWORD *)(a2 + 56) = 0;
LABEL_19:
      v6 = 0;
      goto LABEL_20;
    case 3:
      v6 = -1073741807;
      *(_QWORD *)(a2 + 56) = 0;
      goto LABEL_20;
    case 4:
      *(_QWORD *)(a2 + 56) = *(unsigned int *)(v2 + 8);
      goto LABEL_19;
    case 5:
      if ( *(_DWORD *)(v2 + 16) == 5 )
      {
        v10 = *(_QWORD *)(a2 + 24);
        *(_DWORD *)(v10 + 16) = 1;
        *(_WORD *)(v10 + 20) = 0;
        *(_QWORD *)v10 = 0;
        *(_QWORD *)(v10 + 8) = 0;
        v9 = 24;
        goto LABEL_34;
      }
LABEL_22:
      v9 = *(unsigned int *)(v2 + 8);
      v6 = -1073741821;
LABEL_23:
      *(_QWORD *)(a2 + 56) = v9;
      goto LABEL_20;
    case 0xA:
      if ( *(_DWORD *)(v2 + 16) == 4 )
      {
        **(_DWORD **)(a2 + 24) = 57;
        v9 = 8;
LABEL_34:
        v6 = 0;
        goto LABEL_23;
      }
      goto LABEL_22;
  }
  if ( *(_BYTE *)v2 != 14 )
  {
    if ( *(_BYTE *)v2 != 16 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 3), 30, &WPP_47798432cc4f3443573e38da5669f213_Traceguids);
      v6 = -1073741811;
      goto LABEL_20;
    }
    KsecShutdown();
    *(_QWORD *)(a2 + 56) = 0;
    goto LABEL_19;
  }
  v4 = *(_DWORD *)(v2 + 24);
  if ( (v4 & 3) == 2 && *(_DWORD *)(v2 + 8) )
  {
    v8 = *(_QWORD *)(a2 + 8);
    if ( (*(_BYTE *)(v8 + 10) & 5) != 0 )
      v5 = *(_DWORD **)(v8 + 24);
    else
      v5 = MmMapLockedPagesSpecifyCache((PMDL)v8, 0, MmCached, 0, 0, 0x40000010u);
    v11 = *(_DWORD *)(*(_QWORD *)(a2 + 8) + 40LL);
    if ( !v5 )
    {
      v6 = -1073741670;
      *(_QWORD *)(a2 + 56) = 0;
LABEL_20:
      *(_DWORD *)(a2 + 48) = v6;
      IofCompleteRequest((PIRP)a2, 0);
      return v6;
    }
  }
  else
  {
    v5 = *(_DWORD **)(a2 + 24);
    v11 = *(_DWORD *)(v2 + 8);
  }
  v6 = KsecDeviceControl(*(unsigned int **)(a2 + 24), *(_DWORD *)(v2 + 16), v5, &v11, v4, (PIRP)a2);
  if ( v6 != 259 )
  {
    *(_QWORD *)(a2 + 56) = (unsigned int)v11;
    goto LABEL_20;
  }
  return v6;
}

```

## disassembly

```asm
0x180026de0  push    rbx
0x180026de2  push    rbp
0x180026de3  push    rsi
0x180026de4  push    rdi
0x180026de5  sub     rsp, 38h
0x180026de9  mov     rsi, [rdx+0B8h]
0x180026df0  xor     ebp, ebp
0x180026df2  mov     rdi, rdx
0x180026df5  movzx   r9d, byte ptr [rsi]
0x180026df9  mov     ecx, r9d
0x180026dfc  test    r9d, r9d
0x180026dff  jz      loc_180026ED8
0x180026e05  sub     ecx, 2
0x180026e08  jz      loc_180026ED8
0x180026e0e  sub     ecx, 1
0x180026e11  jz      loc_180026FA2
0x180026e17  sub     ecx, 1
0x180026e1a  jz      loc_180026F96
0x180026e20  sub     ecx, 1
0x180026e23  jz      loc_180026EF4
0x180026e29  sub     ecx, 5
0x180026e2c  jz      loc_180026F5D
0x180026e32  sub     ecx, 4
0x180026e35  jnz     loc_180026F0D
0x180026e3b  mov     ebx, [rsi+18h]
0x180026e3e  mov     eax, ebx
0x180026e40  and     al, 3
0x180026e42  cmp     al, 2
0x180026e44  jz      short loc_180026E84
0x180026e46  mov     eax, [rsi+8]
0x180026e49  mov     r8, [rdx+18h]; int
0x180026e4d  mov     [rsp+58h+arg_8], eax
0x180026e51  mov     edx, [rsi+10h]; int
0x180026e54  lea     r9, [rsp+58h+arg_8]; int
0x180026e59  mov     rcx, [rdi+18h]; int
0x180026e5d  mov     qword ptr [rsp+58h+Priority], rdi; Irp
0x180026e62  mov     [rsp+58h+BugCheckOnFailure], ebx; int
0x180026e66  call    KsecDeviceControl
0x180026e6b  mov     ebx, eax
0x180026e6d  cmp     eax, 103h
0x180026e72  jnz     loc_180026F53
0x180026e78  mov     eax, ebx
0x180026e7a  add     rsp, 38h
0x180026e7e  pop     rdi
0x180026e7f  pop     rsi
0x180026e80  pop     rbp
0x180026e81  pop     rbx
0x180026e82  retn
0x180026e84  cmp     [rsi+8], ebp
0x180026e87  jz      short loc_180026E46
0x180026e89  mov     rcx, [rdx+8]; MemoryDescriptorList
0x180026e8d  test    byte ptr [rcx+0Ah], 5
0x180026e91  jnz     short loc_180026ED2
0x180026e93  xor     r9d, r9d; RequestedAddress
0x180026e96  mov     [rsp+58h+Priority], 40000010h; Priority
0x180026e9e  xor     edx, edx; AccessMode
0x180026ea0  mov     [rsp+58h+BugCheckOnFailure], ebp; BugCheckOnFailure
0x180026ea4  lea     r8d, [r9+1]; CacheType
0x180026ea8  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x180026eaf  nop     dword ptr [rax+rax+00h]
0x180026eb4  mov     r8, rax
0x180026eb7  mov     rax, [rdi+8]
0x180026ebb  mov     ecx, [rax+28h]
0x180026ebe  mov     [rsp+58h+arg_8], ecx
0x180026ec2  test    r8, r8
0x180026ec5  jnz     short loc_180026E51
0x180026ec7  mov     ebx, 0C000009Ah
0x180026ecc  mov     [rdi+38h], rbp
0x180026ed0  jmp     short loc_180026EDE
0x180026ed2  mov     r8, [rcx+18h]
0x180026ed6  jmp     short loc_180026EB7
0x180026ed8  mov     [rdx+38h], rbp
0x180026edc  mov     ebx, ebp
0x180026ede  xor     edx, edx; PriorityBoost
0x180026ee0  mov     [rdi+30h], ebx
0x180026ee3  mov     rcx, rdi; Irp
0x180026ee6  call    cs:__imp_IofCompleteRequest
0x180026eed  nop     dword ptr [rax+rax+00h]
0x180026ef2  jmp     short loc_180026E78
0x180026ef4  cmp     dword ptr [rsi+10h], 5
0x180026ef8  jz      short loc_180026F74
0x180026efa  mov     eax, [rsi+8]
0x180026efd  mov     ebx, 0C0000003h
0x180026f02  mov     ecx, 38h ; '8'
0x180026f07  mov     [rdx+rcx], rax
0x180026f0b  jmp     short loc_180026EDE
0x180026f0d  cmp     ecx, 2
0x180026f10  jz      short loc_180026F48
0x180026f12  mov     rcx, cs:WPP_GLOBAL_Control
0x180026f19  lea     rax, WPP_GLOBAL_Control
0x180026f20  cmp     rcx, rax
0x180026f23  jz      short loc_180026F41
0x180026f25  mov     eax, [rcx+2Ch]
0x180026f28  test    al, 1
0x180026f2a  jz      short loc_180026F41
0x180026f2c  mov     rcx, [rcx+18h]
0x180026f30  lea     r8, WPP_47798432cc4f3443573e38da5669f213_Traceguids
0x180026f37  mov     edx, 1Eh
0x180026f3c  call    WPP_SF_D
0x180026f41  mov     ebx, 0C000000Dh
0x180026f46  jmp     short loc_180026EDE
0x180026f48  call    KsecShutdown
0x180026f4d  mov     [rdi+38h], rbp
0x180026f51  jmp     short loc_180026EDC
0x180026f53  mov     ecx, [rsp+58h+arg_8]
0x180026f57  mov     [rdi+38h], rcx
0x180026f5b  jmp     short loc_180026EDE
0x180026f5d  cmp     dword ptr [rsi+10h], 4
0x180026f61  jnz     short loc_180026EFA
0x180026f63  mov     rax, [rdx+18h]
0x180026f67  mov     dword ptr [rax], 39h ; '9'
0x180026f6d  mov     eax, 8
0x180026f72  jmp     short loc_180026F8F
0x180026f74  mov     rax, [rdx+18h]
0x180026f78  mov     dword ptr [rax+10h], 1
0x180026f7f  mov     [rax+14h], bp
0x180026f83  mov     [rax], rbp
0x180026f86  mov     [rax+8], rbp
0x180026f8a  mov     eax, 18h
0x180026f8f  mov     ebx, ebp
0x180026f91  jmp     loc_180026F02
0x180026f96  mov     eax, [rsi+8]
0x180026f99  mov     [rdx+38h], rax
0x180026f9d  jmp     loc_180026EDC
0x180026fa2  mov     ebx, 0C0000011h
0x180026fa7  mov     [rdx+38h], rbp
0x180026fab  jmp     loc_180026EDE
```
