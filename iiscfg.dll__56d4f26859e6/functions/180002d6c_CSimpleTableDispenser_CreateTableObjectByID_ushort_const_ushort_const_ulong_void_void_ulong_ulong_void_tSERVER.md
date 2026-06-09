# CSimpleTableDispenser::CreateTableObjectByID(ushort const *,ushort const *,ulong,void *,void *,ulong,ulong,void *,tSERVERWIRINGMETARow *,void * *)

- ea: `0x180002d6c`
- end: `0x1800031ab`
- name: `?CreateTableObjectByID@CSimpleTableDispenser@@AEAAJPEBG0KPEAX1KK1PEAUtSERVERWIRINGMETARow@@PEAPEAX@Z`
- size: `1087`
- prototype: `__int64 __fastcall(CSimpleTableDispenser *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, void *, void *, unsigned int, unsigned int, void *, struct tSERVERWIRINGMETARow *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003fd0`

## callees

- `0x180001f70`
- `0x180002970`
- `0x180002d6c`
- `0x1800047f0`
- `0x180030010`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x180002e3e`
- `IisRTL!PuDbgPrint` at `0x180002f47`
- `IisRTL!PuDbgPrint` at `0x180002fc9`
- `IisRTL!PuDbgPrint` at `0x180003159`
- `IisRTL!PuDbgPrint` at `0x180002e3e`
- `IisRTL!PuDbgPrint` at `0x180002f47`
- `IisRTL!PuDbgPrint` at `0x180002fc9`
- `IisRTL!PuDbgPrint` at `0x180003159`

## string_xrefs

- `0x180002e32`: `inetsrv\iis\mb\config\src\core\dispenser\cstdisp.cpp`
- `0x180002f27`: `inetsrv\iis\mb\config\src\core\dispenser\cstdisp.cpp`
- `0x180002fc2`: `inetsrv\iis\mb\config\src\core\dispenser\cstdisp.cpp`
- `0x180003152`: `inetsrv\iis\mb\config\src\core\dispenser\cstdisp.cpp`
- `0x180002e2b`: `CSimpleTableDispenser::CreateTableObjectByID`
- `0x180002f1a`: `CSimpleTableDispenser::CreateTableObjectByID`
- `0x180002fb0`: `CSimpleTableDispenser::CreateTableObjectByID`
- `0x180003140`: `CSimpleTableDispenser::CreateTableObjectByID`
- `0x180002fa9`: `Error: Can't have simple plugins with a fully-fledged interceptor`
- `0x180003011`: `Error: Creation of the read plugin failed`
- `0x180003054`: `Error: Creation of the write plugin failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSimpleTableDispenser::CreateTableObjectByID(
        CSimpleTableDispenser *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        void *a5,
        void *a6,
        unsigned int a7,
        unsigned int a8,
        void *a9,
        struct tSERVERWIRINGMETARow *a10,
        void **a11)
{
  void **v11; // r14
  int *v14; // rax
  int SimpleObjectByID; // ebx
  _DWORD *v16; // rax
  int v17; // eax
  int v18; // ecx
  int v19; // ecx
  int v20; // eax
  int v21; // edi
  void *v23; // [rsp+88h] [rbp-29h] BYREF
  void *v24; // [rsp+90h] [rbp-21h] BYREF
  void *v25; // [rsp+98h] [rbp-19h] BYREF
  __int64 v26; // [rsp+A0h] [rbp-11h] BYREF
  struct IShellInitialize *v27[8]; // [rsp+A8h] [rbp-9h] BYREF

  v11 = a11;
  v27[0] = 0;
  *a11 = 0;
  v14 = (int *)*((_QWORD *)a10 + 6);
  v26 = 0;
  v25 = 0;
  v24 = 0;
  v23 = 0;
  if ( *v14 )
  {
    if ( (a8 & 2) == 0 && (**((_BYTE **)a10 + 8) & 0x21) == 0 )
    {
      SimpleObjectByID = 0;
      *v11 = a9;
      goto LABEL_41;
    }
    SimpleObjectByID = DllGetSimpleObjectByID(*v14, &IID_ISimpleTableInterceptor, &v23);
    if ( SimpleObjectByID < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\config\\src\\core\\dispenser\\cstdisp.cpp",
          818,
          "CSimpleTableDispenser::CreateTableObjectByID",
          "Creation of the interceptor failed");
      goto LABEL_41;
    }
    if ( (**(int (__fastcall ***)(void *, GUID *, __int64 *))v23)(v23, &IID_IInterceptorPlugin, &v26) < 0 )
    {
      v16 = (_DWORD *)*((_QWORD *)a10 + 2);
      a11 = 0;
      if ( *v16 || **((_DWORD **)a10 + 4) )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\mb\\config\\src\\core\\dispenser\\cstdisp.cpp",
            832,
            "CSimpleTableDispenser::CreateTableObjectByID",
            "Error: Can't have simple plugins with a fully-fledged interceptor");
        SimpleObjectByID = -2145318897;
      }
      else
      {
        v17 = (*(__int64 (__fastcall **)(void *, const unsigned __int16 *, const unsigned __int16 *, _QWORD, void *, void *, unsigned int, unsigned int, CSimpleTableDispenser *, _QWORD, void *, void ***))(*(_QWORD *)v23 + 24LL))(
                v23,
                a2,
                a3,
                a4,
                a5,
                a6,
                a7,
                a8,
                this,
                *((_QWORD *)a10 + 9),
                a9,
                &a11);
        SimpleObjectByID = v17;
        if ( !v17 || v17 == -2145318895 )
        {
          if ( (*(int (__fastcall **)(void **, GUID *, void **))*a11)(a11, &IID_ISimpleTableWrite2, v11) >= 0 )
            (*((void (__fastcall **)(void **))*a11 + 2))(a11);
          else
            *v11 = a11;
        }
        else if ( v17 != -2145318896 && (g_dwDebugFlags & 3) != 0 )
        {
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\mb\\config\\src\\core\\dispenser\\cstdisp.cpp",
            844,
            "CSimpleTableDispenser::CreateTableObjectByID",
            "Intercept method failed on interceptor number %d",
            **((_DWORD **)a10 + 6));
        }
      }
      goto LABEL_41;
    }
  }
  if ( (a8 & 0x10000) != 0 )
    goto LABEL_33;
  v18 = **((_DWORD **)a10 + 2);
  if ( v18 )
  {
    SimpleObjectByID = DllGetSimpleObjectByID(v18, &IID_ISimplePlugin, &v25);
    if ( SimpleObjectByID < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\config\\src\\core\\dispenser\\cstdisp.cpp",
          872,
          "CSimpleTableDispenser::CreateTableObjectByID",
          "Error: Creation of the read plugin failed");
      goto LABEL_41;
    }
  }
  v19 = **((_DWORD **)a10 + 4);
  if ( v19
    && (a8 & 2) != 0
    && (SimpleObjectByID = DllGetSimpleObjectByID(v19, &IID_ISimplePlugin, &v24), SimpleObjectByID < 0) )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\config\\src\\core\\dispenser\\cstdisp.cpp",
        886,
        "CSimpleTableDispenser::CreateTableObjectByID",
        "Error: Creation of the write plugin failed");
  }
  else
  {
LABEL_33:
    SimpleObjectByID = CreateShell(v27);
    if ( SimpleObjectByID >= 0 )
    {
      v20 = (*(__int64 (__fastcall **)(struct IShellInitialize *, const unsigned __int16 *, const unsigned __int16 *, _QWORD, void *, void *, unsigned int, unsigned int, CSimpleTableDispenser *, _QWORD, void *, __int64, void *, void *, void **))(*(_QWORD *)v27[0] + 24LL))(
              v27[0],
              a2,
              a3,
              a4,
              a5,
              a6,
              a7,
              a8,
              this,
              *((_QWORD *)a10 + 9),
              a9,
              v26,
              v25,
              v24,
              v11);
      v21 = v20;
      if ( (v20 <= -2145318897 || (unsigned int)(v20 + 2145318894) <= 0x7FDEF7ED) && (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\config\\src\\core\\dispenser\\cstdisp.cpp",
          911,
          "CSimpleTableDispenser::CreateTableObjectByID",
          "Error: Initialization of the shell failed");
      SimpleObjectByID = v21;
    }
    else if ( (g_dwDebugFlags & 3) != 0 )
    {
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\config\\src\\core\\dispenser\\cstdisp.cpp",
        899,
        "CSimpleTableDispenser::CreateTableObjectByID",
        "Error: Creation of the shell failed");
    }
  }
LABEL_41:
  ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(&v23);
  ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(&v24);
  ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(&v25);
  ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(&v26);
  ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(v27);
  return (unsigned int)SimpleObjectByID;
}

```

