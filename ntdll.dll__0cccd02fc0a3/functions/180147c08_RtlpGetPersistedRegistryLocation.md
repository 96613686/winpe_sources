# RtlpGetPersistedRegistryLocation

- ea: `0x180147c08`
- end: `0x180147cde`
- name: `RtlpGetPersistedRegistryLocation`
- size: `214`
- prototype: `__int64 __fastcall(wchar_t *String)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, registry_config`

## callers

- `0x1801479d4`

## callees

- `0x180016bc0`
- `0x18001d490`
- `0x180021fe0`
- `0x180147c08`

## string_xrefs

- `0x180147c47`: `TargetNtPath`
- `0x180147c91`: `TargetNtPath`

## pseudocode

```c
__int64 __fastcall RtlpGetPersistedRegistryLocation(wchar_t *String, __int64 a2, _QWORD *a3, _DWORD *a4)
{
  int PersistedStateLocation; // eax
  int v8; // ebx
  int v9; // ebx
  void *Atom; // rdi
  unsigned int v12[18]; // [rsp+40h] [rbp-48h] BYREF

  v12[0] = 0;
  PersistedStateLocation = RtlGetPersistedStateLocation(String, 0, 0, (__int64)v12);
  v8 = PersistedStateLocation;
  if ( PersistedStateLocation == -2147483643 )
  {
    v9 = v12[0];
    Atom = (void *)RtlpAllocateAtom(v12[0]);
    if ( Atom )
    {
      v8 = RtlGetPersistedStateLocation(String, Atom, v9, (__int64)v12);
      if ( v8 < 0 )
      {
        RtlpSysVolFree(Atom);
      }
      else
      {
        *a3 = Atom;
        if ( a4 )
          *a4 = (v12[0] >> 1) - 1;
      }
    }
    else
    {
      return (unsigned int)-1073741801;
    }
  }
  else if ( PersistedStateLocation >= 0 )
  {
    return (unsigned int)-1073741823;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180147c08  push    rbx
0x180147c0a  push    rbp
0x180147c0b  push    rsi
0x180147c0c  push    rdi
0x180147c0d  push    r14
0x180147c0f  push    r15
0x180147c11  sub     rsp, 58h
0x180147c15  lea     rax, [rsp+88h+var_48]
0x180147c1a  mov     [rsp+88h+var_48], 0
0x180147c22  mov     [rsp+88h+var_58], rax; __int64
0x180147c27  mov     r14, r8
0x180147c2a  mov     rsi, r9
0x180147c2d  mov     [rsp+88h+var_60], 0; int
0x180147c35  mov     rbp, rdx
0x180147c38  mov     [rsp+88h+var_68], 0; void *
0x180147c41  mov     r8, rdx
0x180147c44  xor     r9d, r9d
0x180147c47  lea     rdx, aTargetntpath; "TargetNtPath"
0x180147c4e  mov     r15, rcx
0x180147c51  call    RtlGetPersistedStateLocation
0x180147c56  mov     ebx, eax
0x180147c58  cmp     eax, 80000005h
0x180147c5d  jz      short loc_180147C6A
0x180147c5f  test    eax, eax
0x180147c61  js      short loc_180147CCE
0x180147c63  mov     ebx, 0C0000001h
0x180147c68  jmp     short loc_180147CCE
0x180147c6a  mov     ebx, [rsp+88h+var_48]
0x180147c6e  mov     ecx, ebx
0x180147c70  call    RtlpAllocateAtom
0x180147c75  mov     rdi, rax
0x180147c78  test    rax, rax
0x180147c7b  jnz     short loc_180147C84
0x180147c7d  mov     ebx, 0C0000017h
0x180147c82  jmp     short loc_180147CCE
0x180147c84  lea     rax, [rsp+88h+var_48]
0x180147c89  xor     r9d, r9d
0x180147c8c  mov     [rsp+88h+var_58], rax; __int64
0x180147c91  lea     rdx, aTargetntpath; "TargetNtPath"
0x180147c98  mov     [rsp+88h+var_60], ebx; int
0x180147c9c  mov     r8, rbp
0x180147c9f  mov     rcx, r15; String
0x180147ca2  mov     [rsp+88h+var_68], rdi; void *
0x180147ca7  call    RtlGetPersistedStateLocation
0x180147cac  mov     ebx, eax
0x180147cae  test    eax, eax
0x180147cb0  js      short loc_180147CC6
0x180147cb2  mov     [r14], rdi
0x180147cb5  test    rsi, rsi
0x180147cb8  jz      short loc_180147CCE
0x180147cba  mov     eax, [rsp+88h+var_48]
0x180147cbe  shr     eax, 1
0x180147cc0  dec     eax
0x180147cc2  mov     [rsi], eax
0x180147cc4  jmp     short loc_180147CCE
0x180147cc6  mov     rcx, rdi
0x180147cc9  call    RtlpSysVolFree
0x180147cce  mov     eax, ebx
0x180147cd0  add     rsp, 58h
0x180147cd4  pop     r15
0x180147cd6  pop     r14
0x180147cd8  pop     rdi
0x180147cd9  pop     rsi
0x180147cda  pop     rbp
0x180147cdb  pop     rbx
0x180147cdc  retn
```
