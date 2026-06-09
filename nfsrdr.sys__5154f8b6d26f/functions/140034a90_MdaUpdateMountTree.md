# MdaUpdateMountTree

- ea: `0x140034a90`
- end: `0x140034e34`
- name: `MdaUpdateMountTree`
- size: `932`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1400273f0`

## callees

- `0x1400159cc`
- `0x1400159fc`
- `0x14002372c`
- `0x140034a64`
- `0x140034a90`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140034ad1`
- `ntoskrnl!ExAcquireFastMutex` at `0x140034d39`
- `ntoskrnl!ExAcquireFastMutex` at `0x140034ad1`
- `ntoskrnl!ExAcquireFastMutex` at `0x140034d39`
- `ntoskrnl!ExReleaseFastMutex` at `0x140034aff`
- `ntoskrnl!ExReleaseFastMutex` at `0x140034d6b`
- `ntoskrnl!ExReleaseFastMutex` at `0x140034aff`
- `ntoskrnl!ExReleaseFastMutex` at `0x140034d6b`
- `ntoskrnl!RtlInitAnsiString` at `0x140034bdd`
- `ntoskrnl!RtlInitAnsiString` at `0x140034bdd`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x140034c54`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x140034c54`
- `ntoskrnl!RtlInitializeUnicodePrefix` at `0x140034b60`
- `ntoskrnl!RtlInitializeUnicodePrefix` at `0x140034b60`
- `ntoskrnl!RtlInsertUnicodePrefix` at `0x140034cc3`
- `ntoskrnl!RtlInsertUnicodePrefix` at `0x140034cc3`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x140034d81`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x140034d81`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034bc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034c70`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034d92`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034db6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034dd2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034bc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034c70`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034d92`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034db6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034dd2`
- `ntoskrnl!ExAllocatePool2` at `0x140034b2b`
- `ntoskrnl!ExAllocatePool2` at `0x140034c06`
- `ntoskrnl!ExAllocatePool2` at `0x140034b2b`
- `ntoskrnl!ExAllocatePool2` at `0x140034c06`
- `rpcxdr!OncRpcDestroy` at `0x140034d16`
- `rpcxdr!OncRpcDestroy` at `0x140034d16`

## pseudocode

```c
__int64 __fastcall MdaUpdateMountTree(int a1, __int64 a2)
{
  __int64 v2; // r15
  struct _FAST_MUTEX *v4; // rcx
  int v5; // r13d
  unsigned int v6; // esi
  __int64 v7; // rdi
  __int64 v8; // rbx
  char v9; // r14
  struct _UNICODE_PREFIX_TABLE *Pool2; // rax
  __int64 v11; // rdx
  struct _UNICODE_PREFIX_TABLE *v12; // rdi
  struct _UNICODE_PREFIX_TABLE *v13; // rbx
  int Export; // eax
  unsigned __int16 v15; // dx
  __int64 v16; // rax
  struct _UNICODE_PREFIX_TABLE_ENTRY *v17; // rsi
  struct _UNICODE_STRING *v18; // rbx
  __int64 v19; // rcx
  PWSTR Buffer; // rdx
  struct _FAST_MUTEX *v21; // rcx
  struct _UNICODE_PREFIX_TABLE_ENTRY *UnicodePrefix; // rax
  struct _UNICODE_PREFIX_TABLE_ENTRY *v23; // rdi
  PVOID P[2]; // [rsp+30h] [rbp-10h] BYREF
  int v26; // [rsp+88h] [rbp+48h] BYREF
  __int64 v27; // [rsp+90h] [rbp+50h] BYREF
  __int64 v28; // [rsp+98h] [rbp+58h]

  v2 = *(_QWORD *)(a2 + 32);
  v27 = 0;
  v26 = 0;
  *(_OWORD *)P = 0;
  v4 = *(struct _FAST_MUTEX **)(v2 + 216);
  v5 = a2;
  v28 = v2;
  v6 = 0;
  ExAcquireFastMutex(v4);
  v7 = MEMORY[0xFFFFF78000000014];
  v8 = *(_QWORD *)(v2 + 224) + 600000000LL;
  ExReleaseFastMutex(*(PFAST_MUTEX *)(v2 + 216));
  P[1] = 0;
  if ( v7 <= v8 )
    goto LABEL_37;
  v9 = 1;
  Pool2 = (struct _UNICODE_PREFIX_TABLE *)ExAllocatePool2(258, 24, 1364354638);
  v12 = Pool2;
  if ( Pool2 )
  {
    RtlInitializeUnicodePrefix(Pool2);
    v27 = 0;
    while ( 1 )
    {
      Export = MntFindExport(a1, v5, (unsigned int)&v27, (unsigned int)&v26, (__int64)&P[1]);
      v6 = Export;
      if ( Export < 0 )
        break;
      v15 = v26;
      LOWORD(P[0]) = v26;
      if ( (_WORD)v26 )
      {
        WORD1(P[0]) = v26 + 1;
        if ( (_WORD)v26 == 1 && *(_BYTE *)P[1] == 47 )
        {
          ExFreePoolWithTag(P[1], 0);
          P[1] = 0;
          RtlInitAnsiString((PANSI_STRING)P, "/!");
          v15 = (unsigned __int16)P[0];
          v9 = 0;
        }
        v16 = ExAllocatePool2(258, 2LL * v15 + 74, 1347577422);
        v17 = (struct _UNICODE_PREFIX_TABLE_ENTRY *)v16;
        if ( !v16 )
        {
          OncRpcDestroy(v27);
          goto LABEL_3;
        }
        v18 = (struct _UNICODE_STRING *)((v16 + 63) & 0xFFFFFFFFFFFFFFF8uLL);
        v18->Length = 2 * LOWORD(P[0]);
        v18->MaximumLength = 2 * (LOWORD(P[0]) + 1);
        v18->Buffer = (PWSTR)(((unsigned __int64)&v18[1].MaximumLength + 5) & 0xFFFFFFFFFFFFFFF8uLL);
        RtlAnsiStringToUnicodeString(v18, (PCANSI_STRING)P, 0);
        if ( P[1] )
        {
          if ( v9 )
            ExFreePoolWithTag(P[1], 0);
          P[1] = 0;
        }
        v19 = 0;
        if ( (v18->Length & 0xFFFE) != 0 )
        {
          do
          {
            Buffer = v18->Buffer;
            if ( Buffer[v19] == 47 )
              Buffer[v19] = 92;
            v19 = (unsigned int)(v19 + 1);
          }
          while ( (unsigned int)v19 < v18->Length >> 1 );
          v2 = v28;
        }
        RtlInsertUnicodePrefix(v12, v18, v17);
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids);
      }
    }
    if ( Export == -2147483642 )
    {
      ExAcquireFastMutex(*(PFAST_MUTEX *)(v2 + 216));
      v13 = *(struct _UNICODE_PREFIX_TABLE **)(v2 + 232);
      *(_QWORD *)(v2 + 232) = v12;
      v21 = *(struct _FAST_MUTEX **)(v2 + 216);
      *(_QWORD *)(v2 + 224) = MEMORY[0xFFFFF78000000014];
      ExReleaseFastMutex(v21);
      v6 = 0;
      goto LABEL_5;
    }
  }
  else
  {
LABEL_3:
    v6 = -1073741670;
  }
  v13 = v12;
