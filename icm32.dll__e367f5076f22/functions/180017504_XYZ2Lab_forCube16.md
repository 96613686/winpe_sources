# XYZ2Lab_forCube16

- ea: `0x180017504`
- end: `0x1800176a8`
- name: `XYZ2Lab_forCube16`
- size: `420`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800029a4`
- `0x18001c4a0`
- `0x18003cb08`

## callees

- `0x180017504`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180017528`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180017528`

## pseudocode

```c
ULONG __fastcall XYZ2Lab_forCube16(unsigned __int16 *a1, int a2)
{
  ULONG result; // eax
  int i; // esi
  unsigned __int16 v6; // dx
  int v7; // r9d
  __int64 v8; // rax
  int v9; // r10d
  __int64 v10; // rax
  int v11; // edx
  __int64 v12; // rax
  int v13; // r9d
  int v14; // edx
  int v15; // ecx

  result = EventWrite(g_etwHandle, &CONVERT_XYZ_TO_LAB, 0, 0);
  for ( i = 0; i < a2; a1 += 3 )
  {
    v6 = a1[1];
    v7 = a1[2];
    v8 = v6 >> 7;
    if ( (unsigned int)v8 >= 0x1AF )
      v9 = 39975;
    else
      v9 = word_18003FBA0[v8] + (((v6 & 0x7F) * (word_18003FBA0[v8 + 1] - word_18003FBA0[v8]) + 63) >> 7);
    v10 = (531 * (unsigned int)*a1) >> 16;
    if ( (unsigned int)v10 >= 0x1AF )
      v11 = 39975;
    else
      v11 = word_18003FBA0[v10]
          + ((int)((((531 * (unsigned int)*a1) >> 4) & 0xFFF) * (word_18003FBA0[v10 + 1] - word_18003FBA0[v10]) + 2047) >> 12);
    v12 = (unsigned int)(9931 * v7) >> 20;
    if ( (unsigned int)v12 >= 0x1AF )
      v13 = 39975;
    else
      v13 = word_18003FBA0[v12]
          + ((int)((((unsigned int)(9931 * v7) >> 8) & 0xFFF) * (word_18003FBA0[v12 + 1] - word_18003FBA0[v12]) + 2047) >> 12);
    v14 = (431 * (v11 - v9) + 4194368) >> 7;
    if ( (v14 & 0xFFFF0000) != 0 )
    {
      if ( v14 < 0 )
      {
        LOWORD(v14) = 0;
      }
      else if ( v14 > 0xFFFF )
      {
        LOWORD(v14) = -1;
      }
    }
    v15 = (11035 * (v9 - v13) + 268439552) >> 13;
    if ( (v15 & 0xFFFF0000) != 0 )
    {
      if ( v15 >= 0 )
      {
        if ( v15 > 0xFFFF )
          LOWORD(v15) = -1;
      }
      else
      {
        LOWORD(v15) = 0;
      }
    }
    result = 2 * v9;
    if ( 2 * v9 > 0xFFFF )
      result = 0xFFFF;
    ++i;
    *a1 = result;
    a1[1] = v14;
    a1[2] = v15;
  }
  return result;
}

