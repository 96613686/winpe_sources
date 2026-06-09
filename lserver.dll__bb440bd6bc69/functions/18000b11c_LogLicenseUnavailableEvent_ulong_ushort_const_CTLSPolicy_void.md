# LogLicenseUnavailableEvent(ulong,ushort const *,CTLSPolicy *,void *)

- ea: `0x18000b11c`
- end: `0x18000b50d`
- name: `?LogLicenseUnavailableEvent@@YAXKPEBGPEAVCTLSPolicy@@PEAX@Z`
- size: `1009`
- prototype: `void(unsigned int, const unsigned __int16 *, struct CTLSPolicy *, void *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180071d50`

## callees

- `0x180005665`
- `0x18000b11c`
- `0x18000cff0`
- `0x18001ae3c`
- `0x18001aea4`
- `0x180030a20`
- `0x180031f60`
- `0x180036604`
- `0x1800662a0`
- `0x18007dba8`
- `0x18007e2c0`
- `0x1800a0fb0`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18000b49a`
- `RPCRT4!RpcBindingFree` at `0x18000b49a`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18000b27a`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18000b27a`
- `RPCRT4!RpcStringBindingParseW` at `0x18000b2c7`
- `RPCRT4!RpcStringBindingParseW` at `0x18000b2c7`
- `RPCRT4!RpcStringFreeW` at `0x18000b4b2`
- `RPCRT4!RpcStringFreeW` at `0x18000b4ca`
- `RPCRT4!RpcStringFreeW` at `0x18000b4b2`
- `RPCRT4!RpcStringFreeW` at `0x18000b4ca`
- `RPCRT4!RpcBindingServerFromClient` at `0x18000b23f`
- `RPCRT4!RpcBindingServerFromClient` at `0x18000b23f`
- `KERNEL32!GetSystemDefaultLangID` at `0x18000b3b5`
- `KERNEL32!GetSystemDefaultLangID` at `0x18000b3b5`
- `KERNEL32!GetComputerNameW` at `0x18000b1d6`
- `KERNEL32!GetComputerNameW` at `0x18000b1d6`
- `KERNEL32!GetLastError` at `0x18000b200`
- `KERNEL32!GetLastError` at `0x18000b200`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall LogLicenseUnavailableEvent(int a1, const unsigned __int16 *a2, struct CTLSPolicy *a3, void *a4)
{
  RPC_STATUS v8; // eax
  _QWORD *v9; // rcx
  int v10; // edx
  int v11; // edx
  struct IRdlsDBConnection *v12; // rcx
  int v13; // ebx
  RPC_BINDING_HANDLE ServerBinding; // [rsp+30h] [rbp-D0h] BYREF
  RPC_WSTR StringBinding; // [rsp+38h] [rbp-C8h] BYREF
  RPC_WSTR NetworkAddr; // [rsp+40h] [rbp-C0h] BYREF
  DWORD nSize; // [rsp+48h] [rbp-B8h] BYREF
  struct IRdlsDBConnection *v18; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *String; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v20; // [rsp+60h] [rbp-A0h] BYREF
  int SystemDefaultLangID; // [rsp+68h] [rbp-98h]
  unsigned int v22; // [rsp+6Ch] [rbp-94h]
  _BYTE v23[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v24; // [rsp+78h] [rbp-88h]
  __int64 v25; // [rsp+98h] [rbp-68h]
  int v26; // [rsp+A0h] [rbp-60h]
  unsigned __int16 v27[525]; // [rsp+AA6h] [rbp+9A6h] BYREF
  WCHAR Buffer[8]; // [rsp+EC0h] [rbp+DC0h] BYREF
  __int128 v29; // [rsp+ED0h] [rbp+DD0h]

  ServerBinding = 0;
  StringBinding = 0;
  NetworkAddr = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      302,
      (unsigned int)&WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
      (unsigned int)L"LogLicenseUnavailableEvent",
      a1);
  *(_OWORD *)Buffer = 0;
  v29 = 0;
  nSize = 16;
  if ( GetComputerNameW(Buffer, &nSize) )
  {
    v8 = RpcBindingServerFromClient(0, &ServerBinding);
    if ( v8 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      {
        v10 = 304;
        goto LABEL_8;
      }
    }
    else
    {
      v8 = RpcBindingToStringBindingW(ServerBinding, &StringBinding);
      if ( v8 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        {
          v10 = 305;
          goto LABEL_8;
        }
      }
      else
      {
        v8 = RpcStringBindingParseW(StringBinding, 0, 0, &NetworkAddr, 0, 0);
        if ( v8 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
          {
            v10 = 306;
            goto LABEL_8;
          }
        }
        else
        {
          memset_0(v23, 0, 0xE50u);
          StringCchCopyW(v27, 0x100u, a2);
          v18 = 0;
          if ( (unsigned int)AllocateDBHandle(&v18, *(unsigned int *)&g_GeneralDbTimeout) )
          {
            v12 = g_RdlsDBWorkSpace;
            if ( *(_DWORD *)&g_bUseMultipleConnections )
              v12 = v18;
            v13 = TLSDBKeyPackFind((__int64 *)v12, v11, 4, (__int64)v23, (__int64)v23);
            FREEDBHANDLE(v18);
            if ( v13 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
                WPP_SF_SD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  307,
                  (unsigned int)&WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
                  (unsigned int)L"LogLicenseUnavailableEvent",
                  v13);
            }
            else
            {
              String = 0;
              v20 = v27;
              SystemDefaultLangID = GetSystemDefaultLangID();
              v22 = v27[257] + (v27[256] << 16);
              v8 = CTLSPolicy::PMLicenseRequest(a3, a4, 5u, &v20, (void **)&String, 1);
              if ( !v8 )
              {
                TLSLogLowLicenseWarning(v20, String, String + 512, NetworkAddr, v22, a1 == -1073217528);
                goto LABEL_37;
              }
              v9 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
              {
                v10 = 309;
                goto LABEL_8;
              }
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
          {
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              308,
              &WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
              L"LogLicenseUnavailableEvent");
          }
        }
      }
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    LOBYTE(v8) = GetLastError();
    v9 = WPP_GLOBAL_Control;
    v10 = 303;
LABEL_8:
    WPP_SF_SD(
      v9[2],
      v10,
      (unsigned int)&WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
      (unsigned int)L"LogLicenseUnavailableEvent",
      v8);
  }
LABEL_37:
  if ( ServerBinding )
    RpcBindingFree(&ServerBinding);
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  if ( NetworkAddr )
    RpcStringFreeW(&NetworkAddr);
  __LicensePack::~__LicensePack((__LicensePack *)v23);
}

```

