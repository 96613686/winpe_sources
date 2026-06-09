# MergeAndValidatePrintTicketThunk2

- ea: `0x18001a150`
- end: `0x18001a235`
- name: `MergeAndValidatePrintTicketThunk2`
- size: `229`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, int, unsigned __int8 *, int, unsigned int, unsigned __int8 **, int *, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180005e70`
- `0x1800197e4`
- `0x180019900`
- `0x18001a150`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18001a1b9`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18001a1b9`

## pseudocode

```c
__int64 __fastcall MergeAndValidatePrintTicketThunk2(
        __int64 a1,
        unsigned __int8 *a2,
        int a3,
        unsigned __int8 *a4,
        int a5,
        unsigned int a6,
        unsigned __int8 **a7,
        int *a8,
        __int64 a9)
{
  HRESULT v11; // ebx
  int v12; // eax
  LPSTREAM ppstm; // [rsp+40h] [rbp-28h] BYREF
  struct IStream *v15; // [rsp+48h] [rbp-20h] BYREF
  struct IStream *v16[3]; // [rsp+50h] [rbp-18h] BYREF

  v16[0] = 0;
  v15 = 0;
  ppstm = 0;
  v11 = BufferToIStream(a2, a3, v16);
  if ( v11 >= 0 )
  {
    if ( !a4 || (v11 = BufferToIStream(a4, a5, &v15), v11 >= 0) )
    {
      v11 = CreateStreamOnHGlobal(0, 1, &ppstm);
      if ( v11 >= 0 )
      {
        v11 = ((__int64 (__fastcall *)(__int64, struct IStream *, struct IStream *, _QWORD, LPSTREAM, __int64))qword_1800321E8)(
                a1,
                v16[0],
                v15,
                a6,
                ppstm,
                a9);
        if ( v11 >= 0 )
        {
          v12 = IStreamToBuffer(ppstm, a7, a8);
          if ( v12 < 0 )
            v11 = v12;
        }
      }
    }
  }
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&ppstm);
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v15);
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(v16);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001a150  push    rbp
0x18001a152  push    rbx
0x18001a153  push    rsi
0x18001a154  push    rdi
0x18001a155  mov     rbp, rsp
0x18001a158  sub     rsp, 68h
0x18001a15c  mov     eax, r8d
0x18001a15f  mov     [rbp+var_18], 0
0x18001a167  mov     r10, rdx
0x18001a16a  mov     [rbp+var_20], 0
0x18001a172  mov     rsi, rcx
0x18001a175  mov     [rbp+ppstm], 0
0x18001a17d  mov     edx, eax; int
0x18001a17f  lea     r8, [rbp+var_18]; struct IStream **
0x18001a183  mov     rcx, r10; unsigned __int8 *
0x18001a186  mov     rdi, r9
0x18001a189  call    ?BufferToIStream@@YAJPEAEHPEAPEAUIStream@@@Z; BufferToIStream(uchar *,int,IStream * *)
0x18001a18e  mov     ebx, eax
0x18001a190  test    eax, eax
0x18001a192  js      short loc_18001A20F
0x18001a194  test    rdi, rdi
0x18001a197  jz      short loc_18001A1AE
0x18001a199  mov     edx, [rbp+arg_20]; int
0x18001a19c  lea     r8, [rbp+var_20]; struct IStream **
0x18001a1a0  mov     rcx, rdi; unsigned __int8 *
0x18001a1a3  call    ?BufferToIStream@@YAJPEAEHPEAPEAUIStream@@@Z; BufferToIStream(uchar *,int,IStream * *)
0x18001a1a8  mov     ebx, eax
0x18001a1aa  test    eax, eax
0x18001a1ac  js      short loc_18001A20F
0x18001a1ae  lea     r8, [rbp+ppstm]; ppstm
0x18001a1b2  mov     edx, 1; fDeleteOnRelease
0x18001a1b7  xor     ecx, ecx; hGlobal
0x18001a1b9  call    cs:__imp_CreateStreamOnHGlobal
0x18001a1bf  mov     ebx, eax
0x18001a1c1  test    eax, eax
0x18001a1c3  js      short loc_18001A20F
0x18001a1c5  mov     r9, [rbp+ppstm]
0x18001a1c9  mov     rcx, [rbp+arg_40]
0x18001a1cd  mov     r8, [rbp+var_20]
0x18001a1d1  mov     rdx, [rbp+var_18]
0x18001a1d5  mov     rax, cs:qword_1800321E8
0x18001a1dc  mov     [rsp+68h+var_40], rcx
0x18001a1e1  mov     rcx, rsi
0x18001a1e4  mov     [rsp+68h+var_48], r9
0x18001a1e9  mov     r9d, [rbp+arg_28]
0x18001a1ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1f2  mov     ebx, eax
0x18001a1f4  test    eax, eax
0x18001a1f6  js      short loc_18001A20F
0x18001a1f8  mov     r8, [rbp+arg_38]; int *
0x18001a1fc  mov     rdx, [rbp+arg_30]; unsigned __int8 **
0x18001a200  mov     rcx, [rbp+ppstm]; struct IStream *
0x18001a204  call    ?IStreamToBuffer@@YAJPEAUIStream@@PEAPEAEPEAH@Z; IStreamToBuffer(IStream *,uchar * *,int *)
0x18001a209  test    eax, eax
0x18001a20b  jns     short loc_18001A20F
0x18001a20d  mov     ebx, eax
0x18001a20f  lea     rcx, [rbp+ppstm]
0x18001a213  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001a218  lea     rcx, [rbp+var_20]
0x18001a21c  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001a221  lea     rcx, [rbp+var_18]
0x18001a225  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001a22a  mov     eax, ebx
0x18001a22c  add     rsp, 68h
0x18001a230  pop     rdi
0x18001a231  pop     rsi
0x18001a232  pop     rbx
0x18001a233  pop     rbp
0x18001a234  retn
```
