# CDefragOperation::_GetRetrimSettings(ulong *,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *)

- ea: `0x18002a1d0`
- end: `0x18002a4a8`
- name: `?_GetRetrimSettings@CDefragOperation@@IEAAJPEAK000000@Z`
- size: `728`
- prototype: `__int64 __fastcall(CDefragOperation *__hidden this, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002f280`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x1800193a0`
- `0x18002a1d0`
- `0x18002a720`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a47b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a47b`

## string_xrefs

- `0x18002a2e9`: `RetrimMinRelevantTrimSizeKB`
- `0x18002a310`: `RetrimMaxSingleTrimSizeKB`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDefragOperation::_GetRetrimSettings(
        CDefragOperation *this,
        unsigned int *a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned int *a6,
        unsigned int *a7,
        unsigned int *a8)
{
  HKEY v11; // rdx
  unsigned int v12; // r9d
  unsigned int v13; // r13d
  int v14; // eax
  HKEY v15; // rcx
  int v16; // r15d
  unsigned int v17; // r14d
  unsigned int v18; // r12d
  unsigned int v19; // esi
  unsigned int v20; // edi
  unsigned int v21; // ebx
  int v22; // eax
  unsigned int v23; // ebx
  unsigned __int16 *v25; // [rsp+28h] [rbp-91h]
  unsigned int v26; // [rsp+30h] [rbp-89h]
  struct _SECURITY_ATTRIBUTES *v27; // [rsp+40h] [rbp-79h]
  unsigned int *v28; // [rsp+50h] [rbp-69h]
  HKEY hKey; // [rsp+58h] [rbp-61h] BYREF
  unsigned int v30; // [rsp+60h] [rbp-59h] BYREF
  unsigned int v31; // [rsp+64h] [rbp-55h] BYREF
  unsigned int v32; // [rsp+68h] [rbp-51h] BYREF
  unsigned int v33; // [rsp+6Ch] [rbp-4Dh] BYREF
  unsigned int v34; // [rsp+70h] [rbp-49h] BYREF
  unsigned int v35; // [rsp+74h] [rbp-45h] BYREF
  unsigned int v36; // [rsp+78h] [rbp-41h] BYREF
  __int16 v37; // [rsp+7Ch] [rbp-3Dh]
  CDefragOperation *v38; // [rsp+108h] [rbp+4Fh] BYREF
  unsigned int *v39; // [rsp+110h] [rbp+57h]
  unsigned int *v40; // [rsp+118h] [rbp+5Fh]
  unsigned int *v41; // [rsp+120h] [rbp+67h]

  v41 = a4;
  v40 = a3;
  v39 = a2;
  v38 = this;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v36, "CDefragOperation::_GetRetrimSettings", 1817, 1);
  hKey = 0;
  LODWORD(v38) = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v13 = 0;
  v35 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  if ( a6 )
    *a6 = 0;
  if ( a7 )
    *a7 = 0;
  if ( a8 )
    *a8 = 0;
  v14 = SxRegCreateKeyExStateSeparated(
          L"DfrgRetrimFunction",
          v11,
          L"SOFTWARE\\Microsoft\\Dfrg\\RetrimFunction",
          v12,
          v25,
          v26,
          0x2001Fu,
          v27,
          &hKey,
          v28);
  v15 = hKey;
  if ( v14 < 0 || (unsigned __int64)hKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v19 = 100;
    v20 = 40;
    v21 = 1024;
    v16 = 128;
    v17 = 0x100000;
    v18 = 1;
  }
  else
  {
    v36 = 0;
    v37 = 1862;
    if ( (unsigned int)SxRegReadDWORD(hKey, L"RetrimMinRelevantTrimSizeKB", (unsigned int *)&v38, 1) == 1
      || (v16 = (int)v38) == 0 )
    {
      v16 = 128;
    }
    if ( (unsigned int)SxRegReadDWORD(hKey, L"RetrimMaxSingleTrimSizeKB", &v30, 1) == 1 || (v17 = v30) == 0 )
      v17 = 0x100000;
    if ( (unsigned int)SxRegReadDWORD(hKey, L"MinReclaimSlabsPerThousandUsed", &v31, 1) == 1 || (v18 = v31) == 0 )
      v18 = 1;
    if ( (unsigned int)SxRegReadDWORD(hKey, L"MinReclaimSlabsPerThousandUsedBoundMB", &v32, 1) == 1 || (v19 = v32) == 0 )
      v19 = 100;
    if ( (unsigned int)SxRegReadDWORD(hKey, L"MinReclaimSlabs", &v33, 1) == 1 || (v20 = v33) == 0 )
      v20 = 40;
    if ( (unsigned int)SxRegReadDWORD(hKey, L"MinReclaimSlabsBoundMB", &v34, 1) == 1 || (v21 = v34) == 0 )
      v21 = 1024;
    v22 = SxRegReadDWORD(hKey, L"RetrimOnThinlyProvisionedReFS", &v35, 1);
    v15 = hKey;
    if ( v22 == 1 )
      v13 = 0;
    else
      v13 = v35;
  }
  if ( v39 )
    *v39 = v16;
  if ( v40 )
    *v40 = v17;
  if ( v41 )
    *v41 = v18;
  if ( a5 )
    *a5 = v19;
  if ( a6 )
    *a6 = v20;
  if ( a7 )
    *a7 = v21;
  if ( a8 )
    *a8 = v13;
  v23 = v36;
  if ( (unsigned __int64)v15 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(v15);
    hKey = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v36);
  return v23;
}

