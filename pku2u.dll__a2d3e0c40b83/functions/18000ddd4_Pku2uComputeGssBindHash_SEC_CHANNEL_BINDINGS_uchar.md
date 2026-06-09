# Pku2uComputeGssBindHash(_SEC_CHANNEL_BINDINGS *,uchar *)

- ea: `0x18000ddd4`
- end: `0x18000e1c2`
- name: `?Pku2uComputeGssBindHash@@YAJPEAU_SEC_CHANNEL_BINDINGS@@PEAE@Z`
- size: `1006`
- prototype: `__int64 __fastcall(struct _SEC_CHANNEL_BINDINGS *, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800071a0`
- `0x18000d220`

## callees

- `0x18000ddd4`
- `0x180023d9c`
- `0x180046010`

## import_xrefs

- `cryptdll!CDLocateCheckSum` at `0x18000de06`
- `cryptdll!CDLocateCheckSum` at `0x18000de06`

## string_xrefs

- `0x18000e177`: `onecore\ds\security\protocols\pku2u\tick.cxx`

## pseudocode

```c
__int64 __fastcall Pku2uComputeGssBindHash(struct _SEC_CHANNEL_BINDINGS *a1, unsigned __int8 *a2)
{
  int v4; // ebx
  __int64 cbInitiatorLength; // rdx
  __int64 cbAcceptorLength; // rdx
  __int64 cbApplicationDataLength; // rdx
  __int64 v9; // [rsp+70h] [rbp+40h] BYREF
  __int64 v10; // [rsp+78h] [rbp+48h] BYREF

  v9 = 0;
  v10 = 0;
  v4 = CDLocateCheckSum(7, &v9);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(v9 + 16))(0, &v10);
    if ( v4 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(__int64, __int64, struct _SEC_CHANNEL_BINDINGS *))(v9 + 24))(v10, 4, a1);
      if ( v4 >= 0 )
      {
        v4 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(v9 + 24))(v10, 4, &a1->cbInitiatorLength);
        if ( v4 >= 0 )
        {
          cbInitiatorLength = a1->cbInitiatorLength;
          if ( (_DWORD)cbInitiatorLength
            && (v4 = (*(__int64 (__fastcall **)(__int64, __int64, char *))(v9 + 24))(
                       v10,
                       cbInitiatorLength,
                       (char *)a1 + a1->dwInitiatorOffset),
                v4 < 0) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_dsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                50,
                (unsigned int)&WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
                v4,
                (__int64)"onecore\\ds\\security\\protocols\\pku2u\\tick.cxx",
                243);
          }
          else
          {
            v4 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(v9 + 24))(
                   v10,
                   4,
                   &a1->dwAcceptorAddrType);
            if ( v4 >= 0 )
            {
              v4 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(v9 + 24))(
                     v10,
                     4,
                     &a1->cbAcceptorLength);
              if ( v4 >= 0 )
              {
                cbAcceptorLength = a1->cbAcceptorLength;
                if ( (_DWORD)cbAcceptorLength
                  && (v4 = (*(__int64 (__fastcall **)(__int64, __int64, char *))(v9 + 24))(
                             v10,
                             cbAcceptorLength,
                             (char *)a1 + a1->dwAcceptorOffset),
                      v4 < 0) )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    WPP_SF_dsd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      53,
                      (unsigned int)&WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
                      v4,
                      (__int64)"onecore\\ds\\security\\protocols\\pku2u\\tick.cxx",
                      32);
                }
                else
                {
                  v4 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(v9 + 24))(
                         v10,
                         4,
                         &a1->cbApplicationDataLength);
                  if ( v4 >= 0 )
                  {
                    cbApplicationDataLength = a1->cbApplicationDataLength;
                    if ( (_DWORD)cbApplicationDataLength
                      && (v4 = (*(__int64 (__fastcall **)(__int64, __int64, char *))(v9 + 24))(
                                 v10,
                                 cbApplicationDataLength,
                                 (char *)a1 + a1->dwApplicationDataOffset),
                          v4 < 0) )
                    {
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                        WPP_SF_dsd(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          55,
                          (unsigned int)&WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
                          v4,
                          (__int64)"onecore\\ds\\security\\protocols\\pku2u\\tick.cxx",
                          63);
                    }
                    else
                    {
                      v4 = (*(__int64 (__fastcall **)(__int64, unsigned __int8 *))(v9 + 32))(v10, a2);
                      if ( v4 < 0
                        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                      {
                        WPP_SF_dsd(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          56,
                          (unsigned int)&WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
                          v4,
                          (__int64)"onecore\\ds\\security\\protocols\\pku2u\\tick.cxx",
                          82);
                      }
                    }
                  }
                  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    WPP_SF_dsd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      54,
                      (unsigned int)&WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
                      v4,
                      (__int64)"onecore\\ds\\security\\protocols\\pku2u\\tick.cxx",
                      47);
                  }
                }
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_dsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  52,
                  (unsigned int)&WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
                  v4,
                  (__int64)"onecore\\ds\\security\\protocols\\pku2u\\tick.cxx",
                  16);
              }
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_dsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                51,
                (unsigned int)&WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
                v4,
                (__int64)"onecore\\ds\\security\\protocols\\pku2u\\tick.cxx",
                2);
            }
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_dsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            49,
            (unsigned int)&WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
            v4,
            (__int64)"onecore\\ds\\security\\protocols\\pku2u\\tick.cxx",
            227);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_dsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          48,
          (unsigned int)&WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
          v4,
          (__int64)"onecore\\ds\\security\\protocols\\pku2u\\tick.cxx",
          213);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_dsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        47,
        (unsigned int)&WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
        v4,
        (__int64)"onecore\\ds\\security\\protocols\\pku2u\\tick.cxx",
        195);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_dsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      46,
      (unsigned int)&WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
      v4,
      (__int64)"onecore\\ds\\security\\protocols\\pku2u\\tick.cxx",
      179);
  }
  if ( v9 && v10 )
    (*(void (__fastcall **)(__int64 *))(v9 + 40))(&v10);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000ddd4  mov     [rsp-28h+arg_0], rbx
0x18000ddd9  push    rbp
0x18000ddda  push    rsi
0x18000dddb  push    rdi
0x18000dddc  push    r12
0x18000ddde  push    r14
0x18000dde0  mov     rbp, rsp
0x18000dde3  sub     rsp, 30h
0x18000dde7  mov     r14, rdx
0x18000ddea  mov     [rbp+arg_10], 0
0x18000ddf2  mov     rdi, rcx
0x18000ddf5  mov     [rbp+arg_18], 0
0x18000ddfd  lea     rdx, [rbp+arg_10]
0x18000de01  mov     ecx, 7
0x18000de06  call    cs:__imp_CDLocateCheckSum
0x18000de0c  mov     ebx, eax
0x18000de0e  test    eax, eax
0x18000de10  jns     short loc_18000DE46
0x18000de12  mov     r10, cs:WPP_GLOBAL_Control
0x18000de19  lea     rcx, WPP_GLOBAL_Control
0x18000de20  cmp     r10, rcx
0x18000de23  jz      loc_18000E192
0x18000de29  test    byte ptr [r10+1Ch], 1
0x18000de2e  jz      loc_18000E192
0x18000de34  mov     edx, 2Eh ; '.'
0x18000de39  mov     [rsp+30h+var_8], 0AB3h
0x18000de41  jmp     loc_18000E173
0x18000de46  mov     rax, [rbp+arg_10]
0x18000de4a  lea     rdx, [rbp+arg_18]
0x18000de4e  xor     ecx, ecx
0x18000de50  mov     rax, [rax+10h]
0x18000de54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de59  mov     ebx, eax
0x18000de5b  test    eax, eax
0x18000de5d  jns     short loc_18000DE93
0x18000de5f  mov     r10, cs:WPP_GLOBAL_Control
0x18000de66  lea     rcx, WPP_GLOBAL_Control
0x18000de6d  cmp     r10, rcx
0x18000de70  jz      loc_18000E192
0x18000de76  test    byte ptr [r10+1Ch], 1
0x18000de7b  jz      loc_18000E192
0x18000de81  mov     edx, 2Fh ; '/'
0x18000de86  mov     [rsp+30h+var_8], 0AC3h
0x18000de8e  jmp     loc_18000E173
0x18000de93  mov     rax, [rbp+arg_10]
0x18000de97  mov     r12d, 4
0x18000de9d  mov     rcx, [rbp+arg_18]
0x18000dea1  mov     r8, rdi
0x18000dea4  mov     edx, r12d
0x18000dea7  mov     rax, [rax+18h]
0x18000deab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000deb0  mov     ebx, eax
0x18000deb2  test    eax, eax
0x18000deb4  jns     short loc_18000DEEA
0x18000deb6  mov     r10, cs:WPP_GLOBAL_Control
0x18000debd  lea     rcx, WPP_GLOBAL_Control
0x18000dec4  cmp     r10, rcx
0x18000dec7  jz      loc_18000E192
0x18000decd  test    byte ptr [r10+1Ch], 1
0x18000ded2  jz      loc_18000E192
0x18000ded8  lea     edx, [r12+2Ch]
0x18000dedd  mov     [rsp+30h+var_8], 0AD5h
0x18000dee5  jmp     loc_18000E173
0x18000deea  mov     rax, [rbp+arg_10]
0x18000deee  lea     r8, [rdi+4]
0x18000def2  mov     rcx, [rbp+arg_18]
0x18000def6  mov     edx, r12d
0x18000def9  mov     rax, [rax+18h]
0x18000defd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df02  mov     ebx, eax
0x18000df04  test    eax, eax
0x18000df06  jns     short loc_18000DF3C
0x18000df08  mov     r10, cs:WPP_GLOBAL_Control
0x18000df0f  lea     rcx, WPP_GLOBAL_Control
0x18000df16  cmp     r10, rcx
0x18000df19  jz      loc_18000E192
0x18000df1f  test    byte ptr [r10+1Ch], 1
0x18000df24  jz      loc_18000E192
0x18000df2a  mov     edx, 31h ; '1'
0x18000df2f  mov     [rsp+30h+var_8], 0AE3h
0x18000df37  jmp     loc_18000E173
0x18000df3c  mov     edx, [rdi+4]
0x18000df3f  test    edx, edx
0x18000df41  jz      short loc_18000DF95
0x18000df43  mov     rax, [rbp+arg_10]
0x18000df47  mov     r8d, [rdi+8]
0x18000df4b  mov     rcx, [rbp+arg_18]
0x18000df4f  add     r8, rdi
0x18000df52  mov     rax, [rax+18h]
0x18000df56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df5b  mov     ebx, eax
0x18000df5d  test    eax, eax
0x18000df5f  jns     short loc_18000DF95
0x18000df61  mov     r10, cs:WPP_GLOBAL_Control
0x18000df68  lea     rcx, WPP_GLOBAL_Control
0x18000df6f  cmp     r10, rcx
0x18000df72  jz      loc_18000E192
0x18000df78  test    byte ptr [r10+1Ch], 1
0x18000df7d  jz      loc_18000E192
0x18000df83  mov     edx, 32h ; '2'
0x18000df88  mov     [rsp+30h+var_8], 0AF3h
0x18000df90  jmp     loc_18000E173
0x18000df95  mov     rax, [rbp+arg_10]
0x18000df99  lea     r8, [rdi+0Ch]
0x18000df9d  mov     rcx, [rbp+arg_18]
0x18000dfa1  mov     edx, r12d
0x18000dfa4  mov     rax, [rax+18h]
0x18000dfa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfad  mov     ebx, eax
0x18000dfaf  test    eax, eax
0x18000dfb1  jns     short loc_18000DFE7
0x18000dfb3  mov     r10, cs:WPP_GLOBAL_Control
0x18000dfba  lea     rcx, WPP_GLOBAL_Control
0x18000dfc1  cmp     r10, rcx
0x18000dfc4  jz      loc_18000E192
0x18000dfca  test    byte ptr [r10+1Ch], 1
0x18000dfcf  jz      loc_18000E192
0x18000dfd5  mov     edx, 33h ; '3'
0x18000dfda  mov     [rsp+30h+var_8], 0B02h
0x18000dfe2  jmp     loc_18000E173
0x18000dfe7  mov     rax, [rbp+arg_10]
0x18000dfeb  lea     r8, [rdi+10h]
0x18000dfef  mov     rcx, [rbp+arg_18]
0x18000dff3  mov     edx, r12d
0x18000dff6  mov     rax, [rax+18h]
0x18000dffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfff  mov     ebx, eax
0x18000e001  test    eax, eax
0x18000e003  jns     short loc_18000E039
0x18000e005  mov     r10, cs:WPP_GLOBAL_Control
0x18000e00c  lea     rcx, WPP_GLOBAL_Control
0x18000e013  cmp     r10, rcx
0x18000e016  jz      loc_18000E192
0x18000e01c  test    byte ptr [r10+1Ch], 1
0x18000e021  jz      loc_18000E192
0x18000e027  mov     edx, 34h ; '4'
0x18000e02c  mov     [rsp+30h+var_8], 0B10h
0x18000e034  jmp     loc_18000E173
0x18000e039  mov     edx, [rdi+10h]
0x18000e03c  test    edx, edx
0x18000e03e  jz      short loc_18000E092
0x18000e040  mov     rax, [rbp+arg_10]
0x18000e044  mov     r8d, [rdi+14h]
0x18000e048  mov     rcx, [rbp+arg_18]
0x18000e04c  add     r8, rdi
0x18000e04f  mov     rax, [rax+18h]
0x18000e053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e058  mov     ebx, eax
0x18000e05a  test    eax, eax
0x18000e05c  jns     short loc_18000E092
0x18000e05e  mov     r10, cs:WPP_GLOBAL_Control
0x18000e065  lea     rcx, WPP_GLOBAL_Control
0x18000e06c  cmp     r10, rcx
0x18000e06f  jz      loc_18000E192
0x18000e075  test    byte ptr [r10+1Ch], 1
0x18000e07a  jz      loc_18000E192
0x18000e080  mov     edx, 35h ; '5'
0x18000e085  mov     [rsp+30h+var_8], 0B20h
0x18000e08d  jmp     loc_18000E173
0x18000e092  mov     rax, [rbp+arg_10]
0x18000e096  lea     r8, [rdi+18h]
0x18000e09a  mov     rcx, [rbp+arg_18]
0x18000e09e  mov     edx, r12d
0x18000e0a1  mov     rax, [rax+18h]
0x18000e0a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0aa  mov     ebx, eax
0x18000e0ac  test    eax, eax
0x18000e0ae  jns     short loc_18000E0E4
0x18000e0b0  mov     r10, cs:WPP_GLOBAL_Control
0x18000e0b7  lea     rcx, WPP_GLOBAL_Control
0x18000e0be  cmp     r10, rcx
0x18000e0c1  jz      loc_18000E192
0x18000e0c7  test    byte ptr [r10+1Ch], 1
0x18000e0cc  jz      loc_18000E192
0x18000e0d2  mov     edx, 36h ; '6'
0x18000e0d7  mov     [rsp+30h+var_8], 0B2Fh
0x18000e0df  jmp     loc_18000E173
0x18000e0e4  mov     edx, [rdi+18h]
0x18000e0e7  test    edx, edx
0x18000e0e9  jz      short loc_18000E132
0x18000e0eb  mov     rax, [rbp+arg_10]
0x18000e0ef  mov     r8d, [rdi+1Ch]
0x18000e0f3  mov     rcx, [rbp+arg_18]
0x18000e0f7  add     r8, rdi
0x18000e0fa  mov     rax, [rax+18h]
0x18000e0fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e103  mov     ebx, eax
0x18000e105  test    eax, eax
0x18000e107  jns     short loc_18000E132
0x18000e109  mov     r10, cs:WPP_GLOBAL_Control
0x18000e110  lea     rcx, WPP_GLOBAL_Control
0x18000e117  cmp     r10, rcx
0x18000e11a  jz      short loc_18000E192
0x18000e11c  test    byte ptr [r10+1Ch], 1
0x18000e121  jz      short loc_18000E192
0x18000e123  mov     edx, 37h ; '7'
0x18000e128  mov     [rsp+30h+var_8], 0B3Fh
0x18000e130  jmp     short loc_18000E173
0x18000e132  mov     rax, [rbp+arg_10]
0x18000e136  mov     rdx, r14
0x18000e139  mov     rcx, [rbp+arg_18]
0x18000e13d  mov     rax, [rax+20h]
0x18000e141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e146  mov     ebx, eax
0x18000e148  test    eax, eax
0x18000e14a  jns     short loc_18000E192
0x18000e14c  mov     r10, cs:WPP_GLOBAL_Control
0x18000e153  lea     rcx, WPP_GLOBAL_Control
0x18000e15a  cmp     r10, rcx
0x18000e15d  jz      short loc_18000E192
0x18000e15f  test    byte ptr [r10+1Ch], 1
0x18000e164  jz      short loc_18000E192
0x18000e166  mov     edx, 38h ; '8'
0x18000e16b  mov     [rsp+30h+var_8], 0B52h
0x18000e173  mov     rcx, [r10+10h]
0x18000e177  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\protocols\\pku2u"...
0x18000e17e  mov     r9d, ebx
0x18000e181  mov     [rsp+30h+var_10], rax
0x18000e186  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x18000e18d  call    WPP_SF_dsd
0x18000e192  mov     rax, [rbp+arg_10]
0x18000e196  test    rax, rax
0x18000e199  jz      short loc_18000E1AF
0x18000e19b  cmp     [rbp+arg_18], 0
0x18000e1a0  jz      short loc_18000E1AF
0x18000e1a2  mov     rax, [rax+28h]
0x18000e1a6  lea     rcx, [rbp+arg_18]
0x18000e1aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1af  mov     eax, ebx
0x18000e1b1  mov     rbx, [rsp+30h+arg_0]
0x18000e1b6  add     rsp, 30h
0x18000e1ba  pop     r14
0x18000e1bc  pop     r12
0x18000e1be  pop     rdi
0x18000e1bf  pop     rsi
0x18000e1c0  pop     rbp
0x18000e1c1  retn
```
