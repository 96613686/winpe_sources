# CString::CopyOnWrite(void)

- ea: `0x18001a15c`
- end: `0x18001a1eb`
- name: `?CopyOnWrite@CString@@AEAAXXZ`
- size: `143`
- prototype: `void __fastcall(CString *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800081ec`
- `0x18000e4fc`
- `0x18000ef38`
- `0x180012e94`
- `0x18001a5f0`

## callees

- `0x180001534`
- `0x180006ec0`
- `0x180019e80`
- `0x18001a15c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a1c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a1c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CString::CopyOnWrite(const unsigned __int16 ***this)
{
  CString::StringValue *v2; // rax
  const unsigned __int16 **v3; // rsi
  HLOCAL *v4; // rdi

  if ( *((int *)this[1] + 3) > 1 )
  {
    v2 = (CString::StringValue *)operator new(0x18u);
    if ( v2 )
      v3 = (const unsigned __int16 **)CString::StringValue::StringValue(v2, *this[1]);
    else
      v3 = 0;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)this[1] + 3, 0xFFFFFFFF) == 1 )
    {
      v4 = (HLOCAL *)this[1];
      if ( v4 )
      {
        if ( *v4 )
          LocalFree(*v4);
        operator delete(v4);
      }
    }
    this[1] = v3;
  }
}

```

## disassembly

```asm
0x18001a15c  mov     [rsp+arg_8], rbx
0x18001a161  mov     [rsp+arg_10], rsi
0x18001a166  push    rdi
0x18001a167  sub     rsp, 20h
0x18001a16b  mov     rbx, rcx
0x18001a16e  mov     rax, [rcx+8]
0x18001a172  cmp     dword ptr [rax+0Ch], 1
0x18001a176  jle     short loc_18001A1DB
0x18001a178  mov     ecx, 18h; uBytes
0x18001a17d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a182  mov     [rsp+28h+arg_0], rax
0x18001a187  test    rax, rax
0x18001a18a  jz      short loc_18001A1A0
0x18001a18c  mov     rdx, [rbx+8]
0x18001a190  mov     rdx, [rdx]; unsigned __int16 *
0x18001a193  mov     rcx, rax; this
0x18001a196  call    ??0StringValue@CString@@QEAA@PEBG@Z; CString::StringValue::StringValue(ushort const *)
0x18001a19b  mov     rsi, rax
0x18001a19e  jmp     short loc_18001A1A2
0x18001a1a0  xor     esi, esi
0x18001a1a2  mov     rcx, [rbx+8]
0x18001a1a6  or      eax, 0FFFFFFFFh
0x18001a1a9  lock xadd [rcx+0Ch], eax
0x18001a1ae  cmp     eax, 1
0x18001a1b1  jnz     short loc_18001A1D7
0x18001a1b3  mov     rdi, [rbx+8]
0x18001a1b7  test    rdi, rdi
0x18001a1ba  jz      short loc_18001A1D7
0x18001a1bc  mov     rcx, [rdi]; hMem
0x18001a1bf  test    rcx, rcx
0x18001a1c2  jz      short loc_18001A1CA
0x18001a1c4  call    cs:__imp_LocalFree
0x18001a1ca  mov     edx, 18h; unsigned __int64
0x18001a1cf  mov     rcx, rdi; void *
0x18001a1d2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a1d7  mov     [rbx+8], rsi
0x18001a1db  mov     rbx, [rsp+28h+arg_8]
0x18001a1e0  mov     rsi, [rsp+28h+arg_10]
0x18001a1e5  add     rsp, 20h
0x18001a1e9  pop     rdi
0x18001a1ea  retn
```
