# EfspFileRequiresEncryption

- ea: `0x1400510ac`
- end: `0x140051781`
- name: `EfspFileRequiresEncryption`
- size: `1749`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x14004f8b0`
- `0x140050050`

## callees

- `0x140001010`
- `0x1400010b4`
- `0x1400010e4`
- `0x14000b54c`
- `0x14000b5d0`
- `0x14000b5f4`
- `0x14000c074`
- `0x14000c230`
- `0x1400510ac`
- `0x140052de8`
- `0x14005323c`
- `0x140053314`
- `0x140053360`
- `0x140053690`
- `0x1400559f0`
- `0x140055a7c`
- `0x140055c54`
- `0x14005693c`
- `0x140059940`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400512f1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005131a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400513d3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400512f1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005131a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400513d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400516fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051727`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051742`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400516fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051727`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051742`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400513aa`
- `ntoskrnl!ExReleaseFastMutex` at `0x140051463`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400513aa`
- `ntoskrnl!ExReleaseFastMutex` at `0x140051463`
- `ntoskrnl!ExAcquireFastMutex` at `0x140051372`
- `ntoskrnl!ExAcquireFastMutex` at `0x14005142b`
- `ntoskrnl!ExAcquireFastMutex` at `0x140051372`
- `ntoskrnl!ExAcquireFastMutex` at `0x14005142b`
- `ntoskrnl!KeGetCurrentIrql` at `0x140051185`
- `ntoskrnl!KeGetCurrentIrql` at `0x140051185`
- `ntoskrnl!PsGetCurrentThreadTeb` at `0x14005121f`
- `ntoskrnl!PsGetCurrentThreadTeb` at `0x14005121f`
- `ntoskrnl!wcsrchr` at `0x1400514f9`
- `ntoskrnl!wcsrchr` at `0x1400514f9`

## string_xrefs

- `0x1400512e2`: `\Registry\Machine\System\CurrentControlSet\Services\NTFS\EFS\Parameters`
- `0x14005130b`: `EdpExcludedExtensions`
- `0x1400513c4`: `EdpExcludedPaths`

## pseudocode

```c
__int64 __fastcall EfspFileRequiresEncryption(
        __int64 a1,
        __int64 a2,
        char a3,
        __int64 a4,
        int a5,
        _BYTE *a6,
        _QWORD *a7)
{
  int IsProcessLocalSystem; // esi
  __int64 v10; // rdi
  __int64 v11; // rcx
  char v12; // al
  __int64 v13; // r14
  _QWORD *CurrentThreadTeb; // rax
  wchar_t *v15; // r14
  wchar_t *v16; // r15
  wchar_t *v17; // rax
  const wchar_t *v18; // rdx
  const wchar_t *v19; // r12
  wchar_t *v20; // r9
  wchar_t *v21; // rdx
  wchar_t *v22; // r8
  int v23; // r8d
  char v25; // [rsp+30h] [rbp-178h] BYREF
  char v26; // [rsp+31h] [rbp-177h]
  char v27[2]; // [rsp+32h] [rbp-176h] BYREF
  int v28; // [rsp+34h] [rbp-174h] BYREF
  __int64 v29; // [rsp+38h] [rbp-170h] BYREF
  __int64 v30; // [rsp+40h] [rbp-168h]
  const wchar_t *v31; // [rsp+48h] [rbp-160h] BYREF
  struct _UNICODE_STRING v32; // [rsp+50h] [rbp-158h] BYREF
  __int64 v33; // [rsp+60h] [rbp-148h]
  __int64 v34; // [rsp+68h] [rbp-140h]
  wchar_t *Str; // [rsp+70h] [rbp-138h] BYREF
  __int64 v36; // [rsp+78h] [rbp-130h]
  PVOID P; // [rsp+80h] [rbp-128h] BYREF
  PVOID v38; // [rsp+88h] [rbp-120h] BYREF
  struct _UNICODE_STRING v39; // [rsp+90h] [rbp-118h] BYREF
  struct _UNICODE_STRING v40; // [rsp+A0h] [rbp-108h] BYREF
  struct _UNICODE_STRING v41; // [rsp+B0h] [rbp-F8h] BYREF
  __int64 v42; // [rsp+C0h] [rbp-E8h]
  __int64 v43; // [rsp+C8h] [rbp-E0h]
  struct _UNICODE_STRING DestinationString; // [rsp+D0h] [rbp-D8h] BYREF
  __int128 v45; // [rsp+E0h] [rbp-C8h] BYREF
  _BYTE v46[32]; // [rsp+F0h] [rbp-B8h] BYREF
  struct _UNICODE_STRING *v47; // [rsp+110h] [rbp-98h]
  __int64 v48; // [rsp+118h] [rbp-90h]
  _QWORD v49[2]; // [rsp+120h] [rbp-88h] BYREF
  _BYTE v50[16]; // [rsp+130h] [rbp-78h] BYREF
  int *v51; // [rsp+140h] [rbp-68h]
  __int64 v52; // [rsp+148h] [rbp-60h]
  struct _UNICODE_STRING *v53; // [rsp+150h] [rbp-58h]
  __int64 v54; // [rsp+158h] [rbp-50h]

  v36 = a4;
  v34 = a2;
  v42 = a2;
  v43 = a4;
  *(_QWORD *)&v39.Length = a6;
  *(_QWORD *)&v32.Length = a7;
  IsProcessLocalSystem = 0;
  v30 = 0;
  v26 = 0;
  v27[0] = 0;
  v31 = 0;
  Str = 0;
  DestinationString = 0;
  v40 = 0;
  v41 = 0;
  v38 = 0;
  v45 = 0;
  P = 0;
  v10 = 0;
  v29 = 0;
  *a6 = 0;
  if ( a3 || (!qword_140017A10 || !qword_140017A20) && KeGetCurrentIrql() )
    goto LABEL_38;
  IsProcessLocalSystem = EdppIsProcessLocalSystem(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 32LL, v27);
  if ( IsProcessLocalSystem < 0 )
    goto LABEL_38;
  if ( v27[0] )
    goto LABEL_38;
  IsProcessLocalSystem = SrpGetEnterpriseContext(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 32LL, &v29);
  v28 = IsProcessLocalSystem;
  v10 = v29;
  if ( IsProcessLocalSystem < 0 )
    goto LABEL_38;
  v11 = *(_QWORD *)(v29 + 8) & 0xALL;
  if ( (*(_QWORD *)(v29 + 8) & 3) != 0 || (v12 = 1, !*(_DWORD *)(v29 + 4)) )
    v12 = 0;
  if ( v11 != 10 )
  {
    if ( !v12 )
      goto LABEL_38;
    goto LABEL_17;
  }
  v13 = 0;
  v33 = 0;
  CurrentThreadTeb = PsGetCurrentThreadTeb();
  if ( CurrentThreadTeb )
  {
    v13 = CurrentThreadTeb[740];
    v33 = v13;
  }
  if ( v13 == 3644083109LL )
  {
LABEL_17:
    if ( *(_DWORD *)(v10 + 4) )
    {
      IsProcessLocalSystem = SrpCreateEnterpriseId(*(PCWSTR *)(v10 + 24));
      if ( IsProcessLocalSystem >= 0 )
      {
        v26 = 1;
        if ( !qword_140017A10 || !qword_140017A20 )
        {
          RtlInitUnicodeString(
            &DestinationString,
            L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\NTFS\\EFS\\Parameters");
          if ( !qword_140017A10 )
          {
            RtlInitUnicodeString(&v40, L"EdpExcludedExtensions");
            v32 = v40;
            v39 = DestinationString;
            if ( (int)EdppReadExclusions(&v39, &v32, &v38, &v41) >= 0 )
            {
              ExAcquireFastMutex(&stru_1400179D8);
              if ( !qword_140017A10 )
                EdppBuildExclusionsList(&v41, &qword_140017A10, &dword_140017A18);
              ExReleaseFastMutex(&stru_1400179D8);
            }
          }
          if ( !qword_140017A20 )
          {
            RtlInitUnicodeString(&v40, L"EdpExcludedPaths");
            v41 = v40;
            v32 = DestinationString;
            if ( (int)EdppReadExclusions(&v32, &v41, &P, &v45) >= 0 )
            {
              ExAcquireFastMutex(&stru_1400179D8);
              if ( !qword_140017A20 )
                EdppBuildExclusionsList(&v45, &qword_140017A20, &dword_140017A28);
              ExReleaseFastMutex(&stru_1400179D8);
            }
            if ( !qword_140017A20 )
              goto LABEL_70;
          }
        }
        if ( !(unsigned __int8)EdppIsExcludedPath(a4) )
        {
LABEL_70:
          if ( !qword_140017A10 || !(unsigned __int8)EdppIsExcludedName(a4) )
          {
            *a6 = 1;
            if ( a7 )
            {
              *a7 = v30;
              v26 = 0;
            }
          }
        }
      }
    }
    else
    {
      IsProcessLocalSystem = -1073741811;
      EfspTraceLogAssert(v11, 5, 333, 3221225485LL);
    }
  }
LABEL_38:
  if ( *a6 )
  {
    v15 = 0;
    EfspGetFilePathExtension(a4, &v31);
    EfspGetRequestorProcessName(v34, &Str);
    v16 = Str;
    if ( Str )
    {
      v17 = wcsrchr(Str, 0x5Cu);
      v15 = v17;
      if ( v17 )
      {
        if ( *v17 == 92 )
          v15 = v17 + 1;
      }
    }
    if ( (unsigned int)dword_140017130 <= 5 )
    {
      v19 = v31;
    }
    else
    {
      v25 = a5;
      v47 = (struct _UNICODE_STRING *)&v25;
      v48 = 1;
      v18 = L"NA";
      v19 = v31;
      if ( v31 )
        v18 = v31;
      tlgCreate1Sz_wchar_t(v49, v18);
      v21 = v20;
      if ( v15 )
        v21 = v15;
      tlgCreate1Sz_wchar_t(v50, v21);
      v28 = IsProcessLocalSystem;
      v51 = &v28;
      v52 = 4;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140017130, &byte_140010B77, 0, 0, 6, v46);
    }
    if ( (unsigned int)dword_1400170F8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400170F8, 0x400000000000LL) )
    {
      *(_QWORD *)&v32.Length = 1;
      v47 = &v32;
      v48 = 8;
      v25 = a5;
      v49[0] = &v25;
      v49[1] = 1;
      if ( v15 )
        v22 = v15;
      tlgCreate1Sz_wchar_t(v50, v22);
      v28 = IsProcessLocalSystem;
      v51 = &v28;
      v52 = 4;
      *(_QWORD *)&v39.Length = 0x1000000;
      v53 = &v39;
      v54 = 8;
      tlgWriteAgg((unsigned int)&dword_1400170F8, (unsigned int)byte_140010BE9, v23, 7, (__int64)v46);
    }
    EdpEnforcementLog_FileRequiresEncryption(v36, v30, a5, v10, IsProcessLocalSystem);
    if ( v19 )
      EfspFreeFilePathExtension(v19);
    if ( v16 )
      ExFreePoolWithTag(v16, 0x54736645u);
  }
  if ( v26 )
    SrpDeleteEnterpriseId(v30);
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( v38 )
    ExFreePoolWithTag(v38, 0);
  if ( v10 )
    SrpDeleteEnterpriseId(v10);
  return (unsigned int)IsProcessLocalSystem;
}

