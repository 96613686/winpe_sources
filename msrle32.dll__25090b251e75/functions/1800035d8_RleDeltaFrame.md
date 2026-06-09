# RleDeltaFrame

- ea: `0x1800035d8`
- end: `0x180003756`
- name: `RleDeltaFrame`
- size: `382`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, __int64, __int64, __int64, int, int, int, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002250`
- `0x180002954`

## callees

- `0x180002ee8`
- `0x1800035d8`

## pseudocode

```c
__int64 __fastcall RleDeltaFrame(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        int a8,
        int a9,
        int a10,
        int a11,
        int a12,
        int a13)
{
  int v17; // r15d
  int v18; // ebp
  int v19; // r8d
  int v20; // r12d
  int v21; // eax
  int v22; // r14d
  int v23; // r10d
  int v24; // edi
  __int64 v25; // rdx
  int v26; // eax
  __int64 result; // rax

  if ( a6 )
  {
    v17 = -1;
    v18 = *(_DWORD *)(a6 + 8);
    v19 = a8;
    v20 = 4;
    if ( a12 )
      v17 = a12;
    if ( a13 )
      v20 = a13;
    v21 = a9;
    if ( a9 <= 0 )
      v21 = *(_DWORD *)(a6 + 8);
    v22 = v18 - a8;
    if ( v18 - a8 >= v21 )
      v22 = v21;
    if ( *(_WORD *)(a6 + 14) == 8 && !*(_DWORD *)(a6 + 16) )
    {
      v23 = a7;
      v24 = 0;
      if ( a8 > 0 )
      {
        v23 = a8 * (((unsigned int)(8 * *(_DWORD *)(a6 + 4) + 31) >> 3) & 0x1FFFFFFC) + a7;
        if ( a4 )
        {
          LODWORD(v25) = a5 + a8 * (((unsigned int)(8 * *(_DWORD *)(a4 + 4) + 31) >> 3) & 0x1FFFFFFC);
          goto LABEL_16;
        }
      }
      v25 = a5 & -(__int64)(a4 != 0);
      if ( a8 <= 0 )
      {
LABEL_20:
        *(_DWORD *)(a1 + 8) = v22;
        if ( (unsigned int)DeltaFrameC(a1, v25, v23, a2, a3, v17, v20, (__int64)pMem, a10, a11) )
        {
          *(_DWORD *)(a1 + 20) += v24;
          result = 1;
          *(_DWORD *)(a1 + 8) = v18;
          return result;
        }
      }
      else
      {
        while ( 1 )
        {
LABEL_16:
          v26 = 255;
          if ( v19 < 255 )
            v26 = v19;
          if ( a3 < 4 )
            break;
          *(_WORD *)a2 = 512;
          a3 -= 4;
          *(_BYTE *)(a2 + 2) = 0;
          v19 -= v26;
          *(_BYTE *)(a2 + 3) = v26;
          v24 += 4;
          a2 += 4;
          if ( v19 <= 0 )
            goto LABEL_20;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800035d8  push    rbx
0x1800035da  push    rbp
0x1800035db  push    rsi
0x1800035dc  push    rdi
0x1800035dd  push    r12
0x1800035df  push    r14
0x1800035e1  push    r15
0x1800035e3  sub     rsp, 50h
0x1800035e7  mov     rbx, rcx
0x1800035ea  mov     r11, r9
0x1800035ed  mov     rcx, [rsp+88h+arg_28]
0x1800035f5  mov     esi, r8d
0x1800035f8  mov     r9, rdx
0x1800035fb  test    rcx, rcx
0x1800035fe  jz      loc_180003745
0x180003604  mov     eax, [rsp+88h+arg_58]
0x18000360b  or      r15d, 0FFFFFFFFh
0x18000360f  mov     ebp, [rcx+8]
0x180003612  test    eax, eax
0x180003614  mov     r8d, [rsp+88h+arg_38]
0x18000361c  mov     r12d, 4
0x180003622  cmovnz  r15d, eax
0x180003626  mov     r14d, ebp
0x180003629  mov     eax, [rsp+88h+arg_60]
0x180003630  test    eax, eax
0x180003632  cmovnz  r12d, eax
0x180003636  mov     eax, [rsp+88h+arg_40]
0x18000363d  test    eax, eax
0x18000363f  cmovle  eax, ebp
0x180003642  sub     r14d, r8d
0x180003645  cmp     r14d, eax
0x180003648  cmovge  r14d, eax
0x18000364c  cmp     word ptr [rcx+0Eh], 8
0x180003651  jnz     loc_180003745
0x180003657  cmp     dword ptr [rcx+10h], 0
0x18000365b  jnz     loc_180003745
0x180003661  mov     r10, [rsp+88h+arg_30]
0x180003669  xor     edi, edi
0x18000366b  test    r8d, r8d
0x18000366e  jle     short loc_1800036AE
0x180003670  mov     eax, [rcx+4]
0x180003673  mov     ecx, 1FFFFFFCh
0x180003678  lea     eax, ds:1Fh[rax*8]
0x18000367f  shr     eax, 3
0x180003682  and     eax, ecx
0x180003684  imul    eax, r8d
0x180003688  add     r10, rax
0x18000368b  test    r11, r11
0x18000368e  jz      short loc_1800036AE
0x180003690  mov     eax, [r11+4]
0x180003694  lea     edx, ds:1Fh[rax*8]
0x18000369b  shr     edx, 3
0x18000369e  and     edx, ecx
0x1800036a0  imul    edx, r8d
0x1800036a4  add     rdx, [rsp+88h+arg_20]
0x1800036ac  jmp     short loc_1800036C1
0x1800036ae  neg     r11
0x1800036b1  sbb     rdx, rdx
0x1800036b4  and     rdx, [rsp+88h+arg_20]
0x1800036bc  test    r8d, r8d
0x1800036bf  jle     short loc_1800036F5
0x1800036c1  mov     ecx, 0FFh
0x1800036c6  cmp     r8d, ecx
0x1800036c9  mov     eax, ecx
0x1800036cb  cmovl   eax, r8d
0x1800036cf  cmp     esi, 4
0x1800036d2  jb      short loc_180003745
0x1800036d4  mov     word ptr [r9], 200h
0x1800036da  add     esi, 0FFFFFFFCh
0x1800036dd  mov     byte ptr [r9+2], 0
0x1800036e2  sub     r8d, eax
0x1800036e5  mov     [r9+3], al
0x1800036e9  add     edi, 4
0x1800036ec  add     r9, 4
0x1800036f0  test    r8d, r8d
0x1800036f3  jg      short loc_1800036C6
0x1800036f5  mov     eax, [rsp+88h+arg_50]
0x1800036fc  mov     r8, r10
0x1800036ff  mov     [rsp+88h+var_40], eax
0x180003703  mov     rcx, rbx
0x180003706  mov     eax, [rsp+88h+arg_48]
0x18000370d  mov     [rsp+88h+var_48], eax
0x180003711  mov     [rbx+8], r14d
0x180003715  mov     rax, cs:pMem
0x18000371c  mov     [rsp+88h+var_50], rax
0x180003721  mov     [rsp+88h+var_58], r12d
0x180003726  mov     [rsp+88h+var_60], r15d
0x18000372b  mov     [rsp+88h+var_68], esi
0x18000372f  call    DeltaFrameC
0x180003734  test    eax, eax
0x180003736  jz      short loc_180003745
0x180003738  add     [rbx+14h], edi
0x18000373b  mov     eax, 1
0x180003740  mov     [rbx+8], ebp
0x180003743  jmp     short loc_180003747
0x180003745  xor     eax, eax
0x180003747  add     rsp, 50h
0x18000374b  pop     r15
0x18000374d  pop     r14
0x18000374f  pop     r12
0x180003751  pop     rdi
0x180003752  pop     rsi
0x180003753  pop     rbp
0x180003754  pop     rbx
0x180003755  retn
```
