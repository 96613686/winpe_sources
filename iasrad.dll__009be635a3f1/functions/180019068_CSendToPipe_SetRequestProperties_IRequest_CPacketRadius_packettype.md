# CSendToPipe::SetRequestProperties(IRequest *,CPacketRadius *,_packettype_)

- ea: `0x180019068`
- end: `0x180019338`
- name: `?SetRequestProperties@CSendToPipe@@AEAAJPEAUIRequest@@PEAVCPacketRadius@@W4_packettype_@@@Z`
- size: `720`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180018ca4`

## callees

- `0x1800094e4`
- `0x18000dc54`
- `0x180019068`
- `0x18001d31c`
- `0x180030010`

## string_xrefs

- `0x1800191ca`: `Unable to set protocol type in request before sending it to the backend`

## pseudocode

```c
__int64 __fastcall CSendToPipe::SetRequestProperties(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  char v4; // bl
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rdx
  _QWORD v12[6]; // [rsp+38h] [rbp-30h] BYREF

  v4 = a4;
  v12[0] = 0;
  switch ( a4 )
  {
    case 1:
      v9 = 0;
LABEL_14:
      v8 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a2 + 32LL))(a2, v9);
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a2 + 64LL))(a2, 2);
        if ( v8 >= 0 )
        {
          v8 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a2 + 80LL))(a2, *(_QWORD *)(a1 + 8));
          if ( v8 >= 0 )
          {
            v8 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))a2)(
                   a2,
                   &GUID_6bc096ba_0ce6_11d1_baae_00c04fc2e20d,
                   v12);
            if ( v8 >= 0 )
            {
              v8 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v12[0] + 24LL))(v12[0], a3);
              if ( v8 >= 0
                || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
                || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
              {
                goto LABEL_40;
              }
              WppDbgPrint("Unable to set information in request state before sending request to backend");
              v10 = 29;
            }
            else
            {
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
                || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
              {
                goto LABEL_40;
              }
              WppDbgPrint("Unable to get RequestState interface from request object before sending it to the backend");
              v10 = 28;
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
            {
              goto LABEL_40;
            }
            WppDbgPrint("Unable to set request source type in request before sending it to the backend");
            v10 = 27;
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
          {
            goto LABEL_40;
          }
          WppDbgPrint("Unable to set protocol type in request before sending it to the backend");
          v10 = 26;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
        {
          goto LABEL_40;
        }
        WppDbgPrint("Unable to set request type in request before sending it to the backend");
        v10 = 25;
      }
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, WPP_705ec960347a326cbcb5a6c0ff8f7767_Traceguids, "NPSRAD");
      goto LABEL_40;
    case 2:
      goto LABEL_12;
    case 4:
      v9 = 1;
      goto LABEL_14;
    case 5:
    case 11:
LABEL_12:
      v9 = 999;
      goto LABEL_14;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Packet of unsupported type:%d, before sending request to backend");
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      (unsigned int)WPP_705ec960347a326cbcb5a6c0ff8f7767_Traceguids,
      (unsigned int)"NPSRAD",
      v4);
  }
  v8 = -2147467259;
LABEL_40:
  if ( v12[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v12[0] + 16LL))(v12[0]);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180019068  push    rbx
