# LdrpInitializeNtdllDataTableEntry

- ea: `0x1800be058`
- end: `0x1800be2d8`
- name: `LdrpInitializeNtdllDataTableEntry`
- size: `640`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x1800d6508`

## callees

- `0x18001eb80`
- `0x18001f070`
- `0x180029b70`
- `0x18002ad90`
- `0x180051314`
- `0x1800693a8`
- `0x1800be058`
- `0x1800bf2ac`
- `0x1800bf4c8`
- `0x1800bf68c`
- `0x1800fcd28`
- `0x18010349c`
- `0x18015e730`
- `0x180162000`
- `0x18016f030`

## string_xrefs

- `0x1800be281`: `LdrpInitializeNtdllDataTableEntry`
- `0x1800be277`: `Allocating a data table entry for the system DLL failed\n`

## pseudocode

```c
__int64 __fastcall LdrpInitializeNtdllDataTableEntry(__int64 a1, __int64 *a2, __int64 a3, _OWORD *a4)
{
  __int64 ModuleEntry; // rax
  __int64 v9; // rbx
  int v10; // edi
  __int64 v12; // rbp
  char v13; // [rsp+28h] [rbp-270h]
  __int64 v14; // [rsp+30h] [rbp-268h] BYREF
  __int64 v15; // [rsp+38h] [rbp-260h] BYREF
  _BYTE v16[16]; // [rsp+40h] [rbp-258h] BYREF
  char Src[528]; // [rsp+50h] [rbp-248h] BYREF

  v14 = 0;
  memset_thunk_772440563353939046(v16, 0, 0x218u);
  v15 = 0;
  RtlImageNtHeaderEx(3, a1, 0, &v14);
  ModuleEntry = LdrpAllocateModuleEntry(0);
  v9 = ModuleEntry;
  if ( !ModuleEntry )
  {
    LdrpLogInternal(
      (int)"minkernel\\ldr\\ldrinit.c",
      5287,
      (int)"LdrpInitializeNtdllDataTableEntry",
      0,
      "Allocating a data table entry for the system DLL failed\n",
      v13);
    return (unsigned int)-1073741801;
  }
  *(_DWORD *)(*(_QWORD *)(ModuleEntry + 152) + 24LL) = -1;
  *(_WORD *)(**(_QWORD **)(ModuleEntry + 152) - 52LL) = -1;
  *(_DWORD *)(ModuleEntry + 104) |= 0x204u;
  if ( !a3 )
    *(_QWORD *)(ModuleEntry + 248) -= qword_1801E3470;
  if ( a4 )
  {
    v12 = ModuleEntry + 72;
    *(_OWORD *)(ModuleEntry + 72) = *a4;
    RtlAppendUnicodeStringToString(ModuleEntry + 72, NtDllName);
    *(_OWORD *)(v9 + 88) = *(_OWORD *)NtDllName;
  }
  else
  {
    v10 = ZwQueryVirtualMemory(-1, *(_QWORD *)LdrpNtdllHotPatchContext, 2, v16, 536, &v15, v14);
    if ( v10 < 0 )
      goto LABEL_6;
    v12 = v9 + 72;
    v10 = LdrpResolvePatchDllName(Src);
    if ( v10 < 0 )
      goto LABEL_6;
  }
  *(_QWORD *)(v9 + 48) = a1;
  if ( a3 )
    *(_DWORD *)(v9 + 268) = 9;
  LdrpInsertDataTableEntry(v9);
  LdrpLogDllState(*(_QWORD *)(v9 + 48), v12, 5285);
  LdrpInsertModuleToIndex(v9, v14);
  LODWORD(v14) = LdrpProcessMappedModule(v9, 0, 1);
  v10 = v14;
  if ( (int)v14 >= 0 )
  {
    LdrpLogDllState(*(_QWORD *)(v9 + 48), v12, 5294);
    if ( a3 )
    {
      LdrpRecordModuleDependency(LdrpNtDllDataTableEntry, v9, 0, &v14);
      v10 = v14;
      if ( (int)v14 < 0 )
        goto LABEL_7;
      *(_QWORD *)(v9 + 184) = *(_QWORD *)(a3 + 48);
      *(_DWORD *)(a3 + 304) = 3;
      *(_QWORD *)(a3 + 296) = *(_QWORD *)(v9 + 48);
      *(_DWORD *)(v9 + 304) = 2;
    }
    *(_DWORD *)(*(_QWORD *)(v9 + 152) + 56LL) = 9;
    *a2 = v9;
  }
LABEL_6:
  if ( v10 < 0 )
LABEL_7:
    LdrpFreeUnicodeString(v9 + 72);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800be058  mov     [rsp+arg_18], rbx
0x1800be05d  push    rbp
0x1800be05e  push    rsi
0x1800be05f  push    rdi
0x1800be060  push    r14
0x1800be062  push    r15
0x1800be064  sub     rsp, 270h
0x1800be06b  mov     rax, cs:__security_cookie
0x1800be072  xor     rax, rsp
0x1800be075  mov     [rsp+298h+var_38], rax
0x1800be07d  mov     rsi, r8
0x1800be080  mov     [rsp+298h+var_268], 0
0x1800be089  mov     r15, rdx
0x1800be08c  mov     r14, rcx
0x1800be08f  mov     ebp, 218h
0x1800be094  lea     rcx, [rsp+298h+var_258]; void *
0x1800be099  mov     r8d, ebp; Size
0x1800be09c  xor     edx, edx; Val
0x1800be09e  mov     rdi, r9
0x1800be0a1  call    memset$thunk$772440563353939046
0x1800be0a6  xor     r8d, r8d
0x1800be0a9  mov     [rsp+298h+var_260], 0
0x1800be0b2  lea     r9, [rsp+298h+var_268]
0x1800be0b7  mov     rdx, r14
0x1800be0ba  lea     ecx, [r8+3]
0x1800be0be  call    RtlImageNtHeaderEx
0x1800be0c3  xor     ecx, ecx
0x1800be0c5  call    LdrpAllocateModuleEntry
0x1800be0ca  mov     rbx, rax
0x1800be0cd  test    rax, rax
0x1800be0d0  jz      loc_1800BE277
0x1800be0d6  mov     rax, [rax+98h]
0x1800be0dd  or      r10, 0FFFFFFFFFFFFFFFFh
0x1800be0e1  mov     [rax+18h], r10d
0x1800be0e5  mov     rax, [rbx+98h]
0x1800be0ec  mov     rcx, [rax]
0x1800be0ef  mov     word ptr [rcx-34h], 0FFFFh
0x1800be0f5  mov     eax, [rbx+68h]
0x1800be0f8  or      eax, 204h
0x1800be0fd  mov     [rbx+68h], eax
0x1800be100  test    rsi, rsi
0x1800be103  jnz     short loc_1800BE113
0x1800be105  mov     rax, cs:qword_1801E3470
0x1800be10c  sub     [rbx+0F8h], rax
0x1800be113  test    rdi, rdi
0x1800be116  jnz     short loc_1800BE183
0x1800be118  mov     rdx, cs:LdrpNtdllHotPatchContext
0x1800be11f  lea     rax, [rsp+298h+var_260]
0x1800be124  mov     [rsp+298h+var_270], rax
0x1800be129  lea     r9, [rsp+298h+var_258]
0x1800be12e  lea     r8d, [rdi+2]
0x1800be132  mov     [rsp+298h+Format], rbp
0x1800be137  mov     rcx, r10
0x1800be13a  mov     rdx, [rdx]
0x1800be13d  call    ZwQueryVirtualMemory
0x1800be142  mov     edi, eax
0x1800be144  test    eax, eax
0x1800be146  jns     loc_1800BE2A8
0x1800be14c  test    edi, edi
0x1800be14e  jns     short loc_1800BE159
0x1800be150  lea     rcx, [rbx+48h]
0x1800be154  call    LdrpFreeUnicodeString
0x1800be159  mov     eax, edi
0x1800be15b  mov     rcx, [rsp+298h+var_38]
0x1800be163  xor     rcx, rsp; StackCookie
0x1800be166  call    __security_check_cookie
0x1800be16b  mov     rbx, [rsp+298h+arg_18]
0x1800be173  add     rsp, 270h
0x1800be17a  pop     r15
0x1800be17c  pop     r14
0x1800be17e  pop     rdi
0x1800be17f  pop     rsi
0x1800be180  pop     rbp
0x1800be181  retn
0x1800be183  movups  xmm0, xmmword ptr [rdi]
0x1800be186  lea     rbp, [rbx+48h]
0x1800be18a  lea     rdx, NtDllName
0x1800be191  mov     rcx, rbp
0x1800be194  movdqu  xmmword ptr [rbp+0], xmm0
0x1800be199  call    RtlAppendUnicodeStringToString
0x1800be19e  movups  xmm0, xmmword ptr cs:NtDllName
0x1800be1a5  movdqu  xmmword ptr [rbx+58h], xmm0
0x1800be1aa  mov     [rbx+30h], r14
0x1800be1ae  mov     r14d, 9
0x1800be1b4  test    rsi, rsi
0x1800be1b7  jnz     loc_1800BE2CC
0x1800be1bd  mov     rcx, rbx
0x1800be1c0  call    LdrpInsertDataTableEntry
0x1800be1c5  mov     rcx, [rbx+30h]
0x1800be1c9  mov     r8d, 14A5h
0x1800be1cf  mov     rdx, rbp
0x1800be1d2  call    LdrpLogDllState
0x1800be1d7  mov     rdx, [rsp+298h+var_268]
0x1800be1dc  mov     rcx, rbx
0x1800be1df  call    LdrpInsertModuleToIndex
0x1800be1e4  xor     edx, edx
0x1800be1e6  mov     rcx, rbx
0x1800be1e9  lea     r8d, [rdx+1]
0x1800be1ed  call    LdrpProcessMappedModule
0x1800be1f2  mov     dword ptr [rsp+298h+var_268], eax
0x1800be1f6  mov     edi, eax
0x1800be1f8  test    eax, eax
0x1800be1fa  js      loc_1800BE14C
0x1800be200  mov     rcx, [rbx+30h]
0x1800be204  mov     r8d, 14AEh
0x1800be20a  mov     rdx, rbp
0x1800be20d  call    LdrpLogDllState
0x1800be212  test    rsi, rsi
0x1800be215  jz      short loc_1800BE264
0x1800be217  mov     rcx, cs:LdrpNtDllDataTableEntry
0x1800be21e  lea     r9, [rsp+298h+var_268]
0x1800be223  xor     r8d, r8d
0x1800be226  mov     rdx, rbx
0x1800be229  call    LdrpRecordModuleDependency
0x1800be22e  mov     edi, dword ptr [rsp+298h+var_268]
0x1800be232  test    edi, edi
0x1800be234  js      loc_1800BE150
0x1800be23a  mov     rax, [rsi+30h]
0x1800be23e  mov     [rbx+0B8h], rax
0x1800be245  mov     dword ptr [rsi+130h], 3
0x1800be24f  mov     rax, [rbx+30h]
0x1800be253  mov     [rsi+128h], rax
0x1800be25a  mov     dword ptr [rbx+130h], 2
0x1800be264  mov     rcx, [rbx+98h]
0x1800be26b  mov     [rcx+38h], r14d
0x1800be26f  mov     [r15], rbx
0x1800be272  jmp     loc_1800BE14C
0x1800be277  lea     rax, aAllocatingADat; "Allocating a data table entry for the s"...
0x1800be27e  xor     r9d, r9d; int
0x1800be281  lea     r8, aLdrpinitialize_2; "LdrpInitializeNtdllDataTableEntry"
0x1800be288  mov     [rsp+298h+Format], rax; Format
0x1800be28d  mov     edx, 14A7h; int
0x1800be292  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x1800be299  call    LdrpLogInternal
0x1800be29e  mov     edi, 0C0000017h
0x1800be2a3  jmp     loc_1800BE159
0x1800be2a8  lea     rbp, [rbx+48h]
0x1800be2ac  mov     r8, rbp
0x1800be2af  lea     rdx, [rbx+58h]
0x1800be2b3  lea     rcx, [rsp+298h+Src]; Src
0x1800be2b8  call    LdrpResolvePatchDllName
0x1800be2bd  mov     edi, eax
0x1800be2bf  test    eax, eax
0x1800be2c1  js      loc_1800BE14C
0x1800be2c7  jmp     loc_1800BE1AA
0x1800be2cc  mov     [rbx+10Ch], r14d
0x1800be2d3  jmp     loc_1800BE1BD
```
