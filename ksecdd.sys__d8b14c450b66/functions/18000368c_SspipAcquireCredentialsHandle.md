# SspipAcquireCredentialsHandle

- ea: `0x18000368c`
- end: `0x180003a4c`
- name: `SspipAcquireCredentialsHandle`
- size: `960`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, int, __int64, __int64, __int64, int, _OWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180027738`

## callees

- `0x18000368c`
- `0x180004050`
- `0x180004074`
- `0x180010840`
- `0x180010920`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x1800037a6`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1800037a6`
- `ntoskrnl!PsGetCurrentProcess` at `0x180003783`
- `ntoskrnl!PsGetCurrentProcess` at `0x180003783`
- `ntoskrnl!PsGetProcessId` at `0x180003792`
- `ntoskrnl!PsGetProcessId` at `0x180003792`
- `msrpc!NdrClientCall3` at `0x1800038a2`
- `msrpc!NdrClientCall3` at `0x1800038a2`
- `msrpc!I_RpcExceptionFilter` at `0x1800112fc`
- `msrpc!I_RpcExceptionFilter` at `0x1800112fc`

## pseudocode

```c
__int64 __fastcall SspipAcquireCredentialsHandle(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        int a9,
        _OWORD *a10,
        __int64 *a11)
{
  __int64 result; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  struct _KPROCESS *CurrentProcess; // rax
  __int64 *v19; // rcx
  CLIENT_CALL_RETURN v20; // rax
  int Pointer; // ebx
  _BYTE *v22; // rcx
  __int64 v23; // rsi
  __int64 v24; // rcx
  __int128 *v25; // rax
  _BYTE *v26; // rcx
  __int128 *v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v31; // [rsp+98h] [rbp-120h] BYREF
  __int64 v32; // [rsp+A0h] [rbp-118h]
  __int64 v33; // [rsp+A8h] [rbp-110h]
  __int64 v34; // [rsp+B0h] [rbp-108h]
  __int64 v35; // [rsp+B8h] [rbp-100h] BYREF
  __int128 v36; // [rsp+C0h] [rbp-F8h] BYREF
  __int64 v37; // [rsp+D0h] [rbp-E8h]
  CLIENT_CALL_RETURN v38; // [rsp+D8h] [rbp-E0h]
  _OWORD *v39; // [rsp+E0h] [rbp-D8h]
  __int128 v40; // [rsp+F0h] [rbp-C8h] BYREF
  __int128 v41; // [rsp+100h] [rbp-B8h]
  PVOID DataBuffer[2]; // [rsp+110h] [rbp-A8h]
  __int128 v43; // [rsp+120h] [rbp-98h] BYREF
  __int128 v44; // [rsp+130h] [rbp-88h]
  __int128 v45; // [rsp+140h] [rbp-78h]
  __int128 v46; // [rsp+150h] [rbp-68h] BYREF
  __int128 v47; // [rsp+160h] [rbp-58h] BYREF

  v34 = a4;
  v33 = a7;
  v32 = a8;
  v39 = a10;
  v35 = 0;
  v31 = 0;
  v46 = 0;
  v36 = 0;
  v37 = 0;
  v47 = 0;
  v40 = 0;
  v41 = 0;
  *(_OWORD *)DataBuffer = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  result = IsOkayToExecRpc(&v35);
  if ( (int)result >= 0 )
  {
    CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess(v15, v14, v16, v17);
    *(_QWORD *)&v46 = PsGetProcessId(CurrentProcess);
    *((_QWORD *)&v46 + 1) = PsGetCurrentThreadId();
    v19 = &v31;
    if ( a11 )
      v19 = a11;
    LODWORD(v36) = a5;
    *((_QWORD *)&v36 + 1) = a6;
    v37 = a6;
    if ( *(_QWORD *)&WPP_MAIN_CB.DeviceType )
    {
      Pointer = (*(__int64 (__fastcall **)(_QWORD, __int128 *, __int64, __int64, int, __int64, __int128 *, __int64, __int64, _DWORD, __int128 *, __int64 *, _QWORD, _QWORD))(*(_QWORD *)&WPP_MAIN_CB.DeviceType + 8LL))(
                  0,
                  &v46,
                  a1,
                  a2,
                  a3,
                  v34,
                  &v36,
                  v33,
                  v32,
                  0,
                  &v47,
                  v19,
                  0,
                  0);
    }
    else
    {
      v38.Simple = 0;
      v20.Pointer = NdrClientCall3(
                      (MIDL_STUBLESS_PROXY_INFO *)&sspirpc_ProxyInfo,
                      4u,
                      0,
                      v35,
                      &v46,
                      a1,
                      a2,
                      a3,
                      v34,
                      &v36,
                      v33,
                      v32,
                      0,
                      &v47,
                      v19,
                      &v40,
                      &v43).Pointer;
      Pointer = (int)v20.Pointer;
      v38.Pointer = v20.Pointer;
    }
    if ( Pointer >= 0 )
    {
      *a10 = v47;
      Pointer = 0;
    }
    v22 = DataBuffer[0];
    if ( DataBuffer[0] )
    {
      v28 = DWORD2(v41);
      if ( DWORD2(v41) )
      {
        do
        {
          *v22++ = 0;
          --v28;
        }
        while ( v28 );
        v22 = DataBuffer[0];
      }
      SspiLocalFree(v22);
    }
    v23 = 48;
    v24 = 48;
    v25 = &v40;
    do
    {
      *(_BYTE *)v25 = 0;
      v25 = (__int128 *)((char *)v25 + 1);
      --v24;
    }
    while ( v24 );
    v26 = (_BYTE *)v45;
    if ( (_QWORD)v45 )
    {
      v29 = DWORD2(v44);
      if ( DWORD2(v44) )
      {
        do
        {
          *v26++ = 0;
          --v29;
        }
        while ( v29 );
        v26 = (_BYTE *)v45;
      }
      SspiLocalFree(v26);
    }
    v27 = &v43;
    do
    {
      *(_BYTE *)v27 = 0;
      v27 = (__int128 *)((char *)v27 + 1);
      --v23;
    }
    while ( v23 );
    return (unsigned int)Pointer;
  }
  return result;
}

