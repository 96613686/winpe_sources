# CfAbortOperation

- ea: `0x180002670`
- end: `0x180002c75`
- name: `CfAbortOperation`
- size: `1541`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001aa0`
- `0x18000231e`
- `0x180002670`
- `0x180012054`
- `0x180012c28`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000277b`
- `ntdll!RtlNtStatusToDosError` at `0x18000280d`
- `ntdll!RtlNtStatusToDosError` at `0x1800028a1`
- `ntdll!RtlNtStatusToDosError` at `0x180002936`
- `ntdll!RtlNtStatusToDosError` at `0x1800029cb`
- `ntdll!RtlNtStatusToDosError` at `0x180002a60`
- `ntdll!RtlNtStatusToDosError` at `0x180002aeb`
- `ntdll!RtlNtStatusToDosError` at `0x180002b74`
- `ntdll!RtlNtStatusToDosError` at `0x18000277b`
- `ntdll!RtlNtStatusToDosError` at `0x18000280d`
- `ntdll!RtlNtStatusToDosError` at `0x1800028a1`
- `ntdll!RtlNtStatusToDosError` at `0x180002936`
- `ntdll!RtlNtStatusToDosError` at `0x1800029cb`
- `ntdll!RtlNtStatusToDosError` at `0x180002a60`
- `ntdll!RtlNtStatusToDosError` at `0x180002aeb`
- `ntdll!RtlNtStatusToDosError` at `0x180002b74`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800026e6`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800026e6`
- `FLTLIB!FilterSendMessage` at `0x180002bcb`
- `FLTLIB!FilterSendMessage` at `0x180002bcb`

## string_xrefs

- `0x18000282d`: `SetCldMsgCommand Failed`
- `0x180002b0b`: `SetCldDsMsgProcessId Failed`

## pseudocode

