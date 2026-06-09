# MSMNotifyAuthRestarted

- ea: `0x180012660`
- end: `0x180012793`
- name: `MSMNotifyAuthRestarted`
- size: `307`
- prototype: ``
- caller_count: `6`
- callee_count: `8`
- tags: ``

## callers

- `0x18000a100`
- `0x18000ade0`
- `0x180017f70`
- `0x180022880`
- `0x180022960`
- `0x1800230c0`

## callees

- `0x180004710`
- `0x180005440`
- `0x180007f60`
- `0x18000c5a0`
- `0x180012660`
- `0x1800127a0`
- `0x18001d180`
- `0x1800214f0`

## pseudocode

```c
__int64 __fastcall MSMNotifyAuthRestarted(__int64 a1, int a2)
{
  unsigned int v2; // edi
  _DWORD *v4; // r10
  const wchar_t *AuthRestartReasonDescription; // rax
  __int64 v6; // r10
  __int64 result; // rax
  unsigned int v8; // ebx
  _UNKNOWN **v9; // rcx
  int v10; // [rsp+48h] [rbp+10h] BYREF

  v10 = a2;
  v2 = *(_DWORD *)(a1 + 20);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 0x4Bu, (__int64)WPP_980772dc0b713ed2d597554bce319f4c_Traceguids);
      a2 = v10;
      v4 = WPP_GLOBAL_Control;
    }
    if ( v4 != (_DWORD *)&WPP_GLOBAL_Control && (v4[17] & 0x200) != 0 )
    {
      AuthRestartReasonDescription = SupplicantGetAuthRestartReasonDescription(a2);
      WPP_SF_dS(
        *(_QWORD *)(v6 + 56),
        76,
        (unsigned int)WPP_980772dc0b713ed2d597554bce319f4c_Traceguids,
        v2,
        (__int64)AuthRestartReasonDescription);
      a2 = v10;
    }
  }
  if ( (byte_18003DF41 & 2) != 0 )
    McTemplateU0qq_EtwEventWriteTransfer(a1, (__int64)RestartingAuthentication, v2, a2);
  result = MSMSendOneXEventNotification(a1, 2u, 4, (__int64)&v10);
  v8 = result;
  if ( !(_DWORD)result )
    goto LABEL_13;
  v9 = (_UNKNOWN **)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return result;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 0x4Du, (__int64)WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v2);
LABEL_13:
    v9 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 17) & 0x800) != 0 )
    WPP_SF_D((__int64)v9[7], 0x4Eu, (__int64)WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x180012660  mov     [rsp+arg_0], rbx
0x180012665  mov     [rsp+arg_10], rsi
0x18001266a  mov     [rsp+arg_8], edx
0x18001266e  push    rdi
0x18001266f  sub     rsp, 30h
0x180012673  mov     edi, [rcx+14h]
0x180012676  mov     rbx, rcx
0x180012679  mov     r10, cs:WPP_GLOBAL_Control
0x180012680  lea     rsi, WPP_GLOBAL_Control
0x180012687  cmp     r10, rsi
0x18001268a  jz      short loc_1800126ED
0x18001268c  test    dword ptr [r10+44h], 800h
0x180012694  jz      short loc_1800126B6
0x180012696  mov     rcx, [r10+38h]
0x18001269a  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x1800126a1  mov     edx, 4Bh ; 'K'
0x1800126a6  call    WPP_SF_
0x1800126ab  mov     edx, [rsp+38h+arg_8]
0x1800126af  mov     r10, cs:WPP_GLOBAL_Control
0x1800126b6  cmp     r10, rsi
0x1800126b9  jz      short loc_1800126ED
0x1800126bb  test    dword ptr [r10+44h], 200h
0x1800126c3  jz      short loc_1800126ED
0x1800126c5  mov     ecx, edx
0x1800126c7  call    SupplicantGetAuthRestartReasonDescription
0x1800126cc  mov     rcx, [r10+38h]
0x1800126d0  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x1800126d7  mov     edx, 4Ch ; 'L'
0x1800126dc  mov     [rsp+38h+var_18], rax
0x1800126e1  mov     r9d, edi
0x1800126e4  call    WPP_SF_dS
0x1800126e9  mov     edx, [rsp+38h+arg_8]
0x1800126ed  test    cs:byte_18003DF41, 2
0x1800126f4  jz      short loc_180012708
0x1800126f6  mov     r9d, edx
0x1800126f9  mov     r8d, edi
0x1800126fc  lea     rdx, RestartingAuthentication
0x180012703  call    McTemplateU0qq_EtwEventWriteTransfer
0x180012708  lea     r9, [rsp+38h+arg_8]
0x18001270d  mov     edx, 2
0x180012712  mov     r8d, 4
0x180012718  mov     rcx, rbx
0x18001271b  call    MSMSendOneXEventNotification
0x180012720  mov     ebx, eax
0x180012722  test    eax, eax
0x180012724  jz      short loc_180012754
0x180012726  mov     rcx, cs:WPP_GLOBAL_Control
0x18001272d  cmp     rcx, rsi
0x180012730  jz      short loc_180012783
0x180012732  test    byte ptr [rcx+44h], 1
0x180012736  jz      short loc_18001275B
0x180012738  mov     rcx, [rcx+38h]
0x18001273c  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x180012743  mov     edx, 4Dh ; 'M'
0x180012748  mov     dword ptr [rsp+38h+var_18], eax
0x18001274c  mov     r9d, edi
0x18001274f  call    WPP_SF_dd
0x180012754  mov     rcx, cs:WPP_GLOBAL_Control
0x18001275b  cmp     rcx, rsi
0x18001275e  jz      short loc_180012781
0x180012760  test    dword ptr [rcx+44h], 800h
0x180012767  jz      short loc_180012781
0x180012769  mov     rcx, [rcx+38h]
0x18001276d  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x180012774  mov     edx, 4Eh ; 'N'
0x180012779  mov     r9d, ebx
0x18001277c  call    WPP_SF_D
0x180012781  mov     eax, ebx
0x180012783  mov     rbx, [rsp+38h+arg_0]
0x180012788  mov     rsi, [rsp+38h+arg_10]
0x18001278d  add     rsp, 30h
0x180012791  pop     rdi
0x180012792  retn
```
