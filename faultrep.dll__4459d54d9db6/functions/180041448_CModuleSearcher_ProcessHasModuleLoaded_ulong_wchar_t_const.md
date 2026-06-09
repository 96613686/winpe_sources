# CModuleSearcher::ProcessHasModuleLoaded(ulong,wchar_t const *)

- ea: `0x180041448`
- end: `0x18004181b`
- name: `?ProcessHasModuleLoaded@CModuleSearcher@@AEAAHKPEB_W@Z`
- size: `979`
- prototype: `__int64 __fastcall(CModuleSearcher *this, DWORD, const wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004105c`

## callees

- `0x180002890`
- `0x180003474`
- `0x180009f00`
- `0x180009f8c`
- `0x180041448`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800415ac`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004177f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800415ac`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004177f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800414e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041554`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041632`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041724`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800414e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041554`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041632`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041724`
- `ntdll!wcsrchr` at `0x180041570`
- `ntdll!wcsrchr` at `0x180041570`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800417df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800417e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800417df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800417e8`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18004152a`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18004152a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800414b3`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800414b3`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x1800415ff`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x1800415ff`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x180041794`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x180041794`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x1800416f9`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x1800416f9`

## pseudocode

```c
__int64 __fastcall CModuleSearcher::ProcessHasModuleLoaded(CModuleSearcher *this, DWORD a2, const wchar_t *a3)
{
  unsigned int v5; // r15d
  __int64 v6; // rdi
  HANDLE v7; // r13
  DWORD v8; // eax
  DWORD v9; // eax
  __int64 v10; // rdx
  wchar_t *v11; // rax
  WCHAR *szExePath; // rax
  __int64 v13; // r9
  __int64 v14; // rsi
  char *Toolhelp32Snapshot; // rbx
  MODULEENTRY32W *p_me; // rcx
  _OWORD *v17; // rax
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int64 v27; // rax
  DWORD LastError; // eax
  __int64 v29; // r9
  DWORD dwSize[4]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v32[1088]; // [rsp+40h] [rbp-C0h] BYREF
  MODULEENTRY32W me; // [rsp+480h] [rbp+380h] BYREF

  v5 = 0;
  memset_0(&me, 0, sizeof(me));
  v6 = -1;
  dwSize[0] = 0;
  do
    ++v6;
  while ( a3[v6] );
  v7 = OpenProcess(0x1000u, 0, a2);
  if ( (unsigned __int64)v7 + 1 > 1 )
  {
    dwSize[0] = 260;
    if ( QueryFullProcessImageNameW(v7, 1u, me.szExePath, dwSize) )
    {
      v11 = wcsrchr(me.szExePath, 0x5Cu);
      if ( v11 )
        szExePath = v11 + 1;
      else
        szExePath = me.szExePath;
      v13 = -1;
      do
        ++v13;
      while ( szExePath[v13] );
      if ( v6 == v13 && (!v6 || CompareStringOrdinal(a3, v6, szExePath, v13, 1) == 2) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            16,
            (unsigned int)WPP_828388e69e2438d8439679a7cdeb6348_Traceguids,
            (_DWORD)a3,
            a2);
        v5 = 1;
        goto LABEL_46;
      }
      v14 = 8;
      Toolhelp32Snapshot = (char *)CreateToolhelp32Snapshot(8u, a2);
      if ( Toolhelp32Snapshot != (char *)-1LL && Toolhelp32Snapshot + 1 != (char *)1 )
      {
        memset_0(v32, 0, 0x438u);
        p_me = &me;
        v17 = v32;
        do
        {
          v18 = v17[1];
          *(_OWORD *)&p_me->dwSize = *v17;
          v19 = v17[2];
          *(_OWORD *)&p_me->ProccntUsage = v18;
          v20 = v17[3];
          *(_OWORD *)&p_me->modBaseSize = v19;
          v21 = v17[4];
          *(_OWORD *)p_me->szModule = v20;
          v22 = v17[5];
          *(_OWORD *)&p_me->szModule[8] = v21;
          v23 = v17[6];
          *(_OWORD *)&p_me->szModule[16] = v22;
          v24 = v17[7];
          v17 += 8;
          *(_OWORD *)&p_me->szModule[24] = v23;
          *(_OWORD *)&p_me->szModule[32] = v24;
          p_me = (MODULEENTRY32W *)((char *)p_me + 128);
          --v14;
        }
        while ( v14 );
        v25 = v17[1];
        *(_OWORD *)&p_me->dwSize = *v17;
        v26 = v17[2];
        v27 = *((_QWORD *)v17 + 6);
        *(_OWORD *)&p_me->ProccntUsage = v25;
        *(_OWORD *)&p_me->modBaseSize = v26;
        *(_QWORD *)p_me->szModule = v27;
        me.dwSize = 1080;
        if ( Module32FirstW(Toolhelp32Snapshot, &me) )
        {
          while ( 1 )
          {
            v29 = -1;
            do
              ++v29;
            while ( me.szModule[v29] );
            if ( v6 == v29 && (!v6 || CompareStringOrdinal(a3, v6, me.szModule, v29, 1) == 2) )
              break;
            if ( !Module32NextW(Toolhelp32Snapshot, &me) )
              goto LABEL_45;
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              19,
              (unsigned int)WPP_828388e69e2438d8439679a7cdeb6348_Traceguids,
              (_DWORD)a3,
              a2);
          v5 = 1;
        }
        else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          LastError = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_828388e69e2438d8439679a7cdeb6348_Traceguids, LastError);
        }
LABEL_45:
        CloseHandle(Toolhelp32Snapshot);
        goto LABEL_46;
      }
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_46:
        CloseHandle(v7);
        return v5;
      }
      v9 = GetLastError();
      v10 = 17;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_46;
      v9 = GetLastError();
      v10 = 15;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, WPP_828388e69e2438d8439679a7cdeb6348_Traceguids, v9);
    goto LABEL_46;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v8 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_828388e69e2438d8439679a7cdeb6348_Traceguids, v8);
  }
  return v5;
}

```

