# myFormCertRegPath(ushort const *,ushort const *,ushort const *,CSRegPathType,ushort * *)

- ea: `0x180026810`
- end: `0x180026901`
- name: `?myFormCertRegPath@@YAJPEBG00W4CSRegPathType@@PEAPEAG@Z`
- size: `241`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180025f68`

## callees

- `0x18000b940`
- `0x18000b9cc`
- `0x1800159e0`
- `0x180026810`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002689a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002689a`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002684f`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002684f`

## string_xrefs

- `0x1800268b6`: `SYSTEM\CurrentControlSet\Services\CertSvc\Configuration`

## pseudocode

```c
__int64 __fastcall myFormCertRegPath(
        const unsigned __int16 *a1,
        __int64 a2,
        SIZE_T a3,
        __int64 a4,
        unsigned __int16 **a5)
{
  __int64 v6; // rax
  unsigned __int64 v7; // rax
  unsigned int v8; // ecx
  int v9; // edx
  unsigned int v10; // ebx
  unsigned __int64 v12; // rdi
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // rbx
  SIZE_T uBytes; // [rsp+60h] [rbp+18h] BYREF

  uBytes = a3;
  if ( a1 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a1[v6] );
    v7 = v6 + 56;
    uBytes = 0;
    if ( v7 < 0x37 )
      goto LABEL_5;
  }
  else
  {
    uBytes = 0;
    v7 = 55;
  }
  v12 = v7 + 1;
  if ( v7 + 1 < v7 )
  {
LABEL_5:
    v8 = 6095285;
LABEL_6:
    v9 = -2147024362;
    v10 = -2147024362;
LABEL_7:
    CSPrintErrorLineFile(v8, v9);
    return v10;
  }
  if ( (int)ULongLongMult(v7 + 1, 2u, &uBytes) < 0 )
  {
    v8 = 6488501;
    goto LABEL_6;
  }
  v13 = (unsigned __int16 *)LocalAlloc(0x40u, uBytes);
  v14 = v13;
  if ( !v13 )
  {
    v10 = -2147024882;
    v8 = 7012789;
    v9 = -2147024882;
    goto LABEL_7;
  }
  StringCchCopyW(v13, v12, L"SYSTEM\\CurrentControlSet\\Services\\CertSvc\\Configuration");
  if ( a1 )
  {
    if ( *v14 )
      StringCchCatW(v14, v12, L"\\");
    StringCchCatW(v14, v12, a1);
  }
  *a5 = v14;
  return 0;
}

```

## disassembly

```asm
0x180026810  mov     [rsp+uBytes], r8
0x180026815  push    rbx
0x180026816  push    rbp
0x180026817  push    rsi
0x180026818  push    rdi
0x180026819  sub     rsp, 28h
0x18002681d  xor     ebp, ebp
0x18002681f  mov     rsi, rcx
0x180026822  test    rcx, rcx
0x180026825  jz      short loc_180026860
0x180026827  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002682b  inc     rax
0x18002682e  cmp     [rcx+rax*2], bp
0x180026832  jnz     short loc_18002682B
0x180026834  add     rax, 38h ; '8'
0x180026838  mov     [rsp+48h+uBytes], rbp
0x18002683d  cmp     rax, 37h ; '7'
0x180026841  jnb     short loc_18002686A
0x180026843  mov     ecx, 5D01B5h
0x180026848  mov     edx, 80070216h
0x18002684d  mov     ebx, edx
0x18002684f  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180026855  mov     eax, ebx
0x180026857  add     rsp, 28h
0x18002685b  pop     rdi
0x18002685c  pop     rsi
0x18002685d  pop     rbp
0x18002685e  pop     rbx
0x18002685f  retn
0x180026860  mov     [rsp+48h+uBytes], rbp
0x180026865  mov     eax, 37h ; '7'
0x18002686a  lea     rdi, [rax+1]
0x18002686e  cmp     rdi, rax
0x180026871  jb      short loc_180026843
0x180026873  lea     r8, [rsp+48h+uBytes]; unsigned __int64 *
0x180026878  mov     edx, 2; unsigned __int64
0x18002687d  mov     rcx, rdi; unsigned __int64
0x180026880  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180026885  test    eax, eax
0x180026887  jns     short loc_180026890
0x180026889  mov     ecx, 6301B5h
0x18002688e  jmp     short loc_180026848
0x180026890  mov     rdx, [rsp+48h+uBytes]; uBytes
0x180026895  mov     ecx, 40h ; '@'; uFlags
0x18002689a  call    cs:__imp_LocalAlloc
0x1800268a0  mov     rbx, rax
0x1800268a3  test    rax, rax
0x1800268a6  jnz     short loc_1800268B6
0x1800268a8  mov     ebx, 8007000Eh
0x1800268ad  mov     ecx, 6B01B5h
0x1800268b2  mov     edx, ebx
0x1800268b4  jmp     short loc_18002684F
0x1800268b6  lea     r8, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ce"...
0x1800268bd  mov     rdx, rdi; unsigned __int64
0x1800268c0  mov     rcx, rbx; unsigned __int16 *
0x1800268c3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800268c8  test    rsi, rsi
0x1800268cb  jz      short loc_1800268F2
0x1800268cd  cmp     bp, [rbx]
0x1800268d0  jz      short loc_1800268E4
0x1800268d2  lea     r8, SubStr; "\\"
0x1800268d9  mov     rdx, rdi; unsigned __int64
0x1800268dc  mov     rcx, rbx; unsigned __int16 *
0x1800268df  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800268e4  mov     r8, rsi; unsigned __int16 *
0x1800268e7  mov     rdx, rdi; unsigned __int64
0x1800268ea  mov     rcx, rbx; unsigned __int16 *
0x1800268ed  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800268f2  mov     rax, [rsp+48h+arg_20]
0x1800268f7  mov     [rax], rbx
0x1800268fa  mov     ebx, ebp
0x1800268fc  jmp     loc_180026855
```
