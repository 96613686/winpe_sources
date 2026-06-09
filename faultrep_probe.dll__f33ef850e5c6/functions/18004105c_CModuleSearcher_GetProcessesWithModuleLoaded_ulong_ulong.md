# CModuleSearcher::GetProcessesWithModuleLoaded(ulong *,ulong *)

- ea: `0x18004105c`
- end: `0x18004143f`
- name: `?GetProcessesWithModuleLoaded@CModuleSearcher@@QEAAJPEAK0@Z`
- size: `995`
- prototype: `__int64 __fastcall(CModuleSearcher *__hidden this, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008030`

## callees

- `0x180002890`
- `0x180003474`
- `0x18000758c`
- `0x18000760c`
- `0x180009f00`
- `0x18003e5a8`
- `0x18004105c`
- `0x180041448`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x180041347`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x180041347`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x180041341`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x180041341`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180041339`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180041339`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800412a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800412a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800412a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800412b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800412bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004138f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800413d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800412a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800412b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800412bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004138f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800413d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041384`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041384`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x180041265`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x180041265`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x1800410b4`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x1800410b4`
- `api-ms-win-core-toolhelp-l1-1-0!Process32FirstW` at `0x18004119f`
- `api-ms-win-core-toolhelp-l1-1-0!Process32FirstW` at `0x18004119f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CModuleSearcher::GetProcessesWithModuleLoaded(
        CModuleSearcher *this,
        unsigned int *a2,
        unsigned int *a3)
{
  __int64 v6; // r15
  __int64 v7; // rdi
  PROCESSENTRY32W *p_pe; // rcx
  _OWORD *v9; // rax
  __int64 v10; // rdx
  CModuleSearcher *v11; // rcx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r8
  DWORD th32ProcessID; // r9d
  signed int v16; // eax
  __int64 v17; // rdx
  DWORD TickCount; // eax
  unsigned int v19; // ebx
  signed int v20; // eax
  signed int LastError; // eax
  unsigned int v22; // [rsp+30h] [rbp-D0h]
  HANDLE hSnapshot; // [rsp+38h] [rbp-C8h]
  _BYTE v25[576]; // [rsp+50h] [rbp-B0h] BYREF
  PROCESSENTRY32W pe; // [rsp+290h] [rbp+190h] BYREF
  _DWORD v27[32]; // [rsp+4D0h] [rbp+3D0h]

  *(_OWORD *)a2 = 0;
  *a3 = 0;
  if ( !*(_DWORD *)this )
    return 2147500037LL;
  hSnapshot = CreateToolhelp32Snapshot(2u, 0);
  if ( (unsigned __int64)hSnapshot + 1 <= 1 )
  {
    LastError = GetLastError();
    v19 = LastError;
    if ( LastError > 0 )
      v19 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_828388e69e2438d8439679a7cdeb6348_Traceguids, v19);
    return v19;
  }
  if ( *(_DWORD *)this > 4u )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v6 = 0;
  v22 = 0;
  if ( !*(_DWORD *)this )
    goto LABEL_44;
LABEL_7:
  if ( *a3 >= 4 )
    goto LABEL_44;
  v7 = 0;
  memset_0(v25, 0, 0x238u);
  p_pe = &pe;
  v9 = v25;
  v10 = 4;
  do
  {
    *(_OWORD *)&p_pe->dwSize = *v9;
    *(_OWORD *)&p_pe->th32DefaultHeapID = v9[1];
    *(_OWORD *)&p_pe->th32ParentProcessID = v9[2];
    *(_OWORD *)&p_pe->szExeFile[2] = v9[3];
    *(_OWORD *)&p_pe->szExeFile[10] = v9[4];
    *(_OWORD *)&p_pe->szExeFile[18] = v9[5];
    *(_OWORD *)&p_pe->szExeFile[26] = v9[6];
    *(_OWORD *)&p_pe->szExeFile[34] = v9[7];
    p_pe = (PROCESSENTRY32W *)((char *)p_pe + 128);
    v9 += 8;
    --v10;
  }
  while ( v10 );
  *(_OWORD *)&p_pe->dwSize = *v9;
  *(_OWORD *)&p_pe->th32DefaultHeapID = v9[1];
  *(_OWORD *)&p_pe->th32ParentProcessID = v9[2];
  *(_QWORD *)&p_pe->szExeFile[2] = *((_QWORD *)v9 + 6);
  pe.dwSize = 568;
  if ( Process32FirstW(hSnapshot, &pe) )
  {
    while ( 1 )
    {
      if ( pe.th32ProcessID
        && CModuleSearcher::ProcessHasModuleLoaded(v11, pe.th32ProcessID, *((const wchar_t **)this + v6 + 1))
        && (unsigned int)v7 < 0x20 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_dS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            (unsigned int)&WPP_828388e69e2438d8439679a7cdeb6348_Traceguids,
            pe.th32ProcessID,
            *((_QWORD *)this + v6 + 1));
          v12 = WPP_GLOBAL_Control;
        }
        v13 = 0;
        v14 = *((unsigned int *)this + 24);
        th32ProcessID = pe.th32ProcessID;
        if ( (_DWORD)v14 )
        {
          while ( pe.th32ProcessID != *((_DWORD *)this + v13 + 14) )
          {
            v13 = (unsigned int)(v13 + 1);
            if ( (unsigned int)v13 >= (unsigned int)v14 )
              goto LABEL_20;
          }
        }
        else
        {
LABEL_20:
          v27[v7] = pe.th32ProcessID;
          if ( (unsigned int)v14 < 0xA )
          {
            *((_DWORD *)this + v14 + 14) = th32ProcessID;
            ++*((_DWORD *)this + 24);
            v12 = WPP_GLOBAL_Control;
          }
          v7 = (unsigned int)(v7 + 1);
          if ( (_DWORD)v7 == 32 )
          {
            if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 )
              WPP_SF_S(v12[2], 23, &WPP_828388e69e2438d8439679a7cdeb6348_Traceguids, *((_QWORD *)this + v6 + 1));
            SetLastError(0);
LABEL_29:
            if ( GetLastError() == 18 || !GetLastError() )
            {
              if ( (_DWORD)v7 )
              {
                if ( (*((_BYTE *)this + 4 * v22 + 40) & 1) != 0 )
                {
                  v17 = 0;
                  do
                  {
                    if ( *a3 >= 4 )
                      break;
                    a2[*a3] = v27[v17];
                    v17 = (unsigned int)(v17 + 1);
                    ++*a3;
                  }
                  while ( (unsigned int)v17 < (unsigned int)v7 );
                }
                else
                {
                  TickCount = GetTickCount();
                  _o_srand(TickCount);
                  a2[(*a3)++] = v27[rand() % (unsigned int)v7];
                }
              }
            }
            else
            {
              v16 = GetLastError();
              if ( v16 > 0 )
                v16 = (unsigned __int16)v16 | 0x80070000;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  24,
                  &WPP_828388e69e2438d8439679a7cdeb6348_Traceguids,
                  (unsigned int)v16);
              }
            }
            v6 = ++v22;
            if ( v22 >= *(_DWORD *)this )
            {
LABEL_44:
              v19 = 0;
              goto LABEL_45;
            }
            goto LABEL_7;
          }
        }
      }
      if ( !Process32NextW(hSnapshot, &pe) )
        goto LABEL_29;
      v6 = v22;
    }
  }
  v20 = GetLastError();
  v19 = v20;
  if ( v20 > 0 )
    v19 = (unsigned __int16)v20 | 0x80070000;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_828388e69e2438d8439679a7cdeb6348_Traceguids, v19);
LABEL_45:
  CloseHandle(hSnapshot);
  return v19;
}

```