## disassembly

```asm
0x180041448  mov     [rsp-8+arg_0], rbx
0x18004144d  push    rbp
0x18004144e  push    rsi
0x18004144f  push    rdi
0x180041450  push    r12
0x180041452  push    r13
0x180041454  push    r14
0x180041456  push    r15
0x180041458  lea     rbp, [rsp-7D0h]
0x180041460  sub     rsp, 8D0h
0x180041467  mov     rax, cs:__security_cookie
0x18004146e  xor     rax, rsp
0x180041471  mov     [rbp+800h+var_40], rax
0x180041478  mov     r14, r8
0x18004147b  lea     rcx, [rbp+800h+me]; void *
0x180041482  mov     r12d, edx
0x180041485  xor     esi, esi
0x180041487  xor     edx, edx; Val
0x180041489  mov     r8d, 438h; Size
0x18004148f  mov     r15d, esi
0x180041492  call    memset_0
0x180041497  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004149b  mov     [rsp+900h+dwSize], esi
0x18004149f  inc     rdi
0x1800414a2  cmp     [r14+rdi*2], si
0x1800414a7  jnz     short loc_18004149F
0x1800414a9  mov     r8d, r12d; dwProcessId
0x1800414ac  xor     edx, edx; bInheritHandle
0x1800414ae  mov     ecx, 1000h; dwDesiredAccess
0x1800414b3  call    cs:__imp_OpenProcess
0x1800414b9  mov     r13, rax
0x1800414bc  mov     ebx, 1
0x1800414c1  inc     rax
0x1800414c4  cmp     rax, rbx
0x1800414c7  ja      short loc_180041511
0x1800414c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800414d0  lea     rax, WPP_GLOBAL_Control
0x1800414d7  cmp     rcx, rax
0x1800414da  jz      loc_1800417EE
0x1800414e0  test    [rcx+1Ch], bl
0x1800414e3  jz      loc_1800417EE
0x1800414e9  call    cs:__imp_GetLastError
0x1800414ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800414f6  lea     edx, [rbx+0Dh]
0x1800414f9  mov     r9d, eax
0x1800414fc  lea     r8, WPP_828388e69e2438d8439679a7cdeb6348_Traceguids
0x180041503  mov     rcx, [rcx+10h]
0x180041507  call    WPP_SF_d
0x18004150c  jmp     loc_1800417EE
0x180041511  lea     r9, [rsp+900h+dwSize]; lpdwSize
0x180041516  mov     [rsp+900h+dwSize], 104h
0x18004151e  lea     r8, [rbp+800h+me.szExePath]; lpExeName
0x180041525  mov     edx, ebx; dwFlags
0x180041527  mov     rcx, r13; hProcess
0x18004152a  call    cs:__imp_QueryFullProcessImageNameW
0x180041530  test    eax, eax
0x180041532  jnz     short loc_180041564
0x180041534  mov     rcx, cs:WPP_GLOBAL_Control
0x18004153b  lea     rax, WPP_GLOBAL_Control
0x180041542  cmp     rcx, rax
0x180041545  jz      loc_1800417E5
0x18004154b  test    [rcx+1Ch], bl
0x18004154e  jz      loc_1800417E5
0x180041554  call    cs:__imp_GetLastError
0x18004155a  mov     edx, 0Fh
0x18004155f  jmp     loc_18004163B
0x180041564  mov     edx, 5Ch ; '\'; Ch
0x180041569  lea     rcx, [rbp+800h+me.szExePath]; Str
0x180041570  call    cs:__imp_wcsrchr
0x180041576  test    rax, rax
0x180041579  jz      short loc_180041581
0x18004157b  add     rax, 2
0x18004157f  jmp     short loc_180041588
0x180041581  lea     rax, [rbp+800h+me.szExePath]
0x180041588  or      r9, 0FFFFFFFFFFFFFFFFh
0x18004158c  inc     r9; cchCount2
0x18004158f  cmp     [rax+r9*2], si
0x180041594  jnz     short loc_18004158C
0x180041596  cmp     rdi, r9
0x180041599  jnz     short loc_1800415F5
0x18004159b  test    rdi, rdi
0x18004159e  jz      short loc_1800415B7
0x1800415a0  mov     r8, rax; lpString2
0x1800415a3  mov     [rsp+900h+bIgnoreCase], ebx; bIgnoreCase
0x1800415a7  mov     edx, edi; cchCount1
0x1800415a9  mov     rcx, r14; lpString1
0x1800415ac  call    cs:__imp_CompareStringOrdinal
0x1800415b2  cmp     eax, 2
0x1800415b5  jnz     short loc_1800415F5
0x1800415b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800415be  lea     rax, WPP_GLOBAL_Control
0x1800415c5  cmp     rcx, rax
0x1800415c8  jz      short loc_1800415ED
0x1800415ca  test    byte ptr [rcx+1Ch], 4
0x1800415ce  jz      short loc_1800415ED
0x1800415d0  mov     rcx, [rcx+10h]
0x1800415d4  lea     r8, WPP_828388e69e2438d8439679a7cdeb6348_Traceguids
0x1800415db  mov     edx, 10h
0x1800415e0  mov     [rsp+900h+bIgnoreCase], r12d
0x1800415e5  mov     r9, r14
0x1800415e8  call    WPP_SF_Sd
0x1800415ed  mov     r15d, ebx
0x1800415f0  jmp     loc_1800417E5
0x1800415f5  mov     esi, 8
0x1800415fa  mov     edx, r12d; th32ProcessID
0x1800415fd  mov     ecx, esi; dwFlags
0x1800415ff  call    cs:__imp_CreateToolhelp32Snapshot
0x180041605  mov     rbx, rax
0x180041608  inc     rax
0x18004160b  cmp     rax, 1
0x18004160f  ja      short loc_18004165A
0x180041611  mov     rcx, cs:WPP_GLOBAL_Control
0x180041618  lea     rax, WPP_GLOBAL_Control
0x18004161f  cmp     rcx, rax
0x180041622  jz      loc_1800417E5
0x180041628  test    byte ptr [rcx+1Ch], 1
0x18004162c  jz      loc_1800417E5
0x180041632  call    cs:__imp_GetLastError
0x180041638  lea     edx, [rsi+9]
0x18004163b  mov     rcx, cs:WPP_GLOBAL_Control
0x180041642  lea     r8, WPP_828388e69e2438d8439679a7cdeb6348_Traceguids
0x180041649  mov     r9d, eax
0x18004164c  mov     rcx, [rcx+10h]
0x180041650  call    WPP_SF_d
0x180041655  jmp     loc_1800417E5
0x18004165a  xor     edx, edx; Val
0x18004165c  lea     rcx, [rsp+900h+var_8C0]; void *
0x180041661  mov     r8d, 438h; Size
0x180041667  call    memset_0
0x18004166c  lea     rcx, [rbp+800h+me]
0x180041673  mov     edx, 80h
0x180041678  lea     rax, [rsp+900h+var_8C0]
0x18004167d  movups  xmm0, xmmword ptr [rax]
0x180041680  movups  xmm1, xmmword ptr [rax+10h]
0x180041684  movups  xmmword ptr [rcx], xmm0
0x180041687  movups  xmm0, xmmword ptr [rax+20h]
0x18004168b  movups  xmmword ptr [rcx+10h], xmm1
0x18004168f  movups  xmm1, xmmword ptr [rax+30h]
0x180041693  movups  xmmword ptr [rcx+20h], xmm0
0x180041697  movups  xmm0, xmmword ptr [rax+40h]
0x18004169b  movups  xmmword ptr [rcx+30h], xmm1
0x18004169f  movups  xmm1, xmmword ptr [rax+50h]
0x1800416a3  movups  xmmword ptr [rcx+40h], xmm0
0x1800416a7  movups  xmm0, xmmword ptr [rax+60h]
0x1800416ab  movups  xmmword ptr [rcx+50h], xmm1
0x1800416af  movups  xmm1, xmmword ptr [rax+70h]
0x1800416b3  add     rax, rdx
0x1800416b6  movups  xmmword ptr [rcx+60h], xmm0
0x1800416ba  movups  xmmword ptr [rcx+70h], xmm1
0x1800416be  add     rcx, rdx
0x1800416c1  sub     rsi, 1
0x1800416c5  jnz     short loc_18004167D
0x1800416c7  movups  xmm0, xmmword ptr [rax]
0x1800416ca  lea     rdx, [rbp+800h+me]; lpme
0x1800416d1  movups  xmm1, xmmword ptr [rax+10h]
0x1800416d5  movups  xmmword ptr [rcx], xmm0
0x1800416d8  movups  xmm0, xmmword ptr [rax+20h]
0x1800416dc  mov     rax, [rax+30h]
0x1800416e0  movups  xmmword ptr [rcx+10h], xmm1
0x1800416e4  movups  xmmword ptr [rcx+20h], xmm0
0x1800416e8  mov     [rcx+30h], rax
0x1800416ec  mov     rcx, rbx; hSnapshot
0x1800416ef  mov     [rbp+800h+me.dwSize], 438h
0x1800416f9  call    cs:__imp_Module32FirstW
0x1800416ff  test    eax, eax
0x180041701  jnz     short loc_18004174C
0x180041703  mov     rcx, cs:WPP_GLOBAL_Control
0x18004170a  lea     rax, WPP_GLOBAL_Control
0x180041711  cmp     rcx, rax
0x180041714  jz      loc_1800417DC
0x18004171a  test    byte ptr [rcx+1Ch], 1
0x18004171e  jz      loc_1800417DC
0x180041724  call    cs:__imp_GetLastError
0x18004172a  mov     rcx, cs:WPP_GLOBAL_Control
0x180041731  lea     edx, [rsi+12h]
0x180041734  mov     r9d, eax
0x180041737  lea     r8, WPP_828388e69e2438d8439679a7cdeb6348_Traceguids
0x18004173e  mov     rcx, [rcx+10h]
0x180041742  call    WPP_SF_d
0x180041747  jmp     loc_1800417DC
0x18004174c  lea     rax, [rbp+800h+me.szModule]
0x180041753  or      r9, 0FFFFFFFFFFFFFFFFh
0x180041757  inc     r9; cchCount2
0x18004175a  cmp     [rax+r9*2], si
0x18004175f  jnz     short loc_180041757
0x180041761  cmp     rdi, r9
0x180041764  jnz     short loc_18004178A
0x180041766  test    rdi, rdi
0x180041769  jz      short loc_1800417A0
0x18004176b  mov     edx, edi; cchCount1
0x18004176d  mov     [rsp+900h+bIgnoreCase], 1; bIgnoreCase
0x180041775  lea     r8, [rbp+800h+me.szModule]; lpString2
0x18004177c  mov     rcx, r14; lpString1
0x18004177f  call    cs:__imp_CompareStringOrdinal
0x180041785  cmp     eax, 2
0x180041788  jz      short loc_1800417A0
0x18004178a  lea     rdx, [rbp+800h+me]; lpme
0x180041791  mov     rcx, rbx; hSnapshot
0x180041794  call    cs:__imp_Module32NextW
0x18004179a  test    eax, eax
0x18004179c  jnz     short loc_18004174C
0x18004179e  jmp     short loc_1800417DC
0x1800417a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800417a7  lea     rax, WPP_GLOBAL_Control
0x1800417ae  cmp     rcx, rax
0x1800417b1  jz      short loc_1800417D6
0x1800417b3  test    byte ptr [rcx+1Ch], 4
0x1800417b7  jz      short loc_1800417D6
0x1800417b9  mov     rcx, [rcx+10h]
0x1800417bd  lea     r8, WPP_828388e69e2438d8439679a7cdeb6348_Traceguids
0x1800417c4  mov     edx, 13h
0x1800417c9  mov     [rsp+900h+bIgnoreCase], r12d
0x1800417ce  mov     r9, r14
0x1800417d1  call    WPP_SF_Sd
0x1800417d6  mov     r15d, 1
0x1800417dc  mov     rcx, rbx; hObject
0x1800417df  call    cs:__imp_CloseHandle
0x1800417e5  mov     rcx, r13; hObject
0x1800417e8  call    cs:__imp_CloseHandle
0x1800417ee  mov     eax, r15d
0x1800417f1  mov     rcx, [rbp+800h+var_40]
0x1800417f8  xor     rcx, rsp; StackCookie
0x1800417fb  call    __security_check_cookie
0x180041800  mov     rbx, [rsp+900h+arg_0]
0x180041808  add     rsp, 8D0h
0x18004180f  pop     r15
0x180041811  pop     r14
0x180041813  pop     r13
0x180041815  pop     r12
0x180041817  pop     rdi
0x180041818  pop     rsi
0x180041819  pop     rbp
0x18004181a  retn
```
