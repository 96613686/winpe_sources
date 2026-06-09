# StopMeasuringTimeForAuth

- ea: `0x180018950`
- end: `0x180018a7d`
- name: `StopMeasuringTimeForAuth`
- size: `301`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001ba00`
- `0x180022c30`

## callees

- `0x180004710`
- `0x180004f40`
- `0x180005440`
- `0x180007f60`
- `0x180018950`
- `0x1800214f0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180018990`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180018990`

## pseudocode

```c
__int64 __fastcall StopMeasuringTimeForAuth(_DWORD *a1)
{
  unsigned int v1; // esi
  DWORD TickCount; // edi
  __int64 result; // rax
  __int64 v5; // rcx
  int v6; // edi

  v1 = a1[5];
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 49, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids);
  TickCount = GetTickCount();
  result = (unsigned int)a1[605];
  if ( TickCount >= (unsigned int)result )
  {
    v5 = (unsigned int)a1[606];
    v6 = TickCount - result;
    result = (unsigned int)(v5 + v6);
    if ( (unsigned int)result >= (unsigned int)v5 )
    {
      ++a1[607];
      a1[606] = result;
      if ( (byte_18003DF42 & 1) != 0 )
        McTemplateU0q_EtwEventWriteTransfer(v5, (__int64)AuthPerfStop, v1);
      if ( (byte_18003DF41 & 0x10) != 0 )
        McTemplateU0qq_EtwEventWriteTransfer(v5, (__int64)AuthTimeTaken, v1, v6);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x200) != 0 )
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 50, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids, v1, v6);
      result = (unsigned int)(a1[606] / a1[607]);
      a1[42] = result;
    }
  }
  a1[605] = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    return WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 51, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids, 0);
  return result;
}

```

## disassembly

```asm
0x180018950  push    rbx
0x180018952  push    rbp
0x180018953  push    rsi
0x180018954  push    rdi
0x180018955  sub     rsp, 38h
0x180018959  mov     esi, [rcx+14h]
0x18001895c  mov     rbx, rcx
0x18001895f  mov     rcx, cs:WPP_GLOBAL_Control
0x180018966  lea     rbp, WPP_GLOBAL_Control
0x18001896d  cmp     rcx, rbp
0x180018970  jz      short loc_180018990
0x180018972  test    dword ptr [rcx+44h], 800h
0x180018979  jz      short loc_180018990
0x18001897b  mov     rcx, [rcx+38h]
0x18001897f  lea     r8, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids
0x180018986  mov     edx, 31h ; '1'
0x18001898b  call    WPP_SF_
0x180018990  call    cs:__imp_GetTickCount
0x180018996  mov     edi, eax
0x180018998  mov     eax, [rbx+974h]
0x18001899e  cmp     edi, eax
0x1800189a0  jb      loc_180018A3D
0x1800189a6  mov     ecx, [rbx+978h]
0x1800189ac  sub     edi, eax
0x1800189ae  lea     eax, [rcx+rdi]
0x1800189b1  cmp     eax, ecx
0x1800189b3  jb      loc_180018A3D
0x1800189b9  inc     dword ptr [rbx+97Ch]
0x1800189bf  mov     [rbx+978h], eax
0x1800189c5  test    cs:byte_18003DF42, 1
0x1800189cc  jz      short loc_1800189DD
0x1800189ce  mov     r8d, esi
0x1800189d1  lea     rdx, AuthPerfStop
0x1800189d8  call    McTemplateU0q_EtwEventWriteTransfer
0x1800189dd  test    cs:byte_18003DF41, 10h
0x1800189e4  jz      short loc_1800189F8
0x1800189e6  mov     r9d, edi
0x1800189e9  lea     rdx, AuthTimeTaken
0x1800189f0  mov     r8d, esi
0x1800189f3  call    McTemplateU0qq_EtwEventWriteTransfer
0x1800189f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800189ff  cmp     rcx, rbp
0x180018a02  jz      short loc_180018A29
0x180018a04  test    dword ptr [rcx+44h], 200h
0x180018a0b  jz      short loc_180018A29
0x180018a0d  mov     rcx, [rcx+38h]
0x180018a11  lea     r8, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids
0x180018a18  mov     edx, 32h ; '2'
0x180018a1d  mov     [rsp+58h+var_38], edi
0x180018a21  mov     r9d, esi
0x180018a24  call    WPP_SF_dd
0x180018a29  mov     eax, [rbx+978h]
0x180018a2f  xor     edx, edx
0x180018a31  div     dword ptr [rbx+97Ch]
0x180018a37  mov     [rbx+0A8h], eax
0x180018a3d  mov     dword ptr [rbx+974h], 0
0x180018a47  mov     rcx, cs:WPP_GLOBAL_Control
0x180018a4e  cmp     rcx, rbp
0x180018a51  jz      short loc_180018A74
0x180018a53  test    dword ptr [rcx+44h], 800h
0x180018a5a  jz      short loc_180018A74
0x180018a5c  mov     rcx, [rcx+38h]
0x180018a60  lea     r8, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids
0x180018a67  mov     edx, 33h ; '3'
0x180018a6c  xor     r9d, r9d
0x180018a6f  call    WPP_SF_D
0x180018a74  add     rsp, 38h
0x180018a78  pop     rdi
0x180018a79  pop     rsi
0x180018a7a  pop     rbp
0x180018a7b  pop     rbx
0x180018a7c  retn
```
