# Int_FwValidateComplianceAndReduceCryptoSetToVersion

- ea: `0x180014340`
- end: `0x180014764`
- name: `Int_FwValidateComplianceAndReduceCryptoSetToVersion`
- size: `1060`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180016650`

## callees

- `0x18000ccd4`
- `0x180014340`
- `0x180017d1c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001454b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001454b`

## pseudocode

```c
__int64 __fastcall Int_FwValidateComplianceAndReduceCryptoSetToVersion(__int64 a1, _DWORD *a2, unsigned __int16 a3)
{
  unsigned int v6; // esi
  unsigned int v7; // r11d
  unsigned int i; // r8d
  __int64 v9; // rcx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rax
  unsigned int j; // r9d
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 418, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids);
  v6 = 0;
  v7 = 0;
  if ( *(_DWORD *)(a1 + 12) == 1 )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= *(_DWORD *)(a1 + 52) )
      {
        if ( !a2 )
          *(_DWORD *)(a1 + 52) = v7;
        if ( a3 < 0x208u && (unsigned int)_o__wcsicmp(*(_QWORD *)(a1 + 16), L"{E5A5D32A-4BCE-4e4d-B07F-4AB1BA7E5FE1}") )
        {
          if ( !a2 )
            goto LABEL_80;
          *a2 = 1069056;
          v6 = 87;
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v11 = 423;
            goto LABEL_84;
          }
        }
        return v6;
      }
      if ( a3 != 512 )
      {
        if ( a3 >= 0x208u )
          goto LABEL_25;
        goto LABEL_20;
      }
      v9 = *(_QWORD *)(a1 + 56);
      if ( *(int *)(v9 + 16LL * i + 8) >= 3 && a2 )
      {
        *a2 = 1069064;
        v6 = 87;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 419;
          goto LABEL_84;
        }
        return v6;
      }
      if ( *(int *)(v9 + 16LL * i + 4) < 6 )
      {
        if ( a2 )
          goto LABEL_20;
      }
      else if ( a2 )
      {
        *a2 = 1069063;
        v6 = 87;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 420;
          goto LABEL_84;
        }
        return v6;
      }
      if ( *(int *)(v9 + 16LL * i + 8) >= 3 || *(int *)(v9 + 16LL * i + 4) >= 6 )
        goto LABEL_18;
LABEL_20:
      if ( *(_DWORD *)(*(_QWORD *)(a1 + 56) + 16LL * i) != **(_DWORD **)(a1 + 56) )
      {
        if ( a2 )
        {
          *a2 = 1069060;
          v6 = 87;
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v11 = 421;
            goto LABEL_84;
          }
          return v6;
        }
LABEL_18:
        *(_DWORD *)(a1 + 88) = 0x20000;
        continue;
      }
