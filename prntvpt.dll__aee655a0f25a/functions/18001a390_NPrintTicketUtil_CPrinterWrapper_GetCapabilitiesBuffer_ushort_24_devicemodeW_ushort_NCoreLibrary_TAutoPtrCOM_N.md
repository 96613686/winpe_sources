# NPrintTicketUtil::CPrinterWrapper::GetCapabilitiesBuffer<ushort [24]>(_devicemodeW *,ushort,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::BufferEnumerator<ushort [24]>> &)

- ea: `0x18001a390`
- end: `0x18001a4c6`
- name: `??$GetCapabilitiesBuffer@$$BY0BI@G@CPrinterWrapper@NPrintTicketUtil@@AEAAJPEAU_devicemodeW@@GAEAV?$TAutoPtrCOM@V?$BufferEnumerator@$$BY0BI@G@NPrintTicketUtil@@@NCoreLibrary@@@Z`
- size: `310`
- prototype: `__int64 __fastcall(NPrintTicketUtil::CPrinterWrapper *this, struct _devicemodeW *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001d4c0`

## callees

- `0x180005e70`
- `0x18000a560`
- `0x18000e03c`
- `0x18000f524`
- `0x18000f530`
- `0x18000f53c`
- `0x18001a390`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001a477`
- `KERNEL32!GetLastError` at `0x18001a477`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CPrinterWrapper::GetCapabilitiesBuffer<unsigned short [24]>(
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
  unsigned __int64 v12; // rcx
  unsigned __int16 *v13; // rax
  signed int LastError; // eax
  __int64 v15; // rdx
  __int64 v17[9]; // [rsp+20h] [rbp-48h] BYREF

  v7 = (unsigned int)NPrintTicketUtil::CPrinterWrapper::DeviceCapabilitiesWrapper(this, 0xCu, 0, a2);
  v17[0] = 0;
  v8 = operator new(0x20u);
  if ( v8 )
  {
    v8[2] = 1;
    *(_QWORD *)v8 = &NPrintTicketUtil::BufferEnumerator<unsigned short [24]>::`vftable';
    *((_QWORD *)v8 + 2) = 0;
    *((_QWORD *)v8 + 3) = 0;
  }
  if ( !NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::BufferEnumerator<unsigned long>>::operator=(v17, (__int64)v8) )
    goto LABEL_4;
  v10 = v17[0];
  v9 = 0;
  if ( (int)v7 <= 0 )
    goto LABEL_15;
  v11 = *(void **)(v17[0] + 16);
  if ( v11 )
    operator delete(v11);
  v12 = 24 * v7;
  if ( !is_mul_ok(v7, 0x18u) )
    v12 = -1;
  v13 = (unsigned __int16 *)operator new[](saturated_mul(v12, 2u));
  *(_QWORD *)(v10 + 16) = v13;
  if ( !v13 )
  {
LABEL_4:
    v9 = -2147024882;
    goto LABEL_18;
  }
  *(_DWORD *)(v10 + 28) = v7;
  *(_DWORD *)(v10 + 24) = 0;
  if ( NPrintTicketUtil::CPrinterWrapper::DeviceCapabilitiesWrapper(this, 0xCu, v13, a2) != -1 )
    goto LABEL_15;
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
  if ( v9 >= 0 )
  {
LABEL_15:
    v15 = 0;
    if ( v10 )
    {
      v15 = v10;
      v17[0] = 0;
    }
    NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::BufferEnumerator<unsigned long>>::operator=(a4, v15);
  }
