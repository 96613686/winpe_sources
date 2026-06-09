# FvepCheckMetadataLogicalCopies

- ea: `0x1400afe88`
- end: `0x1400b03e9`
- name: `FvepCheckMetadataLogicalCopies`
- size: `1377`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400a6ed8`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x14000badc`
- `0x14000ca78`
- `0x14000cba0`
- `0x1400afe88`
- `0x1400b09d8`
- `0x1400b39f4`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400b0068`
- `ntoskrnl!RtlCompareMemory` at `0x1400b0068`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400affef`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b0394`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400affef`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b0394`

## pseudocode

```c
__int64 __fastcall FvepCheckMetadataLogicalCopies(__int64 *a1, const void *a2, _DWORD *a3, __int64 a4)
{
  __int64 *v4; // r15
  unsigned __int64 v5; // rcx
  void *v6; // rbx
  unsigned __int64 v7; // rdx
  int v8; // ebp
  __int64 v9; // r11
  unsigned int v10; // edi
  unsigned __int64 v11; // r14
  unsigned __int64 v12; // r8
  unsigned __int64 v13; // r10
  bool v14; // zf
  char v16; // r12
  char v17; // r13
  __int64 v18; // rsi
  int InformationAndValidationFromLogicalCopy; // r15d
  SIZE_T v20; // rbx
  __int64 v21; // r8
  int v22; // r8d
  unsigned int v24; // [rsp+20h] [rbp-B8h]
  int v25; // [rsp+28h] [rbp-B0h]
  unsigned int v26; // [rsp+60h] [rbp-78h]
  __int64 v27; // [rsp+68h] [rbp-70h]
  void *Source1; // [rsp+70h] [rbp-68h] BYREF
  unsigned __int64 v29; // [rsp+78h] [rbp-60h]
  __int64 v30[11]; // [rsp+80h] [rbp-58h] BYREF
  __int64 v34; // [rsp+F8h] [rbp+20h]

  v34 = a4;
  v4 = a1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 438, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids);
    a4 = v34;
  }
  v5 = *((unsigned int *)v4 + 327);
  v6 = 0;
  v7 = v4[131];
  v8 = 0;
  v9 = 0;
  Source1 = 0;
  v27 = 0;
  v30[0] = 0;
  v26 = v5;
  v29 = v7;
  do
  {
    v10 = *(_DWORD *)(a4 + 24 * v9 + 8);
    v11 = *(_QWORD *)(a4 + 24 * v9);
    if ( v10 )
    {
      if ( (((_DWORD)v5 - 1) & (unsigned int)v5) != 0 || !(_DWORD)v5 )
      {
        if ( v10 % (unsigned int)v5 )
          v10 = v5 + v10 - v10 % (unsigned int)v5;
        v7 = v29;
      }
      else
      {
        v10 = ~(v5 - 1) & (v5 + v10 - 1);
      }
    }
    else
    {
      v10 = 0x10000;
    }
    v12 = v10 + v11;
    if ( v12 < v11 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v25 = -1073741675;
        v24 = v10;
        WPP_SF_iiL(WPP_GLOBAL_Control->AttachedDevice, 439, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids, v11);
        v9 = v27;
      }
      if ( v8 >= 0 )
        v8 = -1071579105;
    }
    else
    {
      if ( v11 && v12 <= v7 )
      {
        v13 = v5 - 1;
        if ( (v5 & (v5 - 1)) != 0 || !v5 )
          v14 = v11 % v5 == 0;
        else
          v14 = (v13 & v11) == 0;
        if ( v14 && ((v5 & (v5 - 1)) != 0 || !v5 ? v12 % v5 == 0 : (v13 & v12) == 0) )
        {
          v16 = 0;
          v17 = 0;
          v18 = 0;
          if ( !*((_DWORD *)v4 + 346) )
            goto LABEL_72;
          while ( 1 )
          {
            if ( v6 )
            {
              ExFreePoolWithTag(v6, 0x30455646u);
              Source1 = 0;
              v30[0] = 0;
            }
            InformationAndValidationFromLogicalCopy = FvepReadInformationAndValidationFromLogicalCopy(
                                                        (_DWORD)v4,
                                                        v11,
                                                        v10,
                                                        v18,
                                                        v24,
                                                        v25,
                                                        (__int64)&Source1,
                                                        (__int64)v30);
            if ( InformationAndValidationFromLogicalCopy < 0 )
            {
              if ( InformationAndValidationFromLogicalCopy == -1071579134 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_iDDd(WPP_GLOBAL_Control->AttachedDevice, 443, 3223388162LL, v11, v10, v18, -1071579134);
                }
                v16 = 1;
                *(_DWORD *)(*(_QWORD *)(v34 + 24 * v27 + 16) + 4 * v18) = 2;
              }
              else
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_iDDd(
                    WPP_GLOBAL_Control->AttachedDevice,
                    444,
                    3223388162LL,
                    v11,
                    v10,
                    v18,
                    InformationAndValidationFromLogicalCopy);
                }
                *(_DWORD *)(*(_QWORD *)(v34 + 24 * v27 + 16) + 4 * v18) = 0;
              }
              if ( v8 >= 0 )
                v8 = InformationAndValidationFromLogicalCopy;
            }
            else
            {
              v20 = *(unsigned int *)(v34 + 24 * v27 + 8);
              if ( RtlCompareMemory(Source1, a2, v20) == v20 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  v25 = v18;
                  v24 = v10;
                  WPP_SF_iDD(WPP_GLOBAL_Control->AttachedDevice, 441, v21, v11);
                }
                v9 = v27;
                v17 = 1;
                v4 = a1;
                *(_DWORD *)(*(_QWORD *)(v34 + 24 * v27 + 16) + 4 * v18) = 1;
                v18 = (unsigned int)(v18 + 1);
                goto LABEL_56;
              }
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                WPP_SF_iDD(WPP_GLOBAL_Control->AttachedDevice, 442, v21, v11);
              }
              v16 = 1;
              *(_DWORD *)(*(_QWORD *)(v34 + 24 * v27 + 16) + 4 * v18) = 2;
            }
            v18 = (unsigned int)(v18 + 1);
            v22 = InformationAndValidationFromLogicalCopy;
            v4 = a1;
            v25 = v18;
            FveLogEventWithMetadataInfo(
              *a1,
              (const EVENT_DESCRIPTOR *)FVE_METADATA_LOGICAL_COPY_MATCH_FAIL,
              v22,
              v11,
              v10);
            v9 = v27;
