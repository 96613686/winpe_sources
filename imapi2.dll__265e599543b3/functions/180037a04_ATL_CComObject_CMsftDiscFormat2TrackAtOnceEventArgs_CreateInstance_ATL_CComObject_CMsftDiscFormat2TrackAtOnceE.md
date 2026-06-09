# ATL::CComObject<CMsftDiscFormat2TrackAtOnceEventArgs>::CreateInstance(ATL::CComObject<CMsftDiscFormat2TrackAtOnceEventArgs> * *)

- ea: `0x180037a04`
- end: `0x180037b1b`
- name: `?CreateInstance@?$CComObject@VCMsftDiscFormat2TrackAtOnceEventArgs@@@ATL@@SAJPEAPEAV12@@Z`
- size: `279`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800389f0`
- `0x18003bbe0`

## callees

- `0x180005fa4`
- `0x18000fdd4`
- `0x180037a04`
- `0x18004a010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180037aa5`
- `KERNEL32!GetTickCount` at `0x180037aa5`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMsftDiscFormat2TrackAtOnceEventArgs>::CreateInstance(_QWORD *a1)
{
  char *v3; // rax
  _DWORD *v4; // rbx
  DWORD TickCount; // eax
  struct ATL::CAtlModule *v6; // rcx
  int v7; // eax
  int v8; // ecx
  unsigned int v9; // edi

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v3 = (char *)operator new(0x78u);
  v4 = v3;
  if ( v3 )
  {
    *((_DWORD *)v3 + 2) = 0;
    *((_OWORD *)v3 + 1) = 0;
    *((_OWORD *)v3 + 2) = 0;
    *((_QWORD *)v3 + 6) = 0;
    v3[56] = 0;
    *(_QWORD *)v3 = &CMsftDiscFormat2TrackAtOnceEventArgs::`vftable';
    *((_DWORD *)v3 + 18) = -1;
    *((_DWORD *)v3 + 21) = -1;
    *((_DWORD *)v3 + 23) = -1;
    *((_DWORD *)v3 + 25) = -1;
    *((_DWORD *)v3 + 26) = -1;
    *((_QWORD *)v3 + 8) = 0;
    *(_QWORD *)(v3 + 76) = 0;
    *((_DWORD *)v3 + 22) = 0;
    *((_DWORD *)v3 + 24) = 0;
    *((_DWORD *)v3 + 28) = 1;
    *((_DWORD *)v3 + 29) = 1;
    TickCount = GetTickCount();
    v6 = ATL::_pAtlModule;
    v4[27] = TickCount;
    *(_QWORD *)v4 = &ATL::CComObject<CMsftDiscFormat2TrackAtOnceEventArgs>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v6 + 8LL))(v6);
    v7 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v4 + 4));
    v8 = 0;
    if ( v7 < 0 )
      v8 = v7;
    v9 = 0;
    if ( v8 < 0 )
      v9 = v8;
    if ( !v9 )
      goto LABEL_12;
    (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v4 + 160LL))(v4, 1);
  }
  else
  {
    v9 = -2147024882;
  }
  v4 = 0;
LABEL_12:
  *a1 = v4;
  return v9;
}

```

## disassembly

```asm
0x180037a04  mov     [rsp+arg_0], rbx
0x180037a09  mov     [rsp+arg_8], rsi
0x180037a0e  push    rdi
0x180037a0f  sub     rsp, 20h
0x180037a13  mov     rsi, rcx
0x180037a16  test    rcx, rcx
0x180037a19  jnz     short loc_180037A25
0x180037a1b  mov     eax, 80004003h
0x180037a20  jmp     loc_180037B0B
0x180037a25  mov     qword ptr [rcx], 0
0x180037a2c  mov     ecx, 78h ; 'x'; Size
0x180037a31  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180037a36  mov     rbx, rax
0x180037a39  test    rax, rax
0x180037a3c  jz      loc_180037AFF
0x180037a42  mov     dword ptr [rax+8], 0
0x180037a49  xorps   xmm0, xmm0
0x180037a4c  movups  xmmword ptr [rbx+10h], xmm0
0x180037a50  xor     eax, eax
0x180037a52  movups  xmmword ptr [rbx+20h], xmm0
0x180037a56  mov     [rbx+30h], rax
0x180037a5a  mov     [rbx+38h], al
0x180037a5d  lea     rax, ??_7CMsftDiscFormat2TrackAtOnceEventArgs@@6B@; const CMsftDiscFormat2TrackAtOnceEventArgs::`vftable'
0x180037a64  mov     [rbx], rax
0x180037a67  or      eax, 0FFFFFFFFh
0x180037a6a  mov     [rbx+48h], eax
0x180037a6d  mov     [rbx+54h], eax
0x180037a70  mov     [rbx+5Ch], eax
0x180037a73  mov     [rbx+64h], eax
0x180037a76  mov     [rbx+68h], eax
0x180037a79  mov     qword ptr [rbx+40h], 0
0x180037a81  mov     qword ptr [rbx+4Ch], 0
0x180037a89  mov     dword ptr [rbx+58h], 0
0x180037a90  mov     dword ptr [rbx+60h], 0
0x180037a97  mov     dword ptr [rbx+70h], 1
0x180037a9e  mov     dword ptr [rbx+74h], 1
0x180037aa5  call    cs:__imp_GetTickCount
0x180037aab  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180037ab2  mov     [rbx+6Ch], eax
0x180037ab5  lea     rax, ??_7?$CComObject@VCMsftDiscFormat2TrackAtOnceEventArgs@@@ATL@@6B@; const ATL::CComObject<CMsftDiscFormat2TrackAtOnceEventArgs>::`vftable'
0x180037abc  mov     [rbx], rax
0x180037abf  mov     rax, [rcx]
0x180037ac2  mov     rax, [rax+8]
0x180037ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037acb  lea     rcx, [rbx+10h]; this
0x180037acf  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180037ad4  xor     ecx, ecx
0x180037ad6  test    eax, eax
0x180037ad8  cmovs   ecx, eax
0x180037adb  xor     edi, edi
0x180037add  test    ecx, ecx
0x180037adf  cmovs   edi, ecx
0x180037ae2  test    edi, edi
0x180037ae4  jz      short loc_180037B06
0x180037ae6  mov     rax, [rbx]
0x180037ae9  mov     edx, 1
0x180037aee  mov     rcx, rbx
0x180037af1  mov     rax, [rax+0A0h]
0x180037af8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037afd  jmp     short loc_180037B04
0x180037aff  mov     edi, 8007000Eh
0x180037b04  xor     ebx, ebx
0x180037b06  mov     [rsi], rbx
0x180037b09  mov     eax, edi
0x180037b0b  mov     rbx, [rsp+28h+arg_0]
0x180037b10  mov     rsi, [rsp+28h+arg_8]
0x180037b15  add     rsp, 20h
0x180037b19  pop     rdi
0x180037b1a  retn
```
