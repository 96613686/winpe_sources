# CreateIniMMFilter

- ea: `0x180022348`
- end: `0x18002251d`
- name: `CreateIniMMFilter`
- size: `469`
- prototype: `__int64 __fastcall(__int64, __int128 *, __int128 *, __int64 *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18002163c`
- `0x1800240cc`

## callees

- `0x180006f00`
- `0x180007010`
- `0x18000c828`
- `0x18000e510`
- `0x180019e74`
- `0x180022348`
- `0x1800235fc`

## pseudocode

```c
__int64 __fastcall CreateIniMMFilter(__int64 a1, __int128 *a2, __int128 *a3, __int64 *a4)
{
  __int64 v8; // rax
  __int64 v9; // rbx
  _QWORD *v10; // rcx
  _QWORD *v11; // r14
  __int64 v12; // rax
  __int64 result; // rax
  __int128 v14; // xmm0
  __int128 v15; // xmm0

  v8 = IpsecAllocMem(208);
  v9 = v8;
  if ( !v8 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
LABEL_15:
      *a4 = 0;
      return 8;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids, 8);
      v10 = WPP_GLOBAL_Control;
    }
    v11 = (_QWORD *)(a1 + 24);
    goto LABEL_10;
  }
  *(_QWORD *)(v8 + 124) = 0;
  v11 = (_QWORD *)(a1 + 24);
  *(_DWORD *)(v8 + 132) = 0;
  *(_DWORD *)v8 = *(_DWORD *)a1;
  *(_OWORD *)(v8 + 4) = *(_OWORD *)(a1 + 4);
  v12 = IpsecAllocStr(*(unsigned __int16 **)(a1 + 24));
  *(_QWORD *)(v9 + 24) = v12;
  if ( !v12 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
LABEL_14:
      FreeIniMMFilter((LPVOID)v9);
      goto LABEL_15;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids, 8);
      v10 = WPP_GLOBAL_Control;
    }
LABEL_10:
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x10) != 0 )
      WPP_SF_S_guid_D(v10[2], 41, (unsigned int)WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids, *v11, a1 + 68, 8);
    if ( !v9 )
      goto LABEL_15;
    goto LABEL_14;
  }
  *(_DWORD *)(v9 + 32) = *(_DWORD *)(a1 + 32);
  *(_DWORD *)(v9 + 36) = *(_DWORD *)(a1 + 36);
  *(_DWORD *)(v9 + 40) = *(_DWORD *)(a1 + 40);
  CopyExtToIntAddresses(*(_DWORD *)a1, (int *)(a1 + 88), v9 + 44);
  CopyExtToIntAddresses(*(_DWORD *)a1, (int *)(a1 + 128), v9 + 84);
  if ( a2 )
    v14 = *a2;
  else
    v14 = *(_OWORD *)(a1 + 52);
  *(_OWORD *)(v9 + 136) = v14;
  if ( a3 )
    v15 = *a3;
  else
    v15 = *(_OWORD *)(a1 + 68);
  *(_OWORD *)(v9 + 152) = v15;
  *(_QWORD *)(v9 + 168) = 0;
  result = 0;
  *(_QWORD *)(v9 + 176) = 0;
  *(_DWORD *)(v9 + 184) = 0;
  *(_QWORD *)(v9 + 192) = 0;
  *(_QWORD *)(v9 + 200) = 0;
  *a4 = v9;
  return result;
}

```

## disassembly

