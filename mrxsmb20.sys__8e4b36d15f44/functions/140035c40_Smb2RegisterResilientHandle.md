# Smb2RegisterResilientHandle

- ea: `0x140035c40`
- end: `0x140035e4c`
- name: `Smb2RegisterResilientHandle`
- size: `524`
- prototype: `__int64 __fastcall(__int64, ULONG_PTR)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140005820`
- `0x140024b10`

## callees

- `0x140029840`
- `0x14002a1dc`
- `0x140035c40`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140035cac`
- `ntoskrnl!ExAllocatePool2` at `0x140035cac`
- `ntoskrnl!ExReleaseResourceLite` at `0x140035e2b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140035e2b`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140035cc4`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140035cc4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140035c6a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140035c6a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140035d32`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140035d32`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140035c80`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140035c80`
- `mrxsmb!SmbCeSetConnectionKeepalive` at `0x140035ddf`
- `mrxsmb!SmbCeSetConnectionKeepalive` at `0x140035ddf`
- `mrxsmb!MRxSmbActivateRecurrentService` at `0x140035da7`
- `mrxsmb!MRxSmbActivateRecurrentService` at `0x140035da7`

## pseudocode

```c
__int64 __fastcall Smb2RegisterResilientHandle(__int64 a1, ULONG_PTR a2)
{
  __int64 v2; // rdi
  unsigned int v4; // r12d
  char v5; // r14
  __int64 v6; // rsi
  unsigned int v7; // r15d
  struct _EX_RUNDOWN_REF *Pool2; // rax
  struct _EX_RUNDOWN_REF *v9; // rbx
  struct _EX_RUNDOWN_REF **v10; // r8
  __int64 v11; // rsi
  __int64 v12; // r14

  v2 = *(_QWORD *)(a1 + 2336);
  v4 = 0;
  v5 = 0;
  ExAcquireResourceExclusiveLite((PERESOURCE)v2, 1u);
  v6 = *(_QWORD *)(a2 + 48);
  ExAcquirePushLockExclusiveEx(v6 + 16, 0);
  v7 = 10;
  if ( (*(_DWORD *)(v6 + 8) & 0x40) != 0 )
  {
    v9 = 0;
  }
  else
  {
    Pool2 = (struct _EX_RUNDOWN_REF *)ExAllocatePool2(256, 40, 1834182982);
    v9 = Pool2;
    if ( Pool2 )
    {
      ExInitializeRundownProtection(Pool2 + 3);
      *(_DWORD *)(v6 + 8) |= 0x44u;
      v5 = 1;
      v9[2].Count = a2;
      *(_QWORD *)(v6 + 296) = v9;
    }
    else
    {
      v4 = -1073741670;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          10,
          WPP_826bdefea5f439a79d7b4a7e09ca5b98_Traceguids,
          a2,
          -1073741670);
      }
    }
  }
  ExReleasePushLockExclusiveEx(v6 + 16, 0);
  if ( v5 )
  {
    v10 = *(struct _EX_RUNDOWN_REF ***)(v2 + 112);
    if ( *v10 != (struct _EX_RUNDOWN_REF *)(v2 + 104) )
      __fastfail(3u);
    v11 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 40) + 40LL) + 416LL);
    v12 = *(_QWORD *)(v11 + 384);
    v9->Count = v2 + 104;
    v9[1].Count = (ULONG_PTR)v10;
    *v10 = v9;
    *(_QWORD *)(v2 + 112) = v9;
    LODWORD(v9[4].Count) = *(_DWORD *)(v2 + 132);
    if ( ++*(_DWORD *)(v2 + 120) == 1 )
      MRxSmbActivateRecurrentService(a1, v2 + 136);
    if ( _InterlockedIncrement((volatile signed __int32 *)(v11 + 704)) == 1 )
    {
      if ( *(_DWORD *)(v12 + 772) )
        v7 = *(_DWORD *)(v12 + 772);
      SmbCeSetConnectionKeepalive(v11, v7, 2);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_826bdefea5f439a79d7b4a7e09ca5b98_Traceguids, a2, v9);
    }
  }
  ExReleaseResourceLite((PERESOURCE)v2);
  return v4;
}

```

## disassembly

