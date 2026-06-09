# WinPlatformW8TbsSubmit(void *,uchar * const,uint,uchar *,uint *)

- ea: `0x180146800`
- end: `0x1801468a6`
- name: `?WinPlatformW8TbsSubmit@@YAIPEAXQEAEIPEAEPEAI@Z`
- size: `166`
- prototype: `unsigned int(void *, unsigned __int8 *const, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180146800`

## import_xrefs

- `tbs!Tbsip_Context_Close` at `0x180146869`
- `tbs!Tbsip_Context_Close` at `0x180146869`
- `tbs!Tbsip_Submit_Command` at `0x180146897`
- `tbs!Tbsip_Submit_Command` at `0x180146897`
- `tbs!Tbsi_Context_Create` at `0x18014684a`
- `tbs!Tbsi_Context_Create` at `0x18014684a`

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
0x180146800  push    rbp
0x180146802  push    rbx
0x180146803  push    rsi
0x180146804  push    rdi
0x180146805  mov     rbp, rsp
0x180146808  sub     rsp, 58h
0x18014680c  mov     [rbp+phContext], 0
0x180146814  mov     rbx, r9
0x180146817  mov     edi, r8d
0x18014681a  mov     rsi, rdx
0x18014681d  test    rcx, rcx
0x180146820  jz      short loc_180146827
0x180146822  mov     rcx, [rcx]
0x180146825  jmp     short loc_180146876
0x180146827  mov     rcx, cs:?g_hTbs@@3PEAXEA; void * g_hTbs
0x18014682e  test    rcx, rcx
0x180146831  jnz     short loc_180146876
0x180146833  mov     qword ptr [rbp+pContextParams.version], rcx
0x180146837  lea     rdx, [rbp+phContext]; phContext
0x18014683b  or      [rbp+pContextParams.version+4], 4
0x18014683f  lea     rcx, [rbp+pContextParams]; pContextParams
0x180146843  mov     [rbp+pContextParams.version], 2
0x18014684a  call    cs:__imp_Tbsi_Context_Create
0x180146850  test    eax, eax
0x180146852  js      short loc_18014689D
0x180146854  mov     rcx, [rbp+phContext]
0x180146858  xor     eax, eax
0x18014685a  lock cmpxchg cs:?g_hTbs@@3PEAXEA, rcx; void * g_hTbs
0x180146863  mov     rcx, [rbp+phContext]; hContext
0x180146867  jz      short loc_18014687A
0x180146869  call    cs:__imp_Tbsip_Context_Close
0x18014686f  mov     rcx, cs:?g_hTbs@@3PEAXEA; hContext
0x180146876  mov     [rbp+phContext], rcx
0x18014687a  mov     rax, [rbp+arg_20]
0x18014687e  mov     r9, rsi; pabCommand
0x180146881  mov     [rsp+58h+pcbResult], rax; pcbResult
0x180146886  xor     edx, edx; Locality
0x180146888  mov     [rsp+58h+pabResult], rbx; pabResult
0x18014688d  mov     r8d, 0C8h; Priority
0x180146893  mov     [rsp+58h+cbCommand], edi; cbCommand
0x180146897  call    cs:__imp_Tbsip_Submit_Command
0x18014689d  add     rsp, 58h
0x1801468a1  pop     rdi
0x1801468a2  pop     rsi
0x1801468a3  pop     rbx
0x1801468a4  pop     rbp
0x1801468a5  retn
```
