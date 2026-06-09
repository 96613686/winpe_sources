# VctEstablishConnection

- ea: `0x140094bf0`
- end: `0x140094f83`
- name: `VctEstablishConnection`
- size: `915`
- prototype: `__int64 __fastcall(_QWORD *, const UNICODE_STRING *, __int64, __int64, char, char, _BYTE *, unsigned __int16 *, int, __int64, __int64, char, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14002cc00`

## callees

- `0x14004fd80`
- `0x14008df10`
- `0x140091480`
- `0x140094bf0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140094ced`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140094ced`
- `ntoskrnl!RtlxUnicodeStringToOemSize` at `0x140094d08`
- `ntoskrnl!RtlxUnicodeStringToOemSize` at `0x140094d08`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140094f00`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140094f00`
- `ntoskrnl!PsReferenceSiloContext` at `0x140094dc2`
- `ntoskrnl!PsReferenceSiloContext` at `0x140094dc2`
- `ntoskrnl!ExAllocatePool2` at `0x140094caa`
- `ntoskrnl!ExAllocatePool2` at `0x140094d45`
- `ntoskrnl!ExAllocatePool2` at `0x140094de5`
- `ntoskrnl!ExAllocatePool2` at `0x140094caa`
- `ntoskrnl!ExAllocatePool2` at `0x140094d45`
- `ntoskrnl!ExAllocatePool2` at `0x140094de5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094f1a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094f32`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094f4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094f1a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094f32`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094f4b`

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
        unsigned __int16 *a8,
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
  int v32; // eax
  void *v33; // rcx
  _DWORD v35[18]; // [rsp+90h] [rbp-48h] BYREF

  v35[0] = 0;
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
    v33 = *(void **)(v25 + 104);
    if ( v33 )
    {
      ExFreePoolWithTag(v33, 0x6D536356u);
      *(_QWORD *)(v25 + 104) = 0;
    }
    ExFreePoolWithTag((PVOID)v25, 0x6D536356u);
    if ( v26 )
      ExFreePoolWithTag(v26, 0x6D536356u);
    goto LABEL_35;
  }
  if ( a7 && (*a7 & 1) != 0 )
    *(_BYTE *)(v25 + 112) = 1;
  ServerAvailability = VctBuildTransportAddress(v30, *(unsigned int *)(v25 + 96), a2, v35);
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
    RxCeEstablishConnectionNew(
      (const void **)(v25 + 152),
      v31,
      v25,
      (__int64)VctCompleteConnectRequest,
      (__int64)MRxSmbVctConnectionEventHandler,
      a10,
      a4,
      a7,
      a8,
      a5,
      a6,
      a9,
      a13,
      a14,
      a15,
      a16,
      a17);
    ServerAvailability = v32;
  }
  if ( ServerAvailability != 259 )
    goto LABEL_29;
  return (unsigned int)ServerAvailability;
}

```

## disassembly

