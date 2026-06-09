# LANG_STRING::Terminate(void)

- ea: `0x18002a8f0`
- end: `0x18002a9d0`
- name: `?Terminate@LANG_STRING@@QEAAJXZ`
- size: `224`
- prototype: `__int64 __fastcall(LANG_STRING *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001eba0`

## callees

- `0x180018438`
- `0x18002a3d0`
- `0x18002a8f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002a9ab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002a9ab`

## pseudocode

```c
__int64 __fastcall LANG_STRING::Terminate(LANG_STRING *this, unsigned int a2)
{
  __int64 i; // rdi
  void *v4; // rcx
  unsigned int j; // esi
  _QWORD **v6; // rdi
  _QWORD *v7; // rax
  _QWORD *v8; // rcx
  __int64 result; // rax

  if ( *((_QWORD *)this + 4) )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 10); i = (unsigned int)(i + 1) )
    {
      v4 = *(void **)(*((_QWORD *)this + 4) + 8 * i);
      if ( v4 )
      {
        operator delete(v4);
        *(_QWORD *)(*((_QWORD *)this + 4) + 8 * i) = 0;
      }
    }
    operator delete(*((void **)this + 4));
    *((_QWORD *)this + 4) = 0;
  }
  if ( *((_QWORD *)this + 3) )
  {
    for ( j = 0; j < *((_DWORD *)this + 4); ++j )
    {
      v6 = (_QWORD **)(*((_QWORD *)this + 3) + 16LL * j);
      while ( 1 )
      {
        v7 = *v6;
        if ( *v6 == v6 )
          break;
        if ( (_QWORD **)v7[1] != v6 || (v8 = (_QWORD *)*v7, *(_QWORD **)(*v7 + 8LL) != v7) )
          __fastfail(3u);
        *v6 = v8;
        v8[1] = v6;
        if ( v7 != (_QWORD *)1104 )
          LOCALIZED_STRING::`scalar deleting destructor'((LOCALIZED_STRING *)(v7 - 138), a2);
      }
    }
    operator delete(*((void **)this + 3));
    *((_QWORD *)this + 3) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  result = 0;
  *(_DWORD *)this = 0;
  return result;
}

```

## disassembly

```asm
0x18002a8f0  mov     [rsp+arg_0], rbx
0x18002a8f5  mov     [rsp+arg_8], rsi
0x18002a8fa  push    rdi
0x18002a8fb  sub     rsp, 20h
0x18002a8ff  cmp     qword ptr [rcx+20h], 0
0x18002a904  mov     rbx, rcx
0x18002a907  jz      short loc_18002A946
0x18002a909  xor     edi, edi
0x18002a90b  cmp     [rcx+28h], edi
0x18002a90e  jbe     short loc_18002A935
0x18002a910  mov     rax, [rbx+20h]
0x18002a914  mov     rcx, [rax+rdi*8]; Block
0x18002a918  test    rcx, rcx
0x18002a91b  jz      short loc_18002A92E
0x18002a91d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002a922  mov     rax, [rbx+20h]
0x18002a926  mov     qword ptr [rax+rdi*8], 0
0x18002a92e  inc     edi
0x18002a930  cmp     edi, [rbx+28h]
0x18002a933  jb      short loc_18002A910
0x18002a935  mov     rcx, [rbx+20h]; Block
0x18002a939  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002a93e  mov     qword ptr [rbx+20h], 0
0x18002a946  cmp     qword ptr [rbx+18h], 0
0x18002a94b  jz      short loc_18002A9A7
0x18002a94d  xor     esi, esi
0x18002a94f  cmp     [rbx+10h], esi
0x18002a952  jbe     short loc_18002A996
0x18002a954  mov     edi, esi
0x18002a956  shl     rdi, 4
0x18002a95a  add     rdi, [rbx+18h]
0x18002a95e  mov     rax, [rdi]
0x18002a961  cmp     rax, rdi
0x18002a964  jz      short loc_18002A98F
0x18002a966  cmp     [rax+8], rdi
0x18002a96a  jnz     short loc_18002A9C9
0x18002a96c  mov     rcx, [rax]
0x18002a96f  cmp     [rcx+8], rax
0x18002a973  jnz     short loc_18002A9C9
0x18002a975  mov     [rdi], rcx
0x18002a978  mov     [rcx+8], rdi
0x18002a97c  lea     rcx, [rax-450h]; this
0x18002a983  test    rcx, rcx
0x18002a986  jz      short loc_18002A95E
0x18002a988  call    ??_GLOCALIZED_STRING@@QEAAPEAXI@Z; LOCALIZED_STRING::`scalar deleting destructor'(uint)
0x18002a98d  jmp     short loc_18002A95E
0x18002a98f  inc     esi
0x18002a991  cmp     esi, [rbx+10h]
0x18002a994  jb      short loc_18002A954
0x18002a996  mov     rcx, [rbx+18h]; Block
0x18002a99a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002a99f  mov     qword ptr [rbx+18h], 0
0x18002a9a7  lea     rcx, [rbx+30h]; lpCriticalSection
0x18002a9ab  call    cs:__imp_DeleteCriticalSection
0x18002a9b1  mov     rsi, [rsp+28h+arg_8]
0x18002a9b6  xor     eax, eax
0x18002a9b8  mov     dword ptr [rbx], 0
0x18002a9be  mov     rbx, [rsp+28h+arg_0]
0x18002a9c3  add     rsp, 20h
0x18002a9c7  pop     rdi
0x18002a9c8  retn
0x18002a9c9  mov     ecx, 3
0x18002a9ce  int     29h; Win8: RtlFailFast(ecx)
```
