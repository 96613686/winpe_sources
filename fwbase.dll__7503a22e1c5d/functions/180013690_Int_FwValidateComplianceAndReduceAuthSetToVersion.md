# Int_FwValidateComplianceAndReduceAuthSetToVersion

- ea: `0x180013690`
- end: `0x1800138a6`
- name: `Int_FwValidateComplianceAndReduceAuthSetToVersion`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180014cb0`

## callees

- `0x18000ccd4`
- `0x1800135f0`
- `0x180013690`
- `0x180017d1c`

## pseudocode

```c
__int64 __fastcall Int_FwValidateComplianceAndReduceAuthSetToVersion(__int64 a1, _DWORD *a2, unsigned __int16 a3)
{
  __int64 v6; // rbp
  __int64 i; // rdi
  unsigned int v8; // edi
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 356, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids);
  v6 = 0;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= *(_DWORD *)(a1 + 48) )
    {
      v8 = 0;
      if ( !a2 )
        *(_DWORD *)(a1 + 48) = v6;
      return v8;
    }
    if ( a3 == 512 )
    {
      if ( (*(_BYTE *)(*(_QWORD *)(a1 + 56) + 24 * i + 4) & 0x18) != 0 )
      {
        if ( a2 )
        {
          *a2 = 1052738;
          v8 = 87;
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v10 = 357;
            goto LABEL_32;
          }
          return v8;
        }
        goto LABEL_9;
      }
    }
    else if ( a3 >= 0x209u )
    {
      goto LABEL_16;
    }
    if ( (*(_BYTE *)(*(_QWORD *)(a1 + 56) + 24LL * (unsigned int)i + 4) & 0x20) != 0 )
    {
      if ( a2 )
      {
        *a2 = 1052739;
        v8 = 87;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v10 = 358;
LABEL_32:
          WPP_SF_d(v9[2], v10, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
          return v8;
        }
        return v8;
      }
      goto LABEL_9;
    }
LABEL_16:
    v11 = 24LL * (unsigned int)i;
    if ( a3 >= 0x214u )
      goto LABEL_26;
    v12 = v11 + *(_QWORD *)(a1 + 56);
    if ( ((*(_DWORD *)v12 - 5) & 0xFFFFFFFD) != 0 || !*(_QWORD *)(v12 + 16) )
      break;
    if ( a2 )
    {
      *a2 = 1052785;
      v8 = 87;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v10 = 359;
        goto LABEL_32;
      }
      return v8;
    }
    *(_DWORD *)(a1 + 80) = 0x20000;
    FwAuthSuiteEmptyByVersion(v12, 545);
LABEL_28:
    ;
  }
  if ( (*(_BYTE *)(v12 + 4) & 0x40) == 0 )
  {
LABEL_26:
    if ( !a2 )
    {
      v13 = *(_QWORD *)(a1 + 56);
      v14 = 3 * v6;
      v6 = (unsigned int)(v6 + 1);
      *(_OWORD *)(v13 + 8 * v14) = *(_OWORD *)(v13 + 24LL * (unsigned int)i);
      *(_QWORD *)(v13 + 8 * v14 + 16) = *(_QWORD *)(v13 + v11 + 16);
    }
    goto LABEL_28;
  }
  if ( !a2 )
  {
LABEL_9:
    *(_DWORD *)(a1 + 80) = 0x20000;
    goto LABEL_28;
  }
  *a2 = 1052801;
  v8 = 87;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v10 = 360;
    goto LABEL_32;
  }
  return v8;
}

