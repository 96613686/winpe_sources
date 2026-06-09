# NgcUtils::UnprotectData(uchar const *,ulong,ulong,uchar * *,ulong *)

- ea: `0x180014b18`
- end: `0x180014b9d`
- name: `?UnprotectData@NgcUtils@@YAJPEBEKKPEAPEAEPEAK@Z`
- size: `133`
- prototype: `__int64 __fastcall(BYTE *this, const unsigned __int8 *, __int64, BYTE **, unsigned __int8 **)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001e330`
- `0x18001f3a0`

## callees

- `0x18000b0dc`
- `0x180014b18`

## import_xrefs

- `CRYPT32!CryptUnprotectData` at `0x180014b5d`
- `CRYPT32!CryptUnprotectData` at `0x180014b5d`

## string_xrefs

- `0x180014b6c`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::UnprotectData(
        BYTE *this,
        const unsigned __int8 *a2,
        __int64 a3,
        BYTE **a4,
        unsigned __int8 **a5)
{
  const char *v6; // r9
  DATA_BLOB v8; // [rsp+40h] [rbp-28h] BYREF
  DATA_BLOB v9; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v8.cbData = (unsigned int)a2;
  *(&v8.cbData + 1) = 0;
  v8.pbData = this;
  v9 = 0;
  if ( !CryptUnprotectData(&v8, 0, 0, 0, 0, 0, &v9) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x359,
             (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
             v6);
  *a4 = v9.pbData;
  *(_DWORD *)a5 = v9.cbData;
  return 0;
}

```

## disassembly

```asm
0x180014b18  mov     r11, rsp
0x180014b1b  push    rbx
0x180014b1c  sub     rsp, 60h
0x180014b20  xor     eax, eax
0x180014b22  mov     [rsp+68h+var_28], edx
0x180014b26  mov     [rsp+68h+var_24], eax
0x180014b2a  mov     rbx, r9
0x180014b2d  lea     rax, [r11-18h]
0x180014b31  mov     [r11-20h], rcx
0x180014b35  mov     [r11-38h], rax
0x180014b39  lea     rcx, [r11-28h]; pDataIn
0x180014b3d  xorps   xmm0, xmm0
0x180014b40  mov     [rsp+68h+dwFlags], 0; dwFlags
0x180014b48  xor     r9d, r9d; pvReserved
0x180014b4b  mov     qword ptr [r11-48h], 0
0x180014b53  xor     r8d, r8d; pOptionalEntropy
0x180014b56  xor     edx, edx; ppszDataDescr
0x180014b58  movups  xmmword ptr [rsp+68h+var_18.cbData], xmm0
0x180014b5d  call    cs:__imp_CryptUnprotectData
0x180014b63  test    eax, eax
0x180014b65  jnz     short loc_180014B7F
0x180014b67  mov     rcx, [rsp+68h]; this
0x180014b6c  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180014b73  mov     edx, 359h; void *
0x180014b78  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180014b7d  jmp     short loc_180014B97
0x180014b7f  mov     rax, [rsp+68h+var_18.pbData]
0x180014b84  mov     rcx, [rsp+68h+arg_20]
0x180014b8c  mov     [rbx], rax
0x180014b8f  mov     eax, [rsp+68h+var_18.cbData]
0x180014b93  mov     [rcx], eax
0x180014b95  xor     eax, eax
0x180014b97  add     rsp, 60h
0x180014b9b  pop     rbx
0x180014b9c  retn
```
