# EuRouterInterfaceCreate

- ea: `0x180014198`
- end: `0x1800146c4`
- name: `EuRouterInterfaceCreate`
- size: `1324`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012b78`

## callees

- `0x180014198`
- `0x18003bea0`
- `0x18003c43c`
- `0x18003c860`
- `0x18003ccf4`
- `0x18003ce6c`
- `0x18003d184`
- `0x180048f0c`
- `0x18004d0d2`
- `0x18004d110`
- `0x18004e010`

## import_xrefs

- `samcli!NetUserAdd` at `0x180014457`
- `samcli!NetUserAdd` at `0x180014457`
- `samcli!NetUserDel` at `0x18001464a`
- `samcli!NetUserDel` at `0x18001464a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18001443a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18001443a`
- `MPRAPI!MprAdminInterfaceDelete` at `0x18001462c`
- `MPRAPI!MprAdminInterfaceDelete` at `0x18001462c`
- `USER32!GetActiveWindow` at `0x1800144bc`
- `USER32!GetActiveWindow` at `0x1800144bc`
- `rtutils!TracePrintfExA` at `0x18001424e`
- `rtutils!TracePrintfExA` at `0x180014617`
- `rtutils!TracePrintfExA` at `0x18001424e`
- `rtutils!TracePrintfExA` at `0x180014617`

## string_xrefs

- `0x180014242`: `EuRouterInterfaceCreate`
- `0x180014314`: `EuRouterInterfaceCreate: MprAdminInterfaceCreate error %d`
- `0x180014351`: `EuRouterInterfaceCreate: MprAdminInterfaceGetHandle error %d`
- `0x180014503`: `EuRouterInterfaceCreate: NetUserAdd error %d`
- `0x180014563`: `EuRouterInterfaceCreate: MprAdminUserSetInfo %d`
- `0x1800145a4`: `EuRouterInterfaceCreate: UserSvrConnect error %d`
- `0x1800145d7`: `EuRouterInterfaceCreate: UserOpen error %d`
- `0x180014608`: `EuRouterInterfaceCreate: UserWrite error %d`

## pseudocode

```c
__int64 __fastcall EuRouterInterfaceCreate(__int64 a1)
{
  __int64 result; // rax
  int v3; // r14d
  int v4; // r15d
  __int64 v5; // rcx
  const wchar_t *v6; // rax
  const WCHAR *v7; // rsi
  unsigned int v8; // ebx
  unsigned int v9; // eax
  DWORD v10; // ecx
  const CHAR *v11; // r8
  __int64 v12; // rcx
  BYTE *v13; // rax
  __int16 *v14; // rcx
  __int64 v15; // rax
  __int16 *v16; // rcx
  __int64 v17; // rax
  WCHAR *v18; // rcx
  DWORD v19; // eax
  _BYTE *v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  HWND ActiveWindow; // rax
  __int64 v24; // rcx
  _BYTE *v25; // rax
  WCHAR *v26; // rcx
  WCHAR *v27; // rcx
  DWORD nSize; // [rsp+30h] [rbp-D0h] BYREF
  MPR_SERVER_HANDLE hMprServer; // [rsp+38h] [rbp-C8h] BYREF
  DWORD parm_err; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hInterface; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v32; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v33; // [rsp+58h] [rbp-A8h] BYREF
  BYTE buf[16]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v35; // [rsp+70h] [rbp-90h]
  __int128 v36; // [rsp+80h] [rbp-80h]
  __int64 v37; // [rsp+90h] [rbp-70h]
  va_list Arguments[9]; // [rsp+A0h] [rbp-60h] BYREF
  int v39; // [rsp+E8h] [rbp-18h]
  _BYTE v40[272]; // [rsp+110h] [rbp+10h] BYREF
  wchar_t v41[257]; // [rsp+220h] [rbp+120h] BYREF
  int v42; // [rsp+422h] [rbp+322h]
  __int16 v43; // [rsp+426h] [rbp+326h]
  int v44; // [rsp+430h] [rbp+330h]
  int v45; // [rsp+434h] [rbp+334h]
  WCHAR servername[2]; // [rsp+450h] [rbp+350h] BYREF
  WCHAR Buffer[510]; // [rsp+454h] [rbp+354h] BYREF

  parm_err = 0;
  nSize = 0;
  hMprServer = 0;
  v33 = 0;
  v32 = 0;
  hInterface = 0;
  v40[1] = 0;
  memset_0(v40, 0, 0x103u);
  v37 = 0;
  *(_OWORD *)buf = 0;
  v42 = 0;
  v35 = 0;
  v43 = 0;
  v36 = 0;
  memset_0(v41, 0, 0x222u);
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "EuRouterInterfaceCreate");
  result = ((__int64 (__fastcall *)(_QWORD, MPR_SERVER_HANDLE *))g_pMprAdminServerConnect)(
             *(_QWORD *)(a1 + 48),
             &hMprServer);
  if ( !(_DWORD)result )
  {
    v3 = 0;
    v4 = 0;
    memset_0(v41, 0, 0x228u);
    v5 = *(_QWORD *)(a1 + 872);
    v45 = 2;
    v44 = 1;
    v6 = (const wchar_t *)StrDup(*(STRSAFE_LPCWSTR *)(v5 + 8));
    v7 = v6;
    if ( !v6 )
    {
      v8 = 8;
LABEL_54:
      if ( hInterface )
        MprAdminInterfaceDelete(hMprServer, hInterface);
      if ( v4 )
      {
        v27 = servername;
        if ( !v3 )
          v27 = *(WCHAR **)(a1 + 48);
        NetUserDel(v27, v7);
      }
      goto LABEL_60;
    }
    v8 = StringCchCopyWrapW(v41, 0x101u, v6);
    if ( v8 )
      goto LABEL_54;
    v9 = ((__int64 (__fastcall *)(MPR_SERVER_HANDLE, _QWORD, wchar_t *, HANDLE *))g_pMprAdminInterfaceCreate)(
           hMprServer,
           0,
           v41,
           &hInterface);
    v8 = v9;
    if ( v9 )
    {
      v10 = g_dwTraceId;
      if ( g_dwTraceId == -1 )
        goto LABEL_54;
      v11 = "EuRouterInterfaceCreate: MprAdminInterfaceCreate error %d";
    }
    else
    {
      v9 = ((__int64 (__fastcall *)(MPR_SERVER_HANDLE, const WCHAR *, HANDLE *, _QWORD))g_pMprAdminInterfaceGetHandle)(
             hMprServer,
             v7,
             &hInterface,
             0);
      v8 = v9;
      if ( !v9 )
      {
        if ( *(_DWORD *)(a1 + 936) )
        {
          v12 = 56;
          v13 = buf;
          do
          {
            *v13++ = 0;
            --v12;
          }
          while ( v12 );
          v14 = *(__int16 **)(a1 + 944);
          *(_QWORD *)buf = v7;
          EncodePasswordW(v14);
          v15 = StrDup(*(STRSAFE_LPCWSTR *)(a1 + 944));
          v16 = *(__int16 **)(a1 + 944);
          *(_QWORD *)&buf[8] = v15;
          EncodePasswordW(v16);
          DWORD1(v35) = 1;
          v17 = PszFromId(g_hinstDll, 0x19Au);
          v18 = *(WCHAR **)(a1 + 48);
          *(_QWORD *)&v36 = v17;
          DWORD2(v36) = 66049;
          if ( v18 && *v18 != 92 )
          {
            nSize = 510;
            v8 = StringCchCopyWrapW(servername, 0x200u, L"\\\\");
            if ( v8 )
              goto LABEL_54;
            if ( **(_WORD **)(a1 + 48) )
            {
              v8 = StringCchCatWrapW(servername, 512);
              if ( v8 )
                goto LABEL_54;
            }
            else
            {
              GetComputerNameW(Buffer, &nSize);
            }
            v3 = 1;
            v18 = servername;
          }
          v19 = NetUserAdd(v18, 1u, buf, &parm_err);
          v20 = *(_BYTE **)&buf[8];
          v8 = v19;
          v21 = -1;
          do
            ++v21;
          while ( *(_WORD *)(*(_QWORD *)&buf[8] + 2 * v21) );
          v22 = 2 * v21;
          if ( v22 )
          {
            do
            {
              *v20++ = 0;
              --v22;
            }
            while ( v22 );
            v20 = *(_BYTE **)&buf[8];
          }
          Free0(v20);
          Free0(v36);
          if ( v8 == 2224 )
          {
            memset_0(Arguments, 0, 0x68u);
            Arguments[0] = *(va_list *)buf;
            v39 = 68;
            ActiveWindow = GetActiveWindow();
            if ( (unsigned int)MsgDlgUtil(ActiveWindow, 0x615u, Arguments, g_hinstDll, 0x169u) == 7 )
              goto LABEL_54;
          }
          else
          {
            if ( v8 )
            {
              if ( g_dwTraceId != -1 )
                TracePrintfExA(g_dwTraceId, 0xCu, "EuRouterInterfaceCreate: NetUserAdd error %d", v8);
              goto LABEL_54;
            }
            v4 = 1;
          }
          v24 = 260;
          v25 = v40;
          do
          {
            *v25++ = 0;
            --v24;
          }
          while ( v24 );
          v40[0] = 9;
          if ( *(_DWORD *)(a1 + 36) )
          {
            v9 = ((__int64 (__fastcall *)(_QWORD, const WCHAR *, _QWORD, _BYTE *))g_pRasAdminUserSetInfo)(
                   *(_QWORD *)(a1 + 48),
                   v7,
                   0,
                   v40);
            v8 = v9;
            if ( v9 )
            {
              v10 = g_dwTraceId;
              if ( g_dwTraceId == -1 )
                goto LABEL_54;
              v11 = "EuRouterInterfaceCreate: MprAdminUserSetInfo %d";
              goto LABEL_53;
            }
          }
          else
          {
            v26 = servername;
            if ( !v3 )
              v26 = *(WCHAR **)(a1 + 48);
            v9 = ((__int64 (__fastcall *)(WCHAR *, __int64, __int64 *))g_pMprAdminUserServerConnect)(v26, 1, &v33);
            v8 = v9;
            if ( v9 )
            {
              v10 = g_dwTraceId;
              if ( g_dwTraceId == -1 )
                goto LABEL_54;
              v11 = "EuRouterInterfaceCreate: UserSvrConnect error %d";
              goto LABEL_53;
            }
            v9 = ((__int64 (__fastcall *)(__int64, const WCHAR *, __int64 *))g_pMprAdminUserOpen)(v33, v7, &v32);
            v8 = v9;
            if ( v9 )
            {
              v10 = g_dwTraceId;
              if ( g_dwTraceId == -1 )
                goto LABEL_54;
              v11 = "EuRouterInterfaceCreate: UserOpen error %d";
              goto LABEL_53;
            }
            v9 = ((__int64 (__fastcall *)(__int64, _QWORD, _BYTE *))g_pMprAdminUserWrite)(v32, 0, v40);
            v8 = v9;
            if ( v9 )
            {
              v10 = g_dwTraceId;
              if ( g_dwTraceId == -1 )
                goto LABEL_54;
              v11 = "EuRouterInterfaceCreate: UserWrite error %d";
              goto LABEL_53;
            }
          }
        }
LABEL_60:
        if ( v32 )
          ((void (*)(void))g_pMprAdminUserClose)();
        if ( v33 )
          ((void (*)(void))g_pMprAdminUserServerDisconnect)();
        if ( v7 )
          Free0(v7);
        if ( hMprServer )
          ((void (*)(void))g_pMprAdminServerDisconnect)();
        return v8;
      }
      v10 = g_dwTraceId;
      if ( g_dwTraceId == -1 )
        goto LABEL_54;
      v11 = "EuRouterInterfaceCreate: MprAdminInterfaceGetHandle error %d";
    }
LABEL_53:
    TracePrintfExA(v10, 0xCu, v11, v9);
    goto LABEL_54;
  }
  return result;
}

