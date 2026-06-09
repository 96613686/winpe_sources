# VidMmRotateLegacyAllocation(VIDMM_GLOBAL *,VIDMM_PHYSICAL_ALLOC *,_MM_ROTATE_DIRECTION,long (*)(_MDL *,_MDL *,void *),VIDMM_ROTATE_COPY_CONTEXT *,VIDMM_ROTATE_FLAGS)

- ea: `0x14011f5a8`
- end: `0x14011f82a`
- name: `?VidMmRotateLegacyAllocation@@YAJPEAVVIDMM_GLOBAL@@PEAUVIDMM_PHYSICAL_ALLOC@@W4_MM_ROTATE_DIRECTION@@P6AJPEAU_MDL@@3PEAX@ZPEAUVIDMM_ROTATE_COPY_CONTEXT@@TVIDMM_ROTATE_FLAGS@@@Z`
- size: `642`
- prototype: ``
- caller_count: `8`
- callee_count: `6`
- tags: ``

## callers

- `0x140094660`
- `0x14009fbf4`
- `0x1400a4f78`
- `0x1400c9ddc`
- `0x1400ceb3c`
- `0x1400cfd94`
- `0x140116dc0`
- `0x140121ec4`

## callees

- `0x1400045ec`
- `0x140058760`
- `0x1400bd6ac`
- `0x1400f9ab8`
- `0x14011cd1c`
- `0x14011f5a8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14011f79e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011f7e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011f809`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011f79e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011f7e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011f809`
- `watchdog!WdLogSingleEntry5` at `0x14011f777`
- `watchdog!WdLogSingleEntry5` at `0x14011f777`
- `watchdog!WdLogSingleEntry1` at `0x14011f66b`
- `watchdog!WdLogSingleEntry1` at `0x14011f66b`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x14011f752`
- `dxgkrnl!g_IsInternalRelease` at `0x14011f745`

## string_xrefs

