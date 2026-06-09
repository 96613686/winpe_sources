# GetProtocolDefaults(ProtElem *,ushort const *,ushort const *)

- ea: `0x10043e760`
- end: `0x10043ea9a`
- name: `?GetProtocolDefaults@@YAKPEAVProtElem@@PEBG1@Z`
- size: `826`
- prototype: `unsigned int(struct ProtElem *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x10043cba8`
- `0x10043ebd8`

## callees

- `0x100416508`
- `0x10043e760`
- `0x10043eaa0`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x10043e9df`
- `KERNEL32!CompareStringOrdinal` at `0x10043e9df`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10043e9fb`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10043e9fb`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x10043e86f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x10043ea53`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x10043e86f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x10043ea53`
- `api-ms-win-crt-environment-l1-1-0!_wdupenv_s` at `0x10043e96d`
- `api-ms-win-crt-environment-l1-1-0!_wdupenv_s` at `0x10043e96d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetProtocolDefaults(struct ProtElem *a1, wchar_t *a2, const unsigned __int16 *a3)
{
  unsigned int v6; // ebx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  char *v11; // rdi
  __int64 v12; // rcx
  signed __int64 v13; // rdx
  __int16 v14; // ax
  char *v15; // rax
  char *v16; // rdi
  __int64 v17; // rcx
  signed __int64 v18; // rsi
  __int16 v19; // ax
  char *v20; // rax
  unsigned __int16 *v21; // rdi
  __int64 v22; // rdx
  unsigned __int16 *v23; // rcx
  unsigned __int16 v24; // ax
  unsigned __int16 *v25; // rax
  void *Block; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v27[6]; // [rsp+38h] [rbp-30h] BYREF
  int v28; // [rsp+88h] [rbp+20h] BYREF

  v27[1] = -2;
  v27[0] = -1;
  v6 = 0;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7F60[0] )
    bidScopeEnterW(v27, off_1005E7F60[0], a1);
  Block = 0;
  if ( GetProtocolEnum(a2, (enum ProviderNum *)&v28) )
    goto LABEL_14;
  v7 = v28;
  *(_DWORD *)a1 = v28;
  if ( v7 == 7 )
  {
    *((_WORD *)a1 + 1028) = 0;
    *((_BYTE *)a1 + 2058) = 0;
    *((_DWORD *)a1 + 515) = -1;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    if ( !_wdupenv_s((wchar_t **)&Block, 0, L"_CLUSTER_NETWORK_NAME_") )
    {
      v21 = (unsigned __int16 *)((char *)a1 + 1544);
      v22 = 261;
      v23 = v21;
      do
      {
        if ( v22 == -2147483385 )
          break;
        v24 = *(unsigned __int16 *)((char *)v23 + (char *)L"\\\\" - (char *)v21);
        if ( !v24 )
          break;
        *v23++ = v24;
        --v22;
      }
      while ( v22 );
      v25 = v23 - 1;
      if ( v22 )
        v25 = v23;
      *v25 = 0;
      if ( CompareStringOrdinal(a3, -1, &gwszComputerName, -1, 1) != 2
        || Block && _wcsicmp((const wchar_t *)Block, &szDefault) )
      {
        if ( (int)StringCchCatW(v21, 0x105u, a3) < 0 )
          goto LABEL_14;
      }
      else
      {
        StringCchCatW(v21, 0x105u, L".");
      }
      if ( (int)StringCchCatW(v21, 0x105u, L"\\PIPE\\sql\\query") >= 0 )
        goto LABEL_49;
    }
LABEL_14:
    if ( Block )
      free(Block);
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E5FE0[0] )
      bidTraceW(0, 686080, off_1005E5FE0[0], 0xFFFFFFFFLL);
    v6 = -1;
    goto LABEL_20;
  }
  v9 = v8 - 3;
  if ( v9 )
  {
    if ( v9 != 3 )
    {
      if ( (bidGblFlags & 2) != 0 && off_1005E5FD0[0] && bidID != -1 )
        ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(
          bidID,
          0,
          665600,
          off_1005E5FD0[0],
          0);
      goto LABEL_14;
    }
    v11 = (char *)a1 + 1544;
    v12 = 256;
    v13 = (char *)L"1433" - v11;
    do
    {
      if ( v12 == -2147483390 )
        break;
      v14 = *(_WORD *)&v11[v13];
      if ( !v14 )
        break;
      *(_WORD *)v11 = v14;
      v11 += 2;
      --v12;
    }
    while ( v12 );
    v15 = v11 - 2;
    if ( v12 )
      v15 = v11;
    *(_WORD *)v15 = 0;
  }
  else
  {
    v16 = (char *)a1 + 1544;
    v17 = 512;
    v18 = (char *)a3 - v16;
    do
    {
      if ( v17 == -2147483134 )
        break;
      v19 = *(_WORD *)&v16[v18];
      if ( !v19 )
        break;
      *(_WORD *)v16 = v19;
      v16 += 2;
      --v17;
    }
    while ( v17 );
    v20 = v16 - 2;
    if ( v17 )
      v20 = v16;
    *(_WORD *)v20 = 0;
    if ( !v17 )
      goto LABEL_14;
  }
