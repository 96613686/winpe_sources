# CleanupMgrInfo::deactivateSingleClient(tag_ClientInfo *,PluginDeactivatationStart *,PluginDeactivatationStop *,uint)

- ea: `0x1400124b8`
- end: `0x1400128b5`
- name: `?deactivateSingleClient@CleanupMgrInfo@@IEAAXPEAUtag_ClientInfo@@PEAUPluginDeactivatationStart@@PEAUPluginDeactivatationStop@@I@Z`
- size: `1021`
- prototype: `void __fastcall(CleanupMgrInfo *this, struct tag_ClientInfo *, struct PluginDeactivatationStart *, struct PluginDeactivatationStop *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140012248`
- `0x140013530`

## callees

- `0x1400029a0`
- `0x140005fa0`
- `0x140005fe4`
- `0x1400124b8`
- `0x140018010`

## import_xrefs

- `SHLWAPI!SHDeleteKeyW` at `0x140012844`
- `SHLWAPI!SHDeleteKeyW` at `0x140012844`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012861`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001287a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012861`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001287a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1400125a4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1400125e6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1400125a4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1400125e6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400127e1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400127e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400127ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400127f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001284f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400127ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400127f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001284f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400127ac`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140012831`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400127ac`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140012831`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140012770`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140012770`

## string_xrefs

- `0x140012823`: `Software\Microsoft\Windows\CurrentVersion\Explorer\VolumeCaches`

## pseudocode

