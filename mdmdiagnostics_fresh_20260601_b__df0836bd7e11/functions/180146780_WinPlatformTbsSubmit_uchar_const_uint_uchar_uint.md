# WinPlatformTbsSubmit(uchar * const,uint,uchar *,uint *)

- ea: `0x180146780`
- end: `0x1801467ed`
- name: `?WinPlatformTbsSubmit@@YAIQEAEIPEAEPEAI@Z`
- size: `109`
- prototype: `unsigned int __fastcall(PCBYTE pabCommand, UINT32 cbCommand, PBYTE pabResult, PUINT32 pcbResult)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180146780`

## import_xrefs

- `tbs!Tbsip_Submit_Command` at `0x1801467de`
- `tbs!Tbsip_Submit_Command` at `0x1801467de`
- `tbs!Tbsi_Context_Create` at `0x1801467b4`
- `tbs!Tbsi_Context_Create` at `0x1801467b4`

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
0x180146780  push    rbx
0x180146782  push    rbp
0x180146783  push    rsi
0x180146784  push    rdi
0x180146785  sub     rsp, 58h
0x180146789  mov     rbp, rcx
0x18014678c  mov     [rsp+78h+pContextParams.version], 1
0x180146794  mov     rcx, cs:?g_hTbs@@3PEAXEA; void * g_hTbs
0x18014679b  mov     rbx, r9
0x18014679e  mov     rdi, r8
0x1801467a1  mov     esi, edx
0x1801467a3  test    rcx, rcx
0x1801467a6  jnz     short loc_1801467C5
0x1801467a8  lea     rdx, ?g_hTbs@@3PEAXEA; phContext
0x1801467af  lea     rcx, [rsp+78h+pContextParams]; pContextParams
0x1801467b4  call    cs:__imp_Tbsi_Context_Create
0x1801467ba  test    eax, eax
0x1801467bc  js      short loc_1801467E4
0x1801467be  mov     rcx, cs:?g_hTbs@@3PEAXEA; hContext
0x1801467c5  mov     [rsp+78h+pcbResult], rbx; pcbResult
0x1801467ca  mov     r9, rbp; pabCommand
0x1801467cd  mov     [rsp+78h+pabResult], rdi; pabResult
0x1801467d2  xor     edx, edx; Locality
0x1801467d4  mov     r8d, 0C8h; Priority
0x1801467da  mov     [rsp+78h+cbCommand], esi; cbCommand
0x1801467de  call    cs:__imp_Tbsip_Submit_Command
0x1801467e4  add     rsp, 58h
0x1801467e8  pop     rdi
0x1801467e9  pop     rsi
0x1801467ea  pop     rbp
0x1801467eb  pop     rbx
0x1801467ec  retn
```
