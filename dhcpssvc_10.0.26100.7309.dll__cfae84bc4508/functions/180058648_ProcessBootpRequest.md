# ProcessBootpRequest

- ea: `0x180058648`
- end: `0x180058f31`
- name: `ProcessBootpRequest`
- size: `2281`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `28`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18005ced8`

## callees

- `0x180001834`
- `0x180002854`
- `0x18000323c`
- `0x180003c9c`
- `0x180005a44`
- `0x180006250`
- `0x180006754`
- `0x18000c180`
- `0x180025b98`
- `0x180031ba4`
- `0x18003255c`
- `0x180052f80`
- `0x1800543a4`
- `0x1800547f0`
- `0x18005514c`
- `0x18005585c`
- `0x18005590c`
- `0x180058648`
- `0x18008e3c0`
- `0x18008ee18`
- `0x18008f3f0`
- `0x18008f418`
- `0x1800983b4`
- `0x1800c7fa8`
- `0x1800cc982`
- `0x1800cc99a`
- `0x1800cc9e0`
- `0x1800cd010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18005882d`
- `msvcrt!_wcsicmp` at `0x18005882d`
- `WS2_32!__imp_htonl` at `0x180058c6a`
- `WS2_32!__imp_htonl` at `0x180058d51`
- `WS2_32!__imp_htonl` at `0x180058d8c`
- `WS2_32!__imp_htonl` at `0x180058c6a`
- `WS2_32!__imp_htonl` at `0x180058d51`
- `WS2_32!__imp_htonl` at `0x180058d8c`
- `WS2_32!__imp_ntohl` at `0x1800588d9`
- `WS2_32!__imp_ntohl` at `0x180058a4f`
- `WS2_32!__imp_ntohl` at `0x180058b72`
- `WS2_32!__imp_ntohl` at `0x1800588d9`
- `WS2_32!__imp_ntohl` at `0x180058a4f`
- `WS2_32!__imp_ntohl` at `0x180058b72`
- `KERNEL32!GetComputerNameW` at `0x1800586ef`
- `KERNEL32!GetComputerNameW` at `0x1800586ef`
- `KERNEL32!GetLastError` at `0x1800586ff`
- `KERNEL32!GetLastError` at `0x1800586ff`
- `KERNEL32!EnterCriticalSection` at `0x1800589db`
- `KERNEL32!EnterCriticalSection` at `0x1800589db`
- `KERNEL32!LeaveCriticalSection` at `0x180058ab9`
- `KERNEL32!LeaveCriticalSection` at `0x180058ab9`
- `KERNEL32!HeapFree` at `0x180058ad6`
- `KERNEL32!HeapFree` at `0x180058b4b`
- `KERNEL32!HeapFree` at `0x180058c34`
- `KERNEL32!HeapFree` at `0x180058ad6`
- `KERNEL32!HeapFree` at `0x180058b4b`
- `KERNEL32!HeapFree` at `0x180058c34`

## pseudocode

```c
__int64 __fastcall ProcessBootpRequest(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  DWORD LastError; // ebx
  __int64 result; // rax
  __int64 v9; // rax
  unsigned __int64 v10; // rax
  __int64 v11; // r13
  __int64 v12; // rax
  int v13; // edi
  char v14; // si
  __int64 v15; // rax
  u_long v16; // ecx
  __int64 v17; // rdx
  __int64 v18; // r8
  BOOL v19; // esi
  char v20; // di
  u_long v21; // ebx
  int v22; // eax
  void *v23; // rsi
  u_long v24; // ebx
  unsigned int ClientEntry; // edi
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rdi
  u_long v29; // eax
  __int64 v30; // rdi
  int String; // eax
  _BYTE *v32; // rsi
  int v33; // eax
  _BYTE *v34; // rcx
  __int64 v35; // rdx
  char v36; // al
  _BYTE *v37; // rax
  unsigned __int8 *appended; // rbx
  __int64 v39; // rax
  int v40; // ecx
  u_long v41; // r13d
  unsigned __int8 *v42; // r10
  char v43; // cl
  char v44; // al
  __int64 v45; // rbx
  _BYTE *v46; // r8
  unsigned __int8 *v47; // rax
  _OWORD *v48; // r8
  __int64 v49; // rax
  int v50; // [rsp+38h] [rbp-230h]
  BOOL v51; // [rsp+50h] [rbp-218h]
  __int128 hostlong; // [rsp+60h] [rbp-208h] BYREF
  int v53; // [rsp+70h] [rbp-1F8h] BYREF
  DWORD nSize; // [rsp+74h] [rbp-1F4h] BYREF
  int v55; // [rsp+78h] [rbp-1F0h] BYREF
  int v56; // [rsp+7Ch] [rbp-1ECh]
  int v57; // [rsp+80h] [rbp-1E8h] BYREF
  u_long v58; // [rsp+84h] [rbp-1E4h]
  int v59; // [rsp+88h] [rbp-1E0h] BYREF
  LPVOID v60; // [rsp+90h] [rbp-1D8h] BYREF
  void *Src; // [rsp+98h] [rbp-1D0h] BYREF
  LPVOID lpMem[2]; // [rsp+A0h] [rbp-1C8h] BYREF
  WCHAR *v63; // [rsp+B0h] [rbp-1B8h] BYREF
  __int64 v64; // [rsp+B8h] [rbp-1B0h]
  __int64 v65; // [rsp+C0h] [rbp-1A8h]
  __int64 v66; // [rsp+C8h] [rbp-1A0h]
  __int64 v67; // [rsp+D0h] [rbp-198h]
  __int64 v68; // [rsp+D8h] [rbp-190h]
  __int64 v69; // [rsp+E0h] [rbp-188h]
  wchar_t String2[28]; // [rsp+E8h] [rbp-180h] BYREF
  wchar_t String1[64]; // [rsp+120h] [rbp-148h] BYREF
  _BYTE v72[128]; // [rsp+1A0h] [rbp-C8h] BYREF

  v64 = a3;
  v66 = a2;
  v68 = a1;
  v69 = a2;
  v65 = a2;
  hostlong = 0u;
  v55 = 0;
  v53 = 0;
  Src = 0;
  v59 = 0;
  v57 = 0;
  v63 = 0;
  nSize = 25;
  if ( GetComputerNameW(String2, &nSize) )
  {
    v9 = 24;
    if ( nSize < 0x19 )
      v9 = nSize;
    v10 = v9;
    if ( v10 >= 25 )
      _report_rangecheckfailure();
    String2[v10] = 0;
    v60 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_079646765da4361deec0b4ab82b940ea_Traceguids);
    v11 = *(_QWORD *)a1;
    v67 = *(_QWORD *)a1;
    result = DhcpMessageCheckFilter(a1, a2);
    if ( !(_DWORD)result )
    {
      if ( a4 )
        *a4 = 0;
      if ( *(_QWORD *)(a2 + 48) )
        return 20015;
      if ( *(_QWORD *)(a2 + 16) )
        return 20015;
      *(_BYTE *)(v11 + 107) = 0;
      *(_BYTE *)(v11 + 235) = 0;
      if ( *(_BYTE *)(v11 + 44) && (!DhcpOemToUnicode((PCSZ)(v11 + 44)) || _wcsicmp(String1, String2)) )
      {
        return 20015;
      }
      else
      {
        result = DhcpDetermineInfoFromMessage((__int64 *)a1, a2, &Src, (_DWORD *)&hostlong + 3, (u_long *)&hostlong);
        if ( !(_DWORD)result )
        {
          if ( (unsigned int)DhcpLookupReservationByHardwareAddress((unsigned int)hostlong, Src, HIDWORD(hostlong), a1) )
            return 20016;
          v12 = *(_QWORD *)(a1 + 112);
          if ( v12 )
          {
            v13 = *(_DWORD *)(v12 + 8);
            v14 = *(_BYTE *)(v12 + 12);
          }
          else
          {
            v13 = 0;
            v14 = 0;
          }
          LODWORD(hostlong) = v13;
          v15 = *(_QWORD *)(a1 + 88);
          if ( v15 )
          {
            v58 = *(_DWORD *)(v15 + 12);
            v56 = *(_DWORD *)(v15 + 8);
          }
          else
          {
            v58 = 0;
            v56 = 0;
          }
          v16 = *(_DWORD *)(v11 + 12);
          if ( v16 )
          {
            if ( v13 != ntohl(v16) )
              return 20016;
          }
          if ( (v14 & 2) == 0 )
            return 20016;
          if ( (unsigned int)DhcpSubnetIsDisabled(*(_QWORD *)(a1 + 88), 1) )
            return 20016;
          lpMem[0] = 0;
          lpMem[1] = 0;
          ValidateSubRangeForAddress(
            a1 + 168,
            v13,
            *(_QWORD *)(a1 + 88),
            a1 + 152,
            (__int64)&hostlong + 4,
            (__int64)lpMem,
            a1 + 168,
            a1 + 184);
          MemArrayFree(lpMem, MemFreeSubnetSatisfiedPolicies);
          DhcpGetBootpInfo(a1, v17, (const char *)(v11 + 108), (struct addrinfoW *)v72, &v55);
          if ( v55 == -1 )
          {
            return 20016;
          }
          else
          {
            lpMem[0] = 0;
            LOBYTE(v18) = *(_BYTE *)(v11 + 1);
            DhcpMakeClientUID(Src, HIDWORD(hostlong), v18, v56, lpMem, (_DWORD *)&hostlong + 2);
            EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
            DhcpDnsDecideOptionsForClient(a1, a2, &v53, &v59, &v57, &v63);
            DhcpDetermineHostName(a1, a2, v63, (wchar_t **)&v60);
            v19 = v57 != 0;
            v20 = v53 | 1;
            v21 = ntohl(*(_DWORD *)(a1 + 28));
            v22 = DhcpCalculateTime(0xFFFFFFFFLL);
            v51 = v19;
            v50 = v21;
            v23 = v60;
            v24 = hostlong;
            ClientEntry = DhcpCreateClientEntry(
                            hostlong,
                            (int)lpMem[0],
                            SDWORD2(hostlong),
                            v22,
                            (__int64)v60,
                            0,
                            2,
                            v50,
                            v20);
            DWORD1(hostlong) = ClientEntry;
            LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
            HeapFree(gDhcpHeap, 0, lpMem[0]);
            if ( ClientEntry )
            {
              if ( qword_180155830 )
                qword_180155830(v64 + 88, v64 + 104, 10, *(unsigned int *)(v64 + 116), v64, *(_QWORD *)(v64 + 296));
              if ( v23 )
                HeapFree(gDhcpHeap, 0, v23);
              return ClientEntry;
            }
            else
            {
              if ( qword_180155848 )
              {
                v28 = v64;
                v29 = ntohl(*(_DWORD *)(v64 + 116));
                ((void (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, u_long, int, int, __int64, _QWORD, int, BOOL))qword_180155848)(
                  *(_QWORD *)(v28 + 88),
                  *(unsigned int *)(v28 + 104),
                  805306370,
                  v29,
                  v24,
                  805306371,
                  -1,
                  v28,
                  *(_QWORD *)(v28 + 296),
                  1,
                  v51);
              }
              v30 = v66;
              String = GetString(1143, v26, v27);
              DhcpUpdateAuditLog(20, String, v24, (_DWORD)Src, HIDWORD(hostlong), (__int64)v23);
              if ( v23 )
                HeapFree(gDhcpHeap, 0, v23);
              *(_WORD *)(v11 + 10) |= 0x8000u;
              v32 = *(_BYTE **)(a1 + 8);
              memset_0(v32, 0, 0x12Cu);
              *v32 = 2;
              *((_DWORD *)v32 + 1) = *(_DWORD *)(v11 + 4);
              *((_DWORD *)v32 + 4) = htonl(v24);
              v33 = v55;
              if ( !v55 )
                v33 = *(_DWORD *)(a1 + 28);
              *((_DWORD *)v32 + 5) = v33;
              *((_WORD *)v32 + 5) = *(_WORD *)(v11 + 10);
              v32[1] = *(_BYTE *)(v11 + 1);
              v32[2] = *(_BYTE *)(v11 + 2);
              memcpy_0(v32 + 28, (const void *)(v11 + 28), *(unsigned __int8 *)(v11 + 2));
              *((_DWORD *)v32 + 6) = *(_DWORD *)(v11 + 24);
              v34 = v32 + 108;
              v35 = 128;
              do
              {
                if ( v35 == -2147483518 )
                  break;
                v36 = v34[v72 - (v32 + 108)];
                if ( !v36 )
                  break;
                *v34++ = v36;
                --v35;
              }
              while ( v35 );
              v37 = v34 - 1;
              if ( v35 )
                v37 = v34;
              *v37 = 0;
              memset_0(v32 + 44, 0, 0x40u);
              appended = v32 + 236;
              if ( v32 + 240 < v32 + 299 )
              {
                *(_DWORD *)appended = 1666417251;
                appended = v32 + 240;
              }
              v39 = *(_QWORD *)(a1 + 88);
              v40 = 0;
              if ( v39 )
                LOBYTE(v40) = (unsigned int)(*(_DWORD *)(v39 + 36) - 2) <= 1;
              DWORD2(hostlong) = v40;
              v41 = hostlong;
              if ( v40 )
              {
                DWORD1(hostlong) = htonl(hostlong);
                appended = DhcpAppendOption(appended, 3u, (__int128 *)((char *)&hostlong + 4), 4u, (__int64)(v32 + 300));
              }
              DWORD1(hostlong) = htonl(v58);
              v42 = DhcpAppendOption(appended, 1u, (__int128 *)((char *)&hostlong + 4), 4u, (__int64)(v32 + 300));
              if ( (v53 || v59) && (LOBYTE(hostlong) = 0, !DhcpGlobalUseNoDns) && *(_QWORD *)(v30 + 136) )
              {
                BYTE1(hostlong) = -1;
                if ( (v53 & 0x20) != 0 )
                {
                  v43 = 1;
                  if ( (*(_BYTE *)(v65 + 124) & 1) == 0 )
                    v43 = 3;
                }
                else
                {
                  v43 = *(_BYTE *)(v65 + 124) & 8;
                }
                LOBYTE(hostlong) = *(_BYTE *)(v65 + 124) & 4 | v43;
                v44 = -1;
                if ( (v53 & 0x20) != 0 )
                  v44 = 0;
                BYTE2(hostlong) = v44;
                v45 = (__int64)(v32 + 300);
                v42 = DhcpAppendOption(v42, 0x51u, &hostlong, 3u, (__int64)(v32 + 300));
              }
              else
              {
                v45 = (__int64)(v32 + 300);
              }
              v46 = *(_BYTE **)(v30 + 56);
              if ( !v46 )
              {
                v46 = &pbOptionList;
                *(_QWORD *)(v30 + 56) = &pbOptionList;
                *(_DWORD *)(v30 + 64) = 20;
              }
              v47 = (unsigned __int8 *)AppendClientRequestedParameters(
                                         v41,
                                         a1,
                                         v46,
                                         *(_DWORD *)(v30 + 64),
                                         (__int64)v42,
                                         v45,
                                         SDWORD2(hostlong),
                                         1,
                                         0);
              v48 = *(_OWORD **)(v30 + 240);
              if ( v48 )
                v47 = DhcpAppendOption(v47, 0x52u, v48, *(_DWORD *)(v30 + 236), v45);
              *v47 = -1;
              *(_DWORD *)(a1 + 24) = (_DWORD)v47 + 1 - (_DWORD)v32;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
              {
                v49 = DhcpIpAddressToDottedString(v41);
                WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_079646765da4361deec0b4ab82b940ea_Traceguids, v49);
              }
              return 0;
            }
          }
        }
      }
    }
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_079646765da4361deec0b4ab82b940ea_Traceguids, LastError);
    return LastError;
  }
  return result;
}

