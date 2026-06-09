# LdrpMinimalMapModule

- ea: `0x18007c7d4`
- end: `0x18007cb68`
- name: `LdrpMinimalMapModule`
- size: `916`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180029b2c`

## callees

- `0x18001eb80`
- `0x180029254`
- `0x18007b1a0`
- `0x18007c7d4`
- `0x18007cf60`
- `0x18007d9a8`
- `0x18007da70`
- `0x1800d4620`
- `0x18015efe0`
- `0x18015f020`
- `0x180160e90`

## string_xrefs

- `0x18007c7f3`: `DLL name: %wZ\n`

## pseudocode

```c
__int64 __fastcall LdrpMinimalMapModule(__int64 a1, __int64 a2)
{
  _QWORD *v2; // rdi
  __int64 v4; // r8
  bool v5; // r14
  void *v6; // r12
  int v7; // ebx
  struct _TEB *v8; // rcx
  int v9; // r8d
  int v10; // r13d
  int v11; // edx
  unsigned int v12; // ecx
  bool v13; // zf
  __int64 v14; // rax
  _QWORD *v15; // r8
  int v16; // eax
  __int64 v17; // rdx
  int ArgList; // ebx
  __int64 v20; // rdx
  int v21; // eax
  __int128 v22; // [rsp+50h] [rbp-19h] BYREF
  __int64 v23; // [rsp+60h] [rbp-9h]
  _OWORD v24[5]; // [rsp+68h] [rbp-1h] BYREF
  struct _TEB *v25; // [rsp+D0h] [rbp+67h] BYREF
  __int64 v26; // [rsp+D8h] [rbp+6Fh]
  void *ArbitraryUserPointer; // [rsp+E0h] [rbp+77h] BYREF

  v26 = a2;
  v2 = *(_QWORD **)(a1 + 56);
  LdrpLogInternal(
    (int)"minkernel\\ldr\\ldrmap.c",
    770,
    (int)"LdrpMinimalMapModule",
    3,
    "DLL name: %wZ\n",
    (_BYTE)v2 + 72);
  LdrpLogInternal((int)"minkernel\\ldr\\ldrmap.c", 771, (int)"LdrpMinimalMapModule", 5, "%wZ\n", (_BYTE)v2 + 72);
  LOBYTE(v4) = 1;
  v5 = (unsigned __int8)RtlEqualUnicodeString(v2 + 11, &LdrpKernel32DllName, v4)
    && (*(_BYTE *)(LdrpAppHeaders + 22) & 0x20) != 0;
  v6 = 0;
  ArbitraryUserPointer = 0;
  v7 = 0x800000;
  if ( !v5 )
  {
    if ( LdrpLargePageDllKeyHandle )
    {
      v20 = v2[12];
      LODWORD(v25) = 0;
      RtlQueryImageFileKeyOption(LdrpLargePageDllKeyHandle, v20, 4, &v25, 4, 0);
      if ( (_DWORD)v25 )
      {
        v21 = RtlAcquirePrivilege(&LdrpLockMemoryPrivilege, 1, 0, &ArbitraryUserPointer);
        v6 = ArbitraryUserPointer;
        if ( v21 >= 0 )
          v7 = 0x20000000;
      }
    }
  }
  v8 = NtCurrentTeb();
  *(_QWORD *)(a1 + 168) = 0;
  v25 = v8;
  ArbitraryUserPointer = v8->NtTib.ArbitraryUserPointer;
  v8->NtTib.ArbitraryUserPointer = (void *)v2[10];
  v9 = *(_DWORD *)(a1 + 32) & 0x800000;
  memset(v24, 0, 32);
  v10 = v7 | 0x40000;
  v11 = v9 != 0 ? 2 : 128;
  if ( !v9 )
    v10 = v7;
  v12 = 0;
  v13 = (*(_DWORD *)(a1 + 32) & 0x800) == 0;
  v22 = 0;
  v23 = 0;
  if ( !v13 )
  {
    v12 = 1;
    *((_QWORD *)&v22 + 1) = LdrpMaximumUserModeAddress;
    *((_QWORD *)&v24[0] + 1) = &v22;
    LOBYTE(v24[0]) = 1;
  }
  if ( v9 )
  {
    v14 = v12++;
    LOBYTE(v24[v14]) = 5;
    *((_QWORD *)&v24[v14] + 1) = 512;
  }
  v15 = v2 + 6;
  if ( v12 )
    v16 = ZwMapViewOfSectionEx(v26, -1, v15, 0, a1 + 168, v10, v11, v24, v12);
  else
    v16 = ZwMapViewOfSection(v26, -1, v15, 0, 0, 0, a1 + 168, 1, v10, v11);
  ArgList = v16;
  v25->NtTib.ArbitraryUserPointer = ArbitraryUserPointer;
  if ( v10 == 0x20000000 )
    RtlReleasePrivilege(v6);
  switch ( ArgList )
  {
    case 1073741827:
      goto LABEL_40;
    case 1073741838:
      ArgList = LdrpProcessMachineMismatch(a1);
      break;
    case 1073741878:
LABEL_40:
      if ( LdrpMapAndSnapWork && !*(_QWORD *)(a1 + 176) )
      {
        LOBYTE(v17) = 1;
        if ( (unsigned __int8)LdrpCheckForRetryLoading(a1, v17) )
        {
          ArgList = -1073741267;
        }
        else if ( v5 )
        {
          ArgList = -1073741800;
        }
      }
      break;
  }
  if ( v2[6] && (ArgList < 0 || ArgList == 1073741838) )
  {
    NtUnmapViewOfSection(-1);
    v2[6] = 0;
  }
  LdrpLogInternal((int)"minkernel\\ldr\\ldrmap.c", 1003, (int)"LdrpMinimalMapModule", 4, "Status: 0x%08lx\n", ArgList);
  LdrpLogInternal((int)"minkernel\\ldr\\ldrmap.c", 1004, (int)"LdrpMinimalMapModule", 6, "%x\n", ArgList);
  return (unsigned int)ArgList;
}

