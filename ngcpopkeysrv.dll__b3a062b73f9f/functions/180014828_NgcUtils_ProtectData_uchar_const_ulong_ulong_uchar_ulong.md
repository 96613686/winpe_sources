# NgcUtils::ProtectData(uchar const *,ulong,ulong,uchar * *,ulong *)

- ea: `0x180014828`
- end: `0x1800148ad`
- name: `?ProtectData@NgcUtils@@YAJPEBEKKPEAPEAEPEAK@Z`
- size: `133`
- prototype: `__int64 __fastcall(BYTE *this, const unsigned __int8 *, __int64, BYTE **, unsigned __int8 **)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800190c8`
- `0x18001ba2c`

## callees

- `0x18000b0dc`
- `0x180014828`

## import_xrefs

- `CRYPT32!CryptProtectData` at `0x18001486d`
- `CRYPT32!CryptProtectData` at `0x18001486d`

## string_xrefs

- `0x18001487c`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::ProtectData(
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
  if ( !CryptProtectData(&v8, 0, 0, 0, 0, 0, &v9) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x33A,
             (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
             v6);
  *a4 = v9.pbData;
  *(_DWORD *)a5 = v9.cbData;
  return 0;
}

```

## disassembly

```asm
0x180014828  mov     r11, rsp
0x18001482b  push    rbx
0x18001482c  sub     rsp, 60h
0x180014830  xor     eax, eax
0x180014832  mov     [rsp+68h+var_28], edx
0x180014836  mov     [rsp+68h+var_24], eax
0x18001483a  mov     rbx, r9
0x18001483d  lea     rax, [r11-18h]
0x180014841  mov     [r11-20h], rcx
0x180014845  mov     [r11-38h], rax
0x180014849  lea     rcx, [r11-28h]; pDataIn
0x18001484d  xorps   xmm0, xmm0
0x180014850  mov     [rsp+68h+dwFlags], 0; dwFlags
0x180014858  xor     r9d, r9d; pvReserved
0x18001485b  mov     qword ptr [r11-48h], 0
0x180014863  xor     r8d, r8d; pOptionalEntropy
0x180014866  xor     edx, edx; szDataDescr
0x180014868  movups  xmmword ptr [rsp+68h+var_18.cbData], xmm0
0x18001486d  call    cs:__imp_CryptProtectData
0x180014873  test    eax, eax
0x180014875  jnz     short loc_18001488F
0x180014877  mov     rcx, [rsp+68h]; this
0x18001487c  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180014883  mov     edx, 33Ah; void *
0x180014888  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001488d  jmp     short loc_1800148A7
0x18001488f  mov     rax, [rsp+68h+var_18.pbData]
0x180014894  mov     rcx, [rsp+68h+arg_20]
0x18001489c  mov     [rbx], rax
0x18001489f  mov     eax, [rsp+68h+var_18.cbData]
0x1800148a3  mov     [rcx], eax
0x1800148a5  xor     eax, eax
0x1800148a7  add     rsp, 60h
0x1800148ab  pop     rbx
0x1800148ac  retn
```
