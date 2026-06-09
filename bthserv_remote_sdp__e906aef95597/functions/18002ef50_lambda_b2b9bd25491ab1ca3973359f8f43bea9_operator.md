# _lambda_b2b9bd25491ab1ca3973359f8f43bea9_::operator()

- ea: `0x18002ef50`
- end: `0x18002f203`
- name: `_lambda_b2b9bd25491ab1ca3973359f8f43bea9_::operator()`
- size: `691`
- prototype: `__int64 __fastcall(int **, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x18002dd78`

## callees

- `0x180003740`
- `0x180011b9c`
- `0x1800120b8`
- `0x180012384`
- `0x18002c9b8`
- `0x18002dd10`
- `0x18002ef50`
- `0x18002fb44`
- `0x180030530`

## string_xrefs

- `0x18002f112`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`
- `0x18002f180`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`
- `0x18002f1ee`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`

## pseudocode

```c
__int64 __fastcall lambda_b2b9bd25491ab1ca3973359f8f43bea9_::operator()(int **a1, __int64 a2, __int64 a3)
{
  unsigned int *v3; // rsi
  char v5; // bl
  int v6; // eax
  _BYTE *v7; // rcx
  int v8; // edx
  int v9; // r8d
  bool v10; // cf
  _UNKNOWN **v11; // r9
  int v12; // eax
  int v13; // edx
  int v14; // r8d
  __int64 result; // rax
  int v16; // edx
  int v17; // r8d
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  int v21; // [rsp+20h] [rbp-68h]
  _QWORD v22[2]; // [rsp+60h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  int v24; // [rsp+90h] [rbp+8h] BYREF

  v3 = (unsigned int *)a1[1];
  v5 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, *((_QWORD *)WPP_GLOBAL_Control + 5));
  v22[0] = v3;
  v22[1] = &v24;
  v6 = wil::ResultFromException__lambda_8b2eda5c4de3e195837b02a7d86700e7___(v22, a2, a3);
  v7 = WPP_GLOBAL_Control;
  v8 = 0;
  v24 = v6;
  v9 = v6;
  if ( v6 )
    v10 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
  else
    v10 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u;
  LOBYTE(v8) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (LOBYTE(v8) = !v10, v8);
  v11 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sqd(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v9, *((_QWORD *)WPP_GLOBAL_Control + 5));
    v9 = v24;
    v7 = WPP_GLOBAL_Control;
    v11 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  }
  **a1 = v9;
  if ( v9 < 0 )
  {
    if ( v7 == (_BYTE *)&WPP_GLOBAL_Control || v7[25] < 2u )
      v5 = 0;
    if ( v5 || v11 != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = v5;
      LOBYTE(v9) = v11 != &WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)v7 + 2), v8, v9, *((_QWORD *)v7 + 5));
    }
    v18 = wil::verify_hresult<long>((unsigned int)**a1);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x278,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v18,
      v21);
  }
  v12 = Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::SelectCeremony((Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *)a1[1]);
  **a1 = v12;
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      v5 = 0;
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = v5;
      LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, v14, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
    v19 = wil::verify_hresult<long>((unsigned int)**a1);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x27F,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v19,
      v21);
  }
  result = Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::FinalizePairing((Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *)a1[1]);
  **a1 = result;
  if ( (int)result < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      v5 = 0;
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v16) = v5;
      LOBYTE(v17) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, v17, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
    v20 = wil::verify_hresult<long>((unsigned int)**a1);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x286,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v20,
      v21);
  }
  return result;
}

