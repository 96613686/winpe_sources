# CASFReader::NonDelegatingAddRef(void)

- ea: `0x18000b930`
- end: `0x18000b95d`
- name: `?NonDelegatingAddRef@CASFReader@@UEAAKXZ`
- size: `45`
- prototype: `unsigned int __fastcall(CASFReader *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000b930`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReader::NonDelegatingAddRef(CASFReader *this)
{
  __int64 v1; // rdx
  __int64 result; // rax
  unsigned int v3; // ecx

  v1 = *((_QWORD *)this + 60);
  if ( v1 )
    return (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v1 + 8LL))(*((_QWORD *)this + 60));
  result = 1;
  _InterlockedAdd((volatile signed __int32 *)this + 4, 1u);
  v3 = *((_DWORD *)this + 4);
  if ( v3 > 1 )
    return v3;
  return result;
}

```

## disassembly

```asm
0x18000b930  mov     rdx, [rcx+1E0h]
0x18000b937  test    rdx, rdx
0x18000b93a  jz      short loc_18000B94B
0x18000b93c  mov     rax, [rdx]
0x18000b93f  mov     rcx, rdx
0x18000b942  mov     rax, [rax+8]
0x18000b946  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000b94b  mov     eax, 1
0x18000b950  lock add [rcx+10h], eax
0x18000b954  mov     ecx, [rcx+10h]
0x18000b957  cmp     ecx, eax
0x18000b959  cmova   eax, ecx
0x18000b95c  retn
```
