# HalpInterruptSetDestinationInternal

- ea: `0x1403a8374`
- end: `0x1403a85bc`
- name: `HalpInterruptSetDestinationInternal`
- size: `584`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1403a39d0`

## callees

- `0x1403374a4`
- `0x1403a2f60`
- `0x1403a3d20`
- `0x1403a47e0`
- `0x1403a8374`
- `0x1403a85c4`
- `0x1403a8678`
- `0x140541bf0`

## string_xrefs

- `0x1403a84ef`: `minkernel\hals\lib\interrupts\common\connect.c`
- `0x1403a8512`: `minkernel\hals\lib\interrupts\common\connect.c`
- `0x1403a8572`: `minkernel\hals\lib\interrupts\common\connect.c`

## pseudocode

```c
__int64 __fastcall HalpInterruptSetDestinationInternal(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rax
  ULONG_PTR v6; // rax
  ULONG_PTR v7; // rdi
  __int64 *i; // rbx
  int v9; // edx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r15
  __int64 v14; // rbp
  __int128 v15; // xmm6
  __int128 v16; // xmm7
  __int128 v17; // xmm8
  __int64 v18; // xmm9_8
  __int64 *v19; // r14
  int v20; // r8d
  int v22; // edx
  __int64 v23; // rcx
  signed __int32 v24[8]; // [rsp+0h] [rbp-98h] BYREF
  int v25; // [rsp+28h] [rbp-70h]
  __int64 v26; // [rsp+A0h] [rbp+8h] BYREF

  v26 = *a1;
  HalpInterruptApplyOverrides(&v26, 0, 0);
  LODWORD(v5) = v26;
  while ( 2 )
  {
    v6 = HalpInterruptLookupController((unsigned int)v5);
    v7 = v6;
    if ( v6 )
    {
      if ( (*(_DWORD *)(v6 + 248) & 2) != 0 )
        KeBugCheckEx(0x5Cu, 0x200u, HalpInterruptLastProblem, v6, 0x7931847u);
      for ( i = *(__int64 **)(v6 + 264); ; i = (__int64 *)*i )
      {
        if ( i == (__int64 *)(v6 + 264) )
          goto LABEL_16;
        v9 = *((_DWORD *)i + 5);
        if ( v9 <= SHIDWORD(v26) && *((_DWORD *)i + 6) > SHIDWORD(v26) )
          break;
      }
      if ( !i )
      {
LABEL_16:
        v25 = 1075;
        v22 = 18;
        goto LABEL_17;
      }
      v10 = (unsigned int)(HIDWORD(v26) - v9);
      v11 = v10;
      v12 = 2 * v10;
      if ( *(_BYTE *)(i[6] + 8 * v12) )
      {
        HalpInterruptSetProblemEx(v6, 19, 0, -1, (__int64)"minkernel\\hals\\lib\\interrupts\\common\\connect.c", 1088);
        return (unsigned int)-1073741811;
      }
      else
      {
        v13 = 56 * v11;
        v14 = 56 * v11 + i[5];
        v15 = *(_OWORD *)v14;
        v16 = *(_OWORD *)(v14 + 16);
        v17 = *(_OWORD *)(v14 + 32);
        v18 = *(_QWORD *)(v14 + 48);
        HalpInterruptDestinationToTarget(v12, a2, v14 + 24);
        v19 = (__int64 *)(v14 + 16);
        HalpInterruptFindBestRouting(&v26, *(_QWORD *)a3, v14 + 16);
        _InterlockedOr(v24, 0);
        v20 = HalpInterruptSetLineStateInternal(v7, &v26, v14);
        if ( v20 < 0 )
        {
          HalpInterruptSetProblemEx(
            v7,
            7,
            v20,
            -1,
            (__int64)"minkernel\\hals\\lib\\interrupts\\common\\connect.c",
            1127);
          v23 = i[5];
          *(_OWORD *)(v13 + v23) = v15;
          *(_OWORD *)(v13 + v23 + 16) = v16;
          *(_OWORD *)(v13 + v23 + 32) = v17;
          *(_QWORD *)(v13 + v23 + 48) = v18;
        }
        else if ( *(_DWORD *)(v14 + 20) != *(_DWORD *)(a3 + 4) || *(_DWORD *)v19 != *(_DWORD *)a3 )
        {
          v5 = *v19;
          v26 = *v19;
          continue;
        }
      }
    }
    else
    {
      v25 = 1051;
      v22 = 17;
LABEL_17:
      HalpInterruptSetProblemEx(v6, v22, 0, -1, (__int64)"minkernel\\hals\\lib\\interrupts\\common\\connect.c", v25);
      return (unsigned int)-1073741275;
    }
    return (unsigned int)v20;
  }
}

