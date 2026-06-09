# GetLuxorProgid(void)

- ea: `0x180028828`
- end: `0x180028880`
- name: `?GetLuxorProgid@@YAPEAGXZ`
- size: `88`
- prototype: `unsigned __int16 *(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180028574`

## callees

- `0x1800112b0`
- `0x180028828`

## import_xrefs

- `ole32!ProgIDFromCLSID` at `0x18002884a`
- `ole32!ProgIDFromCLSID` at `0x18002884a`
- `ole32!CoTaskMemFree` at `0x18002886d`
- `ole32!CoTaskMemFree` at `0x18002886d`

## pseudocode

```c
unsigned __int16 *GetLuxorProgid(void)
{
  LPOLESTR lpszProgID; // [rsp+30h] [rbp+8h] BYREF

  if ( !g_wszLuxorProgID )
  {
    lpszProgID = 0;
    if ( ProgIDFromCLSID(&CLSID_SQLOLEDB, &lpszProgID) >= 0 )
    {
      StringCchCopyW(&g_wszLuxorProgID, 0x14u, lpszProgID);
      CoTaskMemFree(lpszProgID);
    }
  }
  return &g_wszLuxorProgID;
}

```

## disassembly

```asm
0x180028828  push    rbx
0x18002882a  sub     rsp, 20h
0x18002882e  xor     ebx, ebx
0x180028830  cmp     cs:?g_wszLuxorProgID@@3PAGA, bx; ushort near * g_wszLuxorProgID
0x180028837  jnz     short loc_180028873
0x180028839  lea     rdx, [rsp+28h+lpszProgID]; lplpszProgID
0x18002883e  mov     [rsp+28h+lpszProgID], rbx
0x180028843  lea     rcx, ?CLSID_SQLOLEDB@@3U_GUID@@B; clsid
0x18002884a  call    cs:__imp_ProgIDFromCLSID
0x180028850  test    eax, eax
0x180028852  js      short loc_180028873
0x180028854  mov     r8, [rsp+28h+lpszProgID]; unsigned __int16 *
0x180028859  lea     edx, [rbx+14h]; unsigned __int64
0x18002885c  lea     rcx, ?g_wszLuxorProgID@@3PAGA; unsigned __int16 *
0x180028863  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180028868  mov     rcx, [rsp+28h+lpszProgID]; pv
0x18002886d  call    cs:__imp_CoTaskMemFree
0x180028873  lea     rax, ?g_wszLuxorProgID@@3PAGA; ushort near * g_wszLuxorProgID
0x18002887a  add     rsp, 20h
0x18002887e  pop     rbx
0x18002887f  retn
```
