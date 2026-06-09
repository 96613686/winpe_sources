# DRMCreateEnablingBitsEncryptor

- ea: `0x18004df00`
- end: `0x18004e0ee`
- name: `DRMCreateEnablingBitsEncryptor`
- size: `494`
- prototype: `HRESULT __stdcall(DRMHANDLE hBoundLicense, PWSTR wszRight, DRMHANDLE hAuxLib, PWSTR wszAuxPlug, DRMHANDLE *phEncryptor)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x180059cec`

## callees

- `0x180001244`
- `0x180001284`
- `0x180004654`
- `0x1800046c8`
- `0x180015438`
- `0x18001f3ac`
- `0x18001fe60`
- `0x18004df00`
- `0x18005f010`

## string_xrefs

- `0x18004df1b`: `[msdrm]:+DRMCreateEnablingBitsEncryptor\n`
- `0x18004e0ad`: `[msdrm]:-DRMCreateEnablingBitsEncryptor HR=0x%x\n`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
HRESULT __stdcall DRMCreateEnablingBitsEncryptor(
        DRMHANDLE hBoundLicense,
        PWSTR wszRight,
        DRMHANDLE hAuxLib,
        PWSTR wszAuxPlug,
        DRMHANDLE *phEncryptor)
{
  CHandlesTable *v7; // rcx
  HRESULT SPHandle; // ebx
  __int64 v9; // rdx
  PWSTR v10; // rax
  unsigned __int64 v11; // rcx
  signed __int64 v12; // rbx
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rax
  CHandlesTable *v15; // rcx
  HRESULT result; // eax
  unsigned int v17; // [rsp+20h] [rbp-78h] BYREF
  unsigned int v18; // [rsp+24h] [rbp-74h] BYREF
  unsigned int v19; // [rsp+28h] [rbp-70h] BYREF
  __int64 v20; // [rsp+30h] [rbp-68h]
  void *Block[2]; // [rsp+38h] [rbp-60h] BYREF
  __int128 v22; // [rsp+48h] [rbp-50h]
  __int128 v23; // [rsp+58h] [rbp-40h]

  v20 = -2;
  _RTLTRACE("[msdrm]:+DRMCreateEnablingBitsEncryptor\n", wszRight, hAuxLib, wszAuxPlug);
  v18 = 0;
  v17 = 0;
  v19 = 0;
  *(_OWORD *)Block = 0;
  v22 = 0;
  v23 = 0;
  if ( !phEncryptor )
  {
    SPHandle = -2147024809;
    goto LABEL_21;
  }
  if ( !wszRight )
    goto LABEL_15;
  v9 = 0x7FFFFFFF;
  v10 = wszRight;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v9;
  }
  while ( v9 );
  SPHandle = v9 == 0 ? 0x80070057 : 0;
  v11 = (0x7FFFFFFF - v9) & -(__int64)(v9 != 0);
  if ( v9 )
  {
    v12 = v11 + 1;
    if ( v11 + 1 < v11 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v11);
    v13 = HIDWORD(v12);
    if ( v12 < 0 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v13);
    v14 = 2LL * (unsigned int)v12;
    v7 = (CHandlesTable *)(v13 << 33);
    if ( (unsigned __int64)v7 + v14 < v14 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v7);
    if ( !(CHandlesTable *)((char *)v7 + v14) )
      goto LABEL_15;
    Block[1] = operator new(saturated_mul(v12, 2u));
    if ( !Block[1] )
    {
      SPHandle = -2147024882;
      goto LABEL_19;
    }
    SPHandle = StringCchCopyW((unsigned __int16 *)Block[1], v12, wszRight);
    if ( SPHandle >= 0 )
    {
LABEL_15:
      SPHandle = CHandlesTable::GetSPHandle(v7, hBoundLicense, &v18);
      if ( SPHandle >= 0 )
      {
        SPHandle = g_pfnSPCreateEncryptor(v18, (struct _SPAPIGRANT *)Block, &v17);
        if ( SPHandle >= 0 )
        {
          SPHandle = CHandlesTable::CreateHandle(v15, &v19, v17);
          if ( SPHandle >= 0 )
          {
            *phEncryptor = v19;
            goto LABEL_21;
          }
        }
      }
    }
  }
