# PropertyNotInShippedSchema(CWriter *,ulong)

- ea: `0x180011a38`
- end: `0x180011bbf`
- name: `?PropertyNotInShippedSchema@@YAHPEAVCWriter@@K@Z`
- size: `391`
- prototype: `__int64 __fastcall(struct CWriter *, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180011c74`
- `0x180011e74`
- `0x180012938`

## callees

- `0x180011a38`
- `0x180012c94`
- `0x18003099a`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x180011b96`
- `IisRTL!PuDbgPrintW` at `0x180011b96`

## pseudocode

```c
__int64 __fastcall PropertyNotInShippedSchema(struct CWriter *a1, unsigned int a2)
{
  __int64 v3; // rcx
  unsigned int v4; // ebx
  int v5; // eax
  __int64 v7; // [rsp+28h] [rbp-D8h]
  unsigned int v8; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v9; // [rsp+48h] [rbp-B8h] BYREF
  int v10; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v11[2]; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD *v12; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v13[18]; // [rsp+70h] [rbp-90h] BYREF

  v9 = a2;
  v11[0] = 0;
  v11[1] = 13;
  memset_0(v13, 0, sizeof(v13));
  v3 = *((_QWORD *)a1 + 8200);
  v4 = 1;
  v13[0] = *(_QWORD *)(v3 + 232);
  v13[13] = &v9;
  v8 = 0;
  v10 = 12;
  v12 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _DWORD *, _QWORD, _QWORD *, unsigned int *))(**(_QWORD **)(v3 + 48) + 56LL))(
         *(_QWORD *)(v3 + 48),
         0,
         2,
         v11,
         0,
         v13,
         &v8);
  if ( v5 < 0
    || (v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, int *, _QWORD, _DWORD **))(**(_QWORD **)(*((_QWORD *)a1 + 8200) + 48LL)
                                                                                          + 32LL))(
               *(_QWORD *)(*((_QWORD *)a1 + 8200) + 48LL),
               v8,
               1,
               &v10,
               0,
               &v12),
        v5 < 0) )
  {
    if ( v5 == -2145318890 )
    {
      return (unsigned int)TagNotInShippedSchema(a1, v9);
    }
    else if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v7) = v5;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\saveschema.cpp",
        873,
        "PropertyNotInShippedSchema",
        L"[PropertyNotInShippedSchema] Internal catalog error. Could not determine if property was not in shipped schema. "
         "Assuming it is not. hr = 0x%x.\n",
        v7);
    }
  }
  else
  {
    return (*v12 & 0x500) != 0;
  }
  return v4;
}

