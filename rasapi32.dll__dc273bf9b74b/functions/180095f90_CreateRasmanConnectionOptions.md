# CreateRasmanConnectionOptions

- ea: `0x180095f90`
- end: `0x1800961ef`
- name: `CreateRasmanConnectionOptions`
- size: `607`
- prototype: `__int64 __fastcall(__int64, _DWORD *, int, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x180029cd0`

## callees

- `0x180012f7c`
- `0x18004e580`
- `0x18004e984`
- `0x18007efdc`
- `0x180095f90`
- `0x180097974`
- `0x1800ca0c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180096078`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180096078`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180096084`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180096084`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009608e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009608e`

## pseudocode

```c
__int64 __fastcall CreateRasmanConnectionOptions(__int64 a1, _DWORD *a2, int a3, __int64 a4)
{
  _DWORD *v7; // rcx
  _DWORD *v8; // rsi
  __int64 v9; // r9
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // r14
  DWORD CurrentProcessId; // eax
  DWORD LastError; // eax

  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    LOBYTE(a4) = a3 != 0;
    WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, a4);
    v7 = WPP_GLOBAL_Control;
  }
  v8 = *(_DWORD **)(a1 + 1584);
  if ( v8 )
  {
    v12 = *(_QWORD *)(a1 + 1592);
    if ( !v12 )
    {
      v9 = 87;
      v10 = 87;
      if ( v7 == (_DWORD *)&WPP_GLOBAL_Control )
        return v10;
      if ( (v7[7] & 0x800) == 0 || *((_BYTE *)v7 + 25) < 2u )
        goto LABEL_37;
      v11 = 31;
      goto LABEL_10;
    }
    *a2 = v8[46];
    CurrentProcessId = GetCurrentProcessId();
    if ( !ProcessIdToSessionId(CurrentProcessId, a2 + 1) )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( !LastError )
        goto LABEL_36;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v10;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_37;
      v11 = 32;
      goto LABEL_22;
    }
    a2[2] = a3 != 0;
    a2[3] = v8[6];
    a2[4] = v8[137];
    a2[5] = RdtFromDeviceType((LPCWCH)(a1 + 924));
    if ( v8[6] == 2 )
    {
      a2[39] = 1;
      LastError = DwGetDeviceName(a1, a2 + 6);
      v10 = LastError;
      if ( LastError )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v10;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_37;
        v11 = 33;
LABEL_22:
        v9 = LastError;
        goto LABEL_10;
      }
    }
    else
    {
      v10 = 0;
      a2[39] = 0;
      StrncpyWtoA(a2 + 6, *(_QWORD *)(v12 + 16), 129, 0);
    }
    a2[40] = v8[214];
    if ( v8[214] == 1
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_425b3625ab793a6219f8039beff53b24_Traceguids);
    }
    a2[41] = v8[128];
    goto LABEL_36;
  }
  v9 = 87;
  v10 = 87;
  if ( v7 == (_DWORD *)&WPP_GLOBAL_Control )
    return v10;
  if ( (v7[7] & 0x800) != 0 && *((_BYTE *)v7 + 25) >= 2u )
  {
    v11 = 30;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v7 + 2), v11, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v9);
LABEL_36:
    v7 = WPP_GLOBAL_Control;
  }
LABEL_37:
  if ( v7 != (_DWORD *)&WPP_GLOBAL_Control && (v7[7] & 0x800) != 0 && *((_BYTE *)v7 + 25) >= 6u )
    WPP_SF_d(*((_QWORD *)v7 + 2), 35, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x180095f90  push    rbx
0x180095f92  push    rbp
0x180095f93  push    rsi
0x180095f94  push    rdi
0x180095f95  push    r12
0x180095f97  push    r13
0x180095f99  push    r14
0x180095f9b  push    r15
0x180095f9d  sub     rsp, 28h
0x180095fa1  mov     r15d, r8d
0x180095fa4  mov     rdi, rdx
0x180095fa7  mov     rbp, rcx
0x180095faa  mov     rcx, cs:WPP_GLOBAL_Control
0x180095fb1  lea     r13, WPP_GLOBAL_Control
0x180095fb8  mov     r12d, 800h
0x180095fbe  cmp     rcx, r13
0x180095fc1  jz      short loc_180095FF2
0x180095fc3  test    [rcx+1Ch], r12d
0x180095fc7  jz      short loc_180095FF2
0x180095fc9  cmp     byte ptr [rcx+19h], 6
0x180095fcd  jb      short loc_180095FF2
0x180095fcf  mov     rcx, [rcx+10h]
0x180095fd3  test    r8d, r8d
0x180095fd6  mov     edx, 1Dh
0x180095fdb  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x180095fe2  setnz   r9b
0x180095fe6  call    WPP_SF_c
0x180095feb  mov     rcx, cs:WPP_GLOBAL_Control
0x180095ff2  mov     rsi, [rbp+630h]
0x180095ff9  test    rsi, rsi
0x180095ffc  jnz     short loc_18009603A
0x180095ffe  lea     r9d, [rsi+57h]
0x180096002  mov     ebx, r9d
0x180096005  cmp     rcx, r13
0x180096008  jz      loc_1800961DC
0x18009600e  test    [rcx+1Ch], r12d
0x180096012  jz      loc_1800961B3
0x180096018  cmp     byte ptr [rcx+19h], 2
0x18009601c  jb      loc_1800961B3
0x180096022  lea     edx, [rsi+1Eh]
0x180096025  mov     rcx, [rcx+10h]
0x180096029  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x180096030  call    WPP_SF_d
0x180096035  jmp     loc_1800961AC
0x18009603a  mov     r14, [rbp+638h]
0x180096041  test    r14, r14
0x180096044  jnz     short loc_180096070
0x180096046  lea     r9d, [r14+57h]
0x18009604a  mov     ebx, r9d
0x18009604d  cmp     rcx, r13
0x180096050  jz      loc_1800961DC
0x180096056  test    [rcx+1Ch], r12d
0x18009605a  jz      loc_1800961B3
0x180096060  cmp     byte ptr [rcx+19h], 2
0x180096064  jb      loc_1800961B3
0x18009606a  lea     edx, [r14+1Fh]
0x18009606e  jmp     short loc_180096025
0x180096070  mov     eax, [rsi+0B8h]
0x180096076  mov     [rdi], eax
0x180096078  call    cs:__imp_GetCurrentProcessId
0x18009607e  mov     ecx, eax; dwProcessId
0x180096080  lea     rdx, [rdi+4]; pSessionId
0x180096084  call    cs:__imp_ProcessIdToSessionId
0x18009608a  test    eax, eax
0x18009608c  jnz     short loc_1800960CF
0x18009608e  call    cs:__imp_GetLastError
0x180096094  mov     ebx, eax
0x180096096  test    eax, eax
0x180096098  jz      loc_1800961AC
0x18009609e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800960a5  cmp     rcx, r13
0x1800960a8  jz      loc_1800961DC
0x1800960ae  test    [rcx+1Ch], r12d
0x1800960b2  jz      loc_1800961B3
0x1800960b8  cmp     byte ptr [rcx+19h], 2
0x1800960bc  jb      loc_1800961B3
0x1800960c2  mov     edx, 20h ; ' '
0x1800960c7  mov     r9d, eax
0x1800960ca  jmp     loc_180096025
0x1800960cf  xor     eax, eax
0x1800960d1  lea     rcx, [rbp+39Ch]; lpString1
0x1800960d8  test    r15d, r15d
0x1800960db  setnz   al
0x1800960de  mov     [rdi+8], eax
0x1800960e1  mov     eax, [rsi+18h]
0x1800960e4  mov     [rdi+0Ch], eax
0x1800960e7  mov     eax, [rsi+224h]
0x1800960ed  mov     [rdi+10h], eax
0x1800960f0  mov     edx, [r14+30h]
0x1800960f4  call    RdtFromDeviceType
0x1800960f9  mov     [rdi+14h], eax
0x1800960fc  lea     rcx, [rdi+18h]
0x180096100  cmp     dword ptr [rsi+18h], 2
0x180096104  jnz     short loc_180096144
0x180096106  mov     rdx, rcx
0x180096109  mov     dword ptr [rdi+9Ch], 1
0x180096113  mov     rcx, rbp
0x180096116  call    DwGetDeviceName
0x18009611b  mov     ebx, eax
0x18009611d  test    eax, eax
0x18009611f  jz      short loc_18009615E
0x180096121  mov     rcx, cs:WPP_GLOBAL_Control
0x180096128  cmp     rcx, r13
0x18009612b  jz      loc_1800961DC
0x180096131  test    [rcx+1Ch], r12d
0x180096135  jz      short loc_1800961B3
0x180096137  cmp     byte ptr [rcx+19h], 2
0x18009613b  jb      short loc_1800961B3
0x18009613d  mov     edx, 21h ; '!'
0x180096142  jmp     short loc_1800960C7
0x180096144  xor     ebx, ebx
0x180096146  xor     r9d, r9d
0x180096149  mov     [rdi+9Ch], ebx
0x18009614f  mov     r8d, 81h
0x180096155  mov     rdx, [r14+10h]
0x180096159  call    StrncpyWtoA
0x18009615e  mov     eax, [rsi+358h]
0x180096164  mov     [rdi+0A0h], eax
0x18009616a  cmp     dword ptr [rsi+358h], 1
0x180096171  jnz     short loc_1800961A0
0x180096173  mov     rcx, cs:WPP_GLOBAL_Control
0x18009617a  cmp     rcx, r13
0x18009617d  jz      short loc_1800961A0
0x18009617f  test    [rcx+1Ch], r12d
0x180096183  jz      short loc_1800961A0
0x180096185  cmp     byte ptr [rcx+19h], 5
0x180096189  jb      short loc_1800961A0
0x18009618b  mov     rcx, [rcx+10h]
0x18009618f  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x180096196  mov     edx, 22h ; '"'
0x18009619b  call    WPP_SF_
0x1800961a0  mov     eax, [rsi+200h]
0x1800961a6  mov     [rdi+0A4h], eax
0x1800961ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800961b3  cmp     rcx, r13
0x1800961b6  jz      short loc_1800961DC
0x1800961b8  test    [rcx+1Ch], r12d
0x1800961bc  jz      short loc_1800961DC
0x1800961be  cmp     byte ptr [rcx+19h], 6
0x1800961c2  jb      short loc_1800961DC
0x1800961c4  mov     rcx, [rcx+10h]
0x1800961c8  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x1800961cf  mov     edx, 23h ; '#'
0x1800961d4  mov     r9d, ebx
0x1800961d7  call    WPP_SF_d
0x1800961dc  mov     eax, ebx
0x1800961de  add     rsp, 28h
0x1800961e2  pop     r15
0x1800961e4  pop     r14
0x1800961e6  pop     r13
0x1800961e8  pop     r12
0x1800961ea  pop     rdi
0x1800961eb  pop     rsi
0x1800961ec  pop     rbp
0x1800961ed  pop     rbx
0x1800961ee  retn
```