LABEL_18:
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(v17);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001a390  push    rbx
0x18001a392  push    rbp
0x18001a393  push    rsi
0x18001a394  push    rdi
0x18001a395  push    r13
0x18001a397  push    r14
0x18001a399  push    r15
0x18001a39b  sub     rsp, 30h
0x18001a39f  mov     rbp, rdx
0x18001a3a2  mov     r15, r9
0x18001a3a5  mov     r9, rbp; struct _devicemodeW *
0x18001a3a8  mov     edx, 0Ch; unsigned __int16
0x18001a3ad  xor     r8d, r8d; unsigned __int16 *
0x18001a3b0  mov     r14, rcx
0x18001a3b3  call    ?DeviceCapabilitiesWrapper@CPrinterWrapper@NPrintTicketUtil@@AEAAHGPEAGPEBU_devicemodeW@@@Z; NPrintTicketUtil::CPrinterWrapper::DeviceCapabilitiesWrapper(ushort,ushort *,_devicemodeW const *)
0x18001a3b8  mov     ecx, 20h ; ' '; Size
0x18001a3bd  mov     esi, eax
0x18001a3bf  mov     [rsp+68h+var_48], 0
0x18001a3c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a3cd  test    rax, rax
0x18001a3d0  jz      short loc_18001A3F3
0x18001a3d2  lea     rcx, ??_7?$BufferEnumerator@$$BY0BI@G@NPrintTicketUtil@@6B@; const NPrintTicketUtil::BufferEnumerator<ushort [24]>::`vftable'
0x18001a3d9  mov     dword ptr [rax+8], 1
0x18001a3e0  mov     [rax], rcx
0x18001a3e3  mov     qword ptr [rax+10h], 0
0x18001a3eb  mov     qword ptr [rax+18h], 0
0x18001a3f3  mov     rdx, rax
0x18001a3f6  lea     rcx, [rsp+68h+var_48]
0x18001a3fb  call    ??4?$TAutoPtrCOM@V?$BufferEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@QEAAPEAV?$BufferEnumerator@K@NPrintTicketUtil@@PEAV23@@Z; NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::BufferEnumerator<ulong>>::operator=(NPrintTicketUtil::BufferEnumerator<ulong> *)
0x18001a400  test    rax, rax
0x18001a403  jnz     short loc_18001A40F
0x18001a405  mov     ebx, 8007000Eh
0x18001a40a  jmp     loc_18001A4AB
0x18001a40f  mov     rdi, [rsp+68h+var_48]
0x18001a414  xor     ebx, ebx
0x18001a416  test    esi, esi
0x18001a418  jle     short loc_18001A490
0x18001a41a  mov     rcx, [rdi+10h]; Block
0x18001a41e  test    rcx, rcx
0x18001a421  jz      short loc_18001A428
0x18001a423  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a428  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18001a42f  mov     eax, 18h
0x18001a434  mul     rsi
0x18001a437  mov     rcx, rax
0x18001a43a  lea     eax, [r13+3]
0x18001a43e  cmovb   rcx, r13
0x18001a442  mul     rcx
0x18001a445  cmovb   rax, r13
0x18001a449  mov     rcx, rax; unsigned __int64
0x18001a44c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001a451  mov     [rdi+10h], rax
0x18001a455  test    rax, rax
0x18001a458  jz      short loc_18001A405
0x18001a45a  lea     edx, [r13+0Dh]; unsigned __int16
0x18001a45e  mov     [rdi+1Ch], esi
0x18001a461  mov     r9, rbp; struct _devicemodeW *
0x18001a464  mov     [rdi+18h], ebx
0x18001a467  mov     r8, rax; unsigned __int16 *
0x18001a46a  mov     rcx, r14; this
0x18001a46d  call    ?DeviceCapabilitiesWrapper@CPrinterWrapper@NPrintTicketUtil@@AEAAHGPEAGPEBU_devicemodeW@@@Z; NPrintTicketUtil::CPrinterWrapper::DeviceCapabilitiesWrapper(ushort,ushort *,_devicemodeW const *)
0x18001a472  cmp     eax, r13d
0x18001a475  jnz     short loc_18001A490
0x18001a477  call    cs:__imp_GetLastError
0x18001a47d  mov     ebx, eax
0x18001a47f  test    eax, eax
0x18001a481  jle     short loc_18001A48C
0x18001a483  movzx   ebx, ax
0x18001a486  or      ebx, 80070000h
0x18001a48c  test    ebx, ebx
0x18001a48e  js      short loc_18001A4AB
0x18001a490  xor     edx, edx
0x18001a492  test    rdi, rdi
0x18001a495  jz      short loc_18001A4A3
0x18001a497  mov     rdx, rdi
0x18001a49a  mov     [rsp+68h+var_48], 0
0x18001a4a3  mov     rcx, r15
0x18001a4a6  call    ??4?$TAutoPtrCOM@V?$BufferEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@QEAAPEAV?$BufferEnumerator@K@NPrintTicketUtil@@PEAV23@@Z; NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::BufferEnumerator<ulong>>::operator=(NPrintTicketUtil::BufferEnumerator<ulong> *)
0x18001a4ab  lea     rcx, [rsp+68h+var_48]
0x18001a4b0  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001a4b5  mov     eax, ebx
0x18001a4b7  add     rsp, 30h
0x18001a4bb  pop     r15
0x18001a4bd  pop     r14
0x18001a4bf  pop     r13
0x18001a4c1  pop     rdi
0x18001a4c2  pop     rsi
0x18001a4c3  pop     rbp
0x18001a4c4  pop     rbx
0x18001a4c5  retn
```
