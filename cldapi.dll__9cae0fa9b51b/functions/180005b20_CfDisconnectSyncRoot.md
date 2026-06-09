# CfDisconnectSyncRoot

- ea: `0x180005b20`
- end: `0x180005ffb`
- name: `CfDisconnectSyncRoot`
- size: `1243`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x18000231e`
- `0x180005b20`
- `0x18000bb10`
- `0x18000c024`
- `0x180012054`
- `0x180012c28`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180005f56`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180005f56`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180005f6d`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180005f6d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180005f9c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180005f9c`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180005f89`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180005f89`
- `ntdll!RtlNtStatusToDosError` at `0x180005c75`
- `ntdll!RtlNtStatusToDosError` at `0x180005cf7`
- `ntdll!RtlNtStatusToDosError` at `0x180005d7b`
- `ntdll!RtlNtStatusToDosError` at `0x180005e06`
- `ntdll!RtlNtStatusToDosError` at `0x180005e9c`
- `ntdll!RtlNtStatusToDosError` at `0x180005c75`
- `ntdll!RtlNtStatusToDosError` at `0x180005cf7`
- `ntdll!RtlNtStatusToDosError` at `0x180005d7b`
- `ntdll!RtlNtStatusToDosError` at `0x180005e06`
- `ntdll!RtlNtStatusToDosError` at `0x180005e9c`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180005b66`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180005b66`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005bb1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005fbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005bb1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005fbd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005bca`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005bca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005fd1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005fd1`
- `FLTLIB!FilterSendMessage` at `0x180005eec`
- `FLTLIB!FilterSendMessage` at `0x180005eec`

## pseudocode

```c
__int64 __fastcall CfDisconnectSyncRoot(__int64 a1)
{
  _DWORD *v2; // rsi
  const WCHAR *v3; // r12
  const WCHAR *v4; // r13
  __int64 v5; // r14
  int v6; // edi
  HANDLE ProcessHeap; // rax
  NTSTATUS v8; // r15d
  NTSTATUS v9; // ecx
  __int64 v10; // rcx
  unsigned int v11; // ecx
  signed int v12; // eax
  NTSTATUS v13; // ecx
  __int64 v14; // rcx
  __int64 v15; // rax
  signed int v16; // eax
  NTSTATUS v17; // ecx
  __int64 v18; // rcx
  __int64 v19; // rax
  signed int v20; // eax
  NTSTATUS v21; // ecx
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rax
  signed int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rax
  signed int v29; // eax
  _QWORD *v30; // rax
  HANDLE v31; // rax
  int v33[4]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v34; // [rsp+50h] [rbp-29h]
  __int64 v35; // [rsp+58h] [rbp-21h]
  DWORD BytesReturned; // [rsp+E0h] [rbp+67h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+E8h] [rbp+6Fh] BYREF
  __int64 Buffer; // [rsp+F0h] [rbp+77h] BYREF

  BytesReturned = 0;
  UnbiasedTime = 0;
  v2 = 0;
  v3 = 0;
  v4 = 0;
  memset_0(v33, 0, 0x58u);
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  v5 = CfpReferenceSyncRoot(a1);
  v6 = v5 == 0 ? 0x57 : 0;
  if ( !v5 )
    v6 |= 0x80070000;
  if ( v6 >= 0 )
  {
    v6 = GlobalPortInit(1);
    if ( v6 >= 0 )
    {
      ProcessHeap = GetProcessHeap();
      v2 = HeapAlloc(ProcessHeap, 8u, 0xE8u);
      v6 = v2 == 0 ? 8 : 0;
      if ( !v2 )
        v6 |= 0x80070000;
      if ( v6 >= 0 )
      {
        *(_QWORD *)v2 = 1886219331;
        v2[2] = 200;
        v2[3] = 1507328;
        memset_0(v2 + 4, 0, 0xB8u);
        v8 = -1073741811;
        if ( *((_WORD *)v2 + 7) )
        {
          v10 = (unsigned int)v2[2];
          if ( ((v10 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 1 <= 0xE8 )
          {
            v11 = (v10 + 3) & 0xFFFFFFFC;
            v2[2] = v11;
            v2[5] = v11;
            v2[4] = 65543;
            *((_BYTE *)v2 + v11) = 1;
            ++v2[2];
            v9 = 0;
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
        v12 = RtlNtStatusToDosError(v9);
        v6 = v12;
        if ( v12 > 0 )
          v6 = (unsigned __int16)v12 | 0x80070000;
        if ( v6 >= 0 )
        {
          if ( *((_WORD *)v2 + 7) > 1u )
          {
            v14 = (unsigned int)v2[2];
            if ( ((v14 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 2 <= 0xE8 )
            {
              v15 = ((_DWORD)v14 + 3) & 0xFFFFFFFC;
              v2[2] = v15;
              if ( *((_WORD *)v2 + 12) )
                *((_WORD *)v2 + 6) |= 1u;
              v2[6] = 131080;
              v13 = 0;
              v2[7] = v15;
              *(_WORD *)((char *)v2 + v15) = 5;
              v2[2] += 2;
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
          v16 = RtlNtStatusToDosError(v13);
          v6 = v16;
          if ( v16 > 0 )
            v6 = (unsigned __int16)v16 | 0x80070000;
          if ( v6 >= 0 )
          {
            if ( *((_WORD *)v2 + 7) > 4u )
            {
              v18 = (unsigned int)v2[2];
              if ( ((v18 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0xE8 )
              {
                v19 = ((_DWORD)v18 + 3) & 0xFFFFFFFC;
                v2[2] = v19;
                if ( *((_WORD *)v2 + 24) )
                  *((_WORD *)v2 + 6) |= 1u;
                v2[12] = 524294;
                v17 = 0;
                v2[13] = v19;
                *(_QWORD *)((char *)v2 + v19) = v5;
                v2[2] += 8;
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
            v20 = RtlNtStatusToDosError(v17);
            v6 = v20;
            if ( v20 > 0 )
              v6 = (unsigned __int16)v20 | 0x80070000;
            if ( v6 >= 0 )
            {
              if ( *((_WORD *)v2 + 7) > 2u )
              {
                v22 = (unsigned int)v2[2];
                if ( ((v22 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0xE8 )
                {
                  v23 = *(_QWORD *)(v5 + 8);
                  v24 = ((_DWORD)v22 + 3) & 0xFFFFFFFC;
                  v2[2] = v24;
                  if ( *((_WORD *)v2 + 16) )
                    *((_WORD *)v2 + 6) |= 1u;
                  v2[8] = 524299;
                  v21 = 0;
                  v2[9] = v24;
                  *(_QWORD *)((char *)v2 + v24) = v23;
                  v2[2] += 8;
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
              v25 = RtlNtStatusToDosError(v21);
              v6 = v25;
              if ( v25 > 0 )
                v6 = (unsigned __int16)v25 | 0x80070000;
              if ( v6 >= 0 )
              {
                if ( *((_WORD *)v2 + 7) > 0x16u )
                {
                  v26 = (unsigned int)v2[2];
                  if ( ((v26 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0xE8 )
                  {
                    v27 = **(_QWORD **)(v5 + 16);
                    v28 = ((_DWORD)v26 + 3) & 0xFFFFFFFC;
                    v2[2] = v28;
                    if ( *((_WORD *)v2 + 96) )
                      *((_WORD *)v2 + 6) |= 1u;
                    v2[48] = 524294;
                    v8 = 0;
                    v2[49] = v28;
                    *(_QWORD *)((char *)v2 + v28) = v27;
                    v2[2] += 8;
                  }
                  else
                  {
                    v8 = -1073741789;
                  }
                }
                v29 = RtlNtStatusToDosError(v8);
                v6 = v29;
                if ( v29 > 0 )
                  v6 = (unsigned __int16)v29 | 0x80070000;
                if ( v6 >= 0 )
                {
                  v2[1] = 0;
                  *((_WORD *)v2 + 6) &= ~2u;
                  v6 = FilterSendMessage(hPort, v2, 0xE8u, 0, 0, &BytesReturned);
                }
              }
            }
          }
        }
      }
    }
  }
  v35 = a1;
  if ( v5 )
  {
    v30 = *(_QWORD **)(v5 + 16);
    v3 = (const WCHAR *)v30 + 14;
    v4 = (const WCHAR *)v30 + 270;
    v34 = *v30;
  }
  TlmLogApiReliability(0xCu, 0, 0, v3, v4, UnbiasedTime, v33, v6);
  if ( v5 )
  {
    Buffer = a1;
    RtlAcquireSRWLockExclusive(&qword_18002ACF8);
    if ( RtlLookupElementGenericTableAvl(&stru_18002AC90, &Buffer) )
      RtlDeleteElementGenericTableAvl(&stru_18002AC90, &Buffer);
    RtlReleaseSRWLockExclusive(&qword_18002ACF8);
    CfpReleaseSyncRoot(v5);
    CfpReleaseSyncRoot(v5);
  }
  if ( v2 )
  {
    v31 = GetProcessHeap();
    HeapFree(v31, 0, v2);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180005b20  mov     [rsp-8+arg_18], rbx
0x180005b25  push    rbp
0x180005b26  push    rsi
0x180005b27  push    rdi
0x180005b28  push    r12
0x180005b2a  push    r13
0x180005b2c  push    r14
0x180005b2e  push    r15
0x180005b30  lea     rbp, [rsp-27h]
0x180005b35  sub     rsp, 0A0h
0x180005b3c  xor     r15d, r15d
0x180005b3f  mov     rbx, rcx
0x180005b42  xor     edx, edx; Val
0x180005b44  mov     [rbp+57h+BytesReturned], r15d
0x180005b48  lea     rcx, [rbp+57h+var_90]; void *
0x180005b4c  mov     [rbp+57h+UnbiasedTime], r15
0x180005b50  mov     esi, r15d
0x180005b53  mov     r12d, r15d
0x180005b56  lea     r8d, [r15+58h]; Size
0x180005b5a  mov     r13d, r15d
0x180005b5d  call    memset_0
0x180005b62  lea     rcx, [rbp+57h+UnbiasedTime]; UnbiasedTime
0x180005b66  call    cs:__imp_QueryUnbiasedInterruptTime
0x180005b6d  nop     dword ptr [rax+rax+00h]
0x180005b72  mov     rcx, rbx
0x180005b75  call    CfpReferenceSyncRoot
0x180005b7a  mov     rcx, rax
0x180005b7d  mov     r14, rax
0x180005b80  neg     rcx
0x180005b83  sbb     edi, edi
0x180005b85  not     edi
0x180005b87  and     edi, 57h
0x180005b8a  mov     ecx, edi
0x180005b8c  or      ecx, 80070000h
0x180005b92  test    rax, rax
0x180005b95  cmovz   edi, ecx
0x180005b98  test    edi, edi
0x180005b9a  js      loc_180005EFA
0x180005ba0  mov     cl, 1
0x180005ba2  call    GlobalPortInit
0x180005ba7  mov     edi, eax
0x180005ba9  test    eax, eax
0x180005bab  js      loc_180005EFA
0x180005bb1  call    cs:__imp_GetProcessHeap
0x180005bb8  nop     dword ptr [rax+rax+00h]
0x180005bbd  lea     edx, [r15+8]; dwFlags
0x180005bc1  mov     r8d, 0E8h; dwBytes
0x180005bc7  mov     rcx, rax; hHeap
0x180005bca  call    cs:__imp_HeapAlloc
0x180005bd1  nop     dword ptr [rax+rax+00h]
0x180005bd6  mov     rsi, rax
0x180005bd9  neg     rax
0x180005bdc  sbb     edi, edi
0x180005bde  not     edi
0x180005be0  and     edi, 8
0x180005be3  mov     eax, edi
0x180005be5  or      eax, 80070000h
0x180005bea  test    rsi, rsi
0x180005bed  cmovz   edi, eax
0x180005bf0  test    edi, edi
0x180005bf2  js      loc_180005EFA
0x180005bf8  xor     edx, edx; Val
0x180005bfa  mov     qword ptr [rsi], 706D6C43h
0x180005c01  mov     r8d, 0B8h; Size
0x180005c07  mov     dword ptr [rsi+8], 0C8h
0x180005c0e  lea     rcx, [rsi+10h]; void *
0x180005c12  mov     dword ptr [rsi+0Ch], 170000h
0x180005c19  call    memset_0
0x180005c1e  mov     eax, r15d
0x180005c21  mov     r15d, 0C000000Dh
0x180005c27  cmp     ax, [rsi+0Eh]
0x180005c2b  jb      short loc_180005C32
0x180005c2d  mov     ecx, r15d
0x180005c30  jmp     short loc_180005C75
0x180005c32  mov     ecx, [rsi+8]
0x180005c35  mov     edx, 1
0x180005c3a  lea     rax, [rcx+3]
0x180005c3e  and     rax, 0FFFFFFFFFFFFFFFCh
0x180005c42  add     rax, rdx
0x180005c45  cmp     rax, 0E8h
0x180005c4b  jbe     short loc_180005C54
0x180005c4d  mov     ecx, 0C0000023h
0x180005c52  jmp     short loc_180005C75
0x180005c54  lea     eax, [rcx+3]
0x180005c57  and     eax, 0FFFFFFFCh
0x180005c5a  mov     ecx, eax
0x180005c5c  mov     [rsi+8], ecx
0x180005c5f  mov     [rsi+14h], ecx
0x180005c62  mov     dword ptr [rsi+10h], 10007h
0x180005c69  mov     [rax+rsi], dl
0x180005c6c  add     [rsi+8], edx
0x180005c6f  xor     r8d, r8d
0x180005c72  mov     ecx, r8d; Status
0x180005c75  call    cs:__imp_RtlNtStatusToDosError
0x180005c7c  nop     dword ptr [rax+rax+00h]
0x180005c81  xor     edx, edx
0x180005c83  mov     edi, eax
0x180005c85  test    eax, eax
0x180005c87  jle     short loc_180005C92
0x180005c89  movzx   edi, ax
0x180005c8c  or      edi, 80070000h
0x180005c92  test    edi, edi
0x180005c94  js      loc_180005EFA
0x180005c9a  mov     r9d, 2
0x180005ca0  lea     r8d, [r9-1]
0x180005ca4  cmp     r8w, [rsi+0Eh]
0x180005ca9  jb      short loc_180005CB0
0x180005cab  mov     ecx, r15d
0x180005cae  jmp     short loc_180005CF7
0x180005cb0  mov     ecx, [rsi+8]
0x180005cb3  lea     rax, [rcx+3]
0x180005cb7  and     rax, 0FFFFFFFFFFFFFFFCh
0x180005cbb  add     rax, r9
0x180005cbe  cmp     rax, 0E8h
0x180005cc4  jbe     short loc_180005CCD
0x180005cc6  mov     ecx, 0C0000023h
0x180005ccb  jmp     short loc_180005CF7
0x180005ccd  lea     eax, [rcx+3]
0x180005cd0  and     eax, 0FFFFFFFCh
0x180005cd3  mov     [rsi+8], eax
0x180005cd6  cmp     [rsi+18h], dx
0x180005cda  jz      short loc_180005CE1
0x180005cdc  or      [rsi+0Ch], r8w
0x180005ce1  mov     dword ptr [rsi+18h], 20008h
0x180005ce8  mov     ecx, edx; Status
0x180005cea  mov     [rsi+1Ch], eax
0x180005ced  mov     word ptr [rax+rsi], 5
0x180005cf3  add     [rsi+8], r9d
0x180005cf7  call    cs:__imp_RtlNtStatusToDosError
0x180005cfe  nop     dword ptr [rax+rax+00h]
0x180005d03  xor     edx, edx
0x180005d05  mov     edi, eax
0x180005d07  test    eax, eax
0x180005d09  jle     short loc_180005D14
0x180005d0b  movzx   edi, ax
0x180005d0e  or      edi, 80070000h
0x180005d14  test    edi, edi
0x180005d16  js      loc_180005EFA
0x180005d1c  mov     eax, 4
0x180005d21  cmp     ax, [rsi+0Eh]
0x180005d25  jb      short loc_180005D2C
0x180005d27  mov     ecx, r15d
0x180005d2a  jmp     short loc_180005D7B
0x180005d2c  mov     ecx, [rsi+8]
0x180005d2f  mov     r8d, 8
0x180005d35  lea     rax, [rcx+3]
0x180005d39  and     rax, 0FFFFFFFFFFFFFFFCh
0x180005d3d  add     rax, r8
0x180005d40  cmp     rax, 0E8h
0x180005d46  jbe     short loc_180005D4F
0x180005d48  mov     ecx, 0C0000023h
0x180005d4d  jmp     short loc_180005D7B
0x180005d4f  lea     eax, [rcx+3]
0x180005d52  and     eax, 0FFFFFFFCh
0x180005d55  mov     [rsi+8], eax
0x180005d58  cmp     [rsi+30h], dx
0x180005d5c  jz      short loc_180005D67
0x180005d5e  mov     ecx, 1
0x180005d63  or      [rsi+0Ch], cx
0x180005d67  mov     dword ptr [rsi+30h], 80006h
0x180005d6e  mov     ecx, edx; Status
0x180005d70  mov     [rsi+34h], eax
0x180005d73  mov     [rax+rsi], r14
0x180005d77  add     [rsi+8], r8d
0x180005d7b  call    cs:__imp_RtlNtStatusToDosError
0x180005d82  nop     dword ptr [rax+rax+00h]
0x180005d87  xor     r8d, r8d
0x180005d8a  mov     edi, eax
0x180005d8c  test    eax, eax
0x180005d8e  jle     short loc_180005D99
0x180005d90  movzx   edi, ax
0x180005d93  or      edi, 80070000h
0x180005d99  test    edi, edi
0x180005d9b  js      loc_180005EFA
0x180005da1  mov     eax, 2
0x180005da6  cmp     ax, [rsi+0Eh]
0x180005daa  jb      short loc_180005DB1
0x180005dac  mov     ecx, r15d
0x180005daf  jmp     short loc_180005E06
0x180005db1  mov     ecx, [rsi+8]
0x180005db4  mov     r9d, 8
0x180005dba  lea     rax, [rcx+3]
0x180005dbe  and     rax, 0FFFFFFFFFFFFFFFCh
0x180005dc2  add     rax, r9
0x180005dc5  cmp     rax, 0E8h
0x180005dcb  jbe     short loc_180005DD4
0x180005dcd  mov     ecx, 0C0000023h
0x180005dd2  jmp     short loc_180005E06
0x180005dd4  mov     rdx, [r14+8]
0x180005dd8  lea     eax, [rcx+3]
0x180005ddb  and     eax, 0FFFFFFFCh
0x180005dde  mov     [rsi+8], eax
0x180005de1  cmp     [rsi+20h], r8w
0x180005de6  jz      short loc_180005DF1
0x180005de8  mov     ecx, 1
0x180005ded  or      [rsi+0Ch], cx
0x180005df1  mov     dword ptr [rsi+20h], 8000Bh
0x180005df8  mov     ecx, r8d; Status
0x180005dfb  mov     [rsi+24h], eax
0x180005dfe  mov     [rax+rsi], rdx
0x180005e02  add     [rsi+8], r9d
0x180005e06  call    cs:__imp_RtlNtStatusToDosError
0x180005e0d  nop     dword ptr [rax+rax+00h]
0x180005e12  xor     r8d, r8d
0x180005e15  mov     edi, eax
0x180005e17  test    eax, eax
0x180005e19  jle     short loc_180005E24
0x180005e1b  movzx   edi, ax
0x180005e1e  or      edi, 80070000h
0x180005e24  test    edi, edi
0x180005e26  js      loc_180005EFA
0x180005e2c  mov     eax, 16h
0x180005e31  cmp     ax, [rsi+0Eh]
0x180005e35  jnb     short loc_180005E99
0x180005e37  mov     ecx, [rsi+8]
0x180005e3a  mov     r9d, 8
0x180005e40  lea     rax, [rcx+3]
0x180005e44  and     rax, 0FFFFFFFFFFFFFFFCh
0x180005e48  add     rax, r9
0x180005e4b  cmp     rax, 0E8h
0x180005e51  jbe     short loc_180005E5B
0x180005e53  mov     r15d, 0C0000023h
0x180005e59  jmp     short loc_180005E99
0x180005e5b  mov     rax, [r14+10h]
0x180005e5f  mov     rdx, [rax]
0x180005e62  lea     eax, [rcx+3]
0x180005e65  and     eax, 0FFFFFFFCh
0x180005e68  mov     [rsi+8], eax
0x180005e6b  cmp     [rsi+0C0h], r8w
0x180005e73  jz      short loc_180005E7E
0x180005e75  mov     ecx, 1
0x180005e7a  or      [rsi+0Ch], cx
0x180005e7e  mov     dword ptr [rsi+0C0h], 80006h
0x180005e88  mov     r15d, r8d
0x180005e8b  mov     [rsi+0C4h], eax
0x180005e91  mov     [rax+rsi], rdx
0x180005e95  add     [rsi+8], r9d
0x180005e99  mov     ecx, r15d; Status
0x180005e9c  call    cs:__imp_RtlNtStatusToDosError
0x180005ea3  nop     dword ptr [rax+rax+00h]
0x180005ea8  xor     r15d, r15d
0x180005eab  mov     edi, eax
0x180005ead  test    eax, eax
0x180005eaf  jle     short loc_180005EBA
0x180005eb1  movzx   edi, ax
0x180005eb4  or      edi, 80070000h
0x180005eba  test    edi, edi
0x180005ebc  js      short loc_180005EFA
0x180005ebe  mov     eax, 0FFFDh
0x180005ec3  mov     [rsi+4], r15d
0x180005ec7  and     [rsi+0Ch], ax
0x180005ecb  xor     r9d, r9d; lpOutBuffer
0x180005ece  mov     rcx, qword ptr cs:hPort; hPort
0x180005ed5  lea     rax, [rbp+57h+BytesReturned]
0x180005ed9  mov     [rsp+0D0h+lpBytesReturned], rax; lpBytesReturned
0x180005ede  mov     r8d, 0E8h; dwInBufferSize
0x180005ee4  mov     rdx, rsi; lpInBuffer
0x180005ee7  mov     [rsp+0D0h+dwOutBufferSize], r15d; dwOutBufferSize
0x180005eec  call    cs:__imp_FilterSendMessage
0x180005ef3  nop     dword ptr [rax+rax+00h]
0x180005ef8  mov     edi, eax
0x180005efa  mov     [rbp+57h+var_78], rbx
0x180005efe  test    r14, r14
0x180005f01  jz      short loc_180005F19
0x180005f03  mov     rax, [r14+10h]
0x180005f07  lea     r12, [rax+1Ch]
0x180005f0b  lea     r13, [rax+21Ch]
0x180005f12  mov     rax, [rax]
0x180005f15  mov     [rbp+57h+var_80], rax
0x180005f19  mov     [rsp+0D0h+var_98], edi
0x180005f1d  lea     rax, [rbp+57h+var_90]
0x180005f21  mov     [rsp+0D0h+var_A0], rax
0x180005f26  mov     ecx, 0Ch
0x180005f2b  mov     rax, [rbp+57h+UnbiasedTime]
0x180005f2f  mov     r9, r12
0x180005f32  mov     [rsp+0D0h+lpBytesReturned], rax
0x180005f37  xor     r8d, r8d
0x180005f3a  xor     edx, edx
0x180005f3c  mov     qword ptr [rsp+0D0h+dwOutBufferSize], r13
0x180005f41  call    TlmLogApiReliability
0x180005f46  test    r14, r14
0x180005f49  jz      short loc_180005FB8
0x180005f4b  lea     rcx, qword_18002ACF8
0x180005f52  mov     [rbp+57h+Buffer], rbx
0x180005f56  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180005f5d  nop     dword ptr [rax+rax+00h]
0x180005f62  lea     rdx, [rbp+57h+Buffer]; Buffer
0x180005f66  lea     rcx, stru_18002AC90; Table
0x180005f6d  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180005f74  nop     dword ptr [rax+rax+00h]
0x180005f79  test    rax, rax
0x180005f7c  jz      short loc_180005F95
0x180005f7e  lea     rdx, [rbp+57h+Buffer]; Buffer
0x180005f82  lea     rcx, stru_18002AC90; Table
0x180005f89  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180005f90  nop     dword ptr [rax+rax+00h]
0x180005f95  lea     rcx, qword_18002ACF8
0x180005f9c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180005fa3  nop     dword ptr [rax+rax+00h]
0x180005fa8  mov     rcx, r14
  ... truncated ...
```
