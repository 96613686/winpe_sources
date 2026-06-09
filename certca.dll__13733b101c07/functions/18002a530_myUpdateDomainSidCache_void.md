# myUpdateDomainSidCache(void)

- ea: `0x18002a530`
- end: `0x18002a5c7`
- name: `?myUpdateDomainSidCache@@YAKXZ`
- size: `151`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18002a290`

## callees

- `0x180008400`
- `0x1800103fc`
- `0x1800281d8`
- `0x18002a530`
- `0x18003b010`

## string_xrefs

- `0x18002a573`: `logoncli.dll`

## pseudocode

```c
__int64 myUpdateDomainSidCache(void)
{
  int NetApi; // eax
  unsigned int v1; // ebx
  unsigned int v2; // ecx

  if ( g_pDomainCache )
  {
    myNetApiBufferFree(g_pDomainCache);
    g_pDomainCache = 0;
  }
  NetApi = myLoadNetApi(
             L"logoncli.dll",
             (CHAR *)"DsEnumerateDomainTrustsW",
             L"DsEnumerateDomainTrustsW",
             &qword_1800C4E98,
             &qword_1800C4EA0);
  v1 = NetApi;
  if ( NetApi )
  {
    v2 = 15139275;
LABEL_7:
    CSPrintErrorLineFile(v2, NetApi);
    return v1;
  }
  NetApi = ((__int64 (__fastcall *)(_QWORD, __int64, void **, unsigned int *))qword_1800C4EA0)(
             0,
             63,
             &g_pDomainCache,
             &g_cDomainCache);
  v1 = NetApi;
  if ( NetApi )
  {
    v2 = 15598027;
    goto LABEL_7;
  }
  return v1;
}

```

## disassembly

```asm
0x18002a530  push    rbx
0x18002a532  sub     rsp, 30h
0x18002a536  mov     rcx, cs:?g_pDomainCache@@3PEAU_DS_DOMAIN_TRUSTSW@@EA; void *
0x18002a53d  test    rcx, rcx
0x18002a540  jz      short loc_18002A552
0x18002a542  call    ?myNetApiBufferFree@@YAKPEAX@Z; myNetApiBufferFree(void *)
0x18002a547  mov     cs:?g_pDomainCache@@3PEAU_DS_DOMAIN_TRUSTSW@@EA, 0; _DS_DOMAIN_TRUSTSW * g_pDomainCache
0x18002a552  lea     rax, qword_1800C4EA0
0x18002a559  lea     r9, qword_1800C4E98; HINSTANCE *
0x18002a560  mov     [rsp+38h+var_18], rax; __int64 (**)(void)
0x18002a565  lea     r8, aDsenumeratedom_0; "DsEnumerateDomainTrustsW"
0x18002a56c  lea     rdx, aDsenumeratedom; "DsEnumerateDomainTrustsW"
0x18002a573  lea     rcx, aLogoncliDll; "logoncli.dll"
0x18002a57a  call    ?myLoadNetApi@@YAJPEBGPEBD0PEAPEAUHINSTANCE__@@PEAP6A_JXZ@Z; myLoadNetApi(ushort const *,char const *,ushort const *,HINSTANCE__ * *,__int64 (**)(void))
0x18002a57f  mov     ebx, eax
0x18002a581  test    eax, eax
0x18002a583  jz      short loc_18002A58C
0x18002a585  mov     ecx, 0E701CBh
0x18002a58a  jmp     short loc_18002A5B8
0x18002a58c  mov     rax, cs:qword_1800C4EA0
0x18002a593  lea     r9, ?g_cDomainCache@@3KA; ulong g_cDomainCache
0x18002a59a  lea     r8, ?g_pDomainCache@@3PEAU_DS_DOMAIN_TRUSTSW@@EA; _DS_DOMAIN_TRUSTSW * g_pDomainCache
0x18002a5a1  mov     edx, 3Fh ; '?'
0x18002a5a6  xor     ecx, ecx
0x18002a5a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a5ad  mov     ebx, eax
0x18002a5af  test    eax, eax
0x18002a5b1  jz      short loc_18002A5BF
0x18002a5b3  mov     ecx, 0EE01CBh; unsigned int
0x18002a5b8  mov     edx, eax; int
0x18002a5ba  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002a5bf  mov     eax, ebx
0x18002a5c1  add     rsp, 30h
0x18002a5c5  pop     rbx
0x18002a5c6  retn
```
