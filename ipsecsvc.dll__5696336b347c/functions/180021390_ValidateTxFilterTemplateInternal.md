# ValidateTxFilterTemplateInternal

- ea: `0x180021390`
- end: `0x180021634`
- name: `ValidateTxFilterTemplateInternal`
- size: `676`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800209bc`

## callees

- `0x18000e510`
- `0x180016174`
- `0x1800161cc`
- `0x180016c7c`
- `0x180016e84`
- `0x18001725c`
- `0x180017348`
- `0x180021390`

## pseudocode

```c
__int64 __fastcall ValidateTxFilterTemplateInternal(__int64 a1)
{
  __int64 v2; // r9
  unsigned int v3; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rsi
  bool v7; // zf
  __int64 v8; // rcx
  int v9; // eax
  int v10; // eax

  if ( a1 )
  {
    v6 = a1 + 48;
    v7 = *(_DWORD *)a1 == 0;
    v8 = a1 + 48;
    if ( v7 )
    {
      v3 = VerifyAddresses4(v8);
      if ( v3 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          return v3;
        v5 = 61;
        goto LABEL_10;
      }
      v3 = VerifyAddresses4(a1 + 88);
      if ( v3 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          return v3;
        v5 = 62;
        goto LABEL_10;
      }
      v9 = AddressesConflict4(v6, a1 + 88);
    }
    else
    {
      v3 = VerifyAddresses6(v8);
      if ( v3 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          return v3;
        v5 = 63;
        goto LABEL_10;
      }
      v3 = VerifyAddresses6(a1 + 88);
      if ( v3 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          return v3;
        v5 = 64;
        goto LABEL_10;
      }
      v9 = AddressesConflict6(v6, a1 + 88);
    }
    if ( v9 )
    {
      v2 = 87;
      v3 = 87;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v5 = 65;
        goto LABEL_46;
      }
      return v3;
    }
    v3 = SpdVerifyProtocols(*(_QWORD *)(a1 + 128));
    if ( v3 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        return v3;
      v5 = 66;
    }
    else
    {
      v3 = SpdVerifyPortsForProtocol(a1 + 136, *(_QWORD *)(a1 + 128));
      if ( v3 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          return v3;
        v5 = 67;
      }
      else
      {
        v3 = SpdVerifyPortsForProtocol(a1 + 144, *(_QWORD *)(a1 + 128));
        if ( !v3 )
        {
          v10 = *(_DWORD *)(a1 + 160);
          if ( (v10 & 0xFFFFFFF3) != 0 || v10 == 12 )
          {
            v2 = 87;
            v3 = 87;
            v4 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            {
              v5 = 69;
              goto LABEL_46;
            }
          }
          return v3;
        }
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          return v3;
        v5 = 68;
      }
    }
LABEL_10:
    v2 = v3;
    goto LABEL_46;
  }
  v2 = 87;
  v3 = 87;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v5 = 60;
LABEL_46:
    WPP_SF_d(v4[2], v5, WPP_9e5bd0d0d2233fe69730d263c30676fb_Traceguids, v2);
  }
  return v3;
}

