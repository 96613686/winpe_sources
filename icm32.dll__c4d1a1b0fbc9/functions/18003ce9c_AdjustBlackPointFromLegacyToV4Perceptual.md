# AdjustBlackPointFromLegacyToV4Perceptual

- ea: `0x18003ce9c`
- end: `0x18003cf56`
- name: `AdjustBlackPointFromLegacyToV4Perceptual`
- size: `186`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800029a4`

## callees

- `0x18003ce9c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18003cebf`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18003cebf`

## pseudocode

```c
__int64 __fastcall AdjustBlackPointFromLegacyToV4Perceptual(unsigned __int16 *a1, int a2)
{
  __int64 result; // rax
  unsigned __int16 *v5; // rdx
  __int64 v6; // rcx

  EventWrite(g_etwHandle, &ADJUST_BLACK_POINT_TO_V4, 0, 0);
  result = (unsigned int)(3 * a2);
  v5 = a1;
  v6 = (int)result;
  if ( (int)result > 0 )
  {
    do
    {
      *v5 = (int)(float)((float)((float)*v5 * 0.99651527) + 110.10048);
      v5[1] = (int)(float)((float)((float)v5[1] * 0.9965269) + 113.80654);
      v5[2] = (int)(float)((float)((float)v5[2] * 0.99652082) + 94.044159);
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
0x18003ce9c  mov     [rsp+arg_0], rbx
0x18003cea1  push    rdi
0x18003cea2  sub     rsp, 20h
0x18003cea6  mov     ebx, edx
0x18003cea8  mov     rdi, rcx
0x18003ceab  mov     rcx, cs:g_etwHandle; RegHandle
0x18003ceb2  lea     rdx, ADJUST_BLACK_POINT_TO_V4; EventDescriptor
0x18003ceb9  xor     r9d, r9d; UserData
0x18003cebc  xor     r8d, r8d; UserDataCount
0x18003cebf  call    cs:__imp_EventWrite
0x18003cec5  lea     eax, [rbx+rbx*2]
0x18003cec8  mov     rdx, rdi
0x18003cecb  movsxd  rcx, eax
0x18003cece  test    eax, eax
0x18003ced0  jle     short loc_18003CF4B
0x18003ced2  movzx   eax, word ptr [rdx]
0x18003ced5  movd    xmm0, eax
0x18003ced9  cvtdq2ps xmm0, xmm0
0x18003cedc  mulss   xmm0, cs:__real@3f7f1ba0
0x18003cee4  addss   xmm0, cs:__real@42dc3372
0x18003ceec  cvttss2si eax, xmm0
0x18003cef0  mov     [rdx], ax
0x18003cef3  movzx   eax, word ptr [rdx+2]
0x18003cef7  movd    xmm0, eax
0x18003cefb  cvtdq2ps xmm0, xmm0
0x18003cefe  mulss   xmm0, cs:__real@3f7f1c63
0x18003cf06  addss   xmm0, cs:__real@42e39cf3
0x18003cf0e  cvttss2si eax, xmm0
0x18003cf12  mov     [rdx+2], ax
0x18003cf16  movzx   eax, word ptr [rdx+4]
0x18003cf1a  movd    xmm0, eax
0x18003cf1e  cvtdq2ps xmm0, xmm0
0x18003cf21  mulss   xmm0, cs:__real@3f7f1bfd
0x18003cf29  addss   xmm0, cs:__real@42bc169c
0x18003cf31  cvttss2si eax, xmm0
0x18003cf35  mov     [rdx+4], ax
0x18003cf39  add     rdx, 6
0x18003cf3d  mov     rax, rdx
0x18003cf40  sub     rax, rdi
0x18003cf43  sar     rax, 1
0x18003cf46  cmp     rax, rcx
0x18003cf49  jl      short loc_18003CED2
0x18003cf4b  mov     rbx, [rsp+28h+arg_0]
0x18003cf50  add     rsp, 20h
0x18003cf54  pop     rdi
0x18003cf55  retn
```
