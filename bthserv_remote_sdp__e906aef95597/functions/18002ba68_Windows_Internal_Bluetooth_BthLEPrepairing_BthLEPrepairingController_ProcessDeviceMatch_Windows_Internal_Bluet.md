# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::ProcessDeviceMatch(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *)

- ea: `0x18002ba68`
- end: `0x18002bd32`
- name: `?ProcessDeviceMatch@BthLEPrepairingController@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAJPEAVBthLEPrepairingDevice@2345@@Z`
- size: `714`
- prototype: `__int64 __fastcall(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *__hidden this, struct Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18002b8ac`
- `0x18002bd38`

## callees

- `0x180012004`
- `0x1800120b8`
- `0x180012384`
- `0x18002b02c`
- `0x18002ba68`
- `0x18002bef4`
- `0x18002c9b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002baf7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002baf7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002bb87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002bb87`
- `BthTelemetry!BthProcessEventOccurrenceBthaddr` at `0x18002bbb2`
- `BthTelemetry!BthProcessEventOccurrenceBthaddr` at `0x18002bbb2`

## string_xrefs

- `0x18002bba7`: `BTH_TELEMETRYDATA_PREPAIRING_INITIAL_HW_FILTER_MATCHED`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::ProcessDeviceMatch(
        Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *this,
        struct Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *a2)
{
  struct Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *v2; // rbp
  char v4; // bl
  char v5; // r15
  int v6; // edi
  int v7; // edx
  int v8; // r8d
  int v9; // ecx
  int v10; // ecx
  _BYTE *v11; // rcx
  bool v12; // dl
  bool v13; // dl
  int v14; // eax
  bool v15; // cf
  Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *v17; // [rsp+90h] [rbp+8h] BYREF

  v2 = a2;
  v4 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)a2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  v5 = 0;
  v6 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v9 = *((_DWORD *)this + 2);
  if ( v9 )
  {
    v10 = v9 - 1;
    if ( v10 )
    {
      if ( v10 == 1 )
      {
        v11 = WPP_GLOBAL_Control;
        v12 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
        if ( v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          WPP_RECORDER_AND_TRACE_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v12,
            WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
            *((_QWORD *)WPP_GLOBAL_Control + 5));
          v11 = WPP_GLOBAL_Control;
        }
        goto LABEL_19;
      }
    }
    else
    {
      *((_DWORD *)this + 2) = 2;
      v5 = 1;
      *((_QWORD *)this + 11) = v2;
    }
    v11 = WPP_GLOBAL_Control;
    goto LABEL_19;
  }
  v11 = WPP_GLOBAL_Control;
  v13 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
  if ( v13 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v11 = WPP_GLOBAL_Control;
  }
  v6 = -2147418113;
LABEL_19:
  if ( this != (Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *)-48LL )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    v11 = WPP_GLOBAL_Control;
  }
  if ( v5 )
  {
    BthProcessEventOccurrenceBthaddr(
      "BTH_TELEMETRYDATA_PREPAIRING_INITIAL_HW_FILTER_MATCHED",
      *(_QWORD *)(*((_QWORD *)this + 11) + 48LL));
    v17 = this;
    v6 = wil::ResultFromException__lambda_69d4ebafcdfc875e4eef5671220ca470___(&v17);
    if ( v6 < 0 )
    {
      LOBYTE(v7) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
      if ( (_BYTE)v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, v8, *((_QWORD *)WPP_GLOBAL_Control + 5));
      }
      Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::ResetPairingState(this);
      v11 = WPP_GLOBAL_Control;
      goto LABEL_40;
    }
    v11 = WPP_GLOBAL_Control;
  }
  if ( !v6 )
  {
    v14 = 0;
    v15 = v11[25] < 5u;
    goto LABEL_41;
  }
LABEL_40:
  v14 = 0;
  v15 = v11[25] < 2u;
