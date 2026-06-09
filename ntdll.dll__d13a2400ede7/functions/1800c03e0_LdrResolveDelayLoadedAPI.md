# LdrResolveDelayLoadedAPI

- ea: `0x1800c03e0`
- end: `0x1800c055f`
- name: `LdrResolveDelayLoadedAPI`
- size: `383`
- prototype: `__int64 __usercall@<rax>(char ArgList@<cl>, __int64, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x18002a4b0`
- `0x18010fb40`

## callees

- `0x18001eb80`
- `0x1800709e0`
- `0x180083bf0`
- `0x1800c03e0`
- `0x1800c0568`
- `0x1800c0690`
- `0x1800eac88`
- `0x18015c50c`

## string_xrefs

- `0x1800c0533`: `LdrResolveDelayLoadedAPI:Unable to locate DLL based at 0x%p.Status = 0x%x\n`
- `0x1800c04f5`: `LdrResolveDelayLoadedAPI:Unable to unsuppress the export suppressed functions that are imported in the DLL based at 0x%p.Status = 0x%x\n`

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
0x1800c03e0  mov     rax, rsp
0x1800c03e3  mov     [rax+8], rbx
0x1800c03e7  mov     [rax+10h], rsi
0x1800c03eb  mov     [rax+18h], r8
0x1800c03ef  push    rdi
0x1800c03f0  push    r12
0x1800c03f2  push    r13
0x1800c03f4  push    r14
0x1800c03f6  push    r15
0x1800c03f8  sub     rsp, 50h
0x1800c03fc  mov     r13, r9
0x1800c03ff  mov     r12, rdx
0x1800c0402  mov     r14, rcx
0x1800c0405  mov     qword ptr [rax-38h], 0
0x1800c040d  xor     esi, esi
0x1800c040f  mov     r15d, [rsp+78h+arg_28]
0x1800c0417  mov     eax, r15d
0x1800c041a  btr     eax, 0Dh
0x1800c041e  cmp     eax, 8
0x1800c0421  jz      short loc_1800C0439
0x1800c0423  mov     eax, cs:LdrpPolicyBits
0x1800c0429  and     eax, 4
0x1800c042c  or      eax, 7Bh
0x1800c042f  shl     eax, 8
0x1800c0432  not     eax
0x1800c0434  test    r15d, eax
0x1800c0437  jnz     short loc_1800C043E
0x1800c0439  test    byte ptr [rdx], 1
0x1800c043c  jnz     short loc_1800C045C
0x1800c043e  mov     rax, rsi
0x1800c0441  lea     r11, [rsp+78h+var_28]
0x1800c0446  mov     rbx, [r11+30h]
0x1800c044a  mov     rsi, [r11+38h]
0x1800c044e  mov     rsp, r11
0x1800c0451  pop     r15
0x1800c0453  pop     r14
0x1800c0455  pop     r13
0x1800c0457  pop     r12
0x1800c0459  pop     rdi
0x1800c045a  retn
0x1800c045c  xor     r8d, r8d
0x1800c045f  lea     rdx, [rsp+78h+var_38]
0x1800c0464  call    LdrpFindLoadedDllByHandle
0x1800c0469  test    eax, eax
0x1800c046b  js      loc_1800C052A
0x1800c0471  mov     rdi, [rsp+78h+arg_20]
0x1800c0479  mov     rsi, [rdi]
0x1800c047c  mov     rcx, rsi
0x1800c047f  mov     rbx, [rsp+78h+var_38]
0x1800c0484  sub     rcx, [rbx+30h]
0x1800c0488  mov     eax, [rbx+40h]
0x1800c048b  cmp     rcx, rax
0x1800c048e  jnb     loc_1800C051D
0x1800c0494  mov     eax, [rbx+68h]
0x1800c0497  mov     dword ptr [rsp+78h+ArgList], r15d
0x1800c049c  mov     r9, r13
0x1800c049f  mov     r8, [rsp+78h+arg_10]
0x1800c04a7  mov     rdx, r12
0x1800c04aa  mov     rcx, rbx
0x1800c04ad  mov     [rsp+78h+Format], rdi
0x1800c04b2  bt      eax, 0Fh
0x1800c04b6  jnb     short loc_1800C04C2
0x1800c04b8  call    LdrpHandleProtectedDelayload
0x1800c04bd  mov     rsi, rax
0x1800c04c0  jmp     short loc_1800C051D
0x1800c04c2  call    LdrpHandleUnprotectedDelayLoad
0x1800c04c7  mov     rsi, rax
0x1800c04ca  test    rax, rax
0x1800c04cd  jz      short loc_1800C051D
0x1800c04cf  call    LdrControlFlowGuardEnforcedWithExportSuppression
0x1800c04d4  test    eax, eax
0x1800c04d6  jz      short loc_1800C051D
0x1800c04d8  sub     edi, r14d
0x1800c04db  mov     r8d, edi
0x1800c04de  mov     edx, edi
0x1800c04e0  mov     rcx, r14
0x1800c04e3  call    LdrpUnsuppressAddressTakenIat
0x1800c04e8  test    eax, eax
0x1800c04ea  jns     short loc_1800C051D
0x1800c04ec  mov     [rsp+78h+var_48], eax
0x1800c04f0  mov     qword ptr [rsp+78h+ArgList], r14; ArgList
0x1800c04f5  lea     rax, aLdrresolvedela_1; "LdrResolveDelayLoadedAPI:Unable to unsu"...
0x1800c04fc  mov     [rsp+78h+Format], rax; Format
0x1800c0501  xor     r9d, r9d; int
0x1800c0504  lea     r8, aLdrresolvedela_3; "LdrResolveDelayLoadedAPI"
0x1800c050b  mov     edx, 52Dh; int
0x1800c0510  lea     rcx, aMinkernelLdrLd; "minkernel\\ldr\\ldrdload.c"
0x1800c0517  call    LdrpLogInternal
0x1800c051c  nop
0x1800c051d  mov     rcx, rbx
0x1800c0520  call    LdrpDereferenceModule
0x1800c0525  jmp     loc_1800C043E
0x1800c052a  mov     [rsp+78h+var_48], eax
0x1800c052e  mov     qword ptr [rsp+78h+ArgList], r14; ArgList
0x1800c0533  lea     rax, aLdrresolvedela_2; "LdrResolveDelayLoadedAPI:Unable to loca"...
0x1800c053a  mov     [rsp+78h+Format], rax; Format
0x1800c053f  xor     r9d, r9d; int
0x1800c0542  lea     r8, aLdrresolvedela_3; "LdrResolveDelayLoadedAPI"
0x1800c0549  mov     edx, 543h; int
0x1800c054e  lea     rcx, aMinkernelLdrLd; "minkernel\\ldr\\ldrdload.c"
0x1800c0555  call    LdrpLogInternal
0x1800c055a  jmp     loc_1800C043E
0x180167fcc  push    rbp
0x180167fce  sub     rsp, 40h
0x180167fd2  mov     rbp, rdx
0x180167fd5  mov     rcx, [rbp+40h]
0x180167fd9  add     rsp, 40h
0x180167fdd  pop     rbp
0x180167fde  jmp     LdrpDereferenceModule
```
