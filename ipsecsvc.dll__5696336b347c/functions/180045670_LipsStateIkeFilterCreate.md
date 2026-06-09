# LipsStateIkeFilterCreate

- ea: `0x180045670`
- end: `0x180045801`
- name: `LipsStateIkeFilterCreate`
- size: `401`
- prototype: `__int64 __fastcall(unsigned int, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180045344`

## callees

- `0x180006f00`
- `0x18000c4d0`
- `0x18000e510`
- `0x180042ef8`
- `0x180045670`
- `0x1800459f4`

## string_xrefs

- `0x1800457dc`: `LipsStateIkeFilterCreate`

## pseudocode

```c
__int64 __fastcall LipsStateIkeFilterCreate(unsigned int a1, _QWORD *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  _QWORD *v9; // rdi
  __int64 i; // rsi
  _QWORD *v11; // rax
  _QWORD *v13; // [rsp+58h] [rbp+10h] BYREF
  SIZE_T v14; // [rsp+60h] [rbp+18h] BYREF

  *a2 = 0;
  v14 = 0;
  v13 = 0;
  v4 = NsuSizeTMultiply(a1, 8, &v14);
  v5 = v4;
  if ( v4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_23;
    v7 = 19;
    v8 = v4;
    goto LABEL_5;
  }
  v13 = IpsecAllocMem(v14);
  v9 = v13;
  if ( !v13 )
  {
    v5 = 8;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_23;
    v7 = 20;
    v8 = 8;
LABEL_5:
    WPP_SF_d(v6[2], v7, WPP_b2e62c343c9f3927bd54de5c93575086_Traceguids, v8);
    goto LABEL_23;
  }
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= a1 )
    {
      *a2 = v9;
      v13 = 0;
      goto LABEL_23;
    }
    v11 = IpsecAllocMem(0x20u);
    v9[i] = v11;
    if ( !v11 )
      break;
    *v11 = IpsecAllocMem(0x10u);
    if ( !*(_QWORD *)v9[i] )
    {
      v5 = 8;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v7 = 22;
LABEL_21:
        v8 = 8;
        goto LABEL_5;
      }
      goto LABEL_23;
    }
  }
  v5 = 8;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v7 = 21;
    goto LABEL_21;
  }
LABEL_23:
  LipsStateIkeFilterDestroy(a1, &v13);
  if ( v5 )
    return LipsReportError(v5, (int)"LipsStateIkeFilterCreate");
  else
    return 0;
}

```

## disassembly