```c
void __fastcall CleanupMgrInfo::deactivateSingleClient(
        CleanupMgrInfo *this,
        struct tag_ClientInfo *a2,
        struct PluginDeactivatationStart *a3,
        struct PluginDeactivatationStop *a4,
        unsigned int a5)
{
  _DWORD *v8; // r12
  _DWORD *v9; // r13
  _QWORD *v10; // rsi
  int v11; // ebx
  ULONGLONG TickCount64; // rax
  double v13; // xmm7_8
  ULONGLONG v14; // rax
  double v15; // xmm6_8
  double v16; // xmm6_8
  unsigned __int64 v17; // rcx
  double v18; // xmm6_8
  int v19; // eax
  HKEY v20; // rcx
  int v21; // ebx
  HKEY v22; // rcx
  LSTATUS v23; // eax
  bool v24; // sf
  void *v25; // rcx
  void *v26; // rcx
  LPBYTE lpData; // [rsp+28h] [rbp-E0h]
  BYTE Data[8]; // [rsp+38h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C8h] BYREF
  DWORD cbData[2]; // [rsp+48h] [rbp-C0h] BYREF
  CleanupMgrInfo *v31; // [rsp+50h] [rbp-B8h]
  WCHAR ValueName[64]; // [rsp+58h] [rbp-B0h] BYREF

  v31 = this;
  ValueName[0] = 0;
  phkResult = (HKEY)((char *)a2 + 600);
  cbData[1] = 0;
  v8 = (_DWORD *)((char *)a2 + 608);
  v9 = (_DWORD *)((char *)a2 + 604);
  v10 = (_QWORD *)((char *)a2 + 24);
  if ( a3 )
  {
    lpData = (LPBYTE)a2 + 40;
    StringCchPrintfW((unsigned __int16 *)a3, 0x50u, L"%-*s");
    *((_OWORD *)a3 + 10) = *(_OWORD *)((char *)a2 + 8);
    *((_QWORD *)a3 + 22) = *v10 == 0;
    *((_DWORD *)a3 + 46) = *v8;
    *((_DWORD *)a3 + 47) = *v9;
    *((_DWORD *)a3 + 48) = *((_DWORD *)a2 + 150);
    *((_DWORD *)a3 + 49) = a5;
  }
  else
  {
    phkResult = (HKEY)((char *)a2 + 600);
  }
  v11 = 1;
  if ( *v10 )
  {
    TickCount64 = GetTickCount64();
    if ( (TickCount64 & 0x8000000000000000uLL) != 0LL )
      v13 = (double)(int)(TickCount64 & 1 | (TickCount64 >> 1)) + (double)(int)(TickCount64 & 1 | (TickCount64 >> 1));
    else
      v13 = (double)(int)TickCount64;
    cbData[0] = (*(__int64 (__fastcall **)(_QWORD, DWORD *))(*(_QWORD *)*v10 + 56LL))(*v10, &cbData[1]);
    v14 = GetTickCount64();
    if ( (v14 & 0x8000000000000000uLL) != 0LL )
      v15 = (double)(int)(v14 & 1 | (v14 >> 1)) + (double)(int)(v14 & 1 | (v14 >> 1));
    else
      v15 = (double)(int)v14;
    v16 = v15 - v13;
    if ( a4 )
    {
      lpData = (LPBYTE)a2 + 40;
      StringCchPrintfW((unsigned __int16 *)a4, 0x50u, L"%-*s");
      v17 = 0;
      v18 = v16 / 1000.0;
      *((_OWORD *)a4 + 10) = *(_OWORD *)((char *)a2 + 8);
      *((_DWORD *)a4 + 48) = *v8;
      *((_DWORD *)a4 + 49) = *v9;
      *(_DWORD *)((struct HKEY__ *)a4 + 50) = *(_DWORD *)phkResult;
      *((_QWORD *)a4 + 23) = (int)cbData[0];
      if ( v18 >= 9.223372036854776e18 )
      {
        v18 = v18 - 9.223372036854776e18;
        if ( v18 < 9.223372036854776e18 )
          v17 = 0x8000000000000000uLL;
      }
      *((_QWORD *)a4 + 22) = v17 + (unsigned int)(int)v18;
      *((_DWORD *)a4 + 51) = a5;
    }
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 16LL))(*v10);
    *v10 = 0;
  }
  if ( *((_QWORD *)a2 + 4) )
  {
    *(_DWORD *)Data = 0;
    cbData[0] = 0;
    v19 = *((_DWORD *)v31 + 408);
    if ( v19 < 0 )
    {
      if ( (v19 & 1) != 0 )
      {
        LODWORD(lpData) = *((_DWORD *)v31 + 409);
        v11 = 2;
        StringCchPrintfW(ValueName, 0x40u, L"%s%04d", L"StateFlags", lpData);
      }
      else
      {
        StringCchCopyW(ValueName, 0x40u, L"StateFlags");
      }
      v20 = (HKEY)*((_QWORD *)a2 + 4);
      *(_DWORD *)Data = 0;
      cbData[0] = 4;
      RegQueryValueExW(v20, ValueName, 0, 0, Data, cbData);
      if ( *((_DWORD *)a2 + 151) )
        v21 = *(_DWORD *)Data | v11;
      else
        v21 = *(_DWORD *)Data & ~v11;
      v22 = (HKEY)*((_QWORD *)a2 + 4);
      *(_DWORD *)Data = v21;
      phkResult = 0;
      v23 = RegOpenKeyExW(v22, 0, 0, 0x20006u, &phkResult);
      v24 = v23 < 0;
      if ( v23 > 0 )
        v24 = 1;
      if ( !v24 )
      {
        RegSetValueExW(phkResult, ValueName, 0, 4u, Data, 4u);
        RegCloseKey(phkResult);
      }
    }
    RegCloseKey(*((HKEY *)a2 + 4));
    if ( (cbData[1] & 4) != 0 )
    {
      if ( *((_DWORD *)a2 + 151) )
      {
        phkResult = 0;
        if ( !RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\VolumeCaches",
                0,
                0x3001Fu,
                &phkResult) )
        {
          SHDeleteKeyW(phkResult, (LPCWSTR)a2 + 20);
          RegCloseKey(phkResult);
        }
      }
    }
  }
  v25 = (void *)*((_QWORD *)a2 + 71);
  if ( v25 )
  {
    CoTaskMemFree(v25);
    *((_QWORD *)a2 + 71) = 0;
  }
  v26 = (void *)*((_QWORD *)a2 + 70);
  if ( v26 )
  {
    CoTaskMemFree(v26);
    *((_QWORD *)a2 + 70) = 0;
  }
}

```

## disassembly

