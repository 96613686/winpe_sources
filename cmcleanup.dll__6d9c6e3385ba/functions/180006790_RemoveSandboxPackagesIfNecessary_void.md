# RemoveSandboxPackagesIfNecessary(void)

- ea: `0x180006790`
- end: `0x18000688c`
- name: `?RemoveSandboxPackagesIfNecessary@@YAJXZ`
- size: `252`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180007820`

## callees

- `0x180005844`
- `0x180006790`
- `0x1800068d4`
- `0x180007e18`
- `0x180007e68`

## import_xrefs

- `DismApi!DismDelete` at `0x180006818`
- `DismApi!DismDelete` at `0x180006853`
- `DismApi!DismDelete` at `0x180006818`
- `DismApi!DismDelete` at `0x180006853`
- `DismApi!DismGetFeatureInfo` at `0x1800067e9`
- `DismApi!DismGetFeatureInfo` at `0x1800067e9`

## string_xrefs

- `0x18000682b`: `onecore\base\gendrv\silos\clem\cleanup\dll\cmcleanup.cpp`

## pseudocode

```c
__int64 __fastcall RemoveSandboxPackagesIfNecessary(__int64 a1, const unsigned __int16 *a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  unsigned __int64 v4; // r9
  __int64 v5; // rdx
  char v6; // di
  int FeatureInfo; // eax
  int v8; // edx
  int v9; // eax
  __int64 *v11; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned int v13; // [rsp+40h] [rbp+8h] BYREF
  char v14; // [rsp+44h] [rbp+Ch]
  __int64 v15; // [rsp+48h] [rbp+10h] BYREF

  v13 = 0;
  v14 = 0;
  v2 = Csl::DismHelper::Initialize((Csl::DismHelper *)&v13, a2);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v6 = 1;
    v15 = 0;
    v11 = &v15;
    FeatureInfo = DismGetFeatureInfo(v13, L"Containers-DisposableClientVM", 0, 1);
    v3 = FeatureInfo;
    if ( FeatureInfo >= 0 )
    {
      v8 = *(_DWORD *)(v15 + 8);
      if ( ((v8 - 4) & 0xFFFFFFFC) != 0 || v8 == 6 )
        v6 = 0;
      DismDelete();
      if ( v6 || (v9 = RemoveSandboxPackages(), v3 = v9, v9 >= 0) )
      {
        v3 = 0;
        goto LABEL_15;
      }
      v4 = (unsigned int)v9;
      v5 = 162;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAB,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\csldism.cpp",
        (const char *)(unsigned int)FeatureInfo,
        (int)&v15);
      if ( v15 )
        DismDelete();
      v4 = v3;
      v5 = 157;
    }
  }
  else
  {
    v4 = (unsigned int)v2;
    v5 = 153;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\cleanup\\dll\\cmcleanup.cpp",
    (const char *)v4,
    (int)v11);
LABEL_15:
  Csl::DismHelper::~DismHelper((Csl::DismHelper *)&v13);
  return v3;
}

```

## disassembly

```asm
0x180006790  mov     rax, rsp
0x180006793  mov     [rax+18h], rbx
0x180006797  push    rdi
0x180006798  sub     rsp, 30h
0x18000679c  lea     rcx, [rax+8]; this
0x1800067a0  mov     dword ptr [rax+8], 0
0x1800067a7  mov     byte ptr [rax+0Ch], 0
0x1800067ab  call    ?Initialize@DismHelper@Csl@@QEAAJPEBG@Z; Csl::DismHelper::Initialize(ushort const *)
0x1800067b0  mov     ebx, eax
0x1800067b2  test    eax, eax
0x1800067b4  jns     short loc_1800067C0
0x1800067b6  mov     r9d, eax
0x1800067b9  mov     edx, 99h
0x1800067be  jmp     short loc_180006826
0x1800067c0  mov     ecx, [rsp+38h+arg_0]
0x1800067c4  lea     rax, [rsp+38h+arg_8]
0x1800067c9  mov     edi, 1
0x1800067ce  mov     [rsp+38h+arg_8], 0
0x1800067d7  mov     r9d, edi
0x1800067da  mov     qword ptr [rsp+38h+var_18], rax; int
0x1800067df  xor     r8d, r8d
0x1800067e2  lea     rdx, aContainersDisp; "Containers-DisposableClientVM"
0x1800067e9  call    cs:__imp_DismGetFeatureInfo
0x1800067ef  mov     ebx, eax
0x1800067f1  test    eax, eax
0x1800067f3  jns     short loc_180006839
0x1800067f5  mov     rcx, [rsp+38h]; this
0x1800067fa  lea     r8, aOnecoreBaseGen; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180006801  mov     r9d, eax; char *
0x180006804  mov     edx, 0ABh; void *
0x180006809  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000680e  mov     rcx, [rsp+38h+arg_8]
0x180006813  test    rcx, rcx
0x180006816  jz      short loc_18000681E
0x180006818  call    cs:__imp_DismDelete
0x18000681e  mov     r9d, ebx; char *
0x180006821  mov     edx, 9Dh; void *
0x180006826  mov     rcx, [rsp+38h]; this
0x18000682b  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\cle"...
0x180006832  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006837  jmp     short loc_180006875
0x180006839  mov     rcx, [rsp+38h+arg_8]
0x18000683e  mov     edx, [rcx+8]
0x180006841  lea     eax, [rdx-4]
0x180006844  test    eax, 0FFFFFFFCh
0x180006849  jnz     short loc_180006850
0x18000684b  cmp     edx, 6
0x18000684e  jnz     short loc_180006853
0x180006850  xor     dil, dil
0x180006853  call    cs:__imp_DismDelete
0x180006859  test    dil, dil
0x18000685c  jnz     short loc_180006873
0x18000685e  call    ?RemoveSandboxPackages@@YAJXZ; RemoveSandboxPackages(void)
0x180006863  mov     ebx, eax
0x180006865  test    eax, eax
0x180006867  jns     short loc_180006873
0x180006869  mov     r9d, eax
0x18000686c  mov     edx, 0A2h
0x180006871  jmp     short loc_180006826
0x180006873  xor     ebx, ebx
0x180006875  lea     rcx, [rsp+38h+arg_0]; this
0x18000687a  call    ??1DismHelper@Csl@@QEAA@XZ; Csl::DismHelper::~DismHelper(void)
0x18000687f  mov     eax, ebx
0x180006881  mov     rbx, [rsp+38h+arg_10]
0x180006886  add     rsp, 30h
0x18000688a  pop     rdi
0x18000688b  retn
```
