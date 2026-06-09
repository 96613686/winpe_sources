# GenericCache_RemoveInstance

- ea: `0x18003deb0`
- end: `0x18003dfa9`
- name: `GenericCache_RemoveInstance`
- size: `249`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18003e700`
- `0x18003e7d0`
- `0x18003eac0`
- `0x18003ebf0`

## callees

- `0x180006e64`
- `0x180007c80`
- `0x18003deb0`
- `0x18003f470`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18003df4f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18003df4f`

## string_xrefs

- `0x18003df41`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall GenericCache_RemoveInstance(__int64 a1, unsigned __int16 *a2)
{
  __int64 v4; // r9
  unsigned __int16 v5; // dx
  unsigned __int16 *v6; // r8
  unsigned __int16 v7; // cx
  unsigned int v8; // esi
  __int64 v9; // rbx
  HMODULE ModuleHandleA; // rax
  __int64 v12; // [rsp+40h] [rbp-40h] BYREF
  __int128 v13; // [rsp+48h] [rbp-38h]
  unsigned __int128 v14; // [rsp+58h] [rbp-28h]
  __int128 v15; // [rsp+68h] [rbp-18h]
  __int64 v16; // [rsp+78h] [rbp-8h]

  v12 = 0;
  v14 = __PAIR128__((unsigned __int64)a2, 0);
  v16 = 0;
  v13 = 0;
  v4 = 2166136261LL;
  v15 = 0;
  v5 = *a2;
  if ( v5 )
  {
    v6 = a2;
    do
    {
      v7 = v5 + 32;
      ++v6;
      if ( (unsigned __int16)(v5 - 65) > 0x19u )
        v7 = v5;
      v5 = *v6;
      v4 = 16777619 * (v4 ^ v7);
    }
    while ( *v6 );
  }
  *(_QWORD *)&v14 = v4;
  v8 = ThreadSafeHashMap_Remove(a1, (__int64)&v12);
  if ( v8 == 6 )
  {
    v9 = *(_QWORD *)(a1 + 128);
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    Intlstr_FormatString_FormatMessage(ModuleHandleA, 2134, v9);
    MI_ReportErrorDetails_ForCustomError(6, (int)L"MI", 0, 0);
  }
  return v8;
}

```

## disassembly

```asm
0x18003deb0  push    rbp
0x18003deb2  push    rbx
0x18003deb3  push    rsi
0x18003deb4  push    rdi
0x18003deb5  push    r14
0x18003deb7  mov     rbp, rsp
0x18003deba  sub     rsp, 80h
0x18003dec1  xorps   xmm1, xmm1
0x18003dec4  xor     r14d, r14d
0x18003dec7  xor     eax, eax
0x18003dec9  mov     [rbp+var_40], r14
0x18003decd  movups  [rbp+var_28], xmm1
0x18003ded1  mov     qword ptr [rbp+var_28+8], rdx
0x18003ded5  mov     rdi, rdx
0x18003ded8  xorps   xmm0, xmm0
0x18003dedb  mov     [rbp+var_8], rax
0x18003dedf  movups  [rbp+var_38], xmm0
0x18003dee3  mov     rbx, rcx
0x18003dee6  mov     r9d, 811C9DC5h
0x18003deec  movups  [rbp+var_18], xmm1
0x18003def0  movzx   edx, word ptr [rdx]
0x18003def3  test    dx, dx
0x18003def6  jz      short loc_18003DF23
0x18003def8  mov     r8, rdi
0x18003defb  lea     eax, [rdx-41h]
0x18003defe  cmp     ax, 19h
0x18003df02  lea     ecx, [rdx+20h]
0x18003df05  lea     r8, [r8+2]
0x18003df09  cmova   cx, dx
0x18003df0d  movzx   edx, word ptr [r8]
0x18003df11  movzx   eax, cx
0x18003df14  xor     rax, r9
0x18003df17  imul    r9, rax, 1000193h
0x18003df1e  test    dx, dx
0x18003df21  jnz     short loc_18003DEFB
0x18003df23  lea     rdx, [rbp+var_40]
0x18003df27  mov     qword ptr [rbp+var_28], r9
0x18003df2b  mov     rcx, rbx
0x18003df2e  call    ThreadSafeHashMap_Remove
0x18003df33  mov     esi, eax
0x18003df35  cmp     eax, 6
0x18003df38  jnz     short loc_18003DF99
0x18003df3a  mov     rbx, [rbx+80h]
0x18003df41  lea     rcx, ModuleName; "mpunits.dll"
0x18003df48  xorps   xmm0, xmm0
0x18003df4b  movups  [rbp+var_50], xmm0
0x18003df4f  call    cs:__imp_GetModuleHandleA
0x18003df55  mov     r9, rdi
0x18003df58  mov     r8, rbx
0x18003df5b  mov     rcx, rax
0x18003df5e  mov     edx, 856h
0x18003df63  call    _Intlstr_FormatString_FormatMessage
0x18003df68  mov     qword ptr [rbp+var_50], rax
0x18003df6c  lea     r9, [rbp+var_50]
0x18003df70  mov     byte ptr [rbp+var_50+8], 1
0x18003df74  lea     r8d, [rsi+7]
0x18003df78  movaps  xmm0, [rbp+var_50]
0x18003df7c  lea     rdx, aMi; "MI"
0x18003df83  mov     [rsp+80h+var_58], r14; __int64
0x18003df88  mov     ecx, esi; int
0x18003df8a  movdqa  [rbp+var_50], xmm0
0x18003df8f  mov     [rsp+80h+var_60], r14; __int64
0x18003df94  call    MI_ReportErrorDetails_ForCustomError
0x18003df99  mov     eax, esi
0x18003df9b  add     rsp, 80h
0x18003dfa2  pop     r14
0x18003dfa4  pop     rdi
0x18003dfa5  pop     rsi
0x18003dfa6  pop     rbx
0x18003dfa7  pop     rbp
0x18003dfa8  retn
```
