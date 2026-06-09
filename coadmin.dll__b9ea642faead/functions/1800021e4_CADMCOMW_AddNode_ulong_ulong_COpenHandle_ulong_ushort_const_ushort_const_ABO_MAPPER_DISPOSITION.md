# CADMCOMW::AddNode(ulong,ulong,COpenHandle *,ulong *,ushort const *,ushort const * *,ABO_MAPPER_DISPOSITION)

- ea: `0x1800021e4`
- end: `0x18000233d`
- name: `?AddNode@CADMCOMW@@QEAAJKKPEAVCOpenHandle@@PEAKPEBGPEAPEBGW4ABO_MAPPER_DISPOSITION@@@Z`
- size: `345`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180007f40`

## callees

- `0x180001064`
- `0x1800010a4`
- `0x1800021e4`
- `0x18000b72c`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180002206`
- `KERNEL32!LocalAlloc` at `0x180002206`
- `KERNEL32!LocalFree` at `0x180002274`
- `KERNEL32!LocalFree` at `0x180002282`
- `KERNEL32!LocalFree` at `0x18000230b`
- `KERNEL32!LocalFree` at `0x18000231e`
- `KERNEL32!LocalFree` at `0x180002274`
- `KERNEL32!LocalFree` at `0x180002282`
- `KERNEL32!LocalFree` at `0x18000230b`
- `KERNEL32!LocalFree` at `0x18000231e`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800022f6`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800022f6`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000224f`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000224f`

## pseudocode

