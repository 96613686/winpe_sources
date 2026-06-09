# Query_PrepareBlob

- ea: `0x180003240`
- end: `0x180003662`
- name: `Query_PrepareBlob`
- size: `1058`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x180002e20`
- `0x180038980`

## callees

- `0x180003240`
- `0x180003668`
- `0x180003750`
- `0x180003de4`
- `0x180046ec0`
- `0x1800863f0`
- `0x180086700`
- `0x180086b1c`
- `0x180086bd4`
- `0x1800871dc`

## import_xrefs

- `DNSAPI!DeRefQueryBlobEx` at `0x1800035e5`
- `DNSAPI!DeRefQueryBlobEx` at `0x1800035e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035ca`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003343`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003343`

## pseudocode

```c
__int64 __fastcall Query_PrepareBlob(
        __int64 a1,
        __int16 a2,
        unsigned int a3,
        int a4,
        int a5,
        int a6,
        unsigned int a7,
        __int64 a8,
        __int16 a9,
        _QWORD *a10,
        __int64 *a11)
{
  unsigned int v12; // ebp
  DWORD v13; // eax
  int v14; // r8d
  DWORD Config; // esi
  __int64 QueryBlob; // rdi
  HANDLE EventW; // rax
  signed __int32 v18; // eax
  __int64 v19; // rcx
  __int128 v23; // [rsp+80h] [rbp-78h] BYREF
  __int128 v24; // [rsp+90h] [rbp-68h]
  __int128 v25; // [rsp+A0h] [rbp-58h]
  __int64 v26; // [rsp+B0h] [rbp-48h]

  v12 = a3;
  v26 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_SDDlDDDqHqq(a5, a2, a3, a1, a2, a3, a4, a5, a6, a7, a8, a9, (__int64)a10, (__int64)a11);
  if ( a11 )
  {
    *a11 = 0;
    if ( a1 )
    {
      v13 = ValidateCustomServers(a7, a8);
      Config = v13;
      if ( v13 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
          return Config;
        WPP_SF_d(1035, 66, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v13);
      }
      else
      {
        if ( (*a10 & 0x10000000000000LL) != 0 )
        {
          if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
            WPP_SF_(1035, 67, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids);
          if ( v12 )
          {
            if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
              WPP_SF_d(1035, 68, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v12);
            v12 = 0;
          }
        }
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_SdiDl((*a10 >> 50) & 1, *a10, v14, a1, a2, *a10, v12, (*a10 & 0x4000000000000LL) != 0);
        QueryBlob = Query_AllocateQueryBlob(0);
        if ( QueryBlob )
        {
          EventW = CreateEventW(0, 1, 0, 0);
          *(_QWORD *)(QueryBlob + 1168) = EventW;
          if ( EventW )
          {
            *(_QWORD *)(QueryBlob + 232) = a1;
            *(_QWORD *)(QueryBlob + 240) = a1;
            *(_QWORD *)(QueryBlob + 248) = a1;
            *(_WORD *)(QueryBlob + 256) = a2;
            *(_QWORD *)(QueryBlob + 264) = *a10;
            *(_QWORD *)(QueryBlob + 600) = *a10;
            *(_DWORD *)(QueryBlob + 396) = a6;
            *(_DWORD *)(QueryBlob + 408) = a4;
            *(_DWORD *)(QueryBlob + 412) = a5;
            *(_QWORD *)(QueryBlob + 352) = a10;
            *(_QWORD *)(QueryBlob + 3384) = 0;
            *(_DWORD *)(QueryBlob + 404) = v12;
            v18 = _InterlockedIncrement(&g_dwCorrelationId);
            *(_WORD *)(QueryBlob + 3512) = a9;
            *(_DWORD *)(QueryBlob + 3516) = v18;
            Config = ZtGetConfig(0, &v23);
            if ( !Config )
            {
              if ( HIDWORD(v26) == 2 )
              {
                if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
                  WPP_SF_qd(v19, 70, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, a8, a7);
                if ( !HIDWORD(v24) )
                  *(_QWORD *)(QueryBlob + 264) |= 0x40uLL;
              }
              else
              {
                *(_DWORD *)(QueryBlob + 1056) = a7;
                *(_QWORD *)(QueryBlob + 1064) = a8;
              }
              *(_QWORD *)(QueryBlob + 1072) = Cache_Query;
              *(_QWORD *)(QueryBlob + 1080) = Cache_QueryResponse;
              *(_QWORD *)(QueryBlob + 1088) = Cache_QueryScreen;
              *(_QWORD *)(QueryBlob + 1144) = ResolverQuery;
              *(_QWORD *)(QueryBlob + 1128) = ResolverProcessQueryResult;
              *(_QWORD *)(QueryBlob + 1120) = VPNTriggerNotify;
              *(_QWORD *)(QueryBlob + 1096) = UnreachableServerCache_IsUnreachable;
              *(_QWORD *)(QueryBlob + 1104) = UnreachableServerCache_UpdateUnreachability;
              *(_QWORD *)(QueryBlob + 1112) = FixConnectionManagerNetInfoForInterfaceIndex;
              *a11 = QueryBlob;
              goto LABEL_15;
            }
          }
          else
          {
            Config = GetLastError();
          }
          DeRefQueryBlobEx(QueryBlob, "Query_PrepareBlob", 2173, 0);
        }
        else
        {
          Config = 14;
        }
      }
    }
    else
    {
      Config = 123;
    }
  }
  else
  {
    Config = 87;
  }
LABEL_15:
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 71, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, Config);
  return Config;
}

