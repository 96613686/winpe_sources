# BSTR_UserUnmarshal

- ea: `0x18000bcb0`
- end: `0x18000c182`
- name: `BSTR_UserUnmarshal`
- size: `1234`
- prototype: `unsigned __int8 *__stdcall(unsigned int *, unsigned __int8 *, BSTR *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001cfb0`
- `0x18001e030`

## callees

- `0x1800039b8`
- `0x18000a920`
- `0x18000aa84`
- `0x18000bcb0`
- `0x18000c190`
- `0x180021d20`
- `0x180021dc0`
- `0x180027ed0`
- `0x180049d54`
- `0x18004e530`
- `0x18009a624`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000bf06`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000bf1e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000bf41`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c032`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000bf06`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000bf1e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000bf41`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c032`
- `RPCRT4!RpcRaiseException` at `0x18000be86`
- `RPCRT4!RpcRaiseException` at `0x18000bee5`
- `RPCRT4!RpcRaiseException` at `0x18000bfd4`
- `RPCRT4!RpcRaiseException` at `0x18000c03f`
- `RPCRT4!RpcRaiseException` at `0x18000c048`
- `RPCRT4!RpcRaiseException` at `0x18000be86`
- `RPCRT4!RpcRaiseException` at `0x18000bee5`
- `RPCRT4!RpcRaiseException` at `0x18000bfd4`
- `RPCRT4!RpcRaiseException` at `0x18000c03f`
- `RPCRT4!RpcRaiseException` at `0x18000c048`
- `RPCRT4!NdrGetUserMarshalInfo` at `0x18000bcfd`
- `RPCRT4!NdrGetUserMarshalInfo` at `0x18000bd47`
- `RPCRT4!NdrGetUserMarshalInfo` at `0x18000bcfd`
- `RPCRT4!NdrGetUserMarshalInfo` at `0x18000bd47`

## string_xrefs

- `0x18000c15e`: `Unexpected end of buffer during BUFFER.Read()`
- `0x18000c052`: `Unexpected end of buffer during BUFFER.Increment(%lu)`
- `0x18000c09d`: `Unexpected end of buffer during BUFFER.Increment(%lu)`

## pseudocode