LABEL_5:
  if ( v13 )
  {
    while ( 1 )
    {
      LOBYTE(v11) = 1;
      UnicodePrefix = (struct _UNICODE_PREFIX_TABLE_ENTRY *)MdaTryNextUnicodePrefix(v13, v11);
      v23 = UnicodePrefix;
      if ( !UnicodePrefix )
        break;
      RtlRemoveUnicodePrefix(v13, UnicodePrefix);
      ExFreePoolWithTag(v23, 0);
    }
    ExFreePoolWithTag(v13, 0);
  }
  if ( P[1] )
  {
    if ( v9 )
      ExFreePoolWithTag(P[1], 0);
    P[1] = 0;
  }
LABEL_37:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids);
  return v6;
}

```

## disassembly

```asm
0x140034a90  mov     [rsp-38h+arg_0], rbx
0x140034a95  push    rbp
0x140034a96  push    rsi
0x140034a97  push    rdi
0x140034a98  push    r12
0x140034a9a  push    r13
0x140034a9c  push    r14
0x140034a9e  push    r15
0x140034aa0  mov     rbp, rsp
0x140034aa3  sub     rsp, 40h
0x140034aa7  mov     r15, [rdx+20h]
0x140034aab  xor     r14d, r14d
0x140034aae  xorps   xmm0, xmm0
0x140034ab1  mov     [rbp+arg_10], r14
0x140034ab5  mov     r12, rcx
0x140034ab8  mov     [rbp+arg_8], r14d
0x140034abc  movups  xmmword ptr [rbp+P], xmm0
0x140034ac0  mov     rcx, [r15+0D8h]; FastMutex
0x140034ac7  mov     r13, rdx
0x140034aca  mov     [rbp+arg_18], r15
0x140034ace  mov     esi, r14d
0x140034ad1  call    cs:__imp_ExAcquireFastMutex
0x140034ad8  nop     dword ptr [rax+rax+00h]
0x140034add  mov     rdi, 0FFFFF78000000014h
0x140034ae7  mov     rdi, [rdi]
0x140034aea  mov     rbx, [r15+0E0h]
0x140034af1  mov     rcx, [r15+0D8h]; FastMutex
0x140034af8  add     rbx, 23C34600h
0x140034aff  call    cs:__imp_ExReleaseFastMutex
0x140034b06  nop     dword ptr [rax+rax+00h]
0x140034b0b  mov     [rbp+P+8], r14
0x140034b0f  cmp     rdi, rbx
0x140034b12  jle     loc_140034DE6
0x140034b18  mov     edx, 18h
0x140034b1d  mov     ecx, 102h
0x140034b22  mov     r8d, 5152664Eh
0x140034b28  mov     r14b, 1
0x140034b2b  call    cs:__imp_ExAllocatePool2
0x140034b32  nop     dword ptr [rax+rax+00h]
0x140034b37  xor     ebx, ebx
0x140034b39  mov     rdi, rax
0x140034b3c  test    rax, rax
0x140034b3f  jnz     short loc_140034B5D
0x140034b41  mov     esi, 0C000009Ah
0x140034b46  mov     rbx, rdi
0x140034b49  test    rbx, rbx
0x140034b4c  jz      loc_140034DC2
0x140034b52  mov     r15d, 1
0x140034b58  jmp     loc_140034D9E
0x140034b5d  mov     rcx, rdi; PrefixTable
0x140034b60  call    cs:__imp_RtlInitializeUnicodePrefix
0x140034b67  nop     dword ptr [rax+rax+00h]
0x140034b6c  mov     [rbp+arg_10], rbx
0x140034b70  lea     rax, [rbp+P+8]
0x140034b74  mov     rdx, r13
0x140034b77  lea     r9, [rbp+arg_8]
0x140034b7b  mov     [rsp+40h+var_20], rax
0x140034b80  lea     r8, [rbp+arg_10]
0x140034b84  mov     rcx, r12
0x140034b87  call    MntFindExport
0x140034b8c  mov     esi, eax
0x140034b8e  test    eax, eax
0x140034b90  js      loc_140034D27
0x140034b96  mov     edx, [rbp+arg_8]
0x140034b99  mov     word ptr [rbp+P], dx
0x140034b9d  test    dx, dx
0x140034ba0  jz      loc_140034CD6
0x140034ba6  mov     ecx, 1
0x140034bab  lea     eax, [rcx+rdx]
0x140034bae  mov     word ptr [rbp+P+2], ax
0x140034bb2  cmp     cx, dx
0x140034bb5  jnz     short loc_140034BF0
0x140034bb7  mov     rcx, [rbp+P+8]; P
0x140034bbb  cmp     byte ptr [rcx], 2Fh ; '/'
0x140034bbe  jnz     short loc_140034BF0
0x140034bc0  xor     edx, edx; Tag
0x140034bc2  call    cs:__imp_ExFreePoolWithTag
0x140034bc9  nop     dword ptr [rax+rax+00h]
0x140034bce  lea     rdx, asc_14003DEC8; "/!"
0x140034bd5  mov     [rbp+P+8], rbx
0x140034bd9  lea     rcx, [rbp+P]; DestinationString
0x140034bdd  call    cs:__imp_RtlInitAnsiString
0x140034be4  nop     dword ptr [rax+rax+00h]
0x140034be9  movzx   edx, word ptr [rbp+P]
0x140034bed  mov     r14b, bl
0x140034bf0  movzx   edx, dx
0x140034bf3  mov     ecx, 102h
0x140034bf8  mov     r8d, 5052664Eh
0x140034bfe  lea     rdx, ds:4Ah[rdx*2]
0x140034c06  call    cs:__imp_ExAllocatePool2
0x140034c0d  nop     dword ptr [rax+rax+00h]
0x140034c12  mov     rsi, rax
0x140034c15  test    rax, rax
0x140034c18  jz      loc_140034D12
0x140034c1e  lea     rbx, [rax+3Fh]
0x140034c22  xor     r8d, r8d; AllocateDestinationString
0x140034c25  movzx   eax, word ptr [rbp+P]
0x140034c29  lea     rdx, [rbp+P]; SourceString
0x140034c2d  add     ax, ax
0x140034c30  and     rbx, 0FFFFFFFFFFFFFFF8h
0x140034c34  mov     rcx, rbx; DestinationString
0x140034c37  mov     [rbx], ax
0x140034c3a  movzx   eax, word ptr [rbp+P]
0x140034c3e  inc     ax
0x140034c41  add     ax, ax
0x140034c44  mov     [rbx+2], ax
0x140034c48  lea     rax, [rbx+17h]
0x140034c4c  and     rax, 0FFFFFFFFFFFFFFF8h
0x140034c50  mov     [rbx+8], rax
0x140034c54  call    cs:__imp_RtlAnsiStringToUnicodeString
0x140034c5b  nop     dword ptr [rax+rax+00h]
0x140034c60  mov     rcx, [rbp+P+8]; P
0x140034c64  test    rcx, rcx
0x140034c67  jz      short loc_140034C84
0x140034c69  test    r14b, r14b
0x140034c6c  jz      short loc_140034C7C
0x140034c6e  xor     edx, edx; Tag
0x140034c70  call    cs:__imp_ExFreePoolWithTag
0x140034c77  nop     dword ptr [rax+rax+00h]
0x140034c7c  mov     [rbp+P+8], 0
0x140034c84  movzx   eax, word ptr [rbx]
0x140034c87  xor     ecx, ecx
0x140034c89  test    eax, 0FFFFFFFEh
0x140034c8e  jbe     short loc_140034CBA
0x140034c90  lea     r8d, [rcx+2Fh]
0x140034c94  mov     rdx, [rbx+8]
0x140034c98  cmp     r8w, [rdx+rcx*2]
0x140034c9d  jnz     short loc_140034CAB
0x140034c9f  mov     word ptr [rdx+rcx*2], 5Ch ; '\'
0x140034ca5  mov     r8d, 2Fh ; '/'
0x140034cab  movzx   eax, word ptr [rbx]
0x140034cae  inc     ecx
0x140034cb0  shr     eax, 1
0x140034cb2  cmp     ecx, eax
0x140034cb4  jb      short loc_140034C94
0x140034cb6  mov     r15, [rbp+arg_18]
0x140034cba  mov     r8, rsi; PrefixTableEntry
0x140034cbd  mov     rdx, rbx; Prefix
0x140034cc0  mov     rcx, rdi; PrefixTable
0x140034cc3  call    cs:__imp_RtlInsertUnicodePrefix
0x140034cca  nop     dword ptr [rax+rax+00h]
0x140034ccf  xor     ebx, ebx
0x140034cd1  jmp     loc_140034B70
0x140034cd6  mov     rcx, cs:WPP_GLOBAL_Control
0x140034cdd  lea     rax, WPP_GLOBAL_Control
0x140034ce4  cmp     rcx, rax
0x140034ce7  jz      loc_140034B70
0x140034ced  mov     eax, [rcx+2Ch]
0x140034cf0  test    al, 2
0x140034cf2  jz      loc_140034B70
0x140034cf8  mov     rcx, [rcx+18h]
0x140034cfc  lea     r8, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids
0x140034d03  mov     edx, 0Ah
0x140034d08  call    WPP_SF_
0x140034d0d  jmp     loc_140034B70
0x140034d12  mov     rcx, [rbp+arg_10]
0x140034d16  call    cs:__imp_OncRpcDestroy
0x140034d1d  nop     dword ptr [rax+rax+00h]
0x140034d22  jmp     loc_140034B41
0x140034d27  cmp     eax, 80000006h
0x140034d2c  jnz     loc_140034B46
0x140034d32  mov     rcx, [r15+0D8h]; FastMutex
0x140034d39  call    cs:__imp_ExAcquireFastMutex
0x140034d40  nop     dword ptr [rax+rax+00h]
0x140034d45  mov     rbx, [r15+0E8h]
0x140034d4c  mov     [r15+0E8h], rdi
0x140034d53  mov     rax, ds:0FFFFF78000000014h
0x140034d5d  mov     rcx, [r15+0D8h]; FastMutex
0x140034d64  mov     [r15+0E0h], rax
0x140034d6b  call    cs:__imp_ExReleaseFastMutex
0x140034d72  nop     dword ptr [rax+rax+00h]
0x140034d77  xor     esi, esi
0x140034d79  jmp     loc_140034B49
0x140034d7e  mov     rdx, rdi; PrefixTableEntry
0x140034d81  call    cs:__imp_RtlRemoveUnicodePrefix
0x140034d88  nop     dword ptr [rax+rax+00h]
0x140034d8d  xor     edx, edx; Tag
0x140034d8f  mov     rcx, rdi; P
0x140034d92  call    cs:__imp_ExFreePoolWithTag
0x140034d99  nop     dword ptr [rax+rax+00h]
0x140034d9e  mov     dl, r15b
0x140034da1  mov     rcx, rbx
0x140034da4  call    MdaTryNextUnicodePrefix
0x140034da9  mov     rdi, rax
0x140034dac  mov     rcx, rbx; P
0x140034daf  test    rax, rax
0x140034db2  jnz     short loc_140034D7E
0x140034db4  xor     edx, edx; Tag
0x140034db6  call    cs:__imp_ExFreePoolWithTag
0x140034dbd  nop     dword ptr [rax+rax+00h]
0x140034dc2  mov     rcx, [rbp+P+8]; P
0x140034dc6  test    rcx, rcx
0x140034dc9  jz      short loc_140034DE6
0x140034dcb  test    r14b, r14b
0x140034dce  jz      short loc_140034DDE
0x140034dd0  xor     edx, edx; Tag
0x140034dd2  call    cs:__imp_ExFreePoolWithTag
0x140034dd9  nop     dword ptr [rax+rax+00h]
0x140034dde  mov     [rbp+P+8], 0
0x140034de6  mov     rcx, cs:WPP_GLOBAL_Control
0x140034ded  lea     rax, WPP_GLOBAL_Control
0x140034df4  cmp     rcx, rax
0x140034df7  jz      short loc_140034E19
0x140034df9  mov     edx, [rcx+2Ch]
0x140034dfc  test    dl, 8
0x140034dff  jz      short loc_140034E19
0x140034e01  mov     rcx, [rcx+18h]
0x140034e05  lea     r8, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids
0x140034e0c  mov     edx, 0Bh
0x140034e11  mov     r9d, esi
0x140034e14  call    WPP_SF_d
0x140034e19  mov     rbx, [rsp+40h+arg_0]
0x140034e21  mov     eax, esi
0x140034e23  add     rsp, 40h
0x140034e27  pop     r15
0x140034e29  pop     r14
0x140034e2b  pop     r13
0x140034e2d  pop     r12
0x140034e2f  pop     rdi
0x140034e30  pop     rsi
0x140034e31  pop     rbp
0x140034e32  retn
```
