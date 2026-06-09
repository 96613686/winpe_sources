# NgcGetNCryptBinaryBlob

- ea: `0x180010c10`
- end: `0x180010d67`
- name: `NgcGetNCryptBinaryBlob`
- size: `343`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a5b4`
- `0x180010c10`
- `0x180013cbc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010d00`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010d36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010d00`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010d36`

## string_xrefs

- `0x180010c37`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180010c61`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180010c8b`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180010d12`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`

## pseudocode

```c
__int64 __fastcall NgcGetNCryptBinaryBlob(NCRYPT_HANDLE a1, const WCHAR *a2, HLOCAL *a3, _DWORD *a4)
{
  int NCryptBinaryBlob; // ebx
  HLOCAL v8; // rcx
  HLOCAL v9; // rcx
  HLOCAL hMem; // [rsp+20h] [rbp-28h] BYREF
  HLOCAL *p_hMem; // [rsp+28h] [rbp-20h]
  unsigned __int16 v12[4]; // [rsp+30h] [rbp-18h] BYREF
  char v13; // [rsp+38h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned __int8 *v15; // [rsp+58h] [rbp+10h] BYREF

  if ( a2 )
  {
    if ( a3 )
    {
      if ( a4 )
      {
        *a3 = 0;
        LODWORD(v15) = 0;
        p_hMem = &hMem;
        *(_QWORD *)v12 = 0;
        v13 = 1;
        NCryptBinaryBlob = NgcUtils::GetNCryptBinaryBlob(a1, a2, v12, &v15, 0);
        if ( v13 )
        {
          v8 = *p_hMem;
          *p_hMem = *(HLOCAL *)v12;
          if ( v8 )
            LocalFree(v8);
        }
        if ( NCryptBinaryBlob >= 0 )
        {
          *a3 = hMem;
          *a4 = (_DWORD)v15;
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xAF,
            (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
            (const char *)(unsigned int)NCryptBinaryBlob,
            (int)hMem);
          v9 = hMem;
          hMem = 0;
          if ( v9 )
            LocalFree(v9);
          return (unsigned int)NCryptBinaryBlob;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAA,
          (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
          (const char *)0x80004003LL,
          (int)hMem);
        return 2147500035LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA9,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
        (const char *)0x80004003LL,
        (int)hMem);
      return 2147500035LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA8,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
      (const char *)0x80004003LL,
      (int)hMem);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180010c10  mov     [rsp+arg_0], rbx
0x180010c15  mov     [rsp+arg_10], rsi
0x180010c1a  push    rdi
0x180010c1b  sub     rsp, 40h
0x180010c1f  mov     rsi, r9
0x180010c22  mov     rdi, r8
0x180010c25  test    rdx, rdx
0x180010c28  jnz     short loc_180010C4F
0x180010c2a  mov     rcx, [rsp+48h]; this
0x180010c2f  mov     ebx, 80004003h
0x180010c34  mov     r9d, ebx; char *
0x180010c37  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180010c3e  mov     edx, 0A8h; void *
0x180010c43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010c48  mov     eax, ebx
0x180010c4a  jmp     loc_180010D56
0x180010c4f  test    rdi, rdi
0x180010c52  jnz     short loc_180010C79
0x180010c54  mov     rcx, [rsp+48h]; this
0x180010c59  mov     ebx, 80004003h
0x180010c5e  mov     r9d, ebx; char *
0x180010c61  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180010c68  mov     edx, 0A9h; void *
0x180010c6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010c72  mov     eax, ebx
0x180010c74  jmp     loc_180010D56
0x180010c79  test    rsi, rsi
0x180010c7c  jnz     short loc_180010CA3
0x180010c7e  mov     rcx, [rsp+48h]; this
0x180010c83  mov     ebx, 80004003h
0x180010c88  mov     r9d, ebx; char *
0x180010c8b  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180010c92  mov     edx, 0AAh; void *
0x180010c97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010c9c  mov     eax, ebx
0x180010c9e  jmp     loc_180010D56
0x180010ca3  mov     qword ptr [r8], 0
0x180010caa  mov     [rsp+48h+hMem], 0; int
0x180010cb3  mov     dword ptr [rsp+48h+arg_8], 0
0x180010cbb  lea     rax, [rsp+48h+hMem]
0x180010cc0  mov     [rsp+48h+var_20], rax
0x180010cc5  mov     qword ptr [rsp+48h+var_18], 0
0x180010cce  mov     [rsp+48h+var_10], 1
0x180010cd3  lea     r9, [rsp+48h+arg_8]; unsigned __int8 **
0x180010cd8  lea     r8, [rsp+48h+var_18]; unsigned __int16 *
0x180010cdd  call    ?GetNCryptBinaryBlob@NgcUtils@@YAJ_KPEBGPEAPEAEPEAK@Z; NgcUtils::GetNCryptBinaryBlob(unsigned __int64,ushort const *,uchar * *,ulong *)
0x180010ce2  mov     ebx, eax
0x180010ce4  cmp     [rsp+48h+var_10], 0
0x180010ce9  jz      short loc_180010D06
0x180010ceb  mov     r8, [rsp+48h+var_20]
0x180010cf0  mov     rcx, [r8]; hMem
0x180010cf3  mov     rdx, qword ptr [rsp+48h+var_18]
0x180010cf8  mov     [r8], rdx
0x180010cfb  test    rcx, rcx
0x180010cfe  jz      short loc_180010D06
0x180010d00  call    cs:__imp_LocalFree
0x180010d06  test    ebx, ebx
0x180010d08  jns     short loc_180010D40
0x180010d0a  mov     rcx, [rsp+48h]; this
0x180010d0f  mov     r9d, ebx; char *
0x180010d12  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180010d19  mov     edx, 0AFh; void *
0x180010d1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010d23  mov     rcx, [rsp+48h+hMem]; hMem
0x180010d28  mov     [rsp+48h+hMem], 0
0x180010d31  test    rcx, rcx
0x180010d34  jz      short loc_180010D3C
0x180010d36  call    cs:__imp_LocalFree
0x180010d3c  mov     eax, ebx
0x180010d3e  jmp     short loc_180010D56
0x180010d40  mov     rax, [rsp+48h+hMem]
0x180010d45  mov     [rdi], rax
0x180010d48  mov     eax, dword ptr [rsp+48h+arg_8]
0x180010d4c  mov     [rsi], eax
0x180010d4e  xor     eax, eax
0x180010d50  jmp     short loc_180010D56
0x180010d52  mov     eax, dword ptr [rsp+48h+arg_8]
0x180010d56  mov     rbx, [rsp+48h+arg_0]
0x180010d5b  mov     rsi, [rsp+48h+arg_10]
0x180010d60  add     rsp, 40h
0x180010d64  pop     rdi
0x180010d65  retn
```
