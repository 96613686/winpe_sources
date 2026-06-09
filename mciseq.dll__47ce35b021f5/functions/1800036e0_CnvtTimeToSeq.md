# CnvtTimeToSeq

- ea: `0x1800036e0`
- end: `0x180003870`
- name: `CnvtTimeToSeq`
- size: `400`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180001810`
- `0x180001a44`
- `0x1800025fc`

## callees

- `0x1800036e0`
- `0x180003878`
- `0x180005270`
- `0x180005ff0`

## pseudocode

```c
__int64 __fastcall CnvtTimeToSeq(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 v3; // r11
  int v4; // ecx
  unsigned int v6; // r10d
  unsigned int v7; // r9d
  int v8; // edx
  int v9; // ecx
  int v10; // ecx
  int v12; // eax
  unsigned __int8 v13; // dl
  unsigned int v14; // r10d
  unsigned __int8 v15; // r8
  int v16; // eax
  unsigned __int8 v17; // dl
  unsigned int v18; // r10d
  unsigned __int8 v19; // r8
  __int64 v21; // [rsp+20h] [rbp-18h] BYREF

  v3 = a1;
  LODWORD(v21) = 0;
  v4 = *(_DWORD *)(a1 + 340);
  v6 = a2;
  v7 = *(_DWORD *)(v3 + 344);
  if ( v4 )
  {
    v8 = 1;
    if ( v7 - 4 <= 1 || v7 == 7 || v7 == 6 )
    {
      v12 = FPSDisplay(v7);
      return *(unsigned __int16 *)(a3 + 2) * (HIBYTE(v14) + (v15 + 60 * (v13 + 60 * (unsigned __int8)v14)) * v12);
    }
    else
    {
      v9 = v4 - 24;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( v10 )
        {
          if ( (unsigned int)(v10 - 4) <= 1 )
            v8 = 30;
        }
        else
        {
          v8 = 25;
        }
      }
      else
      {
        v8 = 24;
      }
      return (v8 * v6 * *(unsigned __int16 *)(a3 + 2) + 500) / 0x3E8;
    }
  }
  else if ( v7 == 16385 )
  {
    return (a2 * *(unsigned __int16 *)(a3 + 2)) >> 2;
  }
  else
  {
    if ( v7 )
    {
      v16 = FPSDisplay(v7);
      v6 = (1000 * (HIBYTE(v18) + v16 * (v19 + 60 * (v17 + 60 * (unsigned __int8)v18))) + v16 / 2) / (unsigned int)v16;
    }
    midiSeqMessage(*(_QWORD *)(v3 + 256), 0xEu, v6, &v21);
    return (unsigned int)v21;
  }
}

