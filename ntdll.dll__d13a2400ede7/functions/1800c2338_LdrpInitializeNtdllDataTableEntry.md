# LdrpInitializeNtdllDataTableEntry

- ea: `0x1800c2338`
- end: `0x1800c25b8`
- name: `LdrpInitializeNtdllDataTableEntry`
- size: `640`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x180050718`

## callees

- `0x18001eb80`
- `0x18001f070`
- `0x180029a60`
- `0x180036fa0`
- `0x18006dcf4`
- `0x180085e5c`
- `0x1800c2338`
- `0x1800c358c`
- `0x1800c37a8`
- `0x1800c396c`
- `0x1800fd348`
- `0x18010421c`
- `0x18015ef40`
- `0x180162810`
- `0x18016f030`

## string_xrefs

- `0x1800c2561`: `LdrpInitializeNtdllDataTableEntry`
- `0x1800c2557`: `Allocating a data table entry for the system DLL failed\n`

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
      5159,
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
0x1800c2338  mov     [rsp+arg_18], rbx
0x1800c233d  push    rbp
0x1800c233e  push    rsi
0x1800c233f  push    rdi
0x1800c2340  push    r14
0x1800c2342  push    r15
0x1800c2344  sub     rsp, 270h
0x1800c234b  mov     rax, cs:__security_cookie
0x1800c2352  xor     rax, rsp
0x1800c2355  mov     [rsp+298h+var_38], rax
0x1800c235d  mov     rsi, r8
0x1800c2360  mov     [rsp+298h+var_268], 0
0x1800c2369  mov     r15, rdx
0x1800c236c  mov     r14, rcx
0x1800c236f  mov     ebp, 218h
0x1800c2374  lea     rcx, [rsp+298h+var_258]; void *
0x1800c2379  mov     r8d, ebp; Size
0x1800c237c  xor     edx, edx; Val
0x1800c237e  mov     rdi, r9
0x1800c2381  call    memset$thunk$772440563353939046
0x1800c2386  xor     r8d, r8d
0x1800c2389  mov     [rsp+298h+var_260], 0
0x1800c2392  lea     r9, [rsp+298h+var_268]
0x1800c2397  mov     rdx, r14
0x1800c239a  lea     ecx, [r8+3]
0x1800c239e  call    RtlImageNtHeaderEx
0x1800c23a3  xor     ecx, ecx
0x1800c23a5  call    LdrpAllocateModuleEntry
0x1800c23aa  mov     rbx, rax
0x1800c23ad  test    rax, rax
0x1800c23b0  jz      loc_1800C2557
0x1800c23b6  mov     rax, [rax+98h]
0x1800c23bd  or      r10, 0FFFFFFFFFFFFFFFFh
0x1800c23c1  mov     [rax+18h], r10d
0x1800c23c5  mov     rax, [rbx+98h]
0x1800c23cc  mov     rcx, [rax]
0x1800c23cf  mov     word ptr [rcx-34h], 0FFFFh
0x1800c23d5  mov     eax, [rbx+68h]
0x1800c23d8  or      eax, 204h
0x1800c23dd  mov     [rbx+68h], eax
0x1800c23e0  test    rsi, rsi
0x1800c23e3  jnz     short loc_1800C23F3
0x1800c23e5  mov     rax, cs:qword_1801E3470
0x1800c23ec  sub     [rbx+0F8h], rax
0x1800c23f3  test    rdi, rdi
0x1800c23f6  jnz     short loc_1800C2463
0x1800c23f8  mov     rdx, cs:LdrpNtdllHotPatchContext
0x1800c23ff  lea     rax, [rsp+298h+var_260]
0x1800c2404  mov     [rsp+298h+var_270], rax
0x1800c2409  lea     r9, [rsp+298h+var_258]
0x1800c240e  lea     r8d, [rdi+2]
0x1800c2412  mov     [rsp+298h+Format], rbp
0x1800c2417  mov     rcx, r10
0x1800c241a  mov     rdx, [rdx]
0x1800c241d  call    ZwQueryVirtualMemory
0x1800c2422  mov     edi, eax
0x1800c2424  test    eax, eax
0x1800c2426  jns     loc_1800C2588
0x1800c242c  test    edi, edi
0x1800c242e  jns     short loc_1800C2439
0x1800c2430  lea     rcx, [rbx+48h]
0x1800c2434  call    LdrpFreeUnicodeString
0x1800c2439  mov     eax, edi
0x1800c243b  mov     rcx, [rsp+298h+var_38]
0x1800c2443  xor     rcx, rsp; StackCookie
0x1800c2446  call    __security_check_cookie
0x1800c244b  mov     rbx, [rsp+298h+arg_18]
0x1800c2453  add     rsp, 270h
0x1800c245a  pop     r15
0x1800c245c  pop     r14
0x1800c245e  pop     rdi
0x1800c245f  pop     rsi
0x1800c2460  pop     rbp
0x1800c2461  retn
0x1800c2463  movups  xmm0, xmmword ptr [rdi]
0x1800c2466  lea     rbp, [rbx+48h]
0x1800c246a  lea     rdx, NtDllName
0x1800c2471  mov     rcx, rbp
0x1800c2474  movdqu  xmmword ptr [rbp+0], xmm0
0x1800c2479  call    RtlAppendUnicodeStringToString
0x1800c247e  movups  xmm0, xmmword ptr cs:NtDllName
0x1800c2485  movdqu  xmmword ptr [rbx+58h], xmm0
0x1800c248a  mov     [rbx+30h], r14
0x1800c248e  mov     r14d, 9
0x1800c2494  test    rsi, rsi
0x1800c2497  jnz     loc_1800C25AC
0x1800c249d  mov     rcx, rbx
0x1800c24a0  call    LdrpInsertDataTableEntry
0x1800c24a5  mov     rcx, [rbx+30h]
0x1800c24a9  mov     r8d, 14A5h
0x1800c24af  mov     rdx, rbp
0x1800c24b2  call    LdrpLogDllState
0x1800c24b7  mov     rdx, [rsp+298h+var_268]
0x1800c24bc  mov     rcx, rbx
0x1800c24bf  call    LdrpInsertModuleToIndex
0x1800c24c4  xor     edx, edx
0x1800c24c6  mov     rcx, rbx
0x1800c24c9  lea     r8d, [rdx+1]
0x1800c24cd  call    LdrpProcessMappedModule
0x1800c24d2  mov     dword ptr [rsp+298h+var_268], eax
0x1800c24d6  mov     edi, eax
0x1800c24d8  test    eax, eax
0x1800c24da  js      loc_1800C242C
0x1800c24e0  mov     rcx, [rbx+30h]
0x1800c24e4  mov     r8d, 14AEh
0x1800c24ea  mov     rdx, rbp
0x1800c24ed  call    LdrpLogDllState
0x1800c24f2  test    rsi, rsi
0x1800c24f5  jz      short loc_1800C2544
0x1800c24f7  mov     rcx, cs:LdrpNtDllDataTableEntry
0x1800c24fe  lea     r9, [rsp+298h+var_268]
0x1800c2503  xor     r8d, r8d
0x1800c2506  mov     rdx, rbx
0x1800c2509  call    LdrpRecordModuleDependency
0x1800c250e  mov     edi, dword ptr [rsp+298h+var_268]
0x1800c2512  test    edi, edi
0x1800c2514  js      loc_1800C2430
0x1800c251a  mov     rax, [rsi+30h]
0x1800c251e  mov     [rbx+0B8h], rax
0x1800c2525  mov     dword ptr [rsi+130h], 3
0x1800c252f  mov     rax, [rbx+30h]
0x1800c2533  mov     [rsi+128h], rax
0x1800c253a  mov     dword ptr [rbx+130h], 2
0x1800c2544  mov     rcx, [rbx+98h]
0x1800c254b  mov     [rcx+38h], r14d
0x1800c254f  mov     [r15], rbx
0x1800c2552  jmp     loc_1800C242C
0x1800c2557  lea     rax, aAllocatingADat; "Allocating a data table entry for the s"...
0x1800c255e  xor     r9d, r9d; int
0x1800c2561  lea     r8, aLdrpinitialize_2; "LdrpInitializeNtdllDataTableEntry"
0x1800c2568  mov     [rsp+298h+Format], rax; Format
0x1800c256d  mov     edx, 1427h; int
0x1800c2572  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x1800c2579  call    LdrpLogInternal
0x1800c257e  mov     edi, 0C0000017h
0x1800c2583  jmp     loc_1800C2439
0x1800c2588  lea     rbp, [rbx+48h]
0x1800c258c  mov     r8, rbp
0x1800c258f  lea     rdx, [rbx+58h]
0x1800c2593  lea     rcx, [rsp+298h+Src]; Src
0x1800c2598  call    LdrpResolvePatchDllName
0x1800c259d  mov     edi, eax
0x1800c259f  test    eax, eax
0x1800c25a1  js      loc_1800C242C
0x1800c25a7  jmp     loc_1800C248A
0x1800c25ac  mov     [rbx+10Ch], r14d
0x1800c25b3  jmp     loc_1800C249D
```
