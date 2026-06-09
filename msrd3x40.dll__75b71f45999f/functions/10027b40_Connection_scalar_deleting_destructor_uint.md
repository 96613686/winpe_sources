# Connection::`scalar deleting destructor'(uint)

- ea: `0x10027b40`
- end: `0x10027be2`
- name: `??_GConnection@@QAEPAXI@Z`
- size: `162`
- prototype: `void *__thiscall(Connection *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x100277d0`
- `0x10027bf0`

## callees

- `0x1000eb60`
- `0x10027b40`
- `0x10044170`
- `0x1005e74d`
- `0x1005e7e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10027baa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10027baa`

## pseudocode

```c
void ***__thiscall Connection::`scalar deleting destructor'(void ***this, unsigned int a2)
{
  void *v3; // esi
  void **v4; // ebx

  while ( this[2] )
  {
    v3 = **this;
    if ( v3 )
    {
      Session::~Session((Session *)**this);
      operator delete(v3, 0xD8u);
    }
  }
  v4 = this[6];
  if ( v4 && !_InterlockedExchangeAdd((volatile signed __int32 *)v4 + 18, 0xFFFFFFFF) )
    (*(void (__thiscall **)(void **, int))*v4)(v4, 1);
  if ( this[27] )
    operator delete[](this[27]);
  DeleteCriticalSection((LPCRITICAL_SECTION)(this + 7));
  if ( this[3] )
    operator delete[](this[3]);
  if ( *this )
    operator delete[](*this);
  operator delete(this, 0x74u);
  return this;
}

```

## disassembly

```asm
0x10027b40  mov     edi, edi
0x10027b42  push    ebx
0x10027b43  push    esi
0x10027b44  push    edi; unsigned int
0x10027b45  mov     edi, ecx
0x10027b47  cmp     dword ptr [edi+8], 0
0x10027b4b  jbe     short loc_10027B73
0x10027b4d  nop     dword ptr [eax]
0x10027b50  mov     eax, [edi]
0x10027b52  mov     esi, [eax]
0x10027b54  test    esi, esi
0x10027b56  jz      short loc_10027B6D
0x10027b58  mov     ecx, esi; this
0x10027b5a  call    ??1Session@@QAE@XZ; Session::~Session(void)
0x10027b5f  push    0D8h; unsigned int
0x10027b64  push    esi; Block
0x10027b65  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x10027b6a  add     esp, 8
0x10027b6d  cmp     dword ptr [edi+8], 0
0x10027b71  ja      short loc_10027B50
0x10027b73  mov     ebx, [edi+18h]
0x10027b76  test    ebx, ebx
0x10027b78  jz      short loc_10027B96
0x10027b7a  or      eax, 0FFFFFFFFh
0x10027b7d  lock xadd [ebx+48h], eax
0x10027b82  jnz     short loc_10027B96
0x10027b84  mov     eax, [ebx]
0x10027b86  push    1; void *
0x10027b88  mov     esi, [eax]
0x10027b8a  mov     ecx, esi
0x10027b8c  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10027b92  mov     ecx, ebx
0x10027b94  call    esi
0x10027b96  mov     eax, [edi+6Ch]
0x10027b99  test    eax, eax
0x10027b9b  jz      short loc_10027BA6
0x10027b9d  push    eax; Block
0x10027b9e  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10027ba3  add     esp, 4
0x10027ba6  lea     eax, [edi+1Ch]
0x10027ba9  push    eax; lpCriticalSection
0x10027baa  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x10027bb0  mov     eax, [edi+0Ch]
0x10027bb3  test    eax, eax
0x10027bb5  jz      short loc_10027BC0
0x10027bb7  push    eax; Block
0x10027bb8  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10027bbd  add     esp, 4
0x10027bc0  mov     eax, [edi]
0x10027bc2  test    eax, eax
0x10027bc4  jz      short loc_10027BCF
0x10027bc6  push    eax; Block
0x10027bc7  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10027bcc  add     esp, 4
0x10027bcf  push    74h ; 't'; unsigned int
0x10027bd1  push    edi; Block
0x10027bd2  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x10027bd7  add     esp, 8
0x10027bda  mov     eax, edi
0x10027bdc  pop     edi
0x10027bdd  pop     esi
0x10027bde  pop     ebx
0x10027bdf  retn    4
```
