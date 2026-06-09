# ExtractAlutFromLut8

- ea: `0x1800211ec`
- end: `0x180021340`
- name: `ExtractAlutFromLut8`
- size: `340`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18001de14`
- `0x180020ae4`

## callees

- `0x1800042e0`
- `0x18000604c`
- `0x180018960`
- `0x180018b68`
- `0x18001a6c8`
- `0x1800211ec`

## pseudocode

```c
__int64 __fastcall ExtractAlutFromLut8(_DWORD *a1, __int64 a2, TAGTYPE a3)
{
  void *v3; // rsi
  int v7; // r9d
  int v8; // r8d
  int v9; // ebp
  int v10; // edx
  int v11; // eax
  int v12; // r12d
  unsigned int v13; // ebx
  void *v14; // rax
  DWORD v15; // r15d
  __int16 v17; // [rsp+70h] [rbp+8h] BYREF
  DWORD pcbElement; // [rsp+88h] [rbp+20h] BYREF

  v3 = 0;
  v17 = 0;
  pcbElement = 0;
  if ( !a1 )
  {
    v13 = 87;
    goto LABEL_20;
  }
  v7 = a1[14];
  if ( !v7 )
    goto LABEL_9;
  v8 = a1[13];
  v9 = v8;
  v10 = 0;
  v11 = a1[12];
  while ( v10 < v11 )
  {
    if ( v9 >= 0x7FFFFFFF / v7 )
      goto LABEL_9;
    v9 *= v7;
    ++v10;
  }
  if ( v9 == 0x7FFFFFFF )
    goto LABEL_9;
  v12 = (v11 << 8) + 48;
  if ( v9 >= 0x7FFFFFFF - v12 )
    goto LABEL_9;
  pcbElement = v8 << 8;
  v14 = SmartNewPtr(v8 << 8, &v17);
  v13 = v17;
  v3 = v14;
  if ( !v17 )
  {
    v15 = pcbElement;
    v13 = CMGetPartialProfileElement(*(HPROFILE *)a2, a3, v12 + v9, &pcbElement, v14);
    if ( !v13 )
    {
      if ( v15 != pcbElement )
      {
LABEL_9:
        v13 = 2011;
        goto LABEL_20;
      }
      if ( *(_BYTE *)(a2 + 50) || *(_BYTE *)(a2 + 52) )
      {
        v13 = Fill_ushort_ALUTs_from_lut8Tag(a1, v3);
        if ( !v13 )
        {
          a1[8] = 1024;
          a1[9] = 16;
        }
      }
      else
      {
        v13 = Fill_byte_ALUTs_from_lut8Tag(a1, v3);
        if ( !v13 )
        {
          a1[8] = 1024;
          a1[9] = 8;
        }
      }
    }
  }
LABEL_20:
  DisposeIfPtr(v3);
  return v13;
}

