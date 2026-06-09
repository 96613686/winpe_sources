# CWSDPublisher::InitInstance(ushort const * const,ushort const * const,ushort const * const)

- ea: `0x180002f24`
- end: `0x1800033fb`
- name: `?InitInstance@CWSDPublisher@@QEAAJQEBG00@Z`
- size: `1239`
- prototype: `__int64 __fastcall(CWSDPublisher *__hidden this, const unsigned __int16 *const, const unsigned __int16 *const, const unsigned __int16 *const)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180001cc0`

## callees

- `0x180001014`
- `0x180001020`
- `0x180001f24`
- `0x180001f70`
- `0x180002f24`
- `0x180003404`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800032a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800032a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800032e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800032e5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800032d9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800032d9`
- `wsdapi!WSDXMLCreateContext` at `0x1800031ec`
- `wsdapi!WSDXMLCreateContext` at `0x1800031ec`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800031d5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800031d5`

## string_xrefs

- `0x1800031fe`: `WSDXMLCreateContext`
- `0x180003214`: `http://schemas.microsoft.com/windows/pub/2005/07`
- `0x180003261`: `IWSDXMLContext::AddNamespace`
- `0x180003242`: `http://schemas.microsoft.com/pnpx/2005/08`
- `0x18000328e`: `System\CurrentControlSet\Services\fdrespub\Parameters`

## pseudocode

