# ConfigClusterCert(wchar_t const *,_CLUSTER_CERT *,_CLUSTER_CERT *,_CLUSTER_CERT *,_CLUSTER_CERT *,ushort)

- ea: `0x1800332b8`
- end: `0x180033594`
- name: `?ConfigClusterCert@@YAJPEB_WPEAU_CLUSTER_CERT@@111G@Z`
- size: `732`
- prototype: `__int64 __usercall@<rax>(const wchar_t *@<rcx>, struct _CLUSTER_CERT *@<rdx>, struct _CLUSTER_CERT *@<r8>, struct _CLUSTER_CERT *@<r9>, struct _CLUSTER_CERT *, unsigned __int16)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800465e0`

## callees

- `0x1800332b8`
- `0x1800395ec`
- `0x18006f910`
- `0x1800b5010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180033574`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180033574`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800332e7`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800332e7`
- `OLEAUT32!__imp_SysAllocString` at `0x1800334e1`
- `OLEAUT32!__imp_SysAllocString` at `0x1800334e1`
- `OLEAUT32!__imp_SysFreeString` at `0x180033557`
- `OLEAUT32!__imp_SysFreeString` at `0x180033557`

## string_xrefs

- `0x18003334f`: `ConfigClusterCertV2(Cluster_SChannel): %x.`
- `0x180033340`: `ConfigClusterCert`
- `0x180033398`: `ConfigClusterCert`
- `0x1800333e8`: `ConfigClusterCert`
- `0x180033433`: `ConfigClusterCert`
- `0x18003347c`: `ConfigClusterCert`
- `0x1800334ad`: `ConfigClusterCert`
- `0x180033500`: `ConfigClusterCert`
- `0x1800333a7`: `ConfigClusterCertV2(Cluster_PKU2U): %x.`
- `0x18003346f`: `ConfigClusterCertV2(Cluster_PKU2U): functional level is less than NT11_MAJOR_VERSION. Skipping configuring cluster pku2u cert`
- `0x1800333f7`: `ConfigClusterCertV2(ClusterLM_SChannel): %x.`
- `0x180033442`: `ConfigClusterCertV2(ClusterLM_PKU2U): %x.`
- `0x1800334bc`: `ConfigClusterCert: %x.`
- `0x18003350f`: `ConfigSvcSecret: %x.`

## pseudocode

```c
__int64 __fastcall ConfigClusterCert(
        const wchar_t *a1,
        const OLECHAR *a2,
        struct _CLUSTER_CERT *a3,
        struct _CLUSTER_CERT *a4,
        struct _CLUSTER_CERT *a5,
        unsigned __int16 a6)
{
  unsigned int v10; // eax
  unsigned int v11; // ebp
  int CPrepSetupReference; // ebx
  struct IClusterSetup *v13; // rdi
  int v14; // esi
  int v15; // ebx
  OLECHAR *v16; // rsi
  __int64 v17; // rax
  __int64 v18; // rcx
  OLECHAR *i; // rax
  __int64 v21; // [rsp+28h] [rbp-60h]
  __int64 v22; // [rsp+28h] [rbp-60h]
  __int64 v23; // [rsp+28h] [rbp-60h]
  __int64 v24; // [rsp+28h] [rbp-60h]
  struct IClusterSetup *v25; // [rsp+30h] [rbp-58h] BYREF

  v25 = 0;
  v10 = CoInitializeEx(0, 4u);
  v11 = v10;
  if ( v10 <= 1 || v10 == -2147417850 )
  {
    CPrepSetupReference = GetCPrepSetupReference(a1, &v25);
    if ( !CPrepSetupReference )
    {
      v13 = v25;
      if ( v25 )
      {
        CPrepSetupReference = (*(__int64 (__fastcall **)(struct IClusterSetup *, const OLECHAR *, _QWORD))(*(_QWORD *)v25 + 112LL))(
                                v25,
                                a2,
                                0);
        TraceMsg(4, 0, L"ConfigClusterCert", 9026, L"ConfigClusterCertV2(Cluster_SChannel): %x.", CPrepSetupReference);
        if ( CPrepSetupReference < 0 )
        {
          LODWORD(v21) = (*(__int64 (__fastcall **)(struct IClusterSetup *, const OLECHAR *))(*(_QWORD *)v13 + 72LL))(
                           v13,
                           a2);
          CPrepSetupReference = v21;
          TraceMsg(4, 0, L"ConfigClusterCert", 9062, L"ConfigClusterCert: %x.", v21);
          if ( CPrepSetupReference < 0 )
          {
            v16 = SysAllocString(a2 + 7684);
            LODWORD(v24) = (*(__int64 (__fastcall **)(struct IClusterSetup *, OLECHAR *))(*(_QWORD *)v13 + 24LL))(
                             v13,
                             v16);
            CPrepSetupReference = v24;
            TraceMsg(4, 0, L"ConfigClusterCert", 9068, L"ConfigSvcSecret: %x.", v24);
            if ( v16 )
            {
              v17 = -1;
              do
                ++v17;
              while ( v16[v17] );
              v18 = 2 * v17 + 2;
              for ( i = v16; v18; --v18 )
              {
                *(_BYTE *)i = 0;
                i = (OLECHAR *)((char *)i + 1);
              }
              SysFreeString(v16);
            }
          }
        }
        else if ( a6 < 0xAu )
        {
          TraceMsg(
            4,
            0,
            L"ConfigClusterCert",
            9036,
            L"ConfigClusterCertV2(Cluster_PKU2U): functional level is less than NT11_MAJOR_VERSION. Skipping configuring c"
             "luster pku2u cert");
        }
        else
        {
          LODWORD(v21) = (*(__int64 (__fastcall **)(struct IClusterSetup *, struct _CLUSTER_CERT *, __int64))(*(_QWORD *)v13 + 112LL))(
                           v13,
                           a3,
                           2);
          CPrepSetupReference = v21;
          TraceMsg(4, 0, L"ConfigClusterCert", 9032, L"ConfigClusterCertV2(Cluster_PKU2U): %x.", v21);
          if ( a6 >= 0xCu )
          {
            v14 = 0;
            LODWORD(v22) = (*(__int64 (__fastcall **)(struct IClusterSetup *, struct _CLUSTER_CERT *, __int64))(*(_QWORD *)v13 + 112LL))(
                             v13,
                             a4,
                             4);
            v15 = v22;
            TraceMsg(4, 0, L"ConfigClusterCert", 9044, L"ConfigClusterCertV2(ClusterLM_SChannel): %x.", v22);
            if ( v15 < 0 )
              v14 = v15;
            LODWORD(v23) = (*(__int64 (__fastcall **)(struct IClusterSetup *, struct _CLUSTER_CERT *, __int64))(*(_QWORD *)v13 + 112LL))(
                             v13,
                             a5,
                             5);
            CPrepSetupReference = v23;
            TraceMsg(4, 0, L"ConfigClusterCert", 9052, L"ConfigClusterCertV2(ClusterLM_PKU2U): %x.", v23);
            if ( CPrepSetupReference >= 0 && v14 < 0 )
              CPrepSetupReference = v14;
          }
        }
        (*(void (__fastcall **)(struct IClusterSetup *))(*(_QWORD *)v13 + 16LL))(v13);
        if ( v11 != -2147417850 )
          CoUninitialize();
      }
      else
      {
        return (unsigned int)-2147417852;
      }
    }
  }
  else
  {
    return v10;
  }
  return (unsigned int)CPrepSetupReference;
}

