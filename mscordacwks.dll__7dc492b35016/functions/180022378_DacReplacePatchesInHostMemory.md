# DacReplacePatchesInHostMemory

- ea: `0x180022378`
- end: `0x1800224d3`
- name: `DacReplacePatchesInHostMemory`
- size: `347`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800edd20`

## callees

- `0x180020f50`
- `0x1800210f0`
- `0x18002127c`
- `0x180022068`
- `0x180022378`
- `0x18007a074`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x180022471`
- `KERNEL32!GetCurrentProcess` at `0x180022471`
- `KERNEL32!FlushInstructionCache` at `0x180022483`
- `KERNEL32!FlushInstructionCache` at `0x180022483`

## pseudocode

```c
__int64 __fastcall DacReplacePatchesInHostMemory(unsigned __int64 *a1, __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  unsigned __int64 *v6; // rax
  __int64 v7; // rdx
  CHashTable *v8; // rsi
  unsigned __int64 v9; // rcx
  unsigned __int8 *i; // rax
  unsigned __int64 v11; // rbx
  unsigned __int64 v12; // rcx
  __int64 v13; // r9
  unsigned __int64 v14; // r8
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // rax
  _BYTE *v17; // rbx
  HANDLE CurrentProcess; // rax
  unsigned __int64 TargetAddrForHostAddr; // rax
  _QWORD *v20; // rax
  int v22; // [rsp+40h] [rbp+18h] BYREF
  int v23; // [rsp+44h] [rbp+1Ch]

  v4 = DacGlobalBase();
  if ( *(_DWORD *)DacInstantiateTypeByAddressHelper(
                    (unsigned int)*DebuggerController::g_patchTableValid[0] + v4,
                    4u,
                    1,
                    1) )
  {
    v5 = DacGlobalBase();
    v6 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper(
                               (unsigned int)*DebuggerController::g_patches + v5,
                               8u,
                               1,
                               1);
    v8 = (CHashTable *)DacInstantiateClassByVTable(*v6);
    v9 = *((_QWORD *)v8 + 3);
    if ( v9 )
    {
      v22 = 1;
      v23 = *(_DWORD *)DacInstantiateTypeByAddressHelper(v9, 4u, 1, 1);
      goto LABEL_14;
    }
    for ( i = 0; ; i = CHashTable::FindNextEntry(v8, (struct HASHFIND *)&v22) )
    {
      LOBYTE(v7) = 1;
      TargetAddrForHostAddr = DacGetTargetAddrForHostAddr(i, v7);
      v20 = DacInstantiateTypeByAddressHelper(TargetAddrForHostAddr, 0xB0u, 1, 1);
      if ( !v20 )
        return 0;
      v11 = v20[6];
      if ( v11 )
      {
        v12 = *a1;
        v13 = v20[8];
        v14 = a1[1];
        if ( *a1 )
        {
          v15 = v11 + 1;
          if ( v11 < v12 )
            goto LABEL_10;
          if ( v15 <= v14 + v12 )
            break;
          if ( v11 <= v12 )
          {
LABEL_10:
            if ( v12 < v15 )
              break;
          }
          v16 = v14 + v12 - 1;
          if ( v11 <= v16 && v16 < v15 )
            break;
        }
      }
LABEL_14:
      ;
    }
    v17 = (_BYTE *)(a2 + v11 - v12);
    *v17 = v13;
    CurrentProcess = GetCurrentProcess();
    FlushInstructionCache(CurrentProcess, v17, 1u);
    goto LABEL_14;
  }
  return 0;
}

```

## disassembly

