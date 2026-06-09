# CNDFAPI::IsDiagnosableResult(long,ushort const *)

- ea: `0x180013ee0`
- end: `0x180013f71`
- name: `?IsDiagnosableResult@CNDFAPI@@UEAAJJPEBG@Z`
- size: `145`
- prototype: `__int64 __fastcall(CNDFAPI *this, int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180013ee0`

## import_xrefs

- `SHLWAPI!PathIsNetworkPathW` at `0x180013f3c`
- `SHLWAPI!PathIsNetworkPathW` at `0x180013f3c`

## pseudocode

```c
__int64 __fastcall CNDFAPI::IsDiagnosableResult(CNDFAPI *this, int a2, const unsigned __int16 *a3)
{
  unsigned int v4; // edi

  switch ( a2 )
  {
    case -2147024843:
      return 0;
    case -2147024829:
      return 0;
    case -2147023693:
      return 0;
    case -2147023665:
      return 0;
    case -2147023624:
      return 0;
  }
  if ( (unsigned int)(a2 + 1067646973) <= 1 )
    return 0;
  if ( a2 == -2147022959 )
    return 0;
  if ( a2 == -1067646966 )
    return 0;
  v4 = -2147467259;
  if ( a3 )
  {
    if ( PathIsNetworkPathW(a3) && (a2 == -2147024894 || a2 == -2147024891 || a2 == -2147467259 || a2 == -2147024775) )
      return 0;
  }
  return v4;
}

```

## disassembly

```asm
0x180013ee0  mov     [rsp+arg_0], rbx
0x180013ee5  push    rdi
0x180013ee6  sub     rsp, 20h
0x180013eea  mov     ebx, edx
0x180013eec  cmp     edx, 80070035h
0x180013ef2  jz      short loc_180013F62
0x180013ef4  cmp     edx, 80070043h
0x180013efa  jz      short loc_180013F62
0x180013efc  cmp     edx, 800704B3h
0x180013f02  jz      short loc_180013F62
0x180013f04  cmp     edx, 800704CFh
0x180013f0a  jz      short loc_180013F62
0x180013f0c  cmp     edx, 800704F8h
0x180013f12  jz      short loc_180013F62
0x180013f14  lea     eax, [rdx+3FA2FFFDh]
0x180013f1a  cmp     eax, 1
0x180013f1d  jbe     short loc_180013F62
0x180013f1f  cmp     edx, 80070791h
0x180013f25  jz      short loc_180013F62
0x180013f27  cmp     edx, 0C05D000Ah
0x180013f2d  jz      short loc_180013F62
0x180013f2f  mov     edi, 80004005h
0x180013f34  test    r8, r8
0x180013f37  jz      short loc_180013F64
0x180013f39  mov     rcx, r8; pszPath
0x180013f3c  call    cs:__imp_PathIsNetworkPathW
0x180013f42  test    eax, eax
0x180013f44  jz      short loc_180013F64
0x180013f46  cmp     ebx, 80070002h
0x180013f4c  jz      short loc_180013F62
0x180013f4e  cmp     ebx, 80070005h
0x180013f54  jz      short loc_180013F62
0x180013f56  cmp     ebx, edi
0x180013f58  jz      short loc_180013F62
0x180013f5a  cmp     ebx, 80070079h
0x180013f60  jnz     short loc_180013F64
0x180013f62  xor     edi, edi
0x180013f64  mov     rbx, [rsp+28h+arg_0]
0x180013f69  mov     eax, edi
0x180013f6b  add     rsp, 20h
0x180013f6f  pop     rdi
0x180013f70  retn
```
