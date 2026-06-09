# RegDeleteTreeW

- ea: `0x1800a3c00`
- end: `0x1800a3edf`
- name: `RegDeleteTreeW`
- size: `735`
- prototype: `LSTATUS __stdcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `7`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x1800883b0`
- `0x18009e74c`
- `0x18010fbd0`
- `0x18012a9e4`
- `0x180135098`
- `0x18014cb60`
- `0x180177464`

## callees

- `0x18005e040`
- `0x18005e320`
- `0x1800a3c00`
- `0x1800a41b0`
- `0x1800a4a40`
- `0x1800e48e8`
- `0x1801369c9`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800a3d8a`
- `ntdll!RtlFreeUnicodeString` at `0x1800a3dbf`
- `ntdll!RtlFreeUnicodeString` at `0x1800a3dde`
- `ntdll!RtlFreeUnicodeString` at `0x1800a3d8a`
- `ntdll!RtlFreeUnicodeString` at `0x1800a3dbf`
- `ntdll!RtlFreeUnicodeString` at `0x1800a3dde`
- `ntdll!RtlCreateUnicodeString` at `0x1800a3c9e`
- `ntdll!RtlCreateUnicodeString` at `0x1800a3e72`
- `ntdll!RtlCreateUnicodeString` at `0x1800a3c9e`
- `ntdll!RtlCreateUnicodeString` at `0x1800a3e72`
- `ntdll!RtlFreeHeap` at `0x1800a3dfc`
- `ntdll!RtlFreeHeap` at `0x1800a3e1a`
- `ntdll!RtlFreeHeap` at `0x1800a3dfc`
- `ntdll!RtlFreeHeap` at `0x1800a3e1a`
- `ntdll!RtlAllocateHeap` at `0x1800a3c3a`
- `ntdll!RtlAllocateHeap` at `0x1800a3c74`
- `ntdll!RtlAllocateHeap` at `0x1800a3c3a`
- `ntdll!RtlAllocateHeap` at `0x1800a3c74`

## pseudocode

```c
LSTATUS __stdcall RegDeleteTreeW(HKEY hKey, LPCWSTR lpSubKey)
{
  char *Heap; // rax
  char *v5; // rsi
  WCHAR *v6; // r12
  LSTATUS v7; // edi
  int v8; // ebp
  LSTATUS v9; // eax
  __int64 v10; // rdx
  LSTATUS v11; // eax
  char *v12; // rbx
  struct _UNICODE_STRING *v13; // rcx
  __int64 v15; // r15
  DWORD cchName; // [rsp+90h] [rbp+18h] BYREF
  HKEY hKeya; // [rsp+98h] [rbp+20h] BYREF

  hKeya = 0;
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x3000u);
  v5 = Heap;
  if ( !Heap )
    return 8;
  memset_0(Heap, 0, 0x3000u);
  v6 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x202u);
  if ( v6 )
  {
    if ( !lpSubKey || !*lpSubKey || RtlCreateUnicodeString((PUNICODE_STRING)(v5 + 8), lpSubKey) )
    {
      v8 = 0;
      *(_QWORD *)v5 = hKey;
      v7 = 0;
      while ( 1 )
      {
        while ( 1 )
        {
          if ( v8 < 0 )
            goto LABEL_20;
          v7 = RegOpenKeyExInternalW(*(HKEY *)&v5[24 * v8], *(PCWSTR *)&v5[24 * v8 + 16], (PHANDLE)&hKeya, 0);
          if ( v7 )
            goto LABEL_18;
          cchName = 257;
          v9 = RegEnumKeyExW(hKeya, 0, v6, &cchName, 0, 0, 0, 0);
          v7 = v9;
          if ( v9 != 259 )
            break;
          v10 = *(_QWORD *)&v5[24 * v8 + 16];
          if ( v10 )
            v11 = RegDeleteKeyExInternalW(*(_QWORD *)&v5[24 * v8], v10, 0, 0, 0);
          else
            v11 = DeleteAllKeyValues(hKey);
          v7 = v11;
          RegCloseKey(hKeya);
          if ( v7 )
            goto LABEL_18;
          v12 = &v5[24 * v8];
          RtlFreeUnicodeString((PUNICODE_STRING)(v12 + 8));
          *(_OWORD *)(v12 + 8) = 0;
          if ( v8 > 0 )
          {
            RegCloseKey(*(HKEY *)&v5[24 * v8]);
            *(_QWORD *)&v5[24 * v8] = 0;
          }
          --v8;
        }
        if ( v9 )
          break;
        if ( v8 + 1 >= 512
          || (v15 = v8 + 1LL, v6[cchName] = 0, !RtlCreateUnicodeString((PUNICODE_STRING)&v5[24 * v15 + 8], v6)) )
        {
          RegCloseKey(hKeya);
          v7 = 8;
LABEL_18:
          while ( 1 )
          {
            v13 = (struct _UNICODE_STRING *)(v5 + 8);
            if ( v8 <= 0 )
              break;
            RtlFreeUnicodeString((struct _UNICODE_STRING *)((char *)v13 + 24 * (unsigned int)v8));
            RegCloseKey(*(HKEY *)&v5[24 * v8--]);
          }
          RtlFreeUnicodeString(v13);
          goto LABEL_20;
        }
        ++v8;
        *(_QWORD *)&v5[24 * v15] = hKeya;
      }
      RegCloseKey(hKeya);
      goto LABEL_18;
    }
    v7 = 8;
LABEL_20:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  }
  else
  {
    v7 = 8;
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  return v7;
}

