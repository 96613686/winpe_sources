# CfReportProviderProgress2

- ea: `0x1800032a0`
- end: `0x1800038ee`
- name: `CfReportProviderProgress2`
- size: `1614`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003270`

## callees

- `0x180001aa0`
- `0x18000231e`
- `0x1800032a0`
- `0x18000bb10`
- `0x18000c024`
- `0x180012c28`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800033db`
- `ntdll!RtlNtStatusToDosError` at `0x180003475`
- `ntdll!RtlNtStatusToDosError` at `0x180003509`
- `ntdll!RtlNtStatusToDosError` at `0x18000359d`
- `ntdll!RtlNtStatusToDosError` at `0x180003631`
- `ntdll!RtlNtStatusToDosError` at `0x1800036c5`
- `ntdll!RtlNtStatusToDosError` at `0x180003759`
- `ntdll!RtlNtStatusToDosError` at `0x1800037f2`
- `ntdll!RtlNtStatusToDosError` at `0x1800033db`
- `ntdll!RtlNtStatusToDosError` at `0x180003475`
- `ntdll!RtlNtStatusToDosError` at `0x180003509`
- `ntdll!RtlNtStatusToDosError` at `0x18000359d`
- `ntdll!RtlNtStatusToDosError` at `0x180003631`
- `ntdll!RtlNtStatusToDosError` at `0x1800036c5`
- `ntdll!RtlNtStatusToDosError` at `0x180003759`
- `ntdll!RtlNtStatusToDosError` at `0x1800037f2`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800032fb`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800032fb`
- `FLTLIB!FilterSendMessage` at `0x18000384d`
- `FLTLIB!FilterSendMessage` at `0x18000384d`

## string_xrefs

- `0x18000349b`: `SetCldMsgCommand Failed`
- `0x18000377f`: `SetCldDsMsgProviderProgressCompleted Failed`

## pseudocode

