# GetProtocolDefaults(ProtElem *,wchar_t const *,wchar_t const *)

- ea: `0x18015ccd0`
- end: `0x18015d1cc`
- name: `?GetProtocolDefaults@@YAKPEAVProtElem@@PEB_W1@Z`
- size: `1276`
- prototype: `unsigned int(struct ProtElem *, const wchar_t *, const wchar_t *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18015d1e0`
- `0x1801a8690`

## callees

- `0x180001f70`
- `0x180002ef0`
- `0x1800030c0`
- `0x180003d80`
- `0x1800993b0`
- `0x18015ccd0`
- `0x1801ad6a0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18015cd94`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18015cdb2`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18015cdd0`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18015d005`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18015cd94`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18015cdb2`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18015cdd0`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18015d005`
- `KERNEL32!CompareStringW` at `0x18015cfe9`
- `KERNEL32!CompareStringW` at `0x18015cfe9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18015d0bd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18015d15b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18015d0bd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18015d15b`
- `api-ms-win-crt-environment-l1-1-0!_wdupenv_s` at `0x18015cf68`
- `api-ms-win-crt-environment-l1-1-0!_wdupenv_s` at `0x18015cf68`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetProtocolDefaults(struct ProtElem *a1, const wchar_t *a2, const wchar_t *a3)
{
  unsigned int v6; // ebp
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  _WORD *v10; // rcx
  __int64 v11; // rdx
  __int16 v12; // ax
  _WORD *v13; // rax
  char *v14; // rcx
  __int64 v15; // rdx
  signed __int64 v16; // rdi
  __int16 v17; // ax
  bool v18; // zf
  wchar_t *v19; // rsi
  __int64 v20; // rdx
  _WORD *v21; // rcx
  __int16 v22; // ax
  _WORD *v23; // rax
  __int64 v24; // rcx
  _WORD *v25; // rax
  __int64 v26; // rbx
  __int64 v27; // rax
  signed __int64 v28; // r8
  __int16 v29; // dx
  char *v30; // rax
  wchar_t *Buffer; // [rsp+30h] [rbp-48h] BYREF
  int v33; // [rsp+38h] [rbp-40h] BYREF
  __int64 v34; // [rsp+40h] [rbp-38h] BYREF
  __int64 v35; // [rsp+48h] [rbp-30h] BYREF

  v35 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1802668B0[0] )
    bidScopeEnterW(&v35, off_1802668B0[0], a1, a2);
  v6 = 0;
  v33 = 0;
  Buffer = 0;
  v34 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1802668A8[0] )
    bidScopeEnterW(&v34, off_1802668A8[0], a2, &v33);
  v33 = 8;
  if ( _wcsicmp(L"TCP", a2) )
  {
    if ( _wcsicmp(L"NP", a2) )
    {
      if ( _wcsicmp(L"SM", a2) )
      {
        if ( (bidGblFlags & 0x20002) == 0x20002 && off_180264100[0] )
          bidTraceW(off_180260DB8[0], 583680, off_180264100[0], 0xFFFFFFFFLL);
        _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v34);
        goto LABEL_70;
      }
      v33 = 3;
    }
    else
    {
      v33 = 1;
    }
  }
  else
  {
    v33 = 6;
  }
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_180264108[0] )
    bidTraceW(off_180260DC0[0], 588800, off_180264108[0], 0);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v34);
  v7 = v33;
  *(_DWORD *)a1 = v33;
  if ( v7 == 6 )
  {
    *((_WORD *)a1 + 1028) = 0;
    *((_BYTE *)a1 + 2058) = 0;
    *((_DWORD *)a1 + 515) = -1;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    if ( !_wdupenv_s(&Buffer, 0, L"_CLUSTER_NETWORK_NAME_") )
    {
      v19 = (wchar_t *)((char *)a1 + 1544);
      v20 = 261;
      v21 = (_WORD *)((char *)a1 + 1544);
      do
      {
        if ( v20 == -2147483385 )
          break;
        v22 = *(_WORD *)((char *)v21 + (char *)L"\\\\" - (char *)v19);
        if ( !v22 )
          break;
        *v21++ = v22;
        --v20;
      }
      while ( v20 );
      v23 = v21 - 1;
      if ( v20 )
        v23 = v21;
      *v23 = 0;
      if ( CompareStringW(0x800u, 0x20001u, a3, -1, &gwszComputerName, -1) != 2 || Buffer && _wcsicmp(Buffer, &Class) )
      {
        if ( (int)StringCchCatW(v19, 0x105u, a3) < 0 )
          goto LABEL_70;
      }
      else
      {
        StringCchCatW(v19, 0x105u, L".");
      }
      v24 = 261;
      v25 = (_WORD *)((char *)a1 + 1544);
      do
      {
        if ( !*v25 )
          break;
        ++v25;
        --v24;
      }
      while ( v24 );
      if ( v24 )
      {
        v26 = v24;
        v14 = (char *)&v19[261 - v24];
        v27 = 2147483646;
        v28 = (char *)L"\\PIPE\\sql\\query" - v14;
        do
        {
          if ( !v27 )
            break;
          v29 = *(_WORD *)&v14[v28];
          if ( !v29 )
            break;
          *(_WORD *)v14 = v29;
          v14 += 2;
          --v27;
          --v26;
        }
        while ( v26 );
        v18 = v26 == 0;
LABEL_58:
        v30 = v14 - 2;
        if ( !v18 )
          v30 = v14;
        *(_WORD *)v30 = 0;
        if ( v18 )
          goto LABEL_70;
        goto LABEL_61;
      }
    }
LABEL_70:
    if ( Buffer )
      free(Buffer);
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_180264120[0] )
      bidTraceW(off_180260DD8[0], 704512, off_180264120[0], 0xFFFFFFFFLL);
    v6 = -1;
    goto LABEL_76;
  }
  v9 = v8 - 2;
  if ( !v9 )
  {
    v14 = (char *)a1 + 1544;
    v15 = 512;
    v16 = (char *)a3 - ((char *)a1 + 1544);
    do
    {
      if ( v15 == -2147483134 )
        break;
      v17 = *(_WORD *)&v14[v16];
      if ( !v17 )
        break;
      *(_WORD *)v14 = v17;
      v14 += 2;
      --v15;
    }
    while ( v15 );
    v18 = v15 == 0;
    goto LABEL_58;
  }
  if ( v9 != 3 )
  {
    if ( (bidGblFlags & 2) != 0 && off_180264110[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, char *, __int64, wchar_t *, _QWORD))off_180248050[0])(
        bidID,
        off_180260DC8[0],
        684032,
        off_180264110[0],
        0);
    goto LABEL_70;
  }
  v10 = (_WORD *)((char *)a1 + 1544);
  v11 = 256;
  do
  {
    if ( v11 == -2147483390 )
      break;
    v12 = *(_WORD *)((char *)v10 + (char *)L"1433" - ((char *)a1 + 1544));
    if ( !v12 )
      break;
    *v10++ = v12;
    --v11;
  }
  while ( v11 );
  v13 = v10 - 1;
  if ( v11 )
    v13 = v10;
  *v13 = 0;
LABEL_61:
  if ( Buffer )
    free(Buffer);
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_180264118[0] )
    bidTraceW(off_180260DD0[0], 693248, off_180264118[0], 0);
LABEL_76:
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v35);
  return v6;
}

```

