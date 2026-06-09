# PrjfPostWrite

- ea: `0x1400057b0`
- end: `0x140005910`
- name: `PrjfPostWrite`
- size: `352`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400057b0`
- `0x14000b1a0`
- `0x14000d008`
- `0x14000d754`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x140005861`
- `FLTMGR!FltReleaseContext` at `0x140005861`

## string_xrefs

- `0x140005810`: `onecore\base\fs\gvflt\filter\sys\readwrite.c`
- `0x1400058a9`: `onecore\base\fs\gvflt\filter\sys\readwrite.c`

## pseudocode

```c
__int64 __fastcall PrjfPostWrite(__int64 a1, __int64 a2, _DWORD *a3, char a4)
{
  void *v4; // rbx
  __int64 v5; // r10
  int v6; // r9d

  v4 = a3;
  v5 = a2;
  if ( (a4 & 1) == 0 )
  {
    v6 = *(_DWORD *)(a1 + 24);
    if ( v6 >= 0 )
    {
      if ( *(_DWORD *)(*(_QWORD *)(a1 + 16) + 24LL) )
      {
        if ( !a3 )
        {
          MicrosoftTelemetryAssertTriggeredMsgKM("Missing streamhandle context!");
          return 0;
        }
        a3[10] |= 4u;
        goto LABEL_8;
      }
      if ( (xmmword_14001A3E0 & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = xmmword_14001A3E0 & 4;
        LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sD(
          1026,
          a2,
          (_DWORD)a3,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          4,
          2,
          12,
          (__int64)&WPP_e0f66f78cb02376c02d9fc0dec322fb4_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\readwrite.c",
          96);
      }
    }
    else if ( v6 != -1071906812
           && ((BYTE8(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
    {
      LOBYTE(a2) = BYTE8(xmmword_14001A3D0) & 4;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDdZ(
        770,
        a2,
        (_DWORD)a3,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        3,
        2,
        11,
        (__int64)&WPP_e0f66f78cb02376c02d9fc0dec322fb4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\readwrite.c",
        82,
        v6,
        *(_QWORD *)(v5 + 32) + 88LL);
    }
  }
  if ( v4 )
LABEL_8:
    FltReleaseContext(v4);
  return 0;
}

```

## disassembly

```asm
0x1400057b0  push    rbx
0x1400057b2  sub     rsp, 60h
0x1400057b6  mov     rbx, r8
0x1400057b9  mov     r10, rdx
0x1400057bc  test    r9b, 1
0x1400057c0  jnz     loc_140005859
0x1400057c6  mov     r9d, [rcx+18h]
0x1400057ca  test    r9d, r9d
0x1400057cd  jns     loc_140005876
0x1400057d3  cmp     r9d, 0C01C0004h
0x1400057da  jz      short loc_140005859
0x1400057dc  mov     dl, byte ptr cs:xmmword_14001A3D0+8
0x1400057e2  lea     rax, WPP_RECORDER_INITIALIZED
0x1400057e9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400057f0  setnz   r8b
0x1400057f4  and     dl, 4
0x1400057f7  jnz     short loc_1400057FE
0x1400057f9  test    r8b, r8b
0x1400057fc  jz      short loc_140005859
0x1400057fe  mov     rax, [r10+20h]
0x140005802  mov     ecx, 302h
0x140005807  add     rax, 58h ; 'X'
0x14000580b  mov     [rsp+68h+var_10], rax
0x140005810  lea     rax, aOnecoreBaseFsG; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140005817  mov     [rsp+68h+var_18], r9d
0x14000581c  mov     r9, cs:WPP_GLOBAL_Control
0x140005823  mov     [rsp+68h+var_20], 152h
0x14000582b  mov     [rsp+68h+var_28], rax
0x140005830  lea     rax, WPP_e0f66f78cb02376c02d9fc0dec322fb4_Traceguids
0x140005837  mov     [rsp+68h+var_30], rax
0x14000583c  mov     r9, [r9+40h]
0x140005840  mov     [rsp+68h+var_38], 0Bh
0x140005847  mov     [rsp+68h+var_40], 2
0x14000584f  mov     [rsp+68h+var_48], 3
0x140005854  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x140005859  test    rbx, rbx
0x14000585c  jz      short loc_14000586D
0x14000585e  mov     rcx, rbx; Context
0x140005861  call    cs:__imp_FltReleaseContext
0x140005868  nop     dword ptr [rax+rax+00h]
0x14000586d  xor     eax, eax
0x14000586f  add     rsp, 60h
0x140005873  pop     rbx
0x140005874  retn
0x140005876  mov     rax, [rcx+10h]
0x14000587a  cmp     dword ptr [rax+18h], 0
0x14000587e  jnz     short loc_1400058F0
0x140005880  mov     dl, byte ptr cs:xmmword_14001A3E0
0x140005886  lea     rax, WPP_RECORDER_INITIALIZED
0x14000588d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140005894  setnz   r8b
0x140005898  and     dl, 4
0x14000589b  jnz     short loc_1400058A2
0x14000589d  test    r8b, r8b
0x1400058a0  jz      short loc_140005859
0x1400058a2  mov     r9, cs:WPP_GLOBAL_Control
0x1400058a9  lea     rax, aOnecoreBaseFsG; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400058b0  mov     [rsp+68h+var_20], 160h
0x1400058b8  mov     ecx, 402h
0x1400058bd  mov     [rsp+68h+var_28], rax
0x1400058c2  lea     rax, WPP_e0f66f78cb02376c02d9fc0dec322fb4_Traceguids
0x1400058c9  mov     [rsp+68h+var_30], rax
0x1400058ce  mov     r9, [r9+40h]
0x1400058d2  mov     [rsp+68h+var_38], 0Ch
0x1400058d9  mov     [rsp+68h+var_40], 2
0x1400058e1  mov     [rsp+68h+var_48], 4
0x1400058e6  call    WPP_RECORDER_AND_TRACE_SF_sD
0x1400058eb  jmp     loc_140005859
0x1400058f0  test    rbx, rbx
0x1400058f3  jnz     short loc_140005906
0x1400058f5  lea     rcx, aMissingStreamh; "Missing streamhandle context!"
0x1400058fc  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140005901  jmp     loc_14000586D
0x140005906  or      dword ptr [r8+28h], 4
0x14000590b  jmp     loc_14000585E
```
