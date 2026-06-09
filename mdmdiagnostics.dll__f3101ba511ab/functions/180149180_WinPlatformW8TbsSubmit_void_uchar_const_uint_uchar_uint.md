# WinPlatformW8TbsSubmit(void *,uchar * const,uint,uchar *,uint *)

- ea: `0x180149180`
- end: `0x180149239`
- name: `?WinPlatformW8TbsSubmit@@YAIPEAXQEAEIPEAEPEAI@Z`
- size: `185`
- prototype: `unsigned int(void *, unsigned __int8 *const, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180149180`

## import_xrefs

- `tbs!Tbsip_Context_Close` at `0x1801491ef`
- `tbs!Tbsip_Context_Close` at `0x1801491ef`
- `tbs!Tbsip_Submit_Command` at `0x180149223`
- `tbs!Tbsip_Submit_Command` at `0x180149223`
- `tbs!Tbsi_Context_Create` at `0x1801491ca`
- `tbs!Tbsi_Context_Create` at `0x1801491ca`

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
0x180149180  push    rbp
0x180149182  push    rbx
0x180149183  push    rsi
0x180149184  push    rdi
0x180149185  mov     rbp, rsp
0x180149188  sub     rsp, 58h
0x18014918c  mov     [rbp+phContext], 0
0x180149194  mov     rbx, r9
0x180149197  mov     edi, r8d
0x18014919a  mov     rsi, rdx
0x18014919d  test    rcx, rcx
0x1801491a0  jz      short loc_1801491A7
0x1801491a2  mov     rcx, [rcx]
0x1801491a5  jmp     short loc_180149202
0x1801491a7  mov     rcx, cs:?g_hTbs@@3PEAXEA; void * g_hTbs
0x1801491ae  test    rcx, rcx
0x1801491b1  jnz     short loc_180149202
0x1801491b3  mov     qword ptr [rbp+pContextParams.version], rcx
0x1801491b7  lea     rdx, [rbp+phContext]; phContext
0x1801491bb  or      [rbp+pContextParams.version+4], 4
0x1801491bf  lea     rcx, [rbp+pContextParams]; pContextParams
0x1801491c3  mov     [rbp+pContextParams.version], 2
0x1801491ca  call    cs:__imp_Tbsi_Context_Create
0x1801491d1  nop     dword ptr [rax+rax+00h]
0x1801491d6  test    eax, eax
0x1801491d8  js      short loc_18014922F
0x1801491da  mov     rcx, [rbp+phContext]
0x1801491de  xor     eax, eax
0x1801491e0  lock cmpxchg cs:?g_hTbs@@3PEAXEA, rcx; void * g_hTbs
0x1801491e9  mov     rcx, [rbp+phContext]; hContext
0x1801491ed  jz      short loc_180149206
0x1801491ef  call    cs:__imp_Tbsip_Context_Close
0x1801491f6  nop     dword ptr [rax+rax+00h]
0x1801491fb  mov     rcx, cs:?g_hTbs@@3PEAXEA; hContext
0x180149202  mov     [rbp+phContext], rcx
0x180149206  mov     rax, [rbp+arg_20]
0x18014920a  mov     r9, rsi; pabCommand
0x18014920d  mov     [rsp+58h+pcbResult], rax; pcbResult
0x180149212  xor     edx, edx; Locality
0x180149214  mov     [rsp+58h+pabResult], rbx; pabResult
0x180149219  mov     r8d, 0C8h; Priority
0x18014921f  mov     [rsp+58h+cbCommand], edi; cbCommand
0x180149223  call    cs:__imp_Tbsip_Submit_Command
0x18014922a  nop     dword ptr [rax+rax+00h]
0x18014922f  add     rsp, 58h
0x180149233  pop     rdi
0x180149234  pop     rsi
0x180149235  pop     rbx
0x180149236  pop     rbp
0x180149237  retn
```
