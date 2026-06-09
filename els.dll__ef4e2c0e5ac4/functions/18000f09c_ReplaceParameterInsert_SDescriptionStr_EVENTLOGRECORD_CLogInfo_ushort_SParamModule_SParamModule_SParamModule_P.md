# ReplaceParameterInsert(SDescriptionStr *,_EVENTLOGRECORD *,CLogInfo *,ushort *,SParamModule *,SParamModule *,SParamModule *,PSK *)

- ea: `0x18000f09c`
- end: `0x18000f4ae`
- name: `?ReplaceParameterInsert@@YAXPEAUSDescriptionStr@@PEAU_EVENTLOGRECORD@@PEAVCLogInfo@@PEAGPEAUSParamModule@@44PEAW4PSK@@@Z`
- size: `1042`
- prototype: `void __fastcall(unsigned __int16 **, struct _EVENTLOGRECORD *, struct CLogInfo *, unsigned __int16 *, struct SParamModule *, LPCVOID *, struct SParamModule *, enum PSK *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18000eb2c`

## callees

- `0x180004b7c`
- `0x18000c368`
- `0x18000e824`
- `0x18000e908`
- `0x18000f09c`
- `0x18000f564`
- `0x18001af3c`
- `0x1800210cc`
- `0x180022292`
- `0x1800222d0`

## import_xrefs

- `msvcrt!wcstoul` at `0x18000f122`
- `msvcrt!wcstoul` at `0x18000f122`
- `KERNEL32!LocalFree` at `0x18000f47a`
- `KERNEL32!LocalFree` at `0x18000f47a`
- `KERNEL32!FormatMessageW` at `0x18000f206`
- `KERNEL32!FormatMessageW` at `0x18000f2bc`
- `KERNEL32!FormatMessageW` at `0x18000f3d0`
- `KERNEL32!FormatMessageW` at `0x18000f441`
- `KERNEL32!FormatMessageW` at `0x18000f206`
- `KERNEL32!FormatMessageW` at `0x18000f2bc`
- `KERNEL32!FormatMessageW` at `0x18000f3d0`
- `KERNEL32!FormatMessageW` at `0x18000f441`

## string_xrefs

- `0x18000f3dd`: `kernel32.dll`

## pseudocode

