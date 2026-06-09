# NPrintTicketUtil::CPrinterWrapper::GetCapabilitiesBuffer<tagPOINT>(_devicemodeW *,ushort,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::BufferEnumerator<tagPOINT>> &)

- ea: `0x18001a73c`
- end: `0x18001a864`
- name: `??$GetCapabilitiesBuffer@UtagPOINT@@@CPrinterWrapper@NPrintTicketUtil@@AEAAJPEAU_devicemodeW@@GAEAV?$TAutoPtrCOM@V?$BufferEnumerator@UtagPOINT@@@NPrintTicketUtil@@@NCoreLibrary@@@Z`
- size: `296`
- prototype: `__int64 __fastcall(NPrintTicketUtil::CPrinterWrapper *this, struct _devicemodeW *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001d6e0`

## callees

- `0x180005e70`
- `0x18000a560`
- `0x18000e03c`
- `0x18000f524`
- `0x18000f530`
- `0x18000f53c`
- `0x18001a73c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001a815`
- `KERNEL32!GetLastError` at `0x18001a815`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CPrinterWrapper::GetCapabilitiesBuffer<tagPOINT>(
        NPrintTicketUtil::CPrinterWrapper *this,
        struct _devicemodeW *a2,
        __int64 a3,
        __int64 *a4)
{
  unsigned __int64 v7; // rsi
  _DWORD *v8; // rax
  signed int v9; // ebx
  __int64 v10; // rdi
  void *v11; // rcx
  unsigned __int16 *v12; // rax
  signed int LastError; // eax
  __int64 v14; // rdx
  __int64 v16[9]; // [rsp+20h] [rbp-48h] BYREF

  v7 = (unsigned int)NPrintTicketUtil::CPrinterWrapper::DeviceCapabilitiesWrapper(this, 3u, 0, a2);
  v16[0] = 0;
  v8 = operator new(0x20u);
  if ( v8 )
  {
    v8[2] = 1;
    *(_QWORD *)v8 = &NPrintTicketUtil::BufferEnumerator<tagPOINT>::`vftable';
    *((_QWORD *)v8 + 2) = 0;
    *((_QWORD *)v8 + 3) = 0;
  }
  if ( !NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::BufferEnumerator<unsigned long>>::operator=(v16, (__int64)v8) )
    goto LABEL_4;
  v10 = v16[0];
  v9 = 0;
  if ( (int)v7 <= 0 )
    goto LABEL_13;
  v11 = *(void **)(v16[0] + 16);
  if ( v11 )
    operator delete(v11);
  v12 = (unsigned __int16 *)operator new[](saturated_mul(v7, 8u));
  *(_QWORD *)(v10 + 16) = v12;
  if ( !v12 )
  {
LABEL_4:
    v9 = -2147024882;
    goto LABEL_16;
  }
  *(_DWORD *)(v10 + 28) = v7;
  *(_DWORD *)(v10 + 24) = 0;
  if ( NPrintTicketUtil::CPrinterWrapper::DeviceCapabilitiesWrapper(this, 3u, v12, a2) != -1 )
    goto LABEL_13;
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
  if ( v9 >= 0 )
  {
LABEL_13:
    v14 = 0;
    if ( v10 )
    {
      v14 = v10;
      v16[0] = 0;
    }
    NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::BufferEnumerator<unsigned long>>::operator=(a4, v14);
  }
LABEL_16:
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(v16);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001a73c  push    rbx
0x18001a73e  push    rbp
0x18001a73f  push    rsi
0x18001a740  push    rdi
0x18001a741  push    r13
0x18001a743  push    r14
0x18001a745  push    r15
0x18001a747  sub     rsp, 30h
0x18001a74b  mov     r14, rdx
0x18001a74e  mov     rbp, r9
0x18001a751  mov     r9, r14; struct _devicemodeW *
0x18001a754  mov     edx, 3; unsigned __int16
0x18001a759  xor     r8d, r8d; unsigned __int16 *
0x18001a75c  mov     r15, rcx
0x18001a75f  call    ?DeviceCapabilitiesWrapper@CPrinterWrapper@NPrintTicketUtil@@AEAAHGPEAGPEBU_devicemodeW@@@Z; NPrintTicketUtil::CPrinterWrapper::DeviceCapabilitiesWrapper(ushort,ushort *,_devicemodeW const *)
0x18001a764  mov     ecx, 20h ; ' '; Size
0x18001a769  mov     esi, eax
0x18001a76b  mov     [rsp+68h+var_48], 0
0x18001a774  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a779  test    rax, rax
0x18001a77c  jz      short loc_18001A79F
0x18001a77e  lea     rcx, ??_7?$BufferEnumerator@UtagPOINT@@@NPrintTicketUtil@@6B@; const NPrintTicketUtil::BufferEnumerator<tagPOINT>::`vftable'
0x18001a785  mov     dword ptr [rax+8], 1
0x18001a78c  mov     [rax], rcx
0x18001a78f  mov     qword ptr [rax+10h], 0
0x18001a797  mov     qword ptr [rax+18h], 0
0x18001a79f  mov     rdx, rax
0x18001a7a2  lea     rcx, [rsp+68h+var_48]
0x18001a7a7  call    ??4?$TAutoPtrCOM@V?$BufferEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@QEAAPEAV?$BufferEnumerator@K@NPrintTicketUtil@@PEAV23@@Z; NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::BufferEnumerator<ulong>>::operator=(NPrintTicketUtil::BufferEnumerator<ulong> *)
0x18001a7ac  test    rax, rax
0x18001a7af  jnz     short loc_18001A7BB
0x18001a7b1  mov     ebx, 8007000Eh
0x18001a7b6  jmp     loc_18001A849
0x18001a7bb  mov     rdi, [rsp+68h+var_48]
0x18001a7c0  xor     ebx, ebx
0x18001a7c2  test    esi, esi
0x18001a7c4  jle     short loc_18001A82E
0x18001a7c6  mov     rcx, [rdi+10h]; Block
0x18001a7ca  test    rcx, rcx
0x18001a7cd  jz      short loc_18001A7D4
0x18001a7cf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a7d4  mov     eax, 8
0x18001a7d9  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18001a7e0  mul     rsi
0x18001a7e3  cmovb   rax, r13
0x18001a7e7  mov     rcx, rax; unsigned __int64
0x18001a7ea  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001a7ef  mov     [rdi+10h], rax
0x18001a7f3  test    rax, rax
0x18001a7f6  jz      short loc_18001A7B1
0x18001a7f8  lea     edx, [r13+4]; unsigned __int16
0x18001a7fc  mov     [rdi+1Ch], esi
0x18001a7ff  mov     r9, r14; struct _devicemodeW *
0x18001a802  mov     [rdi+18h], ebx
0x18001a805  mov     r8, rax; unsigned __int16 *
0x18001a808  mov     rcx, r15; this
0x18001a80b  call    ?DeviceCapabilitiesWrapper@CPrinterWrapper@NPrintTicketUtil@@AEAAHGPEAGPEBU_devicemodeW@@@Z; NPrintTicketUtil::CPrinterWrapper::DeviceCapabilitiesWrapper(ushort,ushort *,_devicemodeW const *)
0x18001a810  cmp     eax, r13d
0x18001a813  jnz     short loc_18001A82E
0x18001a815  call    cs:__imp_GetLastError
0x18001a81b  mov     ebx, eax
0x18001a81d  test    eax, eax
0x18001a81f  jle     short loc_18001A82A
0x18001a821  movzx   ebx, ax
0x18001a824  or      ebx, 80070000h
0x18001a82a  test    ebx, ebx
0x18001a82c  js      short loc_18001A849
0x18001a82e  xor     edx, edx
0x18001a830  test    rdi, rdi
0x18001a833  jz      short loc_18001A841
0x18001a835  mov     rdx, rdi
0x18001a838  mov     [rsp+68h+var_48], 0
0x18001a841  mov     rcx, rbp
0x18001a844  call    ??4?$TAutoPtrCOM@V?$BufferEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@QEAAPEAV?$BufferEnumerator@K@NPrintTicketUtil@@PEAV23@@Z; NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::BufferEnumerator<ulong>>::operator=(NPrintTicketUtil::BufferEnumerator<ulong> *)
0x18001a849  lea     rcx, [rsp+68h+var_48]
0x18001a84e  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001a853  mov     eax, ebx
0x18001a855  add     rsp, 30h
0x18001a859  pop     r15
0x18001a85b  pop     r14
0x18001a85d  pop     r13
0x18001a85f  pop     rdi
0x18001a860  pop     rsi
0x18001a861  pop     rbp
0x18001a862  pop     rbx
0x18001a863  retn
```