```

## disassembly

```asm
0x180003240  mov     r11, rsp
0x180003243  mov     [r11+10h], rbx
0x180003247  push    rbp
0x180003248  push    rsi
0x180003249  push    rdi
0x18000324a  push    r12
0x18000324c  push    r13
0x18000324e  push    r14
0x180003250  push    r15
0x180003252  sub     rsp, 0C0h
0x180003259  mov     rax, cs:__security_cookie
0x180003260  xor     rax, rsp
0x180003263  mov     [rsp+0F8h+var_40], rax
0x18000326b  mov     rdi, [rsp+0F8h+arg_50]
0x180003273  xorps   xmm0, xmm0
0x180003276  mov     r14, [rsp+0F8h+arg_38]
0x18000327e  mov     r12, rcx
0x180003281  mov     r13, [rsp+0F8h+arg_48]
0x180003289  xor     ecx, ecx
0x18000328b  movzx   eax, dx
0x18000328e  mov     ebp, r8d
0x180003291  mov     [r11-48h], rcx
0x180003295  mov     [rsp+0F8h+var_84], r9d
0x18000329a  mov     [rsp+0F8h+var_88], ax
0x18000329f  mov     [rsp+0F8h+var_80], rdi
0x1800032a4  movups  xmmword ptr [r11-78h], xmm0
0x1800032a9  movups  xmmword ptr [r11-68h], xmm0
0x1800032ae  movups  xmmword ptr [r11-58h], xmm0
0x1800032b3  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800032ba  movzx   ebx, [rsp+0F8h+arg_40]
0x1800032c2  mov     r15d, [rsp+0F8h+arg_30]
0x1800032ca  jnz     loc_1800034F6
0x1800032d0  test    rdi, rdi
0x1800032d3  jz      loc_180003658
0x1800032d9  mov     qword ptr [rdi], 0
0x1800032e0  test    r12, r12
0x1800032e3  jz      loc_1800034EF
0x1800032e9  mov     rdx, r14
0x1800032ec  mov     ecx, r15d
0x1800032ef  call    ValidateCustomServers
0x1800032f4  mov     esi, eax
0x1800032f6  test    eax, eax
0x1800032f8  jnz     loc_18000362D
0x1800032fe  mov     rax, 10000000000000h
0x180003308  test    [r13+0], rax
0x18000330c  jnz     loc_18000353F
0x180003312  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180003319  jnz     loc_18000358F
0x18000331f  movzx   esi, [rsp+0F8h+var_88]
0x180003324  xor     ecx, ecx
0x180003326  call    Query_AllocateQueryBlob
0x18000332b  mov     rdi, rax
0x18000332e  test    rax, rax
0x180003331  jz      loc_1800035C0
0x180003337  xor     r9d, r9d; lpName
0x18000333a  xor     r8d, r8d; bInitialState
0x18000333d  xor     ecx, ecx; lpEventAttributes
0x18000333f  lea     edx, [r9+1]; bManualReset
0x180003343  call    cs:__imp_CreateEventW
0x180003349  mov     [rdi+490h], rax
0x180003350  test    rax, rax
0x180003353  jz      loc_1800035CA
0x180003359  mov     [rdi+0E8h], r12
0x180003360  mov     [rdi+0F0h], r12
0x180003367  mov     [rdi+0F8h], r12
0x18000336e  mov     [rdi+100h], si
0x180003375  mov     rax, [r13+0]
0x180003379  mov     [rdi+108h], rax
0x180003380  mov     rax, [r13+0]
0x180003384  mov     [rdi+258h], rax
0x18000338b  mov     eax, [rsp+0F8h+arg_28]
0x180003392  mov     [rdi+18Ch], eax
0x180003398  mov     eax, [rsp+0F8h+var_84]
0x18000339c  mov     [rdi+198h], eax
0x1800033a2  mov     eax, [rsp+0F8h+arg_20]
0x1800033a9  mov     [rdi+19Ch], eax
0x1800033af  mov     eax, 1
0x1800033b4  mov     [rdi+160h], r13
0x1800033bb  mov     qword ptr [rdi+0D38h], 0
0x1800033c6  mov     [rdi+194h], ebp
0x1800033cc  lock xadd cs:g_dwCorrelationId, eax
0x1800033d4  inc     eax
0x1800033d6  mov     [rdi+0DB8h], bx
0x1800033dd  lea     rdx, [rsp+0F8h+var_78]
0x1800033e5  mov     [rdi+0DBCh], eax
0x1800033eb  xor     ecx, ecx
0x1800033ed  call    ZtGetConfig
0x1800033f2  mov     esi, eax
0x1800033f4  test    eax, eax
0x1800033f6  jnz     loc_1800035D2
0x1800033fc  cmp     [rsp+0F8h+var_44], 2
0x180003404  jz      loc_1800035F0
0x18000340a  mov     [rdi+420h], r15d
0x180003411  mov     [rdi+428h], r14
0x180003418  lea     rax, Cache_Query
0x18000341f  mov     [rdi+430h], rax
0x180003426  lea     rax, Cache_QueryResponse
0x18000342d  mov     [rdi+438h], rax
0x180003434  lea     rax, Cache_QueryScreen
0x18000343b  mov     [rdi+440h], rax
0x180003442  lea     rax, ResolverQuery
0x180003449  mov     [rdi+478h], rax
0x180003450  lea     rax, ResolverProcessQueryResult
0x180003457  mov     [rdi+468h], rax
0x18000345e  lea     rax, VPNTriggerNotify
0x180003465  mov     [rdi+460h], rax
0x18000346c  lea     rax, UnreachableServerCache_IsUnreachable
0x180003473  mov     [rdi+448h], rax
0x18000347a  lea     rax, UnreachableServerCache_UpdateUnreachability
0x180003481  mov     [rdi+450h], rax
0x180003488  lea     rax, FixConnectionManagerNetInfoForInterfaceIndex
0x18000348f  mov     [rdi+458h], rax
0x180003496  mov     rax, [rsp+0F8h+var_80]
0x18000349b  mov     [rax], rdi
0x18000349e  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800034a5  jnz     short loc_1800034D4
0x1800034a7  mov     eax, esi
0x1800034a9  mov     rcx, [rsp+0F8h+var_40]
0x1800034b1  xor     rcx, rsp; StackCookie
0x1800034b4  call    __security_check_cookie
0x1800034b9  mov     rbx, [rsp+0F8h+arg_8]
0x1800034c1  add     rsp, 0C0h
0x1800034c8  pop     r15
0x1800034ca  pop     r14
0x1800034cc  pop     r13
0x1800034ce  pop     r12
0x1800034d0  pop     rdi
0x1800034d1  pop     rsi
0x1800034d2  pop     rbp
0x1800034d3  retn
0x1800034d4  mov     edx, 47h ; 'G'
0x1800034d9  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x1800034e0  mov     ecx, 40Bh
0x1800034e5  mov     r9d, esi
0x1800034e8  call    WPP_SF_d
0x1800034ed  jmp     short loc_1800034A7
0x1800034ef  mov     esi, 7Bh ; '{'
0x1800034f4  jmp     short loc_18000349E
0x1800034f6  mov     ecx, [rsp+0F8h+arg_28]
0x1800034fd  mov     [rsp+0F8h+var_90], rdi
0x180003502  mov     [rsp+0F8h+var_98], r13
0x180003507  mov     [rsp+0F8h+var_A0], bx
0x18000350c  mov     [rsp+0F8h+var_A8], r14
0x180003511  mov     [rsp+0F8h+var_B0], r15d
0x180003516  mov     [rsp+0F8h+var_B8], ecx
0x18000351a  mov     ecx, [rsp+0F8h+arg_20]
0x180003521  mov     [rsp+0F8h+var_C0], ecx
0x180003525  mov     [rsp+0F8h+var_C8], r9d
0x18000352a  mov     r9, r12
0x18000352d  mov     dword ptr [rsp+0F8h+var_D0], ebp
0x180003531  mov     [rsp+0F8h+var_D8], eax
0x180003535  call    WPP_SF_SDDlDDDqHqq
0x18000353a  jmp     loc_1800032D0
0x18000353f  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180003546  jz      short loc_18000355E
0x180003548  mov     edx, 43h ; 'C'
0x18000354d  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x180003554  mov     ecx, 40Bh
0x180003559  call    WPP_SF_
0x18000355e  test    ebp, ebp
0x180003560  jz      loc_180003312
0x180003566  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18000356d  jz      short loc_180003588
0x18000356f  mov     edx, 44h ; 'D'
0x180003574  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x18000357b  mov     ecx, 40Bh
0x180003580  mov     r9d, ebp
0x180003583  call    WPP_SF_d
0x180003588  xor     ebp, ebp
0x18000358a  jmp     loc_180003312
0x18000358f  mov     rdx, [r13+0]
0x180003593  mov     r9, r12
0x180003596  movzx   esi, [rsp+0F8h+var_88]
0x18000359b  mov     rcx, rdx
0x18000359e  shr     rcx, 32h
0x1800035a2  and     ecx, 1
0x1800035a5  mov     [rsp+0F8h+var_C0], ecx
0x1800035a9  mov     [rsp+0F8h+var_C8], ebp
0x1800035ad  mov     [rsp+0F8h+var_D0], rdx
0x1800035b2  mov     [rsp+0F8h+var_D8], esi
0x1800035b6  call    WPP_SF_SdiDl
0x1800035bb  jmp     loc_180003324
0x1800035c0  mov     esi, 0Eh
0x1800035c5  jmp     loc_18000349E
0x1800035ca  call    cs:__imp_GetLastError
0x1800035d0  mov     esi, eax
0x1800035d2  xor     r9d, r9d
0x1800035d5  lea     rdx, aQueryPreparebl; "Query_PrepareBlob"
0x1800035dc  mov     r8d, 87Dh
0x1800035e2  mov     rcx, rdi
0x1800035e5  call    cs:__imp_DeRefQueryBlobEx
0x1800035eb  jmp     loc_18000349E
0x1800035f0  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800035f7  jz      short loc_180003612
0x1800035f9  mov     edx, 46h ; 'F'
0x1800035fe  mov     [rsp+0F8h+var_D8], r15d
0x180003603  mov     r9, r14
0x180003606  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x18000360d  call    WPP_SF_qd
0x180003612  cmp     [rsp+0F8h+var_5C], 0
0x18000361a  jnz     loc_180003418
0x180003620  or      qword ptr [rdi+108h], 40h
0x180003628  jmp     loc_180003418
0x18000362d  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180003634  jz      loc_1800034A7
0x18000363a  mov     edx, 42h ; 'B'
0x18000363f  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x180003646  mov     ecx, 40Bh
0x18000364b  mov     r9d, eax
0x18000364e  call    WPP_SF_d
0x180003653  jmp     loc_18000349E
0x180003658  mov     esi, 57h ; 'W'
0x18000365d  jmp     loc_18000349E
```
