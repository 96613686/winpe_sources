# VctEstablishConnection

- ea: `0x140094c40`
- end: `0x140094fd3`
- name: `VctEstablishConnection`
- size: `915`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14002cc00`

## callees

- `0x14004fd80`
- `0x14008df60`
- `0x1400914d0`
- `0x140094c40`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140094d3d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140094d3d`
- `ntoskrnl!RtlxUnicodeStringToOemSize` at `0x140094d58`
- `ntoskrnl!RtlxUnicodeStringToOemSize` at `0x140094d58`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140094f50`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140094f50`
- `ntoskrnl!PsReferenceSiloContext` at `0x140094e12`
- `ntoskrnl!PsReferenceSiloContext` at `0x140094e12`
- `ntoskrnl!ExAllocatePool2` at `0x140094cfa`
- `ntoskrnl!ExAllocatePool2` at `0x140094d95`
- `ntoskrnl!ExAllocatePool2` at `0x140094e35`
- `ntoskrnl!ExAllocatePool2` at `0x140094cfa`
- `ntoskrnl!ExAllocatePool2` at `0x140094d95`
- `ntoskrnl!ExAllocatePool2` at `0x140094e35`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094f6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094f82`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094f9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094f6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094f82`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094f9b`

## pseudocode

```c
__int64 __fastcall VctEstablishConnection(
        _QWORD *a1,
        const UNICODE_STRING *a2,
        __int64 a3,
        __int64 a4,
        char a5,
        char a6,
        _BYTE *a7,
        __int64 a8,
        int a9,
        __int64 a10,
        __int64 a11,
        char a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int64 a17)
{
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 *v21; // rcx
  int ServerAvailability; // ebx
  int v23; // ebp
  __int64 Pool2; // rax
  __int64 v25; // rdi
  void *v26; // rsi
  ULONG v27; // eax
  int v28; // edx
  unsigned int v29; // r8d
  __int64 v30; // rax
  __int64 v31; // rax
  void *v32; // rcx
  _DWORD v34[18]; // [rsp+90h] [rbp-48h] BYREF

  v34[0] = 0;
  if ( !a12 )
  {
    if ( a13
      && a15
      && (*(_DWORD *)(a13 + 336) & 0x2000) != 0
      && (v19 = *(unsigned int *)(a13 + 1300), (unsigned int)v19 < *(_DWORD *)(a15 + 4))
      && (v20 = *(_QWORD *)(a15 + 8 * v19 + 48)) != 0 )
    {
      v21 = (__int64 *)(v20 + 168);
    }
    else
    {
      v21 = MRxSmbHostUnavailableServers;
    }
    ServerAvailability = SmbCeQueryServerAvailability(v21, a2, 3);
    if ( ServerAvailability < 0 )
    {
      v23 = 8;
LABEL_35:
      *(_DWORD *)(a11 + 8) = ServerAvailability;
      *(_DWORD *)(a11 + 12) = v23;
      return (unsigned int)ServerAvailability;
    }
  }
  v23 = 0;
  Pool2 = ExAllocatePool2(64, a2->MaximumLength + 176LL, 1834181462);
  v25 = Pool2;
  if ( !Pool2 )
  {
    ServerAvailability = -1073741670;
    goto LABEL_35;
  }
  *(_QWORD *)(Pool2 + 160) = Pool2 + 168;
  v26 = 0;
  *(_WORD *)(Pool2 + 154) = a2->MaximumLength;
  RtlCopyUnicodeString((PUNICODE_STRING)(Pool2 + 152), a2);
  *(_QWORD *)(v25 + 120) = a11;
  v27 = RtlxUnicodeStringToOemSize(a2);
  v28 = 18;
  if ( v27 > 0x10 )
    v28 = v27 + 2;
  v29 = 3 * v28 + a2->Length + 632;
  *(_DWORD *)(v25 + 96) = v29;
  v30 = ExAllocatePool2(64, v29, 1834181462);
  *(_QWORD *)(v25 + 104) = v30;
  if ( !v30 )
  {
    ServerAvailability = -1073741670;
LABEL_29:
    if ( *(_QWORD *)(v25 + 136) )
      PsDereferenceSiloContext();
    v32 = *(void **)(v25 + 104);
    if ( v32 )
    {
      ExFreePoolWithTag(v32, 0x6D536356u);
      *(_QWORD *)(v25 + 104) = 0;
    }
    ExFreePoolWithTag((PVOID)v25, 0x6D536356u);
    if ( v26 )
      ExFreePoolWithTag(v26, 0x6D536356u);
    goto LABEL_35;
  }
  if ( a7 && (*a7 & 1) != 0 )
    *(_BYTE *)(v25 + 112) = 1;
  ServerAvailability = VctBuildTransportAddress(v30, *(unsigned int *)(v25 + 96), a2, v34);
  if ( !ServerAvailability )
  {
    *(_QWORD *)(v25 + 80) = 0;
    *a1 = 0;
    *(_QWORD *)(v25 + 88) = a1;
    if ( a15 )
    {
      *(_QWORD *)(v25 + 128) = a13;
      PsReferenceSiloContext(a15);
      *(_QWORD *)(v25 + 136) = a15;
    }
    v31 = ExAllocatePool2(66, 72, 1834181462);
    v26 = (void *)v31;
    if ( !v31 )
    {
      ServerAvailability = -1073741670;
      goto LABEL_29;
    }
    *(_DWORD *)v31 = 0;
    *(_DWORD *)(v31 + 16) = 0;
    *(_DWORD *)(v31 + 32) = *(_DWORD *)(v25 + 96);
    *(_QWORD *)(v31 + 40) = *(_QWORD *)(v25 + 104);
    if ( a3 )
    {
      *(_QWORD *)(v31 + 48) = *(_QWORD *)a3;
      *(_DWORD *)(v31 + 56) = *(_DWORD *)(a3 + 16);
      *(_QWORD *)(v31 + 64) = *(_QWORD *)(a3 + 32);
    }
    *(_QWORD *)(v25 + 72) = v31;
    ServerAvailability = RxCeEstablishConnectionNew(
                           (int)v25 + 152,
                           v31,
                           v25,
                           (unsigned int)VctCompleteConnectRequest,
                           (__int64)MRxSmbVctConnectionEventHandler,
                           a10,
                           a4,
                           (__int64)a7,
                           a8,
                           a5,
                           a6,
                           a9,
                           a13,
                           a14,
                           a15,
                           a16,
                           a17);
  }
  if ( ServerAvailability != 259 )
    goto LABEL_29;
  return (unsigned int)ServerAvailability;
}

