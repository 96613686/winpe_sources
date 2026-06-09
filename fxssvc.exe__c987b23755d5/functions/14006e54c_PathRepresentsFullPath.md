# PathRepresentsFullPath

- ea: `0x14006e54c`
- end: `0x14006e6d3`
- name: `PathRepresentsFullPath`
- size: `391`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x14000b9bc`
- `0x14001e140`
- `0x14004fdac`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140065d14`
- `0x140065dbc`
- `0x14006e54c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14006e603`
- `KERNEL32!GetLastError` at `0x14006e692`
- `KERNEL32!GetLastError` at `0x14006e603`
- `KERNEL32!GetLastError` at `0x14006e692`
- `KERNEL32!GetFullPathNameW` at `0x14006e5d3`
- `KERNEL32!GetFullPathNameW` at `0x14006e670`
- `KERNEL32!GetFullPathNameW` at `0x14006e5d3`
- `KERNEL32!GetFullPathNameW` at `0x14006e670`
- `msvcrt!_wcsicmp` at `0x14006e6ac`
- `msvcrt!_wcsicmp` at `0x14006e6ac`

## pseudocode

```c
_BOOL8 __fastcall PathRepresentsFullPath(wchar_t *String1)
{
  CMapDeviceId *v2; // rcx
  BOOL v4; // esi
  DWORD FullPathNameW; // eax
  wchar_t *v6; // rbx
  DWORD LastError; // eax
  __int64 v8; // rdx
  DWORD v9; // ebp
  WCHAR *v10; // rax
  DWORD v11; // eax

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( String1 )
  {
    v4 = 0;
    FullPathNameW = GetFullPathNameW(String1, 0, 0, 0);
    if ( FullPathNameW )
    {
      v9 = FullPathNameW + 1;
      v10 = (WCHAR *)pMemAlloc(2LL * (FullPathNameW + 1));
      v6 = v10;
      if ( !v10 )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids);
        }
        goto LABEL_29;
      }
      v11 = GetFullPathNameW(String1, v9, v10, 0);
      if ( v11 )
      {
        if ( v11 <= v9 )
          v4 = _wcsicmp(String1, v6) == 0;
        goto LABEL_29;
      }
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_29:
        pMemFree(v6);
        return v4;
      }
      LastError = GetLastError();
      v8 = 105;
    }
    else
    {
      v6 = 0;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_29;
      }
      LastError = GetLastError();
      v8 = 103;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, LastError);
    goto LABEL_29;
  }
  if ( v2 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 2) != 0 && *((_BYTE *)v2 + 25) >= 2u )
    WPP_SF_(*((_QWORD *)v2 + 2), 102, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x14006e54c  push    rbx
0x14006e54e  push    rbp
0x14006e54f  push    rsi
0x14006e550  push    rdi
0x14006e551  push    r12
0x14006e553  push    r15
0x14006e555  sub     rsp, 28h
0x14006e559  mov     rdi, rcx
0x14006e55c  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e563  lea     r15, WPP_GLOBAL_Control
0x14006e56a  lea     r12, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x14006e571  cmp     rcx, r15
0x14006e574  jz      short loc_14006E59A
0x14006e576  test    byte ptr [rcx+1Ch], 2
0x14006e57a  jz      short loc_14006E59A
0x14006e57c  cmp     byte ptr [rcx+19h], 5
0x14006e580  jb      short loc_14006E59A
0x14006e582  mov     rcx, [rcx+10h]
0x14006e586  mov     edx, 65h ; 'e'
0x14006e58b  mov     r8, r12
0x14006e58e  call    WPP_SF_
0x14006e593  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e59a  test    rdi, rdi
0x14006e59d  jnz     short loc_14006E5C6
0x14006e59f  cmp     rcx, r15
0x14006e5a2  jz      short loc_14006E5BF
0x14006e5a4  test    byte ptr [rcx+1Ch], 2
0x14006e5a8  jz      short loc_14006E5BF
0x14006e5aa  cmp     byte ptr [rcx+19h], 2
0x14006e5ae  jb      short loc_14006E5BF
0x14006e5b0  mov     rcx, [rcx+10h]
0x14006e5b4  lea     edx, [rdi+66h]
0x14006e5b7  mov     r8, r12
0x14006e5ba  call    WPP_SF_
0x14006e5bf  xor     eax, eax
0x14006e5c1  jmp     loc_14006E6C6
0x14006e5c6  xor     r9d, r9d; lpFilePart
0x14006e5c9  xor     r8d, r8d; lpBuffer
0x14006e5cc  xor     edx, edx; nBufferLength
0x14006e5ce  mov     rcx, rdi; lpFileName
0x14006e5d1  xor     esi, esi
0x14006e5d3  call    cs:__imp_GetFullPathNameW
0x14006e5d9  test    eax, eax
0x14006e5db  jnz     short loc_14006E627
0x14006e5dd  xor     ebx, ebx
0x14006e5df  mov     rax, cs:WPP_GLOBAL_Control
0x14006e5e6  cmp     rax, r15
0x14006e5e9  jz      loc_14006E6BC
0x14006e5ef  test    byte ptr [rax+1Ch], 2
0x14006e5f3  jz      loc_14006E6BC
0x14006e5f9  cmp     byte ptr [rax+19h], 2
0x14006e5fd  jb      loc_14006E6BC
0x14006e603  call    cs:__imp_GetLastError
0x14006e609  lea     edx, [rsi+67h]
0x14006e60c  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e613  mov     r9d, eax
0x14006e616  mov     r8, r12
0x14006e619  mov     rcx, [rcx+10h]
0x14006e61d  call    WPP_SF_d
0x14006e622  jmp     loc_14006E6BC
0x14006e627  lea     ebp, [rax+1]
0x14006e62a  mov     ecx, ebp
0x14006e62c  add     rcx, rcx; dwBytes
0x14006e62f  call    pMemAlloc
0x14006e634  mov     rbx, rax
0x14006e637  test    rax, rax
0x14006e63a  jnz     short loc_14006E665
0x14006e63c  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e643  cmp     rcx, r15
0x14006e646  jz      short loc_14006E6BC
0x14006e648  test    byte ptr [rcx+1Ch], 2
0x14006e64c  jz      short loc_14006E6BC
0x14006e64e  cmp     byte ptr [rcx+19h], 2
0x14006e652  jb      short loc_14006E6BC
0x14006e654  mov     rcx, [rcx+10h]
0x14006e658  lea     edx, [rax+68h]
0x14006e65b  mov     r8, r12
0x14006e65e  call    WPP_SF_
0x14006e663  jmp     short loc_14006E6BC
0x14006e665  xor     r9d, r9d; lpFilePart
0x14006e668  mov     r8, rbx; lpBuffer
0x14006e66b  mov     edx, ebp; nBufferLength
0x14006e66d  mov     rcx, rdi; lpFileName
0x14006e670  call    cs:__imp_GetFullPathNameW
0x14006e676  test    eax, eax
0x14006e678  jnz     short loc_14006E6A2
0x14006e67a  mov     rax, cs:WPP_GLOBAL_Control
0x14006e681  cmp     rax, r15
0x14006e684  jz      short loc_14006E6BC
0x14006e686  test    byte ptr [rax+1Ch], 2
0x14006e68a  jz      short loc_14006E6BC
0x14006e68c  cmp     byte ptr [rax+19h], 2
0x14006e690  jb      short loc_14006E6BC
0x14006e692  call    cs:__imp_GetLastError
0x14006e698  mov     edx, 69h ; 'i'
0x14006e69d  jmp     loc_14006E60C
0x14006e6a2  cmp     eax, ebp
0x14006e6a4  ja      short loc_14006E6BC
0x14006e6a6  mov     rdx, rbx; String2
0x14006e6a9  mov     rcx, rdi; String1
0x14006e6ac  call    cs:__imp__wcsicmp
0x14006e6b2  test    eax, eax
0x14006e6b4  mov     ecx, 1
0x14006e6b9  cmovz   esi, ecx
0x14006e6bc  mov     rcx, rbx; lpMem
0x14006e6bf  call    pMemFree
0x14006e6c4  mov     eax, esi
0x14006e6c6  add     rsp, 28h
0x14006e6ca  pop     r15
0x14006e6cc  pop     r12
0x14006e6ce  pop     rdi
0x14006e6cf  pop     rsi
0x14006e6d0  pop     rbp
0x14006e6d1  pop     rbx
0x14006e6d2  retn
```
