# ExtractXlutFromLut16

- ea: `0x180006f00`
- end: `0x180007128`
- name: `ExtractXlutFromLut16`
- size: `552`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, TAGTYPE)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18001c308`
- `0x18001de14`

## callees

- `0x1800042e0`
- `0x18000604c`
- `0x1800060f0`
- `0x180006f00`
- `0x180018b68`
- `0x18001d15d`

## pseudocode

```c
__int64 __fastcall ExtractXlutFromLut16(__int64 a1, __int64 a2, __int64 a3, TAGTYPE a4)
{
  int v5; // ecx
  void *v7; // rbp
  _BYTE *v8; // r12
  unsigned int v9; // ebx
  int v10; // r13d
  int v11; // edi
  int i; // eax
  int v13; // r15d
  int v14; // eax
  int v15; // edx
  int v16; // r8d
  unsigned int v17; // eax
  DWORD v18; // r13d
  _BYTE *v19; // rax
  int v20; // r8d
  _BYTE *v21; // rcx
  _BYTE *j; // rdx
  HPROFILE v23; // rcx
  DWORD pcbElement[18]; // [rsp+30h] [rbp-48h] BYREF
  __int16 v26; // [rsp+80h] [rbp+8h] BYREF
  __int64 v27; // [rsp+90h] [rbp+18h]
  TAGTYPE tag; // [rsp+98h] [rbp+20h]

  tag = a4;
  v27 = a3;
  v5 = *(_DWORD *)(a1 + 56);
  pcbElement[0] = 0;
  v7 = 0;
  v8 = 0;
  if ( !v5 )
    goto LABEL_2;
  v10 = *(_DWORD *)(a1 + 48);
  v11 = *(_DWORD *)(a1 + 52);
  for ( i = 0; i < v10; ++i )
  {
    if ( v11 >= 0x7FFFFFFF / v5 )
      goto LABEL_2;
    v11 *= v5;
  }
  v13 = *(_DWORD *)(a2 + 40);
  if ( v13 > 0 || *(_BYTE *)(a2 + 51) || *(_BYTE *)(a2 + 49) )
    v11 *= 2;
  if ( v13 )
  {
    v14 = 0;
  }
  else
  {
    v14 = 1;
    if ( v10 - 1 > 0 )
    {
      v15 = 0;
      v16 = 1;
      do
      {
        v16 *= v5;
        ++v15;
        v14 += v16;
      }
      while ( v15 < v10 - 1 );
    }
    if ( *(_BYTE *)(a2 + 51) || *(_BYTE *)(a2 + 49) )
      v14 *= 2;
  }
  v7 = malloc_0(v11 + v14 * *(_DWORD *)(a1 + 52));
  v9 = v7 == 0 ? 8 : 0;
  v26 = v7 == 0 ? 8 : 0;
  if ( (v7 == 0 ? 8 : 0) == 0 )
  {
    v17 = *(unsigned __int16 *)(v27 + 40);
    if ( v17 < 2 )
      goto LABEL_2;
    v18 = 2 * v10 * v17 + 52;
    if ( v13 > 0 || *(_BYTE *)(a2 + 51) || *(_BYTE *)(a2 + 49) )
    {
      v23 = *(HPROFILE *)a2;
      pcbElement[0] = v11;
      v9 = CMGetPartialProfileElement(v23, tag, v18, pcbElement, v7);
      SwapShortOffset(v7, 0, pcbElement[0]);
      *(_DWORD *)(a1 + 60) = 16;
      if ( v9 )
        goto LABEL_33;
      if ( v11 != pcbElement[0] )
        goto LABEL_2;
LABEL_32:
      *(_QWORD *)(a1 + 64) = v7;
      v7 = 0;
      goto LABEL_33;
    }
    pcbElement[0] = 2 * v11;
    v19 = (_BYTE *)SmartNewPtr((unsigned int)(2 * v11), &v26);
    v9 = v26;
    v8 = v19;
    if ( !v26 )
    {
      v9 = CMGetPartialProfileElement(*(HPROFILE *)a2, tag, v18, pcbElement, v19);
      if ( !v9 )
      {
        if ( 2 * v11 == pcbElement[0] )
        {
          v20 = 0;
          v21 = v8;
          for ( j = v7; v20 < v11; ++j )
          {
            ++v20;
            *j = *v21;
            v21 += 2;
          }
          *(_DWORD *)(a1 + 60) = 8;
          goto LABEL_32;
        }
LABEL_2:
        v9 = 2011;
      }
    }
  }
LABEL_33:
  DisposeIfPtr(v7);
  DisposeIfPtr(v8);
  return v9;
}