```

## disassembly

```asm
0x18007c7d4  mov     [rsp-8+arg_8], rdx
0x18007c7d9  push    rbp
0x18007c7da  push    rbx
0x18007c7db  push    rsi
0x18007c7dc  push    rdi
0x18007c7dd  push    r12
0x18007c7df  push    r13
0x18007c7e1  push    r14
0x18007c7e3  lea     rbp, [rsp-27h]
0x18007c7e8  sub     rsp, 90h
0x18007c7ef  mov     rdi, [rcx+38h]
0x18007c7f3  lea     rax, aDllNameWz; "DLL name: %wZ\n"
0x18007c7fa  mov     rsi, rcx
0x18007c7fd  lea     r8, aLdrpminimalmap; "LdrpMinimalMapModule"
0x18007c804  mov     r9d, 3; int
0x18007c80a  lea     rcx, aMinkernelLdrLd_0; "minkernel\\ldr\\ldrmap.c"
0x18007c811  mov     edx, 302h; int
0x18007c816  lea     rbx, [rdi+48h]
0x18007c81a  mov     qword ptr [rsp+0C0h+ArgList], rbx; ArgList
0x18007c81f  mov     [rsp+0C0h+Format], rax; Format
0x18007c824  call    LdrpLogInternal
0x18007c829  lea     rax, aWz_0; "%wZ\n"
0x18007c830  mov     qword ptr [rsp+0C0h+ArgList], rbx; ArgList
0x18007c835  mov     r9d, 5; int
0x18007c83b  mov     [rsp+0C0h+Format], rax; Format
0x18007c840  lea     r8, aLdrpminimalmap; "LdrpMinimalMapModule"
0x18007c847  mov     edx, 303h; int
0x18007c84c  lea     rcx, aMinkernelLdrLd_0; "minkernel\\ldr\\ldrmap.c"
0x18007c853  call    LdrpLogInternal
0x18007c858  lea     rcx, [rdi+58h]
0x18007c85c  mov     r8b, 1
0x18007c85f  lea     rdx, LdrpKernel32DllName
0x18007c866  call    RtlEqualUnicodeString
0x18007c86b  test    al, al
0x18007c86d  jnz     loc_18007CB36
0x18007c873  xor     r14b, r14b
0x18007c876  xor     r12d, r12d
0x18007c879  mov     r13d, 800000h
0x18007c87f  mov     [rbp+57h+arg_10], r12
0x18007c883  mov     ebx, r13d
0x18007c886  lea     eax, [r12+4]
0x18007c88b  test    r14b, r14b
0x18007c88e  jz      loc_18007CA38
0x18007c894  mov     rcx, gs:30h
0x18007c89d  lea     r9, [rsi+0A8h]
0x18007c8a4  mov     qword ptr [r9], 0
0x18007c8ab  xorps   xmm0, xmm0
0x18007c8ae  mov     [rbp+57h+arg_0], rcx
0x18007c8b2  xorps   xmm1, xmm1
0x18007c8b5  mov     rax, [rcx+28h]
0x18007c8b9  mov     [rbp+57h+arg_10], rax
0x18007c8bd  mov     rax, [rdi+50h]
0x18007c8c1  mov     [rcx+28h], rax
0x18007c8c5  mov     r8d, [rsi+20h]
0x18007c8c9  and     r8d, r13d
0x18007c8cc  mov     r13d, ebx
0x18007c8cf  mov     eax, r8d
0x18007c8d2  neg     eax
0x18007c8d4  movups  [rbp+57h+var_58], xmm0
0x18007c8d8  sbb     edx, edx
0x18007c8da  bts     r13d, 12h
0x18007c8df  and     edx, 0FFFFFF82h
0x18007c8e2  sub     edx, 0FFFFFF80h
0x18007c8e5  test    r8d, r8d
0x18007c8e8  movups  [rbp+57h+var_48], xmm0
0x18007c8ec  cmovz   r13d, ebx
0x18007c8f0  xor     ecx, ecx
0x18007c8f2  xor     eax, eax
0x18007c8f4  test    dword ptr [rsi+20h], 800h
0x18007c8fb  movups  [rbp+57h+var_70], xmm1
0x18007c8ff  mov     [rbp+57h+var_60], rax
0x18007c903  jz      short loc_18007C921
0x18007c905  mov     rax, cs:LdrpMaximumUserModeAddress
0x18007c90c  mov     ecx, 1
0x18007c911  mov     qword ptr [rbp+57h+var_70+8], rax
0x18007c915  lea     rax, [rbp+57h+var_70]
0x18007c919  mov     qword ptr [rbp+57h+var_58+8], rax
0x18007c91d  mov     byte ptr [rbp+57h+var_58], 1
0x18007c921  test    r8d, r8d
0x18007c924  jz      short loc_18007C93B
0x18007c926  mov     eax, ecx
0x18007c928  add     rax, rax
0x18007c92b  inc     ecx
0x18007c92d  mov     byte ptr [rbp+rax*8+57h+var_58], 5
0x18007c932  mov     qword ptr [rbp+rax*8+57h+var_58+8], 200h
0x18007c93b  lea     r8, [rdi+30h]
0x18007c93f  test    ecx, ecx
0x18007c941  jnz     loc_18007CA99
0x18007c947  mov     rcx, [rbp+57h+arg_8]
0x18007c94b  mov     [rsp+0C0h+var_78], edx
0x18007c94f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18007c953  mov     [rsp+0C0h+var_80], r13d
0x18007c958  mov     dword ptr [rsp+0C0h+var_88], 1
0x18007c960  mov     [rsp+0C0h+var_90], r9
0x18007c965  xor     r9d, r9d
0x18007c968  mov     qword ptr [rsp+0C0h+ArgList], 0
0x18007c971  mov     [rsp+0C0h+Format], 0
0x18007c97a  call    ZwMapViewOfSection
0x18007c97f  mov     rcx, [rbp+57h+arg_10]
0x18007c983  mov     ebx, eax
0x18007c985  mov     rax, [rbp+57h+arg_0]
0x18007c989  mov     [rax+28h], rcx
0x18007c98d  cmp     r13d, 20000000h
0x18007c994  jz      loc_18007CAC9
0x18007c99a  mov     ecx, ebx
0x18007c99c  sub     ecx, 40000003h
0x18007c9a2  jz      loc_18007CAFC
0x18007c9a8  sub     ecx, 0Bh
0x18007c9ab  jz      loc_18007CB4F
0x18007c9b1  cmp     ecx, 28h ; '('
0x18007c9b4  jz      loc_18007CAFC
0x18007c9ba  mov     rdx, [rdi+30h]
0x18007c9be  test    rdx, rdx
0x18007c9c1  jnz     loc_18007CAD6
0x18007c9c7  lea     rax, aStatus0x08lx; "Status: 0x%08lx\n"
0x18007c9ce  mov     dword ptr [rsp+0C0h+ArgList], ebx; ArgList
0x18007c9d2  mov     r9d, 4; int
0x18007c9d8  mov     [rsp+0C0h+Format], rax; Format
0x18007c9dd  lea     r8, aLdrpminimalmap; "LdrpMinimalMapModule"
0x18007c9e4  mov     edx, 3EBh; int
0x18007c9e9  lea     rcx, aMinkernelLdrLd_0; "minkernel\\ldr\\ldrmap.c"
0x18007c9f0  call    LdrpLogInternal
0x18007c9f5  lea     rax, asc_180175AB4; "%x\n"
0x18007c9fc  mov     dword ptr [rsp+0C0h+ArgList], ebx; ArgList
0x18007ca00  mov     r9d, 6; int
0x18007ca06  mov     [rsp+0C0h+Format], rax; Format
0x18007ca0b  lea     r8, aLdrpminimalmap; "LdrpMinimalMapModule"
0x18007ca12  mov     edx, 3ECh; int
0x18007ca17  lea     rcx, aMinkernelLdrLd_0; "minkernel\\ldr\\ldrmap.c"
0x18007ca1e  call    LdrpLogInternal
0x18007ca23  mov     eax, ebx
0x18007ca25  add     rsp, 90h
0x18007ca2c  pop     r14
0x18007ca2e  pop     r13
0x18007ca30  pop     r12
0x18007ca32  pop     rdi
0x18007ca33  pop     rsi
0x18007ca34  pop     rbx
0x18007ca35  pop     rbp
0x18007ca36  retn
0x18007ca38  mov     rcx, cs:LdrpLargePageDllKeyHandle
0x18007ca3f  test    rcx, rcx
0x18007ca42  jz      loc_18007C894
0x18007ca48  mov     rdx, [rdi+60h]
0x18007ca4c  lea     r9, [rbp+57h+arg_0]
0x18007ca50  mov     qword ptr [rsp+0C0h+ArgList], r12
0x18007ca55  mov     r8d, eax
0x18007ca58  mov     dword ptr [rsp+0C0h+Format], eax
0x18007ca5c  mov     dword ptr [rbp+57h+arg_0], r12d
0x18007ca60  call    RtlQueryImageFileKeyOption
0x18007ca65  cmp     dword ptr [rbp+57h+arg_0], r12d
0x18007ca69  jz      loc_18007C894
0x18007ca6f  xor     r8d, r8d
0x18007ca72  lea     r9, [rbp+57h+arg_10]
0x18007ca76  lea     rcx, LdrpLockMemoryPrivilege
0x18007ca7d  lea     edx, [r8+1]
0x18007ca81  call    RtlAcquirePrivilege
0x18007ca86  mov     r12, [rbp+57h+arg_10]
0x18007ca8a  test    eax, eax
0x18007ca8c  mov     eax, 20000000h
0x18007ca91  cmovns  ebx, eax
0x18007ca94  jmp     loc_18007C894
0x18007ca99  mov     [rsp+0C0h+var_80], ecx
0x18007ca9d  lea     rax, [rbp+57h+var_58]
0x18007caa1  mov     rcx, [rbp+57h+arg_8]
0x18007caa5  mov     [rsp+0C0h+var_88], rax
0x18007caaa  mov     dword ptr [rsp+0C0h+var_90], edx
0x18007caae  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18007cab2  mov     dword ptr [rsp+0C0h+ArgList], r13d
0x18007cab7  mov     [rsp+0C0h+Format], r9
0x18007cabc  xor     r9d, r9d
0x18007cabf  call    ZwMapViewOfSectionEx
0x18007cac4  jmp     loc_18007C97F
0x18007cac9  mov     rcx, r12
0x18007cacc  call    RtlReleasePrivilege
0x18007cad1  jmp     loc_18007C99A
0x18007cad6  test    ebx, ebx
0x18007cad8  js      short loc_18007CAE6
0x18007cada  cmp     ebx, 4000000Eh
0x18007cae0  jnz     loc_18007C9C7
0x18007cae6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18007caea  call    NtUnmapViewOfSection
0x18007caef  mov     qword ptr [rdi+30h], 0
0x18007caf7  jmp     loc_18007C9C7
0x18007cafc  cmp     cs:LdrpMapAndSnapWork, 0
0x18007cb04  jz      loc_18007C9BA
0x18007cb0a  cmp     qword ptr [rsi+0B0h], 0
0x18007cb12  jnz     loc_18007C9BA
0x18007cb18  mov     dl, 1
0x18007cb1a  mov     rcx, rsi
0x18007cb1d  call    LdrpCheckForRetryLoading
0x18007cb22  test    al, al
0x18007cb24  jnz     short loc_18007CB5E
0x18007cb26  test    r14b, r14b
0x18007cb29  mov     eax, 0C0000018h
0x18007cb2e  cmovnz  ebx, eax
0x18007cb31  jmp     loc_18007C9BA
0x18007cb36  mov     rax, cs:LdrpAppHeaders
0x18007cb3d  test    byte ptr [rax+16h], 20h
0x18007cb41  jz      loc_18007C873
0x18007cb47  mov     r14b, 1
0x18007cb4a  jmp     loc_18007C876
0x18007cb4f  mov     rcx, rsi
0x18007cb52  call    LdrpProcessMachineMismatch
0x18007cb57  mov     ebx, eax
0x18007cb59  jmp     loc_18007C9BA
0x18007cb5e  mov     ebx, 0C000022Dh
0x18007cb63  jmp     loc_18007C9BA
```
