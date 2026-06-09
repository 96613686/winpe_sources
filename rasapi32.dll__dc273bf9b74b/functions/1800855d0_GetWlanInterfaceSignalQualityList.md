# GetWlanInterfaceSignalQualityList

- ea: `0x1800855d0`
- end: `0x1800859bc`
- name: `GetWlanInterfaceSignalQualityList`
- size: `1004`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18008dc94`

## callees

- `0x18004e580`
- `0x18004e984`
- `0x1800655d8`
- `0x180085480`
- `0x1800855d0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800858d6`
- `msvcrt!memcpy_s` at `0x1800858d6`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18008578f`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180085871`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18008578f`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180085871`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008591f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008593d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008591f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008593d`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180085956`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180085956`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanCloseHandle` at `0x180085979`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanCloseHandle` at `0x180085979`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanOpenHandle` at `0x1800856eb`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanOpenHandle` at `0x1800856eb`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanEnumInterfaces` at `0x180085741`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanEnumInterfaces` at `0x180085741`

## pseudocode

```c
__int64 __fastcall GetWlanInterfaceSignalQualityList(_QWORD *a1, _DWORD *a2)
{
  _DWORD *v2; // r15
  _DWORD *v4; // rcx
  __int64 v5; // rdx
  unsigned int v6; // ebx
  DWORD v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r9
  _DWORD *v10; // r14
  __int64 v11; // rsi
  DWORD v12; // ebx
  GUID *p_InterfaceGuid; // rdx
  unsigned int WlanInterfaceSignalQuality; // eax
  HGLOBAL v15; // rax
  void *v16; // rdi
  unsigned int v17; // eax
  void *phClientHandle; // [rsp+20h] [rbp-10h] BYREF
  DWORD pdwNegotiatedVersion; // [rsp+80h] [rbp+50h] BYREF
  PWLAN_INTERFACE_INFO_LIST ppInterfaceList; // [rsp+88h] [rbp+58h] BYREF

  v2 = a2;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  phClientHandle = 0;
  pdwNegotiatedVersion = 0;
  ppInterfaceList = 0;
  if ( !a1 )
  {
    if ( v4 == (_DWORD *)&WPP_GLOBAL_Control || (v4[7] & 0x800) == 0 || *((_BYTE *)v4 + 25) < 5u )
      goto LABEL_11;
    v5 = 15;
LABEL_10:
    WPP_SF_(*((_QWORD *)v4 + 2), v5, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
    v4 = WPP_GLOBAL_Control;
LABEL_11:
    v6 = 87;
    goto LABEL_64;
  }
  if ( !v2 )
  {
    if ( v4 == (_DWORD *)&WPP_GLOBAL_Control || (v4[7] & 0x800) == 0 || *((_BYTE *)v4 + 25) < 5u )
      goto LABEL_11;
    v5 = 16;
    goto LABEL_10;
  }
  if ( (unsigned __int8)IsWlanQueryInterfacePresent() )
  {
    v7 = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, &phClientHandle);
    v6 = v7;
    if ( v7 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_64;
      }
      v8 = 18;
    }
    else
    {
      v7 = WlanEnumInterfaces(phClientHandle, 0, &ppInterfaceList);
      v6 = v7;
      if ( !v7 )
      {
        if ( !ppInterfaceList->dwNumberOfItems )
          goto LABEL_63;
        v10 = GlobalAlloc(0x40u, 4LL * ppInterfaceList->dwNumberOfItems);
        if ( v10 )
        {
          v11 = 0;
          v12 = 0;
          if ( ppInterfaceList->dwNumberOfItems )
          {
            do
            {
              p_InterfaceGuid = &ppInterfaceList->InterfaceInfo[v12].InterfaceGuid;
              if ( p_InterfaceGuid[33].Data1 == 1 )
              {
                WlanInterfaceSignalQuality = GetWlanInterfaceSignalQuality(phClientHandle, p_InterfaceGuid);
                if ( WlanInterfaceSignalQuality )
                {
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      21,
                      WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids,
                      WlanInterfaceSignalQuality);
                  }
                }
                else
                {
                  v10[v11] = 0;
                  v11 = (unsigned int)(v11 + 1);
                }
              }
              ++v12;
            }
            while ( v12 < ppInterfaceList->dwNumberOfItems );
            v2 = a2;
          }
          v15 = GlobalAlloc(0x40u, 4LL * (unsigned int)v11);
          v16 = v15;
          if ( v15 )
          {
            v17 = memcpy_s(v15, 4LL * (unsigned int)v11, v10, 4LL * (unsigned int)v11);
            v6 = v17;
            if ( v17 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v17);
              }
              GlobalFree(v16);
            }
            else
            {
              *v2 = v11;
              *a1 = v16;
            }
          }
          else
          {
            v6 = 8;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, 8);
            }
          }
          GlobalFree(v10);
          goto LABEL_63;
        }
        v9 = 8;
        v6 = 8;
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_64;
        }
        v8 = 20;
LABEL_28:
        WPP_SF_d(*((_QWORD *)v4 + 2), v8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v9);
        goto LABEL_63;
      }
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_64;
      }
      v8 = 19;
    }
    v9 = v7;
    goto LABEL_28;
  }
  v6 = 0;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
LABEL_63:
    v4 = WPP_GLOBAL_Control;
  }
LABEL_64:
  if ( ppInterfaceList )
  {
    WlanFreeMemory(ppInterfaceList);
    v4 = WPP_GLOBAL_Control;
    ppInterfaceList = 0;
  }
  if ( phClientHandle )
  {
    WlanCloseHandle(phClientHandle, 0);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != (_DWORD *)&WPP_GLOBAL_Control && (v4[7] & 0x800) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_(*((_QWORD *)v4 + 2), 24, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
  return v6;
}

```

