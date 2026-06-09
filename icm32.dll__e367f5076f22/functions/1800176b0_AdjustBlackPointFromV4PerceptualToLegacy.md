# AdjustBlackPointFromV4PerceptualToLegacy

- ea: `0x1800176b0`
- end: `0x1800177a4`
- name: `AdjustBlackPointFromV4PerceptualToLegacy`
- size: `244`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800029a4`

## callees

- `0x1800176b0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800176d3`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800176d3`

## pseudocode

```c
__int64 __fastcall AdjustBlackPointFromV4PerceptualToLegacy(unsigned __int16 *a1, int a2)
{
  __int64 result; // rax
  unsigned __int16 *v5; // rdx
  __int64 v6; // rcx

  EventWrite(g_etwHandle, &ADJUST_BLACK_POINT_TO_LEGACY, 0, 0);
  result = (unsigned int)(3 * a2);
  v5 = a1;
  v6 = (int)result;
  if ( (int)result > 0 )
  {
    do
    {
      *v5 = (int)fminf(65535.0, fmaxf(0.0, (float)*v5 - 110.10048) / 0.99651527);
      v5[1] = (int)fminf(65535.0, fmaxf(0.0, (float)v5[1] - 113.80654) / 0.9965269);
      v5[2] = (int)fminf(65535.0, fmaxf(0.0, (float)v5[2] - 94.044159) / 0.99652082);
      v5 += 3;
      result = v5 - a1;
    }
    while ( result < v6 );
  }
  return result;
}

```

## disassembly

```asm
0x1800176b0  mov     [rsp+arg_0], rbx
0x1800176b5  push    rdi
0x1800176b6  sub     rsp, 20h
0x1800176ba  mov     ebx, edx
0x1800176bc  mov     rdi, rcx
0x1800176bf  mov     rcx, cs:g_etwHandle; RegHandle
0x1800176c6  lea     rdx, ADJUST_BLACK_POINT_TO_LEGACY; EventDescriptor
0x1800176cd  xor     r9d, r9d; UserData
0x1800176d0  xor     r8d, r8d; UserDataCount
0x1800176d3  call    cs:__imp_EventWrite
0x1800176d9  lea     eax, [rbx+rbx*2]
0x1800176dc  mov     rdx, rdi
0x1800176df  movsxd  rcx, eax
0x1800176e2  test    eax, eax
0x1800176e4  jle     loc_180017799
0x1800176ea  movss   xmm2, cs:__real@477fff00
0x1800176f2  movzx   eax, word ptr [rdx]
0x1800176f5  xorps   xmm1, xmm1
0x1800176f8  movd    xmm0, eax
0x1800176fc  cvtdq2ps xmm0, xmm0
0x1800176ff  subss   xmm0, cs:__real@42dc3372
0x180017707  maxss   xmm1, xmm0
0x18001770b  movaps  xmm0, xmm2
0x18001770e  divss   xmm1, cs:__real@3f7f1ba0
0x180017716  minss   xmm0, xmm1
0x18001771a  xorps   xmm1, xmm1
0x18001771d  cvttss2si eax, xmm0
0x180017721  mov     [rdx], ax
0x180017724  movzx   eax, word ptr [rdx+2]
0x180017728  movd    xmm0, eax
0x18001772c  cvtdq2ps xmm0, xmm0
0x18001772f  subss   xmm0, cs:__real@42e39cf3
0x180017737  maxss   xmm1, xmm0
0x18001773b  movaps  xmm0, xmm2
0x18001773e  divss   xmm1, cs:__real@3f7f1c63
0x180017746  minss   xmm0, xmm1
0x18001774a  xorps   xmm1, xmm1
0x18001774d  cvttss2si eax, xmm0
0x180017751  mov     [rdx+2], ax
0x180017755  movzx   eax, word ptr [rdx+4]
0x180017759  movd    xmm0, eax
0x18001775d  cvtdq2ps xmm0, xmm0
0x180017760  subss   xmm0, cs:__real@42bc169c
0x180017768  maxss   xmm1, xmm0
0x18001776c  movaps  xmm0, xmm2
0x18001776f  divss   xmm1, cs:__real@3f7f1bfd
0x180017777  minss   xmm0, xmm1
0x18001777b  cvttss2si eax, xmm0
0x18001777f  mov     [rdx+4], ax
0x180017783  add     rdx, 6
0x180017787  mov     rax, rdx
0x18001778a  sub     rax, rdi
0x18001778d  sar     rax, 1
0x180017790  cmp     rax, rcx
0x180017793  jl      loc_1800176F2
0x180017799  mov     rbx, [rsp+28h+arg_0]
0x18001779e  add     rsp, 20h
0x1800177a2  pop     rdi
0x1800177a3  retn
```
