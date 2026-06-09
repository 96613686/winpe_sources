# CTerminalTypeHelper::IsSessionCompatible(_GUID,_GUID,int *)

- ea: `0x18004dbfc`
- end: `0x18004de49`
- name: `?IsSessionCompatible@CTerminalTypeHelper@@SAHU_GUID@@0PEAH@Z`
- size: `589`
- prototype: `__int64 __fastcall(struct _GUID *Buf1, UUID *Uuid, int *)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001fbe0`
- `0x180069f30`
- `0x18006dd70`

## callees

- `0x1800077a0`
- `0x18000af60`
- `0x18000bcc8`
- `0x18000c17c`
- `0x180020094`
- `0x18004dbfc`
- `0x18004e850`
- `0x180099590`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x18004dcf0`
- `RPCRT4!UuidToStringW` at `0x18004dd7b`
- `RPCRT4!UuidToStringW` at `0x18004dcf0`
- `RPCRT4!UuidToStringW` at `0x18004dd7b`
- `RPCRT4!RpcStringFreeW` at `0x18004dde6`
- `RPCRT4!RpcStringFreeW` at `0x18004ddfe`
- `RPCRT4!RpcStringFreeW` at `0x18004dde6`
- `RPCRT4!RpcStringFreeW` at `0x18004ddfe`

## string_xrefs

- `0x18004dd1e`: `ReconCompat`
- `0x18004dcc8`: `RegTerminal.OpenKey failed: 0x%x in %s`
- `0x18004dccf`: `CTerminalTypeHelper::IsSessionCompatible`
- `0x18004dd00`: `CTerminalTypeHelper::IsSessionCompatible FAILED to convert source GUID to string: 0x%x`
- `0x18004dd67`: `RegTerminalType.OpenKey failed: 0x%x in %s`
- `0x18004ddc0`: `RegTerminalType.ReadRegDWord failed: 0x%x in %s`
- `0x18004dd8b`: `CTerminalTypeHelper::IsSessionCompatible FAILED to convert target GUID to string: 0x%x`

## pseudocode

```c
__int64 __fastcall CTerminalTypeHelper::IsSessionCompatible(struct _GUID *Buf1, UUID *Uuid, int *a3)
{
  int v6; // edi
  unsigned int v7; // ebx
  signed int v8; // eax
  bool v9; // sf
  unsigned int v10; // eax
  signed int v11; // eax
  bool v12; // sf
  unsigned int v13; // eax
  signed int v14; // eax
  bool v15; // sf
  unsigned __int16 *v17; // [rsp+20h] [rbp-E0h]
  unsigned int v18; // [rsp+30h] [rbp-D0h] BYREF
  RPC_WSTR StringUuid; // [rsp+38h] [rbp-C8h] BYREF
  RPC_WSTR String; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v21[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v22; // [rsp+58h] [rbp-A8h]
  __int64 v23; // [rsp+60h] [rbp-A0h]
  int v24; // [rsp+68h] [rbp-98h]
  int v25; // [rsp+6Ch] [rbp-94h]
  _QWORD v26[2]; // [rsp+70h] [rbp-90h] BYREF
  int v27; // [rsp+80h] [rbp-80h]
  HKEY v28; // [rsp+88h] [rbp-78h]
  int v29; // [rsp+90h] [rbp-70h]
  int v30; // [rsp+94h] [rbp-6Ch]
  unsigned __int16 v31[256]; // [rsp+A0h] [rbp-60h] BYREF

  StringUuid = 0;
  String = 0;
  v29 = -1;
  v30 = -1;
  v24 = -1;
  v25 = -1;
  v6 = 0;
  v26[0] = &CRegistry::`vftable';
  v26[1] = 0;
  v27 = 0;
  v28 = 0;
  v21[0] = &CRegistry::`vftable';
  v21[1] = 0;
  v22 = 0;
  v23 = 0;
  if ( !memcmp_0(Buf1, Uuid, 0x10u) )
  {
    v7 = 1;
  }
  else
  {
    v7 = 0;
    v8 = CRegistry::OpenKey(
           (CRegistry *)v26,
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Control\\Terminal Server\\TerminalTypes",
           0x20019u,
           v17);
    v9 = v8 < 0;
    if ( v8 > 0 )
    {
      v8 = (unsigned __int16)v8 | 0x80070000;
      v9 = v8 < 0;
    }
    if ( v9 )
    {
      _DbgPrintMessage(
        8,
        "RegTerminal.OpenKey failed: 0x%x in %s",
        (unsigned int)v8,
        "CTerminalTypeHelper::IsSessionCompatible");
    }
    else
    {
      v10 = UuidToStringW(Buf1, &StringUuid);
      if ( v10 )
      {
        _DbgPrintMessage(
          8,
          "CTerminalTypeHelper::IsSessionCompatible FAILED to convert source GUID to string: 0x%x",
          v10);
      }
      else
      {
        StringCchPrintfW(v31, 0x100u, L"%ws\\%ws", StringUuid);
        v11 = CRegistry::OpenKey((CRegistry *)v21, v28, v31, 0x20019u, L"ReconCompat");
        v12 = v11 < 0;
        if ( v11 > 0 )
        {
          v11 = (unsigned __int16)v11 | 0x80070000;
          v12 = v11 < 0;
        }
        if ( v12 )
        {
          _DbgPrintMessage(
            8,
            "RegTerminalType.OpenKey failed: 0x%x in %s",
            (unsigned int)v11,
            "CTerminalTypeHelper::IsSessionCompatible");
        }
        else
        {
          v13 = UuidToStringW(Uuid, &String);
          if ( v13 )
          {
            _DbgPrintMessage(
              8,
              "CTerminalTypeHelper::IsSessionCompatible FAILED to convert target GUID to string: 0x%x",
              v13);
          }
          else
          {
            v18 = 0;
            v14 = CRegistry::ReadRegDWord((CRegistry *)v21, String, &v18);
            v15 = v14 < 0;
            if ( v14 > 0 )
            {
              v14 = (unsigned __int16)v14 | 0x80070000;
              v15 = v14 < 0;
            }
            if ( v15 )
            {
              _DbgPrintMessage(
                8,
                "RegTerminalType.ReadRegDWord failed: 0x%x in %s",
                (unsigned int)v14,
                "CTerminalTypeHelper::IsSessionCompatible");
            }
            else
            {
              v7 = 1;
              LOBYTE(v6) = v18 != 0;
            }
          }
        }
      }
    }
    if ( StringUuid )
      RpcStringFreeW(&StringUuid);
    if ( String )
      RpcStringFreeW(&String);
  }
  if ( a3 )
    *a3 = v6;
  CRegistry::~CRegistry((CRegistry *)v21);
  CRegistry::~CRegistry((CRegistry *)v26);
  return v7;
}

```

## disassembly

```asm
0x18004dbfc  push    rbp
0x18004dbfe  push    rbx
0x18004dbff  push    rsi
0x18004dc00  push    rdi
0x18004dc01  push    r12
0x18004dc03  push    r14
0x18004dc05  push    r15
0x18004dc07  lea     rbp, [rsp-1B0h]
0x18004dc0f  sub     rsp, 2B0h
0x18004dc16  mov     rax, cs:__security_cookie
0x18004dc1d  xor     rax, rsp
0x18004dc20  mov     [rbp+1E0h+var_40], rax
0x18004dc27  xor     r12d, r12d
0x18004dc2a  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x18004dc31  mov     r14, rcx
0x18004dc34  mov     [rsp+2E0h+StringUuid], r12
0x18004dc39  or      ecx, 0FFFFFFFFh
0x18004dc3c  mov     [rsp+2E0h+String], r12
0x18004dc41  mov     rsi, r8
0x18004dc44  mov     [rbp+1E0h+var_250], ecx
0x18004dc47  mov     [rbp+1E0h+var_24C], ecx
0x18004dc4a  lea     r8d, [r12+10h]; Size
0x18004dc4f  mov     [rsp+2E0h+var_278], ecx
0x18004dc53  mov     r15, rdx
0x18004dc56  mov     [rsp+2E0h+var_274], ecx
0x18004dc5a  mov     edi, r12d
0x18004dc5d  mov     rcx, r14; Buf1
0x18004dc60  mov     [rsp+2E0h+var_270], rax
0x18004dc65  mov     [rsp+2E0h+var_268], r12
0x18004dc6a  mov     [rbp+1E0h+var_260], r12d
0x18004dc6e  mov     [rbp+1E0h+var_258], r12
0x18004dc72  mov     [rsp+2E0h+var_298], rax
0x18004dc77  mov     [rsp+2E0h+var_290], r12
0x18004dc7c  mov     [rsp+2E0h+var_288], r12d
0x18004dc81  mov     [rsp+2E0h+var_280], r12
0x18004dc86  call    memcmp_0
0x18004dc8b  test    eax, eax
0x18004dc8d  jnz     short loc_18004DC97
0x18004dc8f  lea     ebx, [rax+1]
0x18004dc92  jmp     loc_18004DE0A
0x18004dc97  mov     r9d, 20019h; unsigned int
0x18004dc9d  lea     r8, aSystemCurrentc_11; "System\\CurrentControlSet\\Control\\Ter"...
0x18004dca4  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18004dcab  lea     rcx, [rsp+2E0h+var_270]; this
0x18004dcb0  mov     ebx, r12d
0x18004dcb3  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x18004dcb8  test    eax, eax
0x18004dcba  jle     short loc_18004DCC6
0x18004dcbc  movzx   eax, ax
0x18004dcbf  or      eax, 80070000h
0x18004dcc4  test    eax, eax
0x18004dcc6  jns     short loc_18004DCE8
0x18004dcc8  lea     rdx, aRegterminalOpe; "RegTerminal.OpenKey failed: 0x%x in %s"
0x18004dccf  lea     r9, aCterminaltypeh_2; "CTerminalTypeHelper::IsSessionCompatibl"...
0x18004dcd6  mov     r8d, eax
0x18004dcd9  mov     ecx, 8; int
0x18004dcde  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004dce3  jmp     loc_18004DDDA
0x18004dce8  lea     rdx, [rsp+2E0h+StringUuid]; StringUuid
0x18004dced  mov     rcx, r14; Uuid
0x18004dcf0  call    cs:__imp_UuidToStringW
0x18004dcf7  nop     dword ptr [rax+rax+00h]
0x18004dcfc  test    eax, eax
0x18004dcfe  jz      short loc_18004DD19
0x18004dd00  lea     rdx, aCterminaltypeh_0; "CTerminalTypeHelper::IsSessionCompatibl"...
0x18004dd07  mov     r8d, eax
0x18004dd0a  mov     ecx, 8; int
0x18004dd0f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004dd14  jmp     loc_18004DDDA
0x18004dd19  mov     r9, [rsp+2E0h+StringUuid]
0x18004dd1e  lea     rax, aReconcompat; "ReconCompat"
0x18004dd25  lea     r8, aWsWs; "%ws\\%ws"
0x18004dd2c  mov     [rsp+2E0h+var_2C0], rax; unsigned __int16 *
0x18004dd31  mov     edx, 100h; unsigned __int64
0x18004dd36  lea     rcx, [rbp+1E0h+var_240]; unsigned __int16 *
0x18004dd3a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004dd3f  mov     rdx, [rbp+1E0h+var_258]; HKEY
0x18004dd43  lea     r8, [rbp+1E0h+var_240]; unsigned __int16 *
0x18004dd47  mov     r9d, 20019h; unsigned int
0x18004dd4d  lea     rcx, [rsp+2E0h+var_298]; this
0x18004dd52  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x18004dd57  test    eax, eax
0x18004dd59  jle     short loc_18004DD65
0x18004dd5b  movzx   eax, ax
0x18004dd5e  or      eax, 80070000h
0x18004dd63  test    eax, eax
0x18004dd65  jns     short loc_18004DD73
0x18004dd67  lea     rdx, aRegterminaltyp; "RegTerminalType.OpenKey failed: 0x%x in"...
0x18004dd6e  jmp     loc_18004DCCF
0x18004dd73  lea     rdx, [rsp+2E0h+String]; StringUuid
0x18004dd78  mov     rcx, r15; Uuid
0x18004dd7b  call    cs:__imp_UuidToStringW
0x18004dd82  nop     dword ptr [rax+rax+00h]
0x18004dd87  test    eax, eax
0x18004dd89  jz      short loc_18004DD97
0x18004dd8b  lea     rdx, aCterminaltypeh_1; "CTerminalTypeHelper::IsSessionCompatibl"...
0x18004dd92  jmp     loc_18004DD07
0x18004dd97  mov     rdx, [rsp+2E0h+String]; lpValueName
0x18004dd9c  lea     r8, [rsp+2E0h+var_2B0]; unsigned int *
0x18004dda1  lea     rcx, [rsp+2E0h+var_298]; this
0x18004dda6  mov     [rsp+2E0h+var_2B0], r12d
0x18004ddab  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x18004ddb0  test    eax, eax
0x18004ddb2  jle     short loc_18004DDBE
0x18004ddb4  movzx   eax, ax
0x18004ddb7  or      eax, 80070000h
0x18004ddbc  test    eax, eax
0x18004ddbe  jns     short loc_18004DDCC
0x18004ddc0  lea     rdx, aRegterminaltyp_1; "RegTerminalType.ReadRegDWord failed: 0x"...
0x18004ddc7  jmp     loc_18004DCCF
0x18004ddcc  cmp     [rsp+2E0h+var_2B0], r12d
0x18004ddd1  mov     ebx, 1
0x18004ddd6  setnz   dil
0x18004ddda  cmp     [rsp+2E0h+StringUuid], r12
0x18004dddf  jz      short loc_18004DDF2
0x18004dde1  lea     rcx, [rsp+2E0h+StringUuid]; String
0x18004dde6  call    cs:__imp_RpcStringFreeW
0x18004dded  nop     dword ptr [rax+rax+00h]
0x18004ddf2  cmp     [rsp+2E0h+String], r12
0x18004ddf7  jz      short loc_18004DE0A
0x18004ddf9  lea     rcx, [rsp+2E0h+String]; String
0x18004ddfe  call    cs:__imp_RpcStringFreeW
0x18004de05  nop     dword ptr [rax+rax+00h]
0x18004de0a  test    rsi, rsi
0x18004de0d  jz      short loc_18004DE11
0x18004de0f  mov     [rsi], edi
0x18004de11  lea     rcx, [rsp+2E0h+var_298]; this
0x18004de16  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x18004de1b  lea     rcx, [rsp+2E0h+var_270]; this
0x18004de20  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x18004de25  mov     eax, ebx
0x18004de27  mov     rcx, [rbp+1E0h+var_40]
0x18004de2e  xor     rcx, rsp; StackCookie
0x18004de31  call    __security_check_cookie
0x18004de36  add     rsp, 2B0h
0x18004de3d  pop     r15
0x18004de3f  pop     r14
0x18004de41  pop     r12
0x18004de43  pop     rdi
0x18004de44  pop     rsi
0x18004de45  pop     rbx
0x18004de46  pop     rbp
0x18004de47  retn
```
