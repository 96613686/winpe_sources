# NPrintTicketUtil::CPrinterWrapper::GetCapabilitiesBuffer<ulong>(_devicemodeW *,ushort,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::BufferEnumerator<ulong>> &)

- ea: `0x18001a60c`
- end: `0x18001a734`
- name: `??$GetCapabilitiesBuffer@K@CPrinterWrapper@NPrintTicketUtil@@AEAAJPEAU_devicemodeW@@GAEAV?$TAutoPtrCOM@V?$BufferEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@@Z`
- size: `296`
- prototype: `__int64 __fastcall(NPrintTicketUtil::CPrinterWrapper *this, struct _devicemodeW *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001d550`

## callees

- `0x180005e70`
- `0x18000a560`
- `0x18000e03c`
- `0x18000f524`
- `0x18000f530`
- `0x18000f53c`
- `0x18001a60c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001a6e5`
- `KERNEL32!GetLastError` at `0x18001a6e5`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CPrinterWrapper::GetCapabilitiesBuffer<unsigned long>(
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

  v7 = (unsigned int)NPrintTicketUtil::CPrinterWrapper::DeviceCapabilitiesWrapper(this, 0x23u, 0, a2);
  v16[0] = 0;
  v8 = operator new(0x20u);
  if ( v8 )
  {
    v8[2] = 1;
    *(_QWORD *)v8 = &NPrintTicketUtil::BufferEnumerator<unsigned long>::`vftable';
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
  v12 = (unsigned __int16 *)operator new[](saturated_mul(v7, 4u));
  *(_QWORD *)(v10 + 16) = v12;
  if ( !v12 )
  {
LABEL_4:
    v9 = -2147024882;
    goto LABEL_16;
  }
  *(_DWORD *)(v10 + 28) = v7;
  *(_DWORD *)(v10 + 24) = 0;
  if ( NPrintTicketUtil::CPrinterWrapper::DeviceCapabilitiesWrapper(this, 0x23u, v12, a2) != -1 )
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
0x18001a60c  push    rbx
0x18001a60e  push    rbp
0x18001a60f  push    rsi
0x18001a610  push    rdi
0x18001a611  push    r13
0x18001a613  push    r14
0x18001a615  push    r15
0x18001a617  sub     rsp, 30h
0x18001a61b  mov     r14, rdx
0x18001a61e  mov     rbp, r9
0x18001a621  mov     r9, r14; struct _devicemodeW *
0x18001a624  mov     edx, 23h ; '#'; unsigned __int16
0x18001a629  xor     r8d, r8d; unsigned __int16 *
0x18001a62c  mov     r15, rcx
0x18001a62f  call    ?DeviceCapabilitiesWrapper@CPrinterWrapper@NPrintTicketUtil@@AEAAHGPEAGPEBU_devicemodeW@@@Z; NPrintTicketUtil::CPrinterWrapper::DeviceCapabilitiesWrapper(ushort,ushort *,_devicemodeW const *)
0x18001a634  mov     ecx, 20h ; ' '; Size
0x18001a639  mov     esi, eax
0x18001a63b  mov     [rsp+68h+var_48], 0
0x18001a644  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a649  test    rax, rax
0x18001a64c  jz      short loc_18001A66F
0x18001a64e  lea     rcx, ??_7?$BufferEnumerator@K@NPrintTicketUtil@@6B@; const NPrintTicketUtil::BufferEnumerator<ulong>::`vftable'
0x18001a655  mov     dword ptr [rax+8], 1
0x18001a65c  mov     [rax], rcx
0x18001a65f  mov     qword ptr [rax+10h], 0
0x18001a667  mov     qword ptr [rax+18h], 0
0x18001a66f  mov     rdx, rax
0x18001a672  lea     rcx, [rsp+68h+var_48]
0x18001a677  call    ??4?$TAutoPtrCOM@V?$BufferEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@QEAAPEAV?$BufferEnumerator@K@NPrintTicketUtil@@PEAV23@@Z; NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::BufferEnumerator<ulong>>::operator=(NPrintTicketUtil::BufferEnumerator<ulong> *)
0x18001a67c  test    rax, rax
0x18001a67f  jnz     short loc_18001A68B
0x18001a681  mov     ebx, 8007000Eh
0x18001a686  jmp     loc_18001A719
0x18001a68b  mov     rdi, [rsp+68h+var_48]
0x18001a690  xor     ebx, ebx
0x18001a692  test    esi, esi
0x18001a694  jle     short loc_18001A6FE
0x18001a696  mov     rcx, [rdi+10h]; Block
0x18001a69a  test    rcx, rcx
0x18001a69d  jz      short loc_18001A6A4
0x18001a69f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a6a4  mov     eax, 4
0x18001a6a9  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18001a6b0  mul     rsi
0x18001a6b3  cmovb   rax, r13
0x18001a6b7  mov     rcx, rax; unsigned __int64
0x18001a6ba  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001a6bf  mov     [rdi+10h], rax
0x18001a6c3  test    rax, rax
0x18001a6c6  jz      short loc_18001A681
0x18001a6c8  lea     edx, [r13+24h]; unsigned __int16
0x18001a6cc  mov     [rdi+1Ch], esi
0x18001a6cf  mov     r9, r14; struct _devicemodeW *
0x18001a6d2  mov     [rdi+18h], ebx
0x18001a6d5  mov     r8, rax; unsigned __int16 *
0x18001a6d8  mov     rcx, r15; this
0x18001a6db  call    ?DeviceCapabilitiesWrapper@CPrinterWrapper@NPrintTicketUtil@@AEAAHGPEAGPEBU_devicemodeW@@@Z; NPrintTicketUtil::CPrinterWrapper::DeviceCapabilitiesWrapper(ushort,ushort *,_devicemodeW const *)
0x18001a6e0  cmp     eax, r13d
0x18001a6e3  jnz     short loc_18001A6FE
0x18001a6e5  call    cs:__imp_GetLastError
0x18001a6eb  mov     ebx, eax
0x18001a6ed  test    eax, eax
0x18001a6ef  jle     short loc_18001A6FA
0x18001a6f1  movzx   ebx, ax
0x18001a6f4  or      ebx, 80070000h
0x18001a6fa  test    ebx, ebx
0x18001a6fc  js      short loc_18001A719
0x18001a6fe  xor     edx, edx
0x18001a700  test    rdi, rdi
0x18001a703  jz      short loc_18001A711
0x18001a705  mov     rdx, rdi
0x18001a708  mov     [rsp+68h+var_48], 0
0x18001a711  mov     rcx, rbp
0x18001a714  call    ??4?$TAutoPtrCOM@V?$BufferEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@QEAAPEAV?$BufferEnumerator@K@NPrintTicketUtil@@PEAV23@@Z; NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::BufferEnumerator<ulong>>::operator=(NPrintTicketUtil::BufferEnumerator<ulong> *)
0x18001a719  lea     rcx, [rsp+68h+var_48]
0x18001a71e  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001a723  mov     eax, ebx
0x18001a725  add     rsp, 30h
0x18001a729  pop     r15
0x18001a72b  pop     r14
0x18001a72d  pop     r13
0x18001a72f  pop     rdi
0x18001a730  pop     rsi
0x18001a731  pop     rbp
0x18001a732  pop     rbx
0x18001a733  retn
```