```c
__int64 __fastcall CADMCOMW::AddNode(
        __int64 a1,
        int a2,
        int a3,
        const unsigned __int16 **a4,
        _DWORD *a5,
        unsigned __int16 *a6,
        _QWORD *a7,
        int a8)
{
  _QWORD *v12; // rdi
  COpenHandle *v13; // rax
  COpenHandle *v14; // rbx
  int v15; // esi
  int v16; // ecx
  unsigned int v17; // ecx
  __int64 v18; // rcx

  v12 = LocalAlloc(0, 0x20u);
  v13 = (COpenHandle *)operator new(0x18u);
  v14 = v13;
  if ( v13 )
  {
    *(_QWORD *)v13 = 0;
    *((_DWORD *)v13 + 4) = 0;
  }
  else
  {
    v14 = 0;
  }
  if ( v12 && v14 )
  {
    CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)(a1 + 800));
    v15 = COpenHandle::Init(v14, *(_DWORD *)(a1 + 40), a6, *a4);
    if ( v15 >= 0 )
    {
      v12[3] = v14;
      *((_DWORD *)v12 + 2) = *(_DWORD *)(a1 + 40);
      v16 = *(_DWORD *)(a1 + 40);
      *(_DWORD *)(a1 + 40) = v16 + 1;
      *a5 = v16;
      v17 = *((_DWORD *)v12 + 2);
      *((_DWORD *)v12 + 3) = a2;
      *((_DWORD *)v12 + 4) = a3;
      v18 = v17 % 5;
      *v12 = *(_QWORD *)(a1 + 8 * v18 + 48);
      *(_QWORD *)(a1 + 8 * v18 + 48) = v12;
      if ( a7 )
        *a7 = *(_QWORD *)v14;
      *((_DWORD *)v14 + 4) = a8;
    }
    else
    {
      LocalFree(v12);
      if ( *(_QWORD *)v14 )
        LocalFree(*(HLOCAL *)v14);
      operator delete(v14);
    }
    CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)(a1 + 800));
  }
  else
  {
    v15 = -2147024882;
    if ( v12 )
      LocalFree(v12);
    if ( v14 )
    {
      if ( *(_QWORD *)v14 )
        LocalFree(*(HLOCAL *)v14);
      operator delete(v14);
    }
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800021e4  push    rbx
0x1800021e6  push    rbp
0x1800021e7  push    rsi
0x1800021e8  push    rdi
0x1800021e9  push    r12
0x1800021eb  push    r14
0x1800021ed  push    r15
0x1800021ef  sub     rsp, 20h
0x1800021f3  mov     r12d, edx
0x1800021f6  mov     rbp, rcx
0x1800021f9  mov     edx, 20h ; ' '; uBytes
0x1800021fe  xor     ecx, ecx; uFlags
0x180002200  mov     rsi, r9
0x180002203  mov     r15d, r8d
0x180002206  call    cs:__imp_LocalAlloc
0x18000220c  mov     ecx, 18h; Size
0x180002211  mov     rdi, rax
0x180002214  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002219  mov     rbx, rax
0x18000221c  test    rax, rax
0x18000221f  jz      short loc_180002231
0x180002221  mov     qword ptr [rax], 0
0x180002228  mov     dword ptr [rax+10h], 0
0x18000222f  jmp     short loc_180002233
0x180002231  xor     ebx, ebx
0x180002233  test    rdi, rdi
0x180002236  jz      loc_1800022FE
0x18000223c  test    rbx, rbx
0x18000223f  jz      loc_1800022FE
0x180002245  lea     r14, [rbp+320h]
0x18000224c  mov     rcx, r14
0x18000224f  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180002255  mov     r9, [rsi]; unsigned __int16 *
0x180002258  mov     rcx, rbx; this
0x18000225b  mov     r8, [rsp+58h+arg_28]; unsigned __int16 *
0x180002263  mov     edx, [rbp+28h]; unsigned int
0x180002266  call    ?Init@COpenHandle@@QEAAJKPEBG0@Z; COpenHandle::Init(ulong,ushort const *,ushort const *)
0x18000226b  mov     esi, eax
0x18000226d  test    eax, eax
0x18000226f  jns     short loc_180002292
0x180002271  mov     rcx, rdi; hMem
0x180002274  call    cs:__imp_LocalFree
0x18000227a  mov     rcx, [rbx]; hMem
0x18000227d  test    rcx, rcx
0x180002280  jz      short loc_180002288
0x180002282  call    cs:__imp_LocalFree
0x180002288  mov     rcx, rbx; Block
0x18000228b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002290  jmp     short loc_1800022F3
0x180002292  mov     [rdi+18h], rbx
0x180002296  mov     eax, [rbp+28h]
0x180002299  mov     [rdi+8], eax
0x18000229c  mov     ecx, [rbp+28h]
0x18000229f  lea     eax, [rcx+1]
0x1800022a2  mov     [rbp+28h], eax
0x1800022a5  mov     rax, [rsp+58h+arg_20]
0x1800022ad  mov     [rax], ecx
0x1800022af  mov     eax, 0CCCCCCCDh
0x1800022b4  mov     ecx, [rdi+8]
0x1800022b7  mul     ecx
0x1800022b9  mov     [rdi+0Ch], r12d
0x1800022bd  shr     edx, 2
0x1800022c0  mov     [rdi+10h], r15d
0x1800022c4  lea     eax, [rdx+rdx*4]
0x1800022c7  sub     ecx, eax
0x1800022c9  mov     rax, [rbp+rcx*8+30h]
0x1800022ce  mov     [rdi], rax
0x1800022d1  mov     [rbp+rcx*8+30h], rdi
0x1800022d6  mov     rcx, [rsp+58h+arg_30]
0x1800022de  test    rcx, rcx
0x1800022e1  jz      short loc_1800022E9
0x1800022e3  mov     rax, [rbx]
0x1800022e6  mov     [rcx], rax
0x1800022e9  mov     eax, [rsp+58h+arg_38]
0x1800022f0  mov     [rbx+10h], eax
0x1800022f3  mov     rcx, r14
0x1800022f6  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x1800022fc  jmp     short loc_18000232C
0x1800022fe  mov     esi, 8007000Eh
0x180002303  test    rdi, rdi
0x180002306  jz      short loc_180002311
0x180002308  mov     rcx, rdi; hMem
0x18000230b  call    cs:__imp_LocalFree
0x180002311  test    rbx, rbx
0x180002314  jz      short loc_18000232C
0x180002316  mov     rcx, [rbx]; hMem
0x180002319  test    rcx, rcx
0x18000231c  jz      short loc_180002324
0x18000231e  call    cs:__imp_LocalFree
0x180002324  mov     rcx, rbx; Block
0x180002327  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000232c  mov     eax, esi
0x18000232e  add     rsp, 20h
0x180002332  pop     r15
0x180002334  pop     r14
0x180002336  pop     r12
0x180002338  pop     rdi
0x180002339  pop     rsi
0x18000233a  pop     rbp
0x18000233b  pop     rbx
0x18000233c  retn
```
