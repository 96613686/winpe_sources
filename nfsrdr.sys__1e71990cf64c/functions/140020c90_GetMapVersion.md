# GetMapVersion

- ea: `0x140020c90`
- end: `0x140020f9f`
- name: `GetMapVersion`
- size: `783`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140020fa8`
- `0x1400219e8`

## callees

- `0x14000adb0`
- `0x1400159cc`
- `0x1400159fc`
- `0x140015ab8`
- `0x140020c90`
- `0x14002d1e4`
- `0x14002d334`

## import_xrefs

- `ntoskrnl!ExInitializeResourceLite` at `0x140020dab`
- `ntoskrnl!ExInitializeResourceLite` at `0x140020dab`
- `ntoskrnl!ExDeleteResourceLite` at `0x140020f21`
- `ntoskrnl!ExDeleteResourceLite` at `0x140020f21`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020f32`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020f54`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020f32`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020f54`
- `ntoskrnl!ExAllocatePool2` at `0x140020d0e`
- `ntoskrnl!ExAllocatePool2` at `0x140020d7a`
- `ntoskrnl!ExAllocatePool2` at `0x140020d0e`
- `ntoskrnl!ExAllocatePool2` at `0x140020d7a`

## pseudocode

```c
__int64 __fastcall GetMapVersion(__int64 a1, __int64 a2)
{
  char *Pool2; // rsi
  PDEVICE_OBJECT v5; // rcx
  __int64 v6; // rdx
  int HostByNameWide; // ebx
  _QWORD *v8; // r14
  struct _ERESOURCE *v9; // rax
  unsigned int v10; // r15d
  _OWORD *v11; // rbp
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int16 v14; // ax
  unsigned int v16; // [rsp+B0h] [rbp+18h] BYREF

  v16 = 20;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids);
  if ( g_UniMappingServer.Length && g_UniMappingServer.Buffer )
  {
    Pool2 = (char *)ExAllocatePool2(258, 560, 844260942);
    if ( !Pool2 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_11;
      v6 = 12;
LABEL_10:
      WPP_SF_(v5->AttachedDevice, v6, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids);
LABEL_11:
      HostByNameWide = -1073741670;
      goto LABEL_36;
    }
    *(_DWORD *)(a2 + 12) = 351455;
    *(_DWORD *)(a2 + 16) = 2;
    v8 = (_QWORD *)(a2 + 32);
    *(_QWORD *)(a2 + 24) = 0;
    *(_QWORD *)(a2 + 32) = 0;
    v9 = (struct _ERESOURCE *)ExAllocatePool2(66, 104, 1783785038);
    *(_QWORD *)a2 = v9;
    if ( !v9 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_11;
      v6 = 13;
      goto LABEL_10;
    }
    ExInitializeResourceLite(v9);
    HostByNameWide = GetHostByNameWide(*(_QWORD *)(a1 + 80), &g_UniMappingServer, Pool2, &v16);
    if ( HostByNameWide >= 0 )
    {
      v10 = 0;
      if ( v16 )
      {
        v11 = (_OWORD *)(a2 + 44);
        v12 = a2 + 8;
        while ( 1 )
        {
          v13 = 28LL * v10;
          v14 = *(_WORD *)&Pool2[v13];
          if ( v14 == 2 )
          {
            *v11 = *(_OWORD *)&Pool2[v13];
          }
          else if ( v14 == 23 )
          {
            *v11 = *(_OWORD *)&Pool2[v13];
            *(_OWORD *)(a2 + 56) = *(_OWORD *)&Pool2[v13 + 12];
          }
          else
          {
            *v11 = 0;
            *(_OWORD *)(a2 + 56) = 0;
          }
          HostByNameWide = PmapQueryAndProbe(
                             *(_QWORD *)(a1 + 80),
                             a1,
                             (__int16 *)(a2 + 44),
                             *(_DWORD *)(a2 + 12),
                             (unsigned int *)(a2 + 16),
                             v12,
                             (_QWORD *)(a2 + 24),
                             (_QWORD *)(a2 + 32));
          if ( HostByNameWide >= 0 )
            break;
          if ( *v8 )
            NfsForceDisconnect(a2, 0);
          ++v10;
          *(_QWORD *)(a2 + 24) = 0;
          v12 = a2 + 8;
          *v8 = 0;
          if ( v10 >= v16 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              WPP_SF_ZD(
                WPP_GLOBAL_Control->AttachedDevice,
                14,
                (unsigned int)WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids,
                (unsigned int)&g_UniMappingServer,
                HostByNameWide);
            }
            goto LABEL_36;
          }
        }
      }
      goto LABEL_39;
    }
  }
  else
  {
    Pool2 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids);
    HostByNameWide = -1073741730;
  }
