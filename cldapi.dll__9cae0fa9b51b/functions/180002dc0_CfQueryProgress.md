# CfQueryProgress

- ea: `0x180002dc0`
- end: `0x180003263`
- name: `CfQueryProgress`
- size: `1187`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001aa0`
- `0x18000231e`
- `0x180002dc0`
- `0x180012054`
- `0x180012c28`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180002f05`
- `ntdll!RtlNtStatusToDosError` at `0x180002f98`
- `ntdll!RtlNtStatusToDosError` at `0x180003023`
- `ntdll!RtlNtStatusToDosError` at `0x1800030b0`
- `ntdll!RtlNtStatusToDosError` at `0x180003140`
- `ntdll!RtlNtStatusToDosError` at `0x180002f05`
- `ntdll!RtlNtStatusToDosError` at `0x180002f98`
- `ntdll!RtlNtStatusToDosError` at `0x180003023`
- `ntdll!RtlNtStatusToDosError` at `0x1800030b0`
- `ntdll!RtlNtStatusToDosError` at `0x180003140`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180002e20`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180002e20`
- `FLTLIB!FilterSendMessage` at `0x18000319e`
- `FLTLIB!FilterSendMessage` at `0x18000319e`

## string_xrefs

- `0x180002fb8`: `SetCldMsgCommand Failed`

## pseudocode

