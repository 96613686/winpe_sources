# PathConvertToUNC(ushort const *,ushort * *)

- ea: `0x180006c94`
- end: `0x180006dd8`
- name: `?PathConvertToUNC@@YAJPEBGPEAPEAG@Z`
- size: `324`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180032064`
- `0x180043d8c`

## callees

- `0x180006020`
- `0x180006c94`
- `0x1800081f8`
- `0x1800270c0`
- `0x18002aab4`
- `0x18003235c`
- `0x18004c636`
- `0x18004c670`

## import_xrefs

- `SHLWAPI!PathIsUNCW` at `0x180006cc5`
- `SHLWAPI!PathIsUNCW` at `0x180006cc5`
- `MPR!WNetGetUniversalNameW` at `0x180006d6d`
- `MPR!WNetGetUniversalNameW` at `0x180006d6d`

## pseudocode

```c
__int64 __fastcall PathConvertToUNC(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  unsigned __int64 v4; // rdi
  unsigned int v5; // edx
  void *v6; // rcx
  signed int v7; // ebx
  signed int UniversalNameW; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rdi
  unsigned __int16 **v13; // [rsp+20h] [rbp-278h]
  unsigned __int64 *v14; // [rsp+28h] [rbp-270h]
  unsigned int v15; // [rsp+30h] [rbp-268h]
  DWORD BufferSize[2]; // [rsp+40h] [rbp-258h] BYREF
  _QWORD Buffer[66]; // [rsp+50h] [rbp-248h] BYREF

  *a2 = 0;
  if ( PathIsUNCW(a1) )
  {
    v4 = -1;
    do
      ++v4;
    while ( a1[v4] );
    *a2 = 0;
    if ( v4 + 1 < v4 )
    {
      return (unsigned int)-2147024362;
    }
    else
    {
      *(_QWORD *)BufferSize = 0;
      v7 = ULongLongMult(v4 + 1, 2u, (unsigned __int64 *)BufferSize);
      if ( v7 >= 0 )
        v7 = CTCoAllocPolicy::Alloc(v6, v5, *(unsigned __int64 *)BufferSize, (void **)a2);
      if ( v7 >= 0 )
        StringCchCopyNExW(*a2, v4 + 1, a1, v4, v13, v14, v15);
    }
  }
  else if ( (unsigned int)IsFixedDrive(a1) )
  {
    return (unsigned int)-2147022646;
  }
  else
  {
    memset_0(Buffer, 0, sizeof(Buffer));
    BufferSize[0] = 528;
    UniversalNameW = WNetGetUniversalNameW(a1, 1u, Buffer, BufferSize);
    v7 = UniversalNameW;
    if ( UniversalNameW > 0 )
      v7 = (unsigned __int16)UniversalNameW | 0x80070000;
    if ( v7 >= 0 )
    {
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)(Buffer[0] + 2 * v11) );
      return (unsigned int)_AllocStringWorker<CTCoAllocPolicy>(v10, v9, Buffer[0], v11);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180006c94  mov     [rsp+arg_10], rbx
0x180006c99  push    rbp
0x180006c9a  push    rsi
0x180006c9b  push    rdi
0x180006c9c  push    r14
0x180006c9e  push    r15
0x180006ca0  sub     rsp, 270h
0x180006ca7  mov     rax, cs:__security_cookie
0x180006cae  xor     rax, rsp
0x180006cb1  mov     [rsp+298h+var_38], rax
0x180006cb9  xor     r15d, r15d
0x180006cbc  mov     r14, rdx
0x180006cbf  mov     [rdx], r15
0x180006cc2  mov     rsi, rcx
0x180006cc5  call    cs:__imp_PathIsUNCW
0x180006ccb  test    eax, eax
0x180006ccd  jz      short loc_180006D37
0x180006ccf  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180006cd3  inc     rdi
0x180006cd6  cmp     [rsi+rdi*2], r15w
0x180006cdb  jnz     short loc_180006CD3
0x180006cdd  lea     rbp, [rdi+1]
0x180006ce1  mov     [r14], r15
0x180006ce4  cmp     rbp, rdi
0x180006ce7  jb      short loc_180006D30
0x180006ce9  lea     r8, [rsp+298h+BufferSize]; unsigned __int64 *
0x180006cee  mov     qword ptr [rsp+298h+BufferSize], r15
0x180006cf3  mov     edx, 2; unsigned __int64
0x180006cf8  mov     rcx, rbp; unsigned __int64
0x180006cfb  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180006d00  mov     ebx, eax
0x180006d02  test    eax, eax
0x180006d04  js      short loc_180006D15
0x180006d06  mov     r8, qword ptr [rsp+298h+BufferSize]; unsigned __int64
0x180006d0b  mov     r9, r14; void **
0x180006d0e  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180006d13  mov     ebx, eax
0x180006d15  test    ebx, ebx
0x180006d17  js      loc_180006DAF
0x180006d1d  mov     rcx, [r14]; unsigned __int16 *
0x180006d20  mov     r9, rdi; unsigned __int64
0x180006d23  mov     r8, rsi; unsigned __int16 *
0x180006d26  mov     rdx, rbp; unsigned __int64
0x180006d29  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180006d2e  jmp     short loc_180006DAF
0x180006d30  mov     ebx, 80070216h
0x180006d35  jmp     short loc_180006DAF
0x180006d37  mov     rcx, rsi
0x180006d3a  call    IsFixedDrive
0x180006d3f  test    eax, eax
0x180006d41  jnz     short loc_180006DAA
0x180006d43  mov     ebx, 210h
0x180006d48  lea     rcx, [rsp+298h+Buffer]; void *
0x180006d4d  mov     r8d, ebx; Size
0x180006d50  xor     edx, edx; Val
0x180006d52  call    memset_0
0x180006d57  lea     r9, [rsp+298h+BufferSize]; lpBufferSize
0x180006d5c  mov     [rsp+298h+BufferSize], ebx
0x180006d60  lea     r8, [rsp+298h+Buffer]; lpBuffer
0x180006d65  mov     edx, 1; dwInfoLevel
0x180006d6a  mov     rcx, rsi; lpLocalPath
0x180006d6d  call    cs:__imp_WNetGetUniversalNameW
0x180006d73  mov     ebx, eax
0x180006d75  test    eax, eax
0x180006d77  jle     short loc_180006D82
0x180006d79  movzx   ebx, ax
0x180006d7c  or      ebx, 80070000h
0x180006d82  test    ebx, ebx
0x180006d84  js      short loc_180006DAF
0x180006d86  mov     r8, [rsp+298h+Buffer]
0x180006d8b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180006d8f  inc     rdi
0x180006d92  cmp     [r8+rdi*2], r15w
0x180006d97  jnz     short loc_180006D8F
0x180006d99  mov     r9, rdi
0x180006d9c  mov     [rsp+298h+var_270], r14
0x180006da1  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180006da6  mov     ebx, eax
0x180006da8  jmp     short loc_180006DAF
0x180006daa  mov     ebx, 800708CAh
0x180006daf  mov     eax, ebx
0x180006db1  mov     rcx, [rsp+298h+var_38]
0x180006db9  xor     rcx, rsp; StackCookie
0x180006dbc  call    __security_check_cookie
0x180006dc1  mov     rbx, [rsp+298h+arg_10]
0x180006dc9  add     rsp, 270h
0x180006dd0  pop     r15
0x180006dd2  pop     r14
0x180006dd4  pop     rdi
0x180006dd5  pop     rsi
0x180006dd6  pop     rbp
0x180006dd7  retn
```
