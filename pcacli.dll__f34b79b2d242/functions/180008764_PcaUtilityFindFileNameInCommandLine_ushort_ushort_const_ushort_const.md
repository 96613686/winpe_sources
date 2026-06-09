# PcaUtilityFindFileNameInCommandLine(ushort *,ushort const *,ushort const *)

- ea: `0x180008764`
- end: `0x1800088a1`
- name: `?PcaUtilityFindFileNameInCommandLine@@YAKPEAGPEBG1@Z`
- size: `317`
- prototype: `unsigned int __fastcall(wchar_t *Destination, wchar_t *Source, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002210`

## callees

- `0x180007ee8`
- `0x180008764`
- `0x18000c030`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800087ee`
- `msvcrt!_wcsnicmp` at `0x1800087ee`
- `msvcrt!wcscpy_s` at `0x1800087a0`
- `msvcrt!wcscpy_s` at `0x180008869`
- `msvcrt!wcscpy_s` at `0x1800087a0`
- `msvcrt!wcscpy_s` at `0x180008869`
- `msvcrt!wcsrchr` at `0x180008821`
- `msvcrt!wcsrchr` at `0x180008837`
- `msvcrt!wcsrchr` at `0x180008821`
- `msvcrt!wcsrchr` at `0x180008837`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180008853`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180008853`

## pseudocode

```c
__int64 __fastcall PcaUtilityFindFileNameInCommandLine(
        wchar_t *Destination,
        wchar_t *Source,
        const unsigned __int16 *a3)
{
  unsigned int v4; // esi
  unsigned __int64 v5; // rcx
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // rbx
  wchar_t *v9; // rbx
  wchar_t *v10; // rbx
  wchar_t Destinationa[264]; // [rsp+20h] [rbp-238h] BYREF

  v4 = 87;
  wcscpy_s(Destinationa, 0x104u, Source);
  v5 = -1;
  do
    ++v5;
  while ( Destinationa[v5] );
  *Destination = 0;
  if ( v5 > 4 )
  {
    v6 = 0;
    v7 = v5 - 4;
    while ( v6 <= v7 )
    {
      if ( !_wcsnicmp(&Destinationa[v6], L".cpl", 4u) )
      {
        v8 = 2 * v6 + 8;
        if ( v8 >= 0x208 )
          _report_rangecheckfailure();
        *(wchar_t *)((char *)Destinationa + v8) = 0;
        v9 = wcsrchr(Destinationa, 0x22u);
        if ( v9 || (v9 = wcsrchr(Destinationa, 0x20u)) != 0 )
          v10 = v9 + 1;
        else
          v10 = Destinationa;
        if ( GetFileAttributesW(v10) != -1 )
        {
          wcscpy_s(Destination, 0x104u, v10);
          return 0;
        }
        return v4;
      }
      ++v6;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180008764  mov     [rsp+arg_10], rbx
0x180008769  mov     [rsp+arg_18], rbp
0x18000876e  push    rsi
0x18000876f  push    rdi
0x180008770  push    r14
0x180008772  sub     rsp, 240h
0x180008779  mov     rax, cs:__security_cookie
0x180008780  xor     rax, rsp
0x180008783  mov     [rsp+258h+var_28], rax
0x18000878b  mov     r14, rcx
0x18000878e  mov     r8, rdx; Source
0x180008791  mov     edx, 104h; SizeInWords
0x180008796  lea     rcx, [rsp+258h+Destination]; Destination
0x18000879b  mov     esi, 57h ; 'W'
0x1800087a0  call    cs:__imp_wcscpy_s
0x1800087a6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800087aa  lea     rax, [rsp+258h+Destination]
0x1800087af  xor     ebp, ebp
0x1800087b1  inc     rcx
0x1800087b4  cmp     [rax+rcx*2], bp
0x1800087b8  jnz     short loc_1800087B1
0x1800087ba  mov     [r14], bp
0x1800087be  cmp     rcx, 4
0x1800087c2  jbe     loc_180008871
0x1800087c8  mov     rbx, rbp
0x1800087cb  lea     rdi, [rcx-4]
0x1800087cf  cmp     rbx, rdi
0x1800087d2  ja      loc_180008871
0x1800087d8  lea     rcx, [rsp+258h+Destination]
0x1800087dd  mov     r8d, 4; MaxCount
0x1800087e3  lea     rcx, [rcx+rbx*2]; String1
0x1800087e7  lea     rdx, aCpl; ".cpl"
0x1800087ee  call    cs:__imp__wcsnicmp
0x1800087f4  test    eax, eax
0x1800087f6  jz      short loc_1800087FD
0x1800087f8  inc     rbx
0x1800087fb  jmp     short loc_1800087CF
0x1800087fd  lea     rbx, ds:8[rbx*2]
0x180008805  cmp     rbx, 208h
0x18000880c  jnb     loc_18000889B
0x180008812  mov     edx, 22h ; '"'; Ch
0x180008817  mov     [rsp+rbx+258h+Destination], bp
0x18000881c  lea     rcx, [rsp+258h+Destination]; Str
0x180008821  call    cs:__imp_wcsrchr
0x180008827  mov     rbx, rax
0x18000882a  test    rax, rax
0x18000882d  jnz     short loc_18000884C
0x18000882f  lea     edx, [rax+20h]; Ch
0x180008832  lea     rcx, [rsp+258h+Destination]; Str
0x180008837  call    cs:__imp_wcsrchr
0x18000883d  mov     rbx, rax
0x180008840  test    rax, rax
0x180008843  jnz     short loc_18000884C
0x180008845  lea     rbx, [rsp+258h+Destination]
0x18000884a  jmp     short loc_180008850
0x18000884c  add     rbx, 2
0x180008850  mov     rcx, rbx; lpFileName
0x180008853  call    cs:__imp_GetFileAttributesW
0x180008859  cmp     eax, 0FFFFFFFFh
0x18000885c  jz      short loc_180008871
0x18000885e  mov     r8, rbx; Source
0x180008861  mov     edx, 104h; SizeInWords
0x180008866  mov     rcx, r14; Destination
0x180008869  call    cs:__imp_wcscpy_s
0x18000886f  mov     esi, ebp
0x180008871  mov     eax, esi
0x180008873  mov     rcx, [rsp+258h+var_28]
0x18000887b  xor     rcx, rsp; StackCookie
0x18000887e  call    __security_check_cookie
0x180008883  lea     r11, [rsp+258h+var_18]
0x18000888b  mov     rbx, [r11+30h]
0x18000888f  mov     rbp, [r11+38h]
0x180008893  mov     rsp, r11
0x180008896  pop     r14
0x180008898  pop     rdi
0x180008899  pop     rsi
0x18000889a  retn
0x18000889b  call    __report_rangecheckfailure
```
