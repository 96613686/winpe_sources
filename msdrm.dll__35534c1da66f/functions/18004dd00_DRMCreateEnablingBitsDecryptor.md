# DRMCreateEnablingBitsDecryptor

- ea: `0x18004dd00`
- end: `0x18004deee`
- name: `DRMCreateEnablingBitsDecryptor`
- size: `494`
- prototype: `HRESULT __stdcall(DRMHANDLE hBoundLicense, PWSTR wszRight, DRMHANDLE hAuxLib, PWSTR wszAuxPlug, DRMHANDLE *phDecryptor)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x180004970`
- `0x180059cec`

## callees

- `0x180001244`
- `0x180001284`
- `0x180004654`
- `0x1800046c8`
- `0x180015438`
- `0x18001f3ac`
- `0x18001fe60`
- `0x18004dd00`
- `0x18005f010`

## string_xrefs

- `0x18004dd1b`: `[msdrm]:+DRMCreateEnablingBitsDecryptor\n`
- `0x18004dead`: `[msdrm]:-DRMCreateEnablingBitsDecryptor HR=0x%x\n`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
HRESULT __stdcall DRMCreateEnablingBitsDecryptor(
        DRMHANDLE hBoundLicense,
        PWSTR wszRight,
        DRMHANDLE hAuxLib,
        PWSTR wszAuxPlug,
        DRMHANDLE *phDecryptor)
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
  _RTLTRACE("[msdrm]:+DRMCreateEnablingBitsDecryptor\n", wszRight, hAuxLib, wszAuxPlug);
  v18 = 0;
  v17 = 0;
  v19 = 0;
  *(_OWORD *)Block = 0;
  v22 = 0;
  v23 = 0;
  if ( !phDecryptor )
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
        SPHandle = g_pfnSPCreateDecryptor(v18, (struct _SPAPIGRANT *)Block, &v17);
        if ( SPHandle >= 0 )
        {
          SPHandle = CHandlesTable::CreateHandle(v15, &v19, v17);
          if ( SPHandle >= 0 )
          {
            *phDecryptor = v19;
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
  _RTLTRACE("[msdrm]:-DRMCreateEnablingBitsDecryptor HR=0x%x\n", SPHandle);
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
0x18004dd00  push    rbx
0x18004dd02  push    rsi
0x18004dd03  push    rdi
0x18004dd04  push    r14
0x18004dd06  push    r15
0x18004dd08  sub     rsp, 70h
0x18004dd0c  mov     [rsp+98h+var_68], 0FFFFFFFFFFFFFFFEh
0x18004dd15  mov     rsi, rdx
0x18004dd18  mov     r15d, ecx
0x18004dd1b  lea     rcx, aMsdrmDrmcreate_6; "[msdrm]:+DRMCreateEnablingBitsDecryptor"...
0x18004dd22  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18004dd27  xor     edi, edi
0x18004dd29  mov     [rsp+98h+var_74], edi
0x18004dd2d  mov     [rsp+98h+var_78], edi
0x18004dd31  mov     [rsp+98h+var_70], edi
0x18004dd35  xorps   xmm0, xmm0
0x18004dd38  movups  xmmword ptr [rsp+98h+Block], xmm0
0x18004dd3d  movups  [rsp+98h+var_50], xmm0
0x18004dd42  movups  [rsp+98h+var_40], xmm0
0x18004dd47  mov     r14, [rsp+98h+phDecryptor]
0x18004dd4f  test    r14, r14
0x18004dd52  jnz     short loc_18004DD5E
0x18004dd54  mov     ebx, 80070057h
0x18004dd59  jmp     loc_18004DE9C
0x18004dd5e  test    rsi, rsi
0x18004dd61  jz      loc_18004DE2E
0x18004dd67  mov     r8d, 7FFFFFFFh
0x18004dd6d  mov     edx, r8d
0x18004dd70  mov     rax, rsi
0x18004dd73  cmp     [rax], di
0x18004dd76  jz      short loc_18004DD82
0x18004dd78  add     rax, 2
0x18004dd7c  sub     rdx, 1
0x18004dd80  jnz     short loc_18004DD73
0x18004dd82  mov     rax, rdx
0x18004dd85  neg     rax
0x18004dd88  sbb     ecx, ecx
0x18004dd8a  not     ecx
0x18004dd8c  mov     ebx, 80070057h
0x18004dd91  and     ebx, ecx
0x18004dd93  mov     rax, rdx
0x18004dd96  sub     r8, rdx
0x18004dd99  neg     rax
0x18004dd9c  sbb     rcx, rcx
0x18004dd9f  and     rcx, r8
0x18004dda2  test    rdx, rdx
0x18004dda5  jnz     short loc_18004DDAC
0x18004dda7  jmp     loc_18004DE88
0x18004ddac  lea     rbx, [rcx+1]
0x18004ddb0  cmp     rbx, rcx
0x18004ddb3  jb      loc_18004DEDC
0x18004ddb9  mov     rcx, rbx
0x18004ddbc  shr     rcx, 20h
0x18004ddc0  mov     rax, rcx
0x18004ddc3  shr     rax, 1Fh
0x18004ddc7  test    eax, eax
0x18004ddc9  jnz     loc_18004DEE2
0x18004ddcf  mov     eax, ebx
0x18004ddd1  add     rax, rax
0x18004ddd4  shl     rcx, 21h
0x18004ddd8  lea     rdx, [rcx+rax]
0x18004dddc  cmp     rdx, rax
0x18004dddf  jb      loc_18004DEE7
0x18004dde5  test    rdx, rdx
0x18004dde8  jz      short loc_18004DE2E
0x18004ddea  mov     eax, 2
0x18004ddef  mul     rbx
0x18004ddf2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004ddf9  cmovb   rax, rcx
0x18004ddfd  mov     rcx, rax; Size
0x18004de00  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004de05  mov     [rsp+98h+Block+8], rax
0x18004de0a  test    rax, rax
0x18004de0d  jnz     short loc_18004DE16
0x18004de0f  mov     ebx, 8007000Eh
0x18004de14  jmp     short loc_18004DE88
0x18004de16  mov     r8, rsi; unsigned __int16 *
0x18004de19  mov     rdx, rbx; unsigned __int64
0x18004de1c  mov     rcx, [rsp+98h+Block+8]; unsigned __int16 *
0x18004de21  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004de26  mov     ebx, eax
0x18004de28  test    eax, eax
0x18004de2a  jns     short loc_18004DE2E
0x18004de2c  jmp     short loc_18004DE88
0x18004de2e  lea     r8, [rsp+98h+var_74]; unsigned int *
0x18004de33  mov     edx, r15d; unsigned int
0x18004de36  call    ?GetSPHandle@CHandlesTable@@QEAAJKPEAK@Z; CHandlesTable::GetSPHandle(ulong,ulong *)
0x18004de3b  mov     ebx, eax
0x18004de3d  test    eax, eax
0x18004de3f  js      short loc_18004DE88
0x18004de41  lea     r8, [rsp+98h+var_78]
0x18004de46  lea     rdx, [rsp+98h+Block]
0x18004de4b  mov     ecx, [rsp+98h+var_74]
0x18004de4f  mov     rax, cs:?g_pfnSPCreateDecryptor@@3P6AJKPEAU_SPAPIGRANT@@PEAK@ZEA; long (*g_pfnSPCreateDecryptor)(ulong,_SPAPIGRANT *,ulong *)
0x18004de56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004de5b  mov     ebx, eax
0x18004de5d  test    eax, eax
0x18004de5f  js      short loc_18004DE88
0x18004de61  mov     r8d, [rsp+98h+var_78]; unsigned int
0x18004de66  lea     rdx, [rsp+98h+var_70]; unsigned int *
0x18004de6b  call    ?CreateHandle@CHandlesTable@@QEAAJPEAKK@Z; CHandlesTable::CreateHandle(ulong *,ulong)
0x18004de70  mov     ebx, eax
0x18004de72  test    eax, eax
0x18004de74  js      short loc_18004DE88
0x18004de76  mov     eax, [rsp+98h+var_70]
0x18004de7a  mov     [r14], eax
0x18004de7d  jmp     short loc_18004DE9C
0x18004de7f  xor     edi, edi
0x18004de81  mov     ebx, dword ptr [rsp+98h+phDecryptor]
0x18004de88  mov     ecx, [rsp+98h+var_78]
0x18004de8c  test    ecx, ecx
0x18004de8e  jz      short loc_18004DE9C
0x18004de90  mov     rax, cs:?g_pfnSPCloseHandle@@3P6AJK@ZEA; long (*g_pfnSPCloseHandle)(ulong)
0x18004de97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004de9c  mov     rcx, [rsp+98h+Block+8]; Block
0x18004dea1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004dea6  mov     [rsp+98h+Block+8], rdi
0x18004deab  mov     edx, ebx
0x18004dead  lea     rcx, aMsdrmDrmcreate; "[msdrm]:-DRMCreateEnablingBitsDecryptor"...
0x18004deb4  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18004deb9  mov     eax, 8007007Ah
0x18004debe  cmp     ebx, eax
0x18004dec0  jz      short loc_18004DED0
0x18004dec2  mov     eax, 8004CF2Ch
0x18004dec7  cmp     ebx, 0C004D02Ch
0x18004decd  cmovnz  eax, ebx
0x18004ded0  add     rsp, 70h
0x18004ded4  pop     r15
0x18004ded6  pop     r14
0x18004ded8  pop     rdi
0x18004ded9  pop     rsi
0x18004deda  pop     rbx
0x18004dedb  retn
0x18004dedc  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18004dee2  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18004dee7  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
```