LABEL_25:
      if ( a3 < 0x210u && *(int *)(*(_QWORD *)(a1 + 56) + 16LL * i) >= 6 )
      {
        if ( a2 )
        {
          *a2 = 1069065;
          v6 = 87;
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v11 = 422;
            goto LABEL_84;
          }
          return v6;
        }
        goto LABEL_18;
      }
      if ( !a2 )
      {
        v12 = 2LL * v7++;
        *(_OWORD *)(*(_QWORD *)(a1 + 56) + 8 * v12) = *(_OWORD *)(*(_QWORD *)(a1 + 56) + 16LL * i);
      }
    }
  }
  if ( *(_DWORD *)(a1 + 12) != 2 )
    return v6;
  for ( j = 0; j < *(_DWORD *)(a1 + 52); ++j )
  {
    if ( a3 != 512 )
    {
      if ( a3 >= 0x209u )
        goto LABEL_66;
      goto LABEL_61;
    }
    v14 = 28LL * j;
    v15 = *(_QWORD *)(a1 + 56);
    if ( *(int *)(v14 + v15 + 12) >= 6 && a2 )
    {
      *a2 = 1069094;
      v6 = 87;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v6;
      v11 = 424;
LABEL_84:
      WPP_SF_d(v10[2], v11, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
      return v6;
    }
    if ( *(int *)(v14 + v15 + 4) >= 3 || *(int *)(v14 + v15 + 8) >= 3 )
    {
      if ( a2 )
      {
        *a2 = 1069095;
        v6 = 87;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v6;
        v11 = 425;
        goto LABEL_84;
      }
    }
    else if ( a2 )
    {
      goto LABEL_61;
    }
    if ( *(int *)(v14 + v15 + 12) >= 6 || *(int *)(v14 + v15 + 4) >= 3 || *(int *)(v14 + v15 + 8) >= 3 )
      goto LABEL_59;
LABEL_61:
    if ( *(int *)(28LL * j + *(_QWORD *)(a1 + 56)) >= 4 )
    {
      if ( a2 )
      {
        *a2 = 1069089;
        v6 = 87;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v6;
        v11 = 426;
        goto LABEL_84;
      }
LABEL_59:
      *(_DWORD *)(a1 + 88) = 0x20000;
      continue;
    }
LABEL_66:
    if ( !a2 )
    {
      v16 = *(_QWORD *)(a1 + 56);
      v17 = 28LL * j;
      v18 = 28LL * v7++;
      *(_OWORD *)(v18 + v16) = *(_OWORD *)(v17 + v16);
      *(_OWORD *)(v18 + v16 + 12) = *(_OWORD *)(v17 + v16 + 12);
    }
  }
  if ( !a2 )
    *(_DWORD *)(a1 + 52) = v7;
  if ( a3 < 0x210u && *(int *)(a1 + 48) >= 8 )
  {
    if ( !a2 )
    {
LABEL_80:
      *(_DWORD *)(a1 + 88) = 0x40000;
      return v6;
    }
    *a2 = 1069096;
    v6 = 87;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 427;
      goto LABEL_84;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180014340  push    rbx
0x180014342  push    rbp
0x180014343  push    rsi
0x180014344  push    rdi
0x180014345  push    r12
0x180014347  push    r13
0x180014349  push    r14
0x18001434b  sub     rsp, 20h
0x18001434f  movzx   ebp, r8w
0x180014353  mov     rbx, rdx
0x180014356  mov     rdi, rcx
0x180014359  mov     rcx, cs:WPP_GLOBAL_Control
0x180014360  lea     r12, WPP_GLOBAL_Control
0x180014367  lea     r13, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids
0x18001436e  cmp     rcx, r12
0x180014371  jz      short loc_18001438A
0x180014373  test    byte ptr [rcx+1Ch], 8
0x180014377  jz      short loc_18001438A
0x180014379  mov     rcx, [rcx+10h]
0x18001437d  mov     edx, 1A2h
0x180014382  mov     r8, r13
0x180014385  call    WPP_SF_
0x18001438a  xor     esi, esi
0x18001438c  xor     r11d, r11d
0x18001438f  cmp     dword ptr [rdi+0Ch], 1
0x180014393  jnz     loc_180014595
0x180014399  mov     r14d, 200h
0x18001439f  xor     r8d, r8d
0x1800143a2  mov     r10d, 20000h
0x1800143a8  lea     r9d, [r14+10h]
0x1800143ac  mov     eax, 208h
0x1800143b1  cmp     r8d, [rdi+34h]
0x1800143b5  jnb     loc_18001452E
0x1800143bb  cmp     bp, r14w
0x1800143bf  jnz     short loc_180014436
0x1800143c1  mov     rcx, [rdi+38h]
0x1800143c5  mov     eax, r8d
0x1800143c8  add     rax, rax
0x1800143cb  cmp     dword ptr [rcx+rax*8+8], 3
0x1800143d0  jl      short loc_1800143DB
0x1800143d2  test    rbx, rbx
0x1800143d5  jnz     loc_1800144FB
0x1800143db  cmp     dword ptr [rcx+rax*8+4], 6
0x1800143e0  jl      short loc_18001441A
0x1800143e2  test    rbx, rbx
0x1800143e5  jz      short loc_18001441F
0x1800143e7  mov     r9d, 57h ; 'W'
0x1800143ed  mov     dword ptr [rbx], 105007h
0x1800143f3  mov     esi, r9d
0x1800143f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800143fd  cmp     rcx, r12
0x180014400  jz      loc_180014753
0x180014406  test    byte ptr [rcx+1Ch], 1
0x18001440a  jz      loc_180014753
0x180014410  mov     edx, 1A4h
0x180014415  jmp     loc_180014747
0x18001441a  test    rbx, rbx
0x18001441d  jnz     short loc_18001443B
0x18001441f  cmp     dword ptr [rcx+rax*8+8], 3
0x180014424  jge     short loc_18001442D
0x180014426  cmp     dword ptr [rcx+rax*8+4], 6
0x18001442b  jl      short loc_18001443B
0x18001442d  mov     [rdi+58h], r10d
0x180014431  jmp     loc_1800144F3
0x180014436  cmp     bp, ax
0x180014439  jnb     short loc_180014484
0x18001443b  mov     rdx, [rdi+38h]
0x18001443f  mov     ecx, r8d
0x180014442  add     rcx, rcx
0x180014445  mov     eax, [rdx]
0x180014447  cmp     [rdx+rcx*8], eax
0x18001444a  jz      short loc_180014484
0x18001444c  test    rbx, rbx
0x18001444f  jz      short loc_18001442D
0x180014451  mov     r9d, 57h ; 'W'
0x180014457  mov     dword ptr [rbx], 105004h
0x18001445d  mov     esi, r9d
0x180014460  mov     rcx, cs:WPP_GLOBAL_Control
0x180014467  cmp     rcx, r12
0x18001446a  jz      loc_180014753
0x180014470  test    byte ptr [rcx+1Ch], 1
0x180014474  jz      loc_180014753
0x18001447a  mov     edx, 1A5h
0x18001447f  jmp     loc_180014747
0x180014484  mov     edx, r8d
0x180014487  cmp     bp, r9w
0x18001448b  jnb     short loc_1800144D5
0x18001448d  mov     rax, [rdi+38h]
0x180014491  mov     ecx, r8d
0x180014494  add     rcx, rcx
0x180014497  cmp     dword ptr [rax+rcx*8], 6
0x18001449b  jl      short loc_1800144D5
0x18001449d  test    rbx, rbx
0x1800144a0  jz      short loc_18001442D
0x1800144a2  mov     r9d, 57h ; 'W'
0x1800144a8  mov     dword ptr [rbx], 105009h
0x1800144ae  mov     esi, r9d
0x1800144b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800144b8  cmp     rcx, r12
0x1800144bb  jz      loc_180014753
0x1800144c1  test    byte ptr [rcx+1Ch], 1
0x1800144c5  jz      loc_180014753
0x1800144cb  mov     edx, 1A6h
0x1800144d0  jmp     loc_180014747
0x1800144d5  test    rbx, rbx
0x1800144d8  jnz     short loc_1800144F3
0x1800144da  mov     rcx, [rdi+38h]
0x1800144de  add     rdx, rdx
0x1800144e1  mov     eax, r11d
0x1800144e4  add     rax, rax
0x1800144e7  inc     r11d
0x1800144ea  movups  xmm0, xmmword ptr [rcx+rdx*8]
0x1800144ee  movdqu  xmmword ptr [rcx+rax*8], xmm0
0x1800144f3  inc     r8d
0x1800144f6  jmp     loc_1800143AC
0x1800144fb  mov     r9d, 57h ; 'W'
0x180014501  mov     dword ptr [rbx], 105008h
0x180014507  mov     esi, r9d
0x18001450a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014511  cmp     rcx, r12
0x180014514  jz      loc_180014753
0x18001451a  test    byte ptr [rcx+1Ch], 1
0x18001451e  jz      loc_180014753
0x180014524  mov     edx, 1A3h
0x180014529  jmp     loc_180014747
0x18001452e  test    rbx, rbx
0x180014531  jnz     short loc_180014537
0x180014533  mov     [rdi+34h], r11d
0x180014537  cmp     bp, ax
0x18001453a  jnb     loc_180014753
0x180014540  mov     rcx, [rdi+10h]
0x180014544  lea     rdx, aE5a5d32a4bce4e_0; "{E5A5D32A-4BCE-4e4d-B07F-4AB1BA7E5FE1}"
0x18001454b  call    cs:__imp__o__wcsicmp
0x180014551  test    eax, eax
0x180014553  jz      loc_180014753
0x180014559  test    rbx, rbx
0x18001455c  jz      loc_180014718
0x180014562  mov     r9d, 57h ; 'W'
0x180014568  mov     dword ptr [rbx], 105000h
0x18001456e  mov     esi, r9d
0x180014571  mov     rcx, cs:WPP_GLOBAL_Control
0x180014578  cmp     rcx, r12
0x18001457b  jz      loc_180014753
0x180014581  test    byte ptr [rcx+1Ch], 1
0x180014585  jz      loc_180014753
0x18001458b  mov     edx, 1A7h
0x180014590  jmp     loc_180014747
0x180014595  cmp     dword ptr [rdi+0Ch], 2
0x180014599  jnz     loc_180014753
0x18001459f  xor     r9d, r9d
0x1800145a2  mov     r14d, 200h
0x1800145a8  mov     r10d, 20000h
0x1800145ae  cmp     r9d, [rdi+34h]
0x1800145b2  jnb     loc_1800146F8
0x1800145b8  cmp     bp, r14w
0x1800145bc  jnz     short loc_180014615
0x1800145be  mov     eax, r9d
0x1800145c1  imul    rcx, rax, 1Ch
0x1800145c5  mov     rax, [rdi+38h]
0x1800145c9  cmp     dword ptr [rcx+rax+0Ch], 6
0x1800145ce  jl      short loc_1800145D9
0x1800145d0  test    rbx, rbx
0x1800145d3  jnz     loc_1800146A0
0x1800145d9  cmp     dword ptr [rcx+rax+4], 3
0x1800145de  jge     short loc_1800145EE
0x1800145e0  cmp     dword ptr [rcx+rax+8], 3
0x1800145e5  jge     short loc_1800145EE
0x1800145e7  test    rbx, rbx
0x1800145ea  jz      short loc_1800145F7
0x1800145ec  jmp     short loc_18001461F
0x1800145ee  test    rbx, rbx
0x1800145f1  jnz     loc_1800146D0
0x1800145f7  cmp     dword ptr [rcx+rax+0Ch], 6
0x1800145fc  jge     short loc_18001460C
0x1800145fe  cmp     dword ptr [rcx+rax+4], 3
0x180014603  jge     short loc_18001460C
0x180014605  cmp     dword ptr [rcx+rax+8], 3
0x18001460a  jl      short loc_18001461F
0x18001460c  mov     [rdi+58h], r10d
0x180014610  jmp     loc_180014698
0x180014615  mov     eax, 209h
0x18001461a  cmp     bp, ax
0x18001461d  jnb     short loc_180014668
0x18001461f  mov     eax, r9d
0x180014622  imul    rcx, rax, 1Ch
0x180014626  mov     rax, [rdi+38h]
0x18001462a  cmp     dword ptr [rcx+rax], 4
0x18001462e  jl      short loc_180014668
0x180014630  test    rbx, rbx
0x180014633  jz      short loc_18001460C
0x180014635  mov     r9d, 57h ; 'W'
0x18001463b  mov     dword ptr [rbx], 105021h
0x180014641  mov     esi, r9d
0x180014644  mov     rcx, cs:WPP_GLOBAL_Control
0x18001464b  cmp     rcx, r12
0x18001464e  jz      loc_180014753
0x180014654  test    byte ptr [rcx+1Ch], 1
0x180014658  jz      loc_180014753
0x18001465e  mov     edx, 1AAh
0x180014663  jmp     loc_180014747
0x180014668  test    rbx, rbx
0x18001466b  jnz     short loc_180014698
0x18001466d  mov     r8, [rdi+38h]
0x180014671  mov     eax, r9d
0x180014674  imul    rdx, rax, 1Ch
0x180014678  mov     eax, r11d
0x18001467b  imul    rcx, rax, 1Ch
0x18001467f  movups  xmm0, xmmword ptr [rdx+r8]
0x180014684  inc     r11d
0x180014687  movups  xmmword ptr [rcx+r8], xmm0
0x18001468c  movups  xmm1, xmmword ptr [rdx+r8+0Ch]
0x180014692  movups  xmmword ptr [rcx+r8+0Ch], xmm1
0x180014698  inc     r9d
0x18001469b  jmp     loc_1800145AE
0x1800146a0  mov     r9d, 57h ; 'W'
0x1800146a6  mov     dword ptr [rbx], 105026h
0x1800146ac  mov     esi, r9d
0x1800146af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800146b6  cmp     rcx, r12
0x1800146b9  jz      loc_180014753
0x1800146bf  test    byte ptr [rcx+1Ch], 1
0x1800146c3  jz      loc_180014753
0x1800146c9  mov     edx, 1A8h
0x1800146ce  jmp     short loc_180014747
0x1800146d0  mov     r9d, 57h ; 'W'
0x1800146d6  mov     dword ptr [rbx], 105027h
0x1800146dc  mov     esi, r9d
0x1800146df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800146e6  cmp     rcx, r12
0x1800146e9  jz      short loc_180014753
0x1800146eb  test    byte ptr [rcx+1Ch], 1
0x1800146ef  jz      short loc_180014753
0x1800146f1  mov     edx, 1A9h
0x1800146f6  jmp     short loc_180014747
0x1800146f8  test    rbx, rbx
0x1800146fb  jnz     short loc_180014701
0x1800146fd  mov     [rdi+34h], r11d
0x180014701  mov     r9d, 210h
0x180014707  cmp     bp, r9w
0x18001470b  jnb     short loc_180014753
0x18001470d  cmp     dword ptr [rdi+30h], 8
0x180014711  jl      short loc_180014753
0x180014713  test    rbx, rbx
0x180014716  jnz     short loc_180014721
0x180014718  mov     dword ptr [rdi+58h], 40000h
0x18001471f  jmp     short loc_180014753
0x180014721  mov     r9d, 57h ; 'W'
0x180014727  mov     dword ptr [rbx], 105028h
0x18001472d  mov     esi, r9d
0x180014730  mov     rcx, cs:WPP_GLOBAL_Control
0x180014737  cmp     rcx, r12
0x18001473a  jz      short loc_180014753
0x18001473c  test    byte ptr [rcx+1Ch], 1
0x180014740  jz      short loc_180014753
0x180014742  mov     edx, 1ABh
0x180014747  mov     rcx, [rcx+10h]
0x18001474b  mov     r8, r13
0x18001474e  call    WPP_SF_d
0x180014753  mov     eax, esi
0x180014755  add     rsp, 20h
0x180014759  pop     r14
0x18001475b  pop     r13
0x18001475d  pop     r12
0x18001475f  pop     rdi
0x180014760  pop     rsi
0x180014761  pop     rbp
0x180014762  pop     rbx
0x180014763  retn
```