## disassembly

```asm
0x180002d6c  mov     rax, rsp
0x180002d6f  mov     [rax+18h], rbx
0x180002d73  mov     [rax+10h], rdx
0x180002d77  mov     [rax+8], rcx
0x180002d7b  push    rbp
0x180002d7c  push    rsi
0x180002d7d  push    rdi
0x180002d7e  push    r12
0x180002d80  push    r13
0x180002d82  push    r14
0x180002d84  push    r15
0x180002d86  lea     rbp, [rax-3Fh]
0x180002d8a  sub     rsp, 0B0h
0x180002d91  mov     r14, [rbp+37h+arg_50]
0x180002d98  xor     edx, edx
0x180002d9a  mov     rdi, [rbp+37h+arg_48]
0x180002da1  mov     r12d, r9d
0x180002da4  mov     r15d, [rbp+37h+arg_38]
0x180002da8  mov     r13, r8
0x180002dab  mov     esi, r15d
0x180002dae  mov     [rbp+37h+var_40], rdx
0x180002db2  mov     [r14], rdx
0x180002db5  and     esi, 2
0x180002db8  mov     rax, [rdi+30h]
0x180002dbc  mov     [rbp+37h+var_48], rdx
0x180002dc0  mov     [rbp+37h+var_50], rdx
0x180002dc4  mov     [rbp+37h+var_58], rdx
0x180002dc8  mov     [rbp+37h+var_60], rdx
0x180002dcc  mov     ecx, [rax]
0x180002dce  test    ecx, ecx
0x180002dd0  jz      loc_180002FD9
0x180002dd6  test    esi, esi
0x180002dd8  jnz     short loc_180002DF4
0x180002dda  mov     rax, [rdi+40h]
0x180002dde  test    byte ptr [rax], 21h
0x180002de1  jnz     short loc_180002DF4
0x180002de3  mov     rax, [rbp+37h+arg_40]
0x180002dea  mov     ebx, edx
0x180002dec  mov     [r14], rax
0x180002def  jmp     loc_180003161
0x180002df4  lea     r8, [rbp+37h+var_60]
0x180002df8  lea     rdx, IID_ISimpleTableInterceptor
0x180002dff  call    DllGetSimpleObjectByID
0x180002e04  mov     ebx, eax
0x180002e06  test    eax, eax
0x180002e08  jns     short loc_180002E49
0x180002e0a  test    byte ptr cs:g_dwDebugFlags, 3
0x180002e11  jz      loc_180003161
0x180002e17  lea     rax, aCreationOfTheI; "Creation of the interceptor failed"
0x180002e1e  mov     r8d, 332h
0x180002e24  mov     rcx, cs:g_pDebug
0x180002e2b  lea     r9, aCsimpletabledi; "CSimpleTableDispenser::CreateTableObjec"...
0x180002e32  lea     rdx, aInetsrvIisMbCo_15; "inetsrv\\iis\\mb\\config\\src\\core\\di"...
0x180002e39  mov     [rsp+0E0h+var_C0], rax
0x180002e3e  call    cs:__imp_PuDbgPrint
0x180002e44  jmp     loc_180003161
0x180002e49  mov     rcx, [rbp+37h+var_60]
0x180002e4d  lea     r8, [rbp+37h+var_48]
0x180002e51  lea     rdx, IID_IInterceptorPlugin
0x180002e58  mov     rax, [rcx]
0x180002e5b  mov     rax, [rax]
0x180002e5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e63  xor     edx, edx
0x180002e65  test    eax, eax
0x180002e67  jns     loc_180002FD9
0x180002e6d  mov     rax, [rdi+10h]
0x180002e71  mov     [rbp+37h+arg_50], rdx
0x180002e78  cmp     [rax], edx
0x180002e7a  jnz     loc_180002F99
0x180002e80  mov     rax, [rdi+20h]
0x180002e84  cmp     [rax], edx
0x180002e86  jnz     loc_180002F99
0x180002e8c  mov     rdx, [rdi+48h]
0x180002e90  mov     r9d, r12d
0x180002e93  mov     rcx, [rbp+37h+var_60]
0x180002e97  mov     r8, r13
0x180002e9a  mov     rax, [rcx]
0x180002e9d  mov     r10, [rax+18h]
0x180002ea1  lea     rax, [rbp+37h+arg_50]
0x180002ea8  mov     [rsp+0E0h+var_88], rax
0x180002ead  mov     rax, [rbp+37h+arg_40]
0x180002eb4  mov     [rsp+0E0h+var_90], rax
0x180002eb9  mov     rax, [rbp+37h+arg_0]
0x180002ebd  mov     [rsp+0E0h+var_98], rdx
0x180002ec2  mov     edx, [rbp+37h+arg_30]
0x180002ec5  mov     [rsp+0E0h+var_A0], rax
0x180002eca  mov     rax, r10
0x180002ecd  mov     dword ptr [rsp+0E0h+var_A8], r15d
0x180002ed2  mov     [rsp+0E0h+var_B0], edx
0x180002ed6  mov     rdx, [rbp+37h+arg_28]
0x180002eda  mov     qword ptr [rsp+0E0h+var_B8], rdx
0x180002edf  mov     rdx, [rbp+37h+arg_20]
0x180002ee3  mov     [rsp+0E0h+var_C0], rdx
0x180002ee8  mov     rdx, [rbp+37h+arg_8]
0x180002eec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ef1  mov     ebx, eax
0x180002ef3  test    eax, eax
0x180002ef5  jz      short loc_180002F52
0x180002ef7  cmp     eax, 80210811h
0x180002efc  jz      short loc_180002F52
0x180002efe  cmp     eax, 80210810h
0x180002f03  jz      loc_180003161
0x180002f09  test    byte ptr cs:g_dwDebugFlags, 3
0x180002f10  jz      loc_180003161
0x180002f16  mov     rax, [rdi+30h]
0x180002f1a  lea     r9, aCsimpletabledi; "CSimpleTableDispenser::CreateTableObjec"...
0x180002f21  mov     r8d, 34Ch
0x180002f27  lea     rdx, aInetsrvIisMbCo_15; "inetsrv\\iis\\mb\\config\\src\\core\\di"...
0x180002f2e  mov     ecx, [rax]
0x180002f30  lea     rax, aInterceptMetho; "Intercept method failed on interceptor "...
0x180002f37  mov     [rsp+0E0h+var_B8], ecx
0x180002f3b  mov     rcx, cs:g_pDebug
0x180002f42  mov     [rsp+0E0h+var_C0], rax
0x180002f47  call    cs:__imp_PuDbgPrint
0x180002f4d  jmp     loc_180003161
0x180002f52  mov     rcx, [rbp+37h+arg_50]
0x180002f59  lea     rdx, IID_ISimpleTableWrite2
0x180002f60  mov     r8, r14
0x180002f63  mov     rax, [rcx]
0x180002f66  mov     rax, [rax]
0x180002f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f6e  test    eax, eax
0x180002f70  jns     short loc_180002F81
0x180002f72  mov     rax, [rbp+37h+arg_50]
0x180002f79  mov     [r14], rax
0x180002f7c  jmp     loc_180003161
0x180002f81  mov     rcx, [rbp+37h+arg_50]
0x180002f88  mov     rax, [rcx]
0x180002f8b  mov     rax, [rax+10h]
0x180002f8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f94  jmp     loc_180003161
0x180002f99  test    byte ptr cs:g_dwDebugFlags, 3
0x180002fa0  jz      short loc_180002FCF
0x180002fa2  mov     rcx, cs:g_pDebug
0x180002fa9  lea     rax, aErrorCanTHaveS; "Error: Can't have simple plugins with a"...
0x180002fb0  lea     r9, aCsimpletabledi; "CSimpleTableDispenser::CreateTableObjec"...
0x180002fb7  mov     [rsp+0E0h+var_C0], rax
0x180002fbc  mov     r8d, 340h
0x180002fc2  lea     rdx, aInetsrvIisMbCo_15; "inetsrv\\iis\\mb\\config\\src\\core\\di"...
0x180002fc9  call    cs:__imp_PuDbgPrint
0x180002fcf  mov     ebx, 8021080Fh
0x180002fd4  jmp     loc_180003161
0x180002fd9  bt      r15d, 10h
0x180002fde  jb      loc_180003066
0x180002fe4  mov     rax, [rdi+10h]
0x180002fe8  mov     ecx, [rax]
0x180002fea  test    ecx, ecx
0x180002fec  jz      short loc_180003023
0x180002fee  lea     r8, [rbp+37h+var_50]
0x180002ff2  lea     rdx, IID_ISimplePlugin
0x180002ff9  call    DllGetSimpleObjectByID
0x180002ffe  mov     ebx, eax
0x180003000  test    eax, eax
0x180003002  jns     short loc_180003023
0x180003004  test    byte ptr cs:g_dwDebugFlags, 3
0x18000300b  jz      loc_180003161
0x180003011  lea     rax, aErrorCreationO_0; "Error: Creation of the read plugin fail"...
0x180003018  mov     r8d, 368h
0x18000301e  jmp     loc_180002E24
0x180003023  mov     rax, [rdi+20h]
0x180003027  mov     ecx, [rax]
0x180003029  test    ecx, ecx
0x18000302b  jz      short loc_180003066
0x18000302d  test    esi, esi
0x18000302f  jz      short loc_180003066
0x180003031  lea     r8, [rbp+37h+var_58]
0x180003035  lea     rdx, IID_ISimplePlugin
0x18000303c  call    DllGetSimpleObjectByID
0x180003041  mov     ebx, eax
0x180003043  test    eax, eax
0x180003045  jns     short loc_180003066
0x180003047  test    byte ptr cs:g_dwDebugFlags, 3
0x18000304e  jz      loc_180003161
0x180003054  lea     rax, aErrorCreationO; "Error: Creation of the write plugin fai"...
0x18000305b  mov     r8d, 376h
0x180003061  jmp     loc_180002E24
0x180003066  lea     rcx, [rbp+37h+var_40]; struct IShellInitialize **
0x18000306a  call    ?CreateShell@@YAJPEAPEAUIShellInitialize@@@Z; CreateShell(IShellInitialize * *)
0x18000306f  mov     ebx, eax
0x180003071  test    eax, eax
0x180003073  jns     short loc_180003094
0x180003075  test    byte ptr cs:g_dwDebugFlags, 3
0x18000307c  jz      loc_180003161
0x180003082  lea     rax, aErrorCreationO_1; "Error: Creation of the shell failed"
0x180003089  mov     r8d, 383h
0x18000308f  jmp     loc_180002E24
0x180003094  mov     r11, [rbp+37h+var_40]
0x180003098  mov     r9d, r12d
0x18000309b  mov     rcx, [rbp+37h+var_58]
0x18000309f  mov     rdx, [rbp+37h+var_50]
0x1800030a3  mov     r8, [rbp+37h+var_48]
0x1800030a7  mov     rax, [r11]
0x1800030aa  mov     [rsp+70h], r14
0x1800030af  mov     [rsp+0E0h+var_78], rcx
0x1800030b4  mov     rcx, r11
0x1800030b7  mov     [rsp+0E0h+var_80], rdx
0x1800030bc  mov     r10, [rax+18h]
0x1800030c0  mov     rdx, [rdi+48h]
0x1800030c4  mov     rax, [rbp+37h+arg_40]
0x1800030cb  mov     [rsp+0E0h+var_88], r8
0x1800030d0  mov     r8, r13
0x1800030d3  mov     [rsp+0E0h+var_90], rax
0x1800030d8  mov     rax, [rbp+37h+arg_0]
0x1800030dc  mov     [rsp+0E0h+var_98], rdx
0x1800030e1  mov     edx, [rbp+37h+arg_30]
0x1800030e4  mov     [rsp+0E0h+var_A0], rax
0x1800030e9  mov     rax, r10
0x1800030ec  mov     dword ptr [rsp+0E0h+var_A8], r15d
0x1800030f1  mov     [rsp+0E0h+var_B0], edx
0x1800030f5  mov     rdx, [rbp+37h+arg_28]
0x1800030f9  mov     qword ptr [rsp+0E0h+var_B8], rdx
0x1800030fe  mov     rdx, [rbp+37h+arg_20]
0x180003102  mov     [rsp+0E0h+var_C0], rdx
0x180003107  mov     rdx, [rbp+37h+arg_8]
0x18000310b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003110  mov     ebx, 8021080Fh
0x180003115  mov     edi, eax
0x180003117  cmp     eax, ebx
0x180003119  jle     short loc_180003129
0x18000311b  lea     ecx, [rax+7FDEF7EEh]
0x180003121  cmp     ecx, 7FDEF7EDh
0x180003127  ja      short loc_18000315F
0x180003129  test    byte ptr cs:g_dwDebugFlags, 3
0x180003130  jz      short loc_18000315F
0x180003132  mov     rcx, cs:g_pDebug
0x180003139  lea     rax, aErrorInitializ; "Error: Initialization of the shell fail"...
0x180003140  lea     r9, aCsimpletabledi; "CSimpleTableDispenser::CreateTableObjec"...
0x180003147  mov     [rsp+0E0h+var_C0], rax
0x18000314c  mov     r8d, 38Fh
0x180003152  lea     rdx, aInetsrvIisMbCo_15; "inetsrv\\iis\\mb\\config\\src\\core\\di"...
0x180003159  call    cs:__imp_PuDbgPrint
0x18000315f  mov     ebx, edi
0x180003161  lea     rcx, [rbp+37h+var_60]
0x180003165  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x18000316a  lea     rcx, [rbp+37h+var_58]
0x18000316e  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x180003173  lea     rcx, [rbp+37h+var_50]
0x180003177  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x18000317c  lea     rcx, [rbp+37h+var_48]
0x180003180  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x180003185  lea     rcx, [rbp+37h+var_40]
0x180003189  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x18000318e  mov     eax, ebx
0x180003190  mov     rbx, [rsp+0E0h+arg_10]
0x180003198  add     rsp, 0B0h
0x18000319f  pop     r15
0x1800031a1  pop     r14
0x1800031a3  pop     r13
0x1800031a5  pop     r12
0x1800031a7  pop     rdi
0x1800031a8  pop     rsi
0x1800031a9  pop     rbp
0x1800031aa  retn
```
