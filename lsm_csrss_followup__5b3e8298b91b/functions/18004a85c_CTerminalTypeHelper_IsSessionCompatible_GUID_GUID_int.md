# CTerminalTypeHelper::IsSessionCompatible(_GUID,_GUID,int *)

- ea: `0x18004a85c`
- end: `0x18004aa90`
- name: `?IsSessionCompatible@CTerminalTypeHelper@@SAHU_GUID@@0PEAH@Z`
- size: `564`
- prototype: `__int64 __fastcall(struct _GUID *Buf1, UUID *Uuid, int *)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e430`
- `0x180066260`
- `0x180069f40`

## callees

- `0x1800074c0`
- `0x180017da0`
- `0x180018200`
- `0x18001e8e0`
- `0x18001ea44`
- `0x18004a85c`
- `0x18004b460`
- `0x180094040`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x18004a950`
- `RPCRT4!UuidToStringW` at `0x18004a9d5`
- `RPCRT4!UuidToStringW` at `0x18004a950`
- `RPCRT4!UuidToStringW` at `0x18004a9d5`
- `RPCRT4!RpcStringFreeW` at `0x18004aa3a`
- `RPCRT4!RpcStringFreeW` at `0x18004aa4c`
- `RPCRT4!RpcStringFreeW` at `0x18004aa3a`
- `RPCRT4!RpcStringFreeW` at `0x18004aa4c`

## string_xrefs

- `0x18004a978`: `ReconCompat`
- `0x18004a92f`: `CTerminalTypeHelper::IsSessionCompatible`
- `0x18004a95a`: `CTerminalTypeHelper::IsSessionCompatible FAILED to convert source GUID to string: 0x%x`
- `0x18004a928`: `RegTerminal.OpenKey failed: 0x%x in %s`
- `0x18004a9df`: `CTerminalTypeHelper::IsSessionCompatible FAILED to convert target GUID to string: 0x%x`
- `0x18004a9c1`: `RegTerminalType.OpenKey failed: 0x%x in %s`
- `0x18004aa14`: `RegTerminalType.ReadRegDWord failed: 0x%x in %s`

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
0x18004a85c  push    rbp
0x18004a85e  push    rbx
0x18004a85f  push    rsi
0x18004a860  push    rdi
0x18004a861  push    r12
0x18004a863  push    r14
0x18004a865  push    r15
0x18004a867  lea     rbp, [rsp-1B0h]
0x18004a86f  sub     rsp, 2B0h
0x18004a876  mov     rax, cs:__security_cookie
0x18004a87d  xor     rax, rsp
0x18004a880  mov     [rbp+1E0h+var_40], rax
0x18004a887  xor     r12d, r12d
0x18004a88a  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x18004a891  mov     r14, rcx
0x18004a894  mov     [rsp+2E0h+StringUuid], r12
0x18004a899  or      ecx, 0FFFFFFFFh
0x18004a89c  mov     [rsp+2E0h+String], r12
0x18004a8a1  mov     rsi, r8
0x18004a8a4  mov     [rbp+1E0h+var_250], ecx
0x18004a8a7  mov     [rbp+1E0h+var_24C], ecx
0x18004a8aa  lea     r8d, [r12+10h]; Size
0x18004a8af  mov     [rsp+2E0h+var_278], ecx
0x18004a8b3  mov     r15, rdx
0x18004a8b6  mov     [rsp+2E0h+var_274], ecx
0x18004a8ba  mov     edi, r12d
0x18004a8bd  mov     rcx, r14; Buf1
0x18004a8c0  mov     [rsp+2E0h+var_270], rax
0x18004a8c5  mov     [rsp+2E0h+var_268], r12
0x18004a8ca  mov     [rbp+1E0h+var_260], r12d
0x18004a8ce  mov     [rbp+1E0h+var_258], r12
0x18004a8d2  mov     [rsp+2E0h+var_298], rax
0x18004a8d7  mov     [rsp+2E0h+var_290], r12
0x18004a8dc  mov     [rsp+2E0h+var_288], r12d
0x18004a8e1  mov     [rsp+2E0h+var_280], r12
0x18004a8e6  call    memcmp_0
0x18004a8eb  test    eax, eax
0x18004a8ed  jnz     short loc_18004A8F7
0x18004a8ef  lea     ebx, [rax+1]
0x18004a8f2  jmp     loc_18004AA52
0x18004a8f7  mov     r9d, 20019h; unsigned int
0x18004a8fd  lea     r8, aSystemCurrentc_11; "System\\CurrentControlSet\\Control\\Ter"...
0x18004a904  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18004a90b  lea     rcx, [rsp+2E0h+var_270]; this
0x18004a910  mov     ebx, r12d
0x18004a913  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x18004a918  test    eax, eax
0x18004a91a  jle     short loc_18004A926
0x18004a91c  movzx   eax, ax
0x18004a91f  or      eax, 80070000h
0x18004a924  test    eax, eax
0x18004a926  jns     short loc_18004A948
0x18004a928  lea     rdx, aRegterminalOpe; "RegTerminal.OpenKey failed: 0x%x in %s"
0x18004a92f  lea     r9, aCterminaltypeh_2; "CTerminalTypeHelper::IsSessionCompatibl"...
0x18004a936  mov     r8d, eax
0x18004a939  mov     ecx, 8; int
0x18004a93e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004a943  jmp     loc_18004AA2E
0x18004a948  lea     rdx, [rsp+2E0h+StringUuid]; StringUuid
0x18004a94d  mov     rcx, r14; Uuid
0x18004a950  call    cs:__imp_UuidToStringW
0x18004a956  test    eax, eax
0x18004a958  jz      short loc_18004A973
0x18004a95a  lea     rdx, aCterminaltypeh_0; "CTerminalTypeHelper::IsSessionCompatibl"...
0x18004a961  mov     r8d, eax
0x18004a964  mov     ecx, 8; int
0x18004a969  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004a96e  jmp     loc_18004AA2E
0x18004a973  mov     r9, [rsp+2E0h+StringUuid]
0x18004a978  lea     rax, aReconcompat; "ReconCompat"
0x18004a97f  lea     r8, aWsWs; "%ws\\%ws"
0x18004a986  mov     [rsp+2E0h+var_2C0], rax; unsigned __int16 *
0x18004a98b  mov     edx, 100h; unsigned __int64
0x18004a990  lea     rcx, [rbp+1E0h+var_240]; unsigned __int16 *
0x18004a994  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004a999  mov     rdx, [rbp+1E0h+var_258]; HKEY
0x18004a99d  lea     r8, [rbp+1E0h+var_240]; unsigned __int16 *
0x18004a9a1  mov     r9d, 20019h; unsigned int
0x18004a9a7  lea     rcx, [rsp+2E0h+var_298]; this
0x18004a9ac  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x18004a9b1  test    eax, eax
0x18004a9b3  jle     short loc_18004A9BF
0x18004a9b5  movzx   eax, ax
0x18004a9b8  or      eax, 80070000h
0x18004a9bd  test    eax, eax
0x18004a9bf  jns     short loc_18004A9CD
0x18004a9c1  lea     rdx, aRegterminaltyp; "RegTerminalType.OpenKey failed: 0x%x in"...
0x18004a9c8  jmp     loc_18004A92F
0x18004a9cd  lea     rdx, [rsp+2E0h+String]; StringUuid
0x18004a9d2  mov     rcx, r15; Uuid
0x18004a9d5  call    cs:__imp_UuidToStringW
0x18004a9db  test    eax, eax
0x18004a9dd  jz      short loc_18004A9EB
0x18004a9df  lea     rdx, aCterminaltypeh_1; "CTerminalTypeHelper::IsSessionCompatibl"...
0x18004a9e6  jmp     loc_18004A961
0x18004a9eb  mov     rdx, [rsp+2E0h+String]; lpValueName
0x18004a9f0  lea     r8, [rsp+2E0h+var_2B0]; unsigned int *
0x18004a9f5  lea     rcx, [rsp+2E0h+var_298]; this
0x18004a9fa  mov     [rsp+2E0h+var_2B0], r12d
0x18004a9ff  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x18004aa04  test    eax, eax
0x18004aa06  jle     short loc_18004AA12
0x18004aa08  movzx   eax, ax
0x18004aa0b  or      eax, 80070000h
0x18004aa10  test    eax, eax
0x18004aa12  jns     short loc_18004AA20
0x18004aa14  lea     rdx, aRegterminaltyp_1; "RegTerminalType.ReadRegDWord failed: 0x"...
0x18004aa1b  jmp     loc_18004A92F
0x18004aa20  cmp     [rsp+2E0h+var_2B0], r12d
0x18004aa25  mov     ebx, 1
0x18004aa2a  setnz   dil
0x18004aa2e  cmp     [rsp+2E0h+StringUuid], r12
0x18004aa33  jz      short loc_18004AA40
0x18004aa35  lea     rcx, [rsp+2E0h+StringUuid]; String
0x18004aa3a  call    cs:__imp_RpcStringFreeW
0x18004aa40  cmp     [rsp+2E0h+String], r12
0x18004aa45  jz      short loc_18004AA52
0x18004aa47  lea     rcx, [rsp+2E0h+String]; String
0x18004aa4c  call    cs:__imp_RpcStringFreeW
0x18004aa52  test    rsi, rsi
0x18004aa55  jz      short loc_18004AA59
0x18004aa57  mov     [rsi], edi
0x18004aa59  lea     rcx, [rsp+2E0h+var_298]; this
0x18004aa5e  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x18004aa63  lea     rcx, [rsp+2E0h+var_270]; this
0x18004aa68  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x18004aa6d  mov     eax, ebx
0x18004aa6f  mov     rcx, [rbp+1E0h+var_40]
0x18004aa76  xor     rcx, rsp; StackCookie
0x18004aa79  call    __security_check_cookie
0x18004aa7e  add     rsp, 2B0h
0x18004aa85  pop     r15
0x18004aa87  pop     r14
0x18004aa89  pop     r12
0x18004aa8b  pop     rdi
0x18004aa8c  pop     rsi
0x18004aa8d  pop     rbx
0x18004aa8e  pop     rbp
0x18004aa8f  retn
```
