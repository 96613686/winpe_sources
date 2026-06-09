# LdrpInitializeNode

- ea: `0x1800e6424`
- end: `0x1800e67b0`
- name: `LdrpInitializeNode`
- size: `908`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800c19c0`
- `0x1800e634c`

## callees

- `0x18001a0d0`
- `0x18001a420`
- `0x18001eb80`
- `0x180029a60`
- `0x18006d6e8`
- `0x18006d980`
- `0x1800bfb90`
- `0x1800e6424`
- `0x18010a200`

## string_xrefs

- `0x1800e650e`: `Calling init routine %p for DLL "%wZ"\n`
- `0x1800e66ba`: `Init routine %p for DLL "%wZ" failed during DLL_PROCESS_ATTACH\n`
- `0x1800e6628`: `Init routine %p of DLL "%wZ" raised an exception %x\n`

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
0x1800e6424  mov     [rsp+arg_0], rcx
0x1800e6429  push    rbx
0x1800e642a  push    rsi
0x1800e642b  push    rdi
0x1800e642c  push    r12
0x1800e642e  push    r13
0x1800e6430  push    r14
0x1800e6432  push    r15
0x1800e6434  sub     rsp, 0F0h
0x1800e643b  mov     rdi, rcx
0x1800e643e  lea     r12, [rcx+38h]
0x1800e6442  mov     [rsp+128h+var_A0], r12
0x1800e644a  mov     dword ptr [r12], 8
0x1800e6452  mov     rcx, [rcx+8]
0x1800e6456  cmp     rcx, rdi
0x1800e6459  jnz     loc_1800E66F5
0x1800e645f  xor     r15d, r15d
0x1800e6462  mov     esi, r15d
0x1800e6465  mov     [rsp+128h+arg_18], r15d
0x1800e646d  mov     r14, [rdi+8]
0x1800e6471  mov     [rsp+128h+var_C8], r14
0x1800e6476  cmp     r14, rdi
0x1800e6479  jnz     short loc_1800E64A1
0x1800e647b  mov     eax, esi
0x1800e647d  neg     eax
0x1800e647f  sbb     ecx, ecx
0x1800e6481  and     ecx, 0FFFFFFF3h
0x1800e6484  add     ecx, 9
0x1800e6487  mov     [r12], ecx
0x1800e648b  mov     eax, esi
0x1800e648d  add     rsp, 0F0h
0x1800e6494  pop     r15
0x1800e6496  pop     r14
0x1800e6498  pop     r13
0x1800e649a  pop     r12
0x1800e649c  pop     rdi
0x1800e649d  pop     rsi
0x1800e649e  pop     rbx
0x1800e649f  retn
0x1800e64a1  lea     rbx, [r14-0A0h]
0x1800e64a8  mov     [rsp+128h+var_98], rbx
0x1800e64b0  cmp     rbx, cs:LdrpImageEntry
0x1800e64b7  jz      loc_1800E6731
0x1800e64bd  cmp     dword ptr [rbx+10Ch], 9
0x1800e64c4  jz      loc_1800E675E
0x1800e64ca  mov     [rsp+128h+var_B8], rbx
0x1800e64cf  mov     rax, cs:LdrpCurrentDllInitializer
0x1800e64d6  mov     [rsp+128h+var_C0], rax
0x1800e64db  mov     [rsp+128h+var_A8], rax
0x1800e64e3  mov     cs:LdrpCurrentDllInitializer, rbx
0x1800e64ea  mov     r13, [rbx+38h]
0x1800e64ee  mov     [rsp+128h+var_90], r13
0x1800e64f6  mov     qword ptr [rsp+128h+var_B0], r13
0x1800e64fb  lea     rax, [rbx+48h]
0x1800e64ff  mov     [rsp+128h+var_D0], rax
0x1800e6504  mov     [rsp+128h+var_F8], rax
0x1800e6509  mov     qword ptr [rsp+128h+ArgList], r13; ArgList
0x1800e650e  lea     rax, aCallingInitRou; "Calling init routine %p for DLL \"%wZ\""...
0x1800e6515  mov     [rsp+128h+Format], rax; Format
0x1800e651a  mov     r9d, 2; int
0x1800e6520  lea     r8, aLdrpinitialize_7; "LdrpInitializeNode"
0x1800e6527  mov     edx, 5DEh; int
0x1800e652c  lea     rcx, aMinkernelLdrLd_4; "minkernel\\ldr\\ldrsnap.c"
0x1800e6533  call    LdrpLogInternal
0x1800e6538  mov     [rsp+128h+arg_8], 1
0x1800e6540  mov     [rsp+128h+arg_10], r15b
0x1800e6548  mov     [rsp+128h+var_88], 48h ; 'H'
0x1800e6554  mov     [rsp+128h+var_80], 1
0x1800e6560  xorps   xmm0, xmm0
0x1800e6563  xor     eax, eax
0x1800e6565  movups  [rsp+128h+var_78], xmm0
0x1800e656d  movups  [rsp+128h+var_68], xmm0
0x1800e6575  movups  [rsp+128h+var_58], xmm0
0x1800e657d  mov     [rsp+128h+var_48], rax
0x1800e6585  mov     rdx, [rbx+88h]
0x1800e658c  lea     rcx, [rsp+128h+var_88]
0x1800e6594  call    RtlActivateActivationContextUnsafeFast
0x1800e6599  nop
0x1800e659a  cmp     [rbx+6Eh], r15w
0x1800e659f  jz      short loc_1800E65AE
0x1800e65a1  mov     rdx, rbx
0x1800e65a4  mov     ecx, 1
0x1800e65a9  call    LdrpCallTlsInitializers
0x1800e65ae  test    r13, r13
0x1800e65b1  jz      short loc_1800E65E0
0x1800e65b3  mov     eax, [rbx+68h]
0x1800e65b6  test    al, 20h
0x1800e65b8  mov     r9, r15
0x1800e65bb  cmovnz  r9, cs:LdrpProcessInitContextRecord
0x1800e65c3  mov     r8d, 1
0x1800e65c9  mov     rdx, [rbx+30h]
0x1800e65cd  mov     rcx, r13
0x1800e65d0  call    LdrpCallInitRoutine
0x1800e65d5  mov     [rsp+128h+arg_8], al
0x1800e65dc  mov     [rsp+128h+var_E8], al
0x1800e65e0  lea     rcx, [rsp+128h+var_88]
0x1800e65e8  call    RtlDeactivateActivationContextUnsafeFast
0x1800e65ed  mov     rax, [rsp+128h+var_C0]
0x1800e65f2  jmp     loc_1800E6686
0x1800e65f7  mov     [rsp+128h+arg_10], 1
0x1800e65ff  xor     cl, cl
0x1800e6601  mov     [rsp+128h+arg_8], cl
0x1800e6608  mov     [rsp+128h+var_E8], cl
0x1800e660c  mov     rcx, [rsp+128h+var_B8]
0x1800e6611  add     rcx, 48h ; 'H'
0x1800e6615  mov     [rsp+128h+var_F0], eax
0x1800e6619  mov     [rsp+128h+var_F8], rcx
0x1800e661e  mov     rax, qword ptr [rsp+128h+var_B0]
0x1800e6623  mov     qword ptr [rsp+128h+ArgList], rax; ArgList
0x1800e6628  lea     rax, aInitRoutinePOf; "Init routine %p of DLL \"%wZ\" raised a"...
0x1800e662f  mov     [rsp+128h+Format], rax; Format
0x1800e6634  xor     r9d, r9d; int
0x1800e6637  lea     r8, aLdrpinitialize_7; "LdrpInitializeNode"
0x1800e663e  mov     edx, 606h; int
0x1800e6643  lea     rcx, aMinkernelLdrLd_4; "minkernel\\ldr\\ldrsnap.c"
0x1800e664a  call    LdrpLogInternal
0x1800e664f  xor     r15d, r15d
0x1800e6652  mov     rdi, [rsp+128h+arg_0]
0x1800e665a  mov     r14, [rsp+128h+var_C8]
0x1800e665f  mov     rax, [rsp+128h+var_A8]
0x1800e6667  mov     esi, [rsp+128h+arg_18]
0x1800e666e  mov     r12, [rsp+128h+var_A0]
0x1800e6676  mov     rbx, [rsp+128h+var_98]
0x1800e667e  mov     r13, [rsp+128h+var_90]
0x1800e6686  mov     cs:LdrpCurrentDllInitializer, rax
0x1800e668d  cmp     [rsp+128h+arg_10], r15b
0x1800e6695  jnz     short loc_1800E66A1
0x1800e6697  mov     eax, [rbx+68h]
0x1800e669a  bts     eax, 13h
0x1800e669e  mov     [rbx+68h], eax
0x1800e66a1  mov     rdx, [rsp+128h+var_D0]
0x1800e66a6  cmp     [rsp+128h+arg_8], r15b
0x1800e66ae  jnz     short loc_1800E6722
0x1800e66b0  mov     [rsp+128h+var_F8], rdx
0x1800e66b5  mov     qword ptr [rsp+128h+ArgList], r13; ArgList
0x1800e66ba  lea     rax, aInitRoutinePFo; "Init routine %p for DLL \"%wZ\" failed "...
0x1800e66c1  mov     [rsp+128h+Format], rax; Format
0x1800e66c6  xor     r9d, r9d; int
0x1800e66c9  lea     r8, aLdrpinitialize_7; "LdrpInitializeNode"
0x1800e66d0  mov     edx, 614h; int
0x1800e66d5  lea     rcx, aMinkernelLdrLd_4; "minkernel\\ldr\\ldrsnap.c"
0x1800e66dc  call    LdrpLogInternal
0x1800e66e1  mov     esi, 0C0000142h
0x1800e66e6  mov     eax, [rbx+68h]
0x1800e66e9  bts     eax, 14h
0x1800e66ed  mov     [rbx+68h], eax
0x1800e66f0  jmp     loc_1800E647B
0x1800e66f5  lea     r9, qword_1801CA8F0
0x1800e66fc  mov     rax, cs:qword_1801CA8F8
0x1800e6703  lea     r8, [rcx-0A0h]
0x1800e670a  cmp     r8, cs:LdrpImageEntry
0x1800e6711  jz      short loc_1800E674F
0x1800e6713  mov     rdx, rax
0x1800e6716  cmp     [rax], r9
0x1800e6719  jz      short loc_1800E673A
0x1800e671b  mov     ecx, 3
0x1800e6720  int     29h; Win8: RtlFailFast(ecx)
0x1800e6722  mov     r8d, 14AEh
0x1800e6728  mov     rcx, [rbx+30h]
0x1800e672c  call    LdrpLogDllState
0x1800e6731  mov     r14, [r14+8]
0x1800e6735  jmp     loc_1800E6471
0x1800e673a  lea     rax, [r8+20h]
0x1800e673e  mov     [rax], r9
0x1800e6741  mov     [rax+8], rdx
0x1800e6745  mov     [rdx], rax
0x1800e6748  mov     cs:qword_1801CA8F8, rax
0x1800e674f  mov     rcx, [rcx+8]
0x1800e6753  cmp     rcx, rdi
0x1800e6756  jz      loc_1800E645F
0x1800e675c  jmp     short loc_1800E6703
0x1800e675e  mov     rcx, rbx
0x1800e6761  call    LdrpApplyPatchImage
0x1800e6766  mov     esi, eax
0x1800e6768  mov     [rsp+128h+arg_18], eax
0x1800e676f  test    eax, eax
0x1800e6771  jns     loc_1800E64CA
0x1800e6777  lea     rdx, [rbx+48h]
0x1800e677b  mov     dword ptr [rsp+128h+var_F8], eax
0x1800e677f  mov     qword ptr [rsp+128h+ArgList], rdx; ArgList
0x1800e6784  lea     rax, aApplyingPatchW_0; "Applying patch \"%wZ\" failed - Status "...
0x1800e678b  mov     [rsp+128h+Format], rax; Format
0x1800e6790  xor     r9d, r9d; int
0x1800e6793  lea     r8, aLdrpinitialize_7; "LdrpInitializeNode"
0x1800e679a  mov     edx, 5CBh; int
0x1800e679f  lea     rcx, aMinkernelLdrLd_4; "minkernel\\ldr\\ldrsnap.c"
0x1800e67a6  call    LdrpLogInternal
0x1800e67ab  jmp     loc_1800E647B
0x18016858e  push    rbp
0x180168590  sub     rsp, 40h
0x180168594  mov     rbp, rdx
0x180168597  lea     rcx, [rbp+0A0h]
0x18016859e  call    RtlDeactivateActivationContextUnsafeFast
0x1801685a3  nop
0x1801685a4  add     rsp, 40h
0x1801685a8  pop     rbp
0x1801685a9  retn
0x1801685ab  push    rbp
0x1801685ad  sub     rsp, 40h
0x1801685b1  mov     rbp, rdx
0x1801685b4  mov     [rbp+50h], rcx
0x1801685b8  mov     dword ptr [rbp+44h], 0Bh
0x1801685bf  mov     rax, [rbp+50h]
0x1801685c3  mov     rdx, [rax+8]
0x1801685c7  mov     rax, [rbp+50h]
0x1801685cb  mov     rcx, [rax]
0x1801685ce  mov     r8d, [rbp+44h]
0x1801685d2  call    RtlReportException
0x1801685d7  mov     dword ptr [rbp+48h], 1
0x1801685de  mov     eax, [rbp+48h]
0x1801685e1  add     rsp, 40h
0x1801685e5  pop     rbp
0x1801685e6  retn
```
