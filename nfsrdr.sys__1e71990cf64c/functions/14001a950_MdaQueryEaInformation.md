# MdaQueryEaInformation

- ea: `0x14001a950`
- end: `0x14001ad78`
- name: `MdaQueryEaInformation`
- size: `1064`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path`

## callees

- `0x1400029d0`
- `0x1400132cc`
- `0x140018310`
- `0x14001a950`
- `0x14001db18`
- `0x140027d74`
- `0x14003aba0`
- `0x14003adc0`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14001ace2`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001ace2`

## string_xrefs

- `0x14001aa26`: `NfsSymlinkTargetName`
- `0x14001abd3`: `NfsSymlinkTargetName`

## pseudocode

```c
__int64 __fastcall MdaQueryEaInformation(__int64 a1)
{
  __int64 v2; // rbx
  __int64 v3; // r14
  unsigned int v4; // r15d
  __int64 v5; // rdi
  __int64 v6; // r12
  __int64 v7; // rdx
  __int64 v8; // rcx
  int EAName; // ebx
  int v10; // r14d
  unsigned int v11; // r13d
  unsigned int v12; // ebx
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  int Attributes; // eax
  __int64 v17; // rax
  __int64 v18; // r12
  unsigned int v19; // r13d
  __int64 v20; // r8
  __int64 v21; // rcx
  unsigned int v22; // ecx
  USHORT MaximumLength; // ax
  USHORT v24; // r15
  struct _UNICODE_STRING UnicodeString; // [rsp+30h] [rbp-48h] BYREF
  __int64 v27; // [rsp+40h] [rbp-38h]
  __int64 v28; // [rsp+48h] [rbp-30h]
  char v29[24]; // [rsp+50h] [rbp-28h] BYREF

  v2 = *(_QWORD *)(a1 + 56);
  v3 = *(_QWORD *)(a1 + 64);
  v4 = *(_DWORD *)(a1 + 472);
  strcpy(v29, "MdaQueryEaInformation");
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids, v29);
  v5 = *(_QWORD *)(a1 + 456);
  if ( !v5 || v4 < 0xC )
  {
    v12 = -1073741583;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v12;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_38;
    v14 = 51;
    goto LABEL_37;
  }
  v6 = *(_QWORD *)(v2 + 136);
  v7 = *(unsigned int *)(a1 + 520);
  v8 = *(_QWORD *)(a1 + 512);
  v27 = *(_QWORD *)(*(_QWORD *)(v3 + 32) + 40LL);
  v28 = v6;
  EAName = MdaFindEAName(v8, v7, "NfsV3Attributes");
  v10 = MdaFindEAName(*(_QWORD *)(a1 + 512), *(unsigned int *)(a1 + 520), "NfsSymlinkTargetName");
  *(_QWORD *)v5 = 0;
  if ( EAName )
  {
    v12 = -1073741275;
    v11 = 0;
    goto LABEL_17;
  }
  v11 = 112;
  if ( v4 >= 0x70 )
  {
    v15 = v27;
    *(_BYTE *)(v5 + 5) = 15;
    strcpy((char *)(v5 + 8), "NfsV3Attributes");
    Attributes = NfsGetAttributes(v15, a1, *(_QWORD *)(v6 + 8));
    v12 = Attributes;
    if ( Attributes >= 0 )
    {
      v17 = *(_QWORD *)(v6 + 8);
      *(_OWORD *)(v5 + 24) = *(_OWORD *)(v17 + 128);
      *(_OWORD *)(v5 + 40) = *(_OWORD *)(v17 + 144);
      *(_OWORD *)(v5 + 56) = *(_OWORD *)(v17 + 160);
      *(_OWORD *)(v5 + 72) = *(_OWORD *)(v17 + 176);
      *(_OWORD *)(v5 + 88) = *(_OWORD *)(v17 + 192);
      *(_QWORD *)(v5 + 104) = *(_QWORD *)(v17 + 208);
      *(_WORD *)(v5 + 6) = 88;
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      WPP_SF_sD(
        WPP_GLOBAL_Control->AttachedDevice,
        53,
        (unsigned int)WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids,
        (unsigned int)v29,
        Attributes);
    }
LABEL_17:
    if ( !v10 )
    {
      v18 = v11;
      *(_DWORD *)v5 = v11;
      *(_QWORD *)&UnicodeString.Length = 0;
      v19 = v11 + 29;
      UnicodeString.Buffer = 0;
      *(_WORD *)(v18 + v5 + 6) = 0;
      *(_BYTE *)(v18 + v5 + 4) = 0;
      *(_DWORD *)(v18 + v5) = 0;
      if ( v4 < v19 )
      {
        *(_DWORD *)(a1 + 176) = -1073741789;
        *(_QWORD *)(a1 + 184) = v19 + 260;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids, v29);
      }
      v20 = v28;
      v21 = v27;
      strcpy((char *)(v18 + v5 + 8), "NfsSymlinkTargetName");
      *(_BYTE *)(v18 + v5 + 5) = 20;
      v12 = NfsReadlink(v21, a1, *(_QWORD *)(v20 + 8), &UnicodeString);
      if ( (v12 & 0x80000000) == 0 )
      {
        v22 = (v19 + UnicodeString.Length + 5) & 0xFFFFFFFC;
        if ( v4 >= v22 )
        {
          MaximumLength = UnicodeString.MaximumLength;
          v24 = v4 - v22;
          if ( UnicodeString.MaximumLength >= v24 )
            MaximumLength = v24;
          *(_WORD *)(v18 + v5 + 6) = MaximumLength;
          memmove((void *)(v18 + v5 + 29), UnicodeString.Buffer, MaximumLength);
        }
        else
        {
          v12 = -1073741789;
          *(_QWORD *)(a1 + 184) = v22;
          *(_DWORD *)(a1 + 176) = -1073741789;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 56, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids, v29);
          }
        }
        RtlFreeUnicodeString(&UnicodeString);
      }
      else
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          return v12;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_sD(
            WPP_GLOBAL_Control->AttachedDevice,
            55,
            (unsigned int)WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids,
            (unsigned int)v29,
            v12);
      }
    }
    goto LABEL_38;
  }
  *(_QWORD *)(a1 + 184) = 112;
  v12 = -1073741789;
  *(_DWORD *)(a1 + 176) = -1073741789;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    return v12;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v14 = 52;