LABEL_19:
  if ( v17 )
    ((void (*)(void))g_pfnSPCloseHandle)();
LABEL_21:
  operator delete(Block[1]);
  Block[1] = 0;
  _RTLTRACE("[msdrm]:-DRMCreateEnablingBitsEncryptor HR=0x%x\n", SPHandle);
  result = -2147024774;
  if ( SPHandle != -2147024774 )
  {
    result = -2147168468;
    if ( SPHandle != -1073426388 )
      return SPHandle;
  }
  return result;
}

```

## disassembly

```asm
0x18004df00  push    rbx
0x18004df02  push    rsi
0x18004df03  push    rdi
0x18004df04  push    r14
0x18004df06  push    r15
0x18004df08  sub     rsp, 70h
0x18004df0c  mov     [rsp+98h+var_68], 0FFFFFFFFFFFFFFFEh
0x18004df15  mov     rsi, rdx
0x18004df18  mov     r15d, ecx
0x18004df1b  lea     rcx, aMsdrmDrmcreate_13; "[msdrm]:+DRMCreateEnablingBitsEncryptor"...
0x18004df22  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18004df27  xor     edi, edi
0x18004df29  mov     [rsp+98h+var_74], edi
0x18004df2d  mov     [rsp+98h+var_78], edi
0x18004df31  mov     [rsp+98h+var_70], edi
0x18004df35  xorps   xmm0, xmm0
0x18004df38  movups  xmmword ptr [rsp+98h+Block], xmm0
0x18004df3d  movups  [rsp+98h+var_50], xmm0
0x18004df42  movups  [rsp+98h+var_40], xmm0
0x18004df47  mov     r14, [rsp+98h+phEncryptor]
0x18004df4f  test    r14, r14
0x18004df52  jnz     short loc_18004DF5E
0x18004df54  mov     ebx, 80070057h
0x18004df59  jmp     loc_18004E09C
0x18004df5e  test    rsi, rsi
0x18004df61  jz      loc_18004E02E
0x18004df67  mov     r8d, 7FFFFFFFh
0x18004df6d  mov     edx, r8d
0x18004df70  mov     rax, rsi
0x18004df73  cmp     [rax], di
0x18004df76  jz      short loc_18004DF82
0x18004df78  add     rax, 2
0x18004df7c  sub     rdx, 1
0x18004df80  jnz     short loc_18004DF73
0x18004df82  mov     rax, rdx
0x18004df85  neg     rax
0x18004df88  sbb     ecx, ecx
0x18004df8a  not     ecx
0x18004df8c  mov     ebx, 80070057h
0x18004df91  and     ebx, ecx
0x18004df93  mov     rax, rdx
0x18004df96  sub     r8, rdx
0x18004df99  neg     rax
0x18004df9c  sbb     rcx, rcx
0x18004df9f  and     rcx, r8
0x18004dfa2  test    rdx, rdx
0x18004dfa5  jnz     short loc_18004DFAC
0x18004dfa7  jmp     loc_18004E088
0x18004dfac  lea     rbx, [rcx+1]
0x18004dfb0  cmp     rbx, rcx
0x18004dfb3  jb      loc_18004E0DC
0x18004dfb9  mov     rcx, rbx
0x18004dfbc  shr     rcx, 20h
0x18004dfc0  mov     rax, rcx
0x18004dfc3  shr     rax, 1Fh
0x18004dfc7  test    eax, eax
0x18004dfc9  jnz     loc_18004E0E2
0x18004dfcf  mov     eax, ebx
0x18004dfd1  add     rax, rax
0x18004dfd4  shl     rcx, 21h
0x18004dfd8  lea     rdx, [rcx+rax]
0x18004dfdc  cmp     rdx, rax
0x18004dfdf  jb      loc_18004E0E7
0x18004dfe5  test    rdx, rdx
0x18004dfe8  jz      short loc_18004E02E
0x18004dfea  mov     eax, 2
0x18004dfef  mul     rbx
0x18004dff2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004dff9  cmovb   rax, rcx
0x18004dffd  mov     rcx, rax; Size
0x18004e000  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004e005  mov     [rsp+98h+Block+8], rax
0x18004e00a  test    rax, rax
0x18004e00d  jnz     short loc_18004E016
0x18004e00f  mov     ebx, 8007000Eh
0x18004e014  jmp     short loc_18004E088
0x18004e016  mov     r8, rsi; unsigned __int16 *
0x18004e019  mov     rdx, rbx; unsigned __int64
0x18004e01c  mov     rcx, [rsp+98h+Block+8]; unsigned __int16 *
0x18004e021  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004e026  mov     ebx, eax
0x18004e028  test    eax, eax
0x18004e02a  jns     short loc_18004E02E
0x18004e02c  jmp     short loc_18004E088
0x18004e02e  lea     r8, [rsp+98h+var_74]; unsigned int *
0x18004e033  mov     edx, r15d; unsigned int
0x18004e036  call    ?GetSPHandle@CHandlesTable@@QEAAJKPEAK@Z; CHandlesTable::GetSPHandle(ulong,ulong *)
0x18004e03b  mov     ebx, eax
0x18004e03d  test    eax, eax
0x18004e03f  js      short loc_18004E088
0x18004e041  lea     r8, [rsp+98h+var_78]
0x18004e046  lea     rdx, [rsp+98h+Block]
0x18004e04b  mov     ecx, [rsp+98h+var_74]
0x18004e04f  mov     rax, cs:?g_pfnSPCreateEncryptor@@3P6AJKPEAU_SPAPIGRANT@@PEAK@ZEA; long (*g_pfnSPCreateEncryptor)(ulong,_SPAPIGRANT *,ulong *)
0x18004e056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e05b  mov     ebx, eax
0x18004e05d  test    eax, eax
0x18004e05f  js      short loc_18004E088
0x18004e061  mov     r8d, [rsp+98h+var_78]; unsigned int
0x18004e066  lea     rdx, [rsp+98h+var_70]; unsigned int *
0x18004e06b  call    ?CreateHandle@CHandlesTable@@QEAAJPEAKK@Z; CHandlesTable::CreateHandle(ulong *,ulong)
0x18004e070  mov     ebx, eax
0x18004e072  test    eax, eax
0x18004e074  js      short loc_18004E088
0x18004e076  mov     eax, [rsp+98h+var_70]
0x18004e07a  mov     [r14], eax
0x18004e07d  jmp     short loc_18004E09C
0x18004e07f  xor     edi, edi
0x18004e081  mov     ebx, dword ptr [rsp+98h+phEncryptor]
0x18004e088  mov     ecx, [rsp+98h+var_78]
0x18004e08c  test    ecx, ecx
0x18004e08e  jz      short loc_18004E09C
0x18004e090  mov     rax, cs:?g_pfnSPCloseHandle@@3P6AJK@ZEA; long (*g_pfnSPCloseHandle)(ulong)
0x18004e097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e09c  mov     rcx, [rsp+98h+Block+8]; Block
0x18004e0a1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004e0a6  mov     [rsp+98h+Block+8], rdi
0x18004e0ab  mov     edx, ebx
0x18004e0ad  lea     rcx, aMsdrmDrmcreate_12; "[msdrm]:-DRMCreateEnablingBitsEncryptor"...
0x18004e0b4  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18004e0b9  mov     eax, 8007007Ah
0x18004e0be  cmp     ebx, eax
0x18004e0c0  jz      short loc_18004E0D0
0x18004e0c2  mov     eax, 8004CF2Ch
0x18004e0c7  cmp     ebx, 0C004D02Ch
0x18004e0cd  cmovnz  eax, ebx
0x18004e0d0  add     rsp, 70h
0x18004e0d4  pop     r15
0x18004e0d6  pop     r14
0x18004e0d8  pop     rdi
0x18004e0d9  pop     rsi
0x18004e0da  pop     rbx
0x18004e0db  retn
0x18004e0dc  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18004e0e2  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18004e0e7  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
```
