# Configuration::Dump(Logger)

- ea: `0x18002c880`
- end: `0x18002ce45`
- name: `?Dump@Configuration@@QEAAXVLogger@@@Z`
- size: `1477`
- prototype: `int __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18002ce48`

## callees

- `0x180001de0`
- `0x180001e8c`
- `0x18000d138`
- `0x18002c880`
- `0x18002dc24`
- `0x180030ab8`
- `0x180030d84`
- `0x180032654`
- `0x180032948`
- `0x180032fe8`
- `0x18003dc30`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18002cb41`
- `KERNEL32!HeapFree` at `0x18002cddc`
- `KERNEL32!HeapFree` at `0x18002ce15`
- `KERNEL32!HeapFree` at `0x18002cb41`
- `KERNEL32!HeapFree` at `0x18002cddc`
- `KERNEL32!HeapFree` at `0x18002ce15`
- `KERNEL32!GetProcessHeap` at `0x18002cb2c`
- `KERNEL32!GetProcessHeap` at `0x18002cdc7`
- `KERNEL32!GetProcessHeap` at `0x18002ce00`
- `KERNEL32!GetProcessHeap` at `0x18002cb2c`
- `KERNEL32!GetProcessHeap` at `0x18002cdc7`
- `KERNEL32!GetProcessHeap` at `0x18002ce00`

## string_xrefs

- `0x18002cac7`: `, ConfigExe = %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=30
int __fastcall Configuration::Dump(__int64 a1, __int64 a2)
{
  int v3; // r14d
  int v4; // esi
  unsigned __int16 *v5; // rbx
  __int64 v6; // rbx
  const unsigned __int16 *v7; // rcx
  int v8; // eax
  __int64 v9; // rbx
  __int64 v10; // r8
  __int64 v11; // r8
  void *v12; // rbx
  HANDLE ProcessHeap; // rax
  int v14; // eax
  __int64 v15; // r8
  unsigned int v16; // r15d
  __int64 v17; // rbx
  const unsigned __int16 *const near *v18; // r14
  __int64 v19; // rsi
  __int64 v20; // r8
  SString *v21; // rsi
  __int64 v22; // rsi
  unsigned int v23; // r14d
  __int64 v24; // rax
  __int64 v25; // rsi
  __int64 v26; // r8
  unsigned int v27; // r14d
  __int64 v28; // rax
  __int64 v29; // rsi
  __int64 v30; // r8
  int result; // eax
  void *v32; // rbx
  HANDLE v33; // rax
  void *v34; // rbx
  HANDLE v35; // rax
  int v36; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v37; // [rsp+24h] [rbp-DCh]
  LPVOID v38; // [rsp+30h] [rbp-D0h]
  __int16 v39; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v40; // [rsp+240h] [rbp+140h] BYREF
  __int64 v41; // [rsp+244h] [rbp+144h]
  LPVOID v42; // [rsp+250h] [rbp+150h]
  __int16 v43; // [rsp+258h] [rbp+158h] BYREF
  int v44; // [rsp+460h] [rbp+360h] BYREF
  __int64 v45; // [rsp+464h] [rbp+364h]
  LPVOID lpMem; // [rsp+470h] [rbp+370h]
  __int16 v47; // [rsp+478h] [rbp+378h] BYREF
  __int64 v48; // [rsp+6D8h] [rbp+5D8h] BYREF

  v48 = a2;
  v37 = 512;
  v38 = &v39;
  v36 = 2;
  v39 = 0;
  SString::Printf((SString *)&v36, L"    ");
  v41 = 512;
  v42 = &v43;
  v40 = 2;
  v43 = 0;
  v3 = *(_DWORD *)(a1 + 24);
  if ( v3 )
  {
    SString::Clear((SString *)&v40);
    v4 = 1;
    do
    {
      if ( (v3 & v4) != 0 )
      {
        switch ( v4 )
        {
          case 1:
            v5 = L"ScenarioAll";
            break;
          case 2:
            v5 = L"ScenarioDebug";
            break;
          case 8:
            v5 = L"ScenarioProfile";
            break;
          case 0x10:
            v5 = L"ScenarioTuningDataCollection";
            break;
          case 0x20:
            v5 = L"ScenarioNoDependencies";
            break;
          case 0x10000:
            v5 = L"ScenarioEmitFixups";
            break;
          case 0x20000:
            v5 = L"ScenarioProfileInfo";
            break;
          default:
            v5 = L"**Unknown Scenario**";
            break;
        }
        if ( v40 >> ((v41 & 0x100000000LL) == 0) != 1 )
          SString::Append((SString *)&v40, L" | ");
        SString::Append((SString *)&v40, v5);
      }
      v4 *= 2;
    }
    while ( v4 );
  }
  else
  {
    SString::Set((SString *)&v40, L"ScenarioDefault");
  }
  SString::Append((SString *)&v36, (const struct SString *)&v40);
  if ( *(_QWORD *)(a1 + 568) )
  {
    v45 = 512;
    lpMem = &v47;
    v44 = 2;
    v47 = 0;
    v6 = *(_QWORD *)(a1 + 568);
    if ( v6 )
    {
      SString::ConvertToUnicode(*(SString **)(a1 + 568));
      v7 = *(const unsigned __int16 **)(v6 + 16);
    }
    else
    {
      v7 = 0;
    }
    v8 = IsExe(v7);
    v9 = *(_QWORD *)(a1 + 568);
    if ( v8 )
    {
      if ( v9 )
      {
        SString::ConvertToUnicode(*(SString **)(a1 + 568));
        v10 = *(_QWORD *)(v9 + 16);
      }
      else
      {
        v10 = 0;
      }
      SString::Printf((SString *)&v44, L", ConfigExe = %s", v10);
    }
    else
    {
      if ( v9 )
      {
        SString::ConvertToUnicode(*(SString **)(a1 + 568));
        v11 = *(_QWORD *)(v9 + 16);
      }
      else
      {
        v11 = 0;
      }
      SString::Printf((SString *)&v44, L", AppBase = %s", v11);
    }
    SString::Append((SString *)&v36, (const struct SString *)&v44);
    if ( (v45 & 0x800000000LL) != 0 )
    {
      v12 = lpMem;
      if ( lpMem )
      {
        ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          ProcessHeap = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
        }
        HeapFree(ProcessHeap, 0, v12);
      }
    }
  }
  if ( *(_BYTE *)(a1 + 640) )
    goto LABEL_50;
  v14 = *(_DWORD *)(a1 + 16);
  switch ( v14 )
  {
    case 2:
      goto LABEL_46;
    case 3:
      goto LABEL_50;
    case 0:
LABEL_46:
      if ( (*(_DWORD *)(a1 + 32) & 0xFFFFFFF8) == 0 )
        goto LABEL_54;
      goto LABEL_50;
  }
  if ( v14 != 5 )
    goto LABEL_54;
  if ( !*(_DWORD *)(a1 + 648) )
  {
LABEL_50:
    if ( a1 == -616 )
    {
      v15 = 0;
    }
    else
    {
      SString::ConvertToUnicode((SString *)(a1 + 616));
      v15 = *(_QWORD *)(a1 + 632);
    }
    SString::Printf((SString *)&v40, L", Runtime version = %s", v15);
    SString::Append((SString *)&v36, (const struct SString *)&v40);
LABEL_54:
    if ( !*(_DWORD *)(a1 + 648) )
      goto LABEL_56;
  }
  SString::Append((SString *)&v36, L" (Runtime missing)");
