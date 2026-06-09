# DwmpGetCompositionTimingInfoEx

- ea: `0x180003030`
- end: `0x18000335c`
- name: `DwmpGetCompositionTimingInfoEx`
- size: `812`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180002fc0`

## callees

- `0x180003030`
- `0x180003370`
- `0x180004594`
- `0x180005b5c`
- `0x18000d0a0`
- `0x18000ddac`
- `0x18000ddc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003239`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003239`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000321e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000321e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18000322b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18000322b`
- `dcomp!__imp_DCompositionGetFrameStatistics` at `0x1800030de`
- `dcomp!__imp_DCompositionGetFrameStatistics` at `0x1800030de`

## pseudocode

```c
__int64 __fastcall DwmpGetCompositionTimingInfoEx(__int64 a1, unsigned int *a2)
{
  __int64 v4; // r8
  unsigned int v5; // edi
  int FrameStatistics; // eax
  int v7; // ebx
  __int64 v8; // rcx
  __int64 result; // rax
  signed int LastError; // eax
  int Src; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v12[5]; // [rsp+34h] [rbp-CCh] BYREF
  int v13; // [rsp+5Ch] [rbp-A4h]
  __int64 v14; // [rsp+60h] [rbp-A0h]
  __int64 v15; // [rsp+68h] [rbp-98h]
  int v16; // [rsp+70h] [rbp-90h]
  __int64 v17; // [rsp+74h] [rbp-8Ch]
  __int64 v18; // [rsp+7Ch] [rbp-84h]
  int v19; // [rsp+84h] [rbp-7Ch]
  __int64 v20; // [rsp+88h] [rbp-78h]
  int v21; // [rsp+90h] [rbp-70h]
  __int64 v22; // [rsp+94h] [rbp-6Ch]
  __int64 v23; // [rsp+A0h] [rbp-60h]
  int v24; // [rsp+A8h] [rbp-58h]
  _OWORD v25[2]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v26; // [rsp+190h] [rbp+90h]
  _BYTE v27[16]; // [rsp+198h] [rbp+98h] BYREF

  Src = 0;
  memset_0(v12, 0, 0x138u);
  if ( (Microsoft_Windows_Dwm_ApiEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      Microsoft_Windows_Dwm_Api_Provider_Context,
      (__int64)ApiGetCompositionTimingInfo_Start,
      v4,
      1,
      (__int64)v27);
  if ( a2 )
  {
    v5 = *a2;
    if ( *a2 == 292 || v5 == 316 )
    {
      if ( a1 )
      {
        v7 = -2147024809;
        DoStackCaptureDirect(-2147024809, 0x32u);
      }
      else
      {
        memset(v25, 0, sizeof(v25));
        v26 = 0;
        if ( Frequency.QuadPart || (SetLastError(0), QueryPerformanceFrequency(&Frequency)) )
        {
          FrameStatistics = DCompositionGetFrameStatistics(v25, 0, 0);
          if ( FrameStatistics < 0 )
          {
            v7 = FrameStatistics | 0x10000000;
            DoStackCaptureDirect(FrameStatistics | 0x10000000, 0x43u);
          }
          else
          {
            v7 = 0;
            v12[0] = *((_QWORD *)&v25[0] + 1);
            v8 = qword_18001F4A0++;
            v12[1] = Frequency.QuadPart * (unsigned __int64)HIDWORD(v25[0]) / DWORD2(v25[0]);
            v12[2] = *((_QWORD *)&v25[0] + 1);
            v12[3] = *(_QWORD *)&v25[0];
            v14 = *(_QWORD *)&v25[0];
            v16 = dword_18001F498;
            v19 = dword_18001F498;
            v21 = dword_18001F498++ - 1;
            v12[4] = qword_18001F4A0;
            v13 = dword_18001F498;
            v15 = v8;
            v17 = v8;
            v18 = v8;
            v20 = qword_18001F4A0 - 2;
            v22 = qword_18001F4A0 - 2;
            v23 = 0;
            v24 = 1;
          }
        }
        else
        {
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError > 0 )
            v7 = (unsigned __int16)LastError | 0x80070000;
          if ( v7 >= 0 )
            v7 = -2003304445;
          DoStackCaptureDirect(v7, 0x3Bu);
        }
      }
    }
    else
    {
      v7 = -2003304304;
      DoStackCaptureDirect(-2003304304, 0x2Au);
    }
  }
  else
  {
    v7 = -2147024809;
    v5 = 0;
    DoStackCaptureDirect(-2147024809, 0x23u);
  }
  if ( (Microsoft_Windows_Dwm_ApiEnableBits & 1) != 0 )
    McTemplateU0q_EtwEventWriteTransfer(Microsoft_Windows_Dwm_Api_Provider_Context, ApiGetCompositionTimingInfo_Stop);
  if ( v7 >= 0 )
  {
    memcpy_0(a2, &Src, v5);
    result = (unsigned int)v7;
    *a2 = v5;
    return result;
  }
  if ( v7 > -2003304300 )
  {
    if ( v7 != -2003304299 )
    {
      if ( v7 == -2003304290 )
        return 2149986309LL;
      if ( v7 != -2003292404 )
        return (unsigned int)v7;
    }
    return 2149986307LL;
  }
  switch ( v7 )
  {
    case -2003304300:
      return 2149986308LL;
    case -2003304304:
      return 2147942424LL;
    case -2003304303:
      return 2149986307LL;
  }
  if ( v7 != -2003304302 )
    return (unsigned int)v7;
  return 2149986306LL;
}