```

## disassembly

```asm
0x180006f00  mov     rax, rsp
0x180006f03  mov     [rax+10h], rbx
0x180006f07  mov     [rax+20h], r9d
0x180006f0b  mov     [rax+18h], r8
0x180006f0f  push    rbp
0x180006f10  push    rsi
0x180006f11  push    rdi
0x180006f12  push    r12
0x180006f14  push    r13
0x180006f16  push    r14
0x180006f18  push    r15
0x180006f1a  sub     rsp, 40h
0x180006f1e  xor     r11d, r11d
0x180006f21  mov     r14, rcx
0x180006f24  mov     ecx, [rcx+38h]
0x180006f27  mov     rsi, rdx
0x180006f2a  mov     [rax-48h], r11d
0x180006f2e  mov     ebp, r11d
0x180006f31  mov     r12d, r11d
0x180006f34  test    ecx, ecx
0x180006f36  jnz     short loc_180006F42
0x180006f38  mov     ebx, 7DBh
0x180006f3d  jmp     loc_1800070FE
0x180006f42  mov     r10d, [r14+34h]
0x180006f46  mov     eax, 7FFFFFFFh
0x180006f4b  mov     r13d, [r14+30h]
0x180006f4f  cdq
0x180006f50  idiv    ecx
0x180006f52  mov     edi, r10d
0x180006f55  mov     r8d, eax
0x180006f58  mov     eax, r11d
0x180006f5b  cmp     eax, r13d
0x180006f5e  jge     short loc_180006F6C
0x180006f60  cmp     edi, r8d
0x180006f63  jge     short loc_180006F38
0x180006f65  imul    edi, ecx
0x180006f68  inc     eax
0x180006f6a  jmp     short loc_180006F5B
0x180006f6c  mov     r15d, [rsi+28h]
0x180006f70  test    r15d, r15d
0x180006f73  jg      short loc_180006F81
0x180006f75  cmp     [rsi+33h], r11b
0x180006f79  jnz     short loc_180006F81
0x180006f7b  cmp     [rsi+31h], r11b
0x180006f7f  jz      short loc_180006F83
0x180006f81  add     edi, edi
0x180006f83  test    r15d, r15d
0x180006f86  jnz     short loc_180006FB9
0x180006f88  lea     r9d, [r13-1]
0x180006f8c  lea     eax, [r15+1]
0x180006f90  test    r9d, r9d
0x180006f93  jle     short loc_180006FA9
0x180006f95  mov     edx, r11d
0x180006f98  mov     r8d, eax
0x180006f9b  imul    r8d, ecx
0x180006f9f  inc     edx
0x180006fa1  add     eax, r8d
0x180006fa4  cmp     edx, r9d
0x180006fa7  jl      short loc_180006F9B
0x180006fa9  cmp     [rsi+33h], r11b
0x180006fad  jnz     short loc_180006FB5
0x180006faf  cmp     [rsi+31h], r11b
0x180006fb3  jz      short loc_180006FBC
0x180006fb5  add     eax, eax
0x180006fb7  jmp     short loc_180006FBC
0x180006fb9  mov     eax, r11d
0x180006fbc  imul    r10d, eax
0x180006fc0  add     r10d, edi
0x180006fc3  movsxd  rcx, r10d; Size
0x180006fc6  call    malloc_0
0x180006fcb  mov     rbp, rax
0x180006fce  neg     rax
0x180006fd1  sbb     cx, cx
0x180006fd4  not     cx
0x180006fd7  and     cx, 8
0x180006fdb  movzx   ebx, cx
0x180006fde  mov     [rsp+78h+arg_0], bx
0x180006fe6  jnz     loc_1800070FE
0x180006fec  mov     rax, [rsp+78h+arg_10]
0x180006ff4  movzx   eax, word ptr [rax+28h]
0x180006ff8  cmp     eax, 2
0x180006ffb  jb      loc_180006F38
0x180007001  imul    eax, r13d
0x180007005  lea     r13d, ds:34h[rax*2]
0x18000700d  test    r15d, r15d
0x180007010  jg      loc_1800070B1
0x180007016  cmp     [rsi+33h], r12b
0x18000701a  jnz     loc_1800070B1
0x180007020  cmp     [rsi+31h], r12b
0x180007024  jnz     loc_1800070B1
0x18000702a  lea     r15d, [rdi+rdi]
0x18000702e  mov     ecx, r15d
0x180007031  mov     [rsp+78h+pcbElement], r15d
0x180007036  lea     rdx, [rsp+78h+arg_0]
0x18000703e  call    SmartNewPtr
0x180007043  movsx   ebx, [rsp+78h+arg_0]
0x18000704b  mov     r12, rax
0x18000704e  test    ebx, ebx
0x180007050  jnz     loc_1800070FE
0x180007056  mov     edx, [rsp+78h+tag]; tag
0x18000705d  lea     r9, [rsp+78h+pcbElement]; pcbElement
0x180007062  mov     rcx, [rsi]; hProfile
0x180007065  mov     r8d, r13d; dwOffset
0x180007068  mov     [rsp+78h+var_58], rax; PVOID
0x18000706d  call    CMGetPartialProfileElement
0x180007072  mov     ebx, eax
0x180007074  test    eax, eax
0x180007076  jnz     loc_1800070FE
0x18000707c  cmp     r15d, [rsp+78h+pcbElement]
0x180007081  jnz     loc_180006F38
0x180007087  xor     r8d, r8d
0x18000708a  mov     rcx, r12
0x18000708d  mov     rdx, rbp
0x180007090  test    edi, edi
0x180007092  jle     short loc_1800070A7
0x180007094  mov     al, [rcx]
0x180007096  inc     r8d
0x180007099  mov     [rdx], al
0x18000709b  lea     rcx, [rcx+2]
0x18000709f  inc     rdx
0x1800070a2  cmp     r8d, edi
0x1800070a5  jl      short loc_180007094
0x1800070a7  mov     dword ptr [r14+3Ch], 8
0x1800070af  jmp     short loc_1800070F8
0x1800070b1  mov     edx, [rsp+78h+tag]; tag
0x1800070b8  lea     r9, [rsp+78h+pcbElement]; pcbElement
0x1800070bd  mov     rcx, [rsi]; hProfile
0x1800070c0  mov     r8d, r13d; dwOffset
0x1800070c3  mov     [rsp+78h+pcbElement], edi
0x1800070c7  mov     [rsp+78h+var_58], rbp; PVOID
0x1800070cc  call    CMGetPartialProfileElement
0x1800070d1  mov     r8d, [rsp+78h+pcbElement]
0x1800070d6  xor     edx, edx
0x1800070d8  mov     rcx, rbp
0x1800070db  mov     ebx, eax
0x1800070dd  call    SwapShortOffset
0x1800070e2  mov     dword ptr [r14+3Ch], 10h
0x1800070ea  test    ebx, ebx
0x1800070ec  jnz     short loc_1800070FE
0x1800070ee  cmp     edi, [rsp+78h+pcbElement]
0x1800070f2  jnz     loc_180006F38
0x1800070f8  mov     [r14+40h], rbp
0x1800070fc  xor     ebp, ebp
0x1800070fe  mov     rcx, rbp
0x180007101  call    DisposeIfPtr
0x180007106  mov     rcx, r12
0x180007109  call    DisposeIfPtr
0x18000710e  mov     eax, ebx
0x180007110  mov     rbx, [rsp+78h+arg_8]
0x180007118  add     rsp, 40h
0x18000711c  pop     r15
0x18000711e  pop     r14
0x180007120  pop     r13
0x180007122  pop     r12
0x180007124  pop     rdi
0x180007125  pop     rsi
0x180007126  pop     rbp
0x180007127  retn
```