LABEL_56:
  SString::Printf((SString *)&v40, L" %s\n", (&ProcessedStatusString)[*(int *)(a1 + 16)]);
  SString::Append((SString *)&v36, (const struct SString *)&v40);
  v16 = 0;
  if ( (*(_DWORD *)(a1 + 32) & 0xFFFFFFF8) != 0 )
  {
    while ( 1 )
    {
      v17 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 8LL * v16);
      v18 = (&ProcessedStatusString)[*(int *)(v17 + 16)];
      v19 = *(_QWORD *)(v17 + 88);
      if ( v19 )
      {
        SString::ConvertToUnicode(*(SString **)(v17 + 88));
        v20 = *(_QWORD *)(v19 + 16);
      }
      else
      {
        v20 = 0;
      }
      SString::AppendPrintf((SString *)&v36, L"        %s %s\n", v20, v18);
      v21 = *(SString **)(v17 + 104);
      if ( v21 )
        goto LABEL_63;
      if ( *(_QWORD *)(v17 + 88) )
        break;
LABEL_64:
      v22 = *(_QWORD *)(v17 + 72);
      if ( v22 )
      {
        SString::ConvertToUnicode(*(SString **)(v17 + 72));
        SString::AppendPrintf((SString *)&v36, L"            Native image = %s\n", *(_QWORD *)(v22 + 16));
      }
      SString::Append((SString *)&v36, L"            Hard Dependencies:\n");
      v23 = 0;
      if ( (*(_DWORD *)(v17 + 48) & 0xFFFFFFF8) != 0 )
      {
        do
        {
          v24 = *(_QWORD *)(*(_QWORD *)(v17 + 64) + 8LL * v23);
          v25 = *(_QWORD *)(v24 + 88);
          if ( v25 )
          {
            SString::ConvertToUnicode(*(SString **)(v24 + 88));
            v26 = *(_QWORD *)(v25 + 16);
          }
          else
          {
            v26 = 0;
          }
          SString::AppendPrintf((SString *)&v36, L"                %s\n", v26);
          ++v23;
        }
        while ( v23 < *(_DWORD *)(v17 + 48) >> 3 );
      }
      SString::Append((SString *)&v36, L"            Soft Dependencies:\n");
      v27 = 0;
      if ( (*(_DWORD *)(v17 + 24) & 0xFFFFFFF8) != 0 )
      {
        do
        {
          v28 = *(_QWORD *)(*(_QWORD *)(v17 + 40) + 8LL * v27);
          v29 = *(_QWORD *)(v28 + 88);
          if ( v29 )
          {
            SString::ConvertToUnicode(*(SString **)(v28 + 88));
            v30 = *(_QWORD *)(v29 + 16);
          }
          else
          {
            v30 = 0;
          }
          SString::AppendPrintf((SString *)&v36, L"                %s\n", v30);
          ++v27;
        }
        while ( v27 < *(_DWORD *)(v17 + 24) >> 3 );
      }
      if ( ++v16 >= *(_DWORD *)(a1 + 32) >> 3 )
        goto LABEL_77;
    }
    v21 = *(SString **)(v17 + 88);
