# CConfigDescriptor::ReloadPolicies(void)

- ea: `0x1800086e0`
- end: `0x180008b2a`
- name: `?ReloadPolicies@CConfigDescriptor@@QEAAJXZ`
- size: `1098`
- prototype: `__int64 __fastcall(HANDLE *this)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180003f00`
- `0x1800065c0`

## callees

- `0x1800086e0`
- `0x180008b30`
- `0x18000ca14`
- `0x18000d910`
- `0x18000d970`
- `0x1800105ac`
- `0x180010648`
- `0x1800107ac`
- `0x180013010`

## string_xrefs

- `0x1800087d9`: `Unexpected Configuration Manager error encountered`

## pseudocode

```c
__int64 __fastcall CConfigDescriptor::ReloadPolicies(HANDLE *this)
{
  int v2; // ebx
  PVOID *v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // r9
  _QWORD *v6; // rcx
  int v7; // edx
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  PVOID *v15; // r10
  int v17; // [rsp+60h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+10h] BYREF

  ppv = 0;
  v17 = 0;
  v2 = LoadUserConfiguration(this[1], &ppv, 0, 0);
  if ( v2 == -2147220735 )
  {
    v2 = -2147219967;
    v3 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v4 = 10;
LABEL_5:
      v5 = (unsigned int)v2;
LABEL_6:
      WPP_SF_d(v3[2], v4, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, v5);
      goto LABEL_62;
    }
    goto LABEL_62;
  }
  if ( v2 == -2147220736 )
  {
    v2 = -2147219964;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_62;
    v7 = 11;
    goto LABEL_11;
  }
  if ( v2 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)ppv + 80LL))(ppv, &v17);
    v2 = v8;
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          (unsigned int)&WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
          (unsigned int)*this,
          v8);
      goto LABEL_62;
    }
    if ( v17 )
    {
      if ( v17 == 1 )
      {
        v2 = -2147219965;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_62;
        v7 = 16;
      }
      else
      {
        if ( v17 != 3 )
        {
          v9 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, char *))(*(_QWORD *)ppv + 64LL))(ppv, 0, (char *)this + 48);
          v2 = v9;
          if ( v9 >= 0 )
          {
            v10 = (*(__int64 (__fastcall **)(LPVOID, __int64, char *))(*(_QWORD *)ppv + 64LL))(
                    ppv,
                    7,
                    (char *)this + 56);
            v2 = v10;
            if ( v10 >= 0 )
            {
              v11 = (*(__int64 (__fastcall **)(LPVOID, __int64, char *))(*(_QWORD *)ppv + 64LL))(
                      ppv,
                      8,
                      (char *)this + 64);
              v2 = v11;
              if ( v11 >= 0 )
              {
                v12 = (*(__int64 (__fastcall **)(LPVOID, __int64, char *))(*(_QWORD *)ppv + 64LL))(
                        ppv,
                        9,
                        (char *)this + 72);
                v2 = v12;
                if ( v12 >= 0 )
                {
                  v15 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
                  {
                    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                    {
                      WPP_SF_S(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        22,
                        &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
                        *this);
                      v15 = (PVOID *)WPP_GLOBAL_Control;
                    }
                    if ( v15 != &WPP_GLOBAL_Control )
                    {
                      if ( (*((_BYTE *)v15 + 28) & 8) != 0 )
                      {
                        WPP_SF_iii(
                          v15[2],
                          v13,
                          v14,
                          ((unsigned __int64)this[7] + 0xFFFFF) >> 20,
                          ((unsigned __int64)this[9] + 0xFFFFF) >> 20,
                          ((unsigned __int64)this[8] + 0xFFFFF) >> 20);
                        v15 = (PVOID *)WPP_GLOBAL_Control;
                      }
                      if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 8) != 0 )
                        WPP_SF_i(v15[2], 24, v14, this[6]);
                    }
                  }
                  this[6] = (HANDLE)(10000000LL * (_QWORD)this[6]);
                }
                else
                {
                  v3 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    v4 = 21;
                    v5 = (unsigned int)v12;
                    goto LABEL_6;
                  }
                }
              }
              else
              {
                v3 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v4 = 20;
                  v5 = (unsigned int)v11;
                  goto LABEL_6;
                }
              }
            }
            else
            {
              v3 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v4 = 19;
                v5 = (unsigned int)v10;
                goto LABEL_6;
              }
            }
          }
          else
          {
            v3 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v4 = 18;
              v5 = (unsigned int)v9;
              goto LABEL_6;
            }
          }
          goto LABEL_62;
        }
        v2 = -2147219963;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_62;
        v7 = 17;
      }
    }
    else
    {
      v2 = -2147219966;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_62;
      v7 = 15;
    }
LABEL_11:
    WPP_SF_Sd(v6[2], v7, (unsigned int)&WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, (unsigned int)*this, v2);
    goto LABEL_62;
  }
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_ss(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)&WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
        (unsigned int)"SUCCEEDED(hr)",
        (__int64)"Unexpected Configuration Manager error encountered");
      v3 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 1) != 0 )
    {
      v4 = 13;
      goto LABEL_5;
    }
  }
LABEL_62:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800086e0  mov     [rsp+arg_10], rbx
0x1800086e5  mov     [rsp+arg_18], rbp
0x1800086ea  push    rsi
0x1800086eb  push    rdi
0x1800086ec  push    r12
0x1800086ee  push    r14
0x1800086f0  push    r15
0x1800086f2  sub     rsp, 30h
0x1800086f6  mov     rdi, rcx
0x1800086f9  xor     eax, eax
0x1800086fb  mov     [rsp+58h+ppv], rax
0x180008700  mov     [rsp+58h+arg_0], eax
0x180008704  xor     r9d, r9d
0x180008707  xor     r8d, r8d
0x18000870a  lea     rdx, [rsp+58h+ppv]; ppv
0x18000870f  mov     rcx, [rcx+8]; Token
0x180008713  call    ?LoadUserConfiguration@@YAJPEAXAEAV?$CComPtr@UIFhConfigMgrPriv@@@ATL@@PEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@PEAH@Z; LoadUserConfiguration(void *,ATL::CComPtr<IFhConfigMgrPriv> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,int *)
0x180008718  mov     ebx, eax
0x18000871a  cmp     eax, 80040301h
0x18000871f  jnz     short loc_180008764
0x180008721  mov     ebx, 80040601h
0x180008726  lea     rbp, WPP_GLOBAL_Control
0x18000872d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008734  cmp     rcx, rbp
0x180008737  jz      loc_180008AFA
0x18000873d  test    byte ptr [rcx+1Ch], 1
0x180008741  jz      loc_180008AFA
0x180008747  mov     edx, 0Ah
0x18000874c  mov     r9d, ebx
0x18000874f  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180008756  mov     rcx, [rcx+10h]
0x18000875a  call    WPP_SF_d
0x18000875f  jmp     loc_180008AFA
0x180008764  cmp     ebx, 80040300h
0x18000876a  jnz     short loc_1800087B3
0x18000876c  mov     ebx, 80040604h
0x180008771  lea     rbp, WPP_GLOBAL_Control
0x180008778  mov     rcx, cs:WPP_GLOBAL_Control
0x18000877f  cmp     rcx, rbp
0x180008782  jz      loc_180008AFA
0x180008788  test    byte ptr [rcx+1Ch], 1
0x18000878c  jz      loc_180008AFA
0x180008792  mov     edx, 0Bh
0x180008797  mov     dword ptr [rsp+58h+var_38], ebx
0x18000879b  mov     r9, [rdi]
0x18000879e  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x1800087a5  mov     rcx, [rcx+10h]
0x1800087a9  call    WPP_SF_Sd
0x1800087ae  jmp     loc_180008AFA
0x1800087b3  test    ebx, ebx
0x1800087b5  jns     short loc_180008820
0x1800087b7  lea     rbp, WPP_GLOBAL_Control
0x1800087be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800087c5  cmp     rcx, rbp
0x1800087c8  jz      loc_180008AFA
0x1800087ce  test    byte ptr [rcx+1Ch], 4
0x1800087d2  jz      short loc_180008803
0x1800087d4  mov     edx, 0Ch
0x1800087d9  lea     rax, aUnexpectedConf; "Unexpected Configuration Manager error "...
0x1800087e0  mov     [rsp+58h+var_38], rax
0x1800087e5  lea     r9, aSucceededHr; "SUCCEEDED(hr)"
0x1800087ec  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x1800087f3  mov     rcx, [rcx+10h]
0x1800087f7  call    WPP_SF_ss
0x1800087fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180008803  cmp     rcx, rbp
0x180008806  jz      loc_180008AFA
0x18000880c  test    byte ptr [rcx+1Ch], 1
0x180008810  jz      loc_180008AFA
0x180008816  mov     edx, 0Dh
0x18000881b  jmp     loc_18000874C
0x180008820  mov     rcx, [rsp+58h+ppv]
0x180008825  mov     rax, [rcx]
0x180008828  lea     rdx, [rsp+58h+arg_0]
0x18000882d  mov     rax, [rax+50h]
0x180008831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008836  mov     ebx, eax
0x180008838  test    eax, eax
0x18000883a  jns     short loc_18000886B
0x18000883c  lea     rbp, WPP_GLOBAL_Control
0x180008843  mov     rcx, cs:WPP_GLOBAL_Control
0x18000884a  cmp     rcx, rbp
0x18000884d  jz      loc_180008AFA
0x180008853  test    byte ptr [rcx+1Ch], 1
0x180008857  jz      loc_180008AFA
0x18000885d  mov     edx, 0Eh
0x180008862  mov     dword ptr [rsp+58h+var_38], eax
0x180008866  jmp     loc_18000879B
0x18000886b  mov     eax, [rsp+58h+arg_0]
0x18000886f  test    eax, eax
0x180008871  jnz     short loc_1800088A3
0x180008873  mov     ebx, 80040602h
0x180008878  lea     rbp, WPP_GLOBAL_Control
0x18000887f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008886  cmp     rcx, rbp
0x180008889  jz      loc_180008AFA
0x18000888f  test    byte ptr [rcx+1Ch], 1
0x180008893  jz      loc_180008AFA
0x180008899  mov     edx, 0Fh
0x18000889e  jmp     loc_180008797
0x1800088a3  cmp     eax, 1
0x1800088a6  jnz     short loc_1800088D7
0x1800088a8  mov     ebx, 80040603h
0x1800088ad  lea     rbp, WPP_GLOBAL_Control
0x1800088b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800088bb  cmp     rcx, rbp
0x1800088be  jz      loc_180008AFA
0x1800088c4  test    [rcx+1Ch], al
0x1800088c7  jz      loc_180008AFA
0x1800088cd  mov     edx, 10h
0x1800088d2  jmp     loc_180008797
0x1800088d7  cmp     eax, 3
0x1800088da  jnz     short loc_18000890C
0x1800088dc  mov     ebx, 80040605h
0x1800088e1  lea     rbp, WPP_GLOBAL_Control
0x1800088e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800088ef  cmp     rcx, rbp
0x1800088f2  jz      loc_180008AFA
0x1800088f8  test    byte ptr [rcx+1Ch], 1
0x1800088fc  jz      loc_180008AFA
0x180008902  mov     edx, 11h
0x180008907  jmp     loc_180008797
0x18000890c  mov     rcx, [rsp+58h+ppv]
0x180008911  mov     rax, [rcx]
0x180008914  lea     r8, [rdi+30h]
0x180008918  xor     edx, edx
0x18000891a  mov     rax, [rax+40h]
0x18000891e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008923  mov     ebx, eax
0x180008925  test    eax, eax
0x180008927  jns     short loc_180008957
0x180008929  lea     rbp, WPP_GLOBAL_Control
0x180008930  mov     rcx, cs:WPP_GLOBAL_Control
0x180008937  cmp     rcx, rbp
0x18000893a  jz      loc_180008AFA
0x180008940  test    byte ptr [rcx+1Ch], 1
0x180008944  jz      loc_180008AFA
0x18000894a  mov     edx, 12h
0x18000894f  mov     r9d, eax
0x180008952  jmp     loc_18000874F
0x180008957  mov     rcx, [rsp+58h+ppv]
0x18000895c  mov     rax, [rcx]
0x18000895f  lea     r8, [rdi+38h]
0x180008963  mov     edx, 7
0x180008968  mov     rax, [rax+40h]
0x18000896c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008971  mov     ebx, eax
0x180008973  test    eax, eax
0x180008975  jns     short loc_1800089A5
0x180008977  lea     rbp, WPP_GLOBAL_Control
0x18000897e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008985  cmp     rcx, rbp
0x180008988  jz      loc_180008AFA
0x18000898e  test    byte ptr [rcx+1Ch], 1
0x180008992  jz      loc_180008AFA
0x180008998  mov     edx, 13h
0x18000899d  mov     r9d, eax
0x1800089a0  jmp     loc_18000874F
0x1800089a5  mov     rcx, [rsp+58h+ppv]
0x1800089aa  mov     rax, [rcx]
0x1800089ad  lea     r8, [rdi+40h]
0x1800089b1  mov     edx, 8
0x1800089b6  mov     rax, [rax+40h]
0x1800089ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089bf  mov     ebx, eax
0x1800089c1  test    eax, eax
0x1800089c3  jns     short loc_1800089F3
0x1800089c5  lea     rbp, WPP_GLOBAL_Control
0x1800089cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800089d3  cmp     rcx, rbp
0x1800089d6  jz      loc_180008AFA
0x1800089dc  test    byte ptr [rcx+1Ch], 1
0x1800089e0  jz      loc_180008AFA
0x1800089e6  mov     edx, 14h
0x1800089eb  mov     r9d, eax
0x1800089ee  jmp     loc_18000874F
0x1800089f3  mov     rcx, [rsp+58h+ppv]
0x1800089f8  mov     rax, [rcx]
0x1800089fb  lea     r8, [rdi+48h]
0x1800089ff  mov     edx, 9
0x180008a04  mov     rax, [rax+40h]
0x180008a08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a0d  mov     ebx, eax
0x180008a0f  test    eax, eax
0x180008a11  jns     short loc_180008A41
0x180008a13  lea     rbp, WPP_GLOBAL_Control
0x180008a1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a21  cmp     rcx, rbp
0x180008a24  jz      loc_180008AFA
0x180008a2a  test    byte ptr [rcx+1Ch], 1
0x180008a2e  jz      loc_180008AFA
0x180008a34  mov     edx, 15h
0x180008a39  mov     r9d, eax
0x180008a3c  jmp     loc_18000874F
0x180008a41  lea     rbp, WPP_GLOBAL_Control
0x180008a48  mov     r10, cs:WPP_GLOBAL_Control
0x180008a4f  cmp     r10, rbp
0x180008a52  jz      loc_180008AEE
0x180008a58  test    byte ptr [r10+1Ch], 8
0x180008a5d  jz      short loc_180008A7E
0x180008a5f  mov     edx, 16h
0x180008a64  mov     r9, [rdi]
0x180008a67  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180008a6e  mov     rcx, [r10+10h]
0x180008a72  call    WPP_SF_S
0x180008a77  mov     r10, cs:WPP_GLOBAL_Control
0x180008a7e  cmp     r10, rbp
0x180008a81  jz      short loc_180008AEE
0x180008a83  test    byte ptr [r10+1Ch], 8
0x180008a88  jz      short loc_180008AD0
0x180008a8a  mov     rcx, [rdi+40h]
0x180008a8e  add     rcx, 0FFFFFh
0x180008a95  shr     rcx, 14h
0x180008a99  mov     rax, [rdi+48h]
0x180008a9d  add     rax, 0FFFFFh
0x180008aa3  shr     rax, 14h
0x180008aa7  mov     r9, [rdi+38h]
0x180008aab  add     r9, 0FFFFFh
0x180008ab2  shr     r9, 14h
0x180008ab6  mov     [rsp+58h+var_30], rcx
0x180008abb  mov     [rsp+58h+var_38], rax
0x180008ac0  mov     rcx, [r10+10h]
0x180008ac4  call    WPP_SF_iii
0x180008ac9  mov     r10, cs:WPP_GLOBAL_Control
0x180008ad0  cmp     r10, rbp
0x180008ad3  jz      short loc_180008AEE
0x180008ad5  test    byte ptr [r10+1Ch], 8
0x180008ada  jz      short loc_180008AEE
0x180008adc  mov     edx, 18h
0x180008ae1  mov     r9, [rdi+30h]
0x180008ae5  mov     rcx, [r10+10h]
0x180008ae9  call    WPP_SF_i
0x180008aee  imul    rax, [rdi+30h], 989680h
0x180008af6  mov     [rdi+30h], rax
0x180008afa  mov     rcx, [rsp+58h+ppv]
0x180008aff  test    rcx, rcx
0x180008b02  jz      short loc_180008B11
0x180008b04  mov     rax, [rcx]
0x180008b07  mov     rax, [rax+10h]
0x180008b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b10  nop
0x180008b11  mov     eax, ebx
0x180008b13  mov     rbx, [rsp+58h+arg_10]
0x180008b18  mov     rbp, [rsp+58h+arg_18]
0x180008b1d  add     rsp, 30h
0x180008b21  pop     r15
0x180008b23  pop     r14
0x180008b25  pop     r12
0x180008b27  pop     rdi
0x180008b28  pop     rsi
0x180008b29  retn
```
