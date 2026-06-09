# GetAdditionalInventory(Windows::Compat::Inventory::IInventoryDataReceiver *)

- ea: `0x180029efc`
- end: `0x18002a4f3`
- name: `?GetAdditionalInventory@@YAJPEAVIInventoryDataReceiver@Inventory@Compat@Windows@@@Z`
- size: `1527`
- prototype: `__int64 __fastcall(struct Windows::Compat::Inventory::IInventoryDataReceiver *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18002a500`

## callees

- `0x180005e40`
- `0x180006d02`
- `0x180007014`
- `0x1800279b4`
- `0x180029efc`
- `0x18003af48`
- `0x18003b560`
- `0x18006041c`
- `0x180061690`
- `0x180061754`
- `0x180066c10`
- `0x18010d8dc`
- `0x180116010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x180029fe9`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x180029fe9`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180029fb1`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180029fb1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002a47e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002a47e`

## string_xrefs

- `0x180029ffd`: `0x%08x CoInitializeSecurity failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetAdditionalInventory(struct Windows::Compat::Inventory::IInventoryDataReceiver *a1)
{
  bool v2; // r14
  HRESULT v3; // eax
  HRESULT v4; // ebx
  FILE *v5; // rax
  FILE *v6; // rax
  FILE *v7; // rax
  int PingBackInfo; // eax
  int v9; // ebx
  int v10; // esi
  wchar_t *v11; // rbx
  wchar_t *p_String2; // rdx
  int v13; // esi
  wchar_t *v14; // rbx
  wchar_t *v15; // rdx
  int v16; // esi
  wchar_t *v17; // rbx
  wchar_t *v18; // rdx
  int v19; // esi
  wchar_t *v20; // rbx
  wchar_t *v21; // rdx
  int v22; // esi
  wchar_t *v23; // rbx
  wchar_t *v24; // rdx
  int MemoryInfo; // eax
  const char *v26; // rdi
  __int64 v27; // rsi
  FILE *v28; // rax
  FILE *v29; // rax
  FILE *v30; // rax
  FILE *v31; // rax
  FILE *v32; // rax
  FILE *v33; // rax
  __int64 dwAuthnLevel; // [rsp+20h] [rbp-E0h]
  void **v36; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v37; // [rsp+58h] [rbp-A8h]
  wchar_t *v38; // [rsp+60h] [rbp-A0h]
  wchar_t String2; // [rsp+68h] [rbp-98h] BYREF
  void **v40; // [rsp+70h] [rbp-90h] BYREF
  __int64 v41; // [rsp+78h] [rbp-88h]
  wchar_t *v42; // [rsp+80h] [rbp-80h]
  wchar_t v43; // [rsp+88h] [rbp-78h] BYREF
  void **v44; // [rsp+90h] [rbp-70h] BYREF
  __int64 v45; // [rsp+98h] [rbp-68h]
  wchar_t *v46; // [rsp+A0h] [rbp-60h]
  wchar_t v47; // [rsp+A8h] [rbp-58h] BYREF
  void **v48; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v49; // [rsp+B8h] [rbp-48h]
  wchar_t *v50; // [rsp+C0h] [rbp-40h]
  wchar_t v51; // [rsp+C8h] [rbp-38h] BYREF
  void **v52; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v53; // [rsp+D8h] [rbp-28h]
  wchar_t *v54; // [rsp+E0h] [rbp-20h]
  wchar_t v55; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int64 v56[2]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int64 v57[2]; // [rsp+100h] [rbp+0h]
  unsigned __int64 v58; // [rsp+110h] [rbp+10h]

  *(_OWORD *)v56 = 0;
  *(_OWORD *)v57 = 0;
  v58 = 0;
  v36 = &WString::`vftable';
  v38 = 0;
  String2 = 0;
  v37 = 0;
  WString::Assign((WString *)&v36, 0);
  v40 = &WString::`vftable';
  v42 = 0;
  v43 = 0;
  v41 = 0;
  v44 = &WString::`vftable';
  v46 = 0;
  v47 = 0;
  v45 = 0;
  v48 = &WString::`vftable';
  v50 = 0;
  v51 = 0;
  v49 = 0;
  v52 = &WString::`vftable';
  v54 = 0;
  v55 = 0;
  v53 = 0;
  v2 = CoInitializeEx(0, 2u) >= 0;
  v3 = CoInitializeSecurity(0, -1, 0, 0, 0, 3u, 0, 0, 0);
  v4 = v3;
  if ( v3 < 0 )
  {
    AslLogCallPrintf(2, "GetAdditionalInventory", 562, "0x%08x CoInitializeSecurity failed", v3);
    if ( EnableDevInvStdErrLog )
    {
      v5 = o___acrt_iob_func_0(2u);
      fprintf(v5, "Warning: %s, %u: ", "GetAdditionalInventory", 562);
      v6 = o___acrt_iob_func_0(2u);
      fprintf(v6, "0x%08x CoInitializeSecurity failed", v4);
      v7 = o___acrt_iob_func_0(2u);
      fprintf(v7, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(50331648, "0x%08x CoInitializeSecurity failed", v4);
  }
  PingBackInfo = CDevInventory::GetPingBackInfo((struct _SYSTEMSPECPINGBACKINFO *)&v36);
  v9 = PingBackInfo;
  if ( PingBackInfo < 0 )
  {
    v26 = "[0x%08x] GetPingBackInfo failed";
    v27 = 595;
    AslLogCallPrintf(2, "GetAdditionalInventory", 595, "[0x%08x] GetPingBackInfo failed", PingBackInfo);
    if ( EnableDevInvStdErrLog )
    {
      v31 = o___acrt_iob_func_0(2u);
      fprintf(v31, "Error: %s, %u: ", "GetAdditionalInventory", 595);
      v32 = o___acrt_iob_func_0(2u);
      fprintf(v32, "[0x%08x] GetPingBackInfo failed", v9);
      v33 = o___acrt_iob_func_0(2u);
      fprintf(v33, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, "[0x%08x] GetPingBackInfo failed", (unsigned int)v9);
    goto LABEL_64;
  }
  v9 = (**(__int64 (__fastcall ***)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *))a1)(
         a1,
         L"PingBackInfo");
  if ( v9 >= 0 )
  {
    v10 = v37;
    v11 = v38;
    if ( !v38 || (p_String2 = v38, !(_DWORD)v37) )
      p_String2 = &String2;
    if ( !wcscmp_0(L"FailedToGetValue", p_String2) )
      goto LABEL_70;
    if ( !v11 || !v10 )
      v11 = &String2;
    v9 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, wchar_t *))(*(_QWORD *)a1 + 8LL))(
           a1,
           L"manufacturer",
           v11);
    if ( v9 >= 0 )
    {
LABEL_70:
      v13 = v41;
      v14 = v42;
      if ( !v42 || (v15 = v42, !(_DWORD)v41) )
        v15 = &v43;
      if ( !wcscmp_0(L"FailedToGetValue", v15) )
        goto LABEL_71;
      if ( !v14 || !v13 )
        v14 = &v43;
      v9 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, wchar_t *))(*(_QWORD *)a1 + 8LL))(
             a1,
             L"model",
             v14);
      if ( v9 >= 0 )
      {
LABEL_71:
        v16 = v45;
        v17 = v46;
        if ( !v46 || (v18 = v46, !(_DWORD)v45) )
          v18 = &v47;
        if ( !wcscmp_0(L"FailedToGetValue", v18) )
          goto LABEL_72;
        if ( !v17 || !v16 )
          v17 = &v47;
        v9 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, wchar_t *))(*(_QWORD *)a1 + 8LL))(
               a1,
               L"biosName",
               v17);
        if ( v9 >= 0 )
        {
LABEL_72:
          v19 = v49;
          v20 = v50;
          if ( !v50 || (v21 = v50, !(_DWORD)v49) )
            v21 = &v51;
          if ( !wcscmp_0(L"FailedToGetValue", v21) )
            goto LABEL_73;
          if ( !v20 || !v19 )
            v20 = &v51;
          v9 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, wchar_t *))(*(_QWORD *)a1 + 8LL))(
                 a1,
                 L"biosVersion",
                 v20);
          if ( v9 >= 0 )
          {
LABEL_73:
            v22 = v53;
            v23 = v54;
            if ( !v54 || (v24 = v54, !(_DWORD)v53) )
              v24 = &v55;
            if ( !wcscmp_0(L"FailedToGetValue", v24) )
              goto LABEL_48;
            if ( !v23 || !v22 )
              v23 = &v55;
            v9 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, wchar_t *))(*(_QWORD *)a1 + 8LL))(
                   a1,
                   L"biosDate",
                   v23);
            if ( v9 >= 0 )
            {
LABEL_48:
              MemoryInfo = CDevInventory::GetMemoryInfo((struct _SYSTEMSPECMEMORYINFO *)v56);
              v9 = MemoryInfo;
              if ( MemoryInfo < 0 )
              {
                v26 = "[0x%08x] GetMemoryInfo failed";
                v27 = 602;
                AslLogCallPrintf(2, "GetAdditionalInventory", 602, "[0x%08x] GetMemoryInfo failed", MemoryInfo);
                if ( EnableDevInvStdErrLog )
                {
                  v28 = o___acrt_iob_func_0(2u);
                  fprintf(v28, "Error: %s, %u: ", "GetAdditionalInventory", 602);
                  v29 = o___acrt_iob_func_0(2u);
                  fprintf(v29, "[0x%08x] GetMemoryInfo failed", v9);
                  v30 = o___acrt_iob_func_0(2u);
                  fprintf(v30, "\n");
                }
                if ( g_DeviceMapLogFunction )
                  TraceMessageCallback(0x2000000, "[0x%08x] GetMemoryInfo failed", (unsigned int)v9);
LABEL_64:
                LODWORD(dwAuthnLevel) = v9;
                AslLogCallPrintf(1, "GetAdditionalInventory", v27, v26, dwAuthnLevel);
                goto LABEL_65;
              }
              v9 = (**(__int64 (__fastcall ***)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *))a1)(
                     a1,
                     L"MemoryInfo");
              if ( v9 >= 0 )
              {
                v9 = AddUi64Property(a1, L"pageFile", v56[0]);
                if ( v9 >= 0 )
                {
                  v9 = AddUi64Property(a1, L"ram", v56[1]);
                  if ( v9 >= 0 )
                  {
                    v9 = AddUi64Property(a1, L"virtual", v57[0]);
                    if ( v9 >= 0 )
                    {
                      v9 = AddUi64Property(a1, L"ramKB", v57[1]);
                      if ( v9 >= 0 )
                        v9 = AddUi64Property(a1, L"virtualKB", v58);
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_65:
  if ( v2 )
    CoUninitialize();
  v52 = &WString::`vftable';
  WString::Empty((WString *)&v52);
  v48 = &WString::`vftable';
  WString::Empty((WString *)&v48);
  v44 = &WString::`vftable';
  WString::Empty((WString *)&v44);
  v40 = &WString::`vftable';
  WString::Empty((WString *)&v40);
  v36 = &WString::`vftable';
  WString::Empty((WString *)&v36);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180029efc  push    rbp
0x180029efe  push    rbx
0x180029eff  push    rsi
0x180029f00  push    rdi
0x180029f01  push    r12
0x180029f03  push    r13
0x180029f05  push    r14
0x180029f07  push    r15
0x180029f09  lea     rbp, [rsp-28h]
0x180029f0e  sub     rsp, 128h
0x180029f15  mov     rax, cs:__security_cookie
0x180029f1c  xor     rax, rsp
0x180029f1f  mov     [rbp+60h+var_48], rax
0x180029f23  mov     rdi, rcx
0x180029f26  xorps   xmm0, xmm0
0x180029f29  xor     eax, eax
0x180029f2b  movups  xmmword ptr [rbp+60h+var_70], xmm0
0x180029f2f  movups  xmmword ptr [rbp+60h+var_60], xmm0
0x180029f33  mov     [rbp+60h+var_50], rax
0x180029f37  lea     rbx, ??_7WString@@6B@; const WString::`vftable'
0x180029f3e  mov     [rsp+160h+var_110], rbx
0x180029f43  xor     r15d, r15d
0x180029f46  mov     [rsp+160h+var_100], r15
0x180029f4b  mov     [rsp+160h+String2], r15w
0x180029f51  mov     [rsp+160h+var_108], r15
0x180029f56  xor     edx, edx; unsigned __int16 *
0x180029f58  lea     rcx, [rsp+160h+var_110]; this
0x180029f5d  call    ?Assign@WString@@QEAAJPEBG@Z; WString::Assign(ushort const *)
0x180029f62  mov     [rsp+160h+var_F0], rbx
0x180029f67  mov     [rbp+60h+var_E0], r15
0x180029f6b  mov     [rbp+60h+var_D8], r15w
0x180029f70  mov     [rsp+160h+var_E8], r15
0x180029f75  mov     [rbp+60h+var_D0], rbx
0x180029f79  mov     [rbp+60h+var_C0], r15
0x180029f7d  mov     [rbp+60h+var_B8], r15w
0x180029f82  mov     [rbp+60h+var_C8], r15
0x180029f86  mov     [rbp+60h+var_B0], rbx
0x180029f8a  mov     [rbp+60h+var_A0], r15
0x180029f8e  mov     [rbp+60h+var_98], r15w
0x180029f93  mov     [rbp+60h+var_A8], r15
0x180029f97  mov     [rbp+60h+var_90], rbx
0x180029f9b  mov     [rbp+60h+var_80], r15
0x180029f9f  mov     [rbp+60h+var_78], r15w
0x180029fa4  mov     [rbp+60h+var_88], r15
0x180029fa8  lea     r12d, [r15+2]
0x180029fac  mov     edx, r12d; dwCoInit
0x180029faf  xor     ecx, ecx; pvReserved
0x180029fb1  call    cs:__imp_CoInitializeEx
0x180029fb7  mov     r14d, eax
0x180029fba  shr     r14d, 1Fh
0x180029fbe  xor     r14b, 1
0x180029fc2  mov     [rsp+160h+pReserved3], r15; pReserved3
0x180029fc7  mov     [rsp+160h+dwCapabilities], r15d; dwCapabilities
0x180029fcc  mov     [rsp+160h+pAuthList], r15; pAuthList
0x180029fd1  mov     [rsp+160h+dwImpLevel], 3; dwImpLevel
0x180029fd9  mov     dword ptr [rsp+160h+dwAuthnLevel], r15d; dwAuthnLevel
0x180029fde  xor     r9d, r9d; pReserved1
0x180029fe1  xor     r8d, r8d; asAuthSvc
0x180029fe4  or      edx, 0FFFFFFFFh; cAuthSvc
0x180029fe7  xor     ecx, ecx; pSecDesc
0x180029fe9  call    cs:__imp_CoInitializeSecurity
0x180029fef  mov     ebx, eax
0x180029ff1  test    eax, eax
0x180029ff3  jns     loc_18002A08F
0x180029ff9  mov     dword ptr [rsp+160h+dwAuthnLevel], eax
0x180029ffd  lea     rsi, a0x08xCoinitial; "0x%08x CoInitializeSecurity failed"
0x18002a004  mov     r9, rsi
0x18002a007  mov     r13d, 232h
0x18002a00d  mov     r8d, r13d
0x18002a010  lea     rdx, aGetadditionali; "GetAdditionalInventory"
0x18002a017  mov     ecx, r12d
0x18002a01a  call    AslLogCallPrintf
0x18002a01f  cmp     cs:EnableDevInvStdErrLog, r15d
0x18002a026  jz      short loc_18002A076
0x18002a028  mov     ecx, r12d; Ix
0x18002a02b  call    _o___acrt_iob_func_0
0x18002a030  mov     rcx, rax; Stream
0x18002a033  mov     r9d, r13d
0x18002a036  lea     r8, aGetadditionali; "GetAdditionalInventory"
0x18002a03d  lea     rdx, aWarningSU; "Warning: %s, %u: "
0x18002a044  call    fprintf
0x18002a049  mov     ecx, r12d; Ix
0x18002a04c  call    _o___acrt_iob_func_0
0x18002a051  mov     rcx, rax; Stream
0x18002a054  mov     r8d, ebx
0x18002a057  mov     rdx, rsi; Format
0x18002a05a  call    fprintf
0x18002a05f  mov     ecx, r12d; Ix
0x18002a062  call    _o___acrt_iob_func_0
0x18002a067  mov     rcx, rax; Stream
0x18002a06a  lea     rdx, asc_18011EAD8; "\n"
0x18002a071  call    fprintf
0x18002a076  cmp     cs:g_DeviceMapLogFunction, r15
0x18002a07d  jz      short loc_18002A08F
0x18002a07f  mov     r8d, ebx
0x18002a082  mov     rdx, rsi
0x18002a085  mov     ecx, 3000000h
0x18002a08a  call    TraceMessageCallback
0x18002a08f  lea     rcx, [rsp+160h+var_110]; this
0x18002a094  call    ?GetPingBackInfo@CDevInventory@@SAJPEAU_SYSTEMSPECPINGBACKINFO@@@Z; CDevInventory::GetPingBackInfo(_SYSTEMSPECPINGBACKINFO *)
0x18002a099  mov     ebx, eax
0x18002a09b  test    eax, eax
0x18002a09d  js      loc_18002A3C9
0x18002a0a3  mov     rax, [rdi]
0x18002a0a6  lea     rdx, aPingbackinfo; "PingBackInfo"
0x18002a0ad  mov     rcx, rdi
0x18002a0b0  mov     rax, [rax]
0x18002a0b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0b8  mov     ebx, eax
0x18002a0ba  test    eax, eax
0x18002a0bc  js      loc_18002A479
0x18002a0c2  mov     esi, dword ptr [rsp+160h+var_108]
0x18002a0c6  mov     rbx, [rsp+160h+var_100]
0x18002a0cb  test    rbx, rbx
0x18002a0ce  jz      short loc_18002A0D7
0x18002a0d0  test    esi, esi
0x18002a0d2  mov     rdx, rbx
0x18002a0d5  jnz     short loc_18002A0DC
0x18002a0d7  lea     rdx, [rsp+160h+String2]; String2
0x18002a0dc  lea     r13, aFailedtogetval; "FailedToGetValue"
0x18002a0e3  mov     rcx, r13; String1
0x18002a0e6  call    wcscmp_0
0x18002a0eb  test    eax, eax
0x18002a0ed  jz      short loc_18002A120
0x18002a0ef  mov     rax, [rdi]
0x18002a0f2  test    rbx, rbx
0x18002a0f5  jz      short loc_18002A0FB
0x18002a0f7  test    esi, esi
0x18002a0f9  jnz     short loc_18002A100
0x18002a0fb  lea     rbx, [rsp+160h+String2]
0x18002a100  mov     r8, rbx
0x18002a103  lea     rdx, aManufacturer; "manufacturer"
0x18002a10a  mov     rcx, rdi
0x18002a10d  mov     rax, [rax+8]
0x18002a111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a116  mov     ebx, eax
0x18002a118  test    eax, eax
0x18002a11a  js      loc_18002A479
0x18002a120  mov     esi, dword ptr [rsp+160h+var_E8]
0x18002a124  mov     rbx, [rbp+60h+var_E0]
0x18002a128  test    rbx, rbx
0x18002a12b  jz      short loc_18002A134
0x18002a12d  test    esi, esi
0x18002a12f  mov     rdx, rbx
0x18002a132  jnz     short loc_18002A138
0x18002a134  lea     rdx, [rbp+60h+var_D8]; String2
0x18002a138  mov     rcx, r13; String1
0x18002a13b  call    wcscmp_0
0x18002a140  test    eax, eax
0x18002a142  jz      short loc_18002A174
0x18002a144  mov     rax, [rdi]
0x18002a147  test    rbx, rbx
0x18002a14a  jz      short loc_18002A150
0x18002a14c  test    esi, esi
0x18002a14e  jnz     short loc_18002A154
0x18002a150  lea     rbx, [rbp+60h+var_D8]
0x18002a154  mov     r8, rbx
0x18002a157  lea     rdx, aModel; "model"
0x18002a15e  mov     rcx, rdi
0x18002a161  mov     rax, [rax+8]
0x18002a165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a16a  mov     ebx, eax
0x18002a16c  test    eax, eax
0x18002a16e  js      loc_18002A479
0x18002a174  mov     esi, dword ptr [rbp+60h+var_C8]
0x18002a177  mov     rbx, [rbp+60h+var_C0]
0x18002a17b  test    rbx, rbx
0x18002a17e  jz      short loc_18002A187
0x18002a180  test    esi, esi
0x18002a182  mov     rdx, rbx
0x18002a185  jnz     short loc_18002A18B
0x18002a187  lea     rdx, [rbp+60h+var_B8]; String2
0x18002a18b  mov     rcx, r13; String1
0x18002a18e  call    wcscmp_0
0x18002a193  test    eax, eax
0x18002a195  jz      short loc_18002A1C7
0x18002a197  mov     rax, [rdi]
0x18002a19a  test    rbx, rbx
0x18002a19d  jz      short loc_18002A1A3
0x18002a19f  test    esi, esi
0x18002a1a1  jnz     short loc_18002A1A7
0x18002a1a3  lea     rbx, [rbp+60h+var_B8]
0x18002a1a7  mov     r8, rbx
0x18002a1aa  lea     rdx, aBiosname; "biosName"
0x18002a1b1  mov     rcx, rdi
0x18002a1b4  mov     rax, [rax+8]
0x18002a1b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a1bd  mov     ebx, eax
0x18002a1bf  test    eax, eax
0x18002a1c1  js      loc_18002A479
0x18002a1c7  mov     esi, dword ptr [rbp+60h+var_A8]
0x18002a1ca  mov     rbx, [rbp+60h+var_A0]
0x18002a1ce  test    rbx, rbx
0x18002a1d1  jz      short loc_18002A1DA
0x18002a1d3  test    esi, esi
0x18002a1d5  mov     rdx, rbx
0x18002a1d8  jnz     short loc_18002A1DE
0x18002a1da  lea     rdx, [rbp+60h+var_98]; String2
0x18002a1de  mov     rcx, r13; String1
0x18002a1e1  call    wcscmp_0
0x18002a1e6  test    eax, eax
0x18002a1e8  jz      short loc_18002A21A
0x18002a1ea  mov     rax, [rdi]
0x18002a1ed  test    rbx, rbx
0x18002a1f0  jz      short loc_18002A1F6
0x18002a1f2  test    esi, esi
0x18002a1f4  jnz     short loc_18002A1FA
0x18002a1f6  lea     rbx, [rbp+60h+var_98]
0x18002a1fa  mov     r8, rbx
0x18002a1fd  lea     rdx, aBiosversion_1; "biosVersion"
0x18002a204  mov     rcx, rdi
0x18002a207  mov     rax, [rax+8]
0x18002a20b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a210  mov     ebx, eax
0x18002a212  test    eax, eax
0x18002a214  js      loc_18002A479
0x18002a21a  mov     esi, dword ptr [rbp+60h+var_88]
0x18002a21d  mov     rbx, [rbp+60h+var_80]
0x18002a221  test    rbx, rbx
0x18002a224  jz      short loc_18002A22D
0x18002a226  test    esi, esi
0x18002a228  mov     rdx, rbx
0x18002a22b  jnz     short loc_18002A231
0x18002a22d  lea     rdx, [rbp+60h+var_78]; String2
0x18002a231  mov     rcx, r13; String1
0x18002a234  call    wcscmp_0
0x18002a239  test    eax, eax
0x18002a23b  jz      short loc_18002A26D
0x18002a23d  mov     rax, [rdi]
0x18002a240  test    rbx, rbx
0x18002a243  jz      short loc_18002A249
0x18002a245  test    esi, esi
0x18002a247  jnz     short loc_18002A24D
0x18002a249  lea     rbx, [rbp+60h+var_78]
0x18002a24d  mov     r8, rbx
0x18002a250  lea     rdx, aBiosdate; "biosDate"
0x18002a257  mov     rcx, rdi
0x18002a25a  mov     rax, [rax+8]
0x18002a25e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a263  mov     ebx, eax
0x18002a265  test    eax, eax
0x18002a267  js      loc_18002A479
0x18002a26d  lea     rcx, [rbp+60h+var_70]; struct _SYSTEMSPECMEMORYINFO *
0x18002a271  call    ?GetMemoryInfo@CDevInventory@@SAJPEAU_SYSTEMSPECMEMORYINFO@@@Z; CDevInventory::GetMemoryInfo(_SYSTEMSPECMEMORYINFO *)
0x18002a276  mov     ebx, eax
0x18002a278  test    eax, eax
0x18002a27a  jns     loc_18002A31C
0x18002a280  mov     dword ptr [rsp+160h+dwAuthnLevel], eax
0x18002a284  lea     rdi, a0x08xGetmemory; "[0x%08x] GetMemoryInfo failed"
0x18002a28b  mov     r9, rdi
0x18002a28e  mov     esi, 25Ah
0x18002a293  mov     r8d, esi
0x18002a296  lea     r13, aGetadditionali; "GetAdditionalInventory"
0x18002a29d  mov     rdx, r13
0x18002a2a0  mov     ecx, r12d
0x18002a2a3  call    AslLogCallPrintf
0x18002a2a8  cmp     cs:EnableDevInvStdErrLog, r15d
0x18002a2af  jz      short loc_18002A2FB
0x18002a2b1  mov     ecx, r12d; Ix
0x18002a2b4  call    _o___acrt_iob_func_0
0x18002a2b9  mov     rcx, rax; Stream
0x18002a2bc  mov     r9d, esi
0x18002a2bf  mov     r8, r13
0x18002a2c2  lea     rdx, Format; "Error: %s, %u: "
0x18002a2c9  call    fprintf
0x18002a2ce  mov     ecx, r12d; Ix
0x18002a2d1  call    _o___acrt_iob_func_0
0x18002a2d6  mov     rcx, rax; Stream
0x18002a2d9  mov     r8d, ebx
0x18002a2dc  mov     rdx, rdi; Format
0x18002a2df  call    fprintf
0x18002a2e4  mov     ecx, r12d; Ix
0x18002a2e7  call    _o___acrt_iob_func_0
0x18002a2ec  mov     rcx, rax; Stream
0x18002a2ef  lea     rdx, asc_18011EAD8; "\n"
0x18002a2f6  call    fprintf
0x18002a2fb  cmp     cs:g_DeviceMapLogFunction, r15
0x18002a302  jz      short loc_18002A314
0x18002a304  mov     r8d, ebx
0x18002a307  mov     rdx, rdi
0x18002a30a  mov     ecx, 2000000h
0x18002a30f  call    TraceMessageCallback
0x18002a314  mov     rdx, r13
0x18002a317  jmp     loc_18002A465
0x18002a31c  mov     rax, [rdi]
0x18002a31f  lea     rdx, aMemoryinfo; "MemoryInfo"
0x18002a326  mov     rcx, rdi
0x18002a329  mov     rax, [rax]
0x18002a32c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a331  mov     ebx, eax
0x18002a333  test    eax, eax
0x18002a335  js      loc_18002A479
0x18002a33b  mov     r8, [rbp+60h+var_70]; unsigned __int64
0x18002a33f  lea     rdx, aPagefile; "pageFile"
0x18002a346  mov     rcx, rdi; struct Windows::Compat::Inventory::IInventoryDataReceiver *
0x18002a349  call    ?AddUi64Property@@YAJPEAVIInventoryDataReceiver@Inventory@Compat@Windows@@PEBG_K@Z; AddUi64Property(Windows::Compat::Inventory::IInventoryDataReceiver *,ushort const *,unsigned __int64)
0x18002a34e  mov     ebx, eax
0x18002a350  test    eax, eax
0x18002a352  js      loc_18002A479
0x18002a358  mov     r8, [rbp+60h+var_70+8]; unsigned __int64
  ... truncated ...
```
