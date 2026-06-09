# NPrintTicketUtil::CPrinterWrapper::GetCapabilitiesBuffer<long [2]>(_devicemodeW *,ushort,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::BufferEnumerator<long [2]>> &)

- ea: `0x18001a254`
- end: `0x18001a38a`
- name: `??$GetCapabilitiesBuffer@$$BY01J@CPrinterWrapper@NPrintTicketUtil@@AEAAJPEAU_devicemodeW@@GAEAV?$TAutoPtrCOM@V?$BufferEnumerator@$$BY01J@NPrintTicketUtil@@@NCoreLibrary@@@Z`
- size: `310`
- prototype: `__int64 __fastcall(NPrintTicketUtil::CPrinterWrapper *this, struct _devicemodeW *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001d750`

## callees

- `0x180005e70`
- `0x18000a560`
- `0x18000e03c`
- `0x18000f524`
- `0x18000f530`
- `0x18000f53c`
- `0x18001a254`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001a33b`
- `KERNEL32!GetLastError` at `0x18001a33b`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CPrinterWrapper::GetCapabilitiesBuffer<long [2]>(
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

  v7 = (unsigned int)NPrintTicketUtil::CPrinterWrapper::DeviceCapabilitiesWrapper(this, 0xDu, 0, a2);
  v17[0] = 0;
  v8 = operator new(0x20u);
  if ( v8 )
  {
    v8[2] = 1;
    *(_QWORD *)v8 = &NPrintTicketUtil::BufferEnumerator<tagPOINT>::`vftable';
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
  v12 = 2 * v7;
  if ( !is_mul_ok(v7, 2u) )
    v12 = -1;
  v13 = (unsigned __int16 *)operator new[](saturated_mul(v12, 4u));
  *(_QWORD *)(v10 + 16) = v13;
  if ( !v13 )
  {
LABEL_4:
    v9 = -2147024882;
    goto LABEL_18;
  }
  *(_DWORD *)(v10 + 28) = v7;
  *(_DWORD *)(v10 + 24) = 0;
  if ( NPrintTicketUtil::CPrinterWrapper::DeviceCapabilitiesWrapper(this, 0xDu, v13, a2) != -1 )
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
0x18001a254  push    rbx
0x18001a256  push    rbp
0x18001a257  push    rsi
0x18001a258  push    rdi
0x18001a259  push    r13
0x18001a25b  push    r14
0x18001a25d  push    r15
0x18001a25f  sub     rsp, 30h
0x18001a263  mov     rbp, rdx
0x18001a266  mov     r15, r9
0x18001a269  mov     r9, rbp; struct _devicemodeW *
0x18001a26c  mov     edx, 0Dh; unsigned __int16
0x18001a271  xor     r8d, r8d; unsigned __int16 *
0x18001a274  mov     r14, rcx
0x18001a277  call    ?DeviceCapabilitiesWrapper@CPrinterWrapper@NPrintTicketUtil@@AEAAHGPEAGPEBU_devicemodeW@@@Z; NPrintTicketUtil::CPrinterWrapper::DeviceCapabilitiesWrapper(ushort,ushort *,_devicemodeW const *)
0x18001a27c  mov     ecx, 20h ; ' '; Size
0x18001a281  mov     esi, eax
0x18001a283  mov     [rsp+68h+var_48], 0
0x18001a28c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a291  test    rax, rax
0x18001a294  jz      short loc_18001A2B7
0x18001a296  lea     rcx, ??_7?$BufferEnumerator@UtagPOINT@@@NPrintTicketUtil@@6B@; const NPrintTicketUtil::BufferEnumerator<tagPOINT>::`vftable'
0x18001a29d  mov     dword ptr [rax+8], 1
0x18001a2a4  mov     [rax], rcx
0x18001a2a7  mov     qword ptr [rax+10h], 0
0x18001a2af  mov     qword ptr [rax+18h], 0
0x18001a2b7  mov     rdx, rax
0x18001a2ba  lea     rcx, [rsp+68h+var_48]
0x18001a2bf  call    ??4?$TAutoPtrCOM@V?$BufferEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@QEAAPEAV?$BufferEnumerator@K@NPrintTicketUtil@@PEAV23@@Z; NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::BufferEnumerator<ulong>>::operator=(NPrintTicketUtil::BufferEnumerator<ulong> *)
0x18001a2c4  test    rax, rax
0x18001a2c7  jnz     short loc_18001A2D3
0x18001a2c9  mov     ebx, 8007000Eh
0x18001a2ce  jmp     loc_18001A36F
0x18001a2d3  mov     rdi, [rsp+68h+var_48]
0x18001a2d8  xor     ebx, ebx
0x18001a2da  test    esi, esi
0x18001a2dc  jle     short loc_18001A354
0x18001a2de  mov     rcx, [rdi+10h]; Block
0x18001a2e2  test    rcx, rcx
0x18001a2e5  jz      short loc_18001A2EC
0x18001a2e7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a2ec  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18001a2f3  mov     eax, 2
0x18001a2f8  mul     rsi
0x18001a2fb  mov     rcx, rax
0x18001a2fe  lea     eax, [r13+5]
0x18001a302  cmovb   rcx, r13
0x18001a306  mul     rcx
0x18001a309  cmovb   rax, r13
0x18001a30d  mov     rcx, rax; unsigned __int64
0x18001a310  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001a315  mov     [rdi+10h], rax
0x18001a319  test    rax, rax
0x18001a31c  jz      short loc_18001A2C9
0x18001a31e  lea     edx, [r13+0Eh]; unsigned __int16
0x18001a322  mov     [rdi+1Ch], esi
0x18001a325  mov     r9, rbp; struct _devicemodeW *
0x18001a328  mov     [rdi+18h], ebx
0x18001a32b  mov     r8, rax; unsigned __int16 *
0x18001a32e  mov     rcx, r14; this
0x18001a331  call    ?DeviceCapabilitiesWrapper@CPrinterWrapper@NPrintTicketUtil@@AEAAHGPEAGPEBU_devicemodeW@@@Z; NPrintTicketUtil::CPrinterWrapper::DeviceCapabilitiesWrapper(ushort,ushort *,_devicemodeW const *)
0x18001a336  cmp     eax, r13d
0x18001a339  jnz     short loc_18001A354
0x18001a33b  call    cs:__imp_GetLastError
0x18001a341  mov     ebx, eax
0x18001a343  test    eax, eax
0x18001a345  jle     short loc_18001A350
0x18001a347  movzx   ebx, ax
0x18001a34a  or      ebx, 80070000h
0x18001a350  test    ebx, ebx
0x18001a352  js      short loc_18001A36F
0x18001a354  xor     edx, edx
0x18001a356  test    rdi, rdi
0x18001a359  jz      short loc_18001A367
0x18001a35b  mov     rdx, rdi
0x18001a35e  mov     [rsp+68h+var_48], 0
0x18001a367  mov     rcx, r15
0x18001a36a  call    ??4?$TAutoPtrCOM@V?$BufferEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@QEAAPEAV?$BufferEnumerator@K@NPrintTicketUtil@@PEAV23@@Z; NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::BufferEnumerator<ulong>>::operator=(NPrintTicketUtil::BufferEnumerator<ulong> *)
0x18001a36f  lea     rcx, [rsp+68h+var_48]
0x18001a374  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001a379  mov     eax, ebx
0x18001a37b  add     rsp, 30h
0x18001a37f  pop     r15
0x18001a381  pop     r14
0x18001a383  pop     r13
0x18001a385  pop     rdi
0x18001a386  pop     rsi
0x18001a387  pop     rbp
0x18001a388  pop     rbx
0x18001a389  retn
```
