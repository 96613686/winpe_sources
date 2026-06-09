# UnpackReport

- ea: `0x1800053e0`
- end: `0x180005678`
- name: `UnpackReport`
- size: `664`
- prototype: `__int64 __fastcall(PCHAR Report, unsigned __int16, __int64, __int64, unsigned int, PHIDP_PREPARSED_DATA)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x180004310`

## callees

- `0x1800025e0`
- `0x180005038`
- `0x1800053e0`

## import_xrefs

- `HID!HidP_GetUsages` at `0x18000546a`
- `HID!HidP_GetUsages` at `0x18000546a`
- `HID!HidP_GetScaledUsageValue` at `0x18000560c`
- `HID!HidP_GetScaledUsageValue` at `0x18000560c`
- `HID!HidP_GetUsageValue` at `0x18000559c`
- `HID!HidP_GetUsageValue` at `0x18000559c`

## pseudocode

```c
__int64 __fastcall UnpackReport(
        PCHAR Report,
        unsigned __int16 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        PHIDP_PREPARSED_DATA a6)
{
  unsigned int v6; // r14d
  unsigned int v7; // ebp
  struct _HIDP_PREPARSED_DATA *PreparsedData; // r13
  ULONG ReportLength; // r12d
  USHORT v12; // r8
  USAGE v13; // dx
  USHORT *v14; // r9
  unsigned int Usages; // eax
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rdi
  __int64 v19; // rax
  unsigned int UsageValue; // eax
  unsigned int ScaledUsageValue; // eax
  ULONG UsageLength; // [rsp+A0h] [rbp+18h] BYREF

  v6 = a5;
  v7 = 0;
  UsageLength = 0;
  if ( a5 )
  {
    PreparsedData = a6;
    ReportLength = a2;
    do
    {
      v12 = *(_WORD *)(a4 + 4);
      v13 = *(_WORD *)(a4 + 2);
      if ( !*(_BYTE *)a4 )
      {
        UsageValue = HidP_GetUsageValue(
                       HidP_Input,
                       v13,
                       v12,
                       *(_WORD *)(a4 + 16),
                       (PULONG)(a4 + 20),
                       PreparsedData,
                       Report,
                       ReportLength);
        *(_DWORD *)(a4 + 8) = UsageValue;
        if ( UsageValue != 1114112
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_DD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            12,
            WPP_cf79ee9a75143921db09db349da877be_Traceguids,
            UsageValue,
            *(unsigned __int16 *)(a4 + 16));
        }
        ScaledUsageValue = HidP_GetScaledUsageValue(
                             HidP_Input,
                             *(_WORD *)(a4 + 2),
                             *(_WORD *)(a4 + 4),
                             *(_WORD *)(a4 + 16),
                             (PLONG)(a4 + 24),
                             PreparsedData,
                             Report,
                             ReportLength);
        *(_DWORD *)(a4 + 8) = ScaledUsageValue;
        if ( ScaledUsageValue != 1114112
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_DD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            WPP_cf79ee9a75143921db09db349da877be_Traceguids,
            ScaledUsageValue,
            *(unsigned __int16 *)(a4 + 16));
        }
        goto LABEL_34;
      }
      v14 = *(USHORT **)(a4 + 24);
      UsageLength = *(_DWORD *)(a4 + 16);
      Usages = HidP_GetUsages(HidP_Input, v13, v12, v14, &UsageLength, PreparsedData, Report, ReportLength);
      *(_DWORD *)(a4 + 8) = Usages;
      if ( Usages != 1114112 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_10;
        }
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_cf79ee9a75143921db09db349da877be_Traceguids, Usages);
      }
      v16 = WPP_GLOBAL_Control;
LABEL_10:
      if ( *(_DWORD *)(a4 + 8) == 1114112 && *(_WORD *)(a4 + 2) == 1 )
      {
        v17 = UsageLength;
        v18 = 0;
        if ( ((UsageLength + 1) & 0xFFFFFFFE) != 0 )
        {
          do
          {
            v19 = *(_QWORD *)(a4 + 24);
            if ( *(_WORD *)(v19 + 4 * v18) == 154 )
            {
              if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 8) != 0 && *((_BYTE *)v16 + 25) >= 4u )
                WPP_SF_DD(
                  v16[2],
                  11,
                  WPP_cf79ee9a75143921db09db349da877be_Traceguids,
                  *(unsigned __int16 *)(v19 + 4 * v18 + 2),
                  v18);
              *(_WORD *)(*(_QWORD *)(a4 + 24) + 4 * v18 + 2) = *(_WORD *)(a4 + 2);
              v17 = UsageLength;
              v16 = WPP_GLOBAL_Control;
            }
            v18 = (unsigned int)(v18 + 1);
          }
          while ( (unsigned int)v18 < (unsigned int)(v17 + 1) >> 1 );
          v6 = a5;
        }
      }
      else
      {
        v17 = UsageLength;
      }
      if ( (unsigned int)v17 < *(_DWORD *)(a4 + 16) )
      {
        *(_WORD *)(*(_QWORD *)(a4 + 24) + 4 * v17) = 0;
        *(_WORD *)(*(_QWORD *)(a4 + 24) + 4LL * UsageLength + 2) = 0;
      }
LABEL_34:
      ++v7;
      a4 += 40;
    }
    while ( v7 < v6 );
  }
  return 1;
}

```

