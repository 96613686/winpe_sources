# GetPrintCapabilitiesThunk2

- ea: `0x180019db0`
- end: `0x180019e6f`
- name: `GetPrintCapabilitiesThunk2`
- size: `191`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, int, unsigned __int8 **, int *, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180005e70`
- `0x1800197e4`
- `0x180019900`
- `0x180019db0`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180019e05`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180019e05`

## pseudocode

```c
__int64 __fastcall GetPrintCapabilitiesThunk2(
        __int64 a1,
        unsigned __int8 *a2,
        int a3,
        unsigned __int8 **a4,
        int *a5,
        __int64 a6)
{
  HRESULT v8; // ebx
  struct IStream *v10[3]; // [rsp+30h] [rbp-18h] BYREF
  LPSTREAM ppstm; // [rsp+58h] [rbp+10h] BYREF

  v10[0] = 0;
  ppstm = 0;
  if ( !a2 || !a3 || (v8 = BufferToIStream(a2, a3, v10), v8 >= 0) )
  {
    v8 = CreateStreamOnHGlobal(0, 1, &ppstm);
    if ( v8 >= 0 )
    {
      v8 = ((__int64 (__fastcall *)(__int64, struct IStream *, LPSTREAM, __int64))qword_1800321E0)(
             a1,
             v10[0],
             ppstm,
             a6);
      if ( v8 >= 0 )
        v8 = IStreamToBuffer(ppstm, a4, a5);
    }
  }
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&ppstm);
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(v10);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180019db0  mov     r11, rsp
0x180019db3  mov     [r11+8], rbx
0x180019db7  mov     [r11+18h], rsi
0x180019dbb  push    rdi
0x180019dbc  sub     rsp, 40h
0x180019dc0  mov     qword ptr [r11-18h], 0
0x180019dc8  mov     rdi, r9
0x180019dcb  mov     qword ptr [r11+10h], 0
0x180019dd3  mov     eax, r8d
0x180019dd6  mov     r10, rdx
0x180019dd9  mov     rsi, rcx
0x180019ddc  test    rdx, rdx
0x180019ddf  jz      short loc_180019DF9
0x180019de1  test    eax, eax
0x180019de3  jz      short loc_180019DF9
0x180019de5  lea     r8, [r11-18h]; struct IStream **
0x180019de9  mov     edx, eax; int
0x180019deb  mov     rcx, r10; unsigned __int8 *
0x180019dee  call    ?BufferToIStream@@YAJPEAEHPEAPEAUIStream@@@Z; BufferToIStream(uchar *,int,IStream * *)
0x180019df3  mov     ebx, eax
0x180019df5  test    eax, eax
0x180019df7  js      short loc_180019E49
0x180019df9  lea     r8, [rsp+48h+ppstm]; ppstm
0x180019dfe  mov     edx, 1; fDeleteOnRelease
0x180019e03  xor     ecx, ecx; hGlobal
0x180019e05  call    cs:__imp_CreateStreamOnHGlobal
0x180019e0b  mov     ebx, eax
0x180019e0d  test    eax, eax
0x180019e0f  js      short loc_180019E49
0x180019e11  mov     r9, [rsp+48h+arg_28]
0x180019e16  mov     rcx, rsi
0x180019e19  mov     r8, [rsp+48h+ppstm]
0x180019e1e  mov     rdx, [rsp+48h+var_18]
0x180019e23  mov     rax, cs:qword_1800321E0
0x180019e2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e2f  mov     ebx, eax
0x180019e31  test    eax, eax
0x180019e33  js      short loc_180019E49
0x180019e35  mov     r8, [rsp+48h+arg_20]; int *
0x180019e3a  mov     rdx, rdi; unsigned __int8 **
0x180019e3d  mov     rcx, [rsp+48h+ppstm]; struct IStream *
0x180019e42  call    ?IStreamToBuffer@@YAJPEAUIStream@@PEAPEAEPEAH@Z; IStreamToBuffer(IStream *,uchar * *,int *)
0x180019e47  mov     ebx, eax
0x180019e49  lea     rcx, [rsp+48h+ppstm]
0x180019e4e  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180019e53  lea     rcx, [rsp+48h+var_18]
0x180019e58  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180019e5d  mov     rsi, [rsp+48h+arg_10]
0x180019e62  mov     eax, ebx
0x180019e64  mov     rbx, [rsp+48h+arg_0]
0x180019e69  add     rsp, 40h
0x180019e6d  pop     rdi
0x180019e6e  retn
```
