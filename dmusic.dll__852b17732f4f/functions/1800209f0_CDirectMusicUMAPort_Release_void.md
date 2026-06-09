# CDirectMusicUMAPort::Release(void)

- ea: `0x1800209f0`
- end: `0x180020a51`
- name: `?Release@CDirectMusicUMAPort@@UEAAKXZ`
- size: `97`
- prototype: `unsigned int __fastcall(CDirectMusicUMAPort *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180020a60`
- `0x180020a80`
- `0x180020aa0`
- `0x180020ac0`
- `0x180020ae0`

## callees

- `0x1800012c4`
- `0x18001d7c8`
- `0x1800209f0`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall CDirectMusicUMAPort::Release(CDirectMusicUMAPort *this)
{
  __int64 result; // rax
  __int64 v3; // rcx

  result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)this + 104);
  if ( !(_DWORD)result )
  {
    v3 = *((_QWORD *)this + 55);
    if ( v3 )
      (*(void (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v3 + 24LL))(
        v3,
        ((unsigned __int64)this + 384) & -(__int64)(this != 0));
    CDirectMusicUMAPort::~CDirectMusicUMAPort((struct _RTL_CRITICAL_SECTION *)this);
    operator delete(this);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800209f0  push    rbx
0x1800209f2  sub     rsp, 20h
0x1800209f6  mov     rbx, rcx
0x1800209f9  or      eax, 0FFFFFFFFh
0x1800209fc  lock xadd [rcx+1A0h], eax
0x180020a04  sub     eax, 1
0x180020a07  jnz     short loc_180020A4B
0x180020a09  mov     rcx, [rcx+1B8h]
0x180020a10  test    rcx, rcx
0x180020a13  jz      short loc_180020A34
0x180020a15  mov     r9, [rcx]
0x180020a18  lea     r8, [rbx+180h]
0x180020a1f  mov     rax, rbx
0x180020a22  neg     rax
0x180020a25  mov     rax, [r9+18h]
0x180020a29  sbb     rdx, rdx
0x180020a2c  and     rdx, r8
0x180020a2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a34  mov     rcx, rbx; this
0x180020a37  call    ??1CDirectMusicUMAPort@@UEAA@XZ; CDirectMusicUMAPort::~CDirectMusicUMAPort(void)
0x180020a3c  mov     edx, 8B10h; unsigned __int64
0x180020a41  mov     rcx, rbx; void *
0x180020a44  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020a49  xor     eax, eax
0x180020a4b  add     rsp, 20h
0x180020a4f  pop     rbx
0x180020a50  retn
```
