# NPrintTicketUtil::CPrinterWrapper::GetCapabilitiesBuffer<short>(_devicemodeW *,ushort,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::BufferEnumerator<short>> &)

- ea: `0x18000a348`
- end: `0x18000a41a`
- name: `??$GetCapabilitiesBuffer@F@CPrinterWrapper@NPrintTicketUtil@@AEAAJPEAU_devicemodeW@@GAEAV?$TAutoPtrCOM@V?$BufferEnumerator@F@NPrintTicketUtil@@@NCoreLibrary@@@Z`
- size: `210`
- prototype: `__int64 __fastcall(NPrintTicketUtil::CPrinterWrapper *this, struct _devicemodeW *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001d450`

## callees

- `0x18000a348`
- `0x18000a560`
- `0x18000e03c`
- `0x18000f53c`
- `0x18001b070`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000a3ca`
- `KERNEL32!GetLastError` at `0x18000a3ca`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CPrinterWrapper::GetCapabilitiesBuffer<short>(
        NPrintTicketUtil::CPrinterWrapper *this,
        struct _devicemodeW *a2,
        __int64 a3,
        __int64 *a4)
{
  int v7; // esi
  unsigned __int16 **v8; // rax
  unsigned __int16 **v9; // rbx
  signed int v10; // edi
  signed int LastError; // eax

  v7 = NPrintTicketUtil::CPrinterWrapper::DeviceCapabilitiesWrapper(this, 6u, 0, a2);
  v8 = (unsigned __int16 **)operator new(0x20u);
  v9 = v8;
  if ( v8 )
  {
    v10 = 0;
    *((_DWORD *)v8 + 2) = 1;
    v8[2] = 0;
    *v8 = (unsigned __int16 *)&NPrintTicketUtil::BufferEnumerator<unsigned short>::`vftable';
    v8[3] = 0;
    if ( v7 <= 0 )
      goto LABEL_8;
    v10 = NPrintTicketUtil::BufferEnumerator<short>::Alloc(v8, (unsigned int)v7);
    if ( v10 >= 0 )
    {
      if ( NPrintTicketUtil::CPrinterWrapper::DeviceCapabilitiesWrapper(this, 6u, v9[2], a2) != -1 )
        goto LABEL_8;
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      if ( v10 >= 0 )
      {
LABEL_8:
        NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::BufferEnumerator<unsigned long>>::operator=(a4, (__int64)v9);
        return (unsigned int)v10;
      }
    }
  }
  else
  {
    v10 = -2147024882;
    v9 = 0;
  }
  if ( v9 )
    (*((void (__fastcall **)(unsigned __int16 **))*v9 + 2))(v9);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000a348  push    rbx
0x18000a34a  push    rbp
0x18000a34b  push    rsi
0x18000a34c  push    rdi
0x18000a34d  push    r14
0x18000a34f  push    r15
0x18000a351  sub     rsp, 28h
0x18000a355  mov     rbp, rdx
0x18000a358  mov     r15, r9
0x18000a35b  mov     r9, rbp; struct _devicemodeW *
0x18000a35e  mov     edx, 6; unsigned __int16
0x18000a363  xor     r8d, r8d; unsigned __int16 *
0x18000a366  mov     r14, rcx
0x18000a369  call    ?DeviceCapabilitiesWrapper@CPrinterWrapper@NPrintTicketUtil@@AEAAHGPEAGPEBU_devicemodeW@@@Z; NPrintTicketUtil::CPrinterWrapper::DeviceCapabilitiesWrapper(ushort,ushort *,_devicemodeW const *)
0x18000a36e  mov     ecx, 20h ; ' '; Size
0x18000a373  mov     esi, eax
0x18000a375  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a37a  mov     rbx, rax
0x18000a37d  test    rax, rax
0x18000a380  jz      short loc_18000A3F0
0x18000a382  xor     edi, edi
0x18000a384  mov     dword ptr [rax+8], 1
0x18000a38b  mov     [rbx+10h], rdi
0x18000a38f  lea     rax, ??_7?$BufferEnumerator@G@NPrintTicketUtil@@6B@; const NPrintTicketUtil::BufferEnumerator<ushort>::`vftable'
0x18000a396  mov     [rbx], rax
0x18000a399  mov     [rbx+18h], rdi
0x18000a39d  test    esi, esi
0x18000a39f  jle     short loc_18000A3E3
0x18000a3a1  mov     edx, esi
0x18000a3a3  mov     rcx, rbx
0x18000a3a6  call    ?Alloc@?$BufferEnumerator@F@NPrintTicketUtil@@QEAAJK@Z; NPrintTicketUtil::BufferEnumerator<short>::Alloc(ulong)
0x18000a3ab  mov     edi, eax
0x18000a3ad  test    eax, eax
0x18000a3af  js      short loc_18000A3F7
0x18000a3b1  mov     r8, [rbx+10h]; unsigned __int16 *
0x18000a3b5  mov     edx, 6; unsigned __int16
0x18000a3ba  mov     r9, rbp; struct _devicemodeW *
0x18000a3bd  mov     rcx, r14; this
0x18000a3c0  call    ?DeviceCapabilitiesWrapper@CPrinterWrapper@NPrintTicketUtil@@AEAAHGPEAGPEBU_devicemodeW@@@Z; NPrintTicketUtil::CPrinterWrapper::DeviceCapabilitiesWrapper(ushort,ushort *,_devicemodeW const *)
0x18000a3c5  cmp     eax, 0FFFFFFFFh
0x18000a3c8  jnz     short loc_18000A3E3
0x18000a3ca  call    cs:__imp_GetLastError
0x18000a3d0  mov     edi, eax
0x18000a3d2  test    eax, eax
0x18000a3d4  jle     short loc_18000A3DF
0x18000a3d6  movzx   edi, ax
0x18000a3d9  or      edi, 80070000h
0x18000a3df  test    edi, edi
0x18000a3e1  js      short loc_18000A3F7
0x18000a3e3  mov     rdx, rbx
0x18000a3e6  mov     rcx, r15
0x18000a3e9  call    ??4?$TAutoPtrCOM@V?$BufferEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@QEAAPEAV?$BufferEnumerator@K@NPrintTicketUtil@@PEAV23@@Z; NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::BufferEnumerator<ulong>>::operator=(NPrintTicketUtil::BufferEnumerator<ulong> *)
0x18000a3ee  jmp     short loc_18000A40B
0x18000a3f0  mov     edi, 8007000Eh
0x18000a3f5  xor     ebx, ebx
0x18000a3f7  test    rbx, rbx
0x18000a3fa  jz      short loc_18000A40B
0x18000a3fc  mov     rax, [rbx]
0x18000a3ff  mov     rcx, rbx
0x18000a402  mov     rax, [rax+10h]
0x18000a406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a40b  mov     eax, edi
0x18000a40d  add     rsp, 28h
0x18000a411  pop     r15
0x18000a413  pop     r14
0x18000a415  pop     rdi
0x18000a416  pop     rsi
0x18000a417  pop     rbp
0x18000a418  pop     rbx
0x18000a419  retn
```