```

## disassembly

```asm
0x18002a1d0  mov     rax, rsp
0x18002a1d3  mov     [rax+20h], r9
0x18002a1d7  mov     [rax+18h], r8
0x18002a1db  mov     [rax+10h], rdx
0x18002a1df  mov     [rax+8], rcx
0x18002a1e3  push    rbp
0x18002a1e4  push    rbx
0x18002a1e5  push    rsi
0x18002a1e6  push    rdi
0x18002a1e7  push    r12
0x18002a1e9  push    r13
0x18002a1eb  push    r14
0x18002a1ed  push    r15
0x18002a1ef  lea     rbp, [rax-47h]
0x18002a1f3  sub     rsp, 0B8h
0x18002a1fa  mov     rbx, r9
0x18002a1fd  mov     rsi, r8
0x18002a200  mov     rdi, rdx
0x18002a203  mov     r9d, 1; unsigned __int16
0x18002a209  mov     r8d, 719h; unsigned __int16
0x18002a20f  lea     rdx, aCdefragoperati_13; "CDefragOperation::_GetRetrimSettings"
0x18002a216  lea     rcx, [rbp+3Fh+var_80]; this
0x18002a21a  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002a21f  nop
0x18002a220  xor     r12d, r12d
0x18002a223  mov     [rbp+3Fh+hKey], r12
0x18002a227  mov     dword ptr [rbp+3Fh+arg_0], r12d
0x18002a22b  mov     [rbp+3Fh+var_98], r12d
0x18002a22f  mov     [rbp+3Fh+var_94], r12d
0x18002a233  mov     [rbp+3Fh+var_90], r12d
0x18002a237  mov     [rbp+3Fh+var_8C], r12d
0x18002a23b  mov     [rbp+3Fh+var_88], r12d
0x18002a23f  mov     r13d, r12d
0x18002a242  mov     [rbp+3Fh+var_84], r12d
0x18002a246  test    rsi, rsi
0x18002a249  jz      short loc_18002A24E
0x18002a24b  mov     [rsi], r12d
0x18002a24e  test    rdi, rdi
0x18002a251  jz      short loc_18002A256
0x18002a253  mov     [rdi], r12d
0x18002a256  test    rbx, rbx
0x18002a259  jz      short loc_18002A25E
0x18002a25b  mov     [rbx], r12d
0x18002a25e  mov     rax, [rbp+3Fh+arg_20]
0x18002a262  test    rax, rax
0x18002a265  jz      short loc_18002A26A
0x18002a267  mov     [rax], r12d
0x18002a26a  mov     rax, [rbp+3Fh+arg_28]
0x18002a26e  test    rax, rax
0x18002a271  jz      short loc_18002A276
0x18002a273  mov     [rax], r12d
0x18002a276  mov     rax, [rbp+3Fh+arg_30]
0x18002a27a  test    rax, rax
0x18002a27d  jz      short loc_18002A282
0x18002a27f  mov     [rax], r12d
0x18002a282  mov     rax, [rbp+3Fh+arg_38]
0x18002a289  test    rax, rax
0x18002a28c  jz      short loc_18002A291
0x18002a28e  mov     [rax], r12d
0x18002a291  lea     rax, [rbp+3Fh+hKey]
0x18002a295  mov     [rsp+40h], rax; PHKEY
0x18002a29a  mov     dword ptr [rsp+30h], 2001Fh; REGSAM
0x18002a2a2  lea     r8, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Dfrg\\RetrimFuncti"...
0x18002a2a9  lea     rcx, aDfrgretrimfunc; "DfrgRetrimFunction"
0x18002a2b0  call    ?SxRegCreateKeyExStateSeparated@@YAJPEBGPEAUHKEY__@@0KPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; SxRegCreateKeyExStateSeparated(ushort const *,HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x18002a2b5  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18002a2b9  test    eax, eax
0x18002a2bb  js      loc_18002A3FF
0x18002a2c1  lea     rax, [rcx-1]
0x18002a2c5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002a2c9  ja      loc_18002A3FF
0x18002a2cf  mov     [rbp+3Fh+var_80], r12d
0x18002a2d3  mov     eax, 746h
0x18002a2d8  mov     [rbp+3Fh+var_7C], ax
0x18002a2dc  mov     r13d, 1
0x18002a2e2  mov     r9d, r13d; int
0x18002a2e5  lea     r8, [rbp+3Fh+arg_0]; unsigned int *
0x18002a2e9  lea     rdx, aRetrimminrelev; "RetrimMinRelevantTrimSizeKB"
0x18002a2f0  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x18002a2f5  cmp     eax, r13d
0x18002a2f8  jz      short loc_18002A303
0x18002a2fa  mov     r15d, dword ptr [rbp+3Fh+arg_0]
0x18002a2fe  test    r15d, r15d
0x18002a301  jnz     short loc_18002A309
0x18002a303  mov     r15d, 80h
0x18002a309  mov     r9d, r13d; int
0x18002a30c  lea     r8, [rbp+3Fh+var_98]; unsigned int *
0x18002a310  lea     rdx, aRetrimmaxsingl; "RetrimMaxSingleTrimSizeKB"
0x18002a317  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18002a31b  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x18002a320  cmp     eax, r13d
0x18002a323  jz      short loc_18002A32E
0x18002a325  mov     r14d, [rbp+3Fh+var_98]
0x18002a329  test    r14d, r14d
0x18002a32c  jnz     short loc_18002A334
0x18002a32e  mov     r14d, 100000h
0x18002a334  mov     r9d, r13d; int
0x18002a337  lea     r8, [rbp+3Fh+var_94]; unsigned int *
0x18002a33b  lea     rdx, aMinreclaimslab_3; "MinReclaimSlabsPerThousandUsed"
0x18002a342  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18002a346  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x18002a34b  cmp     eax, r13d
0x18002a34e  jz      short loc_18002A359
0x18002a350  mov     r12d, [rbp+3Fh+var_94]
0x18002a354  test    r12d, r12d
0x18002a357  jnz     short loc_18002A35C
0x18002a359  mov     r12d, r13d
0x18002a35c  mov     r9d, r13d; int
0x18002a35f  lea     r8, [rbp+3Fh+var_90]; unsigned int *
0x18002a363  lea     rdx, aMinreclaimslab_4; "MinReclaimSlabsPerThousandUsedBoundMB"
0x18002a36a  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18002a36e  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x18002a373  cmp     eax, r13d
0x18002a376  jz      short loc_18002A37F
0x18002a378  mov     esi, [rbp+3Fh+var_90]
0x18002a37b  test    esi, esi
0x18002a37d  jnz     short loc_18002A384
0x18002a37f  mov     esi, 64h ; 'd'
0x18002a384  mov     r9d, r13d; int
0x18002a387  lea     r8, [rbp+3Fh+var_8C]; unsigned int *
0x18002a38b  lea     rdx, aMinreclaimslab_5; "MinReclaimSlabs"
0x18002a392  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18002a396  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x18002a39b  cmp     eax, r13d
0x18002a39e  jz      short loc_18002A3A7
0x18002a3a0  mov     edi, [rbp+3Fh+var_8C]
0x18002a3a3  test    edi, edi
0x18002a3a5  jnz     short loc_18002A3AC
0x18002a3a7  mov     edi, 28h ; '('
0x18002a3ac  mov     r9d, r13d; int
0x18002a3af  lea     r8, [rbp+3Fh+var_88]; unsigned int *
0x18002a3b3  lea     rdx, aMinreclaimslab_6; "MinReclaimSlabsBoundMB"
0x18002a3ba  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18002a3be  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x18002a3c3  cmp     eax, r13d
0x18002a3c6  jz      short loc_18002A3CF
0x18002a3c8  mov     ebx, [rbp+3Fh+var_88]
0x18002a3cb  test    ebx, ebx
0x18002a3cd  jnz     short loc_18002A3D4
0x18002a3cf  mov     ebx, 400h
0x18002a3d4  mov     r9d, r13d; int
0x18002a3d7  lea     r8, [rbp+3Fh+var_84]; unsigned int *
0x18002a3db  lea     rdx, aRetrimonthinly; "RetrimOnThinlyProvisionedReFS"
0x18002a3e2  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18002a3e6  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x18002a3eb  mov     rcx, [rbp+3Fh+hKey]
0x18002a3ef  cmp     eax, r13d
0x18002a3f2  jnz     short loc_18002A3F9
0x18002a3f4  xor     r13d, r13d
0x18002a3f7  jmp     short loc_18002A41A
0x18002a3f9  mov     r13d, [rbp+3Fh+var_84]
0x18002a3fd  jmp     short loc_18002A41A
0x18002a3ff  mov     esi, 64h ; 'd'
0x18002a404  lea     edi, [rsi-3Ch]
0x18002a407  mov     ebx, 400h
0x18002a40c  lea     r15d, [rsi+1Ch]
0x18002a410  mov     r14d, 100000h
0x18002a416  lea     r12d, [rsi-63h]
0x18002a41a  mov     rax, [rbp+3Fh+arg_8]
0x18002a41e  test    rax, rax
0x18002a421  jz      short loc_18002A426
0x18002a423  mov     [rax], r15d
0x18002a426  mov     rax, [rbp+3Fh+arg_10]
0x18002a42a  test    rax, rax
0x18002a42d  jz      short loc_18002A432
0x18002a42f  mov     [rax], r14d
0x18002a432  mov     rax, [rbp+3Fh+arg_18]
0x18002a436  test    rax, rax
0x18002a439  jz      short loc_18002A43E
0x18002a43b  mov     [rax], r12d
0x18002a43e  mov     rax, [rbp+3Fh+arg_20]
0x18002a442  test    rax, rax
0x18002a445  jz      short loc_18002A449
0x18002a447  mov     [rax], esi
0x18002a449  mov     rax, [rbp+3Fh+arg_28]
0x18002a44d  test    rax, rax
0x18002a450  jz      short loc_18002A454
0x18002a452  mov     [rax], edi
0x18002a454  mov     rax, [rbp+3Fh+arg_30]
0x18002a458  test    rax, rax
0x18002a45b  jz      short loc_18002A45F
0x18002a45d  mov     [rax], ebx
0x18002a45f  mov     rax, [rbp+3Fh+arg_38]
0x18002a466  test    rax, rax
0x18002a469  jz      short loc_18002A46E
0x18002a46b  mov     [rax], r13d
0x18002a46e  mov     ebx, [rbp+3Fh+var_80]
0x18002a471  lea     rdx, [rcx-1]
0x18002a475  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002a479  ja      short loc_18002A489
0x18002a47b  call    cs:__imp_RegCloseKey
0x18002a481  mov     [rbp+3Fh+hKey], 0
0x18002a489  lea     rcx, [rbp+3Fh+var_80]; this
0x18002a48d  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002a492  mov     eax, ebx
0x18002a494  add     rsp, 0B8h
0x18002a49b  pop     r15
0x18002a49d  pop     r14
0x18002a49f  pop     r13
0x18002a4a1  pop     r12
0x18002a4a3  pop     rdi
0x18002a4a4  pop     rsi
0x18002a4a5  pop     rbx
0x18002a4a6  pop     rbp
0x18002a4a7  retn
```
