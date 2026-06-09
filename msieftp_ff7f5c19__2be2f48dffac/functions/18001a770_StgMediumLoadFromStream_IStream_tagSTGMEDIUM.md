# StgMediumLoadFromStream(IStream *,tagSTGMEDIUM *)

- ea: `0x18001a770`
- end: `0x18001a8ad`
- name: `?StgMediumLoadFromStream@@YAJPEAUIStream@@PEAUtagSTGMEDIUM@@@Z`
- size: `317`
- prototype: `__int64 __fastcall(struct IStream *, struct tagSTGMEDIUM *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001a010`

## callees

- `0x180002240`
- `0x18001a770`
- `0x180028010`

## import_xrefs

- `SHLWAPI!__imp_IStream_Read` at `0x18001a7c3`
- `SHLWAPI!__imp_IStream_Read` at `0x18001a7c3`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x18001a877`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x18001a877`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18001a82f`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18001a82f`

## pseudocode

```c
__int64 __fastcall StgMediumLoadFromStream(struct IStream *a1, struct tagSTGMEDIUM *a2)
{
  HRESULT StreamOnHGlobal; // ebx
  int v5; // eax
  LPSTREAM ppstm[2]; // [rsp+30h] [rbp-30h] BYREF
  __int128 pv; // [rsp+40h] [rbp-20h] BYREF
  __int64 v9; // [rsp+50h] [rbp-10h]

  StreamOnHGlobal = -2147024809;
  if ( a1 )
  {
    if ( a2 )
    {
      a2->pUnkForRelease = 0;
      pv = 0;
      v9 = 0;
      StreamOnHGlobal = IStream_Read(a1, &pv, 0x18u);
      if ( StreamOnHGlobal >= 0 )
      {
        v5 = DWORD2(pv);
        a2->tymed = DWORD2(pv);
        if ( --v5 )
        {
          if ( DWORD1(pv) )
          {
            ppstm[0] = (LPSTREAM)DWORD1(pv);
            (*(void (__fastcall **)(struct IStream *, _QWORD, __int64, _QWORD))(*(_QWORD *)a1 + 40LL))(
              a1,
              DWORD1(pv),
              1,
              0);
          }
          return (unsigned int)-2147467263;
        }
        else
        {
          ppstm[0] = 0;
          StreamOnHGlobal = CreateStreamOnHGlobal(0, 0, ppstm);
          if ( StreamOnHGlobal >= 0 )
          {
            ppstm[1] = (LPSTREAM)DWORD1(pv);
            StreamOnHGlobal = (*(__int64 (__fastcall **)(struct IStream *, LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a1 + 56LL))(
                                a1,
                                ppstm[0],
                                DWORD1(pv),
                                0,
                                0);
            if ( StreamOnHGlobal >= 0 )
              StreamOnHGlobal = GetHGlobalFromStream(ppstm[0], &a2->hMetaFilePict);
            (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm[0] + 16LL))(ppstm[0]);
          }
        }
      }
    }
  }
  return (unsigned int)StreamOnHGlobal;
}

```

## disassembly

