# LdrResolveDelayLoadedAPI

- ea: `0x1800bc100`
- end: `0x1800bc27f`
- name: `LdrResolveDelayLoadedAPI`
- size: `383`
- prototype: `__int64 __usercall@<rax>(char ArgList@<cl>, __int64, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x18002a5c0`
- `0x18010e7e0`

## callees

- `0x18001eb80`
- `0x180054000`
- `0x180067210`
- `0x1800bc100`
- `0x1800bc288`
- `0x1800bc3b0`
- `0x1800ea628`
- `0x18015bcfc`

## string_xrefs

- `0x1800bc253`: `LdrResolveDelayLoadedAPI:Unable to locate DLL based at 0x%p.Status = 0x%x\n`
- `0x1800bc215`: `LdrResolveDelayLoadedAPI:Unable to unsuppress the export suppressed functions that are imported in the DLL based at 0x%p.Status = 0x%x\n`

## pseudocode

```c
__int64 __fastcall LdrResolveDelayLoadedAPI(__int64 ArgList, _BYTE *a2, int a3, int a4, __int64 *a5, int a6)
{
  int v7; // r12d
  __int64 v9; // rsi
  __int64 v11; // rbx
  __int64 v12; // [rsp+40h] [rbp-38h] BYREF

  v7 = (int)a2;
  v12 = 0;
  v9 = 0;
  if ( ((a6 & 0xFFFFDFFF) == 8 || (~((LdrpPolicyBits & 4 | 0x7B) << 8) & a6) == 0) && (*a2 & 1) != 0 )
  {
    if ( (int)LdrpFindLoadedDllByHandle(ArgList, &v12, 0) < 0 )
    {
      LdrpLogInternal(
        (int)"minkernel\\ldr\\ldrdload.c",
        1347,
        (int)"LdrResolveDelayLoadedAPI",
        0,
        "LdrResolveDelayLoadedAPI:Unable to locate DLL based at 0x%p.Status = 0x%x\n",
        ArgList);
    }
    else
    {
      v9 = *a5;
      v11 = v12;
      if ( *a5 - *(_QWORD *)(v12 + 48) < (unsigned __int64)*(unsigned int *)(v12 + 64) )
      {
        if ( (*(_DWORD *)(v12 + 104) & 0x8000) != 0 )
        {
          v9 = LdrpHandleProtectedDelayload(v12, v7, a3, a4, (__int64)a5, a6);
        }
        else
        {
          v9 = LdrpHandleUnprotectedDelayLoad(v12, v7, a3, a4, (__int64)a5, a6);
          if ( v9
            && (unsigned int)LdrControlFlowGuardEnforcedWithExportSuppression()
            && (int)LdrpUnsuppressAddressTakenIat(
                      ArgList,
                      (unsigned int)((_DWORD)a5 - ArgList),
                      (unsigned int)((_DWORD)a5 - ArgList)) < 0 )
          {
            LdrpLogInternal(
              (int)"minkernel\\ldr\\ldrdload.c",
              1325,
              (int)"LdrResolveDelayLoadedAPI",
              0,
              "LdrResolveDelayLoadedAPI:Unable to unsuppress the export suppressed functions that are imported in the DLL"
              " based at 0x%p.Status = 0x%x\n",
              ArgList);
          }
        }
      }
      LdrpDereferenceModule(v11);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x1800bc100  mov     rax, rsp
0x1800bc103  mov     [rax+8], rbx
0x1800bc107  mov     [rax+10h], rsi
0x1800bc10b  mov     [rax+18h], r8
0x1800bc10f  push    rdi
0x1800bc110  push    r12
0x1800bc112  push    r13
0x1800bc114  push    r14
0x1800bc116  push    r15
0x1800bc118  sub     rsp, 50h
0x1800bc11c  mov     r13, r9
0x1800bc11f  mov     r12, rdx
0x1800bc122  mov     r14, rcx
0x1800bc125  mov     qword ptr [rax-38h], 0
0x1800bc12d  xor     esi, esi
0x1800bc12f  mov     r15d, [rsp+78h+arg_28]
0x1800bc137  mov     eax, r15d
0x1800bc13a  btr     eax, 0Dh
0x1800bc13e  cmp     eax, 8
0x1800bc141  jz      short loc_1800BC159
0x1800bc143  mov     eax, cs:LdrpPolicyBits
0x1800bc149  and     eax, 4
0x1800bc14c  or      eax, 7Bh
0x1800bc14f  shl     eax, 8
0x1800bc152  not     eax
0x1800bc154  test    r15d, eax
0x1800bc157  jnz     short loc_1800BC15E
0x1800bc159  test    byte ptr [rdx], 1
0x1800bc15c  jnz     short loc_1800BC17C
0x1800bc15e  mov     rax, rsi
0x1800bc161  lea     r11, [rsp+78h+var_28]
0x1800bc166  mov     rbx, [r11+30h]
0x1800bc16a  mov     rsi, [r11+38h]
0x1800bc16e  mov     rsp, r11
0x1800bc171  pop     r15
0x1800bc173  pop     r14
0x1800bc175  pop     r13
0x1800bc177  pop     r12
0x1800bc179  pop     rdi
0x1800bc17a  retn
0x1800bc17c  xor     r8d, r8d
0x1800bc17f  lea     rdx, [rsp+78h+var_38]
0x1800bc184  call    LdrpFindLoadedDllByHandle
0x1800bc189  test    eax, eax
0x1800bc18b  js      loc_1800BC24A
0x1800bc191  mov     rdi, [rsp+78h+arg_20]
0x1800bc199  mov     rsi, [rdi]
0x1800bc19c  mov     rcx, rsi
0x1800bc19f  mov     rbx, [rsp+78h+var_38]
0x1800bc1a4  sub     rcx, [rbx+30h]
0x1800bc1a8  mov     eax, [rbx+40h]
0x1800bc1ab  cmp     rcx, rax
0x1800bc1ae  jnb     loc_1800BC23D
0x1800bc1b4  mov     eax, [rbx+68h]
0x1800bc1b7  mov     dword ptr [rsp+78h+ArgList], r15d
0x1800bc1bc  mov     r9, r13
0x1800bc1bf  mov     r8, [rsp+78h+arg_10]
0x1800bc1c7  mov     rdx, r12
0x1800bc1ca  mov     rcx, rbx
0x1800bc1cd  mov     [rsp+78h+Format], rdi
0x1800bc1d2  bt      eax, 0Fh
0x1800bc1d6  jnb     short loc_1800BC1E2
0x1800bc1d8  call    LdrpHandleProtectedDelayload
0x1800bc1dd  mov     rsi, rax
0x1800bc1e0  jmp     short loc_1800BC23D
0x1800bc1e2  call    LdrpHandleUnprotectedDelayLoad
0x1800bc1e7  mov     rsi, rax
0x1800bc1ea  test    rax, rax
0x1800bc1ed  jz      short loc_1800BC23D
0x1800bc1ef  call    LdrControlFlowGuardEnforcedWithExportSuppression
0x1800bc1f4  test    eax, eax
0x1800bc1f6  jz      short loc_1800BC23D
0x1800bc1f8  sub     edi, r14d
0x1800bc1fb  mov     r8d, edi
0x1800bc1fe  mov     edx, edi
0x1800bc200  mov     rcx, r14
0x1800bc203  call    LdrpUnsuppressAddressTakenIat
0x1800bc208  test    eax, eax
0x1800bc20a  jns     short loc_1800BC23D
0x1800bc20c  mov     [rsp+78h+var_48], eax
0x1800bc210  mov     qword ptr [rsp+78h+ArgList], r14; ArgList
0x1800bc215  lea     rax, aLdrresolvedela_1; "LdrResolveDelayLoadedAPI:Unable to unsu"...
0x1800bc21c  mov     [rsp+78h+Format], rax; Format
0x1800bc221  xor     r9d, r9d; int
0x1800bc224  lea     r8, aLdrresolvedela_3; "LdrResolveDelayLoadedAPI"
0x1800bc22b  mov     edx, 52Dh; int
0x1800bc230  lea     rcx, aMinkernelLdrLd; "minkernel\\ldr\\ldrdload.c"
0x1800bc237  call    LdrpLogInternal
0x1800bc23c  nop
0x1800bc23d  mov     rcx, rbx
0x1800bc240  call    LdrpDereferenceModule
0x1800bc245  jmp     loc_1800BC15E
0x1800bc24a  mov     [rsp+78h+var_48], eax
0x1800bc24e  mov     qword ptr [rsp+78h+ArgList], r14; ArgList
0x1800bc253  lea     rax, aLdrresolvedela_2; "LdrResolveDelayLoadedAPI:Unable to loca"...
0x1800bc25a  mov     [rsp+78h+Format], rax; Format
0x1800bc25f  xor     r9d, r9d; int
0x1800bc262  lea     r8, aLdrresolvedela_3; "LdrResolveDelayLoadedAPI"
0x1800bc269  mov     edx, 543h; int
0x1800bc26e  lea     rcx, aMinkernelLdrLd; "minkernel\\ldr\\ldrdload.c"
0x1800bc275  call    LdrpLogInternal
0x1800bc27a  jmp     loc_1800BC15E
0x1801676ec  push    rbp
0x1801676ee  sub     rsp, 40h
0x1801676f2  mov     rbp, rdx
0x1801676f5  mov     rcx, [rbp+40h]
0x1801676f9  add     rsp, 40h
0x1801676fd  pop     rbp
0x1801676fe  jmp     LdrpDereferenceModule
```