LABEL_63:
    SString::ConvertToUnicode(v21);
    SString::AppendPrintf((SString *)&v36, L"            DisplayName = %s\n", *((_QWORD *)v21 + 2));
    goto LABEL_64;
  }
LABEL_77:
  SString::ConvertToUnicode((SString *)&v36);
  result = Logger::Log(&v48, v38, 3);
  if ( (v41 & 0x800000000LL) != 0 )
  {
    v32 = v42;
    if ( v42 )
    {
      v33 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        v33 = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = v33;
      }
      result = HeapFree(v33, 0, v32);
    }
  }
  if ( (v37 & 0x800000000LL) != 0 )
  {
    v34 = v38;
    if ( v38 )
    {
      v35 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        v35 = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = v35;
      }
      return HeapFree(v35, 0, v34);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002c880  mov     [rsp-8+arg_10], rbx
0x18002c885  mov     [rsp-8+arg_8], rdx
0x18002c88a  push    rbp
0x18002c88b  push    rsi
0x18002c88c  push    rdi
0x18002c88d  push    r12
0x18002c88f  push    r13
0x18002c891  push    r14
0x18002c893  push    r15
0x18002c895  lea     rbp, [rsp-590h]
0x18002c89d  sub     rsp, 690h
0x18002c8a4  mov     rax, cs:__security_cookie
0x18002c8ab  xor     rax, rsp
0x18002c8ae  mov     [rbp+5C0h+var_40], rax
0x18002c8b5  mov     rdi, rcx
0x18002c8b8  xor     r12d, r12d
0x18002c8bb  mov     [rsp+6C0h+var_6A0], r12
0x18002c8c0  mov     [rsp+6C0h+var_6A0+4], 200h
0x18002c8c9  mov     [rsp+6C0h+var_690], r12
0x18002c8ce  lea     rax, [rsp+6C0h+var_688]
0x18002c8d3  mov     [rsp+6C0h+var_690], rax
0x18002c8d8  mov     dword ptr [rsp+6C0h+var_6A0], 2
0x18002c8e0  mov     rax, [rsp+6C0h+var_690]
0x18002c8e5  mov     [rax], r12w
0x18002c8e9  lea     rdx, asc_180055DA8; "    "
0x18002c8f0  lea     rcx, [rsp+6C0h+var_6A0]; this
0x18002c8f5  call    ?Printf@SString@@QEAAXPEBGZZ; SString::Printf(ushort const *,...)
0x18002c8fa  mov     [rbp+5C0h+var_480], r12
0x18002c901  mov     [rbp+5C0h+var_480+4], 200h
0x18002c90c  mov     [rbp+5C0h+var_470], r12
0x18002c913  lea     rax, [rbp+5C0h+var_468]
0x18002c91a  mov     [rbp+5C0h+var_470], rax
0x18002c921  mov     dword ptr [rbp+5C0h+var_480], 2
0x18002c92b  mov     rax, [rbp+5C0h+var_470]
0x18002c932  mov     [rax], r12w
0x18002c936  mov     r14d, [rdi+18h]
0x18002c93a  lea     rcx, [rbp+5C0h+var_480]; this
0x18002c941  test    r14d, r14d
0x18002c944  jnz     short loc_18002C957
0x18002c946  lea     rdx, aScenariodefaul; "ScenarioDefault"
0x18002c94d  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x18002c952  jmp     loc_18002CA2A
0x18002c957  call    ?Clear@SString@@QEAAXXZ; SString::Clear(void)
0x18002c95c  mov     esi, 1
0x18002c961  test    esi, r14d
0x18002c964  jz      loc_18002CA22
0x18002c96a  mov     ecx, esi
0x18002c96c  test    esi, esi
0x18002c96e  jz      short loc_18002C9E1
0x18002c970  sub     ecx, 1
0x18002c973  jz      short loc_18002C9D8
0x18002c975  sub     ecx, 1
0x18002c978  jz      short loc_18002C9CF
0x18002c97a  sub     ecx, 6
0x18002c97d  jz      short loc_18002C9C6
0x18002c97f  sub     ecx, 8
0x18002c982  jz      short loc_18002C9BD
0x18002c984  sub     ecx, 10h
0x18002c987  jz      short loc_18002C9B4
0x18002c989  sub     ecx, 0FFE0h
0x18002c98f  jz      short loc_18002C9AB
0x18002c991  cmp     ecx, 10000h
0x18002c997  jz      short loc_18002C9A2
0x18002c999  lea     rbx, aUnknownScenari; "**Unknown Scenario**"
0x18002c9a0  jmp     short loc_18002C9E8
0x18002c9a2  lea     rbx, aScenarioprofil_0; "ScenarioProfileInfo"
0x18002c9a9  jmp     short loc_18002C9E8
0x18002c9ab  lea     rbx, aScenarioemitfi; "ScenarioEmitFixups"
0x18002c9b2  jmp     short loc_18002C9E8
0x18002c9b4  lea     rbx, aScenarionodepe; "ScenarioNoDependencies"
0x18002c9bb  jmp     short loc_18002C9E8
0x18002c9bd  lea     rbx, aScenariotuning; "ScenarioTuningDataCollection"
0x18002c9c4  jmp     short loc_18002C9E8
0x18002c9c6  lea     rbx, aScenarioprofil; "ScenarioProfile"
0x18002c9cd  jmp     short loc_18002C9E8
0x18002c9cf  lea     rbx, aScenariodebug; "ScenarioDebug"
0x18002c9d6  jmp     short loc_18002C9E8
0x18002c9d8  lea     rbx, aScenarioall; "ScenarioAll"
0x18002c9df  jmp     short loc_18002C9E8
0x18002c9e1  lea     rbx, aScenariodefaul; "ScenarioDefault"
0x18002c9e8  mov     ecx, [rbp+5C0h+var_478]
0x18002c9ee  not     ecx
0x18002c9f0  and     ecx, 1
0x18002c9f3  mov     eax, dword ptr [rbp+5C0h+var_480]
0x18002c9f9  shr     eax, cl
0x18002c9fb  cmp     eax, 1
0x18002c9fe  jz      short loc_18002CA13
0x18002ca00  lea     rdx, asc_180055F20; " | "
0x18002ca07  lea     rcx, [rbp+5C0h+var_480]; this
0x18002ca0e  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x18002ca13  mov     rdx, rbx; unsigned __int16 *
0x18002ca16  lea     rcx, [rbp+5C0h+var_480]; this
0x18002ca1d  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x18002ca22  add     esi, esi
0x18002ca24  jnz     loc_18002C961
0x18002ca2a  lea     rdx, [rbp+5C0h+var_480]; struct SString *
0x18002ca31  lea     rcx, [rsp+6C0h+var_6A0]; this
0x18002ca36  call    ?Append@SString@@QEAAXAEBV1@@Z; SString::Append(SString const &)
0x18002ca3b  cmp     [rdi+238h], r12
0x18002ca42  jz      loc_18002CB47
0x18002ca48  mov     [rbp+5C0h+var_260], r12
0x18002ca4f  mov     [rbp+5C0h+var_260+4], 200h
0x18002ca5a  mov     [rbp+5C0h+lpMem], r12
0x18002ca61  lea     rax, [rbp+5C0h+var_248]
0x18002ca68  mov     [rbp+5C0h+lpMem], rax
0x18002ca6f  mov     dword ptr [rbp+5C0h+var_260], 2
0x18002ca79  mov     rax, [rbp+5C0h+lpMem]
0x18002ca80  mov     [rax], r12w
0x18002ca84  mov     rbx, [rdi+238h]
0x18002ca8b  test    rbx, rbx
0x18002ca8e  jnz     short loc_18002CA95
0x18002ca90  mov     rcx, r12
0x18002ca93  jmp     short loc_18002CAA1
0x18002ca95  mov     rcx, rbx; this
0x18002ca98  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18002ca9d  mov     rcx, [rbx+10h]; unsigned __int16 *
0x18002caa1  call    ?IsExe@@YAHPEBG@Z; IsExe(ushort const *)
0x18002caa6  mov     rbx, [rdi+238h]
0x18002caad  test    eax, eax
0x18002caaf  jz      short loc_18002CAD0
0x18002cab1  test    rbx, rbx
0x18002cab4  jnz     short loc_18002CABB
0x18002cab6  mov     r8, r12
0x18002cab9  jmp     short loc_18002CAC7
0x18002cabb  mov     rcx, rbx; this
0x18002cabe  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18002cac3  mov     r8, [rbx+10h]
0x18002cac7  lea     rdx, aConfigexeS; ", ConfigExe = %s"
0x18002cace  jmp     short loc_18002CAED
0x18002cad0  test    rbx, rbx
0x18002cad3  jnz     short loc_18002CADA
0x18002cad5  mov     r8, r12
0x18002cad8  jmp     short loc_18002CAE6
0x18002cada  mov     rcx, rbx; this
0x18002cadd  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18002cae2  mov     r8, [rbx+10h]
0x18002cae6  lea     rdx, aAppbaseS; ", AppBase = %s"
0x18002caed  lea     rcx, [rbp+5C0h+var_260]; this
0x18002caf4  call    ?Printf@SString@@QEAAXPEBGZZ; SString::Printf(ushort const *,...)
0x18002caf9  lea     rdx, [rbp+5C0h+var_260]; struct SString *
0x18002cb00  lea     rcx, [rsp+6C0h+var_6A0]; this
0x18002cb05  call    ?Append@SString@@QEAAXAEBV1@@Z; SString::Append(SString const &)
0x18002cb0a  nop
0x18002cb0b  test    [rbp+5C0h+var_258], 8
0x18002cb12  jz      short loc_18002CB47
0x18002cb14  mov     rbx, [rbp+5C0h+lpMem]
0x18002cb1b  test    rbx, rbx
0x18002cb1e  jz      short loc_18002CB47
0x18002cb20  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18002cb27  test    rax, rax
0x18002cb2a  jnz     short loc_18002CB39
0x18002cb2c  call    cs:__imp_GetProcessHeap
0x18002cb32  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18002cb39  mov     r8, rbx; lpMem
0x18002cb3c  xor     edx, edx; dwFlags
0x18002cb3e  mov     rcx, rax; hHeap
0x18002cb41  call    cs:__imp_HeapFree
0x18002cb47  mov     r13d, 0FFFFFFF8h
0x18002cb4d  cmp     [rdi+280h], r12b
0x18002cb54  jnz     short loc_18002CB7D
0x18002cb56  mov     eax, [rdi+10h]
0x18002cb59  cmp     eax, 2
0x18002cb5c  jz      short loc_18002CB67
0x18002cb5e  cmp     eax, 3
0x18002cb61  jz      short loc_18002CB7D
0x18002cb63  test    eax, eax
0x18002cb65  jnz     short loc_18002CB6F
0x18002cb67  test    [rdi+20h], r13d
0x18002cb6b  ja      short loc_18002CB7D
0x18002cb6d  jmp     short loc_18002CBBE
0x18002cb6f  cmp     eax, 5
0x18002cb72  jnz     short loc_18002CBBE
0x18002cb74  cmp     [rdi+288h], r12d
0x18002cb7b  jnz     short loc_18002CBC7
0x18002cb7d  lea     rbx, [rdi+268h]
0x18002cb84  test    rbx, rbx
0x18002cb87  jnz     short loc_18002CB8E
0x18002cb89  mov     r8, r12
0x18002cb8c  jmp     short loc_18002CB9A
0x18002cb8e  mov     rcx, rbx; this
0x18002cb91  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18002cb96  mov     r8, [rbx+10h]
0x18002cb9a  lea     rdx, aRuntimeVersion; ", Runtime version = %s"
0x18002cba1  lea     rcx, [rbp+5C0h+var_480]; this
0x18002cba8  call    ?Printf@SString@@QEAAXPEBGZZ; SString::Printf(ushort const *,...)
0x18002cbad  lea     rdx, [rbp+5C0h+var_480]; struct SString *
0x18002cbb4  lea     rcx, [rsp+6C0h+var_6A0]; this
0x18002cbb9  call    ?Append@SString@@QEAAXAEBV1@@Z; SString::Append(SString const &)
0x18002cbbe  cmp     [rdi+288h], r12d
0x18002cbc5  jz      short loc_18002CBD8
0x18002cbc7  lea     rdx, aRuntimeMissing; " (Runtime missing)"
0x18002cbce  lea     rcx, [rsp+6C0h+var_6A0]; this
0x18002cbd3  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x18002cbd8  movsxd  r8, dword ptr [rdi+10h]
0x18002cbdc  lea     rsi, ?ProcessedStatusString@@3QBQEBGB; ushort const * const near * const ProcessedStatusString
0x18002cbe3  mov     r8, [rsi+r8*8]
0x18002cbe7  lea     rdx, aS_5; " %s\n"
0x18002cbee  lea     rcx, [rbp+5C0h+var_480]; this
0x18002cbf5  call    ?Printf@SString@@QEAAXPEBGZZ; SString::Printf(ushort const *,...)
0x18002cbfa  lea     rdx, [rbp+5C0h+var_480]; struct SString *
0x18002cc01  lea     rcx, [rsp+6C0h+var_6A0]; this
0x18002cc06  call    ?Append@SString@@QEAAXAEBV1@@Z; SString::Append(SString const &)
0x18002cc0b  mov     r15d, r12d
0x18002cc0e  test    [rdi+20h], r13d
0x18002cc12  jbe     loc_18002CD84
0x18002cc18  mov     ecx, r15d
0x18002cc1b  mov     rax, [rdi+30h]
0x18002cc1f  mov     rbx, [rax+rcx*8]
0x18002cc23  movsxd  rax, dword ptr [rbx+10h]
0x18002cc27  mov     r14, [rsi+rax*8]
0x18002cc2b  mov     rsi, [rbx+58h]
0x18002cc2f  test    rsi, rsi
0x18002cc32  jnz     short loc_18002CC39
0x18002cc34  mov     r8, r12
0x18002cc37  jmp     short loc_18002CC45
0x18002cc39  mov     rcx, rsi; this
0x18002cc3c  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18002cc41  mov     r8, [rsi+10h]
0x18002cc45  mov     r9, r14
0x18002cc48  lea     rdx, aSS_0; "        %s %s\n"
0x18002cc4f  lea     rcx, [rsp+6C0h+var_6A0]; this
0x18002cc54  call    ?AppendPrintf@SString@@QEAAXPEBGZZ; SString::AppendPrintf(ushort const *,...)
0x18002cc59  mov     rsi, [rbx+68h]
0x18002cc5d  test    rsi, rsi
0x18002cc60  jnz     short loc_18002CC6C
0x18002cc62  cmp     [rbx+58h], r12
0x18002cc66  jz      short loc_18002CC89
0x18002cc68  mov     rsi, [rbx+58h]
0x18002cc6c  mov     rcx, rsi; this
0x18002cc6f  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18002cc74  mov     r8, [rsi+10h]
0x18002cc78  lea     rdx, aDisplaynameS; "            DisplayName = %s\n"
0x18002cc7f  lea     rcx, [rsp+6C0h+var_6A0]; this
0x18002cc84  call    ?AppendPrintf@SString@@QEAAXPEBGZZ; SString::AppendPrintf(ushort const *,...)
0x18002cc89  mov     rsi, [rbx+48h]
0x18002cc8d  test    rsi, rsi
0x18002cc90  jz      short loc_18002CCAF
0x18002cc92  mov     rcx, rsi; this
0x18002cc95  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18002cc9a  mov     r8, [rsi+10h]
0x18002cc9e  lea     rdx, aNativeImageS; "            Native image = %s\n"
0x18002cca5  lea     rcx, [rsp+6C0h+var_6A0]; this
0x18002ccaa  call    ?AppendPrintf@SString@@QEAAXPEBGZZ; SString::AppendPrintf(ushort const *,...)
0x18002ccaf  lea     rdx, aHardDependenci; "            Hard Dependencies:\n"
0x18002ccb6  lea     rcx, [rsp+6C0h+var_6A0]; this
0x18002ccbb  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x18002ccc0  mov     r14d, r12d
0x18002ccc3  test    [rbx+30h], r13d
0x18002ccc7  jbe     short loc_18002CD0D
0x18002ccc9  mov     ecx, r14d
0x18002cccc  mov     rax, [rbx+40h]
0x18002ccd0  mov     rax, [rax+rcx*8]
0x18002ccd4  mov     rsi, [rax+58h]
0x18002ccd8  test    rsi, rsi
0x18002ccdb  jnz     short loc_18002CCE2
0x18002ccdd  mov     r8, r12
0x18002cce0  jmp     short loc_18002CCEE
0x18002cce2  mov     rcx, rsi; this
0x18002cce5  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18002ccea  mov     r8, [rsi+10h]
0x18002ccee  lea     rdx, aS_2; "                %s\n"
0x18002ccf5  lea     rcx, [rsp+6C0h+var_6A0]; this
0x18002ccfa  call    ?AppendPrintf@SString@@QEAAXPEBGZZ; SString::AppendPrintf(ushort const *,...)
0x18002ccff  inc     r14d
0x18002cd02  mov     eax, [rbx+30h]
0x18002cd05  shr     eax, 3
0x18002cd08  cmp     r14d, eax
0x18002cd0b  jb      short loc_18002CCC9
0x18002cd0d  lea     rdx, aSoftDependenci; "            Soft Dependencies:\n"
0x18002cd14  lea     rcx, [rsp+6C0h+var_6A0]; this
0x18002cd19  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x18002cd1e  mov     r14d, r12d
0x18002cd21  test    [rbx+18h], r13d
0x18002cd25  jbe     short loc_18002CD6B
0x18002cd27  mov     ecx, r14d
0x18002cd2a  mov     rax, [rbx+28h]
0x18002cd2e  mov     rax, [rax+rcx*8]
0x18002cd32  mov     rsi, [rax+58h]
0x18002cd36  test    rsi, rsi
0x18002cd39  jnz     short loc_18002CD40
0x18002cd3b  mov     r8, r12
0x18002cd3e  jmp     short loc_18002CD4C
0x18002cd40  mov     rcx, rsi; this
0x18002cd43  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18002cd48  mov     r8, [rsi+10h]
0x18002cd4c  lea     rdx, aS_2; "                %s\n"
0x18002cd53  lea     rcx, [rsp+6C0h+var_6A0]; this
0x18002cd58  call    ?AppendPrintf@SString@@QEAAXPEBGZZ; SString::AppendPrintf(ushort const *,...)
0x18002cd5d  inc     r14d
0x18002cd60  mov     eax, [rbx+18h]
0x18002cd63  shr     eax, 3
0x18002cd66  cmp     r14d, eax
0x18002cd69  jb      short loc_18002CD27
0x18002cd6b  inc     r15d
0x18002cd6e  mov     eax, [rdi+20h]
0x18002cd71  shr     eax, 3
0x18002cd74  cmp     r15d, eax
0x18002cd77  lea     rsi, ?ProcessedStatusString@@3QBQEBGB; ushort const * const near * const ProcessedStatusString
0x18002cd7e  jb      loc_18002CC18
0x18002cd84  lea     rcx, [rsp+6C0h+var_6A0]; this
  ... truncated ...
```