```asm
0x180022378  mov     [rsp+arg_0], rbx
0x18002237d  mov     [rsp+arg_8], rbp
0x180022382  mov     [rsp+arg_18], rsi
0x180022387  push    rdi
0x180022388  sub     rsp, 20h
0x18002238c  mov     rbp, rdx
0x18002238f  mov     rdi, rcx
0x180022392  call    DacGlobalBase
0x180022397  mov     rcx, rax
0x18002239a  mov     r9b, 1; bool
0x18002239d  mov     rax, cs:?g_patchTableValid@DebuggerController@@0V?$__GlobalVal@H@@A; __GlobalVal<int> DebuggerController::g_patchTableValid
0x1800223a4  mov     ebx, 4
0x1800223a9  mov     edx, ebx; unsigned int
0x1800223ab  mov     r8d, [rax]
0x1800223ae  add     rcx, r8; unsigned __int64
0x1800223b1  mov     r8b, r9b; bool
0x1800223b4  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800223b9  cmp     dword ptr [rax], 0
0x1800223bc  jz      loc_1800224BC
0x1800223c2  call    DacGlobalBase
0x1800223c7  mov     rcx, rax
0x1800223ca  mov     r9b, 1; bool
0x1800223cd  mov     rax, cs:?g_patches@DebuggerController@@0V?$__GlobalPtr@PEAVDebuggerPatchTable@@V?$__VPtr@VDebuggerPatchTable@@@@@@A; __GlobalPtr<DebuggerPatchTable *,__VPtr<DebuggerPatchTable>> DebuggerController::g_patches
0x1800223d4  mov     r8b, r9b; bool
0x1800223d7  mov     edx, [rax]
0x1800223d9  add     rcx, rdx; unsigned __int64
0x1800223dc  lea     edx, [rbx+4]; unsigned int
0x1800223df  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800223e4  mov     r8b, 1
0x1800223e7  lea     edx, [rbx+2Ch]
0x1800223ea  mov     rcx, [rax]; unsigned __int64
0x1800223ed  call    DacInstantiateClassByVTable
0x1800223f2  mov     rsi, rax
0x1800223f5  mov     rcx, [rax+18h]; unsigned __int64
0x1800223f9  test    rcx, rcx
0x1800223fc  jnz     short loc_180022405
0x1800223fe  xor     eax, eax
0x180022400  jmp     loc_180022496
0x180022405  mov     r9b, 1; bool
0x180022408  mov     [rsp+28h+arg_10], 1
0x180022410  mov     r8b, r9b; bool
0x180022413  mov     edx, ebx; unsigned int
0x180022415  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18002241a  mov     ecx, [rax]
0x18002241c  mov     [rsp+28h+arg_14], ecx
0x180022420  jmp     short loc_180022489
0x180022422  mov     rbx, [rax+30h]
0x180022426  test    rbx, rbx
0x180022429  jz      short loc_180022489
0x18002242b  mov     rcx, [rdi]
0x18002242e  mov     r9, [rax+40h]
0x180022432  mov     r8, [rdi+8]
0x180022436  test    rcx, rcx
0x180022439  jz      short loc_180022489
0x18002243b  lea     rdx, [rbx+1]
0x18002243f  cmp     rbx, rcx
0x180022442  jb      short loc_180022452
0x180022444  lea     rax, [r8+rcx]
0x180022448  cmp     rdx, rax
0x18002244b  jbe     short loc_180022468
0x18002244d  cmp     rbx, rcx
0x180022450  ja      short loc_180022457
0x180022452  cmp     rcx, rdx
0x180022455  jb      short loc_180022468
0x180022457  lea     rax, [rcx-1]
0x18002245b  add     rax, r8
0x18002245e  cmp     rbx, rax
0x180022461  ja      short loc_180022489
0x180022463  cmp     rax, rdx
0x180022466  jnb     short loc_180022489
0x180022468  sub     rbx, rcx
0x18002246b  add     rbx, rbp
0x18002246e  mov     [rbx], r9b
0x180022471  call    cs:__imp_GetCurrentProcess
0x180022477  mov     r8d, 1; dwSize
0x18002247d  mov     rdx, rbx; lpBaseAddress
0x180022480  mov     rcx, rax; hProcess
0x180022483  call    cs:__imp_FlushInstructionCache
0x180022489  lea     rdx, [rsp+28h+arg_10]; struct HASHFIND *
0x18002248e  mov     rcx, rsi; this
0x180022491  call    ?FindNextEntry@CHashTable@@QEAAPEAEPEAUHASHFIND@@@Z; CHashTable::FindNextEntry(HASHFIND *)
0x180022496  mov     dl, 1
0x180022498  mov     rcx, rax
0x18002249b  call    DacGetTargetAddrForHostAddr
0x1800224a0  mov     r9b, 1; bool
0x1800224a3  mov     edx, 0B0h; unsigned int
0x1800224a8  mov     r8b, r9b; bool
0x1800224ab  mov     rcx, rax; unsigned __int64
0x1800224ae  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800224b3  test    rax, rax
0x1800224b6  jnz     loc_180022422
0x1800224bc  mov     rbx, [rsp+28h+arg_0]
0x1800224c1  xor     eax, eax
0x1800224c3  mov     rbp, [rsp+28h+arg_8]
0x1800224c8  mov     rsi, [rsp+28h+arg_18]
0x1800224cd  add     rsp, 20h
0x1800224d1  pop     rdi
0x1800224d2  retn
```