```

## disassembly

```asm
0x1400510ac  push    rbx
0x1400510ae  push    rsi
0x1400510af  push    rdi
0x1400510b0  push    r12
0x1400510b2  push    r13
0x1400510b4  push    r14
0x1400510b6  push    r15
0x1400510b8  sub     rsp, 170h
0x1400510bf  mov     rax, cs:__security_cookie
0x1400510c6  xor     rax, rsp
0x1400510c9  mov     [rsp+1A8h+var_48], rax
0x1400510d1  mov     r15, r9
0x1400510d4  mov     [rsp+1A8h+var_130], r9
0x1400510d9  mov     [rsp+1A8h+var_140], rdx
0x1400510de  mov     r14, rcx
0x1400510e1  mov     [rsp+1A8h+var_E8], rdx
0x1400510e9  mov     [rsp+1A8h+var_E0], r9
0x1400510f1  mov     r12, [rsp+1A8h+arg_28]
0x1400510f9  mov     qword ptr [rsp+1A8h+var_118], r12
0x140051101  mov     r13, [rsp+1A8h+arg_30]
0x140051109  mov     qword ptr [rsp+1A8h+var_158], r13
0x14005110e  xor     ebx, ebx
0x140051110  mov     esi, ebx
0x140051112  mov     [rsp+1A8h+var_168], rbx
0x140051117  mov     [rsp+1A8h+var_177], bl
0x14005111b  mov     [rsp+1A8h+var_176], bl
0x14005111f  mov     [rsp+1A8h+var_160], rbx
0x140051124  mov     [rsp+1A8h+Str], rbx
0x140051129  xorps   xmm0, xmm0
0x14005112c  movups  xmmword ptr [rsp+1A8h+DestinationString.Length], xmm0
0x140051134  xorps   xmm1, xmm1
0x140051137  movups  xmmword ptr [rsp+1A8h+var_108.Length], xmm1
0x14005113f  movups  [rsp+1A8h+var_F8], xmm0
0x140051147  mov     [rsp+1A8h+var_120], rbx
0x14005114f  movups  [rsp+1A8h+var_C8], xmm1
0x140051157  mov     [rsp+1A8h+P], rbx
0x14005115f  mov     edi, ebx
0x140051161  mov     [rsp+1A8h+var_170], rbx
0x140051166  mov     [r12], bl
0x14005116a  test    r8b, r8b
0x14005116d  jnz     loc_1400514B2
0x140051173  cmp     cs:qword_140017A10, rbx
0x14005117a  jz      short loc_140051185
0x14005117c  cmp     cs:qword_140017A20, rbx
0x140051183  jnz     short loc_140051199
0x140051185  call    cs:__imp_KeGetCurrentIrql
0x14005118c  nop     dword ptr [rax+rax+00h]
0x140051191  test    al, al
0x140051193  jnz     loc_1400514B2
0x140051199  mov     rax, [r14+8]
0x14005119d  mov     rcx, [rax+8]
0x1400511a1  add     rcx, 20h ; ' '
0x1400511a5  lea     rdx, [rsp+1A8h+var_176]
0x1400511aa  call    EdppIsProcessLocalSystem
0x1400511af  mov     esi, eax
0x1400511b1  test    eax, eax
0x1400511b3  js      loc_1400514B2
0x1400511b9  cmp     [rsp+1A8h+var_176], bl
0x1400511bd  jnz     loc_1400514B2
0x1400511c3  mov     rax, [r14+8]
0x1400511c7  mov     rcx, [rax+8]
0x1400511cb  add     rcx, 20h ; ' '
0x1400511cf  lea     rdx, [rsp+1A8h+var_170]
0x1400511d4  call    SrpGetEnterpriseContext
0x1400511d9  mov     esi, eax
0x1400511db  mov     [rsp+1A8h+var_174], eax
0x1400511df  mov     rdi, [rsp+1A8h+var_170]
0x1400511e4  test    eax, eax
0x1400511e6  js      loc_1400514B2
0x1400511ec  mov     rax, [rdi+8]
0x1400511f0  mov     rcx, rax
0x1400511f3  and     ecx, 0Ah
0x1400511f6  test    al, 3
0x1400511f8  jnz     short loc_140051201
0x1400511fa  cmp     [rdi+4], ebx
0x1400511fd  mov     al, 1
0x1400511ff  ja      short loc_140051203
0x140051201  mov     al, bl
0x140051203  cmp     rcx, 0Ah
0x140051207  jz      short loc_140051217
0x140051209  test    al, al
0x14005120b  jz      loc_1400514B2
0x140051211  cmp     rcx, 0Ah
0x140051215  jnz     short loc_140051287
0x140051217  mov     r14, rbx
0x14005121a  mov     [rsp+1A8h+var_148], rbx
0x14005121f  call    cs:__imp_PsGetCurrentThreadTeb
0x140051226  nop     dword ptr [rax+rax+00h]
0x14005122b  test    rax, rax
0x14005122e  jz      short loc_140051279
0x140051230  mov     r14, [rax+1720h]
0x140051237  mov     [rsp+1A8h+var_148], r14
0x14005123c  jmp     short loc_140051279
0x14005123e  xor     ebx, ebx
0x140051240  mov     esi, [rsp+1A8h+var_174]
0x140051244  mov     [rsp+1A8h+var_177], bl
0x140051248  mov     r14, [rsp+1A8h+var_148]
0x14005124d  mov     rdi, [rsp+1A8h+var_170]
0x140051252  mov     rax, [rsp+1A8h+var_E8]
0x14005125a  mov     [rsp+1A8h+var_140], rax
0x14005125f  mov     r15, [rsp+1A8h+var_E0]
0x140051267  mov     [rsp+1A8h+var_130], r15
0x14005126c  mov     r12, qword ptr [rsp+1A8h+var_118]
0x140051274  mov     r13, qword ptr [rsp+1A8h+var_158]
0x140051279  mov     eax, 0D9344BA5h
0x14005127e  cmp     r14, rax
0x140051281  jnz     loc_1400514B2
0x140051287  cmp     [rdi+4], ebx
0x14005128a  jnz     short loc_1400512A9
0x14005128c  mov     esi, 0C000000Dh
0x140051291  mov     r9d, esi
0x140051294  mov     edx, 5
0x140051299  mov     r8d, 14Dh
0x14005129f  call    EfspTraceLogAssert
0x1400512a4  jmp     loc_1400514B2
0x1400512a9  lea     r8, [rsp+1A8h+var_168]
0x1400512ae  movzx   edx, word ptr [rdi+12h]
0x1400512b2  mov     rcx, [rdi+18h]; SourceString
0x1400512b6  call    SrpCreateEnterpriseId
0x1400512bb  mov     esi, eax
0x1400512bd  test    eax, eax
0x1400512bf  js      loc_1400514B2
0x1400512c5  mov     [rsp+1A8h+var_177], 1
0x1400512ca  cmp     cs:qword_140017A10, 0
0x1400512d2  jz      short loc_1400512E2
0x1400512d4  cmp     cs:qword_140017A20, 0
0x1400512dc  jnz     loc_140051479
0x1400512e2  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400512e9  lea     rcx, [rsp+1A8h+DestinationString]; DestinationString
0x1400512f1  call    cs:__imp_RtlInitUnicodeString
0x1400512f8  nop     dword ptr [rax+rax+00h]
0x1400512fd  cmp     cs:qword_140017A10, 0
0x140051305  jnz     loc_1400513B6
0x14005130b  lea     rdx, aEdpexcludedext; "EdpExcludedExtensions"
0x140051312  lea     rcx, [rsp+1A8h+var_108]; DestinationString
0x14005131a  call    cs:__imp_RtlInitUnicodeString
0x140051321  nop     dword ptr [rax+rax+00h]
0x140051326  movaps  xmm0, xmmword ptr [rsp+1A8h+var_108.Length]
0x14005132e  movdqa  [rsp+1A8h+var_158], xmm0
0x140051334  movaps  xmm1, xmmword ptr [rsp+1A8h+DestinationString.Length]
0x14005133c  movdqa  [rsp+1A8h+var_118], xmm1
0x140051345  lea     r9, [rsp+1A8h+var_F8]
0x14005134d  lea     r8, [rsp+1A8h+var_120]
0x140051355  lea     rdx, [rsp+1A8h+var_158]
0x14005135a  lea     rcx, [rsp+1A8h+var_118]
0x140051362  call    EdppReadExclusions
0x140051367  test    eax, eax
0x140051369  js      short loc_1400513B6
0x14005136b  lea     rcx, stru_1400179D8; FastMutex
0x140051372  call    cs:__imp_ExAcquireFastMutex
0x140051379  nop     dword ptr [rax+rax+00h]
0x14005137e  cmp     cs:qword_140017A10, 0
0x140051386  jnz     short loc_1400513A3
0x140051388  lea     r8, dword_140017A18
0x14005138f  lea     rdx, qword_140017A10
0x140051396  lea     rcx, [rsp+1A8h+var_F8]
0x14005139e  call    EdppBuildExclusionsList
0x1400513a3  lea     rcx, stru_1400179D8; FastMutex
0x1400513aa  call    cs:__imp_ExReleaseFastMutex
0x1400513b1  nop     dword ptr [rax+rax+00h]
0x1400513b6  cmp     cs:qword_140017A20, 0
0x1400513be  jnz     loc_140051479
0x1400513c4  lea     rdx, aEdpexcludedpat; "EdpExcludedPaths"
0x1400513cb  lea     rcx, [rsp+1A8h+var_108]; DestinationString
0x1400513d3  call    cs:__imp_RtlInitUnicodeString
0x1400513da  nop     dword ptr [rax+rax+00h]
0x1400513df  movaps  xmm0, xmmword ptr [rsp+1A8h+var_108.Length]
0x1400513e7  movdqa  [rsp+1A8h+var_F8], xmm0
0x1400513f0  movaps  xmm1, xmmword ptr [rsp+1A8h+DestinationString.Length]
0x1400513f8  movdqa  [rsp+1A8h+var_158], xmm1
0x1400513fe  lea     r9, [rsp+1A8h+var_C8]
0x140051406  lea     r8, [rsp+1A8h+P]
0x14005140e  lea     rdx, [rsp+1A8h+var_F8]
0x140051416  lea     rcx, [rsp+1A8h+var_158]
0x14005141b  call    EdppReadExclusions
0x140051420  test    eax, eax
0x140051422  js      short loc_14005146F
0x140051424  lea     rcx, stru_1400179D8; FastMutex
0x14005142b  call    cs:__imp_ExAcquireFastMutex
0x140051432  nop     dword ptr [rax+rax+00h]
0x140051437  cmp     cs:qword_140017A20, 0
0x14005143f  jnz     short loc_14005145C
0x140051441  lea     r8, dword_140017A28
0x140051448  lea     rdx, qword_140017A20
0x14005144f  lea     rcx, [rsp+1A8h+var_C8]
0x140051457  call    EdppBuildExclusionsList
0x14005145c  lea     rcx, stru_1400179D8; FastMutex
0x140051463  call    cs:__imp_ExReleaseFastMutex
0x14005146a  nop     dword ptr [rax+rax+00h]
0x14005146f  cmp     cs:qword_140017A20, 0
0x140051477  jz      short loc_140051485
0x140051479  mov     rcx, r15
0x14005147c  call    EdppIsExcludedPath
0x140051481  test    al, al
0x140051483  jnz     short loc_1400514B2
0x140051485  cmp     cs:qword_140017A10, 0
0x14005148d  jz      short loc_14005149B
0x14005148f  mov     rcx, r15
0x140051492  call    EdppIsExcludedName
0x140051497  test    al, al
0x140051499  jnz     short loc_1400514B2
0x14005149b  mov     byte ptr [r12], 1
0x1400514a0  test    r13, r13
0x1400514a3  jz      short loc_1400514B2
0x1400514a5  mov     rax, [rsp+1A8h+var_168]
0x1400514aa  mov     [r13+0], rax
0x1400514ae  mov     [rsp+1A8h+var_177], bl
0x1400514b2  cmp     [r12], bl
0x1400514b6  jz      loc_140051708
0x1400514bc  mov     r13d, [rsp+1A8h+arg_20]
0x1400514c4  mov     r14, rbx
0x1400514c7  lea     rdx, [rsp+1A8h+var_160]
0x1400514cc  mov     rcx, r15
0x1400514cf  call    EfspGetFilePathExtension
0x1400514d4  lea     rdx, [rsp+1A8h+Str]
0x1400514d9  mov     rcx, [rsp+1A8h+var_140]
0x1400514de  call    EfspGetRequestorProcessName
0x1400514e3  mov     r15, [rsp+1A8h+Str]
0x1400514e8  test    r15, r15
0x1400514eb  jz      short loc_140051517
0x1400514ed  mov     r12d, 5Ch ; '\'
0x1400514f3  mov     edx, r12d; Ch
0x1400514f6  mov     rcx, r15; Str
0x1400514f9  call    cs:__imp_wcsrchr
0x140051500  nop     dword ptr [rax+rax+00h]
0x140051505  mov     r14, rax
0x140051508  test    rax, rax
0x14005150b  jz      short loc_140051517
0x14005150d  cmp     [rax], r12w
0x140051511  jnz     short loc_140051517
0x140051513  add     r14, 2
0x140051517  mov     ecx, cs:dword_140017130
0x14005151d  cmp     ecx, 5
0x140051520  jbe     loc_1400515CB
0x140051526  mov     [rsp+1A8h+var_178], r13b
0x14005152b  lea     rax, [rsp+1A8h+var_178]
0x140051530  mov     [rsp+1A8h+var_98], rax
0x140051538  mov     [rsp+1A8h+var_90], 1
0x140051544  lea     r9, aNa; "NA"
0x14005154b  mov     rdx, r9
0x14005154e  mov     r12, [rsp+1A8h+var_160]
0x140051553  test    r12, r12
0x140051556  cmovnz  rdx, r12
0x14005155a  lea     rcx, [rsp+1A8h+var_88]
0x140051562  call    _tlgCreate1Sz_wchar_t
0x140051567  mov     rdx, r9
0x14005156a  test    r14, r14
0x14005156d  cmovnz  rdx, r14
0x140051571  lea     rcx, [rsp+1A8h+var_78]
0x140051579  call    _tlgCreate1Sz_wchar_t
0x14005157e  mov     [rsp+1A8h+var_174], esi
0x140051582  lea     rax, [rsp+1A8h+var_174]
0x140051587  mov     [rsp+1A8h+var_68], rax
0x14005158f  mov     [rsp+1A8h+var_60], 4
0x14005159b  lea     rax, [rsp+1A8h+var_B8]
0x1400515a3  mov     [rsp+1A8h+var_180], rax
0x1400515a8  mov     dword ptr [rsp+1A8h+var_188], 6
0x1400515b0  xor     r9d, r9d
0x1400515b3  xor     r8d, r8d
0x1400515b6  lea     rdx, byte_140010B77
0x1400515bd  lea     rcx, dword_140017130
0x1400515c4  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400515c9  jmp     short loc_1400515D0
0x1400515cb  mov     r12, [rsp+1A8h+var_160]
0x1400515d0  lea     r8, aNa; "NA"
0x1400515d7  mov     r9b, r13b
0x1400515da  mov     eax, cs:dword_1400170F8
0x1400515e0  cmp     eax, 5
0x1400515e3  jbe     loc_1400516C9
0x1400515e9  mov     rdx, 400000000000h
0x1400515f3  lea     rcx, dword_1400170F8
0x1400515fa  call    _tlgKeywordOn
0x1400515ff  test    al, al
0x140051601  jz      loc_1400516C9
0x140051607  mov     qword ptr [rsp+1A8h+var_158], 1
0x140051610  lea     rax, [rsp+1A8h+var_158]
0x140051615  mov     [rsp+1A8h+var_98], rax
0x14005161d  mov     [rsp+1A8h+var_90], 8
0x140051629  mov     [rsp+1A8h+var_178], r13b
0x14005162e  lea     rax, [rsp+1A8h+var_178]
0x140051633  mov     [rsp+1A8h+var_88], rax
0x14005163b  mov     [rsp+1A8h+var_80], 1
0x140051647  test    r14, r14
0x14005164a  cmovnz  r8, r14
0x14005164e  mov     rdx, r8
0x140051651  lea     rcx, [rsp+1A8h+var_78]
0x140051659  call    _tlgCreate1Sz_wchar_t
0x14005165e  mov     [rsp+1A8h+var_174], esi
0x140051662  lea     rax, [rsp+1A8h+var_174]
0x140051667  mov     [rsp+1A8h+var_68], rax
0x14005166f  mov     [rsp+1A8h+var_60], 4
0x14005167b  mov     qword ptr [rsp+1A8h+var_118], 1000000h
0x140051687  lea     rax, [rsp+1A8h+var_118]
0x14005168f  mov     [rsp+1A8h+var_58], rax
0x140051697  mov     [rsp+1A8h+var_50], 8
0x1400516a3  lea     rax, [rsp+1A8h+var_B8]
0x1400516ab  mov     [rsp+1A8h+var_188], rax
0x1400516b0  mov     r9d, 7
0x1400516b6  lea     rdx, byte_140010BE9
0x1400516bd  lea     rcx, dword_1400170F8
  ... truncated ...
```
