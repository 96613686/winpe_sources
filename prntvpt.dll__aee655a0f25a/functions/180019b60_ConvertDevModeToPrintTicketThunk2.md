# ConvertDevModeToPrintTicketThunk2

- ea: `0x180019b60`
- end: `0x180019c08`
- name: `ConvertDevModeToPrintTicketThunk2`
- size: `168`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, unsigned __int8 **, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180005e70`
- `0x180019900`
- `0x180019b60`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180019b9f`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180019b9f`

## pseudocode

```c
__int64 __fastcall ConvertDevModeToPrintTicketThunk2(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned __int8 **a5,
        int *a6)
{
  int v9; // ebx
  LPSTREAM ppstm; // [rsp+48h] [rbp+10h] BYREF

  ppstm = 0;
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&ppstm);
  ppstm = 0;
  CreateStreamOnHGlobal(0, 1, &ppstm);
  v9 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64, _QWORD, LPSTREAM))qword_180032210)(
         a1,
         *(unsigned __int16 *)(a2 + 68) + (unsigned int)*(unsigned __int16 *)(a2 + 70),
         a2,
         a4,
         ppstm);
  if ( v9 >= 0 )
    v9 = IStreamToBuffer(ppstm, a5, a6);
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&ppstm);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180019b60  mov     rax, rsp
0x180019b63  mov     [rax+8], rbx
0x180019b67  mov     [rax+18h], rsi
0x180019b6b  push    rdi
0x180019b6c  sub     rsp, 30h
0x180019b70  mov     rsi, rcx
0x180019b73  mov     qword ptr [rax+10h], 0
0x180019b7b  lea     rcx, [rax+10h]
0x180019b7f  mov     edi, r9d
0x180019b82  mov     rbx, rdx
0x180019b85  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180019b8a  lea     r8, [rsp+38h+ppstm]; ppstm
0x180019b8f  mov     [rsp+38h+ppstm], 0
0x180019b98  mov     edx, 1; fDeleteOnRelease
0x180019b9d  xor     ecx, ecx; hGlobal
0x180019b9f  call    cs:__imp_CreateStreamOnHGlobal
0x180019ba5  mov     r9, [rsp+38h+ppstm]
0x180019baa  mov     rcx, rsi
0x180019bad  movzx   r8d, word ptr [rbx+44h]
0x180019bb2  movzx   edx, word ptr [rbx+46h]
0x180019bb6  mov     rax, cs:qword_180032210
0x180019bbd  add     edx, r8d
0x180019bc0  mov     [rsp+38h+var_18], r9
0x180019bc5  mov     r8, rbx
0x180019bc8  mov     r9d, edi
0x180019bcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019bd0  mov     ebx, eax
0x180019bd2  test    eax, eax
0x180019bd4  js      short loc_180019BEC
0x180019bd6  mov     r8, [rsp+38h+arg_28]; int *
0x180019bdb  mov     rdx, [rsp+38h+arg_20]; unsigned __int8 **
0x180019be0  mov     rcx, [rsp+38h+ppstm]; struct IStream *
0x180019be5  call    ?IStreamToBuffer@@YAJPEAUIStream@@PEAPEAEPEAH@Z; IStreamToBuffer(IStream *,uchar * *,int *)
0x180019bea  mov     ebx, eax
0x180019bec  lea     rcx, [rsp+38h+ppstm]
0x180019bf1  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180019bf6  mov     rsi, [rsp+38h+arg_10]
0x180019bfb  mov     eax, ebx
0x180019bfd  mov     rbx, [rsp+38h+arg_0]
0x180019c02  add     rsp, 30h
0x180019c06  pop     rdi
0x180019c07  retn
```
