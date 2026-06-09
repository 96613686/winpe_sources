# ProcessBootpRequest

- ea: `0x180058320`
- end: `0x180058bf9`
- name: `ProcessBootpRequest`
- size: `2265`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `28`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18005cbfc`

## callees

- `0x180001838`
- `0x18000282c`
- `0x180003228`
- `0x180003c90`
- `0x180005a34`
- `0x180006234`
- `0x18000677c`
- `0x18000c164`
- `0x1800250e8`
- `0x180031178`
- `0x180031b6c`
- `0x180052cac`
- `0x1800540c4`
- `0x180054510`
- `0x180054e5c`
- `0x180055590`
- `0x180055640`
- `0x180058320`
- `0x18008e500`
- `0x18008ef8c`
- `0x18008f58c`
- `0x18008f5b4`
- `0x180098658`
- `0x1800c8fd4`
- `0x1800cda62`
- `0x1800cda7a`
- `0x1800cdac0`
- `0x1800cf010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180058503`
- `msvcrt!_wcsicmp` at `0x180058503`
- `WS2_32!__imp_htonl` at `0x18005894b`
- `WS2_32!__imp_htonl` at `0x180058a37`
- `WS2_32!__imp_htonl` at `0x180058a6b`
- `WS2_32!__imp_htonl` at `0x18005894b`
- `WS2_32!__imp_htonl` at `0x180058a37`
- `WS2_32!__imp_htonl` at `0x180058a6b`
- `WS2_32!__imp_ntohl` at `0x1800585b1`
- `WS2_32!__imp_ntohl` at `0x180058722`
- `WS2_32!__imp_ntohl` at `0x180058854`
- `WS2_32!__imp_ntohl` at `0x1800585b1`
- `WS2_32!__imp_ntohl` at `0x180058722`
- `WS2_32!__imp_ntohl` at `0x180058854`
- `KERNEL32!GetComputerNameW` at `0x1800583c1`
- `KERNEL32!GetComputerNameW` at `0x1800583c1`
- `KERNEL32!GetLastError` at `0x1800583d1`
- `KERNEL32!GetLastError` at `0x1800583d1`
- `KERNEL32!EnterCriticalSection` at `0x1800586b4`
- `KERNEL32!EnterCriticalSection` at `0x1800586b4`
- `KERNEL32!LeaveCriticalSection` at `0x18005878d`
- `KERNEL32!LeaveCriticalSection` at `0x18005878d`
- `KERNEL32!HeapFree` at `0x1800587aa`
- `KERNEL32!HeapFree` at `0x18005881f`
- `KERNEL32!HeapFree` at `0x180058914`
- `KERNEL32!HeapFree` at `0x1800587aa`
- `KERNEL32!HeapFree` at `0x18005881f`
- `KERNEL32!HeapFree` at `0x180058914`

## pseudocode

```c
__int64 __fastcall ProcessBootpRequest(__int64 *a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  DWORD LastError; // ebx
  __int64 result; // rax
  __int64 v9; // rax
  unsigned __int64 v10; // rax
  __int64 v11; // r13
  unsigned int v12; // esi
  __int64 v13; // rax
  u_long v14; // ebx
  char v15; // di
  __int64 v16; // rax
  u_long v17; // ecx
  BOOL v18; // esi
  char v19; // di
  u_long v20; // ebx
  int v21; // eax
  void *v22; // rbx
  unsigned int ClientEntry; // edi
  __int64 v24; // rbx
  unsigned int v25; // edi
  __int64 v26; // rsi
  u_long v27; // eax
  int String; // eax
  void *v29; // rbx
  u_long v30; // esi
  __int64 v31; // rdi
  int v32; // eax
  _BYTE *v33; // rcx
  __int64 v34; // rdx
  char v35; // al
  _BYTE *v36; // rax
  _DWORD *appended; // rbx
  __int64 v38; // rax
  BOOL v39; // eax
  __int64 v40; // rdx
  __int64 v41; // rdx
  __int64 v42; // r10
  __int64 v43; // rdx
  char v44; // cl
  char v45; // al
  _BYTE *v46; // rax
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // rbx
  __int64 v50; // rax
  u_long v51; // [rsp+38h] [rbp-230h]
  u_long hostlong; // [rsp+60h] [rbp-208h] BYREF
  __int64 v53; // [rsp+64h] [rbp-204h] BYREF
  int v54; // [rsp+6Ch] [rbp-1FCh] BYREF
  DWORD nSize; // [rsp+70h] [rbp-1F8h] BYREF
  unsigned int Size; // [rsp+74h] [rbp-1F4h] BYREF
  int Size_4; // [rsp+78h] [rbp-1F0h]
  int v58; // [rsp+7Ch] [rbp-1ECh] BYREF
  int v59; // [rsp+80h] [rbp-1E8h] BYREF
  u_long v60; // [rsp+84h] [rbp-1E4h]
  int v61; // [rsp+88h] [rbp-1E0h] BYREF
  LPVOID v62; // [rsp+90h] [rbp-1D8h] BYREF
  void *Src; // [rsp+98h] [rbp-1D0h] BYREF
  LPVOID lpMem[2]; // [rsp+A0h] [rbp-1C8h] BYREF
  __int64 v65; // [rsp+B0h] [rbp-1B8h]
  __int64 v66; // [rsp+B8h] [rbp-1B0h] BYREF
  __int64 v67; // [rsp+C0h] [rbp-1A8h]
  __int64 v68; // [rsp+C8h] [rbp-1A0h]
  __int64 *v69; // [rsp+D0h] [rbp-198h]
  __int64 v70; // [rsp+D8h] [rbp-190h]
  wchar_t String2[32]; // [rsp+E0h] [rbp-188h] BYREF
  wchar_t String1[64]; // [rsp+120h] [rbp-148h] BYREF
  _BYTE v73[128]; // [rsp+1A0h] [rbp-C8h] BYREF

  v65 = a3;
  v69 = a1;
  v70 = a2;
  v67 = a2;
  hostlong = 0;
  v53 = 0;
  v54 = 0;
  v59 = 0;
  Src = 0;
  Size = 0;
  v61 = 0;
  v58 = 0;
  v66 = 0;
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
    v62 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_8d34d085f3b73e207e43a51a56ca0bcb_Traceguids);
    v11 = *a1;
    v68 = *a1;
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
        result = DhcpDetermineInfoFromMessage(
                   (_DWORD)a1,
                   a2,
                   (unsigned int)&Src,
                   (unsigned int)&Size,
                   (__int64)&hostlong);
        if ( !(_DWORD)result )
        {
          v12 = Size;
          if ( (unsigned int)DhcpLookupReservationByHardwareAddress(hostlong, Src, Size, a1) )
            return 20016;
          v13 = a1[14];
          if ( v13 )
          {
            v14 = *(_DWORD *)(v13 + 8);
            v15 = *(_BYTE *)(v13 + 12);
          }
          else
          {
            v14 = 0;
            v15 = 0;
          }
          hostlong = v14;
          v16 = a1[11];
          if ( v16 )
          {
            v60 = *(_DWORD *)(v16 + 12);
            Size_4 = *(_DWORD *)(v16 + 8);
          }
          else
          {
            v60 = 0;
            Size_4 = 0;
          }
          v17 = *(_DWORD *)(v11 + 12);
          if ( v17 )
          {
            if ( v14 != ntohl(v17) )
              return 20016;
          }
          if ( (v15 & 2) == 0 )
            return 20016;
          if ( (unsigned int)DhcpSubnetIsDisabled(a1[11], 1) )
            return 20016;
          lpMem[0] = 0;
          lpMem[1] = 0;
          ValidateSubRangeForAddress(
            (_DWORD)a1 + 168,
            v14,
            a1[11],
            (_DWORD)a1 + 152,
            (__int64)&v53 + 4,
            (__int64)lpMem,
            (__int64)(a1 + 21),
            (__int64)(a1 + 23));
          MemArrayFree(lpMem, MemFreeSubnetSatisfiedPolicies);
          DhcpGetBootpInfo((int)a1, (__int64)&v53);
          if ( (_DWORD)v53 == -1 )
          {
            return 20016;
          }
          else
          {
            lpMem[0] = 0;
            DhcpMakeClientUID(Src, v12, (__int64)lpMem, (__int64)&v59);
            EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
            DhcpDnsDecideOptionsForClient(
              (_DWORD)a1,
              a2,
              (unsigned int)&v54,
              (unsigned int)&v61,
              (__int64)&v58,
              (__int64)&v66);
            DhcpDetermineHostName(a1, a2, v66, &v62);
            v18 = v58 != 0;
            v19 = v54 | 1;
            v20 = ntohl(*((_DWORD *)a1 + 7));
            v21 = DhcpCalculateTime(0xFFFFFFFFLL);
            v51 = v20;
            v22 = v62;
            ClientEntry = DhcpCreateClientEntry(hostlong, lpMem[0], v59, v21, (__int64)v62, 0, 2, v51, v19, 1, v18);
            HIDWORD(v53) = ClientEntry;
            LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
            HeapFree(gDhcpHeap, 0, lpMem[0]);
            if ( ClientEntry )
            {
              if ( qword_1801577D0 )
                qword_1801577D0(v65 + 88, v65 + 104, 10, *(unsigned int *)(v65 + 116), v65, *(_QWORD *)(v65 + 296));
              if ( v22 )
                HeapFree(gDhcpHeap, 0, v22);
              return ClientEntry;
            }
            else
            {
              if ( qword_1801577E8 )
              {
                v24 = *(_QWORD *)(v65 + 296);
                v25 = *(_DWORD *)(v65 + 104);
                v26 = *(_QWORD *)(v65 + 88);
                v27 = ntohl(*(_DWORD *)(v65 + 116));
                ((void (__fastcall *)(__int64, _QWORD, __int64, _QWORD, u_long, int, int, __int64, __int64))qword_1801577E8)(
                  v26,
                  v25,
                  805306370,
                  v27,
                  hostlong,
                  805306371,
                  -1,
                  v65,
                  v24);
              }
              String = GetString(1143);
              v29 = v62;
              v30 = hostlong;
              DhcpUpdateAuditLog(20, String, hostlong, (_DWORD)Src, Size, (__int64)v62);
              if ( v29 )
                HeapFree(gDhcpHeap, 0, v29);
              *(_WORD *)(v11 + 10) |= 0x8000u;
              v31 = a1[1];
              memset_0((void *)(v31 + 1), 0, 0x12Bu);
              *(_BYTE *)v31 = 2;
              *(_DWORD *)(v31 + 4) = *(_DWORD *)(v11 + 4);
              *(_DWORD *)(v31 + 16) = htonl(v30);
              v32 = v53;
              if ( !(_DWORD)v53 )
                v32 = *((_DWORD *)a1 + 7);
              *(_DWORD *)(v31 + 20) = v32;
              *(_WORD *)(v31 + 10) = *(_WORD *)(v11 + 10);
              *(_BYTE *)(v31 + 1) = *(_BYTE *)(v11 + 1);
              *(_BYTE *)(v31 + 2) = *(_BYTE *)(v11 + 2);
              memcpy_0((void *)(v31 + 28), (const void *)(v11 + 28), *(unsigned __int8 *)(v11 + 2));
              *(_DWORD *)(v31 + 24) = *(_DWORD *)(v11 + 24);
              v33 = (_BYTE *)(v31 + 108);
              v34 = 128;
              do
              {
                if ( v34 == -2147483518 )
                  break;
                v35 = v73[(_QWORD)v33 - 108 - v31];
                if ( !v35 )
                  break;
                *v33++ = v35;
                --v34;
              }
              while ( v34 );
              v36 = v33 - 1;
              if ( v34 )
                v36 = v33;
              *v36 = 0;
              memset_0((void *)(v31 + 44), 0, 0x40u);
              appended = (_DWORD *)(v31 + 236);
              if ( v31 + 240 < (unsigned __int64)(v31 + 299) )
              {
                *appended = 1666417251;
                appended = (_DWORD *)(v31 + 240);
              }
              v38 = a1[11];
              v39 = v38 && (*(_DWORD *)(v38 + 36) == 3 || *(_DWORD *)(v38 + 36) == 2);
              LODWORD(v53) = v39;
              if ( v39 )
              {
                HIDWORD(v53) = htonl(v30);
                LOBYTE(v40) = 3;
                appended = (_DWORD *)DhcpAppendOption(appended, v40, (char *)&v53 + 4, 4, v31 + 300);
              }
              HIDWORD(v53) = htonl(v60);
              LOBYTE(v41) = 1;
              v42 = DhcpAppendOption(appended, v41, (char *)&v53 + 4, 4, v31 + 300);
              if ( v54 || v61 )
              {
                v43 = v54 & 0x20;
                LOBYTE(hostlong) = 0;
                if ( !DhcpGlobalUseNoDns )
                {
                  if ( *(_QWORD *)(a2 + 136) )
                  {
                    BYTE1(hostlong) = -1;
                    if ( (v54 & 0x20) != 0 )
                    {
                      v44 = 1;
                      if ( (*(_BYTE *)(v67 + 124) & 1) == 0 )
                        v44 = 3;
                    }
                    else
                    {
                      v44 = *(_BYTE *)(v67 + 124) & 8;
                    }
                    LOBYTE(hostlong) = *(_BYTE *)(v67 + 124) & 4 | v44;
                    v45 = -1;
                    if ( (v54 & 0x20) != 0 )
                      v45 = 0;
                    BYTE2(hostlong) = v45;
                    LOBYTE(v43) = 81;
                    v42 = DhcpAppendOption(v42, v43, &hostlong, 3, v31 + 300);
                  }
                }
              }
              if ( !*(_QWORD *)(a2 + 56) )
              {
                *(_QWORD *)(a2 + 56) = &pbOptionList;
                *(_DWORD *)(a2 + 64) = 20;
              }
              v46 = (_BYTE *)AppendClientRequestedParameters(v30, (int)a1, v42, v31 + 300, v53, 1, 0);
              v48 = *(_QWORD *)(a2 + 240);
              if ( v48 )
              {
                LOBYTE(v47) = 82;
                v46 = (_BYTE *)DhcpAppendOption(v46, v47, v48, *(unsigned int *)(a2 + 236), v31 + 300);
              }
              *v46 = -1;
              *((_DWORD *)a1 + 6) = (_DWORD)v46 + 1 - v31;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
              {
                v49 = *((_QWORD *)WPP_GLOBAL_Control + 2);
                v50 = DhcpIpAddressToDottedString(v30);
                WPP_SF_s(v49, 27, &WPP_8d34d085f3b73e207e43a51a56ca0bcb_Traceguids, v50);
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
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_8d34d085f3b73e207e43a51a56ca0bcb_Traceguids, LastError);
    return LastError;
  }
  return result;
}

```

## disassembly

```asm
0x180058320  mov     r11, rsp
0x180058323  push    rbx
0x180058324  push    rsi
0x180058325  push    rdi
0x180058326  push    r12
0x180058328  push    r13
0x18005832a  push    r14
0x18005832c  push    r15
0x18005832e  sub     rsp, 230h
0x180058335  mov     rax, cs:__security_cookie
0x18005833c  xor     rax, rsp
0x18005833f  mov     [rsp+268h+var_48], rax
0x180058347  mov     rbx, r9
0x18005834a  mov     [rsp+268h+var_1B8], r8
0x180058352  mov     r12, rdx
0x180058355  mov     r15, rcx
0x180058358  mov     [rsp+268h+var_198], rcx
0x180058360  mov     [rsp+268h+var_190], rdx
0x180058368  mov     [rsp+268h+var_1A8], rdx
0x180058370  xor     r14d, r14d
0x180058373  mov     [rsp+268h+hostlong], r14d
0x180058378  mov     dword ptr [rsp+268h+var_204], r14d
0x18005837d  mov     [rsp+268h+var_1FC], r14d
0x180058382  mov     [r11-1E8h], r14d
0x180058389  mov     [r11-1D0h], r14
0x180058390  mov     dword ptr [rsp+268h+Size], r14d
0x180058395  mov     [r11-1E0h], r14d
0x18005839c  mov     dword ptr [rsp+268h+var_204+4], r14d
0x1800583a1  mov     [rsp+268h+var_1EC], r14d
0x1800583a6  mov     [r11-1B0h], r14
0x1800583ad  lea     edi, [r14+19h]
0x1800583b1  mov     [rsp+268h+nSize], edi
0x1800583b5  lea     rdx, [rsp+268h+nSize]; nSize
0x1800583ba  lea     rcx, [r11-188h]; lpBuffer
0x1800583c1  call    cs:__imp_GetComputerNameW
0x1800583c8  nop     dword ptr [rax+rax+00h]
0x1800583cd  test    eax, eax
0x1800583cf  jnz     short loc_180058433
0x1800583d1  call    cs:__imp_GetLastError
0x1800583d8  nop     dword ptr [rax+rax+00h]
0x1800583dd  mov     ebx, eax
0x1800583df  lea     rax, WPP_GLOBAL_Control
0x1800583e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800583ed  cmp     rcx, rax
0x1800583f0  jz      short loc_18005840D
0x1800583f2  test    byte ptr [rcx+1Ch], 10h
0x1800583f6  jz      short loc_18005840D
0x1800583f8  mov     edx, edi
0x1800583fa  mov     r9d, ebx
0x1800583fd  lea     r8, WPP_8d34d085f3b73e207e43a51a56ca0bcb_Traceguids
0x180058404  mov     rcx, [rcx+10h]
0x180058408  call    WPP_SF_D
0x18005840d  mov     eax, ebx
0x18005840f  mov     rcx, [rsp+268h+var_48]
0x180058417  xor     rcx, rsp; StackCookie
0x18005841a  call    __security_check_cookie
0x18005841f  add     rsp, 230h
0x180058426  pop     r15
0x180058428  pop     r14
0x18005842a  pop     r13
0x18005842c  pop     r12
0x18005842e  pop     rdi
0x18005842f  pop     rsi
0x180058430  pop     rbx
0x180058431  retn
0x180058433  mov     eax, 18h
0x180058438  cmp     [rsp+268h+nSize], edi
0x18005843c  cmovb   eax, [rsp+268h+nSize]
0x180058441  add     rax, rax
0x180058444  cmp     rax, 32h ; '2'
0x180058448  jnb     loc_180058BF3
0x18005844e  mov     [rsp+rax+268h+String2], r14w
0x180058457  mov     [rsp+268h+var_1D8], r14
0x18005845f  lea     rax, WPP_GLOBAL_Control
0x180058466  mov     rcx, cs:WPP_GLOBAL_Control
0x18005846d  cmp     rcx, rax
0x180058470  jz      short loc_18005848D
0x180058472  test    byte ptr [rcx+1Ch], 20h
0x180058476  jz      short loc_18005848D
0x180058478  mov     edx, 1Ah
0x18005847d  lea     r8, WPP_8d34d085f3b73e207e43a51a56ca0bcb_Traceguids
0x180058484  mov     rcx, [rcx+10h]
0x180058488  call    WPP_SF_
0x18005848d  mov     r13, [r15]
0x180058490  mov     [rsp+268h+var_1A0], r13
0x180058498  mov     rdx, r12
0x18005849b  mov     rcx, r15
0x18005849e  call    DhcpMessageCheckFilter
0x1800584a3  test    eax, eax
0x1800584a5  jnz     loc_18005840F
0x1800584ab  test    rbx, rbx
0x1800584ae  jz      short loc_1800584B3
0x1800584b0  mov     [rbx], r14d
0x1800584b3  cmp     [r12+30h], r14
0x1800584b8  jnz     loc_180058BE9
0x1800584be  cmp     [r12+10h], r14
0x1800584c3  jnz     loc_180058BE9
0x1800584c9  mov     [r13+6Bh], r14b
0x1800584cd  mov     [r13+0EBh], r14b
0x1800584d4  lea     rcx, [r13+2Ch]; SourceString
0x1800584d8  cmp     [rcx], r14b
0x1800584db  jz      short loc_180058517
0x1800584dd  lea     rdx, [rsp+268h+String1]
0x1800584e5  call    DhcpOemToUnicode
0x1800584ea  test    rax, rax
0x1800584ed  jz      loc_180058BE9
0x1800584f3  lea     rdx, [rsp+268h+String2]; String2
0x1800584fb  lea     rcx, [rsp+268h+String1]; String1
0x180058503  call    cs:__imp__wcsicmp
0x18005850a  nop     dword ptr [rax+rax+00h]
0x18005850f  test    eax, eax
0x180058511  jnz     loc_180058BE9
0x180058517  lea     rax, [rsp+268h+hostlong]
0x18005851c  mov     [rsp+268h+var_248], rax
0x180058521  lea     r9, [rsp+268h+Size]
0x180058526  lea     r8, [rsp+268h+Src]
0x18005852e  mov     rdx, r12
0x180058531  mov     rcx, r15
0x180058534  call    DhcpDetermineInfoFromMessage
0x180058539  test    eax, eax
0x18005853b  jnz     loc_18005840F
0x180058541  mov     r9, r15
0x180058544  mov     esi, dword ptr [rsp+268h+Size]
0x180058548  mov     r8d, esi
0x18005854b  mov     rdx, [rsp+268h+Src]
0x180058553  mov     ecx, [rsp+268h+hostlong]
0x180058557  call    DhcpLookupReservationByHardwareAddress
0x18005855c  test    eax, eax
0x18005855e  jnz     loc_180058BDF
0x180058564  mov     rax, [r15+70h]
0x180058568  test    rax, rax
0x18005856b  jnz     short loc_180058575
0x18005856d  mov     ebx, r14d
0x180058570  mov     dil, r14b
0x180058573  jmp     short loc_18005857C
0x180058575  mov     ebx, [rax+8]
0x180058578  mov     dil, [rax+0Ch]
0x18005857c  mov     [rsp+268h+hostlong], ebx
0x180058580  mov     rax, [r15+58h]
0x180058584  test    rax, rax
0x180058587  jnz     short loc_180058598
0x180058589  mov     dword ptr [rsp+268h+var_1E8+4], r14d
0x180058591  mov     dword ptr [rsp+268h+Size+4], r14d
0x180058596  jmp     short loc_1800585A9
0x180058598  mov     ecx, [rax+0Ch]
0x18005859b  mov     dword ptr [rsp+268h+var_1E8+4], ecx
0x1800585a2  mov     eax, [rax+8]
0x1800585a5  mov     dword ptr [rsp+268h+Size+4], eax
0x1800585a9  mov     ecx, [r13+0Ch]; netlong
0x1800585ad  test    ecx, ecx
0x1800585af  jz      short loc_1800585C5
0x1800585b1  call    cs:__imp_ntohl
0x1800585b8  nop     dword ptr [rax+rax+00h]
0x1800585bd  cmp     ebx, eax
0x1800585bf  jnz     loc_180058BDF
0x1800585c5  test    dil, 2
0x1800585c9  jz      loc_180058BDF
0x1800585cf  mov     edx, 1
0x1800585d4  mov     rcx, [r15+58h]
0x1800585d8  call    DhcpSubnetIsDisabled
0x1800585dd  test    eax, eax
0x1800585df  jnz     loc_180058BDF
0x1800585e5  mov     [rsp+268h+lpMem], r14
0x1800585ed  mov     [rsp+268h+var_1C0], r14
0x1800585f5  lea     rax, [r15+0B8h]
0x1800585fc  lea     rcx, [r15+0A8h]
0x180058603  lea     r9, [r15+98h]
0x18005860a  mov     qword ptr [rsp+268h+var_230], rax
0x18005860f  mov     qword ptr [rsp+268h+var_238], rcx
0x180058614  lea     rax, [rsp+268h+lpMem]
0x18005861c  mov     [rsp+268h+var_240], rax
0x180058621  lea     rax, [rsp+268h+var_204+4]
0x180058626  mov     [rsp+268h+var_248], rax
0x18005862b  mov     r8, [r15+58h]
0x18005862f  mov     edx, ebx
0x180058631  call    ValidateSubRangeForAddress
0x180058636  lea     rdx, MemFreeSubnetSatisfiedPolicies
0x18005863d  lea     rcx, [rsp+268h+lpMem]
0x180058645  call    MemArrayFree
0x18005864a  lea     r8, [r13+6Ch]
0x18005864e  lea     rax, [rsp+268h+var_204]
0x180058653  mov     [rsp+268h+var_248], rax; __int64
0x180058658  lea     r9, [rsp+268h+var_C8]
0x180058660  mov     rcx, r15; int
0x180058663  call    DhcpGetBootpInfo
0x180058668  cmp     dword ptr [rsp+268h+var_204], 0FFFFFFFFh
0x18005866d  jz      loc_180058BDF
0x180058673  mov     [rsp+268h+lpMem], r14
0x18005867b  lea     rax, [rsp+268h+var_1E8]
0x180058683  mov     [rsp+268h+var_240], rax; __int64
0x180058688  lea     rax, [rsp+268h+lpMem]
0x180058690  mov     [rsp+268h+var_248], rax; __int64
0x180058695  mov     r9d, dword ptr [rsp+268h+Size+4]
0x18005869a  mov     r8b, [r13+1]
0x18005869e  mov     edx, esi; Size
0x1800586a0  mov     rcx, [rsp+268h+Src]; Src
0x1800586a8  call    DhcpMakeClientUID
0x1800586ad  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x1800586b4  call    cs:__imp_EnterCriticalSection
0x1800586bb  nop     dword ptr [rax+rax+00h]
0x1800586c0  lea     rax, [rsp+268h+var_1B0]
0x1800586c8  mov     [rsp+268h+var_240], rax
0x1800586cd  lea     rax, [rsp+268h+var_1EC]
0x1800586d2  mov     [rsp+268h+var_248], rax
0x1800586d7  lea     r9, [rsp+268h+var_1E0]
0x1800586df  lea     r8, [rsp+268h+var_1FC]
0x1800586e4  mov     rdx, r12
0x1800586e7  mov     rcx, r15
0x1800586ea  call    DhcpDnsDecideOptionsForClient
0x1800586ef  lea     r9, [rsp+268h+var_1D8]
0x1800586f7  mov     r8, [rsp+268h+var_1B0]
0x1800586ff  mov     rdx, r12
0x180058702  mov     rcx, r15
0x180058705  call    DhcpDetermineHostName
0x18005870a  mov     esi, r14d
0x18005870d  cmp     [rsp+268h+var_1EC], r14d
0x180058712  setnz   sil
0x180058716  mov     edi, [rsp+268h+var_1FC]
0x18005871a  or      dil, 1
0x18005871e  mov     ecx, [r15+1Ch]; netlong
0x180058722  call    cs:__imp_ntohl
0x180058729  nop     dword ptr [rax+rax+00h]
0x18005872e  mov     ebx, eax
0x180058730  or      ecx, 0FFFFFFFFh
0x180058733  call    DhcpCalculateTime
0x180058738  mov     r9, rax
0x18005873b  mov     [rsp+268h+var_218], esi
0x18005873f  mov     [rsp+268h+var_220], 1
0x180058747  mov     byte ptr [rsp+268h+var_228], dil
0x18005874c  mov     [rsp+268h+var_230], ebx
0x180058750  mov     byte ptr [rsp+268h+var_238], 2
0x180058755  mov     [rsp+268h+var_240], r14
0x18005875a  mov     rbx, [rsp+268h+var_1D8]
0x180058762  mov     [rsp+268h+var_248], rbx
0x180058767  mov     r8d, dword ptr [rsp+268h+var_1E8]
0x18005876f  mov     rdx, [rsp+268h+lpMem]
0x180058777  mov     ecx, [rsp+268h+hostlong]
0x18005877b  call    DhcpCreateClientEntry
0x180058780  mov     edi, eax
0x180058782  mov     dword ptr [rsp+268h+var_204+4], eax
0x180058786  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x18005878d  call    cs:__imp_LeaveCriticalSection
0x180058794  nop     dword ptr [rax+rax+00h]
0x180058799  mov     r8, [rsp+268h+lpMem]; lpMem
0x1800587a1  xor     edx, edx; dwFlags
0x1800587a3  mov     rcx, cs:gDhcpHeap; hHeap
0x1800587aa  call    cs:__imp_HeapFree
0x1800587b1  nop     dword ptr [rax+rax+00h]
0x1800587b6  test    edi, edi
0x1800587b8  jz      short loc_180058832
0x1800587ba  mov     r10, cs:qword_1801577D0
0x1800587c1  test    r10, r10
0x1800587c4  jz      short loc_1800587F9
0x1800587c6  mov     rax, [rsp+268h+var_1B8]
0x1800587ce  lea     rdx, [rax+68h]
0x1800587d2  lea     rcx, [rax+58h]
0x1800587d6  mov     r8, [rax+128h]
0x1800587dd  mov     [rsp+268h+var_240], r8
0x1800587e2  mov     [rsp+268h+var_248], rax
0x1800587e7  mov     r9d, [rax+74h]
0x1800587eb  mov     r8d, 0Ah
0x1800587f1  mov     rax, r10
0x1800587f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800587f9  jmp     short loc_18005880E
0x1800587fb  mov     ecx, eax
0x1800587fd  call    DhcpCalloutLogAV
0x180058802  mov     edi, dword ptr [rsp+268h+var_204+4]
0x180058806  mov     rbx, [rsp+268h+var_1D8]
0x18005880e  test    rbx, rbx
0x180058811  jz      short loc_18005882B
0x180058813  mov     r8, rbx; lpMem
0x180058816  xor     edx, edx; dwFlags
0x180058818  mov     rcx, cs:gDhcpHeap; hHeap
0x18005881f  call    cs:__imp_HeapFree
0x180058826  nop     dword ptr [rax+rax+00h]
0x18005882b  mov     eax, edi
0x18005882d  jmp     loc_18005840F
0x180058832  cmp     cs:qword_1801577E8, r14
0x180058839  jz      short loc_1800588A4
0x18005883b  mov     rax, [rsp+268h+var_1B8]
0x180058843  mov     rbx, [rax+128h]
0x18005884a  mov     edi, [rax+68h]
0x18005884d  mov     rsi, [rax+58h]
0x180058851  mov     ecx, [rax+74h]; netlong
0x180058854  call    cs:__imp_ntohl
0x18005885b  nop     dword ptr [rax+rax+00h]
0x180058860  mov     r9d, eax
0x180058863  mov     qword ptr [rsp+268h+var_228], rbx
0x180058868  mov     r8, [rsp+268h+var_1B8]
0x180058870  mov     qword ptr [rsp+268h+var_230], r8
0x180058875  mov     [rsp+268h+var_238], 0FFFFFFFFh
0x18005887d  mov     dword ptr [rsp+268h+var_240], 30000003h
0x180058885  mov     eax, [rsp+268h+hostlong]
0x180058889  mov     dword ptr [rsp+268h+var_248], eax
0x18005888d  mov     r8d, 30000002h
0x180058893  mov     edx, edi
0x180058895  mov     rcx, rsi
0x180058898  mov     rax, cs:qword_1801577E8
0x18005889f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800588a4  jmp     short loc_1800588C8
  ... truncated ...
```
