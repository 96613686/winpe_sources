# WriterOpenExclusive

- ea: `0x1800140ac`
- end: `0x180014281`
- name: `WriterOpenExclusive`
- size: `469`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x18000b650`
- `0x18000d830`
- `0x18000ec90`
- `0x18000fd40`

## callees

- `0x180007bac`
- `0x180007bd4`
- `0x180007d40`
- `0x180007d80`
- `0x1800127ec`
- `0x1800140ac`
- `0x180019010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001413d`
- `OLEAUT32!__imp_SysAllocString` at `0x18001413d`
- `OLEAUT32!__imp_SysFreeString` at `0x180014197`
- `OLEAUT32!__imp_SysFreeString` at `0x180014197`

## pseudocode

```c
__int64 __fastcall WriterOpenExclusive(_QWORD *a1, char a2)
{
  _QWORD *v3; // rcx
  unsigned int v4; // edi
  OLECHAR *v5; // r15
  int v6; // eax
  int v8; // eax

  if ( !a1 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 63, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
      v3 = WPP_GLOBAL_Control;
    }
    v4 = -2147024809;
    goto LABEL_17;
  }
  if ( a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 64, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, a1);
    v5 = SysAllocString(L"IMAPIv1 Shim");
    v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, OLECHAR *))(*(_QWORD *)*a1 + 72LL))(*a1, 0xFFFFFFFFLL, v5);
    v4 = v6;
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          65,
          &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids,
          (unsigned int)v6);
      v4 = TranslateIMAPI2Error(v4);
    }
    SysFreeString(v5);
LABEL_16:
    v3 = WPP_GLOBAL_Control;
    goto LABEL_17;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 66, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, a1);
  v8 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 80LL))(*a1);
  v4 = v8;
  if ( v8 >= 0 )
    goto LABEL_16;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        67,
        &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids,
        (unsigned int)v8);
      v3 = WPP_GLOBAL_Control;
    }
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 68) & 1) != 0 )
    {
      WPP_SF_(v3[7], 68, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
      v3 = WPP_GLOBAL_Control;
    }
  }
  v4 = 0;
LABEL_17:
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 68) & 1) != 0 )
    WPP_SF_qD(v3[7], 69, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, a1, v4);
  return v4;
}

