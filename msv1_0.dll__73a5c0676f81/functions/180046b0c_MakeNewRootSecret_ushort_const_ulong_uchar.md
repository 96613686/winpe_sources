# MakeNewRootSecret(ushort const *,ulong *,uchar * *)

- ea: `0x180046b0c`
- end: `0x180046b92`
- name: `?MakeNewRootSecret@@YAJPEBGPEAKPEAPEAE@Z`
- size: `134`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800483a4`

## callees

- `0x180046b0c`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046b74`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046b74`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046b58`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046b58`

## pseudocode

```c
__int64 __fastcall MakeNewRootSecret(LPCWSTR lpValueName, unsigned int *a2, const BYTE **a3)
{
  signed int v6; // ebx
  LSTATUS v7; // eax

  v6 = (*(__int64 (__fastcall **)(struct NtlmCredIsoApi *))(*(_QWORD *)LocalhostNtLmCredIsoObj::IsoObj + 104LL))(LocalhostNtLmCredIsoObj::IsoObj);
  if ( v6 >= 0 )
  {
    v7 = RegSetValueExW(NtLmGlobalLsaMsv1_0Key, lpValueName, 0, 3u, *a3, *a2);
    if ( v7 )
    {
      if ( v7 > 0 )
        v6 = (unsigned __int16)v7 | 0xC0070000;
      else
        v6 = v7;
      LocalFree((HLOCAL)*a3);
      *a3 = 0;
      *a2 = 0;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180046b0c  push    rbx
0x180046b0e  push    rbp
0x180046b0f  push    rsi
0x180046b10  push    rdi
0x180046b11  sub     rsp, 38h
0x180046b15  mov     rbp, rcx
0x180046b18  mov     rdi, r8
0x180046b1b  mov     rcx, cs:?IsoObj@LocalhostNtLmCredIsoObj@@0PEAVNtlmCredIsoApi@@EA; NtlmCredIsoApi * LocalhostNtLmCredIsoObj::IsoObj
0x180046b22  mov     rsi, rdx
0x180046b25  mov     rax, [rcx]
0x180046b28  mov     rax, [rax+68h]
0x180046b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046b31  mov     ebx, eax
0x180046b33  test    eax, eax
0x180046b35  js      short loc_180046B87
0x180046b37  mov     ecx, [rsi]
0x180046b39  mov     r9d, 3; dwType
0x180046b3f  mov     [rsp+58h+cbData], ecx; cbData
0x180046b43  xor     r8d, r8d; Reserved
0x180046b46  mov     rcx, [rdi]
0x180046b49  mov     rdx, rbp; lpValueName
0x180046b4c  mov     [rsp+58h+lpData], rcx; lpData
0x180046b51  mov     rcx, cs:NtLmGlobalLsaMsv1_0Key; hKey
0x180046b58  call    cs:__imp_RegSetValueExW
0x180046b5e  test    eax, eax
0x180046b60  jz      short loc_180046B87
0x180046b62  jg      short loc_180046B68
0x180046b64  mov     ebx, eax
0x180046b66  jmp     short loc_180046B71
0x180046b68  movzx   ebx, ax
0x180046b6b  or      ebx, 0C0070000h
0x180046b71  mov     rcx, [rdi]; hMem
0x180046b74  call    cs:__imp_LocalFree
0x180046b7a  mov     qword ptr [rdi], 0
0x180046b81  mov     dword ptr [rsi], 0
0x180046b87  mov     eax, ebx
0x180046b89  add     rsp, 38h
0x180046b8d  pop     rdi
0x180046b8e  pop     rsi
0x180046b8f  pop     rbp
0x180046b90  pop     rbx
0x180046b91  retn
```