- `0x14011f67c`: `Failed to create rotate MDL for physical allocation 0x%.16x`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 __fastcall VidMmRotateLegacyAllocation(__int64 a1, _QWORD *a2, unsigned int a3, __int64 a4, __int64 a5, int a6)
{
  __int64 v6; // rsi
  __int64 v8; // r12
  unsigned __int64 v11; // r8
  unsigned __int64 *v12; // r14
  const struct VIDMM_CPU_HOST_APERTURE_RANGE *v13; // rdx
  PMDL v14; // rax
  const struct _MDL *v15; // rdx
  bool v16; // zf
  SIZE_T v17; // rcx
  PMDL v18; // rbp
  int v19; // ecx
  int v20; // r8d
  int v21; // r14d
  __int64 v23; // [rsp+C8h] [rbp+20h]

  v23 = a4;
  v6 = a2[17];
  v8 = *a2;
  if ( !v6 )
    v6 = a2[15];
  if ( a3 > 1 )
  {
    v18 = (PMDL)a2[19];
    v12 = a2 + 2;
  }
  else
  {
    v11 = *(_QWORD *)((char *)a2 + (-(__int64)(a2[13] != 0) & 0xFFFFFFFFFFFFFFE0uLL) + 144);
    v12 = a2 + 2;
    v13 = (const struct VIDMM_CPU_HOST_APERTURE_RANGE *)a2[20];
    if ( v13 )
    {
      v14 = VIDMM_CPU_HOST_APERTURE::BuildMdlFromRange(*(VIDMM_CPU_HOST_APERTURE **)(v6 + 512), v13, v11, *v12, 0);
    }
    else
    {
      v15 = *(const struct _MDL **)(v6 + 32);
      v16 = (*(_DWORD *)(*(_QWORD *)(a1 + 24) + 444LL) & 8) == 0;
      v17 = *v12;
      if ( v16 )
        v14 = VidMmiBuildMdlForContiguousMmIo(v17, (union _LARGE_INTEGER)((char *)v15 + v11));
      else
        v14 = VidMmiBuildMdlFromMdl(v17, v15, v11 >> 12);
    }
    a4 = v23;
    v18 = v14;
  }
  if ( !v18 )
  {
    WdLogSingleEntry1(1, a2);
    WdLogGlobalForLineNumber = 7034;
    DxgkLogInternalTriageEvent(
      v19,
      0x40000,
      v20,
      (unsigned int)L"Failed to create rotate MDL for physical allocation 0x%.16x",
      (__int64)a2,
      0,
      0,
      0);
    v21 = -1073741801;
    goto LABEL_29;
  }
  if ( a5 && (*(_DWORD *)(a1 + 3144) & 0x1000) != 0 )
    *(_DWORD *)(a5 + 40) = 2;
  v21 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, PMDL, _QWORD, unsigned __int64, __int64, __int64, int))(**(_QWORD **)(v8 + 232) + 48LL))(
          *(_QWORD *)(v8 + 232),
          a1,
          *(_QWORD *)(v8 + 240),
          a3,
          v18,
          0,
          *v12,
          a4,
          a5,
          a6);
  if ( a3 - 2 > 1 )
  {
    if ( v21 >= 0 )
    {
      a2[19] = v18;
      _InterlockedIncrement((volatile signed __int32 *)(v6 + 520));
      return (unsigned int)v21;
    }
    if ( (a6 & 2) != 0 )
    {
      _InterlockedDecrement((volatile signed __int32 *)(v6 + 520));
      ExFreePoolWithTag(v18, 0);
      a2[19] = 0;
    }
    goto LABEL_29;
  }
  if ( (int)(v21 + 0x80000000) >= 0 && v21 != -1073741558 && g_IsInternalRelease )
  {
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 9);
    WdLogGlobalForLineNumber = 222;
  }
  if ( (a6 & 2) == 0 )
  {
    _InterlockedDecrement((volatile signed __int32 *)(v6 + 520));
    ExFreePoolWithTag(v18, 0);
    a2[19] = 0;
  }
  if ( v21 < 0 )
  {
LABEL_29:
    if ( a3 <= 1 && v18 )
      ExFreePoolWithTag(v18, 0);
  }
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x14011f5a8  mov     [rsp+arg_18], r9
0x14011f5ad  push    rbx
0x14011f5ae  push    rbp
0x14011f5af  push    rsi
0x14011f5b0  push    rdi
0x14011f5b1  push    r12
0x14011f5b3  push    r13
0x14011f5b5  push    r14
0x14011f5b7  push    r15
0x14011f5b9  sub     rsp, 68h
0x14011f5bd  mov     rsi, [rdx+88h]
0x14011f5c4  mov     r13d, r8d
0x14011f5c7  mov     r12, [rdx]
0x14011f5ca  mov     rdi, rdx
0x14011f5cd  mov     r15, rcx
0x14011f5d0  test    rsi, rsi
0x14011f5d3  jnz     short loc_14011F5D9
0x14011f5d5  mov     rsi, [rdx+78h]
0x14011f5d9  mov     rax, [rdx+68h]
0x14011f5dd  neg     rax
0x14011f5e0  sbb     rcx, rcx
0x14011f5e3  and     rcx, 0FFFFFFFFFFFFFFE0h
0x14011f5e7  cmp     r13d, 1
0x14011f5eb  ja      short loc_14011F655
0x14011f5ed  mov     r8, [rcx+rdx+90h]; unsigned __int64
0x14011f5f5  lea     r14, [rdi+10h]
0x14011f5f9  mov     rdx, [rdx+0A0h]; struct VIDMM_CPU_HOST_APERTURE_RANGE *
0x14011f600  test    rdx, rdx
0x14011f603  jz      short loc_14011F61F
0x14011f605  mov     r9, [r14]; unsigned __int64
0x14011f608  mov     rcx, [rsi+200h]; this
0x14011f60f  mov     [rsp+0A8h+var_88], 0; PIRP
0x14011f618  call    ?BuildMdlFromRange@VIDMM_CPU_HOST_APERTURE@@QEBAPEAU_MDL@@PEBUVIDMM_CPU_HOST_APERTURE_RANGE@@_K1PEAU2@@Z; VIDMM_CPU_HOST_APERTURE::BuildMdlFromRange(VIDMM_CPU_HOST_APERTURE_RANGE const *,unsigned __int64,unsigned __int64,_MDL *)
0x14011f61d  jmp     short loc_14011F648
0x14011f61f  mov     rax, [r15+18h]
0x14011f623  mov     rdx, [rsi+20h]; struct _MDL *
0x14011f627  mov     ecx, [rax+1BCh]
0x14011f62d  test    cl, 8
0x14011f630  mov     rcx, [r14]; Length
0x14011f633  jz      short loc_14011F640
0x14011f635  shr     r8, 0Ch; unsigned __int64
0x14011f639  call    ?VidMmiBuildMdlFromMdl@@YAPEAU_MDL@@_KPEBU1@0@Z; VidMmiBuildMdlFromMdl(unsigned __int64,_MDL const *,unsigned __int64)
0x14011f63e  jmp     short loc_14011F648
0x14011f640  add     rdx, r8; union _LARGE_INTEGER
0x14011f643  call    ?VidMmiBuildMdlForContiguousMmIo@@YAPEAU_MDL@@_KT_LARGE_INTEGER@@@Z; VidMmiBuildMdlForContiguousMmIo(unsigned __int64,_LARGE_INTEGER)
0x14011f648  mov     r9, [rsp+0A8h+arg_18]
0x14011f650  mov     rbp, rax
0x14011f653  jmp     short loc_14011F660
0x14011f655  mov     rbp, [rdx+98h]
0x14011f65c  lea     r14, [rdx+10h]
0x14011f660  test    rbp, rbp
0x14011f663  jnz     short loc_14011F6B1
0x14011f665  mov     rdx, rdi
0x14011f668  lea     ecx, [rbp+1]
0x14011f66b  call    cs:__imp_WdLogSingleEntry1
0x14011f672  nop     dword ptr [rax+rax+00h]
0x14011f677  mov     [rsp+0A8h+var_70], rbp
0x14011f67c  lea     r9, aFailedToCreate_8; "Failed to create rotate MDL for physica"...
0x14011f683  mov     [rsp+0A8h+var_78], rbp
0x14011f688  mov     edx, 40000h
0x14011f68d  mov     [rsp+0A8h+var_80], rbp
0x14011f692  mov     [rsp+0A8h+var_88], rdi
0x14011f697  mov     cs:WdLogGlobalForLineNumber, 1B7Ah
0x14011f6a1  call    DxgkLogInternalTriageEvent
0x14011f6a6  mov     r14d, 0C0000017h
0x14011f6ac  jmp     loc_14011F7F9
0x14011f6b1  mov     rdx, [rsp+0A8h+arg_20]
0x14011f6b9  test    rdx, rdx
0x14011f6bc  jz      short loc_14011F6D2
0x14011f6be  test    dword ptr [r15+0C48h], 1000h
0x14011f6c9  jz      short loc_14011F6D2
0x14011f6cb  mov     dword ptr [rdx+28h], 2
0x14011f6d2  mov     rcx, [r12+0E8h]
0x14011f6da  mov     ebx, [rsp+0A8h+arg_28]
0x14011f6e1  mov     r8, [r12+0F0h]
0x14011f6e9  mov     [rsp+0A8h+var_60], ebx
0x14011f6ed  mov     rax, [rcx]
0x14011f6f0  mov     [rsp+0A8h+var_68], rdx
0x14011f6f5  mov     rdx, [r14]
0x14011f6f8  mov     [rsp+0A8h+var_70], r9
0x14011f6fd  mov     r9d, r13d
0x14011f700  mov     rax, [rax+30h]
0x14011f704  mov     [rsp+0A8h+var_78], rdx
0x14011f709  mov     rdx, r15
0x14011f70c  mov     [rsp+0A8h+var_80], 0
0x14011f715  mov     [rsp+0A8h+var_88], rbp
0x14011f71a  call    _guard_dispatch_icall
0x14011f71f  lea     ecx, [r13-2]
0x14011f723  mov     r14d, eax
0x14011f726  cmp     ecx, 1
0x14011f729  ja      loc_14011F7BC
0x14011f72f  mov     eax, 80000000h
0x14011f734  lea     ecx, [r14+rax]
0x14011f738  test    eax, ecx
0x14011f73a  jnz     short loc_14011F78D
0x14011f73c  cmp     r14d, 0C000010Ah
0x14011f743  jz      short loc_14011F78D
0x14011f745  mov     rcx, cs:__imp_?g_IsInternalRelease@@3EA; uchar g_IsInternalRelease
0x14011f74c  xor     edx, edx
0x14011f74e  cmp     [rcx], dl
0x14011f750  jz      short loc_14011F78D
0x14011f752  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x14011f759  mov     dword ptr [rax], 1
0x14011f75f  mov     [rsp+0A8h+var_80], rdx
0x14011f764  xor     r9d, r9d
0x14011f767  mov     [rsp+0A8h+var_88], rdx
0x14011f76c  xor     ecx, ecx
0x14011f76e  mov     edx, 10Eh
0x14011f773  lea     r8d, [r9+9]
0x14011f777  call    cs:__imp_WdLogSingleEntry5
0x14011f77e  nop     dword ptr [rax+rax+00h]
0x14011f783  mov     cs:WdLogGlobalForLineNumber, 0DEh
0x14011f78d  test    bl, 2
0x14011f790  jnz     short loc_14011F7B5
0x14011f792  lock dec dword ptr [rsi+208h]
0x14011f799  xor     edx, edx; Tag
0x14011f79b  mov     rcx, rbp; P
0x14011f79e  call    cs:__imp_ExFreePoolWithTag
0x14011f7a5  nop     dword ptr [rax+rax+00h]
0x14011f7aa  mov     qword ptr [rdi+98h], 0
0x14011f7b5  test    r14d, r14d
0x14011f7b8  js      short loc_14011F7F9
0x14011f7ba  jmp     short loc_14011F815
0x14011f7bc  test    r14d, r14d
0x14011f7bf  js      short loc_14011F7D1
0x14011f7c1  mov     [rdi+98h], rbp
0x14011f7c8  lock inc dword ptr [rsi+208h]
0x14011f7cf  jmp     short loc_14011F815
0x14011f7d1  test    bl, 2
0x14011f7d4  jz      short loc_14011F7F9
0x14011f7d6  lock dec dword ptr [rsi+208h]
0x14011f7dd  xor     edx, edx; Tag
0x14011f7df  mov     rcx, rbp; P
0x14011f7e2  call    cs:__imp_ExFreePoolWithTag
0x14011f7e9  nop     dword ptr [rax+rax+00h]
0x14011f7ee  mov     qword ptr [rdi+98h], 0
0x14011f7f9  cmp     r13d, 1
0x14011f7fd  ja      short loc_14011F815
0x14011f7ff  test    rbp, rbp
0x14011f802  jz      short loc_14011F815
0x14011f804  xor     edx, edx; Tag
0x14011f806  mov     rcx, rbp; P
0x14011f809  call    cs:__imp_ExFreePoolWithTag
0x14011f810  nop     dword ptr [rax+rax+00h]
0x14011f815  mov     eax, r14d
0x14011f818  add     rsp, 68h
0x14011f81c  pop     r15
0x14011f81e  pop     r14
0x14011f820  pop     r13
0x14011f822  pop     r12
0x14011f824  pop     rdi
0x14011f825  pop     rsi
0x14011f826  pop     rbp
0x14011f827  pop     rbx
0x14011f828  retn
```
