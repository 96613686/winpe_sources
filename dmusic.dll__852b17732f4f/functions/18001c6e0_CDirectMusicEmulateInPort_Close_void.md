# CDirectMusicEmulateInPort::Close(void)

- ea: `0x18001c6e0`
- end: `0x18001c7e7`
- name: `?Close@CDirectMusicEmulateInPort@@UEAAJXZ`
- size: `263`
- prototype: `__int64 __fastcall(CDirectMusicEmulateInPort *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001c458`

## callees

- `0x1800012c4`
- `0x18001ada0`
- `0x18001c6e0`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001c7cf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001c7cf`
- `api-ms-win-mm-mme-l1-1-0!midiInReset` at `0x18001c6f9`
- `api-ms-win-mm-mme-l1-1-0!midiInReset` at `0x18001c6f9`
- `api-ms-win-mm-mme-l1-1-0!midiInClose` at `0x18001c706`
- `api-ms-win-mm-mme-l1-1-0!midiInClose` at `0x18001c706`

## pseudocode

```c
__int64 __fastcall CDirectMusicEmulateInPort::Close(CDirectMusicEmulateInPort *this, unsigned __int64 a2)
{
  HMIDIIN v3; // rcx
  __int64 v4; // rcx
  __int64 i; // rdi
  __int64 v6; // rcx
  __int64 v7; // rcx

  v3 = (HMIDIIN)*((_QWORD *)this + 62);
  if ( v3 )
  {
    midiInReset(v3);
    midiInClose(*((HMIDIIN *)this + 62));
    *((_QWORD *)this + 62) = 0;
  }
  v4 = *((_QWORD *)this + 4308);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 4308) = 0;
  }
  if ( *((_QWORD *)this + 55) )
  {
    for ( i = 0; i != 16; ++i )
    {
      v6 = *(_QWORD *)(*((_QWORD *)this + 55) + 24 * i + 8);
      if ( v6 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    operator delete(*((void **)this + 55), a2);
    *((_QWORD *)this + 55) = 0;
  }
  v7 = *((_QWORD *)this + 54);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    *((_QWORD *)this + 54) = 0;
  }
  if ( *((_QWORD *)this + 47) )
    *((_QWORD *)this + 47) = 0;
  if ( *((_DWORD *)this + 122) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 448));
  return CDirectMusicEmulatePort::Close(this);
}

```

## disassembly

```asm
0x18001c6e0  mov     [rsp+arg_0], rbx
0x18001c6e5  push    rdi
0x18001c6e6  sub     rsp, 20h
0x18001c6ea  mov     rbx, rcx
0x18001c6ed  mov     rcx, [rcx+1F0h]; hmi
0x18001c6f4  test    rcx, rcx
0x18001c6f7  jz      short loc_18001C717
0x18001c6f9  call    cs:__imp_midiInReset
0x18001c6ff  mov     rcx, [rbx+1F0h]; hmi
0x18001c706  call    cs:__imp_midiInClose
0x18001c70c  mov     qword ptr [rbx+1F0h], 0
0x18001c717  mov     rcx, [rbx+86A0h]
0x18001c71e  test    rcx, rcx
0x18001c721  jz      short loc_18001C73A
0x18001c723  mov     rax, [rcx]
0x18001c726  mov     rax, [rax+10h]
0x18001c72a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c72f  mov     qword ptr [rbx+86A0h], 0
0x18001c73a  cmp     qword ptr [rbx+1B8h], 0
0x18001c742  jz      short loc_18001C787
0x18001c744  xor     edi, edi
0x18001c746  mov     rax, [rbx+1B8h]
0x18001c74d  lea     rcx, [rdi+rdi*2]
0x18001c751  mov     rcx, [rax+rcx*8+8]
0x18001c756  test    rcx, rcx
0x18001c759  jz      short loc_18001C767
0x18001c75b  mov     rax, [rcx]
0x18001c75e  mov     rax, [rax+10h]
0x18001c762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c767  inc     rdi
0x18001c76a  cmp     rdi, 10h
0x18001c76e  jnz     short loc_18001C746
0x18001c770  mov     rcx, [rbx+1B8h]; void *
0x18001c777  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001c77c  mov     qword ptr [rbx+1B8h], 0
0x18001c787  mov     rcx, [rbx+1B0h]
0x18001c78e  test    rcx, rcx
0x18001c791  jz      short loc_18001C7AA
0x18001c793  mov     rax, [rcx]
0x18001c796  mov     rax, [rax+10h]
0x18001c79a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c79f  mov     qword ptr [rbx+1B0h], 0
0x18001c7aa  cmp     qword ptr [rbx+178h], 0
0x18001c7b2  jz      short loc_18001C7BF
0x18001c7b4  mov     qword ptr [rbx+178h], 0
0x18001c7bf  cmp     dword ptr [rbx+1E8h], 0
0x18001c7c6  jz      short loc_18001C7D5
0x18001c7c8  lea     rcx, [rbx+1C0h]; lpCriticalSection
0x18001c7cf  call    cs:__imp_DeleteCriticalSection
0x18001c7d5  mov     rcx, rbx; this
0x18001c7d8  mov     rbx, [rsp+28h+arg_0]
0x18001c7dd  add     rsp, 20h
0x18001c7e1  pop     rdi
0x18001c7e2  jmp     ?Close@CDirectMusicEmulatePort@@UEAAJXZ; CDirectMusicEmulatePort::Close(void)
```
