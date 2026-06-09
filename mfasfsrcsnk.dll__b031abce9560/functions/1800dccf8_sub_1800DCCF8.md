# sub_1800DCCF8

- ea: `0x1800dccf8`
- end: `0x1800dd180`
- name: `sub_1800DCCF8`
- size: `1160`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x1800c2b90`

## callees

- `0x180001870`
- `0x180005880`
- `0x18000a580`
- `0x18003d740`
- `0x18004f390`
- `0x1800520c4`
- `0x18006646c`
- `0x18007fdd0`
- `0x18009a1a0`
- `0x1800da804`
- `0x1800dccf8`
- `0x1800dd188`
- `0x1800dd920`
- `0x1800de7e8`
- `0x18013e2e0`

## import_xrefs

- `MFPlat!MFCreateMediaEvent` at `0x1800dcf33`
- `MFPlat!MFCreateMediaEvent` at `0x1800dcf33`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dce06`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dcf4f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dcffd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dce06`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dcf4f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dcffd`

## pseudocode

```c
__int64 __fastcall sub_1800DCCF8(__int64 a1, __int64 a2)
{
  _QWORD *v4; // r15
  _QWORD *v5; // r14
  __int64 v6; // rdx
  HRESULT v7; // ebx
  __int64 (__fastcall ***v8)(); // rcx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 (__fastcall ***v13)(); // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 (__fastcall ***v18)(); // rcx
  __int64 v19; // rax
  __int64 v20; // rax
  _BYTE v22[4]; // [rsp+40h] [rbp-30h] BYREF
  int v23; // [rsp+44h] [rbp-2Ch] BYREF
  IMFMediaEvent *ppEvent; // [rsp+48h] [rbp-28h] BYREF
  PROPVARIANT pvValue; // [rsp+50h] [rbp-20h] BYREF

  sub_18000A580(v22, "CASFBytewiseMediaStream::SetLastSendTimeAndTickIfNeeded", 1609);
  ppEvent = 0;
  v23 = 0;
  v4 = (_QWORD *)(a1 + 296);
  v5 = (_QWORD *)(a1 + 288);
  if ( (unsigned __int8)byte_1801692CB >= 8u )
    sub_18009A1A0(*((_QWORD *)RequestContext + 17), 131, &stru_180158D48, a1, a2 / 10000, *v5 / 10000LL, *v4 / 10000LL);
  v7 = sub_1800DA804(a1, &v23);
  if ( v7 >= 0 )
  {
    if ( v23 )
    {
      if ( (unsigned __int8)byte_1801692CB >= 8u )
        sub_1800520C4(*((_QWORD *)RequestContext + 17), 133, &stru_180158D48, a1);
    }
    else if ( *v5 + 10000000LL < a2 && *v4 + 10000000LL < a2 )
    {
      *(_QWORD *)&pvValue.vt = 20;
      *(_OWORD *)&pvValue.decVal.Lo32 = (unsigned __int64)a2;
      v7 = MFCreateMediaEvent(0xD6u, &Buf1, 0, &pvValue, &ppEvent);
      if ( v7 >= 0 )
      {
        if ( sub_1800DE7E8(a1 + 776, ppEvent) )
        {
          ppEvent = 0;
          if ( (unsigned __int8)byte_1801692CB >= 8u )
            sub_1800DD920(*((_QWORD *)RequestContext + 17), v16, v17, a1, *(_QWORD *)(a1 + 288));
          sub_1800DD188(a1, a2);
          *(_DWORD *)(a1 + 1280) = 1;
          if ( (unsigned __int8)byte_1801692CB >= 2u )
            sub_18006646C(*((_QWORD *)RequestContext + 17), 137, &stru_180158D48, a1, a2);
        }
        else
        {
          v18 = (__int64 (__fastcall ***)())qword_180169350;
          v7 = -2147024882;
          if ( !qword_180169350 )
          {
            v19 = MFGetCallStackTracingWeakReference(0, v16);
            qword_180169350 = v19;
            if ( v19 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
            {
              v18 = (__int64 (__fastcall ***)())qword_180169350;
            }
            else
            {
              v18 = &off_1801683B0;
              qword_180169350 = (__int64)&off_1801683B0;
            }
          }
          if ( *((_BYTE *)v18 + 8) )
          {
            v20 = sub_180001870(v18);
            if ( *(_DWORD *)(v20 + 1996) != -2147024882 )
              sub_18007FDD0(v20, "CASFBytewiseMediaStream::SetLastSendTimeAndTickIfNeeded", 1661, 2147942414LL);
          }
          if ( byte_1801692C8 )
          {
            v11 = 135;
            goto LABEL_14;
          }
        }
      }
      else
      {
        v13 = (__int64 (__fastcall ***)())qword_180169350;
        if ( !qword_180169350 )
        {
          v14 = MFGetCallStackTracingWeakReference(0, v12);
          qword_180169350 = v14;
          if ( v14 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
          {
            v13 = (__int64 (__fastcall ***)())qword_180169350;
          }
          else
          {
            v13 = &off_1801683B0;
            qword_180169350 = (__int64)&off_1801683B0;
          }
        }
        if ( *((_BYTE *)v13 + 8) )
        {
          v15 = sub_180001870(v13);
          if ( *(_DWORD *)(v15 + 1996) != v7 )
            sub_18007FDD0(v15, "CASFBytewiseMediaStream::SetLastSendTimeAndTickIfNeeded", 1658, (unsigned int)v7);
        }
        if ( byte_1801692C8 )
        {
          v11 = 134;
          goto LABEL_14;
        }
      }
    }
  }
  else
  {
    v8 = (__int64 (__fastcall ***)())qword_180169350;
    if ( !qword_180169350 )
    {
      v9 = MFGetCallStackTracingWeakReference(0, v6);
      qword_180169350 = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v8 = (__int64 (__fastcall ***)())qword_180169350;
      }
      else
      {
        v8 = &off_1801683B0;
        qword_180169350 = (__int64)&off_1801683B0;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      v10 = sub_180001870(v8);
      if ( *(_DWORD *)(v10 + 1996) != v7 )
        sub_18007FDD0(v10, "CASFBytewiseMediaStream::SetLastSendTimeAndTickIfNeeded", 1623, (unsigned int)v7);
    }
    if ( byte_1801692C8 )
    {
      v11 = 132;
LABEL_14:
      sub_18004F390(*((_QWORD *)RequestContext + 2), v11, &stru_180158D48, a1, v7);
    }
  }
  if ( ppEvent )
  {
    ((void (__fastcall *)(IMFMediaEvent *))ppEvent->lpVtbl->Release)(ppEvent);
    ppEvent = 0;
  }
  if ( v7 < 0 && byte_1801692C8 )
    sub_18004F390(*((_QWORD *)RequestContext + 2), 138, &stru_180158D48, a1, v7);
  sub_180005880();
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800dccf8  mov     [rsp-28h+arg_10], rbx
0x1800dccfd  mov     [rsp-28h+arg_18], rsi
0x1800dcd02  push    rbp
0x1800dcd03  push    rdi
0x1800dcd04  push    r13
0x1800dcd06  push    r14
0x1800dcd08  push    r15
0x1800dcd0a  mov     rbp, rsp
0x1800dcd0d  sub     rsp, 70h
0x1800dcd11  mov     rax, cs:__security_cookie
0x1800dcd18  xor     rax, rsp
0x1800dcd1b  mov     [rbp+var_8], rax
0x1800dcd1f  mov     rsi, rdx
0x1800dcd22  mov     rdi, rcx
0x1800dcd25  lea     rdx, aCasfbytewiseme_142; "CASFBytewiseMediaStream::SetLastSendTim"...
0x1800dcd2c  mov     r8d, 649h
0x1800dcd32  lea     rcx, [rbp+var_30]
0x1800dcd36  call    sub_18000A580
0x1800dcd3b  mov     [rbp+var_28], 0
0x1800dcd43  mov     [rbp+var_2C], 0
0x1800dcd4a  cmp     cs:byte_1801692CB, 8
0x1800dcd51  lea     r15, [rdi+128h]
0x1800dcd58  lea     r14, [rdi+120h]
0x1800dcd5f  lea     r13, stru_180158D48
0x1800dcd66  jb      short loc_1800DCDE4
0x1800dcd68  mov     r10, 346DC5D63886594Bh
0x1800dcd72  mov     rax, r10
0x1800dcd75  imul    qword ptr [r15]
0x1800dcd78  mov     rax, r10
0x1800dcd7b  mov     r9, rdx
0x1800dcd7e  imul    qword ptr [r14]
0x1800dcd81  sar     r9, 0Bh
0x1800dcd85  mov     rax, r10
0x1800dcd88  mov     rcx, r9
0x1800dcd8b  mov     r8, rdx
0x1800dcd8e  shr     rcx, 3Fh
0x1800dcd92  add     r9, rcx
0x1800dcd95  sar     r8, 0Bh
0x1800dcd99  imul    rsi
0x1800dcd9c  mov     rcx, r8
0x1800dcd9f  mov     [rsp+70h+var_40], r9
0x1800dcda4  shr     rcx, 3Fh
0x1800dcda8  mov     r9, rdi
0x1800dcdab  add     r8, rcx
0x1800dcdae  mov     rcx, rdx
0x1800dcdb1  sar     rcx, 0Bh
0x1800dcdb5  mov     edx, 83h
0x1800dcdba  mov     rax, rcx
0x1800dcdbd  mov     [rsp+70h+var_48], r8
0x1800dcdc2  shr     rax, 3Fh
0x1800dcdc6  mov     r8, r13
0x1800dcdc9  add     rcx, rax
0x1800dcdcc  mov     [rsp+70h+ppEvent], rcx
0x1800dcdd1  mov     rcx, cs:RequestContext
0x1800dcdd8  mov     rcx, [rcx+88h]
0x1800dcddf  call    sub_18009A1A0
0x1800dcde4  lea     rdx, [rbp+var_2C]
0x1800dcde8  mov     rcx, rdi
0x1800dcdeb  call    sub_1800DA804
0x1800dcdf0  mov     ebx, eax
0x1800dcdf2  test    eax, eax
0x1800dcdf4  jns     loc_1800DCEA4
0x1800dcdfa  mov     rcx, cs:qword_180169350
0x1800dce01  test    rcx, rcx
0x1800dce04  jnz     short loc_1800DCE48
0x1800dce06  call    cs:MFGetCallStackTracingWeakReference
0x1800dce0c  mov     cs:qword_180169350, rax
0x1800dce13  mov     rcx, rax
0x1800dce16  test    rax, rax
0x1800dce19  jz      short loc_1800DCE3A
0x1800dce1b  mov     rax, [rax]
0x1800dce1e  mov     edx, 7F0h
0x1800dce23  mov     rax, [rax+8]
0x1800dce27  call    cs:__guard_dispatch_icall_fptr
0x1800dce2d  test    eax, eax
0x1800dce2f  jz      short loc_1800DCE3A
0x1800dce31  mov     rcx, cs:qword_180169350
0x1800dce38  jmp     short loc_1800DCE48
0x1800dce3a  lea     rcx, off_1801683B0
0x1800dce41  mov     cs:qword_180169350, rcx
0x1800dce48  cmp     byte ptr [rcx+8], 0
0x1800dce4c  jz      short loc_1800DCE73
0x1800dce4e  call    sub_180001870
0x1800dce53  cmp     [rax+7CCh], ebx
0x1800dce59  jz      short loc_1800DCE73
0x1800dce5b  mov     r9d, ebx
0x1800dce5e  lea     rdx, aCasfbytewiseme_142; "CASFBytewiseMediaStream::SetLastSendTim"...
0x1800dce65  mov     r8d, 657h
0x1800dce6b  mov     rcx, rax
0x1800dce6e  call    sub_18007FDD0
0x1800dce73  cmp     cs:byte_1801692C8, 1
0x1800dce7a  jb      loc_1800DD106
0x1800dce80  mov     edx, 84h
0x1800dce85  mov     rcx, cs:RequestContext
0x1800dce8c  mov     r9, rdi
0x1800dce8f  mov     r8, r13
0x1800dce92  mov     dword ptr [rsp+70h+ppEvent], ebx
0x1800dce96  mov     rcx, [rcx+10h]
0x1800dce9a  call    sub_18004F390
0x1800dce9f  jmp     loc_1800DD106
0x1800dcea4  cmp     [rbp+var_2C], 0
0x1800dcea8  jz      short loc_1800DCEDA
0x1800dceaa  cmp     cs:byte_1801692CB, 8
0x1800dceb1  jb      loc_1800DD106
0x1800dceb7  mov     rcx, cs:RequestContext
0x1800dcebe  mov     edx, 85h
0x1800dcec3  mov     r9, rdi
0x1800dcec6  mov     r8, r13
0x1800dcec9  mov     rcx, [rcx+88h]
0x1800dced0  call    sub_1800520C4
0x1800dced5  jmp     loc_1800DD106
0x1800dceda  mov     rax, [r14]
0x1800dcedd  mov     ecx, 989680h
0x1800dcee2  add     rax, rcx
0x1800dcee5  cmp     rax, rsi
0x1800dcee8  jge     loc_1800DD106
0x1800dceee  mov     rax, [r15]
0x1800dcef1  add     rax, rcx
0x1800dcef4  cmp     rax, rsi
0x1800dcef7  jge     loc_1800DD106
0x1800dcefd  xor     eax, eax
0x1800dceff  lea     r9, [rbp+pvValue]; pvValue
0x1800dcf03  mov     qword ptr [rbp+pvValue+10h], rax
0x1800dcf07  lea     rdx, Buf1; guidExtendedType
0x1800dcf0e  xorps   xmm0, xmm0
0x1800dcf11  mov     eax, 14h
0x1800dcf16  movups  xmmword ptr [rbp+pvValue], xmm0
0x1800dcf1a  mov     word ptr [rbp+pvValue], ax
0x1800dcf1e  xor     r8d, r8d; hrStatus
0x1800dcf21  lea     rax, [rbp+var_28]
0x1800dcf25  mov     qword ptr [rbp+pvValue+8], rsi
0x1800dcf29  mov     ecx, 0D6h; met
0x1800dcf2e  mov     [rsp+70h+ppEvent], rax; ppEvent
0x1800dcf33  call    cs:MFCreateMediaEvent
0x1800dcf39  mov     ebx, eax
0x1800dcf3b  test    eax, eax
0x1800dcf3d  jns     loc_1800DCFD3
0x1800dcf43  mov     rcx, cs:qword_180169350
0x1800dcf4a  test    rcx, rcx
0x1800dcf4d  jnz     short loc_1800DCF91
0x1800dcf4f  call    cs:MFGetCallStackTracingWeakReference
0x1800dcf55  mov     cs:qword_180169350, rax
0x1800dcf5c  mov     rcx, rax
0x1800dcf5f  test    rax, rax
0x1800dcf62  jz      short loc_1800DCF83
0x1800dcf64  mov     rax, [rax]
0x1800dcf67  mov     edx, 7F0h
0x1800dcf6c  mov     rax, [rax+8]
0x1800dcf70  call    cs:__guard_dispatch_icall_fptr
0x1800dcf76  test    eax, eax
0x1800dcf78  jz      short loc_1800DCF83
0x1800dcf7a  mov     rcx, cs:qword_180169350
0x1800dcf81  jmp     short loc_1800DCF91
0x1800dcf83  lea     rcx, off_1801683B0
0x1800dcf8a  mov     cs:qword_180169350, rcx
0x1800dcf91  cmp     byte ptr [rcx+8], 0
0x1800dcf95  jz      short loc_1800DCFBC
0x1800dcf97  call    sub_180001870
0x1800dcf9c  cmp     [rax+7CCh], ebx
0x1800dcfa2  jz      short loc_1800DCFBC
0x1800dcfa4  mov     r9d, ebx
0x1800dcfa7  lea     rdx, aCasfbytewiseme_142; "CASFBytewiseMediaStream::SetLastSendTim"...
0x1800dcfae  mov     r8d, 67Ah
0x1800dcfb4  mov     rcx, rax
0x1800dcfb7  call    sub_18007FDD0
0x1800dcfbc  cmp     cs:byte_1801692C8, 1
0x1800dcfc3  jb      loc_1800DD106
0x1800dcfc9  mov     edx, 86h
0x1800dcfce  jmp     loc_1800DCE85
0x1800dcfd3  mov     rdx, [rbp+var_28]
0x1800dcfd7  lea     rcx, [rdi+308h]
0x1800dcfde  call    sub_1800DE7E8
0x1800dcfe3  test    rax, rax
0x1800dcfe6  jnz     loc_1800DD081
0x1800dcfec  mov     rcx, cs:qword_180169350
0x1800dcff3  mov     ebx, 8007000Eh
0x1800dcff8  test    rcx, rcx
0x1800dcffb  jnz     short loc_1800DD03F
0x1800dcffd  call    cs:MFGetCallStackTracingWeakReference
0x1800dd003  mov     cs:qword_180169350, rax
0x1800dd00a  mov     rcx, rax
0x1800dd00d  test    rax, rax
0x1800dd010  jz      short loc_1800DD031
0x1800dd012  mov     rax, [rax]
0x1800dd015  mov     edx, 7F0h
0x1800dd01a  mov     rax, [rax+8]
0x1800dd01e  call    cs:__guard_dispatch_icall_fptr
0x1800dd024  test    eax, eax
0x1800dd026  jz      short loc_1800DD031
0x1800dd028  mov     rcx, cs:qword_180169350
0x1800dd02f  jmp     short loc_1800DD03F
0x1800dd031  lea     rcx, off_1801683B0
0x1800dd038  mov     cs:qword_180169350, rcx
0x1800dd03f  cmp     byte ptr [rcx+8], 0
0x1800dd043  jz      short loc_1800DD06A
0x1800dd045  call    sub_180001870
0x1800dd04a  cmp     [rax+7CCh], ebx
0x1800dd050  jz      short loc_1800DD06A
0x1800dd052  mov     r9d, ebx
0x1800dd055  lea     rdx, aCasfbytewiseme_142; "CASFBytewiseMediaStream::SetLastSendTim"...
0x1800dd05c  mov     r8d, 67Dh
0x1800dd062  mov     rcx, rax
0x1800dd065  call    sub_18007FDD0
0x1800dd06a  cmp     cs:byte_1801692C8, 1
0x1800dd071  jb      loc_1800DD106
0x1800dd077  mov     edx, 87h
0x1800dd07c  jmp     loc_1800DCE85
0x1800dd081  mov     [rbp+var_28], 0
0x1800dd089  cmp     cs:byte_1801692CB, 8
0x1800dd090  jb      short loc_1800DD0C5
0x1800dd092  mov     rax, [rdi+128h]
0x1800dd099  mov     r9, rdi
0x1800dd09c  mov     rcx, cs:RequestContext
0x1800dd0a3  mov     [rsp+70h+var_38], rsi
0x1800dd0a8  mov     [rsp+70h+var_40], rax
0x1800dd0ad  mov     rax, [rdi+120h]
0x1800dd0b4  mov     rcx, [rcx+88h]
0x1800dd0bb  mov     [rsp+70h+ppEvent], rax
0x1800dd0c0  call    sub_1800DD920
0x1800dd0c5  mov     rdx, rsi
0x1800dd0c8  mov     rcx, rdi
0x1800dd0cb  call    sub_1800DD188
0x1800dd0d0  mov     dword ptr [rdi+500h], 1
0x1800dd0da  cmp     cs:byte_1801692CB, 2
0x1800dd0e1  jb      short loc_1800DD106
0x1800dd0e3  mov     rcx, cs:RequestContext
0x1800dd0ea  mov     edx, 89h
0x1800dd0ef  mov     r9, rdi
0x1800dd0f2  mov     [rsp+70h+ppEvent], rsi
0x1800dd0f7  mov     r8, r13
0x1800dd0fa  mov     rcx, [rcx+88h]
0x1800dd101  call    sub_18006646C
0x1800dd106  mov     rcx, [rbp+var_28]
0x1800dd10a  test    rcx, rcx
0x1800dd10d  jz      short loc_1800DD124
0x1800dd10f  mov     rax, [rcx]
0x1800dd112  mov     rax, [rax+10h]
0x1800dd116  call    cs:__guard_dispatch_icall_fptr
0x1800dd11c  mov     [rbp+var_28], 0
0x1800dd124  test    ebx, ebx
0x1800dd126  jns     short loc_1800DD150
0x1800dd128  cmp     cs:byte_1801692C8, 1
0x1800dd12f  jb      short loc_1800DD150
0x1800dd131  mov     rcx, cs:RequestContext
0x1800dd138  mov     edx, 8Ah
0x1800dd13d  mov     r9, rdi
0x1800dd140  mov     dword ptr [rsp+70h+ppEvent], ebx
0x1800dd144  mov     r8, r13
0x1800dd147  mov     rcx, [rcx+10h]
0x1800dd14b  call    sub_18004F390
0x1800dd150  lea     rcx, [rbp+var_30]
0x1800dd154  call    sub_180005880
0x1800dd159  mov     eax, ebx
0x1800dd15b  mov     rcx, [rbp+var_8]
0x1800dd15f  xor     rcx, rsp; StackCookie
0x1800dd162  call    __security_check_cookie
0x1800dd167  lea     r11, [rsp+70h+var_s0]
0x1800dd16c  mov     rbx, [r11+40h]
0x1800dd170  mov     rsi, [r11+48h]
0x1800dd174  mov     rsp, r11
0x1800dd177  pop     r15
0x1800dd179  pop     r14
0x1800dd17b  pop     r13
0x1800dd17d  pop     rdi
0x1800dd17e  pop     rbp
0x1800dd17f  retn
```