```c
__int64 __fastcall CWSDPublisher::InitInstance(
        CWSDPublisher *this,
        const unsigned __int16 *const a2,
        const unsigned __int16 *const a3,
        const unsigned __int16 *const a4)
{
  _QWORD *v8; // rcx
  __int64 v9; // r14
  __int64 v10; // rcx
  _WORD *v11; // rax
  unsigned __int64 v12; // rdx
  _WORD *v13; // r8
  __int64 v14; // rdx
  unsigned int Instance; // edi
  unsigned int v16; // ecx
  __int64 v17; // rax
  _WORD *v18; // rcx
  __int64 v19; // rcx
  _WORD *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rbx
  __int64 v23; // rax
  _WORD *v24; // rcx
  __int64 v25; // rcx
  _WORD *v26; // rax
  _WORD *v27; // rcx
  _QWORD *v28; // rbx
  HRESULT v29; // eax
  const struct _EVENT_DESCRIPTOR *v30; // rcx
  unsigned int v31; // r9d
  const unsigned __int16 *v32; // r8
  LSTATUS v33; // ebx
  void *v34; // rcx
  void *v35; // rcx
  void *v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  bool v39; // cf
  __int64 v40; // rdx
  LPVOID *ppv; // [rsp+20h] [rbp-28h]
  BYTE Data[4]; // [rsp+30h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-14h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-10h] BYREF
  DWORD Type; // [rsp+98h] [rbp+50h] BYREF

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( a2 && a3 && a4 )
  {
    v9 = -1;
    v10 = -1;
    do
      ++v10;
    while ( a2[v10] );
    v11 = operator new[](saturated_mul(v10 + 1, 2u));
    *((_QWORD *)this + 8) = v11;
    v13 = v11;
    if ( !v11 )
      goto LABEL_70;
    v14 = -1;
    do
      ++v14;
    while ( a2[v14] );
    Instance = -2147024809;
    v12 = v14 + 1;
    if ( v12 )
    {
      if ( v12 <= 0x7FFFFFFF )
      {
        v17 = 2147483646;
        do
        {
          if ( !v17 )
            break;
          if ( !*a2 )
            break;
          *v13++ = *a2++;
          --v17;
          --v12;
        }
        while ( v12 );
        v18 = v13 - 1;
        if ( v12 )
          v18 = v13;
        v12 = -(__int64)v12;
        *v18 = 0;
        v16 = v12 == 0 ? 0x8007007A : 0;
      }
      else
      {
        v16 = -2147024809;
        *v11 = 0;
      }
    }
    else
    {
      v16 = -2147024809;
    }
    if ( v16 )
      goto LABEL_69;
    v19 = -1;
    do
      ++v19;
    while ( a3[v19] );
    v20 = operator new[](saturated_mul(v19 + 1, 2u));
    *((_QWORD *)this + 6) = v20;
    v13 = v20;
    if ( !v20 )
      goto LABEL_70;
    v21 = -1;
    do
      ++v21;
    while ( a3[v21] );
    v12 = v21 + 1;
    if ( v12 )
    {
      if ( v12 <= 0x7FFFFFFF )
      {
        v22 = 2147483646;
        v23 = 2147483646;
        do
        {
          if ( !v23 )
            break;
          if ( !*a3 )
            break;
          *v13++ = *a3++;
          --v23;
          --v12;
        }
        while ( v12 );
        v24 = v13 - 1;
        if ( v12 )
          v24 = v13;
        v12 = -(__int64)v12;
        *v24 = 0;
        v16 = v12 == 0 ? 0x8007007A : 0;
LABEL_41:
        if ( !v16 )
        {
          v25 = -1;
          do
            ++v25;
          while ( a4[v25] );
          v26 = operator new[](saturated_mul(v25 + 1, 2u));
          *((_QWORD *)this + 7) = v26;
          v13 = v26;
          if ( v26 )
          {
            do
              ++v9;
            while ( a4[v9] );
            v12 = v9 + 1;
            if ( v9 != -1 )
            {
              if ( v12 > 0x7FFFFFFF )
              {
                *v26 = 0;
              }
              else
              {
                do
                {
                  if ( !v22 )
                    break;
                  if ( !*a4 )
                    break;
                  *v13++ = *a4++;
                  --v22;
                  --v12;
                }
                while ( v12 );
                v27 = v13 - 1;
                if ( v12 )
                  v27 = v13;
                v12 = -(__int64)v12;
                Instance = v12 == 0 ? 0x8007007A : 0;
                *v27 = 0;
              }
            }
            if ( !Instance )
            {
              Instance = CoCreateInstance(
                           &GUID_c72be2ec_8e90_452c_b29a_ab8ff1c071fc,
                           0,
                           0x401u,
                           &GUID_4df99b70_e148_4432_b004_4c9eeb535a5e,
                           (LPVOID *)this + 4);
              if ( !Instance )
              {
                v28 = (_QWORD *)((char *)this + 8);
                v29 = WSDXMLCreateContext((IWSDXMLContext **)this + 1);
                Instance = v29;
                if ( v29 )
                {
                  v31 = 362;
                  v32 = L"WSDXMLCreateContext";
                }
                else
                {
                  v29 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, _QWORD))(*(_QWORD *)*v28 + 24LL))(
                          *v28,
                          L"http://schemas.microsoft.com/windows/pub/2005/07",
                          L"pub",
                          0);
                  Instance = v29;
                  if ( v29 )
                  {
                    v31 = 369;
                  }
                  else
                  {
                    v29 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, _QWORD))(*(_QWORD *)*v28 + 24LL))(
                            *v28,
                            L"http://schemas.microsoft.com/pnpx/2005/08",
                            L"pnpx",
                            0);
                    Instance = v29;
                    if ( !v29 )
                    {
                      Type = 0;
                      *(_DWORD *)Data = 0;
                      cbData = 4;
                      phkResult = 0;
                      if ( !RegOpenKeyExW(
                              HKEY_LOCAL_MACHINE,
                              L"System\\CurrentControlSet\\Services\\fdrespub\\Parameters",
                              0,
                              1u,
                              &phkResult) )
                      {
                        v33 = RegQueryValueExW(phkResult, L"MaxPublicationSize", 0, &Type, Data, &cbData);
                        RegCloseKey(phkResult);
                        if ( !v33 && Type == 4 )
                          *((_DWORD *)this + 22) = *(_DWORD *)Data;
                      }
                      goto LABEL_82;
                    }
                    v31 = 375;
                  }
                  v32 = L"IWSDXMLContext::AddNamespace";
                }
                LogError(v30, v29, v32, v31, (const char *)ppv);
              }
            }
LABEL_71:
            v34 = (void *)*((_QWORD *)this + 8);
            if ( v34 )
            {
              operator delete[](v34);
              *((_QWORD *)this + 8) = 0;
            }
            v35 = (void *)*((_QWORD *)this + 6);
            if ( v35 )
            {
              operator delete[](v35);
              *((_QWORD *)this + 6) = 0;
            }
            v36 = (void *)*((_QWORD *)this + 7);
            if ( v36 )
            {
              operator delete[](v36);
              *((_QWORD *)this + 7) = 0;
            }
            v37 = *((_QWORD *)this + 4);
            if ( v37 )
            {
              (*(void (__fastcall **)(__int64, unsigned __int64, _WORD *))(*(_QWORD *)v37 + 16LL))(v37, v12, v13);
              *((_QWORD *)this + 4) = 0;
            }
            v38 = *((_QWORD *)this + 1);
            if ( v38 )
            {
              (*(void (__fastcall **)(__int64, unsigned __int64, _WORD *))(*(_QWORD *)v38 + 16LL))(v38, v12, v13);
              *((_QWORD *)this + 1) = 0;
            }
            if ( Instance )
            {
              v8 = WPP_GLOBAL_Control;
              v39 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
              goto LABEL_84;
            }
LABEL_82:
            v8 = WPP_GLOBAL_Control;
            v39 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u;
LABEL_84:
            if ( v8 != &WPP_GLOBAL_Control && !v39 )
            {
              v40 = 18;
LABEL_90:
              WPP_SF_sqd(v8[2], v40, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids);
              return Instance;
            }
            return Instance;
          }
LABEL_70:
          Instance = -2147024882;
          goto LABEL_71;
        }
LABEL_69:
        Instance = v16;
        goto LABEL_71;
      }
      v16 = -2147024809;
      *v20 = 0;
    }
    else
    {
      v16 = -2147024809;
    }
    v22 = 2147483646;
    goto LABEL_41;
  }
  Instance = -2147024809;
  if ( v8 != &WPP_GLOBAL_Control && *((_BYTE *)v8 + 25) >= 2u )
  {
    v40 = 17;
    goto LABEL_90;
  }
  return Instance;
}

```

