# I_ReaderListReadCertsFromCard

- ea: `0x180005e10`
- end: `0x180005ffc`
- name: `I_ReaderListReadCertsFromCard`
- size: `492`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800115c0`
- `0x180011c10`

## callees

- `0x180004600`
- `0x180005e10`
- `0x180010d90`
- `0x180018b58`
- `0x180018bb4`
- `0x18001e4bc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180005f63`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180005f63`

## pseudocode

```c
__int64 __fastcall I_ReaderListReadCertsFromCard(__int64 a1, __int64 a2)
{
  unsigned int v3; // edi
  STRSAFE_LPSTR v5; // rcx
  __int64 v6; // rdx
  unsigned int v7; // eax
  int v9; // [rsp+60h] [rbp+8h] BYREF

  v3 = 0;
  v9 = 0;
  WppTraceIndent(a1, 0);
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 170, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  if ( *(_DWORD *)(a1 + 24) != 1 )
  {
    if ( *(_DWORD *)(a1 + 24) != 2 )
      goto LABEL_27;
    goto LABEL_7;
  }
  if ( *(_DWORD *)(a2 + 12) == 1024 )
  {
LABEL_7:
    if ( *(_QWORD *)(a2 + 88) )
    {
      v7 = I_CollectCertsUsingCng(a1, a2, &v9);
      goto LABEL_22;
    }
    if ( !*(_QWORD *)(a2 + 80) )
    {
      WppTraceIndent(v5, 2);
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 3u )
      {
        v6 = 172;
LABEL_19:
        WPP_SF_s(*((_QWORD *)v5 + 2), v6, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
        goto LABEL_27;
      }
      goto LABEL_27;
    }
LABEL_20:
    v7 = I_CollectCertsUsingCapi(a1, a2, &v9);
LABEL_22:
    *(_DWORD *)(a2 + 144) = 1;
    *(_DWORD *)(a2 + 152) = 0;
    v3 = v7;
    EventActivityIdControl(1u, (LPGUID)(a2 + 184));
    if ( v3 )
    {
      WppTraceIndent(v5, 2);
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 3u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          173,
          (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
          WPP_pszIndent,
          v3);
      }
    }
    goto LABEL_27;
  }
  if ( *(_QWORD *)(a2 + 80) )
    goto LABEL_20;
  WppTraceIndent(v5, 2);
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 3u )
  {
    v6 = 171;
    goto LABEL_19;
  }
LABEL_27:
  WppTraceIndent(v5, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      174,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      v3);
  }
  return v3;
}

```

## disassembly

