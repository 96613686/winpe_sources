# microsoft::fs::cryptography::CapiHash::Finalize(uchar *,ulong,microsoft::fs::common::FsException *)

- ea: `0x180033020`
- end: `0x18003310c`
- name: `?Finalize@CapiHash@cryptography@fs@microsoft@@UEAAXPEAEKPEAVFsException@common@34@@Z`
- size: `236`
- prototype: `void(microsoft::fs::cryptography::CapiHash *__hidden this, unsigned __int8 *, unsigned int, struct microsoft::fs::common::FsException *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800022ec`
- `0x180019448`
- `0x18002e5e4`
- `0x180031250`
- `0x180033020`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800330b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800330b0`

## string_xrefs

- `0x180033069`: `onecore\ds\security\services\ca\fs\crypto\capihash.cpp`
- `0x1800330ce`: `onecore\ds\security\services\ca\fs\crypto\capihash.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall microsoft::fs::cryptography::CapiHash::Finalize(
        microsoft::fs::cryptography::CapiHash *this,
        unsigned __int8 *a2,
        unsigned int a3,
        struct microsoft::fs::common::FsException *a4)
{
  DWORD LastError; // eax
  int v7; // eax
  microsoft::fs::common::FsException *v8; // rbx
  const struct microsoft::fs::common::FsException *v9; // rax
  const microsoft::fs::common::FsException *v10; // [rsp+30h] [rbp-A8h] BYREF
  _QWORD v11[6]; // [rsp+38h] [rbp-A0h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+68h] [rbp-70h] BYREF
  _BYTE v13[64]; // [rsp+98h] [rbp-40h] BYREF
  unsigned int v14; // [rsp+F0h] [rbp+18h] BYREF
  microsoft::fs::common::FsException *v15; // [rsp+F8h] [rbp+20h]

  v15 = a4;
  v14 = a3;
  try
  {
    if ( a4 )
      (*(void (__fastcall **)(struct microsoft::fs::common::FsException *))(*(_QWORD *)a4 + 8LL))(a4);
    if ( !a2 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)pExceptionObject,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capihash.cpp",
        0x5Au,
        L"pbHash",
        -2147024809);
      throw (microsoft::fs::common::FsException *)pExceptionObject;
    }
    if ( !(unsigned int)fsCryptGetHashParam(*((_QWORD *)this + 3), 2u, a2, &v14, 0) )
    {
      LastError = GetLastError();
      v7 = HR_FROM_WIN32(LastError);
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v13,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capihash.cpp",
        0x5Du,
        L"CryptGetHashParam(m_hHash, HP_HASHVAL, pbHash, &cbHash, 0)",
        v7);
      throw (microsoft::fs::common::FsException *)v13;
    }
  }
  catch ( const microsoft::fs::common::FsException *v10 )
  {
    if ( !v15 )
      throw;
    microsoft::fs::common::FsException::assign(v15, v10);
    return;
  }
  catch ( ... )
  {
    v8 = v15;
    if ( !v15 )
      throw;
    v9 = (const struct microsoft::fs::common::FsException *)microsoft::fs::common::FsException::FsException(
                                                              (microsoft::fs::common::FsException *)v11,
                                                              L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capihash.cpp",
                                                              0x67u,
                                                              &psz,
                                                              -2147467259,
                                                              L"Caught exception of unknown type");
    microsoft::fs::common::FsException::assign(v8, v9);
    v11[0] = &microsoft::fs::common::FsException::`vftable';
    operator delete[]((void *)v11[1]);
    operator delete[]((void *)v11[2]);
    operator delete[]((void *)v11[3]);
    operator delete[]((void *)v11[5]);
  }
}

```

## disassembly

```asm
0x180033020  mov     [rsp+arg_0], rbx
0x180033025  mov     [rsp+arg_18], r9
0x18003302a  mov     [rsp+arg_10], r8d
0x18003302f  push    rdi
0x180033030  sub     rsp, 0D0h
0x180033037  mov     rbx, rdx
0x18003303a  mov     rdi, rcx
0x18003303d  test    r9, r9
0x180033040  jz      short loc_180033051
0x180033042  mov     rax, [r9]
0x180033045  mov     rcx, r9
0x180033048  mov     rax, [rax+8]
0x18003304c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033051  test    rbx, rbx
0x180033054  jnz     short loc_18003308B
0x180033056  mov     [rsp+0D8h+var_B8], 80070057h; int
0x18003305e  lea     r9, aPbhash; "pbHash"
0x180033065  lea     r8d, [rbx+5Ah]; unsigned int
0x180033069  lea     rdx, aOnecoreDsSecur_1; "onecore\\ds\\security\\services\\ca\\fs"...
0x180033070  lea     rcx, [rsp+0D8h+pExceptionObject]; this
0x180033075  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18003307a  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180033081  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x180033086  call    _CxxThrowException_0
0x18003308b  mov     [rsp+0D8h+var_B8], 0; DWORD
0x180033093  lea     r9, [rsp+0D8h+arg_10]; unsigned int *
0x18003309b  mov     r8, rbx; unsigned __int8 *
0x18003309e  mov     edx, 2; unsigned int
0x1800330a3  mov     rcx, [rdi+18h]; unsigned __int64
0x1800330a7  call    ?fsCryptGetHashParam@@YAH_KKPEAEPEAKK@Z; fsCryptGetHashParam(unsigned __int64,ulong,uchar *,ulong *,ulong)
0x1800330ac  test    eax, eax
0x1800330ae  jnz     short loc_1800330F7
0x1800330b0  call    cs:__imp_GetLastError
0x1800330b6  mov     ecx, eax; unsigned int
0x1800330b8  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x1800330bd  mov     [rsp+0D8h+var_B8], eax; int
0x1800330c1  lea     r9, aCryptgethashpa_0; "CryptGetHashParam(m_hHash, HP_HASHVAL, "...
0x1800330c8  mov     r8d, 5Dh ; ']'; unsigned int
0x1800330ce  lea     rdx, aOnecoreDsSecur_1; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800330d5  lea     rcx, [rsp+0D8h+var_40]; this
0x1800330dd  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800330e2  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800330e9  lea     rcx, [rsp+0D8h+var_40]; pExceptionObject
0x1800330f1  call    _CxxThrowException_0
0x1800330f7  jmp     short loc_1800330FB
0x1800330f9  jmp     short $+2
0x1800330fb  mov     rbx, [rsp+0D8h+arg_0]
0x180033103  add     rsp, 0D0h
0x18003310a  pop     rdi
0x18003310b  retn
```