```

## disassembly

```asm
0x180021390  push    rbx
0x180021392  push    rbp
0x180021393  push    rsi
0x180021394  push    rdi
0x180021395  sub     rsp, 28h
0x180021399  mov     rdi, rcx
0x18002139c  test    rcx, rcx
0x18002139f  jnz     short loc_1800213D1
0x1800213a1  lea     r9d, [rcx+57h]
0x1800213a5  mov     ebx, r9d
0x1800213a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800213af  lea     rax, WPP_GLOBAL_Control
0x1800213b6  cmp     rcx, rax
0x1800213b9  jz      loc_180021629
0x1800213bf  test    byte ptr [rcx+1Ch], 10h
0x1800213c3  jz      loc_180021629
0x1800213c9  lea     edx, [rdi+3Ch]
0x1800213cc  jmp     loc_180021619
0x1800213d1  xor     r8d, r8d
0x1800213d4  lea     rsi, [rcx+30h]
0x1800213d8  cmp     [rcx], r8d
0x1800213db  mov     rcx, rsi
0x1800213de  jnz     loc_18002146B
0x1800213e4  call    VerifyAddresses4
0x1800213e9  mov     ebx, eax
0x1800213eb  test    eax, eax
0x1800213ed  jz      short loc_18002141D
0x1800213ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800213f6  lea     rax, WPP_GLOBAL_Control
0x1800213fd  cmp     rcx, rax
0x180021400  jz      loc_180021629
0x180021406  test    byte ptr [rcx+1Ch], 10h
0x18002140a  jz      loc_180021629
0x180021410  mov     edx, 3Dh ; '='
0x180021415  mov     r9d, ebx
0x180021418  jmp     loc_180021619
0x18002141d  mov     r8d, 1
0x180021423  lea     rcx, [rdi+58h]
0x180021427  call    VerifyAddresses4
0x18002142c  mov     ebx, eax
0x18002142e  test    eax, eax
0x180021430  jz      short loc_18002145A
0x180021432  mov     rcx, cs:WPP_GLOBAL_Control
0x180021439  lea     rax, WPP_GLOBAL_Control
0x180021440  cmp     rcx, rax
0x180021443  jz      loc_180021629
0x180021449  test    byte ptr [rcx+1Ch], 10h
0x18002144d  jz      loc_180021629
0x180021453  mov     edx, 3Eh ; '>'
0x180021458  jmp     short loc_180021415
0x18002145a  lea     rdx, [rdi+58h]
0x18002145e  mov     rcx, rsi
0x180021461  call    AddressesConflict4
0x180021466  jmp     loc_1800214ED
0x18002146b  call    VerifyAddresses6
0x180021470  mov     ebx, eax
0x180021472  test    eax, eax
0x180021474  jz      short loc_1800214A1
0x180021476  mov     rcx, cs:WPP_GLOBAL_Control
0x18002147d  lea     rax, WPP_GLOBAL_Control
0x180021484  cmp     rcx, rax
0x180021487  jz      loc_180021629
0x18002148d  test    byte ptr [rcx+1Ch], 10h
0x180021491  jz      loc_180021629
0x180021497  mov     edx, 3Fh ; '?'
0x18002149c  jmp     loc_180021415
0x1800214a1  mov     r8d, 1
0x1800214a7  lea     rcx, [rdi+58h]
0x1800214ab  call    VerifyAddresses6
0x1800214b0  mov     ebx, eax
0x1800214b2  test    eax, eax
0x1800214b4  jz      short loc_1800214E1
0x1800214b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800214bd  lea     rax, WPP_GLOBAL_Control
0x1800214c4  cmp     rcx, rax
0x1800214c7  jz      loc_180021629
0x1800214cd  test    byte ptr [rcx+1Ch], 10h
0x1800214d1  jz      loc_180021629
0x1800214d7  mov     edx, 40h ; '@'
0x1800214dc  jmp     loc_180021415
0x1800214e1  lea     rdx, [rdi+58h]
0x1800214e5  mov     rcx, rsi
0x1800214e8  call    AddressesConflict6
0x1800214ed  test    eax, eax
0x1800214ef  jz      short loc_180021524
0x1800214f1  mov     r9d, 57h ; 'W'
0x1800214f7  mov     ebx, r9d
0x1800214fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180021501  lea     rax, WPP_GLOBAL_Control
0x180021508  cmp     rcx, rax
0x18002150b  jz      loc_180021629
0x180021511  test    byte ptr [rcx+1Ch], 10h
0x180021515  jz      loc_180021629
0x18002151b  lea     edx, [r9-16h]
0x18002151f  jmp     loc_180021619
0x180021524  mov     rcx, [rdi+80h]
0x18002152b  call    SpdVerifyProtocols
0x180021530  mov     ebx, eax
0x180021532  test    eax, eax
0x180021534  jz      short loc_180021561
0x180021536  mov     rcx, cs:WPP_GLOBAL_Control
0x18002153d  lea     rax, WPP_GLOBAL_Control
0x180021544  cmp     rcx, rax
0x180021547  jz      loc_180021629
0x18002154d  test    byte ptr [rcx+1Ch], 10h
0x180021551  jz      loc_180021629
0x180021557  mov     edx, 42h ; 'B'
0x18002155c  jmp     loc_180021415
0x180021561  mov     rdx, [rdi+80h]
0x180021568  lea     rcx, [rdi+88h]
0x18002156f  call    SpdVerifyPortsForProtocol
0x180021574  mov     ebx, eax
0x180021576  test    eax, eax
0x180021578  jz      short loc_1800215A5
0x18002157a  mov     rcx, cs:WPP_GLOBAL_Control
0x180021581  lea     rax, WPP_GLOBAL_Control
0x180021588  cmp     rcx, rax
0x18002158b  jz      loc_180021629
0x180021591  test    byte ptr [rcx+1Ch], 10h
0x180021595  jz      loc_180021629
0x18002159b  mov     edx, 43h ; 'C'
0x1800215a0  jmp     loc_180021415
0x1800215a5  mov     rdx, [rdi+80h]
0x1800215ac  lea     rcx, [rdi+90h]
0x1800215b3  call    SpdVerifyPortsForProtocol
0x1800215b8  mov     ebx, eax
0x1800215ba  test    eax, eax
0x1800215bc  jz      short loc_1800215E1
0x1800215be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800215c5  lea     rax, WPP_GLOBAL_Control
0x1800215cc  cmp     rcx, rax
0x1800215cf  jz      short loc_180021629
0x1800215d1  test    byte ptr [rcx+1Ch], 10h
0x1800215d5  jz      short loc_180021629
0x1800215d7  mov     edx, 44h ; 'D'
0x1800215dc  jmp     loc_180021415
0x1800215e1  mov     eax, [rdi+0A0h]
0x1800215e7  test    eax, 0FFFFFFF3h
0x1800215ec  jnz     short loc_1800215F3
0x1800215ee  cmp     eax, 0Ch
0x1800215f1  jnz     short loc_180021629
0x1800215f3  mov     r9d, 57h ; 'W'
0x1800215f9  mov     ebx, r9d
0x1800215fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180021603  lea     rax, WPP_GLOBAL_Control
0x18002160a  cmp     rcx, rax
0x18002160d  jz      short loc_180021629
0x18002160f  test    byte ptr [rcx+1Ch], 10h
0x180021613  jz      short loc_180021629
0x180021615  lea     edx, [r9-12h]
0x180021619  mov     rcx, [rcx+10h]
0x18002161d  lea     r8, WPP_9e5bd0d0d2233fe69730d263c30676fb_Traceguids
0x180021624  call    WPP_SF_d
0x180021629  mov     eax, ebx
0x18002162b  add     rsp, 28h
0x18002162f  pop     rdi
0x180021630  pop     rsi
0x180021631  pop     rbp
0x180021632  pop     rbx
0x180021633  retn
```
