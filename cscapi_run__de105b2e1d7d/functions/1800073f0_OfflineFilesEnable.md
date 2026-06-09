# OfflineFilesEnable

- ea: `0x1800073f0`
- end: `0x18000786d`
- name: `OfflineFilesEnable`
- size: `1149`
- prototype: `DWORD __stdcall(BOOL bEnable, BOOL *pbRebootRequired)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task`

## callees

- `0x180004cf0`
- `0x1800052f0`
- `0x1800057f0`
- `0x1800073f0`
- `0x180007bcc`
- `0x180007bf4`
- `0x180007c34`
- `0x180007d30`
- `0x180007ee8`
- `0x180007f3c`
- `0x180007ff4`
- `0x180008118`

## string_xrefs

- `0x18000771b`: `CscService`

## pseudocode

```c
DWORD __stdcall OfflineFilesEnable(BOOL bEnable, BOOL *pbRebootRequired)
{
  __int64 v2; // r8
  DWORD started; // ebx
  _QWORD *v6; // rcx
  int v7; // esi
  const char *v8; // r9
  _BOOL8 v9; // r8
  int v10; // ecx
  _BOOL8 v11; // rdx
  _BOOL8 v12; // r14
  DWORD v13; // r9d
  _BOOL8 v14; // r13
  _BOOL8 v15; // r12
  const wchar_t *v16; // r9
  const wchar_t *v17; // rax
  __int64 v18; // rcx
  const wchar_t *v19; // r9
  __int64 v21; // rdx
  DWORD v22; // [rsp+30h] [rbp-20h] BYREF
  BOOL v23; // [rsp+34h] [rbp-1Ch]
  BOOL v24; // [rsp+38h] [rbp-18h]
  DWORD v25; // [rsp+3Ch] [rbp-14h]
  DWORD v26; // [rsp+40h] [rbp-10h]
  DWORD v27; // [rsp+98h] [rbp+48h] BYREF
  int v28; // [rsp+A0h] [rbp+50h] BYREF
  DWORD v29; // [rsp+A8h] [rbp+58h] BYREF

  started = 87;
  v6 = WPP_GLOBAL_Control;
  v7 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
  {
    v8 = "Enabling";
    if ( !bEnable )
      v8 = "Disabling";
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 22), pbRebootRequired, v2, v8);
    v6 = WPP_GLOBAL_Control;
  }
  if ( pbRebootRequired )
  {
    v27 = 0;
    v28 = 0;
    *pbRebootRequired = 0;
    started = QueryDriverAndServiceState(&v27, &v28);
    if ( started )
      goto LABEL_32;
    v22 = 0;
    v29 = 0;
    started = QueryDriverAndServiceStartType(&v22, &v29);
    if ( started )
      goto LABEL_32;
    v25 = bEnable ? 1 : 4;
    v26 = bEnable ? 2 : 4;
    v10 = bEnable ? 4 : 1;
    v11 = v27 == 4;
    v23 = v27 == 4;
    v9 = v28 == 4;
    v24 = v28 == 4;
    v27 = v27 != v10;
    v12 = v28 != v10;
    v13 = v29;
    v14 = v22 != v25;
    v15 = v29 != v26;
    if ( v27 || (v28 = 0, v12) )
      v28 = 1;
    if ( v22 != v25 || v29 != v26 )
      v7 = 1;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
      {
        v16 = L"is";
        v17 = L"is";
        if ( !v9 )
          v17 = L"is not";
        if ( !v11 )
          v16 = L"is not";
        WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 22), v11, (unsigned int)L"is not", (_DWORD)v16, (__int64)v17);
        v6 = WPP_GLOBAL_Control;
        v13 = v29;
      }
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 188) & 1) != 0 )
      {
        WPP_SF_dd(v6[22], 29, v9, v22, v13);
        v6 = WPP_GLOBAL_Control;
      }
    }
    if ( !v12 && !v27 && !v15 && !v14 )
    {
      if ( v6 == &WPP_GLOBAL_Control )
        return started;
      if ( (*((_BYTE *)v6 + 188) & 1) == 0 )
        goto LABEL_33;
      WPP_SF_(v6[22], 30, WPP_00d7c4231f3f33ca0a28c368a7ccec1f_Traceguids);
      goto LABEL_32;
    }
    if ( v7 )
    {
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 188) & 2) != 0 )
        WPP_SF_(v6[22], 31, WPP_00d7c4231f3f33ca0a28c368a7ccec1f_Traceguids);
      v27 = 0;
      started = QueryDriverOrServiceStartType(L"Csc", &v27);
      if ( !started )
      {
        started = SetDriverOrServiceStartType(L"Csc", v25);
        if ( !started )
        {
          started = SetDriverOrServiceStartType(L"CscService", v26);
          if ( started )
          {
            SetDriverOrServiceStartType(L"Csc", v27);
LABEL_32:
            v6 = WPP_GLOBAL_Control;
LABEL_33:
            if ( v6 == &WPP_GLOBAL_Control )
              return started;
            if ( (*((_BYTE *)v6 + 188) & 2) != 0 )
            {
              v18 = v6[22];
              v19 = L"is";
              if ( !*pbRebootRequired )
                v19 = L"is not";
              WPP_SF_S(v18, 37, v9, v19);
              v6 = WPP_GLOBAL_Control;
            }
            goto LABEL_38;
          }
        }
      }
      if ( started )
        goto LABEL_32;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 32, WPP_00d7c4231f3f33ca0a28c368a7ccec1f_Traceguids);
        v6 = WPP_GLOBAL_Control;
      }
    }
    if ( !v28 )
      goto LABEL_33;
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 188) & 2) != 0 )
    {
      WPP_SF_(v6[22], 33, WPP_00d7c4231f3f33ca0a28c368a7ccec1f_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
    if ( bEnable )
    {
      if ( v23 )
      {
        if ( v24 )
          goto LABEL_33;
        if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 188) & 2) != 0 )
          WPP_SF_(v6[22], 34, WPP_00d7c4231f3f33ca0a28c368a7ccec1f_Traceguids);
        started = StartDriverOrService();
        goto LABEL_32;
      }
      if ( v6 == &WPP_GLOBAL_Control || (*((_BYTE *)v6 + 188) & 2) == 0 )
        goto LABEL_69;
      v21 = 36;
    }
    else
    {
      if ( !v23 && !v24 )
        goto LABEL_33;
      if ( v6 == &WPP_GLOBAL_Control || (*((_BYTE *)v6 + 188) & 2) == 0 )
        goto LABEL_69;
      v21 = 35;
    }
    WPP_SF_(v6[22], v21, WPP_00d7c4231f3f33ca0a28c368a7ccec1f_Traceguids);
LABEL_69:
    *pbRebootRequired = 1;
    goto LABEL_32;
  }
LABEL_38:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 188) & 2) != 0 )
    WPP_SF_d(v6[22], 38, WPP_00d7c4231f3f33ca0a28c368a7ccec1f_Traceguids, started);
  return started;
}

```