```

## disassembly

```asm
0x1800a3c00  mov     rax, rsp
0x1800a3c03  mov     [rax+8], rbx
0x1800a3c07  push    rbp
0x1800a3c08  push    rsi
0x1800a3c09  push    rdi
0x1800a3c0a  push    r12
0x1800a3c0c  push    r13
0x1800a3c0e  push    r14
0x1800a3c10  push    r15
0x1800a3c12  sub     rsp, 40h
0x1800a3c16  mov     r13, rcx
0x1800a3c19  mov     rbx, rdx
0x1800a3c1c  xor     r15d, r15d
0x1800a3c1f  mov     edi, 3000h
0x1800a3c24  mov     [rax+20h], r15
0x1800a3c28  mov     r8d, edi; Size
0x1800a3c2b  mov     rcx, gs:60h
0x1800a3c34  xor     edx, edx; Flags
0x1800a3c36  mov     rcx, [rcx+30h]; HeapHandle
0x1800a3c3a  call    cs:__imp_RtlAllocateHeap
0x1800a3c41  nop     dword ptr [rax+rax+00h]
0x1800a3c46  mov     rsi, rax
0x1800a3c49  test    rax, rax
0x1800a3c4c  jz      loc_1800A3EC3
0x1800a3c52  mov     r8d, edi; Size
0x1800a3c55  xor     edx, edx; Val
0x1800a3c57  mov     rcx, rax; void *
0x1800a3c5a  call    memset_0
0x1800a3c5f  mov     rcx, gs:60h
0x1800a3c68  xor     edx, edx; Flags
0x1800a3c6a  mov     r8d, 202h; Size
0x1800a3c70  mov     rcx, [rcx+30h]; HeapHandle
0x1800a3c74  call    cs:__imp_RtlAllocateHeap
0x1800a3c7b  nop     dword ptr [rax+rax+00h]
0x1800a3c80  mov     r12, rax
0x1800a3c83  test    rax, rax
0x1800a3c86  jz      loc_1800A3E95
0x1800a3c8c  test    rbx, rbx
0x1800a3c8f  jz      short loc_1800A3CB7
0x1800a3c91  cmp     [rbx], r15w
0x1800a3c95  jz      short loc_1800A3CB7
0x1800a3c97  lea     rcx, [rsi+8]; DestinationString
0x1800a3c9b  mov     rdx, rbx; SourceString
0x1800a3c9e  call    cs:__imp_RtlCreateUnicodeString
0x1800a3ca5  nop     dword ptr [rax+rax+00h]
0x1800a3caa  test    al, al
0x1800a3cac  jnz     short loc_1800A3CB7
0x1800a3cae  lea     edi, [r15+8]
0x1800a3cb2  jmp     loc_1800A3DEA
0x1800a3cb7  mov     ebp, r15d
0x1800a3cba  mov     [rsi], r13
0x1800a3cbd  mov     edi, r15d
0x1800a3cc0  test    ebp, ebp
0x1800a3cc2  js      loc_1800A3DEA
0x1800a3cc8  lea     rax, [rsp+78h+hKey]
0x1800a3cd0  movsxd  r15, ebp
0x1800a3cd3  xor     ebx, ebx
0x1800a3cd5  mov     r9d, 2000000h
0x1800a3cdb  mov     [rsp+78h+lpClass], rbx; __int64
0x1800a3ce0  xor     r8d, r8d
0x1800a3ce3  mov     [rsp+78h+lpReserved], rax; PHANDLE
0x1800a3ce8  lea     r14, [r15+r15*2]
0x1800a3cec  mov     rdx, [rsi+r14*8+10h]; SourceString
0x1800a3cf1  mov     rcx, [rsi+r14*8]; hKey
0x1800a3cf5  call    RegOpenKeyExInternalW
0x1800a3cfa  mov     edi, eax
0x1800a3cfc  test    eax, eax
0x1800a3cfe  jnz     loc_1800A3DD6
0x1800a3d04  mov     rcx, [rsp+78h+hKey]; hKey
0x1800a3d0c  lea     r9, [rsp+78h+cchName]; lpcchName
0x1800a3d14  mov     [rsp+78h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x1800a3d19  mov     r8, r12; lpName
0x1800a3d1c  mov     [rsp+78h+lpcchClass], rbx; lpcchClass
0x1800a3d21  xor     edx, edx; dwIndex
0x1800a3d23  mov     [rsp+78h+lpClass], rbx; lpClass
0x1800a3d28  mov     [rsp+78h+lpReserved], rbx; lpReserved
0x1800a3d2d  mov     [rsp+78h+cchName], 101h
0x1800a3d38  call    RegEnumKeyExW
0x1800a3d3d  mov     edi, eax
0x1800a3d3f  cmp     eax, 103h
0x1800a3d44  jnz     loc_1800A3E41
0x1800a3d4a  mov     rdx, [rsi+r14*8+10h]
0x1800a3d4f  xor     r15d, r15d
0x1800a3d52  test    rdx, rdx
0x1800a3d55  jz      loc_1800A3E9F
0x1800a3d5b  mov     rcx, [rsi+r14*8]
0x1800a3d5f  xor     r9d, r9d
0x1800a3d62  xor     r8d, r8d
0x1800a3d65  mov     [rsp+78h+lpReserved], r15
0x1800a3d6a  call    RegDeleteKeyExInternalW
0x1800a3d6f  mov     rcx, [rsp+78h+hKey]; hKey
0x1800a3d77  mov     edi, eax
0x1800a3d79  call    RegCloseKey
0x1800a3d7e  test    edi, edi
0x1800a3d80  jnz     short loc_1800A3DD6
0x1800a3d82  lea     rbx, [rsi+r14*8]
0x1800a3d86  lea     rcx, [rbx+8]; UnicodeString
0x1800a3d8a  call    cs:__imp_RtlFreeUnicodeString
0x1800a3d91  nop     dword ptr [rax+rax+00h]
0x1800a3d96  xorps   xmm0, xmm0
0x1800a3d99  movups  xmmword ptr [rbx+8], xmm0
0x1800a3d9d  test    ebp, ebp
0x1800a3d9f  jle     short loc_1800A3DAE
0x1800a3da1  mov     rcx, [rsi+r14*8]; hKey
0x1800a3da5  call    RegCloseKey
0x1800a3daa  mov     [rsi+r14*8], r15
0x1800a3dae  dec     ebp
0x1800a3db0  jmp     loc_1800A3CC0
0x1800a3db5  mov     eax, ebp
0x1800a3db7  lea     rbx, [rax+rax*2]
0x1800a3dbb  lea     rcx, [rcx+rbx*8]; UnicodeString
0x1800a3dbf  call    cs:__imp_RtlFreeUnicodeString
0x1800a3dc6  nop     dword ptr [rax+rax+00h]
0x1800a3dcb  mov     rcx, [rsi+rbx*8]; hKey
0x1800a3dcf  call    RegCloseKey
0x1800a3dd4  dec     ebp
0x1800a3dd6  lea     rcx, [rsi+8]; UnicodeString
0x1800a3dda  test    ebp, ebp
0x1800a3ddc  jg      short loc_1800A3DB5
0x1800a3dde  call    cs:__imp_RtlFreeUnicodeString
0x1800a3de5  nop     dword ptr [rax+rax+00h]
0x1800a3dea  mov     rcx, gs:60h
0x1800a3df3  mov     r8, r12; P
0x1800a3df6  xor     edx, edx; Flags
0x1800a3df8  mov     rcx, [rcx+30h]; HeapHandle
0x1800a3dfc  call    cs:__imp_RtlFreeHeap
0x1800a3e03  nop     dword ptr [rax+rax+00h]
0x1800a3e08  mov     rcx, gs:60h
0x1800a3e11  mov     r8, rsi; P
0x1800a3e14  xor     edx, edx; Flags
0x1800a3e16  mov     rcx, [rcx+30h]; HeapHandle
0x1800a3e1a  call    cs:__imp_RtlFreeHeap
0x1800a3e21  nop     dword ptr [rax+rax+00h]
0x1800a3e26  mov     eax, edi
0x1800a3e28  mov     rbx, [rsp+78h+arg_0]
0x1800a3e30  add     rsp, 40h
0x1800a3e34  pop     r15
0x1800a3e36  pop     r14
0x1800a3e38  pop     r13
0x1800a3e3a  pop     r12
0x1800a3e3c  pop     rdi
0x1800a3e3d  pop     rsi
0x1800a3e3e  pop     rbp
0x1800a3e3f  retn
0x1800a3e41  test    eax, eax
0x1800a3e43  jnz     loc_1800A3ECD
0x1800a3e49  lea     ebx, [rbp+1]
0x1800a3e4c  cmp     ebx, 200h
0x1800a3e52  jge     short loc_1800A3EAC
0x1800a3e54  mov     ecx, [rsp+78h+cchName]
0x1800a3e5b  inc     r15
0x1800a3e5e  mov     rdx, r12; SourceString
0x1800a3e61  mov     [r12+rcx*2], ax
0x1800a3e66  lea     r14, [r15+r15*2]
0x1800a3e6a  lea     rcx, [rsi+8]
0x1800a3e6e  lea     rcx, [rcx+r14*8]; DestinationString
0x1800a3e72  call    cs:__imp_RtlCreateUnicodeString
0x1800a3e79  nop     dword ptr [rax+rax+00h]
0x1800a3e7e  test    al, al
0x1800a3e80  jz      short loc_1800A3EAC
0x1800a3e82  mov     rax, [rsp+78h+hKey]
0x1800a3e8a  mov     ebp, ebx
0x1800a3e8c  mov     [rsi+r14*8], rax
0x1800a3e90  jmp     loc_1800A3CC0
0x1800a3e95  mov     edi, 8
0x1800a3e9a  jmp     loc_1800A3E08
0x1800a3e9f  mov     rcx, r13; hKey
0x1800a3ea2  call    DeleteAllKeyValues
0x1800a3ea7  jmp     loc_1800A3D6F
0x1800a3eac  mov     rcx, [rsp+78h+hKey]; hKey
0x1800a3eb4  call    RegCloseKey
0x1800a3eb9  mov     edi, 8
0x1800a3ebe  jmp     loc_1800A3DD6
0x1800a3ec3  mov     eax, 8
0x1800a3ec8  jmp     loc_1800A3E28
0x1800a3ecd  mov     rcx, [rsp+78h+hKey]; hKey
0x1800a3ed5  call    RegCloseKey
0x1800a3eda  jmp     loc_1800A3DD6
```