```

## disassembly

```asm
0x18002ef50  mov     [rsp+arg_8], rbx
0x18002ef55  mov     [rsp+arg_10], rbp
0x18002ef5a  mov     [rsp+arg_18], rsi
0x18002ef5f  push    rdi
0x18002ef60  push    r12
0x18002ef62  push    r15
0x18002ef64  sub     rsp, 70h
0x18002ef68  mov     rsi, [rcx+8]
0x18002ef6c  mov     rdi, rcx
0x18002ef6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ef76  lea     rbp, WPP_GLOBAL_Control
0x18002ef7d  mov     bl, 1
0x18002ef7f  cmp     rcx, rbp
0x18002ef82  jz      short loc_18002EF8E
0x18002ef84  cmp     byte ptr [rcx+19h], 5
0x18002ef88  jb      short loc_18002EF8E
0x18002ef8a  mov     dl, bl
0x18002ef8c  jmp     short loc_18002EF90
0x18002ef8e  xor     dl, dl
0x18002ef90  lea     r15, WPP_RECORDER_INITIALIZED
0x18002ef97  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18002ef9e  lea     r12, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002efa5  setnz   r8b
0x18002efa9  test    dl, dl
0x18002efab  jnz     short loc_18002EFB2
0x18002efad  test    r8b, r8b
0x18002efb0  jz      short loc_18002EFD0
0x18002efb2  mov     r9, [rcx+28h]
0x18002efb6  mov     rcx, [rcx+10h]
0x18002efba  mov     [rsp+88h+var_40], rsi
0x18002efbf  mov     [rsp+88h+var_50], r12
0x18002efc4  mov     [rsp+88h+var_58], 47h ; 'G'
0x18002efcb  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002efd0  lea     rax, [rsp+88h+arg_0]
0x18002efd8  mov     [rsp+88h+var_28], rsi
0x18002efdd  lea     rcx, [rsp+88h+var_28]
0x18002efe2  mov     [rsp+88h+var_20], rax
0x18002efe7  call    wil__ResultFromException__lambda_8b2eda5c4de3e195837b02a7d86700e7___
0x18002efec  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eff3  xor     edx, edx
0x18002eff5  mov     [rsp+88h+arg_0], eax
0x18002effc  mov     r8d, eax
0x18002efff  test    eax, eax
0x18002f001  jnz     short loc_18002F009
0x18002f003  cmp     byte ptr [rcx+19h], 5
0x18002f007  jmp     short loc_18002F00D
0x18002f009  cmp     byte ptr [rcx+19h], 2
0x18002f00d  setnb   dl
0x18002f010  cmp     rcx, rbp
0x18002f013  jz      short loc_18002F01D
0x18002f015  test    edx, edx
0x18002f017  jz      short loc_18002F01D
0x18002f019  mov     dl, bl
0x18002f01b  jmp     short loc_18002F01F
0x18002f01d  xor     dl, dl
0x18002f01f  mov     r9, cs:WPP_RECORDER_INITIALIZED
0x18002f026  cmp     r9, r15
0x18002f029  setnz   al
0x18002f02c  test    dl, dl
0x18002f02e  jnz     short loc_18002F034
0x18002f030  test    al, al
0x18002f032  jz      short loc_18002F070
0x18002f034  mov     r9, [rcx+28h]
0x18002f038  mov     rcx, [rcx+10h]
0x18002f03c  mov     [rsp+88h+var_38], r8d
0x18002f041  mov     r8b, al
0x18002f044  mov     [rsp+88h+var_40], rsi
0x18002f049  mov     [rsp+88h+var_50], r12
0x18002f04e  mov     [rsp+88h+var_58], 4Ah ; 'J'
0x18002f055  call    WPP_RECORDER_AND_TRACE_SF_sqd
0x18002f05a  mov     r8d, [rsp+88h+arg_0]
0x18002f062  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f069  mov     r9, cs:WPP_RECORDER_INITIALIZED
0x18002f070  mov     rax, [rdi]
0x18002f073  mov     [rax], r8d
0x18002f076  test    r8d, r8d
0x18002f079  js      short loc_18002F0C2
0x18002f07b  mov     rcx, [rdi+8]; this
0x18002f07f  call    ?SelectCeremony@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAJXZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::SelectCeremony(void)
0x18002f084  mov     rcx, [rdi]
0x18002f087  mov     [rcx], eax
0x18002f089  test    eax, eax
0x18002f08b  js      loc_18002F127
0x18002f091  mov     rcx, [rdi+8]; this
0x18002f095  call    ?FinalizePairing@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAJXZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::FinalizePairing(void)
0x18002f09a  mov     rcx, [rdi]
0x18002f09d  mov     [rcx], eax
0x18002f09f  test    eax, eax
0x18002f0a1  js      loc_18002F195
0x18002f0a7  lea     r11, [rsp+88h+var_18]
0x18002f0ac  mov     rbx, [r11+28h]
0x18002f0b0  mov     rbp, [r11+30h]
0x18002f0b4  mov     rsi, [r11+38h]
0x18002f0b8  mov     rsp, r11
0x18002f0bb  pop     r15
0x18002f0bd  pop     r12
0x18002f0bf  pop     rdi
0x18002f0c0  retn
0x18002f0c2  cmp     rcx, rbp
0x18002f0c5  jz      short loc_18002F0CD
0x18002f0c7  cmp     byte ptr [rcx+19h], 2
0x18002f0cb  jnb     short loc_18002F0CF
0x18002f0cd  xor     bl, bl
0x18002f0cf  cmp     r9, r15
0x18002f0d2  setnz   al
0x18002f0d5  test    bl, bl
0x18002f0d7  jnz     short loc_18002F0DD
0x18002f0d9  test    al, al
0x18002f0db  jz      short loc_18002F100
0x18002f0dd  mov     r9, [rcx+28h]
0x18002f0e1  mov     dl, bl
0x18002f0e3  mov     rcx, [rcx+10h]
0x18002f0e7  mov     dword ptr [rsp+88h+var_40], r8d
0x18002f0ec  mov     r8b, al
0x18002f0ef  mov     [rsp+88h+var_50], r12
0x18002f0f4  mov     [rsp+88h+var_58], 43h ; 'C'
0x18002f0fb  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18002f100  mov     rcx, [rdi]
0x18002f103  mov     ecx, [rcx]
0x18002f105  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002f10a  mov     rcx, [rsp+88h]; this
0x18002f112  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002f119  mov     r9d, eax; char *
0x18002f11c  mov     edx, 278h; void *
0x18002f121  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002f127  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f12e  cmp     rcx, rbp
0x18002f131  jz      short loc_18002F139
0x18002f133  cmp     byte ptr [rcx+19h], 2
0x18002f137  jnb     short loc_18002F13B
0x18002f139  xor     bl, bl
0x18002f13b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18002f142  setnz   r8b
0x18002f146  test    bl, bl
0x18002f148  jnz     short loc_18002F14F
0x18002f14a  test    r8b, r8b
0x18002f14d  jz      short loc_18002F16E
0x18002f14f  mov     r9, [rcx+28h]
0x18002f153  mov     dl, bl
0x18002f155  mov     rcx, [rcx+10h]
0x18002f159  mov     dword ptr [rsp+88h+var_40], eax
0x18002f15d  mov     [rsp+88h+var_50], r12
0x18002f162  mov     [rsp+88h+var_58], 44h ; 'D'
0x18002f169  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18002f16e  mov     rcx, [rdi]
0x18002f171  mov     ecx, [rcx]
0x18002f173  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002f178  mov     rcx, [rsp+88h]; this
0x18002f180  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002f187  mov     r9d, eax; char *
0x18002f18a  mov     edx, 27Fh; void *
0x18002f18f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002f195  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f19c  cmp     rcx, rbp
0x18002f19f  jz      short loc_18002F1A7
0x18002f1a1  cmp     byte ptr [rcx+19h], 2
0x18002f1a5  jnb     short loc_18002F1A9
0x18002f1a7  xor     bl, bl
0x18002f1a9  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18002f1b0  setnz   r8b
0x18002f1b4  test    bl, bl
0x18002f1b6  jnz     short loc_18002F1BD
0x18002f1b8  test    r8b, r8b
0x18002f1bb  jz      short loc_18002F1DC
0x18002f1bd  mov     r9, [rcx+28h]
0x18002f1c1  mov     dl, bl
0x18002f1c3  mov     rcx, [rcx+10h]
0x18002f1c7  mov     dword ptr [rsp+88h+var_40], eax
0x18002f1cb  mov     [rsp+88h+var_50], r12
0x18002f1d0  mov     [rsp+88h+var_58], 45h ; 'E'
0x18002f1d7  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18002f1dc  mov     rcx, [rdi]
0x18002f1df  mov     ecx, [rcx]
0x18002f1e1  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002f1e6  mov     rcx, [rsp+88h]; this
0x18002f1ee  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002f1f5  mov     r9d, eax; char *
0x18002f1f8  mov     edx, 286h; void *
0x18002f1fd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