## disassembly

```asm
0x1800053e0  mov     rax, rsp
0x1800053e3  mov     [rax+18h], r8d
0x1800053e7  push    rbx
0x1800053e8  push    rbp
0x1800053e9  push    rsi
0x1800053ea  push    rdi
0x1800053eb  push    r12
0x1800053ed  push    r13
0x1800053ef  push    r14
0x1800053f1  push    r15
0x1800053f3  sub     rsp, 48h
0x1800053f7  mov     r14d, [rsp+88h+arg_20]
0x1800053ff  xor     ebp, ebp
0x180005401  mov     dword ptr [rax+18h], 0
0x180005408  mov     rbx, r9
0x18000540b  mov     r15, rcx
0x18000540e  lea     edi, [rbp+1]
0x180005411  test    r14d, r14d
0x180005414  jz      loc_180005665
0x18000541a  mov     r13, [rsp+88h+arg_28]
0x180005422  lea     rsi, WPP_GLOBAL_Control
0x180005429  movzx   r12d, dx
0x18000542d  movzx   r8d, word ptr [rbx+4]; LinkCollection
0x180005432  xor     ecx, ecx; ReportType
0x180005434  movzx   edx, word ptr [rbx+2]; UsagePage
0x180005438  mov     [rsp+88h+ReportLength], r12d; ReportLength
0x18000543d  mov     [rsp+88h+Report], r15; Report
0x180005442  mov     [rsp+88h+PreparsedData], r13; PreparsedData
0x180005447  cmp     [rbx], cl
0x180005449  jz      loc_18000558E
0x18000544f  mov     eax, [rbx+10h]
0x180005452  mov     r9, [rbx+18h]; UsageList
0x180005456  mov     [rsp+88h+arg_10], eax
0x18000545d  lea     rax, [rsp+88h+arg_10]
0x180005465  mov     [rsp+88h+UsageLength], rax; UsageLength
0x18000546a  call    cs:__imp_HidP_GetUsages
0x180005470  mov     [rbx+8], eax
0x180005473  cmp     eax, 110000h
0x180005478  jz      short loc_1800054AA
0x18000547a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005481  cmp     rcx, rsi
0x180005484  jz      short loc_1800054B1
0x180005486  test    byte ptr [rcx+1Ch], 8
0x18000548a  jz      short loc_1800054B1
0x18000548c  cmp     byte ptr [rcx+19h], 2
0x180005490  jb      short loc_1800054B1
0x180005492  mov     rcx, [rcx+10h]
0x180005496  lea     r8, WPP_cf79ee9a75143921db09db349da877be_Traceguids
0x18000549d  mov     edx, 0Ah
0x1800054a2  mov     r9d, eax
0x1800054a5  call    WPP_SF_D
0x1800054aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800054b1  cmp     dword ptr [rbx+8], 110000h
0x1800054b8  jnz     loc_180005585
0x1800054be  cmp     [rbx+2], di
0x1800054c2  jnz     loc_180005585
0x1800054c8  mov     edx, [rsp+88h+arg_10]
0x1800054cf  xor     edi, edi
0x1800054d1  lea     eax, [rdx+1]
0x1800054d4  test    eax, 0FFFFFFFEh
0x1800054d9  jbe     short loc_180005558
0x1800054db  lea     r14, WPP_GLOBAL_Control
0x1800054e2  mov     rax, [rbx+18h]
0x1800054e6  mov     r8d, 9Ah
0x1800054ec  cmp     [rax+rdi*4], r8w
0x1800054f1  jnz     short loc_18000553E
0x1800054f3  cmp     rcx, r14
0x1800054f6  jz      short loc_180005523
0x1800054f8  test    byte ptr [rcx+1Ch], 8
0x1800054fc  jz      short loc_180005523
0x1800054fe  cmp     byte ptr [rcx+19h], 4
0x180005502  jb      short loc_180005523
0x180005504  movzx   r9d, word ptr [rax+rdi*4+2]
0x18000550a  lea     r8, WPP_cf79ee9a75143921db09db349da877be_Traceguids
0x180005511  mov     rcx, [rcx+10h]
0x180005515  mov     edx, 0Bh
0x18000551a  mov     dword ptr [rsp+88h+UsageLength], edi
0x18000551e  call    WPP_SF_DD
0x180005523  mov     rcx, [rbx+18h]
0x180005527  movzx   eax, word ptr [rbx+2]
0x18000552b  mov     [rcx+rdi*4+2], ax
0x180005530  mov     edx, [rsp+88h+arg_10]
0x180005537  mov     rcx, cs:WPP_GLOBAL_Control
0x18000553e  lea     eax, [rdx+1]
0x180005541  inc     edi
0x180005543  shr     eax, 1
0x180005545  cmp     edi, eax
0x180005547  jb      short loc_1800054E2
0x180005549  mov     r14d, [rsp+88h+arg_20]
0x180005551  lea     rsi, WPP_GLOBAL_Control
0x180005558  mov     edi, 1
0x18000555d  cmp     edx, [rbx+10h]
0x180005560  jnb     loc_180005656
0x180005566  mov     rcx, [rbx+18h]
0x18000556a  xor     eax, eax
0x18000556c  mov     [rcx+rdx*4], ax
0x180005570  mov     edx, [rsp+88h+arg_10]
0x180005577  mov     rcx, [rbx+18h]
0x18000557b  mov     [rcx+rdx*4+2], ax
0x180005580  jmp     loc_180005656
0x180005585  mov     edx, [rsp+88h+arg_10]
0x18000558c  jmp     short loc_18000555D
0x18000558e  movzx   r9d, word ptr [rbx+10h]; Usage
0x180005593  lea     rax, [rbx+14h]
0x180005597  mov     [rsp+88h+UsageLength], rax; UsageValue
0x18000559c  call    cs:__imp_HidP_GetUsageValue
0x1800055a2  mov     [rbx+8], eax
0x1800055a5  mov     r9d, eax
0x1800055a8  cmp     eax, 110000h
0x1800055ad  jz      short loc_1800055E4
0x1800055af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800055b6  cmp     rcx, rsi
0x1800055b9  jz      short loc_1800055E4
0x1800055bb  test    byte ptr [rcx+1Ch], 8
0x1800055bf  jz      short loc_1800055E4
0x1800055c1  cmp     byte ptr [rcx+19h], 2
0x1800055c5  jb      short loc_1800055E4
0x1800055c7  movzx   eax, word ptr [rbx+10h]
0x1800055cb  lea     r8, WPP_cf79ee9a75143921db09db349da877be_Traceguids
0x1800055d2  mov     rcx, [rcx+10h]
0x1800055d6  mov     edx, 0Ch
0x1800055db  mov     dword ptr [rsp+88h+UsageLength], eax
0x1800055df  call    WPP_SF_DD
0x1800055e4  movzx   r9d, word ptr [rbx+10h]; Usage
0x1800055e9  lea     rax, [rbx+18h]
0x1800055ed  movzx   r8d, word ptr [rbx+4]; LinkCollection
0x1800055f2  xor     ecx, ecx; ReportType
0x1800055f4  movzx   edx, word ptr [rbx+2]; UsagePage
0x1800055f8  mov     [rsp+88h+ReportLength], r12d; ReportLength
0x1800055fd  mov     [rsp+88h+Report], r15; Report
0x180005602  mov     [rsp+88h+PreparsedData], r13; PreparsedData
0x180005607  mov     [rsp+88h+UsageLength], rax; UsageValue
0x18000560c  call    cs:__imp_HidP_GetScaledUsageValue
0x180005612  mov     [rbx+8], eax
0x180005615  cmp     eax, 110000h
0x18000561a  jz      short loc_180005656
0x18000561c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005623  cmp     rcx, rsi
0x180005626  jz      short loc_180005656
0x180005628  test    byte ptr [rcx+1Ch], 8
0x18000562c  jz      short loc_180005656
0x18000562e  cmp     byte ptr [rcx+19h], 2
0x180005632  jb      short loc_180005656
0x180005634  movzx   r8d, word ptr [rbx+10h]
0x180005639  mov     edx, 0Dh
0x18000563e  mov     rcx, [rcx+10h]
0x180005642  mov     r9d, eax
0x180005645  mov     dword ptr [rsp+88h+UsageLength], r8d
0x18000564a  lea     r8, WPP_cf79ee9a75143921db09db349da877be_Traceguids
0x180005651  call    WPP_SF_DD
0x180005656  add     ebp, edi
0x180005658  add     rbx, 28h ; '('
0x18000565c  cmp     ebp, r14d
0x18000565f  jb      loc_18000542D
0x180005665  mov     eax, edi
0x180005667  add     rsp, 48h
0x18000566b  pop     r15
0x18000566d  pop     r14
0x18000566f  pop     r13
0x180005671  pop     r12
0x180005673  pop     rdi
0x180005674  pop     rsi
0x180005675  pop     rbp
0x180005676  pop     rbx
0x180005677  retn
```