```c
unsigned __int8 *__stdcall BSTR_UserUnmarshal(unsigned int *a1, unsigned __int8 *a2, BSTR *a3)
{
  BSTR *v3; // rbx
  RPC_STATUS UserMarshalInfo; // eax
  unsigned __int64 BufferSize; // r13
  RPC_STATUS v8; // eax
  unsigned __int8 *v9; // rdi
  __int64 v10; // rcx
  unsigned __int8 *v11; // rcx
  int v12; // eax
  _DWORD *v13; // rcx
  int v14; // r15d
  char *v15; // rcx
  int v16; // esi
  int v17; // r12d
  unsigned int v18; // ebx
  unsigned __int64 v19; // rdx
  int v20; // esi
  BSTR v21; // r12
  __int64 v22; // r15
  unsigned __int64 v23; // rax
  int v24; // ebx
  unsigned int v25; // ebx
  BSTR v26; // rdi
  __int64 *v27; // r14
  BSTR v28; // rdx
  APP_DATA *Value; // rax
  _DWORD *v30; // rax
  _DWORD *v31; // rbx
  int v32; // r14d
  void *v33; // rbx
  int v35; // eax
  __int64 v36; // r9
  UINT v37; // eax
  _BYTE v38[32]; // [rsp+20h] [rbp-E0h] BYREF
  BSTR Buffer; // [rsp+40h] [rbp-C0h]
  NDR_USER_MARSHAL_INFO pMarshalInfo; // [rsp+50h] [rbp-B0h] BYREF
  NDR_USER_MARSHAL_INFO v41; // [rsp+B0h] [rbp-50h] BYREF
  int v43; // [rsp+168h] [rbp+68h]
  BSTR v44; // [rsp+168h] [rbp+68h]

  v3 = a3;
  memset_0(&pMarshalInfo, 0, sizeof(pMarshalInfo));
  UserMarshalInfo = NdrGetUserMarshalInfo(a1, 1u, &pMarshalInfo);
  if ( UserMarshalInfo )
    RpcRaiseException(UserMarshalInfo);
  BufferSize = pMarshalInfo.Level1.BufferSize;
  Buffer = (BSTR)pMarshalInfo.Level1.Buffer;
  if ( !(unsigned int)SBGetConfigValue(0) )
  {
    memset_0(&v41, 0, sizeof(v41));
    v8 = NdrGetUserMarshalInfo(a1, 1u, &v41);
    if ( v8 )
      RpcRaiseException(v8);
    v9 = (unsigned __int8 *)v41.Level1.Buffer + v41.Level1.BufferSize;
    if ( a2 < v41.Level1.Buffer || a2 > v9 )
      SafeBuffer::RaiseShieldException((SafeBuffer *)v38, "Buffer pointer out of bounds");
    v10 = -(int)a2 & 3;
    if ( (int)v9 - (int)a2 < (unsigned int)v10 )
      SafeBuffer::RaiseShieldException((SafeBuffer *)v38, "Unexpected end of buffer during BUFFER.Increment(%lu)", v10);
    v11 = &a2[v10];
    if ( (unsigned __int64)(v9 - v11) < 4
      || (v12 = *(_DWORD *)v11, v13 = v11 + 4, v43 = v12, (unsigned __int64)(v9 - (unsigned __int8 *)v13) < 4)
      || (v14 = *v13, v15 = (char *)(v13 + 1), (unsigned __int64)(v9 - (unsigned __int8 *)v15) < 4) )
    {
      SafeBuffer::RaiseShieldException((SafeBuffer *)v38, "Unexpected end of buffer during BUFFER.Read()");
    }
    v16 = *(_DWORD *)v15;
    v17 = (_DWORD)v15 + 4;
    if ( *(_DWORD *)v15 > 0x7FFFFFFFu )
      SafeBuffer::RaiseShieldException(
        (SafeBuffer *)v38,
        "Input value(s) too large: causes addition overflow (%lu * %lu)",
        v16,
        2);
    v18 = 2 * v16;
    if ( !(unsigned int)SBGetConfigValue(1) && v18 >= 0x7FFFF000 )
      SafeBuffer::RaiseShieldException((SafeBuffer *)v38, "Input value(s) too large: suspected DoS (%lu * %lu)", v16, 2);
    if ( (int)v9 - v17 < v18 )
      SafeBuffer::RaiseShieldException((SafeBuffer *)v38, "Unexpected end of buffer during BUFFER.Increment(%lu)", v18);
    if ( v43 != v16 )
      goto LABEL_15;
    if ( v18 + 6 < v18 )
      SafeBuffer::RaiseShieldException(
        (SafeBuffer *)v38,
        "Input value(s) too large: causes addition overflow (%lu + %lu)",
        v18,
        6);
    if ( !(unsigned int)SBGetConfigValue(1) && v18 + 6 >= 0x7FFFF000 )
      SafeBuffer::RaiseShieldException((SafeBuffer *)v38, "Input value(s) too large: suspected DoS (%lu + %lu)", v18, 6);
    if ( !(unsigned int)SBGetConfigValue(5) && v14 != v18 && v14 != -1 && v14 != v18 - 1 )
LABEL_15:
      SafeBuffer::RaiseShieldException((SafeBuffer *)v38, qword_1800AD360);
    v3 = a3;
  }
  v19 = (unsigned __int64)(a2 + 3) & 0xFFFFFFFFFFFFFFFCuLL;
  if ( BufferSize < 0xC || v19 < (unsigned __int64)Buffer || BufferSize - 12 < v19 - (unsigned __int64)Buffer )
LABEL_25:
    RpcRaiseException(1783);
  v20 = *(_DWORD *)(v19 + 4);
  v21 = (BSTR)(v19 + 12);
  v22 = *(unsigned int *)(v19 + 8);
  if ( v20 == -1 )
  {
    SysFreeString(*v3);
    *v3 = 0;
    return (unsigned __int8 *)&v21[v22];
  }
  v23 = 2LL * (unsigned int)v22;
  if ( v23 > 0xFFFFFFFF )
    RpcRaiseException(-2147418096);
  if ( v21 < Buffer || BufferSize < (unsigned int)v23 || BufferSize - (unsigned int)v23 < (char *)v21 - (char *)Buffer )
    goto LABEL_25;
  v24 = v23 + 25;
  if ( (int)v23 + 25 < (unsigned int)v23 )
LABEL_35:
    RpcRaiseException(-2147024882);
  if ( !TlsGetValue(g_itlsAppData) )
  {
    if ( (int)InitAppData() < 0 )
      goto LABEL_35;
    TlsGetValue(g_itlsAppData);
  }
  v25 = v24 & 0xFFFFFFF0;
  v26 = v21;
  v27 = *(__int64 **)TlsGetValue(g_itlsAppData);
  v28 = *a3;
  if ( !*a3 )
    goto LABEL_39;
  if ( v21 == v28 )
    v26 = 0;
  v44 = v28 - 4;
  if ( v28 == (BSTR)8 )
  {
LABEL_39:
    Value = (APP_DATA *)TlsGetValue(g_itlsAppData);
    if ( Value )
      v30 = APP_DATA::AllocCachedMem(Value, v25);
    else
      v30 = (_DWORD *)(*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v27 + 24))(v27, v25);
  }
  else
  {
    v35 = RefCountMap<unsigned short *>::Get();
    v36 = *v27;
    if ( v35 )
    {
      v31 = (_DWORD *)(*(__int64 (__fastcall **)(__int64 *, _QWORD))(v36 + 24))(v27, v25);
      if ( !v31 )
        goto LABEL_35;
      if ( !v26 )
      {
        v37 = SysStringLen(*a3);
        if ( v37 > (unsigned int)v22 )
          v37 = v22;
        memcpy_0(v31 + 2, *a3, 2LL * v37);
      }
      SysReleaseString(*a3);
      goto LABEL_42;
    }
    v30 = (_DWORD *)(*(__int64 (__fastcall **)(__int64 *, BSTR, _QWORD))(v36 + 32))(v27, v44, v25);
  }
  v31 = v30;
LABEL_42:
  if ( !v31 )
    goto LABEL_35;
  *v31 = 0;
  v32 = 2 * v22;
  v31[1] = 2 * v22;
  v33 = v31 + 2;
  if ( v26 )
    memcpy_0(v33, v26, 2 * v22);
  *((_WORD *)v33 + v22) = 0;
  *a3 = (BSTR)v33;
  if ( (unsigned int)SBGetConfigValue(5) && v20 != v32 && v20 + 1 != v32 )
    v20 = 2 * v22;
  *((_DWORD *)*a3 - 1) = v20;
  return (unsigned __int8 *)&v21[v22];
}

```

