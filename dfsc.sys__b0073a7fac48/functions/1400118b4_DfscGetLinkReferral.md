# DfscGetLinkReferral

- ea: `0x1400118b4`
- end: `0x1400119c6`
- name: `DfscGetLinkReferral`
- size: `274`
- prototype: `__int64 __fastcall(__int64, const UNICODE_STRING *, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140011c80`
- `0x140021688`

## callees

- `0x1400025a0`
- `0x1400118b4`
- `0x14001b230`

## pseudocode

```c
__int64 __fastcall DfscGetLinkReferral(__int64 a1, const UNICODE_STRING *a2, __int64 a3, _QWORD *a4)
{
  int Referral; // edi
  __int64 v6; // rdx
  unsigned __int16 v7; // cx
  __int64 v8; // rdx
  unsigned __int16 v10; // [rsp+38h] [rbp-10h]

  Referral = DfscRmGetReferral(2u, a1, a1 + 168, a2, 0, a3, a4, v10);
  if ( Referral >= 0 )
  {
    v6 = *(unsigned __int16 *)(a1 + 218);
    v7 = *(_WORD *)(a1 + 88) - v6;
    *(_WORD *)(a1 + 202) = v7;
    *(_WORD *)(a1 + 200) = v7;
    if ( v7 )
      v8 = *(_QWORD *)(a1 + 96) + v6;
    else
      v8 = 0;
    *(_QWORD *)(a1 + 208) = v8;
    if ( *(_WORD *)(a1 + 216) <= v7 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
      {
        WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_55706db06074317498eaf8c01331c814_Traceguids);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
      {
        WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_55706db06074317498eaf8c01331c814_Traceguids);
      }
      *(_WORD *)(a1 + 216) = *(_WORD *)(a1 + 200);
    }
  }
  return (unsigned int)Referral;
}

```

## disassembly

```asm
0x1400118b4  mov     r11, rsp
0x1400118b7  mov     [r11+8], rbx
0x1400118bb  push    rdi
0x1400118bc  sub     rsp, 40h
0x1400118c0  mov     [r11-18h], r9
0x1400118c4  mov     rax, r8
0x1400118c7  mov     r9, rdx
0x1400118ca  mov     [r11-20h], rax
0x1400118ce  mov     rdx, rcx
0x1400118d1  mov     qword ptr [r11-28h], 0
0x1400118d9  mov     rbx, rcx
0x1400118dc  lea     r8, [rcx+0A8h]
0x1400118e3  mov     ecx, 2
0x1400118e8  call    DfscRmGetReferral
0x1400118ed  mov     edi, eax
0x1400118ef  test    eax, eax
0x1400118f1  js      loc_1400119B8
0x1400118f7  movzx   edx, word ptr [rbx+0DAh]
0x1400118fe  movzx   ecx, word ptr [rbx+58h]
0x140011902  sub     cx, dx
0x140011905  mov     [rbx+0CAh], cx
0x14001190c  mov     [rbx+0C8h], cx
0x140011913  jz      short loc_14001191B
0x140011915  add     rdx, [rbx+60h]
0x140011919  jmp     short loc_14001191D
0x14001191b  xor     edx, edx
0x14001191d  mov     [rbx+0D0h], rdx
0x140011924  movzx   edx, word ptr [rbx+0D8h]
0x14001192b  cmp     dx, cx
0x14001192e  jbe     short loc_14001197C
0x140011930  mov     r10, cs:WPP_GLOBAL_Control
0x140011937  lea     rax, WPP_GLOBAL_Control
0x14001193e  cmp     r10, rax
0x140011941  jz      short loc_14001196C
0x140011943  test    dword ptr [r10+2Ch], 400000h
0x14001194b  jz      short loc_14001196C
0x14001194d  movzx   eax, cx
0x140011950  lea     r8, WPP_55706db06074317498eaf8c01331c814_Traceguids
0x140011957  mov     rcx, [r10+18h]
0x14001195b  mov     r9d, edx
0x14001195e  mov     edx, 11h
0x140011963  mov     [rsp+48h+var_28], eax
0x140011967  call    WPP_SF_dd
0x14001196c  movzx   eax, word ptr [rbx+0C8h]
0x140011973  mov     [rbx+0D8h], ax
0x14001197a  jmp     short loc_1400119B8
0x14001197c  mov     r10, cs:WPP_GLOBAL_Control
0x140011983  lea     rax, WPP_GLOBAL_Control
0x14001198a  cmp     r10, rax
0x14001198d  jz      short loc_1400119B8
0x14001198f  test    dword ptr [r10+2Ch], 400000h
0x140011997  jz      short loc_1400119B8
0x140011999  movzx   eax, cx
0x14001199c  lea     r8, WPP_55706db06074317498eaf8c01331c814_Traceguids
0x1400119a3  mov     rcx, [r10+18h]
0x1400119a7  mov     r9d, edx
0x1400119aa  mov     edx, 12h
0x1400119af  mov     [rsp+48h+var_28], eax
0x1400119b3  call    WPP_SF_dd
0x1400119b8  mov     rbx, [rsp+48h+arg_0]
0x1400119bd  mov     eax, edi
0x1400119bf  add     rsp, 40h
0x1400119c3  pop     rdi
0x1400119c4  retn
```
