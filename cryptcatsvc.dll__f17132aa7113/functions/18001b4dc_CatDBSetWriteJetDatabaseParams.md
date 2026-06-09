# _CatDBSetWriteJetDatabaseParams

- ea: `0x18001b4dc`
- end: `0x18001b619`
- name: `_CatDBSetWriteJetDatabaseParams`
- size: `317`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180017a04`
- `0x180019314`
- `0x18001966c`
- `0x18001a694`
- `0x18001b8f4`

## callees

- `0x1800038f0`
- `0x18000a59c`
- `0x18000acbc`
- `0x18001b4dc`

## import_xrefs

- `ESENT!JetSetSystemParameterW` at `0x18001b520`
- `ESENT!JetSetSystemParameterW` at `0x18001b54f`
- `ESENT!JetSetSystemParameterW` at `0x18001b57e`
- `ESENT!JetSetSystemParameterW` at `0x18001b5a9`
- `ESENT!JetSetSystemParameterW` at `0x18001b5d4`
- `ESENT!JetSetSystemParameterW` at `0x18001b520`
- `ESENT!JetSetSystemParameterW` at `0x18001b54f`
- `ESENT!JetSetSystemParameterW` at `0x18001b57e`
- `ESENT!JetSetSystemParameterW` at `0x18001b5a9`
- `ESENT!JetSetSystemParameterW` at `0x18001b5d4`

## pseudocode

```c
void CatDBSetWriteJetDatabaseParams()
{
  JET_ERR v0; // ebx
  unsigned int v1; // eax
  unsigned int v2; // edx
  unsigned __int16 *v3; // rcx
  int v4; // [rsp+28h] [rbp-10h]

  if ( !g_fHasWriteJetDatabaseParams && g_JetInstance )
  {
    v0 = JetSetSystemParameterW(&g_JetInstance, 0, 0x17u, 0x20000u, 0);
    if ( (unsigned int)_CatDBJET_errFailure(v0)
      || (v0 = JetSetSystemParameterW(&g_JetInstance, 0, 0x3Cu, 0x200u, 0), (unsigned int)_CatDBJET_errFailure(v0))
      || (v0 = JetSetSystemParameterW(&g_JetInstance, 0, 0x12u, 0x100u, 0), (unsigned int)_CatDBJET_errFailure(v0))
      || (v0 = JetSetSystemParameterW(&g_JetInstance, 0, 0x20u, 0xA3Du, 0), (unsigned int)_CatDBJET_errFailure(v0))
      || (v0 = JetSetSystemParameterW(&g_JetInstance, 0, 0x1Fu, 0x51Eu, 0), (unsigned int)_CatDBJET_errFailure(v0)) )
    {
      v1 = _CatDBMapJetError(v0);
      ErrLog_LogError(v3, v2, 0x1736u, v1, 0, v4);
    }
    g_fHasWriteJetDatabaseParams = 1;
  }
}

```

## disassembly

```asm
0x18001b4dc  mov     [rsp+arg_0], rbx
0x18001b4e1  push    rsi
0x18001b4e2  sub     rsp, 30h
0x18001b4e6  cmp     cs:?g_fHasWriteJetDatabaseParams@@3HA, 0; int g_fHasWriteJetDatabaseParams
0x18001b4ed  jnz     loc_18001B60E
0x18001b4f3  cmp     cs:?g_JetInstance@@3_KA, 0; unsigned __int64 g_JetInstance
0x18001b4fb  jz      loc_18001B60E
0x18001b501  xor     edx, edx; sesid
0x18001b503  mov     [rsp+38h+szParam], 0; szParam
0x18001b50c  lea     rsi, ?g_JetInstance@@3_KA; unsigned __int64 g_JetInstance
0x18001b513  mov     r9d, 20000h; lParam
0x18001b519  mov     rcx, rsi; pinstance
0x18001b51c  lea     r8d, [rdx+17h]; paramid
0x18001b520  call    cs:__imp_JetSetSystemParameterW
0x18001b526  mov     ecx, eax; int
0x18001b528  mov     ebx, eax
0x18001b52a  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18001b52f  test    eax, eax
0x18001b531  jnz     loc_18001B5E7
0x18001b537  xor     edx, edx; sesid
0x18001b539  mov     [rsp+38h+szParam], 0; szParam
0x18001b542  mov     r9d, 200h; lParam
0x18001b548  lea     r8d, [rax+3Ch]; paramid
0x18001b54c  mov     rcx, rsi; pinstance
0x18001b54f  call    cs:__imp_JetSetSystemParameterW
0x18001b555  mov     ecx, eax; int
0x18001b557  mov     ebx, eax
0x18001b559  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18001b55e  test    eax, eax
0x18001b560  jnz     loc_18001B5E7
0x18001b566  xor     edx, edx; sesid
0x18001b568  mov     [rsp+38h+szParam], 0; szParam
0x18001b571  mov     r9d, 100h; lParam
0x18001b577  lea     r8d, [rax+12h]; paramid
0x18001b57b  mov     rcx, rsi; pinstance
0x18001b57e  call    cs:__imp_JetSetSystemParameterW
0x18001b584  mov     ecx, eax; int
0x18001b586  mov     ebx, eax
0x18001b588  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18001b58d  test    eax, eax
0x18001b58f  jnz     short loc_18001B5E7
0x18001b591  xor     edx, edx; sesid
0x18001b593  mov     [rsp+38h+szParam], 0; szParam
0x18001b59c  mov     r9d, 0A3Dh; lParam
0x18001b5a2  lea     r8d, [rax+20h]; paramid
0x18001b5a6  mov     rcx, rsi; pinstance
0x18001b5a9  call    cs:__imp_JetSetSystemParameterW
0x18001b5af  mov     ecx, eax; int
0x18001b5b1  mov     ebx, eax
0x18001b5b3  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18001b5b8  test    eax, eax
0x18001b5ba  jnz     short loc_18001B5E7
0x18001b5bc  xor     edx, edx; sesid
0x18001b5be  mov     [rsp+38h+szParam], 0; szParam
0x18001b5c7  mov     r9d, 51Eh; lParam
0x18001b5cd  lea     r8d, [rax+1Fh]; paramid
0x18001b5d1  mov     rcx, rsi; pinstance
0x18001b5d4  call    cs:__imp_JetSetSystemParameterW
0x18001b5da  mov     ecx, eax; int
0x18001b5dc  mov     ebx, eax
0x18001b5de  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18001b5e3  test    eax, eax
0x18001b5e5  jz      short loc_18001B604
0x18001b5e7  mov     ecx, ebx; int
0x18001b5e9  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x18001b5ee  mov     r9d, eax; unsigned int
0x18001b5f1  mov     dword ptr [rsp+38h+szParam], 0; int
0x18001b5f9  mov     r8d, 1736h; unsigned int
0x18001b5ff  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001b604  mov     cs:?g_fHasWriteJetDatabaseParams@@3HA, 1; int g_fHasWriteJetDatabaseParams
0x18001b60e  mov     rbx, [rsp+38h+arg_0]
0x18001b613  add     rsp, 30h
0x18001b617  pop     rsi
0x18001b618  retn
```