## disassembly

```asm
0x18000bcb0  mov     [rsp-8+arg_0], rbx
0x18000bcb5  mov     [rsp-8+arg_10], r8
0x18000bcba  push    rbp
0x18000bcbb  push    rsi
0x18000bcbc  push    rdi
0x18000bcbd  push    r12
0x18000bcbf  push    r13
0x18000bcc1  push    r14
0x18000bcc3  push    r15
0x18000bcc5  lea     rbp, [rsp-10h]
0x18000bcca  sub     rsp, 110h
0x18000bcd1  mov     rbx, r8
0x18000bcd4  mov     r14, rdx
0x18000bcd7  mov     rdi, rcx
0x18000bcda  mov     esi, 58h ; 'X'
0x18000bcdf  mov     r8d, esi; Size
0x18000bce2  lea     rcx, [rsp+140h+pMarshalInfo]; void *
0x18000bce7  xor     edx, edx; Val
0x18000bce9  call    memset_0
0x18000bcee  lea     r15d, [rsi-57h]
0x18000bcf2  mov     rcx, rdi; pFlags
0x18000bcf5  mov     edx, r15d; InformationLevel
0x18000bcf8  lea     r8, [rsp+140h+pMarshalInfo]; pMarshalInfo
0x18000bcfd  call    cs:__imp_NdrGetUserMarshalInfo
0x18000bd03  test    eax, eax
0x18000bd05  jnz     loc_18000C03D
0x18000bd0b  mov     rax, qword ptr [rsp+140h+pMarshalInfo.8]
0x18000bd10  xor     ecx, ecx
0x18000bd12  mov     r13d, dword ptr [rsp+140h+pMarshalInfo.8+8]
0x18000bd17  mov     [rsp+140h+var_100], rax
0x18000bd1c  call    ?SBGetConfigValue@@YAHW4SBConfigValue@@@Z; SBGetConfigValue(SBConfigValue)
0x18000bd21  mov     r9d, 0FFFFFFFFh
0x18000bd27  test    eax, eax
0x18000bd29  jnz     loc_18000BE5A
0x18000bd2f  mov     r8d, esi; Size
0x18000bd32  lea     rcx, [rbp+40h+var_90]; void *
0x18000bd36  xor     edx, edx; Val
0x18000bd38  call    memset_0
0x18000bd3d  lea     r8, [rbp+40h+var_90]; pMarshalInfo
0x18000bd41  mov     edx, r15d; InformationLevel
0x18000bd44  mov     rcx, rdi; pFlags
0x18000bd47  call    cs:__imp_NdrGetUserMarshalInfo
0x18000bd4d  test    eax, eax
0x18000bd4f  jnz     loc_18000C046
0x18000bd55  mov     edi, dword ptr [rbp+40h+var_90.8+8]
0x18000bd58  add     rdi, qword ptr [rbp+40h+var_90.8]
0x18000bd5c  cmp     r14, qword ptr [rbp+40h+var_90.8]
0x18000bd60  jb      loc_18000C170
0x18000bd66  cmp     r14, rdi
0x18000bd69  ja      loc_18000C170
0x18000bd6f  mov     ecx, r14d
0x18000bd72  mov     eax, edi
0x18000bd74  neg     ecx
0x18000bd76  sub     eax, r14d
0x18000bd79  and     ecx, 3
0x18000bd7c  cmp     eax, ecx
0x18000bd7e  jb      loc_18000C04F
0x18000bd84  add     rcx, r14
0x18000bd87  mov     rax, rdi
0x18000bd8a  sub     rax, rcx
0x18000bd8d  cmp     rax, 4
0x18000bd91  jb      loc_18000C15E
0x18000bd97  mov     eax, [rcx]
0x18000bd99  add     rcx, 4
0x18000bd9d  mov     dword ptr [rbp+40h+arg_18], eax
0x18000bda0  mov     rax, rdi
0x18000bda3  sub     rax, rcx
0x18000bda6  cmp     rax, 4
0x18000bdaa  jb      loc_18000C15E
0x18000bdb0  mov     r15d, [rcx]
0x18000bdb3  mov     rax, rdi
0x18000bdb6  add     rcx, 4
0x18000bdba  sub     rax, rcx
0x18000bdbd  cmp     rax, 4
0x18000bdc1  jb      loc_18000C15E
0x18000bdc7  mov     esi, [rcx]
0x18000bdc9  lea     r12, [rcx+4]
0x18000bdcd  cmp     esi, 7FFFFFFFh
0x18000bdd3  ja      loc_18000C064
0x18000bdd9  mov     ecx, 1
0x18000bdde  lea     ebx, [rsi+rsi]
0x18000bde1  call    ?SBGetConfigValue@@YAHW4SBConfigValue@@@Z; SBGetConfigValue(SBConfigValue)
0x18000bde6  test    eax, eax
0x18000bde8  jnz     short loc_18000BDF6
0x18000bdea  cmp     ebx, 7FFFF000h
0x18000bdf0  jnb     loc_18000C07F
0x18000bdf6  sub     edi, r12d
0x18000bdf9  cmp     edi, ebx
0x18000bdfb  jb      loc_18000C09A
0x18000be01  cmp     dword ptr [rbp+40h+arg_18], esi
0x18000be04  jz      short loc_18000BE18
0x18000be06  lea     rdx, qword_1800AD360; char *
0x18000be0d  lea     rcx, [rsp+140h+var_120]; this
0x18000be12  call    ?RaiseShieldException@SafeBuffer@@QEAAXPEBDZZ; SafeBuffer::RaiseShieldException(char const *,...)
0x18000be18  lea     edi, [rbx+6]
0x18000be1b  cmp     edi, ebx
0x18000be1d  jb      loc_18000C0AF
0x18000be23  mov     ecx, 1
0x18000be28  call    ?SBGetConfigValue@@YAHW4SBConfigValue@@@Z; SBGetConfigValue(SBConfigValue)
0x18000be2d  test    eax, eax
0x18000be2f  jnz     short loc_18000BE3D
0x18000be31  cmp     edi, 7FFFF000h
0x18000be37  jnb     loc_18000C0CA
0x18000be3d  mov     ecx, 5
0x18000be42  call    ?SBGetConfigValue@@YAHW4SBConfigValue@@@Z; SBGetConfigValue(SBConfigValue)
0x18000be47  mov     r9d, 0FFFFFFFFh
0x18000be4d  test    eax, eax
0x18000be4f  jnz     short loc_18000BE56
0x18000be51  cmp     r15d, ebx
0x18000be54  jnz     short loc_18000BE8D
0x18000be56  mov     rbx, [rbp+40h+arg_10]
0x18000be5a  lea     rdx, [r14+3]
0x18000be5e  and     rdx, 0FFFFFFFFFFFFFFFCh
0x18000be62  cmp     r13, 0Ch
0x18000be66  jb      short loc_18000BE81
0x18000be68  mov     r8, [rsp+140h+var_100]
0x18000be6d  cmp     rdx, r8
0x18000be70  jb      short loc_18000BE81
0x18000be72  mov     rcx, rdx
0x18000be75  lea     rax, [r13-0Ch]
0x18000be79  sub     rcx, r8
0x18000be7c  cmp     rax, rcx
0x18000be7f  jnb     short loc_18000BEA0
0x18000be81  mov     ecx, 6F7h; exception
0x18000be86  call    cs:__imp_RpcRaiseException
0x18000be8c  int     3; Trap to Debugger
0x18000be8d  cmp     r15d, r9d
0x18000be90  jz      short loc_18000BE56
0x18000be92  lea     eax, [rbx-1]
0x18000be95  cmp     r15d, eax
0x18000be98  jnz     loc_18000BE06
0x18000be9e  jmp     short loc_18000BE56
0x18000bea0  mov     esi, [rdx+4]
0x18000bea3  lea     r12, [rdx+0Ch]
0x18000bea7  mov     r15d, [rdx+8]
0x18000beab  cmp     esi, r9d
0x18000beae  jz      short loc_18000BEEC
0x18000beb0  mov     eax, r15d
0x18000beb3  add     rax, rax
0x18000beb6  cmp     rax, r9
0x18000beb9  ja      loc_18000BFCF
0x18000bebf  mov     ecx, eax
0x18000bec1  cmp     r12, r8
0x18000bec4  jb      short loc_18000BE81
0x18000bec6  cmp     r13, rcx
0x18000bec9  jb      short loc_18000BE81
0x18000becb  mov     rax, r12
0x18000bece  sub     r13, rcx
0x18000bed1  sub     rax, r8
0x18000bed4  cmp     r13, rax
0x18000bed7  jb      short loc_18000BE81
0x18000bed9  lea     ebx, [rcx+19h]
0x18000bedc  cmp     ebx, ecx
0x18000bede  jnb     short loc_18000BF00
0x18000bee0  mov     ecx, 8007000Eh; exception
0x18000bee5  call    cs:__imp_RpcRaiseException
0x18000beeb  int     3; Trap to Debugger
0x18000beec  mov     rcx, [rbx]; bstrString
0x18000beef  call    SysFreeString
0x18000bef4  mov     qword ptr [rbx], 0
0x18000befb  jmp     loc_18000BFB0
0x18000bf00  mov     ecx, cs:?g_itlsAppData@@3KA; dwTlsIndex
0x18000bf06  call    cs:__imp_TlsGetValue
0x18000bf0c  test    rax, rax
0x18000bf0f  jz      loc_18000C01F
0x18000bf15  mov     ecx, cs:?g_itlsAppData@@3KA; dwTlsIndex
0x18000bf1b  and     ebx, 0FFFFFFF0h
0x18000bf1e  call    cs:__imp_TlsGetValue
0x18000bf24  mov     r13, [rbp+40h+arg_10]
0x18000bf28  mov     rdi, r12
0x18000bf2b  mov     r14, [rax]
0x18000bf2e  mov     rdx, [r13+0]
0x18000bf32  test    rdx, rdx
0x18000bf35  jnz     loc_18000BFDB
0x18000bf3b  mov     ecx, cs:?g_itlsAppData@@3KA; dwTlsIndex
0x18000bf41  call    cs:__imp_TlsGetValue
0x18000bf47  test    rax, rax
0x18000bf4a  jz      loc_18000C130
0x18000bf50  mov     edx, ebx; unsigned int
0x18000bf52  mov     rcx, rax; this
0x18000bf55  call    ?AllocCachedMem@APP_DATA@@QEAAPEAXK@Z; APP_DATA::AllocCachedMem(ulong)
0x18000bf5a  mov     rbx, rax
0x18000bf5d  test    rbx, rbx
0x18000bf60  jz      loc_18000BEE0
0x18000bf66  mov     dword ptr [rbx], 0
0x18000bf6c  lea     r14d, [r15+r15]
0x18000bf70  mov     [rbx+4], r14d
0x18000bf74  add     rbx, 8
0x18000bf78  test    rdi, rdi
0x18000bf7b  jz      short loc_18000BF8E
0x18000bf7d  mov     r8, r15
0x18000bf80  mov     rdx, rdi; Src
0x18000bf83  add     r8, r8; Size
0x18000bf86  mov     rcx, rbx; void *
0x18000bf89  call    memcpy_0
0x18000bf8e  xor     eax, eax
0x18000bf90  mov     [rbx+r15*2], ax
0x18000bf95  mov     [r13+0], rbx
0x18000bf99  lea     ecx, [rax+5]
0x18000bf9c  call    ?SBGetConfigValue@@YAHW4SBConfigValue@@@Z; SBGetConfigValue(SBConfigValue)
0x18000bfa1  test    eax, eax
0x18000bfa3  jnz     loc_18000C146
0x18000bfa9  mov     rax, [r13+0]
0x18000bfad  mov     [rax-4], esi
0x18000bfb0  mov     rbx, [rsp+140h+arg_0]
0x18000bfb8  lea     rax, [r12+r15*2]
0x18000bfbc  add     rsp, 110h
0x18000bfc3  pop     r15
0x18000bfc5  pop     r14
0x18000bfc7  pop     r13
0x18000bfc9  pop     r12
0x18000bfcb  pop     rdi
0x18000bfcc  pop     rsi
0x18000bfcd  pop     rbp
0x18000bfce  retn
0x18000bfcf  mov     ecx, 80010010h; exception
0x18000bfd4  call    cs:__imp_RpcRaiseException
0x18000bfda  int     3; Trap to Debugger
0x18000bfdb  xor     eax, eax
0x18000bfdd  cmp     rdi, rdx
0x18000bfe0  cmovz   rdi, rax
0x18000bfe4  lea     rax, [rdx-8]
0x18000bfe8  mov     [rbp+40h+arg_18], rax
0x18000bfec  test    rax, rax
0x18000bfef  jz      loc_18000BF3B
0x18000bff5  call    ?Get@?$RefCountMap@PEAG@@QEAAHPEAG@Z; RefCountMap<ushort *>::Get(ushort *)
0x18000bffa  mov     r9, [r14]
0x18000bffd  mov     rcx, r14
0x18000c000  mov     edx, ebx
0x18000c002  test    eax, eax
0x18000c004  jnz     loc_18000C0E5
0x18000c00a  mov     rax, [r9+20h]
0x18000c00e  mov     r8d, edx
0x18000c011  mov     rdx, [rbp+40h+arg_18]
0x18000c015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c01a  jmp     loc_18000BF5A
0x18000c01f  call    InitAppData
0x18000c024  test    eax, eax
0x18000c026  js      loc_18000BEE0
0x18000c02c  mov     ecx, cs:?g_itlsAppData@@3KA; dwTlsIndex
0x18000c032  call    cs:__imp_TlsGetValue
0x18000c038  jmp     loc_18000BF15
0x18000c03d  mov     ecx, eax; exception
0x18000c03f  call    cs:__imp_RpcRaiseException
0x18000c045  int     3; Trap to Debugger
0x18000c046  mov     ecx, eax; exception
0x18000c048  call    cs:__imp_RpcRaiseException
0x18000c04e  int     3; Trap to Debugger
0x18000c04f  mov     r8d, ecx
0x18000c052  lea     rdx, aUnexpectedEndO_0; "Unexpected end of buffer during BUFFER."...
0x18000c059  lea     rcx, [rsp+140h+var_120]; this
0x18000c05e  call    ?RaiseShieldException@SafeBuffer@@QEAAXPEBDZZ; SafeBuffer::RaiseShieldException(char const *,...)
0x18000c064  mov     r9d, 2
0x18000c06a  lea     rdx, aInputValueSToo_1; "Input value(s) too large: causes additi"...
0x18000c071  mov     r8d, esi
0x18000c074  lea     rcx, [rsp+140h+var_120]; this
0x18000c079  call    ?RaiseShieldException@SafeBuffer@@QEAAXPEBDZZ; SafeBuffer::RaiseShieldException(char const *,...)
0x18000c07f  mov     r9d, 2
0x18000c085  lea     rdx, aInputValueSToo_0; "Input value(s) too large: suspected DoS"...
0x18000c08c  mov     r8d, esi
0x18000c08f  lea     rcx, [rsp+140h+var_120]; this
0x18000c094  call    ?RaiseShieldException@SafeBuffer@@QEAAXPEBDZZ; SafeBuffer::RaiseShieldException(char const *,...)
0x18000c09a  mov     r8d, ebx
0x18000c09d  lea     rdx, aUnexpectedEndO_0; "Unexpected end of buffer during BUFFER."...
0x18000c0a4  lea     rcx, [rsp+140h+var_120]; this
0x18000c0a9  call    ?RaiseShieldException@SafeBuffer@@QEAAXPEBDZZ; SafeBuffer::RaiseShieldException(char const *,...)
0x18000c0af  mov     r9d, 6
0x18000c0b5  lea     rdx, aInputValueSToo_2; "Input value(s) too large: causes additi"...
0x18000c0bc  mov     r8d, ebx
0x18000c0bf  lea     rcx, [rsp+140h+var_120]; this
0x18000c0c4  call    ?RaiseShieldException@SafeBuffer@@QEAAXPEBDZZ; SafeBuffer::RaiseShieldException(char const *,...)
0x18000c0ca  mov     r9d, 6
0x18000c0d0  lea     rdx, aInputValueSToo; "Input value(s) too large: suspected DoS"...
0x18000c0d7  mov     r8d, ebx
0x18000c0da  lea     rcx, [rsp+140h+var_120]; this
0x18000c0df  call    ?RaiseShieldException@SafeBuffer@@QEAAXPEBDZZ; SafeBuffer::RaiseShieldException(char const *,...)
0x18000c0e5  mov     rax, [r9+18h]
0x18000c0e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0ee  mov     rbx, rax
0x18000c0f1  test    rax, rax
0x18000c0f4  jz      loc_18000BEE0
0x18000c0fa  test    rdi, rdi
0x18000c0fd  jnz     short loc_18000C122
0x18000c0ff  mov     rcx, [r13+0]; pbstr
0x18000c103  call    SysStringLen
0x18000c108  mov     rdx, [r13+0]; Src
0x18000c10c  lea     rcx, [rbx+8]; void *
0x18000c110  cmp     eax, r15d
0x18000c113  cmova   eax, r15d
0x18000c117  mov     r8d, eax
0x18000c11a  add     r8, r8; Size
0x18000c11d  call    memcpy_0
0x18000c122  mov     rcx, [r13+0]; bstrString
0x18000c126  call    SysReleaseString
0x18000c12b  jmp     loc_18000BF5D
0x18000c130  mov     rax, [r14]
0x18000c133  mov     rcx, r14
0x18000c136  mov     edx, ebx
0x18000c138  mov     rax, [rax+18h]
0x18000c13c  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
