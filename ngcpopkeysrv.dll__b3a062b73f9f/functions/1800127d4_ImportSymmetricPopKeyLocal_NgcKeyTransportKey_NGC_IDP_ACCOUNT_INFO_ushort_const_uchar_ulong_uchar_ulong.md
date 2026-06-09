# ImportSymmetricPopKeyLocal(NgcKeyTransportKey *,_NGC_IDP_ACCOUNT_INFO *,ushort const *,uchar *,ulong,uchar * *,ulong *)

- ea: `0x1800127d4`
- end: `0x18001284f`
- name: `?ImportSymmetricPopKeyLocal@@YAJPEAVNgcKeyTransportKey@@PEAU_NGC_IDP_ACCOUNT_INFO@@PEBGPEAEKPEAPEAEPEAK@Z`
- size: `123`
- prototype: `__int64 __fastcall(struct NgcKeyTransportKey *, struct _NGC_IDP_ACCOUNT_INFO *, const unsigned __int16 *, unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000e2b4`

## callees

- `0x18000b0fc`
- `0x1800127d4`
- `0x1800190c8`
- `0x1800193d4`

## string_xrefs

- `0x1800127fe`: `onecore\ds\security\ngc\ngcpopkey\lib\keytransportkey.cpp`

## pseudocode

```c
__int64 __fastcall ImportSymmetricPopKeyLocal(
        struct NgcKeyTransportKey *a1,
        struct _NGC_IDP_ACCOUNT_INFO *a2,
        const unsigned __int16 *a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int8 **a6,
        unsigned int *a7)
{
  int v9; // ebx
  __int64 v10; // rdx
  int v12; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v9 = NgcKeyTransportKey::OpenKey(a1, a2, a3);
  if ( v9 < 0 )
  {
    v10 = 89;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\keytransportkey.cpp",
      (const char *)(unsigned int)v9,
      v12);
    return (unsigned int)v9;
  }
  v9 = NgcKeyTransportKey::DecryptKeyBlobAndExportDpapiProtectedBlob(a1, a4, a5, a6, a7);
  if ( v9 < 0 )
  {
    v10 = 95;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x1800127d4  mov     [rsp+arg_0], rbx
0x1800127d9  mov     [rsp+arg_8], rsi
0x1800127de  push    rdi
0x1800127df  sub     rsp, 30h
0x1800127e3  mov     rsi, r9
0x1800127e6  mov     rdi, rcx
0x1800127e9  call    ?OpenKey@NgcKeyTransportKey@@QEAAJPEAU_NGC_IDP_ACCOUNT_INFO@@PEBG@Z; NgcKeyTransportKey::OpenKey(_NGC_IDP_ACCOUNT_INFO *,ushort const *)
0x1800127ee  mov     ebx, eax
0x1800127f0  test    eax, eax
0x1800127f2  jns     short loc_180012811
0x1800127f4  mov     edx, 59h ; 'Y'; void *
0x1800127f9  mov     rcx, [rsp+38h]; this
0x1800127fe  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180012805  mov     r9d, ebx; char *
0x180012808  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001280d  mov     eax, ebx
0x18001280f  jmp     short loc_18001283F
0x180012811  mov     rax, [rsp+38h+arg_30]
0x180012816  mov     rdx, rsi; unsigned __int8 *
0x180012819  mov     r9, [rsp+38h+arg_28]; unsigned __int8 **
0x18001281e  mov     rcx, rdi; this
0x180012821  mov     r8d, [rsp+38h+arg_20]; unsigned int
0x180012826  mov     qword ptr [rsp+38h+var_18], rax; unsigned int *
0x18001282b  call    ?DecryptKeyBlobAndExportDpapiProtectedBlob@NgcKeyTransportKey@@QEAAJPEAEKPEAPEAEPEAK@Z; NgcKeyTransportKey::DecryptKeyBlobAndExportDpapiProtectedBlob(uchar *,ulong,uchar * *,ulong *)
0x180012830  mov     ebx, eax
0x180012832  test    eax, eax
0x180012834  jns     short loc_18001283D
0x180012836  mov     edx, 5Fh ; '_'
0x18001283b  jmp     short loc_1800127F9
0x18001283d  xor     eax, eax
0x18001283f  mov     rbx, [rsp+38h+arg_0]
0x180012844  mov     rsi, [rsp+38h+arg_8]
0x180012849  add     rsp, 30h
0x18001284d  pop     rdi
0x18001284e  retn
```