```asm
0x180005e10  push    rbx
0x180005e12  push    rbp
0x180005e13  push    rsi
0x180005e14  push    rdi
0x180005e15  sub     rsp, 38h
0x180005e19  mov     rsi, rdx
0x180005e1c  xor     edi, edi
0x180005e1e  xor     edx, edx
0x180005e20  mov     [rsp+58h+arg_0], edi
0x180005e24  mov     rbx, rcx
0x180005e27  call    WppTraceIndent
0x180005e2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e33  lea     rbp, WPP_GLOBAL_Control
0x180005e3a  cmp     rcx, rbp
0x180005e3d  jz      short loc_180005E67
0x180005e3f  test    byte ptr [rcx+1Ch], 2
0x180005e43  jz      short loc_180005E67
0x180005e45  cmp     byte ptr [rcx+19h], 5
0x180005e49  jb      short loc_180005E67
0x180005e4b  mov     r9, cs:WPP_pszIndent
0x180005e52  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180005e59  mov     rcx, [rcx+10h]
0x180005e5d  mov     edx, 0AAh
0x180005e62  call    WPP_SF_s
0x180005e67  mov     eax, [rbx+18h]
0x180005e6a  sub     eax, 1
0x180005e6d  jz      short loc_180005EC1
0x180005e6f  cmp     eax, 1
0x180005e72  jnz     loc_180005FAF
0x180005e78  cmp     [rsi+58h], rdi
0x180005e7c  jnz     loc_180005F31
0x180005e82  cmp     [rsi+50h], rdi
0x180005e86  jnz     loc_180005F1F
0x180005e8c  mov     edx, 2
0x180005e91  call    WppTraceIndent
0x180005e96  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e9d  cmp     rcx, rbp
0x180005ea0  jz      loc_180005FAF
0x180005ea6  test    byte ptr [rcx+1Ch], 1
0x180005eaa  jz      loc_180005FAF
0x180005eb0  cmp     byte ptr [rcx+19h], 3
0x180005eb4  jb      loc_180005FAF
0x180005eba  mov     edx, 0ACh
0x180005ebf  jmp     short loc_180005F03
0x180005ec1  cmp     dword ptr [rsi+0Ch], 400h
0x180005ec8  jz      short loc_180005E78
0x180005eca  cmp     [rsi+50h], rdi
0x180005ece  jnz     short loc_180005F1F
0x180005ed0  mov     edx, 2
0x180005ed5  call    WppTraceIndent
0x180005eda  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ee1  cmp     rcx, rbp
0x180005ee4  jz      loc_180005FAF
0x180005eea  test    byte ptr [rcx+1Ch], 1
0x180005eee  jz      loc_180005FAF
0x180005ef4  cmp     byte ptr [rcx+19h], 3
0x180005ef8  jb      loc_180005FAF
0x180005efe  mov     edx, 0ABh
0x180005f03  mov     r9, cs:WPP_pszIndent
0x180005f0a  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180005f11  mov     rcx, [rcx+10h]
0x180005f15  call    WPP_SF_s
0x180005f1a  jmp     loc_180005FAF
0x180005f1f  lea     r8, [rsp+58h+arg_0]
0x180005f24  mov     rdx, rsi
0x180005f27  mov     rcx, rbx
0x180005f2a  call    I_CollectCertsUsingCapi
0x180005f2f  jmp     short loc_180005F41
0x180005f31  lea     r8, [rsp+58h+arg_0]
0x180005f36  mov     rdx, rsi
0x180005f39  mov     rcx, rbx
0x180005f3c  call    I_CollectCertsUsingCng
0x180005f41  lea     rdx, [rsi+0B8h]; ActivityId
0x180005f48  mov     dword ptr [rsi+90h], 1
0x180005f52  mov     ecx, 1; ControlCode
0x180005f57  mov     dword ptr [rsi+98h], 0
0x180005f61  mov     edi, eax
0x180005f63  call    cs:__imp_EventActivityIdControl
0x180005f69  test    edi, edi
0x180005f6b  jz      short loc_180005FAF
0x180005f6d  mov     edx, 2
0x180005f72  call    WppTraceIndent
0x180005f77  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f7e  cmp     rcx, rbp
0x180005f81  jz      short loc_180005FAF
0x180005f83  test    byte ptr [rcx+1Ch], 1
0x180005f87  jz      short loc_180005FAF
0x180005f89  cmp     byte ptr [rcx+19h], 3
0x180005f8d  jb      short loc_180005FAF
0x180005f8f  mov     r9, cs:WPP_pszIndent
0x180005f96  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180005f9d  mov     rcx, [rcx+10h]
0x180005fa1  mov     edx, 0ADh
0x180005fa6  mov     [rsp+58h+var_38], edi
0x180005faa  call    WPP_SF_sD
0x180005faf  mov     edx, 1
0x180005fb4  call    WppTraceIndent
0x180005fb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180005fc0  cmp     rcx, rbp
0x180005fc3  jz      short loc_180005FF1
0x180005fc5  test    byte ptr [rcx+1Ch], 2
0x180005fc9  jz      short loc_180005FF1
0x180005fcb  cmp     byte ptr [rcx+19h], 5
0x180005fcf  jb      short loc_180005FF1
0x180005fd1  mov     r9, cs:WPP_pszIndent
0x180005fd8  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180005fdf  mov     rcx, [rcx+10h]
0x180005fe3  mov     edx, 0AEh
0x180005fe8  mov     [rsp+58h+var_38], edi
0x180005fec  call    WPP_SF_sD
0x180005ff1  mov     eax, edi
0x180005ff3  add     rsp, 38h
0x180005ff7  pop     rdi
0x180005ff8  pop     rsi
0x180005ff9  pop     rbp
0x180005ffa  pop     rbx
0x180005ffb  retn
```
