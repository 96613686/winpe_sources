# EuClearCustomPolicy

- ea: `0x1800128e4`
- end: `0x180012b6f`
- name: `EuClearCustomPolicy`
- size: `651`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180012b78`

## callees

- `0x1800128e4`
- `0x18003bea0`
- `0x18003c860`
- `0x18004d0d2`

## import_xrefs

- `MPRAPI!MprConfigBufferFree` at `0x180012a2c`
- `MPRAPI!MprConfigBufferFree` at `0x180012a4a`
- `MPRAPI!MprConfigBufferFree` at `0x180012b28`
- `MPRAPI!MprConfigBufferFree` at `0x180012b37`
- `MPRAPI!MprConfigBufferFree` at `0x180012a2c`
- `MPRAPI!MprConfigBufferFree` at `0x180012a4a`
- `MPRAPI!MprConfigBufferFree` at `0x180012b28`
- `MPRAPI!MprConfigBufferFree` at `0x180012b37`
- `MPRAPI!MprConfigInterfaceGetHandle` at `0x1800129c9`
- `MPRAPI!MprConfigInterfaceGetHandle` at `0x1800129c9`
- `MPRAPI!MprConfigInterfaceGetCustomInfoEx` at `0x1800129fc`
- `MPRAPI!MprConfigInterfaceGetCustomInfoEx` at `0x1800129fc`
- `MPRAPI!MprAdminServerDisconnect` at `0x180012b46`
- `MPRAPI!MprAdminServerDisconnect` at `0x180012b46`
- `MPRAPI!MprConfigServerConnect` at `0x180012989`
- `MPRAPI!MprConfigServerConnect` at `0x180012989`
- `MPRAPI!MprAdminServerConnect` at `0x180012a93`
- `MPRAPI!MprAdminServerConnect` at `0x180012a93`
- `MPRAPI!MprAdminInterfaceGetHandle` at `0x180012ac1`
- `MPRAPI!MprAdminInterfaceGetHandle` at `0x180012ac1`
- `MPRAPI!MprConfigInterfaceSetCustomInfoEx` at `0x180012a64`
- `MPRAPI!MprConfigInterfaceSetCustomInfoEx` at `0x180012a64`
- `MPRAPI!MprAdminInterfaceSetCustomInfoEx` at `0x180012aed`
- `MPRAPI!MprAdminInterfaceSetCustomInfoEx` at `0x180012aed`
- `MPRAPI!MprConfigServerDisconnect` at `0x180012b55`
- `MPRAPI!MprConfigServerDisconnect` at `0x180012b55`
- `rtutils!TracePrintfExA` at `0x18001294d`
- `rtutils!TracePrintfExA` at `0x180012b11`
- `rtutils!TracePrintfExA` at `0x18001294d`
- `rtutils!TracePrintfExA` at `0x180012b11`

## string_xrefs

- `0x1800129a4`: `EuClearCustomPolicy: MprConfigServerConnect error %d`
- `0x1800129e4`: `EuClearCustomPolicy: MprConfigInterfaceGetHandle error %d`
- `0x180012a17`: `EuClearCustomPolicy: MprConfigInterfaceGetCustomInfoEx error %d`
- `0x180012a7f`: `EuClearCustomPolicy: MprConfigInterfaceSetCustomInfoEx error %d`

## pseudocode

```c
__int64 __fastcall EuClearCustomPolicy(__int64 a1)
{
  WCHAR *v2; // rsi
  unsigned int v3; // ebx
  DWORD v4; // eax
  DWORD Handle; // eax
  unsigned int CustomInfo; // eax
  unsigned int v7; // eax
  DWORD v8; // eax
  DWORD v9; // eax
  unsigned int v10; // eax
  _DWORD v12[6]; // [rsp+20h] [rbp-60h] BYREF
  LPVOID pBuffer; // [rsp+38h] [rbp-48h]
  LPVOID v14; // [rsp+40h] [rbp-40h]
  HANDLE phMprConfig; // [rsp+C0h] [rbp+40h] BYREF
  MPR_SERVER_HANDLE phMprServer; // [rsp+C8h] [rbp+48h] BYREF
  HANDLE phRouterInterface; // [rsp+D0h] [rbp+50h] BYREF
  HANDLE phInterface; // [rsp+D8h] [rbp+58h] BYREF

  memset_0(v12, 0, 0x58u);
  phMprServer = 0;
  phInterface = 0;
  phMprConfig = 0;
  phRouterInterface = 0;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "EuClearCustomPolicy");
  memset_0(v12, 0, 0x58u);
  v2 = (WCHAR *)StrDup(*(STRSAFE_LPCWSTR *)(*(_QWORD *)(a1 + 872) + 8LL));
  if ( v2 )
  {
    v4 = MprConfigServerConnect(*(LPWSTR *)(a1 + 48), &phMprConfig);
    v3 = v4;
    if ( v4 )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "EuClearCustomPolicy: MprConfigServerConnect error %d", v4);
    }
    else
    {
      v12[0] = 5768705;
      v12[1] = 1;
      Handle = MprConfigInterfaceGetHandle(phMprConfig, v2, &phRouterInterface);
      v3 = Handle;
      if ( Handle )
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "EuClearCustomPolicy: MprConfigInterfaceGetHandle error %d", Handle);
      }
      else
      {
        CustomInfo = MprConfigInterfaceGetCustomInfoEx(phMprConfig, phRouterInterface, v12);
        v3 = CustomInfo;
        if ( CustomInfo )
        {
          if ( g_dwTraceId != -1 )
            TracePrintfExA(
              g_dwTraceId,
              0xCu,
              "EuClearCustomPolicy: MprConfigInterfaceGetCustomInfoEx error %d",
              CustomInfo);
        }
        else
        {
          if ( pBuffer )
          {
            MprConfigBufferFree(pBuffer);
            pBuffer = 0;
            v12[4] = 0;
          }
          if ( v14 )
          {
            MprConfigBufferFree(v14);
            v14 = 0;
          }
          v7 = MprConfigInterfaceSetCustomInfoEx(phMprConfig, phRouterInterface, v12);
          v3 = v7;
          if ( v7 )
          {
            if ( g_dwTraceId != -1 )
              TracePrintfExA(g_dwTraceId, 0xCu, "EuClearCustomPolicy: MprConfigInterfaceSetCustomInfoEx error %d", v7);
          }
          else
          {
            v8 = MprAdminServerConnect(*(LPWSTR *)(a1 + 48), &phMprServer);
            v3 = v8;
            if ( v8 )
            {
              if ( g_dwTraceId != -1 )
                TracePrintfExA(g_dwTraceId, 0xCu, "EuClearCustomPolicy: MprAdminServerConnect error %d", v8);
            }
            else
            {
              v9 = MprAdminInterfaceGetHandle(phMprServer, v2, &phInterface, 0);
              v3 = v9;
              if ( v9 )
              {
                if ( g_dwTraceId != -1 )
                  TracePrintfExA(g_dwTraceId, 0xCu, "EuClearCustomPolicy: MprAdminInterfaceGetHandle error %d", v9);
              }
              else
              {
                v10 = MprAdminInterfaceSetCustomInfoEx(phMprServer, phInterface, v12);
                v3 = v10;
                if ( v10 && g_dwTraceId != -1 )
                  TracePrintfExA(
                    g_dwTraceId,
                    0xCu,
                    "EuClearCustomPolicy: MprAdminInterfaceSetCustomInfoEx error %d",
                    v10);
              }
            }
          }
        }
      }
    }
    Free0(v2);
  }
  else
  {
    v3 = 8;
  }
  if ( pBuffer )
    MprConfigBufferFree(pBuffer);
  if ( v14 )
    MprConfigBufferFree(v14);
  if ( phMprServer )
    MprAdminServerDisconnect(phMprServer);
  if ( phMprConfig )
    MprConfigServerDisconnect(phMprConfig);
  return v3;
}

