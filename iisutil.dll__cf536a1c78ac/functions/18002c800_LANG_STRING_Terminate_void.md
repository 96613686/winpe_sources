# LANG_STRING::Terminate(void)

- ea: `0x18002c800`
- end: `0x18002c8e7`
- name: `?Terminate@LANG_STRING@@QEAAJXZ`
- size: `231`
- prototype: `__int64 __fastcall(LANG_STRING *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001fda0`

## callees

- `0x180019270`
- `0x18002c2b4`
- `0x18002c800`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002c8bb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002c8bb`

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
0x18002c800  mov     [rsp+arg_0], rbx
0x18002c805  mov     [rsp+arg_8], rsi
0x18002c80a  push    rdi
0x18002c80b  sub     rsp, 20h
0x18002c80f  cmp     qword ptr [rcx+20h], 0
0x18002c814  mov     rbx, rcx
0x18002c817  jz      short loc_18002C856
0x18002c819  xor     edi, edi
0x18002c81b  cmp     [rcx+28h], edi
0x18002c81e  jbe     short loc_18002C845
0x18002c820  mov     rax, [rbx+20h]
0x18002c824  mov     rcx, [rax+rdi*8]; Block
0x18002c828  test    rcx, rcx
0x18002c82b  jz      short loc_18002C83E
0x18002c82d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c832  mov     rax, [rbx+20h]
0x18002c836  mov     qword ptr [rax+rdi*8], 0
0x18002c83e  inc     edi
0x18002c840  cmp     edi, [rbx+28h]
0x18002c843  jb      short loc_18002C820
0x18002c845  mov     rcx, [rbx+20h]; Block
0x18002c849  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c84e  mov     qword ptr [rbx+20h], 0
0x18002c856  cmp     qword ptr [rbx+18h], 0
0x18002c85b  jz      short loc_18002C8B7
0x18002c85d  xor     esi, esi
0x18002c85f  cmp     [rbx+10h], esi
0x18002c862  jbe     short loc_18002C8A6
0x18002c864  mov     edi, esi
0x18002c866  shl     rdi, 4
0x18002c86a  add     rdi, [rbx+18h]
0x18002c86e  mov     rax, [rdi]
0x18002c871  cmp     rax, rdi
0x18002c874  jz      short loc_18002C89F
0x18002c876  cmp     [rax+8], rdi
0x18002c87a  jnz     short loc_18002C8E0
0x18002c87c  mov     rcx, [rax]
0x18002c87f  cmp     [rcx+8], rax
0x18002c883  jnz     short loc_18002C8E0
0x18002c885  mov     [rdi], rcx
0x18002c888  mov     [rcx+8], rdi
0x18002c88c  lea     rcx, [rax-450h]; this
0x18002c893  test    rcx, rcx
0x18002c896  jz      short loc_18002C86E
0x18002c898  call    ??_GLOCALIZED_STRING@@QEAAPEAXI@Z; LOCALIZED_STRING::`scalar deleting destructor'(uint)
0x18002c89d  jmp     short loc_18002C86E
0x18002c89f  inc     esi
0x18002c8a1  cmp     esi, [rbx+10h]
0x18002c8a4  jb      short loc_18002C864
0x18002c8a6  mov     rcx, [rbx+18h]; Block
0x18002c8aa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c8af  mov     qword ptr [rbx+18h], 0
0x18002c8b7  lea     rcx, [rbx+30h]; lpCriticalSection
0x18002c8bb  call    cs:__imp_DeleteCriticalSection
0x18002c8c2  nop     dword ptr [rax+rax+00h]
0x18002c8c7  mov     rsi, [rsp+28h+arg_8]
0x18002c8cc  xor     eax, eax
0x18002c8ce  mov     dword ptr [rbx], 0
0x18002c8d4  mov     rbx, [rsp+28h+arg_0]
0x18002c8d9  add     rsp, 20h
0x18002c8dd  pop     rdi
0x18002c8de  retn
0x18002c8e0  mov     ecx, 3
0x18002c8e5  int     29h; Win8: RtlFailFast(ecx)
```