```asm
0x140094bf0  mov     rax, rsp
0x140094bf3  mov     [rax+10h], rbx
0x140094bf7  mov     [rax+20h], r9
0x140094bfb  mov     [rax+8], rcx
0x140094bff  push    rbp
0x140094c00  push    rsi
0x140094c01  push    rdi
0x140094c02  push    r12
0x140094c04  push    r13
0x140094c06  push    r14
0x140094c08  push    r15
0x140094c0a  sub     rsp, 0A0h
0x140094c11  cmp     [rsp+0D8h+arg_58], 0
0x140094c19  mov     r12, r8
0x140094c1c  mov     r14, [rsp+0D8h+arg_70]
0x140094c24  mov     r13, rdx
0x140094c27  mov     r15, [rsp+0D8h+arg_60]
0x140094c2f  mov     dword ptr [rax-48h], 0
0x140094c36  jnz     short loc_140094C91
0x140094c38  test    r15, r15
0x140094c3b  jz      short loc_140094C6F
0x140094c3d  test    r14, r14
0x140094c40  jz      short loc_140094C6F
0x140094c42  test    dword ptr [r15+150h], 2000h
0x140094c4d  jz      short loc_140094C6F
0x140094c4f  mov     eax, [r15+514h]
0x140094c56  cmp     eax, [r14+4]
0x140094c5a  jnb     short loc_140094C6F
0x140094c5c  mov     rcx, [r14+rax*8+30h]
0x140094c61  test    rcx, rcx
0x140094c64  jz      short loc_140094C6F
0x140094c66  add     rcx, 0A8h
0x140094c6d  jmp     short loc_140094C76
0x140094c6f  lea     rcx, MRxSmbHostUnavailableServers
0x140094c76  mov     r8d, 3
0x140094c7c  call    SmbCeQueryServerAvailability
0x140094c81  mov     ebx, eax
0x140094c83  test    eax, eax
0x140094c85  jns     short loc_140094C91
0x140094c87  mov     ebp, 8
0x140094c8c  jmp     loc_140094F57
0x140094c91  movzx   edx, word ptr [r13+2]
0x140094c96  mov     ecx, 40h ; '@'
0x140094c9b  add     rdx, 0B0h
0x140094ca2  mov     r8d, 6D536356h
0x140094ca8  xor     ebp, ebp
0x140094caa  call    cs:__imp_ExAllocatePool2
0x140094cb1  nop     dword ptr [rax+rax+00h]
0x140094cb6  mov     rdi, rax
0x140094cb9  test    rax, rax
0x140094cbc  jnz     short loc_140094CC8
0x140094cbe  mov     ebx, 0C000009Ah
0x140094cc3  jmp     loc_140094F57
0x140094cc8  add     rax, 0A8h
0x140094cce  lea     rcx, [rdi+98h]; DestinationString
0x140094cd5  mov     [rdi+0A0h], rax
0x140094cdc  mov     rdx, r13; SourceString
0x140094cdf  movzx   eax, word ptr [r13+2]
0x140094ce4  xor     esi, esi
0x140094ce6  mov     [rdi+9Ah], ax
0x140094ced  call    cs:__imp_RtlCopyUnicodeString
0x140094cf4  nop     dword ptr [rax+rax+00h]
0x140094cf9  mov     rax, [rsp+0D8h+arg_50]
0x140094d01  mov     rcx, r13; UnicodeString
0x140094d04  mov     [rdi+78h], rax
0x140094d08  call    cs:__imp_RtlxUnicodeStringToOemSize
0x140094d0f  nop     dword ptr [rax+rax+00h]
0x140094d14  mov     edx, 12h
0x140094d19  cmp     eax, 10h
0x140094d1c  jbe     short loc_140094D21
0x140094d1e  lea     edx, [rax+2]
0x140094d21  movzx   r8d, word ptr [r13+0]
0x140094d26  lea     edx, [rdx+rdx*2]
0x140094d29  add     r8d, 278h
0x140094d30  mov     ecx, 40h ; '@'
0x140094d35  add     r8d, edx
0x140094d38  mov     [rdi+60h], r8d
0x140094d3c  mov     edx, r8d
0x140094d3f  mov     r8d, 6D536356h
0x140094d45  call    cs:__imp_ExAllocatePool2
0x140094d4c  nop     dword ptr [rax+rax+00h]
0x140094d51  mov     [rdi+68h], rax
0x140094d55  mov     rcx, rax
0x140094d58  test    rax, rax
0x140094d5b  jnz     short loc_140094D6A
0x140094d5d  mov     ebx, 0C000009Ah
0x140094d62  xor     r13d, r13d
0x140094d65  jmp     loc_140094EF4
0x140094d6a  mov     rax, [rsp+0D8h+arg_30]
0x140094d72  test    rax, rax
0x140094d75  jz      short loc_140094D80
0x140094d77  test    byte ptr [rax], 1
0x140094d7a  jz      short loc_140094D80
0x140094d7c  mov     byte ptr [rdi+70h], 1
0x140094d80  mov     edx, [rdi+60h]
0x140094d83  lea     r9, [rsp+0D8h+var_48]
0x140094d8b  mov     r8, r13
0x140094d8e  call    VctBuildTransportAddress
0x140094d93  xor     r13d, r13d
0x140094d96  mov     ebx, eax
0x140094d98  test    eax, eax
0x140094d9a  jnz     loc_140094EEC
0x140094da0  mov     rax, [rsp+0D8h+arg_0]
0x140094da8  mov     [rdi+50h], r13
0x140094dac  mov     [rax], r13
0x140094daf  mov     [rdi+58h], rax
0x140094db3  test    r14, r14
0x140094db6  jz      short loc_140094DD5
0x140094db8  mov     rcx, r14
0x140094dbb  mov     [rdi+80h], r15
0x140094dc2  call    cs:__imp_PsReferenceSiloContext
0x140094dc9  nop     dword ptr [rax+rax+00h]
0x140094dce  mov     [rdi+88h], r14
0x140094dd5  mov     edx, 48h ; 'H'
0x140094dda  mov     ecx, 42h ; 'B'
0x140094ddf  mov     r8d, 6D536356h
0x140094de5  call    cs:__imp_ExAllocatePool2
0x140094dec  nop     dword ptr [rax+rax+00h]
0x140094df1  mov     rsi, rax
0x140094df4  test    rax, rax
0x140094df7  jnz     short loc_140094E03
0x140094df9  mov     ebx, 0C000009Ah
0x140094dfe  jmp     loc_140094EF4
0x140094e03  mov     [rax], r13d
0x140094e06  mov     [rax+10h], r13d
0x140094e0a  mov     eax, [rdi+60h]
0x140094e0d  mov     [rsi+20h], eax
0x140094e10  mov     rax, [rdi+68h]
0x140094e14  mov     [rsi+28h], rax
0x140094e18  test    r12, r12
0x140094e1b  jz      short loc_140094E36
0x140094e1d  mov     rax, [r12]
0x140094e21  mov     [rsi+30h], rax
0x140094e25  mov     eax, [r12+10h]
0x140094e2a  mov     [rsi+38h], eax
0x140094e2d  mov     rax, [r12+20h]
0x140094e32  mov     [rsi+40h], rax
0x140094e36  mov     rax, [rsp+0D8h+arg_80]
0x140094e3e  lea     r9, VctCompleteConnectRequest
0x140094e45  mov     [rsp+0D8h+var_58], rax
0x140094e4d  lea     rcx, [rdi+98h]
0x140094e54  mov     rax, [rsp+0D8h+arg_78]
0x140094e5c  mov     r8, rdi
0x140094e5f  mov     [rsp+0D8h+var_60], rax
0x140094e64  mov     rdx, rsi
0x140094e67  mov     rax, [rsp+0D8h+arg_68]
0x140094e6f  mov     [rsp+0D8h+var_68], r14
0x140094e74  mov     [rsp+0D8h+var_70], rax
0x140094e79  mov     eax, [rsp+0D8h+arg_40]
0x140094e80  mov     [rsp+0D8h+var_78], r15
0x140094e85  mov     [rsp+0D8h+var_80], eax
0x140094e89  movzx   eax, [rsp+0D8h+arg_28]
0x140094e91  mov     [rsp+0D8h+var_88], al
0x140094e95  movzx   eax, [rsp+0D8h+arg_20]
0x140094e9d  mov     [rsp+0D8h+var_90], al
0x140094ea1  mov     rax, [rsp+0D8h+arg_38]
0x140094ea9  mov     [rsp+0D8h+var_98], rax
0x140094eae  mov     rax, [rsp+0D8h+arg_30]
0x140094eb6  mov     [rsp+0D8h+var_A0], rax
0x140094ebb  mov     rax, [rsp+0D8h+arg_18]
0x140094ec3  mov     [rsp+0D8h+var_A8], rax
0x140094ec8  mov     rax, [rsp+0D8h+arg_48]
0x140094ed0  mov     [rsp+0D8h+var_B0], rax
0x140094ed5  lea     rax, MRxSmbVctConnectionEventHandler
0x140094edc  mov     [rsp+0D8h+var_B8], rax
0x140094ee1  mov     [rdi+48h], rsi
0x140094ee5  call    RxCeEstablishConnectionNew
0x140094eea  mov     ebx, eax
0x140094eec  cmp     ebx, 103h
0x140094ef2  jz      short loc_140094F65
0x140094ef4  mov     rcx, [rdi+88h]
0x140094efb  test    rcx, rcx
0x140094efe  jz      short loc_140094F0C
0x140094f00  call    cs:__imp_PsDereferenceSiloContext
0x140094f07  nop     dword ptr [rax+rax+00h]
0x140094f0c  mov     rcx, [rdi+68h]; P
0x140094f10  test    rcx, rcx
0x140094f13  jz      short loc_140094F2A
0x140094f15  mov     edx, 6D536356h; Tag
0x140094f1a  call    cs:__imp_ExFreePoolWithTag
0x140094f21  nop     dword ptr [rax+rax+00h]
0x140094f26  mov     [rdi+68h], r13
0x140094f2a  mov     edx, 6D536356h; Tag
0x140094f2f  mov     rcx, rdi; P
0x140094f32  call    cs:__imp_ExFreePoolWithTag
0x140094f39  nop     dword ptr [rax+rax+00h]
0x140094f3e  test    rsi, rsi
0x140094f41  jz      short loc_140094F57
0x140094f43  mov     edx, 6D536356h; Tag
0x140094f48  mov     rcx, rsi; P
0x140094f4b  call    cs:__imp_ExFreePoolWithTag
0x140094f52  nop     dword ptr [rax+rax+00h]
0x140094f57  mov     rax, [rsp+0D8h+arg_50]
0x140094f5f  mov     [rax+8], ebx
0x140094f62  mov     [rax+0Ch], ebp
0x140094f65  mov     eax, ebx
0x140094f67  mov     rbx, [rsp+0D8h+arg_8]
0x140094f6f  add     rsp, 0A0h
0x140094f76  pop     r15
0x140094f78  pop     r14
0x140094f7a  pop     r13
0x140094f7c  pop     r12
0x140094f7e  pop     rdi
0x140094f7f  pop     rsi
0x140094f80  pop     rbp
0x140094f81  retn
```
