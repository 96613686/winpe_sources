# MintValue_CoerceToNumberImpl

- ea: `0x18000e650`
- end: `0x18000e79f`
- name: `MintValue_CoerceToNumberImpl`
- size: `335`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000c4f0`
- `0x18000eaf0`
- `0x18000ec70`
- `0x18000f1a0`
- `0x180014b50`
- `0x180014de0`

## callees

- `0x180006ef8`
- `0x180007c80`
- `0x18000e650`
- `0x18000e7ec`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000e6f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000e6f3`

## string_xrefs

- `0x18000e6e8`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall MintValue_CoerceToNumberImpl(__int64 a1, char *a2)
{
  char v2; // al
  bool v4; // zf
  __int64 result; // rax
  __int128 v6; // xmm0
  HMODULE ModuleHandleA; // rax
  __int128 v8; // [rsp+30h] [rbp-10h] BYREF

  v2 = *a2;
  if ( *a2 == -1 || (*(_DWORD *)a2 & 0x100) != 0 )
  {
    *(_QWORD *)&v8 = 6;
    result = a1;
    goto LABEL_15;
  }
  if ( v2 )
  {
    if ( v2 == 13 )
    {
      v6 = *(_OWORD *)MintValue_CoerceToNumber_String(&v8, *(_QWORD *)(*((_QWORD *)a2 + 1) + 16LL));
    }
    else
    {
      if ( v2 == 15
        && ((__int64 (__fastcall *)(_QWORD))Observable_FromInstance)(*(_QWORD *)(*((_QWORD *)a2 + 1) + 24LL)) )
      {
        v8 = 0;
        ModuleHandleA = GetModuleHandleA("mpunits.dll");
        *(_QWORD *)&v8 = Intlstr_GetString_LoadString(ModuleHandleA, 2066);
        BYTE8(v8) = 0;
        MI_ReportErrorDetails_ForCustomError(7, (int)L"MI", 0, 0);
        *(_DWORD *)(a1 + 4) = 0;
        *(_QWORD *)(a1 + 8) = 0;
        *(_DWORD *)a1 = 254;
        return a1;
      }
      v8 = 0xFFu;
      v6 = 0xFFu;
    }
    *(_OWORD *)a1 = v6;
    return a1;
  }
  v4 = a2[8] == 0;
  result = a1;
  *(_QWORD *)&v8 = 6;
  if ( v4 )
  {
LABEL_15:
    *((_QWORD *)&v8 + 1) = 0;
    goto LABEL_16;
  }
  *((_QWORD *)&v8 + 1) = 1;
LABEL_16:
  *(_OWORD *)a1 = v8;
  return result;
}

```

## disassembly

```asm
0x18000e650  mov     [rsp-8+arg_0], rbx
0x18000e655  push    rbp
0x18000e656  mov     rbp, rsp
0x18000e659  sub     rsp, 40h
0x18000e65d  mov     al, [rdx]
0x18000e65f  mov     rbx, rcx
0x18000e662  cmp     al, 0FFh
0x18000e664  jz      loc_18000E779
0x18000e66a  test    dword ptr [rdx], 100h
0x18000e670  jnz     loc_18000E779
0x18000e676  test    al, al
0x18000e678  jnz     short loc_18000E69C
0x18000e67a  cmp     byte ptr [rdx+8], 0
0x18000e67e  mov     rax, rcx
0x18000e681  mov     qword ptr [rbp+var_10], 6
0x18000e689  jz      loc_18000E784
0x18000e68f  mov     qword ptr [rbp+var_10+8], 1
0x18000e697  jmp     loc_18000E78C
0x18000e69c  cmp     al, 0Dh
0x18000e69e  jnz     short loc_18000E6C0
0x18000e6a0  mov     rdx, [rdx+8]
0x18000e6a4  lea     rcx, [rbp+var_10]
0x18000e6a8  mov     rdx, [rdx+10h]
0x18000e6ac  call    MintValue_CoerceToNumber_String
0x18000e6b1  movups  xmm0, xmmword ptr [rax]
0x18000e6b4  movdqu  xmmword ptr [rbx], xmm0
0x18000e6b8  mov     rax, rbx
0x18000e6bb  jmp     loc_18000E794
0x18000e6c0  cmp     al, 0Fh
0x18000e6c2  jnz     loc_18000E762
0x18000e6c8  mov     rcx, [rdx+8]
0x18000e6cc  mov     rax, cs:off_180047B90
0x18000e6d3  mov     rcx, [rcx+18h]
0x18000e6d7  mov     rax, [rax+8]
0x18000e6db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6e0  test    rax, rax
0x18000e6e3  jz      short loc_18000E762
0x18000e6e5  xorps   xmm0, xmm0
0x18000e6e8  lea     rcx, ModuleName; "mpunits.dll"
0x18000e6ef  movups  [rbp+var_10], xmm0
0x18000e6f3  call    cs:__imp_GetModuleHandleA
0x18000e6f9  mov     rcx, rax
0x18000e6fc  mov     edx, 812h
0x18000e701  call    _Intlstr_GetString_LoadString
0x18000e706  mov     qword ptr [rbp+var_10], rax
0x18000e70a  lea     r9, [rbp+var_10]
0x18000e70e  mov     byte ptr [rbp+var_10+8], 0
0x18000e712  lea     rdx, aMi; "MI"
0x18000e719  movaps  xmm0, [rbp+var_10]
0x18000e71d  mov     r8d, 0Bh
0x18000e723  mov     [rsp+40h+var_18], 0; __int64
0x18000e72c  movdqa  [rbp+var_10], xmm0
0x18000e731  mov     [rsp+40h+var_20], 0; __int64
0x18000e73a  lea     ecx, [r8-4]; int
0x18000e73e  call    MI_ReportErrorDetails_ForCustomError
0x18000e743  xor     edx, edx
0x18000e745  xor     ecx, ecx
0x18000e747  mov     eax, 0FFh
0x18000e74c  mov     [rbx+4], edx
0x18000e74f  and     eax, 0FFFFFFFEh
0x18000e752  mov     [rbx+8], rcx
0x18000e756  or      eax, 0FEh
0x18000e75b  mov     [rbx], eax
0x18000e75d  jmp     loc_18000E6B8
0x18000e762  xor     eax, eax
0x18000e764  mov     qword ptr [rbp+var_10], 0FFh
0x18000e76c  mov     qword ptr [rbp+var_10+8], rax
0x18000e770  movups  xmm0, [rbp+var_10]
0x18000e774  jmp     loc_18000E6B4
0x18000e779  mov     qword ptr [rbp+var_10], 6
0x18000e781  mov     rax, rbx
0x18000e784  mov     qword ptr [rbp+var_10+8], 0
0x18000e78c  movups  xmm0, [rbp+var_10]
0x18000e790  movdqu  xmmword ptr [rcx], xmm0
0x18000e794  mov     rbx, [rsp+40h+arg_0]
0x18000e799  add     rsp, 40h
0x18000e79d  pop     rbp
0x18000e79e  retn
```
