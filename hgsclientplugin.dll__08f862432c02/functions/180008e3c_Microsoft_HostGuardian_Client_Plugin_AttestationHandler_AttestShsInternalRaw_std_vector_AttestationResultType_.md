# Microsoft::HostGuardian::Client::Plugin::AttestationHandler::AttestShsInternalRaw(std::vector<AttestationResultType,std::allocator<AttestationResultType>> const &,ShsAttestationFlag,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,uint,uint *,AttestationResult * *)

- ea: `0x180008e3c`
- end: `0x180008ec3`
- name: `?AttestShsInternalRaw@AttestationHandler@Plugin@Client@HostGuardian@Microsoft@@AEAA?AW4AttestationError@@AEBV?$vector@W4AttestationResultType@@V?$allocator@W4AttestationResultType@@@std@@@std@@W4ShsAttestationFlag@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@8@IPEAIPEAPEAUAttestationResult@@@Z`
- size: `135`
- prototype: `__int64 __fastcall(__int64 *, __int64 *, int, __int64 *, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008d18`

## callees

- `0x180008e3c`

## import_xrefs

- `hgattest!Attest` at `0x180008eb7`
- `hgattest!Attest` at `0x180008eb7`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::Plugin::AttestationHandler::AttestShsInternalRaw(
        __int64 *a1,
        __int64 *a2,
        int a3,
        __int64 *a4,
        int a5,
        __int64 a6,
        __int64 a7)
{
  bool v7; // cc
  int v8; // eax
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rcx
  _DWORD v13[4]; // [rsp+20h] [rbp-30h] BYREF
  __int64 *v14; // [rsp+30h] [rbp-20h]
  __int128 v15; // [rsp+38h] [rbp-18h]
  __int64 v16; // [rsp+48h] [rbp-8h]

  v7 = (unsigned __int64)a4[3] <= 7;
  v8 = *((_DWORD *)a4 + 4);
  v15 = 0;
  v13[0] = 0;
  v16 = 0;
  v13[3] = v8;
  if ( !v7 )
    a4 = (__int64 *)*a4;
  v9 = *a1;
  v14 = a4;
  v13[2] = a5;
  v13[1] = a3;
  DWORD1(v15) = *(_DWORD *)(v9 + 120);
  v10 = *(_DWORD *)(v9 + 124);
  v11 = a2[1];
  LODWORD(v15) = v10;
  v16 = *a2;
  DWORD2(v15) = (v11 - v16) >> 2;
  v13[0] = 48;
  return Attest(2, v13, a6, a7);
}

```

## disassembly

```asm
0x180008e3c  push    rbp
0x180008e3e  mov     rbp, rsp
0x180008e41  sub     rsp, 50h
0x180008e45  cmp     qword ptr [r9+18h], 7
0x180008e4a  xorps   xmm0, xmm0
0x180008e4d  mov     eax, [r9+10h]
0x180008e51  movdqu  [rbp+var_18], xmm0
0x180008e56  mov     [rbp+var_30], 0
0x180008e5d  mov     [rbp+var_8], 0
0x180008e65  mov     [rbp+var_24], eax
0x180008e68  jbe     short loc_180008E6D
0x180008e6a  mov     r9, [r9]
0x180008e6d  mov     rcx, [rcx]
0x180008e70  mov     eax, [rbp+arg_20]
0x180008e73  mov     [rbp+var_20], r9
0x180008e77  mov     r9, [rbp+arg_30]
0x180008e7b  mov     [rbp+var_28], eax
0x180008e7e  mov     [rbp+var_2C], r8d
0x180008e82  mov     eax, [rcx+78h]
0x180008e85  mov     r8, [rbp+arg_28]
0x180008e89  mov     dword ptr [rbp+var_18+4], eax
0x180008e8c  mov     eax, [rcx+7Ch]
0x180008e8f  mov     rcx, [rdx+8]
0x180008e93  mov     dword ptr [rbp+var_18], eax
0x180008e96  mov     rax, [rdx]
0x180008e99  lea     rdx, [rbp+var_30]
0x180008e9d  sub     rcx, rax
0x180008ea0  mov     [rbp+var_8], rax
0x180008ea4  sar     rcx, 2
0x180008ea8  mov     dword ptr [rbp+var_18+8], ecx
0x180008eab  mov     ecx, 2
0x180008eb0  mov     [rbp+var_30], 30h ; '0'
0x180008eb7  call    cs:__imp_Attest
0x180008ebd  add     rsp, 50h
0x180008ec1  pop     rbp
0x180008ec2  retn
```
