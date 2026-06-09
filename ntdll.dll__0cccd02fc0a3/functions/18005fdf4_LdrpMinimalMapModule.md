# LdrpMinimalMapModule

- ea: `0x18005fdf4`
- end: `0x180060188`
- name: `LdrpMinimalMapModule`
- size: `916`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180029c3c`

## callees

- `0x18001eb80`
- `0x180029364`
- `0x18005e7c0`
- `0x18005fdf4`
- `0x180060580`
- `0x180060fc8`
- `0x180061090`
- `0x1800733c0`
- `0x18015e7d0`
- `0x18015e810`
- `0x180160680`

## string_xrefs

- `0x18005fe13`: `DLL name: %wZ\n`

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
0x18005fdf4  mov     [rsp-8+arg_8], rdx
0x18005fdf9  push    rbp
0x18005fdfa  push    rbx
0x18005fdfb  push    rsi
0x18005fdfc  push    rdi
0x18005fdfd  push    r12
0x18005fdff  push    r13
0x18005fe01  push    r14
0x18005fe03  lea     rbp, [rsp-27h]
0x18005fe08  sub     rsp, 90h
0x18005fe0f  mov     rdi, [rcx+38h]
0x18005fe13  lea     rax, aDllNameWz; "DLL name: %wZ\n"
0x18005fe1a  mov     rsi, rcx
0x18005fe1d  lea     r8, aLdrpminimalmap; "LdrpMinimalMapModule"
0x18005fe24  mov     r9d, 3; int
0x18005fe2a  lea     rcx, aMinkernelLdrLd_0; "minkernel\\ldr\\ldrmap.c"
0x18005fe31  mov     edx, 302h; int
0x18005fe36  lea     rbx, [rdi+48h]
0x18005fe3a  mov     qword ptr [rsp+0C0h+ArgList], rbx; ArgList
0x18005fe3f  mov     [rsp+0C0h+Format], rax; Format
0x18005fe44  call    LdrpLogInternal
0x18005fe49  lea     rax, aWz_0; "%wZ\n"
0x18005fe50  mov     qword ptr [rsp+0C0h+ArgList], rbx; ArgList
0x18005fe55  mov     r9d, 5; int
0x18005fe5b  mov     [rsp+0C0h+Format], rax; Format
0x18005fe60  lea     r8, aLdrpminimalmap; "LdrpMinimalMapModule"
0x18005fe67  mov     edx, 303h; int
0x18005fe6c  lea     rcx, aMinkernelLdrLd_0; "minkernel\\ldr\\ldrmap.c"
0x18005fe73  call    LdrpLogInternal
0x18005fe78  lea     rcx, [rdi+58h]
0x18005fe7c  mov     r8b, 1
0x18005fe7f  lea     rdx, LdrpKernel32DllName
0x18005fe86  call    RtlEqualUnicodeString
0x18005fe8b  test    al, al
0x18005fe8d  jnz     loc_180060156
0x18005fe93  xor     r14b, r14b
0x18005fe96  xor     r12d, r12d
0x18005fe99  mov     r13d, 800000h
0x18005fe9f  mov     [rbp+57h+arg_10], r12
0x18005fea3  mov     ebx, r13d
0x18005fea6  lea     eax, [r12+4]
0x18005feab  test    r14b, r14b
0x18005feae  jz      loc_180060058
0x18005feb4  mov     rcx, gs:30h
0x18005febd  lea     r9, [rsi+0A8h]
0x18005fec4  mov     qword ptr [r9], 0
0x18005fecb  xorps   xmm0, xmm0
0x18005fece  mov     [rbp+57h+arg_0], rcx
0x18005fed2  xorps   xmm1, xmm1
0x18005fed5  mov     rax, [rcx+28h]
0x18005fed9  mov     [rbp+57h+arg_10], rax
0x18005fedd  mov     rax, [rdi+50h]
0x18005fee1  mov     [rcx+28h], rax
0x18005fee5  mov     r8d, [rsi+20h]
0x18005fee9  and     r8d, r13d
0x18005feec  mov     r13d, ebx
0x18005feef  mov     eax, r8d
0x18005fef2  neg     eax
0x18005fef4  movups  [rbp+57h+var_58], xmm0
0x18005fef8  sbb     edx, edx
0x18005fefa  bts     r13d, 12h
0x18005feff  and     edx, 0FFFFFF82h
0x18005ff02  sub     edx, 0FFFFFF80h
0x18005ff05  test    r8d, r8d
0x18005ff08  movups  [rbp+57h+var_48], xmm0
0x18005ff0c  cmovz   r13d, ebx
0x18005ff10  xor     ecx, ecx
0x18005ff12  xor     eax, eax
0x18005ff14  test    dword ptr [rsi+20h], 800h
0x18005ff1b  movups  [rbp+57h+var_70], xmm1
0x18005ff1f  mov     [rbp+57h+var_60], rax
0x18005ff23  jz      short loc_18005FF41
0x18005ff25  mov     rax, cs:LdrpMaximumUserModeAddress
0x18005ff2c  mov     ecx, 1
0x18005ff31  mov     qword ptr [rbp+57h+var_70+8], rax
0x18005ff35  lea     rax, [rbp+57h+var_70]
0x18005ff39  mov     qword ptr [rbp+57h+var_58+8], rax
0x18005ff3d  mov     byte ptr [rbp+57h+var_58], 1
0x18005ff41  test    r8d, r8d
0x18005ff44  jz      short loc_18005FF5B
0x18005ff46  mov     eax, ecx
0x18005ff48  add     rax, rax
0x18005ff4b  inc     ecx
0x18005ff4d  mov     byte ptr [rbp+rax*8+57h+var_58], 5
0x18005ff52  mov     qword ptr [rbp+rax*8+57h+var_58+8], 200h
0x18005ff5b  lea     r8, [rdi+30h]
0x18005ff5f  test    ecx, ecx
0x18005ff61  jnz     loc_1800600B9
0x18005ff67  mov     rcx, [rbp+57h+arg_8]
0x18005ff6b  mov     [rsp+0C0h+var_78], edx
0x18005ff6f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18005ff73  mov     [rsp+0C0h+var_80], r13d
0x18005ff78  mov     dword ptr [rsp+0C0h+var_88], 1
0x18005ff80  mov     [rsp+0C0h+var_90], r9
0x18005ff85  xor     r9d, r9d
0x18005ff88  mov     qword ptr [rsp+0C0h+ArgList], 0
0x18005ff91  mov     [rsp+0C0h+Format], 0
0x18005ff9a  call    ZwMapViewOfSection
0x18005ff9f  mov     rcx, [rbp+57h+arg_10]
0x18005ffa3  mov     ebx, eax
0x18005ffa5  mov     rax, [rbp+57h+arg_0]
0x18005ffa9  mov     [rax+28h], rcx
0x18005ffad  cmp     r13d, 20000000h
0x18005ffb4  jz      loc_1800600E9
0x18005ffba  mov     ecx, ebx
0x18005ffbc  sub     ecx, 40000003h
0x18005ffc2  jz      loc_18006011C
0x18005ffc8  sub     ecx, 0Bh
0x18005ffcb  jz      loc_18006016F
0x18005ffd1  cmp     ecx, 28h ; '('
0x18005ffd4  jz      loc_18006011C
0x18005ffda  mov     rdx, [rdi+30h]
0x18005ffde  test    rdx, rdx
0x18005ffe1  jnz     loc_1800600F6
0x18005ffe7  lea     rax, aStatus0x08lx; "Status: 0x%08lx\n"
0x18005ffee  mov     dword ptr [rsp+0C0h+ArgList], ebx; ArgList
0x18005fff2  mov     r9d, 4; int
0x18005fff8  mov     [rsp+0C0h+Format], rax; Format
0x18005fffd  lea     r8, aLdrpminimalmap; "LdrpMinimalMapModule"
0x180060004  mov     edx, 3EBh; int
0x180060009  lea     rcx, aMinkernelLdrLd_0; "minkernel\\ldr\\ldrmap.c"
0x180060010  call    LdrpLogInternal
0x180060015  lea     rax, asc_180175AB4; "%x\n"
0x18006001c  mov     dword ptr [rsp+0C0h+ArgList], ebx; ArgList
0x180060020  mov     r9d, 6; int
0x180060026  mov     [rsp+0C0h+Format], rax; Format
0x18006002b  lea     r8, aLdrpminimalmap; "LdrpMinimalMapModule"
0x180060032  mov     edx, 3ECh; int
0x180060037  lea     rcx, aMinkernelLdrLd_0; "minkernel\\ldr\\ldrmap.c"
0x18006003e  call    LdrpLogInternal
0x180060043  mov     eax, ebx
0x180060045  add     rsp, 90h
0x18006004c  pop     r14
0x18006004e  pop     r13
0x180060050  pop     r12
0x180060052  pop     rdi
0x180060053  pop     rsi
0x180060054  pop     rbx
0x180060055  pop     rbp
0x180060056  retn
0x180060058  mov     rcx, cs:LdrpLargePageDllKeyHandle
0x18006005f  test    rcx, rcx
0x180060062  jz      loc_18005FEB4
0x180060068  mov     rdx, [rdi+60h]
0x18006006c  lea     r9, [rbp+57h+arg_0]
0x180060070  mov     qword ptr [rsp+0C0h+ArgList], r12
0x180060075  mov     r8d, eax
0x180060078  mov     dword ptr [rsp+0C0h+Format], eax
0x18006007c  mov     dword ptr [rbp+57h+arg_0], r12d
0x180060080  call    RtlQueryImageFileKeyOption
0x180060085  cmp     dword ptr [rbp+57h+arg_0], r12d
0x180060089  jz      loc_18005FEB4
0x18006008f  xor     r8d, r8d
0x180060092  lea     r9, [rbp+57h+arg_10]
0x180060096  lea     rcx, LdrpLockMemoryPrivilege
0x18006009d  lea     edx, [r8+1]
0x1800600a1  call    RtlAcquirePrivilege
0x1800600a6  mov     r12, [rbp+57h+arg_10]
0x1800600aa  test    eax, eax
0x1800600ac  mov     eax, 20000000h
0x1800600b1  cmovns  ebx, eax
0x1800600b4  jmp     loc_18005FEB4
0x1800600b9  mov     [rsp+0C0h+var_80], ecx
0x1800600bd  lea     rax, [rbp+57h+var_58]
0x1800600c1  mov     rcx, [rbp+57h+arg_8]
0x1800600c5  mov     [rsp+0C0h+var_88], rax
0x1800600ca  mov     dword ptr [rsp+0C0h+var_90], edx
0x1800600ce  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800600d2  mov     dword ptr [rsp+0C0h+ArgList], r13d
0x1800600d7  mov     [rsp+0C0h+Format], r9
0x1800600dc  xor     r9d, r9d
0x1800600df  call    ZwMapViewOfSectionEx
0x1800600e4  jmp     loc_18005FF9F
0x1800600e9  mov     rcx, r12
0x1800600ec  call    RtlReleasePrivilege
0x1800600f1  jmp     loc_18005FFBA
0x1800600f6  test    ebx, ebx
0x1800600f8  js      short loc_180060106
0x1800600fa  cmp     ebx, 4000000Eh
0x180060100  jnz     loc_18005FFE7
0x180060106  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18006010a  call    NtUnmapViewOfSection
0x18006010f  mov     qword ptr [rdi+30h], 0
0x180060117  jmp     loc_18005FFE7
0x18006011c  cmp     cs:LdrpMapAndSnapWork, 0
0x180060124  jz      loc_18005FFDA
0x18006012a  cmp     qword ptr [rsi+0B0h], 0
0x180060132  jnz     loc_18005FFDA
0x180060138  mov     dl, 1
0x18006013a  mov     rcx, rsi
0x18006013d  call    LdrpCheckForRetryLoading
0x180060142  test    al, al
0x180060144  jnz     short loc_18006017E
0x180060146  test    r14b, r14b
0x180060149  mov     eax, 0C0000018h
0x18006014e  cmovnz  ebx, eax
0x180060151  jmp     loc_18005FFDA
0x180060156  mov     rax, cs:LdrpAppHeaders
0x18006015d  test    byte ptr [rax+16h], 20h
0x180060161  jz      loc_18005FE93
0x180060167  mov     r14b, 1
0x18006016a  jmp     loc_18005FE96
0x18006016f  mov     rcx, rsi
0x180060172  call    LdrpProcessMachineMismatch
0x180060177  mov     ebx, eax
0x180060179  jmp     loc_18005FFDA
0x18006017e  mov     ebx, 0C000022Dh
0x180060183  jmp     loc_18005FFDA
```
