# CIsoBurn::StartBurn(ushort const *,ushort const *,int,int,IIsoBurnProgress *)

- ea: `0x140008890`
- end: `0x140008999`
- name: `?StartBurn@CIsoBurn@@UEAAJPEBG0HHPEAUIIsoBurnProgress@@@Z`
- size: `265`
- prototype: `int(CIsoBurn *__hidden this, const unsigned __int16 *, const unsigned __int16 *, int, int, struct IIsoBurnProgress *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14000469c`
- `0x140008890`
- `0x140010010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140008970`
- `KERNEL32!GetLastError` at `0x140008970`
- `KERNEL32!CloseHandle` at `0x1400088ff`
- `KERNEL32!CloseHandle` at `0x1400088ff`
- `KERNEL32!CreateThread` at `0x140008961`
- `KERNEL32!CreateThread` at `0x140008961`

## pseudocode

```c
__int64 __fastcall CIsoBurn::StartBurn(
        unsigned __int16 **this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        int a5,
        struct IIsoBurnProgress *a6)
{
  int v9; // ebx
  unsigned __int16 *v10; // rcx
  unsigned __int16 *v11; // rcx
  unsigned __int16 *Thread; // rax
  signed int LastError; // eax

  if ( !a2 || !a3 || !a6 )
    return 2147942487LL;
  v9 = CoAllocString(a2, this + 8);
  if ( v9 >= 0 )
  {
    v9 = CoAllocString(a3, this + 9);
    if ( v9 >= 0 )
    {
      v10 = this[11];
      if ( v10 )
        CloseHandle(v10);
      *((_DWORD *)this + 21) = a5;
      *((_DWORD *)this + 20) = a4;
      if ( this[12] != (unsigned __int16 *)a6 )
      {
        (*(void (__fastcall **)(struct IIsoBurnProgress *))(*(_QWORD *)a6 + 8LL))(a6);
        v11 = this[12];
        if ( v11 )
          (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v11 + 16LL))(v11);
        this[12] = (unsigned __int16 *)a6;
      }
      Thread = (unsigned __int16 *)CreateThread(0, 0, s_BurnThreadProc, this - 7, 0, 0);
      this[11] = Thread;
      if ( !Thread )
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140008890  push    rbx
0x140008892  push    rbp
0x140008893  push    rsi
0x140008894  push    rdi
0x140008895  push    r14
0x140008897  sub     rsp, 30h
0x14000889b  mov     r14d, r9d
0x14000889e  mov     rbp, r8
0x1400088a1  mov     rax, rdx
0x1400088a4  mov     rdi, rcx
0x1400088a7  test    rdx, rdx
0x1400088aa  jz      loc_140008989
0x1400088b0  test    r8, r8
0x1400088b3  jz      loc_140008989
0x1400088b9  mov     rsi, [rsp+58h+arg_28]
0x1400088c1  test    rsi, rsi
0x1400088c4  jz      loc_140008989
0x1400088ca  lea     rdx, [rcx+40h]; unsigned __int16 **
0x1400088ce  mov     rcx, rax; unsigned __int16 *
0x1400088d1  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x1400088d6  mov     ebx, eax
0x1400088d8  test    eax, eax
0x1400088da  js      loc_140008985
0x1400088e0  lea     rdx, [rdi+48h]; unsigned __int16 **
0x1400088e4  mov     rcx, rbp; unsigned __int16 *
0x1400088e7  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x1400088ec  mov     ebx, eax
0x1400088ee  test    eax, eax
0x1400088f0  js      loc_140008985
0x1400088f6  mov     rcx, [rdi+58h]; hObject
0x1400088fa  test    rcx, rcx
0x1400088fd  jz      short loc_140008905
0x1400088ff  call    cs:__imp_CloseHandle
0x140008905  mov     eax, [rsp+58h+arg_20]
0x14000890c  mov     [rdi+54h], eax
0x14000890f  mov     [rdi+50h], r14d
0x140008913  cmp     [rdi+60h], rsi
0x140008917  jz      short loc_140008941
0x140008919  mov     rax, [rsi]
0x14000891c  mov     rcx, rsi
0x14000891f  mov     rax, [rax+8]
0x140008923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008928  mov     rcx, [rdi+60h]
0x14000892c  test    rcx, rcx
0x14000892f  jz      short loc_14000893D
0x140008931  mov     rax, [rcx]
0x140008934  mov     rax, [rax+10h]
0x140008938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000893d  mov     [rdi+60h], rsi
0x140008941  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x14000894a  lea     r9, [rdi-38h]; lpParameter
0x14000894e  lea     r8, ?s_BurnThreadProc@@YAKPEAX@Z; lpStartAddress
0x140008955  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x14000895d  xor     edx, edx; dwStackSize
0x14000895f  xor     ecx, ecx; lpThreadAttributes
0x140008961  call    cs:__imp_CreateThread
0x140008967  mov     [rdi+58h], rax
0x14000896b  test    rax, rax
0x14000896e  jnz     short loc_140008985
0x140008970  call    cs:__imp_GetLastError
0x140008976  mov     ebx, eax
0x140008978  test    eax, eax
0x14000897a  jle     short loc_140008985
0x14000897c  movzx   ebx, ax
0x14000897f  or      ebx, 80070000h
0x140008985  mov     eax, ebx
0x140008987  jmp     short loc_14000898E
0x140008989  mov     eax, 80070057h
0x14000898e  add     rsp, 30h
0x140008992  pop     r14
0x140008994  pop     rdi
0x140008995  pop     rsi
0x140008996  pop     rbp
0x140008997  pop     rbx
0x140008998  retn
```
