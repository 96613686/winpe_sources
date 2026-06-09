# RetrieveStringTypeAttributes(std::vector<_CACHE_WSTRING_ATTRIBUTE_VARIABLE,std::allocator<_CACHE_WSTRING_ATTRIBUTE_VARIABLE>> &,Windows::Compat::Inventory::InventoryCacheItem *)

- ea: `0x18005fb10`
- end: `0x18005fedf`
- name: `?RetrieveStringTypeAttributes@@YAKAEAV?$vector@U_CACHE_WSTRING_ATTRIBUTE_VARIABLE@@V?$allocator@U_CACHE_WSTRING_ATTRIBUTE_VARIABLE@@@std@@@std@@PEAVInventoryCacheItem@Inventory@Compat@Windows@@@Z`
- size: `975`
- prototype: ``
- caller_count: `7`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001d920`
- `0x1800227a0`
- `0x18004a950`
- `0x18004bb00`
- `0x18004d1c0`
- `0x180058120`
- `0x180058f90`

## callees

- `0x180006d02`
- `0x180007014`
- `0x18005e35c`
- `0x18005fb10`
- `0x18006041c`
- `0x180066c10`
- `0x180116010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005fea7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005fea7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18005fb34`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18005fb34`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x18005fc73`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x18005fc73`

## string_xrefs

- `0x18005fcd0`: `InventoryCacheItem::GetItemProperty failed, [%#x], %ws`
- `0x18005fd31`: `InventoryCacheItem::GetItemProperty failed, [%#x], %ws`
- `0x18005fd6c`: `InventoryCacheItem::GetItemProperty failed, [%#x], %ws`
- `0x18005fd87`: `InventoryCacheItem::GetItemProperty failed, [%#x], %ws`

## pseudocode

