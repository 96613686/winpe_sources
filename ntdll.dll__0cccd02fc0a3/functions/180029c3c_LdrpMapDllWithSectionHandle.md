# LdrpMapDllWithSectionHandle

- ea: `0x180029c3c`
- end: `0x180029fab`
- name: `LdrpMapDllWithSectionHandle`
- size: `879`
- prototype: ``
- caller_count: `3`
- callee_count: `23`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180028bd0`
- `0x1800296e0`
- `0x18010d7f4`

## callees

- `0x180017e90`
- `0x1800183a0`
- `0x18001f070`
- `0x180027550`
- `0x180029b70`
- `0x180029c3c`
- `0x180052720`
- `0x180053e34`
- `0x180054000`
- `0x18005fdf4`
- `0x1800693a8`
- `0x1800a8a90`
- `0x1800bb614`
- `0x1800bf50c`
- `0x1800bf68c`
- `0x1800d2b80`
- `0x1800db200`
- `0x1800fc74c`
- `0x18010349c`
- `0x18011a39c`
- `0x18015e730`
- `0x180162000`
- `0x18016f030`

## pseudocode

```c
__int64 __fastcall LdrpMapDllWithSectionHandle(__int64 a1, __int64 a2)
{
  int v4; // eax
  int v5; // edi
  __int64 v6; // rdx
  __int64 result; // rax
  __int64 v8; // rbx
  __int64 v9; // rbx
  __int64 v10; // r8
  int v11; // r12d
  __int64 v12; // r14
  int v13; // r8d
  int v14; // edx
  int LoadedDllByNameLockHeld; // eax
  __int64 v16; // rcx
  __int64 v17; // r15
  __int64 v18; // r8
  __int64 v19; // rax
  bool v20; // cl
  __int64 v21; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v24[16]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE Src[528]; // [rsp+60h] [rbp-A0h] BYREF

  v21 = 0;
  v23 = 0;
  memset_thunk_772440563353939046(v24, 0, 0x218u);
  v4 = LdrpMinimalMapModule(a1, a2);
  v5 = v4;
  if ( v4 < 0 || v4 == 1073741838 )
    return (unsigned int)v5;
  v6 = *(_QWORD *)(a1 + 56);
  if ( *(_DWORD *)(v6 + 268) != 9 )
  {
LABEL_7:
    v9 = *(_QWORD *)(a1 + 56);
    v10 = *(_QWORD *)(a1 + 168);
    v11 = v5;
    v22 = 0;
    v5 = RtlImageNtHeaderEx(0, *(_QWORD *)(v9 + 48), v10, &v21);
    if ( v5 >= 0 )
    {
      if ( (*(_DWORD *)(a1 + 32) & 0x800000) != 0 )
      {
        v12 = v21;
        v11 = 0;
        *(_DWORD *)(v9 + 128) = *(_DWORD *)(v21 + 8);
        *(_DWORD *)(v9 + 288) = *(_DWORD *)(v12 + 88);
        *(_DWORD *)(v9 + 64) = *(_DWORD *)(v12 + 80);
LABEL_10:
        if ( (void *)qword_1801C4900 == NtCurrentTeb()->ClientId.UniqueThread )
        {
          return (unsigned int)-1073741275;
        }
        else
        {
          v5 = LdrpCompleteMapModule(a1, v12, v11);
          if ( v5 >= 0 )
          {
            v5 = LdrpProcessMappedModule(v9, *(unsigned int *)(a1 + 32), 1);
            if ( v5 >= 0 )
            {
              LdrpLogNewDllLoad(*(_QWORD *)(a1 + 48), v9);
              v19 = *(_QWORD *)(a1 + 48);
              if ( v19 )
                *(_QWORD *)(v9 + 184) = *(_QWORD *)(v19 + 48);
              v20 = 0;
              if ( *(_DWORD *)(v9 + 268) == 9 && LdrpImageEntry )
                v20 = *(_QWORD *)(v9 + 184) == *(_QWORD *)(LdrpImageEntry + 48);
              if ( (*(_DWORD *)(v9 + 104) & 4) != 0 || (*(_DWORD *)(a1 + 32) & 0x800000) != 0 || v20 )
              {
                if ( (*(_DWORD *)(v9 + 104) & 0x1000000) != 0 )
                {
                  return (unsigned int)LdrpCorProcessImports(v9);
                }
                else
                {
                  LdrpMapAndSnapDependency(a1);
                  return (unsigned int)**(_DWORD **)(a1 + 40);
                }
              }
              else
              {
                LdrpLogDllState(*(_QWORD *)(v9 + 48), v9 + 72, 5294);
                v5 = 0;
                *(_DWORD *)(*(_QWORD *)(v9 + 152) + 56LL) = 9;
              }
            }
          }
        }
        return (unsigned int)v5;
      }
      RtlAcquireSRWLockExclusive(&LdrpModuleDatatableLock);
      v13 = *(_DWORD *)(a1 + 32);
      if ( (v13 & 0x20) != 0 )
        v14 = 0;
      else
        v14 = v9 + 72;
      LoadedDllByNameLockHeld = LdrpFindLoadedDllByNameLockHeld(
                                  (int)v9 + 88,
                                  v14,
                                  v13,
                                  (unsigned int)&v22,
                                  *(_DWORD *)(v9 + 264));
      v12 = v21;
      if ( LoadedDllByNameLockHeld == -1073741515 )
      {
        v16 = *(_QWORD *)(v9 + 48);
        LODWORD(v21) = *(_DWORD *)(v21 + 8);
        HIDWORD(v21) = *(_DWORD *)(v12 + 80);
        LdrpFindLoadedDllByMappingLockHeld(v16, v12, &v21, &v22);
      }
      v17 = v22;
      if ( !v22 )
      {
        LdrpInsertDataTableEntry(v9);
        LdrpInsertModuleToIndexLockHeld(v9, v12);
      }
      RtlReleaseSRWLockExclusive(&LdrpModuleDatatableLock);
      if ( !v17 )
        goto LABEL_10;
      v18 = *(_QWORD *)(a1 + 56);
      if ( *(_DWORD *)(v18 + 268) != 9 || *(_DWORD *)(v17 + 268) == 9 )
      {
        LdrpLoadContextReplaceModule(a1, v17);
      }
      else
      {
        v5 = -1073740608;
        LdrpLogEtwHotPatchStatus(LdrpImageEntry + 88, *(_QWORD *)(a1 + 48), v18 + 72, -1073740608, 3);
        LdrpDereferenceModule(v17);
      }
    }
    return (unsigned int)v5;
  }
  result = ZwQueryVirtualMemory(-1, *(_QWORD *)(v6 + 48), 2, v24, 536, &v23);
  if ( (int)result >= 0 )
  {
    result = LdrpResolvePatchDllName(Src);
    v5 = result;
    if ( (int)result >= 0 )
    {
      v8 = *(_QWORD *)(a1 + 56);
      *(_DWORD *)(v8 + 264) = LdrpHashUnicodeString(v8 + 88);
      goto LABEL_7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180029c3c  mov     [rsp-8+arg_10], rbx
0x180029c41  mov     [rsp-8+arg_18], rsi
0x180029c46  push    rbp
0x180029c47  push    rdi
0x180029c48  push    r12
0x180029c4a  push    r14
0x180029c4c  push    r15
0x180029c4e  lea     rbp, [rsp-180h]
0x180029c56  sub     rsp, 280h
0x180029c5d  mov     rax, cs:__security_cookie
0x180029c64  xor     rax, rsp
0x180029c67  mov     [rbp+1A0h+var_30], rax
0x180029c6e  mov     rbx, rdx
0x180029c71  mov     [rsp+2A0h+var_270], 0
0x180029c7a  mov     rsi, rcx
0x180029c7d  mov     [rsp+2A0h+var_260], 0
0x180029c86  mov     r14d, 218h
0x180029c8c  lea     rcx, [rsp+2A0h+var_250]; void *
0x180029c91  mov     r8d, r14d; Size
0x180029c94  xor     edx, edx; Val
0x180029c96  call    memset$thunk$772440563353939046
0x180029c9b  mov     rdx, rbx
0x180029c9e  mov     rcx, rsi
0x180029ca1  call    LdrpMinimalMapModule
0x180029ca6  mov     edi, eax
0x180029ca8  test    eax, eax
0x180029caa  js      loc_180029F7D
0x180029cb0  cmp     eax, 4000000Eh
0x180029cb5  jz      loc_180029F7D
0x180029cbb  mov     rdx, [rsi+38h]
0x180029cbf  cmp     dword ptr [rdx+10Ch], 9
0x180029cc6  jnz     short loc_180029D2A
0x180029cc8  mov     rdx, [rdx+30h]
0x180029ccc  lea     rax, [rsp+2A0h+var_260]
0x180029cd1  mov     [rsp+2A0h+var_278], rax
0x180029cd6  lea     r9, [rsp+2A0h+var_250]
0x180029cdb  mov     r8d, 2
0x180029ce1  mov     [rsp+2A0h+var_280], r14
0x180029ce6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180029cea  call    ZwQueryVirtualMemory
0x180029cef  test    eax, eax
0x180029cf1  js      loc_180029F7F
0x180029cf7  mov     rdx, [rsi+38h]
0x180029cfb  lea     rcx, [rsp+2A0h+Src]; Src
0x180029d00  lea     r8, [rdx+48h]
0x180029d04  add     rdx, 58h ; 'X'
0x180029d08  call    LdrpResolvePatchDllName
0x180029d0d  mov     edi, eax
0x180029d0f  test    eax, eax
0x180029d11  js      loc_180029F7F
0x180029d17  mov     rbx, [rsi+38h]
0x180029d1b  lea     rcx, [rbx+58h]
0x180029d1f  call    LdrpHashUnicodeString
0x180029d24  mov     [rbx+108h], eax
0x180029d2a  mov     rbx, [rsi+38h]
0x180029d2e  lea     r9, [rsp+2A0h+var_270]
0x180029d33  mov     r8, [rsi+0A8h]
0x180029d3a  xor     ecx, ecx
0x180029d3c  mov     r12d, edi
0x180029d3f  mov     [rsp+2A0h+var_268], 0
0x180029d48  mov     rdx, [rbx+30h]
0x180029d4c  call    RtlImageNtHeaderEx
0x180029d51  mov     edi, eax
0x180029d53  test    eax, eax
0x180029d55  js      loc_180029F7D
0x180029d5b  test    dword ptr [rsi+20h], 800000h
0x180029d62  jz      short loc_180029DAB
0x180029d64  mov     r14, [rsp+2A0h+var_270]
0x180029d69  xor     r12d, r12d
0x180029d6c  mov     eax, [r14+8]
0x180029d70  mov     [rbx+80h], eax
0x180029d76  mov     eax, [r14+58h]
0x180029d7a  mov     [rbx+120h], eax
0x180029d80  mov     eax, [r14+50h]
0x180029d84  mov     [rbx+40h], eax
0x180029d87  mov     rax, gs:30h
0x180029d90  mov     rcx, [rax+48h]
0x180029d94  cmp     cs:qword_1801C4900, rcx
0x180029d9b  jnz     loc_180029EA2
0x180029da1  mov     edi, 0C0000225h
0x180029da6  jmp     loc_180029F7D
0x180029dab  lea     rcx, LdrpModuleDatatableLock
0x180029db2  call    RtlAcquireSRWLockExclusive
0x180029db7  mov     r8d, [rsi+20h]
0x180029dbb  test    r8b, 20h
0x180029dbf  jz      short loc_180029DC5
0x180029dc1  xor     edx, edx
0x180029dc3  jmp     short loc_180029DC9
0x180029dc5  lea     rdx, [rbx+48h]
0x180029dc9  mov     eax, [rbx+108h]
0x180029dcf  lea     rcx, [rbx+58h]
0x180029dd3  lea     r9, [rsp+2A0h+var_268]
0x180029dd8  mov     dword ptr [rsp+2A0h+var_280], eax
0x180029ddc  call    LdrpFindLoadedDllByNameLockHeld
0x180029de1  mov     r14, [rsp+2A0h+var_270]
0x180029de6  cmp     eax, 0C0000135h
0x180029deb  jnz     short loc_180029E13
0x180029ded  mov     eax, [r14+8]
0x180029df1  lea     r9, [rsp+2A0h+var_268]
0x180029df6  mov     rcx, [rbx+30h]
0x180029dfa  lea     r8, [rsp+2A0h+var_270]
0x180029dff  mov     dword ptr [rsp+2A0h+var_270], eax
0x180029e03  mov     rdx, r14
0x180029e06  mov     eax, [r14+50h]
0x180029e0a  mov     dword ptr [rsp+2A0h+var_270+4], eax
0x180029e0e  call    LdrpFindLoadedDllByMappingLockHeld
0x180029e13  mov     r15, [rsp+2A0h+var_268]
0x180029e18  test    r15, r15
0x180029e1b  jnz     short loc_180029E30
0x180029e1d  mov     rcx, rbx
0x180029e20  call    LdrpInsertDataTableEntry
0x180029e25  mov     rdx, r14
0x180029e28  mov     rcx, rbx
0x180029e2b  call    LdrpInsertModuleToIndexLockHeld
0x180029e30  lea     rcx, LdrpModuleDatatableLock
0x180029e37  call    RtlReleaseSRWLockExclusive
0x180029e3c  test    r15, r15
0x180029e3f  jz      loc_180029D87
0x180029e45  mov     r8, [rsi+38h]
0x180029e49  cmp     dword ptr [r8+10Ch], 9
0x180029e51  jnz     short loc_180029E92
0x180029e53  cmp     dword ptr [r15+10Ch], 9
0x180029e5b  jz      short loc_180029E92
0x180029e5d  mov     rcx, cs:LdrpImageEntry
0x180029e64  mov     edi, 0C00004C0h
0x180029e69  mov     rdx, [rsi+30h]
0x180029e6d  add     rcx, 58h ; 'X'
0x180029e71  mov     r9d, edi
0x180029e74  mov     dword ptr [rsp+2A0h+var_280], 3
0x180029e7c  add     r8, 48h ; 'H'
0x180029e80  call    LdrpLogEtwHotPatchStatus
0x180029e85  mov     rcx, r15
0x180029e88  call    LdrpDereferenceModule
0x180029e8d  jmp     loc_180029F7D
0x180029e92  mov     rdx, r15
0x180029e95  mov     rcx, rsi
0x180029e98  call    LdrpLoadContextReplaceModule
0x180029e9d  jmp     loc_180029F7D
0x180029ea2  mov     r8d, r12d
0x180029ea5  mov     rdx, r14
0x180029ea8  mov     rcx, rsi
0x180029eab  call    LdrpCompleteMapModule
0x180029eb0  mov     edi, eax
0x180029eb2  test    eax, eax
0x180029eb4  js      loc_180029F7D
0x180029eba  mov     edx, [rsi+20h]
0x180029ebd  mov     r14d, 1
0x180029ec3  mov     r8d, r14d
0x180029ec6  mov     rcx, rbx
0x180029ec9  call    LdrpProcessMappedModule
0x180029ece  mov     edi, eax
0x180029ed0  test    eax, eax
0x180029ed2  js      loc_180029F7D
0x180029ed8  mov     rcx, [rsi+30h]
0x180029edc  mov     rdx, rbx
0x180029edf  call    LdrpLogNewDllLoad
0x180029ee4  mov     rax, [rsi+30h]
0x180029ee8  test    rax, rax
0x180029eeb  jz      short loc_180029EF8
0x180029eed  mov     rax, [rax+30h]
0x180029ef1  mov     [rbx+0B8h], rax
0x180029ef8  xor     cl, cl
0x180029efa  cmp     dword ptr [rbx+10Ch], 9
0x180029f01  jnz     short loc_180029F21
0x180029f03  mov     rax, cs:LdrpImageEntry
0x180029f0a  test    rax, rax
0x180029f0d  jz      short loc_180029F21
0x180029f0f  mov     rax, [rax+30h]
0x180029f13  cmp     [rbx+0B8h], rax
0x180029f1a  movzx   ecx, cl
0x180029f1d  cmovz   ecx, r14d
0x180029f21  mov     eax, [rbx+68h]
0x180029f24  test    al, 4
0x180029f26  jnz     short loc_180029F5A
0x180029f28  test    dword ptr [rsi+20h], 800000h
0x180029f2f  jnz     short loc_180029F5A
0x180029f31  test    cl, cl
0x180029f33  jnz     short loc_180029F5A
0x180029f35  mov     rcx, [rbx+30h]
0x180029f39  lea     rdx, [rbx+48h]
0x180029f3d  mov     r8d, 14AEh
0x180029f43  call    LdrpLogDllState
0x180029f48  mov     rax, [rbx+98h]
0x180029f4f  xor     edi, edi
0x180029f51  mov     dword ptr [rax+38h], 9
0x180029f58  jmp     short loc_180029F7D
0x180029f5a  mov     eax, [rbx+68h]
0x180029f5d  bt      eax, 18h
0x180029f61  jb      short loc_180029F73
0x180029f63  mov     rcx, rsi
0x180029f66  call    LdrpMapAndSnapDependency
0x180029f6b  mov     rax, [rsi+28h]
0x180029f6f  mov     edi, [rax]
0x180029f71  jmp     short loc_180029F7D
0x180029f73  mov     rcx, rbx
0x180029f76  call    LdrpCorProcessImports
0x180029f7b  mov     edi, eax
0x180029f7d  mov     eax, edi
0x180029f7f  mov     rcx, [rbp+1A0h+var_30]
0x180029f86  xor     rcx, rsp; StackCookie
0x180029f89  call    __security_check_cookie
0x180029f8e  lea     r11, [rsp+2A0h+var_20]
0x180029f96  mov     rbx, [r11+40h]
0x180029f9a  mov     rsi, [r11+48h]
0x180029f9e  mov     rsp, r11
0x180029fa1  pop     r15
0x180029fa3  pop     r14
0x180029fa5  pop     r12
0x180029fa7  pop     rdi
0x180029fa8  pop     rbp
0x180029fa9  retn
```