## disassembly

```asm
0x1800073f0  mov     [rsp-38h+arg_0], rbx
0x1800073f5  push    rbp
0x1800073f6  push    rsi
0x1800073f7  push    rdi
0x1800073f8  push    r12
0x1800073fa  push    r13
0x1800073fc  push    r14
0x1800073fe  push    r15
0x180007400  mov     rbp, rsp
0x180007403  sub     rsp, 50h
0x180007407  mov     rdi, rdx
0x18000740a  mov     r15d, ecx
0x18000740d  mov     ebx, 57h ; 'W'
0x180007412  mov     rcx, cs:WPP_GLOBAL_Control
0x180007419  lea     rax, WPP_GLOBAL_Control
0x180007420  xor     esi, esi
0x180007422  cmp     rcx, rax
0x180007425  jz      short loc_180007458
0x180007427  test    byte ptr [rcx+0BCh], 1
0x18000742e  jz      short loc_180007458
0x180007430  mov     rcx, [rcx+0B0h]
0x180007437  lea     rax, aDisabling; "Disabling"
0x18000743e  test    r15d, r15d
0x180007441  lea     r9, aEnabling; "Enabling"
0x180007448  cmovz   r9, rax
0x18000744c  call    WPP_SF_s
0x180007451  mov     rcx, cs:WPP_GLOBAL_Control
0x180007458  test    rdi, rdi
0x18000745b  jz      loc_18000766A
0x180007461  lea     rdx, [rbp+arg_10]
0x180007465  mov     [rbp+arg_8], esi
0x180007468  lea     rcx, [rbp+arg_8]
0x18000746c  mov     [rbp+arg_10], esi
0x18000746f  mov     [rdi], esi
0x180007471  call    _QueryDriverAndServiceState
0x180007476  mov     ebx, eax
0x180007478  test    eax, eax
0x18000747a  jnz     loc_180007621
0x180007480  lea     rdx, [rbp+arg_18]
0x180007484  mov     [rbp+var_20], esi
0x180007487  lea     rcx, [rbp+var_20]
0x18000748b  mov     [rbp+arg_18], esi
0x18000748e  call    _QueryDriverAndServiceStartType
0x180007493  mov     ebx, eax
0x180007495  test    eax, eax
0x180007497  jnz     loc_180007621
0x18000749d  mov     edx, esi
0x18000749f  mov     eax, r15d
0x1800074a2  neg     eax
0x1800074a4  mov     r8d, esi
0x1800074a7  mov     eax, r15d
0x1800074aa  mov     r14d, esi
0x1800074ad  sbb     r9d, r9d
0x1800074b0  mov     r13d, esi
0x1800074b3  and     r9d, 0FFFFFFFDh
0x1800074b7  mov     r12d, esi
0x1800074ba  add     r9d, 4
0x1800074be  neg     eax
0x1800074c0  mov     [rbp+var_14], r9d
0x1800074c4  mov     eax, r15d
0x1800074c7  sbb     r10d, r10d
0x1800074ca  and     r10d, 0FFFFFFFEh
0x1800074ce  add     r10d, 4
0x1800074d2  neg     eax
0x1800074d4  mov     [rbp+var_10], r10d
0x1800074d8  mov     eax, esi
0x1800074da  sbb     ecx, ecx
0x1800074dc  and     ecx, 3
0x1800074df  inc     ecx
0x1800074e1  cmp     [rbp+arg_8], 4
0x1800074e5  setz    dl
0x1800074e8  cmp     [rbp+arg_10], 4
0x1800074ec  mov     [rbp+var_1C], edx
0x1800074ef  setz    r8b
0x1800074f3  cmp     [rbp+arg_8], ecx
0x1800074f6  mov     [rbp+var_18], r8d
0x1800074fa  setnz   al
0x1800074fd  cmp     [rbp+arg_10], ecx
0x180007500  mov     [rbp+arg_8], eax
0x180007503  setnz   r14b
0x180007507  cmp     [rbp+var_20], r9d
0x18000750b  mov     r9d, [rbp+arg_18]
0x18000750f  setnz   r13b
0x180007513  cmp     r9d, r10d
0x180007516  setnz   r12b
0x18000751a  test    eax, eax
0x18000751c  jnz     short loc_180007526
0x18000751e  mov     [rbp+arg_10], esi
0x180007521  test    r14d, r14d
0x180007524  jz      short loc_18000752D
0x180007526  mov     [rbp+arg_10], 1
0x18000752d  test    r13d, r13d
0x180007530  jnz     short loc_180007537
0x180007532  test    r12d, r12d
0x180007535  jz      short loc_18000753C
0x180007537  mov     esi, 1
0x18000753c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007543  lea     rax, WPP_GLOBAL_Control
0x18000754a  cmp     rcx, rax
0x18000754d  jz      loc_1800075D3
0x180007553  test    byte ptr [rcx+0BCh], 1
0x18000755a  jz      short loc_18000759D
0x18000755c  mov     rcx, [rcx+0B0h]
0x180007563  lea     r9, aIs; "is"
0x18000756a  test    r8d, r8d
0x18000756d  mov     rax, r9
0x180007570  lea     r8, aIsNot; "is not"
0x180007577  cmovz   rax, r8
0x18000757b  test    edx, edx
0x18000757d  mov     [rsp+50h+var_30], rax
0x180007582  cmovz   r9, r8
0x180007586  call    WPP_SF_SS
0x18000758b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007592  lea     rax, WPP_GLOBAL_Control
0x180007599  mov     r9d, [rbp+arg_18]
0x18000759d  cmp     rcx, rax
0x1800075a0  jz      short loc_1800075D3
0x1800075a2  test    byte ptr [rcx+0BCh], 1
0x1800075a9  jz      short loc_1800075D3
0x1800075ab  mov     rcx, [rcx+0B0h]
0x1800075b2  mov     edx, 1Dh
0x1800075b7  mov     dword ptr [rsp+50h+var_30], r9d
0x1800075bc  mov     r9d, [rbp+var_20]
0x1800075c0  call    WPP_SF_dd
0x1800075c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800075cc  lea     rax, WPP_GLOBAL_Control
0x1800075d3  test    r14d, r14d
0x1800075d6  jnz     loc_1800076B4
0x1800075dc  cmp     [rbp+arg_8], r14d
0x1800075e0  jnz     loc_1800076B4
0x1800075e6  test    r12d, r12d
0x1800075e9  jnz     loc_1800076B4
0x1800075ef  test    r13d, r13d
0x1800075f2  jnz     loc_1800076B4
0x1800075f8  cmp     rcx, rax
0x1800075fb  jz      loc_18000769A
0x180007601  test    byte ptr [rcx+0BCh], 1
0x180007608  jz      short loc_18000762F
0x18000760a  mov     rcx, [rcx+0B0h]
0x180007611  lea     edx, [r14+1Eh]
0x180007615  lea     r8, WPP_00d7c4231f3f33ca0a28c368a7ccec1f_Traceguids
0x18000761c  call    WPP_SF_
0x180007621  lea     rax, WPP_GLOBAL_Control
0x180007628  mov     rcx, cs:WPP_GLOBAL_Control
0x18000762f  cmp     rcx, rax
0x180007632  jz      short loc_18000769A
0x180007634  test    byte ptr [rcx+0BCh], 2
0x18000763b  jz      short loc_18000766A
0x18000763d  cmp     dword ptr [rdi], 0
0x180007640  lea     rdx, aIsNot; "is not"
0x180007647  mov     rcx, [rcx+0B0h]
0x18000764e  lea     r9, aIs; "is"
0x180007655  cmovz   r9, rdx
0x180007659  mov     edx, 25h ; '%'
0x18000765e  call    WPP_SF_S
0x180007663  mov     rcx, cs:WPP_GLOBAL_Control
0x18000766a  lea     rdi, WPP_GLOBAL_Control
0x180007671  cmp     rcx, rdi
0x180007674  jz      short loc_18000769A
0x180007676  test    byte ptr [rcx+0BCh], 2
0x18000767d  jz      short loc_18000769A
0x18000767f  mov     rcx, [rcx+0B0h]
0x180007686  lea     r8, WPP_00d7c4231f3f33ca0a28c368a7ccec1f_Traceguids
0x18000768d  mov     edx, 26h ; '&'
0x180007692  mov     r9d, ebx
0x180007695  call    WPP_SF_d
0x18000769a  mov     eax, ebx
0x18000769c  mov     rbx, [rsp+50h+arg_0]
0x1800076a4  add     rsp, 50h
0x1800076a8  pop     r15
0x1800076aa  pop     r14
0x1800076ac  pop     r13
0x1800076ae  pop     r12
0x1800076b0  pop     rdi
0x1800076b1  pop     rsi
0x1800076b2  pop     rbp
0x1800076b3  retn
0x1800076b4  test    esi, esi
0x1800076b6  jz      loc_180007787
0x1800076bc  lea     r9, WPP_GLOBAL_Control
0x1800076c3  cmp     rcx, r9
0x1800076c6  jz      short loc_1800076E9
0x1800076c8  test    byte ptr [rcx+0BCh], 2
0x1800076cf  jz      short loc_1800076E9
0x1800076d1  mov     rcx, [rcx+0B0h]
0x1800076d8  lea     r8, WPP_00d7c4231f3f33ca0a28c368a7ccec1f_Traceguids
0x1800076df  mov     edx, 1Fh
0x1800076e4  call    WPP_SF_
0x1800076e9  lea     r14, g_szCscDriverName; "Csc"
0x1800076f0  xor     esi, esi
0x1800076f2  mov     rcx, r14; lpServiceName
0x1800076f5  mov     [rbp+arg_8], esi
0x1800076f8  lea     rdx, [rbp+arg_8]
0x1800076fc  call    _QueryDriverOrServiceStartType
0x180007701  mov     ebx, eax
0x180007703  test    eax, eax
0x180007705  jnz     short loc_18000773D
0x180007707  mov     edx, [rbp+var_14]
0x18000770a  mov     rcx, r14
0x18000770d  call    _SetDriverOrServiceStartType
0x180007712  mov     ebx, eax
0x180007714  test    eax, eax
0x180007716  jnz     short loc_18000773D
0x180007718  mov     edx, [rbp+var_10]
0x18000771b  lea     rcx, g_szCscServiceName; "CscService"
0x180007722  call    _SetDriverOrServiceStartType
0x180007727  mov     ebx, eax
0x180007729  test    eax, eax
0x18000772b  jz      short loc_18000773D
0x18000772d  mov     edx, [rbp+arg_8]
0x180007730  mov     rcx, r14
0x180007733  call    _SetDriverOrServiceStartType
0x180007738  jmp     loc_180007621
0x18000773d  test    ebx, ebx
0x18000773f  jnz     loc_180007621
0x180007745  mov     rcx, cs:WPP_GLOBAL_Control
0x18000774c  lea     rax, WPP_GLOBAL_Control
0x180007753  cmp     rcx, rax
0x180007756  jz      short loc_180007789
0x180007758  test    byte ptr [rcx+0BCh], 2
0x18000775f  jz      short loc_180007789
0x180007761  mov     rcx, [rcx+0B0h]
0x180007768  lea     edx, [rbx+20h]
0x18000776b  lea     r8, WPP_00d7c4231f3f33ca0a28c368a7ccec1f_Traceguids
0x180007772  call    WPP_SF_
0x180007777  mov     rcx, cs:WPP_GLOBAL_Control
0x18000777e  lea     rax, WPP_GLOBAL_Control
0x180007785  jmp     short loc_180007789
0x180007787  xor     esi, esi
0x180007789  cmp     [rbp+arg_10], esi
0x18000778c  jz      loc_18000762F
0x180007792  cmp     rcx, rax
0x180007795  jz      short loc_1800077C6
0x180007797  test    byte ptr [rcx+0BCh], 2
0x18000779e  jz      short loc_1800077C6
0x1800077a0  mov     rcx, [rcx+0B0h]
0x1800077a7  lea     r8, WPP_00d7c4231f3f33ca0a28c368a7ccec1f_Traceguids
0x1800077ae  mov     edx, 21h ; '!'
0x1800077b3  call    WPP_SF_
0x1800077b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800077bf  lea     rax, WPP_GLOBAL_Control
0x1800077c6  test    r15d, r15d
0x1800077c9  jz      short loc_18000784A
0x1800077cb  cmp     [rbp+var_1C], esi
0x1800077ce  jz      short loc_180007812
0x1800077d0  cmp     [rbp+var_18], esi
0x1800077d3  jnz     loc_18000762F
0x1800077d9  lea     rbx, WPP_GLOBAL_Control
0x1800077e0  cmp     rcx, rbx
0x1800077e3  jz      short loc_180007806
0x1800077e5  test    byte ptr [rcx+0BCh], 2
0x1800077ec  jz      short loc_180007806
0x1800077ee  mov     rcx, [rcx+0B0h]
0x1800077f5  lea     r8, WPP_00d7c4231f3f33ca0a28c368a7ccec1f_Traceguids
0x1800077fc  mov     edx, 22h ; '"'
0x180007801  call    WPP_SF_
0x180007806  call    _StartDriverOrService
0x18000780b  mov     ebx, eax
0x18000780d  jmp     loc_180007621
0x180007812  cmp     rcx, rax
0x180007815  jz      short loc_18000783F
0x180007817  test    byte ptr [rcx+0BCh], 2
0x18000781e  jz      short loc_18000783F
0x180007820  mov     edx, 24h ; '$'
0x180007825  mov     rcx, [rcx+0B0h]
0x18000782c  lea     r8, WPP_00d7c4231f3f33ca0a28c368a7ccec1f_Traceguids
0x180007833  call    WPP_SF_
0x180007838  lea     rax, WPP_GLOBAL_Control
0x18000783f  mov     dword ptr [rdi], 1
0x180007845  jmp     loc_180007628
0x18000784a  cmp     [rbp+var_1C], esi
0x18000784d  jnz     short loc_180007858
0x18000784f  cmp     [rbp+var_18], esi
0x180007852  jz      loc_18000762F
0x180007858  cmp     rcx, rax
0x18000785b  jz      short loc_18000783F
0x18000785d  test    byte ptr [rcx+0BCh], 2
0x180007864  jz      short loc_18000783F
0x180007866  mov     edx, 23h ; '#'
0x18000786b  jmp     short loc_180007825
```