```asm
0x140035c40  mov     [rsp+arg_0], rcx
0x140035c45  push    rbx
0x140035c46  push    rbp
0x140035c47  push    rsi
0x140035c48  push    rdi
0x140035c49  push    r12
0x140035c4b  push    r13
0x140035c4d  push    r14
0x140035c4f  push    r15
0x140035c51  sub     rsp, 38h
0x140035c55  mov     rdi, [rcx+920h]
0x140035c5c  mov     rbp, rdx
0x140035c5f  mov     rcx, rdi; Resource
0x140035c62  mov     dl, 1; Wait
0x140035c64  xor     r12d, r12d
0x140035c67  xor     r14b, r14b
0x140035c6a  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140035c71  nop     dword ptr [rax+rax+00h]
0x140035c76  mov     rsi, [rbp+30h]
0x140035c7a  xor     edx, edx
0x140035c7c  lea     rcx, [rsi+10h]
0x140035c80  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140035c87  nop     dword ptr [rax+rax+00h]
0x140035c8c  mov     eax, [rsi+8]
0x140035c8f  lea     r15d, [r12+0Ah]
0x140035c94  test    al, 40h
0x140035c96  jnz     loc_140035D2A
0x140035c9c  lea     edx, [r12+28h]
0x140035ca1  mov     ecx, 100h
0x140035ca6  mov     r8d, 6D536946h
0x140035cac  call    cs:__imp_ExAllocatePool2
0x140035cb3  nop     dword ptr [rax+rax+00h]
0x140035cb8  mov     rbx, rax
0x140035cbb  test    rax, rax
0x140035cbe  jz      short loc_140035CE4
0x140035cc0  lea     rcx, [rax+18h]; RunRef
0x140035cc4  call    cs:__imp_ExInitializeRundownProtection
0x140035ccb  nop     dword ptr [rax+rax+00h]
0x140035cd0  or      dword ptr [rsi+8], 44h
0x140035cd4  mov     r14b, 1
0x140035cd7  mov     [rbx+10h], rbp
0x140035cdb  mov     [rsi+128h], rbx
0x140035ce2  jmp     short loc_140035D2C
0x140035ce4  mov     r12d, 0C000009Ah
0x140035cea  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140035cf1  lea     rax, WPP_GLOBAL_Control
0x140035cf8  cmp     rcx, rax
0x140035cfb  jz      short loc_140035D2C
0x140035cfd  mov     eax, [rcx+2Ch]
0x140035d00  test    al, 1
0x140035d02  jz      short loc_140035D2C
0x140035d04  cmp     byte ptr [rcx+29h], 1
0x140035d08  jb      short loc_140035D2C
0x140035d0a  mov     rcx, [rcx+18h]
0x140035d0e  lea     r8, WPP_826bdefea5f439a79d7b4a7e09ca5b98_Traceguids
0x140035d15  mov     edx, r15d
0x140035d18  mov     dword ptr [rsp+78h+var_58], 0C000009Ah
0x140035d20  mov     r9, rbp
0x140035d23  call    WPP_SF_qD
0x140035d28  jmp     short loc_140035D2C
0x140035d2a  xor     ebx, ebx
0x140035d2c  xor     edx, edx
0x140035d2e  lea     rcx, [rsi+10h]
0x140035d32  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140035d39  nop     dword ptr [rax+rax+00h]
0x140035d3e  test    r14b, r14b
0x140035d41  jz      loc_140035E28
0x140035d47  lea     rdx, [rdi+68h]
0x140035d4b  mov     r8, [rdx+8]
0x140035d4f  cmp     [r8], rdx
0x140035d52  jz      short loc_140035D5B
0x140035d54  mov     ecx, 3
0x140035d59  int     29h; Win8: RtlFailFast(ecx)
0x140035d5b  mov     rax, [rbp+28h]
0x140035d5f  mov     r13d, 1
0x140035d65  mov     rcx, [rax+28h]
0x140035d69  mov     rsi, [rcx+1A0h]
0x140035d70  mov     r14, [rsi+180h]
0x140035d77  mov     [rbx], rdx
0x140035d7a  mov     [rbx+8], r8
0x140035d7e  mov     [r8], rbx
0x140035d81  mov     [rdx+8], rbx
0x140035d85  mov     eax, [rdi+84h]
0x140035d8b  mov     [rbx+20h], eax
0x140035d8e  add     [rdi+78h], r13d
0x140035d92  cmp     [rdi+78h], r13d
0x140035d96  jnz     short loc_140035DB3
0x140035d98  mov     rcx, [rsp+78h+arg_0]
0x140035da0  lea     rdx, [rdi+88h]
0x140035da7  call    cs:__imp_MRxSmbActivateRecurrentService
0x140035dae  nop     dword ptr [rax+rax+00h]
0x140035db3  mov     eax, r13d
0x140035db6  lock xadd [rsi+2C0h], eax
0x140035dbe  add     eax, r13d
0x140035dc1  cmp     eax, r13d
0x140035dc4  jnz     short loc_140035DEB
0x140035dc6  mov     eax, [r14+304h]
0x140035dcd  mov     r8d, 2
0x140035dd3  test    eax, eax
0x140035dd5  mov     rcx, rsi
0x140035dd8  cmovnz  r15d, eax
0x140035ddc  mov     edx, r15d
0x140035ddf  call    cs:__imp_SmbCeSetConnectionKeepalive
0x140035de6  nop     dword ptr [rax+rax+00h]
0x140035deb  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140035df2  lea     rax, WPP_GLOBAL_Control
0x140035df9  cmp     rcx, rax
0x140035dfc  jz      short loc_140035E28
0x140035dfe  mov     eax, [rcx+2Ch]
0x140035e01  test    al, 40h
0x140035e03  jz      short loc_140035E28
0x140035e05  cmp     byte ptr [rcx+29h], 2
0x140035e09  jb      short loc_140035E28
0x140035e0b  mov     rcx, [rcx+18h]
0x140035e0f  lea     r8, WPP_826bdefea5f439a79d7b4a7e09ca5b98_Traceguids
0x140035e16  mov     edx, 0Bh
0x140035e1b  mov     [rsp+78h+var_58], rbx
0x140035e20  mov     r9, rbp
0x140035e23  call    WPP_SF_qq
0x140035e28  mov     rcx, rdi; Resource
0x140035e2b  call    cs:__imp_ExReleaseResourceLite
0x140035e32  nop     dword ptr [rax+rax+00h]
0x140035e37  mov     eax, r12d
0x140035e3a  add     rsp, 38h
0x140035e3e  pop     r15
0x140035e40  pop     r14
0x140035e42  pop     r13
0x140035e44  pop     r12
0x140035e46  pop     rdi
0x140035e47  pop     rsi
0x140035e48  pop     rbp
0x140035e49  pop     rbx
0x140035e4a  retn
```