```

## disassembly

```asm
0x180013690  push    rbx
0x180013692  push    rbp
0x180013693  push    rsi
0x180013694  push    rdi
0x180013695  push    r12
0x180013697  push    r13
0x180013699  push    r14
0x18001369b  sub     rsp, 20h
0x18001369f  movzx   r14d, r8w
0x1800136a3  mov     rbx, rdx
0x1800136a6  mov     rsi, rcx
0x1800136a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800136b0  lea     r12, WPP_GLOBAL_Control
0x1800136b7  lea     r13, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids
0x1800136be  cmp     rcx, r12
0x1800136c1  jz      short loc_1800136DA
0x1800136c3  test    byte ptr [rcx+1Ch], 8
0x1800136c7  jz      short loc_1800136DA
0x1800136c9  mov     rcx, [rcx+10h]
0x1800136cd  mov     edx, 164h
0x1800136d2  mov     r8, r13
0x1800136d5  call    WPP_SF_
0x1800136da  xor     ebp, ebp
0x1800136dc  mov     r9d, 20000h
0x1800136e2  xor     edi, edi
0x1800136e4  cmp     edi, [rsi+30h]
0x1800136e7  jnb     loc_18001388B
0x1800136ed  mov     eax, 200h
0x1800136f2  mov     edx, edi
0x1800136f4  cmp     r14w, ax
0x1800136f8  jnz     short loc_18001371B
0x1800136fa  mov     rax, [rsi+38h]
0x1800136fe  lea     rcx, [rdi+rdi*2]
0x180013702  test    byte ptr [rax+rcx*8+4], 18h
0x180013707  jz      short loc_180013726
0x180013709  test    rbx, rbx
0x18001370c  jnz     loc_18001382F
0x180013712  mov     [rsi+50h], r9d
0x180013716  jmp     loc_180013828
0x18001371b  mov     eax, 209h
0x180013720  cmp     r14w, ax
0x180013724  jnb     short loc_18001376D
0x180013726  mov     rax, [rsi+38h]
0x18001372a  lea     rcx, [rdx+rdx*2]
0x18001372e  test    byte ptr [rax+rcx*8+4], 20h
0x180013733  jz      short loc_18001376D
0x180013735  test    rbx, rbx
0x180013738  jz      short loc_180013712
0x18001373a  mov     r9d, 57h ; 'W'
0x180013740  mov     dword ptr [rbx], 101043h
0x180013746  mov     edi, r9d
0x180013749  mov     rcx, cs:WPP_GLOBAL_Control
0x180013750  cmp     rcx, r12
0x180013753  jz      loc_180013895
0x180013759  test    byte ptr [rcx+1Ch], 1
0x18001375d  jz      loc_180013895
0x180013763  mov     edx, 166h
0x180013768  jmp     loc_180013855
0x18001376d  lea     rax, [rdx+rdx*2]
0x180013771  lea     r8, ds:0[rax*8]
0x180013779  mov     eax, 214h
0x18001377e  cmp     r14w, ax
0x180013782  jnb     short loc_1800137FC
0x180013784  mov     rcx, [rsi+38h]
0x180013788  add     rcx, r8
0x18001378b  mov     eax, [rcx]
0x18001378d  sub     eax, 5
0x180013790  test    eax, 0FFFFFFFDh
0x180013795  jnz     short loc_1800137BD
0x180013797  cmp     qword ptr [rcx+10h], 0
0x18001379c  jz      short loc_1800137BD
0x18001379e  test    rbx, rbx
0x1800137a1  jnz     loc_180013863
0x1800137a7  mov     edx, 221h
0x1800137ac  mov     [rsi+50h], r9d
0x1800137b0  call    FwAuthSuiteEmptyByVersion
0x1800137b5  mov     r9d, 20000h
0x1800137bb  jmp     short loc_180013828
0x1800137bd  test    byte ptr [rcx+4], 40h
0x1800137c1  jz      short loc_1800137FC
0x1800137c3  test    rbx, rbx
0x1800137c6  jz      loc_180013712
0x1800137cc  mov     r9d, 57h ; 'W'
0x1800137d2  mov     dword ptr [rbx], 101081h
0x1800137d8  mov     edi, r9d
0x1800137db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800137e2  cmp     rcx, r12
0x1800137e5  jz      loc_180013895
0x1800137eb  test    byte ptr [rcx+1Ch], 1
0x1800137ef  jz      loc_180013895
0x1800137f5  mov     edx, 168h
0x1800137fa  jmp     short loc_180013855
0x1800137fc  test    rbx, rbx
0x1800137ff  jnz     short loc_180013828
0x180013801  mov     rdx, [rsi+38h]
0x180013805  lea     rcx, ds:0[rbp*2]
0x18001380d  add     rcx, rbp
0x180013810  inc     ebp
0x180013812  movups  xmm0, xmmword ptr [rdx+r8]
0x180013817  movups  xmmword ptr [rdx+rcx*8], xmm0
0x18001381b  movsd   xmm1, qword ptr [rdx+r8+10h]
0x180013822  movsd   qword ptr [rdx+rcx*8+10h], xmm1
0x180013828  inc     edi
0x18001382a  jmp     loc_1800136E4
0x18001382f  mov     r9d, 57h ; 'W'
0x180013835  mov     dword ptr [rbx], 101042h
0x18001383b  mov     edi, r9d
0x18001383e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013845  cmp     rcx, r12
0x180013848  jz      short loc_180013895
0x18001384a  test    byte ptr [rcx+1Ch], 1
0x18001384e  jz      short loc_180013895
0x180013850  mov     edx, 165h
0x180013855  mov     rcx, [rcx+10h]
0x180013859  mov     r8, r13
0x18001385c  call    WPP_SF_d
0x180013861  jmp     short loc_180013895
0x180013863  mov     r9d, 57h ; 'W'
0x180013869  mov     dword ptr [rbx], 101071h
0x18001386f  mov     edi, r9d
0x180013872  mov     rcx, cs:WPP_GLOBAL_Control
0x180013879  cmp     rcx, r12
0x18001387c  jz      short loc_180013895
0x18001387e  test    byte ptr [rcx+1Ch], 1
0x180013882  jz      short loc_180013895
0x180013884  mov     edx, 167h
0x180013889  jmp     short loc_180013855
0x18001388b  xor     edi, edi
0x18001388d  test    rbx, rbx
0x180013890  jnz     short loc_180013895
0x180013892  mov     [rsi+30h], ebp
0x180013895  mov     eax, edi
0x180013897  add     rsp, 20h
0x18001389b  pop     r14
0x18001389d  pop     r13
0x18001389f  pop     r12
0x1800138a1  pop     rdi
0x1800138a2  pop     rsi
0x1800138a3  pop     rbp
0x1800138a4  pop     rbx
0x1800138a5  retn
```