## disassembly

```asm
0x18000b11c  mov     [rsp-8+arg_0], rbx
0x18000b121  mov     [rsp-8+arg_8], rsi
0x18000b126  push    rbp
0x18000b127  push    rdi
0x18000b128  push    r13
0x18000b12a  push    r14
0x18000b12c  push    r15
0x18000b12e  lea     rbp, [rsp-0DF0h]
0x18000b136  sub     rsp, 0EF0h
0x18000b13d  mov     rax, cs:__security_cookie
0x18000b144  xor     rax, rsp
0x18000b147  mov     [rbp+0E10h+var_30], rax
0x18000b14e  mov     r14, r9
0x18000b151  mov     rsi, r8
0x18000b154  mov     rbx, rdx
0x18000b157  mov     edi, ecx
0x18000b159  xor     r15d, r15d
0x18000b15c  mov     [rsp+0F10h+ServerBinding], r15
0x18000b161  mov     [rsp+0F10h+StringBinding], r15
0x18000b166  mov     [rsp+0F10h+NetworkAddr], r15
0x18000b16b  mov     [rsp+0F10h+var_E98], r15
0x18000b170  mov     [rbp+0E10h+var_E78], r15
0x18000b174  mov     [rbp+0E10h+var_E70], r15d
0x18000b178  lea     r13, WPP_GLOBAL_Control
0x18000b17f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b186  cmp     rcx, r13
0x18000b189  jz      short loc_18000B1B1
0x18000b18b  test    byte ptr [rcx+1Ch], 20h
0x18000b18f  jz      short loc_18000B1B1
0x18000b191  mov     edx, 12Eh
0x18000b196  mov     dword ptr [rsp+0F10h+Endpoint], edi
0x18000b19a  lea     r9, aLoglicenseunav; "LogLicenseUnavailableEvent"
0x18000b1a1  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x18000b1a8  mov     rcx, [rcx+10h]
0x18000b1ac  call    WPP_SF_SD
0x18000b1b1  xorps   xmm0, xmm0
0x18000b1b4  movups  xmmword ptr [rbp+0E10h+Buffer], xmm0
0x18000b1bb  movups  [rbp+0E10h+var_40], xmm0
0x18000b1c2  mov     [rsp+0F10h+nSize], 10h
0x18000b1ca  lea     rdx, [rsp+0F10h+nSize]; nSize
0x18000b1cf  lea     rcx, [rbp+0E10h+Buffer]; lpBuffer
0x18000b1d6  call    cs:__imp_GetComputerNameW
0x18000b1dd  nop     dword ptr [rax+rax+00h]
0x18000b1e2  test    eax, eax
0x18000b1e4  jnz     short loc_18000B238
0x18000b1e6  mov     rax, cs:WPP_GLOBAL_Control
0x18000b1ed  cmp     rax, r13
0x18000b1f0  jz      loc_18000B48E
0x18000b1f6  test    byte ptr [rax+1Ch], 20h
0x18000b1fa  jz      loc_18000B48E
0x18000b200  call    cs:__imp_GetLastError
0x18000b207  nop     dword ptr [rax+rax+00h]
0x18000b20c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b213  mov     edx, 12Fh
0x18000b218  mov     dword ptr [rsp+0F10h+Endpoint], eax
0x18000b21c  lea     r9, aLoglicenseunav; "LogLicenseUnavailableEvent"
0x18000b223  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x18000b22a  mov     rcx, [rcx+10h]
0x18000b22e  call    WPP_SF_SD
0x18000b233  jmp     loc_18000B48E
0x18000b238  lea     rdx, [rsp+0F10h+ServerBinding]; ServerBinding
0x18000b23d  xor     ecx, ecx; ClientBinding
0x18000b23f  call    cs:__imp_RpcBindingServerFromClient
0x18000b246  nop     dword ptr [rax+rax+00h]
0x18000b24b  test    eax, eax
0x18000b24d  jz      short loc_18000B270
0x18000b24f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b256  cmp     rcx, r13
0x18000b259  jz      loc_18000B48E
0x18000b25f  test    byte ptr [rcx+1Ch], 20h
0x18000b263  jz      loc_18000B48E
0x18000b269  mov     edx, 130h
0x18000b26e  jmp     short loc_18000B218
0x18000b270  lea     rdx, [rsp+0F10h+StringBinding]; StringBinding
0x18000b275  mov     rcx, [rsp+0F10h+ServerBinding]; Binding
0x18000b27a  call    cs:__imp_RpcBindingToStringBindingW
0x18000b281  nop     dword ptr [rax+rax+00h]
0x18000b286  test    eax, eax
0x18000b288  jz      short loc_18000B2AE
0x18000b28a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b291  cmp     rcx, r13
0x18000b294  jz      loc_18000B48E
0x18000b29a  test    byte ptr [rcx+1Ch], 20h
0x18000b29e  jz      loc_18000B48E
0x18000b2a4  mov     edx, 131h
0x18000b2a9  jmp     loc_18000B218
0x18000b2ae  mov     [rsp+0F10h+NetworkOptions], r15; NetworkOptions
0x18000b2b3  mov     [rsp+0F10h+Endpoint], r15; Endpoint
0x18000b2b8  lea     r9, [rsp+0F10h+NetworkAddr]; NetworkAddr
0x18000b2bd  xor     r8d, r8d; Protseq
0x18000b2c0  xor     edx, edx; ObjUuid
0x18000b2c2  mov     rcx, [rsp+0F10h+StringBinding]; StringBinding
0x18000b2c7  call    cs:__imp_RpcStringBindingParseW
0x18000b2ce  nop     dword ptr [rax+rax+00h]
0x18000b2d3  test    eax, eax
0x18000b2d5  jz      short loc_18000B2FB
0x18000b2d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b2de  cmp     rcx, r13
0x18000b2e1  jz      loc_18000B48E
0x18000b2e7  test    byte ptr [rcx+1Ch], 20h
0x18000b2eb  jz      loc_18000B48E
0x18000b2f1  mov     edx, 132h
0x18000b2f6  jmp     loc_18000B218
0x18000b2fb  xor     edx, edx; Val
0x18000b2fd  mov     r8d, 0E50h; Size
0x18000b303  lea     rcx, [rsp+0F10h+var_EA0]; void *
0x18000b308  call    memset_0
0x18000b30d  mov     r8, rbx; unsigned __int16 *
0x18000b310  mov     edx, 100h; unsigned __int64
0x18000b315  lea     rcx, [rbp+0E10h+var_46A]; unsigned __int16 *
0x18000b31c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b321  mov     [rsp+0F10h+var_EC0], r15
0x18000b326  mov     edx, cs:?g_GeneralDbTimeout@@3KA; unsigned int
0x18000b32c  lea     rcx, [rsp+0F10h+var_EC0]; struct IRdlsDBConnection **
0x18000b331  call    ?AllocateDBHandle@@YAHPEAPEAVIRdlsDBConnection@@K@Z; AllocateDBHandle(IRdlsDBConnection * *,ulong)
0x18000b336  test    eax, eax
0x18000b338  jz      loc_18000B460
0x18000b33e  mov     rcx, cs:?g_RdlsDBWorkSpace@@3PEAVIRdlsDBConnection@@EA; IRdlsDBConnection * g_RdlsDBWorkSpace
0x18000b345  cmp     cs:?g_bUseMultipleConnections@@3KA, r15d; ulong g_bUseMultipleConnections
0x18000b34c  cmovnz  rcx, [rsp+0F10h+var_EC0]
0x18000b352  lea     rax, [rsp+0F10h+var_EA0]
0x18000b357  mov     [rsp+0F10h+Endpoint], rax
0x18000b35c  lea     r9, [rsp+0F10h+var_EA0]
0x18000b361  mov     r8d, 4
0x18000b367  call    TLSDBKeyPackFind
0x18000b36c  mov     ebx, eax
0x18000b36e  mov     rcx, [rsp+0F10h+var_EC0]; struct IRdlsDBConnection *
0x18000b373  call    ?FREEDBHANDLE@@YAXPEAVIRdlsDBConnection@@@Z; FREEDBHANDLE(IRdlsDBConnection *)
0x18000b378  test    ebx, ebx
0x18000b37a  jz      short loc_18000B3A4
0x18000b37c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b383  cmp     rcx, r13
0x18000b386  jz      loc_18000B48E
0x18000b38c  test    byte ptr [rcx+1Ch], 20h
0x18000b390  jz      loc_18000B48E
0x18000b396  mov     edx, 133h
0x18000b39b  mov     dword ptr [rsp+0F10h+Endpoint], ebx
0x18000b39f  jmp     loc_18000B21C
0x18000b3a4  mov     [rsp+0F10h+String], r15
0x18000b3a9  lea     rax, [rbp+0E10h+var_46A]
0x18000b3b0  mov     [rsp+0F10h+var_EB0], rax
0x18000b3b5  call    cs:__imp_GetSystemDefaultLangID
0x18000b3bc  nop     dword ptr [rax+rax+00h]
0x18000b3c1  movzx   eax, ax
0x18000b3c4  mov     [rsp+0F10h+var_EA8], eax
0x18000b3c8  movzx   r8d, [rbp+0E10h+var_26A]
0x18000b3d0  shl     r8d, 10h
0x18000b3d4  movzx   eax, [rbp+0E10h+var_268]
0x18000b3db  add     r8d, eax
0x18000b3de  mov     [rsp+0F10h+var_EA4], r8d
0x18000b3e3  mov     dword ptr [rsp+0F10h+NetworkOptions], 1; int
0x18000b3eb  lea     rax, [rsp+0F10h+String]
0x18000b3f0  mov     [rsp+0F10h+Endpoint], rax; void **
0x18000b3f5  lea     r9, [rsp+0F10h+var_EB0]; void *
0x18000b3fa  mov     r8d, 5; unsigned int
0x18000b400  mov     rdx, r14; void *
0x18000b403  mov     rcx, rsi; this
0x18000b406  call    ?PMLicenseRequest@CTLSPolicy@@QEAAKPEAXKQEAXPEAPEAXH@Z; CTLSPolicy::PMLicenseRequest(void *,ulong,void * const,void * *,int)
0x18000b40b  test    eax, eax
0x18000b40d  jz      short loc_18000B42B
0x18000b40f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b416  cmp     rcx, r13
0x18000b419  jz      short loc_18000B48E
0x18000b41b  test    byte ptr [rcx+1Ch], 20h
0x18000b41f  jz      short loc_18000B48E
0x18000b421  mov     edx, 135h
0x18000b426  jmp     loc_18000B218
0x18000b42b  mov     eax, r15d
0x18000b42e  cmp     edi, 0C0080008h
0x18000b434  setz    al
0x18000b437  mov     rdx, [rsp+0F10h+String]; String
0x18000b43c  lea     r8, [rdx+400h]; unsigned __int16 *
0x18000b443  mov     dword ptr [rsp+0F10h+NetworkOptions], eax; int
0x18000b447  mov     eax, [rsp+0F10h+var_EA4]
0x18000b44b  mov     dword ptr [rsp+0F10h+Endpoint], eax; unsigned int
0x18000b44f  mov     r9, [rsp+0F10h+NetworkAddr]; unsigned __int16 *
0x18000b454  mov     rcx, [rsp+0F10h+var_EB0]; unsigned __int16 *
0x18000b459  call    ?TLSLogLowLicenseWarning@@YAXPEBG000KH@Z; TLSLogLowLicenseWarning(ushort const *,ushort const *,ushort const *,ushort const *,ulong,int)
0x18000b45e  jmp     short loc_18000B48E
0x18000b460  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b467  cmp     rcx, r13
0x18000b46a  jz      short loc_18000B48E
0x18000b46c  test    byte ptr [rcx+1Ch], 20h
0x18000b470  jz      short loc_18000B48E
0x18000b472  mov     edx, 134h
0x18000b477  lea     r9, aLoglicenseunav; "LogLicenseUnavailableEvent"
0x18000b47e  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x18000b485  mov     rcx, [rcx+10h]
0x18000b489  call    WPP_SF_S
0x18000b48e  cmp     [rsp+0F10h+ServerBinding], r15
0x18000b493  jz      short loc_18000B4A6
0x18000b495  lea     rcx, [rsp+0F10h+ServerBinding]; Binding
0x18000b49a  call    cs:__imp_RpcBindingFree
0x18000b4a1  nop     dword ptr [rax+rax+00h]
0x18000b4a6  cmp     [rsp+0F10h+StringBinding], r15
0x18000b4ab  jz      short loc_18000B4BE
0x18000b4ad  lea     rcx, [rsp+0F10h+StringBinding]; String
0x18000b4b2  call    cs:__imp_RpcStringFreeW
0x18000b4b9  nop     dword ptr [rax+rax+00h]
0x18000b4be  cmp     [rsp+0F10h+NetworkAddr], r15
0x18000b4c3  jz      short loc_18000B4D7
0x18000b4c5  lea     rcx, [rsp+0F10h+NetworkAddr]; String
0x18000b4ca  call    cs:__imp_RpcStringFreeW
0x18000b4d1  nop     dword ptr [rax+rax+00h]
0x18000b4d6  nop
0x18000b4d7  lea     rcx, [rsp+0F10h+var_EA0]; this
0x18000b4dc  call    ??1__LicensePack@@QEAA@XZ; __LicensePack::~__LicensePack(void)
0x18000b4e1  mov     rcx, [rbp+0E10h+var_30]
0x18000b4e8  xor     rcx, rsp; StackCookie
0x18000b4eb  call    __security_check_cookie
0x18000b4f0  lea     r11, [rsp+0F10h+var_20]
0x18000b4f8  mov     rbx, [r11+30h]
0x18000b4fc  mov     rsi, [r11+38h]
0x18000b500  mov     rsp, r11
0x18000b503  pop     r15
0x18000b505  pop     r14
0x18000b507  pop     r13
0x18000b509  pop     rdi
0x18000b50a  pop     rbp
0x18000b50b  retn
```
