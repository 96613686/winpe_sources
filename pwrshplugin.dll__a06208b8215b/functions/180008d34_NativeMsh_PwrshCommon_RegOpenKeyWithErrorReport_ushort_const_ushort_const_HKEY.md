# NativeMsh::PwrshCommon::RegOpenKeyWithErrorReport(ushort const *,ushort const *,HKEY__ * *)

- ea: `0x180008d34`
- end: `0x180008db7`
- name: `?RegOpenKeyWithErrorReport@PwrshCommon@NativeMsh@@IEAA_NPEBG0PEAPEAUHKEY__@@@Z`
- size: `131`
- prototype: `char __fastcall(NativeMsh::PwrshCommon *this, const unsigned __int16 *, const unsigned __int16 *, HKEY *phkResult)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800086b8`
- `0x180008890`

## callees

- `0x180008d34`
- `0x18000b010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180008d5d`
- `ADVAPI32!RegOpenKeyExW` at `0x180008d5d`

## pseudocode

```c
char __fastcall NativeMsh::PwrshCommon::RegOpenKeyWithErrorReport(
        NativeMsh::PwrshCommon *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        HKEY *phkResult)
{
  char v7; // bl
  unsigned int v8; // eax
  __int64 v9; // rdx
  __int64 *v10; // rcx
  __int64 v11; // rax
  void (__fastcall *v12)(_QWORD *, __int64, __int64, const unsigned __int16 *); // rax
  __int64 v13; // r8

  v7 = 1;
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20019u, phkResult);
  v9 = v8;
  if ( v8 )
  {
    v10 = (__int64 *)*((_QWORD *)this + 1);
    v11 = *v10;
    if ( (_DWORD)v9 == 2 )
    {
      v12 = *(void (__fastcall **)(_QWORD *, __int64, __int64, const unsigned __int16 *))(v11 + 8);
      v9 = 0;
      if ( a3 )
      {
        ((void (__fastcall *)(__int64 *, _QWORD, __int64, const unsigned __int16 *, const unsigned __int16 *))v12)(
          v10,
          0,
          39,
          a2,
          a3);
        return 0;
      }
      v13 = 30;
    }
    else
    {
      v12 = *(void (__fastcall **)(_QWORD *, __int64, __int64, const unsigned __int16 *))(v11 + 16);
      v13 = 20;
    }
    v12(v10, v9, v13, a2);
    return 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180008d34  push    rbx
0x180008d36  push    rbp
0x180008d37  push    rsi
0x180008d38  push    rdi
0x180008d39  sub     rsp, 38h
0x180008d3d  mov     rsi, r8
0x180008d40  mov     [rsp+58h+phkResult], r9; phkResult
0x180008d45  mov     rbp, rcx
0x180008d48  mov     r9d, 20019h; samDesired
0x180008d4e  xor     r8d, r8d; ulOptions
0x180008d51  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008d58  mov     rdi, rdx
0x180008d5b  mov     bl, 1
0x180008d5d  call    cs:__imp_RegOpenKeyExW
0x180008d63  mov     edx, eax
0x180008d65  test    eax, eax
0x180008d67  jz      short loc_180008DAC
0x180008d69  mov     rcx, [rbp+8]
0x180008d6d  mov     r9, rdi
0x180008d70  mov     rax, [rcx]
0x180008d73  cmp     edx, 2
0x180008d76  jnz     short loc_180008D9B
0x180008d78  mov     rax, [rax+8]
0x180008d7c  xor     edx, edx
0x180008d7e  test    rsi, rsi
0x180008d81  jnz     short loc_180008D89
0x180008d83  lea     r8d, [rdx+1Eh]
0x180008d87  jmp     short loc_180008DA5
0x180008d89  mov     r8d, 27h ; '''
0x180008d8f  mov     [rsp+58h+phkResult], rsi
0x180008d94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d99  jmp     short loc_180008DAA
0x180008d9b  mov     rax, [rax+10h]
0x180008d9f  mov     r8d, 14h
0x180008da5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008daa  xor     bl, bl
0x180008dac  mov     al, bl
0x180008dae  add     rsp, 38h
0x180008db2  pop     rdi
0x180008db3  pop     rsi
0x180008db4  pop     rbp
0x180008db5  pop     rbx
0x180008db6  retn
```
