# PAUpdateNFAData

- ea: `0x18002b314`
- end: `0x18002b42f`
- name: `PAUpdateNFAData`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x18002d8c4`

## callees

- `0x180007584`
- `0x180009314`
- `0x18000cfdc`
- `0x18001cc18`
- `0x18002a484`
- `0x18002ada0`
- `0x18002ae7c`
- `0x18002b238`
- `0x18002b314`

## pseudocode

```c
__int64 __fastcall PAUpdateNFAData(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        unsigned int a6)
{
  __int64 result; // rax
  __int64 v7; // rdi
  unsigned int v12; // esi
  __int64 v13; // rbx
  __int64 NFAData; // rax
  __int64 v15; // rbp
  __int64 v16[11]; // [rsp+30h] [rbp-58h] BYREF
  int v17; // [rsp+A0h] [rbp+18h] BYREF

  result = 0;
  v7 = 0;
  if ( a3 )
  {
    v12 = a6;
    do
    {
      v13 = *(_QWORD *)(a2 + 8 * v7);
      v16[0] = v13;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_47679c2dfd963daebcc0d8b26e9f494e_Traceguids, v13 + 8);
      NFAData = FindNFAData(v13, a4, a5);
      v15 = NFAData;
      if ( NFAData )
      {
        v17 = 0;
        PAUpdateAuthMethod(a1, NFAData, v13, &v17, v12);
        if ( !v17 )
          PAUpdateMMFilters(a1, v15, v13, v12);
        result = PAProcessQMNFAUpdate(v15, v13, v12);
      }
      else
      {
        PAAddMMAuthMethods(v16, 1, v12);
        PAAddMMFilterSpecs(a1, v13, v12);
        result = PAAddQMInfoForNFA(v13, v12);
      }
      v7 = (unsigned int)(v7 + 1);
    }
    while ( (unsigned int)v7 < a3 );
  }
  return result;
}

```

## disassembly

```asm
0x18002b314  push    rbx
0x18002b316  push    rbp
0x18002b317  push    rsi
0x18002b318  push    rdi
0x18002b319  push    r12
0x18002b31b  push    r13
0x18002b31d  push    r14
0x18002b31f  push    r15
0x18002b321  sub     rsp, 48h
0x18002b325  xor     eax, eax
0x18002b327  xor     edi, edi
0x18002b329  mov     r13, r9
0x18002b32c  mov     r15d, r8d
0x18002b32f  mov     r12, rdx
0x18002b332  mov     r14, rcx
0x18002b335  test    r8d, r8d
0x18002b338  jz      loc_18002B41E
0x18002b33e  mov     esi, [rsp+88h+arg_28]
0x18002b345  mov     rbx, [r12+rdi*8]
0x18002b349  mov     [rsp+88h+var_58], rbx
0x18002b34e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b355  lea     rax, WPP_GLOBAL_Control
0x18002b35c  cmp     rcx, rax
0x18002b35f  jz      short loc_18002B380
0x18002b361  test    byte ptr [rcx+1Ch], 4
0x18002b365  jz      short loc_18002B380
0x18002b367  mov     rcx, [rcx+10h]
0x18002b36b  lea     r9, [rbx+8]
0x18002b36f  mov     edx, 0Dh
0x18002b374  lea     r8, WPP_47679c2dfd963daebcc0d8b26e9f494e_Traceguids
0x18002b37b  call    WPP_SF__guid_
0x18002b380  mov     r8d, [rsp+88h+arg_20]
0x18002b388  mov     rdx, r13
0x18002b38b  mov     rcx, rbx
0x18002b38e  call    FindNFAData
0x18002b393  mov     rbp, rax
0x18002b396  test    rax, rax
0x18002b399  jnz     short loc_18002B3C5
0x18002b39b  mov     r8d, esi
0x18002b39e  lea     edx, [rax+1]
0x18002b3a1  lea     rcx, [rsp+88h+var_58]
0x18002b3a6  call    PAAddMMAuthMethods
0x18002b3ab  mov     r8d, esi
0x18002b3ae  mov     rdx, rbx
0x18002b3b1  mov     rcx, r14
0x18002b3b4  call    PAAddMMFilterSpecs
0x18002b3b9  mov     edx, esi
0x18002b3bb  mov     rcx, rbx
0x18002b3be  call    PAAddQMInfoForNFA
0x18002b3c3  jmp     short loc_18002B413
0x18002b3c5  lea     r9, [rsp+88h+arg_10]
0x18002b3cd  mov     [rsp+88h+arg_10], 0
0x18002b3d8  mov     r8, rbx
0x18002b3db  mov     [rsp+88h+var_68], esi
0x18002b3df  mov     rdx, rbp
0x18002b3e2  mov     rcx, r14
0x18002b3e5  call    PAUpdateAuthMethod
0x18002b3ea  cmp     [rsp+88h+arg_10], 0
0x18002b3f2  jnz     short loc_18002B405
0x18002b3f4  mov     r9d, esi
0x18002b3f7  mov     r8, rbx
0x18002b3fa  mov     rdx, rbp
0x18002b3fd  mov     rcx, r14
0x18002b400  call    PAUpdateMMFilters
0x18002b405  mov     r8d, esi
0x18002b408  mov     rdx, rbx
0x18002b40b  mov     rcx, rbp
0x18002b40e  call    PAProcessQMNFAUpdate
0x18002b413  inc     edi
0x18002b415  cmp     edi, r15d
0x18002b418  jb      loc_18002B345
0x18002b41e  add     rsp, 48h
0x18002b422  pop     r15
0x18002b424  pop     r14
0x18002b426  pop     r13
0x18002b428  pop     r12
0x18002b42a  pop     rdi
0x18002b42b  pop     rsi
0x18002b42c  pop     rbp
0x18002b42d  pop     rbx
0x18002b42e  retn
```