```

## disassembly

```asm
0x180017504  push    rbx
0x180017506  push    rbp
0x180017507  push    rsi
0x180017508  push    rdi
0x180017509  push    r12
0x18001750b  sub     rsp, 20h
0x18001750f  mov     edi, edx
0x180017511  mov     rbx, rcx
0x180017514  mov     rcx, cs:g_etwHandle; RegHandle
0x18001751b  lea     rdx, CONVERT_XYZ_TO_LAB; EventDescriptor
0x180017522  xor     r9d, r9d; UserData
0x180017525  xor     r8d, r8d; UserDataCount
0x180017528  call    cs:__imp_EventWrite
0x18001752e  xor     esi, esi
0x180017530  test    edi, edi
0x180017532  jle     loc_18001765C
0x180017538  lea     r12, word_18003FBA0
0x18001753f  mov     ebp, 0FFFFh
0x180017544  movzx   edx, word ptr [rbx+2]
0x180017548  movzx   r8d, word ptr [rbx]
0x18001754c  mov     eax, edx
0x18001754e  movzx   r9d, word ptr [rbx+4]
0x180017553  shr     eax, 7
0x180017556  cmp     eax, 1AFh
0x18001755b  jnb     loc_18001768F
0x180017561  movzx   ecx, word ptr [r12+rax*2]
0x180017566  and     edx, 7Fh
0x180017569  movzx   r10d, word ptr [r12+rax*2+2]
0x18001756f  sub     r10d, ecx
0x180017572  imul    r10d, edx
0x180017576  add     r10d, 3Fh ; '?'
0x18001757a  sar     r10d, 7
0x18001757e  add     r10d, ecx
0x180017581  imul    r8d, 213h
0x180017588  shr     r8d, 4
0x18001758c  mov     eax, r8d
0x18001758f  shr     eax, 0Ch
0x180017592  cmp     eax, 1AFh
0x180017597  jnb     loc_18001767A
0x18001759d  movzx   ecx, word ptr [r12+rax*2]
0x1800175a2  and     r8d, 0FFFh
0x1800175a9  movzx   edx, word ptr [r12+rax*2+2]
0x1800175af  sub     edx, ecx
0x1800175b1  imul    edx, r8d
0x1800175b5  add     edx, 7FFh
0x1800175bb  sar     edx, 0Ch
0x1800175be  add     edx, ecx
0x1800175c0  imul    r8d, r9d, 26CBh
0x1800175c7  shr     r8d, 8
0x1800175cb  mov     eax, r8d
0x1800175ce  shr     eax, 0Ch
0x1800175d1  cmp     eax, 1AFh
0x1800175d6  jnb     loc_180017684
0x1800175dc  movzx   ecx, word ptr [r12+rax*2]
0x1800175e1  and     r8d, 0FFFh
0x1800175e8  movzx   r9d, word ptr [r12+rax*2+2]
0x1800175ee  sub     r9d, ecx
0x1800175f1  imul    r9d, r8d
0x1800175f5  add     r9d, 7FFh
0x1800175fc  sar     r9d, 0Ch
0x180017600  add     r9d, ecx
0x180017603  sub     edx, r10d
0x180017606  imul    edx, 1AFh
0x18001760c  add     edx, 400040h
0x180017612  sar     edx, 7
0x180017615  test    edx, 0FFFF0000h
0x18001761b  jnz     short loc_180017667
0x18001761d  mov     eax, r10d
0x180017620  sub     eax, r9d
0x180017623  imul    ecx, eax, 2B1Bh
0x180017629  add     ecx, 10001000h
0x18001762f  sar     ecx, 0Dh
0x180017632  test    ecx, 0FFFF0000h
0x180017638  jnz     short loc_180017672
0x18001763a  lea     eax, [r10+r10]
0x18001763e  cmp     eax, ebp
0x180017640  cmovg   eax, ebp
0x180017643  inc     esi
0x180017645  mov     [rbx], ax
0x180017648  mov     [rbx+2], dx
0x18001764c  mov     [rbx+4], cx
0x180017650  add     rbx, 6
0x180017654  cmp     esi, edi
0x180017656  jl      loc_180017544
0x18001765c  add     rsp, 20h
0x180017660  pop     r12
0x180017662  pop     rdi
0x180017663  pop     rsi
0x180017664  pop     rbp
0x180017665  pop     rbx
0x180017666  retn
0x180017667  test    edx, edx
0x180017669  js      short loc_18001769A
0x18001766b  cmp     edx, ebp
0x18001766d  cmovg   edx, ebp
0x180017670  jmp     short loc_18001761D
0x180017672  test    ecx, ecx
0x180017674  jns     short loc_1800176A1
0x180017676  xor     ecx, ecx
0x180017678  jmp     short loc_18001763A
0x18001767a  mov     edx, 9C27h
0x18001767f  jmp     loc_1800175C0
0x180017684  mov     r9d, 9C27h
0x18001768a  jmp     loc_180017603
0x18001768f  mov     r10d, 9C27h
0x180017695  jmp     loc_180017581
0x18001769a  xor     edx, edx
0x18001769c  jmp     loc_18001761D
0x1800176a1  cmp     ecx, ebp
0x1800176a3  cmovg   ecx, ebp
0x1800176a6  jmp     short loc_18001763A
```