```

## disassembly

```asm
0x1800332b8  push    rbx
0x1800332ba  push    rbp
0x1800332bb  push    rsi
0x1800332bc  push    rdi
0x1800332bd  push    r12
0x1800332bf  push    r13
0x1800332c1  push    r14
0x1800332c3  push    r15
0x1800332c5  sub     rsp, 48h
0x1800332c9  xor     r12d, r12d
0x1800332cc  mov     rsi, rdx
0x1800332cf  mov     rbx, rcx
0x1800332d2  mov     [rsp+88h+var_58], r12
0x1800332d7  xor     ecx, ecx; pvReserved
0x1800332d9  mov     r15, r9
0x1800332dc  mov     r14, r8
0x1800332df  lea     r13d, [r12+4]
0x1800332e4  mov     edx, r13d; dwCoInit
0x1800332e7  call    cs:__imp_CoInitializeEx
0x1800332ed  mov     ebp, eax
0x1800332ef  cmp     eax, 1
0x1800332f2  jbe     short loc_180033302
0x1800332f4  cmp     eax, 80010106h
0x1800332f9  jz      short loc_180033302
0x1800332fb  mov     ebx, eax
0x1800332fd  jmp     loc_180033581
0x180033302  lea     rdx, [rsp+88h+var_58]; struct IClusterSetup **
0x180033307  mov     rcx, rbx; wchar_t *
0x18003330a  call    ?GetCPrepSetupReference@@YAJPEB_WPEAPEAUIClusterSetup@@@Z; GetCPrepSetupReference(wchar_t const *,IClusterSetup * *)
0x18003330f  mov     ebx, eax
0x180033311  test    eax, eax
0x180033313  jnz     loc_180033581
0x180033319  mov     rdi, [rsp+88h+var_58]
0x18003331e  test    rdi, rdi
0x180033321  jz      loc_18003357C
0x180033327  mov     rax, [rdi]
0x18003332a  xor     r8d, r8d
0x18003332d  mov     rdx, rsi
0x180033330  mov     rcx, rdi
0x180033333  mov     rax, [rax+70h]
0x180033337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003333c  mov     dword ptr [rsp+88h+var_60], eax
0x180033340  lea     r8, aConfigclusterc; "ConfigClusterCert"
0x180033347  mov     ebx, eax
0x180033349  mov     r9d, 2342h
0x18003334f  lea     rax, aConfigclusterc_2; "ConfigClusterCertV2(Cluster_SChannel): "...
0x180033356  xor     edx, edx
0x180033358  mov     ecx, r13d
0x18003335b  mov     [rsp+88h+var_68], rax
0x180033360  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180033365  test    ebx, ebx
0x180033367  js      loc_180033497
0x18003336d  cmp     [rsp+88h+arg_28], 0Ah
0x180033376  jb      loc_18003346F
0x18003337c  mov     rax, [rdi]
0x18003337f  mov     r8d, 2
0x180033385  mov     rdx, r14
0x180033388  mov     rcx, rdi
0x18003338b  mov     rax, [rax+70h]
0x18003338f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033394  mov     dword ptr [rsp+88h+var_60], eax
0x180033398  lea     r8, aConfigclusterc; "ConfigClusterCert"
0x18003339f  mov     ebx, eax
0x1800333a1  mov     r9d, 2348h
0x1800333a7  lea     rax, aConfigclusterc_0; "ConfigClusterCertV2(Cluster_PKU2U): %x."
0x1800333ae  xor     edx, edx
0x1800333b0  mov     ecx, r13d
0x1800333b3  mov     [rsp+88h+var_68], rax
0x1800333b8  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800333bd  cmp     [rsp+88h+arg_28], 0Ch
0x1800333c6  jb      loc_18003355D
0x1800333cc  mov     rax, [rdi]
0x1800333cf  mov     r8d, r13d
0x1800333d2  mov     rdx, r15
0x1800333d5  mov     rcx, rdi
0x1800333d8  mov     esi, r12d
0x1800333db  mov     rax, [rax+70h]
0x1800333df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800333e4  mov     dword ptr [rsp+88h+var_60], eax
0x1800333e8  lea     r8, aConfigclusterc; "ConfigClusterCert"
0x1800333ef  mov     ebx, eax
0x1800333f1  mov     r9d, 2354h
0x1800333f7  lea     rax, aConfigclusterc_4; "ConfigClusterCertV2(ClusterLM_SChannel)"...
0x1800333fe  xor     edx, edx
0x180033400  mov     ecx, r13d
0x180033403  mov     [rsp+88h+var_68], rax
0x180033408  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18003340d  mov     rax, [rdi]
0x180033410  test    ebx, ebx
0x180033412  mov     rdx, [rsp+88h+arg_20]
0x18003341a  mov     r8d, 5
0x180033420  mov     rcx, rdi
0x180033423  cmovs   esi, ebx
0x180033426  mov     rax, [rax+70h]
0x18003342a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003342f  mov     dword ptr [rsp+88h+var_60], eax
0x180033433  lea     r8, aConfigclusterc; "ConfigClusterCert"
0x18003343a  mov     ebx, eax
0x18003343c  mov     r9d, 235Ch
0x180033442  lea     rax, aConfigclusterc_3; "ConfigClusterCertV2(ClusterLM_PKU2U): %"...
0x180033449  xor     edx, edx
0x18003344b  mov     ecx, r13d
0x18003344e  mov     [rsp+88h+var_68], rax
0x180033453  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180033458  test    ebx, ebx
0x18003345a  js      loc_18003355D
0x180033460  test    esi, esi
0x180033462  jns     loc_18003355D
0x180033468  mov     ebx, esi
0x18003346a  jmp     loc_18003355D
0x18003346f  lea     rax, aConfigclusterc_5; "ConfigClusterCertV2(Cluster_PKU2U): fun"...
0x180033476  mov     r9d, 234Ch
0x18003347c  lea     r8, aConfigclusterc; "ConfigClusterCert"
0x180033483  mov     [rsp+88h+var_68], rax
0x180033488  xor     edx, edx
0x18003348a  mov     ecx, r13d
0x18003348d  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180033492  jmp     loc_18003355D
0x180033497  mov     rax, [rdi]
0x18003349a  mov     rdx, rsi
0x18003349d  mov     rcx, rdi
0x1800334a0  mov     rax, [rax+48h]
0x1800334a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800334a9  mov     dword ptr [rsp+88h+var_60], eax
0x1800334ad  lea     r8, aConfigclusterc; "ConfigClusterCert"
0x1800334b4  mov     ebx, eax
0x1800334b6  mov     r9d, 2366h
0x1800334bc  lea     rax, aConfigclusterc_1; "ConfigClusterCert: %x."
0x1800334c3  xor     edx, edx
0x1800334c5  mov     ecx, r13d
0x1800334c8  mov     [rsp+88h+var_68], rax
0x1800334cd  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800334d2  test    ebx, ebx
0x1800334d4  jns     loc_18003355D
0x1800334da  lea     rcx, [rsi+3C08h]; psz
0x1800334e1  call    cs:__imp_SysAllocString
0x1800334e7  mov     rcx, [rdi]
0x1800334ea  mov     rsi, rax
0x1800334ed  mov     rdx, rsi
0x1800334f0  mov     rax, [rcx+18h]
0x1800334f4  mov     rcx, rdi
0x1800334f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800334fc  mov     dword ptr [rsp+88h+var_60], eax
0x180033500  lea     r8, aConfigclusterc; "ConfigClusterCert"
0x180033507  mov     ebx, eax
0x180033509  mov     r9d, 236Ch
0x18003350f  lea     rax, aConfigsvcsecre; "ConfigSvcSecret: %x."
0x180033516  xor     edx, edx
0x180033518  mov     ecx, r13d
0x18003351b  mov     [rsp+88h+var_68], rax
0x180033520  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180033525  test    rsi, rsi
0x180033528  jz      short loc_18003355D
0x18003352a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003352e  inc     rax
0x180033531  cmp     [rsi+rax*2], r12w
0x180033536  jnz     short loc_18003352E
0x180033538  lea     rcx, ds:2[rax*2]
0x180033540  mov     rax, rsi
0x180033543  test    rcx, rcx
0x180033546  jz      short loc_180033554
0x180033548  mov     [rax], r12b
0x18003354b  inc     rax
0x18003354e  sub     rcx, 1
0x180033552  jnz     short loc_180033548
0x180033554  mov     rcx, rsi; bstrString
0x180033557  call    cs:__imp_SysFreeString
0x18003355d  mov     rax, [rdi]
0x180033560  mov     rcx, rdi
0x180033563  mov     rax, [rax+10h]
0x180033567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003356c  cmp     ebp, 80010106h
0x180033572  jz      short loc_180033581
0x180033574  call    cs:__imp_CoUninitialize
0x18003357a  jmp     short loc_180033581
0x18003357c  mov     ebx, 80010104h
0x180033581  mov     eax, ebx
0x180033583  add     rsp, 48h
0x180033587  pop     r15
0x180033589  pop     r14
0x18003358b  pop     r13
0x18003358d  pop     r12
0x18003358f  pop     rdi
0x180033590  pop     rsi
0x180033591  pop     rbp
0x180033592  pop     rbx
0x180033593  retn
```