```c
__int64 __fastcall CfReportProviderProgress2(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, int a6)
{
  int v10; // r12d
  const wchar_t *v11; // rax
  NTSTATUS v12; // r13d
  NTSTATUS v13; // ecx
  DWORD v14; // ecx
  signed int v15; // eax
  NTSTATUS v16; // ecx
  DWORD v17; // eax
  signed int v18; // eax
  NTSTATUS v19; // ecx
  DWORD v20; // eax
  signed int v21; // eax
  NTSTATUS v22; // ecx
  DWORD v23; // eax
  signed int v24; // eax
  NTSTATUS v25; // ecx
  DWORD v26; // eax
  signed int v27; // eax
  NTSTATUS v28; // ecx
  DWORD v29; // eax
  signed int v30; // eax
  NTSTATUS v31; // ecx
  DWORD v32; // eax
  signed int v33; // eax
  DWORD v34; // eax
  signed int v35; // eax
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v39; // [rsp+50h] [rbp-B0h]
  int v40; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v41; // [rsp+68h] [rbp-98h]
  __int64 v42; // [rsp+70h] [rbp-90h]
  __int64 v43; // [rsp+78h] [rbp-88h]
  __int64 v44; // [rsp+80h] [rbp-80h]
  __int64 v45; // [rsp+88h] [rbp-78h]
  __int64 v46; // [rsp+90h] [rbp-70h]
  __int64 InBuffer; // [rsp+C0h] [rbp-40h] BYREF
  DWORD dwInBufferSize; // [rsp+C8h] [rbp-38h]
  int v49; // [rsp+CCh] [rbp-34h]
  _DWORD v50[2]; // [rsp+D0h] [rbp-30h] BYREF
  int v51; // [rsp+D8h] [rbp-28h]
  DWORD v52; // [rsp+DCh] [rbp-24h]
  int v53; // [rsp+F0h] [rbp-10h]
  DWORD v54; // [rsp+F4h] [rbp-Ch]
  int v55; // [rsp+108h] [rbp+8h]
  DWORD v56; // [rsp+10Ch] [rbp+Ch]
  int v57; // [rsp+130h] [rbp+30h]
  DWORD v58; // [rsp+134h] [rbp+34h]
  int v59; // [rsp+138h] [rbp+38h]
  DWORD v60; // [rsp+13Ch] [rbp+3Ch]
  int v61; // [rsp+140h] [rbp+40h]
  DWORD v62; // [rsp+144h] [rbp+44h]
  int v63; // [rsp+148h] [rbp+48h]
  DWORD v64; // [rsp+14Ch] [rbp+4Ch]

  BytesReturned = 0;
  memset_0(&v40, 0, 0x58u);
  UnbiasedTime = 0;
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  v39 = CfpReferenceSyncRoot(a1);
  v10 = v39 == 0 ? 0x57 : 0;
  if ( !v39 )
    v10 |= 0x80070000;
  if ( v10 > -1 )
  {
    memset_0(v50, 0, 0xF0u);
    InBuffer = 1886219331;
    dwInBufferSize = 200;
    v49 = 1507328;
    memset_0(v50, 0, 0xB8u);
    v12 = -1073741811;
    if ( HIWORD(v49) )
    {
      v14 = dwInBufferSize;
      if ( ((dwInBufferSize + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 1 <= 0x100 )
      {
        v50[0] = 65543;
        dwInBufferSize = (dwInBufferSize + 3) & 0xFFFFFFFC;
        v50[1] = (v14 + 3) & 0xFFFFFFFC;
        v13 = 0;
        *((_BYTE *)&InBuffer + dwInBufferSize++) = 1;
      }
      else
      {
        v13 = -1073741789;
      }
    }
    else
    {
      v13 = -1073741811;
    }
    v15 = RtlNtStatusToDosError(v13);
    v10 = v15;
    if ( v15 > 0 )
      v10 = (unsigned __int16)v15 | 0x80070000;
    if ( v10 > -1 )
    {
      if ( HIWORD(v49) > 1u )
      {
        if ( ((dwInBufferSize + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 2 <= 0x100 )
        {
          v17 = (dwInBufferSize + 3) & 0xFFFFFFFC;
          dwInBufferSize = v17;
          if ( (_WORD)v51 )
            LOWORD(v49) = v49 | 1;
          v51 = 131080;
          v52 = v17;
          *(_WORD *)((char *)&InBuffer + v17) = 262;
          v16 = 0;
          dwInBufferSize += 2;
        }
        else
        {
          v16 = -1073741789;
        }
      }
      else
      {
        v16 = -1073741811;
      }
      v18 = RtlNtStatusToDosError(v16);
      v10 = v18;
      if ( v18 > 0 )
        v10 = (unsigned __int16)v18 | 0x80070000;
      if ( v10 > -1 )
      {
        if ( HIWORD(v49) > 4u )
        {
          if ( ((dwInBufferSize + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0x100 )
          {
            v20 = (dwInBufferSize + 3) & 0xFFFFFFFC;
            dwInBufferSize = v20;
            if ( (_WORD)v53 )
              LOWORD(v49) = v49 | 1;
            v54 = v20;
            v53 = 524294;
            *(__int64 *)((char *)&InBuffer + v20) = a1;
            v19 = 0;
            dwInBufferSize += 8;
          }
          else
          {
            v19 = -1073741789;
          }
        }
        else
        {
          v19 = -1073741811;
        }
        v21 = RtlNtStatusToDosError(v19);
        v10 = v21;
        if ( v21 > 0 )
          v10 = (unsigned __int16)v21 | 0x80070000;
        if ( v10 > -1 )
        {
          if ( HIWORD(v49) > 7u )
          {
            if ( ((dwInBufferSize + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0x100 )
            {
              v23 = (dwInBufferSize + 3) & 0xFFFFFFFC;
              dwInBufferSize = v23;
              if ( (_WORD)v55 )
                LOWORD(v49) = v49 | 1;
              v56 = v23;
              v55 = 524294;
              *(__int64 *)((char *)&InBuffer + v23) = a2;
              v22 = 0;
              dwInBufferSize += 8;
            }
            else
            {
              v22 = -1073741789;
            }
          }
          else
          {
            v22 = -1073741811;
          }
          v24 = RtlNtStatusToDosError(v22);
          v10 = v24;
          if ( v24 > 0 )
            v10 = (unsigned __int16)v24 | 0x80070000;
          if ( v10 > -1 )
          {
            if ( HIWORD(v49) > 0xCu )
            {
              if ( ((dwInBufferSize + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0x100 )
              {
                v26 = (dwInBufferSize + 3) & 0xFFFFFFFC;
                dwInBufferSize = v26;
                if ( (_WORD)v57 )
                  LOWORD(v49) = v49 | 1;
                v58 = v26;
                v57 = 524294;
                *(__int64 *)((char *)&InBuffer + v26) = a3;
                v25 = 0;
                dwInBufferSize += 8;
              }
              else
              {
                v25 = -1073741789;
              }
            }
            else
            {
              v25 = -1073741811;
            }
            v27 = RtlNtStatusToDosError(v25);
            v10 = v27;
            if ( v27 > 0 )
              v10 = (unsigned __int16)v27 | 0x80070000;
            if ( v10 > -1 )
            {
              if ( HIWORD(v49) > 0xDu )
              {
                if ( ((dwInBufferSize + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0x100 )
                {
                  v29 = (dwInBufferSize + 3) & 0xFFFFFFFC;
                  dwInBufferSize = v29;
                  if ( (_WORD)v59 )
                    LOWORD(v49) = v49 | 1;
                  v60 = v29;
                  v59 = 524294;
                  *(__int64 *)((char *)&InBuffer + v29) = a4;
                  v28 = 0;
                  dwInBufferSize += 8;
                }
                else
                {
                  v28 = -1073741789;
                }
              }
              else
              {
                v28 = -1073741811;
              }
              v30 = RtlNtStatusToDosError(v28);
              v10 = v30;
              if ( v30 > 0 )
                v10 = (unsigned __int16)v30 | 0x80070000;
              if ( v10 > -1 )
              {
                if ( HIWORD(v49) > 0xEu )
                {
                  if ( ((dwInBufferSize + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0x100 )
                  {
                    v32 = (dwInBufferSize + 3) & 0xFFFFFFFC;
                    dwInBufferSize = v32;
                    if ( (_WORD)v61 )
                      LOWORD(v49) = v49 | 1;
                    v62 = v32;
                    v61 = 524294;
                    *(__int64 *)((char *)&InBuffer + v32) = a5;
                    v31 = 0;
                    dwInBufferSize += 8;
                  }
                  else
                  {
                    v31 = -1073741789;
                  }
                }
                else
                {
                  v31 = -1073741811;
                }
                v33 = RtlNtStatusToDosError(v31);
                v10 = v33;
                if ( v33 > 0 )
                  v10 = (unsigned __int16)v33 | 0x80070000;
                if ( v10 > -1 )
                {
                  if ( HIWORD(v49) > 0xFu )
                  {
                    if ( ((dwInBufferSize + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= 0x100 )
                    {
                      v34 = (dwInBufferSize + 3) & 0xFFFFFFFC;
                      dwInBufferSize = v34;
                      if ( (_WORD)v63 )
                        LOWORD(v49) = v49 | 1;
                      v12 = 0;
                      v63 = 262154;
                      v64 = v34;
                      *(_DWORD *)((char *)&InBuffer + v34) = a6;
                      dwInBufferSize += 4;
                    }
                    else
                    {
                      v12 = -1073741789;
                    }
                  }
                  v35 = RtlNtStatusToDosError(v12);
                  v10 = v35;
                  if ( v35 > 0 )
                    v10 = (unsigned __int16)v35 | 0x80070000;
                  if ( v10 > -1 )
                  {
                    LOWORD(v49) = v49 & 0xFFFD;
                    HIDWORD(InBuffer) = 0;
                    v10 = FilterSendMessage(hPort, &InBuffer, dwInBufferSize, 0, 0, &BytesReturned);
                    v11 = L"FilterSendMessage failed";
                    if ( v10 > -1 )
                      v11 = 0;
                  }
                  else
                  {
                    v11 = L"SetCldDsMsgRequestorSessionId Failed";
                  }
                }
                else
                {
                  v11 = L"SetCldDsMsgProviderProgressCompleted Failed";
                }
              }
              else
              {
                v11 = L"SetCldDsMsgProviderProgressTotal Failed";
              }
            }
            else
            {
              v11 = L"SetCldDsMsgRequestKey Failed";
            }
          }
          else
          {
            v11 = L"SetCldDsMsgStreamKey Failed";
          }
        }
        else
        {
          v11 = L"SetCldDsMsgSyncRootKey Failed";
        }
      }
      else
      {
        v11 = L"SetCldMsgCommand Failed";
      }
    }
    else
    {
      v11 = L"SetVersion Failed";
    }
  }
  else
  {
    v11 = L"No SyncRoot found with ConnectionKey";
  }
  v41 = v11;
  v42 = a1;
  v43 = a2;
  v44 = a3;
  v45 = a4;
  v46 = a5;
  TlmLogApiReliability(0x21u, 0, 0, 0, 0, UnbiasedTime, &v40, v10);
  if ( v39 )
    CfpReleaseSyncRoot(v39);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800032a0  push    rbp
0x1800032a2  push    rbx
0x1800032a3  push    rsi
0x1800032a4  push    rdi
0x1800032a5  push    r12
0x1800032a7  push    r13
0x1800032a9  push    r14
0x1800032ab  push    r15
0x1800032ad  lea     rbp, [rsp-0D8h]
0x1800032b5  sub     rsp, 1D8h
0x1800032bc  mov     rax, cs:__security_cookie
0x1800032c3  xor     rax, rsp
0x1800032c6  mov     [rbp+110h+var_50], rax
0x1800032cd  xor     r15d, r15d
0x1800032d0  mov     rsi, r8
0x1800032d3  mov     rdi, rdx
0x1800032d6  mov     [rsp+210h+BytesReturned], r15d
0x1800032db  mov     rbx, rcx
0x1800032de  xor     edx, edx; Val
0x1800032e0  lea     rcx, [rsp+210h+var_1B0]; void *
0x1800032e5  mov     r14, r9
0x1800032e8  lea     r8d, [r15+58h]; Size
0x1800032ec  call    memset_0
0x1800032f1  lea     rcx, [rsp+210h+UnbiasedTime]; UnbiasedTime
0x1800032f6  mov     [rsp+210h+UnbiasedTime], r15
0x1800032fb  call    cs:__imp_QueryUnbiasedInterruptTime
0x180003302  nop     dword ptr [rax+rax+00h]
0x180003307  mov     rcx, rbx
0x18000330a  call    CfpReferenceSyncRoot
0x18000330f  mov     r15, [rbp+110h+arg_20]
0x180003316  mov     rcx, rax
0x180003319  neg     rcx
0x18000331c  mov     [rsp+210h+var_1C0], rax
0x180003321  sbb     r12d, r12d
0x180003324  xor     edx, edx; Val
0x180003326  not     r12d
0x180003329  and     r12d, 57h
0x18000332d  mov     ecx, r12d
0x180003330  or      ecx, 80070000h
0x180003336  test    rax, rax
0x180003339  cmovz   r12d, ecx
0x18000333d  cmp     r12d, 0FFFFFFFFh
0x180003341  jg      short loc_18000334F
0x180003343  lea     rax, aNoSyncrootFoun; "No SyncRoot found with ConnectionKey"
0x18000334a  jmp     loc_18000386D
0x18000334f  mov     r8d, 0F0h; Size
0x180003355  lea     rcx, [rbp+110h+var_140]; void *
0x180003359  call    memset_0
0x18000335e  xor     edx, edx; Val
0x180003360  mov     [rbp+110h+InBuffer], 706D6C43h
0x180003368  mov     r8d, 0B8h; Size
0x18000336e  mov     [rbp+110h+dwInBufferSize], 0C8h
0x180003375  lea     rcx, [rbp+110h+var_140]; void *
0x180003379  mov     [rbp+110h+var_144], 170000h
0x180003380  xor     r12d, r12d
0x180003383  call    memset_0
0x180003388  lea     edx, [r12+1]
0x18000338d  mov     r13d, 0C000000Dh
0x180003393  cmp     r12w, word ptr [rbp+110h+var_144+2]
0x180003398  jb      short loc_18000339F
0x18000339a  mov     ecx, r13d
0x18000339d  jmp     short loc_1800033DB
0x18000339f  mov     ecx, [rbp+110h+dwInBufferSize]
0x1800033a2  lea     rax, [rcx+3]
0x1800033a6  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800033aa  add     rax, rdx
0x1800033ad  cmp     rax, 100h
0x1800033b3  jbe     short loc_1800033BC
0x1800033b5  mov     ecx, 0C0000023h
0x1800033ba  jmp     short loc_1800033DB
0x1800033bc  lea     eax, [rcx+3]
0x1800033bf  mov     [rbp+110h+var_140], 10007h
0x1800033c6  and     eax, 0FFFFFFFCh
0x1800033c9  mov     ecx, eax
0x1800033cb  mov     [rbp+110h+dwInBufferSize], ecx
0x1800033ce  mov     [rbp+110h+var_13C], ecx
0x1800033d1  mov     ecx, r12d; Status
0x1800033d4  mov     byte ptr [rbp+rax+110h+InBuffer], dl
0x1800033d8  add     [rbp+110h+dwInBufferSize], edx
0x1800033db  call    cs:__imp_RtlNtStatusToDosError
0x1800033e2  nop     dword ptr [rax+rax+00h]
0x1800033e7  xor     edx, edx
0x1800033e9  mov     r12d, eax
0x1800033ec  test    eax, eax
0x1800033ee  jle     short loc_1800033FB
0x1800033f0  movzx   r12d, ax
0x1800033f4  or      r12d, 80070000h
0x1800033fb  cmp     r12d, 0FFFFFFFFh
0x1800033ff  jg      short loc_18000340D
0x180003401  lea     rax, aSetversionFail_0; "SetVersion Failed"
0x180003408  jmp     loc_18000386D
0x18000340d  mov     r10d, 1
0x180003413  cmp     r10w, word ptr [rbp+110h+var_144+2]
0x180003418  jb      short loc_18000341F
0x18000341a  mov     ecx, r13d
0x18000341d  jmp     short loc_180003475
0x18000341f  mov     ecx, [rbp+110h+dwInBufferSize]
0x180003422  mov     r8d, 2
0x180003428  lea     rax, [rcx+3]
0x18000342c  and     rax, 0FFFFFFFFFFFFFFFCh
0x180003430  add     rax, r8
0x180003433  cmp     rax, 100h
0x180003439  jbe     short loc_180003442
0x18000343b  mov     ecx, 0C0000023h
0x180003440  jmp     short loc_180003475
0x180003442  lea     eax, [rcx+3]
0x180003445  and     eax, 0FFFFFFFCh
0x180003448  mov     ecx, eax
0x18000344a  mov     [rbp+110h+dwInBufferSize], eax
0x18000344d  cmp     word ptr [rbp+110h+var_138], dx
0x180003451  jz      short loc_180003458
0x180003453  or      word ptr [rbp+110h+var_144], r10w
0x180003458  mov     rax, rcx
0x18000345b  mov     [rbp+110h+var_138], 20008h
0x180003462  mov     ecx, 106h
0x180003467  mov     [rbp+110h+var_134], eax
0x18000346a  mov     word ptr [rbp+rax+110h+InBuffer], cx
0x18000346f  mov     ecx, edx; Status
0x180003471  add     [rbp+110h+dwInBufferSize], r8d
0x180003475  call    cs:__imp_RtlNtStatusToDosError
0x18000347c  nop     dword ptr [rax+rax+00h]
0x180003481  xor     edx, edx
0x180003483  mov     r12d, eax
0x180003486  test    eax, eax
0x180003488  jle     short loc_180003495
0x18000348a  movzx   r12d, ax
0x18000348e  or      r12d, 80070000h
0x180003495  cmp     r12d, 0FFFFFFFFh
0x180003499  jg      short loc_1800034A7
0x18000349b  lea     rax, aSetcldmsgcomma_0; "SetCldMsgCommand Failed"
0x1800034a2  jmp     loc_18000386D
0x1800034a7  mov     eax, 4
0x1800034ac  cmp     ax, word ptr [rbp+110h+var_144+2]
0x1800034b0  jb      short loc_1800034B7
0x1800034b2  mov     ecx, r13d
0x1800034b5  jmp     short loc_180003509
0x1800034b7  mov     ecx, [rbp+110h+dwInBufferSize]
0x1800034ba  mov     r8d, 8
0x1800034c0  lea     rax, [rcx+3]
0x1800034c4  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800034c8  add     rax, r8
0x1800034cb  cmp     rax, 100h
0x1800034d1  jbe     short loc_1800034DA
0x1800034d3  mov     ecx, 0C0000023h
0x1800034d8  jmp     short loc_180003509
0x1800034da  lea     eax, [rcx+3]
0x1800034dd  and     eax, 0FFFFFFFCh
0x1800034e0  mov     ecx, eax
0x1800034e2  mov     [rbp+110h+dwInBufferSize], eax
0x1800034e5  cmp     word ptr [rbp+110h+var_120], dx
0x1800034e9  jz      short loc_1800034F4
0x1800034eb  mov     eax, 1
0x1800034f0  or      word ptr [rbp+110h+var_144], ax
0x1800034f4  mov     [rbp+110h+var_11C], ecx
0x1800034f7  mov     [rbp+110h+var_120], 80006h
0x1800034fe  mov     [rbp+rcx+110h+InBuffer], rbx
0x180003503  mov     ecx, edx; Status
0x180003505  add     [rbp+110h+dwInBufferSize], r8d
0x180003509  call    cs:__imp_RtlNtStatusToDosError
0x180003510  nop     dword ptr [rax+rax+00h]
0x180003515  xor     edx, edx
0x180003517  mov     r12d, eax
0x18000351a  test    eax, eax
0x18000351c  jle     short loc_180003529
0x18000351e  movzx   r12d, ax
0x180003522  or      r12d, 80070000h
0x180003529  cmp     r12d, 0FFFFFFFFh
0x18000352d  jg      short loc_18000353B
0x18000352f  lea     rax, aSetclddsmsgsyn; "SetCldDsMsgSyncRootKey Failed"
0x180003536  jmp     loc_18000386D
0x18000353b  mov     eax, 7
0x180003540  cmp     ax, word ptr [rbp+110h+var_144+2]
0x180003544  jb      short loc_18000354B
0x180003546  mov     ecx, r13d
0x180003549  jmp     short loc_18000359D
0x18000354b  mov     ecx, [rbp+110h+dwInBufferSize]
0x18000354e  mov     r8d, 8
0x180003554  lea     rax, [rcx+3]
0x180003558  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000355c  add     rax, r8
0x18000355f  cmp     rax, 100h
0x180003565  jbe     short loc_18000356E
0x180003567  mov     ecx, 0C0000023h
0x18000356c  jmp     short loc_18000359D
0x18000356e  lea     eax, [rcx+3]
0x180003571  and     eax, 0FFFFFFFCh
0x180003574  mov     ecx, eax
0x180003576  mov     [rbp+110h+dwInBufferSize], eax
0x180003579  cmp     word ptr [rbp+110h+var_108], dx
0x18000357d  jz      short loc_180003588
0x18000357f  mov     eax, 1
0x180003584  or      word ptr [rbp+110h+var_144], ax
0x180003588  mov     [rbp+110h+var_104], ecx
0x18000358b  mov     [rbp+110h+var_108], 80006h
0x180003592  mov     [rbp+rcx+110h+InBuffer], rdi
0x180003597  mov     ecx, edx; Status
0x180003599  add     [rbp+110h+dwInBufferSize], r8d
0x18000359d  call    cs:__imp_RtlNtStatusToDosError
0x1800035a4  nop     dword ptr [rax+rax+00h]
0x1800035a9  xor     edx, edx
0x1800035ab  mov     r12d, eax
0x1800035ae  test    eax, eax
0x1800035b0  jle     short loc_1800035BD
0x1800035b2  movzx   r12d, ax
0x1800035b6  or      r12d, 80070000h
0x1800035bd  cmp     r12d, 0FFFFFFFFh
0x1800035c1  jg      short loc_1800035CF
0x1800035c3  lea     rax, aSetclddsmsgstr; "SetCldDsMsgStreamKey Failed"
0x1800035ca  jmp     loc_18000386D
0x1800035cf  mov     eax, 0Ch
0x1800035d4  cmp     ax, word ptr [rbp+110h+var_144+2]
0x1800035d8  jb      short loc_1800035DF
0x1800035da  mov     ecx, r13d
0x1800035dd  jmp     short loc_180003631
0x1800035df  mov     ecx, [rbp+110h+dwInBufferSize]
0x1800035e2  mov     r8d, 8
0x1800035e8  lea     rax, [rcx+3]
0x1800035ec  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800035f0  add     rax, r8
0x1800035f3  cmp     rax, 100h
0x1800035f9  jbe     short loc_180003602
0x1800035fb  mov     ecx, 0C0000023h
0x180003600  jmp     short loc_180003631
0x180003602  lea     eax, [rcx+3]
0x180003605  and     eax, 0FFFFFFFCh
0x180003608  mov     ecx, eax
0x18000360a  mov     [rbp+110h+dwInBufferSize], eax
0x18000360d  cmp     word ptr [rbp+110h+var_E0], dx
0x180003611  jz      short loc_18000361C
0x180003613  mov     eax, 1
0x180003618  or      word ptr [rbp+110h+var_144], ax
0x18000361c  mov     [rbp+110h+var_DC], ecx
0x18000361f  mov     [rbp+110h+var_E0], 80006h
0x180003626  mov     [rbp+rcx+110h+InBuffer], rsi
0x18000362b  mov     ecx, edx; Status
0x18000362d  add     [rbp+110h+dwInBufferSize], r8d
0x180003631  call    cs:__imp_RtlNtStatusToDosError
0x180003638  nop     dword ptr [rax+rax+00h]
0x18000363d  xor     edx, edx
0x18000363f  mov     r12d, eax
0x180003642  test    eax, eax
0x180003644  jle     short loc_180003651
0x180003646  movzx   r12d, ax
0x18000364a  or      r12d, 80070000h
0x180003651  cmp     r12d, 0FFFFFFFFh
0x180003655  jg      short loc_180003663
0x180003657  lea     rax, aSetclddsmsgreq; "SetCldDsMsgRequestKey Failed"
0x18000365e  jmp     loc_18000386D
0x180003663  mov     eax, 0Dh
0x180003668  cmp     ax, word ptr [rbp+110h+var_144+2]
0x18000366c  jb      short loc_180003673
0x18000366e  mov     ecx, r13d
0x180003671  jmp     short loc_1800036C5
0x180003673  mov     ecx, [rbp+110h+dwInBufferSize]
0x180003676  mov     r8d, 8
0x18000367c  lea     rax, [rcx+3]
0x180003680  and     rax, 0FFFFFFFFFFFFFFFCh
0x180003684  add     rax, r8
0x180003687  cmp     rax, 100h
0x18000368d  jbe     short loc_180003696
0x18000368f  mov     ecx, 0C0000023h
0x180003694  jmp     short loc_1800036C5
0x180003696  lea     eax, [rcx+3]
0x180003699  and     eax, 0FFFFFFFCh
0x18000369c  mov     ecx, eax
0x18000369e  mov     [rbp+110h+dwInBufferSize], eax
0x1800036a1  cmp     word ptr [rbp+110h+var_D8], dx
0x1800036a5  jz      short loc_1800036B0
0x1800036a7  mov     eax, 1
0x1800036ac  or      word ptr [rbp+110h+var_144], ax
0x1800036b0  mov     [rbp+110h+var_D4], ecx
0x1800036b3  mov     [rbp+110h+var_D8], 80006h
0x1800036ba  mov     [rbp+rcx+110h+InBuffer], r14
0x1800036bf  mov     ecx, edx; Status
0x1800036c1  add     [rbp+110h+dwInBufferSize], r8d
0x1800036c5  call    cs:__imp_RtlNtStatusToDosError
0x1800036cc  nop     dword ptr [rax+rax+00h]
0x1800036d1  xor     edx, edx
0x1800036d3  mov     r12d, eax
0x1800036d6  test    eax, eax
0x1800036d8  jle     short loc_1800036E5
0x1800036da  movzx   r12d, ax
0x1800036de  or      r12d, 80070000h
0x1800036e5  cmp     r12d, 0FFFFFFFFh
0x1800036e9  jg      short loc_1800036F7
0x1800036eb  lea     rax, aSetclddsmsgpro; "SetCldDsMsgProviderProgressTotal Failed"
0x1800036f2  jmp     loc_18000386D
0x1800036f7  mov     eax, 0Eh
0x1800036fc  cmp     ax, word ptr [rbp+110h+var_144+2]
0x180003700  jb      short loc_180003707
0x180003702  mov     ecx, r13d
0x180003705  jmp     short loc_180003759
0x180003707  mov     ecx, [rbp+110h+dwInBufferSize]
0x18000370a  mov     r8d, 8
0x180003710  lea     rax, [rcx+3]
0x180003714  and     rax, 0FFFFFFFFFFFFFFFCh
0x180003718  add     rax, r8
0x18000371b  cmp     rax, 100h
0x180003721  jbe     short loc_18000372A
0x180003723  mov     ecx, 0C0000023h
  ... truncated ...
```
