# GetPrintDeviceCapabilitiesThunk2

- ea: `0x180019eb0`
- end: `0x180019f9e`
- name: `GetPrintDeviceCapabilitiesThunk2`
- size: `238`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, int, LPVOID *, int *, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180005e70`
- `0x1800197e4`
- `0x180019900`
- `0x180019eb0`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180019f2a`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180019f2a`

## pseudocode

```c
__int64 __fastcall GetPrintDeviceCapabilitiesThunk2(
        __int64 a1,
        unsigned __int8 *a2,
        int a3,
        LPVOID *a4,
        int *a5,
        __int64 a6)
{
  int *v8; // rdi
  int v9; // ebx
  struct IStream *v11[7]; // [rsp+30h] [rbp-38h] BYREF
  LPSTREAM ppstm; // [rsp+88h] [rbp+20h] BYREF

  if ( !a4 )
    return 2147942487LL;
  v8 = a5;
  if ( !a5 )
    return 2147942487LL;
  *a4 = 0;
  *v8 = 0;
  v11[0] = 0;
  ppstm = 0;
  if ( !a2 || !a3 || (v9 = BufferToIStream(a2, a3, v11), v9 >= 0) )
  {
    v9 = CreateStreamOnHGlobal(0, 1, &ppstm);
    if ( v9 >= 0 )
    {
      v9 = ((__int64 (__fastcall *)(__int64, struct IStream *, LPSTREAM, __int64))qword_1800321F8)(
             a1,
             v11[0],
             ppstm,
             a6);
      if ( v9 >= 0 )
        v9 = IStreamToBuffer(ppstm, a4, v8);
    }
  }
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&ppstm);
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(v11);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180019eb0  mov     r11, rsp
0x180019eb3  push    rbx
0x180019eb4  push    rbp
0x180019eb5  push    rsi
0x180019eb6  push    rdi
0x180019eb7  sub     rsp, 48h
0x180019ebb  mov     rsi, r9
0x180019ebe  mov     eax, r8d
0x180019ec1  mov     r9, rdx
0x180019ec4  mov     rbp, rcx
0x180019ec7  test    rsi, rsi
0x180019eca  jz      loc_180019F90
0x180019ed0  mov     rdi, [rsp+68h+arg_20]
0x180019ed8  test    rdi, rdi
0x180019edb  jz      loc_180019F90
0x180019ee1  mov     qword ptr [rsi], 0
0x180019ee8  mov     dword ptr [rdi], 0
0x180019eee  mov     qword ptr [r11-38h], 0
0x180019ef6  mov     qword ptr [r11+20h], 0
0x180019efe  test    rdx, rdx
0x180019f01  jz      short loc_180019F1B
0x180019f03  test    eax, eax
0x180019f05  jz      short loc_180019F1B
0x180019f07  lea     r8, [r11-38h]; struct IStream **
0x180019f0b  mov     edx, eax; int
0x180019f0d  mov     rcx, r9; unsigned __int8 *
0x180019f10  call    ?BufferToIStream@@YAJPEAEHPEAPEAUIStream@@@Z; BufferToIStream(uchar *,int,IStream * *)
0x180019f15  mov     ebx, eax
0x180019f17  test    eax, eax
0x180019f19  js      short loc_180019F75
0x180019f1b  lea     r8, [rsp+68h+ppstm]; ppstm
0x180019f23  mov     edx, 1; fDeleteOnRelease
0x180019f28  xor     ecx, ecx; hGlobal
0x180019f2a  call    cs:__imp_CreateStreamOnHGlobal
0x180019f30  mov     ebx, eax
0x180019f32  test    eax, eax
0x180019f34  js      short loc_180019F75
0x180019f36  mov     r9, [rsp+68h+arg_28]
0x180019f3e  mov     rcx, rbp
0x180019f41  mov     r8, [rsp+68h+ppstm]
0x180019f49  mov     rdx, [rsp+68h+var_38]
0x180019f4e  mov     rax, cs:qword_1800321F8
0x180019f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f5a  mov     ebx, eax
0x180019f5c  test    eax, eax
0x180019f5e  js      short loc_180019F75
0x180019f60  mov     rcx, [rsp+68h+ppstm]; struct IStream *
0x180019f68  mov     r8, rdi; int *
0x180019f6b  mov     rdx, rsi; unsigned __int8 **
0x180019f6e  call    ?IStreamToBuffer@@YAJPEAUIStream@@PEAPEAEPEAH@Z; IStreamToBuffer(IStream *,uchar * *,int *)
0x180019f73  mov     ebx, eax
0x180019f75  lea     rcx, [rsp+68h+ppstm]
0x180019f7d  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180019f82  lea     rcx, [rsp+68h+var_38]
0x180019f87  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180019f8c  mov     eax, ebx
0x180019f8e  jmp     short loc_180019F95
0x180019f90  mov     eax, 80070057h
0x180019f95  add     rsp, 48h
0x180019f99  pop     rdi
0x180019f9a  pop     rsi
0x180019f9b  pop     rbp
0x180019f9c  pop     rbx
0x180019f9d  retn
```
