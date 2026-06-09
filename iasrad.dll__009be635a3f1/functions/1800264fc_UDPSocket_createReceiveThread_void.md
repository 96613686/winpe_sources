# UDPSocket::createReceiveThread(void)

- ea: `0x1800264fc`
- end: `0x180026581`
- name: `?createReceiveThread@UDPSocket@@IEAAHXZ`
- size: `133`
- prototype: `__int64 __fastcall(UDPSocket *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180026588`
- `0x180026a84`

## callees

- `0x18000e4e0`
- `0x1800264fc`

## import_xrefs

- `msvcrt!free` at `0x18002654a`
- `msvcrt!free` at `0x18002654a`
- `iassvcs!IASRequestThread` at `0x18002653b`
- `iassvcs!IASRequestThread` at `0x18002653b`
- `KERNEL32!SetEvent` at `0x180026569`
- `KERNEL32!SetEvent` at `0x180026569`

## pseudocode

```c
__int64 __fastcall UDPSocket::createReceiveThread(UDPSocket *this, const struct std::nothrow_t *a2)
{
  _QWORD *v3; // rsi
  unsigned int v4; // edi

  if ( *((_DWORD *)this + 11) )
  {
    v4 = 1;
    SetEvent(*((HANDLE *)this + 6));
  }
  else
  {
    v3 = operator new[](0x10u, a2);
    if ( v3 )
    {
      v3[1] = this;
      *v3 = UDPSocket::startRoutine;
      v4 = IASRequestThread(v3);
      if ( v4 )
        _InterlockedCompareExchange((volatile signed __int32 *)this + 10, 1, 0);
      else
        free(v3);
    }
    else
    {
      return 0;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800264fc  mov     [rsp+arg_0], rbx
0x180026501  mov     [rsp+arg_8], rsi
0x180026506  push    rdi
0x180026507  sub     rsp, 20h
0x18002650b  cmp     dword ptr [rcx+2Ch], 0
0x18002650f  mov     rbx, rcx
0x180026512  jnz     short loc_180026560
0x180026514  mov     ecx, 10h; Size
0x180026519  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002651e  mov     rsi, rax
0x180026521  test    rax, rax
0x180026524  jnz     short loc_18002652A
0x180026526  xor     edi, edi
0x180026528  jmp     short loc_18002656F
0x18002652a  lea     rax, ?startRoutine@UDPSocket@@KAXPEAUIAS_CALLBACK@@@Z; UDPSocket::startRoutine(IAS_CALLBACK *)
0x180026531  mov     [rsi+8], rbx
0x180026535  mov     rcx, rsi
0x180026538  mov     [rsi], rax
0x18002653b  call    cs:__imp_IASRequestThread
0x180026541  mov     edi, eax
0x180026543  test    eax, eax
0x180026545  jnz     short loc_180026552
0x180026547  mov     rcx, rsi; Block
0x18002654a  call    cs:__imp_free
0x180026550  jmp     short loc_18002656F
0x180026552  mov     ecx, 1
0x180026557  xor     eax, eax
0x180026559  lock cmpxchg [rbx+28h], ecx
0x18002655e  jmp     short loc_18002656F
0x180026560  mov     rcx, [rcx+30h]; hEvent
0x180026564  mov     edi, 1
0x180026569  call    cs:__imp_SetEvent
0x18002656f  mov     rbx, [rsp+28h+arg_0]
0x180026574  mov     eax, edi
0x180026576  mov     rsi, [rsp+28h+arg_8]
0x18002657b  add     rsp, 20h
0x18002657f  pop     rdi
0x180026580  retn
```
