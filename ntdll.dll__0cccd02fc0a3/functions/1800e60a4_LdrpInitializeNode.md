# LdrpInitializeNode

- ea: `0x1800e60a4`
- end: `0x1800e6430`
- name: `LdrpInitializeNode`
- size: `908`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800bd6e0`
- `0x1800e5fcc`

## callees

- `0x18001a0d0`
- `0x18001a420`
- `0x18001eb80`
- `0x180029b70`
- `0x180050d08`
- `0x180050fa0`
- `0x1800bb8b0`
- `0x1800e60a4`
- `0x180109270`

## string_xrefs

- `0x1800e618e`: `Calling init routine %p for DLL "%wZ"\n`
- `0x1800e633a`: `Init routine %p for DLL "%wZ" failed during DLL_PROCESS_ATTACH\n`
- `0x1800e62a8`: `Init routine %p of DLL "%wZ" raised an exception %x\n`

## pseudocode

```c
__int64 __fastcall LdrpInitializeNode(__int64 a1)
{
  _DWORD *v2; // r12
  __int64 v3; // rcx
  int v4; // esi
  __int64 i; // r14
  __int64 v7; // rbx
  __int64 ArgList; // r13
  __int64 v9; // r9
  __int64 **v10; // rax
  __int64 v11; // r8
  __int64 **v12; // rdx
  __int64 v13; // [rsp+68h] [rbp-C0h]
  _QWORD v14[2]; // [rsp+A0h] [rbp-88h] BYREF
  __int128 v15; // [rsp+B0h] [rbp-78h]
  __int128 v16; // [rsp+C0h] [rbp-68h]
  __int128 v17; // [rsp+D0h] [rbp-58h]
  __int64 v18; // [rsp+E0h] [rbp-48h]
  char v19; // [rsp+138h] [rbp+10h]

  v2 = (_DWORD *)(a1 + 56);
  *(_DWORD *)(a1 + 56) = 8;
  v3 = *(_QWORD *)(a1 + 8);
  if ( v3 != a1 )
  {
    v10 = (__int64 **)qword_1801CA8F8;
    do
    {
      v11 = v3 - 160;
      if ( v3 - 160 != LdrpImageEntry )
      {
        v12 = v10;
        if ( *v10 != &qword_1801CA8F0 )
          __fastfail(3u);
        v10 = (__int64 **)(v11 + 32);
        *(_QWORD *)(v11 + 32) = &qword_1801CA8F0;
        *(_QWORD *)(v11 + 40) = v12;
        *v12 = (__int64 *)(v11 + 32);
        qword_1801CA8F8 = v11 + 32;
      }
      v3 = *(_QWORD *)(v3 + 8);
    }
    while ( v3 != a1 );
  }
  v4 = 0;
  for ( i = *(_QWORD *)(a1 + 8); i != a1; i = *(_QWORD *)(i + 8) )
  {
    v7 = i - 160;
    if ( i - 160 != LdrpImageEntry )
    {
      if ( *(_DWORD *)(v7 + 268) == 9 )
      {
        v4 = LdrpApplyPatchImage(i - 160);
        if ( v4 < 0 )
        {
          LdrpLogInternal(
            (int)"minkernel\\ldr\\ldrsnap.c",
            1483,
            (int)"LdrpInitializeNode",
            0,
            "Applying patch \"%wZ\" failed - Status = 0x%x\n",
            i - 88);
          break;
        }
      }
      v13 = LdrpCurrentDllInitializer;
      LdrpCurrentDllInitializer = i - 160;
      ArgList = *(_QWORD *)(v7 + 56);
      LdrpLogInternal(
        (int)"minkernel\\ldr\\ldrsnap.c",
        1502,
        (int)"LdrpInitializeNode",
        2,
        "Calling init routine %p for DLL \"%wZ\"\n",
        ArgList);
      v19 = 1;
      v14[0] = 72;
      v14[1] = 1;
      v15 = 0;
      v16 = 0;
      v17 = 0;
      v18 = 0;
      RtlActivateActivationContextUnsafeFast(v14, *(_QWORD *)(v7 + 136));
      if ( *(_WORD *)(v7 + 110) )
        LdrpCallTlsInitializers(1, i - 160);
      if ( ArgList )
      {
        v9 = 0;
        if ( (*(_DWORD *)(v7 + 104) & 0x20) != 0 )
          v9 = LdrpProcessInitContextRecord;
        v19 = LdrpCallInitRoutine(ArgList, *(_QWORD *)(v7 + 48), 1, v9);
      }
      RtlDeactivateActivationContextUnsafeFast(v14);
      LdrpCurrentDllInitializer = v13;
      *(_DWORD *)(v7 + 104) |= 0x80000u;
      if ( !v19 )
      {
        LdrpLogInternal(
          (int)"minkernel\\ldr\\ldrsnap.c",
          1556,
          (int)"LdrpInitializeNode",
          0,
          "Init routine %p for DLL \"%wZ\" failed during DLL_PROCESS_ATTACH\n",
          ArgList);
        v4 = -1073741502;
        *(_DWORD *)(v7 + 104) |= 0x100000u;
        break;
      }
      LdrpLogDllState(*(_QWORD *)(v7 + 48), v7 + 72, 5294);
    }
  }
  *v2 = v4 != 0 ? -4 : 9;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800e60a4  mov     [rsp+arg_0], rcx
0x1800e60a9  push    rbx
0x1800e60aa  push    rsi
0x1800e60ab  push    rdi
0x1800e60ac  push    r12
0x1800e60ae  push    r13
0x1800e60b0  push    r14
0x1800e60b2  push    r15
0x1800e60b4  sub     rsp, 0F0h
0x1800e60bb  mov     rdi, rcx
0x1800e60be  lea     r12, [rcx+38h]
0x1800e60c2  mov     [rsp+128h+var_A0], r12
0x1800e60ca  mov     dword ptr [r12], 8
0x1800e60d2  mov     rcx, [rcx+8]
0x1800e60d6  cmp     rcx, rdi
0x1800e60d9  jnz     loc_1800E6375
0x1800e60df  xor     r15d, r15d
0x1800e60e2  mov     esi, r15d
0x1800e60e5  mov     [rsp+128h+arg_18], r15d
0x1800e60ed  mov     r14, [rdi+8]
0x1800e60f1  mov     [rsp+128h+var_C8], r14
0x1800e60f6  cmp     r14, rdi
0x1800e60f9  jnz     short loc_1800E6121
0x1800e60fb  mov     eax, esi
0x1800e60fd  neg     eax
0x1800e60ff  sbb     ecx, ecx
0x1800e6101  and     ecx, 0FFFFFFF3h
0x1800e6104  add     ecx, 9
0x1800e6107  mov     [r12], ecx
0x1800e610b  mov     eax, esi
0x1800e610d  add     rsp, 0F0h
0x1800e6114  pop     r15
0x1800e6116  pop     r14
0x1800e6118  pop     r13
0x1800e611a  pop     r12
0x1800e611c  pop     rdi
0x1800e611d  pop     rsi
0x1800e611e  pop     rbx
0x1800e611f  retn
0x1800e6121  lea     rbx, [r14-0A0h]
0x1800e6128  mov     [rsp+128h+var_98], rbx
0x1800e6130  cmp     rbx, cs:LdrpImageEntry
0x1800e6137  jz      loc_1800E63B1
0x1800e613d  cmp     dword ptr [rbx+10Ch], 9
0x1800e6144  jz      loc_1800E63DE
0x1800e614a  mov     [rsp+128h+var_B8], rbx
0x1800e614f  mov     rax, cs:LdrpCurrentDllInitializer
0x1800e6156  mov     [rsp+128h+var_C0], rax
0x1800e615b  mov     [rsp+128h+var_A8], rax
0x1800e6163  mov     cs:LdrpCurrentDllInitializer, rbx
0x1800e616a  mov     r13, [rbx+38h]
0x1800e616e  mov     [rsp+128h+var_90], r13
0x1800e6176  mov     qword ptr [rsp+128h+var_B0], r13
0x1800e617b  lea     rax, [rbx+48h]
0x1800e617f  mov     [rsp+128h+var_D0], rax
0x1800e6184  mov     [rsp+128h+var_F8], rax
0x1800e6189  mov     qword ptr [rsp+128h+ArgList], r13; ArgList
0x1800e618e  lea     rax, aCallingInitRou; "Calling init routine %p for DLL \"%wZ\""...
0x1800e6195  mov     [rsp+128h+Format], rax; Format
0x1800e619a  mov     r9d, 2; int
0x1800e61a0  lea     r8, aLdrpinitialize_7; "LdrpInitializeNode"
0x1800e61a7  mov     edx, 5DEh; int
0x1800e61ac  lea     rcx, aMinkernelLdrLd_4; "minkernel\\ldr\\ldrsnap.c"
0x1800e61b3  call    LdrpLogInternal
0x1800e61b8  mov     [rsp+128h+arg_8], 1
0x1800e61c0  mov     [rsp+128h+arg_10], r15b
0x1800e61c8  mov     [rsp+128h+var_88], 48h ; 'H'
0x1800e61d4  mov     [rsp+128h+var_80], 1
0x1800e61e0  xorps   xmm0, xmm0
0x1800e61e3  xor     eax, eax
0x1800e61e5  movups  [rsp+128h+var_78], xmm0
0x1800e61ed  movups  [rsp+128h+var_68], xmm0
0x1800e61f5  movups  [rsp+128h+var_58], xmm0
0x1800e61fd  mov     [rsp+128h+var_48], rax
0x1800e6205  mov     rdx, [rbx+88h]
0x1800e620c  lea     rcx, [rsp+128h+var_88]
0x1800e6214  call    RtlActivateActivationContextUnsafeFast
0x1800e6219  nop
0x1800e621a  cmp     [rbx+6Eh], r15w
0x1800e621f  jz      short loc_1800E622E
0x1800e6221  mov     rdx, rbx
0x1800e6224  mov     ecx, 1
0x1800e6229  call    LdrpCallTlsInitializers
0x1800e622e  test    r13, r13
0x1800e6231  jz      short loc_1800E6260
0x1800e6233  mov     eax, [rbx+68h]
0x1800e6236  test    al, 20h
0x1800e6238  mov     r9, r15
0x1800e623b  cmovnz  r9, cs:LdrpProcessInitContextRecord
0x1800e6243  mov     r8d, 1
0x1800e6249  mov     rdx, [rbx+30h]
0x1800e624d  mov     rcx, r13
0x1800e6250  call    LdrpCallInitRoutine
0x1800e6255  mov     [rsp+128h+arg_8], al
0x1800e625c  mov     [rsp+128h+var_E8], al
0x1800e6260  lea     rcx, [rsp+128h+var_88]
0x1800e6268  call    RtlDeactivateActivationContextUnsafeFast
0x1800e626d  mov     rax, [rsp+128h+var_C0]
0x1800e6272  jmp     loc_1800E6306
0x1800e6277  mov     [rsp+128h+arg_10], 1
0x1800e627f  xor     cl, cl
0x1800e6281  mov     [rsp+128h+arg_8], cl
0x1800e6288  mov     [rsp+128h+var_E8], cl
0x1800e628c  mov     rcx, [rsp+128h+var_B8]
0x1800e6291  add     rcx, 48h ; 'H'
0x1800e6295  mov     [rsp+128h+var_F0], eax
0x1800e6299  mov     [rsp+128h+var_F8], rcx
0x1800e629e  mov     rax, qword ptr [rsp+128h+var_B0]
0x1800e62a3  mov     qword ptr [rsp+128h+ArgList], rax; ArgList
0x1800e62a8  lea     rax, aInitRoutinePOf; "Init routine %p of DLL \"%wZ\" raised a"...
0x1800e62af  mov     [rsp+128h+Format], rax; Format
0x1800e62b4  xor     r9d, r9d; int
0x1800e62b7  lea     r8, aLdrpinitialize_7; "LdrpInitializeNode"
0x1800e62be  mov     edx, 606h; int
0x1800e62c3  lea     rcx, aMinkernelLdrLd_4; "minkernel\\ldr\\ldrsnap.c"
0x1800e62ca  call    LdrpLogInternal
0x1800e62cf  xor     r15d, r15d
0x1800e62d2  mov     rdi, [rsp+128h+arg_0]
0x1800e62da  mov     r14, [rsp+128h+var_C8]
0x1800e62df  mov     rax, [rsp+128h+var_A8]
0x1800e62e7  mov     esi, [rsp+128h+arg_18]
0x1800e62ee  mov     r12, [rsp+128h+var_A0]
0x1800e62f6  mov     rbx, [rsp+128h+var_98]
0x1800e62fe  mov     r13, [rsp+128h+var_90]
0x1800e6306  mov     cs:LdrpCurrentDllInitializer, rax
0x1800e630d  cmp     [rsp+128h+arg_10], r15b
0x1800e6315  jnz     short loc_1800E6321
0x1800e6317  mov     eax, [rbx+68h]
0x1800e631a  bts     eax, 13h
0x1800e631e  mov     [rbx+68h], eax
0x1800e6321  mov     rdx, [rsp+128h+var_D0]
0x1800e6326  cmp     [rsp+128h+arg_8], r15b
0x1800e632e  jnz     short loc_1800E63A2
0x1800e6330  mov     [rsp+128h+var_F8], rdx
0x1800e6335  mov     qword ptr [rsp+128h+ArgList], r13; ArgList
0x1800e633a  lea     rax, aInitRoutinePFo; "Init routine %p for DLL \"%wZ\" failed "...
0x1800e6341  mov     [rsp+128h+Format], rax; Format
0x1800e6346  xor     r9d, r9d; int
0x1800e6349  lea     r8, aLdrpinitialize_7; "LdrpInitializeNode"
0x1800e6350  mov     edx, 614h; int
0x1800e6355  lea     rcx, aMinkernelLdrLd_4; "minkernel\\ldr\\ldrsnap.c"
0x1800e635c  call    LdrpLogInternal
0x1800e6361  mov     esi, 0C0000142h
0x1800e6366  mov     eax, [rbx+68h]
0x1800e6369  bts     eax, 14h
0x1800e636d  mov     [rbx+68h], eax
0x1800e6370  jmp     loc_1800E60FB
0x1800e6375  lea     r9, qword_1801CA8F0
0x1800e637c  mov     rax, cs:qword_1801CA8F8
0x1800e6383  lea     r8, [rcx-0A0h]
0x1800e638a  cmp     r8, cs:LdrpImageEntry
0x1800e6391  jz      short loc_1800E63CF
0x1800e6393  mov     rdx, rax
0x1800e6396  cmp     [rax], r9
0x1800e6399  jz      short loc_1800E63BA
0x1800e639b  mov     ecx, 3
0x1800e63a0  int     29h; Win8: RtlFailFast(ecx)
0x1800e63a2  mov     r8d, 14AEh
0x1800e63a8  mov     rcx, [rbx+30h]
0x1800e63ac  call    LdrpLogDllState
0x1800e63b1  mov     r14, [r14+8]
0x1800e63b5  jmp     loc_1800E60F1
0x1800e63ba  lea     rax, [r8+20h]
0x1800e63be  mov     [rax], r9
0x1800e63c1  mov     [rax+8], rdx
0x1800e63c5  mov     [rdx], rax
0x1800e63c8  mov     cs:qword_1801CA8F8, rax
0x1800e63cf  mov     rcx, [rcx+8]
0x1800e63d3  cmp     rcx, rdi
0x1800e63d6  jz      loc_1800E60DF
0x1800e63dc  jmp     short loc_1800E6383
0x1800e63de  mov     rcx, rbx
0x1800e63e1  call    LdrpApplyPatchImage
0x1800e63e6  mov     esi, eax
0x1800e63e8  mov     [rsp+128h+arg_18], eax
0x1800e63ef  test    eax, eax
0x1800e63f1  jns     loc_1800E614A
0x1800e63f7  lea     rdx, [rbx+48h]
0x1800e63fb  mov     dword ptr [rsp+128h+var_F8], eax
0x1800e63ff  mov     qword ptr [rsp+128h+ArgList], rdx; ArgList
0x1800e6404  lea     rax, aApplyingPatchW_0; "Applying patch \"%wZ\" failed - Status "...
0x1800e640b  mov     [rsp+128h+Format], rax; Format
0x1800e6410  xor     r9d, r9d; int
0x1800e6413  lea     r8, aLdrpinitialize_7; "LdrpInitializeNode"
0x1800e641a  mov     edx, 5CBh; int
0x1800e641f  lea     rcx, aMinkernelLdrLd_4; "minkernel\\ldr\\ldrsnap.c"
0x1800e6426  call    LdrpLogInternal
0x1800e642b  jmp     loc_1800E60FB
0x180167d6e  push    rbp
0x180167d70  sub     rsp, 40h
0x180167d74  mov     rbp, rdx
0x180167d77  lea     rcx, [rbp+0A0h]
0x180167d7e  call    RtlDeactivateActivationContextUnsafeFast
0x180167d83  nop
0x180167d84  add     rsp, 40h
0x180167d88  pop     rbp
0x180167d89  retn
0x180167d8b  push    rbp
0x180167d8d  sub     rsp, 40h
0x180167d91  mov     rbp, rdx
0x180167d94  mov     [rbp+50h], rcx
0x180167d98  mov     dword ptr [rbp+44h], 0Bh
0x180167d9f  mov     rax, [rbp+50h]
0x180167da3  mov     rdx, [rax+8]
0x180167da7  mov     rax, [rbp+50h]
0x180167dab  mov     rcx, [rax]
0x180167dae  mov     r8d, [rbp+44h]
0x180167db2  call    RtlReportException
0x180167db7  mov     dword ptr [rbp+48h], 1
0x180167dbe  mov     eax, [rbp+48h]
0x180167dc1  add     rsp, 40h
0x180167dc5  pop     rbp
0x180167dc6  retn
```
