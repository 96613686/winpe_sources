# APP_POOL_DATA_OBJECT_CS::SetEnvironmentFromConfigStoreData(INativeConfigurationElement *)

- ea: `0x180044f28`
- end: `0x18004536c`
- name: `?SetEnvironmentFromConfigStoreData@APP_POOL_DATA_OBJECT_CS@@QEAAJPEAVINativeConfigurationElement@@@Z`
- size: `1092`
- prototype: `__int64 __fastcall(APP_POOL_DATA_OBJECT_CS *__hidden this, struct INativeConfigurationElement *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180044950`

## callees

- `0x180044f28`
- `0x18005310c`
- `0x180053908`
- `0x180061060`
- `0x180062010`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18004533d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004533d`
- `iisutil!PuDbgPrint` at `0x180045090`
- `iisutil!PuDbgPrint` at `0x1800450f8`
- `iisutil!PuDbgPrint` at `0x180045090`
- `iisutil!PuDbgPrint` at `0x1800450f8`
- `iisutil!PuDbgPrintError` at `0x180044fdc`
- `iisutil!PuDbgPrintError` at `0x1800452cf`
- `iisutil!PuDbgPrintError` at `0x180044fdc`
- `iisutil!PuDbgPrintError` at `0x1800452cf`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180044f7b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180044f7b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004516a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004516a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180045189`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800451e1`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180045189`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800451e1`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x1800450a0`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x1800450a0`
- `iisutil!?Append@MULTISZ@@QEAAHAEAVSTRU@@@Z` at `0x1800451f8`
- `iisutil!?Append@MULTISZ@@QEAAHAEAVSTRU@@@Z` at `0x1800451f8`

## string_xrefs

- `0x180044fa5`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\apppoolstore_cs.cxx`
- `0x180044f9b`: `APP_POOL_DATA_OBJECT_CS::SetEnvironmentFromConfigStoreData`
- `0x180045084`: ` Number of AppPool environment variables to read %u\n`

## pseudocode

