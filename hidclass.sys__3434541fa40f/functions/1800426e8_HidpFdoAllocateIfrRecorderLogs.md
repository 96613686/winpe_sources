# HidpFdoAllocateIfrRecorderLogs

- ea: `0x1800426e8`
- end: `0x180042a72`
- name: `HidpFdoAllocateIfrRecorderLogs`
- size: `906`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18003a590`

## callees

- `0x18000ddc8`
- `0x180012e50`
- `0x180015044`
- `0x18001d630`
- `0x180027ba0`
- `0x1800426e8`

## import_xrefs

- `WppRecorder!imp_WppRecorderLogCreate` at `0x1800427a1`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x1800428ad`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x1800429ba`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x1800427a1`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x1800428ad`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x1800429ba`

## pseudocode

```c
__int64 __fastcall HidpFdoAllocateIfrRecorderLogs(_QWORD *a1)
{
  char v2; // bl
  unsigned int v3; // eax
  __int64 *v4; // r15
  int v5; // edx
  int v6; // edi
  _UNKNOWN **v7; // r8
  unsigned int v8; // eax
  int v9; // edx
  int v10; // esi
  int v11; // r8d
  __int64 v12; // r9
  unsigned int v13; // eax
  unsigned int v14; // r10d
  __int64 result; // rax
  int v16; // edx
  int v17; // r8d
  unsigned int v18; // edi
  __int64 v19; // r9
  __int64 v20; // [rsp+50h] [rbp-29h] BYREF
  __int64 v21; // [rsp+58h] [rbp-21h]
  __int64 v22; // [rsp+60h] [rbp-19h]
  __int64 v23; // [rsp+68h] [rbp-11h]
  char pszDest[16]; // [rsp+70h] [rbp-9h] BYREF
  __int64 v25; // [rsp+80h] [rbp+7h]

  v20 = 56;
  v2 = 1;
  *(_OWORD *)pszDest = 0;
  v25 = 0x200000001LL;
  pszDest[0] = 0;
  v22 = 0;
  v23 = 0x1000000000LL;
  v21 = 0x33300001000LL;
  v3 = WStrLen(L"\\Device\\_");
  RtlStringCchPrintfA(pszDest, 0x10u, "%ws", a1[33] + 2LL * v3);
  v4 = a1 + 84;
  v6 = imp_WppRecorderLogCreate(WPP_GLOBAL_Control, &v20, a1 + 84);
  v7 = &WPP_RECORDER_INITIALIZED;
  if ( v6 < 0 )
  {
    *v4 = g_RecorderLog;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
      || (LOBYTE(v5) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
    {
      LOBYTE(v5) = 0;
    }
    if ( (_BYTE)v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qL(
        WPP_GLOBAL_Control->AttachedDevice,
        v5,
        (_DWORD)v7,
        g_RecorderLog,
        2,
        2,
        28,
        (__int64)WPP_7228c8f8fc8f39095d4c835c051ae1a4_Traceguids,
        *a1,
        v6);
    }
    TraceLoggingWppRecorderFailed((unsigned int)v6);
  }
  v20 = 56;
  pszDest[0] = 0;
  HIDWORD(v23) = 16;
  v22 = 0;
  LOBYTE(v23) = 0;
  v25 = 0x200000002LL;
  v21 = 0x33300001000LL;
  v8 = WStrLen(L"\\Device\\_");
  RtlStringCchPrintfA(pszDest, 0x10u, "%ws(DI)", a1[33] + 2LL * v8);
  v10 = imp_WppRecorderLogCreate(WPP_GLOBAL_Control, &v20, a1 + 85);
  if ( v10 < 0 )
  {
    v12 = *v4;
    a1[85] = *v4;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
      || (LOBYTE(v9) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
    {
      LOBYTE(v9) = 0;
    }
    if ( (_BYTE)v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qL(
        WPP_GLOBAL_Control->AttachedDevice,
        v9,
        v11,
        v12,
        2,
        2,
        29,
        (__int64)WPP_7228c8f8fc8f39095d4c835c051ae1a4_Traceguids,
        *a1,
        v10);
    }
    TraceLoggingWppRecorderFailed((unsigned int)v10);
  }
  v20 = 56;
  HIDWORD(v23) = 16;
  pszDest[0] = 0;
  v22 = 0;
  LOBYTE(v23) = 0;
  v25 = 0x200000002LL;
  v21 = 0x33300001000LL;
  v13 = WStrLen(L"\\Device\\_");
  RtlStringCchPrintfA(pszDest, v14, "%ws(IR)", a1[33] + 2LL * v13);
  result = imp_WppRecorderLogCreate(WPP_GLOBAL_Control, &v20, a1 + 86);
  v18 = result;
  if ( (int)result < 0 )
  {
    v19 = *v4;
    a1[86] = *v4;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v2 = 0;
    }
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v16) = v2;
      LOBYTE(v17) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qL(
        WPP_GLOBAL_Control->AttachedDevice,
        v16,
        v17,
        v19,
        2,
        2,
        30,
        (__int64)WPP_7228c8f8fc8f39095d4c835c051ae1a4_Traceguids,
        *a1,
        result);
    }
    return TraceLoggingWppRecorderFailed(v18);
  }
  return result;
}

```