0x18001906a  push    rsi
0x18001906b  push    rdi
0x18001906c  push    r14
0x18001906e  sub     rsp, 48h
0x180019072  mov     ebx, r9d
0x180019075  mov     r14, r8
0x180019078  mov     rdi, rdx
0x18001907b  mov     rsi, rcx
0x18001907e  mov     [rsp+68h+var_30], 0
0x180019087  mov     r10d, ebx
0x18001908a  sub     r10d, 1
0x18001908e  jz      loc_18001911F
0x180019094  sub     r10d, 1
0x180019098  jz      short loc_180019118
0x18001909a  sub     r10d, 2
0x18001909e  jz      short loc_180019111
0x1800190a0  sub     r10d, 1
0x1800190a4  jz      short loc_180019118
0x1800190a6  cmp     r10d, 6
0x1800190aa  jz      short loc_180019118
0x1800190ac  lea     rax, WPP_GLOBAL_Control
0x1800190b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800190ba  cmp     rcx, rax
0x1800190bd  jz      short loc_180019103
0x1800190bf  cmp     byte ptr [rcx+19h], 2
0x1800190c3  jb      short loc_180019103
0x1800190c5  test    dword ptr [rcx+1Ch], 100h
0x1800190cc  jz      short loc_180019103
0x1800190ce  mov     edx, ebx
0x1800190d0  lea     rcx, aPacketOfUnsupp; "Packet of unsupported type:%d, before s"...
0x1800190d7  call    WppDbgPrint
0x1800190dc  mov     edx, 18h
0x1800190e1  mov     [rsp+68h+var_48], ebx
0x1800190e5  lea     r9, aNpsrad; "NPSRAD"
0x1800190ec  lea     r8, WPP_705ec960347a326cbcb5a6c0ff8f7767_Traceguids
0x1800190f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800190fa  mov     rcx, [rcx+10h]
0x1800190fe  call    WPP_SF_sd
0x180019103  mov     ebx, 80004005h
0x180019108  mov     [rsp+68h+var_38], ebx
0x18001910c  jmp     loc_180019316
0x180019111  mov     edx, 1
0x180019116  jmp     short loc_180019121
0x180019118  mov     edx, 3E7h
0x18001911d  jmp     short loc_180019121
0x18001911f  xor     edx, edx
0x180019121  mov     rax, [rdi]
0x180019124  mov     rcx, rdi
0x180019127  mov     rax, [rax+20h]
0x18001912b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019130  mov     ebx, eax
0x180019132  mov     [rsp+68h+var_38], eax
0x180019136  test    eax, eax
0x180019138  jns     short loc_18001917E
0x18001913a  lea     rax, WPP_GLOBAL_Control
0x180019141  mov     rcx, cs:WPP_GLOBAL_Control
0x180019148  cmp     rcx, rax
0x18001914b  jz      loc_180019316
0x180019151  cmp     byte ptr [rcx+19h], 2
0x180019155  jb      loc_180019316
0x18001915b  test    dword ptr [rcx+1Ch], 100h
0x180019162  jz      loc_180019316
0x180019168  lea     rcx, aUnableToSetReq_0; "Unable to set request type in request b"...
0x18001916f  call    WppDbgPrint
0x180019174  mov     edx, 19h
0x180019179  jmp     loc_1800192F7
0x18001917e  mov     rax, [rdi]
0x180019181  mov     edx, 2
0x180019186  mov     rcx, rdi
0x180019189  mov     rax, [rax+40h]
0x18001918d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019192  mov     ebx, eax
0x180019194  mov     [rsp+68h+var_38], eax
0x180019198  test    eax, eax
0x18001919a  jns     short loc_1800191E0
0x18001919c  lea     rax, WPP_GLOBAL_Control
0x1800191a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800191aa  cmp     rcx, rax
0x1800191ad  jz      loc_180019316
0x1800191b3  cmp     byte ptr [rcx+19h], 2
0x1800191b7  jb      loc_180019316
0x1800191bd  test    dword ptr [rcx+1Ch], 100h
0x1800191c4  jz      loc_180019316
0x1800191ca  lea     rcx, aUnableToSetPro; "Unable to set protocol type in request "...
0x1800191d1  call    WppDbgPrint
0x1800191d6  mov     edx, 1Ah
0x1800191db  jmp     loc_1800192F7
0x1800191e0  mov     rax, [rdi]
0x1800191e3  mov     rdx, [rsi+8]
0x1800191e7  mov     rcx, rdi
0x1800191ea  mov     rax, [rax+50h]
0x1800191ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191f3  mov     ebx, eax
0x1800191f5  mov     [rsp+68h+var_38], eax
0x1800191f9  test    eax, eax
0x1800191fb  jns     short loc_180019241
0x1800191fd  lea     rax, WPP_GLOBAL_Control
0x180019204  mov     rcx, cs:WPP_GLOBAL_Control
0x18001920b  cmp     rcx, rax
0x18001920e  jz      loc_180019316
0x180019214  cmp     byte ptr [rcx+19h], 2
0x180019218  jb      loc_180019316
0x18001921e  test    dword ptr [rcx+1Ch], 100h
0x180019225  jz      loc_180019316
0x18001922b  lea     rcx, aUnableToSetReq; "Unable to set request source type in re"...
0x180019232  call    WppDbgPrint
0x180019237  mov     edx, 1Bh
0x18001923c  jmp     loc_1800192F7
0x180019241  mov     rax, [rdi]
0x180019244  lea     r8, [rsp+68h+var_30]
0x180019249  lea     rdx, _GUID_6bc096ba_0ce6_11d1_baae_00c04fc2e20d
0x180019250  mov     rcx, rdi
0x180019253  mov     rax, [rax]
0x180019256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001925b  mov     ebx, eax
0x18001925d  mov     [rsp+68h+var_38], eax
0x180019261  test    eax, eax
0x180019263  jns     short loc_1800192A6
0x180019265  lea     rax, WPP_GLOBAL_Control
0x18001926c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019273  cmp     rcx, rax
0x180019276  jz      loc_180019316
0x18001927c  cmp     byte ptr [rcx+19h], 2
0x180019280  jb      loc_180019316
0x180019286  test    dword ptr [rcx+1Ch], 100h
0x18001928d  jz      loc_180019316
0x180019293  lea     rcx, aUnableToGetReq; "Unable to get RequestState interface fr"...
0x18001929a  call    WppDbgPrint
0x18001929f  mov     edx, 1Ch
0x1800192a4  jmp     short loc_1800192F7
0x1800192a6  mov     rcx, [rsp+68h+var_30]
0x1800192ab  mov     rax, [rcx]
0x1800192ae  mov     rdx, r14
0x1800192b1  mov     rax, [rax+18h]
0x1800192b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192ba  mov     ebx, eax
0x1800192bc  mov     [rsp+68h+var_38], eax
0x1800192c0  test    eax, eax
0x1800192c2  jns     short loc_180019316
0x1800192c4  lea     rax, WPP_GLOBAL_Control
0x1800192cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800192d2  cmp     rcx, rax
0x1800192d5  jz      short loc_180019316
0x1800192d7  cmp     byte ptr [rcx+19h], 2
0x1800192db  jb      short loc_180019316
0x1800192dd  test    dword ptr [rcx+1Ch], 100h
0x1800192e4  jz      short loc_180019316
0x1800192e6  lea     rcx, aUnableToSetInf; "Unable to set information in request st"...
0x1800192ed  call    WppDbgPrint
0x1800192f2  mov     edx, 1Dh
0x1800192f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800192fe  lea     r9, aNpsrad; "NPSRAD"
0x180019305  lea     r8, WPP_705ec960347a326cbcb5a6c0ff8f7767_Traceguids
0x18001930c  mov     rcx, [rcx+10h]
0x180019310  call    WPP_SF_s
0x180019315  nop
0x180019316  mov     rcx, [rsp+68h+var_30]
0x18001931b  test    rcx, rcx
0x18001931e  jz      short loc_18001932C
0x180019320  mov     rax, [rcx]
0x180019323  mov     rax, [rax+10h]
0x180019327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001932c  mov     eax, ebx
0x18001932e  add     rsp, 48h
0x180019332  pop     r14
0x180019334  pop     rdi
0x180019335  pop     rsi
0x180019336  pop     rbx
0x180019337  retn
0x18002f047  push    rbp
0x18002f049  sub     rsp, 30h
0x18002f04d  mov     rbp, rdx
0x18002f050  mov     rcx, [rbp+38h]
0x18002f054  test    rcx, rcx
0x18002f057  jz      short loc_18002F066
0x18002f059  mov     rax, [rcx]
0x18002f05c  mov     rax, [rax+10h]
0x18002f060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f065  nop
0x18002f066  add     rsp, 30h
0x18002f06a  pop     rbp
0x18002f06b  retn
```