LABEL_56:
            v6 = Source1;
            if ( (unsigned int)v18 >= *((_DWORD *)v4 + 346) )
            {
              if ( v17 && v16 )
                *a3 |= 0x10000u;
              goto LABEL_72;
            }
          }
        }
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v25 = 0;
        v24 = v10 + v11;
        WPP_SF_iiL(WPP_GLOBAL_Control->AttachedDevice, 440, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids, v11);
        v9 = v27;
      }
      if ( v8 >= 0 )
        v8 = -1071579105;
    }
LABEL_72:
    v5 = v26;
    ++v9;
    a4 = v34;
    v7 = v29;
    v27 = v9;
  }
  while ( v9 != 3 );
  if ( v6 )
    ExFreePoolWithTag(v6, 0x30455646u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 445, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids, (unsigned int)v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400afe88  mov     rax, rsp
0x1400afe8b  mov     [rax+20h], r9
0x1400afe8f  mov     [rax+18h], r8
0x1400afe93  mov     [rax+10h], rdx
0x1400afe97  mov     [rax+8], rcx
0x1400afe9b  push    rbx
0x1400afe9c  push    rbp
0x1400afe9d  push    rsi
0x1400afe9e  push    rdi
0x1400afe9f  push    r12
0x1400afea1  push    r13
0x1400afea3  push    r14
0x1400afea5  push    r15
0x1400afea7  sub     rsp, 98h
0x1400afeae  mov     r15, rcx
0x1400afeb1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400afeb8  lea     rsi, WPP_GLOBAL_Control
0x1400afebf  cmp     rcx, rsi
0x1400afec2  jz      short loc_1400AFEEE
0x1400afec4  mov     eax, [rcx+2Ch]
0x1400afec7  test    al, 4
0x1400afec9  jz      short loc_1400AFEEE
0x1400afecb  cmp     byte ptr [rcx+29h], 5
0x1400afecf  jb      short loc_1400AFEEE
0x1400afed1  mov     rcx, [rcx+18h]
0x1400afed5  lea     r8, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids
0x1400afedc  mov     edx, 1B6h
0x1400afee1  call    WPP_SF_
0x1400afee6  mov     r9, [rsp+0D8h+arg_18]
0x1400afeee  mov     ecx, [r15+51Ch]
0x1400afef5  xor     ebx, ebx
0x1400afef7  mov     rdx, [r15+418h]
0x1400afefe  xor     ebp, ebp
0x1400aff00  xor     r11d, r11d
0x1400aff03  mov     [rsp+0D8h+Source1], rbx
0x1400aff08  mov     [rsp+0D8h+var_70], r11
0x1400aff0d  mov     r12d, 0C021001Fh
0x1400aff13  mov     [rsp+0D8h+var_58], rbx
0x1400aff1b  mov     [rsp+0D8h+var_78], ecx
0x1400aff1f  mov     [rsp+0D8h+var_60], rdx
0x1400aff24  lea     rax, [r11+r11*2]
0x1400aff28  mov     edi, [r9+rax*8+8]
0x1400aff2d  mov     r14, [r9+rax*8]
0x1400aff31  test    edi, edi
0x1400aff33  jnz     short loc_1400AFF3C
0x1400aff35  mov     edi, 10000h
0x1400aff3a  jmp     short loc_1400AFF64
0x1400aff3c  lea     eax, [rcx-1]
0x1400aff3f  test    ecx, eax
0x1400aff41  jnz     short loc_1400AFF51
0x1400aff43  test    ecx, ecx
0x1400aff45  jz      short loc_1400AFF51
0x1400aff47  dec     edi
0x1400aff49  not     eax
0x1400aff4b  add     edi, ecx
0x1400aff4d  and     edi, eax
0x1400aff4f  jmp     short loc_1400AFF64
0x1400aff51  xor     edx, edx
0x1400aff53  mov     eax, edi
0x1400aff55  div     ecx
0x1400aff57  test    edx, edx
0x1400aff59  jz      short loc_1400AFF5F
0x1400aff5b  sub     edi, edx
0x1400aff5d  add     edi, ecx
0x1400aff5f  mov     rdx, [rsp+0D8h+var_60]
0x1400aff64  mov     r9d, edi
0x1400aff67  lea     r8, [r9+r14]
0x1400aff6b  cmp     r8, r14
0x1400aff6e  jb      loc_1400B030C
0x1400aff74  test    r14, r14
0x1400aff77  jz      loc_1400B02C0
0x1400aff7d  cmp     r8, rdx
0x1400aff80  ja      loc_1400B02C0
0x1400aff86  lea     r10, [rcx-1]
0x1400aff8a  mov     r9, r10
0x1400aff8d  and     r9, rcx
0x1400aff90  jnz     short loc_1400AFF9C
0x1400aff92  test    rcx, rcx
0x1400aff95  jz      short loc_1400AFF9C
0x1400aff97  test    r14, r10
0x1400aff9a  jmp     short loc_1400AFFA7
0x1400aff9c  xor     edx, edx
0x1400aff9e  mov     rax, r14
0x1400affa1  div     rcx
0x1400affa4  test    rdx, rdx
0x1400affa7  jnz     loc_1400B02C0
0x1400affad  test    r9, r9
0x1400affb0  jnz     short loc_1400AFFBC
0x1400affb2  test    rcx, rcx
0x1400affb5  jz      short loc_1400AFFBC
0x1400affb7  test    r8, r10
0x1400affba  jmp     short loc_1400AFFC7
0x1400affbc  xor     edx, edx
0x1400affbe  mov     rax, r8
0x1400affc1  div     rcx
0x1400affc4  test    rdx, rdx
0x1400affc7  jnz     loc_1400B02C0
0x1400affcd  xor     r12b, r12b
0x1400affd0  xor     r13b, r13b
0x1400affd3  xor     esi, esi
0x1400affd5  cmp     [r15+568h], esi
0x1400affdc  jbe     loc_1400B0357
0x1400affe2  test    rbx, rbx
0x1400affe5  jz      short loc_1400B0010
0x1400affe7  mov     edx, 30455646h; Tag
0x1400affec  mov     rcx, rbx; P
0x1400affef  call    cs:__imp_ExFreePoolWithTag
0x1400afff6  nop     dword ptr [rax+rax+00h]
0x1400afffb  mov     [rsp+0D8h+Source1], 0
0x1400b0004  mov     [rsp+0D8h+var_58], 0
0x1400b0010  lea     rax, [rsp+0D8h+var_58]
0x1400b0018  mov     r9d, esi
0x1400b001b  mov     [rsp+0D8h+var_A0], rax
0x1400b0020  mov     r8d, edi
0x1400b0023  lea     rax, [rsp+0D8h+Source1]
0x1400b0028  mov     rdx, r14
0x1400b002b  mov     rcx, r15
0x1400b002e  mov     [rsp+0D8h+var_A8], rax
0x1400b0033  call    FvepReadInformationAndValidationFromLogicalCopy
0x1400b0038  mov     r15d, eax
0x1400b003b  test    eax, eax
0x1400b003d  js      loc_1400B0144
0x1400b0043  mov     rdx, [rsp+0D8h+var_70]
0x1400b0048  mov     rcx, [rsp+0D8h+arg_18]
0x1400b0050  lea     rax, [rdx+rdx*2]
0x1400b0054  mov     rdx, [rsp+0D8h+Source2]; Source2
0x1400b005c  mov     ebx, [rcx+rax*8+8]
0x1400b0060  mov     rcx, [rsp+0D8h+Source1]; Source1
0x1400b0065  mov     r8d, ebx; Length
0x1400b0068  call    cs:__imp_RtlCompareMemory
0x1400b006f  nop     dword ptr [rax+rax+00h]
0x1400b0074  cmp     rax, rbx
0x1400b0077  jnz     short loc_1400B00E1
0x1400b0079  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b0080  lea     rax, WPP_GLOBAL_Control
0x1400b0087  cmp     rcx, rax
0x1400b008a  jz      short loc_1400B00B2
0x1400b008c  mov     eax, [rcx+2Ch]
0x1400b008f  test    al, 4
0x1400b0091  jz      short loc_1400B00B2
0x1400b0093  cmp     byte ptr [rcx+29h], 4
0x1400b0097  jb      short loc_1400B00B2
0x1400b0099  mov     rcx, [rcx+18h]
0x1400b009d  mov     edx, 1B9h
0x1400b00a2  mov     dword ptr [rsp+0D8h+var_B0], esi
0x1400b00a6  mov     r9, r14
0x1400b00a9  mov     dword ptr [rsp+0D8h+var_B8], edi
0x1400b00ad  call    WPP_SF_iDD
0x1400b00b2  mov     r11, [rsp+0D8h+var_70]
0x1400b00b7  mov     r13b, 1
0x1400b00ba  mov     rdx, [rsp+0D8h+arg_18]
0x1400b00c2  mov     r15, [rsp+0D8h+arg_0]
0x1400b00ca  lea     rax, [r11+r11*2]
0x1400b00ce  mov     rax, [rdx+rax*8+10h]
0x1400b00d3  mov     dword ptr [rax+rsi*4], 1
0x1400b00da  inc     esi
0x1400b00dc  jmp     loc_1400B027D
0x1400b00e1  mov     ebx, 4CA2h
0x1400b00e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b00ed  lea     rax, WPP_GLOBAL_Control
0x1400b00f4  cmp     rcx, rax
0x1400b00f7  jz      short loc_1400B011F
0x1400b00f9  mov     eax, [rcx+2Ch]
0x1400b00fc  test    al, 4
0x1400b00fe  jz      short loc_1400B011F
0x1400b0100  cmp     byte ptr [rcx+29h], 2
0x1400b0104  jb      short loc_1400B011F
0x1400b0106  mov     rcx, [rcx+18h]
0x1400b010a  mov     edx, 1BAh
0x1400b010f  mov     dword ptr [rsp+0D8h+var_B0], esi
0x1400b0113  mov     r9, r14
0x1400b0116  mov     dword ptr [rsp+0D8h+var_B8], edi
0x1400b011a  call    WPP_SF_iDD
0x1400b011f  mov     r8, [rsp+0D8h+var_70]
0x1400b0124  mov     r12b, 1
0x1400b0127  mov     rdx, [rsp+0D8h+arg_18]
0x1400b012f  lea     rax, [r8+r8*2]
0x1400b0133  mov     rax, [rdx+rax*8+10h]
0x1400b0138  mov     dword ptr [rax+rsi*4], 2
0x1400b013f  jmp     loc_1400B021A
0x1400b0144  mov     r8d, 0C0210002h
0x1400b014a  cmp     r15d, r8d
0x1400b014d  jnz     short loc_1400B01B4
0x1400b014f  mov     ebx, 4CB4h
0x1400b0154  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b015b  lea     rax, WPP_GLOBAL_Control
0x1400b0162  cmp     rcx, rax
0x1400b0165  jz      short loc_1400B0192
0x1400b0167  mov     eax, [rcx+2Ch]
0x1400b016a  test    al, 4
0x1400b016c  jz      short loc_1400B0192
0x1400b016e  cmp     byte ptr [rcx+29h], 2
0x1400b0172  jb      short loc_1400B0192
0x1400b0174  mov     rcx, [rcx+18h]
0x1400b0178  mov     edx, 1BBh
0x1400b017d  mov     dword ptr [rsp+0D8h+var_A8], r8d
0x1400b0182  mov     r9, r14
0x1400b0185  mov     dword ptr [rsp+0D8h+var_B0], esi
0x1400b0189  mov     dword ptr [rsp+0D8h+var_B8], edi
0x1400b018d  call    WPP_SF_iDDd
0x1400b0192  mov     r8, [rsp+0D8h+var_70]
0x1400b0197  mov     r12b, 1
0x1400b019a  mov     rdx, [rsp+0D8h+arg_18]
0x1400b01a2  lea     rax, [r8+r8*2]
0x1400b01a6  mov     rax, [rdx+rax*8+10h]
0x1400b01ab  mov     dword ptr [rax+rsi*4], 2
0x1400b01b2  jmp     short loc_1400B0214
0x1400b01b4  mov     ebx, 4CC3h
0x1400b01b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b01c0  lea     rax, WPP_GLOBAL_Control
0x1400b01c7  cmp     rcx, rax
0x1400b01ca  jz      short loc_1400B01F7
0x1400b01cc  mov     eax, [rcx+2Ch]
0x1400b01cf  test    al, 4
0x1400b01d1  jz      short loc_1400B01F7
0x1400b01d3  cmp     byte ptr [rcx+29h], 2
0x1400b01d7  jb      short loc_1400B01F7
0x1400b01d9  mov     rcx, [rcx+18h]
0x1400b01dd  mov     edx, 1BCh
0x1400b01e2  mov     dword ptr [rsp+0D8h+var_A8], r15d
0x1400b01e7  mov     r9, r14
0x1400b01ea  mov     dword ptr [rsp+0D8h+var_B0], esi
0x1400b01ee  mov     dword ptr [rsp+0D8h+var_B8], edi
0x1400b01f2  call    WPP_SF_iDDd
0x1400b01f7  mov     r8, [rsp+0D8h+var_70]
0x1400b01fc  mov     rdx, [rsp+0D8h+arg_18]
0x1400b0204  lea     rax, [r8+r8*2]
0x1400b0208  mov     rax, [rdx+rax*8+10h]
0x1400b020d  mov     dword ptr [rax+rsi*4], 0
0x1400b0214  test    ebp, ebp
0x1400b0216  cmovns  ebp, r15d
0x1400b021a  mov     r8, [rsp+0D8h+arg_0]
0x1400b0222  inc     esi
0x1400b0224  mov     [rsp+0D8h+var_88], 0
0x1400b0229  mov     r9, r14
0x1400b022c  mov     [rsp+0D8h+var_90], 0
0x1400b0231  mov     eax, ebx
0x1400b0233  mov     ecx, [r8+568h]
0x1400b023a  mov     [rsp+0D8h+var_98], rax
0x1400b023f  mov     rax, [r8+558h]
0x1400b0246  mov     r8d, r15d
0x1400b0249  mov     r15, [rsp+0D8h+arg_0]
0x1400b0251  mov     [rsp+0D8h+var_A0], rax
0x1400b0256  mov     [rsp+0D8h+var_A8], rcx
0x1400b025b  mov     edx, esi
0x1400b025d  mov     rcx, [r15]
0x1400b0260  mov     [rsp+0D8h+var_B0], rdx
0x1400b0265  lea     rdx, FVE_METADATA_LOGICAL_COPY_MATCH_FAIL
0x1400b026c  mov     eax, edi
0x1400b026e  mov     [rsp+0D8h+var_B8], rax
0x1400b0273  call    FveLogEventWithMetadataInfo
0x1400b0278  mov     r11, [rsp+0D8h+var_70]
0x1400b027d  mov     rbx, [rsp+0D8h+Source1]
0x1400b0282  cmp     esi, [r15+568h]
0x1400b0289  jb      loc_1400AFFE2
0x1400b028f  test    r13b, r13b
0x1400b0292  jz      loc_1400B0357
0x1400b0298  test    r12b, r12b
0x1400b029b  lea     rsi, WPP_GLOBAL_Control
0x1400b02a2  mov     r12d, 0C021001Fh
0x1400b02a8  jz      loc_1400B0364
0x1400b02ae  mov     r8, [rsp+0D8h+arg_10]
0x1400b02b6  bts     dword ptr [r8], 10h
0x1400b02bb  jmp     loc_1400B0364
0x1400b02c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b02c7  cmp     rcx, rsi
0x1400b02ca  jz      short loc_1400B0303
0x1400b02cc  mov     eax, [rcx+2Ch]
0x1400b02cf  test    al, 4
0x1400b02d1  jz      short loc_1400B0303
0x1400b02d3  cmp     byte ptr [rcx+29h], 2
0x1400b02d7  jb      short loc_1400B0303
0x1400b02d9  mov     rcx, [rcx+18h]
0x1400b02dd  mov     edx, 1B8h
0x1400b02e2  mov     dword ptr [rsp+0D8h+var_B0], 0
0x1400b02ea  mov     r9, r14
0x1400b02ed  mov     [rsp+0D8h+var_B8], r8
0x1400b02f2  lea     r8, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids
0x1400b02f9  call    WPP_SF_iiL
0x1400b02fe  mov     r11, [rsp+0D8h+var_70]
0x1400b0303  test    ebp, ebp
0x1400b0305  js      short loc_1400B0364
0x1400b0307  mov     ebp, r12d
0x1400b030a  jmp     short loc_1400B0364
0x1400b030c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b0313  cmp     rcx, rsi
0x1400b0316  jz      short loc_1400B034F
0x1400b0318  mov     eax, [rcx+2Ch]
0x1400b031b  test    al, 4
0x1400b031d  jz      short loc_1400B034F
0x1400b031f  cmp     byte ptr [rcx+29h], 2
0x1400b0323  jb      short loc_1400B034F
0x1400b0325  mov     rcx, [rcx+18h]
0x1400b0329  lea     r8, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids
0x1400b0330  mov     dword ptr [rsp+0D8h+var_B0], 0C0000095h
0x1400b0338  mov     edx, 1B7h
0x1400b033d  mov     [rsp+0D8h+var_B8], r9
0x1400b0342  mov     r9, r14
0x1400b0345  call    WPP_SF_iiL
0x1400b034a  mov     r11, [rsp+0D8h+var_70]
  ... truncated ...
```
