# NPrintTicketUtil::CPrinterWrapper::GetCapabilitiesBuffer<ushort>(_devicemodeW *,ushort,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::BufferEnumerator<ushort>> &)

- ea: `0x18000a420`
- end: `0x18000a4f2`
- name: `??$GetCapabilitiesBuffer@G@CPrinterWrapper@NPrintTicketUtil@@AEAAJPEAU_devicemodeW@@GAEAV?$TAutoPtrCOM@V?$BufferEnumerator@G@NPrintTicketUtil@@@NCoreLibrary@@@Z`
- size: `210`
- prototype: `__int64 __fastcall(NPrintTicketUtil::CPrinterWrapper *this, struct _devicemodeW *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000a2e0`

## callees

- `0x18000a420`
- `0x18000a560`
- `0x18000e03c`
- `0x18000f53c`
- `0x18001b070`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000a4a2`
- `KERNEL32!GetLastError` at `0x18000a4a2`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CPrinterWrapper::GetCapabilitiesBuffer<unsigned short>(
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

  v7 = NPrintTicketUtil::CPrinterWrapper::DeviceCapabilitiesWrapper(this, 2u, 0, a2);
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
      if ( NPrintTicketUtil::CPrinterWrapper::DeviceCapabilitiesWrapper(this, 2u, v9[2], a2) != -1 )
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
0x18000a420  push    rbx
0x18000a422  push    rbp
0x18000a423  push    rsi
0x18000a424  push    rdi
0x18000a425  push    r14
0x18000a427  push    r15
0x18000a429  sub     rsp, 28h
0x18000a42d  mov     rbp, rdx
0x18000a430  mov     r15, r9
0x18000a433  mov     r9, rbp; struct _devicemodeW *
0x18000a436  mov     edx, 2; unsigned __int16
0x18000a43b  xor     r8d, r8d; unsigned __int16 *
0x18000a43e  mov     r14, rcx
0x18000a441  call    ?DeviceCapabilitiesWrapper@CPrinterWrapper@NPrintTicketUtil@@AEAAHGPEAGPEBU_devicemodeW@@@Z; NPrintTicketUtil::CPrinterWrapper::DeviceCapabilitiesWrapper(ushort,ushort *,_devicemodeW const *)
0x18000a446  mov     ecx, 20h ; ' '; Size
0x18000a44b  mov     esi, eax
0x18000a44d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a452  mov     rbx, rax
0x18000a455  test    rax, rax
0x18000a458  jz      short loc_18000A4C8
0x18000a45a  xor     edi, edi
0x18000a45c  mov     dword ptr [rax+8], 1
0x18000a463  mov     [rbx+10h], rdi
0x18000a467  lea     rax, ??_7?$BufferEnumerator@G@NPrintTicketUtil@@6B@; const NPrintTicketUtil::BufferEnumerator<ushort>::`vftable'
0x18000a46e  mov     [rbx], rax
0x18000a471  mov     [rbx+18h], rdi
0x18000a475  test    esi, esi
0x18000a477  jle     short loc_18000A4BB
0x18000a479  mov     edx, esi
0x18000a47b  mov     rcx, rbx
0x18000a47e  call    ?Alloc@?$BufferEnumerator@F@NPrintTicketUtil@@QEAAJK@Z; NPrintTicketUtil::BufferEnumerator<short>::Alloc(ulong)
0x18000a483  mov     edi, eax
0x18000a485  test    eax, eax
0x18000a487  js      short loc_18000A4CF
0x18000a489  mov     r8, [rbx+10h]; unsigned __int16 *
0x18000a48d  mov     edx, 2; unsigned __int16
0x18000a492  mov     r9, rbp; struct _devicemodeW *
0x18000a495  mov     rcx, r14; this
0x18000a498  call    ?DeviceCapabilitiesWrapper@CPrinterWrapper@NPrintTicketUtil@@AEAAHGPEAGPEBU_devicemodeW@@@Z; NPrintTicketUtil::CPrinterWrapper::DeviceCapabilitiesWrapper(ushort,ushort *,_devicemodeW const *)
0x18000a49d  cmp     eax, 0FFFFFFFFh
0x18000a4a0  jnz     short loc_18000A4BB
0x18000a4a2  call    cs:__imp_GetLastError
0x18000a4a8  mov     edi, eax
0x18000a4aa  test    eax, eax
0x18000a4ac  jle     short loc_18000A4B7
0x18000a4ae  movzx   edi, ax
0x18000a4b1  or      edi, 80070000h
0x18000a4b7  test    edi, edi
0x18000a4b9  js      short loc_18000A4CF
0x18000a4bb  mov     rdx, rbx
0x18000a4be  mov     rcx, r15
0x18000a4c1  call    ??4?$TAutoPtrCOM@V?$BufferEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@QEAAPEAV?$BufferEnumerator@K@NPrintTicketUtil@@PEAV23@@Z; NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::BufferEnumerator<ulong>>::operator=(NPrintTicketUtil::BufferEnumerator<ulong> *)
0x18000a4c6  jmp     short loc_18000A4E3
0x18000a4c8  mov     edi, 8007000Eh
0x18000a4cd  xor     ebx, ebx
0x18000a4cf  test    rbx, rbx
0x18000a4d2  jz      short loc_18000A4E3
0x18000a4d4  mov     rax, [rbx]
0x18000a4d7  mov     rcx, rbx
0x18000a4da  mov     rax, [rax+10h]
0x18000a4de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4e3  mov     eax, edi
0x18000a4e5  add     rsp, 28h
0x18000a4e9  pop     r15
0x18000a4eb  pop     r14
0x18000a4ed  pop     rdi
0x18000a4ee  pop     rsi
0x18000a4ef  pop     rbp
0x18000a4f0  pop     rbx
0x18000a4f1  retn
```