```

## disassembly

```asm
0x180011a38  mov     [rsp-8+arg_10], rbx
0x180011a3d  mov     [rsp-8+arg_18], rdi
0x180011a42  push    rbp
0x180011a43  lea     rbp, [rsp-10h]
0x180011a48  sub     rsp, 110h
0x180011a4f  mov     rax, cs:__security_cookie
0x180011a56  xor     rax, rsp
0x180011a59  mov     [rbp+10h+var_10], rax
0x180011a5d  mov     rdi, rcx
0x180011a60  mov     [rsp+110h+var_C8], edx
0x180011a64  xor     edx, edx; Val
0x180011a66  mov     [rsp+110h+var_B8], 0
0x180011a6e  lea     rcx, [rsp+110h+var_A0]; void *
0x180011a73  mov     [rsp+110h+var_B4], 0Dh
0x180011a7b  mov     r8d, 90h; Size
0x180011a81  call    memset_0
0x180011a86  mov     rcx, [rdi+10040h]
0x180011a8d  lea     rdx, [rsp+110h+var_D0]
0x180011a92  mov     [rsp+110h+var_E0], rdx
0x180011a97  lea     r9, [rsp+110h+var_B8]
0x180011a9c  lea     rdx, [rsp+110h+var_A0]
0x180011aa1  mov     ebx, 1
0x180011aa6  mov     [rsp+110h+var_E8], rdx
0x180011aab  xor     edx, edx
0x180011aad  mov     rax, [rcx+0E8h]
0x180011ab4  mov     [rsp+110h+var_A0], rax
0x180011ab9  lea     rax, [rsp+110h+var_C8]
0x180011abe  mov     [rbp+10h+var_38], rax
0x180011ac2  lea     r8d, [rbx+1]
0x180011ac6  mov     [rsp+110h+var_D0], 0
0x180011ace  mov     [rsp+110h+var_C0], 0Ch
0x180011ad6  mov     [rsp+110h+var_B0], 0
0x180011adf  mov     rcx, [rcx+30h]
0x180011ae3  mov     [rsp+110h+var_F0], 0
0x180011aec  mov     rax, [rcx]
0x180011aef  mov     rax, [rax+38h]
0x180011af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011af8  test    eax, eax
0x180011afa  js      short loc_180011B47
0x180011afc  mov     rax, [rdi+10040h]
0x180011b03  lea     rdx, [rsp+110h+var_B0]
0x180011b08  mov     [rsp+110h+var_E8], rdx
0x180011b0d  lea     r9, [rsp+110h+var_C0]
0x180011b12  mov     edx, [rsp+110h+var_D0]
0x180011b16  mov     r8d, ebx
0x180011b19  mov     [rsp+110h+var_F0], 0
0x180011b22  mov     rcx, [rax+30h]
0x180011b26  mov     rax, [rcx]
0x180011b29  mov     rax, [rax+20h]
0x180011b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b32  test    eax, eax
0x180011b34  js      short loc_180011B47
0x180011b36  mov     rax, [rsp+110h+var_B0]
0x180011b3b  test    dword ptr [rax], 500h
0x180011b41  jnz     short loc_180011B9C
0x180011b43  xor     ebx, ebx
0x180011b45  jmp     short loc_180011B9C
0x180011b47  cmp     eax, 80210816h
0x180011b4c  jnz     short loc_180011B5E
0x180011b4e  mov     edx, [rsp+110h+var_C8]; unsigned int
0x180011b52  mov     rcx, rdi; struct CWriter *
0x180011b55  call    ?TagNotInShippedSchema@@YAHPEAVCWriter@@K@Z; TagNotInShippedSchema(CWriter *,ulong)
0x180011b5a  mov     ebx, eax
0x180011b5c  jmp     short loc_180011B9C
0x180011b5e  test    eax, eax
0x180011b60  jns     short loc_180011B9C
0x180011b62  test    byte ptr cs:g_dwDebugFlags, 3
0x180011b69  jz      short loc_180011B9C
0x180011b6b  mov     rcx, cs:g_pDebug
0x180011b72  lea     r9, aPropertynotins_0; "PropertyNotInShippedSchema"
0x180011b79  mov     dword ptr [rsp+110h+var_E8], eax
0x180011b7d  lea     rdx, aInetsrvIisMbMe_4; "inetsrv\\iis\\mb\\metadata\\saveschema."...
0x180011b84  lea     rax, aPropertynotins; "[PropertyNotInShippedSchema] Internal c"...
0x180011b8b  mov     r8d, 369h
0x180011b91  mov     [rsp+110h+var_F0], rax
0x180011b96  call    cs:__imp_PuDbgPrintW
0x180011b9c  mov     eax, ebx
0x180011b9e  mov     rcx, [rbp+10h+var_10]
0x180011ba2  xor     rcx, rsp; StackCookie
0x180011ba5  call    __security_check_cookie
0x180011baa  lea     r11, [rsp+110h+var_s0]
0x180011bb2  mov     rbx, [r11+20h]
0x180011bb6  mov     rdi, [r11+28h]
0x180011bba  mov     rsp, r11
0x180011bbd  pop     rbp
0x180011bbe  retn
```