```

## disassembly

```asm
0x1800128e4  push    rbp
0x1800128e6  push    rbx
0x1800128e7  push    rsi
0x1800128e8  push    rdi
0x1800128e9  push    r12
0x1800128eb  push    r13
0x1800128ed  push    r15
0x1800128ef  mov     rbp, rsp
0x1800128f2  sub     rsp, 80h
0x1800128f9  mov     rdi, rcx
0x1800128fc  mov     r13d, 58h ; 'X'
0x180012902  mov     r8d, r13d; Size
0x180012905  lea     rcx, [rbp+var_60]; void *
0x180012909  xor     edx, edx; Val
0x18001290b  call    memset_0
0x180012910  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180012916  lea     r12d, [r13-4Ch]
0x18001291a  or      r15d, 0FFFFFFFFh
0x18001291e  mov     [rbp+phMprServer], 0
0x180012926  mov     [rbp+phInterface], 0
0x18001292e  mov     [rbp+phMprConfig], 0
0x180012936  mov     [rbp+phRouterInterface], 0
0x18001293e  cmp     ecx, r15d
0x180012941  jz      short loc_180012953
0x180012943  lea     r8, aEuclearcustomp; "EuClearCustomPolicy"
0x18001294a  mov     edx, r12d; dwFlags
0x18001294d  call    cs:__imp_TracePrintfExA
0x180012953  mov     r8, r13; Size
0x180012956  lea     rcx, [rbp+var_60]; void *
0x18001295a  xor     edx, edx; Val
0x18001295c  call    memset_0
0x180012961  mov     rcx, [rdi+368h]
0x180012968  mov     rcx, [rcx+8]; pszSrc
0x18001296c  call    StrDup
0x180012971  mov     rsi, rax
0x180012974  test    rax, rax
0x180012977  jnz     short loc_180012981
0x180012979  lea     ebx, [rax+8]
0x18001297c  jmp     loc_180012B1F
0x180012981  mov     rcx, [rdi+30h]; lpwsServerName
0x180012985  lea     rdx, [rbp+phMprConfig]; phMprConfig
0x180012989  call    cs:__imp_MprConfigServerConnect
0x18001298f  mov     ebx, eax
0x180012991  test    eax, eax
0x180012993  jz      short loc_1800129B0
0x180012995  mov     ecx, cs:g_dwTraceId
0x18001299b  cmp     ecx, r15d
0x18001299e  jz      loc_180012B17
0x1800129a4  lea     r8, aEuclearcustomp_1; "EuClearCustomPolicy: MprConfigServerCon"...
0x1800129ab  jmp     loc_180012B0B
0x1800129b0  mov     rcx, [rbp+phMprConfig]; hMprConfig
0x1800129b4  lea     r8, [rbp+phRouterInterface]; phRouterInterface
0x1800129b8  mov     rdx, rsi; lpwsInterfaceName
0x1800129bb  mov     [rbp+var_60], 580601h
0x1800129c2  mov     [rbp+var_5C], 1
0x1800129c9  call    cs:__imp_MprConfigInterfaceGetHandle
0x1800129cf  mov     ebx, eax
0x1800129d1  test    eax, eax
0x1800129d3  jz      short loc_1800129F0
0x1800129d5  mov     ecx, cs:g_dwTraceId
0x1800129db  cmp     ecx, r15d
0x1800129de  jz      loc_180012B17
0x1800129e4  lea     r8, aEuclearcustomp_4; "EuClearCustomPolicy: MprConfigInterface"...
0x1800129eb  jmp     loc_180012B0B
0x1800129f0  mov     rdx, [rbp+phRouterInterface]
0x1800129f4  lea     r8, [rbp+var_60]
0x1800129f8  mov     rcx, [rbp+phMprConfig]
0x1800129fc  call    cs:__imp_MprConfigInterfaceGetCustomInfoEx
0x180012a02  mov     ebx, eax
0x180012a04  test    eax, eax
0x180012a06  jz      short loc_180012A23
0x180012a08  mov     ecx, cs:g_dwTraceId
0x180012a0e  cmp     ecx, r15d
0x180012a11  jz      loc_180012B17
0x180012a17  lea     r8, aEuclearcustomp_6; "EuClearCustomPolicy: MprConfigInterface"...
0x180012a1e  jmp     loc_180012B0B
0x180012a23  mov     rcx, [rbp+pBuffer]; pBuffer
0x180012a27  test    rcx, rcx
0x180012a2a  jz      short loc_180012A41
0x180012a2c  call    cs:__imp_MprConfigBufferFree
0x180012a32  mov     [rbp+pBuffer], 0
0x180012a3a  mov     [rbp+var_50], 0
0x180012a41  mov     rcx, [rbp+var_40]; pBuffer
0x180012a45  test    rcx, rcx
0x180012a48  jz      short loc_180012A58
0x180012a4a  call    cs:__imp_MprConfigBufferFree
0x180012a50  mov     [rbp+var_40], 0
0x180012a58  mov     rdx, [rbp+phRouterInterface]
0x180012a5c  lea     r8, [rbp+var_60]
0x180012a60  mov     rcx, [rbp+phMprConfig]
0x180012a64  call    cs:__imp_MprConfigInterfaceSetCustomInfoEx
0x180012a6a  mov     ebx, eax
0x180012a6c  test    eax, eax
0x180012a6e  jz      short loc_180012A8B
0x180012a70  mov     ecx, cs:g_dwTraceId
0x180012a76  cmp     ecx, r15d
0x180012a79  jz      loc_180012B17
0x180012a7f  lea     r8, aEuclearcustomp_7; "EuClearCustomPolicy: MprConfigInterface"...
0x180012a86  jmp     loc_180012B0B
0x180012a8b  mov     rcx, [rdi+30h]; lpwsServerName
0x180012a8f  lea     rdx, [rbp+phMprServer]; phMprServer
0x180012a93  call    cs:__imp_MprAdminServerConnect
0x180012a99  mov     ebx, eax
0x180012a9b  test    eax, eax
0x180012a9d  jz      short loc_180012AB3
0x180012a9f  mov     ecx, cs:g_dwTraceId
0x180012aa5  cmp     ecx, r15d
0x180012aa8  jz      short loc_180012B17
0x180012aaa  lea     r8, aEuclearcustomp_5; "EuClearCustomPolicy: MprAdminServerConn"...
0x180012ab1  jmp     short loc_180012B0B
0x180012ab3  mov     rcx, [rbp+phMprServer]; hMprServer
0x180012ab7  lea     r8, [rbp+phInterface]; phInterface
0x180012abb  xor     r9d, r9d; fIncludeClientInterfaces
0x180012abe  mov     rdx, rsi; lpwsInterfaceName
0x180012ac1  call    cs:__imp_MprAdminInterfaceGetHandle
0x180012ac7  mov     ebx, eax
0x180012ac9  test    eax, eax
0x180012acb  jz      short loc_180012AE1
0x180012acd  mov     ecx, cs:g_dwTraceId
0x180012ad3  cmp     ecx, r15d
0x180012ad6  jz      short loc_180012B17
0x180012ad8  lea     r8, aEuclearcustomp_0; "EuClearCustomPolicy: MprAdminInterfaceG"...
0x180012adf  jmp     short loc_180012B0B
0x180012ae1  mov     rdx, [rbp+phInterface]
0x180012ae5  lea     r8, [rbp+var_60]
0x180012ae9  mov     rcx, [rbp+phMprServer]
0x180012aed  call    cs:__imp_MprAdminInterfaceSetCustomInfoEx
0x180012af3  mov     ebx, eax
0x180012af5  test    eax, eax
0x180012af7  jz      short loc_180012B17
0x180012af9  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180012aff  cmp     ecx, r15d
0x180012b02  jz      short loc_180012B17
0x180012b04  lea     r8, aEuclearcustomp_3; "EuClearCustomPolicy: MprAdminInterfaceS"...
0x180012b0b  mov     r9d, eax
0x180012b0e  mov     edx, r12d; dwFlags
0x180012b11  call    cs:__imp_TracePrintfExA
0x180012b17  mov     rcx, rsi
0x180012b1a  call    Free0
0x180012b1f  mov     rcx, [rbp+pBuffer]; pBuffer
0x180012b23  test    rcx, rcx
0x180012b26  jz      short loc_180012B2E
0x180012b28  call    cs:__imp_MprConfigBufferFree
0x180012b2e  mov     rcx, [rbp+var_40]; pBuffer
0x180012b32  test    rcx, rcx
0x180012b35  jz      short loc_180012B3D
0x180012b37  call    cs:__imp_MprConfigBufferFree
0x180012b3d  mov     rcx, [rbp+phMprServer]; hMprServer
0x180012b41  test    rcx, rcx
0x180012b44  jz      short loc_180012B4C
0x180012b46  call    cs:__imp_MprAdminServerDisconnect
0x180012b4c  mov     rcx, [rbp+phMprConfig]; hMprConfig
0x180012b50  test    rcx, rcx
0x180012b53  jz      short loc_180012B5B
0x180012b55  call    cs:__imp_MprConfigServerDisconnect
0x180012b5b  mov     eax, ebx
0x180012b5d  add     rsp, 80h
0x180012b64  pop     r15
0x180012b66  pop     r13
0x180012b68  pop     r12
0x180012b6a  pop     rdi
0x180012b6b  pop     rsi
0x180012b6c  pop     rbx
0x180012b6d  pop     rbp
0x180012b6e  retn
```
