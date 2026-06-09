# GetRegistryValueToWrite(IIS_SETUP_REGISTRY_ENTRY *,BUFFER *,ulong *)

- ea: `0x18000224c`
- end: `0x180002328`
- name: `?GetRegistryValueToWrite@@YAJPEAUIIS_SETUP_REGISTRY_ENTRY@@PEAVBUFFER@@PEAK@Z`
- size: `220`
- prototype: `__int64 __fastcall(struct IIS_SETUP_REGISTRY_ENTRY *, struct BUFFER *this, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180002d14`

## callees

- `0x180001afc`
- `0x180001b90`
- `0x180001d7c`
- `0x18000224c`
- `0x180002330`
- `0x180003024`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800022b8`
- `msvcrt!_wtoi` at `0x1800022b8`
- `KERNEL32!GetLastError` at `0x18000229b`
- `KERNEL32!GetLastError` at `0x18000229b`

## pseudocode

```c
__int64 __fastcall GetRegistryValueToWrite(struct IIS_SETUP_REGISTRY_ENTRY *a1, void **this, unsigned int *a3)
{
  unsigned int v6; // eax
  signed int LastError; // eax
  unsigned int v8; // ebx
  int v9; // eax
  int *v10; // rcx

  if ( !a1 || !this || !a3 )
    return (unsigned int)-2147024809;
  v6 = ConvertStringToType(*((wchar_t **)a1 + 4));
  if ( v6 != 4 )
  {
    if ( v6 - 1 <= 1 )
    {
      return (unsigned int)GetStringRegistryValueToWrite(a1, this, a3);
    }
    else if ( v6 == 7 )
    {
      return (unsigned int)GetMultiSzRegistryValueToWrite(a1, this, a3);
    }
    else
    {
      if ( v6 != 3 )
        return (unsigned int)-2147024883;
      return (unsigned int)GetBinaryRegistryValueToWrite(a1, this, a3);
    }
  }
  if ( *((_DWORD *)this + 10) >= 4u || BUFFER::ReallocStorage((BUFFER *)this, 4u) )
  {
    v8 = 0;
    v9 = _wtoi(*((const wchar_t **)a1 + 5));
    v10 = (int *)this[4];
    *a3 = 4;
    *v10 = v9;
  }
  else
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v8;
}

```

## disassembly

```asm
0x18000224c  push    rbx
0x18000224e  push    rsi
0x18000224f  push    rdi
0x180002250  push    r14
0x180002252  sub     rsp, 28h
0x180002256  mov     r14, r8
0x180002259  mov     rdi, rdx
0x18000225c  mov     rsi, rcx
0x18000225f  test    rcx, rcx
0x180002262  jz      loc_180002317
0x180002268  test    rdx, rdx
0x18000226b  jz      loc_180002317
0x180002271  test    r8, r8
0x180002274  jz      loc_180002317
0x18000227a  mov     rcx, [rcx+20h]; String1
0x18000227e  call    ?ConvertStringToType@@YAKPEAG@Z; ConvertStringToType(ushort *)
0x180002283  mov     edx, eax; unsigned int
0x180002285  cmp     eax, 4
0x180002288  jnz     short loc_1800022CD
0x18000228a  cmp     [rdi+28h], eax
0x18000228d  jnb     short loc_1800022B2
0x18000228f  mov     rcx, rdi; this
0x180002292  call    ?ReallocStorage@BUFFER@@AEAA_NK@Z; BUFFER::ReallocStorage(ulong)
0x180002297  test    al, al
0x180002299  jnz     short loc_1800022B2
0x18000229b  call    cs:__imp_GetLastError
0x1800022a1  mov     ebx, eax
0x1800022a3  test    eax, eax
0x1800022a5  jle     short loc_18000231C
0x1800022a7  movzx   ebx, ax
0x1800022aa  or      ebx, 80070000h
0x1800022b0  jmp     short loc_18000231C
0x1800022b2  mov     rcx, [rsi+28h]; String
0x1800022b6  xor     ebx, ebx
0x1800022b8  call    cs:__imp__wtoi
0x1800022be  mov     rcx, [rdi+20h]
0x1800022c2  mov     dword ptr [r14], 4
0x1800022c9  mov     [rcx], eax
0x1800022cb  jmp     short loc_18000231C
0x1800022cd  dec     eax
0x1800022cf  cmp     eax, 1
0x1800022d2  jbe     short loc_180002305
0x1800022d4  cmp     edx, 7
0x1800022d7  jnz     short loc_1800022E9
0x1800022d9  mov     r8, r14; unsigned int *
0x1800022dc  mov     rdx, rdi; this
0x1800022df  mov     rcx, rsi; struct IIS_SETUP_REGISTRY_ENTRY *
0x1800022e2  call    ?GetMultiSzRegistryValueToWrite@@YAJPEAUIIS_SETUP_REGISTRY_ENTRY@@PEAVBUFFER@@PEAK@Z; GetMultiSzRegistryValueToWrite(IIS_SETUP_REGISTRY_ENTRY *,BUFFER *,ulong *)
0x1800022e7  jmp     short loc_180002313
0x1800022e9  cmp     edx, 3
0x1800022ec  jnz     short loc_1800022FE
0x1800022ee  mov     r8, r14; unsigned int *
0x1800022f1  mov     rdx, rdi; struct BUFFER *
0x1800022f4  mov     rcx, rsi; struct IIS_SETUP_REGISTRY_ENTRY *
0x1800022f7  call    ?GetBinaryRegistryValueToWrite@@YAJPEAUIIS_SETUP_REGISTRY_ENTRY@@PEAVBUFFER@@PEAK@Z; GetBinaryRegistryValueToWrite(IIS_SETUP_REGISTRY_ENTRY *,BUFFER *,ulong *)
0x1800022fc  jmp     short loc_180002313
0x1800022fe  mov     ebx, 8007000Dh
0x180002303  jmp     short loc_18000231C
0x180002305  mov     r8, r14; unsigned int *
0x180002308  mov     rdx, rdi; struct BUFFER *
0x18000230b  mov     rcx, rsi; struct IIS_SETUP_REGISTRY_ENTRY *
0x18000230e  call    ?GetStringRegistryValueToWrite@@YAJPEAUIIS_SETUP_REGISTRY_ENTRY@@PEAVBUFFER@@PEAK@Z; GetStringRegistryValueToWrite(IIS_SETUP_REGISTRY_ENTRY *,BUFFER *,ulong *)
0x180002313  mov     ebx, eax
0x180002315  jmp     short loc_18000231C
0x180002317  mov     ebx, 80070057h
0x18000231c  mov     eax, ebx
0x18000231e  add     rsp, 28h
0x180002322  pop     r14
0x180002324  pop     rdi
0x180002325  pop     rsi
0x180002326  pop     rbx
0x180002327  retn
```