## disassembly

```asm
0x18004105c  mov     [rsp-8+arg_18], rbx
0x180041061  push    rbp
0x180041062  push    rsi
0x180041063  push    rdi
0x180041064  push    r12
0x180041066  push    r15
0x180041068  lea     rbp, [rsp-460h]
0x180041070  sub     rsp, 560h
0x180041077  mov     rax, cs:__security_cookie
0x18004107e  xor     rax, rsp
0x180041081  mov     [rbp+480h+var_30], rax
0x180041088  mov     r12, r8
0x18004108b  mov     [rsp+580h+var_540], rdx
0x180041090  mov     rbx, rcx
0x180041093  xorps   xmm0, xmm0
0x180041096  movups  xmmword ptr [rdx], xmm0
0x180041099  mov     dword ptr [r8], 0
0x1800410a0  cmp     dword ptr [rcx], 0
0x1800410a3  jnz     short loc_1800410AF
0x1800410a5  mov     eax, 80004005h
0x1800410aa  jmp     loc_180041419
0x1800410af  xor     edx, edx; th32ProcessID
0x1800410b1  lea     ecx, [rdx+2]; dwFlags
0x1800410b4  call    cs:__imp_CreateToolhelp32Snapshot
0x1800410ba  mov     [rsp+580h+hSnapshot], rax
0x1800410bf  lea     rcx, [rax+1]
0x1800410c3  cmp     rcx, 1
0x1800410c7  jbe     loc_1800413D0
0x1800410cd  cmp     dword ptr [rbx], 4
0x1800410d0  jbe     short loc_1800410D7
0x1800410d2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800410d7  xor     r15d, r15d
0x1800410da  mov     [rsp+580h+var_550], r15d
0x1800410df  cmp     [rbx], r15d
0x1800410e2  jbe     loc_18004137D
0x1800410e8  lea     rsi, WPP_GLOBAL_Control
0x1800410ef  cmp     dword ptr [r12], 4
0x1800410f4  jnb     loc_18004137D
0x1800410fa  xor     edi, edi
0x1800410fc  xor     edx, edx; Val
0x1800410fe  mov     r8d, 238h; Size
0x180041104  lea     rcx, [rsp+580h+var_530]; void *
0x180041109  call    memset_0
0x18004110e  lea     rcx, [rbp+480h+pe]
0x180041115  lea     rax, [rsp+580h+var_530]
0x18004111a  lea     edx, [rdi+4]
0x18004111d  lea     r8d, [rdx+7Ch]
0x180041121  movups  xmm0, xmmword ptr [rax]
0x180041124  movups  xmmword ptr [rcx], xmm0
0x180041127  movups  xmm1, xmmword ptr [rax+10h]
0x18004112b  movups  xmmword ptr [rcx+10h], xmm1
0x18004112f  movups  xmm0, xmmword ptr [rax+20h]
0x180041133  movups  xmmword ptr [rcx+20h], xmm0
0x180041137  movups  xmm1, xmmword ptr [rax+30h]
0x18004113b  movups  xmmword ptr [rcx+30h], xmm1
0x18004113f  movups  xmm0, xmmword ptr [rax+40h]
0x180041143  movups  xmmword ptr [rcx+40h], xmm0
0x180041147  movups  xmm1, xmmword ptr [rax+50h]
0x18004114b  movups  xmmword ptr [rcx+50h], xmm1
0x18004114f  movups  xmm0, xmmword ptr [rax+60h]
0x180041153  movups  xmmword ptr [rcx+60h], xmm0
0x180041157  movups  xmm1, xmmword ptr [rax+70h]
0x18004115b  movups  xmmword ptr [rcx+70h], xmm1
0x18004115f  add     rcx, r8
0x180041162  add     rax, r8
0x180041165  sub     rdx, 1
0x180041169  jnz     short loc_180041121
0x18004116b  movups  xmm0, xmmword ptr [rax]
0x18004116e  movups  xmmword ptr [rcx], xmm0
0x180041171  movups  xmm1, xmmword ptr [rax+10h]
0x180041175  movups  xmmword ptr [rcx+10h], xmm1
0x180041179  movups  xmm0, xmmword ptr [rax+20h]
0x18004117d  movups  xmmword ptr [rcx+20h], xmm0
0x180041181  mov     rax, [rax+30h]
0x180041185  mov     [rcx+30h], rax
0x180041189  mov     [rbp+480h+pe.dwSize], 238h
0x180041193  lea     rdx, [rbp+480h+pe]; lppe
0x18004119a  mov     rcx, [rsp+580h+hSnapshot]; hSnapshot
0x18004119f  call    cs:__imp_Process32FirstW
0x1800411a5  test    eax, eax
0x1800411a7  jz      loc_18004138F
0x1800411ad  mov     edx, [rbp+480h+pe.th32ProcessID]; unsigned int
0x1800411b3  test    edx, edx
0x1800411b5  jz      loc_180041259
0x1800411bb  mov     r8, [rbx+r15*8+8]; wchar_t *
0x1800411c0  call    ?ProcessHasModuleLoaded@CModuleSearcher@@AEAAHKPEB_W@Z; CModuleSearcher::ProcessHasModuleLoaded(ulong,wchar_t const *)
0x1800411c5  test    eax, eax
0x1800411c7  jz      loc_180041259
0x1800411cd  cmp     edi, 20h ; ' '
0x1800411d0  jnb     loc_180041259
0x1800411d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800411dd  cmp     rcx, rsi
0x1800411e0  jz      short loc_180041215
0x1800411e2  test    byte ptr [rcx+1Ch], 8
0x1800411e6  jz      short loc_180041215
0x1800411e8  mov     edx, 16h
0x1800411ed  mov     rax, [rbx+r15*8+8]
0x1800411f2  mov     [rsp+580h+var_560], rax
0x1800411f7  mov     r9d, [rbp+480h+pe.th32ProcessID]
0x1800411fe  lea     r8, WPP_828388e69e2438d8439679a7cdeb6348_Traceguids
0x180041205  mov     rcx, [rcx+10h]
0x180041209  call    WPP_SF_dS
0x18004120e  mov     rcx, cs:WPP_GLOBAL_Control
0x180041215  xor     edx, edx
0x180041217  mov     r8d, [rbx+60h]
0x18004121b  mov     r9d, [rbp+480h+pe.th32ProcessID]
0x180041222  test    r8d, r8d
0x180041225  jz      short loc_180041235
0x180041227  cmp     r9d, [rbx+rdx*4+38h]
0x18004122c  jz      short loc_180041259
0x18004122e  inc     edx
0x180041230  cmp     edx, r8d
0x180041233  jb      short loc_180041227
0x180041235  mov     [rbp+rdi*4+480h+var_B0], r9d
0x18004123d  cmp     r8d, 0Ah
0x180041241  jnb     short loc_180041252
0x180041243  mov     [rbx+r8*4+38h], r9d
0x180041248  inc     dword ptr [rbx+60h]
0x18004124b  mov     rcx, cs:WPP_GLOBAL_Control
0x180041252  inc     edi
0x180041254  cmp     edi, 20h ; ' '
0x180041257  jz      short loc_180041279
0x180041259  lea     rdx, [rbp+480h+pe]; lppe
0x180041260  mov     rcx, [rsp+580h+hSnapshot]; hSnapshot
0x180041265  call    cs:__imp_Process32NextW
0x18004126b  test    eax, eax
0x18004126d  jz      short loc_1800412A6
0x18004126f  mov     r15d, [rsp+580h+var_550]
0x180041274  jmp     loc_1800411AD
0x180041279  cmp     rcx, rsi
0x18004127c  jz      short loc_18004129E
0x18004127e  test    byte ptr [rcx+1Ch], 2
0x180041282  jz      short loc_18004129E
0x180041284  mov     edx, 17h
0x180041289  mov     r9, [rbx+r15*8+8]
0x18004128e  lea     r8, WPP_828388e69e2438d8439679a7cdeb6348_Traceguids
0x180041295  mov     rcx, [rcx+10h]
0x180041299  call    WPP_SF_S
0x18004129e  xor     ecx, ecx; dwErrCode
0x1800412a0  call    cs:__imp_SetLastError
0x1800412a6  call    cs:__imp_GetLastError
0x1800412ac  cmp     eax, 12h
0x1800412af  jz      short loc_180041301
0x1800412b1  call    cs:__imp_GetLastError
0x1800412b7  test    eax, eax
0x1800412b9  jz      short loc_180041301
0x1800412bb  call    cs:__imp_GetLastError
0x1800412c1  test    eax, eax
0x1800412c3  jle     short loc_1800412CD
0x1800412c5  movzx   eax, ax
0x1800412c8  or      eax, 80070000h
0x1800412cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800412d4  cmp     rcx, rsi
0x1800412d7  jz      loc_180041368
0x1800412dd  test    byte ptr [rcx+1Ch], 1
0x1800412e1  jz      loc_180041368
0x1800412e7  mov     edx, 18h
0x1800412ec  mov     r9d, eax
0x1800412ef  lea     r8, WPP_828388e69e2438d8439679a7cdeb6348_Traceguids
0x1800412f6  mov     rcx, [rcx+10h]
0x1800412fa  call    WPP_SF_d
0x1800412ff  jmp     short loc_180041368
0x180041301  test    edi, edi
0x180041303  jz      short loc_180041368
0x180041305  mov     eax, [rsp+580h+var_550]
0x180041309  test    byte ptr [rbx+rax*4+28h], 1
0x18004130e  jz      short loc_180041339
0x180041310  xor     edx, edx
0x180041312  mov     r8, [rsp+580h+var_540]
0x180041317  cmp     dword ptr [r12], 4
0x18004131c  jnb     short loc_180041368
0x18004131e  mov     ecx, [r12]
0x180041322  mov     eax, [rbp+rdx*4+480h+var_B0]
0x180041329  mov     [r8+rcx*4], eax
0x18004132d  inc     edx
0x18004132f  inc     dword ptr [r12]
0x180041333  cmp     edx, edi
0x180041335  jb      short loc_180041317
0x180041337  jmp     short loc_180041368
0x180041339  call    cs:__imp_GetTickCount
0x18004133f  mov     ecx, eax
0x180041341  call    cs:__imp__o_srand
0x180041347  call    cs:__imp_rand
0x18004134d  xor     edx, edx
0x18004134f  div     edi
0x180041351  mov     edx, [rbp+rdx*4+480h+var_B0]
0x180041358  mov     eax, [r12]
0x18004135c  mov     rcx, [rsp+580h+var_540]
0x180041361  mov     [rcx+rax*4], edx
0x180041364  inc     dword ptr [r12]
0x180041368  mov     eax, [rsp+580h+var_550]
0x18004136c  inc     eax
0x18004136e  mov     [rsp+580h+var_550], eax
0x180041372  cmp     eax, [rbx]
0x180041374  mov     r15d, eax
0x180041377  jb      loc_1800410EF
0x18004137d  xor     ebx, ebx
0x18004137f  mov     rcx, [rsp+580h+hSnapshot]; hObject
0x180041384  call    cs:__imp_CloseHandle
0x18004138a  jmp     loc_180041417
0x18004138f  call    cs:__imp_GetLastError
0x180041395  mov     ebx, eax
0x180041397  test    eax, eax
0x180041399  jle     short loc_1800413A4
0x18004139b  movzx   ebx, ax
0x18004139e  or      ebx, 80070000h
0x1800413a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800413ab  cmp     rcx, rsi
0x1800413ae  jz      short loc_18004137F
0x1800413b0  test    byte ptr [rcx+1Ch], 1
0x1800413b4  jz      short loc_18004137F
0x1800413b6  mov     edx, 15h
0x1800413bb  mov     r9d, ebx
0x1800413be  lea     r8, WPP_828388e69e2438d8439679a7cdeb6348_Traceguids
0x1800413c5  mov     rcx, [rcx+10h]
0x1800413c9  call    WPP_SF_d
0x1800413ce  jmp     short loc_18004137F
0x1800413d0  call    cs:__imp_GetLastError
0x1800413d6  mov     ebx, eax
0x1800413d8  test    eax, eax
0x1800413da  jle     short loc_1800413E5
0x1800413dc  movzx   ebx, ax
0x1800413df  or      ebx, 80070000h
0x1800413e5  lea     rsi, WPP_GLOBAL_Control
0x1800413ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800413f3  cmp     rcx, rsi
0x1800413f6  jz      short loc_180041417
0x1800413f8  test    byte ptr [rcx+1Ch], 1
0x1800413fc  jz      short loc_180041417
0x1800413fe  mov     edx, 14h
0x180041403  mov     r9d, ebx
0x180041406  lea     r8, WPP_828388e69e2438d8439679a7cdeb6348_Traceguids
0x18004140d  mov     rcx, [rcx+10h]
0x180041411  call    WPP_SF_d
0x180041416  nop
0x180041417  mov     eax, ebx
0x180041419  mov     rcx, [rbp+480h+var_30]
0x180041420  xor     rcx, rsp; StackCookie
0x180041423  call    __security_check_cookie
0x180041428  mov     rbx, [rsp+580h+arg_18]
0x180041430  add     rsp, 560h
0x180041437  pop     r15
0x180041439  pop     r12
0x18004143b  pop     rdi
0x18004143c  pop     rsi
0x18004143d  pop     rbp
0x18004143e  retn
```
