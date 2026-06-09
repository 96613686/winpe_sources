# GetPrintDeviceResourcesThunk2

- ea: `0x180019ff0`
- end: `0x18001a0e2`
- name: `GetPrintDeviceResourcesThunk2`
- size: `242`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int8 *, int, LPSTREAM ppstm, int *, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180005e70`
- `0x1800197e4`
- `0x180019900`
- `0x180019ff0`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18001a06e`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18001a06e`

## pseudocode

```c
__int64 __fastcall GetPrintDeviceResourcesThunk2(
        __int64 a1,
        __int64 a2,
        unsigned __int8 *a3,
        int a4,
        LPSTREAM ppstm,
        int *a6,
        __int64 a7)
{
  LPSTREAM v7; // rsi
  int *v9; // rdi
  int v10; // ebx
  struct IStream *v12[7]; // [rsp+30h] [rbp-38h] BYREF

  v7 = ppstm;
  if ( !ppstm )
    return 2147942487LL;
  v9 = a6;
  if ( !a6 )
    return 2147942487LL;
  ppstm->lpVtbl = 0;
  *v9 = 0;
  v12[0] = 0;
  ppstm = 0;
  if ( !a3 || !a4 || (v10 = BufferToIStream(a3, a4, v12), v10 >= 0) )
  {
    v10 = CreateStreamOnHGlobal(0, 1, &ppstm);
    if ( v10 >= 0 )
    {
      v10 = ((__int64 (__fastcall *)(__int64, struct IStream *, LPSTREAM, __int64))qword_1800321F8)(
              a1,
              v12[0],
              ppstm,
              a7);
      if ( v10 >= 0 )
        v10 = IStreamToBuffer(ppstm, (LPVOID *)&v7->lpVtbl, v9);
    }
  }
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&ppstm);
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(v12);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180019ff0  mov     r11, rsp
0x180019ff3  push    rbx
0x180019ff4  push    rbp
0x180019ff5  push    rsi
0x180019ff6  push    rdi
0x180019ff7  sub     rsp, 48h
0x180019ffb  mov     rsi, [rsp+68h+ppstm]
0x18001a003  mov     rax, r8
0x18001a006  mov     rbp, rcx
0x18001a009  test    rsi, rsi
0x18001a00c  jz      loc_18001A0D4
0x18001a012  mov     rdi, [rsp+68h+arg_28]
0x18001a01a  test    rdi, rdi
0x18001a01d  jz      loc_18001A0D4
0x18001a023  mov     qword ptr [rsi], 0
0x18001a02a  mov     dword ptr [rdi], 0
0x18001a030  mov     qword ptr [r11-38h], 0
0x18001a038  mov     qword ptr [r11+28h], 0
0x18001a040  test    rax, rax
0x18001a043  jz      short loc_18001A05F
0x18001a045  test    r9d, r9d
0x18001a048  jz      short loc_18001A05F
0x18001a04a  lea     r8, [r11-38h]; struct IStream **
0x18001a04e  mov     edx, r9d; int
0x18001a051  mov     rcx, rax; unsigned __int8 *
0x18001a054  call    ?BufferToIStream@@YAJPEAEHPEAPEAUIStream@@@Z; BufferToIStream(uchar *,int,IStream * *)
0x18001a059  mov     ebx, eax
0x18001a05b  test    eax, eax
0x18001a05d  js      short loc_18001A0B9
0x18001a05f  lea     r8, [rsp+68h+ppstm]; ppstm
0x18001a067  mov     edx, 1; fDeleteOnRelease
0x18001a06c  xor     ecx, ecx; hGlobal
0x18001a06e  call    cs:__imp_CreateStreamOnHGlobal
0x18001a074  mov     ebx, eax
0x18001a076  test    eax, eax
0x18001a078  js      short loc_18001A0B9
0x18001a07a  mov     r9, [rsp+68h+arg_30]
0x18001a082  mov     rcx, rbp
0x18001a085  mov     r8, [rsp+68h+ppstm]
0x18001a08d  mov     rdx, [rsp+68h+var_38]
0x18001a092  mov     rax, cs:qword_1800321F8
0x18001a099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a09e  mov     ebx, eax
0x18001a0a0  test    eax, eax
0x18001a0a2  js      short loc_18001A0B9
0x18001a0a4  mov     rcx, [rsp+68h+ppstm]; struct IStream *
0x18001a0ac  mov     r8, rdi; int *
0x18001a0af  mov     rdx, rsi; unsigned __int8 **
0x18001a0b2  call    ?IStreamToBuffer@@YAJPEAUIStream@@PEAPEAEPEAH@Z; IStreamToBuffer(IStream *,uchar * *,int *)
0x18001a0b7  mov     ebx, eax
0x18001a0b9  lea     rcx, [rsp+68h+ppstm]
0x18001a0c1  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001a0c6  lea     rcx, [rsp+68h+var_38]
0x18001a0cb  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001a0d0  mov     eax, ebx
0x18001a0d2  jmp     short loc_18001A0D9
0x18001a0d4  mov     eax, 80070057h
0x18001a0d9  add     rsp, 48h
0x18001a0dd  pop     rdi
0x18001a0de  pop     rsi
0x18001a0df  pop     rbp
0x18001a0e0  pop     rbx
0x18001a0e1  retn
```
