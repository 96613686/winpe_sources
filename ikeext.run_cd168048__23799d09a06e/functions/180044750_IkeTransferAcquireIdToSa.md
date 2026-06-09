# IkeTransferAcquireIdToSa

- ea: `0x180044750`
- end: `0x180044b1d`
- name: `IkeTransferAcquireIdToSa`
- size: `973`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800eb6dc`

## callees

- `0x180006910`
- `0x180008388`
- `0x180020b80`
- `0x180044750`
- `0x180050850`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800447e6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004482b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800449ba`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800449ff`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800447e6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004482b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800449ba`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800449ff`
- `ntdll!EtwEventWriteTransfer` at `0x1800448fa`
- `ntdll!EtwEventWriteTransfer` at `0x180044adc`
- `ntdll!EtwEventWriteTransfer` at `0x1800448fa`
- `ntdll!EtwEventWriteTransfer` at `0x180044adc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044969`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044969`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044904`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044904`

## pseudocode

```c
__int64 __fastcall IkeTransferAcquireIdToSa(_QWORD *a1, __int64 a2)
{
  __int64 v4; // r14
  __int64 v5; // rbx
  LPCRITICAL_SECTION v6; // rax
  DWORD LockSemaphore; // ecx
  __int64 *Value; // rax
  __int64 v9; // rcx
  DWORD v10; // ecx
  char *v11; // rax
  const WCHAR *v12; // rdx
  __int64 v13; // rax
  bool v14; // zf
  int v15; // eax
  __int64 v16; // rcx
  void *v17; // rcx
  void *v18; // rcx
  LPCRITICAL_SECTION v19; // rax
  DWORD v20; // ecx
  __int64 *v21; // rax
  __int64 v22; // rcx
  DWORD v23; // ecx
  char *v24; // rax
  const WCHAR *v25; // rdx
  int v26; // ebx
  __int64 v28; // [rsp+38h] [rbp-51h] BYREF
  int v29; // [rsp+40h] [rbp-49h] BYREF
  int v30; // [rsp+44h] [rbp-45h]
  __int64 v31; // [rsp+48h] [rbp-41h]
  char *v32; // [rsp+50h] [rbp-39h] BYREF
  int v33; // [rsp+58h] [rbp-31h]
  int v34; // [rsp+5Ch] [rbp-2Dh]
  int *v35; // [rsp+60h] [rbp-29h]
  int v36; // [rsp+68h] [rbp-21h]
  int v37; // [rsp+6Ch] [rbp-1Dh]
  __int64 *v38; // [rsp+70h] [rbp-19h]
  __int64 v39; // [rsp+78h] [rbp-11h]
  const WCHAR *v40; // [rsp+80h] [rbp-9h]
  int v41; // [rsp+88h] [rbp-1h]
  int v42; // [rsp+8Ch] [rbp+3h]
  const char *v43; // [rsp+90h] [rbp+7h]
  __int64 v44; // [rsp+98h] [rbp+Fh]

  v4 = 0;
  v5 = -1;
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    goto LABEL_20;
  v6 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_9;
  LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( LockSemaphore == -1 )
    goto LABEL_9;
  Value = (__int64 *)TlsGetValue(LockSemaphore);
  if ( !Value )
  {
    v6 = gIkeExtGlobals;
LABEL_9:
    v9 = 0;
    goto LABEL_10;
  }
  v9 = *Value;
  v6 = gIkeExtGlobals;
LABEL_10:
  v28 = v9;
  v38 = &v28;
  v39 = 8;
  if ( !v6 )
    goto LABEL_18;
  v10 = (DWORD)v6[86].LockSemaphore;
  if ( v10 == -1 )
    goto LABEL_18;
  v11 = (char *)TlsGetValue(v10);
  v12 = (const WCHAR *)(v11 + 8);
  if ( !v11 )
    v12 = 0;
  if ( v12 )
  {
    v13 = -1;
    do
      v14 = v12[++v13] == 0;
    while ( !v14 );
    v15 = 2 * v13 + 2;
  }
  else
  {
LABEL_18:
    v12 = &LocaleName;
    v15 = 2;
  }
  v41 = v15;
  v30 = 5;
  v32 = off_180173280;
  v40 = v12;
  v42 = 0;
  v43 = "IkeTransferAcquireIdToSa";
  v44 = 25;
  v29 = 184549376;
  v31 = 1;
  v33 = *(unsigned __int16 *)off_180173280;
  v35 = &dword_180166EA4;
  v34 = 2;
  v36 = 45;
  v37 = 1;
  EtwEventWriteTransfer(qword_180173298, &v29, 0, 0, 5, &v32);
LABEL_20:
  EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 48));
  v16 = a1[49];
  if ( !v16 || (v4 = IkeCopyIpsecId(v16, (_QWORD *)(a2 + 304))) == 0 )
  {
    v17 = (void *)a1[50];
    if ( !v17 || (v4 = IkeDupeTokenHandle(v17, (LPHANDLE)(a2 + 312))) == 0 )
    {
      v18 = (void *)a1[51];
      if ( v18 )
        v4 = IkeDupeTokenHandle(v18, (LPHANDLE)(a2 + 328));
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a2 + 48));
  if ( (unsigned int)dword_180173278 > 5 && (qword_180173288 & 1) != 0 && (qword_180173290 & 1) == qword_180173290 )
  {
    v19 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v20 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v20 != -1 )
      {
        v21 = (__int64 *)TlsGetValue(v20);
        if ( v21 )
        {
          v22 = *v21;
          v19 = gIkeExtGlobals;
LABEL_35:
          v28 = v22;
          v38 = &v28;
          v39 = 8;
          if ( !v19 )
            goto LABEL_42;
          v23 = (DWORD)v19[86].LockSemaphore;
          if ( v23 == -1 )
            goto LABEL_42;
          v24 = (char *)TlsGetValue(v23);
          v25 = (const WCHAR *)(v24 + 8);
          if ( !v24 )
            v25 = 0;
          if ( v25 )
          {
            do
              v14 = v25[++v5] == 0;
            while ( !v14 );
            v26 = 2 * v5 + 2;
          }
          else
          {
LABEL_42:
            v25 = &LocaleName;
            v26 = 2;
          }
          v30 = 5;
          v32 = off_180173280;
          v41 = v26;
          v40 = v25;
          v42 = 0;
          v43 = "IkeTransferAcquireIdToSa";
          v44 = 25;
          v29 = 184549376;
          v31 = 1;
          v33 = *(unsigned __int16 *)off_180173280;
          v35 = (int *)byte_180166E6B;
          v34 = 2;
          v36 = 45;
          v37 = 1;
          EtwEventWriteTransfer(qword_180173298, &v29, 0, 0, 5, &v32);
          return IkeReturnError(v4, "IkeTransferAcquireIdToSa");
        }
        v19 = gIkeExtGlobals;
      }
    }
    v22 = 0;
    goto LABEL_35;
  }
  return IkeReturnError(v4, "IkeTransferAcquireIdToSa");
}

```

