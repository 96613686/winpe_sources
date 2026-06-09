# SspipProcessSecurityContext

- ea: `0x180002a84`
- end: `0x18000356c`
- name: `SspipProcessSecurityContext`
- size: `2792`
- prototype: `__int64 __fastcall(__int128 *, _OWORD *, __int64, struct _SecBufferDesc *, int, int, _OWORD *, __int64, _DWORD *, __int64, bool *, __int64, _DWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800248c0`

## callees

- `0x180002a84`
- `0x180004050`
- `0x180004074`
- `0x1800046fc`
- `0x180004b38`
- `0x180007ba8`
- `0x180007bd8`
- `0x180007c1c`
- `0x18000b298`
- `0x18000b2ec`
- `0x180010840`
- `0x180010920`
- `0x180010980`
- `0x180010c80`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x180002eb0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x180002eb0`
- `ntoskrnl!PsGetCurrentProcess` at `0x180002e8d`
- `ntoskrnl!PsGetCurrentProcess` at `0x180002e8d`
- `ntoskrnl!PsGetProcessId` at `0x180002e9c`
- `ntoskrnl!PsGetProcessId` at `0x180002e9c`
- `msrpc!I_RpcExceptionFilter` at `0x1800112a6`
- `msrpc!I_RpcExceptionFilter` at `0x1800112a6`

## pseudocode

```c
__int64 __fastcall SspipProcessSecurityContext(
        __int128 *a1,
        _OWORD *a2,
        __int64 a3,
        struct _SecBufferDesc *a4,
        int a5,
        int a6,
        _OWORD *a7,
        __int64 a8,
        _DWORD *a9,
        _QWORD *a10,
        bool *a11,
        __int64 a12,
        _DWORD *a13,
        __int64 a14,
        __int64 a15)
{
  int Pointer; // ebx
  unsigned int cBuffers; // r8d
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  struct _SecBufferDesc *v24; // r13
  __int128 *v25; // rax
  _QWORD *v26; // rcx
  _DWORD *v27; // r14
  _QWORD *v28; // r15
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // r9
  struct _KPROCESS *CurrentProcess; // rax
  unsigned int i; // r14d
  __int64 v35; // rcx
  __int64 v36; // rdx
  size_t v37; // r8
  _DWORD *v38; // r14
  _QWORD *v39; // r15
  _QWORD *v40; // r12
  unsigned int j; // edi
  __int64 v42; // rcx
  _BYTE *v43; // rcx
  __int64 v44; // rax
  __int64 v45; // rdi
  __int64 v46; // rcx
  __int128 *v47; // rax
  _BYTE *v48; // rcx
  __int64 v49; // rax
  __int128 *v50; // rax
  __int64 result; // rax
  int v52; // [rsp+B0h] [rbp-388h] BYREF
  __int128 v53; // [rsp+B8h] [rbp-380h] BYREF
  _DWORD *v54; // [rsp+C8h] [rbp-370h]
  PVOID DataBuffer; // [rsp+D0h] [rbp-368h] BYREF
  __int64 v56; // [rsp+D8h] [rbp-360h]
  _DWORD *v57; // [rsp+E0h] [rbp-358h]
  _OWORD *v58; // [rsp+E8h] [rbp-350h]
  _QWORD *v59; // [rsp+F0h] [rbp-348h]
  int v60; // [rsp+F8h] [rbp-340h]
  _QWORD *v61; // [rsp+100h] [rbp-338h]
  __int128 v62; // [rsp+110h] [rbp-328h] BYREF
  __int64 v63; // [rsp+120h] [rbp-318h]
  __int64 v64; // [rsp+128h] [rbp-310h]
  __int64 v65; // [rsp+130h] [rbp-308h]
  __int64 v66; // [rsp+138h] [rbp-300h] BYREF
  bool *v67; // [rsp+140h] [rbp-2F8h]
  char *v68; // [rsp+148h] [rbp-2F0h]
  char *v69; // [rsp+150h] [rbp-2E8h]
  struct _SecBufferDesc *v70; // [rsp+158h] [rbp-2E0h]
  __int64 v71; // [rsp+160h] [rbp-2D8h]
  _OWORD *v72; // [rsp+168h] [rbp-2D0h]
  _QWORD v73[2]; // [rsp+170h] [rbp-2C8h] BYREF
  __int128 v74; // [rsp+180h] [rbp-2B8h] BYREF
  __int128 v75; // [rsp+190h] [rbp-2A8h]
  PVOID v76[2]; // [rsp+1A0h] [rbp-298h]
  __int128 v77; // [rsp+1B0h] [rbp-288h] BYREF
  __int128 v78; // [rsp+1C0h] [rbp-278h]
  PVOID v79[2]; // [rsp+1D0h] [rbp-268h]
  __int128 v80; // [rsp+1E0h] [rbp-258h] BYREF
  __int128 v81; // [rsp+1F0h] [rbp-248h] BYREF
  __int128 v82; // [rsp+200h] [rbp-238h] BYREF
  __int128 v83; // [rsp+210h] [rbp-228h] BYREF
  __int128 v84; // [rsp+220h] [rbp-218h] BYREF
  __int128 v85; // [rsp+230h] [rbp-208h] BYREF
  _DWORD v86[36]; // [rsp+240h] [rbp-1F8h] BYREF
  _QWORD v87[36]; // [rsp+2D0h] [rbp-168h] BYREF

  v56 = a3;
  v61 = a2;
  v67 = a11;
  v71 = a3;
  v59 = a10;
  v58 = a7;
  v73[1] = a2;
  v72 = a2;
  v57 = a9;
  v63 = a12;
  v54 = a13;
  v65 = a14;
  v64 = a15;
  v52 = 0;
  v66 = 0;
  v85 = 0;
  v73[0] = 0;
  v84 = 0;
  v83 = 0;
  v82 = 0;
  v80 = 0;
  v81 = 0;
  v53 = 0;
  memset(v87, 0, sizeof(v87));
  memset(v86, 0, sizeof(v86));
  v62 = 0;
  DataBuffer = 0;
  v74 = 0;
  v75 = 0;
  *(_OWORD *)v76 = 0;
  v77 = 0;
  v78 = 0;
  *(_OWORD *)v79 = 0;
  if ( !a1 )
  {
    Pointer = -2146893054;
    goto LABEL_84;
  }
  if ( a4 )
  {
    cBuffers = a4->cBuffers;
    if ( cBuffers > 0x12 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
        goto LABEL_9;
      v21 = 13;
      goto LABEL_8;
    }
    if ( cBuffers && !a4->pBuffers )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
        goto LABEL_9;
      v23 = 14;
      goto LABEL_15;
    }
  }
  if ( a8 )
  {
    cBuffers = *(_DWORD *)(a8 + 4);
    if ( cBuffers > 0x12 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
        goto LABEL_9;
      v21 = 15;
LABEL_8:
      WPP_SF_D(v20[3], v21, WPP_c36fb4c2aaf6301e6032cbac527c9a1d_Traceguids, cBuffers);
LABEL_9:
      Pointer = -2146893048;
      goto LABEL_84;
    }
    if ( cBuffers && !*(_QWORD *)(a8 + 8) )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
        goto LABEL_9;
      v23 = 16;
LABEL_15:
      WPP_SF_(v22[3], v23, WPP_c36fb4c2aaf6301e6032cbac527c9a1d_Traceguids);
      goto LABEL_9;
    }
  }
  Pointer = IsOkayToExecRpc(&v66);
  if ( Pointer >= 0 )
  {
    v84 = *a1;
    if ( a2 )
      v83 = *a2;
    v24 = (struct _SecBufferDesc *)&v80;
    if ( a4 )
      v24 = a4;
    v25 = &v81;
    if ( a8 )
      v25 = (__int128 *)a8;
    v26 = v73;
    if ( v59 )
      v26 = v59;
    v59 = v26;
    LODWORD(v53) = *(_DWORD *)v25;
    v27 = (_DWORD *)v25 + 1;
    v69 = (char *)v25 + 4;
    DWORD1(v53) = *((_DWORD *)v25 + 1);
    *((_QWORD *)&v53 + 1) = v87;
    v28 = (_QWORD *)v25 + 1;
    v68 = (char *)v25 + 8;
    memmove(v87, *((const void **)v25 + 1), 16LL * DWORD1(v53));
    *(_QWORD *)&v62 = v53;
    *((_QWORD *)&v62 + 1) = v86;
    v32 = 0;
    if ( DWORD1(v53) )
    {
      do
      {
        v29 = (unsigned int)v32;
        v31 = 2LL * (unsigned int)v32;
        *(_DWORD *)(*((_QWORD *)&v62 + 1) + 8LL * (unsigned int)v32 + 4) = *(_DWORD *)(*v28
                                                                                     + 16LL * (unsigned int)v32
                                                                                     + 4);
        v30 = *(unsigned int *)(*v28 + 16LL * (unsigned int)v32);
        *(_DWORD *)(*((_QWORD *)&v62 + 1) + 8LL * (unsigned int)v32) = v30;
        if ( (a5 & 0x100) != 0 )
          v87[2 * (unsigned int)v32 + 1] = 0;
        v32 = (unsigned int)(v32 + 1);
      }
      while ( (unsigned int)v32 < *v27 );
    }
    CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess(v30, v29, v31, v32);
    *(_QWORD *)&v85 = PsGetProcessId(CurrentProcess);
    *((_QWORD *)&v85 + 1) = PsGetCurrentThreadId();
    v70 = v24;
    if ( *(_QWORD *)&WPP_MAIN_CB.DeviceType )
    {
      Pointer = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _DWORD *, __int64, __int128 *, __int128 *, int, int, __int64, __int64, struct _SecBufferDesc *, __int128 *, __int128 *, PVOID *, __int64, __int128 *, _DWORD *, _QWORD *, int *, _QWORD, _QWORD))(*(_QWORD *)&WPP_MAIN_CB.DeviceType + 24LL))(
                  0,
                  &v85,
                  v54,
                  v56,
                  &v84,
                  &v83,
                  a5,
                  a6,
                  v65,
                  v64,
                  v24,
                  &v62,
                  &v53,
                  &DataBuffer,
                  v63,
                  &v82,
                  v57,
                  v59,
                  &v52,
                  0,
                  0);
    }
    else
    {
      Pointer = (unsigned int)SspirProcessSecurityContext(
                                v66,
                                (__int64)&v85,
                                (__int64)v54,
                                v56,
                                (__int64)&v84,
                                (__int64)&v83,
                                a5,
                                a6,
                                v65,
                                v64,
                                (__int64)v24,
                                (__int64)&v62,
                                (__int64)&v53,
                                (__int64)&DataBuffer,
                                v63,
                                (__int64)&v82,
                                (__int64)v57,
                                (__int64)v59,
                                (__int64)&v52,
                                (__int64)&v74,
                                (__int64)&v77).Pointer;
      v60 = Pointer;
    }
    if ( Pointer < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          17,
          WPP_c36fb4c2aaf6301e6032cbac527c9a1d_Traceguids,
          (unsigned int)Pointer);
      goto LABEL_84;
    }
    if ( DWORD1(v53) > *v27 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_LL(*((_QWORD *)WPP_GLOBAL_Control + 3), 18, WPP_c36fb4c2aaf6301e6032cbac527c9a1d_Traceguids);
      Pointer = 261;
      goto LABEL_84;
    }
    for ( i = 0; i < DWORD1(v53); ++i )
    {
      v35 = *(_QWORD *)(*((_QWORD *)&v53 + 1) + 16LL * i + 8);
      if ( v35 )
      {
        if ( !*(_QWORD *)&WPP_MAIN_CB.DeviceType || (a5 & 0x100) != 0 )
        {
          *(_QWORD *)(*v28 + 16LL * i + 8) = v35;
          *(_QWORD *)(*((_QWORD *)&v53 + 1) + 16LL * i + 8) = 0;
        }
        else
        {
          v36 = *(unsigned int *)(*v28 + 16LL * i);
          v37 = *(unsigned int *)(*((_QWORD *)&v53 + 1) + 16LL * i);
          if ( (unsigned int)v36 < (unsigned int)v37 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
            {
              WPP_SF_LLL(*((_QWORD *)WPP_GLOBAL_Control + 3), v36, v37, i, v36, v37);
            }
            Pointer = -1073741789;
            goto LABEL_84;
          }
          memmove(*(void **)(*v28 + 16LL * i + 8), *(const void **)(*((_QWORD *)&v53 + 1) + 16LL * i + 8), v37);
        }
      }
      *(_QWORD *)(*v28 + 16LL * i) = *(_QWORD *)(*((_QWORD *)&v53 + 1) + 16LL * i);
    }
    if ( v52 >= 0 )
    {
      v38 = v54;
      v39 = v58;
      v40 = v58;
LABEL_82:
      Pointer = CopyExtraBuffers((struct _SecBufferInfoArray *)DataBuffer, v24);
      if ( Pointer >= 0 )
      {
        *v67 = (*v38 & 0x2000) != 0;
        *v39 = v82;
        v40[1] = *((_QWORD *)&v82 + 1);
        Pointer = 0;
      }
      goto LABEL_84;
    }
    if ( *((_QWORD *)v72 + 1) || *v61 )
    {
      v38 = v54;
      if ( (*v54 & 0x20) != 0 )
      {
        v39 = v58;
        *v58 = v82;
        v40 = v39;
        Pointer = 0;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          WPP_SF_PP(*((_QWORD *)WPP_GLOBAL_Control + 3), 20, WPP_c36fb4c2aaf6301e6032cbac527c9a1d_Traceguids);
LABEL_73:
        if ( v56 || (*v57 & 0x8000) == 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
            WPP_SF_D(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              21,
              WPP_c36fb4c2aaf6301e6032cbac527c9a1d_Traceguids,
              (unsigned int)v52);
          if ( v52 == -2146893032 || v52 == -2146892950 )
            Pointer = CopyExtraBuffers((struct _SecBufferInfoArray *)DataBuffer, v24);
          goto LABEL_84;
        }
        goto LABEL_82;
      }
    }
    else
    {
      v38 = v54;
    }
    v39 = v58;
    v40 = v58;
    goto LABEL_73;
  }
