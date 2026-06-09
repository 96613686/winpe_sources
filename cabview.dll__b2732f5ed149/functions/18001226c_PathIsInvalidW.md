# PathIsInvalidW

- ea: `0x18001226c`
- end: `0x180012304`
- name: `PathIsInvalidW`
- size: `152`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180004e50`
- `0x1800051e0`
- `0x18000ed4c`

## callees

- `0x180002620`
- `0x180008af8`
- `0x180008c48`
- `0x18001226c`

## import_xrefs

- `SHLWAPI!PathIsRelativeW` at `0x180012288`
- `SHLWAPI!PathIsRelativeW` at `0x180012288`
- `ntdll!RtlIsDosDeviceName_U` at `0x1800122dd`
- `ntdll!RtlIsDosDeviceName_U` at `0x1800122dd`

## pseudocode

```c
_BOOL8 __fastcall PathIsInvalidW(unsigned __int16 *a1)
{
  unsigned __int16 *v1; // rbx
  unsigned __int64 v2; // rax
  unsigned int v4; // r11d
  unsigned __int16 v5[16]; // [rsp+20h] [rbp-38h] BYREF

  v1 = a1;
  if ( !PathIsRelativeW(a1) )
  {
    v2 = -1;
    do
      ++v2;
    while ( v1[v2] );
    if ( v2 >= 0xE )
      return 0;
    StringCchCopyW(v5, 0x10u, L".\\");
    StringCchCatW(v5, v4, v1);
    v1 = v5;
  }
  return RtlIsDosDeviceName_U(v1) != 0;
}

```

## disassembly

```asm
0x18001226c  mov     [rsp+arg_8], rbx
0x180012271  push    rdi
0x180012272  sub     rsp, 50h
0x180012276  mov     rax, cs:__security_cookie
0x18001227d  xor     rax, rsp
0x180012280  mov     [rsp+58h+var_18], rax
0x180012285  mov     rbx, rcx
0x180012288  call    cs:__imp_PathIsRelativeW
0x18001228e  xor     edi, edi
0x180012290  test    eax, eax
0x180012292  jnz     short loc_1800122DA
0x180012294  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012298  inc     rax
0x18001229b  cmp     [rbx+rax*2], di
0x18001229f  jnz     short loc_180012298
0x1800122a1  cmp     rax, 0Eh
0x1800122a5  jb      short loc_1800122AB
0x1800122a7  xor     eax, eax
0x1800122a9  jmp     short loc_1800122EC
0x1800122ab  mov     r11d, 10h
0x1800122b1  lea     r8, asc_180015C20; ".\\"
0x1800122b8  mov     edx, r11d; unsigned __int64
0x1800122bb  lea     rcx, [rsp+58h+var_38]; unsigned __int16 *
0x1800122c0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800122c5  mov     r8, rbx; unsigned __int16 *
0x1800122c8  lea     rcx, [rsp+58h+var_38]; unsigned __int16 *
0x1800122cd  mov     edx, r11d; unsigned __int64
0x1800122d0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800122d5  lea     rbx, [rsp+58h+var_38]
0x1800122da  mov     rcx, rbx; Name
0x1800122dd  call    cs:__imp_RtlIsDosDeviceName_U
0x1800122e3  test    eax, eax
0x1800122e5  mov     ecx, edi
0x1800122e7  setnz   cl
0x1800122ea  mov     eax, ecx
0x1800122ec  mov     rcx, [rsp+58h+var_18]
0x1800122f1  xor     rcx, rsp; StackCookie
0x1800122f4  call    __security_check_cookie
0x1800122f9  mov     rbx, [rsp+58h+arg_8]
0x1800122fe  add     rsp, 50h
0x180012302  pop     rdi
0x180012303  retn
```