```asm
0x180022348  push    rbx
0x18002234a  push    rbp
0x18002234b  push    rsi
0x18002234c  push    rdi
0x18002234d  push    r14
0x18002234f  push    r15
0x180022351  sub     rsp, 38h
0x180022355  mov     rdi, rcx
0x180022358  mov     r15, r9
0x18002235b  mov     ecx, 0D0h
0x180022360  mov     rsi, r8
0x180022363  mov     rbp, rdx
0x180022366  call    IpsecAllocMem
0x18002236b  mov     rbx, rax
0x18002236e  test    rax, rax
0x180022371  jnz     short loc_1800223B4
0x180022373  mov     rcx, cs:WPP_GLOBAL_Control
0x18002237a  lea     rsi, WPP_GLOBAL_Control
0x180022381  cmp     rcx, rsi
0x180022384  jz      loc_180022464
0x18002238a  test    byte ptr [rcx+1Ch], 10h
0x18002238e  jz      short loc_1800223AE
0x180022390  mov     rcx, [rcx+10h]
0x180022394  lea     edx, [rax+27h]
0x180022397  lea     r9d, [rax+8]
0x18002239b  lea     r8, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids
0x1800223a2  call    WPP_SF_d
0x1800223a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800223ae  lea     r14, [rdi+18h]
0x1800223b2  jmp     short loc_180022423
0x1800223b4  mov     qword ptr [rax+7Ch], 0
0x1800223bc  lea     r14, [rdi+18h]
0x1800223c0  mov     dword ptr [rax+84h], 0
0x1800223ca  mov     eax, [rdi]
0x1800223cc  mov     [rbx], eax
0x1800223ce  movups  xmm0, xmmword ptr [rdi+4]
0x1800223d2  movdqu  xmmword ptr [rbx+4], xmm0
0x1800223d7  mov     rcx, [r14]; unsigned __int16 *
0x1800223da  call    IpsecAllocStr
0x1800223df  mov     [rbx+18h], rax
0x1800223e3  test    rax, rax
0x1800223e6  jnz     loc_180022475
0x1800223ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800223f3  lea     rsi, WPP_GLOBAL_Control
0x1800223fa  cmp     rcx, rsi
0x1800223fd  jz      short loc_18002245C
0x1800223ff  test    byte ptr [rcx+1Ch], 10h
0x180022403  jz      short loc_180022423
0x180022405  mov     rcx, [rcx+10h]
0x180022409  lea     edx, [rax+28h]
0x18002240c  lea     r9d, [rax+8]
0x180022410  lea     r8, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids
0x180022417  call    WPP_SF_d
0x18002241c  mov     rcx, cs:WPP_GLOBAL_Control
0x180022423  cmp     rcx, rsi
0x180022426  jz      short loc_180022457
0x180022428  test    byte ptr [rcx+1Ch], 10h
0x18002242c  jz      short loc_180022457
0x18002242e  mov     r9, [r14]
0x180022431  lea     rax, [rdi+44h]
0x180022435  mov     rcx, [rcx+10h]
0x180022439  lea     r8, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids
0x180022440  mov     edx, 29h ; ')'
0x180022445  mov     [rsp+68h+var_40], 8
0x18002244d  mov     [rsp+68h+var_48], rax
0x180022452  call    WPP_SF_S_guid_D
0x180022457  test    rbx, rbx
0x18002245a  jz      short loc_180022464
0x18002245c  mov     rcx, rbx; lpMem
0x18002245f  call    FreeIniMMFilter
0x180022464  mov     qword ptr [r15], 0
0x18002246b  mov     eax, 8
0x180022470  jmp     loc_180022510
0x180022475  mov     eax, [rdi+20h]
0x180022478  lea     r8, [rbx+2Ch]
0x18002247c  mov     [rbx+20h], eax
0x18002247f  lea     rdx, [rdi+58h]
0x180022483  mov     eax, [rdi+24h]
0x180022486  mov     [rbx+24h], eax
0x180022489  mov     eax, [rdi+28h]
0x18002248c  mov     [rbx+28h], eax
0x18002248f  mov     ecx, [rdi]
0x180022491  call    CopyExtToIntAddresses
0x180022496  mov     ecx, [rdi]
0x180022498  lea     r8, [rbx+54h]
0x18002249c  lea     rdx, [rdi+80h]
0x1800224a3  call    CopyExtToIntAddresses
0x1800224a8  test    rbp, rbp
0x1800224ab  jz      short loc_1800224B3
0x1800224ad  movups  xmm0, xmmword ptr [rbp+0]
0x1800224b1  jmp     short loc_1800224B7
0x1800224b3  movups  xmm0, xmmword ptr [rdi+34h]
0x1800224b7  movdqu  xmmword ptr [rbx+88h], xmm0
0x1800224bf  test    rsi, rsi
0x1800224c2  jz      short loc_1800224C9
0x1800224c4  movups  xmm0, xmmword ptr [rsi]
0x1800224c7  jmp     short loc_1800224CD
0x1800224c9  movups  xmm0, xmmword ptr [rdi+44h]
0x1800224cd  movdqu  xmmword ptr [rbx+98h], xmm0
0x1800224d5  mov     qword ptr [rbx+0A8h], 0
0x1800224e0  xor     eax, eax
0x1800224e2  mov     qword ptr [rbx+0B0h], 0
0x1800224ed  mov     dword ptr [rbx+0B8h], 0
0x1800224f7  mov     qword ptr [rbx+0C0h], 0
0x180022502  mov     qword ptr [rbx+0C8h], 0
0x18002250d  mov     [r15], rbx
0x180022510  add     rsp, 38h
0x180022514  pop     r15
0x180022516  pop     r14
0x180022518  pop     rdi
0x180022519  pop     rsi
0x18002251a  pop     rbp
0x18002251b  pop     rbx
0x18002251c  retn
```
