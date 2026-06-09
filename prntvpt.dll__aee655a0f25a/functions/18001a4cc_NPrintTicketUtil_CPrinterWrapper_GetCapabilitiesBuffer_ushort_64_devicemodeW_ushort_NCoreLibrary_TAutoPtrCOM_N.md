# NPrintTicketUtil::CPrinterWrapper::GetCapabilitiesBuffer<ushort [64]>(_devicemodeW *,ushort,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::BufferEnumerator<ushort [64]>> &)

- ea: `0x18001a4cc`
- end: `0x18001a603`
- name: `??$GetCapabilitiesBuffer@$$BY0EA@G@CPrinterWrapper@NPrintTicketUtil@@AEAAJPEAU_devicemodeW@@GAEAV?$TAutoPtrCOM@V?$BufferEnumerator@$$BY0EA@G@NPrintTicketUtil@@@NCoreLibrary@@@Z`
- size: `311`
- prototype: `__int64 __fastcall(NPrintTicketUtil::CPrinterWrapper *this, struct _devicemodeW *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001d5c0`
- `0x18001d650`

## callees

- `0x180005e70`
- `0x18000a560`
- `0x18000e03c`
- `0x18000f524`
- `0x18000f530`
- `0x18000f53c`
- `0x18001a4cc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001a5b4`
- `KERNEL32!GetLastError` at `0x18001a5b4`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CPrinterWrapper::GetCapabilitiesBuffer<unsigned short [64]>(
        NPrintTicketUtil::CPrinterWrapper *this,
        struct _devicemodeW *a2,
        unsigned __int16 a3,
        __int64 *a4)
{
  unsigned __int64 v8; // rsi
  _DWORD *v9; // rax
  signed int v10; // ebx
  __int64 v11; // rdi
  void *v12; // rcx
  unsigned __int64 v13; // rcx
  unsigned __int16 *v14; // rax
  signed int LastError; // eax
  __int64 v16; // rdx
  __int64 v18[9]; // [rsp+20h] [rbp-48h] BYREF

  v8 = (unsigned int)NPrintTicketUtil::CPrinterWrapper::DeviceCapabilitiesWrapper(this, a3, 0, a2);
  v18[0] = 0;
  v9 = operator new(0x20u);
  if ( v9 )
  {
    v9[2] = 1;
    *(_QWORD *)v9 = &NPrintTicketUtil::BufferEnumerator<unsigned short [64]>::`vftable';
    *((_QWORD *)v9 + 2) = 0;
    *((_QWORD *)v9 + 3) = 0;
  }
  if ( !NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::BufferEnumerator<unsigned long>>::operator=(v18, (__int64)v9) )
    goto LABEL_4;
  v11 = v18[0];
  v10 = 0;
  if ( (int)v8 <= 0 )
    goto LABEL_15;
  v12 = *(void **)(v18[0] + 16);
  if ( v12 )
    operator delete(v12);
  v13 = v8 << 6;
  if ( !is_mul_ok(v8, 0x40u) )
    v13 = -1;
  v14 = (unsigned __int16 *)operator new[](saturated_mul(v13, 2u));
  *(_QWORD *)(v11 + 16) = v14;
  if ( !v14 )
  {
LABEL_4:
    v10 = -2147024882;
    goto LABEL_18;
  }
  *(_DWORD *)(v11 + 28) = v8;
  *(_DWORD *)(v11 + 24) = 0;
  if ( NPrintTicketUtil::CPrinterWrapper::DeviceCapabilitiesWrapper(this, a3, v14, a2) != -1 )
    goto LABEL_15;
  LastError = GetLastError();
  v10 = LastError;
  if ( LastError > 0 )
    v10 = (unsigned __int16)LastError | 0x80070000;
  if ( v10 >= 0 )
  {
LABEL_15:
    v16 = 0;
    if ( v11 )
    {
      v16 = v11;
      v18[0] = 0;
    }
    NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::BufferEnumerator<unsigned long>>::operator=(a4, v16);
  }
LABEL_18:
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(v18);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001a4cc  push    rbx
0x18001a4ce  push    rbp
0x18001a4cf  push    rsi
0x18001a4d0  push    rdi
0x18001a4d1  push    r12
0x18001a4d3  push    r14
0x18001a4d5  push    r15
0x18001a4d7  sub     rsp, 30h
0x18001a4db  movzx   ebp, r8w
0x18001a4df  mov     r12, r9
0x18001a4e2  mov     r9, rdx; struct _devicemodeW *
0x18001a4e5  mov     r14, rdx
0x18001a4e8  movzx   edx, bp; unsigned __int16
0x18001a4eb  xor     r8d, r8d; unsigned __int16 *
0x18001a4ee  mov     r15, rcx
0x18001a4f1  call    ?DeviceCapabilitiesWrapper@CPrinterWrapper@NPrintTicketUtil@@AEAAHGPEAGPEBU_devicemodeW@@@Z; NPrintTicketUtil::CPrinterWrapper::DeviceCapabilitiesWrapper(ushort,ushort *,_devicemodeW const *)
0x18001a4f6  mov     ecx, 20h ; ' '; Size
0x18001a4fb  mov     esi, eax
0x18001a4fd  mov     [rsp+68h+var_48], 0
0x18001a506  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a50b  test    rax, rax
0x18001a50e  jz      short loc_18001A531
0x18001a510  lea     rcx, ??_7?$BufferEnumerator@$$BY0EA@G@NPrintTicketUtil@@6B@; const NPrintTicketUtil::BufferEnumerator<ushort [64]>::`vftable'
0x18001a517  mov     dword ptr [rax+8], 1
0x18001a51e  mov     [rax], rcx
0x18001a521  mov     qword ptr [rax+10h], 0
0x18001a529  mov     qword ptr [rax+18h], 0
0x18001a531  mov     rdx, rax
0x18001a534  lea     rcx, [rsp+68h+var_48]
0x18001a539  call    ??4?$TAutoPtrCOM@V?$BufferEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@QEAAPEAV?$BufferEnumerator@K@NPrintTicketUtil@@PEAV23@@Z; NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::BufferEnumerator<ulong>>::operator=(NPrintTicketUtil::BufferEnumerator<ulong> *)
0x18001a53e  test    rax, rax
0x18001a541  jnz     short loc_18001A54D
0x18001a543  mov     ebx, 8007000Eh
0x18001a548  jmp     loc_18001A5E8
0x18001a54d  mov     rdi, [rsp+68h+var_48]
0x18001a552  xor     ebx, ebx
0x18001a554  test    esi, esi
0x18001a556  jle     short loc_18001A5CD
0x18001a558  mov     rcx, [rdi+10h]; Block
0x18001a55c  test    rcx, rcx
0x18001a55f  jz      short loc_18001A566
0x18001a561  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a566  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18001a56d  mov     eax, 40h ; '@'
0x18001a572  mul     rsi
0x18001a575  mov     rcx, rax
0x18001a578  lea     eax, [r8+3]
0x18001a57c  cmovb   rcx, r8
0x18001a580  mul     rcx
0x18001a583  cmovb   rax, r8
0x18001a587  mov     rcx, rax; unsigned __int64
0x18001a58a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001a58f  mov     [rdi+10h], rax
0x18001a593  test    rax, rax
0x18001a596  jz      short loc_18001A543
0x18001a598  mov     r9, r14; struct _devicemodeW *
0x18001a59b  mov     [rdi+1Ch], esi
0x18001a59e  mov     r8, rax; unsigned __int16 *
0x18001a5a1  mov     [rdi+18h], ebx
0x18001a5a4  movzx   edx, bp; unsigned __int16
0x18001a5a7  mov     rcx, r15; this
0x18001a5aa  call    ?DeviceCapabilitiesWrapper@CPrinterWrapper@NPrintTicketUtil@@AEAAHGPEAGPEBU_devicemodeW@@@Z; NPrintTicketUtil::CPrinterWrapper::DeviceCapabilitiesWrapper(ushort,ushort *,_devicemodeW const *)
0x18001a5af  cmp     eax, 0FFFFFFFFh
0x18001a5b2  jnz     short loc_18001A5CD
0x18001a5b4  call    cs:__imp_GetLastError
0x18001a5ba  mov     ebx, eax
0x18001a5bc  test    eax, eax
0x18001a5be  jle     short loc_18001A5C9
0x18001a5c0  movzx   ebx, ax
0x18001a5c3  or      ebx, 80070000h
0x18001a5c9  test    ebx, ebx
0x18001a5cb  js      short loc_18001A5E8
0x18001a5cd  xor     edx, edx
0x18001a5cf  test    rdi, rdi
0x18001a5d2  jz      short loc_18001A5E0
0x18001a5d4  mov     rdx, rdi
0x18001a5d7  mov     [rsp+68h+var_48], 0
0x18001a5e0  mov     rcx, r12
0x18001a5e3  call    ??4?$TAutoPtrCOM@V?$BufferEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@QEAAPEAV?$BufferEnumerator@K@NPrintTicketUtil@@PEAV23@@Z; NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::BufferEnumerator<ulong>>::operator=(NPrintTicketUtil::BufferEnumerator<ulong> *)
0x18001a5e8  lea     rcx, [rsp+68h+var_48]
0x18001a5ed  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001a5f2  mov     eax, ebx
0x18001a5f4  add     rsp, 30h
0x18001a5f8  pop     r15
0x18001a5fa  pop     r14
0x18001a5fc  pop     r12
0x18001a5fe  pop     rdi
0x18001a5ff  pop     rsi
0x18001a600  pop     rbp
0x18001a601  pop     rbx
0x18001a602  retn
```