```

## disassembly

```asm
0x180058648  mov     r11, rsp
0x18005864b  push    rbx
0x18005864c  push    rsi
0x18005864d  push    rdi
0x18005864e  push    r13
0x180058650  push    r14
0x180058652  push    r15
0x180058654  sub     rsp, 238h
0x18005865b  mov     rax, cs:__security_cookie
0x180058662  xor     rax, rsp
0x180058665  mov     [rsp+268h+var_48], rax
0x18005866d  mov     rdi, r9
0x180058670  mov     [rsp+268h+var_1B0], r8
0x180058678  mov     rbx, rdx
0x18005867b  mov     [rsp+268h+var_1A0], rdx
0x180058683  mov     r15, rcx
0x180058686  mov     [rsp+268h+var_190], rcx
0x18005868e  mov     [rsp+268h+var_188], rdx
0x180058696  mov     [rsp+268h+var_1A8], rdx
0x18005869e  xor     r14d, r14d
0x1800586a1  mov     [rsp+268h+hostlong], r14d
0x1800586a6  mov     dword ptr [rsp+268h+var_1F0], r14d
0x1800586ab  mov     [rsp+268h+var_1F8], r14d
0x1800586b0  mov     dword ptr [rsp+268h+Size], r14d
0x1800586b5  mov     [r11-1D0h], r14
0x1800586bc  mov     dword ptr [rsp+268h+Size+4], r14d
0x1800586c1  mov     [r11-1E0h], r14d
0x1800586c8  mov     [rsp+268h+var_204], r14d
0x1800586cd  mov     [r11-1E8h], r14d
0x1800586d4  mov     [r11-1B8h], r14
0x1800586db  lea     esi, [r14+19h]
0x1800586df  mov     [rsp+268h+nSize], esi
0x1800586e3  lea     rdx, [rsp+268h+nSize]; nSize
0x1800586e8  lea     rcx, [r11-180h]; lpBuffer
0x1800586ef  call    cs:__imp_GetComputerNameW
0x1800586f6  nop     dword ptr [rax+rax+00h]
0x1800586fb  test    eax, eax
0x1800586fd  jnz     short loc_18005875F
0x1800586ff  call    cs:__imp_GetLastError
0x180058706  nop     dword ptr [rax+rax+00h]
0x18005870b  mov     ebx, eax
0x18005870d  lea     rax, WPP_GLOBAL_Control
0x180058714  mov     rcx, cs:WPP_GLOBAL_Control
0x18005871b  cmp     rcx, rax
0x18005871e  jz      short loc_18005873B
0x180058720  test    byte ptr [rcx+1Ch], 10h
0x180058724  jz      short loc_18005873B
0x180058726  mov     edx, esi
0x180058728  mov     r9d, ebx
0x18005872b  lea     r8, WPP_079646765da4361deec0b4ab82b940ea_Traceguids
0x180058732  mov     rcx, [rcx+10h]
0x180058736  call    WPP_SF_D
0x18005873b  mov     eax, ebx
0x18005873d  mov     rcx, [rsp+268h+var_48]
0x180058745  xor     rcx, rsp; StackCookie
0x180058748  call    __security_check_cookie
0x18005874d  add     rsp, 238h
0x180058754  pop     r15
0x180058756  pop     r14
0x180058758  pop     r13
0x18005875a  pop     rdi
0x18005875b  pop     rsi
0x18005875c  pop     rbx
0x18005875d  retn
0x18005875f  mov     eax, 18h
0x180058764  cmp     [rsp+268h+nSize], esi
0x180058768  cmovb   eax, [rsp+268h+nSize]
0x18005876d  add     rax, rax
0x180058770  cmp     rax, 32h ; '2'
0x180058774  jnb     loc_180058F2B
0x18005877a  mov     [rsp+rax+268h+String2], r14w
0x180058783  mov     [rsp+268h+var_1D8], r14
0x18005878b  lea     rax, WPP_GLOBAL_Control
0x180058792  mov     rcx, cs:WPP_GLOBAL_Control
0x180058799  cmp     rcx, rax
0x18005879c  jz      short loc_1800587B9
0x18005879e  test    byte ptr [rcx+1Ch], 20h
0x1800587a2  jz      short loc_1800587B9
0x1800587a4  mov     edx, 1Ah
0x1800587a9  lea     r8, WPP_079646765da4361deec0b4ab82b940ea_Traceguids
0x1800587b0  mov     rcx, [rcx+10h]
0x1800587b4  call    WPP_SF_
0x1800587b9  mov     r13, [r15]
0x1800587bc  mov     [rsp+268h+var_198], r13
0x1800587c4  mov     rdx, rbx
0x1800587c7  mov     rcx, r15
0x1800587ca  call    DhcpMessageCheckFilter
0x1800587cf  test    eax, eax
0x1800587d1  jnz     loc_18005873D
0x1800587d7  test    rdi, rdi
0x1800587da  jz      short loc_1800587DF
0x1800587dc  mov     [rdi], r14d
0x1800587df  cmp     [rbx+30h], r14
0x1800587e3  jnz     loc_180058F21
0x1800587e9  cmp     [rbx+10h], r14
0x1800587ed  jnz     loc_180058F21
0x1800587f3  mov     [r13+6Bh], r14b
0x1800587f7  mov     [r13+0EBh], r14b
0x1800587fe  lea     rcx, [r13+2Ch]; SourceString
0x180058802  cmp     [rcx], r14b
0x180058805  jz      short loc_180058841
0x180058807  lea     rdx, [rsp+268h+String1]
0x18005880f  call    DhcpOemToUnicode
0x180058814  test    rax, rax
0x180058817  jz      loc_180058F21
0x18005881d  lea     rdx, [rsp+268h+String2]; String2
0x180058825  lea     rcx, [rsp+268h+String1]; String1
0x18005882d  call    cs:__imp__wcsicmp
0x180058834  nop     dword ptr [rax+rax+00h]
0x180058839  test    eax, eax
0x18005883b  jnz     loc_180058F21
0x180058841  lea     rax, [rsp+268h+hostlong]
0x180058846  mov     [rsp+268h+var_248], rax
0x18005884b  lea     r9, [rsp+268h+Size+4]
0x180058850  lea     r8, [rsp+268h+Src]
0x180058858  mov     rdx, rbx
0x18005885b  mov     rcx, r15
0x18005885e  call    DhcpDetermineInfoFromMessage
0x180058863  test    eax, eax
0x180058865  jnz     loc_18005873D
0x18005886b  mov     r9, r15
0x18005886e  mov     r8d, dword ptr [rsp+268h+Size+4]
0x180058873  mov     rdx, [rsp+268h+Src]
0x18005887b  mov     ecx, [rsp+268h+hostlong]
0x18005887f  call    DhcpLookupReservationByHardwareAddress
0x180058884  test    eax, eax
0x180058886  jnz     loc_180058F17
0x18005888c  mov     rax, [r15+70h]
0x180058890  test    rax, rax
0x180058893  jnz     short loc_18005889D
0x180058895  mov     edi, r14d
0x180058898  mov     sil, r14b
0x18005889b  jmp     short loc_1800588A4
0x18005889d  mov     edi, [rax+8]
0x1800588a0  mov     sil, [rax+0Ch]
0x1800588a4  mov     [rsp+268h+hostlong], edi
0x1800588a8  mov     rax, [r15+58h]
0x1800588ac  test    rax, rax
0x1800588af  jnz     short loc_1800588C0
0x1800588b1  mov     [rsp+268h+var_1E4], r14d
0x1800588b9  mov     dword ptr [rsp+268h+var_1F0+4], r14d
0x1800588be  jmp     short loc_1800588D1
0x1800588c0  mov     ecx, [rax+0Ch]
0x1800588c3  mov     [rsp+268h+var_1E4], ecx
0x1800588ca  mov     eax, [rax+8]
0x1800588cd  mov     dword ptr [rsp+268h+var_1F0+4], eax
0x1800588d1  mov     ecx, [r13+0Ch]; netlong
0x1800588d5  test    ecx, ecx
0x1800588d7  jz      short loc_1800588ED
0x1800588d9  call    cs:__imp_ntohl
0x1800588e0  nop     dword ptr [rax+rax+00h]
0x1800588e5  cmp     edi, eax
0x1800588e7  jnz     loc_180058F17
0x1800588ed  test    sil, 2
0x1800588f1  jz      loc_180058F17
0x1800588f7  mov     edx, 1
0x1800588fc  mov     rcx, [r15+58h]
0x180058900  call    DhcpSubnetIsDisabled
0x180058905  test    eax, eax
0x180058907  jnz     loc_180058F17
0x18005890d  mov     [rsp+268h+lpMem], r14
0x180058915  mov     [rsp+268h+var_1C0], r14
0x18005891d  lea     rax, [r15+0B8h]
0x180058924  lea     rcx, [r15+0A8h]
0x18005892b  lea     r9, [r15+98h]
0x180058932  mov     qword ptr [rsp+268h+var_230], rax
0x180058937  mov     qword ptr [rsp+268h+var_238], rcx
0x18005893c  lea     rax, [rsp+268h+lpMem]
0x180058944  mov     [rsp+268h+var_240], rax
0x180058949  lea     rax, [rsp+268h+var_204]
0x18005894e  mov     [rsp+268h+var_248], rax
0x180058953  mov     r8, [r15+58h]
0x180058957  mov     edx, edi
0x180058959  call    ValidateSubRangeForAddress
0x18005895e  lea     rdx, MemFreeSubnetSatisfiedPolicies
0x180058965  lea     rcx, [rsp+268h+lpMem]
0x18005896d  call    MemArrayFree
0x180058972  lea     r8, [r13+6Ch]
0x180058976  lea     rax, [rsp+268h+var_1F0]
0x18005897b  mov     [rsp+268h+var_248], rax; __int64
0x180058980  lea     r9, [rsp+268h+var_C8]
0x180058988  mov     rcx, r15; int
0x18005898b  call    DhcpGetBootpInfo
0x180058990  cmp     dword ptr [rsp+268h+var_1F0], 0FFFFFFFFh
0x180058995  jz      loc_180058F17
0x18005899b  mov     [rsp+268h+lpMem], r14
0x1800589a3  lea     rax, [rsp+268h+Size]
0x1800589a8  mov     [rsp+268h+var_240], rax; __int64
0x1800589ad  lea     rax, [rsp+268h+lpMem]
0x1800589b5  mov     [rsp+268h+var_248], rax; __int64
0x1800589ba  mov     r9d, dword ptr [rsp+268h+var_1F0+4]
0x1800589bf  mov     r8b, [r13+1]
0x1800589c3  mov     edx, dword ptr [rsp+268h+Size+4]; Size
0x1800589c7  mov     rcx, [rsp+268h+Src]; Src
0x1800589cf  call    DhcpMakeClientUID
0x1800589d4  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x1800589db  call    cs:__imp_EnterCriticalSection
0x1800589e2  nop     dword ptr [rax+rax+00h]
0x1800589e7  lea     rax, [rsp+268h+var_1B8]
0x1800589ef  mov     [rsp+268h+var_240], rax
0x1800589f4  lea     rax, [rsp+268h+var_1E8]
0x1800589fc  mov     [rsp+268h+var_248], rax
0x180058a01  lea     r9, [rsp+268h+var_1E0]
0x180058a09  lea     r8, [rsp+268h+var_1F8]
0x180058a0e  mov     rdx, rbx
0x180058a11  mov     rcx, r15
0x180058a14  call    DhcpDnsDecideOptionsForClient
0x180058a19  lea     r9, [rsp+268h+var_1D8]
0x180058a21  mov     r8, [rsp+268h+var_1B8]
0x180058a29  mov     rdx, rbx
0x180058a2c  mov     rcx, r15
0x180058a2f  call    DhcpDetermineHostName
0x180058a34  mov     esi, r14d
0x180058a37  cmp     [rsp+268h+var_1E8], r14d
0x180058a3f  setnz   sil
0x180058a43  mov     edi, [rsp+268h+var_1F8]
0x180058a47  or      dil, 1
0x180058a4b  mov     ecx, [r15+1Ch]; netlong
0x180058a4f  call    cs:__imp_ntohl
0x180058a56  nop     dword ptr [rax+rax+00h]
0x180058a5b  mov     ebx, eax
0x180058a5d  or      ecx, 0FFFFFFFFh
0x180058a60  call    DhcpCalculateTime
0x180058a65  mov     r9, rax
0x180058a68  mov     [rsp+268h+var_218], esi
0x180058a6c  mov     [rsp+268h+var_220], 1
0x180058a74  mov     byte ptr [rsp+268h+var_228], dil
0x180058a79  mov     [rsp+268h+var_230], ebx
0x180058a7d  mov     byte ptr [rsp+268h+var_238], 2
0x180058a82  mov     [rsp+268h+var_240], r14
0x180058a87  mov     rsi, [rsp+268h+var_1D8]
0x180058a8f  mov     [rsp+268h+var_248], rsi
0x180058a94  mov     r8d, dword ptr [rsp+268h+Size]
0x180058a99  mov     rdx, [rsp+268h+lpMem]
0x180058aa1  mov     ebx, [rsp+268h+hostlong]
0x180058aa5  mov     ecx, ebx
0x180058aa7  call    DhcpCreateClientEntry
0x180058aac  mov     edi, eax
0x180058aae  mov     [rsp+268h+var_204], eax
0x180058ab2  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180058ab9  call    cs:__imp_LeaveCriticalSection
0x180058ac0  nop     dword ptr [rax+rax+00h]
0x180058ac5  mov     r8, [rsp+268h+lpMem]; lpMem
0x180058acd  xor     edx, edx; dwFlags
0x180058acf  mov     rcx, cs:gDhcpHeap; hHeap
0x180058ad6  call    cs:__imp_HeapFree
0x180058add  nop     dword ptr [rax+rax+00h]
0x180058ae2  test    edi, edi
0x180058ae4  jz      short loc_180058B5E
0x180058ae6  mov     r10, cs:qword_180155830
0x180058aed  test    r10, r10
0x180058af0  jz      short loc_180058B25
0x180058af2  mov     rax, [rsp+268h+var_1B0]
0x180058afa  lea     rdx, [rax+68h]
0x180058afe  lea     rcx, [rax+58h]
0x180058b02  mov     r8, [rax+128h]
0x180058b09  mov     [rsp+268h+var_240], r8
0x180058b0e  mov     [rsp+268h+var_248], rax
0x180058b13  mov     r9d, [rax+74h]
0x180058b17  mov     r8d, 0Ah
0x180058b1d  mov     rax, r10
0x180058b20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058b25  jmp     short loc_180058B3A
0x180058b27  mov     ecx, eax
0x180058b29  call    DhcpCalloutLogAV
0x180058b2e  mov     edi, [rsp+268h+var_204]
0x180058b32  mov     rsi, [rsp+268h+var_1D8]
0x180058b3a  test    rsi, rsi
0x180058b3d  jz      short loc_180058B57
0x180058b3f  mov     r8, rsi; lpMem
0x180058b42  xor     edx, edx; dwFlags
0x180058b44  mov     rcx, cs:gDhcpHeap; hHeap
0x180058b4b  call    cs:__imp_HeapFree
0x180058b52  nop     dword ptr [rax+rax+00h]
0x180058b57  mov     eax, edi
0x180058b59  jmp     loc_18005873D
0x180058b5e  cmp     cs:qword_180155848, r14
0x180058b65  jz      short loc_180058BBC
0x180058b67  mov     rdi, [rsp+268h+var_1B0]
0x180058b6f  mov     ecx, [rdi+74h]; netlong
0x180058b72  call    cs:__imp_ntohl
0x180058b79  nop     dword ptr [rax+rax+00h]
0x180058b7e  mov     r9d, eax
0x180058b81  mov     rcx, [rdi+128h]
0x180058b88  mov     qword ptr [rsp+268h+var_228], rcx
0x180058b8d  mov     qword ptr [rsp+268h+var_230], rdi
0x180058b92  or      [rsp+268h+var_238], 0FFFFFFFFh
0x180058b97  mov     dword ptr [rsp+268h+var_240], 30000003h
0x180058b9f  mov     dword ptr [rsp+268h+var_248], ebx
0x180058ba3  mov     r8d, 30000002h
0x180058ba9  mov     edx, [rdi+68h]
0x180058bac  mov     rcx, [rdi+58h]
0x180058bb0  mov     rax, cs:qword_180155848
0x180058bb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058bbc  mov     rdi, [rsp+268h+var_1A0]
0x180058bc4  jmp     short loc_180058BF4
0x180058bc6  mov     ecx, eax
0x180058bc8  call    DhcpCalloutLogAV
0x180058bcd  xor     r14d, r14d
0x180058bd0  mov     r13, [rsp+268h+var_198]
  ... truncated ...
```