```c
void __fastcall ReplaceParameterInsert(
        unsigned __int16 **a1,
        struct _EVENTLOGRECORD *a2,
        struct CLogInfo *a3,
        unsigned __int16 *a4,
        struct SParamModule *a5,
        LPCVOID *a6,
        struct SParamModule *a7,
        enum PSK *a8)
{
  unsigned __int16 **v10; // r12
  unsigned __int16 *v11; // rcx
  DWORD v12; // eax
  wchar_t *v13; // r14
  wchar_t *v14; // rcx
  wchar_t *v15; // rax
  int v16; // ebx
  int v17; // eax
  CSafeReg *v18; // rdx
  DWORD v19; // r13d
  int v20; // eax
  CSafeReg *v21; // rcx
  CDllCache *v22; // rcx
  int v23; // eax
  struct CLogInfo *v24; // r15
  __int64 v25; // r14
  char *v26; // rdi
  __int64 v27; // rax
  __int64 v28; // rcx
  CDllCache *v29; // rcx
  LPWSTR lpBuffer; // [rsp+20h] [rbp-E0h]
  WCHAR Buffer[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD dwMessageId; // [rsp+48h] [rbp-B8h]
  wchar_t *EndPtr; // [rsp+50h] [rbp-B0h] BYREF
  enum PSK *v34; // [rsp+58h] [rbp-A8h]
  struct CLogInfo *v35; // [rsp+60h] [rbp-A0h]
  struct _EVENTLOGRECORD *v36; // [rsp+68h] [rbp-98h]
  unsigned __int16 **v37; // [rsp+70h] [rbp-90h]
  unsigned __int16 v38; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v39[526]; // [rsp+82h] [rbp-7Eh] BYREF
  unsigned __int16 v40; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v41[526]; // [rsp+292h] [rbp+192h] BYREF
  unsigned __int16 v42; // [rsp+4A0h] [rbp+3A0h] BYREF
  _BYTE v43[526]; // [rsp+4A2h] [rbp+3A2h] BYREF

  v37 = a1;
  v10 = a1 + 1;
  v34 = a8;
  v11 = a1[1];
  v36 = a2;
  v35 = a3;
  EndPtr = 0;
  v12 = wcstoul(v11 + 2, &EndPtr, 10);
  dwMessageId = v12;
  v13 = (wchar_t *)(((unsigned __int64)a3 + 32) & -(__int64)(*((_WORD *)a3 + 16) != 0));
  if ( (*((_BYTE *)a3 + 24) & 1) != 0 )
  {
    v14 = &g_wszAuxMessageSource;
    if ( !g_wszAuxMessageSource )
      v14 = (wchar_t *)(((unsigned __int64)a3 + 32) & -(__int64)(*((_WORD *)a3 + 16) != 0));
    v13 = v14;
  }
  if ( !v12 && (*v10)[2] != 48 )
  {
    v15 = *v10 + 1;
    goto LABEL_50;
  }
  *(_QWORD *)Buffer = 0;
  v42 = 0;
  memset_0(v43, 0, 0x208u);
  v16 = 2;
  if ( !v13 )
    goto LABEL_16;
  v17 = *(_DWORD *)a5;
  if ( !*(_DWORD *)a5 )
  {
    if ( !*a4 || (v18 = (CSafeReg *)*((_QWORD *)a5 + 1), !*(_QWORD *)v18) )
    {
      *(_DWORD *)a5 = 2;
      goto LABEL_16;
    }
    v17 = LoadRemoteParamModule(v13, v18, a4, &v42, (__int64)lpBuffer, (struct SParamModule *)((char *)a5 + 16));
    *(_DWORD *)a5 = v17;
  }
  if ( v17 == 1 )
  {
    v19 = dwMessageId;
    FormatMessageW(0xBFFu, *((LPCVOID *)a5 + 2), dwMessageId, 0, Buffer, 0x100u, 0);
    goto LABEL_17;
  }
LABEL_16:
  v19 = dwMessageId;
LABEL_17:
  v38 = 0;
  memset_0(v39, 0, 0x208u);
  if ( !*(_QWORD *)Buffer )
  {
    v20 = *(_DWORD *)a6;
    if ( *(_DWORD *)a6
      || ((v21 = (CSafeReg *)a6[1], !*(_QWORD *)v21)
       || CSafeReg::QueryPath(v21, L"ParameterMessageFile", &v38, 0x105u, 1) < 0
        ? (v20 = 2)
        : (v20 = (((int)CDllCache::Fetch(v22, &v38, (struct CSafeCacheHandle *)(a6 + 2)) >> 31) & 1) + 1),
          *(_DWORD *)a6 = v20,
          !*(_QWORD *)Buffer) )
    {
      if ( v20 == 1 )
        FormatMessageW(0xBFFu, a6[2], v19, 0, Buffer, 0x100u, 0);
    }
  }
  v40 = 0;
  memset_0(v41, 0, 0x208u);
  if ( *(_QWORD *)Buffer )
    goto LABEL_47;
  if ( *(_DWORD *)a7 )
  {
    v16 = *(_DWORD *)a7;
  }
  else
  {
    v23 = *(_DWORD *)v34;
    if ( !*(_DWORD *)v34 )
    {
      v24 = v35;
      v25 = *((_QWORD *)a7 + 1);
      v26 = (char *)v35 + 4784;
      if ( !*((_DWORD *)v35 + 1196) )
        CSources::_Init((struct CLogInfo *)((char *)v35 + 4784));
      v27 = *((_QWORD *)v26 + 6);
      if ( v27 )
        v28 = *(_QWORD *)(v27 + 24);
      else
        v28 = 0;
      v23 = OpenPrimarySourceKey(v28, &v36[1], (char *)v24 + 554, v25);
      *(_DWORD *)v34 = v23;
    }
    if ( v23 == 4 && CSafeReg::QueryPath(*((CSafeReg **)a7 + 1), L"ParameterMessageFile", &v40, 0x105u, 1) >= 0 )
      v16 = (((int)CDllCache::Fetch(v29, &v40, (struct SParamModule *)((char *)a7 + 16)) >> 31) & 1) + 1;
    *(_DWORD *)a7 = v16;
    if ( *(_QWORD *)Buffer )
      goto LABEL_47;
  }
  if ( v16 != 1 || (FormatMessageW(0xBFFu, *((LPCVOID *)a7 + 2), v19, 0, Buffer, 0x100u, 0), !*(_QWORD *)Buffer) )
  {
    if ( wcsistr(&v42, L"kernel32.dll") || wcsistr(&v38, L"kernel32.dll") || wcsistr(&v40, L"kernel32.dll") )
      FormatMessageW(0x13FFu, 0, v19, 0, Buffer, 0x100u, 0);
  }
LABEL_47:
  if ( *(_QWORD *)Buffer )
  {
    ReplaceSubStr(
      *(const unsigned __int16 **)Buffer,
      v37,
      v10,
      EndPtr,
      (unsigned int *)v37 + 4,
      (unsigned int *)v37 + 5);
    LocalFree(*(HLOCAL *)Buffer);
    return;
  }
  v15 = EndPtr;
LABEL_50:
  *v10 = v15;
}

```