```

## disassembly

```asm
0x180014198  push    rbp
0x18001419a  push    rbx
0x18001419b  push    rsi
0x18001419c  push    rdi
0x18001419d  push    r12
0x18001419f  push    r13
0x1800141a1  push    r14
0x1800141a3  push    r15
0x1800141a5  lea     rbp, [rsp-768h]
0x1800141ad  sub     rsp, 868h
0x1800141b4  mov     rax, cs:__security_cookie
0x1800141bb  xor     rax, rsp
0x1800141be  mov     [rbp+7A0h+var_50], rax
0x1800141c5  xor     r12d, r12d
0x1800141c8  mov     rdi, rcx
0x1800141cb  xor     eax, eax
0x1800141cd  mov     [rsp+8A0h+parm_err], r12d
0x1800141d2  lea     rcx, [rbp+7A0h+var_790]; void *
0x1800141d6  mov     [rsp+8A0h+nSize], r12d
0x1800141db  xor     edx, edx; Val
0x1800141dd  mov     [rsp+8A0h+hMprServer], r12
0x1800141e2  mov     r8d, 103h; Size
0x1800141e8  mov     [rsp+8A0h+var_848], r12
0x1800141ed  mov     [rsp+8A0h+var_850], r12
0x1800141f2  mov     [rsp+8A0h+hInterface], r12
0x1800141f7  mov     [rbp+7A0h+var_78F], al
0x1800141fa  call    memset_0
0x1800141ff  xorps   xmm0, xmm0
0x180014202  lea     rcx, [rbp+7A0h+var_680]; void *
0x180014209  xor     eax, eax
0x18001420b  xor     edx, edx; Val
0x18001420d  mov     r8d, 222h; Size
0x180014213  mov     [rbp+7A0h+var_810], rax
0x180014217  movups  xmmword ptr [rsp+8A0h+buf], xmm0
0x18001421c  mov     [rbp+7A0h+var_47E], eax
0x180014222  movups  [rsp+8A0h+var_830], xmm0
0x180014227  mov     [rbp+7A0h+var_47A], ax
0x18001422e  movups  [rbp+7A0h+var_820], xmm0
0x180014232  call    memset_0
0x180014237  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001423d  cmp     ecx, 0FFFFFFFFh
0x180014240  jz      short loc_180014254
0x180014242  lea     r8, aEurouterinterf_3; "EuRouterInterfaceCreate"
0x180014249  lea     edx, [r12+0Ch]; dwFlags
0x18001424e  call    cs:__imp_TracePrintfExA
0x180014254  mov     rcx, [rdi+30h]
0x180014258  lea     rdx, [rsp+8A0h+hMprServer]
0x18001425d  mov     rax, cs:g_pMprAdminServerConnect
0x180014264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014269  test    eax, eax
0x18001426b  jnz     loc_1800146A1
0x180014271  xor     edx, edx; Val
0x180014273  lea     rcx, [rbp+7A0h+var_680]; void *
0x18001427a  mov     r8d, 228h; Size
0x180014280  mov     r14d, r12d
0x180014283  mov     r15d, r12d
0x180014286  call    memset_0
0x18001428b  mov     rcx, [rdi+368h]
0x180014292  mov     r13d, 1
0x180014298  mov     [rbp+7A0h+var_46C], 2
0x1800142a2  mov     [rbp+7A0h+var_470], r13d
0x1800142a9  mov     rcx, [rcx+8]; pszSrc
0x1800142ad  call    StrDup
0x1800142b2  mov     rsi, rax
0x1800142b5  test    rax, rax
0x1800142b8  jnz     short loc_1800142C2
0x1800142ba  lea     ebx, [rax+8]
0x1800142bd  jmp     loc_18001461D
0x1800142c2  mov     r8, rsi
0x1800142c5  lea     rcx, [rbp+7A0h+var_680]
0x1800142cc  mov     edx, 101h
0x1800142d1  call    StringCchCopyWrapW
0x1800142d6  mov     ebx, eax
0x1800142d8  test    eax, eax
0x1800142da  jnz     loc_18001461D
0x1800142e0  mov     rcx, [rsp+8A0h+hMprServer]
0x1800142e5  lea     r9, [rsp+8A0h+hInterface]
0x1800142ea  mov     rax, cs:g_pMprAdminInterfaceCreate
0x1800142f1  lea     r8, [rbp+7A0h+var_680]
0x1800142f8  xor     edx, edx
0x1800142fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142ff  mov     ebx, eax
0x180014301  test    eax, eax
0x180014303  jz      short loc_180014320
0x180014305  mov     ecx, cs:g_dwTraceId
0x18001430b  cmp     ecx, 0FFFFFFFFh
0x18001430e  jz      loc_18001461D
0x180014314  lea     r8, aEurouterinterf_1; "EuRouterInterfaceCreate: MprAdminInterf"...
0x18001431b  jmp     loc_18001460F
0x180014320  mov     rcx, [rsp+8A0h+hMprServer]
0x180014325  lea     r8, [rsp+8A0h+hInterface]
0x18001432a  mov     rax, cs:g_pMprAdminInterfaceGetHandle
0x180014331  xor     r9d, r9d
0x180014334  mov     rdx, rsi
0x180014337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001433c  mov     ebx, eax
0x18001433e  test    eax, eax
0x180014340  jz      short loc_18001435D
0x180014342  mov     ecx, cs:g_dwTraceId
0x180014348  cmp     ecx, 0FFFFFFFFh
0x18001434b  jz      loc_18001461D
0x180014351  lea     r8, aEurouterinterf_4; "EuRouterInterfaceCreate: MprAdminInterf"...
0x180014358  jmp     loc_18001460F
0x18001435d  cmp     [rdi+3A8h], r12d
0x180014364  jz      loc_180014650
0x18001436a  mov     ecx, 38h ; '8'
0x18001436f  lea     rax, [rsp+8A0h+buf]
0x180014374  mov     [rax], r12b
0x180014377  add     rax, r13
0x18001437a  sub     rcx, r13
0x18001437d  jnz     short loc_180014374
0x18001437f  mov     rcx, [rdi+3B0h]
0x180014386  mov     qword ptr [rsp+8A0h+buf], rsi
0x18001438b  call    EncodePasswordW
0x180014390  mov     rcx, [rdi+3B0h]; pszSrc
0x180014397  call    StrDup
0x18001439c  mov     rcx, [rdi+3B0h]
0x1800143a3  mov     qword ptr [rsp+8A0h+buf+8], rax
0x1800143a8  call    EncodePasswordW
0x1800143ad  mov     rcx, cs:g_hinstDll; hInstance
0x1800143b4  mov     edx, 19Ah; uID
0x1800143b9  mov     dword ptr [rsp+8A0h+var_830+4], r13d
0x1800143be  call    PszFromId
0x1800143c3  mov     rcx, [rdi+30h]
0x1800143c7  mov     qword ptr [rbp+7A0h+var_820], rax
0x1800143cb  mov     dword ptr [rbp+7A0h+var_820+8], 10201h
0x1800143d2  test    rcx, rcx
0x1800143d5  jz      short loc_18001444A
0x1800143d7  cmp     word ptr [rcx], 5Ch ; '\'
0x1800143db  jz      short loc_18001444A
0x1800143dd  lea     r8, asc_180054458; "\\\\"
0x1800143e4  mov     [rsp+8A0h+nSize], 1FEh
0x1800143ec  mov     edx, 200h
0x1800143f1  lea     rcx, [rbp+7A0h+servername]
0x1800143f8  call    StringCchCopyWrapW
0x1800143fd  mov     ebx, eax
0x1800143ff  test    eax, eax
0x180014401  jnz     loc_18001461D
0x180014407  mov     r8, [rdi+30h]
0x18001440b  cmp     [r8], r12w
0x18001440f  jz      short loc_18001442E
0x180014411  mov     edx, 200h
0x180014416  lea     rcx, [rbp+7A0h+servername]
0x18001441d  call    StringCchCatWrapW
0x180014422  mov     ebx, eax
0x180014424  test    eax, eax
0x180014426  jnz     loc_18001461D
0x18001442c  jmp     short loc_180014440
0x18001442e  lea     rdx, [rsp+8A0h+nSize]; nSize
0x180014433  lea     rcx, [rbp+7A0h+Buffer]; lpBuffer
0x18001443a  call    cs:__imp_GetComputerNameW
0x180014440  mov     r14d, r13d
0x180014443  lea     rcx, [rbp+7A0h+servername]; servername
0x18001444a  lea     r9, [rsp+8A0h+parm_err]; parm_err
0x18001444f  mov     edx, r13d; level
0x180014452  lea     r8, [rsp+8A0h+buf]; buf
0x180014457  call    cs:__imp_NetUserAdd
0x18001445d  mov     rcx, qword ptr [rsp+8A0h+buf+8]
0x180014462  mov     ebx, eax
0x180014464  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014468  inc     rax
0x18001446b  cmp     [rcx+rax*2], r12w
0x180014470  jnz     short loc_180014468
0x180014472  add     rax, rax
0x180014475  jz      short loc_180014487
0x180014477  mov     [rcx], r12b
0x18001447a  add     rcx, r13
0x18001447d  sub     rax, r13
0x180014480  jnz     short loc_180014477
0x180014482  mov     rcx, qword ptr [rsp+8A0h+buf+8]
0x180014487  call    Free0
0x18001448c  mov     rcx, qword ptr [rbp+7A0h+var_820]
0x180014490  call    Free0
0x180014495  cmp     ebx, 8B0h
0x18001449b  jnz     short loc_1800144ED
0x18001449d  xor     edx, edx; Val
0x18001449f  lea     rcx, [rbp+7A0h+Arguments]; void *
0x1800144a3  lea     r8d, [rdx+68h]; Size
0x1800144a7  call    memset_0
0x1800144ac  mov     rax, qword ptr [rsp+8A0h+buf]
0x1800144b1  mov     [rbp+7A0h+Arguments], rax
0x1800144b5  mov     [rbp+7A0h+var_7B8], 44h ; 'D'
0x1800144bc  call    cs:__imp_GetActiveWindow
0x1800144c2  mov     r9, cs:g_hinstDll; hInstance
0x1800144c9  lea     r8, [rbp+7A0h+Arguments]; Arguments
0x1800144cd  mov     rcx, rax; hWnd
0x1800144d0  mov     [rsp+8A0h+var_880], 169h; UINT
0x1800144d8  mov     edx, 615h; uID
0x1800144dd  call    MsgDlgUtil
0x1800144e2  cmp     eax, 7
0x1800144e5  jz      loc_18001461D
0x1800144eb  jmp     short loc_180014512
0x1800144ed  test    ebx, ebx
0x1800144ef  jz      short loc_18001450F
0x1800144f1  mov     ecx, cs:g_dwTraceId
0x1800144f7  cmp     ecx, 0FFFFFFFFh
0x1800144fa  jz      loc_18001461D
0x180014500  mov     r9d, ebx
0x180014503  lea     r8, aEurouterinterf_2; "EuRouterInterfaceCreate: NetUserAdd err"...
0x18001450a  jmp     loc_180014612
0x18001450f  mov     r15d, r13d
0x180014512  mov     ecx, 104h
0x180014517  lea     rax, [rbp+7A0h+var_790]
0x18001451b  mov     [rax], r12b
0x18001451e  add     rax, r13
0x180014521  sub     rcx, r13
0x180014524  jnz     short loc_18001451B
0x180014526  mov     [rbp+7A0h+var_790], 9
0x18001452a  cmp     [rdi+24h], r12d
0x18001452e  jz      short loc_18001456F
0x180014530  mov     rcx, [rdi+30h]
0x180014534  lea     r9, [rbp+7A0h+var_790]
0x180014538  mov     rax, cs:g_pRasAdminUserSetInfo
0x18001453f  xor     r8d, r8d
0x180014542  mov     rdx, rsi
0x180014545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001454a  mov     ebx, eax
0x18001454c  test    eax, eax
0x18001454e  jz      loc_180014650
0x180014554  mov     ecx, cs:g_dwTraceId
0x18001455a  cmp     ecx, 0FFFFFFFFh
0x18001455d  jz      loc_18001461D
0x180014563  lea     r8, aEurouterinterf; "EuRouterInterfaceCreate: MprAdminUserSe"...
0x18001456a  jmp     loc_18001460F
0x18001456f  lea     rcx, [rbp+7A0h+servername]
0x180014576  test    r14d, r14d
0x180014579  jnz     short loc_18001457F
0x18001457b  mov     rcx, [rdi+30h]
0x18001457f  mov     rax, cs:g_pMprAdminUserServerConnect
0x180014586  lea     r8, [rsp+8A0h+var_848]
0x18001458b  mov     edx, r13d
0x18001458e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014593  mov     ebx, eax
0x180014595  test    eax, eax
0x180014597  jz      short loc_1800145AD
0x180014599  mov     ecx, cs:g_dwTraceId
0x18001459f  cmp     ecx, 0FFFFFFFFh
0x1800145a2  jz      short loc_18001461D
0x1800145a4  lea     r8, aEurouterinterf_5; "EuRouterInterfaceCreate: UserSvrConnect"...
0x1800145ab  jmp     short loc_18001460F
0x1800145ad  mov     rcx, [rsp+8A0h+var_848]
0x1800145b2  lea     r8, [rsp+8A0h+var_850]
0x1800145b7  mov     rax, cs:g_pMprAdminUserOpen
0x1800145be  mov     rdx, rsi
0x1800145c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800145c6  mov     ebx, eax
0x1800145c8  test    eax, eax
0x1800145ca  jz      short loc_1800145E0
0x1800145cc  mov     ecx, cs:g_dwTraceId
0x1800145d2  cmp     ecx, 0FFFFFFFFh
0x1800145d5  jz      short loc_18001461D
0x1800145d7  lea     r8, aEurouterinterf_6; "EuRouterInterfaceCreate: UserOpen error"...
0x1800145de  jmp     short loc_18001460F
0x1800145e0  mov     rcx, [rsp+8A0h+var_850]
0x1800145e5  lea     r8, [rbp+7A0h+var_790]
0x1800145e9  mov     rax, cs:g_pMprAdminUserWrite
0x1800145f0  xor     edx, edx
0x1800145f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800145f7  mov     ebx, eax
0x1800145f9  test    eax, eax
0x1800145fb  jz      short loc_180014650
0x1800145fd  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180014603  cmp     ecx, 0FFFFFFFFh
0x180014606  jz      short loc_18001461D
0x180014608  lea     r8, aEurouterinterf_0; "EuRouterInterfaceCreate: UserWrite erro"...
0x18001460f  mov     r9d, eax
0x180014612  mov     edx, 0Ch; dwFlags
0x180014617  call    cs:__imp_TracePrintfExA
0x18001461d  mov     rdx, [rsp+8A0h+hInterface]; hInterface
0x180014622  test    rdx, rdx
0x180014625  jz      short loc_180014632
0x180014627  mov     rcx, [rsp+8A0h+hMprServer]; hMprServer
0x18001462c  call    cs:__imp_MprAdminInterfaceDelete
0x180014632  test    r15d, r15d
0x180014635  jz      short loc_180014650
0x180014637  lea     rcx, [rbp+7A0h+servername]
0x18001463e  test    r14d, r14d
0x180014641  jnz     short loc_180014647
0x180014643  mov     rcx, [rdi+30h]; servername
0x180014647  mov     rdx, rsi; username
0x18001464a  call    cs:__imp_NetUserDel
0x180014650  mov     rcx, [rsp+8A0h+var_850]
0x180014655  test    rcx, rcx
0x180014658  jz      short loc_180014666
0x18001465a  mov     rax, cs:g_pMprAdminUserClose
0x180014661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014666  mov     rcx, [rsp+8A0h+var_848]
0x18001466b  test    rcx, rcx
0x18001466e  jz      short loc_18001467C
0x180014670  mov     rax, cs:g_pMprAdminUserServerDisconnect
0x180014677  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001467c  test    rsi, rsi
0x18001467f  jz      short loc_180014689
0x180014681  mov     rcx, rsi
0x180014684  call    Free0
0x180014689  mov     rcx, [rsp+8A0h+hMprServer]
0x18001468e  test    rcx, rcx
0x180014691  jz      short loc_18001469F
0x180014693  mov     rax, cs:g_pMprAdminServerDisconnect
0x18001469a  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
