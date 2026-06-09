# EventWriteScrubDataOutput(_SCRUB_ENVIRONMENT *,_SCRUB_VOLUME_IDENTIFIER const *,_UNICODE_STRING const *,_SCRUB_DATA_TYPE,_SCRUB_DATA_OUTPUT const *,uchar)

- ea: `0x18000ad94`
- end: `0x18000b6b3`
- name: `?EventWriteScrubDataOutput@@YAXPEAU_SCRUB_ENVIRONMENT@@PEBU_SCRUB_VOLUME_IDENTIFIER@@PEBU_UNICODE_STRING@@W4_SCRUB_DATA_TYPE@@PEBU_SCRUB_DATA_OUTPUT@@E@Z`
- size: `2335`
- prototype: `char __fastcall(__int64, __int64, __int64, int, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180022450`

## callees

- `0x180001354`
- `0x18000166c`
- `0x18000ad94`
- `0x180011ba0`

## pseudocode

```c
char __fastcall EventWriteScrubDataOutput(__int64 a1, __int64 a2, __int64 a3, int a4, __int64 a5, char a6)
{
  __int64 v6; // rbx
  __int64 v11; // rcx
  char result; // al
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  char *v19; // rdx
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // [rsp+68h] [rbp-9h] BYREF
  __int64 v24; // [rsp+70h] [rbp-1h] BYREF
  __int64 v25; // [rsp+78h] [rbp+7h] BYREF
  __int64 v26; // [rsp+80h] [rbp+Fh] BYREF
  __int64 v27; // [rsp+88h] [rbp+17h] BYREF
  __int64 v28[5]; // [rsp+90h] [rbp+1Fh] BYREF

  v6 = a5;
  v11 = *(_QWORD *)(a5 + 40);
  if ( v11 )
  {
    if ( a4 == 1 )
    {
      if ( !*(_DWORD *)(a1 + 8) )
      {
        if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 2) != 0 )
          McTemplateU0hzr0iiiiidj_EventWriteTransfer(
            v11,
            (unsigned int)DISCAN_EVENT_VOLUME_DATA_CORRUPTION_NOT_REPAIRED,
            *(_WORD *)a3 >> 1,
            *(_QWORD *)(a3 + 8),
            *(_QWORD *)(a5 + 48),
            *(_QWORD *)(a5 + 16),
            *(_QWORD *)(a5 + 24),
            *(_QWORD *)(a5 + 32),
            v11,
            *(_DWORD *)(a5 + 8),
            *(_QWORD *)(a2 + 24));
        result = dword_1800470B8;
        if ( (unsigned int)dword_1800470B8 > 5 )
        {
          result = tlgKeywordOn(v11, a2, a3);
          if ( result )
          {
            v23 = *(_QWORD *)(v6 + 24);
            v24 = *(_QWORD *)(v6 + 16);
            LODWORD(a5) = *(_DWORD *)(v6 + 8);
            v25 = *(_QWORD *)(v6 + 40);
            v26 = *(_QWORD *)(v6 + 32);
            v27 = *(_QWORD *)(a2 + 24);
            v28[0] = a1 + 52;
            return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                     v13,
                     (__int64)byte_180040825,
                     v14,
                     v15,
                     v28,
                     &v27,
                     (__int64)&v26,
                     (__int64)&v25,
                     (__int64)&a5,
                     (__int64)&v24,
                     (__int64)&v23);
          }
        }
        return result;
      }
      if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 0x10) != 0 )
        McTemplateU0hzr0iiiiidj_EventWriteTransfer(
          v11,
          (unsigned int)DISCANCR_EVENT_VOLUME_DATA_CORRUPTION_NOT_REPAIRED,
          *(_WORD *)a3 >> 1,
          *(_QWORD *)(a3 + 8),
          *(_QWORD *)(a5 + 48),
          *(_QWORD *)(a5 + 16),
          *(_QWORD *)(a5 + 24),
          *(_QWORD *)(a5 + 32),
          v11,
          *(_DWORD *)(a5 + 8),
          *(_QWORD *)(a2 + 24));
      result = dword_1800470B8;
      if ( (unsigned int)dword_1800470B8 > 5 )
      {
        result = tlgKeywordOn(v11, a2, a3);
        if ( result )
        {
          v19 = byte_180040773;
LABEL_92:
          v28[0] = *(_QWORD *)(v6 + 24);
          v27 = *(_QWORD *)(v6 + 16);
          LODWORD(a5) = *(_DWORD *)(v6 + 8);
          v26 = *(_QWORD *)(v6 + 40);
          v25 = *(_QWORD *)(v6 + 32);
          v24 = *(_QWORD *)(a2 + 24);
          v23 = a1 + 52;
          return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                   v16,
                   (__int64)v19,
                   v17,
                   v18,
                   &v23,
                   &v24,
                   (__int64)&v25,
                   (__int64)&v26,
                   (__int64)&a5,
                   (__int64)&v27,
                   (__int64)v28);
        }
      }
    }
    else
    {
      v20 = *(_DWORD *)(a1 + 8);
      if ( (*(_DWORD *)(a5 + 4) & 0x10000) != 0 )
      {
        if ( v20 )
        {
          if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 0x10) != 0 )
            McTemplateU0hzr0iiiiidj_EventWriteTransfer(
              v11,
              (unsigned int)DISCANCR_EVENT_NON_USER_DATA_CORRUPTION_NOT_REPAIRED,
              *(_WORD *)a3 >> 1,
              *(_QWORD *)(a3 + 8),
              *(_QWORD *)(a5 + 48),
              *(_QWORD *)(a5 + 16),
              *(_QWORD *)(a5 + 24),
              *(_QWORD *)(a5 + 32),
              v11,
              *(_DWORD *)(a5 + 8),
              *(_QWORD *)(a2 + 24));
          result = dword_1800470B8;
          if ( (unsigned int)dword_1800470B8 > 5 )
          {
            result = tlgKeywordOn(v11, a2, a3);
            if ( result )
            {
              v19 = &byte_18004060F;
              goto LABEL_92;
            }
          }
        }
        else
        {
          if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 2) != 0 )
            McTemplateU0hzr0iiiiidj_EventWriteTransfer(
              v11,
              (unsigned int)DISCAN_EVENT_NON_USER_DATA_CORRUPTION_NOT_REPAIRED,
              *(_WORD *)a3 >> 1,
              *(_QWORD *)(a3 + 8),
              *(_QWORD *)(a5 + 48),
              *(_QWORD *)(a5 + 16),
              *(_QWORD *)(a5 + 24),
              *(_QWORD *)(a5 + 32),
              v11,
              *(_DWORD *)(a5 + 8),
              *(_QWORD *)(a2 + 24));
          result = dword_1800470B8;
          if ( (unsigned int)dword_1800470B8 > 5 )
          {
            result = tlgKeywordOn(v11, a2, a3);
            if ( result )
            {
              v19 = (char *)word_1800406C2;
              goto LABEL_92;
            }
          }
        }
      }
      else if ( v20 )
      {
        if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 0x10) != 0 )
          McTemplateU0hzr0iiiiidj_EventWriteTransfer(
            v11,
            (unsigned int)DISCANCR_EVENT_CORRUPTION_NOT_REPAIRED,
            *(_WORD *)a3 >> 1,
            *(_QWORD *)(a3 + 8),
            *(_QWORD *)(a5 + 48),
            *(_QWORD *)(a5 + 16),
            *(_QWORD *)(a5 + 24),
            *(_QWORD *)(a5 + 32),
            v11,
            *(_DWORD *)(a5 + 8),
            *(_QWORD *)(a2 + 24));
        result = dword_1800470B8;
        if ( (unsigned int)dword_1800470B8 > 5 )
        {
          result = tlgKeywordOn(v11, a2, a3);
          if ( result )
          {
            v19 = byte_1800404C1;
            goto LABEL_92;
          }
        }
      }
      else
      {
        if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 2) != 0 )
          McTemplateU0hzr0iiiiidj_EventWriteTransfer(
            v11,
            (unsigned int)DISCAN_EVENT_CORRUPTION_NOT_REPAIRED,
            *(_WORD *)a3 >> 1,
            *(_QWORD *)(a3 + 8),
            *(_QWORD *)(a5 + 48),
            *(_QWORD *)(a5 + 16),
            *(_QWORD *)(a5 + 24),
            *(_QWORD *)(a5 + 32),
            v11,
            *(_DWORD *)(a5 + 8),
            *(_QWORD *)(a2 + 24));
        result = dword_1800470B8;
        if ( (unsigned int)dword_1800470B8 > 5 )
        {
          result = tlgKeywordOn(v11, a2, a3);
          if ( result )
          {
            v19 = byte_180040569;
            goto LABEL_92;
          }
        }
      }
    }
  }
  else
  {
    v21 = *(_QWORD *)(a5 + 32);
    result = a6;
    if ( !v21 && !a6 )
      return result;
    if ( a4 == 1 )
    {
      if ( *(_DWORD *)(a1 + 8) )
      {
        if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 8) != 0 )
          McTemplateU0hzr0iiiiidj_EventWriteTransfer(
            0,
            (unsigned int)DISCANCR_EVENT_VOLUME_DATA_CORRUPTION_REPAIRED,
            *(_WORD *)a3 >> 1,
            *(_QWORD *)(a3 + 8),
            *(_QWORD *)(a5 + 48),
            *(_QWORD *)(a5 + 16),
            *(_QWORD *)(a5 + 24),
            v21,
            0,
            *(_DWORD *)(a5 + 8),
            *(_QWORD *)(a2 + 24));
        result = dword_1800470B8;
        if ( (unsigned int)dword_1800470B8 > 5 )
        {
          result = tlgKeywordOn(v11, v21, a3);
          if ( result )
          {
            v19 = (char *)word_1800402B2;
            goto LABEL_92;
          }
        }
      }
      else if ( a6 )
      {
        if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 4) != 0 )
          McTemplateU0hzr0iiiiidj_EventWriteTransfer(
            0,
            (unsigned int)DISCAN_EVENT_VOLUME_DATA_CORRUPTION_REPAIR_DEFERRED,
            *(_WORD *)a3 >> 1,
            *(_QWORD *)(a3 + 8),
            *(_QWORD *)(a5 + 48),
            *(_QWORD *)(a5 + 16),
            *(_QWORD *)(a5 + 24),
            v21,
            0,
            *(_DWORD *)(a5 + 8),
            *(_QWORD *)(a2 + 24));
        result = dword_1800470B8;
        if ( (unsigned int)dword_1800470B8 > 5 )
        {
          result = tlgKeywordOn(v11, v21, a3);
          if ( result )
          {
            v19 = (char *)&word_18004040E;
            goto LABEL_92;
          }
        }
      }
      else
      {
        if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 4) != 0 )
          McTemplateU0hzr0iiiiidj_EventWriteTransfer(
            0,
            (unsigned int)DISCAN_EVENT_VOLUME_DATA_CORRUPTION_REPAIRED,
            *(_WORD *)a3 >> 1,
            *(_QWORD *)(a3 + 8),
            *(_QWORD *)(a5 + 48),
            *(_QWORD *)(a5 + 16),
            *(_QWORD *)(a5 + 24),
            v21,
            0,
            *(_DWORD *)(a5 + 8),
            *(_QWORD *)(a2 + 24));
        result = dword_1800470B8;
        if ( (unsigned int)dword_1800470B8 > 5 )
        {
          result = tlgKeywordOn(v11, v21, a3);
          if ( result )
          {
            v19 = byte_180040361;
            goto LABEL_92;
          }
        }
      }
    }
    else
    {
      v22 = *(unsigned int *)(a1 + 8);
      if ( (*(_DWORD *)(a5 + 4) & 0x10000) != 0 )
      {
        if ( (_DWORD)v22 )
        {
          if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 8) != 0 )
            McTemplateU0hzr0iiiiidj_EventWriteTransfer(
              0,
              (unsigned int)DISCANCR_EVENT_NON_USER_DATA_CORRUPTION_REPAIRED,
              *(_WORD *)a3 >> 1,
              *(_QWORD *)(a3 + 8),
              *(_QWORD *)(a5 + 48),
              *(_QWORD *)(a5 + 16),
              *(_QWORD *)(a5 + 24),
              v21,
              0,
              *(_DWORD *)(a5 + 8),
              *(_QWORD *)(a2 + 24));
          result = dword_1800470B8;
          if ( (unsigned int)dword_1800470B8 > 5 )
          {
            result = tlgKeywordOn(v11, v21, v22);
            if ( result )
            {
              v19 = (char *)&unk_1800400A0;
              goto LABEL_92;
            }
          }
        }
        else if ( a6 )
        {
          if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 4) != 0 )
            McTemplateU0hzr0iiiiidj_EventWriteTransfer(
              0,
              (unsigned int)DISCAN_EVENT_NON_USER_DATA_CORRUPTION_REPAIR_DEFERRED,
              *(_WORD *)a3 >> 1,
              *(_QWORD *)(a3 + 8),
              *(_QWORD *)(a5 + 48),
              *(_QWORD *)(a5 + 16),
              *(_QWORD *)(a5 + 24),
              v21,
              0,
              *(_DWORD *)(a5 + 8),
              *(_QWORD *)(a2 + 24));
          result = dword_1800470B8;
          if ( (unsigned int)dword_1800470B8 > 5 )
          {
            result = tlgKeywordOn(v11, v21, v22);
            if ( result )
            {
              v19 = (char *)&word_1800401FE;
              goto LABEL_92;
            }
          }
        }
        else
        {
          if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 4) != 0 )
            McTemplateU0hzr0iiiiidj_EventWriteTransfer(
              0,
              (unsigned int)DISCAN_EVENT_NON_USER_DATA_CORRUPTION_REPAIRED,
              *(_WORD *)a3 >> 1,
              *(_QWORD *)(a3 + 8),
              *(_QWORD *)(a5 + 48),
              *(_QWORD *)(a5 + 16),
              *(_QWORD *)(a5 + 24),
              v21,
              0,
              *(_DWORD *)(a5 + 8),
              *(_QWORD *)(a2 + 24));
          result = dword_1800470B8;
          if ( (unsigned int)dword_1800470B8 > 5 )
          {
            result = tlgKeywordOn(v11, v21, v22);
            if ( result )
            {
              v19 = (char *)&unk_180040150;
              goto LABEL_92;
            }
          }
        }
      }
      else if ( (_DWORD)v22 )
      {
        if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 8) != 0 )
          McTemplateU0hzr0iiiiidj_EventWriteTransfer(
            0,
            (unsigned int)DISCANCR_EVENT_CORRUPTION_REPAIRED,
            *(_WORD *)a3 >> 1,
            *(_QWORD *)(a3 + 8),
            *(_QWORD *)(a5 + 48),
            *(_QWORD *)(a5 + 16),
            *(_QWORD *)(a5 + 24),
            v21,
            0,
            *(_DWORD *)(a5 + 8),
            *(_QWORD *)(a2 + 24));
        result = dword_1800470B8;
        if ( (unsigned int)dword_1800470B8 > 5 )
        {
          result = tlgKeywordOn(v11, v21, v22);
          if ( result )
          {
            v19 = &byte_18003FEAF;
            goto LABEL_92;
          }
        }
      }
      else if ( a6 )
      {
        if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 4) != 0 )
          McTemplateU0hzr0iiiiidj_EventWriteTransfer(
            0,
            (unsigned int)DISCAN_EVENT_CORRUPTION_REPAIR_DEFERRED,
            *(_WORD *)a3 >> 1,
            *(_QWORD *)(a3 + 8),
            *(_QWORD *)(a5 + 48),
            *(_QWORD *)(a5 + 16),
            *(_QWORD *)(a5 + 24),
            v21,
            0,
            *(_DWORD *)(a5 + 8),
            *(_QWORD *)(a2 + 24));
        result = dword_1800470B8;
        if ( (unsigned int)dword_1800470B8 > 5 )
        {
          result = tlgKeywordOn(v11, v21, v22);
          if ( result )
          {
            v19 = &byte_18003FFF7;
            goto LABEL_92;
          }
        }
      }
      else
      {
        if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 4) != 0 )
          McTemplateU0hzr0iiiiidj_EventWriteTransfer(
            0,
            (unsigned int)DISCAN_EVENT_CORRUPTION_REPAIRED,
            *(_WORD *)a3 >> 1,
            *(_QWORD *)(a3 + 8),
            *(_QWORD *)(a5 + 48),
            *(_QWORD *)(a5 + 16),
            *(_QWORD *)(a5 + 24),
            v21,
            0,
            *(_DWORD *)(a5 + 8),
            *(_QWORD *)(a2 + 24));
        result = dword_1800470B8;
        if ( (unsigned int)dword_1800470B8 > 5 )
        {
          result = tlgKeywordOn(v11, v21, v22);
          if ( result )
          {
            v19 = (char *)&dword_18003FF54;
            goto LABEL_92;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000ad94  mov     r11, rsp
0x18000ad97  push    rbp
0x18000ad98  push    rbx
0x18000ad99  push    rsi
0x18000ad9a  push    rdi
0x18000ad9b  lea     rbp, [r11-4Fh]
0x18000ad9f  sub     rsp, 98h
0x18000ada6  mov     rbx, [rbp+47h+arg_20]
0x18000adaa  mov     rsi, rcx
0x18000adad  mov     r10d, r9d
0x18000adb0  mov     rdi, rdx
0x18000adb3  mov     r9, r8
0x18000adb6  mov     rcx, [rbx+28h]
0x18000adba  test    rcx, rcx
0x18000adbd  jz      loc_18000B170
0x18000adc3  cmp     r10d, 1
0x18000adc7  jnz     loc_18000AF48
0x18000adcd  cmp     dword ptr [rsi+8], 0
0x18000add1  jnz     loc_18000AEC6
0x18000add7  test    cs:Microsoft_Windows_DataIntegrityScanEnableBits, 2
0x18000adde  jz      short loc_18000AE2E
0x18000ade0  mov     rax, [rdx+18h]
0x18000ade4  lea     rdx, DISCAN_EVENT_VOLUME_DATA_CORRUPTION_NOT_REPAIRED
0x18000adeb  movzx   r8d, word ptr [r8]
0x18000adef  mov     r9, [r9+8]
0x18000adf3  mov     [r11-68h], rax
0x18000adf7  mov     eax, [rbx+8]
0x18000adfa  mov     dword ptr [rsp+0B0h+var_68], eax
0x18000adfe  mov     rax, [rbx+20h]
0x18000ae02  mov     [r11-78h], rcx
0x18000ae06  mov     [r11-80h], rax
0x18000ae0a  mov     rax, [rbx+18h]
0x18000ae0e  mov     [rsp+0B0h+var_80], rax
0x18000ae13  mov     rax, [rbx+10h]
0x18000ae17  mov     [rsp+0B0h+var_88], rax
0x18000ae1c  mov     rax, [rbx+30h]
0x18000ae20  shr     r8w, 1
0x18000ae24  mov     [rsp+0B0h+var_90], rax
0x18000ae29  call    McTemplateU0hzr0iiiiidj_EventWriteTransfer
0x18000ae2e  mov     eax, cs:dword_1800470B8
0x18000ae34  cmp     eax, 5
0x18000ae37  jbe     loc_18000B6A7
0x18000ae3d  call    _tlgKeywordOn
0x18000ae42  test    al, al
0x18000ae44  jz      loc_18000B6A7
0x18000ae4a  mov     rax, [rbx+18h]
0x18000ae4e  lea     rdx, byte_180040825
0x18000ae55  mov     [rbp+47h+var_50], rax
0x18000ae59  mov     rax, [rbx+10h]
0x18000ae5d  mov     [rbp+47h+var_48], rax
0x18000ae61  mov     eax, [rbx+8]
0x18000ae64  mov     dword ptr [rbp+47h+arg_20], eax
0x18000ae67  mov     rax, [rbx+28h]
0x18000ae6b  mov     [rbp+47h+var_40], rax
0x18000ae6f  mov     rax, [rbx+20h]
0x18000ae73  mov     [rbp+47h+var_38], rax
0x18000ae77  mov     rax, [rdi+18h]
0x18000ae7b  mov     [rbp+47h+var_30], rax
0x18000ae7f  lea     rax, [rsi+34h]
0x18000ae83  mov     [rbp+47h+var_28], rax
0x18000ae87  lea     rax, [rbp+47h+var_50]
0x18000ae8b  mov     [rsp+50h], rax
0x18000ae90  lea     rax, [rbp+47h+var_48]
0x18000ae94  mov     [rsp+0B0h+var_68], rax
0x18000ae99  lea     rax, [rbp+47h+arg_20]
0x18000ae9d  mov     [rsp+0B0h+var_70], rax
0x18000aea2  lea     rax, [rbp+47h+var_40]
0x18000aea6  mov     [rsp+0B0h+var_78], rax
0x18000aeab  lea     rax, [rbp+47h+var_38]
0x18000aeaf  mov     [rsp+0B0h+var_80], rax
0x18000aeb4  lea     rax, [rbp+47h+var_30]
0x18000aeb8  mov     [rsp+0B0h+var_88], rax
0x18000aebd  lea     rax, [rbp+47h+var_28]
0x18000aec1  jmp     loc_18000B69D
0x18000aec6  test    cs:Microsoft_Windows_DataIntegrityScanEnableBits, 10h
0x18000aecd  jz      short loc_18000AF20
0x18000aecf  mov     rax, [rdx+18h]
0x18000aed3  lea     rdx, DISCANCR_EVENT_VOLUME_DATA_CORRUPTION_NOT_REPAIRED
0x18000aeda  movzx   r8d, word ptr [r8]
0x18000aede  mov     r9, [r9+8]
0x18000aee2  mov     [rsp+50h], rax
0x18000aee7  mov     eax, [rbx+8]
0x18000aeea  mov     dword ptr [rsp+0B0h+var_68], eax
0x18000aeee  mov     rax, [rbx+20h]
0x18000aef2  mov     [rsp+0B0h+var_70], rcx
0x18000aef7  mov     [rsp+0B0h+var_78], rax
0x18000aefc  mov     rax, [rbx+18h]
0x18000af00  mov     [rsp+0B0h+var_80], rax
0x18000af05  mov     rax, [rbx+10h]
0x18000af09  mov     [rsp+0B0h+var_88], rax
0x18000af0e  mov     rax, [rbx+30h]
0x18000af12  shr     r8w, 1
0x18000af16  mov     [rsp+0B0h+var_90], rax
0x18000af1b  call    McTemplateU0hzr0iiiiidj_EventWriteTransfer
0x18000af20  mov     eax, cs:dword_1800470B8
0x18000af26  cmp     eax, 5
0x18000af29  jbe     loc_18000B6A7
0x18000af2f  call    _tlgKeywordOn
0x18000af34  test    al, al
0x18000af36  jz      loc_18000B6A7
0x18000af3c  lea     rdx, byte_180040773
0x18000af43  jmp     loc_18000B62D
0x18000af48  test    dword ptr [rbx+4], 10000h
0x18000af4f  mov     eax, [rsi+8]
0x18000af52  jz      loc_18000B064
0x18000af58  test    eax, eax
0x18000af5a  jnz     loc_18000AFE2
0x18000af60  test    cs:Microsoft_Windows_DataIntegrityScanEnableBits, 2
0x18000af67  jz      short loc_18000AFBA
0x18000af69  mov     rax, [rdx+18h]
0x18000af6d  lea     rdx, DISCAN_EVENT_NON_USER_DATA_CORRUPTION_NOT_REPAIRED
0x18000af74  movzx   r8d, word ptr [r8]
0x18000af78  mov     r9, [r9+8]
0x18000af7c  mov     [rsp+50h], rax
0x18000af81  mov     eax, [rbx+8]
0x18000af84  mov     dword ptr [rsp+0B0h+var_68], eax
0x18000af88  mov     rax, [rbx+20h]
0x18000af8c  mov     [rsp+0B0h+var_70], rcx
0x18000af91  mov     [rsp+0B0h+var_78], rax
0x18000af96  mov     rax, [rbx+18h]
0x18000af9a  mov     [rsp+0B0h+var_80], rax
0x18000af9f  mov     rax, [rbx+10h]
0x18000afa3  mov     [rsp+0B0h+var_88], rax
0x18000afa8  mov     rax, [rbx+30h]
0x18000afac  shr     r8w, 1
0x18000afb0  mov     [rsp+0B0h+var_90], rax
0x18000afb5  call    McTemplateU0hzr0iiiiidj_EventWriteTransfer
0x18000afba  mov     eax, cs:dword_1800470B8
0x18000afc0  cmp     eax, 5
0x18000afc3  jbe     loc_18000B6A7
0x18000afc9  call    _tlgKeywordOn
0x18000afce  test    al, al
0x18000afd0  jz      loc_18000B6A7
0x18000afd6  lea     rdx, word_1800406C2
0x18000afdd  jmp     loc_18000B62D
0x18000afe2  test    cs:Microsoft_Windows_DataIntegrityScanEnableBits, 10h
0x18000afe9  jz      short loc_18000B03C
0x18000afeb  mov     rax, [rdx+18h]
0x18000afef  lea     rdx, DISCANCR_EVENT_NON_USER_DATA_CORRUPTION_NOT_REPAIRED
0x18000aff6  movzx   r8d, word ptr [r8]
0x18000affa  mov     r9, [r9+8]
0x18000affe  mov     [rsp+50h], rax
0x18000b003  mov     eax, [rbx+8]
0x18000b006  mov     dword ptr [rsp+0B0h+var_68], eax
0x18000b00a  mov     rax, [rbx+20h]
0x18000b00e  mov     [rsp+0B0h+var_70], rcx
0x18000b013  mov     [rsp+0B0h+var_78], rax
0x18000b018  mov     rax, [rbx+18h]
0x18000b01c  mov     [rsp+0B0h+var_80], rax
0x18000b021  mov     rax, [rbx+10h]
0x18000b025  mov     [rsp+0B0h+var_88], rax
0x18000b02a  mov     rax, [rbx+30h]
0x18000b02e  shr     r8w, 1
0x18000b032  mov     [rsp+0B0h+var_90], rax
0x18000b037  call    McTemplateU0hzr0iiiiidj_EventWriteTransfer
0x18000b03c  mov     eax, cs:dword_1800470B8
0x18000b042  cmp     eax, 5
0x18000b045  jbe     loc_18000B6A7
0x18000b04b  call    _tlgKeywordOn
0x18000b050  test    al, al
0x18000b052  jz      loc_18000B6A7
0x18000b058  lea     rdx, byte_18004060F
0x18000b05f  jmp     loc_18000B62D
0x18000b064  test    eax, eax
0x18000b066  jnz     loc_18000B0EE
0x18000b06c  test    cs:Microsoft_Windows_DataIntegrityScanEnableBits, 2
0x18000b073  jz      short loc_18000B0C6
0x18000b075  mov     rax, [rdx+18h]
0x18000b079  lea     rdx, DISCAN_EVENT_CORRUPTION_NOT_REPAIRED
0x18000b080  movzx   r8d, word ptr [r8]
0x18000b084  mov     r9, [r9+8]
0x18000b088  mov     [rsp+50h], rax
0x18000b08d  mov     eax, [rbx+8]
0x18000b090  mov     dword ptr [rsp+0B0h+var_68], eax
0x18000b094  mov     rax, [rbx+20h]
0x18000b098  mov     [rsp+0B0h+var_70], rcx
0x18000b09d  mov     [rsp+0B0h+var_78], rax
0x18000b0a2  mov     rax, [rbx+18h]
0x18000b0a6  mov     [rsp+0B0h+var_80], rax
0x18000b0ab  mov     rax, [rbx+10h]
0x18000b0af  mov     [rsp+0B0h+var_88], rax
0x18000b0b4  mov     rax, [rbx+30h]
0x18000b0b8  shr     r8w, 1
0x18000b0bc  mov     [rsp+0B0h+var_90], rax
0x18000b0c1  call    McTemplateU0hzr0iiiiidj_EventWriteTransfer
0x18000b0c6  mov     eax, cs:dword_1800470B8
0x18000b0cc  cmp     eax, 5
0x18000b0cf  jbe     loc_18000B6A7
0x18000b0d5  call    _tlgKeywordOn
0x18000b0da  test    al, al
0x18000b0dc  jz      loc_18000B6A7
0x18000b0e2  lea     rdx, byte_180040569
0x18000b0e9  jmp     loc_18000B62D
0x18000b0ee  test    cs:Microsoft_Windows_DataIntegrityScanEnableBits, 10h
0x18000b0f5  jz      short loc_18000B148
0x18000b0f7  mov     rax, [rdx+18h]
0x18000b0fb  lea     rdx, DISCANCR_EVENT_CORRUPTION_NOT_REPAIRED
0x18000b102  movzx   r8d, word ptr [r8]
0x18000b106  mov     r9, [r9+8]
0x18000b10a  mov     [rsp+50h], rax
0x18000b10f  mov     eax, [rbx+8]
0x18000b112  mov     dword ptr [rsp+0B0h+var_68], eax
0x18000b116  mov     rax, [rbx+20h]
0x18000b11a  mov     [rsp+0B0h+var_70], rcx
0x18000b11f  mov     [rsp+0B0h+var_78], rax
0x18000b124  mov     rax, [rbx+18h]
0x18000b128  mov     [rsp+0B0h+var_80], rax
0x18000b12d  mov     rax, [rbx+10h]
0x18000b131  mov     [rsp+0B0h+var_88], rax
0x18000b136  mov     rax, [rbx+30h]
0x18000b13a  shr     r8w, 1
0x18000b13e  mov     [rsp+0B0h+var_90], rax
0x18000b143  call    McTemplateU0hzr0iiiiidj_EventWriteTransfer
0x18000b148  mov     eax, cs:dword_1800470B8
0x18000b14e  cmp     eax, 5
0x18000b151  jbe     loc_18000B6A7
0x18000b157  call    _tlgKeywordOn
0x18000b15c  test    al, al
0x18000b15e  jz      loc_18000B6A7
0x18000b164  lea     rdx, byte_1800404C1
0x18000b16b  jmp     loc_18000B62D
0x18000b170  mov     rdx, [rbx+20h]
0x18000b174  mov     al, [rbp+47h+arg_28]
0x18000b177  test    rdx, rdx
0x18000b17a  jnz     short loc_18000B184
0x18000b17c  test    al, al
0x18000b17e  jz      loc_18000B6A7
0x18000b184  cmp     r10d, 1
0x18000b188  jnz     loc_18000B316
0x18000b18e  cmp     dword ptr [rsi+8], 0
0x18000b192  jnz     loc_18000B298
0x18000b198  test    al, al
0x18000b19a  jz      short loc_18000B21A
0x18000b19c  test    cs:Microsoft_Windows_DataIntegrityScanEnableBits, 4
0x18000b1a3  jz      short loc_18000B1F2
0x18000b1a5  mov     rax, [rdi+18h]
0x18000b1a9  movzx   r8d, word ptr [r8]
0x18000b1ad  mov     r9, [r9+8]
0x18000b1b1  mov     [rsp+50h], rax
0x18000b1b6  mov     eax, [rbx+8]
0x18000b1b9  mov     dword ptr [rsp+0B0h+var_68], eax
0x18000b1bd  mov     rax, [rbx+18h]
0x18000b1c1  mov     [rsp+0B0h+var_70], rcx
0x18000b1c6  mov     [rsp+0B0h+var_78], rdx
0x18000b1cb  lea     rdx, DISCAN_EVENT_VOLUME_DATA_CORRUPTION_REPAIR_DEFERRED
0x18000b1d2  mov     [rsp+0B0h+var_80], rax
0x18000b1d7  mov     rax, [rbx+10h]
0x18000b1db  mov     [rsp+0B0h+var_88], rax
0x18000b1e0  mov     rax, [rbx+30h]
0x18000b1e4  shr     r8w, 1
0x18000b1e8  mov     [rsp+0B0h+var_90], rax
0x18000b1ed  call    McTemplateU0hzr0iiiiidj_EventWriteTransfer
0x18000b1f2  mov     eax, cs:dword_1800470B8
0x18000b1f8  cmp     eax, 5
0x18000b1fb  jbe     loc_18000B6A7
0x18000b201  call    _tlgKeywordOn
0x18000b206  test    al, al
0x18000b208  jz      loc_18000B6A7
0x18000b20e  lea     rdx, word_18004040E
0x18000b215  jmp     loc_18000B62D
0x18000b21a  test    cs:Microsoft_Windows_DataIntegrityScanEnableBits, 4
0x18000b221  jz      short loc_18000B270
0x18000b223  mov     rax, [rdi+18h]
0x18000b227  movzx   r8d, word ptr [r8]
0x18000b22b  mov     r9, [r9+8]
0x18000b22f  mov     [rsp+50h], rax
0x18000b234  mov     eax, [rbx+8]
0x18000b237  mov     dword ptr [rsp+0B0h+var_68], eax
0x18000b23b  mov     rax, [rbx+18h]
0x18000b23f  mov     [rsp+0B0h+var_70], rcx
0x18000b244  mov     [rsp+0B0h+var_78], rdx
0x18000b249  lea     rdx, DISCAN_EVENT_VOLUME_DATA_CORRUPTION_REPAIRED
0x18000b250  mov     [rsp+0B0h+var_80], rax
0x18000b255  mov     rax, [rbx+10h]
0x18000b259  mov     [rsp+0B0h+var_88], rax
0x18000b25e  mov     rax, [rbx+30h]
0x18000b262  shr     r8w, 1
0x18000b266  mov     [rsp+0B0h+var_90], rax
0x18000b26b  call    McTemplateU0hzr0iiiiidj_EventWriteTransfer
0x18000b270  mov     eax, cs:dword_1800470B8
0x18000b276  cmp     eax, 5
0x18000b279  jbe     loc_18000B6A7
0x18000b27f  call    _tlgKeywordOn
0x18000b284  test    al, al
0x18000b286  jz      loc_18000B6A7
0x18000b28c  lea     rdx, byte_180040361
0x18000b293  jmp     loc_18000B62D
0x18000b298  test    cs:Microsoft_Windows_DataIntegrityScanEnableBits, 8
0x18000b29f  jz      short loc_18000B2EE
0x18000b2a1  mov     rax, [rdi+18h]
0x18000b2a5  movzx   r8d, word ptr [r8]
0x18000b2a9  mov     r9, [r9+8]
0x18000b2ad  mov     [rsp+50h], rax
0x18000b2b2  mov     eax, [rbx+8]
0x18000b2b5  mov     dword ptr [rsp+0B0h+var_68], eax
0x18000b2b9  mov     rax, [rbx+18h]
0x18000b2bd  mov     [rsp+0B0h+var_70], rcx
0x18000b2c2  mov     [rsp+0B0h+var_78], rdx
0x18000b2c7  lea     rdx, DISCANCR_EVENT_VOLUME_DATA_CORRUPTION_REPAIRED
0x18000b2ce  mov     [rsp+0B0h+var_80], rax
  ... truncated ...
```