LABEL_37:
    WPP_SF_s(v13->AttachedDevice, v14, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids, v29);
  }
LABEL_38:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_sD(
      WPP_GLOBAL_Control->AttachedDevice,
      57,
      (unsigned int)WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids,
      (unsigned int)v29,
      v12);
  return v12;
}

```

## disassembly

```asm
0x14001a950  push    rbp
0x14001a952  push    rbx
0x14001a953  push    rsi
0x14001a954  push    rdi
0x14001a955  push    r12
0x14001a957  push    r13
0x14001a959  push    r14
0x14001a95b  push    r15
0x14001a95d  mov     rbp, rsp
0x14001a960  sub     rsp, 78h
0x14001a964  mov     rax, cs:__security_cookie
0x14001a96b  xor     rax, rsp
0x14001a96e  mov     [rbp+var_10], rax
0x14001a972  movups  xmm0, xmmword ptr cs:aMdaqueryeainfo; "MdaQueryEaInformation"
0x14001a979  mov     rsi, rcx
0x14001a97c  mov     rbx, [rcx+38h]
0x14001a980  movsd   xmm1, qword ptr cs:aMdaqueryeainfo+0Eh; "rmation"
0x14001a988  mov     r14, [rcx+40h]
0x14001a98c  mov     r15d, [rcx+1D8h]
0x14001a993  movups  xmmword ptr [rbp+var_28], xmm0
0x14001a997  movsd   qword ptr [rbp+var_28+0Eh], xmm1
0x14001a99c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a9a3  lea     rax, WPP_GLOBAL_Control
0x14001a9aa  cmp     rcx, rax
0x14001a9ad  jz      short loc_14001A9D6
0x14001a9af  mov     eax, [rcx+2Ch]
0x14001a9b2  test    al, 8
0x14001a9b4  jz      short loc_14001A9CF
0x14001a9b6  mov     rcx, [rcx+18h]
0x14001a9ba  lea     r9, [rbp+var_28]
0x14001a9be  mov     edx, 32h ; '2'
0x14001a9c3  lea     r8, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids
0x14001a9ca  call    WPP_SF_s
0x14001a9cf  lea     rax, WPP_GLOBAL_Control
0x14001a9d6  mov     rdi, [rsi+1C8h]
0x14001a9dd  test    rdi, rdi
0x14001a9e0  jz      loc_14001ACF0
0x14001a9e6  cmp     r15d, 0Ch
0x14001a9ea  jb      loc_14001ACF0
0x14001a9f0  mov     rax, [r14+20h]
0x14001a9f4  lea     r8, aNfsv3attribute; "NfsV3Attributes"
0x14001a9fb  mov     r12, [rbx+88h]
0x14001aa02  mov     edx, [rsi+208h]
0x14001aa08  mov     rcx, [rsi+200h]
0x14001aa0f  mov     rax, [rax+28h]
0x14001aa13  mov     [rbp+var_38], rax
0x14001aa17  mov     [rbp+var_30], r12
0x14001aa1b  call    MdaFindEAName
0x14001aa20  mov     edx, [rsi+208h]
0x14001aa26  lea     r8, aNfssymlinktarg; "NfsSymlinkTargetName"
0x14001aa2d  mov     rcx, [rsi+200h]
0x14001aa34  mov     ebx, eax
0x14001aa36  call    MdaFindEAName
0x14001aa3b  xor     ecx, ecx
0x14001aa3d  mov     r14d, eax
0x14001aa40  mov     [rdi], rcx
0x14001aa43  test    ebx, ebx
0x14001aa45  jnz     loc_14001AB4C
0x14001aa4b  lea     r13d, [rcx+70h]
0x14001aa4f  cmp     r15d, r13d
0x14001aa52  jnb     short loc_14001AA96
0x14001aa54  mov     r14d, 0C0000023h
0x14001aa5a  mov     [rsi+0B8h], r13
0x14001aa61  mov     ebx, r14d
0x14001aa64  mov     [rsi+0B0h], r14d
0x14001aa6b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001aa72  lea     rax, WPP_GLOBAL_Control
0x14001aa79  cmp     rcx, rax
0x14001aa7c  jz      loc_14001AD58
0x14001aa82  mov     eax, [rcx+2Ch]
0x14001aa85  test    al, 1
0x14001aa87  jz      loc_14001AD21
0x14001aa8d  lea     edx, [r13-3Ch]
0x14001aa91  jmp     loc_14001AD0D
0x14001aa96  movups  xmm0, xmmword ptr cs:aNfsv3attribute; "NfsV3Attributes"
0x14001aa9d  mov     rcx, [rbp+var_38]
0x14001aaa1  mov     rdx, rsi
0x14001aaa4  mov     byte ptr [rdi+5], 0Fh
0x14001aaa8  movdqu  xmmword ptr [rdi+8], xmm0
0x14001aaad  mov     r8, [r12+8]
0x14001aab2  call    NfsGetAttributes
0x14001aab7  mov     ebx, eax
0x14001aab9  test    eax, eax
0x14001aabb  jns     short loc_14001AAFB
0x14001aabd  mov     rcx, cs:WPP_GLOBAL_Control
0x14001aac4  lea     rdx, WPP_GLOBAL_Control
0x14001aacb  cmp     rcx, rdx
0x14001aace  jz      loc_14001AB5B
0x14001aad4  mov     edx, [rcx+2Ch]
0x14001aad7  test    dl, 1
0x14001aada  jz      short loc_14001AB54
0x14001aadc  mov     rcx, [rcx+18h]
0x14001aae0  lea     r9, [rbp+var_28]
0x14001aae4  mov     edx, 35h ; '5'
0x14001aae9  mov     [rsp+78h+var_58], eax
0x14001aaed  lea     r8, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids
0x14001aaf4  call    WPP_SF_sD
0x14001aaf9  jmp     short loc_14001AB54
0x14001aafb  mov     rax, [r12+8]
0x14001ab00  movups  xmm0, xmmword ptr [rax+80h]
0x14001ab07  movups  xmmword ptr [rdi+18h], xmm0
0x14001ab0b  movups  xmm1, xmmword ptr [rax+90h]
0x14001ab12  movups  xmmword ptr [rdi+28h], xmm1
0x14001ab16  movups  xmm0, xmmword ptr [rax+0A0h]
0x14001ab1d  movups  xmmword ptr [rdi+38h], xmm0
0x14001ab21  movups  xmm1, xmmword ptr [rax+0B0h]
0x14001ab28  movups  xmmword ptr [rdi+48h], xmm1
0x14001ab2c  movups  xmm0, xmmword ptr [rax+0C0h]
0x14001ab33  movups  xmmword ptr [rdi+58h], xmm0
0x14001ab37  movsd   xmm1, qword ptr [rax+0D0h]
0x14001ab3f  movsd   qword ptr [rdi+68h], xmm1
0x14001ab44  mov     word ptr [rdi+6], 58h ; 'X'
0x14001ab4a  jmp     short loc_14001AB54
0x14001ab4c  mov     ebx, 0C0000225h
0x14001ab51  xor     r13d, r13d
0x14001ab54  lea     rdx, WPP_GLOBAL_Control
0x14001ab5b  test    r14d, r14d
0x14001ab5e  jnz     loc_14001AD21
0x14001ab64  xor     eax, eax
0x14001ab66  mov     r12d, r13d
0x14001ab69  mov     [rdi], r13d
0x14001ab6c  mov     r14d, 0C0000023h
0x14001ab72  mov     qword ptr [rbp+UnicodeString.Length], rax
0x14001ab76  add     r13d, 1Dh
0x14001ab7a  mov     [rbp+UnicodeString.Buffer], rax
0x14001ab7e  mov     [r12+rdi+6], ax
0x14001ab84  mov     [r12+rdi+4], al
0x14001ab89  mov     [r12+rdi], eax
0x14001ab8d  cmp     r15d, r13d
0x14001ab90  jnb     short loc_14001ABD3
0x14001ab92  lea     ecx, [r13+104h]
0x14001ab99  mov     [rsi+0B0h], r14d
0x14001aba0  mov     [rsi+0B8h], rcx
0x14001aba7  mov     rcx, cs:WPP_GLOBAL_Control
0x14001abae  cmp     rcx, rdx
0x14001abb1  jz      short loc_14001ABD3
0x14001abb3  mov     eax, [rcx+2Ch]
0x14001abb6  test    al, 1
0x14001abb8  jz      short loc_14001ABD3
0x14001abba  mov     rcx, [rcx+18h]
0x14001abbe  lea     r9, [rbp+var_28]
0x14001abc2  mov     edx, 36h ; '6'
0x14001abc7  lea     r8, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids
0x14001abce  call    WPP_SF_s
0x14001abd3  movups  xmm0, xmmword ptr cs:aNfssymlinktarg; "NfsSymlinkTargetName"
0x14001abda  mov     r8, [rbp+var_30]
0x14001abde  lea     r9, [rbp+UnicodeString]
0x14001abe2  mov     rcx, [rbp+var_38]
0x14001abe6  mov     rdx, rsi
0x14001abe9  movups  xmmword ptr [r12+rdi+8], xmm0
0x14001abef  movsd   xmm1, qword ptr cs:aNfssymlinktarg+0Dh; "getName"
0x14001abf7  movsd   qword ptr [r12+rdi+15h], xmm1
0x14001abfe  mov     byte ptr [r12+rdi+5], 14h
0x14001ac04  mov     r8, [r8+8]
0x14001ac08  call    NfsReadlink
0x14001ac0d  mov     ebx, eax
0x14001ac0f  test    eax, eax
0x14001ac11  jns     short loc_14001AC57
0x14001ac13  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ac1a  lea     rax, WPP_GLOBAL_Control
0x14001ac21  cmp     rcx, rax
0x14001ac24  jz      loc_14001AD58
0x14001ac2a  mov     eax, [rcx+2Ch]
0x14001ac2d  test    al, 1
0x14001ac2f  jz      loc_14001AD21
0x14001ac35  mov     rcx, [rcx+18h]
0x14001ac39  lea     r9, [rbp+var_28]
0x14001ac3d  mov     edx, 37h ; '7'
0x14001ac42  mov     [rsp+78h+var_58], ebx
0x14001ac46  lea     r8, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids
0x14001ac4d  call    WPP_SF_sD
0x14001ac52  jmp     loc_14001AD21
0x14001ac57  movzx   ecx, [rbp+UnicodeString.Length]
0x14001ac5b  add     ecx, 5
0x14001ac5e  add     ecx, r13d
0x14001ac61  and     ecx, 0FFFFFFFCh
0x14001ac64  cmp     r15d, ecx
0x14001ac67  jnb     short loc_14001ACB1
0x14001ac69  mov     eax, ecx
0x14001ac6b  mov     ebx, r14d
0x14001ac6e  mov     [rsi+0B8h], rax
0x14001ac75  mov     [rsi+0B0h], r14d
0x14001ac7c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ac83  lea     rax, WPP_GLOBAL_Control
0x14001ac8a  cmp     rcx, rax
0x14001ac8d  jz      short loc_14001ACDE
0x14001ac8f  mov     eax, [rcx+2Ch]
0x14001ac92  test    al, 1
0x14001ac94  jz      short loc_14001ACDE
0x14001ac96  mov     rcx, [rcx+18h]
0x14001ac9a  lea     r9, [rbp+var_28]
0x14001ac9e  mov     edx, 38h ; '8'
0x14001aca3  lea     r8, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids
0x14001acaa  call    WPP_SF_s
0x14001acaf  jmp     short loc_14001ACDE
0x14001acb1  movzx   eax, [rbp+UnicodeString.MaximumLength]
0x14001acb5  sub     r15w, cx
0x14001acb9  cmp     [rbp+UnicodeString.MaximumLength], r15w
0x14001acbe  jb      short loc_14001ACC4
0x14001acc0  movzx   eax, r15w
0x14001acc4  movzx   r8d, ax; Size
0x14001acc8  lea     rcx, [rdi+1Dh]
0x14001accc  mov     [r12+rdi+6], r8w
0x14001acd2  add     rcx, r12; void *
0x14001acd5  mov     rdx, [rbp+UnicodeString.Buffer]; Src
0x14001acd9  call    memmove
0x14001acde  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14001ace2  call    cs:__imp_RtlFreeUnicodeString
0x14001ace9  nop     dword ptr [rax+rax+00h]
0x14001acee  jmp     short loc_14001AD21
0x14001acf0  mov     ebx, 0C00000F1h
0x14001acf5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001acfc  cmp     rcx, rax
0x14001acff  jz      short loc_14001AD58
0x14001ad01  mov     eax, [rcx+2Ch]
0x14001ad04  test    al, 1
0x14001ad06  jz      short loc_14001AD21
0x14001ad08  mov     edx, 33h ; '3'
0x14001ad0d  mov     rcx, [rcx+18h]
0x14001ad11  lea     r9, [rbp+var_28]
0x14001ad15  lea     r8, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids
0x14001ad1c  call    WPP_SF_s
0x14001ad21  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ad28  lea     rax, WPP_GLOBAL_Control
0x14001ad2f  cmp     rcx, rax
0x14001ad32  jz      short loc_14001AD58
0x14001ad34  mov     eax, [rcx+2Ch]
0x14001ad37  test    al, 8
0x14001ad39  jz      short loc_14001AD58
0x14001ad3b  mov     rcx, [rcx+18h]
0x14001ad3f  lea     r9, [rbp+var_28]
0x14001ad43  mov     edx, 39h ; '9'
0x14001ad48  mov     [rsp+78h+var_58], ebx
0x14001ad4c  lea     r8, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids
0x14001ad53  call    WPP_SF_sD
0x14001ad58  mov     eax, ebx
0x14001ad5a  mov     rcx, [rbp+var_10]
0x14001ad5e  xor     rcx, rsp; StackCookie
0x14001ad61  call    __security_check_cookie
0x14001ad66  add     rsp, 78h
0x14001ad6a  pop     r15
0x14001ad6c  pop     r14
0x14001ad6e  pop     r13
0x14001ad70  pop     r12
0x14001ad72  pop     rdi
0x14001ad73  pop     rsi
0x14001ad74  pop     rbx
0x14001ad75  pop     rbp
0x14001ad76  retn
```
