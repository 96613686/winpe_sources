# WinPlatformW8TbsSubmit(void *,uchar * const,uint,uchar *,uint *)

- ea: `0x1800de320`
- end: `0x1800de3d9`
- name: `?WinPlatformW8TbsSubmit@@YAIPEAXQEAEIPEAEPEAI@Z`
- size: `185`
- prototype: `unsigned int(void *, unsigned __int8 *const, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800de320`

## import_xrefs

- `tbs!Tbsi_Context_Create` at `0x1800de36a`
- `tbs!Tbsi_Context_Create` at `0x1800de36a`
- `tbs!Tbsip_Context_Close` at `0x1800de38f`
- `tbs!Tbsip_Context_Close` at `0x1800de38f`
- `tbs!Tbsip_Submit_Command` at `0x1800de3c3`
- `tbs!Tbsip_Submit_Command` at `0x1800de3c3`

## pseudocode

```c
int __fastcall WinPlatformW8TbsSubmit(
        PVOID *a1,
        unsigned __int8 *const a2,
        UINT32 a3,
        unsigned __int8 *a4,
        unsigned int *pcbResult)
{
  PVOID v8; // rcx
  int result; // eax
  TBS_CONTEXT_PARAMS pContextParams[2]; // [rsp+40h] [rbp-18h] BYREF
  PVOID phContext; // [rsp+80h] [rbp+28h] BYREF

  phContext = 0;
  if ( a1 )
  {
    v8 = *a1;
LABEL_7:
    phContext = v8;
    return Tbsip_Submit_Command(v8, 0, 0xC8u, a2, a3, a4, pcbResult);
  }
  v8 = g_hTbs;
  if ( g_hTbs )
    goto LABEL_7;
  pContextParams[1].version = 4;
  pContextParams[0].version = 2;
  result = Tbsi_Context_Create(pContextParams, &phContext);
  if ( result < 0 )
    return result;
  v8 = phContext;
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_hTbs, (signed __int64)phContext, 0) )
  {
    Tbsip_Context_Close(phContext);
    v8 = g_hTbs;
    goto LABEL_7;
  }
  return Tbsip_Submit_Command(v8, 0, 0xC8u, a2, a3, a4, pcbResult);
}

```

## disassembly

```asm
0x1800de320  push    rbp
0x1800de322  push    rbx
0x1800de323  push    rsi
0x1800de324  push    rdi
0x1800de325  mov     rbp, rsp
0x1800de328  sub     rsp, 58h
0x1800de32c  mov     [rbp+phContext], 0
0x1800de334  mov     rbx, r9
0x1800de337  mov     edi, r8d
0x1800de33a  mov     rsi, rdx
0x1800de33d  test    rcx, rcx
0x1800de340  jz      short loc_1800DE347
0x1800de342  mov     rcx, [rcx]
0x1800de345  jmp     short loc_1800DE3A2
0x1800de347  mov     rcx, cs:?g_hTbs@@3PEAXEA; void * g_hTbs
0x1800de34e  test    rcx, rcx
0x1800de351  jnz     short loc_1800DE3A2
0x1800de353  mov     qword ptr [rbp+pContextParams.version], rcx
0x1800de357  lea     rdx, [rbp+phContext]; phContext
0x1800de35b  or      [rbp+pContextParams.version+4], 4
0x1800de35f  lea     rcx, [rbp+pContextParams]; pContextParams
0x1800de363  mov     [rbp+pContextParams.version], 2
0x1800de36a  call    cs:__imp_Tbsi_Context_Create
0x1800de371  nop     dword ptr [rax+rax+00h]
0x1800de376  test    eax, eax
0x1800de378  js      short loc_1800DE3CF
0x1800de37a  mov     rcx, [rbp+phContext]
0x1800de37e  xor     eax, eax
0x1800de380  lock cmpxchg cs:?g_hTbs@@3PEAXEA, rcx; void * g_hTbs
0x1800de389  mov     rcx, [rbp+phContext]; hContext
0x1800de38d  jz      short loc_1800DE3A6
0x1800de38f  call    cs:__imp_Tbsip_Context_Close
0x1800de396  nop     dword ptr [rax+rax+00h]
0x1800de39b  mov     rcx, cs:?g_hTbs@@3PEAXEA; hContext
0x1800de3a2  mov     [rbp+phContext], rcx
0x1800de3a6  mov     rax, [rbp+arg_20]
0x1800de3aa  mov     r9, rsi; pabCommand
0x1800de3ad  mov     [rsp+58h+pcbResult], rax; pcbResult
0x1800de3b2  xor     edx, edx; Locality
0x1800de3b4  mov     [rsp+58h+pabResult], rbx; pabResult
0x1800de3b9  mov     r8d, 0C8h; Priority
0x1800de3bf  mov     [rsp+58h+cbCommand], edi; cbCommand
0x1800de3c3  call    cs:__imp_Tbsip_Submit_Command
0x1800de3ca  nop     dword ptr [rax+rax+00h]
0x1800de3cf  add     rsp, 58h
0x1800de3d3  pop     rdi
0x1800de3d4  pop     rsi
0x1800de3d5  pop     rbx
0x1800de3d6  pop     rbp
0x1800de3d7  retn
```
