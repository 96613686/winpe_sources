# AppendDisabledPorts

- ea: `0x180011a54`
- end: `0x180011b6f`
- name: `AppendDisabledPorts`
- size: `283`
- prototype: `_BOOL8 __fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800126c8`
- `0x180013b90`

## callees

- `0x180011a54`
- `0x18003b57c`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180011ab9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180011acb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180011ab9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180011acb`
- `RASAPI32!SetDefaultModemSettings` at `0x180011b17`
- `RASAPI32!SetDefaultModemSettings` at `0x180011b17`
- `RASAPI32!CopyToPbport` at `0x180011af3`
- `RASAPI32!CopyToPbport` at `0x180011af3`
- `RASAPI32!DestroyLinkNode` at `0x180011b00`
- `RASAPI32!DestroyLinkNode` at `0x180011b00`
- `RASAPI32!CreateLinkNode` at `0x180011adb`
- `RASAPI32!CreateLinkNode` at `0x180011adb`

## pseudocode

```c
_BOOL8 __fastcall AppendDisabledPorts(__int64 a1, int a2)
{
  __int64 i; // rbx
  __int64 v5; // rdi
  __int64 j; // rbp
  LPCWSTR *v7; // r14
  __int64 LinkNode; // rax
  __int64 v9; // rbp
  __int64 v10; // r14
  _BOOL8 result; // rax

  for ( i = **(_QWORD **)(a1 + 880); i; i = *(_QWORD *)(i + 8) )
  {
    v5 = *(_QWORD *)(i + 16);
    if ( a2 != -1 )
    {
      if ( a2 == -2 )
      {
        if ( *(_DWORD *)(v5 + 44) == 2 )
          continue;
      }
      else if ( *(_DWORD *)(v5 + 44) != a2 )
      {
        continue;
      }
    }
    for ( j = **(_QWORD **)(*(_QWORD *)(a1 + 872) + 32LL); j; j = *(_QWORD *)(j + 8) )
    {
      v7 = *(LPCWSTR **)(j + 16);
      if ( !lstrcmpW(*v7, *(LPCWSTR *)v5) && !lstrcmpW(v7[2], *(LPCWSTR *)(v5 + 16)) )
        goto LABEL_19;
    }
    LinkNode = CreateLinkNode();
    v9 = LinkNode;
    if ( LinkNode )
    {
      v10 = *(_QWORD *)(LinkNode + 16);
      if ( (unsigned int)CopyToPbport(v10, v5) )
      {
        DestroyLinkNode(v9);
      }
      else
      {
        if ( *(_DWORD *)(v5 + 40) == 3 || (*(_BYTE *)(v5 + 48) & 4) != 0 )
          SetDefaultModemSettings(v10);
        *(_DWORD *)(v10 + 188) = 0;
        DtlAddNodeLast(*(_QWORD *)(*(_QWORD *)(a1 + 872) + 32LL), v9);
      }
    }
LABEL_19:
    ;
  }
  result = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 872) + 32LL) + 16LL) > 1;
  *(_DWORD *)(a1 + 324) = result;
  return result;
}

```

## disassembly

```asm
0x180011a54  push    rbx
0x180011a56  push    rbp
0x180011a57  push    rsi
0x180011a58  push    rdi
0x180011a59  push    r14
0x180011a5b  push    r15
0x180011a5d  sub     rsp, 28h
0x180011a61  mov     rax, [rcx+370h]
0x180011a68  mov     r15d, edx
0x180011a6b  mov     rsi, rcx
0x180011a6e  mov     rbx, [rax]
0x180011a71  jmp     loc_180011B3F
0x180011a76  mov     rdi, [rbx+10h]
0x180011a7a  cmp     r15d, 0FFFFFFFFh
0x180011a7e  jz      short loc_180011A9C
0x180011a80  cmp     r15d, 0FFFFFFFEh
0x180011a84  jnz     short loc_180011A92
0x180011a86  cmp     dword ptr [rdi+2Ch], 2
0x180011a8a  jz      loc_180011B3B
0x180011a90  jmp     short loc_180011A9C
0x180011a92  cmp     [rdi+2Ch], r15d
0x180011a96  jnz     loc_180011B3B
0x180011a9c  mov     rax, [rsi+368h]
0x180011aa3  mov     rcx, [rax+20h]
0x180011aa7  mov     rbp, [rcx]
0x180011aaa  test    rbp, rbp
0x180011aad  jz      short loc_180011ADB
0x180011aaf  mov     r14, [rbp+10h]
0x180011ab3  mov     rdx, [rdi]; lpString2
0x180011ab6  mov     rcx, [r14]; lpString1
0x180011ab9  call    cs:__imp_lstrcmpW
0x180011abf  test    eax, eax
0x180011ac1  jnz     short loc_180011AD5
0x180011ac3  mov     rdx, [rdi+10h]; lpString2
0x180011ac7  mov     rcx, [r14+10h]; lpString1
0x180011acb  call    cs:__imp_lstrcmpW
0x180011ad1  test    eax, eax
0x180011ad3  jz      short loc_180011B3B
0x180011ad5  mov     rbp, [rbp+8]
0x180011ad9  jmp     short loc_180011AAA
0x180011adb  call    cs:__imp_CreateLinkNode
0x180011ae1  mov     rbp, rax
0x180011ae4  test    rax, rax
0x180011ae7  jz      short loc_180011B3B
0x180011ae9  mov     r14, [rax+10h]
0x180011aed  mov     rdx, rdi
0x180011af0  mov     rcx, r14
0x180011af3  call    cs:__imp_CopyToPbport
0x180011af9  test    eax, eax
0x180011afb  jz      short loc_180011B08
0x180011afd  mov     rcx, rbp
0x180011b00  call    cs:__imp_DestroyLinkNode
0x180011b06  jmp     short loc_180011B3B
0x180011b08  cmp     dword ptr [rdi+28h], 3
0x180011b0c  jz      short loc_180011B14
0x180011b0e  test    byte ptr [rdi+30h], 4
0x180011b12  jz      short loc_180011B1D
0x180011b14  mov     rcx, r14
0x180011b17  call    cs:__imp_SetDefaultModemSettings
0x180011b1d  mov     dword ptr [r14+0BCh], 0
0x180011b28  mov     rdx, rbp
0x180011b2b  mov     rcx, [rsi+368h]
0x180011b32  mov     rcx, [rcx+20h]
0x180011b36  call    DtlAddNodeLast
0x180011b3b  mov     rbx, [rbx+8]
0x180011b3f  test    rbx, rbx
0x180011b42  jnz     loc_180011A76
0x180011b48  mov     rax, [rsi+368h]
0x180011b4f  mov     rcx, [rax+20h]
0x180011b53  xor     eax, eax
0x180011b55  cmp     dword ptr [rcx+10h], 1
0x180011b59  setnle  al
0x180011b5c  mov     [rsi+144h], eax
0x180011b62  add     rsp, 28h
0x180011b66  pop     r15
0x180011b68  pop     r14
0x180011b6a  pop     rdi
0x180011b6b  pop     rsi
0x180011b6c  pop     rbp
0x180011b6d  pop     rbx
0x180011b6e  retn
```
