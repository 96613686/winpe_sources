# IISFilterEvents::FILTER_START::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *)

- ea: `0x18000c12c`
- end: `0x18000c216`
- name: `?RaiseEvent@FILTER_START@IISFilterEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBG@Z`
- size: `234`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003a20`
- `0x180006440`

## callees

- `0x18000c12c`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall IISFilterEvents::FILTER_START::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2,
        const unsigned __int16 *a3)
{
  int v3; // eax
  __int64 v4; // rax
  _QWORD v6[6]; // [rsp+20h] [rbp-59h] BYREF
  __int128 v7; // [rsp+50h] [rbp-29h]
  int v8; // [rsp+60h] [rbp-19h]
  int v9; // [rsp+64h] [rbp-15h]
  int v10; // [rsp+68h] [rbp-11h]
  _QWORD v11[2]; // [rsp+6Ch] [rbp-Dh] BYREF
  const wchar_t *v12; // [rsp+80h] [rbp+7h] BYREF
  int v13; // [rsp+88h] [rbp+Fh]
  __int64 v14; // [rsp+90h] [rbp+17h]
  int v15; // [rsp+98h] [rbp+1Fh]
  __int64 v16; // [rsp+A0h] [rbp+27h]
  const wchar_t *v17; // [rsp+A8h] [rbp+2Fh]
  int v18; // [rsp+B0h] [rbp+37h]
  const unsigned __int16 *v19; // [rsp+B8h] [rbp+3Fh]
  int v20; // [rsp+C0h] [rbp+47h]
  __int64 v21; // [rsp+C8h] [rbp+4Fh]

  v6[1] = 8;
  memset(v11, 0, 12);
  v6[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v6[2] = &`IISFilterEvents::GetAreaGuid'::`2'::AreaGuid;
  v6[4] = L"FILTER_START";
  v12 = L"ContextId";
  v6[3] = 1;
  v17 = L"FilterName";
  v6[5] = 1;
  v10 = 2;
  v7 = 0;
  v8 = 0;
  v9 = 1;
  v13 = 72;
  v14 = 0;
  v15 = 16;
  v16 = 0;
  v18 = 31;
  v19 = a3;
  if ( a3 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a3[v4] );
    v3 = 2 * v4 + 2;
  }
  else
  {
    v3 = 0;
  }
  v20 = v3;
  v21 = 0;
  *(_QWORD *)((char *)v11 + 4) = &v12;
  (*(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(*(_QWORD *)a1 + 16LL))(a1, v6);
  return 0;
}

```

## disassembly

```asm
0x18000c12c  push    rbp
0x18000c12e  lea     rbp, [rsp-57h]
0x18000c133  sub     rsp, 0D0h
0x18000c13a  xor     eax, eax
0x18000c13c  mov     [rbp+57h+var_A8], 8
0x18000c144  mov     [rbp+57h+var_64], rax
0x18000c148  xor     r9d, r9d
0x18000c14b  mov     [rbp+57h+var_5C], eax
0x18000c14e  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000c155  mov     [rbp+57h+var_B0], rax
0x18000c159  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISFilterEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISFilterEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000c160  mov     [rbp+57h+var_A0], rax
0x18000c164  lea     rax, aFilterStart; "FILTER_START"
0x18000c16b  mov     [rbp+57h+var_90], rax
0x18000c16f  lea     rax, aContextid; "ContextId"
0x18000c176  mov     [rbp+57h+var_50], rax
0x18000c17a  mov     edx, 1
0x18000c17f  mov     [rbp+57h+var_98], 1
0x18000c187  lea     rax, aFiltername; "FilterName"
0x18000c18e  mov     [rbp+57h+var_28], rax
0x18000c192  xorps   xmm0, xmm0
0x18000c195  mov     [rbp+57h+var_88], rdx
0x18000c199  mov     [rbp+57h+var_68], 2
0x18000c1a0  movdqa  [rbp+57h+var_80], xmm0
0x18000c1a5  mov     [rbp+57h+var_70], r9d
0x18000c1a9  mov     [rbp+57h+var_6C], edx
0x18000c1ac  mov     [rbp+57h+var_48], 48h ; 'H'
0x18000c1b3  mov     [rbp+57h+var_40], r9
0x18000c1b7  mov     [rbp+57h+var_38], 10h
0x18000c1be  mov     [rbp+57h+var_30], r9
0x18000c1c2  mov     [rbp+57h+var_20], 1Fh
0x18000c1c9  mov     [rbp+57h+var_18], r8
0x18000c1cd  test    r8, r8
0x18000c1d0  jnz     short loc_18000C1D7
0x18000c1d2  mov     eax, r9d
0x18000c1d5  jmp     short loc_18000C1EC
0x18000c1d7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c1db  inc     rax
0x18000c1de  cmp     [r8+rax*2], r9w
0x18000c1e3  jnz     short loc_18000C1DB
0x18000c1e5  lea     eax, ds:2[rax*2]
0x18000c1ec  mov     [rbp+57h+var_10], eax
0x18000c1ef  lea     rdx, [rbp+57h+var_B0]
0x18000c1f3  lea     rax, [rbp+57h+var_50]
0x18000c1f7  mov     [rbp+57h+var_8], r9
0x18000c1fb  mov     [rbp+57h+var_64+4], rax
0x18000c1ff  mov     rax, [rcx]
0x18000c202  mov     rax, [rax+10h]
0x18000c206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c20b  xor     eax, eax
0x18000c20d  add     rsp, 0D0h
0x18000c214  pop     rbp
0x18000c215  retn
```