LABEL_49:
  if ( Block )
    free(Block);
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E5FD8[0] )
    bidTraceW(0, 674816, off_1005E5FD8[0], 0);
LABEL_20:
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)v27);
  return v6;
}

```

## disassembly

```asm
0x10043e760  mov     r11, rsp
0x10043e763  push    rsi
0x10043e764  push    rdi
0x10043e765  push    r14
0x10043e767  sub     rsp, 50h
0x10043e76b  mov     qword ptr [r11-28h], 0FFFFFFFFFFFFFFFEh
0x10043e773  mov     [r11+8], rbx
0x10043e777  mov     [r11+10h], rbp
0x10043e77b  mov     rsi, r8
0x10043e77e  mov     rbp, rdx
0x10043e781  mov     rdi, rcx
0x10043e784  or      r14, 0FFFFFFFFFFFFFFFFh
0x10043e788  mov     [r11-30h], r14
0x10043e78c  mov     eax, cs:_bidGblFlags
0x10043e792  mov     ecx, 20004h
0x10043e797  and     eax, ecx
0x10043e799  xor     ebx, ebx
0x10043e79b  cmp     eax, ecx
0x10043e79d  jnz     short loc_10043E7C5
0x10043e79f  mov     rax, cs:off_1005E7F60; "<GetProtocolDefaults|API|SNI> pProtElem"...
0x10043e7a6  test    rax, rax
0x10043e7a9  jz      short loc_10043E7C5
0x10043e7ab  mov     [r11-48h], r8
0x10043e7af  mov     r9, rdx
0x10043e7b2  mov     r8, rdi
0x10043e7b5  mov     rdx, cs:off_1005E7F60; "<GetProtocolDefaults|API|SNI> pProtElem"...
0x10043e7bc  lea     rcx, [r11-30h]
0x10043e7c0  call    _bidScopeEnterW
0x10043e7c5  mov     [rsp+68h+Block], rbx
0x10043e7ca  lea     rdx, [rsp+68h+arg_18]; enum ProviderNum *
0x10043e7d2  mov     rcx, rbp; String2
0x10043e7d5  call    ?GetProtocolEnum@@YAKPEBGPEAW4ProviderNum@@@Z; GetProtocolEnum(ushort const *,ProviderNum *)
0x10043e7da  test    eax, eax
0x10043e7dc  jnz     loc_10043E865
0x10043e7e2  mov     ecx, [rsp+68h+arg_18]
0x10043e7e9  mov     [rdi], ecx
0x10043e7eb  cmp     ecx, 7
0x10043e7ee  jnz     short loc_10043E804
0x10043e7f0  mov     [rdi+808h], bx
0x10043e7f7  mov     [rdi+80Ah], bl
0x10043e7fd  mov     [rdi+80Ch], r14d
0x10043e804  sub     ecx, 1
0x10043e807  jz      loc_10043E95F
0x10043e80d  sub     ecx, 3
0x10043e810  jz      loc_10043E915
0x10043e816  cmp     ecx, 3
0x10043e819  jz      loc_10043E8CA
0x10043e81f  test    byte ptr cs:_bidGblFlags, 2
0x10043e826  jz      short loc_10043E865
0x10043e828  mov     rax, cs:off_1005E5FD0; "<GetProtocolDefaults|ERR|SNI> providerN"...
0x10043e82f  test    rax, rax
0x10043e832  jz      short loc_10043E865
0x10043e834  cmp     cs:_bidID, r14
0x10043e83b  jz      short loc_10043E865
0x10043e83d  mov     rax, cs:off_1005D39E0
0x10043e844  mov     qword ptr [rsp+68h+bIgnoreCase], rbx
0x10043e849  mov     r9, cs:off_1005E5FD0; "<GetProtocolDefaults|ERR|SNI> providerN"...
0x10043e850  xor     edx, edx
0x10043e852  mov     r8d, 0A2800h
0x10043e858  mov     rcx, cs:_bidID
0x10043e85f  call    cs:__guard_dispatch_icall_fptr
0x10043e865  mov     rcx, [rsp+68h+Block]; Block
0x10043e86a  test    rcx, rcx
0x10043e86d  jz      short loc_10043E875
0x10043e86f  call    cs:__imp_free
0x10043e875  mov     eax, cs:_bidGblFlags
0x10043e87b  mov     ecx, 20002h
0x10043e880  and     eax, ecx
0x10043e882  cmp     eax, ecx
0x10043e884  jnz     short loc_10043E8A8
0x10043e886  mov     rax, cs:off_1005E5FE0; "<GetProtocolDefaults|RET|SNI> %d{WINERR"...
0x10043e88d  test    rax, rax
0x10043e890  jz      short loc_10043E8A8
0x10043e892  mov     r9d, r14d
0x10043e895  mov     r8, cs:off_1005E5FE0; "<GetProtocolDefaults|RET|SNI> %d{WINERR"...
0x10043e89c  mov     edx, 0A7800h
0x10043e8a1  xor     ecx, ecx
0x10043e8a3  call    _bidTraceW
0x10043e8a8  or      ebx, 0FFFFFFFFh
0x10043e8ab  lea     rcx, [rsp+68h+var_30]; this
0x10043e8b0  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x10043e8b5  mov     eax, ebx
0x10043e8b7  mov     rbx, [rsp+68h+arg_0]
0x10043e8bc  mov     rbp, [rsp+68h+arg_8]
0x10043e8c1  add     rsp, 50h
0x10043e8c5  pop     r14
0x10043e8c7  pop     rdi
0x10043e8c8  pop     rsi
0x10043e8c9  retn
0x10043e8ca  add     rdi, 608h
0x10043e8d1  mov     ecx, 100h
0x10043e8d6  lea     rdx, a1433; "1433"
0x10043e8dd  sub     rdx, rdi
0x10043e8e0  lea     rax, [rcx+7FFFFEFEh]
0x10043e8e7  test    rax, rax
0x10043e8ea  jz      short loc_10043E902
0x10043e8ec  movzx   eax, word ptr [rdx+rdi]
0x10043e8f0  test    ax, ax
0x10043e8f3  jz      short loc_10043E902
0x10043e8f5  mov     [rdi], ax
0x10043e8f8  add     rdi, 2
0x10043e8fc  sub     rcx, 1
0x10043e900  jnz     short loc_10043E8E0
0x10043e902  lea     rax, [rdi-2]
0x10043e906  test    rcx, rcx
0x10043e909  cmovnz  rax, rdi
0x10043e90d  mov     [rax], bx
0x10043e910  jmp     loc_10043EA49
0x10043e915  add     rdi, 608h
0x10043e91c  mov     ecx, 200h
0x10043e921  sub     rsi, rdi
0x10043e924  lea     rax, [rcx+7FFFFDFEh]
0x10043e92b  test    rax, rax
0x10043e92e  jz      short loc_10043E946
0x10043e930  movzx   eax, word ptr [rsi+rdi]
0x10043e934  test    ax, ax
0x10043e937  jz      short loc_10043E946
0x10043e939  mov     [rdi], ax
0x10043e93c  add     rdi, 2
0x10043e940  sub     rcx, 1
0x10043e944  jnz     short loc_10043E924
0x10043e946  lea     rax, [rdi-2]
0x10043e94a  test    rcx, rcx
0x10043e94d  cmovnz  rax, rdi
0x10043e951  mov     [rax], bx
0x10043e954  jz      loc_10043E865
0x10043e95a  jmp     loc_10043EA49
0x10043e95f  lea     r8, aClusterNetwork; "_CLUSTER_NETWORK_NAME_"
0x10043e966  xor     edx, edx; BufferCount
0x10043e968  lea     rcx, [rsp+68h+Block]; Buffer
0x10043e96d  call    cs:__imp__wdupenv_s
0x10043e973  test    eax, eax
0x10043e975  jnz     loc_10043E865
0x10043e97b  add     rdi, 608h
0x10043e982  mov     ebp, 105h
0x10043e987  mov     edx, ebp
0x10043e989  mov     rcx, rdi
0x10043e98c  lea     r8, asc_100559CFC; "\\\\"
0x10043e993  sub     r8, rdi
0x10043e996  lea     rax, [rdx+7FFFFEF9h]
0x10043e99d  test    rax, rax
0x10043e9a0  jz      short loc_10043E9B9
0x10043e9a2  movzx   eax, word ptr [r8+rcx]
0x10043e9a7  test    ax, ax
0x10043e9aa  jz      short loc_10043E9B9
0x10043e9ac  mov     [rcx], ax
0x10043e9af  add     rcx, 2
0x10043e9b3  sub     rdx, 1
0x10043e9b7  jnz     short loc_10043E996
0x10043e9b9  lea     rax, [rcx-2]
0x10043e9bd  test    rdx, rdx
0x10043e9c0  cmovnz  rax, rcx
0x10043e9c4  mov     [rax], bx
0x10043e9c7  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x10043e9cf  mov     r9d, r14d; cchCount2
0x10043e9d2  lea     r8, ?gwszComputerName@@3PAGA; lpString2
0x10043e9d9  mov     edx, r14d; cchCount1
0x10043e9dc  mov     rcx, rsi; lpString1
0x10043e9df  call    cs:__imp_CompareStringOrdinal
0x10043e9e5  cmp     eax, 2
0x10043e9e8  jnz     short loc_10043EA19
0x10043e9ea  mov     rcx, [rsp+68h+Block]; String1
0x10043e9ef  test    rcx, rcx
0x10043e9f2  jz      short loc_10043EA05
0x10043e9f4  lea     rdx, szDefault; String2
0x10043e9fb  call    cs:__imp__wcsicmp
0x10043ea01  test    eax, eax
0x10043ea03  jnz     short loc_10043EA19
0x10043ea05  lea     r8, asc_100581260; "."
0x10043ea0c  mov     rdx, rbp; unsigned __int64
0x10043ea0f  mov     rcx, rdi; unsigned __int16 *
0x10043ea12  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x10043ea17  jmp     short loc_10043EA2F
0x10043ea19  mov     r8, rsi; unsigned __int16 *
0x10043ea1c  mov     rdx, rbp; unsigned __int64
0x10043ea1f  mov     rcx, rdi; unsigned __int16 *
0x10043ea22  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x10043ea27  test    eax, eax
0x10043ea29  js      loc_10043E865
0x10043ea2f  lea     r8, aPipeSqlQuery; "\\PIPE\\sql\\query"
0x10043ea36  mov     rdx, rbp; unsigned __int64
0x10043ea39  mov     rcx, rdi; unsigned __int16 *
0x10043ea3c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x10043ea41  test    eax, eax
0x10043ea43  js      loc_10043E865
0x10043ea49  mov     rcx, [rsp+68h+Block]; Block
0x10043ea4e  test    rcx, rcx
0x10043ea51  jz      short loc_10043EA59
0x10043ea53  call    cs:__imp_free
0x10043ea59  mov     eax, cs:_bidGblFlags
0x10043ea5f  mov     ecx, 20002h
0x10043ea64  and     eax, ecx
0x10043ea66  cmp     eax, ecx
0x10043ea68  jnz     loc_10043E8AB
0x10043ea6e  mov     rax, cs:off_1005E5FD8; "<GetProtocolDefaults|RET|SNI> %d{WINERR"...
0x10043ea75  test    rax, rax
0x10043ea78  jz      loc_10043E8AB
0x10043ea7e  xor     r9d, r9d
0x10043ea81  mov     r8, cs:off_1005E5FD8; "<GetProtocolDefaults|RET|SNI> %d{WINERR"...
0x10043ea88  mov     edx, 0A4C00h
0x10043ea8d  xor     ecx, ecx
0x10043ea8f  call    _bidTraceW
0x10043ea94  jmp     loc_10043E8AB
```
