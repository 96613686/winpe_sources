# RtlpGetPersistedRegistryLocation

- ea: `0x180148568`
- end: `0x18014863e`
- name: `RtlpGetPersistedRegistryLocation`
- size: `214`
- prototype: `__int64 __fastcall(wchar_t *String)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, registry_config`

## callers

- `0x180148334`

## callees

- `0x180016bc0`
- `0x18001d490`
- `0x180021fd0`
- `0x180148568`

## string_xrefs

- `0x1801485a7`: `TargetNtPath`
- `0x1801485f1`: `TargetNtPath`

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
0x180148568  push    rbx
0x18014856a  push    rbp
0x18014856b  push    rsi
0x18014856c  push    rdi
0x18014856d  push    r14
0x18014856f  push    r15
0x180148571  sub     rsp, 58h
0x180148575  lea     rax, [rsp+88h+var_48]
0x18014857a  mov     [rsp+88h+var_48], 0
0x180148582  mov     [rsp+88h+var_58], rax; __int64
0x180148587  mov     r14, r8
0x18014858a  mov     rsi, r9
0x18014858d  mov     [rsp+88h+var_60], 0; int
0x180148595  mov     rbp, rdx
0x180148598  mov     [rsp+88h+var_68], 0; void *
0x1801485a1  mov     r8, rdx
0x1801485a4  xor     r9d, r9d
0x1801485a7  lea     rdx, aTargetntpath; "TargetNtPath"
0x1801485ae  mov     r15, rcx
0x1801485b1  call    RtlGetPersistedStateLocation
0x1801485b6  mov     ebx, eax
0x1801485b8  cmp     eax, 80000005h
0x1801485bd  jz      short loc_1801485CA
0x1801485bf  test    eax, eax
0x1801485c1  js      short loc_18014862E
0x1801485c3  mov     ebx, 0C0000001h
0x1801485c8  jmp     short loc_18014862E
0x1801485ca  mov     ebx, [rsp+88h+var_48]
0x1801485ce  mov     ecx, ebx
0x1801485d0  call    RtlpAllocateAtom
0x1801485d5  mov     rdi, rax
0x1801485d8  test    rax, rax
0x1801485db  jnz     short loc_1801485E4
0x1801485dd  mov     ebx, 0C0000017h
0x1801485e2  jmp     short loc_18014862E
0x1801485e4  lea     rax, [rsp+88h+var_48]
0x1801485e9  xor     r9d, r9d
0x1801485ec  mov     [rsp+88h+var_58], rax; __int64
0x1801485f1  lea     rdx, aTargetntpath; "TargetNtPath"
0x1801485f8  mov     [rsp+88h+var_60], ebx; int
0x1801485fc  mov     r8, rbp
0x1801485ff  mov     rcx, r15; String
0x180148602  mov     [rsp+88h+var_68], rdi; void *
0x180148607  call    RtlGetPersistedStateLocation
0x18014860c  mov     ebx, eax
0x18014860e  test    eax, eax
0x180148610  js      short loc_180148626
0x180148612  mov     [r14], rdi
0x180148615  test    rsi, rsi
0x180148618  jz      short loc_18014862E
0x18014861a  mov     eax, [rsp+88h+var_48]
0x18014861e  shr     eax, 1
0x180148620  dec     eax
0x180148622  mov     [rsi], eax
0x180148624  jmp     short loc_18014862E
0x180148626  mov     rcx, rdi
0x180148629  call    RtlpSysVolFree
0x18014862e  mov     eax, ebx
0x180148630  add     rsp, 58h
0x180148634  pop     r15
0x180148636  pop     r14
0x180148638  pop     rdi
0x180148639  pop     rsi
0x18014863a  pop     rbp
0x18014863b  pop     rbx
0x18014863c  retn
```