## disassembly

```asm
0x18015ccd0  mov     [rsp+arg_18], rbx
0x18015ccd5  push    rbp
0x18015ccd6  push    rsi
0x18015ccd7  push    rdi
0x18015ccd8  sub     rsp, 60h
0x18015ccdc  mov     rax, cs:__security_cookie
0x18015cce3  xor     rax, rsp
0x18015cce6  mov     [rsp+78h+var_28], rax
0x18015cceb  mov     rdi, r8
0x18015ccee  mov     rsi, rdx
0x18015ccf1  mov     rbx, rcx
0x18015ccf4  mov     [rsp+78h+var_30], 0FFFFFFFFFFFFFFFFh
0x18015ccfd  mov     eax, cs:_bidGblFlags
0x18015cd03  and     eax, 20004h
0x18015cd08  cmp     eax, 20004h
0x18015cd0d  jnz     short loc_18015CD37
0x18015cd0f  mov     rax, cs:off_1802668B0; "<GetProtocolDefaults|API|SNI> pProtElem"...
0x18015cd16  test    rax, rax
0x18015cd19  jz      short loc_18015CD37
0x18015cd1b  mov     [rsp+78h+lpString2], r8
0x18015cd20  mov     r9, rdx
0x18015cd23  mov     r8, rcx
0x18015cd26  mov     rdx, cs:off_1802668B0; "<GetProtocolDefaults|API|SNI> pProtElem"...
0x18015cd2d  lea     rcx, [rsp+78h+var_30]
0x18015cd32  call    _bidScopeEnterW
0x18015cd37  xor     ebp, ebp
0x18015cd39  mov     [rsp+78h+var_40], ebp
0x18015cd3d  mov     [rsp+78h+Buffer], rbp
0x18015cd42  mov     [rsp+78h+var_38], 0FFFFFFFFFFFFFFFFh
0x18015cd4b  mov     eax, cs:_bidGblFlags
0x18015cd51  and     eax, 20004h
0x18015cd56  cmp     eax, 20004h
0x18015cd5b  jnz     short loc_18015CD82
0x18015cd5d  mov     rax, cs:off_1802668A8; "<GetProtocolEnum|API|SNI> pszProtocol: "...
0x18015cd64  test    rax, rax
0x18015cd67  jz      short loc_18015CD82
0x18015cd69  lea     r9, [rsp+78h+var_40]
0x18015cd6e  mov     r8, rsi
0x18015cd71  mov     rdx, cs:off_1802668A8; "<GetProtocolEnum|API|SNI> pszProtocol: "...
0x18015cd78  lea     rcx, [rsp+78h+var_38]
0x18015cd7d  call    _bidScopeEnterW
0x18015cd82  mov     [rsp+78h+var_40], 8
0x18015cd8a  mov     rdx, rsi; String2
0x18015cd8d  lea     rcx, aTcp_0; "TCP"
0x18015cd94  call    cs:__imp__wcsicmp
0x18015cd9a  test    eax, eax
0x18015cd9c  jnz     short loc_18015CDA8
0x18015cd9e  mov     [rsp+78h+var_40], 6
0x18015cda6  jmp     short loc_18015CDE6
0x18015cda8  mov     rdx, rsi; String2
0x18015cdab  lea     rcx, aNp_0; "NP"
0x18015cdb2  call    cs:__imp__wcsicmp
0x18015cdb8  test    eax, eax
0x18015cdba  jnz     short loc_18015CDC6
0x18015cdbc  mov     [rsp+78h+var_40], 1
0x18015cdc4  jmp     short loc_18015CDE6
0x18015cdc6  mov     rdx, rsi; String2
0x18015cdc9  lea     rcx, aSm_2; "SM"
0x18015cdd0  call    cs:__imp__wcsicmp
0x18015cdd6  test    eax, eax
0x18015cdd8  jnz     loc_18015D109
0x18015cdde  mov     [rsp+78h+var_40], 3
0x18015cde6  mov     eax, cs:_bidGblFlags
0x18015cdec  and     eax, 20002h
0x18015cdf1  cmp     eax, 20002h
0x18015cdf6  jnz     short loc_18015CE20
0x18015cdf8  mov     rax, cs:off_180264108; "<GetProtocolEnum|RET|SNI> %d{WINERR}\n"
0x18015cdff  test    rax, rax
0x18015ce02  jz      short loc_18015CE20
0x18015ce04  xor     r9d, r9d
0x18015ce07  mov     r8, cs:off_180264108; "<GetProtocolEnum|RET|SNI> %d{WINERR}\n"
0x18015ce0e  mov     edx, 8FC00h
0x18015ce13  mov     rcx, cs:off_180260DC0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015ce1a  call    _bidTraceW
0x18015ce1f  nop
0x18015ce20  lea     rcx, [rsp+78h+var_38]; this
0x18015ce25  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x18015ce2a  nop
0x18015ce2b  mov     ecx, [rsp+78h+var_40]
0x18015ce2f  mov     [rbx], ecx
0x18015ce31  cmp     ecx, 6
0x18015ce34  jnz     short loc_18015CE50
0x18015ce36  mov     word ptr [rbx+808h], 0
0x18015ce3f  mov     byte ptr [rbx+80Ah], 0
0x18015ce46  mov     dword ptr [rbx+80Ch], 0FFFFFFFFh
0x18015ce50  sub     ecx, 1
0x18015ce53  jz      loc_18015CF5A
0x18015ce59  sub     ecx, 2
0x18015ce5c  jz      loc_18015CF16
0x18015ce62  cmp     ecx, 3
0x18015ce65  jz      short loc_18015CEC4
0x18015ce67  test    byte ptr cs:_bidGblFlags, 2
0x18015ce6e  jz      loc_18015D151
0x18015ce74  mov     rax, cs:off_180264110; "<GetProtocolDefaults|ERR|SNI> providerN"...
0x18015ce7b  test    rax, rax
0x18015ce7e  jz      loc_18015D151
0x18015ce84  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x18015ce8c  jz      loc_18015D151
0x18015ce92  mov     rax, cs:off_180248050
0x18015ce99  mov     [rsp+78h+lpString2], rbp
0x18015ce9e  mov     r9, cs:off_180264110; "<GetProtocolDefaults|ERR|SNI> providerN"...
0x18015cea5  mov     r8d, 0A7000h
0x18015ceab  mov     rdx, cs:off_180260DC8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015ceb2  mov     rcx, cs:_bidID
0x18015ceb9  call    cs:__guard_dispatch_icall_fptr
0x18015cebf  jmp     loc_18015D151
0x18015cec4  lea     rcx, [rbx+608h]
0x18015cecb  mov     edx, 100h
0x18015ced0  lea     r8, a1433; "1433"
0x18015ced7  sub     r8, rcx
0x18015ceda  nop     word ptr [rax+rax+00h]
0x18015cee0  lea     rax, [rdx+7FFFFEFEh]
0x18015cee7  test    rax, rax
0x18015ceea  jz      short loc_18015CF03
0x18015ceec  movzx   eax, word ptr [r8+rcx]
0x18015cef1  test    ax, ax
0x18015cef4  jz      short loc_18015CF03
0x18015cef6  mov     [rcx], ax
0x18015cef9  add     rcx, 2
0x18015cefd  sub     rdx, 1
0x18015cf01  jnz     short loc_18015CEE0
0x18015cf03  lea     rax, [rcx-2]
0x18015cf07  test    rdx, rdx
0x18015cf0a  cmovnz  rax, rcx
0x18015cf0e  mov     [rax], bp
0x18015cf11  jmp     loc_18015D0B3
0x18015cf16  lea     rcx, [rbx+608h]
0x18015cf1d  mov     edx, 200h
0x18015cf22  sub     rdi, rcx
0x18015cf25  nop     word ptr [rax+rax+00000000h]
0x18015cf30  lea     rax, [rdx+7FFFFDFEh]
0x18015cf37  test    rax, rax
0x18015cf3a  jz      short loc_18015CF52
0x18015cf3c  movzx   eax, word ptr [rdi+rcx]
0x18015cf40  test    ax, ax
0x18015cf43  jz      short loc_18015CF52
0x18015cf45  mov     [rcx], ax
0x18015cf48  add     rcx, 2
0x18015cf4c  sub     rdx, 1
0x18015cf50  jnz     short loc_18015CF30
0x18015cf52  test    rdx, rdx
0x18015cf55  jmp     loc_18015D0A2
0x18015cf5a  lea     r8, aClusterNetwork; "_CLUSTER_NETWORK_NAME_"
0x18015cf61  xor     edx, edx; BufferCount
0x18015cf63  lea     rcx, [rsp+78h+Buffer]; Buffer
0x18015cf68  call    cs:__imp__wdupenv_s
0x18015cf6e  test    eax, eax
0x18015cf70  jnz     loc_18015D151
0x18015cf76  lea     rsi, [rbx+608h]
0x18015cf7d  mov     ebx, 105h
0x18015cf82  mov     edx, ebx
0x18015cf84  mov     rcx, rsi
0x18015cf87  lea     r8, asc_1801ED3AC; "\\\\"
0x18015cf8e  sub     r8, rsi
0x18015cf91  lea     rax, [rdx+7FFFFEF9h]
0x18015cf98  test    rax, rax
0x18015cf9b  jz      short loc_18015CFB4
0x18015cf9d  movzx   eax, word ptr [r8+rcx]
0x18015cfa2  test    ax, ax
0x18015cfa5  jz      short loc_18015CFB4
0x18015cfa7  mov     [rcx], ax
0x18015cfaa  add     rcx, 2
0x18015cfae  sub     rdx, 1
0x18015cfb2  jnz     short loc_18015CF91
0x18015cfb4  lea     rax, [rcx-2]
0x18015cfb8  test    rdx, rdx
0x18015cfbb  cmovnz  rax, rcx
0x18015cfbf  mov     [rax], bp
0x18015cfc2  mov     [rsp+78h+cchCount2], 0FFFFFFFFh; cchCount2
0x18015cfca  lea     rax, ?gwszComputerName@@3PA_WA; wchar_t near * gwszComputerName
0x18015cfd1  mov     [rsp+78h+lpString2], rax; lpString2
0x18015cfd6  mov     r9d, 0FFFFFFFFh; cchCount1
0x18015cfdc  mov     r8, rdi; lpString1
0x18015cfdf  mov     edx, 20001h; dwCmpFlags
0x18015cfe4  mov     ecx, 800h; Locale
0x18015cfe9  call    cs:__imp_CompareStringW
0x18015cfef  cmp     eax, 2
0x18015cff2  jnz     short loc_18015D023
0x18015cff4  mov     rcx, [rsp+78h+Buffer]; String1
0x18015cff9  test    rcx, rcx
0x18015cffc  jz      short loc_18015D00F
0x18015cffe  lea     rdx, Class; String2
0x18015d005  call    cs:__imp__wcsicmp
0x18015d00b  test    eax, eax
0x18015d00d  jnz     short loc_18015D023
0x18015d00f  lea     r8, asc_1801BF298; "."
0x18015d016  mov     rdx, rbx; unsigned __int64
0x18015d019  mov     rcx, rsi; wchar_t *
0x18015d01c  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18015d021  jmp     short loc_18015D039
0x18015d023  mov     r8, rdi; wchar_t *
0x18015d026  mov     rdx, rbx; unsigned __int64
0x18015d029  mov     rcx, rsi; wchar_t *
0x18015d02c  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18015d031  test    eax, eax
0x18015d033  js      loc_18015D151
0x18015d039  mov     rcx, rbx
0x18015d03c  mov     rax, rsi
0x18015d03f  nop
0x18015d040  cmp     word ptr [rax], 0
0x18015d044  jz      short loc_18015D050
0x18015d046  add     rax, 2
0x18015d04a  sub     rcx, 1
0x18015d04e  jnz     short loc_18015D040
0x18015d050  mov     rax, rbx
0x18015d053  sub     rax, rcx
0x18015d056  test    rcx, rcx
0x18015d059  cmovz   rax, rbp
0x18015d05d  jz      loc_18015D151
0x18015d063  sub     rbx, rax
0x18015d066  lea     rcx, [rsi+rax*2]
0x18015d06a  jz      short loc_18015D09F
0x18015d06c  mov     eax, 7FFFFFFEh
0x18015d071  lea     r8, aPipeSqlQuery; "\\PIPE\\sql\\query"
0x18015d078  sub     r8, rcx
0x18015d07b  nop     dword ptr [rax+rax+00h]
0x18015d080  test    rax, rax
0x18015d083  jz      short loc_18015D09F
0x18015d085  movzx   edx, word ptr [r8+rcx]
0x18015d08a  test    dx, dx
0x18015d08d  jz      short loc_18015D09F
0x18015d08f  mov     [rcx], dx
0x18015d092  add     rcx, 2
0x18015d096  dec     rax
0x18015d099  sub     rbx, 1
0x18015d09d  jnz     short loc_18015D080
0x18015d09f  test    rbx, rbx
0x18015d0a2  lea     rax, [rcx-2]
0x18015d0a6  cmovnz  rax, rcx
0x18015d0aa  mov     [rax], bp
0x18015d0ad  jz      loc_18015D151
0x18015d0b3  mov     rcx, [rsp+78h+Buffer]; Block
0x18015d0b8  test    rcx, rcx
0x18015d0bb  jz      short loc_18015D0C3
0x18015d0bd  call    cs:__imp_free
0x18015d0c3  mov     eax, cs:_bidGblFlags
0x18015d0c9  and     eax, 20002h
0x18015d0ce  cmp     eax, 20002h
0x18015d0d3  jnz     loc_18015D1A2
0x18015d0d9  mov     rax, cs:off_180264118; "<GetProtocolDefaults|RET|SNI> %d{WINERR"...
0x18015d0e0  test    rax, rax
0x18015d0e3  jz      loc_18015D1A2
0x18015d0e9  xor     r9d, r9d
0x18015d0ec  mov     r8, cs:off_180264118; "<GetProtocolDefaults|RET|SNI> %d{WINERR"...
0x18015d0f3  mov     edx, 0A9400h
0x18015d0f8  mov     rcx, cs:off_180260DD0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015d0ff  call    _bidTraceW
0x18015d104  jmp     loc_18015D1A2
0x18015d109  mov     eax, cs:_bidGblFlags
0x18015d10f  and     eax, 20002h
0x18015d114  cmp     eax, 20002h
0x18015d119  jnz     short loc_18015D146
0x18015d11b  mov     rax, cs:off_180264100; "<GetProtocolEnum|RET|SNI> %d{WINERR}\n"
0x18015d122  test    rax, rax
0x18015d125  jz      short loc_18015D146
0x18015d127  mov     r9d, 0FFFFFFFFh
0x18015d12d  mov     r8, cs:off_180264100; "<GetProtocolEnum|RET|SNI> %d{WINERR}\n"
0x18015d134  mov     edx, 8E800h
0x18015d139  mov     rcx, cs:off_180260DB8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015d140  call    _bidTraceW
0x18015d145  nop
0x18015d146  lea     rcx, [rsp+78h+var_38]; this
0x18015d14b  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x18015d150  nop
0x18015d151  mov     rcx, [rsp+78h+Buffer]; Block
0x18015d156  test    rcx, rcx
0x18015d159  jz      short loc_18015D161
0x18015d15b  call    cs:__imp_free
0x18015d161  mov     eax, cs:_bidGblFlags
0x18015d167  and     eax, 20002h
0x18015d16c  cmp     eax, 20002h
0x18015d171  jnz     short loc_18015D19D
0x18015d173  mov     rax, cs:off_180264120; "<GetProtocolDefaults|RET|SNI> %d{WINERR"...
0x18015d17a  test    rax, rax
0x18015d17d  jz      short loc_18015D19D
0x18015d17f  mov     r9d, 0FFFFFFFFh
0x18015d185  mov     r8, cs:off_180264120; "<GetProtocolDefaults|RET|SNI> %d{WINERR"...
0x18015d18c  mov     edx, 0AC000h
0x18015d191  mov     rcx, cs:off_180260DD8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015d198  call    _bidTraceW
0x18015d19d  mov     ebp, 0FFFFFFFFh
0x18015d1a2  lea     rcx, [rsp+78h+var_30]; this
0x18015d1a7  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x18015d1ac  nop
0x18015d1ad  mov     eax, ebp
0x18015d1af  mov     rcx, [rsp+78h+var_28]
0x18015d1b4  xor     rcx, rsp; StackCookie
0x18015d1b7  call    __security_check_cookie
0x18015d1bc  mov     rbx, [rsp+78h+arg_18]
0x18015d1c4  add     rsp, 60h
0x18015d1c8  pop     rdi
0x18015d1c9  pop     rsi
0x18015d1ca  pop     rbp
0x18015d1cb  retn
```
