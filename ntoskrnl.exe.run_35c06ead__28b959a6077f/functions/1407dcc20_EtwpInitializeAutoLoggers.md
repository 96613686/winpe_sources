# EtwpInitializeAutoLoggers

- ea: `0x1407dcc20`
- end: `0x1407dcef9`
- name: `EtwpInitializeAutoLoggers`
- size: `729`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1407d6854`

## callees

- `0x1403d4450`
- `0x1404509c0`
- `0x1406d9d70`
- `0x1406f4880`
- `0x1407dc918`
- `0x1407dcbec`
- `0x1407dcc20`
- `0x140973560`
- `0x140ad9fbc`
- `0x140bae410`
- `0x140bae8e0`
- `0x140c83658`

## string_xrefs

- `0x1407dccc2`: `\Registry\Machine\System\CurrentControlSet\Control\WMI\GlobalLogger`
- `0x1407dce4b`: `ETWGlobalLoggerPath`
- `0x1407dcdfb`: `ETWAutoLoggerPath`
- `0x1407dcc49`: `\Registry\Machine\System\CurrentControlSet\Control\WMI\AutoLogger`

## pseudocode

```c
__int64 __fastcall EtwpInitializeAutoLoggers(__int64 a1)
{
  _QWORD *v2; // rbx
  _QWORD *i; // rdi
  _WORD *v4; // rdx
  __int64 v5; // r8
  void *Pool2; // rbx
  void *v7; // rdi
  BOOLEAN NewElement[4]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v10; // [rsp+44h] [rbp-BCh] BYREF
  RTL_AVL_TABLE Table; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SourceString[16]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR Path[72]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v14; // [rsp+170h] [rbp+70h]
  __int128 v15; // [rsp+180h] [rbp+80h]
  __int128 v16; // [rsp+190h] [rbp+90h]
  __int128 v17; // [rsp+1A0h] [rbp+A0h]
  __int128 v18; // [rsp+1B0h] [rbp+B0h]
  __int128 v19; // [rsp+1C0h] [rbp+C0h]
  __int128 v20; // [rsp+1D0h] [rbp+D0h]
  __int128 v21; // [rsp+1E0h] [rbp+E0h]
  __int64 v22; // [rsp+1F0h] [rbp+F0h]

  wcscpy(Path, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\WMI\\AutoLogger");
  v22 = *(_QWORD *)L"ger";
  v14 = *(_OWORD *)L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\WMI\\GlobalLogger";
  v15 = *(_OWORD *)L"y\\Machine\\System\\CurrentControlSet\\Control\\WMI\\GlobalLogger";
  v16 = *(_OWORD *)L"e\\System\\CurrentControlSet\\Control\\WMI\\GlobalLogger";
  v17 = *(_OWORD *)L"\\CurrentControlSet\\Control\\WMI\\GlobalLogger";
  v18 = *(_OWORD *)L"ControlSet\\Control\\WMI\\GlobalLogger";
  v19 = *(_OWORD *)L"et\\Control\\WMI\\GlobalLogger";
  v20 = *(_OWORD *)L"ol\\WMI\\GlobalLogger";
  v21 = *(_OWORD *)L"lobalLogger";
  wcscpy(SourceString, L"GllLogger");
  memset_0(&Table, 0, sizeof(Table));
  RtlInitializeGenericTableAvl(&Table, EtwpAvlCompareKeyNames, EtwpAllocateKeyNameEntry, EtwpFreeKeyNameEntry, 0);
  if ( a1 )
  {
    v2 = (_QWORD *)(a1 + 8);
    if ( (_QWORD *)*v2 != v2 )
    {
      EtwpEnableBootLoggerRegistryProviders(Path, a1);
      for ( i = (_QWORD *)*v2; i != v2; i = (_QWORD *)*i )
      {
        v4 = (_WORD *)i[2];
        v5 = -1;
        do
          ++v5;
        while ( v4[v5] );
        RtlInsertElementGenericTableAvl(&Table, v4, 2 * v5 + 2, NewElement);
      }
    }
  }
  Pool2 = (void *)ExAllocatePool2(256, 520, 1953985605);
  if ( Pool2 )
  {
    if ( (unsigned int)RtlGetPersistedStateLocation(L"ETWAutoLoggerPath", Pool2, 520, (__int64)&v10) )
    {
      ExFreePoolWithTag(Pool2, 0x74777445u);
      Pool2 = 0;
    }
    v7 = (void *)ExAllocatePool2(256, 520, 1953985605);
    if ( v7 )
    {
      if ( (unsigned int)RtlGetPersistedStateLocation(L"ETWGlobalLoggerPath", v7, 520, (__int64)&v10) )
      {
        ExFreePoolWithTag(v7, 0x74777445u);
        v7 = 0;
      }
      EtwStartAutoLogger(SourceString);
      EtwpEnumerateAutologgerPath(Path);
      if ( !Pool2 )
        goto LABEL_18;
      EtwpEnumerateAutologgerPath((PCWSTR)Pool2);
    }
    else if ( !Pool2 )
    {
      return EtwpFreeKeyNameList(&Table);
    }
    ExFreePoolWithTag(Pool2, 0x74777445u);
LABEL_18:
    if ( v7 )
      ExFreePoolWithTag(v7, 0x74777445u);
  }
  return EtwpFreeKeyNameList(&Table);
}

```

## disassembly

```asm
0x1407dcc20  push    rbp
0x1407dcc22  push    rbx
0x1407dcc23  push    rsi
0x1407dcc24  push    rdi
0x1407dcc25  push    r14
0x1407dcc27  push    r15
0x1407dcc29  lea     rbp, [rsp-118h]
0x1407dcc31  sub     rsp, 218h
0x1407dcc38  mov     rax, cs:__security_cookie
0x1407dcc3f  xor     rax, rsp
0x1407dcc42  mov     [rbp+140h+var_40], rax
0x1407dcc49  movaps  xmm0, xmmword ptr cs:aRegistryMachin_92; "\\Registry\\Machine\\System\\CurrentCon"...
0x1407dcc50  xor     edx, edx; Val
0x1407dcc52  movaps  xmm1, xmmword ptr cs:aRegistryMachin_92+10h; "y\\Machine\\System\\CurrentControlSet\\"...
0x1407dcc59  mov     rdi, rcx
0x1407dcc5c  mov     eax, dword ptr cs:aRegistryMachin_92+80h; "r"
0x1407dcc62  lea     rcx, [rsp+240h+Table]; void *
0x1407dcc67  movups  xmmword ptr [rbp+140h+Path], xmm0
0x1407dcc6b  lea     r8d, [rdx+68h]; Size
0x1407dcc6f  mov     [rbp+140h+var_E0], eax
0x1407dcc72  movaps  xmm0, xmmword ptr cs:aRegistryMachin_92+20h; "e\\System\\CurrentControlSet\\Control\\"...
0x1407dcc79  mov     rax, qword ptr cs:aRegistryMachin_63+80h; "ger"
0x1407dcc80  movups  [rbp+140h+var_150], xmm1
0x1407dcc84  mov     [rbp+140h+var_50], rax
0x1407dcc8b  movaps  xmm1, xmmword ptr cs:aRegistryMachin_92+30h; "\\CurrentControlSet\\Control\\WMI\\Auto"...
0x1407dcc92  movups  [rbp+140h+var_140], xmm0
0x1407dcc96  movaps  xmm0, xmmword ptr cs:aRegistryMachin_92+40h; "ControlSet\\Control\\WMI\\AutoLogger"
0x1407dcc9d  movups  [rbp+140h+var_130], xmm1
0x1407dcca1  movaps  xmm1, xmmword ptr cs:aRegistryMachin_92+50h; "et\\Control\\WMI\\AutoLogger"
0x1407dcca8  movups  [rbp+140h+var_120], xmm0
0x1407dccac  movaps  xmm0, xmmword ptr cs:aRegistryMachin_92+60h; "ol\\WMI\\AutoLogger"
0x1407dccb3  movups  [rbp+140h+var_110], xmm1
0x1407dccb7  movaps  xmm1, xmmword ptr cs:aRegistryMachin_92+70h; "utoLogger"
0x1407dccbe  movups  [rbp+140h+var_100], xmm0
0x1407dccc2  movaps  xmm0, xmmword ptr cs:aRegistryMachin_63; "\\Registry\\Machine\\System\\CurrentCon"...
0x1407dccc9  movups  [rbp+140h+var_F0], xmm1
0x1407dcccd  movaps  xmm1, xmmword ptr cs:aRegistryMachin_63+10h; "y\\Machine\\System\\CurrentControlSet\\"...
0x1407dccd4  movups  [rbp+140h+var_D0], xmm0
0x1407dccd8  movaps  xmm0, xmmword ptr cs:aRegistryMachin_63+20h; "e\\System\\CurrentControlSet\\Control\\"...
0x1407dccdf  movups  [rbp+140h+var_C0], xmm1
0x1407dcce6  movaps  xmm1, xmmword ptr cs:aRegistryMachin_63+30h; "\\CurrentControlSet\\Control\\WMI\\Glob"...
0x1407dcced  movups  [rbp+140h+var_B0], xmm0
0x1407dccf4  movaps  xmm0, xmmword ptr cs:aRegistryMachin_63+40h; "ControlSet\\Control\\WMI\\GlobalLogger"
0x1407dccfb  movups  [rbp+140h+var_A0], xmm1
0x1407dcd02  movaps  xmm1, xmmword ptr cs:aRegistryMachin_63+50h; "et\\Control\\WMI\\GlobalLogger"
0x1407dcd09  movups  [rbp+140h+var_90], xmm0
0x1407dcd10  movaps  xmm0, xmmword ptr cs:aRegistryMachin_63+60h; "ol\\WMI\\GlobalLogger"
0x1407dcd17  movups  [rbp+140h+var_80], xmm1
0x1407dcd1e  movaps  xmm1, xmmword ptr cs:aRegistryMachin_63+70h; "lobalLogger"
0x1407dcd25  movups  [rbp+140h+var_70], xmm0
0x1407dcd2c  movups  xmm0, xmmword ptr cs:aGloballogger; "GlobalLogger"
0x1407dcd33  movups  [rbp+140h+var_60], xmm1
0x1407dcd3a  movups  xmm1, xmmword ptr cs:aGloballogger+0Ah; "lLogger"
0x1407dcd41  movups  xmmword ptr [rbp+140h+SourceString], xmm0
0x1407dcd45  movups  xmmword ptr [rbp+140h+SourceString+0Ah], xmm1
0x1407dcd49  call    memset_0
0x1407dcd4e  xor     esi, esi
0x1407dcd50  lea     r9, EtwpFreeKeyNameEntry; FreeRoutine
0x1407dcd57  lea     r8, EtwpAllocateKeyNameEntry; AllocateRoutine
0x1407dcd5e  mov     [rsp+240h+TableContext], rsi; TableContext
0x1407dcd63  lea     rdx, EtwpAvlCompareKeyNames; CompareRoutine
0x1407dcd6a  lea     rcx, [rsp+240h+Table]; Table
0x1407dcd6f  call    RtlInitializeGenericTableAvl
0x1407dcd74  test    rdi, rdi
0x1407dcd77  jz      short loc_1407DCDC4
0x1407dcd79  lea     rbx, [rdi+8]
0x1407dcd7d  cmp     [rbx], rbx
0x1407dcd80  jz      short loc_1407DCDC4
0x1407dcd82  mov     rdx, rdi
0x1407dcd85  lea     rcx, [rbp+140h+Path]
0x1407dcd89  call    EtwpEnableBootLoggerRegistryProviders
0x1407dcd8e  mov     rdi, [rbx]
0x1407dcd91  jmp     short loc_1407DCDBF
0x1407dcd93  mov     rdx, [rdi+10h]; Buffer
0x1407dcd97  or      r8, 0FFFFFFFFFFFFFFFFh
0x1407dcd9b  inc     r8
0x1407dcd9e  cmp     [rdx+r8*2], si
0x1407dcda3  jnz     short loc_1407DCD9B
0x1407dcda5  lea     r8d, ds:2[r8*2]; BufferSize
0x1407dcdad  lea     r9, [rsp+240h+NewElement]; NewElement
0x1407dcdb2  lea     rcx, [rsp+240h+Table]; Table
0x1407dcdb7  call    RtlInsertElementGenericTableAvl
0x1407dcdbc  mov     rdi, [rdi]
0x1407dcdbf  cmp     rdi, rbx
0x1407dcdc2  jnz     short loc_1407DCD93
0x1407dcdc4  mov     r14d, 74777445h
0x1407dcdca  mov     r15d, 208h
0x1407dcdd0  mov     edi, 100h
0x1407dcdd5  mov     r8d, r14d
0x1407dcdd8  mov     edx, r15d
0x1407dcddb  mov     ecx, edi
0x1407dcddd  call    ExAllocatePool2
0x1407dcde2  mov     rbx, rax
0x1407dcde5  test    rax, rax
0x1407dcde8  jz      loc_1407DCECF
0x1407dcdee  lea     rax, [rsp+240h+var_1FC]
0x1407dcdf3  xor     r9d, r9d
0x1407dcdf6  mov     [rsp+240h+var_210], rax; __int64
0x1407dcdfb  lea     rcx, aEtwautologgerp; "ETWAutoLoggerPath"
0x1407dce02  mov     [rsp+240h+var_218], r15d; int
0x1407dce07  xor     r8d, r8d
0x1407dce0a  xor     edx, edx
0x1407dce0c  mov     [rsp+240h+TableContext], rbx; void *
0x1407dce11  call    RtlGetPersistedStateLocation
0x1407dce16  test    eax, eax
0x1407dce18  jz      short loc_1407DCE28
0x1407dce1a  mov     edx, r14d; Tag
0x1407dce1d  mov     rcx, rbx; P
0x1407dce20  call    ExFreePoolWithTag
0x1407dce25  mov     rbx, rsi
0x1407dce28  mov     r8d, r14d
0x1407dce2b  mov     rdx, r15
0x1407dce2e  mov     rcx, rdi
0x1407dce31  call    ExAllocatePool2
0x1407dce36  mov     rdi, rax
0x1407dce39  test    rax, rax
0x1407dce3c  jz      short loc_1407DCEAF
0x1407dce3e  lea     rax, [rsp+240h+var_1FC]
0x1407dce43  xor     r9d, r9d
0x1407dce46  mov     [rsp+240h+var_210], rax; __int64
0x1407dce4b  lea     rcx, aEtwgloballogge; "ETWGlobalLoggerPath"
0x1407dce52  mov     [rsp+240h+var_218], r15d; int
0x1407dce57  xor     r8d, r8d
0x1407dce5a  xor     edx, edx
0x1407dce5c  mov     [rsp+240h+TableContext], rdi; void *
0x1407dce61  call    RtlGetPersistedStateLocation
0x1407dce66  test    eax, eax
0x1407dce68  jz      short loc_1407DCE78
0x1407dce6a  mov     edx, r14d; Tag
0x1407dce6d  mov     rcx, rdi; P
0x1407dce70  call    ExFreePoolWithTag
0x1407dce75  mov     rdi, rsi
0x1407dce78  mov     r8, rdi
0x1407dce7b  lea     rdx, [rbp+140h+var_D0]
0x1407dce7f  lea     rcx, [rbp+140h+SourceString]; SourceString
0x1407dce83  call    EtwStartAutoLogger
0x1407dce88  lea     r8, [rsp+240h+Table]
0x1407dce8d  mov     rdx, rbx
0x1407dce90  lea     rcx, [rbp+140h+Path]; Path
0x1407dce94  call    EtwpEnumerateAutologgerPath
0x1407dce99  test    rbx, rbx
0x1407dce9c  jz      short loc_1407DCEBF
0x1407dce9e  lea     r8, [rsp+240h+Table]
0x1407dcea3  xor     edx, edx
0x1407dcea5  mov     rcx, rbx; Path
0x1407dcea8  call    EtwpEnumerateAutologgerPath
0x1407dcead  jmp     short loc_1407DCEB4
0x1407dceaf  test    rbx, rbx
0x1407dceb2  jz      short loc_1407DCECF
0x1407dceb4  mov     edx, r14d; Tag
0x1407dceb7  mov     rcx, rbx; P
0x1407dceba  call    ExFreePoolWithTag
0x1407dcebf  test    rdi, rdi
0x1407dcec2  jz      short loc_1407DCECF
0x1407dcec4  mov     edx, r14d; Tag
0x1407dcec7  mov     rcx, rdi; P
0x1407dceca  call    ExFreePoolWithTag
0x1407dcecf  lea     rcx, [rsp+240h+Table]; Table
0x1407dced4  call    EtwpFreeKeyNameList
0x1407dced9  mov     rcx, [rbp+140h+var_40]
0x1407dcee0  xor     rcx, rsp; StackCookie
0x1407dcee3  call    __security_check_cookie
0x1407dcee8  add     rsp, 218h
0x1407dceef  pop     r15
0x1407dcef1  pop     r14
0x1407dcef3  pop     rdi
0x1407dcef4  pop     rsi
0x1407dcef5  pop     rbx
0x1407dcef6  pop     rbp
0x1407dcef7  retn
```