```c
__int64 __fastcall CfQueryProgress(int a1, __int64 a2, unsigned int *a3)
{
  unsigned int v6; // esi
  unsigned int v7; // eax
  int v8; // ebx
  const wchar_t *v9; // rax
  NTSTATUS v10; // edi
  NTSTATUS v11; // ecx
  __int64 v12; // rcx
  signed int v13; // eax
  NTSTATUS v14; // ecx
  unsigned int v15; // eax
  signed int v16; // eax
  NTSTATUS v17; // ecx
  unsigned int v18; // eax
  signed int v19; // eax
  NTSTATUS v20; // ecx
  unsigned int v21; // eax
  signed int v22; // eax
  unsigned int v23; // eax
  signed int v24; // eax
  __int64 OutBuffer; // [rsp+40h] [rbp-C0h] BYREF
  DWORD BytesReturned; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+50h] [rbp-B0h] BYREF
  int v29; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v30; // [rsp+68h] [rbp-98h]
  int v31; // [rsp+70h] [rbp-90h]
  unsigned int v32; // [rsp+74h] [rbp-8Ch]
  int v33; // [rsp+78h] [rbp-88h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  bool v35; // [rsp+88h] [rbp-78h]
  __int64 InBuffer; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v37; // [rsp+C8h] [rbp-38h]
  int v38; // [rsp+CCh] [rbp-34h]
  _DWORD v39[2]; // [rsp+D0h] [rbp-30h] BYREF
  int v40; // [rsp+D8h] [rbp-28h]
  unsigned int v41; // [rsp+DCh] [rbp-24h]
  int v42; // [rsp+138h] [rbp+38h]
  unsigned int v43; // [rsp+13Ch] [rbp+3Ch]
  int v44; // [rsp+140h] [rbp+40h]
  unsigned int v45; // [rsp+144h] [rbp+44h]
  int v46; // [rsp+148h] [rbp+48h]
  unsigned int v47; // [rsp+14Ch] [rbp+4Ch]

  OutBuffer = 0;
  BytesReturned = 0;
  UnbiasedTime = 0;
  memset_0(&v29, 0, 0x58u);
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  v6 = *a3;
  v7 = 144 * *a3;
  OutBuffer = v7;
  if ( !v6 || a2 && v7 / v6 == 144 )
    v8 = 0;
  else
    v8 = 87;
  if ( v8 )
    v8 |= 0x80070000;
  if ( v8 > -1 )
  {
    v8 = GlobalPortInit(0);
    if ( v8 > -1 )
    {
      InBuffer = 1886219331;
      v37 = 200;
      v38 = 1507328;
      memset_0(v39, 0, 0xB8u);
      v10 = -1073741811;
      if ( HIWORD(v38) )
      {
        if ( ((v37 + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 1 <= 0xE0 )
        {
          v39[0] = 65543;
          v12 = (v37 + 3) & 0xFFFFFFFC;
          v37 = v12;
          v39[1] = v12;
          *((_BYTE *)&InBuffer + v12) = 1;
          v11 = 0;
          ++v37;
        }
        else
        {
          v11 = -1073741789;
        }
      }
      else
      {
        v11 = -1073741811;
      }
      v13 = RtlNtStatusToDosError(v11);
      v8 = v13;
      if ( v13 > 0 )
        v8 = (unsigned __int16)v13 | 0x80070000;
      if ( v8 > -1 )
      {
        if ( HIWORD(v38) > 1u )
        {
          if ( ((v37 + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 2 <= 0xE0 )
          {
            v15 = (v37 + 3) & 0xFFFFFFFC;
            v37 = v15;
            if ( (_WORD)v40 )
              LOWORD(v38) = v38 | 1;
            v40 = 131080;
            v41 = v15;
            *(_WORD *)((char *)&InBuffer + v15) = 16385;
            v14 = 0;
            v37 += 2;
          }
          else
          {
            v14 = -1073741789;
          }
        }
        else
        {
          v14 = -1073741811;
        }
        v16 = RtlNtStatusToDosError(v14);
        v8 = v16;
        if ( v16 > 0 )
          v8 = (unsigned __int16)v16 | 0x80070000;
        if ( v8 > -1 )
        {
          if ( HIWORD(v38) > 0xDu )
          {
            if ( ((v37 + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= 0xE0 )
            {
              v18 = (v37 + 3) & 0xFFFFFFFC;
              v37 = v18;
              if ( (_WORD)v42 )
                LOWORD(v38) = v38 | 1;
              v43 = v18;
              v42 = 262154;
              *(_DWORD *)((char *)&InBuffer + v18) = a1;
              v17 = 0;
              v37 += 4;
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
          v8 = v19;
          if ( v19 > 0 )
            v8 = (unsigned __int16)v19 | 0x80070000;
          if ( v8 > -1 )
          {
            if ( HIWORD(v38) > 0xEu )
            {
              if ( ((v37 + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0xE0 )
              {
                v21 = (v37 + 3) & 0xFFFFFFFC;
                v37 = v21;
                if ( (_WORD)v44 )
                  LOWORD(v38) = v38 | 1;
                v45 = v21;
                v44 = 524299;
                *(__int64 *)((char *)&InBuffer + v21) = a2;
                v20 = 0;
                v37 += 8;
              }
              else
              {
                v20 = -1073741789;
              }
            }
            else
            {
              v20 = -1073741811;
            }
            v22 = RtlNtStatusToDosError(v20);
            v8 = v22;
            if ( v22 > 0 )
              v8 = (unsigned __int16)v22 | 0x80070000;
            if ( v8 > -1 )
            {
              if ( HIWORD(v38) > 0xFu )
              {
                if ( ((v37 + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= 0xE0 )
                {
                  v23 = (v37 + 3) & 0xFFFFFFFC;
                  v37 = v23;
                  if ( (_WORD)v46 )
                    LOWORD(v38) = v38 | 1;
                  v46 = 262154;
                  v10 = 0;
                  v47 = v23;
                  *(_DWORD *)((char *)&InBuffer + v23) = OutBuffer;
                  v37 += 4;
                }
                else
                {
                  v10 = -1073741789;
                }
              }
              v24 = RtlNtStatusToDosError(v10);
              v8 = v24;
              if ( v24 > 0 )
                v8 = (unsigned __int16)v24 | 0x80070000;
              if ( v8 > -1 )
              {
                HIDWORD(InBuffer) = 0;
                LOWORD(v38) = v38 & 0xFFFD;
                v8 = FilterSendMessage(hPort, &InBuffer, 0xE0u, &OutBuffer, 8u, &BytesReturned);
                if ( (int)(v8 + 0x80000000) < 0 || v8 == -2147024774 )
                {
                  v9 = 0;
                  v6 = (unsigned int)OutBuffer / 0x90;
                  *a3 = (unsigned int)OutBuffer / 0x90;
                }
                else
                {
                  v9 = L"FilterSendMessage returned error";
                }
              }
              else
              {
                v9 = L"SetCldDsMsgQueryProgressBufferLength Failed";
              }
            }
            else
            {
              v9 = L"SetCldDsMsgQueryProgressBuffer Failed";
            }
          }
          else
          {
            v9 = L"SetCldDsMsgQueryProgressFlags Failed";
          }
        }
        else
        {
          v9 = L"SetCldMsgCommand Failed";
        }
      }
      else
      {
        v9 = L"SetVersion Failed";
      }
    }
    else
    {
      v9 = L"GlobalPortInit Failed";
    }
  }
  else
  {
    v9 = L"Invalid Parameter";
  }
  v30 = v9;
  v34 = OutBuffer;
  v35 = a2 != 0;
  v32 = v6;
  v31 = a1;
  v33 = 144;
  TlmLogApiReliability(0x20u, 0, 0, 0, 0, UnbiasedTime, &v29, v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180002dc0  mov     [rsp-8+arg_18], rbx
0x180002dc5  push    rbp
0x180002dc6  push    rsi
0x180002dc7  push    rdi
0x180002dc8  push    r12
0x180002dca  push    r13
0x180002dcc  push    r14
0x180002dce  push    r15
0x180002dd0  lea     rbp, [rsp-0B0h]
0x180002dd8  sub     rsp, 1B0h
0x180002ddf  mov     rax, cs:__security_cookie
0x180002de6  xor     rax, rsp
0x180002de9  mov     [rbp+0E0h+var_40], rax
0x180002df0  xor     r13d, r13d
0x180002df3  mov     r15, r8
0x180002df6  mov     r14, rdx
0x180002df9  mov     [rsp+1E0h+OutBuffer], r13
0x180002dfe  mov     r12d, ecx
0x180002e01  mov     [rsp+1E0h+BytesReturned], r13d
0x180002e06  xor     edx, edx; Val
0x180002e08  mov     [rsp+1E0h+UnbiasedTime], r13
0x180002e0d  lea     r8d, [r13+58h]; Size
0x180002e11  lea     rcx, [rsp+1E0h+var_180]; void *
0x180002e16  call    memset_0
0x180002e1b  lea     rcx, [rsp+1E0h+UnbiasedTime]; UnbiasedTime
0x180002e20  call    cs:__imp_QueryUnbiasedInterruptTime
0x180002e27  nop     dword ptr [rax+rax+00h]
0x180002e2c  mov     esi, [r15]
0x180002e2f  lea     eax, [rsi+rsi*8]
0x180002e32  shl     eax, 4
0x180002e35  mov     [rsp+1E0h+OutBuffer], rax
0x180002e3a  test    esi, esi
0x180002e3c  jz      short loc_180002E55
0x180002e3e  test    r14, r14
0x180002e41  jz      short loc_180002E4E
0x180002e43  xor     edx, edx
0x180002e45  div     esi
0x180002e47  cmp     eax, 90h
0x180002e4c  jz      short loc_180002E55
0x180002e4e  mov     ebx, 57h ; 'W'
0x180002e53  jmp     short loc_180002E58
0x180002e55  mov     ebx, r13d
0x180002e58  mov     eax, ebx
0x180002e5a  or      eax, 80070000h
0x180002e5f  test    ebx, ebx
0x180002e61  cmovnz  ebx, eax
0x180002e64  cmp     ebx, 0FFFFFFFFh
0x180002e67  jg      short loc_180002E75
0x180002e69  lea     rax, aInvalidParamet; "Invalid Parameter"
0x180002e70  jmp     loc_1800031DC
0x180002e75  xor     ecx, ecx
0x180002e77  call    GlobalPortInit
0x180002e7c  mov     ebx, eax
0x180002e7e  cmp     eax, 0FFFFFFFFh
0x180002e81  jg      short loc_180002E8F
0x180002e83  lea     rax, aGlobalportinit; "GlobalPortInit Failed"
0x180002e8a  jmp     loc_1800031DC
0x180002e8f  xor     edx, edx; Val
0x180002e91  mov     [rbp+0E0h+InBuffer], 706D6C43h
0x180002e99  mov     r8d, 0B8h; Size
0x180002e9f  mov     [rbp+0E0h+var_118], 0C8h
0x180002ea6  lea     rcx, [rbp+0E0h+var_110]; void *
0x180002eaa  mov     [rbp+0E0h+var_114], 170000h
0x180002eb1  call    memset_0
0x180002eb6  mov     edx, 1
0x180002ebb  mov     edi, 0C000000Dh
0x180002ec0  cmp     r13w, word ptr [rbp+0E0h+var_114+2]
0x180002ec5  jb      short loc_180002ECB
0x180002ec7  mov     ecx, edi
0x180002ec9  jmp     short loc_180002F05
0x180002ecb  mov     ecx, [rbp+0E0h+var_118]
0x180002ece  lea     rax, [rcx+3]
0x180002ed2  and     rax, 0FFFFFFFFFFFFFFFCh
0x180002ed6  add     rax, rdx
0x180002ed9  cmp     rax, 0E0h
0x180002edf  jbe     short loc_180002EE8
0x180002ee1  mov     ecx, 0C0000023h
0x180002ee6  jmp     short loc_180002F05
0x180002ee8  add     ecx, 3
0x180002eeb  mov     [rbp+0E0h+var_110], 10007h
0x180002ef2  and     ecx, 0FFFFFFFCh
0x180002ef5  mov     [rbp+0E0h+var_118], ecx
0x180002ef8  mov     [rbp+0E0h+var_10C], ecx
0x180002efb  mov     byte ptr [rbp+rcx+0E0h+InBuffer], dl
0x180002eff  mov     ecx, r13d; Status
0x180002f02  add     [rbp+0E0h+var_118], edx
0x180002f05  call    cs:__imp_RtlNtStatusToDosError
0x180002f0c  nop     dword ptr [rax+rax+00h]
0x180002f11  mov     ebx, eax
0x180002f13  test    eax, eax
0x180002f15  jle     short loc_180002F20
0x180002f17  movzx   ebx, ax
0x180002f1a  or      ebx, 80070000h
0x180002f20  cmp     ebx, 0FFFFFFFFh
0x180002f23  jg      short loc_180002F31
0x180002f25  lea     rax, aSetversionFail_0; "SetVersion Failed"
0x180002f2c  jmp     loc_1800031DC
0x180002f31  mov     r8d, 1
0x180002f37  cmp     r8w, word ptr [rbp+0E0h+var_114+2]
0x180002f3c  jb      short loc_180002F42
0x180002f3e  mov     ecx, edi
0x180002f40  jmp     short loc_180002F98
0x180002f42  mov     ecx, [rbp+0E0h+var_118]
0x180002f45  mov     edx, 2
0x180002f4a  lea     rax, [rcx+3]
0x180002f4e  and     rax, 0FFFFFFFFFFFFFFFCh
0x180002f52  add     rax, rdx
0x180002f55  cmp     rax, 0E0h
0x180002f5b  jbe     short loc_180002F64
0x180002f5d  mov     ecx, 0C0000023h
0x180002f62  jmp     short loc_180002F98
0x180002f64  lea     eax, [rcx+3]
0x180002f67  and     eax, 0FFFFFFFCh
0x180002f6a  mov     ecx, eax
0x180002f6c  mov     [rbp+0E0h+var_118], eax
0x180002f6f  cmp     word ptr [rbp+0E0h+var_108], r13w
0x180002f74  jz      short loc_180002F7B
0x180002f76  or      word ptr [rbp+0E0h+var_114], r8w
0x180002f7b  mov     rax, rcx
0x180002f7e  mov     [rbp+0E0h+var_108], 20008h
0x180002f85  mov     ecx, 4001h
0x180002f8a  mov     [rbp+0E0h+var_104], eax
0x180002f8d  mov     word ptr [rbp+rax+0E0h+InBuffer], cx
0x180002f92  mov     ecx, r13d; Status
0x180002f95  add     [rbp+0E0h+var_118], edx
0x180002f98  call    cs:__imp_RtlNtStatusToDosError
0x180002f9f  nop     dword ptr [rax+rax+00h]
0x180002fa4  mov     ebx, eax
0x180002fa6  test    eax, eax
0x180002fa8  jle     short loc_180002FB3
0x180002faa  movzx   ebx, ax
0x180002fad  or      ebx, 80070000h
0x180002fb3  cmp     ebx, 0FFFFFFFFh
0x180002fb6  jg      short loc_180002FC4
0x180002fb8  lea     rax, aSetcldmsgcomma_0; "SetCldMsgCommand Failed"
0x180002fbf  jmp     loc_1800031DC
0x180002fc4  mov     eax, 0Dh
0x180002fc9  lea     edx, [rax-9]
0x180002fcc  cmp     ax, word ptr [rbp+0E0h+var_114+2]
0x180002fd0  jb      short loc_180002FD6
0x180002fd2  mov     ecx, edi
0x180002fd4  jmp     short loc_180003023
0x180002fd6  mov     ecx, [rbp+0E0h+var_118]
0x180002fd9  lea     rax, [rcx+3]
0x180002fdd  and     rax, 0FFFFFFFFFFFFFFFCh
0x180002fe1  add     rax, rdx
0x180002fe4  cmp     rax, 0E0h
0x180002fea  jbe     short loc_180002FF3
0x180002fec  mov     ecx, 0C0000023h
0x180002ff1  jmp     short loc_180003023
0x180002ff3  lea     eax, [rcx+3]
0x180002ff6  and     eax, 0FFFFFFFCh
0x180002ff9  mov     ecx, eax
0x180002ffb  mov     [rbp+0E0h+var_118], eax
0x180002ffe  cmp     word ptr [rbp+0E0h+var_A8], r13w
0x180003003  jz      short loc_18000300E
0x180003005  mov     eax, 1
0x18000300a  or      word ptr [rbp+0E0h+var_114], ax
0x18000300e  mov     [rbp+0E0h+var_A4], ecx
0x180003011  mov     [rbp+0E0h+var_A8], 4000Ah
0x180003018  mov     dword ptr [rbp+rcx+0E0h+InBuffer], r12d
0x18000301d  mov     ecx, r13d; Status
0x180003020  add     [rbp+0E0h+var_118], edx
0x180003023  call    cs:__imp_RtlNtStatusToDosError
0x18000302a  nop     dword ptr [rax+rax+00h]
0x18000302f  mov     ebx, eax
0x180003031  test    eax, eax
0x180003033  jle     short loc_18000303E
0x180003035  movzx   ebx, ax
0x180003038  or      ebx, 80070000h
0x18000303e  cmp     ebx, 0FFFFFFFFh
0x180003041  jg      short loc_18000304F
0x180003043  lea     rax, aSetclddsmsgque_0; "SetCldDsMsgQueryProgressFlags Failed"
0x18000304a  jmp     loc_1800031DC
0x18000304f  mov     eax, 0Eh
0x180003054  cmp     ax, word ptr [rbp+0E0h+var_114+2]
0x180003058  jb      short loc_18000305E
0x18000305a  mov     ecx, edi
0x18000305c  jmp     short loc_1800030B0
0x18000305e  mov     ecx, [rbp+0E0h+var_118]
0x180003061  mov     edx, 8
0x180003066  lea     rax, [rcx+3]
0x18000306a  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000306e  add     rax, rdx
0x180003071  cmp     rax, 0E0h
0x180003077  jbe     short loc_180003080
0x180003079  mov     ecx, 0C0000023h
0x18000307e  jmp     short loc_1800030B0
0x180003080  lea     eax, [rcx+3]
0x180003083  and     eax, 0FFFFFFFCh
0x180003086  mov     ecx, eax
0x180003088  mov     [rbp+0E0h+var_118], eax
0x18000308b  cmp     word ptr [rbp+0E0h+var_A0], r13w
0x180003090  jz      short loc_18000309B
0x180003092  mov     eax, 1
0x180003097  or      word ptr [rbp+0E0h+var_114], ax
0x18000309b  mov     [rbp+0E0h+var_9C], ecx
0x18000309e  mov     [rbp+0E0h+var_A0], 8000Bh
0x1800030a5  mov     [rbp+rcx+0E0h+InBuffer], r14
0x1800030aa  mov     ecx, r13d; Status
0x1800030ad  add     [rbp+0E0h+var_118], edx
0x1800030b0  call    cs:__imp_RtlNtStatusToDosError
0x1800030b7  nop     dword ptr [rax+rax+00h]
0x1800030bc  mov     ebx, eax
0x1800030be  test    eax, eax
0x1800030c0  jle     short loc_1800030CB
0x1800030c2  movzx   ebx, ax
0x1800030c5  or      ebx, 80070000h
0x1800030cb  cmp     ebx, 0FFFFFFFFh
0x1800030ce  jg      short loc_1800030DC
0x1800030d0  lea     rax, aSetclddsmsgque_1; "SetCldDsMsgQueryProgressBuffer Failed"
0x1800030d7  jmp     loc_1800031DC
0x1800030dc  mov     eax, 0Fh
0x1800030e1  cmp     ax, word ptr [rbp+0E0h+var_114+2]
0x1800030e5  jnb     short loc_18000313E
0x1800030e7  mov     ecx, [rbp+0E0h+var_118]
0x1800030ea  mov     r8d, 4
0x1800030f0  lea     rax, [rcx+3]
0x1800030f4  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800030f8  add     rax, r8
0x1800030fb  cmp     rax, 0E0h
0x180003101  jbe     short loc_18000310A
0x180003103  mov     edi, 0C0000023h
0x180003108  jmp     short loc_18000313E
0x18000310a  mov     edx, dword ptr [rsp+1E0h+OutBuffer]
0x18000310e  lea     eax, [rcx+3]
0x180003111  and     eax, 0FFFFFFFCh
0x180003114  mov     ecx, eax
0x180003116  mov     [rbp+0E0h+var_118], eax
0x180003119  cmp     word ptr [rbp+0E0h+var_98], r13w
0x18000311e  jz      short loc_180003129
0x180003120  mov     eax, 1
0x180003125  or      word ptr [rbp+0E0h+var_114], ax
0x180003129  mov     [rbp+0E0h+var_98], 4000Ah
0x180003130  mov     edi, r13d
0x180003133  mov     [rbp+0E0h+var_94], ecx
0x180003136  mov     dword ptr [rbp+rcx+0E0h+InBuffer], edx
0x18000313a  add     [rbp+0E0h+var_118], r8d
0x18000313e  mov     ecx, edi; Status
0x180003140  call    cs:__imp_RtlNtStatusToDosError
0x180003147  nop     dword ptr [rax+rax+00h]
0x18000314c  mov     ebx, eax
0x18000314e  test    eax, eax
0x180003150  jle     short loc_18000315B
0x180003152  movzx   ebx, ax
0x180003155  or      ebx, 80070000h
0x18000315b  cmp     ebx, 0FFFFFFFFh
0x18000315e  jg      short loc_180003169
0x180003160  lea     rax, aSetclddsmsgque; "SetCldDsMsgQueryProgressBufferLength Fa"...
0x180003167  jmp     short loc_1800031DC
0x180003169  mov     rcx, qword ptr cs:hPort; hPort
0x180003170  lea     r9, [rsp+1E0h+OutBuffer]; lpOutBuffer
0x180003175  mov     eax, 0FFFDh
0x18000317a  mov     dword ptr [rbp+0E0h+InBuffer+4], r13d
0x18000317e  and     word ptr [rbp+0E0h+var_114], ax
0x180003182  lea     rdx, [rbp+0E0h+InBuffer]; lpInBuffer
0x180003186  lea     rax, [rsp+1E0h+BytesReturned]
0x18000318b  mov     r8d, 0E0h; dwInBufferSize
0x180003191  mov     [rsp+1E0h+lpBytesReturned], rax; lpBytesReturned
0x180003196  mov     [rsp+1E0h+dwOutBufferSize], 8; dwOutBufferSize
0x18000319e  call    cs:__imp_FilterSendMessage
0x1800031a5  nop     dword ptr [rax+rax+00h]
0x1800031aa  mov     ecx, 80000000h
0x1800031af  mov     ebx, eax
0x1800031b1  add     eax, ecx
0x1800031b3  test    ecx, eax
0x1800031b5  jnz     short loc_1800031C8
0x1800031b7  cmp     ebx, 8007007Ah
0x1800031bd  jz      short loc_1800031C8
0x1800031bf  lea     rax, aFiltersendmess_1; "FilterSendMessage returned error"
0x1800031c6  jmp     short loc_1800031DC
0x1800031c8  mov     eax, 38E38E39h
0x1800031cd  mul     dword ptr [rsp+1E0h+OutBuffer]
0x1800031d1  mov     rax, r13
0x1800031d4  mov     esi, edx
0x1800031d6  shr     esi, 5
0x1800031d9  mov     [r15], esi
0x1800031dc  mov     [rsp+1E0h+var_178], rax
0x1800031e1  test    r14, r14
0x1800031e4  mov     eax, dword ptr [rsp+1E0h+OutBuffer]
0x1800031e8  mov     ecx, 20h ; ' '
0x1800031ed  mov     dword ptr [rbp+0E0h+var_160], eax
0x1800031f0  setnz   [rbp+0E0h+var_158]
0x1800031f4  mov     eax, dword ptr [rsp+1E0h+OutBuffer+4]
0x1800031f8  xor     r9d, r9d
0x1800031fb  mov     dword ptr [rbp+0E0h+var_160+4], eax
0x1800031fe  xor     r8d, r8d
0x180003201  mov     [rsp+1E0h+var_1A8], ebx
0x180003205  lea     rax, [rsp+1E0h+var_180]
0x18000320a  mov     [rsp+1E0h+var_1B0], rax
0x18000320f  xor     edx, edx
0x180003211  mov     rax, [rsp+1E0h+UnbiasedTime]
0x180003216  mov     [rsp+1E0h+lpBytesReturned], rax
0x18000321b  mov     qword ptr [rsp+1E0h+dwOutBufferSize], r13
0x180003220  mov     [rsp+1E0h+var_16C], esi
0x180003224  mov     [rsp+1E0h+var_170], r12d
0x180003229  mov     [rsp+1E0h+var_168], 90h
0x180003231  call    TlmLogApiReliability
0x180003236  mov     eax, ebx
0x180003238  mov     rcx, [rbp+0E0h+var_40]
  ... truncated ...
```