```c
__int64 __fastcall RetrieveStringTypeAttributes(__int64 *a1, __int64 *a2)
{
  __int64 *v3; // rbx
  wchar_t *v4; // r15
  unsigned __int16 v5; // bx
  FILE *v6; // rax
  FILE *v7; // rax
  FILE *v8; // rax
  __int64 v9; // rcx
  __int64 v10; // r13
  int v11; // eax
  int v12; // r12d
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rdx
  FILE *v16; // rax
  __int64 v17; // rbx
  FILE *v18; // rax
  FILE *v19; // rax
  const wchar_t *v20; // rcx
  int v21; // edi
  FILE *v22; // rax
  FILE *v23; // rax
  FILE *v24; // rax
  __int64 v27; // [rsp+20h] [rbp-48h]
  __int64 v28; // [rsp+20h] [rbp-48h]
  unsigned int v30; // [rsp+80h] [rbp+18h] BYREF
  int i; // [rsp+88h] [rbp+20h]

  v3 = a2;
  v4 = (wchar_t *)malloc(0x208u);
  if ( !v4 )
  {
    v5 = 14;
    AslLogCallPrintf(2, "RetrieveStringTypeAttributes", 1327, "Out of memory [%#x]", -2147024882);
    if ( EnableDevInvStdErrLog )
    {
      v6 = o___acrt_iob_func_0(2u);
      fprintf(v6, "Error: %s, %u: ", "RetrieveStringTypeAttributes", 1327);
      v7 = o___acrt_iob_func_0(2u);
      fprintf(v7, "Out of memory [%#x]", -2147024882);
      v8 = o___acrt_iob_func_0(2u);
      fprintf(v8, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, "Out of memory [%#x]", -2147024882);
    AslLogCallPrintf(1, "RetrieveStringTypeAttributes", 1327, "Out of memory [%#x]", -2147024882);
    return v5;
  }
  v9 = *a1;
  if ( !((a1[1] - *a1) >> 4) )
  {
LABEL_28:
    v21 = 0;
    goto LABEL_29;
  }
  v10 = 0;
  v11 = 260;
  for ( i = 260; ; v11 = i )
  {
    v30 = v11;
    v12 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, wchar_t *, unsigned int *))(*v3 + 64))(
            v3,
            *(_QWORD *)(v9 + 16 * v10),
            v4,
            &v30);
    if ( v12 != -2147024662 )
      goto LABEL_12;
    v13 = _o_realloc(v4, 2LL * v30);
    if ( !v13 )
      break;
    v14 = *v3;
    v15 = *a1;
    v4 = (wchar_t *)v13;
    i = v30;
    v12 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, unsigned int *))(v14 + 64))(
            v3,
            *(_QWORD *)(v15 + 16 * v10),
            v13,
            &v30);
LABEL_12:
    if ( v12 >= 0 )
    {
      v20 = v4;
    }
    else
    {
      if ( v12 != -2147024894 )
      {
        LODWORD(v27) = v12;
        AslLogCallPrintf(
          2,
          "RetrieveStringTypeAttributes",
          1359,
          "InventoryCacheItem::GetItemProperty failed, [%#x], %ws",
          v27,
          *(_QWORD *)(*a1 + 16 * v10));
        if ( EnableDevInvStdErrLog )
        {
          v16 = o___acrt_iob_func_0(2u);
          fprintf(v16, "Error: %s, %u: ", "RetrieveStringTypeAttributes", 1359);
          v17 = *(_QWORD *)(*a1 + 16 * v10);
          v18 = o___acrt_iob_func_0(2u);
          fprintf(v18, "InventoryCacheItem::GetItemProperty failed, [%#x], %ws", (unsigned int)v12, v17);
          v19 = o___acrt_iob_func_0(2u);
          fprintf(v19, "\n");
          v3 = a2;
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(
            0x2000000,
            "InventoryCacheItem::GetItemProperty failed, [%#x], %ws",
            (unsigned int)v12,
            *(_QWORD *)(*a1 + 16 * v10));
        LODWORD(v28) = v12;
        AslLogCallPrintf(
          1,
          "RetrieveStringTypeAttributes",
          1359,
          "InventoryCacheItem::GetItemProperty failed, [%#x], %ws",
          v28,
          *(_QWORD *)(*a1 + 16 * v10));
      }
      v20 = &S2;
    }
    PwstrToWstringNoChange(v20, *(_QWORD *)(*a1 + 16 * v10 + 8));
    v9 = *a1;
    if ( ++v10 >= (unsigned __int64)((a1[1] - *a1) >> 4) )
      goto LABEL_28;
  }
  v21 = -2147024882;
  AslLogCallPrintf(2, "RetrieveStringTypeAttributes", 1343, "Out of memory [%#x]", -2147024882);
  if ( EnableDevInvStdErrLog )
  {
    v22 = o___acrt_iob_func_0(2u);
    fprintf(v22, "Error: %s, %u: ", "RetrieveStringTypeAttributes", 1343);
    v23 = o___acrt_iob_func_0(2u);
    fprintf(v23, "Out of memory [%#x]", -2147024882);
    v24 = o___acrt_iob_func_0(2u);
    fprintf(v24, "\n");
  }
  if ( g_DeviceMapLogFunction )
    TraceMessageCallback(0x2000000, "Out of memory [%#x]", -2147024882);
  AslLogCallPrintf(1, "RetrieveStringTypeAttributes", 1343, "Out of memory [%#x]", -2147024882);
LABEL_29:
  free(v4);
  if ( v21 < 0 )
    return (unsigned __int16)v21;
  return 0;
}

```

## disassembly