## disassembly

```asm
0x180002f24  push    rbp
0x180002f26  push    rbx
0x180002f27  push    rsi
0x180002f28  push    rdi
0x180002f29  push    r12
0x180002f2b  push    r13
0x180002f2d  push    r14
0x180002f2f  push    r15
0x180002f31  mov     rbp, rsp
0x180002f34  sub     rsp, 48h
0x180002f38  mov     r13, r9
0x180002f3b  mov     r12, r8
0x180002f3e  mov     rbx, rdx
0x180002f41  mov     rsi, rcx
0x180002f44  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f4b  lea     rax, WPP_GLOBAL_Control
0x180002f52  cmp     rcx, rax
0x180002f55  jz      short loc_180002F85
0x180002f57  cmp     byte ptr [rcx+19h], 4
0x180002f5b  jb      short loc_180002F85
0x180002f5d  mov     rcx, [rcx+10h]
0x180002f61  lea     r8, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids
0x180002f68  mov     edx, 10h
0x180002f6d  mov     [rsp+48h+ppv], rsi
0x180002f72  call    WPP_SF_sq
0x180002f77  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f7e  lea     rax, WPP_GLOBAL_Control
0x180002f85  xor     r9d, r9d
0x180002f88  test    rbx, rbx
0x180002f8b  jz      loc_1800033B5
0x180002f91  test    r12, r12
0x180002f94  jz      loc_1800033B5
0x180002f9a  test    r13, r13
0x180002f9d  jz      loc_1800033B5
0x180002fa3  or      r14, 0FFFFFFFFFFFFFFFFh
0x180002fa7  mov     rcx, r14
0x180002faa  inc     rcx
0x180002fad  cmp     [rbx+rcx*2], r9w
0x180002fb2  jnz     short loc_180002FAA
0x180002fb4  inc     rcx
0x180002fb7  mov     r15d, 2
0x180002fbd  mov     eax, r15d
0x180002fc0  mul     rcx
0x180002fc3  cmovb   rax, r14
0x180002fc7  mov     rcx, rax; unsigned __int64
0x180002fca  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180002fcf  xor     r9d, r9d
0x180002fd2  mov     [rsi+40h], rax
0x180002fd6  mov     r8, rax
0x180002fd9  test    rax, rax
0x180002fdc  jz      loc_18000330C
0x180002fe2  mov     rdx, r14
0x180002fe5  inc     rdx
0x180002fe8  cmp     [rbx+rdx*2], r9w
0x180002fed  jnz     short loc_180002FE5
0x180002fef  mov     edi, 80070057h
0x180002ff4  add     rdx, 1
0x180002ff8  jz      short loc_18000304A
0x180002ffa  cmp     rdx, 7FFFFFFFh
0x180003001  jbe     short loc_180003007
0x180003003  mov     ecx, edi
0x180003005  jmp     short loc_180003051
0x180003007  mov     eax, 7FFFFFFEh
0x18000300c  test    rax, rax
0x18000300f  jz      short loc_18000302C
0x180003011  movzx   ecx, word ptr [rbx]
0x180003014  test    cx, cx
0x180003017  jz      short loc_18000302C
0x180003019  mov     [r8], cx
0x18000301d  add     rbx, r15
0x180003020  add     r8, r15
0x180003023  dec     rax
0x180003026  sub     rdx, 1
0x18000302a  jnz     short loc_18000300C
0x18000302c  test    rdx, rdx
0x18000302f  lea     rcx, [r8-2]
0x180003033  cmovnz  rcx, r8
0x180003037  neg     rdx
0x18000303a  mov     [rcx], r9w
0x18000303e  sbb     ecx, ecx
0x180003040  not     ecx
0x180003042  and     ecx, 8007007Ah
0x180003048  jmp     short loc_180003055
0x18000304a  mov     ecx, edi
0x18000304c  test    rdx, rdx
0x18000304f  jz      short loc_180003055
0x180003051  mov     [rax], r9w
0x180003055  test    ecx, ecx
0x180003057  jnz     loc_180003305
0x18000305d  mov     rcx, r14
0x180003060  inc     rcx
0x180003063  cmp     [r12+rcx*2], r9w
0x180003068  jnz     short loc_180003060
0x18000306a  inc     rcx
0x18000306d  mov     rax, r15
0x180003070  mul     rcx
0x180003073  cmovb   rax, r14
0x180003077  mov     rcx, rax; unsigned __int64
0x18000307a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000307f  xor     r9d, r9d
0x180003082  mov     [rsi+30h], rax
0x180003086  mov     r8, rax
0x180003089  test    rax, rax
0x18000308c  jz      loc_18000330C
0x180003092  mov     rdx, r14
0x180003095  inc     rdx
0x180003098  cmp     [r12+rdx*2], r9w
0x18000309d  jnz     short loc_180003095
0x18000309f  add     rdx, 1
0x1800030a3  jz      short loc_1800030FF
0x1800030a5  cmp     rdx, 7FFFFFFFh
0x1800030ac  jbe     short loc_1800030B5
0x1800030ae  mov     ecx, edi
0x1800030b0  xor     r12d, r12d
0x1800030b3  jmp     short loc_180003109
0x1800030b5  mov     ebx, 7FFFFFFEh
0x1800030ba  mov     eax, ebx
0x1800030bc  test    rax, rax
0x1800030bf  jz      short loc_1800030DE
0x1800030c1  movzx   ecx, word ptr [r12]
0x1800030c6  test    cx, cx
0x1800030c9  jz      short loc_1800030DE
0x1800030cb  mov     [r8], cx
0x1800030cf  add     r12, r15
0x1800030d2  add     r8, r15
0x1800030d5  dec     rax
0x1800030d8  sub     rdx, 1
0x1800030dc  jnz     short loc_1800030BC
0x1800030de  xor     r12d, r12d
0x1800030e1  lea     rcx, [r8-2]
0x1800030e5  test    rdx, rdx
0x1800030e8  cmovnz  rcx, r8
0x1800030ec  neg     rdx
0x1800030ef  mov     [rcx], r12w
0x1800030f3  sbb     ecx, ecx
0x1800030f5  not     ecx
0x1800030f7  and     ecx, 8007007Ah
0x1800030fd  jmp     short loc_180003112
0x1800030ff  xor     r12d, r12d
0x180003102  mov     ecx, edi
0x180003104  test    rdx, rdx
0x180003107  jz      short loc_18000310D
0x180003109  mov     [rax], r12w
0x18000310d  mov     ebx, 7FFFFFFEh
0x180003112  test    ecx, ecx
0x180003114  jnz     loc_180003308
0x18000311a  mov     rcx, r14
0x18000311d  inc     rcx
0x180003120  cmp     [r13+rcx*2+0], r12w
0x180003126  jnz     short loc_18000311D
0x180003128  inc     rcx
0x18000312b  mov     rax, r15
0x18000312e  mul     rcx
0x180003131  cmovb   rax, r14
0x180003135  mov     rcx, rax; unsigned __int64
0x180003138  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000313d  mov     [rsi+38h], rax
0x180003141  mov     r8, rax
0x180003144  test    rax, rax
0x180003147  jz      loc_18000330F
0x18000314d  inc     r14
0x180003150  cmp     [r13+r14*2+0], r12w
0x180003156  jnz     short loc_18000314D
0x180003158  lea     rdx, [r14+1]
0x18000315c  test    rdx, rdx
0x18000315f  jz      short loc_1800031AE
0x180003161  cmp     rdx, 7FFFFFFFh
0x180003168  ja      short loc_1800031AA
0x18000316a  test    rbx, rbx
0x18000316d  jz      short loc_18000318C
0x18000316f  movzx   eax, word ptr [r13+0]
0x180003174  test    ax, ax
0x180003177  jz      short loc_18000318C
0x180003179  mov     [r8], ax
0x18000317d  add     r13, r15
0x180003180  add     r8, r15
0x180003183  dec     rbx
0x180003186  sub     rdx, 1
0x18000318a  jnz     short loc_18000316A
0x18000318c  test    rdx, rdx
0x18000318f  lea     rcx, [r8-2]
0x180003193  cmovnz  rcx, r8
0x180003197  neg     rdx
0x18000319a  sbb     edi, edi
0x18000319c  not     edi
0x18000319e  and     edi, 8007007Ah
0x1800031a4  mov     [rcx], r12w
0x1800031a8  jmp     short loc_1800031AE
0x1800031aa  mov     [rax], r12w
0x1800031ae  test    edi, edi
0x1800031b0  jnz     loc_180003314
0x1800031b6  lea     rax, [rsi+20h]
0x1800031ba  xor     edx, edx; pUnkOuter
0x1800031bc  lea     r9, _GUID_4df99b70_e148_4432_b004_4c9eeb535a5e; riid
0x1800031c3  mov     [rsp+48h+ppv], rax; char *
0x1800031c8  mov     r8d, 401h; dwClsContext
0x1800031ce  lea     rcx, _GUID_c72be2ec_8e90_452c_b29a_ab8ff1c071fc; rclsid
0x1800031d5  call    cs:__imp_CoCreateInstance
0x1800031db  mov     edi, eax
0x1800031dd  test    eax, eax
0x1800031df  jnz     loc_180003314
0x1800031e5  lea     rbx, [rsi+8]
0x1800031e9  mov     rcx, rbx; ppContext
0x1800031ec  call    cs:__imp_WSDXMLCreateContext
0x1800031f2  mov     edi, eax
0x1800031f4  test    eax, eax
0x1800031f6  jz      short loc_180003207
0x1800031f8  mov     r9d, 16Ah
0x1800031fe  lea     r8, aWsdxmlcreateco; "WSDXMLCreateContext"
0x180003205  jmp     short loc_180003268
0x180003207  mov     rcx, [rbx]
0x18000320a  lea     r8, aPub; "pub"
0x180003211  xor     r9d, r9d
0x180003214  lea     rdx, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/pu"...
0x18000321b  mov     rax, [rcx]
0x18000321e  mov     rax, [rax+18h]
0x180003222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003227  mov     edi, eax
0x180003229  test    eax, eax
0x18000322b  jz      short loc_180003235
0x18000322d  mov     r9d, 171h
0x180003233  jmp     short loc_180003261
0x180003235  mov     rcx, [rbx]
0x180003238  lea     r8, aPnpx; "pnpx"
0x18000323f  xor     r9d, r9d
0x180003242  lea     rdx, aHttpSchemasMic_1; "http://schemas.microsoft.com/pnpx/2005/"...
0x180003249  mov     rax, [rcx]
0x18000324c  mov     rax, [rax+18h]
0x180003250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003255  mov     edi, eax
0x180003257  test    eax, eax
0x180003259  jz      short loc_180003274
0x18000325b  mov     r9d, 177h; unsigned int
0x180003261  lea     r8, aIwsdxmlcontext; "IWSDXMLContext::AddNamespace"
0x180003268  mov     edx, eax; int
0x18000326a  call    ?LogError@@YAJPEBU_EVENT_DESCRIPTOR@@JPEBGKPEBD@Z; LogError(_EVENT_DESCRIPTOR const *,long,ushort const *,ulong,char const *)
0x18000326f  jmp     loc_180003314
0x180003274  lea     rax, [rbp+phkResult]
0x180003278  mov     [rbp+Type], r12d
0x18000327c  mov     r9d, 1; samDesired
0x180003282  mov     [rsp+48h+ppv], rax; phkResult
0x180003287  xor     r8d, r8d; ulOptions
0x18000328a  mov     dword ptr [rbp+Data], r12d
0x18000328e  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\fd"...
0x180003295  mov     [rbp+cbData], 4
0x18000329c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800032a3  mov     [rbp+phkResult], r12
0x1800032a7  call    cs:__imp_RegOpenKeyExW
0x1800032ad  test    eax, eax
0x1800032af  jnz     loc_180003380
0x1800032b5  mov     rcx, [rbp+phkResult]; hKey
0x1800032b9  lea     rax, [rbp+cbData]
0x1800032bd  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800032c2  lea     r9, [rbp+Type]; lpType
0x1800032c6  lea     rax, [rbp+Data]
0x1800032ca  xor     r8d, r8d; lpReserved
0x1800032cd  lea     rdx, aMaxpublication; "MaxPublicationSize"
0x1800032d4  mov     [rsp+48h+ppv], rax; lpData
0x1800032d9  call    cs:__imp_RegQueryValueExW
0x1800032df  mov     rcx, [rbp+phkResult]; hKey
0x1800032e3  mov     ebx, eax
0x1800032e5  call    cs:__imp_RegCloseKey
0x1800032eb  test    ebx, ebx
0x1800032ed  jnz     loc_180003380
0x1800032f3  cmp     [rbp+Type], 4
0x1800032f7  jnz     loc_180003380
0x1800032fd  mov     eax, dword ptr [rbp+Data]
0x180003300  mov     [rsi+58h], eax
0x180003303  jmp     short loc_180003380
0x180003305  xor     r12d, r12d
0x180003308  mov     edi, ecx
0x18000330a  jmp     short loc_180003314
0x18000330c  xor     r12d, r12d
0x18000330f  mov     edi, 8007000Eh
0x180003314  mov     rcx, [rsi+40h]; Block
0x180003318  test    rcx, rcx
0x18000331b  jz      short loc_180003326
0x18000331d  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180003322  mov     [rsi+40h], r12
0x180003326  mov     rcx, [rsi+30h]; Block
0x18000332a  test    rcx, rcx
0x18000332d  jz      short loc_180003338
0x18000332f  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180003334  mov     [rsi+30h], r12
0x180003338  mov     rcx, [rsi+38h]; Block
0x18000333c  test    rcx, rcx
0x18000333f  jz      short loc_18000334A
0x180003341  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180003346  mov     [rsi+38h], r12
0x18000334a  mov     rcx, [rsi+20h]
0x18000334e  test    rcx, rcx
0x180003351  jz      short loc_180003363
0x180003353  mov     rax, [rcx]
0x180003356  mov     rax, [rax+10h]
0x18000335a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000335f  mov     [rsi+20h], r12
0x180003363  mov     rcx, [rsi+8]
0x180003367  test    rcx, rcx
0x18000336a  jz      short loc_18000337C
0x18000336c  mov     rax, [rcx]
  ... truncated ...
```
