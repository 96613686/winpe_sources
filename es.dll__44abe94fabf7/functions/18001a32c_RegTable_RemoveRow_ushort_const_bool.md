# RegTable::RemoveRow(ushort const *,bool)

- ea: `0x18001a32c`
- end: `0x18001a40f`
- name: `?RemoveRow@RegTable@@QEAAJPEBG_N@Z`
- size: `227`
- prototype: `__int64 __fastcall(RegTable *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001a2b0`
- `0x18003aa30`

## callees

- `0x180010410`
- `0x18001a32c`
- `0x18001a420`
- `0x18001a4b8`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a3f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a3f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800446e7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001a3e4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001a3e4`

## pseudocode

```c
__int64 __fastcall RegTable::RemoveRow(RegTable *this, const unsigned __int16 *a2, char a3)
{
  unsigned int v6; // edi
  struct _RTL_CRITICAL_SECTION *v7; // r14
  __int64 v8; // rsi
  const WCHAR *v9; // rbx
  HKEY v10; // rax
  LSTATUS v11; // eax
  __int64 v13; // [rsp+58h] [rbp+20h] BYREF

  v6 = 0;
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 616);
  CSemExclusiveES::Lock((RegTable *)((char *)this + 616));
  v13 = 0;
  if ( (unsigned int)CMap<CString,unsigned short const *,RegRow *,RegRow *>::Lookup((char *)this + 576, a2, &v13) )
  {
    CMap<CString,unsigned short const *,RegRow *,RegRow *>::RemoveKey((char *)this + 576, a2);
    v8 = v13;
    if ( a3 )
    {
      v9 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 168LL))(v13);
      v10 = (HKEY)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 160LL))(v8);
      v11 = RegDeleteTreeW(v10, v9);
      if ( v11 )
      {
        if ( v11 > 0 )
          v6 = (unsigned __int16)v11 | 0x80070000;
        else
          v6 = v11;
      }
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  LeaveCriticalSection(v7);
  return v6;
}

```

## disassembly

```asm
0x18001a32c  mov     [rsp+arg_8], rbx
0x18001a331  mov     [rsp+arg_10], rsi
0x18001a336  mov     [rsp+arg_0], rcx
0x18001a33b  push    rdi
0x18001a33c  push    r14
0x18001a33e  push    r15
0x18001a340  sub     rsp, 20h
0x18001a344  mov     r15b, r8b
0x18001a347  mov     rsi, rdx
0x18001a34a  mov     rbx, rcx
0x18001a34d  xor     edi, edi
0x18001a34f  lea     r14, [rcx+268h]
0x18001a356  mov     rcx, r14; this
0x18001a359  call    ?Lock@CSemExclusiveES@@QEAAXXZ; CSemExclusiveES::Lock(void)
0x18001a35e  nop
0x18001a35f  mov     [rsp+38h+arg_18], rdi
0x18001a364  lea     r8, [rsp+38h+arg_18]
0x18001a369  mov     rdx, rsi
0x18001a36c  lea     rcx, [rbx+240h]
0x18001a373  call    ?Lookup@?$CMap@VCString@@PEBGPEAVRegRow@@PEAV2@@@QEBAHPEBGAEAPEAVRegRow@@@Z; CMap<CString,ushort const *,RegRow *,RegRow *>::Lookup(ushort const *,RegRow * &)
0x18001a378  test    eax, eax
0x18001a37a  jz      short loc_18001A3F0
0x18001a37c  mov     rdx, rsi
0x18001a37f  lea     rcx, [rbx+240h]
0x18001a386  call    ?RemoveKey@?$CMap@VCString@@PEBGPEAVRegRow@@PEAV2@@@QEAAHPEBG@Z; CMap<CString,ushort const *,RegRow *,RegRow *>::RemoveKey(ushort const *)
0x18001a38b  mov     rsi, [rsp+38h+arg_18]
0x18001a390  test    r15b, r15b
0x18001a393  jnz     short loc_18001A3B7
0x18001a395  mov     rax, [rsi]
0x18001a398  mov     rcx, rsi
0x18001a39b  mov     rax, [rax+10h]
0x18001a39f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3a4  jmp     short loc_18001A3F0
0x18001a3a6  jg      short loc_18001A3AC
0x18001a3a8  mov     edi, eax
0x18001a3aa  jmp     short loc_18001A395
0x18001a3ac  movzx   edi, ax
0x18001a3af  or      edi, 80070000h
0x18001a3b5  jmp     short loc_18001A395
0x18001a3b7  mov     rax, [rsi]
0x18001a3ba  mov     rcx, rsi
0x18001a3bd  mov     rax, [rax+0A8h]
0x18001a3c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3c9  mov     rbx, rax
0x18001a3cc  mov     rcx, [rsi]
0x18001a3cf  mov     rax, [rcx+0A0h]
0x18001a3d6  mov     rcx, rsi
0x18001a3d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3de  mov     rdx, rbx; lpSubKey
0x18001a3e1  mov     rcx, rax; hKey
0x18001a3e4  call    cs:__imp_RegDeleteTreeW
0x18001a3ea  test    eax, eax
0x18001a3ec  jz      short loc_18001A395
0x18001a3ee  jmp     short loc_18001A3A6
0x18001a3f0  mov     rcx, r14; lpCriticalSection
0x18001a3f3  call    cs:__imp_LeaveCriticalSection
0x18001a3f9  mov     eax, edi
0x18001a3fb  mov     rbx, [rsp+38h+arg_8]
0x18001a400  mov     rsi, [rsp+38h+arg_10]
0x18001a405  add     rsp, 20h
0x18001a409  pop     r15
0x18001a40b  pop     r14
0x18001a40d  pop     rdi
0x18001a40e  retn
0x1800446ce  push    rbp
0x1800446d0  sub     rsp, 20h
0x1800446d4  mov     rbp, rdx
0x1800446d7  mov     rcx, [rbp+40h]
0x1800446db  add     rcx, 268h
0x1800446e2  add     rsp, 20h
0x1800446e6  pop     rbp
0x1800446e7  jmp     cs:__imp_LeaveCriticalSection
```
