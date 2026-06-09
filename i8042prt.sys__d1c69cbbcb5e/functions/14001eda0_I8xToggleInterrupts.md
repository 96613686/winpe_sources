# I8xToggleInterrupts

- ea: `0x14001eda0`
- end: `0x14001ee9a`
- name: `I8xToggleInterrupts`
- size: `250`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400171e8`
- `0x14001be20`
- `0x14001e950`

## callees

- `0x1400043e0`
- `0x140005560`
- `0x140008a10`
- `0x14001eda0`

## pseudocode

```c
__int64 __fastcall I8xToggleInterrupts(char a1, __int64 a2)
{
  const char *v3; // rax
  int v4; // ecx
  int v5; // edx
  unsigned int v6; // edi
  const char *v7; // rcx
  __int64 v9; // [rsp+40h] [rbp-38h] BYREF
  int v10; // [rsp+48h] [rbp-30h]

  v9 = 0;
  v10 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v3 = "TRUE";
    if ( !a1 )
      v3 = "FALSE";
    WPP_RECORDER_SF_s(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      a2,
      0xFu,
      0x1Eu,
      (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
      v3);
  }
  v4 = **(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
  LODWORD(v9) = **(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
  if ( a1 )
  {
    BYTE4(v9) = 0;
    BYTE5(v9) = v4 & 3;
  }
  else
  {
    WORD2(v9) = -1023;
  }
  I8xTransmitControllerCommand((unsigned int *)&v9, a2);
  v6 = v10;
  if ( v10 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v7 = "en";
    if ( !a1 )
      v7 = "dis";
    WPP_RECORDER_SF_sD(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      17,
      31,
      (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
      (__int64)v7,
      v10);
  }
  return v6;
}

```

## disassembly

```asm
0x14001eda0  push    rbx
0x14001eda2  push    rbp
0x14001eda3  push    rsi
0x14001eda4  push    rdi
0x14001eda5  sub     rsp, 58h
0x14001eda9  xor     eax, eax
0x14001edab  movzx   ebx, cl
0x14001edae  mov     [rsp+78h+var_38], rax
0x14001edb3  mov     [rsp+78h+var_30], eax
0x14001edb7  lea     rsi, WPP_RECORDER_INITIALIZED
0x14001edbe  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14001edc5  lea     rbp, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x14001edcc  jz      short loc_14001EE08
0x14001edce  test    bl, bl
0x14001edd0  lea     rcx, aFalse_0; "FALSE"
0x14001edd7  lea     rax, aTrue_0; "TRUE"
0x14001edde  mov     r9d, 1Eh
0x14001ede4  cmovz   rax, rcx
0x14001ede8  mov     r8d, 0Fh
0x14001edee  mov     rcx, cs:WPP_GLOBAL_Control
0x14001edf5  mov     [rsp+78h+var_50], rax
0x14001edfa  mov     [rsp+78h+var_58], rbp
0x14001edff  mov     rcx, [rcx+40h]
0x14001ee03  call    WPP_RECORDER_SF_s
0x14001ee08  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14001ee0f  mov     ecx, [rax]
0x14001ee11  mov     dword ptr [rsp+78h+var_38], ecx
0x14001ee15  test    bl, bl
0x14001ee17  jz      short loc_14001EE2E
0x14001ee19  movzx   eax, cl
0x14001ee1c  mov     byte ptr [rsp+78h+var_38+4], 0
0x14001ee21  and     al, 1
0x14001ee23  and     cl, 2
0x14001ee26  or      al, cl
0x14001ee28  mov     byte ptr [rsp+78h+var_38+5], al
0x14001ee2c  jmp     short loc_14001EE35
0x14001ee2e  mov     word ptr [rsp+78h+var_38+4], 0FC01h
0x14001ee35  lea     rcx, [rsp+78h+var_38]
0x14001ee3a  call    I8xTransmitControllerCommand
0x14001ee3f  mov     edi, [rsp+78h+var_30]
0x14001ee43  test    edi, edi
0x14001ee45  jns     short loc_14001EE8E
0x14001ee47  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14001ee4e  jz      short loc_14001EE8E
0x14001ee50  test    bl, bl
0x14001ee52  mov     [rsp+78h+var_48], edi
0x14001ee56  lea     rax, aDis; "dis"
0x14001ee5d  mov     r9d, 1Fh
0x14001ee63  lea     rcx, aEn; "en"
0x14001ee6a  mov     r8d, 11h
0x14001ee70  cmovz   rcx, rax
0x14001ee74  mov     [rsp+78h+var_50], rcx
0x14001ee79  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ee80  mov     [rsp+78h+var_58], rbp
0x14001ee85  mov     rcx, [rcx+40h]
0x14001ee89  call    WPP_RECORDER_SF_sD
0x14001ee8e  mov     eax, edi
0x14001ee90  add     rsp, 58h
0x14001ee94  pop     rdi
0x14001ee95  pop     rsi
0x14001ee96  pop     rbp
0x14001ee97  pop     rbx
0x14001ee98  retn
```
