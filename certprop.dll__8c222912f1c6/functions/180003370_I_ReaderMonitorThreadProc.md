# I_ReaderMonitorThreadProc

- ea: `0x180003370`
- end: `0x180003508`
- name: `I_ReaderMonitorThreadProc`
- size: `408`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180003370`
- `0x180003510`
- `0x180004600`
- `0x180018b58`
- `0x180018bb4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180003442`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000344b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180003442`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000344b`

## pseudocode

```c
__int64 __fastcall I_ReaderMonitorThreadProc(PVOID Parameter)
{
  ULONGLONG TickCount64; // rsi
  int v2; // ebp
  unsigned int v4; // eax
  STRSAFE_LPSTR v5; // rcx
  unsigned int v6; // ebx
  ULONGLONG v8; // rax
  int v9; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v10; // [rsp+58h] [rbp+10h] BYREF

  TickCount64 = 0;
  v9 = 1;
  v2 = 0;
  v10 = 0;
  WppTraceIndent(Parameter, 0);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 234, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  do
  {
    while ( 1 )
    {
      v4 = I_ReaderMonitorWorker(Parameter, &v9, &v10);
      v6 = v4;
      if ( v4 == -2146435043 )
        goto LABEL_3;
      if ( !v4 )
        break;
      if ( v4 != -2146435054 && v4 != -2146435042 )
      {
        if ( !TickCount64 )
          TickCount64 = GetTickCount64();
        v8 = GetTickCount64();
        v5 = (STRSAFE_LPSTR)(v8 - TickCount64);
        if ( v8 - TickCount64 <= 0x36EE80 )
        {
          if ( (unsigned int)++v2 >= 3 )
            goto LABEL_4;
        }
        else
        {
          TickCount64 = v8;
          v2 = 1;
        }
      }
LABEL_3:
      if ( !v9 )
        goto LABEL_4;
    }
    WppTraceIndent(v5, 2);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        235,
        &WPP_173052b9a503333cb537dada0074ae31_Traceguids,
        WPP_pszIndent);
    }
  }
  while ( v9 );
  v6 = v10;
LABEL_4:
  WppTraceIndent(v5, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      236,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      v6);
  }
  return v6;
}

```

## disassembly

```asm
0x180003370  mov     [rsp+arg_10], rbx
0x180003375  mov     [rsp+arg_18], rbp
0x18000337a  push    rsi
0x18000337b  push    rdi
0x18000337c  push    r14
0x18000337e  sub     rsp, 30h
0x180003382  xor     esi, esi
0x180003384  mov     [rsp+48h+arg_0], 1
0x18000338c  xor     ebp, ebp
0x18000338e  mov     [rsp+48h+arg_8], esi
0x180003392  xor     edx, edx
0x180003394  mov     rdi, rcx
0x180003397  call    WppTraceIndent
0x18000339c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033a3  lea     r14, WPP_GLOBAL_Control
0x1800033aa  cmp     rcx, r14
0x1800033ad  jnz     short loc_180003401
0x1800033af  nop
0x1800033b0  lea     r8, [rsp+48h+arg_8]
0x1800033b5  mov     rcx, rdi
0x1800033b8  lea     rdx, [rsp+48h+arg_0]
0x1800033bd  call    I_ReaderMonitorWorker
0x1800033c2  mov     ebx, eax
0x1800033c4  cmp     eax, 8010001Dh
0x1800033c9  jnz     short loc_18000342B
0x1800033cb  cmp     [rsp+48h+arg_0], 0
0x1800033d0  jnz     short loc_1800033B0
0x1800033d2  mov     edx, 1
0x1800033d7  call    WppTraceIndent
0x1800033dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033e3  cmp     rcx, r14
0x1800033e6  jnz     loc_1800034CF
0x1800033ec  mov     rbp, [rsp+48h+arg_18]
0x1800033f1  mov     eax, ebx
0x1800033f3  mov     rbx, [rsp+48h+arg_10]
0x1800033f8  add     rsp, 30h
0x1800033fc  pop     r14
0x1800033fe  pop     rdi
0x1800033ff  pop     rsi
0x180003400  retn
0x180003401  test    byte ptr [rcx+1Ch], 2
0x180003405  jz      short loc_1800033B0
0x180003407  cmp     byte ptr [rcx+19h], 5
0x18000340b  jb      short loc_1800033B0
0x18000340d  mov     r9, cs:WPP_pszIndent
0x180003414  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18000341b  mov     rcx, [rcx+10h]
0x18000341f  mov     edx, 0EAh
0x180003424  call    WPP_SF_s
0x180003429  jmp     short loc_1800033B0
0x18000342b  test    eax, eax
0x18000342d  jz      short loc_18000347D
0x18000342f  cmp     eax, 80100012h
0x180003434  jz      short loc_1800033CB
0x180003436  cmp     eax, 8010001Eh
0x18000343b  jz      short loc_1800033CB
0x18000343d  test    rsi, rsi
0x180003440  jnz     short loc_18000344B
0x180003442  call    cs:__imp_GetTickCount64
0x180003448  mov     rsi, rax
0x18000344b  call    cs:__imp_GetTickCount64
0x180003451  mov     rcx, rax
0x180003454  sub     rcx, rsi
0x180003457  cmp     rcx, 36EE80h
0x18000345e  jbe     short loc_18000346D
0x180003460  mov     rsi, rax
0x180003463  mov     ebp, 1
0x180003468  jmp     loc_1800033CB
0x18000346d  inc     ebp
0x18000346f  cmp     ebp, 3
0x180003472  jnb     loc_1800033D2
0x180003478  jmp     loc_1800033CB
0x18000347d  mov     edx, 2
0x180003482  call    WppTraceIndent
0x180003487  mov     rcx, cs:WPP_GLOBAL_Control
0x18000348e  cmp     rcx, r14
0x180003491  jz      short loc_1800034BB
0x180003493  test    byte ptr [rcx+1Ch], 1
0x180003497  jz      short loc_1800034BB
0x180003499  cmp     byte ptr [rcx+19h], 4
0x18000349d  jb      short loc_1800034BB
0x18000349f  mov     r9, cs:WPP_pszIndent
0x1800034a6  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x1800034ad  mov     rcx, [rcx+10h]
0x1800034b1  mov     edx, 0EBh
0x1800034b6  call    WPP_SF_s
0x1800034bb  cmp     [rsp+48h+arg_0], 0
0x1800034c0  jnz     loc_1800033B0
0x1800034c6  mov     ebx, [rsp+48h+arg_8]
0x1800034ca  jmp     loc_1800033D2
0x1800034cf  test    byte ptr [rcx+1Ch], 2
0x1800034d3  jz      loc_1800033EC
0x1800034d9  cmp     byte ptr [rcx+19h], 5
0x1800034dd  jb      loc_1800033EC
0x1800034e3  mov     r9, cs:WPP_pszIndent
0x1800034ea  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x1800034f1  mov     rcx, [rcx+10h]
0x1800034f5  mov     edx, 0ECh
0x1800034fa  mov     [rsp+48h+var_28], ebx
0x1800034fe  call    WPP_SF_sD
0x180003503  jmp     loc_1800033EC
```
