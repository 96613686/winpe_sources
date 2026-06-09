# IsSamePath

- ea: `0x1800069d8`
- end: `0x180006af6`
- name: `IsSamePath`
- size: `286`
- prototype: `_BOOL8 __fastcall(wchar_t *Path, wchar_t *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180006184`
- `0x180007628`

## callees

- `0x180002368`
- `0x1800069d8`
- `0x180014ae0`

## import_xrefs

- `msvcrt!_wfullpath` at `0x180006a0b`
- `msvcrt!_wfullpath` at `0x180006a2a`
- `msvcrt!_wfullpath` at `0x180006a0b`
- `msvcrt!_wfullpath` at `0x180006a2a`
- `msvcrt!_wcsicmp` at `0x180006abc`
- `msvcrt!_wcsicmp` at `0x180006abc`

## pseudocode

```c
_BOOL8 __fastcall IsSamePath(wchar_t *Path, wchar_t *a2)
{
  __int64 v3; // rcx
  __int64 v4; // rax
  unsigned __int64 v5; // rdx
  unsigned __int64 v6; // rcx
  wchar_t String2[264]; // [rsp+20h] [rbp-438h] BYREF
  wchar_t Buffer[264]; // [rsp+230h] [rbp-228h] BYREF

  if ( _wfullpath(Buffer, Path, 0x104u) && _wfullpath(String2, a2, 0x104u) )
  {
    v3 = -1;
    v4 = -1;
    do
      ++v4;
    while ( Buffer[v4] );
    if ( (_WORD)v4 && String2[(unsigned __int16)v4 + 263] == 92 )
    {
      v5 = 2LL * (unsigned __int16)v4 - 2;
      if ( v5 >= 0x208 )
        goto LABEL_15;
      *(wchar_t *)((char *)Buffer + v5) = 0;
    }
    do
      ++v3;
    while ( String2[v3] );
    if ( !(_WORD)v3 || String2[(unsigned __int16)v3 - 1] != 92 )
      return _wcsicmp(Buffer, String2) == 0;
    v6 = 2LL * (unsigned __int16)v3 - 2;
    if ( v6 < 0x208 )
    {
      *(wchar_t *)((char *)String2 + v6) = 0;
      return _wcsicmp(Buffer, String2) == 0;
    }
LABEL_15:
    _report_rangecheckfailure();
  }
  return 0;
}

```

## disassembly

```asm
0x1800069d8  mov     [rsp+arg_10], rbx
0x1800069dd  push    rdi
0x1800069de  sub     rsp, 450h
0x1800069e5  mov     rax, cs:__security_cookie
0x1800069ec  xor     rax, rsp
0x1800069ef  mov     [rsp+458h+var_18], rax
0x1800069f7  mov     rbx, rdx
0x1800069fa  mov     r8d, 104h; BufferCount
0x180006a00  mov     rdx, rcx; Path
0x180006a03  lea     rcx, [rsp+458h+Buffer]; Buffer
0x180006a0b  call    cs:__imp__wfullpath
0x180006a11  xor     edi, edi
0x180006a13  test    rax, rax
0x180006a16  jz      loc_180006AD3
0x180006a1c  mov     r8d, 104h; BufferCount
0x180006a22  lea     rcx, [rsp+458h+String2]; Buffer
0x180006a27  mov     rdx, rbx; Path
0x180006a2a  call    cs:__imp__wfullpath
0x180006a30  test    rax, rax
0x180006a33  jz      loc_180006AD3
0x180006a39  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180006a3d  lea     rdx, [rsp+458h+Buffer]
0x180006a45  mov     rax, rcx
0x180006a48  inc     rax
0x180006a4b  cmp     [rdx+rax*2], di
0x180006a4f  jnz     short loc_180006A48
0x180006a51  mov     r8d, 208h
0x180006a57  test    ax, ax
0x180006a5a  jz      short loc_180006A7F
0x180006a5c  movzx   edx, ax
0x180006a5f  cmp     [rsp+rdx*2+458h+var_22A], 5Ch ; '\'
0x180006a68  jnz     short loc_180006A7F
0x180006a6a  lea     rdx, ds:0FFFFFFFFFFFFFFFEh[rdx*2]
0x180006a72  cmp     rdx, r8
0x180006a75  jnb     short loc_180006ACD
0x180006a77  mov     [rsp+rdx+458h+Buffer], di
0x180006a7f  lea     rax, [rsp+458h+String2]
0x180006a84  inc     rcx
0x180006a87  cmp     [rax+rcx*2], di
0x180006a8b  jnz     short loc_180006A84
0x180006a8d  test    cx, cx
0x180006a90  jz      short loc_180006AAF
0x180006a92  movzx   ecx, cx
0x180006a95  cmp     [rsp+rcx*2+458h+var_43A], 5Ch ; '\'
0x180006a9b  jnz     short loc_180006AAF
0x180006a9d  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rcx*2]
0x180006aa5  cmp     rcx, r8
0x180006aa8  jnb     short loc_180006ACD
0x180006aaa  mov     [rsp+rcx+458h+String2], di
0x180006aaf  lea     rdx, [rsp+458h+String2]; String2
0x180006ab4  lea     rcx, [rsp+458h+Buffer]; String1
0x180006abc  call    cs:__imp__wcsicmp
0x180006ac2  test    eax, eax
0x180006ac4  mov     ecx, edi
0x180006ac6  setz    cl
0x180006ac9  mov     eax, ecx
0x180006acb  jmp     short loc_180006AD5
0x180006acd  call    __report_rangecheckfailure
0x180006ad3  xor     eax, eax
0x180006ad5  mov     rcx, [rsp+458h+var_18]
0x180006add  xor     rcx, rsp; StackCookie
0x180006ae0  call    __security_check_cookie
0x180006ae5  mov     rbx, [rsp+458h+arg_10]
0x180006aed  add     rsp, 450h
0x180006af4  pop     rdi
0x180006af5  retn
```