```

## disassembly

```asm
0x1800140ac  push    rsi
0x1800140ae  push    rdi
0x1800140af  push    r14
0x1800140b1  push    r15
0x1800140b3  sub     rsp, 38h
0x1800140b7  mov     r14, rcx
0x1800140ba  test    rcx, rcx
0x1800140bd  jnz     short loc_1800140FD
0x1800140bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800140c6  lea     rsi, WPP_GLOBAL_Control
0x1800140cd  cmp     rcx, rsi
0x1800140d0  jz      short loc_1800140F3
0x1800140d2  test    byte ptr [rcx+44h], 1
0x1800140d6  jz      short loc_1800140F3
0x1800140d8  mov     rcx, [rcx+38h]
0x1800140dc  lea     edx, [r14+3Fh]
0x1800140e0  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x1800140e7  call    WPP_SF_
0x1800140ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800140f3  mov     edi, 80070057h
0x1800140f8  jmp     loc_1800141A4
0x1800140fd  test    dl, dl
0x1800140ff  jz      loc_1800141D8
0x180014105  mov     rcx, cs:WPP_GLOBAL_Control
0x18001410c  lea     rsi, WPP_GLOBAL_Control
0x180014113  cmp     rcx, rsi
0x180014116  jz      short loc_180014136
0x180014118  test    byte ptr [rcx+44h], 1
0x18001411c  jz      short loc_180014136
0x18001411e  mov     rcx, [rcx+38h]
0x180014122  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x180014129  mov     edx, 40h ; '@'
0x18001412e  mov     r9, r14
0x180014131  call    WPP_SF_q
0x180014136  lea     rcx, psz; "IMAPIv1 Shim"
0x18001413d  call    cs:__imp_SysAllocString
0x180014143  mov     rcx, [r14]
0x180014146  or      edx, 0FFFFFFFFh
0x180014149  mov     r15, rax
0x18001414c  mov     r8, r15
0x18001414f  mov     rax, [rcx]
0x180014152  mov     rax, [rax+48h]
0x180014156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001415b  mov     edi, eax
0x18001415d  test    eax, eax
0x18001415f  jns     short loc_180014194
0x180014161  mov     rcx, cs:WPP_GLOBAL_Control
0x180014168  cmp     rcx, rsi
0x18001416b  jz      short loc_18001418B
0x18001416d  test    byte ptr [rcx+44h], 1
0x180014171  jz      short loc_18001418B
0x180014173  mov     rcx, [rcx+38h]
0x180014177  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x18001417e  mov     edx, 41h ; 'A'
0x180014183  mov     r9d, eax
0x180014186  call    WPP_SF_d
0x18001418b  mov     ecx, edi
0x18001418d  call    TranslateIMAPI2Error
0x180014192  mov     edi, eax
0x180014194  mov     rcx, r15; bstrString
0x180014197  call    cs:__imp_SysFreeString
0x18001419d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800141a4  cmp     rcx, rsi
0x1800141a7  jz      short loc_1800141CB
0x1800141a9  test    byte ptr [rcx+44h], 1
0x1800141ad  jz      short loc_1800141CB
0x1800141af  mov     rcx, [rcx+38h]
0x1800141b3  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x1800141ba  mov     edx, 45h ; 'E'
0x1800141bf  mov     [rsp+58h+var_38], edi
0x1800141c3  mov     r9, r14
0x1800141c6  call    WPP_SF_qD
0x1800141cb  mov     eax, edi
0x1800141cd  add     rsp, 38h
0x1800141d1  pop     r15
0x1800141d3  pop     r14
0x1800141d5  pop     rdi
0x1800141d6  pop     rsi
0x1800141d7  retn
0x1800141d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800141df  lea     rsi, WPP_GLOBAL_Control
0x1800141e6  cmp     rcx, rsi
0x1800141e9  jz      short loc_180014209
0x1800141eb  test    byte ptr [rcx+44h], 1
0x1800141ef  jz      short loc_180014209
0x1800141f1  mov     rcx, [rcx+38h]
0x1800141f5  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x1800141fc  mov     edx, 42h ; 'B'
0x180014201  mov     r9, r14
0x180014204  call    WPP_SF_q
0x180014209  mov     rcx, [r14]
0x18001420c  mov     rax, [rcx]
0x18001420f  mov     rax, [rax+50h]
0x180014213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014218  mov     edi, eax
0x18001421a  test    eax, eax
0x18001421c  jns     loc_18001419D
0x180014222  mov     rcx, cs:WPP_GLOBAL_Control
0x180014229  cmp     rcx, rsi
0x18001422c  jz      short loc_18001427A
0x18001422e  test    byte ptr [rcx+44h], 1
0x180014232  jz      short loc_180014253
0x180014234  mov     rcx, [rcx+38h]
0x180014238  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x18001423f  mov     edx, 43h ; 'C'
0x180014244  mov     r9d, eax
0x180014247  call    WPP_SF_d
0x18001424c  mov     rcx, cs:WPP_GLOBAL_Control
0x180014253  cmp     rcx, rsi
0x180014256  jz      short loc_18001427A
0x180014258  test    byte ptr [rcx+44h], 1
0x18001425c  jz      short loc_18001427A
0x18001425e  mov     rcx, [rcx+38h]
0x180014262  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x180014269  mov     edx, 44h ; 'D'
0x18001426e  call    WPP_SF_
0x180014273  mov     rcx, cs:WPP_GLOBAL_Control
0x18001427a  xor     edi, edi
0x18001427c  jmp     loc_1800141A4
```
