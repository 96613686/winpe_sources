# SBackendEntryEapConfigChanged

- ea: `0x180024750`
- end: `0x180024855`
- name: `SBackendEntryEapConfigChanged`
- size: `261`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180005440`
- `0x180007f60`
- `0x18000cd90`
- `0x18001971c`
- `0x1800214f0`
- `0x180024750`

## pseudocode

```c
__int64 __fastcall SBackendEntryEapConfigChanged(__int64 a1)
{
  __int64 v1; // rbx
  unsigned int v2; // edi
  int v3; // eax
  unsigned int SupplicantEvent; // eax
  unsigned int v5; // ebx
  _QWORD *v6; // rcx

  v1 = *(_QWORD *)(a1 + 24);
  v2 = *(_DWORD *)(v1 + 20);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 48, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids);
  v3 = EapClearStateOnConfigChanged(v1 + 2496);
  if ( v3 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 49, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids, v2, v3);
  SupplicantEvent = GenerateSupplicantEvent(v1, 24);
  v5 = SupplicantEvent;
  if ( !SupplicantEvent )
    goto LABEL_12;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v5;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      50,
      WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids,
      v2,
      SupplicantEvent);
LABEL_12:
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 17) & 0x800) != 0 )
    WPP_SF_D(v6[7], 51, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180024750  mov     [rsp+arg_0], rbx
0x180024755  mov     [rsp+arg_8], rsi
0x18002475a  push    rdi
0x18002475b  sub     rsp, 30h
0x18002475f  mov     rbx, [rcx+18h]
0x180024763  mov     edi, [rbx+14h]
0x180024766  mov     rcx, cs:WPP_GLOBAL_Control
0x18002476d  lea     rsi, WPP_GLOBAL_Control
0x180024774  cmp     rcx, rsi
0x180024777  jz      short loc_180024797
0x180024779  test    dword ptr [rcx+44h], 800h
0x180024780  jz      short loc_180024797
0x180024782  mov     rcx, [rcx+38h]
0x180024786  lea     r8, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids
0x18002478d  mov     edx, 30h ; '0'
0x180024792  call    WPP_SF_
0x180024797  lea     rcx, [rbx+9C0h]
0x18002479e  call    EapClearStateOnConfigChanged
0x1800247a3  test    eax, eax
0x1800247a5  jz      short loc_1800247D5
0x1800247a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800247ae  cmp     rcx, rsi
0x1800247b1  jz      short loc_1800247D5
0x1800247b3  test    byte ptr [rcx+44h], 1
0x1800247b7  jz      short loc_1800247D5
0x1800247b9  mov     rcx, [rcx+38h]
0x1800247bd  lea     r8, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids
0x1800247c4  mov     edx, 31h ; '1'
0x1800247c9  mov     [rsp+38h+var_18], eax
0x1800247cd  mov     r9d, edi
0x1800247d0  call    WPP_SF_dd
0x1800247d5  mov     edx, 18h
0x1800247da  mov     rcx, rbx
0x1800247dd  call    GenerateSupplicantEvent
0x1800247e2  mov     ebx, eax
0x1800247e4  test    eax, eax
0x1800247e6  jz      short loc_180024816
0x1800247e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800247ef  cmp     rcx, rsi
0x1800247f2  jz      short loc_180024843
0x1800247f4  test    byte ptr [rcx+44h], 1
0x1800247f8  jz      short loc_18002481D
0x1800247fa  mov     rcx, [rcx+38h]
0x1800247fe  lea     r8, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids
0x180024805  mov     edx, 32h ; '2'
0x18002480a  mov     [rsp+38h+var_18], eax
0x18002480e  mov     r9d, edi
0x180024811  call    WPP_SF_dd
0x180024816  mov     rcx, cs:WPP_GLOBAL_Control
0x18002481d  cmp     rcx, rsi
0x180024820  jz      short loc_180024843
0x180024822  test    dword ptr [rcx+44h], 800h
0x180024829  jz      short loc_180024843
0x18002482b  mov     rcx, [rcx+38h]
0x18002482f  lea     r8, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids
0x180024836  mov     edx, 33h ; '3'
0x18002483b  mov     r9d, ebx
0x18002483e  call    WPP_SF_D
0x180024843  mov     rsi, [rsp+38h+arg_8]
0x180024848  mov     eax, ebx
0x18002484a  mov     rbx, [rsp+38h+arg_0]
0x18002484f  add     rsp, 30h
0x180024853  pop     rdi
0x180024854  retn
```
