# IsPathInDriverStore

- ea: `0x1800362e4`
- end: `0x1800363c0`
- name: `IsPathInDriverStore`
- size: `220`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000d080`
- `0x1800281a0`

## callees

- `0x180002300`
- `0x180002f48`
- `0x1800078f0`
- `0x1800362e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180036390`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180036390`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180036329`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180036329`

## pseudocode

```c
_BOOL8 __fastcall IsPathInDriverStore(__int64 a1)
{
  UINT SystemDirectoryW; // eax
  __int64 v4; // r8
  WCHAR Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  memset_0(Buffer, 0, 0x208u);
  if ( a1
    && (SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u)) != 0
    && (Buffer[SystemDirectoryW - 1] == 92 || StringCchCatW(Buffer, 0x104u, L"\\") >= 0)
    && StringCchCatW(Buffer, 0x104u, L"DriverStore\\FileRepository") >= 0 )
  {
    v4 = -1;
    do
      ++v4;
    while ( Buffer[v4] );
    return _o__wcsnicmp(Buffer, a1) == 0;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x1800362e4  mov     [rsp+arg_8], rbx
0x1800362e9  push    rdi
0x1800362ea  sub     rsp, 240h
0x1800362f1  mov     rax, cs:__security_cookie
0x1800362f8  xor     rax, rsp
0x1800362fb  mov     [rsp+248h+var_18], rax
0x180036303  mov     rbx, rcx
0x180036306  xor     edx, edx; Val
0x180036308  lea     rcx, [rsp+248h+Buffer]; void *
0x18003630d  mov     r8d, 208h; Size
0x180036313  call    memset_0
0x180036318  xor     edi, edi
0x18003631a  test    rbx, rbx
0x18003631d  jz      short loc_180036371
0x18003631f  mov     edx, 104h; uSize
0x180036324  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x180036329  call    cs:__imp_GetSystemDirectoryW
0x18003632f  test    eax, eax
0x180036331  jz      short loc_180036371
0x180036333  dec     eax
0x180036335  cmp     [rsp+rax*2+248h+Buffer], 5Ch ; '\'
0x18003633b  jz      short loc_180036357
0x18003633d  lea     r8, SubBlock; "\\"
0x180036344  mov     edx, 104h; unsigned __int64
0x180036349  lea     rcx, [rsp+248h+Buffer]; unsigned __int16 *
0x18003634e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180036353  test    eax, eax
0x180036355  js      short loc_180036371
0x180036357  lea     r8, aDriverstoreFil_0; "DriverStore\\FileRepository"
0x18003635e  mov     edx, 104h; unsigned __int64
0x180036363  lea     rcx, [rsp+248h+Buffer]; unsigned __int16 *
0x180036368  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003636d  test    eax, eax
0x18003636f  jns     short loc_180036375
0x180036371  mov     ecx, edi
0x180036373  jmp     short loc_18003639D
0x180036375  lea     rax, [rsp+248h+Buffer]
0x18003637a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003637e  inc     r8
0x180036381  cmp     [rax+r8*2], di
0x180036386  jnz     short loc_18003637E
0x180036388  mov     rdx, rbx
0x18003638b  lea     rcx, [rsp+248h+Buffer]
0x180036390  call    cs:__imp__o__wcsnicmp
0x180036396  test    eax, eax
0x180036398  mov     ecx, edi
0x18003639a  setz    cl
0x18003639d  mov     eax, ecx
0x18003639f  mov     rcx, [rsp+248h+var_18]
0x1800363a7  xor     rcx, rsp; StackCookie
0x1800363aa  call    __security_check_cookie
0x1800363af  mov     rbx, [rsp+248h+arg_8]
0x1800363b7  add     rsp, 240h
0x1800363be  pop     rdi
0x1800363bf  retn
```