LABEL_41:
  if ( v11 == (_BYTE *)&WPP_GLOBAL_Control || (LOBYTE(v14) = !v15, !v14) )
    v4 = 0;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v7) = v4;
    LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sqd(*((_QWORD *)v11 + 2), v7, v8, *((_QWORD *)v11 + 5));
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002ba68  mov     [rsp+arg_8], rbx
0x18002ba6d  mov     [rsp+arg_10], rbp
0x18002ba72  mov     [rsp+arg_18], rsi
0x18002ba77  push    rdi
0x18002ba78  push    r12
0x18002ba7a  push    r13
0x18002ba7c  push    r14
0x18002ba7e  push    r15
0x18002ba80  sub     rsp, 60h
0x18002ba84  mov     rbp, rdx
0x18002ba87  mov     rsi, rcx
0x18002ba8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ba91  lea     r12, WPP_GLOBAL_Control
0x18002ba98  mov     bl, 1
0x18002ba9a  cmp     rcx, r12
0x18002ba9d  jz      short loc_18002BAA9
0x18002ba9f  cmp     byte ptr [rcx+19h], 5
0x18002baa3  jb      short loc_18002BAA9
0x18002baa5  mov     dl, bl
0x18002baa7  jmp     short loc_18002BAAB
0x18002baa9  xor     dl, dl
0x18002baab  lea     r13, WPP_RECORDER_INITIALIZED
0x18002bab2  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002bab9  lea     r9, WPP_a555314c10c534a6d8c11e317bc5bc21_Traceguids
0x18002bac0  setnz   r8b
0x18002bac4  test    dl, dl
0x18002bac6  jnz     short loc_18002BACD
0x18002bac8  test    r8b, r8b
0x18002bacb  jz      short loc_18002BAEB
0x18002bacd  mov     [rsp+88h+var_40], rsi
0x18002bad2  mov     [rsp+88h+var_50], r9
0x18002bad7  mov     r9, [rcx+28h]
0x18002badb  mov     rcx, [rcx+10h]
0x18002badf  mov     [rsp+88h+var_58], 20h ; ' '
0x18002bae6  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002baeb  lea     r14, [rsi+30h]
0x18002baef  xor     r15b, r15b
0x18002baf2  mov     rcx, r14; lpCriticalSection
0x18002baf5  xor     edi, edi
0x18002baf7  call    cs:__imp_EnterCriticalSection
0x18002bafe  nop     dword ptr [rax+rax+00h]
0x18002bb03  mov     ecx, [rsi+8]
0x18002bb06  test    ecx, ecx
0x18002bb08  jz      loc_18002BC0A
0x18002bb0e  sub     ecx, 1
0x18002bb11  jz      loc_18002BBF7
0x18002bb17  cmp     ecx, 1
0x18002bb1a  jnz     short loc_18002BB71
0x18002bb1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bb23  cmp     rcx, r12
0x18002bb26  jz      short loc_18002BB32
0x18002bb28  cmp     byte ptr [rcx+19h], 4
0x18002bb2c  jb      short loc_18002BB32
0x18002bb2e  mov     dl, bl
0x18002bb30  jmp     short loc_18002BB34
0x18002bb32  xor     dl, dl
0x18002bb34  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002bb3b  setnz   r8b
0x18002bb3f  test    dl, dl
0x18002bb41  jnz     short loc_18002BB48
0x18002bb43  test    r8b, r8b
0x18002bb46  jz      short loc_18002BB78
0x18002bb48  mov     r9, [rcx+28h]
0x18002bb4c  lea     rbp, WPP_a555314c10c534a6d8c11e317bc5bc21_Traceguids
0x18002bb53  mov     rcx, [rcx+10h]
0x18002bb57  mov     [rsp+88h+var_50], rbp
0x18002bb5c  mov     [rsp+88h+var_58], 22h ; '"'
0x18002bb63  call    WPP_RECORDER_AND_TRACE_SF_s
0x18002bb68  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bb6f  jmp     short loc_18002BB7F
0x18002bb71  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bb78  lea     rbp, WPP_a555314c10c534a6d8c11e317bc5bc21_Traceguids
0x18002bb7f  test    r14, r14
0x18002bb82  jz      short loc_18002BB9A
0x18002bb84  mov     rcx, r14; lpCriticalSection
0x18002bb87  call    cs:__imp_LeaveCriticalSection
0x18002bb8e  nop     dword ptr [rax+rax+00h]
0x18002bb93  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bb9a  test    r15b, r15b
0x18002bb9d  jz      loc_18002BD26
0x18002bba3  mov     rdx, [rsi+58h]
0x18002bba7  lea     rcx, aBthTelemetryda; "BTH_TELEMETRYDATA_PREPAIRING_INITIAL_HW"...
0x18002bbae  mov     rdx, [rdx+30h]
0x18002bbb2  call    cs:__imp_?BthProcessEventOccurrenceBthaddr@@YAXPEBD_K@Z; BthProcessEventOccurrenceBthaddr(char const *,unsigned __int64)
0x18002bbb9  nop     dword ptr [rax+rax+00h]
0x18002bbbe  lea     rcx, [rsp+88h+arg_0]
0x18002bbc6  mov     [rsp+88h+arg_0], rsi
0x18002bbce  call    wil__ResultFromException__lambda_69d4ebafcdfc875e4eef5671220ca470___
0x18002bbd3  mov     edi, eax
0x18002bbd5  test    eax, eax
0x18002bbd7  jns     loc_18002BD1F
0x18002bbdd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bbe4  cmp     rcx, r12
0x18002bbe7  jz      loc_18002BC70
0x18002bbed  cmp     byte ptr [rcx+19h], 2
0x18002bbf1  jb      short loc_18002BC70
0x18002bbf3  mov     dl, bl
0x18002bbf5  jmp     short loc_18002BC72
0x18002bbf7  mov     dword ptr [rsi+8], 2
0x18002bbfe  mov     r15b, bl
0x18002bc01  mov     [rsi+58h], rbp
0x18002bc05  jmp     loc_18002BB71
0x18002bc0a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bc11  cmp     rcx, r12
0x18002bc14  jz      short loc_18002BC20
0x18002bc16  cmp     byte ptr [rcx+19h], 2
0x18002bc1a  jb      short loc_18002BC20
0x18002bc1c  mov     dl, bl
0x18002bc1e  jmp     short loc_18002BC22
0x18002bc20  xor     dl, dl
0x18002bc22  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002bc29  setnz   r8b
0x18002bc2d  test    dl, dl
0x18002bc2f  jnz     short loc_18002BC36
0x18002bc31  test    r8b, r8b
0x18002bc34  jz      short loc_18002BC5F
0x18002bc36  mov     r9, [rcx+28h]
0x18002bc3a  lea     rbp, WPP_a555314c10c534a6d8c11e317bc5bc21_Traceguids
0x18002bc41  mov     rcx, [rcx+10h]
0x18002bc45  mov     [rsp+88h+var_50], rbp
0x18002bc4a  mov     [rsp+88h+var_58], 21h ; '!'
0x18002bc51  call    WPP_RECORDER_AND_TRACE_SF_s
0x18002bc56  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bc5d  jmp     short loc_18002BC66
0x18002bc5f  lea     rbp, WPP_a555314c10c534a6d8c11e317bc5bc21_Traceguids
0x18002bc66  mov     edi, 8000FFFFh
0x18002bc6b  jmp     loc_18002BB7F
0x18002bc70  xor     dl, dl
0x18002bc72  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002bc79  setnz   r8b
0x18002bc7d  test    dl, dl
0x18002bc7f  jnz     short loc_18002BC86
0x18002bc81  test    r8b, r8b
0x18002bc84  jz      short loc_18002BCA3
0x18002bc86  mov     r9, [rcx+28h]
0x18002bc8a  mov     rcx, [rcx+10h]
0x18002bc8e  mov     dword ptr [rsp+88h+var_40], eax
0x18002bc92  mov     [rsp+88h+var_50], rbp
0x18002bc97  mov     [rsp+88h+var_58], 23h ; '#'
0x18002bc9e  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18002bca3  mov     rcx, rsi; this
0x18002bca6  call    ?ResetPairingState@BthLEPrepairingController@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAXXZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::ResetPairingState(void)
0x18002bcab  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bcb2  xor     eax, eax
0x18002bcb4  cmp     byte ptr [rcx+19h], 2
0x18002bcb8  setnb   al
0x18002bcbb  cmp     rcx, r12
0x18002bcbe  jz      short loc_18002BCC4
0x18002bcc0  test    eax, eax
0x18002bcc2  jnz     short loc_18002BCC6
0x18002bcc4  xor     bl, bl
0x18002bcc6  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002bccd  setnz   r8b
0x18002bcd1  test    bl, bl
0x18002bcd3  jnz     short loc_18002BCDA
0x18002bcd5  test    r8b, r8b
0x18002bcd8  jz      short loc_18002BCFE
0x18002bcda  mov     r9, [rcx+28h]
0x18002bcde  mov     dl, bl
0x18002bce0  mov     rcx, [rcx+10h]
0x18002bce4  mov     [rsp+88h+var_38], edi
0x18002bce8  mov     [rsp+88h+var_40], rsi
0x18002bced  mov     [rsp+88h+var_50], rbp
0x18002bcf2  mov     [rsp+88h+var_58], 24h ; '$'
0x18002bcf9  call    WPP_RECORDER_AND_TRACE_SF_sqd
0x18002bcfe  lea     r11, [rsp+88h+var_28]
0x18002bd03  mov     eax, edi
0x18002bd05  mov     rbx, [r11+38h]
0x18002bd09  mov     rbp, [r11+40h]
0x18002bd0d  mov     rsi, [r11+48h]
0x18002bd11  mov     rsp, r11
0x18002bd14  pop     r15
0x18002bd16  pop     r14
0x18002bd18  pop     r13
0x18002bd1a  pop     r12
0x18002bd1c  pop     rdi
0x18002bd1d  retn
0x18002bd1f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bd26  test    edi, edi
0x18002bd28  jnz     short loc_18002BCB2
0x18002bd2a  xor     eax, eax
0x18002bd2c  cmp     byte ptr [rcx+19h], 5
0x18002bd30  jmp     short loc_18002BCB8
```