```

## disassembly

```asm
0x140094c40  mov     rax, rsp
0x140094c43  mov     [rax+10h], rbx
0x140094c47  mov     [rax+20h], r9
0x140094c4b  mov     [rax+8], rcx
0x140094c4f  push    rbp
0x140094c50  push    rsi
0x140094c51  push    rdi
0x140094c52  push    r12
0x140094c54  push    r13
0x140094c56  push    r14
0x140094c58  push    r15
0x140094c5a  sub     rsp, 0A0h
0x140094c61  cmp     [rsp+0D8h+arg_58], 0
0x140094c69  mov     r12, r8
0x140094c6c  mov     r14, [rsp+0D8h+arg_70]
0x140094c74  mov     r13, rdx
0x140094c77  mov     r15, [rsp+0D8h+arg_60]
0x140094c7f  mov     dword ptr [rax-48h], 0
0x140094c86  jnz     short loc_140094CE1
0x140094c88  test    r15, r15
0x140094c8b  jz      short loc_140094CBF
0x140094c8d  test    r14, r14
0x140094c90  jz      short loc_140094CBF
0x140094c92  test    dword ptr [r15+150h], 2000h
0x140094c9d  jz      short loc_140094CBF
0x140094c9f  mov     eax, [r15+514h]
0x140094ca6  cmp     eax, [r14+4]
0x140094caa  jnb     short loc_140094CBF
0x140094cac  mov     rcx, [r14+rax*8+30h]
0x140094cb1  test    rcx, rcx
0x140094cb4  jz      short loc_140094CBF
0x140094cb6  add     rcx, 0A8h
0x140094cbd  jmp     short loc_140094CC6
0x140094cbf  lea     rcx, MRxSmbHostUnavailableServers
0x140094cc6  mov     r8d, 3
0x140094ccc  call    SmbCeQueryServerAvailability
0x140094cd1  mov     ebx, eax
0x140094cd3  test    eax, eax
0x140094cd5  jns     short loc_140094CE1
0x140094cd7  mov     ebp, 8
0x140094cdc  jmp     loc_140094FA7
0x140094ce1  movzx   edx, word ptr [r13+2]
0x140094ce6  mov     ecx, 40h ; '@'
0x140094ceb  add     rdx, 0B0h
0x140094cf2  mov     r8d, 6D536356h
0x140094cf8  xor     ebp, ebp
0x140094cfa  call    cs:__imp_ExAllocatePool2
0x140094d01  nop     dword ptr [rax+rax+00h]
0x140094d06  mov     rdi, rax
0x140094d09  test    rax, rax
0x140094d0c  jnz     short loc_140094D18
0x140094d0e  mov     ebx, 0C000009Ah
0x140094d13  jmp     loc_140094FA7
0x140094d18  add     rax, 0A8h
0x140094d1e  lea     rcx, [rdi+98h]; DestinationString
0x140094d25  mov     [rdi+0A0h], rax
0x140094d2c  mov     rdx, r13; SourceString
0x140094d2f  movzx   eax, word ptr [r13+2]
0x140094d34  xor     esi, esi
0x140094d36  mov     [rdi+9Ah], ax
0x140094d3d  call    cs:__imp_RtlCopyUnicodeString
0x140094d44  nop     dword ptr [rax+rax+00h]
0x140094d49  mov     rax, [rsp+0D8h+arg_50]
0x140094d51  mov     rcx, r13; UnicodeString
0x140094d54  mov     [rdi+78h], rax
0x140094d58  call    cs:__imp_RtlxUnicodeStringToOemSize
0x140094d5f  nop     dword ptr [rax+rax+00h]
0x140094d64  mov     edx, 12h
0x140094d69  cmp     eax, 10h
0x140094d6c  jbe     short loc_140094D71
0x140094d6e  lea     edx, [rax+2]
0x140094d71  movzx   r8d, word ptr [r13+0]
0x140094d76  lea     edx, [rdx+rdx*2]
0x140094d79  add     r8d, 278h
0x140094d80  mov     ecx, 40h ; '@'
0x140094d85  add     r8d, edx
0x140094d88  mov     [rdi+60h], r8d
0x140094d8c  mov     edx, r8d
0x140094d8f  mov     r8d, 6D536356h
0x140094d95  call    cs:__imp_ExAllocatePool2
0x140094d9c  nop     dword ptr [rax+rax+00h]
0x140094da1  mov     [rdi+68h], rax
0x140094da5  mov     rcx, rax
0x140094da8  test    rax, rax
0x140094dab  jnz     short loc_140094DBA
0x140094dad  mov     ebx, 0C000009Ah
0x140094db2  xor     r13d, r13d
0x140094db5  jmp     loc_140094F44
0x140094dba  mov     rax, [rsp+0D8h+arg_30]
0x140094dc2  test    rax, rax
0x140094dc5  jz      short loc_140094DD0
0x140094dc7  test    byte ptr [rax], 1
0x140094dca  jz      short loc_140094DD0
0x140094dcc  mov     byte ptr [rdi+70h], 1
0x140094dd0  mov     edx, [rdi+60h]
0x140094dd3  lea     r9, [rsp+0D8h+var_48]
0x140094ddb  mov     r8, r13
0x140094dde  call    VctBuildTransportAddress
0x140094de3  xor     r13d, r13d
0x140094de6  mov     ebx, eax
0x140094de8  test    eax, eax
0x140094dea  jnz     loc_140094F3C
0x140094df0  mov     rax, [rsp+0D8h+arg_0]
0x140094df8  mov     [rdi+50h], r13
0x140094dfc  mov     [rax], r13
0x140094dff  mov     [rdi+58h], rax
0x140094e03  test    r14, r14
0x140094e06  jz      short loc_140094E25
0x140094e08  mov     rcx, r14
0x140094e0b  mov     [rdi+80h], r15
0x140094e12  call    cs:__imp_PsReferenceSiloContext
0x140094e19  nop     dword ptr [rax+rax+00h]
0x140094e1e  mov     [rdi+88h], r14
0x140094e25  mov     edx, 48h ; 'H'
0x140094e2a  mov     ecx, 42h ; 'B'
0x140094e2f  mov     r8d, 6D536356h
0x140094e35  call    cs:__imp_ExAllocatePool2
0x140094e3c  nop     dword ptr [rax+rax+00h]
0x140094e41  mov     rsi, rax
0x140094e44  test    rax, rax
0x140094e47  jnz     short loc_140094E53
0x140094e49  mov     ebx, 0C000009Ah
0x140094e4e  jmp     loc_140094F44
0x140094e53  mov     [rax], r13d
0x140094e56  mov     [rax+10h], r13d
0x140094e5a  mov     eax, [rdi+60h]
0x140094e5d  mov     [rsi+20h], eax
0x140094e60  mov     rax, [rdi+68h]
0x140094e64  mov     [rsi+28h], rax
0x140094e68  test    r12, r12
0x140094e6b  jz      short loc_140094E86
0x140094e6d  mov     rax, [r12]
0x140094e71  mov     [rsi+30h], rax
0x140094e75  mov     eax, [r12+10h]
0x140094e7a  mov     [rsi+38h], eax
0x140094e7d  mov     rax, [r12+20h]
0x140094e82  mov     [rsi+40h], rax
0x140094e86  mov     rax, [rsp+0D8h+arg_80]
0x140094e8e  lea     r9, VctCompleteConnectRequest
0x140094e95  mov     [rsp+0D8h+var_58], rax
0x140094e9d  lea     rcx, [rdi+98h]
0x140094ea4  mov     rax, [rsp+0D8h+arg_78]
0x140094eac  mov     r8, rdi
0x140094eaf  mov     [rsp+0D8h+var_60], rax
0x140094eb4  mov     rdx, rsi
0x140094eb7  mov     rax, [rsp+0D8h+arg_68]
0x140094ebf  mov     [rsp+0D8h+var_68], r14
0x140094ec4  mov     [rsp+0D8h+var_70], rax
0x140094ec9  mov     eax, [rsp+0D8h+arg_40]
0x140094ed0  mov     [rsp+0D8h+var_78], r15
0x140094ed5  mov     [rsp+0D8h+var_80], eax
0x140094ed9  movzx   eax, [rsp+0D8h+arg_28]
0x140094ee1  mov     [rsp+0D8h+var_88], al
0x140094ee5  movzx   eax, [rsp+0D8h+arg_20]
0x140094eed  mov     [rsp+0D8h+var_90], al
0x140094ef1  mov     rax, [rsp+0D8h+arg_38]
0x140094ef9  mov     [rsp+0D8h+var_98], rax
0x140094efe  mov     rax, [rsp+0D8h+arg_30]
0x140094f06  mov     [rsp+0D8h+var_A0], rax
0x140094f0b  mov     rax, [rsp+0D8h+arg_18]
0x140094f13  mov     [rsp+0D8h+var_A8], rax
0x140094f18  mov     rax, [rsp+0D8h+arg_48]
0x140094f20  mov     [rsp+0D8h+var_B0], rax
0x140094f25  lea     rax, MRxSmbVctConnectionEventHandler
0x140094f2c  mov     [rsp+0D8h+var_B8], rax
0x140094f31  mov     [rdi+48h], rsi
0x140094f35  call    RxCeEstablishConnectionNew
0x140094f3a  mov     ebx, eax
0x140094f3c  cmp     ebx, 103h
0x140094f42  jz      short loc_140094FB5
0x140094f44  mov     rcx, [rdi+88h]
0x140094f4b  test    rcx, rcx
0x140094f4e  jz      short loc_140094F5C
0x140094f50  call    cs:__imp_PsDereferenceSiloContext
0x140094f57  nop     dword ptr [rax+rax+00h]
0x140094f5c  mov     rcx, [rdi+68h]; P
0x140094f60  test    rcx, rcx
0x140094f63  jz      short loc_140094F7A
0x140094f65  mov     edx, 6D536356h; Tag
0x140094f6a  call    cs:__imp_ExFreePoolWithTag
0x140094f71  nop     dword ptr [rax+rax+00h]
0x140094f76  mov     [rdi+68h], r13
0x140094f7a  mov     edx, 6D536356h; Tag
0x140094f7f  mov     rcx, rdi; P
0x140094f82  call    cs:__imp_ExFreePoolWithTag
0x140094f89  nop     dword ptr [rax+rax+00h]
0x140094f8e  test    rsi, rsi
0x140094f91  jz      short loc_140094FA7
0x140094f93  mov     edx, 6D536356h; Tag
0x140094f98  mov     rcx, rsi; P
0x140094f9b  call    cs:__imp_ExFreePoolWithTag
0x140094fa2  nop     dword ptr [rax+rax+00h]
0x140094fa7  mov     rax, [rsp+0D8h+arg_50]
0x140094faf  mov     [rax+8], ebx
0x140094fb2  mov     [rax+0Ch], ebp
0x140094fb5  mov     eax, ebx
0x140094fb7  mov     rbx, [rsp+0D8h+arg_8]
0x140094fbf  add     rsp, 0A0h
0x140094fc6  pop     r15
0x140094fc8  pop     r14
0x140094fca  pop     r13
0x140094fcc  pop     r12
0x140094fce  pop     rdi
0x140094fcf  pop     rsi
0x140094fd0  pop     rbp
0x140094fd1  retn
```