LABEL_84:
  if ( DataBuffer )
  {
    if ( *(_QWORD *)&WPP_MAIN_CB.DeviceType )
      (**(void (__fastcall ***)(PVOID))&WPP_MAIN_CB.DeviceType)(DataBuffer);
    else
      SspiLocalFree(DataBuffer);
  }
  if ( *((_QWORD *)&v53 + 1) && *((_QWORD **)&v53 + 1) != v87 && *(_QWORD *)&WPP_MAIN_CB.DeviceType )
  {
    for ( j = 0; j < DWORD1(v53); ++j )
    {
      v42 = *(_QWORD *)(*((_QWORD *)&v53 + 1) + 16LL * j + 8);
      if ( v42 )
        (**(void (__fastcall ***)(__int64))&WPP_MAIN_CB.DeviceType)(v42);
    }
    (**(void (__fastcall ***)(_QWORD))&WPP_MAIN_CB.DeviceType)(*((_QWORD *)&v53 + 1));
  }
  v43 = v76[0];
  if ( v76[0] )
  {
    v44 = DWORD2(v75);
    if ( DWORD2(v75) )
    {
      do
      {
        *v43++ = 0;
        --v44;
      }
      while ( v44 );
      v43 = v76[0];
    }
    SspiLocalFree(v43);
  }
  v45 = 48;
  v46 = 48;
  v47 = &v74;
  do
  {
    *(_BYTE *)v47 = 0;
    v47 = (__int128 *)((char *)v47 + 1);
    --v46;
  }
  while ( v46 );
  v48 = v79[0];
  if ( v79[0] )
  {
    v49 = DWORD2(v78);
    if ( DWORD2(v78) )
    {
      do
      {
        *v48++ = 0;
        --v49;
      }
      while ( v49 );
      v48 = v79[0];
    }
    SspiLocalFree(v48);
  }
  v50 = &v77;
  do
  {
    *(_BYTE *)v50 = 0;
    v50 = (__int128 *)((char *)v50 + 1);
    --v45;
  }
  while ( v45 );
  result = (unsigned int)v52;
  if ( Pointer < 0 )
    return (unsigned int)Pointer;
  return result;
}

