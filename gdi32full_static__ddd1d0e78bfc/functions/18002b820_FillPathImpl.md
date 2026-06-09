# FillPathImpl

- ea: `0x18002b820`
- end: `0x18002b8e3`
- name: `FillPathImpl`
- size: `195`
- prototype: `__int64 __fastcall(HDC hdc)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002b708`
- `0x18002b820`
- `0x18002bea8`

## import_xrefs

- `GDI32!StartPage` at `0x18002b8c2`
- `GDI32!StartPage` at `0x18002b8c2`
- `GDI32!pldcGet` at `0x18002b842`
- `GDI32!pldcGet` at `0x18002b842`
- `GDI32!GdiSetLastError` at `0x18002b8d5`
- `GDI32!GdiSetLastError` at `0x18002b8d5`
- `win32u!NtGdiFillPath` at `0x18002b8a3`
- `win32u!NtGdiFillPath` at `0x18002b8a3`

## pseudocode

```c
__int64 __fastcall FillPathImpl(HDC hdc)
{
  __int64 v2; // rax
  __int64 v3; // rbx

  if ( ((unsigned int)hdc & 0x7F0000) == 0x10000 )
    goto LABEL_11;
  if ( ((unsigned int)hdc & 0x7F0000) != 0x660000 )
  {
    v2 = pldcGet(hdc);
    v3 = v2;
    if ( v2 )
    {
      if ( *(_DWORD *)(v2 + 12) != 2 || (unsigned int)MF_BoundRecord(hdc, 62) )
      {
        if ( (*(_BYTE *)(v3 + 8) & 0x20) != 0 )
          vSAPCallback(v3);
        if ( (*(_DWORD *)(v3 + 8) & 0x10000) == 0 )
        {
          if ( (*(_DWORD *)(v3 + 8) & 0x100) != 0 )
            StartPage(hdc);
LABEL_11:
          LODWORD(NtCurrentTeb()->Win32ClientInfo[1]) = 0;
          return NtGdiFillPath(hdc);
        }
      }
    }
    else
    {
      GdiSetLastError(6);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002b820  mov     [rsp+arg_0], rbx
0x18002b825  push    rdi
0x18002b826  sub     rsp, 20h
0x18002b82a  mov     eax, ecx
0x18002b82c  mov     rdi, rcx
0x18002b82f  and     eax, 7F0000h
0x18002b834  cmp     eax, 10000h
0x18002b839  jz      short loc_18002B88D
0x18002b83b  cmp     eax, 660000h
0x18002b840  jz      short loc_18002B8BB
0x18002b842  call    cs:__imp_pldcGet
0x18002b849  nop     dword ptr [rax+rax+00h]
0x18002b84e  mov     rbx, rax
0x18002b851  test    rax, rax
0x18002b854  jz      short loc_18002B8D0
0x18002b856  cmp     dword ptr [rax+0Ch], 2
0x18002b85a  jnz     short loc_18002B86D
0x18002b85c  mov     edx, 3Eh ; '>'
0x18002b861  mov     rcx, rdi
0x18002b864  call    MF_BoundRecord
0x18002b869  test    eax, eax
0x18002b86b  jz      short loc_18002B8BB
0x18002b86d  test    byte ptr [rbx+8], 20h
0x18002b871  jz      short loc_18002B87B
0x18002b873  mov     rcx, rbx
0x18002b876  call    vSAPCallback
0x18002b87b  test    dword ptr [rbx+8], 10000h
0x18002b882  jnz     short loc_18002B8BB
0x18002b884  test    dword ptr [rbx+8], 100h
0x18002b88b  jnz     short loc_18002B8BF
0x18002b88d  mov     rax, gs:30h
0x18002b896  mov     rcx, rdi
0x18002b899  mov     dword ptr [rax+808h], 0
0x18002b8a3  call    cs:__imp_NtGdiFillPath
0x18002b8aa  nop     dword ptr [rax+rax+00h]
0x18002b8af  mov     rbx, [rsp+28h+arg_0]
0x18002b8b4  add     rsp, 20h
0x18002b8b8  pop     rdi
0x18002b8b9  retn
0x18002b8bb  xor     eax, eax
0x18002b8bd  jmp     short loc_18002B8AF
0x18002b8bf  mov     rcx, rdi; hdc
0x18002b8c2  call    cs:__imp_StartPage
0x18002b8c9  nop     dword ptr [rax+rax+00h]
0x18002b8ce  jmp     short loc_18002B88D
0x18002b8d0  mov     ecx, 6
0x18002b8d5  call    cs:__imp_GdiSetLastError
0x18002b8dc  nop     dword ptr [rax+rax+00h]
0x18002b8e1  jmp     short loc_18002B8BB
```