```

## disassembly

```asm
0x1403a8374  mov     r11, rsp
0x1403a8377  mov     [r11+10h], rbx
0x1403a837b  mov     [r11+18h], rbp
0x1403a837f  push    rsi
0x1403a8380  push    rdi
0x1403a8381  push    r12
0x1403a8383  push    r14
0x1403a8385  push    r15
0x1403a8387  sub     rsp, 70h
0x1403a838b  mov     rax, [rcx]
0x1403a838e  mov     rsi, r8
0x1403a8391  movaps  [rsp+98h+var_38], xmm6
0x1403a8396  lea     rcx, [r11+8]
0x1403a839a  movaps  [rsp+98h+var_48], xmm7
0x1403a839f  mov     r12, rdx
0x1403a83a2  movaps  xmmword ptr [r11-58h], xmm8
0x1403a83a7  xor     r8d, r8d
0x1403a83aa  xor     edx, edx
0x1403a83ac  movaps  xmmword ptr [r11-68h], xmm9
0x1403a83b1  mov     [r11+8], rax
0x1403a83b5  call    HalpInterruptApplyOverrides
0x1403a83ba  mov     rax, [rsp+98h+arg_0]
0x1403a83c2  mov     ecx, eax
0x1403a83c4  call    HalpInterruptLookupController
0x1403a83c9  mov     rdi, rax
0x1403a83cc  test    rax, rax
0x1403a83cf  jz      loc_1403A8558
0x1403a83d5  mov     eax, [rax+0F8h]
0x1403a83db  test    al, 2
0x1403a83dd  jnz     loc_1403A8599
0x1403a83e3  mov     eax, dword ptr [rsp+98h+arg_0+4]
0x1403a83ea  lea     rcx, [rdi+108h]
0x1403a83f1  mov     rbx, [rcx]
0x1403a83f4  cmp     rbx, rcx
0x1403a83f7  jz      loc_1403A84E2
0x1403a83fd  mov     edx, [rbx+14h]
0x1403a8400  cmp     edx, eax
0x1403a8402  jg      short loc_1403A8409
0x1403a8404  cmp     [rbx+18h], eax
0x1403a8407  jg      short loc_1403A840E
0x1403a8409  mov     rbx, [rbx]
0x1403a840c  jmp     short loc_1403A83F4
0x1403a840e  test    rbx, rbx
0x1403a8411  jz      loc_1403A84E2
0x1403a8417  sub     eax, edx
0x1403a8419  mov     ecx, eax
0x1403a841b  mov     edx, eax
0x1403a841d  add     rcx, rcx
0x1403a8420  mov     rax, [rbx+30h]
0x1403a8424  cmp     byte ptr [rax+rcx*8], 0
0x1403a8428  jnz     loc_1403A8567
0x1403a842e  mov     rbp, [rbx+28h]
0x1403a8432  imul    r15, rdx, 38h ; '8'
0x1403a8436  mov     rdx, r12
0x1403a8439  add     rbp, r15
0x1403a843c  movups  xmm6, xmmword ptr [rbp+0]
0x1403a8440  lea     r8, [rbp+18h]
0x1403a8444  movups  xmm7, xmmword ptr [rbp+10h]
0x1403a8448  movups  xmm8, xmmword ptr [rbp+20h]
0x1403a844d  movsd   xmm9, qword ptr [rbp+30h]
0x1403a8453  call    HalpInterruptDestinationToTarget
0x1403a8458  mov     rdx, [rsi]
0x1403a845b  lea     r14, [rbp+10h]
0x1403a845f  mov     r8, r14
0x1403a8462  lea     rcx, [rsp+98h+arg_0]
0x1403a846a  call    HalpInterruptFindBestRouting
0x1403a846f  lock or [rsp+98h+var_98], 0
0x1403a8474  mov     r8, rbp
0x1403a8477  lea     rdx, [rsp+98h+arg_0]
0x1403a847f  mov     rcx, rdi
0x1403a8482  call    HalpInterruptSetLineStateInternal
0x1403a8487  mov     r8d, eax
0x1403a848a  test    eax, eax
0x1403a848c  js      loc_1403A8512
0x1403a8492  mov     ecx, [rsi+4]
0x1403a8495  cmp     [rbp+14h], ecx
0x1403a8498  jz      short loc_1403A84AA
0x1403a849a  mov     rax, [r14]
0x1403a849d  mov     [rsp+98h+arg_0], rax
0x1403a84a5  jmp     loc_1403A83C2
0x1403a84aa  mov     ecx, [rsi]
0x1403a84ac  cmp     [r14], ecx
0x1403a84af  jnz     short loc_1403A849A
0x1403a84b1  movaps  xmm6, [rsp+98h+var_38]
0x1403a84b6  lea     r11, [rsp+98h+var_28]
0x1403a84bb  mov     rbx, [r11+38h]
0x1403a84bf  mov     eax, r8d
0x1403a84c2  mov     rbp, [r11+40h]
0x1403a84c6  movaps  xmm8, xmmword ptr [r11-30h]
0x1403a84cb  movaps  xmm9, xmmword ptr [r11-40h]
0x1403a84d0  movaps  xmm7, [rsp+98h+var_48]
0x1403a84d5  mov     rsp, r11
0x1403a84d8  pop     r15
0x1403a84da  pop     r14
0x1403a84dc  pop     r12
0x1403a84de  pop     rdi
0x1403a84df  pop     rsi
0x1403a84e0  retn
0x1403a84e2  mov     [rsp+98h+var_70], 433h
0x1403a84ea  mov     edx, 12h
0x1403a84ef  lea     rax, aMinkernelHalsL_8; "minkernel\\hals\\lib\\interrupts\\commo"...
0x1403a84f6  or      r9d, 0FFFFFFFFh
0x1403a84fa  xor     r8d, r8d
0x1403a84fd  mov     [rsp+98h+BugCheckParameter4], rax
0x1403a8502  mov     rcx, rdi
0x1403a8505  call    HalpInterruptSetProblemEx
0x1403a850a  mov     r8d, 0C0000225h
0x1403a8510  jmp     short loc_1403A84B1
0x1403a8512  lea     rax, aMinkernelHalsL_8; "minkernel\\hals\\lib\\interrupts\\commo"...
0x1403a8519  mov     [rsp+98h+var_70], 467h
0x1403a8521  or      r9d, 0FFFFFFFFh
0x1403a8525  mov     [rsp+98h+BugCheckParameter4], rax
0x1403a852a  mov     edx, 7
0x1403a852f  mov     rcx, rdi
0x1403a8532  call    HalpInterruptSetProblemEx
0x1403a8537  mov     rcx, [rbx+28h]
0x1403a853b  movups  xmmword ptr [r15+rcx], xmm6
0x1403a8540  movups  xmmword ptr [r15+rcx+10h], xmm7
0x1403a8546  movups  xmmword ptr [r15+rcx+20h], xmm8
0x1403a854c  movsd   qword ptr [r15+rcx+30h], xmm9
0x1403a8553  jmp     loc_1403A84B1
0x1403a8558  mov     [rsp+98h+var_70], 41Bh
0x1403a8560  mov     edx, 11h
0x1403a8565  jmp     short loc_1403A84EF
0x1403a8567  xor     r8d, r8d
0x1403a856a  mov     [rsp+98h+var_70], 440h
0x1403a8572  lea     rax, aMinkernelHalsL_8; "minkernel\\hals\\lib\\interrupts\\commo"...
0x1403a8579  or      r9d, 0FFFFFFFFh
0x1403a857d  mov     rcx, rdi
0x1403a8580  mov     [rsp+98h+BugCheckParameter4], rax
0x1403a8585  lea     edx, [r8+13h]
0x1403a8589  call    HalpInterruptSetProblemEx
0x1403a858e  mov     r8d, 0C000000Dh
0x1403a8594  jmp     loc_1403A84B1
0x1403a8599  movsxd  r8, cs:HalpInterruptLastProblem; BugCheckParameter2
0x1403a85a0  mov     r9, rdi; BugCheckParameter3
0x1403a85a3  mov     edx, 200h; BugCheckParameter1
0x1403a85a8  mov     [rsp+98h+BugCheckParameter4], 7931847h; BugCheckParameter4
0x1403a85b1  mov     ecx, 5Ch ; '\'; BugCheckCode
0x1403a85b6  call    KeBugCheckEx
```