```c
__int64 __fastcall CfAbortOperation(int a1, __int64 *a2, int a3)
{
  int v6; // ebx
  const wchar_t *v7; // rcx
  NTSTATUS v8; // esi
  NTSTATUS v9; // ecx
  DWORD v10; // ecx
  signed int v11; // eax
  NTSTATUS v12; // ecx
  DWORD v13; // ecx
  __int64 v14; // rax
  signed int v15; // eax
  __int64 v16; // rdx
  NTSTATUS v17; // ecx
  __int64 v18; // rax
  signed int v19; // eax
  __int64 v20; // rdx
  NTSTATUS v21; // ecx
  __int64 v22; // rax
  signed int v23; // eax
  __int64 v24; // rdx
  NTSTATUS v25; // ecx
  __int64 v26; // rax
  signed int v27; // eax
  __int64 v28; // rdx
  NTSTATUS v29; // ecx
  __int64 v30; // rax
  signed int v31; // eax
  NTSTATUS v32; // ecx
  __int64 v33; // rax
  signed int v34; // eax
  __int64 v35; // rax
  signed int v36; // eax
  HRESULT v37; // eax
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+48h] [rbp-B8h] BYREF
  int v41; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v42; // [rsp+58h] [rbp-A8h]
  int v43; // [rsp+60h] [rbp-A0h]
  int v44; // [rsp+64h] [rbp-9Ch]
  __int64 v45; // [rsp+68h] [rbp-98h]
  __int64 v46; // [rsp+70h] [rbp-90h]
  __int64 InBuffer; // [rsp+B0h] [rbp-50h] BYREF
  DWORD dwInBufferSize; // [rsp+B8h] [rbp-48h]
  int v49; // [rsp+BCh] [rbp-44h]
  _DWORD v50[2]; // [rsp+C0h] [rbp-40h] BYREF
  int v51; // [rsp+C8h] [rbp-38h]
  unsigned int v52; // [rsp+CCh] [rbp-34h]
  int v53; // [rsp+E0h] [rbp-20h]
  int v54; // [rsp+E4h] [rbp-1Ch]
  int v55; // [rsp+E8h] [rbp-18h]
  int v56; // [rsp+ECh] [rbp-14h]
  int v57; // [rsp+F8h] [rbp-8h]
  int v58; // [rsp+FCh] [rbp-4h]
  int v59; // [rsp+120h] [rbp+20h]
  int v60; // [rsp+124h] [rbp+24h]
  int v61; // [rsp+128h] [rbp+28h]
  int v62; // [rsp+12Ch] [rbp+2Ch]
  int v63; // [rsp+130h] [rbp+30h]
  int v64; // [rsp+134h] [rbp+34h]

  BytesReturned = 0;
  memset_0(&v41, 0, 0x58u);
  UnbiasedTime = 0;
  v6 = GlobalPortInit(0);
  if ( v6 > -1 )
  {
    QueryUnbiasedInterruptTime(&UnbiasedTime);
    memset_0(v50, 0, 0xF0u);
    InBuffer = 1886219331;
    dwInBufferSize = 200;
    v49 = 1507328;
    memset_0(v50, 0, 0xB8u);
    v8 = -1073741811;
    if ( HIWORD(v49) )
    {
      v10 = dwInBufferSize;
      if ( ((dwInBufferSize + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 1 <= 0xF8 )
      {
        v50[0] = 65543;
        dwInBufferSize = (dwInBufferSize + 3) & 0xFFFFFFFC;
        v50[1] = (v10 + 3) & 0xFFFFFFFC;
        v9 = 0;
        *((_BYTE *)&InBuffer + dwInBufferSize++) = 1;
      }
      else
      {
        v9 = -1073741789;
      }
    }
    else
    {
      v9 = -1073741811;
    }
    v11 = RtlNtStatusToDosError(v9);
    v6 = v11;
    if ( v11 > 0 )
      v6 = (unsigned __int16)v11 | 0x80070000;
    if ( v6 > -1 )
    {
      if ( HIWORD(v49) > 1u )
      {
        v13 = dwInBufferSize;
        if ( ((dwInBufferSize + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 2 <= 0xF8 )
        {
          v14 = (dwInBufferSize + 3) & 0xFFFFFFFC;
          dwInBufferSize = (dwInBufferSize + 3) & 0xFFFFFFFC;
          if ( (_WORD)v51 )
            LOWORD(v49) = v49 | 1;
          v51 = 131080;
          v52 = (v13 + 3) & 0xFFFFFFFC;
          *(_WORD *)((char *)&InBuffer + v14) = 16386;
          v12 = 0;
          dwInBufferSize += 2;
        }
        else
        {
          v12 = -1073741789;
        }
      }
      else
      {
        v12 = -1073741811;
      }
      v15 = RtlNtStatusToDosError(v12);
      v6 = v15;
      if ( v15 > 0 )
        v6 = (unsigned __int16)v15 | 0x80070000;
      if ( v6 > -1 )
      {
        if ( a2 )
          v16 = *a2;
        else
          v16 = 0;
        if ( HIWORD(v49) > 0xDu )
        {
          if ( ((dwInBufferSize + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0xF8 )
          {
            v18 = (dwInBufferSize + 3) & 0xFFFFFFFC;
            dwInBufferSize = (dwInBufferSize + 3) & 0xFFFFFFFC;
            if ( (_WORD)v61 )
              LOWORD(v49) = v49 | 1;
            v61 = 524294;
            v17 = 0;
            v62 = v18;
            *(__int64 *)((char *)&InBuffer + v18) = v16;
            dwInBufferSize += 8;
          }
          else
          {
            v17 = -1073741789;
          }
        }
        else
        {
          v17 = -1073741811;
        }
        v19 = RtlNtStatusToDosError(v17);
        v6 = v19;
        if ( v19 > 0 )
          v6 = (unsigned __int16)v19 | 0x80070000;
        if ( v6 > -1 )
        {
          if ( a2 )
            v20 = a2[1];
          else
            v20 = 0;
          if ( HIWORD(v49) > 4u )
          {
            if ( ((dwInBufferSize + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0xF8 )
            {
              v22 = (dwInBufferSize + 3) & 0xFFFFFFFC;
              dwInBufferSize = (dwInBufferSize + 3) & 0xFFFFFFFC;
              if ( (_WORD)v53 )
                LOWORD(v49) = v49 | 1;
              v53 = 524294;
              v21 = 0;
              v54 = v22;
              *(__int64 *)((char *)&InBuffer + v22) = v20;
              dwInBufferSize += 8;
            }
            else
            {
              v21 = -1073741789;
            }
          }
          else
          {
            v21 = -1073741811;
          }
          v23 = RtlNtStatusToDosError(v21);
          v6 = v23;
          if ( v23 > 0 )
            v6 = (unsigned __int16)v23 | 0x80070000;
          if ( v6 > -1 )
          {
            if ( a2 )
              v24 = a2[2];
            else
              v24 = 0;
            if ( HIWORD(v49) > 7u )
            {
              if ( ((dwInBufferSize + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0xF8 )
              {
                v26 = (dwInBufferSize + 3) & 0xFFFFFFFC;
                dwInBufferSize = (dwInBufferSize + 3) & 0xFFFFFFFC;
                if ( (_WORD)v57 )
                  LOWORD(v49) = v49 | 1;
                v57 = 524294;
                v25 = 0;
                v58 = v26;
                *(__int64 *)((char *)&InBuffer + v26) = v24;
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
            v6 = v27;
            if ( v27 > 0 )
              v6 = (unsigned __int16)v27 | 0x80070000;
            if ( v6 > -1 )
            {
              if ( a2 )
                v28 = a2[3];
              else
                v28 = 0;
              if ( HIWORD(v49) > 0xCu )
              {
                if ( ((dwInBufferSize + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0xF8 )
                {
                  v30 = (dwInBufferSize + 3) & 0xFFFFFFFC;
                  dwInBufferSize = (dwInBufferSize + 3) & 0xFFFFFFFC;
                  if ( (_WORD)v59 )
                    LOWORD(v49) = v49 | 1;
                  v59 = 524294;
                  v29 = 0;
                  v60 = v30;
                  *(__int64 *)((char *)&InBuffer + v30) = v28;
                  dwInBufferSize += 8;
                }
                else
                {
                  v29 = -1073741789;
                }
              }
              else
              {
                v29 = -1073741811;
              }
              v31 = RtlNtStatusToDosError(v29);
              v6 = v31;
              if ( v31 > 0 )
                v6 = (unsigned __int16)v31 | 0x80070000;
              if ( v6 > -1 )
              {
                if ( HIWORD(v49) > 0xEu )
                {
                  if ( ((dwInBufferSize + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= 0xF8 )
                  {
                    v33 = (dwInBufferSize + 3) & 0xFFFFFFFC;
                    dwInBufferSize = (dwInBufferSize + 3) & 0xFFFFFFFC;
                    if ( (_WORD)v63 )
                      LOWORD(v49) = v49 | 1;
                    v63 = 262154;
                    v32 = 0;
                    v64 = v33;
                    *(_DWORD *)((char *)&InBuffer + v33) = a1;
                    dwInBufferSize += 4;
                  }
                  else
                  {
                    v32 = -1073741789;
                  }
                }
                else
                {
                  v32 = -1073741811;
                }
                v34 = RtlNtStatusToDosError(v32);
                v6 = v34;
                if ( v34 > 0 )
                  v6 = (unsigned __int16)v34 | 0x80070000;
                if ( v6 > -1 )
                {
                  if ( HIWORD(v49) > 5u )
                  {
                    if ( ((dwInBufferSize + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= 0xF8 )
                    {
                      v35 = (dwInBufferSize + 3) & 0xFFFFFFFC;
                      dwInBufferSize = (dwInBufferSize + 3) & 0xFFFFFFFC;
                      if ( (_WORD)v55 )
                        LOWORD(v49) = v49 | 1;
                      v55 = 262154;
                      v8 = 0;
                      v56 = v35;
                      *(_DWORD *)((char *)&InBuffer + v35) = a3;
                      dwInBufferSize += 4;
                    }
                    else
                    {
                      v8 = -1073741789;
                    }
                  }
                  v36 = RtlNtStatusToDosError(v8);
                  v6 = v36;
                  if ( v36 > 0 )
                    v6 = (unsigned __int16)v36 | 0x80070000;
                  if ( v6 > -1 )
                  {
                    LOWORD(v49) = v49 & 0xFFFD;
                    HIDWORD(InBuffer) = 0;
                    v37 = FilterSendMessage(hPort, &InBuffer, dwInBufferSize, 0, 0, &BytesReturned);
                    v7 = L"FilterSendMessage failed";
                    v6 = v37;
                    if ( v37 > -1 )
                      v7 = 0;
                  }
                  else
                  {
                    v7 = L"SetCldDsMsgFlags Failed";
                  }
                }
                else
                {
                  v7 = L"SetCldDsMsgProcessId Failed";
                }
              }
              else
              {
                v7 = L"SetCldDsMsgRequestKey Failed";
              }
            }
            else
            {
              v7 = L"SetCldDsMsgStreamKey Failed";
            }
          }
          else
          {
            v7 = L"SetCldDsMsgSyncRootKey Failed";
          }
        }
        else
        {
          v7 = L"SetCldDsMsgProviderKey Failed";
        }
      }
      else
      {
        v7 = L"SetCldMsgCommand Failed";
      }
    }
    else
    {
      v7 = L"SetVersion Failed";
    }
  }
  else
  {
    v7 = L"GlobalPortInit Failed";
  }
  v42 = v7;
  v44 = a3;
  v43 = a1;
  if ( a2 )
  {
    v45 = a2[1];
    v46 = a2[2];
  }
  else
  {
    v45 = 0;
    v46 = 0;
  }
  TlmLogApiReliability(0x15u, 0, 0, 0, 0, UnbiasedTime, &v41, v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180002670  mov     [rsp-8+arg_18], rbx
0x180002675  push    rbp
0x180002676  push    rsi
0x180002677  push    rdi
0x180002678  push    r12
0x18000267a  push    r13
0x18000267c  push    r14
0x18000267e  push    r15
0x180002680  lea     rbp, [rsp-0C0h]
0x180002688  sub     rsp, 1C0h
0x18000268f  mov     rax, cs:__security_cookie
0x180002696  xor     rax, rsp
0x180002699  mov     [rbp+0F0h+var_40], rax
0x1800026a0  xor     r12d, r12d
0x1800026a3  mov     r14d, r8d
0x1800026a6  mov     rdi, rdx
0x1800026a9  mov     [rsp+1F0h+BytesReturned], r12d
0x1800026ae  mov     r15d, ecx
0x1800026b1  xor     edx, edx; Val
0x1800026b3  lea     rcx, [rsp+1F0h+var_1A0]; void *
0x1800026b8  lea     r8d, [r12+58h]; Size
0x1800026bd  call    memset_0
0x1800026c2  xor     ecx, ecx
0x1800026c4  mov     [rsp+1F0h+UnbiasedTime], r12
0x1800026c9  call    GlobalPortInit
0x1800026ce  mov     ebx, eax
0x1800026d0  cmp     eax, 0FFFFFFFFh
0x1800026d3  jg      short loc_1800026E1
0x1800026d5  lea     rcx, aGlobalportinit; "GlobalPortInit Failed"
0x1800026dc  jmp     loc_180002BE7
0x1800026e1  lea     rcx, [rsp+1F0h+UnbiasedTime]; UnbiasedTime
0x1800026e6  call    cs:__imp_QueryUnbiasedInterruptTime
0x1800026ed  nop     dword ptr [rax+rax+00h]
0x1800026f2  xor     edx, edx; Val
0x1800026f4  lea     rcx, [rbp+0F0h+var_130]; void *
0x1800026f8  mov     r8d, 0F0h; Size
0x1800026fe  call    memset_0
0x180002703  xor     edx, edx; Val
0x180002705  mov     [rbp+0F0h+InBuffer], 706D6C43h
0x18000270d  mov     r8d, 0B8h; Size
0x180002713  mov     [rbp+0F0h+dwInBufferSize], 0C8h
0x18000271a  lea     rcx, [rbp+0F0h+var_130]; void *
0x18000271e  mov     [rbp+0F0h+var_134], 170000h
0x180002725  call    memset_0
0x18000272a  mov     edx, 1
0x18000272f  mov     esi, 0C000000Dh
0x180002734  cmp     r12w, word ptr [rbp+0F0h+var_134+2]
0x180002739  jb      short loc_18000273F
0x18000273b  mov     ecx, esi
0x18000273d  jmp     short loc_18000277B
0x18000273f  mov     ecx, [rbp+0F0h+dwInBufferSize]
0x180002742  lea     rax, [rcx+3]
0x180002746  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000274a  add     rax, rdx
0x18000274d  cmp     rax, 0F8h
0x180002753  jbe     short loc_18000275C
0x180002755  mov     ecx, 0C0000023h
0x18000275a  jmp     short loc_18000277B
0x18000275c  lea     eax, [rcx+3]
0x18000275f  mov     [rbp+0F0h+var_130], 10007h
0x180002766  and     eax, 0FFFFFFFCh
0x180002769  mov     ecx, eax
0x18000276b  mov     [rbp+0F0h+dwInBufferSize], ecx
0x18000276e  mov     [rbp+0F0h+var_12C], ecx
0x180002771  mov     ecx, r12d; Status
0x180002774  mov     byte ptr [rbp+rax+0F0h+InBuffer], dl
0x180002778  add     [rbp+0F0h+dwInBufferSize], edx
0x18000277b  call    cs:__imp_RtlNtStatusToDosError
0x180002782  nop     dword ptr [rax+rax+00h]
0x180002787  mov     ebx, eax
0x180002789  test    eax, eax
0x18000278b  jle     short loc_180002796
0x18000278d  movzx   ebx, ax
0x180002790  or      ebx, 80070000h
0x180002796  cmp     ebx, 0FFFFFFFFh
0x180002799  jg      short loc_1800027A7
0x18000279b  lea     rcx, aSetversionFail_0; "SetVersion Failed"
0x1800027a2  jmp     loc_180002BE7
0x1800027a7  mov     r13d, 8
0x1800027ad  lea     r8d, [r13-7]
0x1800027b1  cmp     r8w, word ptr [rbp+0F0h+var_134+2]
0x1800027b6  jb      short loc_1800027BC
0x1800027b8  mov     ecx, esi
0x1800027ba  jmp     short loc_18000280D
0x1800027bc  mov     ecx, [rbp+0F0h+dwInBufferSize]
0x1800027bf  mov     edx, 2
0x1800027c4  lea     rax, [rcx+3]
0x1800027c8  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800027cc  add     rax, rdx
0x1800027cf  cmp     rax, 0F8h
0x1800027d5  jbe     short loc_1800027DE
0x1800027d7  mov     ecx, 0C0000023h
0x1800027dc  jmp     short loc_18000280D
0x1800027de  lea     eax, [rcx+3]
0x1800027e1  and     eax, 0FFFFFFFCh
0x1800027e4  mov     [rbp+0F0h+dwInBufferSize], eax
0x1800027e7  cmp     word ptr [rbp+0F0h+var_128], r12w
0x1800027ec  jz      short loc_1800027F3
0x1800027ee  or      word ptr [rbp+0F0h+var_134], r8w
0x1800027f3  mov     ecx, 4002h
0x1800027f8  mov     [rbp+0F0h+var_128], 20008h
0x1800027ff  mov     [rbp+0F0h+var_124], eax
0x180002802  mov     word ptr [rbp+rax+0F0h+InBuffer], cx
0x180002807  mov     ecx, r12d; Status
0x18000280a  add     [rbp+0F0h+dwInBufferSize], edx
0x18000280d  call    cs:__imp_RtlNtStatusToDosError
0x180002814  nop     dword ptr [rax+rax+00h]
0x180002819  mov     ebx, eax
0x18000281b  test    eax, eax
0x18000281d  jle     short loc_180002828
0x18000281f  movzx   ebx, ax
0x180002822  or      ebx, 80070000h
0x180002828  cmp     ebx, 0FFFFFFFFh
0x18000282b  jg      short loc_180002839
0x18000282d  lea     rcx, aSetcldmsgcomma_0; "SetCldMsgCommand Failed"
0x180002834  jmp     loc_180002BE7
0x180002839  test    rdi, rdi
0x18000283c  jz      short loc_180002843
0x18000283e  mov     rdx, [rdi]
0x180002841  jmp     short loc_180002846
0x180002843  mov     rdx, r12
0x180002846  mov     eax, 0Dh
0x18000284b  cmp     ax, word ptr [rbp+0F0h+var_134+2]
0x18000284f  jb      short loc_180002855
0x180002851  mov     ecx, esi
0x180002853  jmp     short loc_1800028A1
0x180002855  mov     ecx, [rbp+0F0h+dwInBufferSize]
0x180002858  lea     rax, [rcx+3]
0x18000285c  and     rax, 0FFFFFFFFFFFFFFFCh
0x180002860  add     rax, r13
0x180002863  cmp     rax, 0F8h
0x180002869  jbe     short loc_180002872
0x18000286b  mov     ecx, 0C0000023h
0x180002870  jmp     short loc_1800028A1
0x180002872  lea     eax, [rcx+3]
0x180002875  and     eax, 0FFFFFFFCh
0x180002878  mov     [rbp+0F0h+dwInBufferSize], eax
0x18000287b  cmp     word ptr [rbp+0F0h+var_C8], r12w
0x180002880  jz      short loc_18000288B
0x180002882  mov     ecx, 1
0x180002887  or      word ptr [rbp+0F0h+var_134], cx
0x18000288b  mov     [rbp+0F0h+var_C8], 80006h
0x180002892  mov     ecx, r12d; Status
0x180002895  mov     [rbp+0F0h+var_C4], eax
0x180002898  mov     [rbp+rax+0F0h+InBuffer], rdx
0x18000289d  add     [rbp+0F0h+dwInBufferSize], r13d
0x1800028a1  call    cs:__imp_RtlNtStatusToDosError
0x1800028a8  nop     dword ptr [rax+rax+00h]
0x1800028ad  mov     ebx, eax
0x1800028af  test    eax, eax
0x1800028b1  jle     short loc_1800028BC
0x1800028b3  movzx   ebx, ax
0x1800028b6  or      ebx, 80070000h
0x1800028bc  cmp     ebx, 0FFFFFFFFh
0x1800028bf  jg      short loc_1800028CD
0x1800028c1  lea     rcx, aSetclddsmsgpro_0; "SetCldDsMsgProviderKey Failed"
0x1800028c8  jmp     loc_180002BE7
0x1800028cd  test    rdi, rdi
0x1800028d0  jz      short loc_1800028D8
0x1800028d2  mov     rdx, [rdi+8]
0x1800028d6  jmp     short loc_1800028DB
0x1800028d8  mov     rdx, r12
0x1800028db  mov     eax, 4
0x1800028e0  cmp     ax, word ptr [rbp+0F0h+var_134+2]
0x1800028e4  jb      short loc_1800028EA
0x1800028e6  mov     ecx, esi
0x1800028e8  jmp     short loc_180002936
0x1800028ea  mov     ecx, [rbp+0F0h+dwInBufferSize]
0x1800028ed  lea     rax, [rcx+3]
0x1800028f1  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800028f5  add     rax, r13
0x1800028f8  cmp     rax, 0F8h
0x1800028fe  jbe     short loc_180002907
0x180002900  mov     ecx, 0C0000023h
0x180002905  jmp     short loc_180002936
0x180002907  lea     eax, [rcx+3]
0x18000290a  and     eax, 0FFFFFFFCh
0x18000290d  mov     [rbp+0F0h+dwInBufferSize], eax
0x180002910  cmp     word ptr [rbp+0F0h+var_110], r12w
0x180002915  jz      short loc_180002920
0x180002917  mov     ecx, 1
0x18000291c  or      word ptr [rbp+0F0h+var_134], cx
0x180002920  mov     [rbp+0F0h+var_110], 80006h
0x180002927  mov     ecx, r12d; Status
0x18000292a  mov     [rbp+0F0h+var_10C], eax
0x18000292d  mov     [rbp+rax+0F0h+InBuffer], rdx
0x180002932  add     [rbp+0F0h+dwInBufferSize], r13d
0x180002936  call    cs:__imp_RtlNtStatusToDosError
0x18000293d  nop     dword ptr [rax+rax+00h]
0x180002942  mov     ebx, eax
0x180002944  test    eax, eax
0x180002946  jle     short loc_180002951
0x180002948  movzx   ebx, ax
0x18000294b  or      ebx, 80070000h
0x180002951  cmp     ebx, 0FFFFFFFFh
0x180002954  jg      short loc_180002962
0x180002956  lea     rcx, aSetclddsmsgsyn; "SetCldDsMsgSyncRootKey Failed"
0x18000295d  jmp     loc_180002BE7
0x180002962  test    rdi, rdi
0x180002965  jz      short loc_18000296D
0x180002967  mov     rdx, [rdi+10h]
0x18000296b  jmp     short loc_180002970
0x18000296d  mov     rdx, r12
0x180002970  mov     eax, 7
0x180002975  cmp     ax, word ptr [rbp+0F0h+var_134+2]
0x180002979  jb      short loc_18000297F
0x18000297b  mov     ecx, esi
0x18000297d  jmp     short loc_1800029CB
0x18000297f  mov     ecx, [rbp+0F0h+dwInBufferSize]
0x180002982  lea     rax, [rcx+3]
0x180002986  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000298a  add     rax, r13
0x18000298d  cmp     rax, 0F8h
0x180002993  jbe     short loc_18000299C
0x180002995  mov     ecx, 0C0000023h
0x18000299a  jmp     short loc_1800029CB
0x18000299c  lea     eax, [rcx+3]
0x18000299f  and     eax, 0FFFFFFFCh
0x1800029a2  mov     [rbp+0F0h+dwInBufferSize], eax
0x1800029a5  cmp     word ptr [rbp+0F0h+var_F8], r12w
0x1800029aa  jz      short loc_1800029B5
0x1800029ac  mov     ecx, 1
0x1800029b1  or      word ptr [rbp+0F0h+var_134], cx
0x1800029b5  mov     [rbp+0F0h+var_F8], 80006h
0x1800029bc  mov     ecx, r12d; Status
0x1800029bf  mov     [rbp+0F0h+var_F4], eax
0x1800029c2  mov     [rbp+rax+0F0h+InBuffer], rdx
0x1800029c7  add     [rbp+0F0h+dwInBufferSize], r13d
0x1800029cb  call    cs:__imp_RtlNtStatusToDosError
0x1800029d2  nop     dword ptr [rax+rax+00h]
0x1800029d7  mov     ebx, eax
0x1800029d9  test    eax, eax
0x1800029db  jle     short loc_1800029E6
0x1800029dd  movzx   ebx, ax
0x1800029e0  or      ebx, 80070000h
0x1800029e6  cmp     ebx, 0FFFFFFFFh
0x1800029e9  jg      short loc_1800029F7
0x1800029eb  lea     rcx, aSetclddsmsgstr; "SetCldDsMsgStreamKey Failed"
0x1800029f2  jmp     loc_180002BE7
0x1800029f7  test    rdi, rdi
0x1800029fa  jz      short loc_180002A02
0x1800029fc  mov     rdx, [rdi+18h]
0x180002a00  jmp     short loc_180002A05
0x180002a02  mov     rdx, r12
0x180002a05  mov     eax, 0Ch
0x180002a0a  cmp     ax, word ptr [rbp+0F0h+var_134+2]
0x180002a0e  jb      short loc_180002A14
0x180002a10  mov     ecx, esi
0x180002a12  jmp     short loc_180002A60
0x180002a14  mov     ecx, [rbp+0F0h+dwInBufferSize]
0x180002a17  lea     rax, [rcx+3]
0x180002a1b  and     rax, 0FFFFFFFFFFFFFFFCh
0x180002a1f  add     rax, r13
0x180002a22  cmp     rax, 0F8h
0x180002a28  jbe     short loc_180002A31
0x180002a2a  mov     ecx, 0C0000023h
0x180002a2f  jmp     short loc_180002A60
0x180002a31  lea     eax, [rcx+3]
0x180002a34  and     eax, 0FFFFFFFCh
0x180002a37  mov     [rbp+0F0h+dwInBufferSize], eax
0x180002a3a  cmp     word ptr [rbp+0F0h+var_D0], r12w
0x180002a3f  jz      short loc_180002A4A
0x180002a41  mov     ecx, 1
0x180002a46  or      word ptr [rbp+0F0h+var_134], cx
0x180002a4a  mov     [rbp+0F0h+var_D0], 80006h
0x180002a51  mov     ecx, r12d; Status
0x180002a54  mov     [rbp+0F0h+var_CC], eax
0x180002a57  mov     [rbp+rax+0F0h+InBuffer], rdx
0x180002a5c  add     [rbp+0F0h+dwInBufferSize], r13d
0x180002a60  call    cs:__imp_RtlNtStatusToDosError
0x180002a67  nop     dword ptr [rax+rax+00h]
0x180002a6c  mov     ebx, eax
0x180002a6e  test    eax, eax
0x180002a70  jle     short loc_180002A7B
0x180002a72  movzx   ebx, ax
0x180002a75  or      ebx, 80070000h
0x180002a7b  cmp     ebx, 0FFFFFFFFh
0x180002a7e  jg      short loc_180002A8C
0x180002a80  lea     rcx, aSetclddsmsgreq; "SetCldDsMsgRequestKey Failed"
0x180002a87  jmp     loc_180002BE7
0x180002a8c  mov     eax, 0Eh
0x180002a91  cmp     ax, word ptr [rbp+0F0h+var_134+2]
0x180002a95  jb      short loc_180002A9B
0x180002a97  mov     ecx, esi
0x180002a99  jmp     short loc_180002AEB
0x180002a9b  mov     ecx, [rbp+0F0h+dwInBufferSize]
0x180002a9e  mov     edx, 4
0x180002aa3  lea     rax, [rcx+3]
0x180002aa7  and     rax, 0FFFFFFFFFFFFFFFCh
0x180002aab  add     rax, rdx
0x180002aae  cmp     rax, 0F8h
0x180002ab4  jbe     short loc_180002ABD
0x180002ab6  mov     ecx, 0C0000023h
0x180002abb  jmp     short loc_180002AEB
0x180002abd  lea     eax, [rcx+3]
0x180002ac0  and     eax, 0FFFFFFFCh
0x180002ac3  mov     [rbp+0F0h+dwInBufferSize], eax
0x180002ac6  cmp     word ptr [rbp+0F0h+var_C0], r12w
0x180002acb  jz      short loc_180002AD6
0x180002acd  mov     ecx, 1
  ... truncated ...
```
