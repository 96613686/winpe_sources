# myCLSIDToWsz(_GUID const *,ushort * *)

- ea: `0x18001d8a8`
- end: `0x18001d974`
- name: `?myCLSIDToWsz@@YAJPEBU_GUID@@PEAPEAG@Z`
- size: `204`
- prototype: `int(const struct _GUID *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800172f0`

## callees

- `0x18001d8a8`
- `0x180020a6c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d95c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d95c`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001d8c8`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001d8c8`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001d94c`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001d94c`

## pseudocode

```c
__int64 __fastcall myCLSIDToWsz(const struct _GUID *a1, unsigned __int16 **a2)
{
  HRESULT v3; // eax
  unsigned int v4; // ebx
  unsigned int v5; // ecx
  unsigned __int16 *v6; // rcx
  __int16 v7; // dx
  __int64 v8; // rax
  unsigned __int16 *v9; // rdx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  pv = 0;
  v3 = StringFromCLSID(a1, (LPOLESTR *)&pv);
  v4 = v3;
  if ( v3 )
  {
    v5 = 8585626;
LABEL_15:
    CSPrintErrorLineFile(v5, v3);
    goto LABEL_16;
  }
  v6 = (unsigned __int16 *)pv;
  v7 = *(_WORD *)pv;
  if ( *(_WORD *)pv )
  {
    do
    {
      if ( (unsigned __int16)(v7 - 65) <= 5u )
        *v6 = v7 + 32;
      v7 = *++v6;
    }
    while ( *v6 );
    v6 = (unsigned __int16 *)pv;
  }
  v8 = -1;
  do
    ++v8;
  while ( v6[v8] );
  if ( *v6 == 123 )
  {
    v9 = &v6[v8];
    if ( *(v9 - 1) == 125 )
    {
      ++v6;
      *(v9 - 1) = 0;
    }
  }
  v3 = myDupString(v6, a2);
  v4 = v3;
  if ( v3 )
  {
    v5 = 9765274;
    goto LABEL_15;
  }
LABEL_16:
  if ( pv )
    CoTaskMemFree(pv);
  return v4;
}

```

## disassembly

```asm
0x18001d8a8  mov     rax, rsp
0x18001d8ab  mov     [rax+8], rbx
0x18001d8af  mov     [rax+18h], rsi
0x18001d8b3  push    rdi
0x18001d8b4  sub     rsp, 20h
0x18001d8b8  xor     esi, esi
0x18001d8ba  mov     rdi, rdx
0x18001d8bd  mov     [rdx], rsi
0x18001d8c0  lea     rdx, [rax+10h]; lplpsz
0x18001d8c4  mov     [rax+10h], rsi
0x18001d8c8  call    cs:__imp_StringFromCLSID
0x18001d8ce  mov     ebx, eax
0x18001d8d0  test    eax, eax
0x18001d8d2  jz      short loc_18001D8DB
0x18001d8d4  mov     ecx, 83019Ah
0x18001d8d9  jmp     short loc_18001D94A
0x18001d8db  mov     rcx, [rsp+28h+pv]
0x18001d8e0  movzx   edx, word ptr [rcx]
0x18001d8e3  cmp     si, dx
0x18001d8e6  jz      short loc_18001D909
0x18001d8e8  lea     eax, [rdx-41h]
0x18001d8eb  cmp     ax, 5
0x18001d8ef  ja      short loc_18001D8F8
0x18001d8f1  add     dx, 20h ; ' '
0x18001d8f5  mov     [rcx], dx
0x18001d8f8  add     rcx, 2
0x18001d8fc  movzx   edx, word ptr [rcx]
0x18001d8ff  cmp     si, dx
0x18001d902  jnz     short loc_18001D8E8
0x18001d904  mov     rcx, [rsp+28h+pv]
0x18001d909  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001d90d  inc     rax
0x18001d910  cmp     [rcx+rax*2], si
0x18001d914  jnz     short loc_18001D90D
0x18001d916  mov     edx, 7Bh ; '{'
0x18001d91b  cmp     dx, [rcx]
0x18001d91e  jnz     short loc_18001D937
0x18001d920  lea     rdx, [rcx+rax*2]
0x18001d924  mov     eax, 7Dh ; '}'
0x18001d929  cmp     ax, [rdx-2]
0x18001d92d  jnz     short loc_18001D937
0x18001d92f  add     rcx, 2; Src
0x18001d933  mov     [rdx-2], si
0x18001d937  mov     rdx, rdi; unsigned __int16 **
0x18001d93a  call    ?myDupString@@YAJPEBGPEAPEAG@Z; myDupString(ushort const *,ushort * *)
0x18001d93f  mov     ebx, eax
0x18001d941  test    eax, eax
0x18001d943  jz      short loc_18001D952
0x18001d945  mov     ecx, 95019Ah
0x18001d94a  mov     edx, eax
0x18001d94c  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001d952  mov     rcx, [rsp+28h+pv]; pv
0x18001d957  test    rcx, rcx
0x18001d95a  jz      short loc_18001D962
0x18001d95c  call    cs:__imp_CoTaskMemFree
0x18001d962  mov     rsi, [rsp+28h+arg_10]
0x18001d967  mov     eax, ebx
0x18001d969  mov     rbx, [rsp+28h+arg_0]
0x18001d96e  add     rsp, 20h
0x18001d972  pop     rdi
0x18001d973  retn
```
