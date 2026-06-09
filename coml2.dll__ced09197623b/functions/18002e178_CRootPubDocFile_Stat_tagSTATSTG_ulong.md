# CRootPubDocFile::Stat(tagSTATSTG *,ulong)

- ea: `0x18002e178`
- end: `0x18002e282`
- name: `?Stat@CRootPubDocFile@@QEAAJPEAUtagSTATSTG@@K@Z`
- size: `266`
- prototype: `__int64 __fastcall(CRootPubDocFile *__hidden this, struct tagSTATSTG *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800146d0`

## callees

- `0x18002e178`
- `0x18002e288`
- `0x18002e42c`
- `0x18002e7e0`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e26c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e26c`

## pseudocode

```c
__int64 __fastcall CRootPubDocFile::Stat(CRootPubDocFile *this, struct tagSTATSTG *a2, unsigned int a3)
{
  __int64 v5; // rcx
  int Class; // ebx
  __int64 v7; // rdx
  PDocFile *v8; // rcx
  __int64 v9; // rdx
  PDocFile *v10; // rcx

  if ( (*((_BYTE *)this + 20) & 0x20) != 0 )
  {
    return (unsigned int)-2147286782;
  }
  else
  {
    v5 = *((_QWORD *)this + 20);
    if ( v5 )
      v5 += *(_QWORD *)NtCurrentTeb()->ReservedForOle;
    Class = (*(__int64 (__fastcall **)(_QWORD, struct tagSTATSTG *, _QWORD))(**(_QWORD **)(v5 + 48) + 72LL))(
              *(_QWORD *)(v5 + 48),
              a2,
              a3);
    if ( Class >= 0 )
    {
      *((_DWORD *)a2 + 12) = DFlagsToMode(*((_DWORD *)this + 5));
      v7 = *((_QWORD *)this + 15);
      if ( v7 )
        v8 = (PDocFile *)(v7 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
      else
        v8 = 0;
      Class = PDocFile::GetClass(v8, (struct _GUID *)((char *)a2 + 56));
      if ( Class >= 0 )
      {
        v9 = *((_QWORD *)this + 15);
        v10 = v9 ? (PDocFile *)(v9 + *(_QWORD *)NtCurrentTeb()->ReservedForOle) : 0LL;
        Class = PDocFile::GetStateBits(v10, (unsigned int *)a2 + 18);
        if ( Class >= 0 )
          return 0;
      }
      if ( *(_QWORD *)a2 )
      {
        CoTaskMemFree(*(LPVOID *)a2);
        *(_QWORD *)a2 = 0;
      }
    }
  }
  return (unsigned int)Class;
}

```

## disassembly

```asm
0x18002e178  mov     [rsp+arg_0], rbx
0x18002e17d  mov     [rsp+arg_8], rsi
0x18002e182  push    rdi
0x18002e183  sub     rsp, 20h
0x18002e187  test    byte ptr [rcx+14h], 20h
0x18002e18b  mov     r9d, r8d
0x18002e18e  mov     rdi, rdx
0x18002e191  mov     rsi, rcx
0x18002e194  jnz     loc_18002E27B
0x18002e19a  mov     rcx, [rcx+0A0h]
0x18002e1a1  test    rcx, rcx
0x18002e1a4  jz      loc_18002E267
0x18002e1aa  mov     rax, gs:30h
0x18002e1b3  mov     r8, [rax+1758h]
0x18002e1ba  add     rcx, [r8]
0x18002e1bd  mov     rcx, [rcx+30h]
0x18002e1c1  mov     r8d, r9d
0x18002e1c4  mov     rax, [rcx]
0x18002e1c7  mov     rax, [rax+48h]
0x18002e1cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e1d0  mov     ebx, eax
0x18002e1d2  test    eax, eax
0x18002e1d4  js      loc_18002E25B
0x18002e1da  mov     ecx, [rsi+14h]; unsigned int
0x18002e1dd  call    ?DFlagsToMode@@YAKK@Z; DFlagsToMode(ulong)
0x18002e1e2  mov     [rdi+30h], eax
0x18002e1e5  mov     rdx, [rsi+78h]
0x18002e1e9  test    rdx, rdx
0x18002e1ec  jz      short loc_18002E25F
0x18002e1ee  mov     rax, gs:30h
0x18002e1f7  mov     rcx, [rax+1758h]
0x18002e1fe  mov     rcx, [rcx]
0x18002e201  add     rcx, rdx; this
0x18002e204  lea     rdx, [rdi+38h]; struct _GUID *
0x18002e208  call    ?GetClass@PDocFile@@QEAAJPEAU_GUID@@@Z; PDocFile::GetClass(_GUID *)
0x18002e20d  mov     ebx, eax
0x18002e20f  test    eax, eax
0x18002e211  js      short loc_18002E253
0x18002e213  mov     rdx, [rsi+78h]
0x18002e217  test    rdx, rdx
0x18002e21a  jz      short loc_18002E263
0x18002e21c  mov     rax, gs:30h
0x18002e225  mov     rcx, [rax+1758h]
0x18002e22c  mov     rcx, [rcx]
0x18002e22f  add     rcx, rdx; this
0x18002e232  lea     rdx, [rdi+48h]; unsigned int *
0x18002e236  call    ?GetStateBits@PDocFile@@QEAAJPEAK@Z; PDocFile::GetStateBits(ulong *)
0x18002e23b  mov     ebx, eax
0x18002e23d  test    eax, eax
0x18002e23f  js      short loc_18002E253
0x18002e241  xor     eax, eax
0x18002e243  mov     rbx, [rsp+28h+arg_0]
0x18002e248  mov     rsi, [rsp+28h+arg_8]
0x18002e24d  add     rsp, 20h
0x18002e251  pop     rdi
0x18002e252  retn
0x18002e253  mov     rcx, [rdi]; pv
0x18002e256  test    rcx, rcx
0x18002e259  jnz     short loc_18002E26C
0x18002e25b  mov     eax, ebx
0x18002e25d  jmp     short loc_18002E243
0x18002e25f  xor     ecx, ecx
0x18002e261  jmp     short loc_18002E204
0x18002e263  xor     ecx, ecx
0x18002e265  jmp     short loc_18002E232
0x18002e267  jmp     loc_18002E1BD
0x18002e26c  call    cs:__imp_CoTaskMemFree
0x18002e272  mov     qword ptr [rdi], 0
0x18002e279  jmp     short loc_18002E25B
0x18002e27b  mov     ebx, 80030102h
0x18002e280  jmp     short loc_18002E25B
```