## disassembly

```asm
0x1800855d0  mov     [rsp-38h+arg_8], rdx
0x1800855d5  push    rbp
0x1800855d6  push    rbx
0x1800855d7  push    rsi
0x1800855d8  push    rdi
0x1800855d9  push    r12
0x1800855db  push    r14
0x1800855dd  push    r15
0x1800855df  mov     rbp, rsp
0x1800855e2  sub     rsp, 30h
0x1800855e6  mov     r15, rdx
0x1800855e9  mov     r12, rcx
0x1800855ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800855f3  lea     rsi, WPP_GLOBAL_Control
0x1800855fa  mov     edi, 800h
0x1800855ff  cmp     rcx, rsi
0x180085602  jz      short loc_18008562B
0x180085604  test    [rcx+1Ch], edi
0x180085607  jz      short loc_18008562B
0x180085609  cmp     byte ptr [rcx+19h], 6
0x18008560d  jb      short loc_18008562B
0x18008560f  mov     rcx, [rcx+10h]
0x180085613  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x18008561a  mov     edx, 0Eh
0x18008561f  call    WPP_SF_
0x180085624  mov     rcx, cs:WPP_GLOBAL_Control
0x18008562b  mov     [rbp+phClientHandle], 0
0x180085633  mov     [rbp+pdwNegotiatedVersion], 0
0x18008563a  mov     [rbp+ppInterfaceList], 0
0x180085642  test    r12, r12
0x180085645  jnz     short loc_18008567D
0x180085647  cmp     rcx, rsi
0x18008564a  jz      short loc_180085673
0x18008564c  test    [rcx+1Ch], edi
0x18008564f  jz      short loc_180085673
0x180085651  cmp     byte ptr [rcx+19h], 5
0x180085655  jb      short loc_180085673
0x180085657  lea     edx, [r12+0Fh]
0x18008565c  mov     rcx, [rcx+10h]
0x180085660  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x180085667  call    WPP_SF_
0x18008566c  mov     rcx, cs:WPP_GLOBAL_Control
0x180085673  mov     ebx, 57h ; 'W'
0x180085678  jmp     loc_18008594A
0x18008567d  test    r15, r15
0x180085680  jnz     short loc_180085698
0x180085682  cmp     rcx, rsi
0x180085685  jz      short loc_180085673
0x180085687  test    [rcx+1Ch], edi
0x18008568a  jz      short loc_180085673
0x18008568c  cmp     byte ptr [rcx+19h], 5
0x180085690  jb      short loc_180085673
0x180085692  lea     edx, [r15+10h]
0x180085696  jmp     short loc_18008565C
0x180085698  call    IsWlanQueryInterfacePresent
0x18008569d  test    al, al
0x18008569f  jnz     short loc_1800856DE
0x1800856a1  xor     ebx, ebx
0x1800856a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800856aa  cmp     rcx, rsi
0x1800856ad  jz      loc_18008594A
0x1800856b3  test    [rcx+1Ch], edi
0x1800856b6  jz      loc_18008594A
0x1800856bc  cmp     byte ptr [rcx+19h], 5
0x1800856c0  jb      loc_18008594A
0x1800856c6  mov     rcx, [rcx+10h]
0x1800856ca  lea     edx, [rbx+11h]
0x1800856cd  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x1800856d4  call    WPP_SF_
0x1800856d9  jmp     loc_180085943
0x1800856de  xor     edx, edx; pReserved
0x1800856e0  lea     r9, [rbp+phClientHandle]; phClientHandle
0x1800856e4  lea     r8, [rbp+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x1800856e8  lea     ecx, [rdx+2]; dwClientVersion
0x1800856eb  call    cs:__imp_WlanOpenHandle
0x1800856f1  mov     ebx, eax
0x1800856f3  test    eax, eax
0x1800856f5  jz      short loc_180085737
0x1800856f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800856fe  cmp     rcx, rsi
0x180085701  jz      loc_18008594A
0x180085707  test    [rcx+1Ch], edi
0x18008570a  jz      loc_18008594A
0x180085710  cmp     byte ptr [rcx+19h], 2
0x180085714  jb      loc_18008594A
0x18008571a  mov     edx, 12h
0x18008571f  mov     r9d, eax
0x180085722  mov     rcx, [rcx+10h]
0x180085726  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x18008572d  call    WPP_SF_d
0x180085732  jmp     loc_180085943
0x180085737  mov     rcx, [rbp+phClientHandle]; hClientHandle
0x18008573b  lea     r8, [rbp+ppInterfaceList]; ppInterfaceList
0x18008573f  xor     edx, edx; pReserved
0x180085741  call    cs:__imp_WlanEnumInterfaces
0x180085747  mov     ebx, eax
0x180085749  test    eax, eax
0x18008574b  jz      short loc_180085777
0x18008574d  mov     rcx, cs:WPP_GLOBAL_Control
0x180085754  cmp     rcx, rsi
0x180085757  jz      loc_18008594A
0x18008575d  test    [rcx+1Ch], edi
0x180085760  jz      loc_18008594A
0x180085766  cmp     byte ptr [rcx+19h], 2
0x18008576a  jb      loc_18008594A
0x180085770  mov     edx, 13h
0x180085775  jmp     short loc_18008571F
0x180085777  mov     rax, [rbp+ppInterfaceList]
0x18008577b  cmp     dword ptr [rax], 0
0x18008577e  jbe     loc_180085943
0x180085784  mov     edx, [rax]
0x180085786  mov     ecx, 40h ; '@'; uFlags
0x18008578b  shl     rdx, 2; dwBytes
0x18008578f  call    cs:__imp_GlobalAlloc
0x180085795  mov     r14, rax
0x180085798  test    rax, rax
0x18008579b  jnz     short loc_1800857CF
0x18008579d  lea     r9d, [rax+8]
0x1800857a1  mov     ebx, r9d
0x1800857a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800857ab  cmp     rcx, rsi
0x1800857ae  jz      loc_18008594A
0x1800857b4  test    [rcx+1Ch], edi
0x1800857b7  jz      loc_18008594A
0x1800857bd  cmp     byte ptr [rcx+19h], 2
0x1800857c1  jb      loc_18008594A
0x1800857c7  lea     edx, [rax+14h]
0x1800857ca  jmp     loc_180085722
0x1800857cf  mov     rax, [rbp+ppInterfaceList]
0x1800857d3  xor     esi, esi
0x1800857d5  xor     ebx, ebx
0x1800857d7  cmp     [rax], ebx
0x1800857d9  jbe     loc_180085863
0x1800857df  lea     r15, WPP_GLOBAL_Control
0x1800857e6  mov     rdx, [rbp+ppInterfaceList]
0x1800857ea  add     rdx, 8
0x1800857ee  mov     eax, ebx
0x1800857f0  imul    rcx, rax, 214h
0x1800857f7  add     rdx, rcx; pInterfaceGuid
0x1800857fa  cmp     dword ptr [rdx+210h], 1
0x180085801  jnz     short loc_180085855
0x180085803  mov     rcx, [rbp+phClientHandle]; hClientHandle
0x180085807  lea     r8, [rbp+arg_0]
0x18008580b  mov     [rbp+arg_0], 0
0x180085812  call    GetWlanInterfaceSignalQuality
0x180085817  test    eax, eax
0x180085819  jz      short loc_18008584C
0x18008581b  mov     rcx, cs:WPP_GLOBAL_Control
0x180085822  cmp     rcx, r15
0x180085825  jz      short loc_180085855
0x180085827  test    [rcx+1Ch], edi
0x18008582a  jz      short loc_180085855
0x18008582c  cmp     byte ptr [rcx+19h], 2
0x180085830  jb      short loc_180085855
0x180085832  mov     rcx, [rcx+10h]
0x180085836  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x18008583d  mov     edx, 15h
0x180085842  mov     r9d, eax
0x180085845  call    WPP_SF_d
0x18008584a  jmp     short loc_180085855
0x18008584c  mov     eax, [rbp+arg_0]
0x18008584f  mov     [r14+rsi*4], eax
0x180085853  inc     esi
0x180085855  mov     rax, [rbp+ppInterfaceList]
0x180085859  inc     ebx
0x18008585b  cmp     ebx, [rax]
0x18008585d  jb      short loc_1800857E6
0x18008585f  mov     r15, [rbp+arg_8]
0x180085863  mov     ebx, esi
0x180085865  mov     ecx, 40h ; '@'; uFlags
0x18008586a  shl     rbx, 2
0x18008586e  mov     rdx, rbx; dwBytes
0x180085871  call    cs:__imp_GlobalAlloc
0x180085877  mov     rdi, rax
0x18008587a  test    rax, rax
0x18008587d  jnz     short loc_1800858CA
0x18008587f  lea     r9d, [rax+8]
0x180085883  mov     ebx, r9d
0x180085886  mov     rcx, cs:WPP_GLOBAL_Control
0x18008588d  lea     rsi, WPP_GLOBAL_Control
0x180085894  mov     edi, 800h
0x180085899  cmp     rcx, rsi
0x18008589c  jz      loc_18008593A
0x1800858a2  test    [rcx+1Ch], edi
0x1800858a5  jz      loc_18008593A
0x1800858ab  cmp     byte ptr [rcx+19h], 2
0x1800858af  jb      loc_18008593A
0x1800858b5  mov     rcx, [rcx+10h]
0x1800858b9  lea     edx, [rax+16h]
0x1800858bc  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x1800858c3  call    WPP_SF_d
0x1800858c8  jmp     short loc_18008593A
0x1800858ca  mov     r9, rbx; SourceSize
0x1800858cd  mov     r8, r14; Source
0x1800858d0  mov     rdx, rbx; DestinationSize
0x1800858d3  mov     rcx, rdi; Destination
0x1800858d6  call    cs:__imp_memcpy_s
0x1800858dc  mov     ebx, eax
0x1800858de  test    eax, eax
0x1800858e0  jz      short loc_180085927
0x1800858e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800858e9  lea     rsi, WPP_GLOBAL_Control
0x1800858f0  cmp     rcx, rsi
0x1800858f3  jz      short loc_18008591C
0x1800858f5  test    dword ptr [rcx+1Ch], 800h
0x1800858fc  jz      short loc_18008591C
0x1800858fe  cmp     byte ptr [rcx+19h], 2
0x180085902  jb      short loc_18008591C
0x180085904  mov     rcx, [rcx+10h]
0x180085908  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x18008590f  mov     edx, 17h
0x180085914  mov     r9d, eax
0x180085917  call    WPP_SF_d
0x18008591c  mov     rcx, rdi; hMem
0x18008591f  call    cs:__imp_GlobalFree
0x180085925  jmp     short loc_180085935
0x180085927  mov     [r15], esi
0x18008592a  lea     rsi, WPP_GLOBAL_Control
0x180085931  mov     [r12], rdi
0x180085935  mov     edi, 800h
0x18008593a  mov     rcx, r14; hMem
0x18008593d  call    cs:__imp_GlobalFree
0x180085943  mov     rcx, cs:WPP_GLOBAL_Control
0x18008594a  mov     rax, [rbp+ppInterfaceList]
0x18008594e  test    rax, rax
0x180085951  jz      short loc_18008596B
0x180085953  mov     rcx, rax; pMemory
0x180085956  call    cs:__imp_WlanFreeMemory
0x18008595c  mov     rcx, cs:WPP_GLOBAL_Control
0x180085963  mov     [rbp+ppInterfaceList], 0
0x18008596b  mov     rax, [rbp+phClientHandle]
0x18008596f  test    rax, rax
0x180085972  jz      short loc_180085986
0x180085974  xor     edx, edx; pReserved
0x180085976  mov     rcx, rax; hClientHandle
0x180085979  call    cs:__imp_WlanCloseHandle
0x18008597f  mov     rcx, cs:WPP_GLOBAL_Control
0x180085986  cmp     rcx, rsi
0x180085989  jz      short loc_1800859AB
0x18008598b  test    [rcx+1Ch], edi
0x18008598e  jz      short loc_1800859AB
0x180085990  cmp     byte ptr [rcx+19h], 6
0x180085994  jb      short loc_1800859AB
0x180085996  mov     rcx, [rcx+10h]
0x18008599a  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x1800859a1  mov     edx, 18h
0x1800859a6  call    WPP_SF_
0x1800859ab  mov     eax, ebx
0x1800859ad  add     rsp, 30h
0x1800859b1  pop     r15
0x1800859b3  pop     r14
0x1800859b5  pop     r12
0x1800859b7  pop     rdi
0x1800859b8  pop     rsi
0x1800859b9  pop     rbx
0x1800859ba  pop     rbp
0x1800859bb  retn
```
