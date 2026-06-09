# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::Start(void)

- ea: `0x180030930`
- end: `0x180030c32`
- name: `?Start@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAAJXZ`
- size: `770`
- prototype: `__int64 __fastcall(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002c7d0`

## callees

- `0x180012004`
- `0x1800120b8`
- `0x180012384`
- `0x18002c9b8`
- `0x18002fd84`
- `0x180030930`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180030af0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180030af0`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::Start(
        Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *this)
{
  _BYTE *v2; // rcx
  char v3; // di
  bool v4; // dl
  int v5; // esi
  int v6; // edx
  int v7; // r8d
  int v8; // edx
  int v9; // edx
  signed __int32 v10; // eax
  struct _TP_TIMER *v11; // rcx
  bool v12; // dl
  BOOL v13; // eax
  bool v14; // dl
  struct _FILETIME pftDueTime; // [rsp+80h] [rbp+8h] BYREF

  v2 = WPP_GLOBAL_Control;
  v3 = 1;
  v4 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v4,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v2 = WPP_GLOBAL_Control;
  }
  v5 = 0;
  if ( *((_DWORD *)this + 11) == 3 )
  {
    v14 = v2 != (_BYTE *)&WPP_GLOBAL_Control && v2[25] >= 4u;
    if ( v14 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)v2 + 2),
        v14,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        *((_QWORD *)v2 + 5));
      v2 = WPP_GLOBAL_Control;
    }
    goto LABEL_53;
  }
  *((_BYTE *)this + 144) = 0;
  v5 = Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::IncomingLEOobPairing(this);
  if ( v5 >= 0 )
  {
    if ( *((_BYTE *)this + 144) )
    {
      *((_DWORD *)this + 14) = 0;
      *((_DWORD *)this + 11) = 1;
    }
    else
    {
      v2 = WPP_GLOBAL_Control;
      v12 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
      if ( !v12 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
LABEL_44:
        if ( v5 )
          goto LABEL_45;
LABEL_53:
        v13 = v2[25] >= 5u;
        goto LABEL_54;
      }
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
LABEL_43:
    v2 = WPP_GLOBAL_Control;
    goto LABEL_44;
  }
  v2 = WPP_GLOBAL_Control;
  LOBYTE(v6) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, v7, *((_QWORD *)WPP_GLOBAL_Control + 5));
    v2 = WPP_GLOBAL_Control;
  }
  v8 = *((_DWORD *)this + 11);
  if ( !v8 || (v9 = v8 - 1) == 0 )
  {
    *((_DWORD *)this + 11) = 2;
    goto LABEL_33;
  }
  if ( v9 != 1 )
    goto LABEL_44;
  LOBYTE(v9) = v2 != (_BYTE *)&WPP_GLOBAL_Control && v2[25] >= 4u;
  if ( (_BYTE)v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)v2 + 2), v9, v7, *((_QWORD *)v2 + 5));
  }
  ++*((_DWORD *)this + 14);
  v10 = _InterlockedCompareExchange((volatile signed __int32 *)this + 20, 1, 0);
  if ( *((_DWORD *)this + 14) <= 3u || v10 || !*((_QWORD *)this + 9) || *((_DWORD *)this + 35) )
    goto LABEL_43;
  pftDueTime.dwHighDateTime = -1;
  v11 = (struct _TP_TIMER *)*((_QWORD *)this + 9);
  *((_DWORD *)this + 11) = 3;
  pftDueTime.dwLowDateTime = -300000000;
  SetThreadpoolTimer(v11, &pftDueTime, 0, 0);
LABEL_33:
  v2 = WPP_GLOBAL_Control;
LABEL_45:
  v13 = v2[25] >= 2u;
LABEL_54:
  if ( v2 == (_BYTE *)&WPP_GLOBAL_Control || !v13 )
    v3 = 0;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_sqd(
      *((_QWORD *)v2 + 2),
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v2 + 5));
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180030930  mov     [rsp+arg_8], rbx
0x180030935  mov     [rsp+arg_10], rsi
0x18003093a  mov     [rsp+arg_18], rdi
0x18003093f  push    r12
0x180030941  push    r14
0x180030943  push    r15
0x180030945  sub     rsp, 60h
0x180030949  mov     rbx, rcx
0x18003094c  mov     rcx, cs:WPP_GLOBAL_Control
0x180030953  lea     r14, WPP_GLOBAL_Control
0x18003095a  mov     edi, 1
0x18003095f  cmp     rcx, r14
0x180030962  jz      short loc_18003096F
0x180030964  cmp     byte ptr [rcx+19h], 5
0x180030968  jb      short loc_18003096F
0x18003096a  mov     dl, dil
0x18003096d  jmp     short loc_180030971
0x18003096f  xor     dl, dl
0x180030971  lea     r15, WPP_RECORDER_INITIALIZED
0x180030978  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18003097f  lea     r12, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x180030986  setnz   r8b
0x18003098a  test    dl, dl
0x18003098c  jnz     short loc_180030993
0x18003098e  test    r8b, r8b
0x180030991  jz      short loc_1800309B8
0x180030993  mov     r9, [rcx+28h]
0x180030997  mov     rcx, [rcx+10h]
0x18003099b  mov     [rsp+78h+var_30], rbx
0x1800309a0  mov     [rsp+78h+var_40], r12
0x1800309a5  mov     [rsp+78h+var_48], 1Ch
0x1800309ac  call    WPP_RECORDER_AND_TRACE_SF_si
0x1800309b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800309b8  xor     esi, esi
0x1800309ba  cmp     dword ptr [rbx+2Ch], 3
0x1800309be  jz      loc_180030B7F
0x1800309c4  mov     rcx, rbx; this
0x1800309c7  mov     [rbx+90h], sil
0x1800309ce  call    ?IncomingLEOobPairing@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAJXZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::IncomingLEOobPairing(void)
0x1800309d3  mov     esi, eax
0x1800309d5  test    eax, eax
0x1800309d7  jns     loc_180030B0E
0x1800309dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800309e4  cmp     rcx, r14
0x1800309e7  jz      short loc_1800309F4
0x1800309e9  cmp     byte ptr [rcx+19h], 4
0x1800309ed  jb      short loc_1800309F4
0x1800309ef  mov     dl, dil
0x1800309f2  jmp     short loc_1800309F6
0x1800309f4  xor     dl, dl
0x1800309f6  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1800309fd  setnz   r8b
0x180030a01  test    dl, dl
0x180030a03  jnz     short loc_180030A0A
0x180030a05  test    r8b, r8b
0x180030a08  jz      short loc_180030A2E
0x180030a0a  mov     r9, [rcx+28h]
0x180030a0e  mov     rcx, [rcx+10h]
0x180030a12  mov     dword ptr [rsp+78h+var_30], esi
0x180030a16  mov     [rsp+78h+var_40], r12
0x180030a1b  mov     [rsp+78h+var_48], 1Dh
0x180030a22  call    WPP_RECORDER_AND_TRACE_SF_sD
0x180030a27  mov     rcx, cs:WPP_GLOBAL_Control
0x180030a2e  mov     edx, [rbx+2Ch]
0x180030a31  test    edx, edx
0x180030a33  jz      loc_180030AFE
0x180030a39  sub     edx, edi
0x180030a3b  jz      loc_180030AFE
0x180030a41  cmp     edx, edi
0x180030a43  jnz     loc_180030B6D
0x180030a49  cmp     rcx, r14
0x180030a4c  jz      short loc_180030A59
0x180030a4e  cmp     byte ptr [rcx+19h], 4
0x180030a52  jb      short loc_180030A59
0x180030a54  mov     dl, dil
0x180030a57  jmp     short loc_180030A5B
0x180030a59  xor     dl, dl
0x180030a5b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180030a62  setnz   r8b
0x180030a66  test    dl, dl
0x180030a68  jnz     short loc_180030A6F
0x180030a6a  test    r8b, r8b
0x180030a6d  jz      short loc_180030A8F
0x180030a6f  mov     eax, [rbx+38h]
0x180030a72  mov     r9, [rcx+28h]
0x180030a76  mov     rcx, [rcx+10h]
0x180030a7a  mov     dword ptr [rsp+78h+var_30], eax
0x180030a7e  mov     [rsp+78h+var_40], r12
0x180030a83  mov     [rsp+78h+var_48], 1Eh
0x180030a8a  call    WPP_RECORDER_AND_TRACE_SF_sD
0x180030a8f  add     [rbx+38h], edi
0x180030a92  xor     eax, eax
0x180030a94  lock cmpxchg [rbx+50h], edi
0x180030a99  cmp     dword ptr [rbx+38h], 3
0x180030a9d  jbe     loc_180030B66
0x180030aa3  test    eax, eax
0x180030aa5  jnz     loc_180030B66
0x180030aab  cmp     qword ptr [rbx+48h], 0
0x180030ab0  jz      loc_180030B66
0x180030ab6  mov     eax, [rbx+8Ch]
0x180030abc  test    eax, eax
0x180030abe  jnz     loc_180030B66
0x180030ac4  or      [rsp+78h+pftDueTime.dwHighDateTime], 0FFFFFFFFh
0x180030acc  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x180030ad4  mov     rcx, [rbx+48h]; pti
0x180030ad8  xor     r9d, r9d; msWindowLength
0x180030adb  xor     r8d, r8d; msPeriod
0x180030ade  mov     dword ptr [rbx+2Ch], 3
0x180030ae5  mov     [rsp+78h+pftDueTime.dwLowDateTime], 0EE1E5D00h
0x180030af0  call    cs:__imp_SetThreadpoolTimer
0x180030af7  nop     dword ptr [rax+rax+00h]
0x180030afc  jmp     short loc_180030B05
0x180030afe  mov     dword ptr [rbx+2Ch], 2
0x180030b05  mov     rcx, cs:WPP_GLOBAL_Control
0x180030b0c  jmp     short loc_180030B71
0x180030b0e  cmp     byte ptr [rbx+90h], 0
0x180030b15  jz      short loc_180030B20
0x180030b17  and     dword ptr [rbx+38h], 0
0x180030b1b  mov     [rbx+2Ch], edi
0x180030b1e  jmp     short loc_180030B66
0x180030b20  mov     rcx, cs:WPP_GLOBAL_Control
0x180030b27  cmp     rcx, r14
0x180030b2a  jz      short loc_180030B37
0x180030b2c  cmp     byte ptr [rcx+19h], 2
0x180030b30  jb      short loc_180030B37
0x180030b32  mov     dl, dil
0x180030b35  jmp     short loc_180030B39
0x180030b37  xor     dl, dl
0x180030b39  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180030b40  setnz   r8b
0x180030b44  test    dl, dl
0x180030b46  jnz     short loc_180030B4D
0x180030b48  test    r8b, r8b
0x180030b4b  jz      short loc_180030B6D
0x180030b4d  mov     r9, [rcx+28h]
0x180030b51  mov     rcx, [rcx+10h]
0x180030b55  mov     [rsp+78h+var_40], r12
0x180030b5a  mov     [rsp+78h+var_48], 1Fh
0x180030b61  call    WPP_RECORDER_AND_TRACE_SF_s
0x180030b66  mov     rcx, cs:WPP_GLOBAL_Control
0x180030b6d  test    esi, esi
0x180030b6f  jz      short loc_180030BC5
0x180030b71  cmp     byte ptr [rcx+19h], 2
0x180030b75  jb      short loc_180030B7B
0x180030b77  mov     eax, edi
0x180030b79  jmp     short loc_180030BCE
0x180030b7b  xor     eax, eax
0x180030b7d  jmp     short loc_180030BCE
0x180030b7f  cmp     rcx, r14
0x180030b82  jz      short loc_180030B8F
0x180030b84  cmp     byte ptr [rcx+19h], 4
0x180030b88  jb      short loc_180030B8F
0x180030b8a  mov     dl, dil
0x180030b8d  jmp     short loc_180030B91
0x180030b8f  xor     dl, dl
0x180030b91  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180030b98  setnz   r8b
0x180030b9c  test    dl, dl
0x180030b9e  jnz     short loc_180030BA5
0x180030ba0  test    r8b, r8b
0x180030ba3  jz      short loc_180030BC5
0x180030ba5  mov     r9, [rcx+28h]
0x180030ba9  mov     rcx, [rcx+10h]
0x180030bad  mov     [rsp+78h+var_40], r12
0x180030bb2  mov     [rsp+78h+var_48], 20h ; ' '
0x180030bb9  call    WPP_RECORDER_AND_TRACE_SF_s
0x180030bbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180030bc5  xor     eax, eax
0x180030bc7  cmp     byte ptr [rcx+19h], 5
0x180030bcb  setnb   al
0x180030bce  cmp     rcx, r14
0x180030bd1  jz      short loc_180030BD7
0x180030bd3  test    eax, eax
0x180030bd5  jnz     short loc_180030BDA
0x180030bd7  xor     dil, dil
0x180030bda  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180030be1  setnz   r8b
0x180030be5  test    dil, dil
0x180030be8  jnz     short loc_180030BEF
0x180030bea  test    r8b, r8b
0x180030bed  jz      short loc_180030C14
0x180030bef  mov     r9, [rcx+28h]
0x180030bf3  mov     dl, dil
0x180030bf6  mov     rcx, [rcx+10h]
0x180030bfa  mov     [rsp+78h+var_28], esi
0x180030bfe  mov     [rsp+78h+var_30], rbx
0x180030c03  mov     [rsp+78h+var_40], r12
0x180030c08  mov     [rsp+78h+var_48], 21h ; '!'
0x180030c0f  call    WPP_RECORDER_AND_TRACE_SF_sqd
0x180030c14  lea     r11, [rsp+78h+var_18]
0x180030c19  mov     eax, esi
0x180030c1b  mov     rbx, [r11+28h]
0x180030c1f  mov     rsi, [r11+30h]
0x180030c23  mov     rdi, [r11+38h]
0x180030c27  mov     rsp, r11
0x180030c2a  pop     r15
0x180030c2c  pop     r14
0x180030c2e  pop     r12
0x180030c30  retn
```
