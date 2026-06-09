# CASFReader::CallStop(void)

- ea: `0x180008764`
- end: `0x1800087d0`
- name: `?CallStop@CASFReader@@AEAAJXZ`
- size: `108`
- prototype: `__int64 __fastcall(CASFReader *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18000d4f0`
- `0x18000d550`

## callees

- `0x180008764`
- `0x18000d1e0`
- `0x18001f010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18000879d`
- `KERNEL32!WaitForSingleObject` at `0x18000879d`

## pseudocode

```c
__int64 __fastcall CASFReader::CallStop(CASFReader *this)
{
  int v2; // edi

  if ( _InterlockedIncrement((volatile signed __int32 *)this + 111)
    || (v2 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 43) + 88LL))(*((_QWORD *)this + 43))) == 0 )
  {
    WaitForSingleObject(*((HANDLE *)this + 53), 0xFFFFFFFF);
    v2 = *((_DWORD *)this + 110);
    if ( v2 >= 0 && !*((_DWORD *)this + 112) )
      CASFReader::SetupActiveStreams(this, 1);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180008764  mov     [rsp+arg_0], rbx
0x180008769  push    rdi
0x18000876a  sub     rsp, 20h
0x18000876e  mov     rbx, rcx
0x180008771  lock inc dword ptr [rcx+1BCh]
0x180008778  jnz     short loc_180008793
0x18000877a  mov     rcx, [rcx+158h]
0x180008781  mov     rax, [rcx]
0x180008784  mov     rax, [rax+58h]
0x180008788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000878d  mov     edi, eax
0x18000878f  test    eax, eax
0x180008791  jnz     short loc_1800087C3
0x180008793  mov     rcx, [rbx+1A8h]; hHandle
0x18000879a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000879d  call    cs:__imp_WaitForSingleObject
0x1800087a3  mov     edi, [rbx+1B8h]
0x1800087a9  test    edi, edi
0x1800087ab  js      short loc_1800087C3
0x1800087ad  cmp     dword ptr [rbx+1C0h], 0
0x1800087b4  jnz     short loc_1800087C3
0x1800087b6  mov     edx, 1; int
0x1800087bb  mov     rcx, rbx; this
0x1800087be  call    ?SetupActiveStreams@CASFReader@@AEAAJH@Z; CASFReader::SetupActiveStreams(int)
0x1800087c3  mov     rbx, [rsp+28h+arg_0]
0x1800087c8  mov     eax, edi
0x1800087ca  add     rsp, 20h
0x1800087ce  pop     rdi
0x1800087cf  retn
```
