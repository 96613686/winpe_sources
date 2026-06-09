# RxFirstCanonicalize

- ea: `0x140053f50`
- end: `0x1400548dd`
- name: `RxFirstCanonicalize`
- size: `2445`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x140052bb0`
- `0x1400538b0`
- `0x140065830`

## callees

- `0x140014e40`
- `0x140016e20`
- `0x140017280`
- `0x140017370`
- `0x140017dcc`
- `0x140017e40`
- `0x140025c20`
- `0x140025d80`
- `0x140053f50`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400542c0`
- `ntoskrnl!ExAllocatePool2` at `0x1400542c0`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x1400540e2`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x1400540e2`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400543a8`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400545ff`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14005463d`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400546c8`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14007c666`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14007c688`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400543a8`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400545ff`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14005463d`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400546c8`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14007c666`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14007c688`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14005432e`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14005432e`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140054545`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140054557`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140054545`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140054557`
- `ntoskrnl!EtwActivityIdControl` at `0x14005459c`
- `ntoskrnl!EtwActivityIdControl` at `0x14005459c`
- `ntoskrnl!SeQuerySessionIdToken` at `0x1400540a2`
- `ntoskrnl!SeQuerySessionIdToken` at `0x1400540a2`

## pseudocode

```c
__int64 __fastcall RxFirstCanonicalize(__int64 a1, char *i, const UNICODE_STRING *a3, UNICODE_STRING *a4, char *a5)
{
  char *v5; // rax
  PCUNICODE_STRING v7; // rdi
  char *v9; // r12
  unsigned int v10; // ebx
  char v11; // r8
  NTSTATUS v12; // esi
  unsigned int Length; // eax
  char v14; // r14
  wchar_t *Buffer; // rcx
  __int64 v16; // r10
  char v17; // r9
  unsigned __int16 Data1; // r15
  wchar_t *v19; // rcx
  char v20; // al
  __int64 v21; // rax
  __int64 v22; // rax
  void *v23; // rcx
  ULONG v24; // ecx
  char *v25; // r8
  wchar_t *v26; // rax
  unsigned __int16 v27; // di
  unsigned __int16 v28; // r8
  UNICODE_STRING v29; // xmm0
  BOOLEAN v30; // r12
  unsigned __int16 v31; // ax
  unsigned __int16 v32; // r9
  char v33; // r11
  char *v34; // r8
  const UNICODE_STRING *v35; // r12
  char v36; // di
  __int64 Pool2; // rax
  __int64 v38; // rcx
  BOOLEAN v40; // al
  int v41; // edx
  int v42; // ebx
  wchar_t *v43; // rax
  _QWORD *v44; // rsi
  _WORD *v45; // rbx
  int v46; // ecx
  _WORD *v47; // rcx
  BOOLEAN v48; // [rsp+40h] [rbp-91h]
  char v49; // [rsp+41h] [rbp-90h]
  void *Src[2]; // [rsp+50h] [rbp-81h] BYREF
  PCUNICODE_STRING SourceString; // [rsp+60h] [rbp-71h]
  __int64 v52; // [rsp+68h] [rbp-69h]
  UNICODE_STRING String1; // [rsp+70h] [rbp-61h] BYREF
  ULONG SessionId[2]; // [rsp+80h] [rbp-51h] BYREF
  char *v55; // [rsp+88h] [rbp-49h]
  UNICODE_STRING String; // [rsp+90h] [rbp-41h] BYREF
  GUID ActivityId; // [rsp+A0h] [rbp-31h] BYREF
  char v58; // [rsp+B0h] [rbp-21h] BYREF

  SourceString = a3;
  v5 = i;
  v52 = a1;
  LODWORD(i) = a3->Length;
  v55 = a5;
  v7 = a3;
  ActivityId = 0;
  String1 = 0;
  *(_OWORD *)Src = 0;
  String = 0;
  if ( (unsigned int)i < 4 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_33191d0ffcd43ffb8501ed291b5a2f46_Traceguids, (unsigned int)i);
    }
    v12 = -1073741773;
    v14 = 4;
    goto LABEL_92;
  }
  v9 = (char *)*((_QWORD *)v5 + 23);
  v10 = 0;
  v11 = 0;
  a4->Length = 0;
  v12 = 0;
  Length = v7->Length;
  v14 = 0;
  v49 = 0;
  LOBYTE(i) = 4;
  if ( Length <= 0xA )
  {
    if ( Length < 4 )
    {
LABEL_99:
      v10 = v7->Length;
      *a5 = 4;
      *(_QWORD *)SessionId = *(_QWORD *)ActivityId.Data4;
LABEL_8:
      v16 = v52;
      v17 = 0;
      Data1 = ActivityId.Data1;
      v48 = 0;
      goto LABEL_49;
    }
  }
  else
  {
    Buffer = v7->Buffer;
    if ( *Buffer == 92 && Buffer[1] == 59 )
    {
      if ( Buffer[3] == 58 )
      {
        LOBYTE(i) = 0;
      }
      else
      {
        LODWORD(i) = 4;
        if ( Buffer[2] != 58 )
          LODWORD(i) = 3;
      }
      v10 = v7->Length;
      *(_QWORD *)SessionId = *(_QWORD *)ActivityId.Data4;
      *a5 = (char)i;
      goto LABEL_8;
    }
  }
  v19 = v7->Buffer;
  if ( *v19 != 92 )
    goto LABEL_99;
  LODWORD(i) = (_DWORD)v19 + 2;
  if ( v19[1] == 59 && (Length < 6 || v19[2] != 58) )
    goto LABEL_99;
  *(_WORD *)(a1 + 746) |= 1u;
  WORD1(Src[0]) = Length - 2;
  LOWORD(Src[0]) = Length - 2;
  Src[1] = v19 + 1;
  v20 = *v9;
  v48 = 0;
  SessionId[0] = 0;
  if ( v20 == 14 )
  {
    if ( *((_DWORD *)v9 + 6) == 1311123 )
    {
      v22 = *(_QWORD *)(**((_QWORD **)v9 + 4) + 8LL);
      goto LABEL_16;
    }
LABEL_104:
    v24 = 0;
    goto LABEL_21;
  }
  if ( v20 )
    goto LABEL_104;
  v21 = *((_QWORD *)v9 + 1);
  if ( !v21 )
    goto LABEL_104;
  v22 = *(_QWORD *)(v21 + 8);
LABEL_16:
  v23 = *(void **)(v22 + 32);
  if ( !v23 )
    v23 = *(void **)(v22 + 48);
  SeQuerySessionIdToken(v23, SessionId);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_b27d4ea20cf23c7ef3650225eec88b96_Traceguids, SessionId[0]);
  }
  v24 = SessionId[0];
LABEL_21:
  *(_DWORD *)&String.Length = 0x200000;
  String.Buffer = (wchar_t *)&v58;
  v14 = 76;
  v12 = RtlIntegerToUnicodeString(v24, 0xAu, &String);
  v25 = (char *)Src[1] + LOWORD(Src[0]);
  *(void **)SessionId = Src[1];
  for ( i = (char *)Src[1]; i != v25; i += 2 )
  {
    if ( *(_WORD *)i == 92 )
      break;
  }
  v26 = v7->Buffer;
  if ( v26[1] == 59 && v26[2] == 58 && i != v25 )
  {
    for ( i += 2; i != v25; i += 2 )
    {
      if ( *(_WORD *)i == 92 )
        break;
    }
  }
  v27 = (_WORD)i - LOWORD(Src[1]);
  v28 = (_WORD)v25 - (_WORD)i;
  Src[1] = i;
  LOWORD(Src[0]) = v28;
  Data1 = v27;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_33191d0ffcd43ffb8501ed291b5a2f46_Traceguids, Src);
    i = (char *)Src[1];
    v28 = (unsigned __int16)Src[0];
  }
  if ( !v27 )
  {
    v12 = -1073741767;
    v14 = 42;
    v17 = 0;
    v33 = 4;
LABEL_103:
    v7 = SourceString;
    v16 = v52;
    goto LABEL_47;
  }
  if ( v28 <= 2u )
  {
    if ( (*((_DWORD *)v9 + 4) & 0x80u) != 0 )
    {
      v17 = 1;
      LOWORD(Src[0]) = 0;
      Src[1] = 0;
      v33 = 1;
      v48 = 1;
      String1 = s_IpcShareName;
      v10 = v27 + (unsigned __int16)_mm_cvtsi128_si32((__m128i)s_IpcShareName) + 2;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_33191d0ffcd43ffb8501ed291b5a2f46_Traceguids);
      }
      v12 = -1073741767;
      v14 = 48;
      v17 = 0;
      v33 = 4;
    }
    goto LABEL_103;
  }
  v29 = *(UNICODE_STRING *)Src;
  String1 = *(UNICODE_STRING *)Src;
  if ( v28 == 10 || v28 > 0xAu && *((_WORD *)i + 5) == 92 )
  {
    String1.Length = 10;
    v40 = RtlEqualUnicodeString(&String1, &s_PipeShareName, 1u);
    v28 = (unsigned __int16)Src[0];
    v30 = v40;
    v48 = v40;
    if ( v40 )
    {
      v16 = v52;
      v28 = LOWORD(Src[0]) - 10;
      v33 = 1;
      Src[1] = (char *)Src[1] + 10;
      String1 = s_IpcShareName;
      LOWORD(Src[0]) -= 10;
      v32 = _mm_cvtsi128_si32((__m128i)s_IpcShareName);
      goto LABEL_73;
    }
    i = (char *)Src[1];
    v29 = *(UNICODE_STRING *)Src;
  }
  else
  {
    v30 = 0;
  }
  String1 = v29;
  if ( v28 != 10 && (v28 <= 0xAu || *((_WORD *)i + 5) != 92) )
  {
LABEL_36:
    String1 = v29;
    if ( v28 != 18 && (v28 <= 0x12u || *((_WORD *)i + 9) != 92) )
    {
LABEL_39:
      v31 = 1;
      v32 = String1.Length;
      v49 = 0;
      while ( 1 )
      {
        Data1 = v27;
        if ( v31 >= (unsigned __int16)(String1.Length >> 1) || (LODWORD(i) = String1.Buffer[v31], (_WORD)i == 92) )
        {
          v16 = v52;
          v33 = 4;
          goto LABEL_45;
        }
        if ( (_WORD)i == 58 )
          break;
        ++v31;
      }
      String1.Length = 2 * v31;
      if ( RtlEqualUnicodeString(&String1, &s_MailSlotShareName, 1u)
        || RtlEqualUnicodeString(&String1, &s_IpcShareName, 1u)
        || RtlEqualUnicodeString(&String1, &s_PipeShareName, 1u) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_Z(
            WPP_GLOBAL_Control->AttachedDevice,
            14,
            WPP_33191d0ffcd43ffb8501ed291b5a2f46_Traceguids,
            SourceString);
        }
        v12 = -1073741773;
        v14 = 0;
        goto LABEL_92;
      }
      v33 = 4;
      v32 = String1.Length;
      v16 = v52;
      v28 = LOWORD(Src[0]) - String1.Length;
      Src[1] = (char *)Src[1] + String1.Length;
      LOWORD(Src[0]) -= String1.Length;
      v49 = 1;
      v48 = 1;
      goto LABEL_73;
    }
    String1.Length = 18;
    v48 = RtlEqualUnicodeString(&String1, &s_MailSlotShareName, 1u);
    v30 = v48;
    if ( !v48 )
    {
      v28 = (unsigned __int16)Src[0];
      goto LABEL_39;
    }
    v16 = v52;
    v33 = 5;
    v47 = *(_WORD **)SessionId;
    *(_DWORD *)(v52 + 120) |= 0x400u;
    if ( v47[((unsigned __int64)v27 >> 1) - 1] == 42 && v27 == 2 )
    {
      v32 = String1.Length;
      v28 = LOWORD(Src[0]) - String1.Length;
      Src[1] = (char *)Src[1] + String1.Length;
      Data1 = s_PrimaryDomainName.Length;
      LOWORD(Src[0]) -= String1.Length;
      *(_QWORD *)SessionId = s_PrimaryDomainName.Buffer;
    }
    else
    {
      v32 = String1.Length;
      v30 = 0;
      v28 = (unsigned __int16)Src[0];
      v48 = 0;
    }
LABEL_45:
    if ( !v30 )
      goto LABEL_46;
LABEL_73:
    v7 = SourceString;
    v41 = v32;
    v17 = v48;
    LODWORD(i) = v28 + Data1 + v41;
    v42 = (_DWORD)i + 2;
    if ( !v49 )
      v42 = (int)i;
    v10 = v42 + 2;
    if ( (*(_DWORD *)(v16 + 120) & 0x400) != 0 )
      v10 += 8;
    goto LABEL_47;
  }
  String1.Length = 10;
  if ( !RtlEqualUnicodeString(&String1, &s_IpcShareName, 1u) )
  {
    i = (char *)Src[1];
    v28 = (unsigned __int16)Src[0];
    v29 = *(UNICODE_STRING *)Src;
    goto LABEL_36;
  }
  v16 = v52;
  v33 = 1;
LABEL_46:
  v7 = SourceString;
  v17 = v48;
  v10 = SourceString->Length;
LABEL_47:
  v34 = v55;
  *v55 = v33;
  if ( v12 )
  {
    v35 = SourceString;
    goto LABEL_67;
  }
  v11 = 1;
LABEL_49:
  if ( (*(_DWORD *)(v16 + 120) & 0x400) != 0 || !v11 || v7->Length < 6u || v7->Buffer[2] == 58 )
  {
    v35 = SourceString;
    v36 = 0;
    if ( !v17 && *SourceString->Buffer != 92 )
    {
      v12 = -1073741767;
      v14 = 103;
    }
  }
  else
  {
    v35 = SourceString;
    v36 = 1;
    if ( v17 )
      v10 += 6;
    else
      v10 += 6 + String.Length;
  }
  if ( v10 > 0xFFFF )
  {
    v12 = -1073741773;
    v14 = 113;
  }
  else if ( !v12 )
  {
    if ( v10 > 0xFFFE )
    {
      v12 = -1073741767;
      a4->Buffer = 0;
      v14 = 121;
    }
    else
    {
      Pool2 = ExAllocatePool2(258, v10, 843937874);
      a4->Buffer = (wchar_t *)Pool2;
      if ( Pool2 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_33191d0ffcd43ffb8501ed291b5a2f46_Traceguids, Pool2);
        }
        v38 = v52;
        *(_QWORD *)(v52 + 608) = a4->Buffer;
        a4->MaximumLength = v10;
        a4->Length = 0;
        if ( v48 )
        {
          v43 = a4->Buffer;
          a4->Length = v10;
          *v43 = 92;
          v44 = v43 + 1;
          if ( (*(_DWORD *)(v38 + 120) & 0x400) != 0 )
          {
            *v44 = *(_QWORD *)L";$:\\";
            v44 = v43 + 5;
          }
          else if ( v36 )
          {
            v44 = v43 + 4;
            a4->Buffer[1] = 59;
            a4->Buffer[2] = 58;
            a4->Buffer[3] = 92;
          }
          memmove(v44, *(const void **)SessionId, Data1);
          memmove((char *)v44 + Data1, String1.Buffer, String1.Length);
          v45 = (_WORD *)((char *)v44 + Data1 + String1.Length);
          if ( v49 )
            *v45++ = 92;
          LODWORD(i) = Src[1];
          if ( Src[1] )
            memmove(v45, Src[1], LOWORD(Src[0]));
          v14 = 121;
          a4->Length = LOWORD(Src[0]) + (_WORD)v45 - LOWORD(a4->Buffer);
          v12 = 0;
        }
        else
        {
          if ( v36 )
          {
            *a4->Buffer = 92;
            a4->Buffer[1] = 59;
            a4->Buffer[2] = 58;
            a4->Length = 6;
            RtlAppendUnicodeStringToString(a4, &String);
            RtlAppendUnicodeStringToString(a4, v35);
          }
          else
          {
            RtlCopyUnicodeString(a4, v35);
          }
          v14 = 121;
          v12 = 0;
        }
      }
      else
      {
        v12 = -1073741670;
        v14 = 121;
      }
    }
  }
  v34 = v55;
LABEL_67:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_LdZZ(WPP_GLOBAL_Control->AttachedDevice, (_DWORD)i, (_DWORD)v34, v12, *v34, (__int64)v35, (__int64)a4);
  }
  if ( v12 < 0 )
  {
LABEL_92:
    ActivityId = 0;
    EtwActivityIdControl(1u, &ActivityId);
    if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 1) != 0 )
      McTemplateK0qqq_EtwWriteTransfer(v46, (unsigned int)CanonicalizeError, (unsigned int)&ActivityId, v12, v14, 0);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140053f50  push    rbp
0x140053f52  push    rbx
0x140053f53  push    rsi
0x140053f54  push    rdi
0x140053f55  push    r12
0x140053f57  push    r13
0x140053f59  push    r14
0x140053f5b  push    r15
0x140053f5d  lea     rbp, [rsp-17h]
0x140053f62  sub     rsp, 0E8h
0x140053f69  mov     rax, cs:__security_cookie
0x140053f70  xor     rax, rsp
0x140053f73  mov     [rbp+4Fh+var_50], rax
0x140053f77  mov     r10, [rbp+4Fh+arg_20]
0x140053f7b  xorps   xmm0, xmm0
0x140053f7e  xorps   xmm1, xmm1
0x140053f81  mov     [rbp+4Fh+SourceString], r8
0x140053f85  mov     rax, rdx
0x140053f88  mov     [rbp+4Fh+var_B8], rcx
0x140053f8c  movzx   edx, word ptr [r8]
0x140053f90  mov     r13, r9
0x140053f93  mov     [rbp+4Fh+var_98], r10
0x140053f97  mov     rdi, r8
0x140053f9a  mov     r9, rcx
0x140053f9d  movups  xmmword ptr [rbp+4Fh+ActivityId.Data1], xmm0
0x140053fa1  movups  xmmword ptr [rbp+4Fh+String1.Length], xmm1
0x140053fa5  movups  xmmword ptr [rsp+120h+Src], xmm0
0x140053faa  movups  xmmword ptr [rbp+4Fh+String.Length], xmm1
0x140053fae  cmp     edx, 4
0x140053fb1  jb      loc_140054568
0x140053fb7  mov     r12, [rax+0B8h]
0x140053fbe  lea     r15, WPP_GLOBAL_Control
0x140053fc5  xor     ebx, ebx
0x140053fc7  xor     r8b, r8b
0x140053fca  mov     [r13+0], bx
0x140053fcf  mov     esi, ebx
0x140053fd1  movzx   eax, word ptr [rdi]
0x140053fd4  mov     r14d, ebx
0x140053fd7  mov     [rsp+120h+var_DF], bl
0x140053fdb  mov     dl, 4
0x140053fdd  cmp     eax, 0Ah
0x140053fe0  jbe     short loc_140054023
0x140053fe2  mov     rcx, [rdi+8]
0x140053fe6  cmp     word ptr [rcx], 5Ch ; '\'
0x140053fea  jnz     short loc_14005402C
0x140053fec  cmp     word ptr [rcx+2], 3Bh ; ';'
0x140053ff1  jnz     short loc_14005402C
0x140053ff3  cmp     word ptr [rcx+6], 3Ah ; ':'
0x140053ff8  jnz     loc_140054710
0x140053ffe  xor     dl, dl
0x140054000  mov     rcx, qword ptr [rbp+4Fh+ActivityId.Data4]
0x140054004  mov     ebx, eax
0x140054006  mov     qword ptr [rbp+4Fh+SessionId], rcx
0x14005400a  mov     [r10], dl
0x14005400d  mov     r10, [rbp+4Fh+var_B8]
0x140054011  xor     r9b, r9b
0x140054014  movzx   r15d, word ptr [rbp+4Fh+ActivityId.Data1]
0x140054019  mov     [rsp+120h+var_E0], r9b
0x14005401e  jmp     loc_14005424C
0x140054023  cmp     eax, 4
0x140054026  jb      loc_140054659
0x14005402c  mov     rcx, [rdi+8]
0x140054030  cmp     word ptr [rcx], 5Ch ; '\'
0x140054034  jnz     loc_140054659
0x14005403a  cmp     word ptr [rcx+2], 3Bh ; ';'
0x14005403f  lea     rdx, [rcx+2]
0x140054043  jz      loc_140054778
0x140054049  or      word ptr [r9+2EAh], 1
0x140054052  sub     ax, 2
0x140054056  mov     word ptr [rbp+4Fh+Src+2], ax
0x14005405a  mov     word ptr [rsp+120h+Src], ax
0x14005405f  mov     [rbp+4Fh+Src+8], rdx
0x140054063  movzx   eax, byte ptr [r12]
0x140054068  mov     [rsp+120h+var_E0], bl
0x14005406c  mov     [rbp+4Fh+SessionId], ebx
0x14005406f  cmp     al, 0Eh
0x140054071  jz      loc_1400544FD
0x140054077  test    al, al
0x140054079  jnz     loc_1400546AC
0x14005407f  mov     rax, [r12+8]
0x140054084  test    rax, rax
0x140054087  jz      loc_1400546AC
0x14005408d  mov     rax, [rax+8]
0x140054091  mov     rcx, [rax+20h]
0x140054095  test    rcx, rcx
0x140054098  jnz     short loc_14005409E
0x14005409a  mov     rcx, [rax+30h]; Token
0x14005409e  lea     rdx, [rbp+4Fh+SessionId]; SessionId
0x1400540a2  call    cs:__imp_SeQuerySessionIdToken
0x1400540a9  nop     dword ptr [rax+rax+00h]
0x1400540ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400540b5  cmp     rcx, r15
0x1400540b8  jz      short loc_1400540C7
0x1400540ba  test    dword ptr [rcx+2Ch], 1000h
0x1400540c1  jnz     loc_140054791
0x1400540c7  mov     ecx, [rbp+4Fh+SessionId]; Value
0x1400540ca  lea     rax, [rbp+4Fh+var_70]
0x1400540ce  mov     dword ptr [rbp+4Fh+String.Length], 200000h
0x1400540d5  lea     r8, [rbp+4Fh+String]; String
0x1400540d9  mov     [rbp+4Fh+String.Buffer], rax
0x1400540dd  mov     edx, 0Ah; Base
0x1400540e2  call    cs:__imp_RtlIntegerToUnicodeString
0x1400540e9  nop     dword ptr [rax+rax+00h]
0x1400540ee  mov     rcx, [rbp+4Fh+Src+8]
0x1400540f2  mov     r14d, 14Ch
0x1400540f8  movzx   r8d, word ptr [rsp+120h+Src]
0x1400540fe  mov     esi, eax
0x140054100  add     r8, rcx
0x140054103  mov     qword ptr [rbp+4Fh+SessionId], rcx
0x140054107  mov     rdx, rcx
0x14005410a  cmp     rcx, r8
0x14005410d  jz      short loc_14005411F
0x14005410f  nop
0x140054110  cmp     word ptr [rdx], 5Ch ; '\'
0x140054114  jz      short loc_14005411F
0x140054116  add     rdx, 2
0x14005411a  cmp     rdx, r8
0x14005411d  jnz     short loc_140054110
0x14005411f  mov     rax, [rdi+8]
0x140054123  cmp     word ptr [rax+2], 3Bh ; ';'
0x140054128  jz      loc_1400547B9
0x14005412e  movzx   edi, dx
0x140054131  sub     di, word ptr [rbp+4Fh+Src+8]
0x140054135  sub     r8w, dx
0x140054139  mov     [rbp+4Fh+Src+8], rdx
0x14005413d  mov     word ptr [rsp+120h+Src], r8w
0x140054143  movzx   r15d, di
0x140054147  mov     rcx, cs:WPP_GLOBAL_Control
0x14005414e  lea     r9, WPP_GLOBAL_Control
0x140054155  cmp     rcx, r9
0x140054158  jz      short loc_140054165
0x14005415a  mov     eax, [rcx+2Ch]
0x14005415d  test    al, 8
0x14005415f  jnz     loc_1400547DF
0x140054165  test    di, di
0x140054168  jz      loc_14005468E
0x14005416e  cmp     r8w, 2
0x140054173  jbe     loc_14007C6CB
0x140054179  movaps  xmm0, xmmword ptr [rsp+120h+Src]
0x14005417e  movdqa  xmmword ptr [rbp+4Fh+String1.Length], xmm0
0x140054183  cmp     r8w, 0Ah
0x140054188  jz      loc_140054391
0x14005418e  jbe     short loc_14005419B
0x140054190  cmp     word ptr [rdx+0Ah], 5Ch ; '\'
0x140054195  jz      loc_140054391
0x14005419b  xor     r12b, r12b
0x14005419e  movdqa  xmmword ptr [rbp+4Fh+String1.Length], xmm0
0x1400541a3  cmp     r8w, 0Ah
0x1400541a8  jz      loc_140054626
0x1400541ae  jbe     short loc_1400541BB
0x1400541b0  cmp     word ptr [rdx+0Ah], 5Ch ; '\'
0x1400541b5  jz      loc_140054626
0x1400541bb  movdqa  xmmword ptr [rbp+4Fh+String1.Length], xmm0
0x1400541c0  cmp     r8w, 12h
0x1400541c5  jz      loc_1400545E8
0x1400541cb  jbe     short loc_1400541D8
0x1400541cd  cmp     word ptr [rdx+12h], 5Ch ; '\'
0x1400541d2  jz      loc_1400545E8
0x1400541d8  mov     r10, [rbp+4Fh+String1.Buffer]
0x1400541dc  mov     eax, 1
0x1400541e1  movzx   r9d, [rbp+4Fh+String1.Length]
0x1400541e6  mov     [rsp+120h+var_DF], bl
0x1400541ea  nop     word ptr [rax+rax+00h]
0x1400541f0  movzx   ecx, r9w
0x1400541f4  movzx   r15d, di
0x1400541f8  shr     cx, 1
0x1400541fb  cmp     ax, cx
0x1400541fe  jnb     short loc_14005421D
0x140054200  movzx   ecx, ax
0x140054203  movzx   edx, word ptr [r10+rcx*2]
0x140054208  cmp     dx, 5Ch ; '\'
0x14005420c  jz      short loc_14005421D
0x14005420e  cmp     dx, 3Ah ; ':'
0x140054212  jz      loc_1400546B3
0x140054218  inc     ax
0x14005421b  jmp     short loc_1400541F0
0x14005421d  mov     r10, [rbp+4Fh+var_B8]
0x140054221  mov     r11b, 4
0x140054224  test    r12b, r12b
0x140054227  jnz     loc_1400543F5
0x14005422d  mov     rdi, [rbp+4Fh+SourceString]
0x140054231  movzx   r9d, [rsp+120h+var_E0]
0x140054237  movzx   ebx, word ptr [rdi]
0x14005423a  mov     r8, [rbp+4Fh+var_98]
0x14005423e  mov     [r8], r11b
0x140054241  test    esi, esi
0x140054243  jnz     loc_1400545DD
0x140054249  mov     r8b, 1
0x14005424c  test    dword ptr [r10+78h], 400h
0x140054254  jnz     short loc_140054283
0x140054256  test    r8b, r8b
0x140054259  jz      short loc_140054283
0x14005425b  cmp     word ptr [rdi], 6
0x14005425f  jb      short loc_140054283
0x140054261  mov     rax, [rdi+8]
0x140054265  cmp     word ptr [rax+4], 3Ah ; ':'
0x14005426a  jz      short loc_140054283
0x14005426c  mov     r12, [rbp+4Fh+SourceString]
0x140054270  mov     dil, 1
0x140054273  lea     eax, [rbx+6]
0x140054276  test    r9b, r9b
0x140054279  jz      loc_140054837
0x14005427f  mov     ebx, eax
0x140054281  jmp     short loc_140054293
0x140054283  mov     r12, [rbp+4Fh+SourceString]
0x140054287  xor     dil, dil
0x14005428a  test    r9b, r9b
0x14005428d  jz      loc_140054759
0x140054293  cmp     ebx, 0FFFFh
0x140054299  ja      loc_140054842
0x14005429f  test    esi, esi
0x1400542a1  jnz     loc_14005443E
0x1400542a7  cmp     ebx, 0FFFEh
0x1400542ad  ja      loc_140054852
0x1400542b3  mov     edx, ebx
0x1400542b5  mov     ecx, 102h
0x1400542ba  mov     r8d, 324D7852h
0x1400542c0  call    cs:__imp_ExAllocatePool2
0x1400542c7  nop     dword ptr [rax+rax+00h]
0x1400542cc  mov     [r13+8], rax
0x1400542d0  mov     r9, rax
0x1400542d3  test    rax, rax
0x1400542d6  jz      loc_140054433
0x1400542dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400542e3  lea     rax, WPP_GLOBAL_Control
0x1400542ea  cmp     rcx, rax
0x1400542ed  jz      short loc_1400542FA
0x1400542ef  mov     eax, [rcx+2Ch]
0x1400542f2  test    al, 2
0x1400542f4  jnz     loc_140054868
0x1400542fa  mov     rax, [r13+8]
0x1400542fe  mov     rcx, [rbp+4Fh+var_B8]
0x140054302  mov     [rcx+260h], rax
0x140054309  xor     eax, eax
0x14005430b  mov     [r13+2], bx
0x140054310  mov     [r13+0], ax
0x140054315  cmp     [rsp+120h+var_E0], al
0x140054319  jnz     loc_140054445
0x14005431f  mov     rcx, r13; Destination
0x140054322  test    dil, dil
0x140054325  jnz     loc_14005451D
0x14005432b  mov     rdx, r12; SourceString
0x14005432e  call    cs:__imp_RtlCopyUnicodeString
0x140054335  nop     dword ptr [rax+rax+00h]
0x14005433a  xor     ebx, ebx
0x14005433c  mov     r14d, 279h
0x140054342  mov     esi, ebx
0x140054344  mov     r8, [rbp+4Fh+var_98]
0x140054348  mov     rcx, cs:WPP_GLOBAL_Control
0x14005434f  lea     rax, WPP_GLOBAL_Control
0x140054356  cmp     rcx, rax
0x140054359  jz      short loc_140054366
0x14005435b  mov     eax, [rcx+2Ch]
0x14005435e  test    al, 8
0x140054360  jnz     loc_1400548B0
0x140054366  test    esi, esi
0x140054368  js      loc_14005458C
0x14005436e  mov     eax, esi
0x140054370  mov     rcx, [rbp+4Fh+var_50]
0x140054374  xor     rcx, rsp; StackCookie
0x140054377  call    __security_check_cookie
0x14005437c  add     rsp, 0E8h
0x140054383  pop     r15
0x140054385  pop     r14
0x140054387  pop     r13
0x140054389  pop     r12
0x14005438b  pop     rdi
0x14005438c  pop     rsi
0x14005438d  pop     rbx
0x14005438e  pop     rbp
0x14005438f  retn
0x140054391  mov     eax, 0Ah
0x140054396  lea     rdx, s_PipeShareName; String2
0x14005439d  mov     r8b, 1; CaseInSensitive
0x1400543a0  mov     [rbp+4Fh+String1.Length], ax
0x1400543a4  lea     rcx, [rbp+4Fh+String1]; String1
0x1400543a8  call    cs:__imp_RtlEqualUnicodeString
0x1400543af  nop     dword ptr [rax+rax+00h]
0x1400543b4  movzx   r8d, word ptr [rsp+120h+Src]
0x1400543ba  movzx   r12d, al
0x1400543be  mov     [rsp+120h+var_E0], al
0x1400543c2  test    al, al
0x1400543c4  jz      loc_14005466C
0x1400543ca  movups  xmm0, xmmword ptr cs:s_IpcShareName.Length
0x1400543d1  mov     r10, [rbp+4Fh+var_B8]
0x1400543d5  mov     eax, 0FFF6h
0x1400543da  add     r8w, ax
0x1400543de  mov     r11b, 1
0x1400543e1  add     [rbp+4Fh+Src+8], 0Ah
0x1400543e6  movaps  xmmword ptr [rbp+4Fh+String1.Length], xmm0
0x1400543ea  mov     word ptr [rsp+120h+Src], r8w
0x1400543f0  movd    r9d, xmm0
0x1400543f5  mov     rdi, [rbp+4Fh+SourceString]
0x1400543f9  movzx   edx, r9w
0x1400543fd  movzx   r9d, [rsp+120h+var_E0]
0x140054403  movzx   eax, r15w
0x140054407  add     edx, eax
0x140054409  movzx   eax, r8w
0x14005440d  add     edx, eax
0x14005440f  cmp     [rsp+120h+var_DF], 0
  ... truncated ...
```