```

## disassembly

```asm
0x18000368c  mov     r11, rsp
0x18000368f  push    rbx
0x180003690  push    rsi
0x180003691  push    r12
0x180003693  push    r13
0x180003695  push    r14
0x180003697  push    r15
0x180003699  sub     rsp, 188h
0x1800036a0  mov     rax, cs:__security_cookie
0x1800036a7  xor     rax, rsp
0x1800036aa  mov     [rsp+1B8h+var_48], rax
0x1800036b2  mov     [rsp+1B8h+var_108], r9
0x1800036ba  mov     [rsp+1B8h+var_128], r8d
0x1800036c2  mov     r13, rdx
0x1800036c5  mov     r12, rcx
0x1800036c8  mov     r15, [rsp+1B8h+arg_50]
0x1800036d0  mov     rsi, [rsp+1B8h+arg_48]
0x1800036d8  mov     rbx, [rsp+1B8h+arg_28]
0x1800036e0  mov     rax, [rsp+1B8h+arg_30]
0x1800036e8  mov     [rsp+1B8h+var_110], rax
0x1800036f0  mov     rax, [rsp+1B8h+arg_38]
0x1800036f8  mov     [rsp+1B8h+var_118], rax
0x180003700  mov     r14, rsi
0x180003703  mov     [rsp+1B8h+var_D8], rsi
0x18000370b  mov     qword ptr [r11-100h], 0
0x180003716  mov     qword ptr [r11-120h], 0
0x180003721  xorps   xmm0, xmm0
0x180003724  movups  xmmword ptr [r11-68h], xmm0
0x180003729  xorps   xmm1, xmm1
0x18000372c  xor     eax, eax
0x18000372e  movups  [rsp+1B8h+var_F8], xmm1
0x180003736  mov     [r11-0E8h], rax
0x18000373d  movups  xmmword ptr [r11-58h], xmm0
0x180003742  movups  [rsp+1B8h+var_C8], xmm1
0x18000374a  movups  [rsp+1B8h+var_B8], xmm1
0x180003752  movups  xmmword ptr [rsp+1B8h+DataBuffer], xmm1
0x18000375a  movups  [rsp+1B8h+var_98], xmm0
0x180003762  movups  [rsp+1B8h+var_88], xmm0
0x18000376a  movups  xmmword ptr [r11-78h], xmm0
0x18000376f  lea     rcx, [r11-100h]
0x180003776  call    IsOkayToExecRpc
0x18000377b  test    eax, eax
0x18000377d  js      loc_180003946
0x180003783  call    cs:__imp_PsGetCurrentProcess
0x18000378a  nop     dword ptr [rax+rax+00h]
0x18000378f  mov     rcx, rax; Process
0x180003792  call    cs:__imp_PsGetProcessId
0x180003799  nop     dword ptr [rax+rax+00h]
0x18000379e  mov     [rsp+1B8h+var_68], rax
0x1800037a6  call    cs:__imp_PsGetCurrentThreadId
0x1800037ad  nop     dword ptr [rax+rax+00h]
0x1800037b2  mov     [rsp+1B8h+var_60], rax
0x1800037ba  lea     rcx, [rsp+1B8h+var_120]
0x1800037c2  test    r15, r15
0x1800037c5  cmovnz  rcx, r15
0x1800037c9  mov     eax, [rsp+1B8h+arg_20]
0x1800037d0  mov     dword ptr [rsp+1B8h+var_F8], eax
0x1800037d7  mov     qword ptr [rsp+1B8h+var_F8+8], rbx
0x1800037df  mov     [rsp+1B8h+var_E8], rbx
0x1800037e7  mov     rax, qword ptr cs:WPP_MAIN_CB.DeviceType
0x1800037ee  test    rax, rax
0x1800037f1  jnz     loc_180003969
0x1800037f7  mov     [rsp+1B8h+var_E0], rax
0x1800037ff  lea     rax, [rsp+1B8h+var_98]
0x180003807  mov     [rsp+1B8h+var_138], rax
0x18000380f  lea     rax, [rsp+1B8h+var_C8]
0x180003817  mov     [rsp+1B8h+var_140], rax
0x18000381c  mov     [rsp+1B8h+var_148], rcx
0x180003821  lea     rax, [rsp+1B8h+var_58]
0x180003829  mov     [rsp+1B8h+var_150], rax
0x18000382e  mov     dword ptr [rsp+1B8h+var_158], 0
0x180003836  mov     rcx, [rsp+1B8h+var_118]
0x18000383e  mov     [rsp+1B8h+var_160], rcx
0x180003843  mov     rcx, [rsp+1B8h+var_110]
0x18000384b  mov     [rsp+1B8h+var_168], rcx
0x180003850  lea     rax, [rsp+1B8h+var_F8]
0x180003858  mov     [rsp+1B8h+var_170], rax
0x18000385d  mov     rcx, [rsp+1B8h+var_108]
0x180003865  mov     [rsp+1B8h+var_178], rcx
0x18000386a  mov     ecx, [rsp+1B8h+var_128]
0x180003871  mov     dword ptr [rsp+1B8h+var_180], ecx
0x180003875  mov     [rsp+1B8h+var_188], r13
0x18000387a  mov     [rsp+1B8h+var_190], r12
0x18000387f  lea     rax, [rsp+1B8h+var_68]
0x180003887  mov     [rsp+1B8h+var_198], rax
0x18000388c  mov     r9, [rsp+1B8h+var_100]
0x180003894  xor     r8d, r8d; pReturnValue
0x180003897  lea     edx, [r8+4]; nProcNum
0x18000389b  lea     rcx, ?sspirpc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800038a2  call    cs:__imp_NdrClientCall3
0x1800038a9  nop     dword ptr [rax+rax+00h]
0x1800038ae  mov     rbx, rax
0x1800038b1  mov     [rsp+1B8h+var_E0], rax
0x1800038b9  mov     [rsp+1B8h+var_124], eax
0x1800038c0  jmp     short loc_1800038D6
0x1800038c2  mov     ebx, eax
0x1800038c4  mov     [rsp+1B8h+var_124], eax
0x1800038cb  mov     r14, [rsp+1B8h+var_D8]
0x1800038d3  mov     rsi, r14
0x1800038d6  test    ebx, ebx
0x1800038d8  js      short loc_1800038F3
0x1800038da  mov     rax, [rsp+1B8h+var_58]
0x1800038e2  mov     [rsi], rax
0x1800038e5  mov     rax, [rsp+1B8h+var_50]
0x1800038ed  mov     [r14+8], rax
0x1800038f1  xor     ebx, ebx
0x1800038f3  mov     rcx, [rsp+1B8h+DataBuffer]; DataBuffer
0x1800038fb  test    rcx, rcx
0x1800038fe  jnz     loc_1800039F4
0x180003904  mov     esi, 30h ; '0'
0x180003909  mov     ecx, esi
0x18000390b  lea     rax, [rsp+1B8h+var_C8]
0x180003913  mov     byte ptr [rax], 0
0x180003916  inc     rax
0x180003919  sub     rcx, 1
0x18000391d  jnz     short loc_180003913
0x18000391f  mov     rcx, qword ptr [rsp+1B8h+var_78]; DataBuffer
0x180003927  test    rcx, rcx
0x18000392a  jnz     loc_180003A0A
0x180003930  lea     rax, [rsp+1B8h+var_98]
0x180003938  mov     byte ptr [rax], 0
0x18000393b  inc     rax
0x18000393e  sub     rsi, 1
0x180003942  jnz     short loc_180003938
0x180003944  mov     eax, ebx
0x180003946  mov     rcx, [rsp+1B8h+var_48]
0x18000394e  xor     rcx, rsp; StackCookie
0x180003951  call    __security_check_cookie
0x180003956  add     rsp, 188h
0x18000395d  pop     r15
0x18000395f  pop     r14
0x180003961  pop     r13
0x180003963  pop     r12
0x180003965  pop     rsi
0x180003966  pop     rbx
0x180003967  retn
0x180003969  mov     rax, [rax+8]
0x18000396d  mov     [rsp+1B8h+var_150], 0
0x180003976  mov     [rsp+1B8h+var_158], 0
0x18000397f  mov     [rsp+1B8h+var_160], rcx
0x180003984  lea     rcx, [rsp+1B8h+var_58]
0x18000398c  mov     [rsp+1B8h+var_168], rcx
0x180003991  mov     dword ptr [rsp+1B8h+var_170], 0
0x180003999  mov     rcx, [rsp+1B8h+var_118]
0x1800039a1  mov     [rsp+1B8h+var_178], rcx
0x1800039a6  mov     rcx, [rsp+1B8h+var_110]
0x1800039ae  mov     [rsp+1B8h+var_180], rcx
0x1800039b3  lea     rcx, [rsp+1B8h+var_F8]
0x1800039bb  mov     [rsp+1B8h+var_188], rcx
0x1800039c0  mov     rcx, [rsp+1B8h+var_108]
0x1800039c8  mov     [rsp+1B8h+var_190], rcx
0x1800039cd  mov     ecx, [rsp+1B8h+var_128]
0x1800039d4  mov     dword ptr [rsp+1B8h+var_198], ecx
0x1800039d8  mov     r9, r13
0x1800039db  mov     r8, r12
0x1800039de  lea     rdx, [rsp+1B8h+var_68]
0x1800039e6  xor     ecx, ecx
0x1800039e8  call    _guard_dispatch_icall
0x1800039ed  mov     ebx, eax
0x1800039ef  jmp     loc_1800038D6
0x1800039f4  mov     eax, dword ptr [rsp+1B8h+var_B8+8]
0x1800039fb  test    rax, rax
0x1800039fe  jnz     short loc_180003A20
0x180003a00  call    SspiLocalFree
0x180003a05  jmp     loc_180003904
0x180003a0a  mov     eax, dword ptr [rsp+1B8h+var_88+8]
0x180003a11  test    rax, rax
0x180003a14  jnz     short loc_180003A36
0x180003a16  call    SspiLocalFree
0x180003a1b  jmp     loc_180003930
0x180003a20  mov     byte ptr [rcx], 0
0x180003a23  inc     rcx
0x180003a26  sub     rax, 1
0x180003a2a  jnz     short loc_180003A20
0x180003a2c  mov     rcx, [rsp+1B8h+DataBuffer]
0x180003a34  jmp     short loc_180003A00
0x180003a36  mov     byte ptr [rcx], 0
0x180003a39  inc     rcx
0x180003a3c  sub     rax, 1
0x180003a40  jnz     short loc_180003A36
0x180003a42  mov     rcx, qword ptr [rsp+1B8h+var_78]
0x180003a4a  jmp     short loc_180003A16
0x1800112eb  push    rbp
0x1800112ed  sub     rsp, 90h
0x1800112f4  mov     rbp, rdx
0x1800112f7  mov     rcx, [rcx]
0x1800112fa  mov     ecx, [rcx]; ExceptionCode
0x1800112fc  call    cs:__imp_I_RpcExceptionFilter
0x180011303  nop     dword ptr [rax+rax+00h]
0x180011308  nop
0x180011309  add     rsp, 90h
0x180011310  pop     rbp
0x180011311  retn
```
