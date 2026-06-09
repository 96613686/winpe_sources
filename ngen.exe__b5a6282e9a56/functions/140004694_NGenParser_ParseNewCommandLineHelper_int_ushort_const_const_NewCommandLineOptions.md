# NGenParser::ParseNewCommandLineHelper(int,ushort const * * const,NewCommandLineOptions &)

- ea: `0x140004694`
- end: `0x140004b05`
- name: `?ParseNewCommandLineHelper@NGenParser@@AEAA_NHQEAPEBGAEAUNewCommandLineOptions@@@Z`
- size: `1137`
- prototype: `char __fastcall(NGenParser *this, int, const unsigned __int16 **const, BSTR *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1400081f8`

## callees

- `0x1400011d4`
- `0x1400016f4`
- `0x140001950`
- `0x140001bac`
- `0x140001f28`
- `0x140001fa0`
- `0x140001fb4`
- `0x140002090`
- `0x140002168`
- `0x140004694`
- `0x14000ab08`
- `0x14000b010`
- `0x14000bd40`
- `0x14000e5e4`
- `0x140010454`
- `0x140013200`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140004a00`
- `KERNEL32!HeapFree` at `0x140004a00`
- `KERNEL32!GetProcessHeap` at `0x1400049eb`
- `KERNEL32!GetProcessHeap` at `0x1400049eb`
- `OLEAUT32!__imp_SysAllocString` at `0x14000499d`
- `OLEAUT32!__imp_SysAllocString` at `0x14000499d`
- `OLEAUT32!__imp_SysFreeString` at `0x1400049b0`
- `OLEAUT32!__imp_SysFreeString` at `0x1400049b0`

## string_xrefs

- `0x1400046f8`: `install`
- `0x140004720`: `uninstall`
- `0x14000474c`: `update`
- `0x140004815`: `createpdb`
- `0x140004840`: `removetaskboottrigger`
- `0x140004868`: `removetaskdelaystarttrigger`

## pseudocode

```c
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
0x140004694  mov     [rsp-8+arg_8], rbx
0x140004699  push    rbp
0x14000469a  push    rsi
0x14000469b  push    rdi
0x14000469c  push    r12
0x14000469e  push    r13
0x1400046a0  push    r14
0x1400046a2  push    r15
0x1400046a4  lea     rbp, [rsp-180h]
0x1400046ac  sub     rsp, 280h
0x1400046b3  mov     rax, cs:__security_cookie
0x1400046ba  xor     rax, rsp
0x1400046bd  mov     [rbp+1B0h+var_40], rax
0x1400046c4  mov     rbx, r9
0x1400046c7  mov     r14, r8
0x1400046ca  mov     edi, edx
0x1400046cc  mov     r12, rcx
0x1400046cf  mov     r15d, 1
0x1400046d5  cmp     edx, r15d
0x1400046d8  jl      loc_140004A57
0x1400046de  mov     rsi, [r8]
0x1400046e1  sub     edi, r15d
0x1400046e4  add     r14, 8
0x1400046e8  xor     r13d, r13d
0x1400046eb  mov     [rsp+2B0h+var_288], r13d; int
0x1400046f0  mov     [rsp+2B0h+var_290], r15d; int
0x1400046f5  xor     r8d, r8d; unsigned int
0x1400046f8  lea     rdx, aInstall; "install"
0x1400046ff  mov     rcx, rsi; unsigned __int16 *
0x140004702  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x140004707  test    eax, eax
0x140004709  jnz     short loc_140004713
0x14000470b  mov     [rbx], r13d
0x14000470e  jmp     loc_1400048C4
0x140004713  mov     [rsp+2B0h+var_288], r13d; int
0x140004718  mov     [rsp+2B0h+var_290], r15d; int
0x14000471d  xor     r8d, r8d; unsigned int
0x140004720  lea     rdx, aUninstall; "uninstall"
0x140004727  mov     rcx, rsi; unsigned __int16 *
0x14000472a  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x14000472f  test    eax, eax
0x140004731  jnz     short loc_14000473F
0x140004733  mov     [rbx], r15d
0x140004736  mov     [rbx+18h], r15d
0x14000473a  jmp     loc_1400048C4
0x14000473f  mov     [rsp+2B0h+var_288], r13d; int
0x140004744  mov     [rsp+2B0h+var_290], r15d; int
0x140004749  xor     r8d, r8d; unsigned int
0x14000474c  lea     rdx, aUpdate; "update"
0x140004753  mov     rcx, rsi; unsigned __int16 *
0x140004756  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x14000475b  test    eax, eax
0x14000475d  jnz     short loc_14000476A
0x14000475f  mov     dword ptr [rbx], 2
0x140004765  jmp     loc_1400048C4
0x14000476a  mov     [rsp+2B0h+var_288], r13d; int
0x14000476f  mov     [rsp+2B0h+var_290], r15d; int
0x140004774  xor     r8d, r8d; unsigned int
0x140004777  lea     rdx, aDisplay; "display"
0x14000477e  mov     rcx, rsi; unsigned __int16 *
0x140004781  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x140004786  test    eax, eax
0x140004788  jnz     short loc_140004795
0x14000478a  mov     dword ptr [rbx], 3
0x140004790  jmp     loc_1400048C4
0x140004795  mov     [rsp+2B0h+var_288], r13d; int
0x14000479a  mov     [rsp+2B0h+var_290], r15d; int
0x14000479f  xor     r8d, r8d; unsigned int
0x1400047a2  lea     rdx, aExecutequeuedi; "executeQueuedItems"
0x1400047a9  mov     rcx, rsi; unsigned __int16 *
0x1400047ac  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x1400047b1  test    eax, eax
0x1400047b3  jz      loc_140004887
0x1400047b9  mov     [rsp+2B0h+var_288], r13d; int
0x1400047be  mov     [rsp+2B0h+var_290], r15d; int
0x1400047c3  xor     r8d, r8d; unsigned int
0x1400047c6  lea     rdx, aEqi; "eqi"
0x1400047cd  mov     rcx, rsi; unsigned __int16 *
0x1400047d0  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x1400047d5  test    eax, eax
0x1400047d7  jz      loc_140004887
0x1400047dd  mov     [rsp+2B0h+var_288], r13d; int
0x1400047e2  mov     [rsp+2B0h+var_290], r15d; int
0x1400047e7  xor     r8d, r8d; unsigned int
0x1400047ea  lea     rdx, aQueue_0; "queue"
0x1400047f1  mov     rcx, rsi; unsigned __int16 *
0x1400047f4  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x1400047f9  test    eax, eax
0x1400047fb  jnz     short loc_140004808
0x1400047fd  mov     dword ptr [rbx], 5
0x140004803  jmp     loc_1400048C4
0x140004808  mov     [rsp+2B0h+var_288], r13d; int
0x14000480d  mov     [rsp+2B0h+var_290], r15d; int
0x140004812  xor     r8d, r8d; unsigned int
0x140004815  lea     rdx, aCreatepdb; "createpdb"
0x14000481c  mov     rcx, rsi; unsigned __int16 *
0x14000481f  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x140004824  test    eax, eax
0x140004826  jnz     short loc_140004833
0x140004828  mov     dword ptr [rbx], 6
0x14000482e  jmp     loc_1400048C4
0x140004833  mov     [rsp+2B0h+var_288], r13d; int
0x140004838  mov     [rsp+2B0h+var_290], r15d; int
0x14000483d  xor     r8d, r8d; unsigned int
0x140004840  lea     rdx, aRemovetaskboot; "removetaskboottrigger"
0x140004847  mov     rcx, rsi; unsigned __int16 *
0x14000484a  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x14000484f  test    eax, eax
0x140004851  jnz     short loc_14000485B
0x140004853  mov     dword ptr [rbx], 7
0x140004859  jmp     short loc_1400048C4
0x14000485b  mov     [rsp+2B0h+var_288], r13d; int
0x140004860  mov     [rsp+2B0h+var_290], r15d; int
0x140004865  xor     r8d, r8d; unsigned int
0x140004868  lea     rdx, aRemovetaskdela; "removetaskdelaystarttrigger"
0x14000486f  mov     rcx, rsi; unsigned __int16 *
0x140004872  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x140004877  test    eax, eax
0x140004879  jnz     loc_140004A57
0x14000487f  mov     dword ptr [rbx], 8
0x140004885  jmp     short loc_1400048C4
0x140004887  mov     dword ptr [rbx], 4
0x14000488d  mov     dword ptr [rbx+0A8h], 3
0x140004897  jmp     short loc_1400048C4
0x140004899  mov     rsi, [r14]
0x14000489c  lea     r8, [rbx+18h]; enum __MIDL___MIDL_itf_mscorsvc_0001_0004_0001 *
0x1400048a0  mov     rdx, rsi; unsigned __int16 *
0x1400048a3  call    ?IsScenario@NGenParser@@AEAA_NPEBGPEAW4__MIDL___MIDL_itf_mscorsvc_0001_0004_0001@@@Z; NGenParser::IsScenario(ushort const *,__MIDL___MIDL_itf_mscorsvc_0001_0004_0001 *)
0x1400048a8  test    al, al
0x1400048aa  jnz     short loc_1400048BE
0x1400048ac  mov     r8, rbx; struct NewCommandLineOptions *
0x1400048af  mov     rdx, rsi; unsigned __int16 *
0x1400048b2  mov     rcx, r12; this
0x1400048b5  call    ?IsCommandLineOption@NGenParser@@AEAA_NPEBGAEAUNewCommandLineOptions@@@Z; NGenParser::IsCommandLineOption(ushort const *,NewCommandLineOptions &)
0x1400048ba  test    al, al
0x1400048bc  jz      short loc_1400048C8
0x1400048be  dec     edi
0x1400048c0  add     r14, 8
0x1400048c4  test    edi, edi
0x1400048c6  jg      short loc_140004899
0x1400048c8  test    dword ptr [rbx], 0FFFFFFFCh
0x1400048ce  jnz     loc_140004A06
0x1400048d4  cmp     dword ptr [rbx], 2
0x1400048d7  jz      loc_140004A06
0x1400048dd  cmp     edi, r15d
0x1400048e0  jl      loc_140004A52
0x1400048e6  mov     [rsp+2B0h+var_260], r13
0x1400048eb  mov     [rsp+2B0h+var_260+4], 200h
0x1400048f4  mov     [rsp+2B0h+psz], r13
0x1400048f9  lea     rax, [rsp+2B0h+var_248]
0x1400048fe  mov     [rsp+2B0h+psz], rax
0x140004903  mov     dword ptr [rsp+2B0h+var_260], 2
0x14000490b  mov     rax, [rsp+2B0h+psz]
0x140004910  mov     [rax], r13w
0x140004914  mov     rcx, [r14]; unsigned __int16 *
0x140004917  movzx   eax, word ptr [rcx]
0x14000491a  sub     ax, 2Dh ; '-'
0x14000491e  mov     edx, 0FFFDh
0x140004923  test    dx, ax
0x140004926  jz      loc_1400049CE
0x14000492c  cmp     [rbx], r13d
0x14000492f  jz      short loc_140004939
0x140004931  cmp     dword ptr [rbx], 3
0x140004934  mov     r8d, r13d
0x140004937  jnz     short loc_14000493C
0x140004939  mov     r8d, r15d; int
0x14000493c  lea     rdx, [rsp+2B0h+var_260]; this
0x140004941  call    ?CanonicalizePath@@YAXPEBGAEAVSString@@H@Z; CanonicalizePath(ushort const *,SString &,int)
0x140004946  call    ?IsNgenOffline@@YA_NXZ; IsNgenOffline(void)
0x14000494b  test    al, al
0x14000494d  jz      short loc_14000498E
0x14000494f  lea     rcx, [rsp+2B0h+var_260]; this
0x140004954  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x140004959  mov     rsi, [rsp+2B0h+psz]
0x14000495e  mov     rcx, rsi; unsigned __int16 *
0x140004961  call    ?IsExe@@YAHPEBG@Z; IsExe(ushort const *)
0x140004966  test    eax, eax
0x140004968  jnz     loc_140004AE5
0x14000496e  mov     rcx, rsi; unsigned __int16 *
0x140004971  call    ?IsDll@@YAHPEBG@Z; IsDll(ushort const *)
0x140004976  test    eax, eax
0x140004978  jnz     loc_140004AE5
0x14000497e  mov     rcx, rsi; unsigned __int16 *
0x140004981  call    ?IsWinMD@@YAHPEBG@Z; IsWinMD(ushort const *)
0x140004986  test    eax, eax
0x140004988  jnz     loc_140004AE5
0x14000498e  lea     rcx, [rsp+2B0h+var_260]; this
0x140004993  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x140004998  mov     rcx, [rsp+2B0h+psz]; psz
0x14000499d  call    cs:__imp_SysAllocString
0x1400049a3  mov     rsi, rax
0x1400049a6  cmp     [rbx+10h], r13d
0x1400049aa  jz      short loc_1400049BA
0x1400049ac  mov     rcx, [rbx+8]; bstrString
0x1400049b0  call    cs:__imp_SysFreeString
0x1400049b6  mov     [rbx+10h], r13d
0x1400049ba  mov     [rbx+8], rsi
0x1400049be  test    rsi, rsi
0x1400049c1  jz      short loc_1400049C7
0x1400049c3  mov     [rbx+10h], r15d
0x1400049c7  sub     edi, r15d
0x1400049ca  add     r14, 8
0x1400049ce  test    [rsp+2B0h+var_258], 8
0x1400049d3  jz      short loc_140004A06
0x1400049d5  mov     rsi, [rsp+2B0h+psz]
0x1400049da  test    rsi, rsi
0x1400049dd  jz      short loc_140004A06
0x1400049df  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1400049e6  test    rax, rax
0x1400049e9  jnz     short loc_1400049F8
0x1400049eb  call    cs:__imp_GetProcessHeap
0x1400049f1  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1400049f8  mov     r8, rsi; lpMem
0x1400049fb  xor     edx, edx; dwFlags
0x1400049fd  mov     rcx, rax; hHeap
0x140004a00  call    cs:__imp_HeapFree
0x140004a06  test    edi, edi
0x140004a08  jle     short loc_140004A3F
0x140004a0a  mov     rsi, [r14]
0x140004a0d  dec     edi
0x140004a0f  lea     r14, [r14+8]
0x140004a13  lea     r8, [rbx+18h]; enum __MIDL___MIDL_itf_mscorsvc_0001_0004_0001 *
0x140004a17  mov     rdx, rsi; unsigned __int16 *
0x140004a1a  call    ?IsScenario@NGenParser@@AEAA_NPEBGPEAW4__MIDL___MIDL_itf_mscorsvc_0001_0004_0001@@@Z; NGenParser::IsScenario(ushort const *,__MIDL___MIDL_itf_mscorsvc_0001_0004_0001 *)
0x140004a1f  test    al, al
0x140004a21  jnz     short loc_140004A35
0x140004a23  mov     r8, rbx; struct NewCommandLineOptions *
0x140004a26  mov     rdx, rsi; unsigned __int16 *
0x140004a29  mov     rcx, r12; this
0x140004a2c  call    ?IsCommandLineOption@NGenParser@@AEAA_NPEBGAEAUNewCommandLineOptions@@@Z; NGenParser::IsCommandLineOption(ushort const *,NewCommandLineOptions &)
0x140004a31  test    al, al
0x140004a33  jz      short loc_140004A83
0x140004a35  test    edi, edi
0x140004a37  jg      short loc_140004A0A
0x140004a39  mov     r15d, 1
0x140004a3f  cmp     [rbx], r15d
0x140004a42  jnz     short loc_140004A52
0x140004a44  mov     ecx, [rbx+18h]
0x140004a47  cmp     ecx, r15d
0x140004a4a  jz      short loc_140004A52
0x140004a4c  and     ecx, 0FFFFFFFEh
0x140004a4f  mov     [rbx+18h], ecx
0x140004a52  mov     al, r15b
0x140004a55  jmp     short loc_140004A59
0x140004a57  xor     al, al
0x140004a59  mov     rcx, [rbp+1B0h+var_40]
0x140004a60  xor     rcx, rsp; StackCookie
0x140004a63  call    __security_check_cookie
0x140004a68  mov     rbx, [rsp+2B0h+arg_8]
0x140004a70  add     rsp, 280h
0x140004a77  pop     r15
0x140004a79  pop     r14
0x140004a7b  pop     r13
0x140004a7d  pop     r12
0x140004a7f  pop     rdi
0x140004a80  pop     rsi
0x140004a81  pop     rbp
0x140004a82  retn
0x140004a83  mov     rcx, r12; this
0x140004a86  call    ?PrintLogoHelper@NGenParser@@AEAAXXZ; NGenParser::PrintLogoHelper(void)
0x140004a8b  mov     [rsp+2B0h+var_260], r13
0x140004a90  mov     [rsp+2B0h+var_260+4], 200h
0x140004a99  mov     [rsp+2B0h+psz], r13
0x140004a9e  lea     rax, [rsp+2B0h+var_248]
0x140004aa3  mov     [rsp+2B0h+psz], rax
0x140004aa8  mov     dword ptr [rsp+2B0h+var_260], 2
0x140004ab0  mov     rax, [rsp+2B0h+psz]
0x140004ab5  mov     [rax], r13w
0x140004ab9  mov     r8, rsi
0x140004abc  lea     rdx, aErrorUnrecogni_1; "Error: Unrecognized option %s\n"
0x140004ac3  lea     rcx, [rsp+2B0h+var_260]; this
0x140004ac8  call    ?Printf@SString@@QEAAXPEBGZZ; SString::Printf(ushort const *,...)
0x140004acd  mov     rcx, r12; this
0x140004ad0  call    ?PrintUsageHelper@NGenParser@@AEAAXXZ; NGenParser::PrintUsageHelper(void)
0x140004ad5  lea     rdx, [rsp+2B0h+var_260]; struct SString *
0x140004ada  mov     ecx, 80070057h; int
0x140004adf  call    ?ThrowHR@@YAXJAEBVSString@@@Z; ThrowHR(long,SString const &)
0x140004ae5  lea     r8, aErrorOnlyStron; "Error: Only strong-named assemblies are"...
0x140004aec  lea     rcx, [rsp+2B0h+var_280]
0x140004af1  call    ??0SString@@QEAA@W4tagLiteral@0@PEBG@Z; SString::SString(SString::tagLiteral,ushort const *)
0x140004af6  nop
0x140004af7  mov     rdx, rax; struct SString *
0x140004afa  mov     ecx, 800700A0h; int
0x140004aff  call    ?ThrowHR@@YAXJAEBVSString@@@Z; ThrowHR(long,SString const &)
```
