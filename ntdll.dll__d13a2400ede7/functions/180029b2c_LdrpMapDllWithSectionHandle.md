# LdrpMapDllWithSectionHandle

- ea: `0x180029b2c`
- end: `0x180029e9b`
- name: `LdrpMapDllWithSectionHandle`
- size: `879`
- prototype: ``
- caller_count: `3`
- callee_count: `23`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180028ac0`
- `0x1800295d0`
- `0x18010eb44`

## callees

- `0x180017e90`
- `0x1800183a0`
- `0x18001f070`
- `0x180027434`
- `0x180029a60`
- `0x180029b2c`
- `0x18006f100`
- `0x180070814`
- `0x1800709e0`
- `0x18007c7d4`
- `0x180085e5c`
- `0x1800b1460`
- `0x1800bf8f4`
- `0x1800c37ec`
- `0x1800c396c`
- `0x1800d6e30`
- `0x1800dbc80`
- `0x1800fcd6c`
- `0x18010421c`
- `0x18011ae8c`
- `0x18015ef40`
- `0x180162810`
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
        if ( (void *)qword_1801C4930 == NtCurrentTeb()->ClientId.UniqueThread )
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
      RtlAcquireSRWLockExclusive(LdrpModuleDatatableLock);
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
      RtlReleaseSRWLockExclusive(LdrpModuleDatatableLock);
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
0x180029b2c  mov     [rsp-8+arg_10], rbx
0x180029b31  mov     [rsp-8+arg_18], rsi
0x180029b36  push    rbp
0x180029b37  push    rdi
0x180029b38  push    r12
0x180029b3a  push    r14
0x180029b3c  push    r15
0x180029b3e  lea     rbp, [rsp-180h]
0x180029b46  sub     rsp, 280h
0x180029b4d  mov     rax, cs:__security_cookie
0x180029b54  xor     rax, rsp
0x180029b57  mov     [rbp+1A0h+var_30], rax
0x180029b5e  mov     rbx, rdx
0x180029b61  mov     [rsp+2A0h+var_270], 0
0x180029b6a  mov     rsi, rcx
0x180029b6d  mov     [rsp+2A0h+var_260], 0
0x180029b76  mov     r14d, 218h
0x180029b7c  lea     rcx, [rsp+2A0h+var_250]; void *
0x180029b81  mov     r8d, r14d; Size
0x180029b84  xor     edx, edx; Val
0x180029b86  call    memset$thunk$772440563353939046
0x180029b8b  mov     rdx, rbx
0x180029b8e  mov     rcx, rsi
0x180029b91  call    LdrpMinimalMapModule
0x180029b96  mov     edi, eax
0x180029b98  test    eax, eax
0x180029b9a  js      loc_180029E6D
0x180029ba0  cmp     eax, 4000000Eh
0x180029ba5  jz      loc_180029E6D
0x180029bab  mov     rdx, [rsi+38h]
0x180029baf  cmp     dword ptr [rdx+10Ch], 9
0x180029bb6  jnz     short loc_180029C1A
0x180029bb8  mov     rdx, [rdx+30h]
0x180029bbc  lea     rax, [rsp+2A0h+var_260]
0x180029bc1  mov     [rsp+2A0h+var_278], rax
0x180029bc6  lea     r9, [rsp+2A0h+var_250]
0x180029bcb  mov     r8d, 2
0x180029bd1  mov     [rsp+2A0h+var_280], r14
0x180029bd6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180029bda  call    ZwQueryVirtualMemory
0x180029bdf  test    eax, eax
0x180029be1  js      loc_180029E6F
0x180029be7  mov     rdx, [rsi+38h]
0x180029beb  lea     rcx, [rsp+2A0h+Src]; Src
0x180029bf0  lea     r8, [rdx+48h]
0x180029bf4  add     rdx, 58h ; 'X'
0x180029bf8  call    LdrpResolvePatchDllName
0x180029bfd  mov     edi, eax
0x180029bff  test    eax, eax
0x180029c01  js      loc_180029E6F
0x180029c07  mov     rbx, [rsi+38h]
0x180029c0b  lea     rcx, [rbx+58h]
0x180029c0f  call    LdrpHashUnicodeString
0x180029c14  mov     [rbx+108h], eax
0x180029c1a  mov     rbx, [rsi+38h]
0x180029c1e  lea     r9, [rsp+2A0h+var_270]
0x180029c23  mov     r8, [rsi+0A8h]
0x180029c2a  xor     ecx, ecx
0x180029c2c  mov     r12d, edi
0x180029c2f  mov     [rsp+2A0h+var_268], 0
0x180029c38  mov     rdx, [rbx+30h]
0x180029c3c  call    RtlImageNtHeaderEx
0x180029c41  mov     edi, eax
0x180029c43  test    eax, eax
0x180029c45  js      loc_180029E6D
0x180029c4b  test    dword ptr [rsi+20h], 800000h
0x180029c52  jz      short loc_180029C9B
0x180029c54  mov     r14, [rsp+2A0h+var_270]
0x180029c59  xor     r12d, r12d
0x180029c5c  mov     eax, [r14+8]
0x180029c60  mov     [rbx+80h], eax
0x180029c66  mov     eax, [r14+58h]
0x180029c6a  mov     [rbx+120h], eax
0x180029c70  mov     eax, [r14+50h]
0x180029c74  mov     [rbx+40h], eax
0x180029c77  mov     rax, gs:30h
0x180029c80  mov     rcx, [rax+48h]
0x180029c84  cmp     cs:qword_1801C4930, rcx
0x180029c8b  jnz     loc_180029D92
0x180029c91  mov     edi, 0C0000225h
0x180029c96  jmp     loc_180029E6D
0x180029c9b  lea     rcx, LdrpModuleDatatableLock
0x180029ca2  call    RtlAcquireSRWLockExclusive
0x180029ca7  mov     r8d, [rsi+20h]
0x180029cab  test    r8b, 20h
0x180029caf  jz      short loc_180029CB5
0x180029cb1  xor     edx, edx
0x180029cb3  jmp     short loc_180029CB9
0x180029cb5  lea     rdx, [rbx+48h]
0x180029cb9  mov     eax, [rbx+108h]
0x180029cbf  lea     rcx, [rbx+58h]
0x180029cc3  lea     r9, [rsp+2A0h+var_268]
0x180029cc8  mov     dword ptr [rsp+2A0h+var_280], eax
0x180029ccc  call    LdrpFindLoadedDllByNameLockHeld
0x180029cd1  mov     r14, [rsp+2A0h+var_270]
0x180029cd6  cmp     eax, 0C0000135h
0x180029cdb  jnz     short loc_180029D03
0x180029cdd  mov     eax, [r14+8]
0x180029ce1  lea     r9, [rsp+2A0h+var_268]
0x180029ce6  mov     rcx, [rbx+30h]
0x180029cea  lea     r8, [rsp+2A0h+var_270]
0x180029cef  mov     dword ptr [rsp+2A0h+var_270], eax
0x180029cf3  mov     rdx, r14
0x180029cf6  mov     eax, [r14+50h]
0x180029cfa  mov     dword ptr [rsp+2A0h+var_270+4], eax
0x180029cfe  call    LdrpFindLoadedDllByMappingLockHeld
0x180029d03  mov     r15, [rsp+2A0h+var_268]
0x180029d08  test    r15, r15
0x180029d0b  jnz     short loc_180029D20
0x180029d0d  mov     rcx, rbx
0x180029d10  call    LdrpInsertDataTableEntry
0x180029d15  mov     rdx, r14
0x180029d18  mov     rcx, rbx
0x180029d1b  call    LdrpInsertModuleToIndexLockHeld
0x180029d20  lea     rcx, LdrpModuleDatatableLock
0x180029d27  call    RtlReleaseSRWLockExclusive
0x180029d2c  test    r15, r15
0x180029d2f  jz      loc_180029C77
0x180029d35  mov     r8, [rsi+38h]
0x180029d39  cmp     dword ptr [r8+10Ch], 9
0x180029d41  jnz     short loc_180029D82
0x180029d43  cmp     dword ptr [r15+10Ch], 9
0x180029d4b  jz      short loc_180029D82
0x180029d4d  mov     rcx, cs:LdrpImageEntry
0x180029d54  mov     edi, 0C00004C0h
0x180029d59  mov     rdx, [rsi+30h]
0x180029d5d  add     rcx, 58h ; 'X'
0x180029d61  mov     r9d, edi
0x180029d64  mov     dword ptr [rsp+2A0h+var_280], 3
0x180029d6c  add     r8, 48h ; 'H'
0x180029d70  call    LdrpLogEtwHotPatchStatus
0x180029d75  mov     rcx, r15
0x180029d78  call    LdrpDereferenceModule
0x180029d7d  jmp     loc_180029E6D
0x180029d82  mov     rdx, r15
0x180029d85  mov     rcx, rsi
0x180029d88  call    LdrpLoadContextReplaceModule
0x180029d8d  jmp     loc_180029E6D
0x180029d92  mov     r8d, r12d
0x180029d95  mov     rdx, r14
0x180029d98  mov     rcx, rsi
0x180029d9b  call    LdrpCompleteMapModule
0x180029da0  mov     edi, eax
0x180029da2  test    eax, eax
0x180029da4  js      loc_180029E6D
0x180029daa  mov     edx, [rsi+20h]
0x180029dad  mov     r14d, 1
0x180029db3  mov     r8d, r14d
0x180029db6  mov     rcx, rbx
0x180029db9  call    LdrpProcessMappedModule
0x180029dbe  mov     edi, eax
0x180029dc0  test    eax, eax
0x180029dc2  js      loc_180029E6D
0x180029dc8  mov     rcx, [rsi+30h]
0x180029dcc  mov     rdx, rbx
0x180029dcf  call    LdrpLogNewDllLoad
0x180029dd4  mov     rax, [rsi+30h]
0x180029dd8  test    rax, rax
0x180029ddb  jz      short loc_180029DE8
0x180029ddd  mov     rax, [rax+30h]
0x180029de1  mov     [rbx+0B8h], rax
0x180029de8  xor     cl, cl
0x180029dea  cmp     dword ptr [rbx+10Ch], 9
0x180029df1  jnz     short loc_180029E11
0x180029df3  mov     rax, cs:LdrpImageEntry
0x180029dfa  test    rax, rax
0x180029dfd  jz      short loc_180029E11
0x180029dff  mov     rax, [rax+30h]
0x180029e03  cmp     [rbx+0B8h], rax
0x180029e0a  movzx   ecx, cl
0x180029e0d  cmovz   ecx, r14d
0x180029e11  mov     eax, [rbx+68h]
0x180029e14  test    al, 4
0x180029e16  jnz     short loc_180029E4A
0x180029e18  test    dword ptr [rsi+20h], 800000h
0x180029e1f  jnz     short loc_180029E4A
0x180029e21  test    cl, cl
0x180029e23  jnz     short loc_180029E4A
0x180029e25  mov     rcx, [rbx+30h]
0x180029e29  lea     rdx, [rbx+48h]
0x180029e2d  mov     r8d, 14AEh
0x180029e33  call    LdrpLogDllState
0x180029e38  mov     rax, [rbx+98h]
0x180029e3f  xor     edi, edi
0x180029e41  mov     dword ptr [rax+38h], 9
0x180029e48  jmp     short loc_180029E6D
0x180029e4a  mov     eax, [rbx+68h]
0x180029e4d  bt      eax, 18h
0x180029e51  jb      short loc_180029E63
0x180029e53  mov     rcx, rsi
0x180029e56  call    LdrpMapAndSnapDependency
0x180029e5b  mov     rax, [rsi+28h]
0x180029e5f  mov     edi, [rax]
0x180029e61  jmp     short loc_180029E6D
0x180029e63  mov     rcx, rbx
0x180029e66  call    LdrpCorProcessImports
0x180029e6b  mov     edi, eax
0x180029e6d  mov     eax, edi
0x180029e6f  mov     rcx, [rbp+1A0h+var_30]
0x180029e76  xor     rcx, rsp; StackCookie
0x180029e79  call    __security_check_cookie
0x180029e7e  lea     r11, [rsp+2A0h+var_20]
0x180029e86  mov     rbx, [r11+40h]
0x180029e8a  mov     rsi, [r11+48h]
0x180029e8e  mov     rsp, r11
0x180029e91  pop     r15
0x180029e93  pop     r14
0x180029e95  pop     r12
0x180029e97  pop     rdi
0x180029e98  pop     rbp
0x180029e99  retn
```
