# NGenParser::ParseNewCommandLineHelper(int,ushort const * * const,NewCommandLineOptions &)

- ea: `0x1800100bc`
- end: `0x18001052d`
- name: `?ParseNewCommandLineHelper@NGenParser@@AEAA_NHQEAPEBGAEAUNewCommandLineOptions@@@Z`
- size: `1137`
- prototype: `bool __fastcall(NGenParser *__hidden this, int, const unsigned __int16 **const, struct NewCommandLineOptions *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180011e5c`

## callees

- `0x180001da0`
- `0x18000d138`
- `0x18000d394`
- `0x18000d5f0`
- `0x18000d96c`
- `0x18000d9e4`
- `0x18000d9f8`
- `0x18000dad4`
- `0x18000dbac`
- `0x1800100bc`
- `0x180030840`
- `0x180030d84`
- `0x180032654`
- `0x1800350c4`
- `0x180037c10`
- `0x18003dc30`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180010428`
- `KERNEL32!HeapFree` at `0x180010428`
- `KERNEL32!GetProcessHeap` at `0x180010413`
- `KERNEL32!GetProcessHeap` at `0x180010413`
- `OLEAUT32!__imp_SysAllocString` at `0x1800103c5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800103c5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800103d8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800103d8`

## string_xrefs

- `0x180010120`: `install`
- `0x180010148`: `uninstall`
- `0x180010174`: `update`
- `0x18001023d`: `createpdb`
- `0x180010268`: `removetaskboottrigger`
- `0x180010290`: `removetaskdelaystarttrigger`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
char __fastcall NGenParser::ParseNewCommandLineHelper(
        NGenParser *this,
        int a2,
        const unsigned __int16 **const a3,
        BSTR *a4)
{
  const unsigned __int16 *v6; // rsi
  int v7; // edi
  const unsigned __int16 **v8; // r14
  unsigned __int16 *v9; // rcx
  __int64 v10; // r9
  __int64 v11; // r9
  __int64 v12; // r9
  __int64 v13; // r9
  __int64 v14; // r9
  __int64 v15; // r9
  __int64 v16; // r9
  __int64 v17; // r9
  __int64 v18; // r9
  const unsigned __int16 *v19; // rsi
  __int64 v20; // r9
  int v21; // r8d
  OLECHAR *v22; // rsi
  __int64 v23; // rdx
  BSTR v24; // rsi
  OLECHAR *v25; // rsi
  HANDLE ProcessHeap; // rax
  const unsigned __int16 *v27; // rsi
  __int64 v28; // r9
  int v29; // ecx
  const struct SString *v31; // rax
  _BYTE v32[32]; // [rsp+30h] [rbp-D0h] BYREF
  int v33; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v34; // [rsp+54h] [rbp-ACh]
  OLECHAR *psz; // [rsp+60h] [rbp-A0h]
  _WORD v36[260]; // [rsp+68h] [rbp-98h] BYREF

  if ( a2 >= 1 )
  {
    v6 = *a3;
    v7 = a2 - 1;
    v8 = a3 + 1;
    if ( !(unsigned int)SString::CaseCompareHelper(*a3, L"install", 0, (__int64)a4, 1, 0) )
    {
      *(_DWORD *)a4 = 0;
LABEL_24:
      while ( v7 > 0 )
      {
        v19 = *v8;
        if ( !NGenParser::IsScenario((NGenParser *)v9, *v8, (enum __MIDL___MIDL_itf_mscorsvc_0001_0004_0001 *)(a4 + 3))
          && !NGenParser::IsCommandLineOption(this, v19, a4, v20) )
        {
          break;
        }
        --v7;
        ++v8;
      }
      if ( (*(_DWORD *)a4 & 0xFFFFFFFC) == 0 && *(_DWORD *)a4 != 2 )
      {
        if ( v7 < 1 )
          return 1;
        v34 = 512;
        psz = v36;
        v33 = 2;
        v36[0] = 0;
        v9 = (unsigned __int16 *)*v8;
        if ( ((**v8 - 45) & 0xFFFD) != 0 )
        {
          if ( !*(_DWORD *)a4 || (v21 = 0, *(_DWORD *)a4 == 3) )
            v21 = 1;
          CanonicalizePath(v9, (struct SString *)&v33, v21);
          if ( IsNgenOffline() )
          {
            SString::ConvertToUnicode((SString *)&v33);
            v22 = psz;
            if ( (unsigned int)IsExe(psz) || (unsigned int)IsDll(v22) || (unsigned int)IsWinMD(v22) )
            {
              v31 = (const struct SString *)SString::SString(
                                              v32,
                                              v23,
                                              L"Error: Only strong-named assemblies are allowed with offline ngen");
              ThrowHR(-2147024736, v31);
            }
          }
          SString::ConvertToUnicode((SString *)&v33);
          v24 = SysAllocString(psz);
          if ( *((_DWORD *)a4 + 4) )
          {
            SysFreeString(a4[1]);
            *((_DWORD *)a4 + 4) = 0;
          }
          a4[1] = v24;
          if ( v24 )
            *((_DWORD *)a4 + 4) = 1;
          --v7;
          ++v8;
        }
        if ( (v34 & 0x800000000LL) != 0 )
        {
          v25 = psz;
          if ( psz )
          {
            ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
            if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
            {
              ProcessHeap = GetProcessHeap();
              `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
            }
            HeapFree(ProcessHeap, 0, v25);
          }
        }
      }
      while ( v7 > 0 )
      {
        v27 = *v8;
        --v7;
        ++v8;
        if ( !NGenParser::IsScenario((NGenParser *)v9, v27, (enum __MIDL___MIDL_itf_mscorsvc_0001_0004_0001 *)(a4 + 3))
          && !NGenParser::IsCommandLineOption(this, v27, a4, v28) )
        {
          NGenParser::PrintLogoHelper(this);
          v34 = 512;
          psz = v36;
          v33 = 2;
          v36[0] = 0;
          SString::Printf((SString *)&v33, L"Error: Unrecognized option %s\n", v27);
          NGenParser::PrintUsageHelper(this);
          ThrowHR(-2147024809, (const struct SString *)&v33);
        }
      }
      if ( *(_DWORD *)a4 == 1 )
      {
        v29 = *((_DWORD *)a4 + 6);
        if ( v29 != 1 )
          *((_DWORD *)a4 + 6) = v29 & 0xFFFFFFFE;
      }
      return 1;
    }
    if ( !(unsigned int)SString::CaseCompareHelper(v6, L"uninstall", 0, v10, 1, 0) )
    {
      *(_DWORD *)a4 = 1;
      *((_DWORD *)a4 + 6) = 1;
      goto LABEL_24;
    }
    if ( !(unsigned int)SString::CaseCompareHelper(v6, L"update", 0, v11, 1, 0) )
    {
      *(_DWORD *)a4 = 2;
      goto LABEL_24;
    }
    if ( !(unsigned int)SString::CaseCompareHelper(v6, L"display", 0, v12, 1, 0) )
    {
      *(_DWORD *)a4 = 3;
      goto LABEL_24;
    }
    if ( !(unsigned int)SString::CaseCompareHelper(v6, L"executeQueuedItems", 0, v13, 1, 0)
      || !(unsigned int)SString::CaseCompareHelper(v6, L"eqi", 0, v14, 1, 0) )
    {
      *(_DWORD *)a4 = 4;
      *((_DWORD *)a4 + 42) = 3;
      goto LABEL_24;
    }
    if ( !(unsigned int)SString::CaseCompareHelper(v6, L"queue", 0, v15, 1, 0) )
    {
      *(_DWORD *)a4 = 5;
      goto LABEL_24;
    }
    if ( !(unsigned int)SString::CaseCompareHelper(v6, L"createpdb", 0, v16, 1, 0) )
    {
      *(_DWORD *)a4 = 6;
      goto LABEL_24;
    }
    if ( !(unsigned int)SString::CaseCompareHelper(v6, L"removetaskboottrigger", 0, v17, 1, 0) )
    {
      *(_DWORD *)a4 = 7;
      goto LABEL_24;
    }
    if ( !(unsigned int)SString::CaseCompareHelper(v6, L"removetaskdelaystarttrigger", 0, v18, 1, 0) )
    {
      *(_DWORD *)a4 = 8;
      goto LABEL_24;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800100bc  mov     [rsp-8+arg_8], rbx
0x1800100c1  push    rbp
0x1800100c2  push    rsi
0x1800100c3  push    rdi
0x1800100c4  push    r12
0x1800100c6  push    r13
0x1800100c8  push    r14
0x1800100ca  push    r15
0x1800100cc  lea     rbp, [rsp-180h]
0x1800100d4  sub     rsp, 280h
0x1800100db  mov     rax, cs:__security_cookie
0x1800100e2  xor     rax, rsp
0x1800100e5  mov     [rbp+1B0h+var_40], rax
0x1800100ec  mov     rbx, r9
0x1800100ef  mov     r14, r8
0x1800100f2  mov     edi, edx
0x1800100f4  mov     r12, rcx
0x1800100f7  mov     r15d, 1
0x1800100fd  cmp     edx, r15d
0x180010100  jl      loc_18001047F
0x180010106  mov     rsi, [r8]
0x180010109  sub     edi, r15d
0x18001010c  add     r14, 8
0x180010110  xor     r13d, r13d
0x180010113  mov     [rsp+2B0h+var_288], r13d; int
0x180010118  mov     [rsp+2B0h+var_290], r15d; int
0x18001011d  xor     r8d, r8d; unsigned int
0x180010120  lea     rdx, aInstall; "install"
0x180010127  mov     rcx, rsi; unsigned __int16 *
0x18001012a  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x18001012f  test    eax, eax
0x180010131  jnz     short loc_18001013B
0x180010133  mov     [rbx], r13d
0x180010136  jmp     loc_1800102EC
0x18001013b  mov     [rsp+2B0h+var_288], r13d; int
0x180010140  mov     [rsp+2B0h+var_290], r15d; int
0x180010145  xor     r8d, r8d; unsigned int
0x180010148  lea     rdx, aUninstall; "uninstall"
0x18001014f  mov     rcx, rsi; unsigned __int16 *
0x180010152  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x180010157  test    eax, eax
0x180010159  jnz     short loc_180010167
0x18001015b  mov     [rbx], r15d
0x18001015e  mov     [rbx+18h], r15d
0x180010162  jmp     loc_1800102EC
0x180010167  mov     [rsp+2B0h+var_288], r13d; int
0x18001016c  mov     [rsp+2B0h+var_290], r15d; int
0x180010171  xor     r8d, r8d; unsigned int
0x180010174  lea     rdx, aUpdate; "update"
0x18001017b  mov     rcx, rsi; unsigned __int16 *
0x18001017e  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x180010183  test    eax, eax
0x180010185  jnz     short loc_180010192
0x180010187  mov     dword ptr [rbx], 2
0x18001018d  jmp     loc_1800102EC
0x180010192  mov     [rsp+2B0h+var_288], r13d; int
0x180010197  mov     [rsp+2B0h+var_290], r15d; int
0x18001019c  xor     r8d, r8d; unsigned int
0x18001019f  lea     rdx, aDisplay; "display"
0x1800101a6  mov     rcx, rsi; unsigned __int16 *
0x1800101a9  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x1800101ae  test    eax, eax
0x1800101b0  jnz     short loc_1800101BD
0x1800101b2  mov     dword ptr [rbx], 3
0x1800101b8  jmp     loc_1800102EC
0x1800101bd  mov     [rsp+2B0h+var_288], r13d; int
0x1800101c2  mov     [rsp+2B0h+var_290], r15d; int
0x1800101c7  xor     r8d, r8d; unsigned int
0x1800101ca  lea     rdx, aExecutequeuedi; "executeQueuedItems"
0x1800101d1  mov     rcx, rsi; unsigned __int16 *
0x1800101d4  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x1800101d9  test    eax, eax
0x1800101db  jz      loc_1800102AF
0x1800101e1  mov     [rsp+2B0h+var_288], r13d; int
0x1800101e6  mov     [rsp+2B0h+var_290], r15d; int
0x1800101eb  xor     r8d, r8d; unsigned int
0x1800101ee  lea     rdx, aEqi; "eqi"
0x1800101f5  mov     rcx, rsi; unsigned __int16 *
0x1800101f8  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x1800101fd  test    eax, eax
0x1800101ff  jz      loc_1800102AF
0x180010205  mov     [rsp+2B0h+var_288], r13d; int
0x18001020a  mov     [rsp+2B0h+var_290], r15d; int
0x18001020f  xor     r8d, r8d; unsigned int
0x180010212  lea     rdx, aQueue_0; "queue"
0x180010219  mov     rcx, rsi; unsigned __int16 *
0x18001021c  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x180010221  test    eax, eax
0x180010223  jnz     short loc_180010230
0x180010225  mov     dword ptr [rbx], 5
0x18001022b  jmp     loc_1800102EC
0x180010230  mov     [rsp+2B0h+var_288], r13d; int
0x180010235  mov     [rsp+2B0h+var_290], r15d; int
0x18001023a  xor     r8d, r8d; unsigned int
0x18001023d  lea     rdx, aCreatepdb; "createpdb"
0x180010244  mov     rcx, rsi; unsigned __int16 *
0x180010247  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x18001024c  test    eax, eax
0x18001024e  jnz     short loc_18001025B
0x180010250  mov     dword ptr [rbx], 6
0x180010256  jmp     loc_1800102EC
0x18001025b  mov     [rsp+2B0h+var_288], r13d; int
0x180010260  mov     [rsp+2B0h+var_290], r15d; int
0x180010265  xor     r8d, r8d; unsigned int
0x180010268  lea     rdx, aRemovetaskboot; "removetaskboottrigger"
0x18001026f  mov     rcx, rsi; unsigned __int16 *
0x180010272  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x180010277  test    eax, eax
0x180010279  jnz     short loc_180010283
0x18001027b  mov     dword ptr [rbx], 7
0x180010281  jmp     short loc_1800102EC
0x180010283  mov     [rsp+2B0h+var_288], r13d; int
0x180010288  mov     [rsp+2B0h+var_290], r15d; int
0x18001028d  xor     r8d, r8d; unsigned int
0x180010290  lea     rdx, aRemovetaskdela; "removetaskdelaystarttrigger"
0x180010297  mov     rcx, rsi; unsigned __int16 *
0x18001029a  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x18001029f  test    eax, eax
0x1800102a1  jnz     loc_18001047F
0x1800102a7  mov     dword ptr [rbx], 8
0x1800102ad  jmp     short loc_1800102EC
0x1800102af  mov     dword ptr [rbx], 4
0x1800102b5  mov     dword ptr [rbx+0A8h], 3
0x1800102bf  jmp     short loc_1800102EC
0x1800102c1  mov     rsi, [r14]
0x1800102c4  lea     r8, [rbx+18h]; enum __MIDL___MIDL_itf_mscorsvc_0001_0004_0001 *
0x1800102c8  mov     rdx, rsi; unsigned __int16 *
0x1800102cb  call    ?IsScenario@NGenParser@@AEAA_NPEBGPEAW4__MIDL___MIDL_itf_mscorsvc_0001_0004_0001@@@Z; NGenParser::IsScenario(ushort const *,__MIDL___MIDL_itf_mscorsvc_0001_0004_0001 *)
0x1800102d0  test    al, al
0x1800102d2  jnz     short loc_1800102E6
0x1800102d4  mov     r8, rbx; struct NewCommandLineOptions *
0x1800102d7  mov     rdx, rsi; unsigned __int16 *
0x1800102da  mov     rcx, r12; this
0x1800102dd  call    ?IsCommandLineOption@NGenParser@@AEAA_NPEBGAEAUNewCommandLineOptions@@@Z; NGenParser::IsCommandLineOption(ushort const *,NewCommandLineOptions &)
0x1800102e2  test    al, al
0x1800102e4  jz      short loc_1800102F0
0x1800102e6  dec     edi
0x1800102e8  add     r14, 8
0x1800102ec  test    edi, edi
0x1800102ee  jg      short loc_1800102C1
0x1800102f0  test    dword ptr [rbx], 0FFFFFFFCh
0x1800102f6  jnz     loc_18001042E
0x1800102fc  cmp     dword ptr [rbx], 2
0x1800102ff  jz      loc_18001042E
0x180010305  cmp     edi, r15d
0x180010308  jl      loc_18001047A
0x18001030e  mov     [rsp+2B0h+var_260], r13
0x180010313  mov     [rsp+2B0h+var_260+4], 200h
0x18001031c  mov     [rsp+2B0h+psz], r13
0x180010321  lea     rax, [rsp+2B0h+var_248]
0x180010326  mov     [rsp+2B0h+psz], rax
0x18001032b  mov     dword ptr [rsp+2B0h+var_260], 2
0x180010333  mov     rax, [rsp+2B0h+psz]
0x180010338  mov     [rax], r13w
0x18001033c  mov     rcx, [r14]; unsigned __int16 *
0x18001033f  movzx   eax, word ptr [rcx]
0x180010342  sub     ax, 2Dh ; '-'
0x180010346  mov     edx, 0FFFDh
0x18001034b  test    dx, ax
0x18001034e  jz      loc_1800103F6
0x180010354  cmp     [rbx], r13d
0x180010357  jz      short loc_180010361
0x180010359  cmp     dword ptr [rbx], 3
0x18001035c  mov     r8d, r13d
0x18001035f  jnz     short loc_180010364
0x180010361  mov     r8d, r15d; int
0x180010364  lea     rdx, [rsp+2B0h+var_260]; this
0x180010369  call    ?CanonicalizePath@@YAXPEBGAEAVSString@@H@Z; CanonicalizePath(ushort const *,SString &,int)
0x18001036e  call    ?IsNgenOffline@@YA_NXZ; IsNgenOffline(void)
0x180010373  test    al, al
0x180010375  jz      short loc_1800103B6
0x180010377  lea     rcx, [rsp+2B0h+var_260]; this
0x18001037c  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180010381  mov     rsi, [rsp+2B0h+psz]
0x180010386  mov     rcx, rsi; unsigned __int16 *
0x180010389  call    ?IsExe@@YAHPEBG@Z; IsExe(ushort const *)
0x18001038e  test    eax, eax
0x180010390  jnz     loc_18001050D
0x180010396  mov     rcx, rsi; unsigned __int16 *
0x180010399  call    ?IsDll@@YAHPEBG@Z; IsDll(ushort const *)
0x18001039e  test    eax, eax
0x1800103a0  jnz     loc_18001050D
0x1800103a6  mov     rcx, rsi; unsigned __int16 *
0x1800103a9  call    ?IsWinMD@@YAHPEBG@Z; IsWinMD(ushort const *)
0x1800103ae  test    eax, eax
0x1800103b0  jnz     loc_18001050D
0x1800103b6  lea     rcx, [rsp+2B0h+var_260]; this
0x1800103bb  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x1800103c0  mov     rcx, [rsp+2B0h+psz]; psz
0x1800103c5  call    cs:__imp_SysAllocString
0x1800103cb  mov     rsi, rax
0x1800103ce  cmp     [rbx+10h], r13d
0x1800103d2  jz      short loc_1800103E2
0x1800103d4  mov     rcx, [rbx+8]; bstrString
0x1800103d8  call    cs:__imp_SysFreeString
0x1800103de  mov     [rbx+10h], r13d
0x1800103e2  mov     [rbx+8], rsi
0x1800103e6  test    rsi, rsi
0x1800103e9  jz      short loc_1800103EF
0x1800103eb  mov     [rbx+10h], r15d
0x1800103ef  sub     edi, r15d
0x1800103f2  add     r14, 8
0x1800103f6  test    [rsp+2B0h+var_258], 8
0x1800103fb  jz      short loc_18001042E
0x1800103fd  mov     rsi, [rsp+2B0h+psz]
0x180010402  test    rsi, rsi
0x180010405  jz      short loc_18001042E
0x180010407  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18001040e  test    rax, rax
0x180010411  jnz     short loc_180010420
0x180010413  call    cs:__imp_GetProcessHeap
0x180010419  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180010420  mov     r8, rsi; lpMem
0x180010423  xor     edx, edx; dwFlags
0x180010425  mov     rcx, rax; hHeap
0x180010428  call    cs:__imp_HeapFree
0x18001042e  test    edi, edi
0x180010430  jle     short loc_180010467
0x180010432  mov     rsi, [r14]
0x180010435  dec     edi
0x180010437  lea     r14, [r14+8]
0x18001043b  lea     r8, [rbx+18h]; enum __MIDL___MIDL_itf_mscorsvc_0001_0004_0001 *
0x18001043f  mov     rdx, rsi; unsigned __int16 *
0x180010442  call    ?IsScenario@NGenParser@@AEAA_NPEBGPEAW4__MIDL___MIDL_itf_mscorsvc_0001_0004_0001@@@Z; NGenParser::IsScenario(ushort const *,__MIDL___MIDL_itf_mscorsvc_0001_0004_0001 *)
0x180010447  test    al, al
0x180010449  jnz     short loc_18001045D
0x18001044b  mov     r8, rbx; struct NewCommandLineOptions *
0x18001044e  mov     rdx, rsi; unsigned __int16 *
0x180010451  mov     rcx, r12; this
0x180010454  call    ?IsCommandLineOption@NGenParser@@AEAA_NPEBGAEAUNewCommandLineOptions@@@Z; NGenParser::IsCommandLineOption(ushort const *,NewCommandLineOptions &)
0x180010459  test    al, al
0x18001045b  jz      short loc_1800104AB
0x18001045d  test    edi, edi
0x18001045f  jg      short loc_180010432
0x180010461  mov     r15d, 1
0x180010467  cmp     [rbx], r15d
0x18001046a  jnz     short loc_18001047A
0x18001046c  mov     ecx, [rbx+18h]
0x18001046f  cmp     ecx, r15d
0x180010472  jz      short loc_18001047A
0x180010474  and     ecx, 0FFFFFFFEh
0x180010477  mov     [rbx+18h], ecx
0x18001047a  mov     al, r15b
0x18001047d  jmp     short loc_180010481
0x18001047f  xor     al, al
0x180010481  mov     rcx, [rbp+1B0h+var_40]
0x180010488  xor     rcx, rsp; StackCookie
0x18001048b  call    __security_check_cookie
0x180010490  mov     rbx, [rsp+2B0h+arg_8]
0x180010498  add     rsp, 280h
0x18001049f  pop     r15
0x1800104a1  pop     r14
0x1800104a3  pop     r13
0x1800104a5  pop     r12
0x1800104a7  pop     rdi
0x1800104a8  pop     rsi
0x1800104a9  pop     rbp
0x1800104aa  retn
0x1800104ab  mov     rcx, r12; this
0x1800104ae  call    ?PrintLogoHelper@NGenParser@@AEAAXXZ; NGenParser::PrintLogoHelper(void)
0x1800104b3  mov     [rsp+2B0h+var_260], r13
0x1800104b8  mov     [rsp+2B0h+var_260+4], 200h
0x1800104c1  mov     [rsp+2B0h+psz], r13
0x1800104c6  lea     rax, [rsp+2B0h+var_248]
0x1800104cb  mov     [rsp+2B0h+psz], rax
0x1800104d0  mov     dword ptr [rsp+2B0h+var_260], 2
0x1800104d8  mov     rax, [rsp+2B0h+psz]
0x1800104dd  mov     [rax], r13w
0x1800104e1  mov     r8, rsi
0x1800104e4  lea     rdx, aErrorUnrecogni_0; "Error: Unrecognized option %s\n"
0x1800104eb  lea     rcx, [rsp+2B0h+var_260]; this
0x1800104f0  call    ?Printf@SString@@QEAAXPEBGZZ; SString::Printf(ushort const *,...)
0x1800104f5  mov     rcx, r12; this
0x1800104f8  call    ?PrintUsageHelper@NGenParser@@AEAAXXZ; NGenParser::PrintUsageHelper(void)
0x1800104fd  lea     rdx, [rsp+2B0h+var_260]; struct SString *
0x180010502  mov     ecx, 80070057h; int
0x180010507  call    ?ThrowHR@@YAXJAEBVSString@@@Z; ThrowHR(long,SString const &)
0x18001050d  lea     r8, aErrorOnlyStron; "Error: Only strong-named assemblies are"...
0x180010514  lea     rcx, [rsp+2B0h+var_280]
0x180010519  call    ??0SString@@QEAA@W4tagLiteral@0@PEBG@Z; SString::SString(SString::tagLiteral,ushort const *)
0x18001051e  nop
0x18001051f  mov     rdx, rax; struct SString *
0x180010522  mov     ecx, 800700A0h; int
0x180010527  call    ?ThrowHR@@YAXJAEBVSString@@@Z; ThrowHR(long,SString const &)
```