```

## disassembly

```asm
0x180002a84  push    rbx
0x180002a86  push    rsi
0x180002a87  push    rdi
0x180002a88  push    r12
0x180002a8a  push    r13
0x180002a8c  push    r14
0x180002a8e  push    r15
0x180002a90  sub     rsp, 400h
0x180002a97  mov     rax, cs:__security_cookie
0x180002a9e  xor     rax, rsp
0x180002aa1  mov     [rsp+438h+var_48], rax
0x180002aa9  mov     rdi, r9
0x180002aac  mov     [rsp+438h+var_360], r8
0x180002ab4  mov     [rsp+438h+var_338], rdx
0x180002abc  mov     r15, rcx
0x180002abf  mov     rcx, [rsp+438h+arg_50]
0x180002ac7  mov     [rsp+438h+var_2F8], rcx
0x180002acf  mov     [rsp+438h+var_2D8], r8
0x180002ad7  mov     rcx, [rsp+438h+arg_48]
0x180002adf  mov     [rsp+438h+var_348], rcx
0x180002ae7  mov     r14, [rsp+438h+arg_38]
0x180002aef  mov     rcx, [rsp+438h+arg_30]
0x180002af7  mov     [rsp+438h+var_350], rcx
0x180002aff  mov     [rsp+438h+var_2C0], rdx
0x180002b07  mov     r13, rdx
0x180002b0a  mov     [rsp+438h+var_2D0], rdx
0x180002b12  mov     rax, [rsp+438h+arg_40]
0x180002b1a  mov     [rsp+438h+var_358], rax
0x180002b22  mov     rax, [rsp+438h+arg_58]
0x180002b2a  mov     [rsp+438h+var_318], rax
0x180002b32  mov     rax, [rsp+438h+arg_60]
0x180002b3a  mov     [rsp+438h+var_370], rax
0x180002b42  mov     rax, [rsp+438h+arg_68]
0x180002b4a  mov     [rsp+438h+var_308], rax
0x180002b52  mov     rax, [rsp+438h+arg_70]
0x180002b5a  mov     [rsp+438h+var_310], rax
0x180002b62  xor     esi, esi
0x180002b64  mov     [rsp+438h+var_388], esi
0x180002b6b  mov     [rsp+438h+var_300], rsi
0x180002b73  xorps   xmm0, xmm0
0x180002b76  movups  [rsp+438h+var_208], xmm0
0x180002b7e  mov     [rsp+438h+var_2C8], rsi
0x180002b86  xorps   xmm1, xmm1
0x180002b89  movups  [rsp+438h+var_218], xmm1
0x180002b91  movups  [rsp+438h+var_228], xmm0
0x180002b99  movups  [rsp+438h+var_238], xmm1
0x180002ba1  movups  [rsp+438h+var_258], xmm0
0x180002ba9  movups  [rsp+438h+var_248], xmm1
0x180002bb1  movups  [rsp+438h+var_380], xmm0
0x180002bb9  mov     [rsp+438h+var_168], esi
0x180002bc0  xor     edx, edx; Val
0x180002bc2  mov     r8d, 11Ch; Size
0x180002bc8  lea     rcx, [rsp+438h+var_164]; void *
0x180002bd0  call    memset
0x180002bd5  mov     [rsp+438h+var_1F8], esi
0x180002bdc  xor     edx, edx; Val
0x180002bde  mov     r8d, 8Ch; Size
0x180002be4  lea     rcx, [rsp+438h+var_1F4]; void *
0x180002bec  call    memset
0x180002bf1  xorps   xmm0, xmm0
0x180002bf4  movups  [rsp+438h+var_328], xmm0
0x180002bfc  mov     [rsp+438h+DataBuffer], rsi
0x180002c04  xorps   xmm1, xmm1
0x180002c07  movups  [rsp+438h+var_2B8], xmm1
0x180002c0f  movups  [rsp+438h+var_2A8], xmm1
0x180002c17  movups  xmmword ptr [rsp+438h+var_298], xmm1
0x180002c1f  movups  [rsp+438h+var_288], xmm0
0x180002c27  movups  [rsp+438h+var_278], xmm0
0x180002c2f  movups  xmmword ptr [rsp+438h+var_268], xmm0
0x180002c37  test    r15, r15
0x180002c3a  jnz     short loc_180002C46
0x180002c3c  mov     ebx, 80090302h
0x180002c41  jmp     loc_180003400
0x180002c46  test    rdi, rdi
0x180002c49  jz      loc_180002CD1
0x180002c4f  mov     r8d, [rdi+4]
0x180002c53  cmp     r8d, 12h
0x180002c57  jbe     short loc_180002C95
0x180002c59  lea     rdi, WPP_GLOBAL_Control
0x180002c60  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c67  cmp     rcx, rdi
0x180002c6a  jz      short loc_180002C8B
0x180002c6c  mov     eax, [rcx+2Ch]
0x180002c6f  test    al, 1
0x180002c71  jz      short loc_180002C8B
0x180002c73  mov     edx, 0Dh
0x180002c78  mov     r9d, r8d
0x180002c7b  lea     r8, WPP_c36fb4c2aaf6301e6032cbac527c9a1d_Traceguids
0x180002c82  mov     rcx, [rcx+18h]
0x180002c86  call    WPP_SF_D
0x180002c8b  mov     ebx, 80090308h
0x180002c90  jmp     loc_180003400
0x180002c95  test    r8d, r8d
0x180002c98  jz      short loc_180002CD1
0x180002c9a  cmp     [rdi+8], rsi
0x180002c9e  jnz     short loc_180002CD1
0x180002ca0  lea     rdi, WPP_GLOBAL_Control
0x180002ca7  mov     rcx, cs:WPP_GLOBAL_Control
0x180002cae  cmp     rcx, rdi
0x180002cb1  jz      short loc_180002C8B
0x180002cb3  mov     eax, [rcx+2Ch]
0x180002cb6  test    al, 1
0x180002cb8  jz      short loc_180002C8B
0x180002cba  mov     edx, 0Eh
0x180002cbf  lea     r8, WPP_c36fb4c2aaf6301e6032cbac527c9a1d_Traceguids
0x180002cc6  mov     rcx, [rcx+18h]
0x180002cca  call    WPP_SF_
0x180002ccf  jmp     short loc_180002C8B
0x180002cd1  test    r14, r14
0x180002cd4  jz      short loc_180002D38
0x180002cd6  mov     r8d, [r14+4]
0x180002cda  cmp     r8d, 12h
0x180002cde  jbe     short loc_180002D04
0x180002ce0  lea     rdi, WPP_GLOBAL_Control
0x180002ce7  mov     rcx, cs:WPP_GLOBAL_Control
0x180002cee  cmp     rcx, rdi
0x180002cf1  jz      short loc_180002C8B
0x180002cf3  mov     eax, [rcx+2Ch]
0x180002cf6  test    al, 1
0x180002cf8  jz      short loc_180002C8B
0x180002cfa  mov     edx, 0Fh
0x180002cff  jmp     loc_180002C78
0x180002d04  test    r8d, r8d
0x180002d07  jz      short loc_180002D38
0x180002d09  cmp     [r14+8], rsi
0x180002d0d  jnz     short loc_180002D38
0x180002d0f  lea     rdi, WPP_GLOBAL_Control
0x180002d16  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d1d  cmp     rcx, rdi
0x180002d20  jz      loc_180002C8B
0x180002d26  mov     eax, [rcx+2Ch]
0x180002d29  test    al, 1
0x180002d2b  jz      loc_180002C8B
0x180002d31  mov     edx, 10h
0x180002d36  jmp     short loc_180002CBF
0x180002d38  lea     rcx, [rsp+438h+var_300]
0x180002d40  call    IsOkayToExecRpc
0x180002d45  mov     ebx, eax
0x180002d47  test    eax, eax
0x180002d49  js      loc_180003400
0x180002d4f  mov     r12d, [rsp+438h+arg_20]
0x180002d57  mov     rax, [r15]
0x180002d5a  mov     qword ptr [rsp+438h+var_218], rax
0x180002d62  mov     rax, [r15+8]
0x180002d66  mov     qword ptr [rsp+438h+var_218+8], rax
0x180002d6e  test    r13, r13
0x180002d71  jz      short loc_180002D8B
0x180002d73  mov     rax, [r13+0]
0x180002d77  mov     qword ptr [rsp+438h+var_228], rax
0x180002d7f  mov     rax, [r13+8]
0x180002d83  mov     qword ptr [rsp+438h+var_228+8], rax
0x180002d8b  lea     r13, [rsp+438h+var_258]
0x180002d93  test    rdi, rdi
0x180002d96  cmovnz  r13, rdi
0x180002d9a  lea     rax, [rsp+438h+var_248]
0x180002da2  test    r14, r14
0x180002da5  cmovnz  rax, r14
0x180002da9  lea     rcx, [rsp+438h+var_2C8]
0x180002db1  mov     rdx, [rsp+438h+var_348]
0x180002db9  test    rdx, rdx
0x180002dbc  cmovnz  rcx, rdx
0x180002dc0  mov     [rsp+438h+var_348], rcx
0x180002dc8  mov     ebx, [rax]
0x180002dca  mov     dword ptr [rsp+438h+var_380], ebx
0x180002dd1  lea     r14, [rax+4]
0x180002dd5  mov     [rsp+438h+var_2E8], r14
0x180002ddd  mov     edi, [r14]
0x180002de0  mov     dword ptr [rsp+438h+var_380+4], edi
0x180002de7  lea     rcx, [rsp+438h+var_168]
0x180002def  mov     qword ptr [rsp+438h+var_380+8], rcx
0x180002df7  lea     r15, [rax+8]
0x180002dfb  mov     [rsp+438h+var_2F0], r15
0x180002e03  mov     r8d, edi
0x180002e06  shl     r8, 4; Size
0x180002e0a  mov     rdx, [r15]; Src
0x180002e0d  lea     rcx, [rsp+438h+var_168]; void *
0x180002e15  call    memmove
0x180002e1a  mov     dword ptr [rsp+438h+var_328], ebx
0x180002e21  mov     dword ptr [rsp+438h+var_328+4], edi
0x180002e28  lea     rax, [rsp+438h+var_1F8]
0x180002e30  mov     qword ptr [rsp+438h+var_328+8], rax
0x180002e38  mov     r9d, esi
0x180002e3b  test    edi, edi
0x180002e3d  jz      short loc_180002E8D
0x180002e3f  mov     r10d, r12d
0x180002e42  and     r10d, 100h
0x180002e49  mov     edx, r9d
0x180002e4c  mov     r8d, r9d
0x180002e4f  add     r8, r8
0x180002e52  mov     rax, [r15]
0x180002e55  mov     ecx, [rax+r8*8+4]
0x180002e5a  mov     rax, qword ptr [rsp+438h+var_328+8]
0x180002e62  mov     [rax+rdx*8+4], ecx
0x180002e66  mov     rax, [r15]
0x180002e69  mov     ecx, [rax+r8*8]
0x180002e6d  mov     rax, qword ptr [rsp+438h+var_328+8]
0x180002e75  mov     [rax+rdx*8], ecx
0x180002e78  test    r10d, r10d
0x180002e7b  jz      short loc_180002E85
0x180002e7d  mov     [rsp+r8*8+438h+var_160], rsi
0x180002e85  inc     r9d
0x180002e88  cmp     r9d, [r14]
0x180002e8b  jb      short loc_180002E49
0x180002e8d  call    cs:__imp_PsGetCurrentProcess
0x180002e94  nop     dword ptr [rax+rax+00h]
0x180002e99  mov     rcx, rax; Process
0x180002e9c  call    cs:__imp_PsGetProcessId
0x180002ea3  nop     dword ptr [rax+rax+00h]
0x180002ea8  mov     qword ptr [rsp+438h+var_208], rax
0x180002eb0  call    cs:__imp_PsGetCurrentThreadId
0x180002eb7  nop     dword ptr [rax+rax+00h]
0x180002ebc  mov     qword ptr [rsp+438h+var_208+8], rax
0x180002ec4  mov     [rsp+438h+var_2E0], r13
0x180002ecc  mov     rax, qword ptr cs:WPP_MAIN_CB.DeviceType
0x180002ed3  test    rax, rax
0x180002ed6  jz      loc_180002FD0
0x180002edc  mov     rax, [rax+18h]
0x180002ee0  mov     [rsp+438h+var_398], rsi
0x180002ee8  mov     [rsp+438h+var_3A0], rsi
0x180002ef0  lea     rcx, [rsp+438h+var_388]
0x180002ef8  mov     [rsp+438h+var_3A8], rcx
0x180002f00  mov     rcx, [rsp+438h+var_348]
0x180002f08  mov     [rsp+438h+var_3B0], rcx
0x180002f10  mov     rcx, [rsp+438h+var_358]
0x180002f18  mov     [rsp+438h+var_3B8], rcx
0x180002f20  lea     rcx, [rsp+438h+var_238]
0x180002f28  mov     [rsp+438h+var_3C0], rcx
0x180002f2d  mov     rcx, [rsp+438h+var_318]
0x180002f35  mov     [rsp+438h+var_3C8], rcx
0x180002f3a  lea     rcx, [rsp+438h+DataBuffer]
0x180002f42  mov     [rsp+438h+var_3D0], rcx
0x180002f47  lea     rcx, [rsp+438h+var_380]
0x180002f4f  mov     [rsp+438h+var_3D8], rcx
0x180002f54  lea     rcx, [rsp+438h+var_328]
0x180002f5c  mov     [rsp+438h+var_3E0], rcx
0x180002f61  mov     [rsp+438h+var_3E8], r13
0x180002f66  mov     rcx, [rsp+438h+var_310]
0x180002f6e  mov     [rsp+438h+var_3F0], rcx
0x180002f73  mov     rcx, [rsp+438h+var_308]
0x180002f7b  mov     [rsp+438h+var_3F8], rcx
0x180002f80  mov     ecx, [rsp+438h+arg_28]
0x180002f87  mov     [rsp+438h+var_400], ecx
0x180002f8b  mov     [rsp+438h+var_408], r12d
0x180002f90  lea     rcx, [rsp+438h+var_228]
0x180002f98  mov     [rsp+438h+var_410], rcx
0x180002f9d  lea     rcx, [rsp+438h+var_218]
0x180002fa5  mov     [rsp+438h+var_418], rcx
0x180002faa  mov     r9, [rsp+438h+var_360]
0x180002fb2  mov     r8, [rsp+438h+var_370]
0x180002fba  lea     rdx, [rsp+438h+var_208]
0x180002fc2  xor     ecx, ecx
0x180002fc4  call    _guard_dispatch_icall
0x180002fc9  mov     ebx, eax
0x180002fcb  jmp     loc_180003125
0x180002fd0  lea     rax, [rsp+438h+var_288]
0x180002fd8  mov     [rsp+438h+var_398], rax
0x180002fe0  lea     rax, [rsp+438h+var_2B8]
0x180002fe8  mov     [rsp+438h+var_3A0], rax
0x180002ff0  lea     rax, [rsp+438h+var_388]
0x180002ff8  mov     [rsp+438h+var_3A8], rax
0x180003000  mov     rcx, [rsp+438h+var_348]
0x180003008  mov     [rsp+438h+var_3B0], rcx
0x180003010  mov     rcx, [rsp+438h+var_358]
0x180003018  mov     [rsp+438h+var_3B8], rcx
0x180003020  lea     rax, [rsp+438h+var_238]
0x180003028  mov     [rsp+438h+var_3C0], rax
0x18000302d  mov     rcx, [rsp+438h+var_318]
0x180003035  mov     [rsp+438h+var_3C8], rcx
0x18000303a  lea     rax, [rsp+438h+DataBuffer]
0x180003042  mov     [rsp+438h+var_3D0], rax
0x180003047  lea     rax, [rsp+438h+var_380]
0x18000304f  mov     [rsp+438h+var_3D8], rax
0x180003054  lea     rax, [rsp+438h+var_328]
0x18000305c  mov     [rsp+438h+var_3E0], rax
0x180003061  mov     [rsp+438h+var_3E8], r13
0x180003066  mov     rcx, [rsp+438h+var_310]
0x18000306e  mov     [rsp+438h+var_3F0], rcx
0x180003073  mov     rcx, [rsp+438h+var_308]
0x18000307b  mov     [rsp+438h+var_3F8], rcx
0x180003080  mov     eax, [rsp+438h+arg_28]
0x180003087  mov     [rsp+438h+var_400], eax
0x18000308b  mov     [rsp+438h+var_408], r12d
0x180003090  lea     rax, [rsp+438h+var_228]
0x180003098  mov     [rsp+438h+var_410], rax
0x18000309d  lea     rax, [rsp+438h+var_218]
0x1800030a5  mov     [rsp+438h+var_418], rax
0x1800030aa  mov     r9, [rsp+438h+var_360]
0x1800030b2  mov     r8, [rsp+438h+var_370]
0x1800030ba  lea     rdx, [rsp+438h+var_208]
0x1800030c2  mov     rcx, [rsp+438h+var_300]
0x1800030ca  call    SspirProcessSecurityContext
0x1800030cf  mov     ebx, eax
0x1800030d1  mov     [rsp+438h+var_340], eax
0x1800030d8  jmp     short loc_180003125
0x1800030da  mov     ebx, eax
0x1800030dc  mov     [rsp+438h+var_340], eax
0x1800030e3  xor     esi, esi
0x1800030e5  mov     r12d, [rsp+438h+arg_20]
0x1800030ed  mov     rcx, [rsp+438h+var_2C0]
0x1800030f5  mov     [rsp+438h+var_338], rcx
  ... truncated ...
```
