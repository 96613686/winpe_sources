# WinPlatformTbsSubmit(uchar * const,uint,uchar *,uint *)

- ea: `0x180149100`
- end: `0x18014917a`
- name: `?WinPlatformTbsSubmit@@YAIQEAEIPEAEPEAI@Z`
- size: `122`
- prototype: `unsigned int __fastcall(PCBYTE pabCommand, UINT32 cbCommand, PBYTE pabResult, PUINT32 pcbResult)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180149100`

## import_xrefs

- `tbs!Tbsip_Submit_Command` at `0x180149164`
- `tbs!Tbsip_Submit_Command` at `0x180149164`
- `tbs!Tbsi_Context_Create` at `0x180149134`
- `tbs!Tbsi_Context_Create` at `0x180149134`

## pseudocode

```c
int __fastcall WinPlatformTbsSubmit(PCBYTE pabCommand, UINT32 cbCommand, PBYTE pabResult, PUINT32 pcbResult)
{
  PVOID v5; // rcx
  int result; // eax
  TBS_CONTEXT_PARAMS pContextParams; // [rsp+40h] [rbp-38h] BYREF

  pContextParams.version = 1;
  v5 = g_hTbs;
  if ( !g_hTbs )
  {
    result = Tbsi_Context_Create(&pContextParams, &g_hTbs);
    if ( result < 0 )
      return result;
    v5 = g_hTbs;
  }
  return Tbsip_Submit_Command(v5, 0, 0xC8u, pabCommand, cbCommand, pabResult, pcbResult);
}

```

## disassembly

```asm
0x180149100  push    rbx
0x180149102  push    rbp
0x180149103  push    rsi
0x180149104  push    rdi
0x180149105  sub     rsp, 58h
0x180149109  mov     rbp, rcx
0x18014910c  mov     [rsp+78h+pContextParams.version], 1
0x180149114  mov     rcx, cs:?g_hTbs@@3PEAXEA; void * g_hTbs
0x18014911b  mov     rbx, r9
0x18014911e  mov     rdi, r8
0x180149121  mov     esi, edx
0x180149123  test    rcx, rcx
0x180149126  jnz     short loc_18014914B
0x180149128  lea     rdx, ?g_hTbs@@3PEAXEA; phContext
0x18014912f  lea     rcx, [rsp+78h+pContextParams]; pContextParams
0x180149134  call    cs:__imp_Tbsi_Context_Create
0x18014913b  nop     dword ptr [rax+rax+00h]
0x180149140  test    eax, eax
0x180149142  js      short loc_180149170
0x180149144  mov     rcx, cs:?g_hTbs@@3PEAXEA; hContext
0x18014914b  mov     [rsp+78h+pcbResult], rbx; pcbResult
0x180149150  mov     r9, rbp; pabCommand
0x180149153  mov     [rsp+78h+pabResult], rdi; pabResult
0x180149158  xor     edx, edx; Locality
0x18014915a  mov     r8d, 0C8h; Priority
0x180149160  mov     [rsp+78h+cbCommand], esi; cbCommand
0x180149164  call    cs:__imp_Tbsip_Submit_Command
0x18014916b  nop     dword ptr [rax+rax+00h]
0x180149170  add     rsp, 58h
0x180149174  pop     rdi
0x180149175  pop     rsi
0x180149176  pop     rbp
0x180149177  pop     rbx
0x180149178  retn
```