```asm
0x18005fb10  mov     [rsp+arg_0], rbx
0x18005fb15  mov     [rsp+arg_8], rdx
0x18005fb1a  push    rbp
0x18005fb1b  push    rsi
0x18005fb1c  push    rdi
0x18005fb1d  push    r12
0x18005fb1f  push    r13
0x18005fb21  push    r14
0x18005fb23  push    r15
0x18005fb25  sub     rsp, 30h
0x18005fb29  mov     rdi, rcx
0x18005fb2c  mov     rbx, rdx
0x18005fb2f  mov     ecx, 208h; Size
0x18005fb34  call    cs:__imp_malloc
0x18005fb3a  mov     r15, rax
0x18005fb3d  test    rax, rax
0x18005fb40  jnz     loc_18005FC00
0x18005fb46  lea     r14d, [rax+2]
0x18005fb4a  mov     edi, 52Fh
0x18005fb4f  lea     rsi, aOutOfMemoryX; "Out of memory [%#x]"
0x18005fb56  mov     ebx, 8007000Eh
0x18005fb5b  lea     rbp, aRetrievestring; "RetrieveStringTypeAttributes"
0x18005fb62  mov     dword ptr [rsp+68h+var_48], ebx
0x18005fb66  mov     r9, rsi
0x18005fb69  mov     r8d, edi
0x18005fb6c  mov     rdx, rbp
0x18005fb6f  mov     ecx, r14d
0x18005fb72  call    AslLogCallPrintf
0x18005fb77  cmp     cs:EnableDevInvStdErrLog, r15d
0x18005fb7e  jz      short loc_18005FBCA
0x18005fb80  mov     ecx, r14d; Ix
0x18005fb83  call    _o___acrt_iob_func_0
0x18005fb88  mov     rcx, rax; Stream
0x18005fb8b  lea     rdx, Format; "Error: %s, %u: "
0x18005fb92  mov     r9d, edi
0x18005fb95  mov     r8, rbp
0x18005fb98  call    fprintf
0x18005fb9d  mov     ecx, r14d; Ix
0x18005fba0  call    _o___acrt_iob_func_0
0x18005fba5  mov     rcx, rax; Stream
0x18005fba8  mov     r8d, ebx
0x18005fbab  mov     rdx, rsi; Format
0x18005fbae  call    fprintf
0x18005fbb3  mov     ecx, r14d; Ix
0x18005fbb6  call    _o___acrt_iob_func_0
0x18005fbbb  mov     rcx, rax; Stream
0x18005fbbe  lea     rdx, asc_18011EAD8; "\n"
0x18005fbc5  call    fprintf
0x18005fbca  cmp     cs:g_DeviceMapLogFunction, 0
0x18005fbd2  jz      short loc_18005FBE4
0x18005fbd4  mov     r8d, ebx
0x18005fbd7  mov     rdx, rsi
0x18005fbda  mov     ecx, 2000000h
0x18005fbdf  call    TraceMessageCallback
0x18005fbe4  mov     r9, rsi
0x18005fbe7  mov     dword ptr [rsp+68h+var_48], ebx
0x18005fbeb  mov     r8, rdi
0x18005fbee  mov     rdx, rbp
0x18005fbf1  mov     ecx, 1
0x18005fbf6  call    AslLogCallPrintf
0x18005fbfb  jmp     loc_18005FEC5
0x18005fc00  mov     rcx, [rdi]
0x18005fc03  mov     rax, [rdi+8]
0x18005fc07  sub     rax, rcx
0x18005fc0a  sar     rax, 4
0x18005fc0e  test    rax, rax
0x18005fc11  jz      loc_18005FE9D
0x18005fc17  xor     r13d, r13d
0x18005fc1a  lea     rbp, aRetrievestring; "RetrieveStringTypeAttributes"
0x18005fc21  mov     eax, 104h
0x18005fc26  mov     [rsp+68h+arg_18], eax
0x18005fc2d  lea     r14d, [r13+2]
0x18005fc31  mov     [rsp+68h+arg_10], eax
0x18005fc38  lea     r9, [rsp+68h+arg_10]
0x18005fc40  mov     rax, [rbx]
0x18005fc43  mov     rsi, r13
0x18005fc46  add     rsi, rsi
0x18005fc49  mov     r8, r15
0x18005fc4c  mov     rax, [rax+40h]
0x18005fc50  mov     rdx, [rcx+rsi*8]
0x18005fc54  mov     rcx, rbx
0x18005fc57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fc5c  mov     r12d, eax
0x18005fc5f  cmp     eax, 800700EAh
0x18005fc64  jnz     short loc_18005FCB7
0x18005fc66  mov     edx, [rsp+68h+arg_10]
0x18005fc6d  mov     rcx, r15
0x18005fc70  add     rdx, rdx
0x18005fc73  call    cs:__imp__o_realloc
0x18005fc79  mov     r8, rax
0x18005fc7c  test    rax, rax
0x18005fc7f  jz      loc_18005FDEE
0x18005fc85  mov     rcx, [rbx]
0x18005fc88  lea     r9, [rsp+68h+arg_10]
0x18005fc90  mov     rdx, [rdi]
0x18005fc93  mov     r15, rax
0x18005fc96  mov     eax, [rsp+68h+arg_10]
0x18005fc9d  mov     [rsp+68h+arg_18], eax
0x18005fca4  mov     rax, [rcx+40h]
0x18005fca8  mov     rcx, rbx
0x18005fcab  mov     rdx, [rdx+rsi*8]
0x18005fcaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fcb4  mov     r12d, eax
0x18005fcb7  test    r12d, r12d
0x18005fcba  jns     loc_18005FDB8
0x18005fcc0  cmp     r12d, 80070002h
0x18005fcc7  jz      loc_18005FDAF
0x18005fccd  mov     rax, [rdi]
0x18005fcd0  lea     r9, aInventorycache_2; "InventoryCacheItem::GetItemProperty fai"...
0x18005fcd7  mov     r8d, 54Fh
0x18005fcdd  mov     rdx, rbp
0x18005fce0  mov     rcx, [rax+rsi*8]
0x18005fce4  mov     [rsp+68h+var_40], rcx
0x18005fce9  mov     ecx, r14d
0x18005fcec  mov     dword ptr [rsp+68h+var_48], r12d
0x18005fcf1  call    AslLogCallPrintf
0x18005fcf6  cmp     cs:EnableDevInvStdErrLog, 0
0x18005fcfd  jz      short loc_18005FD5F
0x18005fcff  mov     ecx, r14d; Ix
0x18005fd02  call    _o___acrt_iob_func_0
0x18005fd07  mov     rcx, rax; Stream
0x18005fd0a  lea     rdx, Format; "Error: %s, %u: "
0x18005fd11  mov     r9d, 54Fh
0x18005fd17  mov     r8, rbp
0x18005fd1a  call    fprintf
0x18005fd1f  mov     rax, [rdi]
0x18005fd22  mov     ecx, r14d; Ix
0x18005fd25  mov     rbx, [rax+rsi*8]
0x18005fd29  call    _o___acrt_iob_func_0
0x18005fd2e  mov     r9, rbx
0x18005fd31  lea     rdx, aInventorycache_2; "InventoryCacheItem::GetItemProperty fai"...
0x18005fd38  mov     r8d, r12d
0x18005fd3b  mov     rcx, rax; Stream
0x18005fd3e  call    fprintf
0x18005fd43  mov     ecx, r14d; Ix
0x18005fd46  call    _o___acrt_iob_func_0
0x18005fd4b  mov     rcx, rax; Stream
0x18005fd4e  lea     rdx, asc_18011EAD8; "\n"
0x18005fd55  call    fprintf
0x18005fd5a  mov     rbx, [rsp+68h+arg_8]
0x18005fd5f  cmp     cs:g_DeviceMapLogFunction, 0
0x18005fd67  jz      short loc_18005FD84
0x18005fd69  mov     r9, [rdi]
0x18005fd6c  lea     rdx, aInventorycache_2; "InventoryCacheItem::GetItemProperty fai"...
0x18005fd73  mov     r8d, r12d
0x18005fd76  mov     ecx, 2000000h
0x18005fd7b  mov     r9, [r9+rsi*8]
0x18005fd7f  call    TraceMessageCallback
0x18005fd84  mov     rax, [rdi]
0x18005fd87  lea     r9, aInventorycache_2; "InventoryCacheItem::GetItemProperty fai"...
0x18005fd8e  mov     r8d, 54Fh
0x18005fd94  mov     rdx, rbp
0x18005fd97  mov     rcx, [rax+rsi*8]
0x18005fd9b  mov     [rsp+68h+var_40], rcx
0x18005fda0  mov     ecx, 1
0x18005fda5  mov     dword ptr [rsp+68h+var_48], r12d
0x18005fdaa  call    AslLogCallPrintf
0x18005fdaf  lea     rcx, S2
0x18005fdb6  jmp     short loc_18005FDBB
0x18005fdb8  mov     rcx, r15
0x18005fdbb  mov     rax, [rdi]
0x18005fdbe  mov     rdx, [rax+rsi*8+8]
0x18005fdc3  call    ?PwstrToWstringNoChange@@YAKPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PwstrToWstringNoChange(ushort const *,std::wstring &)
0x18005fdc8  mov     rcx, [rdi]
0x18005fdcb  inc     r13
0x18005fdce  mov     rax, [rdi+8]
0x18005fdd2  sub     rax, rcx
0x18005fdd5  sar     rax, 4
0x18005fdd9  cmp     r13, rax
0x18005fddc  jnb     loc_18005FE9D
0x18005fde2  mov     eax, [rsp+68h+arg_18]
0x18005fde9  jmp     loc_18005FC31
0x18005fdee  mov     ebx, 8007000Eh
0x18005fdf3  lea     rsi, aOutOfMemoryX; "Out of memory [%#x]"
0x18005fdfa  mov     r12d, 53Fh
0x18005fe00  mov     dword ptr [rsp+68h+var_48], ebx
0x18005fe04  mov     r9, rsi
0x18005fe07  mov     r8d, r12d
0x18005fe0a  mov     rdx, rbp
0x18005fe0d  mov     ecx, r14d
0x18005fe10  mov     edi, ebx
0x18005fe12  call    AslLogCallPrintf
0x18005fe17  cmp     cs:EnableDevInvStdErrLog, 0
0x18005fe1e  jz      short loc_18005FE6A
0x18005fe20  mov     ecx, r14d; Ix
0x18005fe23  call    _o___acrt_iob_func_0
0x18005fe28  mov     rcx, rax; Stream
0x18005fe2b  lea     rdx, Format; "Error: %s, %u: "
0x18005fe32  mov     r9d, r12d
0x18005fe35  mov     r8, rbp
0x18005fe38  call    fprintf
0x18005fe3d  mov     ecx, r14d; Ix
0x18005fe40  call    _o___acrt_iob_func_0
0x18005fe45  mov     rcx, rax; Stream
0x18005fe48  mov     r8d, ebx
0x18005fe4b  mov     rdx, rsi; Format
0x18005fe4e  call    fprintf
0x18005fe53  mov     ecx, r14d; Ix
0x18005fe56  call    _o___acrt_iob_func_0
0x18005fe5b  mov     rcx, rax; Stream
0x18005fe5e  lea     rdx, asc_18011EAD8; "\n"
0x18005fe65  call    fprintf
0x18005fe6a  cmp     cs:g_DeviceMapLogFunction, 0
0x18005fe72  jz      short loc_18005FE84
0x18005fe74  mov     r8d, ebx
0x18005fe77  mov     rdx, rsi
0x18005fe7a  mov     ecx, 2000000h
0x18005fe7f  call    TraceMessageCallback
0x18005fe84  mov     r9, rsi
0x18005fe87  mov     dword ptr [rsp+68h+var_48], ebx
0x18005fe8b  mov     r8, r12
0x18005fe8e  mov     rdx, rbp
0x18005fe91  mov     ecx, 1
0x18005fe96  call    AslLogCallPrintf
0x18005fe9b  jmp     short loc_18005FE9F
0x18005fe9d  xor     edi, edi
0x18005fe9f  test    r15, r15
0x18005fea2  jz      short loc_18005FEAD
0x18005fea4  mov     rcx, r15; Block
0x18005fea7  call    cs:__imp_free
0x18005fead  test    edi, edi
0x18005feaf  js      short loc_18005FEB5
0x18005feb1  xor     edi, edi
0x18005feb3  jmp     short loc_18005FEC8
0x18005feb5  mov     eax, edi
0x18005feb7  mov     ebx, edi
0x18005feb9  and     eax, 1FFF0000h
0x18005febe  cmp     eax, 70000h
0x18005fec3  jnz     short loc_18005FEC8
0x18005fec5  movzx   edi, bx
0x18005fec8  mov     rbx, [rsp+68h+arg_0]
0x18005fecd  mov     eax, edi
0x18005fecf  add     rsp, 30h
0x18005fed3  pop     r15
0x18005fed5  pop     r14
0x18005fed7  pop     r13
0x18005fed9  pop     r12
0x18005fedb  pop     rdi
0x18005fedc  pop     rsi
0x18005fedd  pop     rbp
0x18005fede  retn
```