## disassembly

```asm
0x1800426e8  push    rbp
0x1800426ea  push    rbx
0x1800426eb  push    rsi
0x1800426ec  push    rdi
0x1800426ed  push    r12
0x1800426ef  push    r13
0x1800426f1  push    r14
0x1800426f3  push    r15
0x1800426f5  lea     rbp, [rsp-1Fh]
0x1800426fa  sub     rsp, 98h
0x180042701  mov     rax, cs:__security_cookie
0x180042708  xor     rax, rsp
0x18004270b  mov     [rbp+57h+var_48], rax
0x18004270f  xor     eax, eax
0x180042711  xorps   xmm0, xmm0
0x180042714  xor     r12d, r12d
0x180042717  mov     [rbp+57h+var_50], rax
0x18004271b  movups  [rbp+57h+var_80], xmm0
0x18004271f  mov     r14, rcx
0x180042722  lea     rcx, aDevice; "\\Device\\_"
0x180042729  movups  [rbp+57h+var_70], xmm0
0x18004272d  lea     esi, [rax+10h]
0x180042730  mov     qword ptr [rbp+57h+var_80], 38h ; '8'
0x180042738  lea     r13d, [rax+2]
0x18004273c  mov     dword ptr [rbp+57h+var_70+0Ch], esi
0x18004273f  lea     ebx, [rax+1]
0x180042742  mov     dword ptr [rbp+57h+var_50+4], r13d
0x180042746  movups  xmmword ptr [rbp+57h+pszDest], xmm0
0x18004274a  mov     dword ptr [rbp+57h+var_50], ebx
0x18004274d  mov     [rbp+57h+pszDest], r12b
0x180042751  mov     qword ptr [rbp+57h+var_70], r12
0x180042755  mov     byte ptr [rbp+57h+var_70+8], r12b
0x180042759  mov     dword ptr [rbp+57h+var_80+8], 1000h
0x180042760  mov     dword ptr [rbp+57h+var_80+0Ch], 333h
0x180042767  call    WStrLen
0x18004276c  mov     r8d, eax
0x18004276f  lea     rcx, [rbp+57h+pszDest]; pszDest
0x180042773  mov     rax, [r14+108h]
0x18004277a  mov     edx, esi; cchDest
0x18004277c  lea     r9, [rax+r8*2]
0x180042780  lea     r8, aWs; "%ws"
0x180042787  call    RtlStringCchPrintfA
0x18004278c  mov     rcx, cs:WPP_GLOBAL_Control
0x180042793  lea     r15, [r14+2A0h]
0x18004279a  mov     r8, r15
0x18004279d  lea     rdx, [rbp+57h+var_80]
0x1800427a1  call    cs:__imp_imp_WppRecorderLogCreate
0x1800427a8  nop     dword ptr [rax+rax+00h]
0x1800427ad  mov     edi, eax
0x1800427af  lea     r8, WPP_RECORDER_INITIALIZED
0x1800427b6  lea     rax, WPP_GLOBAL_Control
0x1800427bd  lea     r10, WPP_7228c8f8fc8f39095d4c835c051ae1a4_Traceguids
0x1800427c4  test    edi, edi
0x1800427c6  jns     short loc_18004283E
0x1800427c8  mov     rcx, cs:g_RecorderLog
0x1800427cf  mov     [r15], rcx
0x1800427d2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800427d9  cmp     rcx, rax
0x1800427dc  jz      short loc_1800427EE
0x1800427de  mov     eax, [rcx+2Ch]
0x1800427e1  test    r13b, al
0x1800427e4  jz      short loc_1800427EE
0x1800427e6  mov     dl, bl
0x1800427e8  cmp     [rcx+29h], r13b
0x1800427ec  jnb     short loc_1800427F1
0x1800427ee  mov     dl, r12b
0x1800427f1  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x1800427f8  setnz   r8b
0x1800427fc  test    dl, dl
0x1800427fe  jnz     short loc_180042805
0x180042800  test    r8b, r8b
0x180042803  jz      short loc_180042837
0x180042805  mov     rax, [r14]
0x180042808  mov     r9, cs:g_RecorderLog
0x18004280f  mov     rcx, [rcx+18h]
0x180042813  mov     [rsp+0D0h+var_88], edi
0x180042817  mov     [rsp+0D0h+var_90], rax
0x18004281c  mov     [rsp+0D0h+var_98], r10
0x180042821  mov     [rsp+0D0h+var_A0], 1Ch
0x180042828  mov     [rsp+0D0h+var_A8], r13d
0x18004282d  mov     [rsp+0D0h+var_B0], r13b
0x180042832  call    WPP_RECORDER_AND_TRACE_SF_qL
0x180042837  mov     ecx, edi
0x180042839  call    TraceLoggingWppRecorderFailed
0x18004283e  lea     rcx, aDevice; "\\Device\\_"
0x180042845  mov     qword ptr [rbp+57h+var_80], 38h ; '8'
0x18004284d  mov     [rbp+57h+pszDest], r12b
0x180042851  mov     dword ptr [rbp+57h+var_70+0Ch], esi
0x180042854  mov     qword ptr [rbp+57h+var_70], r12
0x180042858  mov     byte ptr [rbp+57h+var_70+8], r12b
0x18004285c  mov     dword ptr [rbp+57h+var_50], r13d
0x180042860  mov     dword ptr [rbp+57h+var_50+4], r13d
0x180042864  mov     dword ptr [rbp+57h+var_80+8], 1000h
0x18004286b  mov     dword ptr [rbp+57h+var_80+0Ch], 333h
0x180042872  call    WStrLen
0x180042877  mov     r8d, eax
0x18004287a  lea     rcx, [rbp+57h+pszDest]; pszDest
0x18004287e  mov     rax, [r14+108h]
0x180042885  mov     rdx, rsi; cchDest
0x180042888  lea     r9, [rax+r8*2]
0x18004288c  lea     r8, aWsDi; "%ws(DI)"
0x180042893  call    RtlStringCchPrintfA
0x180042898  mov     rcx, cs:WPP_GLOBAL_Control
0x18004289f  lea     rdi, [r14+2A8h]
0x1800428a6  mov     r8, rdi
0x1800428a9  lea     rdx, [rbp+57h+var_80]
0x1800428ad  call    cs:__imp_imp_WppRecorderLogCreate
0x1800428b4  nop     dword ptr [rax+rax+00h]
0x1800428b9  mov     esi, eax
0x1800428bb  test    eax, eax
0x1800428bd  jns     loc_180042944
0x1800428c3  mov     r9, [r15]
0x1800428c6  mov     [rdi], r9
0x1800428c9  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800428d0  lea     rax, WPP_GLOBAL_Control
0x1800428d7  cmp     r10, rax
0x1800428da  jz      short loc_1800428ED
0x1800428dc  mov     ecx, [r10+2Ch]
0x1800428e0  test    r13b, cl
0x1800428e3  jz      short loc_1800428ED
0x1800428e5  mov     dl, bl
0x1800428e7  cmp     [r10+29h], r13b
0x1800428eb  jnb     short loc_1800428F0
0x1800428ed  mov     dl, r12b
0x1800428f0  lea     rax, WPP_RECORDER_INITIALIZED
0x1800428f7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800428fe  setnz   r8b
0x180042902  test    dl, dl
0x180042904  jnz     short loc_18004290B
0x180042906  test    r8b, r8b
0x180042909  jz      short loc_18004293D
0x18004290b  mov     rax, [r14]
0x18004290e  mov     rcx, [r10+18h]
0x180042912  mov     [rsp+0D0h+var_88], esi
0x180042916  mov     [rsp+0D0h+var_90], rax
0x18004291b  lea     rax, WPP_7228c8f8fc8f39095d4c835c051ae1a4_Traceguids
0x180042922  mov     [rsp+0D0h+var_98], rax
0x180042927  mov     [rsp+0D0h+var_A0], 1Dh
0x18004292e  mov     [rsp+0D0h+var_A8], r13d
0x180042933  mov     [rsp+0D0h+var_B0], r13b
0x180042938  call    WPP_RECORDER_AND_TRACE_SF_qL
0x18004293d  mov     ecx, esi
0x18004293f  call    TraceLoggingWppRecorderFailed
0x180042944  mov     r10d, 10h
0x18004294a  mov     qword ptr [rbp+57h+var_80], 38h ; '8'
0x180042952  lea     rcx, aDevice; "\\Device\\_"
0x180042959  mov     dword ptr [rbp+57h+var_70+0Ch], r10d
0x18004295d  mov     [rbp+57h+pszDest], r12b
0x180042961  mov     qword ptr [rbp+57h+var_70], r12
0x180042965  mov     byte ptr [rbp+57h+var_70+8], r12b
0x180042969  mov     dword ptr [rbp+57h+var_50], r13d
0x18004296d  mov     dword ptr [rbp+57h+var_50+4], r13d
0x180042971  mov     dword ptr [rbp+57h+var_80+8], 1000h
0x180042978  mov     dword ptr [rbp+57h+var_80+0Ch], 333h
0x18004297f  call    WStrLen
0x180042984  mov     r8d, eax
0x180042987  lea     rcx, [rbp+57h+pszDest]; pszDest
0x18004298b  mov     rax, [r14+108h]
0x180042992  mov     edx, r10d; cchDest
0x180042995  lea     r9, [rax+r8*2]
0x180042999  lea     r8, aWsIr; "%ws(IR)"
0x1800429a0  call    RtlStringCchPrintfA
0x1800429a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800429ac  lea     rsi, [r14+2B0h]
0x1800429b3  mov     r8, rsi
0x1800429b6  lea     rdx, [rbp+57h+var_80]
0x1800429ba  call    cs:__imp_imp_WppRecorderLogCreate
0x1800429c1  nop     dword ptr [rax+rax+00h]
0x1800429c6  mov     edi, eax
0x1800429c8  test    eax, eax
0x1800429ca  jns     loc_180042A51
0x1800429d0  mov     r9, [r15]
0x1800429d3  mov     [rsi], r9
0x1800429d6  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800429dd  lea     rax, WPP_GLOBAL_Control
0x1800429e4  cmp     r10, rax
0x1800429e7  jz      short loc_1800429F8
0x1800429e9  mov     ecx, [r10+2Ch]
0x1800429ed  test    r13b, cl
0x1800429f0  jz      short loc_1800429F8
0x1800429f2  cmp     [r10+29h], r13b
0x1800429f6  jnb     short loc_1800429FB
0x1800429f8  mov     bl, r12b
0x1800429fb  lea     rax, WPP_RECORDER_INITIALIZED
0x180042a02  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180042a09  setnz   r8b
0x180042a0d  test    bl, bl
0x180042a0f  jnz     short loc_180042A16
0x180042a11  test    r8b, r8b
0x180042a14  jz      short loc_180042A4A
0x180042a16  mov     rax, [r14]
0x180042a19  mov     dl, bl
0x180042a1b  mov     rcx, [r10+18h]
0x180042a1f  mov     [rsp+0D0h+var_88], edi
0x180042a23  mov     [rsp+0D0h+var_90], rax
0x180042a28  lea     rax, WPP_7228c8f8fc8f39095d4c835c051ae1a4_Traceguids
0x180042a2f  mov     [rsp+0D0h+var_98], rax
0x180042a34  mov     [rsp+0D0h+var_A0], 1Eh
0x180042a3b  mov     [rsp+0D0h+var_A8], r13d
0x180042a40  mov     [rsp+0D0h+var_B0], r13b
0x180042a45  call    WPP_RECORDER_AND_TRACE_SF_qL
0x180042a4a  mov     ecx, edi
0x180042a4c  call    TraceLoggingWppRecorderFailed
0x180042a51  mov     rcx, [rbp+57h+var_48]
0x180042a55  xor     rcx, rsp; StackCookie
0x180042a58  call    __security_check_cookie
0x180042a5d  add     rsp, 98h
0x180042a64  pop     r15
0x180042a66  pop     r14
0x180042a68  pop     r13
0x180042a6a  pop     r12
0x180042a6c  pop     rdi
0x180042a6d  pop     rsi
0x180042a6e  pop     rbx
0x180042a6f  pop     rbp
0x180042a70  retn
```