## disassembly

```asm
0x180044750  mov     [rsp-8+arg_10], rbx
0x180044755  push    rbp
0x180044756  push    rsi
0x180044757  push    rdi
0x180044758  push    r12
0x18004475a  push    r13
0x18004475c  push    r14
0x18004475e  push    r15
0x180044760  lea     rbp, [rsp-27h]
0x180044765  sub     rsp, 0B0h
0x18004476c  mov     rax, cs:__security_cookie
0x180044773  xor     rax, rsp
0x180044776  mov     [rbp+57h+var_40], rax
0x18004477a  mov     eax, cs:dword_180173278
0x180044780  lea     rdi, aIketransferacq; "IkeTransferAcquireIdToSa"
0x180044787  xor     r13d, r13d
0x18004478a  lea     r12, _TraceLoggingMetadataEnd
0x180044791  mov     rsi, rdx
0x180044794  mov     r15, rcx
0x180044797  mov     r14d, r13d
0x18004479a  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800447a1  cmp     eax, 5
0x1800447a4  jbe     loc_180044900
0x1800447aa  mov     rcx, cs:qword_180173290
0x1800447b1  mov     rax, cs:qword_180173288
0x1800447b8  test    al, 1
0x1800447ba  jz      loc_180044900
0x1800447c0  mov     rax, rcx
0x1800447c3  and     eax, 1
0x1800447c6  cmp     rax, rcx
0x1800447c9  jnz     loc_180044900
0x1800447cf  mov     rax, cs:gIkeExtGlobals
0x1800447d6  test    rax, rax
0x1800447d9  jz      short loc_180044804
0x1800447db  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800447e1  cmp     ecx, 0FFFFFFFFh
0x1800447e4  jz      short loc_180044804
0x1800447e6  call    cs:__imp_TlsGetValue
0x1800447ec  test    rax, rax
0x1800447ef  jz      short loc_1800447FD
0x1800447f1  mov     rcx, [rax]
0x1800447f4  mov     rax, cs:gIkeExtGlobals
0x1800447fb  jmp     short loc_180044807
0x1800447fd  mov     rax, cs:gIkeExtGlobals
0x180044804  mov     rcx, r13
0x180044807  mov     [rbp+57h+var_A8], rcx
0x18004480b  lea     rcx, [rbp+57h+var_A8]
0x18004480f  mov     [rbp+57h+var_70], rcx
0x180044813  mov     [rbp+57h+var_68], 8
0x18004481b  test    rax, rax
0x18004481e  jz      short loc_180044859
0x180044820  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180044826  cmp     ecx, 0FFFFFFFFh
0x180044829  jz      short loc_180044859
0x18004482b  call    cs:__imp_TlsGetValue
0x180044831  test    rax, rax
0x180044834  lea     rdx, [rax+8]
0x180044838  cmovz   rdx, r13
0x18004483c  test    rdx, rdx
0x18004483f  jz      short loc_180044859
0x180044841  mov     rax, rbx
0x180044844  cmp     [rdx+rax*2+2], r13w
0x18004484a  lea     rax, [rax+1]
0x18004484e  jnz     short loc_180044844
0x180044850  lea     eax, ds:2[rax*2]
0x180044857  jmp     short loc_180044865
0x180044859  lea     rdx, LocaleName
0x180044860  mov     eax, 2
0x180044865  mov     [rbp+57h+var_58], eax
0x180044868  lea     rcx, _TraceLoggingMetadata
0x18004486f  movzx   eax, cs:word_180166E9A
0x180044876  xor     r9d, r9d
0x180044879  mov     [rbp+57h+var_9C], eax
0x18004487c  xor     r8d, r8d
0x18004487f  mov     rax, cs:off_180173280
0x180044886  mov     [rbp+57h+var_90], rax
0x18004488a  mov     [rbp+57h+var_60], rdx
0x18004488e  lea     rdx, [rbp+57h+var_A0]
0x180044892  mov     [rbp+57h+var_54], r13d
0x180044896  mov     [rbp+57h+var_50], rdi
0x18004489a  mov     [rbp+57h+var_48], 19h
0x1800448a2  mov     [rbp+57h+var_A0], 0B000000h
0x1800448a9  mov     [rbp+57h+var_98], 1
0x1800448b1  movzx   eax, word ptr [rax]
0x1800448b4  mov     [rbp+57h+var_88], eax
0x1800448b7  lea     rax, dword_180166EA4
0x1800448be  mov     [rbp+57h+var_80], rax
0x1800448c2  mov     rax, r12
0x1800448c5  sub     eax, ecx
0x1800448c7  mov     [rbp+57h+var_84], 2
0x1800448ce  mov     [rbp+57h+var_78], 2Dh ; '-'
0x1800448d5  mov     [rbp+57h+var_74], 1
0x1800448dc  mov     [rbp+57h+var_B0], eax
0x1800448df  mov     eax, [rbp+57h+var_B0]
0x1800448e2  mov     rcx, cs:qword_180173298
0x1800448e9  lea     rax, [rbp+57h+var_90]
0x1800448ed  mov     [rsp+0E0h+var_B8], rax
0x1800448f2  mov     [rsp+0E0h+var_C0], 5
0x1800448fa  call    cs:__imp_EtwEventWriteTransfer
0x180044900  lea     rcx, [rsi+30h]; lpCriticalSection
0x180044904  call    cs:__imp_EnterCriticalSection
0x18004490a  mov     rcx, [r15+188h]
0x180044911  test    rcx, rcx
0x180044914  jz      short loc_18004492A
0x180044916  lea     rdx, [rsi+130h]
0x18004491d  call    IkeCopyIpsecId
0x180044922  mov     r14, rax
0x180044925  test    rax, rax
0x180044928  jnz     short loc_180044965
0x18004492a  mov     rcx, [r15+190h]; hSourceHandle
0x180044931  test    rcx, rcx
0x180044934  jz      short loc_18004494A
0x180044936  lea     rdx, [rsi+138h]; lpTargetHandle
0x18004493d  call    IkeDupeTokenHandle
0x180044942  mov     r14, rax
0x180044945  test    rax, rax
0x180044948  jnz     short loc_180044965
0x18004494a  mov     rcx, [r15+198h]; hSourceHandle
0x180044951  test    rcx, rcx
0x180044954  jz      short loc_180044965
0x180044956  lea     rdx, [rsi+148h]; lpTargetHandle
0x18004495d  call    IkeDupeTokenHandle
0x180044962  mov     r14, rax
0x180044965  lea     rcx, [rsi+30h]; lpCriticalSection
0x180044969  call    cs:__imp_LeaveCriticalSection
0x18004496f  mov     eax, cs:dword_180173278
0x180044975  cmp     eax, 5
0x180044978  jbe     loc_180044AE4
0x18004497e  mov     rcx, cs:qword_180173290
0x180044985  mov     rax, cs:qword_180173288
0x18004498c  test    al, 1
0x18004498e  jz      loc_180044AE4
0x180044994  mov     rax, rcx
0x180044997  and     eax, 1
0x18004499a  cmp     rax, rcx
0x18004499d  jnz     loc_180044AE4
0x1800449a3  mov     rax, cs:gIkeExtGlobals
0x1800449aa  test    rax, rax
0x1800449ad  jz      short loc_1800449D8
0x1800449af  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800449b5  cmp     ecx, 0FFFFFFFFh
0x1800449b8  jz      short loc_1800449D8
0x1800449ba  call    cs:__imp_TlsGetValue
0x1800449c0  test    rax, rax
0x1800449c3  jz      short loc_1800449D1
0x1800449c5  mov     rcx, [rax]
0x1800449c8  mov     rax, cs:gIkeExtGlobals
0x1800449cf  jmp     short loc_1800449DB
0x1800449d1  mov     rax, cs:gIkeExtGlobals
0x1800449d8  mov     rcx, r13
0x1800449db  mov     [rbp+57h+var_A8], rcx
0x1800449df  lea     rcx, [rbp+57h+var_A8]
0x1800449e3  mov     [rbp+57h+var_70], rcx
0x1800449e7  mov     [rbp+57h+var_68], 8
0x1800449ef  test    rax, rax
0x1800449f2  jz      short loc_180044A35
0x1800449f4  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800449fa  cmp     ecx, 0FFFFFFFFh
0x1800449fd  jz      short loc_180044A35
0x1800449ff  call    cs:__imp_TlsGetValue
0x180044a05  test    rax, rax
0x180044a08  lea     rdx, [rax+8]
0x180044a0c  cmovz   rdx, r13
0x180044a10  test    rdx, rdx
0x180044a13  jz      short loc_180044A35
0x180044a15  nop     word ptr [rax+rax+00000000h]
0x180044a20  cmp     [rdx+rbx*2+2], r13w
0x180044a26  lea     rbx, [rbx+1]
0x180044a2a  jnz     short loc_180044A20
0x180044a2c  lea     ebx, ds:2[rbx*2]
0x180044a33  jmp     short loc_180044A41
0x180044a35  lea     rdx, LocaleName
0x180044a3c  mov     ebx, 2
0x180044a41  movzx   eax, cs:word_180166E61
0x180044a48  xor     r9d, r9d
0x180044a4b  mov     [rbp+57h+var_9C], eax
0x180044a4e  xor     r8d, r8d
0x180044a51  mov     rax, cs:off_180173280
0x180044a58  mov     [rbp+57h+var_90], rax
0x180044a5c  mov     [rbp+57h+var_58], ebx
0x180044a5f  lea     rbx, aIketransferacq; "IkeTransferAcquireIdToSa"
0x180044a66  mov     [rbp+57h+var_60], rdx
0x180044a6a  lea     rdx, [rbp+57h+var_A0]
0x180044a6e  mov     [rbp+57h+var_54], r13d
0x180044a72  mov     [rbp+57h+var_50], rbx
0x180044a76  mov     [rbp+57h+var_48], 19h
0x180044a7e  mov     [rbp+57h+var_A0], 0B000000h
0x180044a85  mov     [rbp+57h+var_98], 1
0x180044a8d  movzx   eax, word ptr [rax]
0x180044a90  mov     [rbp+57h+var_88], eax
0x180044a93  lea     rax, byte_180166E6B
0x180044a9a  mov     [rbp+57h+var_80], rax
0x180044a9e  lea     rax, _TraceLoggingMetadata
0x180044aa5  sub     r12d, eax
0x180044aa8  mov     [rbp+57h+var_84], 2
0x180044aaf  mov     [rbp+57h+var_78], 2Dh ; '-'
0x180044ab6  mov     [rbp+57h+var_74], 1
0x180044abd  mov     [rbp+57h+var_B0], r12d
0x180044ac1  mov     eax, [rbp+57h+var_B0]
0x180044ac4  mov     rcx, cs:qword_180173298
0x180044acb  lea     rax, [rbp+57h+var_90]
0x180044acf  mov     [rsp+0E0h+var_B8], rax
0x180044ad4  mov     [rsp+0E0h+var_C0], 5
0x180044adc  call    cs:__imp_EtwEventWriteTransfer
0x180044ae2  jmp     short loc_180044AEB
0x180044ae4  lea     rbx, aIketransferacq; "IkeTransferAcquireIdToSa"
0x180044aeb  mov     rdx, rbx
0x180044aee  mov     rcx, r14
0x180044af1  call    IkeReturnError
0x180044af6  mov     rcx, [rbp+57h+var_40]
0x180044afa  xor     rcx, rsp; StackCookie
0x180044afd  call    __security_check_cookie
0x180044b02  mov     rbx, [rsp+0E0h+arg_10]
0x180044b0a  add     rsp, 0B0h
0x180044b11  pop     r15
0x180044b13  pop     r14
0x180044b15  pop     r13
0x180044b17  pop     r12
0x180044b19  pop     rdi
0x180044b1a  pop     rsi
0x180044b1b  pop     rbp
0x180044b1c  retn
```
