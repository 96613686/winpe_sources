# ExtractAlutFromLut16

- ea: `0x180021060`
- end: `0x1800211e6`
- name: `ExtractAlutFromLut16`
- size: `390`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, TAGTYPE)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18001c308`
- `0x18001de14`

## callees

- `0x1800042e0`
- `0x18000604c`
- `0x1800060f0`
- `0x1800177ac`
- `0x180018b28`
- `0x180021060`
- `0x1800217fc`

## pseudocode

```c
__int64 __fastcall ExtractAlutFromLut16(_DWORD *a1, __int64 a2, __int64 a3, TAGTYPE a4)
{
  void *v4; // rsi
  int v7; // ecx
  int v8; // edx
  int v9; // eax
  unsigned int v10; // ecx
  unsigned int v11; // ebx
  unsigned int v12; // ebp
  int v13; // r12d
  int v14; // r13d
  void *v15; // rax
  DWORD v16; // r15d
  char v17; // dl
  __int64 v18; // r8
  DWORD pcbElement[18]; // [rsp+30h] [rbp-48h] BYREF
  __int16 v21; // [rsp+80h] [rbp+8h] BYREF
  TAGTYPE tag; // [rsp+98h] [rbp+20h]

  tag = a4;
  v4 = 0;
  v21 = 0;
  pcbElement[0] = 0;
  if ( !a1 )
  {
    v11 = 87;
    goto LABEL_22;
  }
  v7 = a1[14];
  if ( !v7 )
    goto LABEL_9;
  v8 = 0;
  v9 = a1[13];
  while ( v8 < a1[12] )
  {
    if ( v9 >= 0x7FFFFFFF / v7 )
      goto LABEL_9;
    v9 *= v7;
    ++v8;
  }
  if ( v9 >= 0x3FFFFFFF )
    goto LABEL_9;
  v10 = *(unsigned __int16 *)(a3 + 40);
  if ( v10 < 2 )
    goto LABEL_9;
  v12 = *(unsigned __int16 *)(a3 + 42);
  if ( v12 < 2 )
    goto LABEL_9;
  v13 = 2 * v9;
  v14 = 2 * a1[12] * v10 + 52;
  if ( 2 * v9 >= 0x7FFFFFFF - v14 )
    goto LABEL_9;
  pcbElement[0] = 2 * a1[13] * v12;
  v15 = (void *)SmartNewPtrClear(pcbElement[0], &v21);
  v11 = v21;
  v4 = v15;
  if ( v21 )
    goto LABEL_22;
  v16 = pcbElement[0];
  v11 = CMGetPartialProfileElement(*(HPROFILE *)a2, tag, v13 + v14, pcbElement, v15);
  if ( v11 )
    goto LABEL_22;
  if ( v16 != pcbElement[0] )
  {
LABEL_9:
    v11 = 2011;
    goto LABEL_22;
  }
  SwapShortOffset(v4, 0, pcbElement[0]);
  if ( *(_BYTE *)(a2 + 50) == v17 && *(_BYTE *)(a2 + 52) == v17 )
  {
    v11 = Fill_byte_ALUTs_from_lut16Tag(a1, v4, v18, v12);
    if ( !v11 )
    {
      a1[8] = 1024;
      a1[9] = 8;
    }
  }
  else
  {
    v11 = Fill_ushort_ALUTs_from_lut16Tag(a1, v4, v18, v12);
    if ( !v11 )
    {
      a1[8] = 1024;
      a1[9] = 16;
    }
  }
LABEL_22:
  DisposeIfPtr(v4);
  return v11;
}