```asm
0x1400124b8  mov     rax, rsp
0x1400124bb  push    rbp
0x1400124bc  push    rbx
0x1400124bd  push    rsi
0x1400124be  push    rdi
0x1400124bf  push    r12
0x1400124c1  push    r13
0x1400124c3  push    r14
0x1400124c5  push    r15
0x1400124c7  lea     rbp, [rax-48h]
0x1400124cb  sub     rsp, 108h
0x1400124d2  movaps  xmmword ptr [rax-58h], xmm6
0x1400124d6  movaps  xmmword ptr [rax-68h], xmm7
0x1400124da  mov     rax, cs:__security_cookie
0x1400124e1  xor     rax, rsp
0x1400124e4  mov     [rbp+40h+var_70], rax
0x1400124e8  xor     eax, eax
0x1400124ea  mov     [rsp+140h+var_F8], rcx
0x1400124ef  mov     [rsp+140h+ValueName], ax
0x1400124f4  lea     rax, [rdx+258h]
0x1400124fb  mov     [rsp+140h+phkResult], rax
0x140012500  mov     r14, r9
0x140012503  mov     [rsp+140h+cbData+4], 0
0x14001250b  mov     rbx, r8
0x14001250e  lea     rcx, [rdx+28h]
0x140012512  mov     rdi, rdx
0x140012515  lea     r12, [rdx+260h]
0x14001251c  lea     r13, [rdx+25Ch]
0x140012523  lea     rsi, [rdx+18h]
0x140012527  test    r8, r8
0x14001252a  jz      short loc_140012590
0x14001252c  mov     r9d, 4Fh ; 'O'
0x140012532  mov     [rsp+140h+lpData], rcx
0x140012537  lea     r8, aS; "%-*s"
0x14001253e  mov     rcx, rbx; unsigned __int16 *
0x140012541  lea     edx, [r9+1]; unsigned __int64
0x140012545  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001254a  movups  xmm0, xmmword ptr [rdi+8]
0x14001254e  xor     eax, eax
0x140012550  movdqu  xmmword ptr [rbx+0A0h], xmm0
0x140012558  cmp     [rsi], rax
0x14001255b  setz    al
0x14001255e  mov     [rbx+0B0h], rax
0x140012565  mov     eax, [r12]
0x140012569  mov     [rbx+0B8h], eax
0x14001256f  mov     eax, [r13+0]
0x140012573  mov     [rbx+0BCh], eax
0x140012579  mov     eax, [rdi+258h]
0x14001257f  mov     [rbx+0C0h], eax
0x140012585  mov     eax, [rbp+40h+arg_20]
0x140012588  mov     [rbx+0C4h], eax
0x14001258e  jmp     short loc_140012595
0x140012590  mov     [rsp+140h+phkResult], rax
0x140012595  cmp     qword ptr [rsi], 0
0x140012599  mov     ebx, 1
0x14001259e  jz      loc_1400126DA
0x1400125a4  call    cs:__imp_GetTickCount64
0x1400125aa  mov     rcx, rax
0x1400125ad  xorps   xmm7, xmm7
0x1400125b0  test    rax, rax
0x1400125b3  js      short loc_1400125BC
0x1400125b5  cvtsi2sd xmm7, rax
0x1400125ba  jmp     short loc_1400125CE
0x1400125bc  shr     rax, 1
0x1400125bf  and     rcx, rbx
0x1400125c2  or      rax, rcx
0x1400125c5  cvtsi2sd xmm7, rax
0x1400125ca  addsd   xmm7, xmm7
0x1400125ce  mov     rcx, [rsi]
0x1400125d1  lea     rdx, [rsp+140h+cbData+4]
0x1400125d6  mov     rax, [rcx]
0x1400125d9  mov     rax, [rax+38h]
0x1400125dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400125e2  mov     [rsp+140h+cbData], eax
0x1400125e6  call    cs:__imp_GetTickCount64
0x1400125ec  mov     rcx, rax
0x1400125ef  xorps   xmm6, xmm6
0x1400125f2  test    rax, rax
0x1400125f5  js      short loc_1400125FE
0x1400125f7  cvtsi2sd xmm6, rax
0x1400125fc  jmp     short loc_140012610
0x1400125fe  shr     rax, 1
0x140012601  and     rcx, rbx
0x140012604  or      rax, rcx
0x140012607  cvtsi2sd xmm6, rax
0x14001260c  addsd   xmm6, xmm6
0x140012610  subsd   xmm6, xmm7
0x140012614  test    r14, r14
0x140012617  jz      loc_1400126C4
0x14001261d  mov     r9d, 4Fh ; 'O'
0x140012623  lea     rax, [rdi+28h]
0x140012627  lea     r8, aS; "%-*s"
0x14001262e  mov     [rsp+140h+lpData], rax
0x140012633  mov     rcx, r14; unsigned __int16 *
0x140012636  lea     edx, [r9+1]; unsigned __int64
0x14001263a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001263f  movups  xmm0, xmmword ptr [rdi+8]
0x140012643  xor     ecx, ecx
0x140012645  divsd   xmm6, cs:__real@408f400000000000
0x14001264d  movdqu  xmmword ptr [r14+0A0h], xmm0
0x140012656  mov     eax, [r12]
0x14001265a  movsd   xmm0, cs:__real@43e0000000000000
0x140012662  comisd  xmm6, xmm0
0x140012666  mov     [r14+0C0h], eax
0x14001266d  mov     eax, [r13+0]
0x140012671  mov     [r14+0C4h], eax
0x140012678  mov     rax, [rsp+140h+phkResult]
0x14001267d  mov     eax, [rax]
0x14001267f  mov     [r14+0C8h], eax
0x140012686  movsxd  rax, [rsp+140h+cbData]
0x14001268b  mov     [r14+0B8h], rax
0x140012692  jb      short loc_1400126AB
0x140012694  subsd   xmm6, xmm0
0x140012698  comisd  xmm6, xmm0
0x14001269c  jnb     short loc_1400126AB
0x14001269e  mov     rax, 8000000000000000h
0x1400126a8  mov     rcx, rax
0x1400126ab  cvttsd2si rax, xmm6
0x1400126b0  add     rax, rcx
0x1400126b3  mov     [r14+0B0h], rax
0x1400126ba  mov     eax, [rbp+40h+arg_20]
0x1400126bd  mov     [r14+0CCh], eax
0x1400126c4  mov     rcx, [rsi]
0x1400126c7  mov     rax, [rcx]
0x1400126ca  mov     rax, [rax+10h]
0x1400126ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400126d3  mov     qword ptr [rsi], 0
0x1400126da  xor     esi, esi
0x1400126dc  cmp     [rdi+20h], rsi
0x1400126e0  jz      loc_140012855
0x1400126e6  mov     rcx, [rsp+140h+var_F8]
0x1400126eb  lea     r14d, [rsi+4]
0x1400126ef  mov     dword ptr [rsp+140h+Data], esi
0x1400126f3  mov     [rsp+140h+cbData], esi
0x1400126f7  mov     eax, [rcx+660h]
0x1400126fd  test    eax, eax
0x1400126ff  jns     loc_1400127F2
0x140012705  lea     edx, [rsi+40h]; unsigned __int64
0x140012708  test    bl, al
0x14001270a  jz      short loc_140012733
0x14001270c  mov     eax, [rcx+664h]
0x140012712  lea     r9, aStateflags; "StateFlags"
0x140012719  lea     rcx, [rsp+140h+ValueName]; unsigned __int16 *
0x14001271e  mov     dword ptr [rsp+140h+lpData], eax
0x140012722  lea     r8, aS04d; "%s%04d"
0x140012729  lea     ebx, [rsi+2]
0x14001272c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140012731  jmp     short loc_140012744
0x140012733  lea     r8, aStateflags; "StateFlags"
0x14001273a  lea     rcx, [rsp+140h+ValueName]; unsigned __int16 *
0x14001273f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140012744  mov     rcx, [rdi+20h]; hKey
0x140012748  lea     rax, [rsp+140h+cbData]
0x14001274d  mov     [rsp+140h+lpcbData], rax; lpcbData
0x140012752  lea     rdx, [rsp+140h+ValueName]; lpValueName
0x140012757  lea     rax, [rsp+140h+Data]
0x14001275c  mov     dword ptr [rsp+140h+Data], esi
0x140012760  xor     r9d, r9d; lpType
0x140012763  mov     [rsp+140h+lpData], rax; lpData
0x140012768  xor     r8d, r8d; lpReserved
0x14001276b  mov     [rsp+140h+cbData], r14d
0x140012770  call    cs:__imp_RegQueryValueExW
0x140012776  cmp     [rdi+25Ch], esi
0x14001277c  jz      short loc_140012784
0x14001277e  or      ebx, dword ptr [rsp+140h+Data]
0x140012782  jmp     short loc_14001278A
0x140012784  not     ebx
0x140012786  and     ebx, dword ptr [rsp+140h+Data]
0x14001278a  mov     rcx, [rdi+20h]; hKey
0x14001278e  lea     rax, [rsp+140h+phkResult]
0x140012793  mov     r9d, 20006h; samDesired
0x140012799  mov     [rsp+140h+lpData], rax; phkResult
0x14001279e  xor     r8d, r8d; ulOptions
0x1400127a1  mov     dword ptr [rsp+140h+Data], ebx
0x1400127a5  xor     edx, edx; lpSubKey
0x1400127a7  mov     [rsp+140h+phkResult], rsi
0x1400127ac  call    cs:__imp_RegOpenKeyExW
0x1400127b2  test    eax, eax
0x1400127b4  jle     short loc_1400127C0
0x1400127b6  movzx   eax, ax
0x1400127b9  or      eax, 80070000h
0x1400127be  test    eax, eax
0x1400127c0  js      short loc_1400127F2
0x1400127c2  mov     rcx, [rsp+140h+phkResult]; hKey
0x1400127c7  lea     rax, [rsp+140h+Data]
0x1400127cc  mov     dword ptr [rsp+140h+lpcbData], r14d; cbData
0x1400127d1  lea     rdx, [rsp+140h+ValueName]; lpValueName
0x1400127d6  mov     r9d, r14d; dwType
0x1400127d9  mov     [rsp+140h+lpData], rax; lpData
0x1400127de  xor     r8d, r8d; Reserved
0x1400127e1  call    cs:__imp_RegSetValueExW
0x1400127e7  mov     rcx, [rsp+140h+phkResult]; hKey
0x1400127ec  call    cs:__imp_RegCloseKey
0x1400127f2  mov     rcx, [rdi+20h]; hKey
0x1400127f6  call    cs:__imp_RegCloseKey
0x1400127fc  test    byte ptr [rsp+140h+cbData+4], r14b
0x140012801  jz      short loc_140012855
0x140012803  cmp     [rdi+25Ch], esi
0x140012809  jz      short loc_140012855
0x14001280b  lea     rax, [rsp+140h+phkResult]
0x140012810  mov     [rsp+140h+phkResult], rsi
0x140012815  mov     r9d, 3001Fh; samDesired
0x14001281b  mov     [rsp+140h+lpData], rax; phkResult
0x140012820  xor     r8d, r8d; ulOptions
0x140012823  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14001282a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140012831  call    cs:__imp_RegOpenKeyExW
0x140012837  test    eax, eax
0x140012839  jnz     short loc_140012855
0x14001283b  mov     rcx, [rsp+140h+phkResult]; hkey
0x140012840  lea     rdx, [rdi+28h]; pszSubKey
0x140012844  call    cs:__imp_SHDeleteKeyW
0x14001284a  mov     rcx, [rsp+140h+phkResult]; hKey
0x14001284f  call    cs:__imp_RegCloseKey
0x140012855  mov     rcx, [rdi+238h]; pv
0x14001285c  test    rcx, rcx
0x14001285f  jz      short loc_14001286E
0x140012861  call    cs:__imp_CoTaskMemFree
0x140012867  mov     [rdi+238h], rsi
0x14001286e  mov     rcx, [rdi+230h]; pv
0x140012875  test    rcx, rcx
0x140012878  jz      short loc_140012887
0x14001287a  call    cs:__imp_CoTaskMemFree
0x140012880  mov     [rdi+230h], rsi
0x140012887  mov     rcx, [rbp+40h+var_70]
0x14001288b  xor     rcx, rsp; StackCookie
0x14001288e  call    __security_check_cookie
0x140012893  lea     r11, [rsp+140h+var_38]
0x14001289b  movaps  xmm6, xmmword ptr [r11-18h]
0x1400128a0  movaps  xmm7, xmmword ptr [r11-28h]
0x1400128a5  mov     rsp, r11
0x1400128a8  pop     r15
0x1400128aa  pop     r14
0x1400128ac  pop     r13
0x1400128ae  pop     r12
0x1400128b0  pop     rdi
0x1400128b1  pop     rsi
0x1400128b2  pop     rbx
0x1400128b3  pop     rbp
0x1400128b4  retn
```
