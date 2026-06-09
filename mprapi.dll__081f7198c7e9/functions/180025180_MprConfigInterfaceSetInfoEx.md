# MprConfigInterfaceSetInfoEx

- ea: `0x180025180`
- end: `0x180025593`
- name: `MprConfigInterfaceSetInfoEx`
- size: `1043`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x1800178ac`
- `0x180017960`
- `0x180017a10`
- `0x180025180`
- `0x180027d5c`
- `0x180043390`
- `0x180043498`
- `0x18005112a`
- `0x180051160`

## import_xrefs

- `msvcrt!_time64` at `0x1800251ee`
- `msvcrt!_time64` at `0x1800251ee`
- `msvcrt!free` at `0x180025554`
- `msvcrt!free` at `0x180025554`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025248`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025546`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025248`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025546`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025235`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025235`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002532c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025369`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025502`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002552f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002532c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025369`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025502`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002552f`

## pseudocode

```c
__int64 __fastcall MprConfigInterfaceSetInfoEx(__int64 a1, __int64 a2, __int64 a3)
{
  BYTE *v6; // r14
  __int64 result; // rax
  unsigned int v8; // ebx
  int v9; // eax
  __int128 v10; // xmm1
  int v11; // r15d
  __int128 v12; // xmm0
  _WORD *v13; // r9
  __int64 v14; // r8
  __int64 v15; // rdx
  char *v16; // rax
  __int64 v17; // rcx
  _WORD *v18; // r11
  __int64 v19; // r10
  char *v20; // rcx
  _WORD *v21; // rax
  _WORD *v22; // rcx
  int v23; // eax
  HKEY v24; // rcx
  int v25; // edx
  unsigned int v26; // eax
  int v27; // [rsp+38h] [rbp-D0h] BYREF
  int v28; // [rsp+3Ch] [rbp-CCh] BYREF
  DWORD cbData[2]; // [rsp+40h] [rbp-C8h] BYREF
  BYTE *lpData; // [rsp+48h] [rbp-C0h] BYREF
  __time64_t Data; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE Data_8[28]; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v33; // [rsp+74h] [rbp-94h]
  char v34; // [rsp+90h] [rbp-78h] BYREF
  int v35; // [rsp+294h] [rbp+18Ch]
  __int128 v36; // [rsp+298h] [rbp+190h]
  int v37; // [rsp+2A8h] [rbp+1A0h]

  memset_0(Data_8, 0, 0x2C8u);
  v27 = 0;
  v6 = 0;
  v28 = 0;
  lpData = 0;
  cbData[0] = 0;
  Data = _time64(0);
  if ( !a3 || !a2 )
    return 87;
  if ( *(_BYTE *)a3 != 1 || *(_BYTE *)(a3 + 1) != 100 )
    return 50;
  result = MprConfigServerValidateCb(a1);
  if ( !(_DWORD)result )
  {
    EnterCriticalSection(&CfgLock);
    if ( *(_DWORD *)(a2 + 56) )
    {
      LeaveCriticalSection(&CfgLock);
      return 905;
    }
    else
    {
      v8 = CheckMultiTenancy(a1, &v27);
      if ( !v8 )
      {
        v8 = CheckModernStackEnabled(a1, &v28);
        if ( !v8 )
        {
          if ( (!v27 || *(_QWORD *)(a2 + 200) == *(_QWORD *)(a3 + 556) && *(_QWORD *)(a2 + 208) == *(_QWORD *)(a3 + 564))
            && (*(_QWORD *)(a3 + 556) == *(_QWORD *)&GUID_NULL.Data1
             && *(_QWORD *)(a3 + 564) == _mm_srli_si128((__m128i)GUID_NULL, 8).m128i_u64[0]
             || v27 && *(_DWORD *)(a2 + 24) == 2)
            && ((unsigned int)(*(_DWORD *)(a3 + 540) - 3) > 1 || *(_DWORD *)(a3 + 536)) )
          {
            v8 = RegSetValueExW(*(HKEY *)(a2 + 40), L"Enabled", 0, 4u, (const BYTE *)(a3 + 536), 4u);
            if ( !v8
              && (!v28
               || (v8 = RegSetValueExW(*(HKEY *)(a2 + 40), L"AutoConnectEnabled", 0, 4u, (const BYTE *)(a3 + 1276), 4u)) == 0) )
            {
              *(_DWORD *)(a2 + 28) = *(_DWORD *)(a3 + 536);
              if ( *(_DWORD *)(a3 + 540) != 2 )
                goto LABEL_51;
              v8 = ValidateQoSPolicies(a3 + 572);
              if ( !v8 )
              {
                v9 = *(_DWORD *)(a3 + 1136);
                v10 = *(_OWORD *)(a3 + 584);
                v11 = v27;
                *(_OWORD *)Data_8 = *(_OWORD *)(a3 + 572);
                v37 = v9;
                v12 = *(_OWORD *)(a2 + 200);
                *(_OWORD *)&Data_8[12] = v10;
                v33 = v12;
                v36 = *(_OWORD *)(a3 + 1120);
                *(_OWORD *)(a2 + 764) = v36;
                *(_DWORD *)(a2 + 780) = *(_DWORD *)(a3 + 1136);
                if ( v11 )
                {
                  v13 = (_WORD *)(a3 + 604);
                  v14 = 2147483646;
                  v15 = 257;
                  v16 = &v34;
                  v17 = 2147483646;
                  v18 = (_WORD *)(a3 + 604);
                  v19 = 257;
                  do
                  {
                    if ( !v17 )
                      break;
                    if ( !*v18 )
                      break;
                    *(_WORD *)v16 = *v18++;
                    v16 += 2;
                    --v17;
                    --v19;
                  }
                  while ( v19 );
                  v20 = v16 - 2;
                  if ( v19 )
                    v20 = v16;
                  v21 = (_WORD *)(a2 + 244);
                  *(_WORD *)v20 = 0;
                  do
                  {
                    if ( !v14 )
                      break;
                    if ( !*v13 )
                      break;
                    *v21++ = *v13++;
                    --v14;
                    --v15;
                  }
                  while ( v15 );
                  v22 = v21 - 1;
                  if ( v15 )
                    v22 = v21;
                  *v22 = 0;
                }
                v23 = *(_DWORD *)(a3 + 600);
                v24 = *(HKEY *)(a2 + 40);
                *(_DWORD *)(a2 + 760) = v23;
                v25 = *(_DWORD *)(a3 + 540);
                v35 = v23;
                v8 = WriteInterfaceExtraInfo(v24, v25, v11, (const struct in_addr *)Data_8);
                if ( !v8 )
                {
LABEL_51:
                  if ( !v28
                    || (v26 = ConvertPbkToRegistryEntry(a3 + 1144, &lpData, cbData), v6 = lpData, (v8 = v26) == 0)
                    && (v8 = RegSetValueExW(*(HKEY *)(a2 + 40), L"InterfaceInfoPbk", 0, 3u, lpData, cbData[0])) == 0 )
                  {
                    RegSetValueExW(*(HKEY *)(a2 + 40), 0, 0, 0xBu, (const BYTE *)&Data, 8u);
                    v8 = 0;
                  }
                }
              }
            }
          }
          else
          {
            v8 = 87;
          }
        }
      }
      LeaveCriticalSection(&CfgLock);
      if ( v6 )
        free(v6);
      return v8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180025180  mov     rax, rsp
0x180025183  push    rbp
0x180025184  push    rbx
0x180025185  push    rsi
0x180025186  push    rdi
0x180025187  push    r12
0x180025189  push    r14
0x18002518b  push    r15
0x18002518d  lea     rbp, [rax-278h]
0x180025194  sub     rsp, 340h
0x18002519b  movaps  xmmword ptr [rax-48h], xmm6
0x18002519f  mov     rax, cs:__security_cookie
0x1800251a6  xor     rax, rsp
0x1800251a9  mov     [rbp+270h+var_50], rax
0x1800251b0  mov     rdi, r8
0x1800251b3  mov     rsi, rdx
0x1800251b6  mov     r15, rcx
0x1800251b9  xor     edx, edx; Val
0x1800251bb  mov     r8d, 2C8h; Size
0x1800251c1  lea     rcx, [rsp+370h+Data+8]; void *
0x1800251c6  call    memset_0
0x1800251cb  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x1800251d2  xor     r12d, r12d
0x1800251d5  xor     ecx, ecx; Time
0x1800251d7  mov     [rsp+370h+var_340], r12d
0x1800251dc  mov     r14d, r12d
0x1800251df  mov     [rsp+370h+var_33C], r12d
0x1800251e4  mov     [rsp+370h+var_330], r12
0x1800251e9  mov     [rsp+370h+var_338], r12d
0x1800251ee  call    cs:__imp__time64
0x1800251f4  mov     qword ptr [rsp+370h+Data], rax
0x1800251f9  test    rdi, rdi
0x1800251fc  jz      loc_180025565
0x180025202  test    rsi, rsi
0x180025205  jz      loc_180025565
0x18002520b  cmp     byte ptr [rdi], 1
0x18002520e  jnz     loc_18002555E
0x180025214  cmp     byte ptr [rdi+1], 64h ; 'd'
0x180025218  jnz     loc_18002555E
0x18002521e  mov     rcx, r15
0x180025221  call    MprConfigServerValidateCb
0x180025226  test    eax, eax
0x180025228  jnz     loc_18002556A
0x18002522e  lea     rcx, CfgLock; lpCriticalSection
0x180025235  call    cs:__imp_EnterCriticalSection
0x18002523b  cmp     [rsi+38h], r12d
0x18002523f  jz      short loc_180025258
0x180025241  lea     rcx, CfgLock; lpCriticalSection
0x180025248  call    cs:__imp_LeaveCriticalSection
0x18002524e  mov     eax, 389h
0x180025253  jmp     loc_18002556A
0x180025258  lea     rdx, [rsp+370h+var_340]
0x18002525d  mov     rcx, r15
0x180025260  call    CheckMultiTenancy
0x180025265  mov     ebx, eax
0x180025267  test    eax, eax
0x180025269  jnz     loc_18002553F
0x18002526f  lea     rdx, [rsp+370h+var_33C]
0x180025274  mov     rcx, r15
0x180025277  call    CheckModernStackEnabled
0x18002527c  mov     ebx, eax
0x18002527e  test    eax, eax
0x180025280  jnz     loc_18002553F
0x180025286  mov     ecx, [rsp+370h+var_340]
0x18002528a  test    ecx, ecx
0x18002528c  jz      short loc_1800252B6
0x18002528e  mov     rax, [rsi+0C8h]
0x180025295  cmp     rax, [rdi+22Ch]
0x18002529c  jnz     loc_18002553A
0x1800252a2  mov     rax, [rsi+0D0h]
0x1800252a9  cmp     rax, [rdi+234h]
0x1800252b0  jnz     loc_18002553A
0x1800252b6  movq    rax, xmm6
0x1800252bb  cmp     [rdi+22Ch], rax
0x1800252c2  jnz     short loc_1800252D7
0x1800252c4  psrldq  xmm6, 8
0x1800252c9  movq    rax, xmm6
0x1800252ce  cmp     [rdi+234h], rax
0x1800252d5  jz      short loc_1800252E9
0x1800252d7  test    ecx, ecx
0x1800252d9  jz      loc_18002553A
0x1800252df  cmp     dword ptr [rsi+18h], 2
0x1800252e3  jnz     loc_18002553A
0x1800252e9  mov     eax, [rdi+21Ch]
0x1800252ef  sub     eax, 3
0x1800252f2  cmp     eax, 1
0x1800252f5  ja      short loc_180025304
0x1800252f7  cmp     [rdi+218h], r12d
0x1800252fe  jz      loc_18002553A
0x180025304  mov     rcx, [rsi+28h]; hKey
0x180025308  lea     r15, [rdi+218h]
0x18002530f  mov     [rsp+370h+cbData], 4; cbData
0x180025317  lea     rdx, c_szEnabled; "Enabled"
0x18002531e  mov     r9d, 4; dwType
0x180025324  mov     [rsp+370h+lpData], r15; lpData
0x180025329  xor     r8d, r8d; Reserved
0x18002532c  call    cs:__imp_RegSetValueExW
0x180025332  mov     ebx, eax
0x180025334  test    eax, eax
0x180025336  jnz     loc_18002553F
0x18002533c  cmp     [rsp+370h+var_33C], r12d
0x180025341  jz      short loc_180025379
0x180025343  mov     rcx, [rsi+28h]; hKey
0x180025347  lea     rax, [rdi+4FCh]
0x18002534e  mov     [rsp+370h+cbData], 4; cbData
0x180025356  lea     r9d, [rbx+4]; dwType
0x18002535a  xor     r8d, r8d; Reserved
0x18002535d  mov     [rsp+370h+lpData], rax; lpData
0x180025362  lea     rdx, c_szAutoConnectEnabled; "AutoConnectEnabled"
0x180025369  call    cs:__imp_RegSetValueExW
0x18002536f  mov     ebx, eax
0x180025371  test    eax, eax
0x180025373  jnz     loc_18002553F
0x180025379  mov     eax, [r15]
0x18002537c  mov     [rsi+1Ch], eax
0x18002537f  cmp     dword ptr [rdi+21Ch], 2
0x180025386  jnz     loc_1800254BB
0x18002538c  lea     r15, [rdi+23Ch]
0x180025393  mov     rcx, r15
0x180025396  call    ValidateQoSPolicies
0x18002539b  mov     ebx, eax
0x18002539d  test    eax, eax
0x18002539f  jnz     loc_18002553F
0x1800253a5  movups  xmm0, xmmword ptr [r15]
0x1800253a9  mov     eax, [rdi+470h]
0x1800253af  movups  xmm1, xmmword ptr [r15+0Ch]
0x1800253b4  mov     r15d, [rsp+370h+var_340]
0x1800253b9  movaps  xmmword ptr [rsp+370h+Data+8], xmm0
0x1800253be  mov     [rbp+270h+var_D0], eax
0x1800253c4  movups  xmm0, xmmword ptr [rsi+0C8h]
0x1800253cb  movups  xmmword ptr [rsp+5Ch], xmm1
0x1800253d0  movdqu  [rsp+370h+var_30C+8], xmm0
0x1800253d6  movups  xmm0, xmmword ptr [rdi+460h]
0x1800253dd  movaps  [rbp+270h+var_E0], xmm0
0x1800253e4  movups  xmmword ptr [rsi+2FCh], xmm0
0x1800253eb  mov     eax, [rdi+470h]
0x1800253f1  mov     [rsi+30Ch], eax
0x1800253f7  test    r15d, r15d
0x1800253fa  jz      loc_180025488
0x180025400  lea     r9, [rdi+25Ch]
0x180025407  mov     r8d, 7FFFFFFEh
0x18002540d  mov     edx, 101h
0x180025412  lea     rax, [rbp+270h+var_2E8]
0x180025416  mov     ecx, r8d
0x180025419  mov     r11, r9
0x18002541c  mov     r10d, edx
0x18002541f  test    rcx, rcx
0x180025422  jz      short loc_180025441
0x180025424  movzx   ebx, word ptr [r11]
0x180025428  test    bx, bx
0x18002542b  jz      short loc_180025441
0x18002542d  mov     [rax], bx
0x180025430  add     r11, 2
0x180025434  add     rax, 2
0x180025438  dec     rcx
0x18002543b  sub     r10, 1
0x18002543f  jnz     short loc_18002541F
0x180025441  lea     rcx, [rax-2]
0x180025445  test    r10, r10
0x180025448  cmovnz  rcx, rax
0x18002544c  lea     rax, [rsi+0F4h]
0x180025453  mov     [rcx], r12w
0x180025457  test    r8, r8
0x18002545a  jz      short loc_180025479
0x18002545c  movzx   ecx, word ptr [r9]
0x180025460  test    cx, cx
0x180025463  jz      short loc_180025479
0x180025465  mov     [rax], cx
0x180025468  add     r9, 2
0x18002546c  add     rax, 2
0x180025470  dec     r8
0x180025473  sub     rdx, 1
0x180025477  jnz     short loc_180025457
0x180025479  test    rdx, rdx
0x18002547c  lea     rcx, [rax-2]
0x180025480  cmovnz  rcx, rax
0x180025484  mov     [rcx], r12w
0x180025488  mov     eax, [rdi+258h]
0x18002548e  lea     r9, [rsp+370h+Data+8]
0x180025493  mov     rcx, [rsi+28h]; hKey
0x180025497  mov     r8d, r15d
0x18002549a  mov     [rsi+2F8h], eax
0x1800254a0  mov     edx, [rdi+21Ch]
0x1800254a6  mov     [rbp+270h+var_E4], eax
0x1800254ac  call    WriteInterfaceExtraInfo
0x1800254b1  mov     ebx, eax
0x1800254b3  test    eax, eax
0x1800254b5  jnz     loc_18002553F
0x1800254bb  cmp     [rsp+370h+var_33C], r12d
0x1800254c0  jz      short loc_18002550E
0x1800254c2  lea     rcx, [rdi+478h]
0x1800254c9  lea     r8, [rsp+370h+var_338]
0x1800254ce  lea     rdx, [rsp+370h+var_330]
0x1800254d3  call    ConvertPbkToRegistryEntry
0x1800254d8  mov     r14, [rsp+370h+var_330]
0x1800254dd  mov     ebx, eax
0x1800254df  test    eax, eax
0x1800254e1  jnz     short loc_18002553F
0x1800254e3  mov     eax, [rsp+370h+var_338]
0x1800254e7  lea     r9d, [rbx+3]; dwType
0x1800254eb  mov     rcx, [rsi+28h]; hKey
0x1800254ef  lea     rdx, c_szInterfaceInfoPbk; "InterfaceInfoPbk"
0x1800254f6  mov     [rsp+370h+cbData], eax; cbData
0x1800254fa  xor     r8d, r8d; Reserved
0x1800254fd  mov     [rsp+370h+lpData], r14; lpData
0x180025502  call    cs:__imp_RegSetValueExW
0x180025508  mov     ebx, eax
0x18002550a  test    eax, eax
0x18002550c  jnz     short loc_18002553F
0x18002550e  mov     rcx, [rsi+28h]; hKey
0x180025512  lea     rax, [rsp+370h+Data]
0x180025517  mov     [rsp+370h+cbData], 8; cbData
0x18002551f  mov     r9d, 0Bh; dwType
0x180025525  xor     r8d, r8d; Reserved
0x180025528  mov     [rsp+370h+lpData], rax; lpData
0x18002552d  xor     edx, edx; lpValueName
0x18002552f  call    cs:__imp_RegSetValueExW
0x180025535  mov     ebx, r12d
0x180025538  jmp     short loc_18002553F
0x18002553a  mov     ebx, 57h ; 'W'
0x18002553f  lea     rcx, CfgLock; lpCriticalSection
0x180025546  call    cs:__imp_LeaveCriticalSection
0x18002554c  test    r14, r14
0x18002554f  jz      short loc_18002555A
0x180025551  mov     rcx, r14; Block
0x180025554  call    cs:__imp_free
0x18002555a  mov     eax, ebx
0x18002555c  jmp     short loc_18002556A
0x18002555e  mov     eax, 32h ; '2'
0x180025563  jmp     short loc_18002556A
0x180025565  mov     eax, 57h ; 'W'
0x18002556a  mov     rcx, [rbp+270h+var_50]
0x180025571  xor     rcx, rsp; StackCookie
0x180025574  call    __security_check_cookie
0x180025579  movaps  xmm6, [rsp+370h+var_48+8]
0x180025581  add     rsp, 340h
0x180025588  pop     r15
0x18002558a  pop     r14
0x18002558c  pop     r12
0x18002558e  pop     rdi
0x18002558f  pop     rsi
0x180025590  pop     rbx
0x180025591  pop     rbp
0x180025592  retn
```