```

## disassembly

```asm
0x180003030  push    rbp
0x180003032  push    rbx
0x180003033  push    rsi
0x180003034  lea     rbp, [rsp-0B0h]
0x18000303c  sub     rsp, 1B0h
0x180003043  mov     rax, cs:__security_cookie
0x18000304a  xor     rax, rsp
0x18000304d  mov     [rbp+0C0h+var_18], rax
0x180003054  mov     rsi, rdx
0x180003057  mov     [rsp+1C0h+arg_10], r14
0x18000305f  mov     rbx, rcx
0x180003062  xor     r14d, r14d
0x180003065  xor     edx, edx; Val
0x180003067  mov     [rsp+1C0h+Src], r14d
0x18000306c  mov     r8d, 138h; Size
0x180003072  lea     rcx, [rsp+1C0h+var_18C]; void *
0x180003077  call    memset_0
0x18000307c  test    cs:Microsoft_Windows_Dwm_ApiEnableBits, 1
0x180003083  jnz     loc_1800032C4
0x180003089  mov     [rsp+1C0h+arg_0], rdi
0x180003091  test    rsi, rsi
0x180003094  jz      loc_180003203
0x18000309a  mov     edi, [rsi]
0x18000309c  cmp     edi, 124h
0x1800030a2  jnz     loc_1800031E4
0x1800030a8  test    rbx, rbx
0x1800030ab  jnz     loc_1800032EE
0x1800030b1  xor     eax, eax
0x1800030b3  xorps   xmm0, xmm0
0x1800030b6  cmp     qword ptr cs:Frequency, rax
0x1800030bd  movups  [rbp+0C0h+var_50], xmm0
0x1800030c1  mov     [rbp+0C0h+var_30], rax
0x1800030c8  movups  [rbp+0C0h+var_40], xmm0
0x1800030cf  jz      loc_18000321C
0x1800030d5  xor     r8d, r8d
0x1800030d8  lea     rcx, [rbp+0C0h+var_50]
0x1800030dc  xor     edx, edx
0x1800030de  call    cs:__imp_DCompositionGetFrameStatistics
0x1800030e4  mov     ebx, eax
0x1800030e6  test    eax, eax
0x1800030e8  js      loc_180003304
0x1800030ee  mov     ecx, dword ptr [rbp+0C0h+var_50+8]
0x1800030f1  xor     edx, edx
0x1800030f3  mov     eax, dword ptr [rbp+0C0h+var_50+0Ch]
0x1800030f6  mov     ebx, r14d
0x1800030f9  mov     r9, cs:qword_18001F4A0
0x180003100  mov     r8d, cs:dword_18001F498
0x180003107  inc     r9
0x18000310a  mov     dword ptr [rsp+1C0h+var_18C+4], eax
0x18000310e  inc     r8d
0x180003111  imul    rax, qword ptr cs:Frequency
0x180003119  mov     dword ptr [rsp+1C0h+var_18C], ecx
0x18000311d  div     rcx
0x180003120  lea     rcx, [r9-1]
0x180003124  mov     cs:qword_18001F4A0, r9
0x18000312b  mov     [rsp+1C0h+var_184], rax
0x180003130  lea     rdx, [r9-2]
0x180003134  mov     rax, [rsp+1C0h+var_18C]
0x180003139  mov     [rsp+1C0h+var_17C], rax
0x18000313e  mov     rax, qword ptr [rbp+0C0h+var_50]
0x180003142  mov     [rsp+1C0h+var_174], rax
0x180003147  mov     [rsp+1C0h+var_160], rax
0x18000314c  lea     eax, [r8-1]
0x180003150  mov     [rsp+1C0h+var_150], eax
0x180003154  mov     [rbp+0C0h+var_13C], eax
0x180003157  lea     eax, [r8-2]
0x18000315b  mov     [rbp+0C0h+var_130], eax
0x18000315e  mov     cs:dword_18001F498, r8d
0x180003165  mov     [rsp+1C0h+var_16C], r9
0x18000316a  mov     [rsp+1C0h+var_164], r8d
0x18000316f  mov     [rsp+1C0h+var_158], rcx
0x180003174  mov     [rsp+1C0h+var_14C], rcx
0x180003179  mov     [rsp+1C0h+var_144], rcx
0x18000317e  mov     [rbp+0C0h+var_138], rdx
0x180003182  mov     [rbp+0C0h+var_12C], rdx
0x180003186  mov     [rbp+0C0h+var_120], r14
0x18000318a  mov     [rbp+0C0h+var_118], 1
0x180003191  test    cs:Microsoft_Windows_Dwm_ApiEnableBits, 1
0x180003198  mov     r14, [rsp+1C0h+arg_10]
0x1800031a0  jnz     loc_180003319
0x1800031a6  test    ebx, ebx
0x1800031a8  js      loc_180003269
0x1800031ae  mov     r8d, edi; Size
0x1800031b1  lea     rdx, [rsp+1C0h+Src]; Src
0x1800031b6  mov     rcx, rsi; void *
0x1800031b9  call    memcpy_0
0x1800031be  mov     eax, ebx
0x1800031c0  mov     [rsi], edi
0x1800031c2  mov     rdi, [rsp+1C0h+arg_0]
0x1800031ca  mov     rcx, [rbp+0C0h+var_18]
0x1800031d1  xor     rcx, rsp; StackCookie
0x1800031d4  call    __security_check_cookie
0x1800031d9  add     rsp, 1B0h
0x1800031e0  pop     rsi
0x1800031e1  pop     rbx
0x1800031e2  pop     rbp
0x1800031e3  retn
0x1800031e4  cmp     edi, 13Ch
0x1800031ea  jz      loc_1800030A8
0x1800031f0  mov     ebx, 88980090h
0x1800031f5  mov     edx, 2Ah ; '*'; unsigned int
0x1800031fa  mov     ecx, ebx; int
0x1800031fc  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x180003201  jmp     short loc_180003191
0x180003203  mov     ebx, 80070057h
0x180003208  mov     edx, 23h ; '#'; unsigned int
0x18000320d  mov     ecx, ebx; int
0x18000320f  mov     edi, r14d
0x180003212  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x180003217  jmp     loc_180003191
0x18000321c  xor     ecx, ecx; dwErrCode
0x18000321e  call    cs:__imp_SetLastError
0x180003224  lea     rcx, Frequency; lpFrequency
0x18000322b  call    cs:__imp_QueryPerformanceFrequency
0x180003231  test    eax, eax
0x180003233  jnz     loc_1800030D5
0x180003239  call    cs:__imp_GetLastError
0x18000323f  mov     ebx, eax
0x180003241  test    eax, eax
0x180003243  jle     short loc_18000324E
0x180003245  movzx   ebx, ax
0x180003248  or      ebx, 80070000h
0x18000324e  test    ebx, ebx
0x180003250  mov     eax, 88980003h
0x180003255  mov     edx, 3Bh ; ';'; unsigned int
0x18000325a  cmovns  ebx, eax
0x18000325d  mov     ecx, ebx; int
0x18000325f  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x180003264  jmp     loc_180003191
0x180003269  cmp     ebx, 88980094h
0x18000326f  jg      short loc_18000329E
0x180003271  jz      loc_180003348
0x180003277  cmp     ebx, 88980090h
0x18000327d  jz      loc_18000333E
0x180003283  cmp     ebx, 88980091h
0x180003289  jz      short loc_1800032BA
0x18000328b  cmp     ebx, 88980092h
0x180003291  jz      loc_180003334
0x180003297  mov     eax, ebx
0x180003299  jmp     loc_1800031C2
0x18000329e  cmp     ebx, 88980095h
0x1800032a4  jz      short loc_1800032BA
0x1800032a6  cmp     ebx, 8898009Eh
0x1800032ac  jz      loc_180003352
0x1800032b2  cmp     ebx, 88982F0Ch
0x1800032b8  jnz     short loc_180003297
0x1800032ba  mov     eax, 80263003h
0x1800032bf  jmp     loc_1800031C2
0x1800032c4  lea     rax, [rbp+0C0h+var_28]
0x1800032cb  mov     r9d, 1
0x1800032d1  lea     rdx, ApiGetCompositionTimingInfo_Start
0x1800032d8  mov     [rsp+1C0h+var_1A0], rax
0x1800032dd  lea     rcx, Microsoft_Windows_Dwm_Api_Provider_Context
0x1800032e4  call    McGenEventWrite_EtwEventWriteTransfer
0x1800032e9  jmp     loc_180003089
0x1800032ee  mov     ebx, 80070057h
0x1800032f3  mov     edx, 32h ; '2'; unsigned int
0x1800032f8  mov     ecx, ebx; int
0x1800032fa  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x1800032ff  jmp     loc_180003191
0x180003304  bts     ebx, 1Ch
0x180003308  mov     edx, 43h ; 'C'; unsigned int
0x18000330d  mov     ecx, ebx; int
0x18000330f  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x180003314  jmp     loc_180003191
0x180003319  mov     r8d, ebx
0x18000331c  lea     rdx, ApiGetCompositionTimingInfo_Stop
0x180003323  lea     rcx, Microsoft_Windows_Dwm_Api_Provider_Context
0x18000332a  call    McTemplateU0q_EtwEventWriteTransfer
0x18000332f  jmp     loc_1800031A6
0x180003334  mov     eax, 80263002h
0x180003339  jmp     loc_1800031C2
0x18000333e  mov     eax, 80070018h
0x180003343  jmp     loc_1800031C2
0x180003348  mov     eax, 80263004h
0x18000334d  jmp     loc_1800031C2
0x180003352  mov     eax, 80263005h
0x180003357  jmp     loc_1800031C2
```