```asm
0x180045670  mov     rax, rsp
0x180045673  mov     [rax+8], rbx
0x180045677  mov     [rax+20h], rbp
0x18004567b  push    rsi
0x18004567c  push    rdi
0x18004567d  push    r12
0x18004567f  push    r14
0x180045681  push    r15
0x180045683  sub     rsp, 20h
0x180045687  mov     r15, rdx
0x18004568a  mov     qword ptr [rdx], 0
0x180045691  mov     esi, 8
0x180045696  mov     ebp, ecx
0x180045698  mov     edx, esi
0x18004569a  mov     ecx, ecx
0x18004569c  lea     r8, [rax+18h]
0x1800456a0  mov     qword ptr [rax+18h], 0
0x1800456a8  mov     qword ptr [rax+10h], 0
0x1800456b0  call    NsuSizeTMultiply
0x1800456b5  mov     ebx, eax
0x1800456b7  test    eax, eax
0x1800456b9  jz      short loc_1800456F7
0x1800456bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800456c2  lea     rdx, WPP_GLOBAL_Control
0x1800456c9  cmp     rcx, rdx
0x1800456cc  jz      loc_1800457C8
0x1800456d2  test    byte ptr [rcx+1Ch], 10h
0x1800456d6  jz      loc_1800457C8
0x1800456dc  lea     edx, [rsi+0Bh]
0x1800456df  mov     r9d, eax
0x1800456e2  mov     rcx, [rcx+10h]
0x1800456e6  lea     r8, WPP_b2e62c343c9f3927bd54de5c93575086_Traceguids
0x1800456ed  call    WPP_SF_d
0x1800456f2  jmp     loc_1800457C8
0x1800456f7  mov     rcx, [rsp+48h+arg_10]
0x1800456fc  call    IpsecAllocMem
0x180045701  mov     [rsp+48h+arg_8], rax
0x180045706  mov     rdi, rax
0x180045709  test    rax, rax
0x18004570c  jnz     short loc_180045739
0x18004570e  mov     ebx, esi
0x180045710  mov     rcx, cs:WPP_GLOBAL_Control
0x180045717  lea     rdx, WPP_GLOBAL_Control
0x18004571e  cmp     rcx, rdx
0x180045721  jz      loc_1800457C8
0x180045727  test    byte ptr [rcx+1Ch], 10h
0x18004572b  jz      loc_1800457C8
0x180045731  lea     edx, [rax+14h]
0x180045734  mov     r9d, esi
0x180045737  jmp     short loc_1800456E2
0x180045739  xor     esi, esi
0x18004573b  cmp     esi, ebp
0x18004573d  jnb     short loc_1800457BC
0x18004573f  mov     ecx, 20h ; ' '
0x180045744  call    IpsecAllocMem
0x180045749  mov     [rdi+rsi*8], rax
0x18004574d  mov     r14, rax
0x180045750  test    rax, rax
0x180045753  jz      short loc_180045793
0x180045755  mov     ecx, 10h
0x18004575a  call    IpsecAllocMem
0x18004575f  mov     [r14], rax
0x180045762  mov     rax, [rdi+rsi*8]
0x180045766  cmp     qword ptr [rax], 0
0x18004576a  jz      short loc_180045770
0x18004576c  inc     esi
0x18004576e  jmp     short loc_18004573B
0x180045770  mov     ebx, 8
0x180045775  mov     rcx, cs:WPP_GLOBAL_Control
0x18004577c  lea     rdx, WPP_GLOBAL_Control
0x180045783  cmp     rcx, rdx
0x180045786  jz      short loc_1800457C8
0x180045788  test    byte ptr [rcx+1Ch], 10h
0x18004578c  jz      short loc_1800457C8
0x18004578e  lea     edx, [rbx+0Eh]
0x180045791  jmp     short loc_1800457B4
0x180045793  mov     ebx, 8
0x180045798  mov     rcx, cs:WPP_GLOBAL_Control
0x18004579f  lea     rdx, WPP_GLOBAL_Control
0x1800457a6  cmp     rcx, rdx
0x1800457a9  jz      short loc_1800457C8
0x1800457ab  test    byte ptr [rcx+1Ch], 10h
0x1800457af  jz      short loc_1800457C8
0x1800457b1  lea     edx, [rbx+0Dh]
0x1800457b4  mov     r9d, ebx
0x1800457b7  jmp     loc_1800456E2
0x1800457bc  mov     [r15], rdi
0x1800457bf  mov     [rsp+48h+arg_8], 0
0x1800457c8  lea     rdx, [rsp+48h+arg_8]
0x1800457cd  mov     ecx, ebp
0x1800457cf  call    LipsStateIkeFilterDestroy
0x1800457d4  test    ebx, ebx
0x1800457d6  jnz     short loc_1800457DC
0x1800457d8  xor     eax, eax
0x1800457da  jmp     short loc_1800457EA
0x1800457dc  lea     rdx, aLipsstateikefi_6; "LipsStateIkeFilterCreate"
0x1800457e3  mov     ecx, ebx
0x1800457e5  call    LipsReportError
0x1800457ea  mov     rbx, [rsp+48h+arg_0]
0x1800457ef  mov     rbp, [rsp+48h+arg_18]
0x1800457f4  add     rsp, 20h
0x1800457f8  pop     r15
0x1800457fa  pop     r14
0x1800457fc  pop     r12
0x1800457fe  pop     rdi
0x1800457ff  pop     rsi
0x180045800  retn
```
