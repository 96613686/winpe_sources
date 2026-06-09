# __fcloseall

- ea: `0x1003b9aa`
- end: `0x1003ba47`
- name: `__fcloseall`
- size: `157`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x10037257`

## callees

- `0x1002df32`
- `0x10034c80`
- `0x10034cc5`
- `0x10034e74`
- `0x10034fde`
- `0x1003b9aa`
- `0x1003cbc8`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1003ba07`
- `KERNEL32!DeleteCriticalSection` at `0x1003ba07`

## pseudocode

```c
int __cdecl _fcloseall()
{
  int v0; // edi
  int i; // esi
  int v2; // eax

  v0 = 0;
  _lock(1);
  for ( i = 3; i < _nstream; ++i )
  {
    v2 = *((_DWORD *)__piob + i);
    if ( v2 )
    {
      if ( (*(_BYTE *)(v2 + 12) & 0x83) != 0 && fclose(*((FILE **)__piob + i)) != -1 )
        ++v0;
      if ( i >= 20 )
      {
        DeleteCriticalSection((LPCRITICAL_SECTION)(*((_DWORD *)__piob + i) + 32));
        free(*((void **)__piob + i));
        *((_DWORD *)__piob + i) = 0;
      }
    }
  }
  _unlock(1);
  return v0;
}

```

## disassembly

```asm
0x1003b9aa  push    10h
0x1003b9ac  push    offset stru_1003D180
0x1003b9b1  call    __SEH_prolog4
0x1003b9b6  xor     edi, edi
0x1003b9b8  mov     [ebp+var_1C], edi
0x1003b9bb  push    1
0x1003b9bd  call    __lock
0x1003b9c2  pop     ecx
0x1003b9c3  and     [ebp+ms_exc.registration.TryLevel], edi
0x1003b9c6  push    3
0x1003b9c8  pop     esi
0x1003b9c9  mov     [ebp+var_20], esi
0x1003b9cc  cmp     esi, __nstream
0x1003b9d2  jge     short loc_1003BA27
0x1003b9d4  mov     eax, ___piob
0x1003b9d9  mov     eax, [eax+esi*4]
0x1003b9dc  test    eax, eax
0x1003b9de  jz      short loc_1003BA24
0x1003b9e0  test    byte ptr [eax+0Ch], 83h
0x1003b9e4  jz      short loc_1003B9F6
0x1003b9e6  push    eax; Stream
0x1003b9e7  call    _fclose
0x1003b9ec  pop     ecx
0x1003b9ed  cmp     eax, 0FFFFFFFFh
0x1003b9f0  jz      short loc_1003B9F6
0x1003b9f2  inc     edi
0x1003b9f3  mov     [ebp+var_1C], edi
0x1003b9f6  cmp     esi, 14h
0x1003b9f9  jl      short loc_1003BA24
0x1003b9fb  mov     eax, ___piob
0x1003ba00  mov     eax, [eax+esi*4]
0x1003ba03  add     eax, 20h ; ' '
0x1003ba06  push    eax; lpCriticalSection
0x1003ba07  call    ds:__imp__DeleteCriticalSection@4
0x1003ba0d  mov     eax, ___piob
0x1003ba12  push    dword ptr [eax+esi*4]; Block
0x1003ba15  call    _free
0x1003ba1a  pop     ecx
0x1003ba1b  mov     eax, ___piob
0x1003ba20  and     dword ptr [eax+esi*4], 0
0x1003ba24  inc     esi
0x1003ba25  jmp     short loc_1003B9C9
0x1003ba27  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1003ba2e  call    loc_1003BA3E
0x1003ba33  mov     eax, edi
0x1003ba35  call    __SEH_epilog4
0x1003ba3a  retn
0x1003ba3b  mov     edi, [ebp+var_1C]
0x1003ba3e  push    1
0x1003ba40  call    __unlock
0x1003ba45  pop     ecx
0x1003ba46  retn
```