## disassembly

```asm
0x18000f09c  push    rbp
0x18000f09e  push    rbx
0x18000f09f  push    rsi
0x18000f0a0  push    rdi
0x18000f0a1  push    r12
0x18000f0a3  push    r13
0x18000f0a5  push    r14
0x18000f0a7  push    r15
0x18000f0a9  lea     rbp, [rsp-5C8h]
0x18000f0b1  sub     rsp, 6C8h
0x18000f0b8  mov     rax, cs:__security_cookie
0x18000f0bf  xor     rax, rsp
0x18000f0c2  mov     [rbp+600h+var_50], rax
0x18000f0c9  mov     rsi, [rbp+600h+arg_30]
0x18000f0d0  mov     rax, rcx
0x18000f0d3  mov     r15, [rbp+600h+arg_28]
0x18000f0da  mov     rbx, r8
0x18000f0dd  mov     rdi, [rbp+600h+arg_20]
0x18000f0e4  mov     r8d, 0Ah; Radix
0x18000f0ea  mov     [rsp+700h+var_690], rcx
0x18000f0ef  mov     r13, r9
0x18000f0f2  mov     rcx, [rbp+600h+arg_38]
0x18000f0f9  lea     r12, [rax+8]
0x18000f0fd  mov     [rsp+700h+var_6A8], rcx
0x18000f102  mov     rcx, [r12]
0x18000f106  mov     [rsp+700h+var_698], rdx
0x18000f10b  add     rcx, 4; String
0x18000f10f  lea     rdx, [rsp+700h+EndPtr]; EndPtr
0x18000f114  mov     [rsp+700h+var_6A0], rbx
0x18000f119  mov     [rsp+700h+EndPtr], 0
0x18000f122  call    cs:__imp_wcstoul
0x18000f128  lea     rdx, [rbx+20h]
0x18000f12c  mov     [rsp+700h+dwMessageId], eax
0x18000f130  movzx   ecx, word ptr [rdx]
0x18000f133  neg     cx
0x18000f136  sbb     r14, r14
0x18000f139  and     r14, rdx
0x18000f13c  xor     edx, edx
0x18000f13e  test    byte ptr [rbx+18h], 1
0x18000f142  jz      short loc_18000F159
0x18000f144  cmp     cs:?g_wszAuxMessageSource@@3PAGA, dx; ushort near * g_wszAuxMessageSource
0x18000f14b  lea     rcx, ?g_wszAuxMessageSource@@3PAGA; ushort near * g_wszAuxMessageSource
0x18000f152  cmovz   rcx, r14
0x18000f156  mov     r14, rcx
0x18000f159  test    eax, eax
0x18000f15b  jnz     short loc_18000F175
0x18000f15d  mov     rax, [r12]
0x18000f161  mov     ecx, 30h ; '0'
0x18000f166  cmp     cx, [rax+4]
0x18000f16a  jz      short loc_18000F175
0x18000f16c  add     rax, 2
0x18000f170  jmp     loc_18000F487
0x18000f175  mov     qword ptr [rsp+700h+Buffer], rdx
0x18000f17a  lea     rcx, [rbp+600h+var_25E]; void *
0x18000f181  mov     [rbp+600h+var_260], dx
0x18000f188  mov     r8d, 208h; Size
0x18000f18e  xor     edx, edx; Val
0x18000f190  call    memset_0
0x18000f195  xor     ecx, ecx
0x18000f197  mov     ebx, 2
0x18000f19c  test    r14, r14
0x18000f19f  jz      short loc_18000F210
0x18000f1a1  mov     eax, [rdi]
0x18000f1a3  test    eax, eax
0x18000f1a5  jnz     short loc_18000F1D6
0x18000f1a7  cmp     [r13+0], cx
0x18000f1ac  jz      short loc_18000F20E
0x18000f1ae  mov     rdx, [rdi+8]
0x18000f1b2  cmp     [rdx], rcx
0x18000f1b5  jz      short loc_18000F20E
0x18000f1b7  lea     rax, [rdi+10h]
0x18000f1bb  mov     r8, r13
0x18000f1be  lea     r9, [rbp+600h+var_260]
0x18000f1c5  mov     qword ptr [rsp+700h+nSize], rax
0x18000f1ca  mov     rcx, r14
0x18000f1cd  call    ?LoadRemoteParamModule@@YA?AW4MODULE_LOAD_STATUS@@PEBGPEAVCSafeReg@@0PEAGKPEAVCSafeCacheHandle@@@Z; LoadRemoteParamModule(ushort const *,CSafeReg *,ushort const *,ushort *,ulong,CSafeCacheHandle *)
0x18000f1d2  mov     [rdi], eax
0x18000f1d4  xor     ecx, ecx
0x18000f1d6  cmp     eax, 1
0x18000f1d9  jnz     short loc_18000F210
0x18000f1db  mov     r13d, [rsp+700h+dwMessageId]
0x18000f1e0  lea     rax, [rsp+700h+Buffer]
0x18000f1e5  mov     rdx, [rdi+10h]; lpSource
0x18000f1e9  mov     r8d, r13d; dwMessageId
0x18000f1ec  mov     [rsp+700h+Arguments], rcx; Arguments
0x18000f1f1  xor     r9d, r9d; dwLanguageId
0x18000f1f4  mov     [rsp+700h+nSize], 100h; nSize
0x18000f1fc  mov     ecx, 0BFFh; dwFlags
0x18000f201  mov     [rsp+700h+lpBuffer], rax; lpBuffer
0x18000f206  call    cs:__imp_FormatMessageW
0x18000f20c  jmp     short loc_18000F215
0x18000f20e  mov     [rdi], ebx
0x18000f210  mov     r13d, [rsp+700h+dwMessageId]
0x18000f215  mov     r14d, 208h
0x18000f21b  lea     rcx, [rbp+600h+var_67E]; void *
0x18000f21f  xor     edi, edi
0x18000f221  mov     r8d, r14d; Size
0x18000f224  xor     edx, edx; Val
0x18000f226  mov     [rbp+600h+var_680], di
0x18000f22a  call    memset_0
0x18000f22f  cmp     qword ptr [rsp+700h+Buffer], rdi
0x18000f234  jnz     loc_18000F2C2
0x18000f23a  mov     eax, [r15]
0x18000f23d  test    eax, eax
0x18000f23f  jnz     short loc_18000F291
0x18000f241  mov     rcx, [r15+8]; this
0x18000f245  cmp     [rcx], rdi
0x18000f248  jz      short loc_18000F283
0x18000f24a  mov     r9d, 105h; unsigned int
0x18000f250  mov     dword ptr [rsp+700h+lpBuffer], 1; int
0x18000f258  lea     r8, [rbp+600h+var_680]; unsigned __int16 *
0x18000f25c  lea     rdx, aParametermessa; "ParameterMessageFile"
0x18000f263  call    ?QueryPath@CSafeReg@@QEAAJPEBGPEAGKH@Z; CSafeReg::QueryPath(ushort const *,ushort *,ulong,int)
0x18000f268  test    eax, eax
0x18000f26a  js      short loc_18000F283
0x18000f26c  lea     r8, [r15+10h]; struct CSafeCacheHandle *
0x18000f270  lea     rdx, [rbp+600h+var_680]; unsigned __int16 *
0x18000f274  call    ?Fetch@CDllCache@@QEAAJPEBGPEAVCSafeCacheHandle@@@Z; CDllCache::Fetch(ushort const *,CSafeCacheHandle *)
0x18000f279  sar     eax, 1Fh
0x18000f27c  and     eax, 1
0x18000f27f  inc     eax
0x18000f281  jmp     short loc_18000F285
0x18000f283  mov     eax, ebx
0x18000f285  mov     rcx, r15
0x18000f288  mov     [rcx], eax
0x18000f28a  cmp     qword ptr [rsp+700h+Buffer], rdi
0x18000f28f  jnz     short loc_18000F2C2
0x18000f291  cmp     eax, 1
0x18000f294  jnz     short loc_18000F2C2
0x18000f296  mov     rdx, [r15+10h]; lpSource
0x18000f29a  lea     rax, [rsp+700h+Buffer]
0x18000f29f  mov     [rsp+700h+Arguments], rdi; Arguments
0x18000f2a4  xor     r9d, r9d; dwLanguageId
0x18000f2a7  mov     [rsp+700h+nSize], 100h; nSize
0x18000f2af  mov     r8d, r13d; dwMessageId
0x18000f2b2  mov     ecx, 0BFFh; dwFlags
0x18000f2b7  mov     [rsp+700h+lpBuffer], rax; lpBuffer
0x18000f2bc  call    cs:__imp_FormatMessageW
0x18000f2c2  mov     r8, r14; Size
0x18000f2c5  mov     [rbp+600h+var_470], di
0x18000f2cc  xor     edx, edx; Val
0x18000f2ce  lea     rcx, [rbp+600h+var_46E]; void *
0x18000f2d5  call    memset_0
0x18000f2da  cmp     qword ptr [rsp+700h+Buffer], rdi
0x18000f2df  jnz     loc_18000F447
0x18000f2e5  cmp     [rsi], edi
0x18000f2e7  jnz     loc_18000F3A3
0x18000f2ed  mov     rax, [rsp+700h+var_6A8]
0x18000f2f2  mov     eax, [rax]
0x18000f2f4  test    eax, eax
0x18000f2f6  jnz     short loc_18000F349
0x18000f2f8  mov     r15, [rsp+700h+var_6A0]
0x18000f2fd  xor     edx, edx
0x18000f2ff  mov     r14, [rsi+8]
0x18000f303  lea     rdi, [r15+12B0h]
0x18000f30a  cmp     [rdi], edx
0x18000f30c  jnz     short loc_18000F316
0x18000f30e  mov     rcx, rdi; this
0x18000f311  call    ?_Init@CSources@@AEAAJXZ; CSources::_Init(void)
0x18000f316  mov     rax, [rdi+30h]
0x18000f31a  xor     edi, edi
0x18000f31c  test    rax, rax
0x18000f31f  jz      short loc_18000F327
0x18000f321  mov     rcx, [rax+18h]
0x18000f325  jmp     short loc_18000F32A
0x18000f327  mov     rcx, rdi
0x18000f32a  mov     rdx, [rsp+700h+var_698]
0x18000f32f  lea     r8, [r15+22Ah]
0x18000f336  add     rdx, 38h ; '8'
0x18000f33a  mov     r9, r14
0x18000f33d  call    ?OpenPrimarySourceKey@@YA?AW4PSK@@PEBG00PEAVCSafeReg@@@Z; OpenPrimarySourceKey(ushort const *,ushort const *,ushort const *,CSafeReg *)
0x18000f342  mov     rcx, [rsp+700h+var_6A8]
0x18000f347  mov     [rcx], eax
0x18000f349  cmp     eax, 4
0x18000f34c  jnz     short loc_18000F391
0x18000f34e  mov     rcx, [rsi+8]; this
0x18000f352  lea     r8, [rbp+600h+var_470]; unsigned __int16 *
0x18000f359  mov     r9d, 105h; unsigned int
0x18000f35f  mov     dword ptr [rsp+700h+lpBuffer], 1; int
0x18000f367  lea     rdx, aParametermessa; "ParameterMessageFile"
0x18000f36e  call    ?QueryPath@CSafeReg@@QEAAJPEBGPEAGKH@Z; CSafeReg::QueryPath(ushort const *,ushort *,ulong,int)
0x18000f373  test    eax, eax
0x18000f375  js      short loc_18000F391
0x18000f377  lea     r8, [rsi+10h]; struct CSafeCacheHandle *
0x18000f37b  lea     rdx, [rbp+600h+var_470]; unsigned __int16 *
0x18000f382  call    ?Fetch@CDllCache@@QEAAJPEBGPEAVCSafeCacheHandle@@@Z; CDllCache::Fetch(ushort const *,CSafeCacheHandle *)
0x18000f387  mov     ebx, eax
0x18000f389  sar     ebx, 1Fh
0x18000f38c  and     ebx, 1
0x18000f38f  inc     ebx
0x18000f391  mov     rax, rsi
0x18000f394  mov     [rax], ebx
0x18000f396  cmp     qword ptr [rsp+700h+Buffer], rdi
0x18000f39b  jnz     loc_18000F447
0x18000f3a1  jmp     short loc_18000F3A5
0x18000f3a3  mov     ebx, [rsi]
0x18000f3a5  cmp     ebx, 1
0x18000f3a8  jnz     short loc_18000F3DD
0x18000f3aa  mov     rdx, [rsi+10h]; lpSource
0x18000f3ae  lea     rax, [rsp+700h+Buffer]
0x18000f3b3  mov     [rsp+700h+Arguments], rdi; Arguments
0x18000f3b8  xor     r9d, r9d; dwLanguageId
0x18000f3bb  mov     [rsp+700h+nSize], 100h; nSize
0x18000f3c3  mov     r8d, r13d; dwMessageId
0x18000f3c6  mov     ecx, 0BFFh; dwFlags
0x18000f3cb  mov     [rsp+700h+lpBuffer], rax; lpBuffer
0x18000f3d0  call    cs:__imp_FormatMessageW
0x18000f3d6  cmp     qword ptr [rsp+700h+Buffer], rdi
0x18000f3db  jnz     short loc_18000F447
0x18000f3dd  lea     rbx, aKernel32Dll_0; "kernel32.dll"
0x18000f3e4  mov     rdx, rbx; unsigned __int16 *
0x18000f3e7  lea     rcx, [rbp+600h+var_260]; unsigned __int16 *
0x18000f3ee  call    ?wcsistr@@YAPEAGPEBG0@Z; wcsistr(ushort const *,ushort const *)
0x18000f3f3  test    rax, rax
0x18000f3f6  jnz     short loc_18000F41D
0x18000f3f8  mov     rdx, rbx; unsigned __int16 *
0x18000f3fb  lea     rcx, [rbp+600h+var_680]; unsigned __int16 *
0x18000f3ff  call    ?wcsistr@@YAPEAGPEBG0@Z; wcsistr(ushort const *,ushort const *)
0x18000f404  test    rax, rax
0x18000f407  jnz     short loc_18000F41D
0x18000f409  mov     rdx, rbx; unsigned __int16 *
0x18000f40c  lea     rcx, [rbp+600h+var_470]; unsigned __int16 *
0x18000f413  call    ?wcsistr@@YAPEAGPEBG0@Z; wcsistr(ushort const *,ushort const *)
0x18000f418  test    rax, rax
0x18000f41b  jz      short loc_18000F447
0x18000f41d  mov     [rsp+700h+Arguments], rdi; Arguments
0x18000f422  lea     rax, [rsp+700h+Buffer]
0x18000f427  mov     [rsp+700h+nSize], 100h; nSize
0x18000f42f  xor     r9d, r9d; dwLanguageId
0x18000f432  mov     r8d, r13d; dwMessageId
0x18000f435  mov     [rsp+700h+lpBuffer], rax; lpBuffer
0x18000f43a  xor     edx, edx; lpSource
0x18000f43c  mov     ecx, 13FFh; dwFlags
0x18000f441  call    cs:__imp_FormatMessageW
0x18000f447  mov     rcx, qword ptr [rsp+700h+Buffer]; unsigned __int16 *
0x18000f44c  test    rcx, rcx
0x18000f44f  jz      short loc_18000F482
0x18000f451  mov     rdx, [rsp+700h+var_690]; unsigned __int16 **
0x18000f456  mov     r8, r12; unsigned __int16 **
0x18000f459  lea     r9, [rdx+10h]
0x18000f45d  lea     rax, [rdx+14h]
0x18000f461  mov     qword ptr [rsp+700h+nSize], rax; unsigned int *
0x18000f466  mov     [rsp+700h+lpBuffer], r9; unsigned int *
0x18000f46b  mov     r9, [rsp+700h+EndPtr]; unsigned __int16 *
0x18000f470  call    ?ReplaceSubStr@@YAJPEBGPEAPEAG10PEAK2@Z; ReplaceSubStr(ushort const *,ushort * *,ushort * *,ushort const *,ulong *,ulong *)
0x18000f475  mov     rcx, qword ptr [rsp+700h+Buffer]; hMem
0x18000f47a  call    cs:__imp_LocalFree
0x18000f480  jmp     short loc_18000F48B
0x18000f482  mov     rax, [rsp+700h+EndPtr]
0x18000f487  mov     [r12], rax
0x18000f48b  mov     rcx, [rbp+600h+var_50]
0x18000f492  xor     rcx, rsp; StackCookie
0x18000f495  call    __security_check_cookie
0x18000f49a  add     rsp, 6C8h
0x18000f4a1  pop     r15
0x18000f4a3  pop     r14
0x18000f4a5  pop     r13
0x18000f4a7  pop     r12
0x18000f4a9  pop     rdi
0x18000f4aa  pop     rsi
0x18000f4ab  pop     rbx
0x18000f4ac  pop     rbp
0x18000f4ad  retn
```