```asm
0x18001a770  mov     [rsp-18h+arg_10], rbx
0x18001a775  push    rbp
0x18001a776  push    rsi
0x18001a777  push    rdi
0x18001a778  mov     rbp, rsp
0x18001a77b  sub     rsp, 60h
0x18001a77f  mov     rax, cs:__security_cookie
0x18001a786  xor     rax, rsp
0x18001a789  mov     [rbp+var_8], rax
0x18001a78d  mov     rdi, rdx
0x18001a790  mov     rsi, rcx
0x18001a793  mov     ebx, 80070057h
0x18001a798  test    rcx, rcx
0x18001a79b  jz      loc_18001A88F
0x18001a7a1  test    rdx, rdx
0x18001a7a4  jz      loc_18001A88F
0x18001a7aa  xor     eax, eax
0x18001a7ac  xorps   xmm0, xmm0
0x18001a7af  mov     [rdx+10h], rax
0x18001a7b3  lea     rdx, [rbp+pv]; pv
0x18001a7b7  movups  [rbp+pv], xmm0
0x18001a7bb  mov     [rbp+var_10], rax
0x18001a7bf  lea     r8d, [rax+18h]; cb
0x18001a7c3  call    cs:__imp_IStream_Read
0x18001a7c9  mov     ebx, eax
0x18001a7cb  test    eax, eax
0x18001a7cd  js      loc_18001A88F
0x18001a7d3  mov     eax, dword ptr [rbp+pv+8]
0x18001a7d6  mov     [rdi], eax
0x18001a7d8  sub     eax, 1
0x18001a7db  jz      short loc_18001A81F
0x18001a7dd  sub     eax, 1
0x18001a7e0  jz      short loc_18001A7EF
0x18001a7e2  sub     eax, 2
0x18001a7e5  jz      short loc_18001A7EF
0x18001a7e7  sub     eax, 4
0x18001a7ea  jz      short loc_18001A7EF
0x18001a7ec  sub     eax, 8
0x18001a7ef  mov     eax, dword ptr [rbp+pv+4]
0x18001a7f2  test    eax, eax
0x18001a7f4  jz      short loc_18001A818
0x18001a7f6  xor     ecx, ecx
0x18001a7f8  mov     dword ptr [rbp+ppstm], eax
0x18001a7fb  mov     rax, [rsi]
0x18001a7fe  xor     r9d, r9d
0x18001a801  mov     dword ptr [rbp+ppstm+4], ecx
0x18001a804  mov     rdx, [rbp+ppstm]
0x18001a808  lea     r8d, [rcx+1]
0x18001a80c  mov     rcx, rsi
0x18001a80f  mov     rax, [rax+28h]
0x18001a813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a818  mov     ebx, 80004001h
0x18001a81d  jmp     short loc_18001A88F
0x18001a81f  lea     r8, [rbp+ppstm]; ppstm
0x18001a823  mov     [rbp+ppstm], 0
0x18001a82b  xor     edx, edx; fDeleteOnRelease
0x18001a82d  xor     ecx, ecx; hGlobal
0x18001a82f  call    cs:__imp_CreateStreamOnHGlobal
0x18001a835  mov     ebx, eax
0x18001a837  test    eax, eax
0x18001a839  js      short loc_18001A88F
0x18001a83b  mov     rdx, [rbp+ppstm]
0x18001a83f  xor     eax, eax
0x18001a841  mov     dword ptr [rbp+var_28+4], eax
0x18001a844  xor     r9d, r9d
0x18001a847  mov     eax, dword ptr [rbp+pv+4]
0x18001a84a  mov     rcx, rsi
0x18001a84d  mov     dword ptr [rbp+var_28], eax
0x18001a850  mov     rax, [rsi]
0x18001a853  mov     r8, [rbp+var_28]
0x18001a857  mov     [rsp+60h+var_40], 0
0x18001a860  mov     rax, [rax+38h]
0x18001a864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a869  mov     ebx, eax
0x18001a86b  test    eax, eax
0x18001a86d  js      short loc_18001A87F
0x18001a86f  mov     rcx, [rbp+ppstm]; pstm
0x18001a873  lea     rdx, [rdi+8]; phglobal
0x18001a877  call    cs:__imp_GetHGlobalFromStream
0x18001a87d  mov     ebx, eax
0x18001a87f  mov     rcx, [rbp+ppstm]
0x18001a883  mov     rax, [rcx]
0x18001a886  mov     rax, [rax+10h]
0x18001a88a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a88f  mov     eax, ebx
0x18001a891  mov     rcx, [rbp+var_8]
0x18001a895  xor     rcx, rsp; StackCookie
0x18001a898  call    __security_check_cookie
0x18001a89d  mov     rbx, [rsp+60h+arg_10]
0x18001a8a5  add     rsp, 60h
0x18001a8a9  pop     rdi
0x18001a8aa  pop     rsi
0x18001a8ab  pop     rbp
0x18001a8ac  retn
```
