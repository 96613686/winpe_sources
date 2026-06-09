# TranslateSecurityAttributes

- ea: `0x18002eef8`
- end: `0x18002efac`
- name: `TranslateSecurityAttributes`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180028780`

## callees

- `0x180029b70`
- `0x18002eef8`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002ef67`
- `KERNEL32!GetProcAddress` at `0x18002ef67`

## string_xrefs

- `0x18002ef60`: `TranslateSecurityAttributes`

## pseudocode

```c
__int64 __fastcall TranslateSecurityAttributes(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6)
{
  __int64 result; // rax
  int (*ProcAddress)(struct CORSEC_ATTRSET *, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, unsigned int *); // rax
  HMODULE hModule; // [rsp+40h] [rbp-38h] BYREF

  if ( g_TranslateSecurityAttributes )
    return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64, __int64, __int64))g_TranslateSecurityAttributes)(
             a1,
             a2,
             a3,
             a4,
             a5,
             a6);
  hModule = 0;
  result = GetInstallation((CLRFullPath *)1, &hModule, 0);
  if ( (int)result >= 0 )
  {
    ProcAddress = (int (*)(struct CORSEC_ATTRSET *, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, unsigned int *))GetProcAddress(hModule, "TranslateSecurityAttributes");
    g_TranslateSecurityAttributes = ProcAddress;
    if ( ProcAddress )
      return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64, __int64, __int64))ProcAddress)(
               a1,
               a2,
               a3,
               a4,
               a5,
               a6);
    else
      return 2148734721LL;
  }
  return result;
}

```

## disassembly

```asm
0x18002eef8  push    rbx
0x18002eefa  push    rbp
0x18002eefb  push    rsi
0x18002eefc  push    rdi
0x18002eefd  sub     rsp, 58h
0x18002ef01  mov     rax, cs:?g_TranslateSecurityAttributes@@3P6AJPEAVCORSEC_ATTRSET@@PEAPEAEPEAK122@ZEA; long (*g_TranslateSecurityAttributes)(CORSEC_ATTRSET *,uchar * *,ulong *,uchar * *,ulong *,ulong *)
0x18002ef08  mov     rbx, r9
0x18002ef0b  mov     rdi, r8
0x18002ef0e  mov     rsi, rdx
0x18002ef11  mov     rbp, rcx
0x18002ef14  test    rax, rax
0x18002ef17  jz      short loc_18002EF3D
0x18002ef19  mov     r10, [rsp+78h+arg_28]
0x18002ef21  mov     r9, [rsp+78h+arg_20]
0x18002ef29  mov     [rsp+78h+var_50], r10
0x18002ef2e  mov     [rsp+78h+var_58], r9
0x18002ef33  mov     r9, rbx
0x18002ef36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef3b  jmp     short loc_18002EFA3
0x18002ef3d  xor     r8d, r8d; int
0x18002ef40  mov     [rsp+78h+hModule], 0
0x18002ef49  lea     rdx, [rsp+78h+hModule]; HINSTANCE *
0x18002ef4e  lea     ecx, [r8+1]; int
0x18002ef52  call    ?GetInstallation@@YAJHPEAPEAUHINSTANCE__@@H@Z; GetInstallation(int,HINSTANCE__ * *,int)
0x18002ef57  test    eax, eax
0x18002ef59  js      short loc_18002EFA3
0x18002ef5b  mov     rcx, [rsp+78h+hModule]; hModule
0x18002ef60  lea     rdx, aTranslatesecur_1; "TranslateSecurityAttributes"
0x18002ef67  call    cs:__imp_GetProcAddress
0x18002ef6d  mov     cs:?g_TranslateSecurityAttributes@@3P6AJPEAVCORSEC_ATTRSET@@PEAPEAEPEAK122@ZEA, rax; long (*g_TranslateSecurityAttributes)(CORSEC_ATTRSET *,uchar * *,ulong *,uchar * *,ulong *,ulong *)
0x18002ef74  test    rax, rax
0x18002ef77  jz      short loc_18002EF9E
0x18002ef79  mov     rcx, [rsp+78h+arg_28]
0x18002ef81  mov     r8, rdi
0x18002ef84  mov     [rsp+78h+var_50], rcx
0x18002ef89  mov     rdx, rsi
0x18002ef8c  mov     rcx, [rsp+78h+arg_20]
0x18002ef94  mov     [rsp+78h+var_58], rcx
0x18002ef99  mov     rcx, rbp
0x18002ef9c  jmp     short loc_18002EF33
0x18002ef9e  mov     eax, 80131701h
0x18002efa3  add     rsp, 58h
0x18002efa7  pop     rdi
0x18002efa8  pop     rsi
0x18002efa9  pop     rbp
0x18002efaa  pop     rbx
0x18002efab  retn
```
