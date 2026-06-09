# Int_FwValidateComplianceAndReduceHyperVRuleToVersion

- ea: `0x18002edf0`
- end: `0x18002eed2`
- name: `Int_FwValidateComplianceAndReduceHyperVRuleToVersion`
- size: `226`
- prototype: `__int64 __fastcall(__int64, _DWORD *, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002e420`

## callees

- `0x18000ccd4`
- `0x180017d1c`
- `0x18002edf0`
- `0x18002f43c`

## pseudocode

```c
__int64 __fastcall Int_FwValidateComplianceAndReduceHyperVRuleToVersion(
        __int64 a1,
        _DWORD *a2,
        unsigned __int16 a3,
        int a4)
{
  _QWORD *v8; // rcx
  unsigned int v9; // ebx

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 460, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( (unsigned int)(a4 - 1) > 1 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v8 = WPP_GLOBAL_Control;
  }
  if ( a3 < 0x221u && *(_DWORD *)(a1 + 288) )
  {
    if ( a2 )
    {
      *a2 = 0x20000;
      v8 = WPP_GLOBAL_Control;
    }
    if ( a4 == 1 )
    {
      v9 = 87;
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
        WPP_SF_d(v8[2], 461, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
      return v9;
    }
    if ( a4 == 2 )
      *(_DWORD *)(a1 + 288) = 0;
  }
  v9 = 0;
  if ( !*(_DWORD *)(a1 + 288) )
    *(_DWORD *)(a1 + 288) = 0x7FFFFFFF;
  return v9;
}

```

## disassembly

```asm
0x18002edf0  push    rbx
0x18002edf2  push    rbp
0x18002edf3  push    rsi
0x18002edf4  push    rdi
0x18002edf5  push    r14
0x18002edf7  sub     rsp, 20h
0x18002edfb  mov     ebx, r9d
0x18002edfe  movzx   ebp, r8w
0x18002ee02  mov     rsi, rdx
0x18002ee05  mov     rdi, rcx
0x18002ee08  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ee0f  lea     r14, WPP_GLOBAL_Control
0x18002ee16  cmp     rcx, r14
0x18002ee19  jz      short loc_18002EE3D
0x18002ee1b  test    byte ptr [rcx+1Ch], 8
0x18002ee1f  jz      short loc_18002EE3D
0x18002ee21  mov     rcx, [rcx+10h]
0x18002ee25  lea     r8, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids
0x18002ee2c  mov     edx, 1CCh
0x18002ee31  call    WPP_SF_
0x18002ee36  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ee3d  lea     eax, [rbx-1]
0x18002ee40  cmp     eax, 1
0x18002ee43  jbe     short loc_18002EE51
0x18002ee45  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "verifyFlags == FW_VERIFY_FLAGS_VALIDATE || verifyFlags == FW_VERIFY_FLAGS_REDUCE")
0x18002ee4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ee51  mov     eax, 221h
0x18002ee56  xor     edx, edx
0x18002ee58  cmp     bp, ax
0x18002ee5b  jnb     short loc_18002EEB1
0x18002ee5d  cmp     [rdi+120h], edx
0x18002ee63  jz      short loc_18002EEB1
0x18002ee65  test    rsi, rsi
0x18002ee68  jz      short loc_18002EE77
0x18002ee6a  mov     dword ptr [rsi], 20000h
0x18002ee70  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ee77  cmp     ebx, 1
0x18002ee7a  jnz     short loc_18002EEA6
0x18002ee7c  mov     ebx, 57h ; 'W'
0x18002ee81  cmp     rcx, r14
0x18002ee84  jz      short loc_18002EEC5
0x18002ee86  test    byte ptr [rcx+1Ch], 1
0x18002ee8a  jz      short loc_18002EEC5
0x18002ee8c  mov     rcx, [rcx+10h]
0x18002ee90  lea     r8, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids
0x18002ee97  mov     edx, 1CDh
0x18002ee9c  mov     r9d, ebx
0x18002ee9f  call    WPP_SF_d
0x18002eea4  jmp     short loc_18002EEC5
0x18002eea6  cmp     ebx, 2
0x18002eea9  jnz     short loc_18002EEB1
0x18002eeab  mov     [rdi+120h], edx
0x18002eeb1  mov     ebx, edx
0x18002eeb3  cmp     [rdi+120h], edx
0x18002eeb9  jnz     short loc_18002EEC5
0x18002eebb  mov     dword ptr [rdi+120h], 7FFFFFFFh
0x18002eec5  mov     eax, ebx
0x18002eec7  add     rsp, 20h
0x18002eecb  pop     r14
0x18002eecd  pop     rdi
0x18002eece  pop     rsi
0x18002eecf  pop     rbp
0x18002eed0  pop     rbx
0x18002eed1  retn
```