LABEL_36:
  if ( *(_QWORD *)a2 )
  {
    ExDeleteResourceLite(*(PERESOURCE *)a2);
    ExFreePoolWithTag(*(PVOID *)a2, 0);
    *(_QWORD *)a2 = 0;
  }
  if ( Pool2 )
LABEL_39:
    ExFreePoolWithTag(Pool2, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids,
      (unsigned int)HostByNameWide);
  return (unsigned int)HostByNameWide;
}

```

## disassembly

```asm
0x140020c90  mov     rax, rsp
0x140020c93  push    rbx
0x140020c94  push    rbp
0x140020c95  push    rsi
0x140020c96  push    rdi
0x140020c97  push    r12
0x140020c99  push    r13
0x140020c9b  push    r14
0x140020c9d  push    r15
0x140020c9f  sub     rsp, 58h
0x140020ca3  mov     rdi, rdx
0x140020ca6  mov     dword ptr [rax+18h], 14h
0x140020cad  mov     r13, rcx
0x140020cb0  mov     rcx, cs:WPP_GLOBAL_Control
0x140020cb7  lea     rbx, WPP_GLOBAL_Control
0x140020cbe  lea     r15, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids
0x140020cc5  cmp     rcx, rbx
0x140020cc8  jz      short loc_140020CE2
0x140020cca  mov     eax, [rcx+2Ch]
0x140020ccd  test    al, 10h
0x140020ccf  jz      short loc_140020CE2
0x140020cd1  mov     rcx, [rcx+18h]
0x140020cd5  mov     edx, 0Ah
0x140020cda  mov     r8, r15
0x140020cdd  call    WPP_SF_
0x140020ce2  xor     ebp, ebp
0x140020ce4  cmp     cs:g_UniMappingServer.Length, bp
0x140020ceb  jbe     loc_140020EE6
0x140020cf1  cmp     cs:g_UniMappingServer.Buffer, rbp
0x140020cf8  jz      loc_140020EE6
0x140020cfe  mov     edx, 230h
0x140020d03  mov     ecx, 102h
0x140020d08  mov     r8d, 3252664Eh
0x140020d0e  call    cs:__imp_ExAllocatePool2
0x140020d15  nop     dword ptr [rax+rax+00h]
0x140020d1a  mov     rsi, rax
0x140020d1d  test    rax, rax
0x140020d20  jnz     short loc_140020D4F
0x140020d22  mov     rcx, cs:WPP_GLOBAL_Control
0x140020d29  cmp     rcx, rbx
0x140020d2c  jz      short loc_140020D45
0x140020d2e  mov     edx, [rcx+2Ch]
0x140020d31  test    dl, 1
0x140020d34  jz      short loc_140020D45
0x140020d36  lea     edx, [rbp+0Ch]
0x140020d39  mov     rcx, [rcx+18h]
0x140020d3d  mov     r8, r15
0x140020d40  call    WPP_SF_
0x140020d45  mov     ebx, 0C000009Ah
0x140020d4a  jmp     loc_140020F12
0x140020d4f  mov     edx, 68h ; 'h'
0x140020d54  mov     dword ptr [rdi+0Ch], 55CDFh
0x140020d5b  lea     r12, [rdi+18h]
0x140020d5f  mov     dword ptr [rdi+10h], 2
0x140020d66  lea     r14, [rdi+20h]
0x140020d6a  mov     [r12], rbp
0x140020d6e  mov     r8d, 6A52664Eh
0x140020d74  mov     [r14], rbp
0x140020d77  lea     ecx, [rdx-26h]
0x140020d7a  call    cs:__imp_ExAllocatePool2
0x140020d81  nop     dword ptr [rax+rax+00h]
0x140020d86  mov     [rdi], rax
0x140020d89  test    rax, rax
0x140020d8c  jnz     short loc_140020DA8
0x140020d8e  mov     rcx, cs:WPP_GLOBAL_Control
0x140020d95  cmp     rcx, rbx
0x140020d98  jz      short loc_140020D45
0x140020d9a  mov     eax, [rcx+2Ch]
0x140020d9d  test    al, 1
0x140020d9f  jz      short loc_140020D45
0x140020da1  mov     edx, 0Dh
0x140020da6  jmp     short loc_140020D39
0x140020da8  mov     rcx, rax; Resource
0x140020dab  call    cs:__imp_ExInitializeResourceLite
0x140020db2  nop     dword ptr [rax+rax+00h]
0x140020db7  mov     rcx, [r13+50h]
0x140020dbb  lea     r9, [rsp+98h+arg_10]
0x140020dc3  mov     r8, rsi
0x140020dc6  lea     rdx, g_UniMappingServer
0x140020dcd  call    GetHostByNameWide
0x140020dd2  mov     ebx, eax
0x140020dd4  test    eax, eax
0x140020dd6  js      loc_140020F12
0x140020ddc  mov     r15d, ebp
0x140020ddf  cmp     [rsp+98h+arg_10], ebp
0x140020de6  jbe     loc_140020F48
0x140020dec  lea     rbp, [rdi+2Ch]
0x140020df0  lea     rdx, [rdi+8]
0x140020df4  mov     eax, r15d
0x140020df7  mov     r8d, 2
0x140020dfd  imul    rcx, rax, 1Ch
0x140020e01  movzx   eax, word ptr [rcx+rsi]
0x140020e05  cmp     ax, r8w
0x140020e09  jz      short loc_140020E31
0x140020e0b  cmp     ax, 17h
0x140020e0f  jz      short loc_140020E1E
0x140020e11  xorps   xmm0, xmm0
0x140020e14  movups  xmmword ptr [rbp+0], xmm0
0x140020e18  movups  xmmword ptr [rbp+0Ch], xmm0
0x140020e1c  jmp     short loc_140020E3A
0x140020e1e  movups  xmm0, xmmword ptr [rcx+rsi]
0x140020e22  movups  xmmword ptr [rbp+0], xmm0
0x140020e26  movups  xmm1, xmmword ptr [rcx+rsi+0Ch]
0x140020e2b  movups  xmmword ptr [rbp+0Ch], xmm1
0x140020e2f  jmp     short loc_140020E3A
0x140020e31  movups  xmm0, xmmword ptr [rcx+rsi]
0x140020e35  movdqu  xmmword ptr [rbp+0], xmm0
0x140020e3a  mov     r9d, [rdi+0Ch]
0x140020e3e  lea     rax, [rdi+10h]
0x140020e42  mov     rcx, [r13+50h]
0x140020e46  mov     r8, rbp
0x140020e49  mov     [rsp+98h+var_58], 0
0x140020e4e  mov     [rsp+98h+var_60], r14
0x140020e53  mov     [rsp+98h+var_68], r12
0x140020e58  mov     [rsp+98h+var_70], rdx
0x140020e5d  mov     rdx, r13
0x140020e60  mov     [rsp+98h+var_78], rax
0x140020e65  call    PmapQueryAndProbe
0x140020e6a  mov     ebx, eax
0x140020e6c  test    eax, eax
0x140020e6e  jns     loc_140020F48
0x140020e74  cmp     qword ptr [r14], 0
0x140020e78  jz      short loc_140020E84
0x140020e7a  xor     edx, edx
0x140020e7c  mov     rcx, rdi
0x140020e7f  call    NfsForceDisconnect
0x140020e84  inc     r15d
0x140020e87  mov     qword ptr [r12], 0
0x140020e8f  lea     rdx, [rdi+8]
0x140020e93  mov     qword ptr [r14], 0
0x140020e9a  cmp     r15d, [rsp+98h+arg_10]
0x140020ea2  jb      loc_140020DF4
0x140020ea8  mov     rcx, cs:WPP_GLOBAL_Control
0x140020eaf  lea     r14, WPP_GLOBAL_Control
0x140020eb6  cmp     rcx, r14
0x140020eb9  jz      short loc_140020EE2
0x140020ebb  mov     eax, [rcx+2Ch]
0x140020ebe  test    al, 1
0x140020ec0  jz      short loc_140020EE2
0x140020ec2  mov     rcx, [rcx+18h]
0x140020ec6  lea     r9, g_UniMappingServer
0x140020ecd  mov     edx, 0Eh
0x140020ed2  mov     dword ptr [rsp+98h+var_78], ebx
0x140020ed6  lea     r8, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids
0x140020edd  call    WPP_SF_ZD
0x140020ee2  xor     ebp, ebp
0x140020ee4  jmp     short loc_140020F19
0x140020ee6  mov     rcx, cs:WPP_GLOBAL_Control
0x140020eed  mov     rsi, rbp
0x140020ef0  cmp     rcx, rbx
0x140020ef3  jz      short loc_140020F0D
0x140020ef5  mov     eax, [rcx+2Ch]
0x140020ef8  test    al, 1
0x140020efa  jz      short loc_140020F0D
0x140020efc  mov     rcx, [rcx+18h]
0x140020f00  mov     edx, 0Bh
0x140020f05  mov     r8, r15
0x140020f08  call    WPP_SF_
0x140020f0d  mov     ebx, 0C000005Eh
0x140020f12  lea     r14, WPP_GLOBAL_Control
0x140020f19  mov     rcx, [rdi]; Resource
0x140020f1c  test    rcx, rcx
0x140020f1f  jz      short loc_140020F41
0x140020f21  call    cs:__imp_ExDeleteResourceLite
0x140020f28  nop     dword ptr [rax+rax+00h]
0x140020f2d  mov     rcx, [rdi]; P
0x140020f30  xor     edx, edx; Tag
0x140020f32  call    cs:__imp_ExFreePoolWithTag
0x140020f39  nop     dword ptr [rax+rax+00h]
0x140020f3e  mov     [rdi], rbp
0x140020f41  test    rsi, rsi
0x140020f44  jz      short loc_140020F60
0x140020f46  jmp     short loc_140020F4F
0x140020f48  lea     r14, WPP_GLOBAL_Control
0x140020f4f  xor     edx, edx; Tag
0x140020f51  mov     rcx, rsi; P
0x140020f54  call    cs:__imp_ExFreePoolWithTag
0x140020f5b  nop     dword ptr [rax+rax+00h]
0x140020f60  mov     rcx, cs:WPP_GLOBAL_Control
0x140020f67  cmp     rcx, r14
0x140020f6a  jz      short loc_140020F8B
0x140020f6c  mov     eax, [rcx+2Ch]
0x140020f6f  test    al, 10h
0x140020f71  jz      short loc_140020F8B
0x140020f73  mov     rcx, [rcx+18h]
0x140020f77  lea     r8, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids
0x140020f7e  mov     edx, 0Fh
0x140020f83  mov     r9d, ebx
0x140020f86  call    WPP_SF_d
0x140020f8b  mov     eax, ebx
0x140020f8d  add     rsp, 58h
0x140020f91  pop     r15
0x140020f93  pop     r14
0x140020f95  pop     r13
0x140020f97  pop     r12
0x140020f99  pop     rdi
0x140020f9a  pop     rsi
0x140020f9b  pop     rbp
0x140020f9c  pop     rbx
0x140020f9d  retn
```
