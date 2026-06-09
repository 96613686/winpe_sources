# File::~File(void)

- ea: `0x10050d08`
- end: `0x10050d90`
- name: `??1File@@QAE@XZ`
- size: `136`
- prototype: `void __thiscall(File *__hidden this)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1004946a`
- `0x10052ede`
- `0x1005313d`
- `0x10054e93`

## callees

- `0x10050d08`
- `0x10050f9a`
- `0x10074b2c`
- `0x10122f60`
- `0x10123af8`
- `0x10123e98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10050d7c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10050d7c`

## pseudocode

```c
void __thiscall File::~File(File *this)
{
  _DWORD v2[8]; // [esp+8h] [ebp-20h] BYREF

  v2[0] = 1;
  File::Close(this, (struct Err *)v2);
  if ( *((_DWORD *)this + 1) )
    operator delete[](*((void **)this + 1));
  if ( *((_DWORD *)this + 2) )
    operator delete[](*((void **)this + 2));
  if ( (v2[0] & 0xFFFFFFFE) != 0 )
    Err::Delete((Err *)v2);
  v2[7] = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 1);
}

```

## disassembly

```asm
0x10050d08  mov     edi, edi
0x10050d0a  push    ebp
0x10050d0b  mov     ebp, esp
0x10050d0d  push    0FFFFFFFFh
0x10050d0f  push    offset ??1File@@QAE@XZ_SEH
0x10050d14  mov     eax, large fs:0
0x10050d1a  push    eax
0x10050d1b  sub     esp, 14h
0x10050d1e  push    esi
0x10050d1f  mov     eax, ___security_cookie
0x10050d24  xor     eax, ebp
0x10050d26  push    eax
0x10050d27  lea     eax, [ebp+var_C]
0x10050d2a  mov     large fs:0, eax
0x10050d30  mov     esi, ecx
0x10050d32  lea     eax, [ebp+var_20]
0x10050d35  mov     [ebp+var_20], 1
0x10050d3c  push    eax; struct Err *
0x10050d3d  call    ?Close@File@@QAEXAAVErr@@@Z; File::Close(Err &)
0x10050d42  cmp     dword ptr [esi+4], 0
0x10050d46  jz      short loc_10050D51
0x10050d48  push    dword ptr [esi+4]; Block
0x10050d4b  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10050d50  pop     ecx
0x10050d51  cmp     dword ptr [esi+8], 0
0x10050d55  jz      short loc_10050D60
0x10050d57  push    dword ptr [esi+8]; Block
0x10050d5a  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10050d5f  pop     ecx
0x10050d60  test    [ebp+var_20], 0FFFFFFFEh
0x10050d67  jz      short loc_10050D71
0x10050d69  lea     ecx, [ebp+var_20]; this
0x10050d6c  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x10050d71  lea     eax, [esi+18h]
0x10050d74  mov     [ebp+var_4], 0
0x10050d7b  push    eax; lpCriticalSection
0x10050d7c  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x10050d82  mov     ecx, [ebp+var_C]
0x10050d85  mov     large fs:0, ecx
0x10050d8c  pop     ecx
0x10050d8d  pop     esi
0x10050d8e  leave
0x10050d8f  retn
0x10123eb0  jmp     ds:__imp____std_terminate
0x101250b3  nop
0x101250b4  nop
0x101250b5  mov     edx, [esp-4+arg_4]
0x101250b9  lea     eax, [edx+0Ch]
0x101250bc  mov     ecx, [edx-1Ch]
0x101250bf  xor     ecx, eax; StackCookie
0x101250c1  call    @__security_check_cookie@4; __security_check_cookie(x)
0x101250c6  mov     eax, offset stru_101278CC
0x101250cb  jmp     ___CxxFrameHandler3
```
