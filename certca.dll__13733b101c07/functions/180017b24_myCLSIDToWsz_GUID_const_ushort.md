# myCLSIDToWsz(_GUID const *,ushort * *)

- ea: `0x180017b24`
- end: `0x180017bef`
- name: `?myCLSIDToWsz@@YAJPEBU_GUID@@PEAPEAG@Z`
- size: `203`
- prototype: `__int64 __fastcall(const struct _GUID *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180017fe0`
- `0x180020040`

## callees

- `0x180008400`
- `0x18000dce0`
- `0x180017b24`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017bd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017bd7`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180017b44`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180017b44`

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
0x180017b24  mov     rax, rsp
0x180017b27  mov     [rax+8], rbx
0x180017b2b  mov     [rax+18h], rsi
0x180017b2f  push    rdi
0x180017b30  sub     rsp, 20h
0x180017b34  xor     esi, esi
0x180017b36  mov     rdi, rdx
0x180017b39  mov     [rdx], rsi
0x180017b3c  lea     rdx, [rax+10h]; lplpsz
0x180017b40  mov     [rax+10h], rsi
0x180017b44  call    cs:__imp_StringFromCLSID
0x180017b4a  mov     ebx, eax
0x180017b4c  test    eax, eax
0x180017b4e  jz      short loc_180017B57
0x180017b50  mov     ecx, 83019Ah
0x180017b55  jmp     short loc_180017BC6
0x180017b57  mov     rcx, [rsp+28h+pv]
0x180017b5c  movzx   edx, word ptr [rcx]
0x180017b5f  cmp     si, dx
0x180017b62  jz      short loc_180017B85
0x180017b64  lea     eax, [rdx-41h]
0x180017b67  cmp     ax, 5
0x180017b6b  ja      short loc_180017B74
0x180017b6d  add     dx, 20h ; ' '
0x180017b71  mov     [rcx], dx
0x180017b74  add     rcx, 2
0x180017b78  movzx   edx, word ptr [rcx]
0x180017b7b  cmp     si, dx
0x180017b7e  jnz     short loc_180017B64
0x180017b80  mov     rcx, [rsp+28h+pv]
0x180017b85  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017b89  inc     rax
0x180017b8c  cmp     [rcx+rax*2], si
0x180017b90  jnz     short loc_180017B89
0x180017b92  mov     edx, 7Bh ; '{'
0x180017b97  cmp     dx, [rcx]
0x180017b9a  jnz     short loc_180017BB3
0x180017b9c  lea     rdx, [rcx+rax*2]
0x180017ba0  mov     eax, 7Dh ; '}'
0x180017ba5  cmp     ax, [rdx-2]
0x180017ba9  jnz     short loc_180017BB3
0x180017bab  add     rcx, 2; Src
0x180017baf  mov     [rdx-2], si
0x180017bb3  mov     rdx, rdi; unsigned __int16 **
0x180017bb6  call    ?myDupString@@YAJPEBGPEAPEAG@Z; myDupString(ushort const *,ushort * *)
0x180017bbb  mov     ebx, eax
0x180017bbd  test    eax, eax
0x180017bbf  jz      short loc_180017BCD
0x180017bc1  mov     ecx, 95019Ah; unsigned int
0x180017bc6  mov     edx, eax; int
0x180017bc8  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180017bcd  mov     rcx, [rsp+28h+pv]; pv
0x180017bd2  test    rcx, rcx
0x180017bd5  jz      short loc_180017BDD
0x180017bd7  call    cs:__imp_CoTaskMemFree
0x180017bdd  mov     rsi, [rsp+28h+arg_10]
0x180017be2  mov     eax, ebx
0x180017be4  mov     rbx, [rsp+28h+arg_0]
0x180017be9  add     rsp, 20h
0x180017bed  pop     rdi
0x180017bee  retn
```