```c
__int64 __fastcall APP_POOL_DATA_OBJECT_CS::SetEnvironmentFromConfigStoreData(
        APP_POOL_DATA_OBJECT_CS *this,
        struct INativeConfigurationElement *a2)
{
  int v4; // eax
  int v5; // ebx
  unsigned int v6; // edi
  struct INativePropertyException *v7; // r9
  const unsigned __int16 *v8; // rdx
  struct CONFIG_ERROR *v9; // rdx
  struct INativePropertyException *v10; // rcx
  struct INativePropertyException *v12; // [rsp+30h] [rbp-59h] BYREF
  unsigned int v13; // [rsp+38h] [rbp-51h] BYREF
  unsigned __int16 *v14; // [rsp+40h] [rbp-49h] BYREF
  __int64 v15; // [rsp+48h] [rbp-41h] BYREF
  __int64 v16; // [rsp+50h] [rbp-39h] BYREF
  struct CONFIG_ERROR *v17; // [rsp+58h] [rbp-31h] BYREF
  __int64 v18; // [rsp+60h] [rbp-29h] BYREF
  _BYTE v19[32]; // [rsp+68h] [rbp-21h] BYREF
  _WORD *v20; // [rsp+88h] [rbp-1h]
  int v21; // [rsp+98h] [rbp+Fh]

  v16 = 0;
  v15 = 0;
  v18 = 0;
  v13 = 0;
  v12 = 0;
  v17 = 0;
  v14 = 0;
  STRU::STRU((STRU *)v19);
  v4 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, __int64 *))(*(_QWORD *)a2 + 32LL))(
         a2,
         L"environmentVariables",
         &v18);
  if ( v4 < 0 && (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
      417,
      "APP_POOL_DATA_OBJECT_CS::SetEnvironmentFromConfigStoreData",
      v4,
      " Failed getting environment variables element \n");
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 40LL))(v18, &v16);
  if ( v5 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
        425,
        "APP_POOL_DATA_OBJECT_CS::SetEnvironmentFromConfigStoreData",
        v5,
        " Failed getting environment variables collection \n");
    goto LABEL_40;
  }
  v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v16 + 24LL))(v16, &v13);
  if ( v5 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
        434,
        "APP_POOL_DATA_OBJECT_CS::SetEnvironmentFromConfigStoreData",
        v5,
        " Failed getting environment variables count \n");
    goto LABEL_40;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
      443,
      "APP_POOL_DATA_OBJECT_CS::SetEnvironmentFromConfigStoreData",
      " Number of AppPool environment variables to read %u\n",
      v13);
  MULTISZ::Reset((APP_POOL_DATA_OBJECT_CS *)((char *)this + 936));
  v6 = 0;
  if ( v13 )
  {
    while ( 1 )
    {
      *v20 = 0;
      v21 = 0;
      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
          460,
          "APP_POOL_DATA_OBJECT_CS::SetEnvironmentFromConfigStoreData",
          " Getting %d environment variable\n",
          v6);
      v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v16 + 32LL))(v16, v6, &v15);
      if ( v5 < 0 )
        break;
      v5 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int16 **, struct INativePropertyException **, _QWORD))(*(_QWORD *)v15 + 64LL))(
             v15,
             L"name",
             &v14,
             &v12,
             0);
      if ( v5 < 0 )
      {
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
            481,
            "APP_POOL_DATA_OBJECT_CS::SetEnvironmentFromConfigStoreData",
            v5,
            " Failed to get AppPool environment variable name. \n");
        goto LABEL_40;
      }
      v7 = v12;
      if ( v12 )
      {
        v8 = L"name";
        goto LABEL_30;
      }
      if ( !v14 )
        goto LABEL_42;
      v5 = STRU::Copy((STRU *)v19, v14);
      if ( v5 < 0 )
        goto LABEL_40;
      v14 = 0;
      v5 = STRU::Append((STRU *)v19, L"=");
      if ( v5 < 0 )
        goto LABEL_40;
      v5 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int16 **, struct INativePropertyException **, _QWORD))(*(_QWORD *)v15 + 64LL))(
             v15,
             L"value",
             &v14,
             &v12,
             0);
      if ( v5 < 0 )
      {
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
            526,
            "APP_POOL_DATA_OBJECT_CS::SetEnvironmentFromConfigStoreData",
            v5,
            " Failed to get AppPool environment variable value. \n");
        goto LABEL_40;
      }
      v7 = v12;
      if ( v12 )
      {
        v8 = L"value";
LABEL_30:
        CONFIG_ERROR::CreateAndInitWithString(&v17, v8, v14, v7);
        v9 = v17;
        if ( v17 )
        {
          *((_DWORD *)v17 + 2) = 51;
          CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v9);
        }
        v10 = v12;
        goto LABEL_41;
      }
      if ( !v14 )
        goto LABEL_42;
      v5 = STRU::Append((STRU *)v19, v14);
      if ( v5 < 0 )
        goto LABEL_40;
      if ( !MULTISZ::Append((APP_POOL_DATA_OBJECT_CS *)((char *)this + 936), (struct STRU *)v19) )
      {
        v5 = -2147024882;
        goto LABEL_40;
      }
      v14 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      ++v6;
      v15 = 0;
      if ( v6 >= v13 )
        goto LABEL_40;
    }
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
        468,
        "APP_POOL_DATA_OBJECT_CS::SetEnvironmentFromConfigStoreData",
        v5,
        " Failed to get a environment variable element \n");
  }
LABEL_40:
  v10 = v12;
  if ( v12 )
  {
LABEL_41:
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v10 + 16LL))(v10);
    v12 = 0;
  }
LABEL_42:
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  STRU::~STRU((STRU *)v19);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180044f28  mov     [rsp-8+arg_10], rbx
0x180044f2d  push    rbp
0x180044f2e  push    rsi
0x180044f2f  push    rdi
0x180044f30  push    r12
0x180044f32  push    r13
0x180044f34  push    r14
0x180044f36  push    r15
0x180044f38  lea     rbp, [rsp-27h]
0x180044f3d  sub     rsp, 0B0h
0x180044f44  mov     rax, cs:__security_cookie
0x180044f4b  xor     rax, rsp
0x180044f4e  mov     [rbp+57h+var_40], rax
0x180044f52  xor     r15d, r15d
0x180044f55  mov     rsi, rcx
0x180044f58  lea     rcx, [rbp+57h+var_78]
0x180044f5c  mov     [rbp+57h+var_90], r15
0x180044f60  mov     [rbp+57h+var_98], r15
0x180044f64  mov     rbx, rdx
0x180044f67  mov     [rbp+57h+var_80], r15
0x180044f6b  mov     [rbp+57h+var_A8], r15d
0x180044f6f  mov     [rbp+57h+var_B0], r15
0x180044f73  mov     [rbp+57h+var_88], r15
0x180044f77  mov     [rbp+57h+var_A0], r15
0x180044f7b  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180044f81  mov     rax, [rbx]
0x180044f84  lea     r8, [rbp+57h+var_80]
0x180044f88  lea     rdx, aEnvironmentvar_1; "environmentVariables"
0x180044f8f  mov     rcx, rbx
0x180044f92  mov     rax, [rax+20h]
0x180044f96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044f9b  lea     r12, aAppPoolDataObj_6; "APP_POOL_DATA_OBJECT_CS::SetEnvironment"...
0x180044fa2  mov     dil, 0Fh
0x180044fa5  lea     r13, aServercommonIn_62; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180044fac  test    eax, eax
0x180044fae  jns     short loc_180044FE2
0x180044fb0  test    byte ptr cs:g_dwDebugFlags, dil
0x180044fb7  jz      short loc_180044FE2
0x180044fb9  lea     rcx, aFailedGettingE_0; " Failed getting environment variables e"...
0x180044fc0  mov     r9, r12
0x180044fc3  mov     [rsp+0E0h+var_B8], rcx
0x180044fc8  mov     r8d, 1A1h
0x180044fce  mov     rcx, cs:g_pDebug
0x180044fd5  mov     rdx, r13
0x180044fd8  mov     dword ptr [rsp+0E0h+var_C0], eax
0x180044fdc  call    cs:__imp_PuDbgPrintError
0x180044fe2  mov     rcx, [rbp+57h+var_80]
0x180044fe6  lea     rdx, [rbp+57h+var_90]
0x180044fea  mov     rax, [rcx]
0x180044fed  mov     rax, [rax+28h]
0x180044ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044ff6  mov     ebx, eax
0x180044ff8  test    eax, eax
0x180044ffa  jns     short loc_18004501B
0x180044ffc  test    byte ptr cs:g_dwDebugFlags, dil
0x180045003  jz      loc_1800452D5
0x180045009  lea     rax, aFailedGettingE_1; " Failed getting environment variables c"...
0x180045010  mov     r8d, 1A9h
0x180045016  jmp     loc_1800452B9
0x18004501b  mov     rcx, [rbp+57h+var_90]
0x18004501f  lea     rdx, [rbp+57h+var_A8]
0x180045023  mov     rax, [rcx]
0x180045026  mov     rax, [rax+18h]
0x18004502a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004502f  mov     ebx, eax
0x180045031  test    eax, eax
0x180045033  jns     short loc_180045054
0x180045035  test    byte ptr cs:g_dwDebugFlags, dil
0x18004503c  jz      loc_1800452D5
0x180045042  lea     rax, aFailedGettingE_2; " Failed getting environment variables c"...
0x180045049  mov     r8d, 1B2h
0x18004504f  jmp     loc_1800452B9
0x180045054  mov     eax, cs:g_dwDebugFlags
0x18004505a  test    al, 3
0x18004505c  setnz   cl
0x18004505f  bt      eax, 1Eh
0x180045063  setb    al
0x180045066  test    al, cl
0x180045068  jz      short loc_180045096
0x18004506a  mov     eax, [rbp+57h+var_A8]
0x18004506d  mov     r9, r12
0x180045070  mov     rcx, cs:g_pDebug
0x180045077  mov     r8d, 1BBh
0x18004507d  mov     dword ptr [rsp+0E0h+var_B8], eax
0x180045081  mov     rdx, r13
0x180045084  lea     rax, aNumberOfApppoo; " Number of AppPool environment variable"...
0x18004508b  mov     [rsp+0E0h+var_C0], rax
0x180045090  call    cs:__imp_PuDbgPrint
0x180045096  lea     r14, [rsi+3A8h]
0x18004509d  mov     rcx, r14
0x1800450a0  call    cs:__imp_?Reset@MULTISZ@@QEAAXXZ; MULTISZ::Reset(void)
0x1800450a6  mov     edi, r15d
0x1800450a9  cmp     [rbp+57h+var_A8], r15d
0x1800450ad  jbe     loc_1800452D5
0x1800450b3  mov     rax, [rbp+57h+var_58]
0x1800450b7  mov     [rax], r15w
0x1800450bb  mov     eax, cs:g_dwDebugFlags
0x1800450c1  test    al, 3
0x1800450c3  mov     [rbp+57h+var_48], r15d
0x1800450c7  setnz   cl
0x1800450ca  bt      eax, 1Eh
0x1800450ce  setb    al
0x1800450d1  test    al, cl
0x1800450d3  jz      short loc_1800450FE
0x1800450d5  mov     rcx, cs:g_pDebug
0x1800450dc  lea     rax, aGettingDEnviro; " Getting %d environment variable\n"
0x1800450e3  mov     dword ptr [rsp+0E0h+var_B8], edi
0x1800450e7  mov     r9, r12
0x1800450ea  mov     r8d, 1CCh
0x1800450f0  mov     [rsp+0E0h+var_C0], rax
0x1800450f5  mov     rdx, r13
0x1800450f8  call    cs:__imp_PuDbgPrint
0x1800450fe  mov     rcx, [rbp+57h+var_90]
0x180045102  lea     r8, [rbp+57h+var_98]
0x180045106  mov     edx, edi
0x180045108  mov     rax, [rcx]
0x18004510b  mov     rax, [rax+20h]
0x18004510f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045114  mov     ebx, eax
0x180045116  test    eax, eax
0x180045118  js      loc_1800452A3
0x18004511e  mov     rcx, [rbp+57h+var_98]
0x180045122  lea     r9, [rbp+57h+var_B0]
0x180045126  lea     r8, [rbp+57h+var_A0]
0x18004512a  mov     [rsp+0E0h+var_C0], r15
0x18004512f  lea     rdx, aName_0; "name"
0x180045136  mov     rax, [rcx]
0x180045139  mov     rax, [rax+40h]
0x18004513d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045142  mov     ebx, eax
0x180045144  test    eax, eax
0x180045146  js      loc_18004528B
0x18004514c  mov     r9, [rbp+57h+var_B0]
0x180045150  test    r9, r9
0x180045153  jnz     loc_180045282
0x180045159  mov     rdx, [rbp+57h+var_A0]
0x18004515d  test    rdx, rdx
0x180045160  jz      loc_1800452EE
0x180045166  lea     rcx, [rbp+57h+var_78]
0x18004516a  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180045170  mov     ebx, eax
0x180045172  test    eax, eax
0x180045174  js      loc_1800452D5
0x18004517a  lea     rdx, asc_1800793C4; "="
0x180045181  mov     [rbp+57h+var_A0], r15
0x180045185  lea     rcx, [rbp+57h+var_78]
0x180045189  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18004518f  mov     ebx, eax
0x180045191  test    eax, eax
0x180045193  js      loc_1800452D5
0x180045199  mov     rcx, [rbp+57h+var_98]
0x18004519d  lea     r9, [rbp+57h+var_B0]
0x1800451a1  lea     r8, [rbp+57h+var_A0]
0x1800451a5  mov     [rsp+0E0h+var_C0], r15
0x1800451aa  lea     rdx, aValue; "value"
0x1800451b1  mov     rax, [rcx]
0x1800451b4  mov     rax, [rax+40h]
0x1800451b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800451bd  mov     ebx, eax
0x1800451bf  test    eax, eax
0x1800451c1  js      loc_18004526A
0x1800451c7  mov     r9, [rbp+57h+var_B0]; struct INativePropertyException *
0x1800451cb  test    r9, r9
0x1800451ce  jnz     short loc_180045234
0x1800451d0  mov     rdx, [rbp+57h+var_A0]
0x1800451d4  test    rdx, rdx
0x1800451d7  jz      loc_1800452EE
0x1800451dd  lea     rcx, [rbp+57h+var_78]
0x1800451e1  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800451e7  mov     ebx, eax
0x1800451e9  test    eax, eax
0x1800451eb  js      loc_1800452D5
0x1800451f1  lea     rdx, [rbp+57h+var_78]
0x1800451f5  mov     rcx, r14
0x1800451f8  call    cs:__imp_?Append@MULTISZ@@QEAAHAEAVSTRU@@@Z; MULTISZ::Append(STRU &)
0x1800451fe  test    eax, eax
0x180045200  jz      short loc_18004522A
0x180045202  mov     rcx, [rbp+57h+var_98]
0x180045206  mov     [rbp+57h+var_A0], r15
0x18004520a  mov     rax, [rcx]
0x18004520d  mov     rax, [rax+10h]
0x180045211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045216  inc     edi
0x180045218  mov     [rbp+57h+var_98], r15
0x18004521c  cmp     edi, [rbp+57h+var_A8]
0x18004521f  jb      loc_1800450B3
0x180045225  jmp     loc_1800452D5
0x18004522a  mov     ebx, 8007000Eh
0x18004522f  jmp     loc_1800452D5
0x180045234  lea     rdx, aValue; "value"
0x18004523b  mov     r8, [rbp+57h+var_A0]; unsigned __int16 *
0x18004523f  lea     rcx, [rbp+57h+var_88]; struct CONFIG_ERROR **
0x180045243  call    ?CreateAndInitWithString@CONFIG_ERROR@@SAXPEAPEAV1@PEBG1PEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithString(CONFIG_ERROR * *,ushort const *,ushort const *,INativePropertyException *)
0x180045248  mov     rdx, [rbp+57h+var_88]; struct CONFIG_ERROR *
0x18004524c  test    rdx, rdx
0x18004524f  jz      short loc_180045264
0x180045251  lea     rcx, [rsi+3E8h]; this
0x180045258  mov     dword ptr [rdx+8], 33h ; '3'
0x18004525f  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x180045264  mov     rcx, [rbp+57h+var_B0]
0x180045268  jmp     short loc_1800452DE
0x18004526a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180045271  jz      short loc_1800452D5
0x180045273  lea     rax, aFailedToGetApp; " Failed to get AppPool environment vari"...
0x18004527a  mov     r8d, 20Eh
0x180045280  jmp     short loc_1800452B9
0x180045282  lea     rdx, aName_0; "name"
0x180045289  jmp     short loc_18004523B
0x18004528b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180045292  jz      short loc_1800452D5
0x180045294  lea     rax, aFailedToGetApp_1; " Failed to get AppPool environment vari"...
0x18004529b  mov     r8d, 1E1h
0x1800452a1  jmp     short loc_1800452B9
0x1800452a3  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800452aa  jz      short loc_1800452D5
0x1800452ac  lea     rax, aFailedToGetAEn; " Failed to get a environment variable e"...
0x1800452b3  mov     r8d, 1D4h
0x1800452b9  mov     rcx, cs:g_pDebug
0x1800452c0  mov     r9, r12
0x1800452c3  mov     [rsp+0E0h+var_B8], rax
0x1800452c8  mov     rdx, r13
0x1800452cb  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x1800452cf  call    cs:__imp_PuDbgPrintError
0x1800452d5  mov     rcx, [rbp+57h+var_B0]
0x1800452d9  test    rcx, rcx
0x1800452dc  jz      short loc_1800452EE
0x1800452de  mov     rax, [rcx]
0x1800452e1  mov     rax, [rax+10h]
0x1800452e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800452ea  mov     [rbp+57h+var_B0], r15
0x1800452ee  mov     rcx, [rbp+57h+var_98]
0x1800452f2  test    rcx, rcx
0x1800452f5  jz      short loc_180045307
0x1800452f7  mov     rax, [rcx]
0x1800452fa  mov     rax, [rax+10h]
0x1800452fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045303  mov     [rbp+57h+var_98], r15
0x180045307  mov     rcx, [rbp+57h+var_90]
0x18004530b  test    rcx, rcx
0x18004530e  jz      short loc_180045320
0x180045310  mov     rax, [rcx]
0x180045313  mov     rax, [rax+10h]
0x180045317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004531c  mov     [rbp+57h+var_90], r15
0x180045320  mov     rcx, [rbp+57h+var_80]
0x180045324  test    rcx, rcx
0x180045327  jz      short loc_180045339
0x180045329  mov     rax, [rcx]
0x18004532c  mov     rax, [rax+10h]
0x180045330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045335  mov     [rbp+57h+var_80], r15
0x180045339  lea     rcx, [rbp+57h+var_78]
0x18004533d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180045343  mov     eax, ebx
0x180045345  mov     rcx, [rbp+57h+var_40]
0x180045349  xor     rcx, rsp; StackCookie
0x18004534c  call    __security_check_cookie
0x180045351  mov     rbx, [rsp+0E0h+arg_10]
0x180045359  add     rsp, 0B0h
0x180045360  pop     r15
0x180045362  pop     r14
0x180045364  pop     r13
0x180045366  pop     r12
0x180045368  pop     rdi
0x180045369  pop     rsi
0x18004536a  pop     rbp
0x18004536b  retn
```