```

## disassembly

```asm
0x1800211ec  mov     r11, rsp
0x1800211ef  mov     [r11+10h], rbx
0x1800211f3  push    rbp
0x1800211f4  push    rsi
0x1800211f5  push    rdi
0x1800211f6  push    r12
0x1800211f8  push    r13
0x1800211fa  push    r14
0x1800211fc  push    r15
0x1800211fe  sub     rsp, 30h
0x180021202  xor     eax, eax
0x180021204  xor     esi, esi
0x180021206  mov     [rsp+68h+arg_0], ax
0x18002120b  mov     r13d, r8d
0x18002120e  mov     [r11+20h], eax
0x180021212  mov     r14, rdx
0x180021215  mov     rdi, rcx
0x180021218  test    rcx, rcx
0x18002121b  jz      loc_18002131C
0x180021221  mov     r9d, [rcx+38h]
0x180021225  test    r9d, r9d
0x180021228  jz      short loc_180021267
0x18002122a  mov     r8d, [rdi+34h]
0x18002122e  mov     ecx, 7FFFFFFFh
0x180021233  mov     eax, ecx
0x180021235  mov     ebp, r8d
0x180021238  cdq
0x180021239  idiv    r9d
0x18002123c  xor     edx, edx
0x18002123e  mov     r10d, eax
0x180021241  mov     eax, [rdi+30h]
0x180021244  cmp     edx, eax
0x180021246  jge     short loc_180021255
0x180021248  cmp     ebp, r10d
0x18002124b  jge     short loc_180021267
0x18002124d  imul    ebp, r9d
0x180021251  inc     edx
0x180021253  jmp     short loc_180021244
0x180021255  cmp     ebp, ecx
0x180021257  jge     short loc_180021267
0x180021259  shl     eax, 8
0x18002125c  lea     r12d, [rax+30h]
0x180021260  sub     ecx, r12d
0x180021263  cmp     ebp, ecx
0x180021265  jl      short loc_180021271
0x180021267  mov     ebx, 7DBh
0x18002126c  jmp     loc_180021321
0x180021271  shl     r8d, 8
0x180021275  lea     rdx, [rsp+68h+arg_0]
0x18002127a  mov     ecx, r8d
0x18002127d  mov     [rsp+68h+pcbElement], r8d
0x180021285  call    SmartNewPtr
0x18002128a  movsx   ebx, [rsp+68h+arg_0]
0x18002128f  mov     rsi, rax
0x180021292  test    ebx, ebx
0x180021294  jnz     loc_180021321
0x18002129a  mov     rcx, [r14]; hProfile
0x18002129d  lea     r8d, [r12+rbp]; dwOffset
0x1800212a1  mov     r15d, [rsp+68h+pcbElement]
0x1800212a9  lea     r9, [rsp+68h+pcbElement]; pcbElement
0x1800212b1  mov     edx, r13d; tag
0x1800212b4  mov     [rsp+68h+var_48], rax; PVOID
0x1800212b9  call    CMGetPartialProfileElement
0x1800212be  mov     ebx, eax
0x1800212c0  test    eax, eax
0x1800212c2  jnz     short loc_180021321
0x1800212c4  cmp     r15d, [rsp+68h+pcbElement]
0x1800212cc  jnz     short loc_180021267
0x1800212ce  cmp     [r14+32h], al
0x1800212d2  jnz     short loc_1800212FB
0x1800212d4  cmp     [r14+34h], al
0x1800212d8  jnz     short loc_1800212FB
0x1800212da  mov     rdx, rsi
0x1800212dd  mov     rcx, rdi
0x1800212e0  call    Fill_byte_ALUTs_from_lut8Tag
0x1800212e5  mov     ebx, eax
0x1800212e7  test    eax, eax
0x1800212e9  jnz     short loc_180021321
0x1800212eb  mov     dword ptr [rdi+20h], 400h
0x1800212f2  mov     dword ptr [rdi+24h], 8
0x1800212f9  jmp     short loc_180021321
0x1800212fb  mov     rdx, rsi
0x1800212fe  mov     rcx, rdi
0x180021301  call    Fill_ushort_ALUTs_from_lut8Tag
0x180021306  mov     ebx, eax
0x180021308  test    eax, eax
0x18002130a  jnz     short loc_180021321
0x18002130c  mov     dword ptr [rdi+20h], 400h
0x180021313  mov     dword ptr [rdi+24h], 10h
0x18002131a  jmp     short loc_180021321
0x18002131c  mov     ebx, 57h ; 'W'
0x180021321  mov     rcx, rsi
0x180021324  call    DisposeIfPtr
0x180021329  mov     eax, ebx
0x18002132b  mov     rbx, [rsp+68h+arg_8]
0x180021330  add     rsp, 30h
0x180021334  pop     r15
0x180021336  pop     r14
0x180021338  pop     r13
0x18002133a  pop     r12
0x18002133c  pop     rdi
0x18002133d  pop     rsi
0x18002133e  pop     rbp
0x18002133f  retn
```