```

## disassembly

```asm
0x1800036e0  push    rbx
0x1800036e2  sub     rsp, 30h
0x1800036e6  mov     rax, cs:__security_cookie
0x1800036ed  xor     rax, rsp
0x1800036f0  mov     [rsp+38h+var_10], rax
0x1800036f5  mov     r11, rcx
0x1800036f8  mov     dword ptr [rsp+38h+var_18], 0
0x180003700  mov     ecx, [rcx+154h]
0x180003706  mov     rbx, r8
0x180003709  mov     r10d, edx
0x18000370c  mov     r9d, [r11+158h]
0x180003713  test    ecx, ecx
0x180003715  jz      short loc_18000377E
0x180003717  lea     eax, [r9-4]
0x18000371b  mov     edx, 1
0x180003720  cmp     eax, edx
0x180003722  jbe     loc_1800037A8
0x180003728  cmp     r9d, 7
0x18000372c  jz      short loc_1800037A8
0x18000372e  cmp     r9d, 6
0x180003732  jz      short loc_1800037A8
0x180003734  sub     ecx, 18h
0x180003737  jz      short loc_180003754
0x180003739  sub     ecx, edx
0x18000373b  jz      short loc_18000374D
0x18000373d  sub     ecx, 4
0x180003740  jz      short loc_180003746
0x180003742  cmp     ecx, edx
0x180003744  jnz     short loc_180003759
0x180003746  mov     edx, 1Eh
0x18000374b  jmp     short loc_180003759
0x18000374d  mov     edx, 19h
0x180003752  jmp     short loc_180003759
0x180003754  mov     edx, 18h
0x180003759  movzx   ecx, word ptr [r8+2]
0x18000375e  mov     eax, 10624DD3h
0x180003763  imul    ecx, r10d
0x180003767  imul    ecx, edx
0x18000376a  add     ecx, 1F4h
0x180003770  mul     ecx
0x180003772  mov     r9d, edx
0x180003775  shr     r9d, 6
0x180003779  jmp     loc_18000385A
0x18000377e  cmp     r9d, 4001h
0x180003785  jnz     short loc_1800037EA
0x180003787  lea     eax, [r9-4]
0x18000378b  cmp     eax, 2
0x18000378e  jbe     short loc_1800037A8
0x180003790  cmp     r9d, 7
0x180003794  jz      short loc_1800037A8
0x180003796  movzx   r9d, word ptr [r8+2]
0x18000379b  imul    r9d, r10d
0x18000379f  shr     r9d, 2
0x1800037a3  jmp     loc_18000385A
0x1800037a8  mov     edx, r10d
0x1800037ab  mov     r8d, r10d
0x1800037ae  mov     ecx, r9d
0x1800037b1  shr     edx, 8
0x1800037b4  shr     r8d, 10h
0x1800037b8  call    FPSDisplay
0x1800037bd  mov     r9d, eax
0x1800037c0  movzx   eax, r10b
0x1800037c4  imul    ecx, eax, 3Ch ; '<'
0x1800037c7  movzx   eax, dl
0x1800037ca  shr     r10d, 18h
0x1800037ce  add     ecx, eax
0x1800037d0  movzx   eax, r8b
0x1800037d4  imul    edx, ecx, 3Ch ; '<'
0x1800037d7  add     edx, eax
0x1800037d9  movzx   eax, word ptr [rbx+2]
0x1800037dd  imul    r9d, edx
0x1800037e1  add     r9d, r10d
0x1800037e4  imul    r9d, eax
0x1800037e8  jmp     short loc_18000385A
0x1800037ea  test    r9d, r9d
0x1800037ed  jz      short loc_18000383C
0x1800037ef  mov     r8d, r10d
0x1800037f2  shr     edx, 8
0x1800037f5  mov     ecx, r9d
0x1800037f8  shr     r8d, 10h
0x1800037fc  call    FPSDisplay
0x180003801  mov     r9d, eax
0x180003804  movzx   eax, r10b
0x180003808  imul    ecx, eax, 3Ch ; '<'
0x18000380b  movzx   eax, dl
0x18000380e  shr     r10d, 18h
0x180003812  add     ecx, eax
0x180003814  movzx   eax, r8b
0x180003818  imul    edx, ecx, 3Ch ; '<'
0x18000381b  add     edx, eax
0x18000381d  mov     eax, r9d
0x180003820  imul    edx, r9d
0x180003824  add     edx, r10d
0x180003827  imul    ecx, edx, 3E8h
0x18000382d  cdq
0x18000382e  sub     eax, edx
0x180003830  xor     edx, edx
0x180003832  sar     eax, 1
0x180003834  add     eax, ecx
0x180003836  div     r9d
0x180003839  mov     r10d, eax
0x18000383c  mov     rcx, [r11+100h]; dwUser
0x180003843  lea     r9, [rsp+38h+var_18]
0x180003848  mov     r8d, r10d
0x18000384b  mov     edx, 0Eh
0x180003850  call    midiSeqMessage
0x180003855  mov     r9d, dword ptr [rsp+38h+var_18]
0x18000385a  mov     eax, r9d
0x18000385d  mov     rcx, [rsp+38h+var_10]
0x180003862  xor     rcx, rsp; StackCookie
0x180003865  call    __security_check_cookie
0x18000386a  add     rsp, 30h
0x18000386e  pop     rbx
0x18000386f  retn
```