```

## disassembly

```asm
0x180021060  mov     r11, rsp
0x180021063  mov     [r11+10h], rbx
0x180021067  mov     [r11+20h], r9d
0x18002106b  push    rbp
0x18002106c  push    rsi
0x18002106d  push    rdi
0x18002106e  push    r12
0x180021070  push    r13
0x180021072  push    r14
0x180021074  push    r15
0x180021076  sub     rsp, 40h
0x18002107a  xor     eax, eax
0x18002107c  xor     esi, esi
0x18002107e  mov     [r11+8], ax
0x180021083  mov     r14, rdx
0x180021086  mov     [rsp+78h+pcbElement], eax
0x18002108a  mov     rdi, rcx
0x18002108d  test    rcx, rcx
0x180021090  jz      loc_1800211BF
0x180021096  mov     ecx, [rcx+38h]
0x180021099  test    ecx, ecx
0x18002109b  jz      short loc_1800210D3
0x18002109d  mov     r9d, 7FFFFFFFh
0x1800210a3  mov     eax, r9d
0x1800210a6  cdq
0x1800210a7  idiv    ecx
0x1800210a9  xor     edx, edx
0x1800210ab  mov     r10d, eax
0x1800210ae  mov     eax, [rdi+34h]
0x1800210b1  cmp     edx, [rdi+30h]
0x1800210b4  jge     short loc_1800210C2
0x1800210b6  cmp     eax, r10d
0x1800210b9  jge     short loc_1800210D3
0x1800210bb  imul    eax, ecx
0x1800210be  inc     edx
0x1800210c0  jmp     short loc_1800210B1
0x1800210c2  cmp     eax, 3FFFFFFFh
0x1800210c7  jge     short loc_1800210D3
0x1800210c9  movzx   ecx, word ptr [r8+28h]
0x1800210ce  cmp     ecx, 2
0x1800210d1  jnb     short loc_1800210DD
0x1800210d3  mov     ebx, 7DBh
0x1800210d8  jmp     loc_1800211C4
0x1800210dd  movzx   ebp, word ptr [r8+2Ah]
0x1800210e2  cmp     ebp, 2
0x1800210e5  jb      short loc_1800210D3
0x1800210e7  imul    ecx, [rdi+30h]
0x1800210eb  lea     r12d, [rax+rax]
0x1800210ef  lea     r13d, ds:34h[rcx*2]
0x1800210f7  sub     r9d, r13d
0x1800210fa  cmp     r12d, r9d
0x1800210fd  jge     short loc_1800210D3
0x1800210ff  mov     ecx, ebp
0x180021101  lea     rdx, [rsp+78h+arg_0]
0x180021109  imul    ecx, [rdi+34h]
0x18002110d  add     ecx, ecx
0x18002110f  mov     [rsp+78h+pcbElement], ecx
0x180021113  call    SmartNewPtrClear
0x180021118  movsx   ebx, [rsp+78h+arg_0]
0x180021120  mov     rsi, rax
0x180021123  test    ebx, ebx
0x180021125  jnz     loc_1800211C4
0x18002112b  mov     edx, [rsp+78h+tag]; tag
0x180021132  lea     r8d, [r12+r13]; dwOffset
0x180021136  mov     rcx, [r14]; hProfile
0x180021139  lea     r9, [rsp+78h+pcbElement]; pcbElement
0x18002113e  mov     r15d, [rsp+78h+pcbElement]
0x180021143  mov     [rsp+78h+var_58], rax; PVOID
0x180021148  call    CMGetPartialProfileElement
0x18002114d  mov     ebx, eax
0x18002114f  test    eax, eax
0x180021151  jnz     short loc_1800211C4
0x180021153  mov     r8d, [rsp+78h+pcbElement]
0x180021158  cmp     r15d, r8d
0x18002115b  jnz     loc_1800210D3
0x180021161  xor     edx, edx
0x180021163  mov     rcx, rsi
0x180021166  call    SwapShortOffset
0x18002116b  cmp     [r14+32h], dl
0x18002116f  jnz     short loc_18002119B
0x180021171  cmp     [r14+34h], dl
0x180021175  jnz     short loc_18002119B
0x180021177  mov     r9d, ebp
0x18002117a  mov     rdx, rsi
0x18002117d  mov     rcx, rdi
0x180021180  call    Fill_byte_ALUTs_from_lut16Tag
0x180021185  mov     ebx, eax
0x180021187  test    eax, eax
0x180021189  jnz     short loc_1800211C4
0x18002118b  mov     dword ptr [rdi+20h], 400h
0x180021192  mov     dword ptr [rdi+24h], 8
0x180021199  jmp     short loc_1800211C4
0x18002119b  mov     r9d, ebp
0x18002119e  mov     rdx, rsi
0x1800211a1  mov     rcx, rdi
0x1800211a4  call    Fill_ushort_ALUTs_from_lut16Tag
0x1800211a9  mov     ebx, eax
0x1800211ab  test    eax, eax
0x1800211ad  jnz     short loc_1800211C4
0x1800211af  mov     dword ptr [rdi+20h], 400h
0x1800211b6  mov     dword ptr [rdi+24h], 10h
0x1800211bd  jmp     short loc_1800211C4
0x1800211bf  mov     ebx, 57h ; 'W'
0x1800211c4  mov     rcx, rsi
0x1800211c7  call    DisposeIfPtr
0x1800211cc  mov     eax, ebx
0x1800211ce  mov     rbx, [rsp+78h+arg_8]
0x1800211d6  add     rsp, 40h
0x1800211da  pop     r15
0x1800211dc  pop     r14
0x1800211de  pop     r13
0x1800211e0  pop     r12
0x1800211e2  pop     rdi
0x1800211e3  pop     rsi
0x1800211e4  pop     rbp
0x1800211e5  retn
```
