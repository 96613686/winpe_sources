# ReadRasFile

- ea: `0x180020b18`
- end: `0x180020c72`
- name: `ReadRasFile`
- size: `346`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18000714c`
- `0x18002092c`

## callees

- `0x1800208ec`
- `0x180020b18`
- `0x180020c78`
- `0x180020d14`
- `0x180020f94`
- `0x180021080`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x180020bee`
- `rtutils!TracePrintfExA` at `0x180020c2c`
- `rtutils!TracePrintfExA` at `0x180020c65`
- `rtutils!TracePrintfExA` at `0x180020bee`
- `rtutils!TracePrintfExA` at `0x180020c2c`
- `rtutils!TracePrintfExA` at `0x180020c65`

## string_xrefs

- `0x180020be3`: `ReadRasFile: ReadEntryList returned %d`
- `0x180020c20`: `ReadRasFile: File %S does not exist`
- `0x180020c59`: `ReadRasFile called with NULL path`

## pseudocode

```c
__int64 __fastcall ReadRasFile(LPCWSTR lpFileName)
{
  __int64 result; // rax

  if ( lpFileName && *lpFileName )
  {
    if ( (unsigned int)FFileExists(lpFileName) )
    {
      result = LoadFile(lpFileName);
      if ( !(_DWORD)result )
        return 622;
    }
    else
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "ReadRasFile: File %S does not exist", lpFileName);
      return 0;
    }
  }
  else
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "ReadRasFile called with NULL path");
    return 3;
  }
  return result;
}

```

## disassembly

```asm
0x180020b18  mov     [rsp+arg_8], rbx
0x180020b1d  mov     [rsp+arg_10], rsi
0x180020b22  push    rdi
0x180020b23  push    r12
0x180020b25  push    r13
0x180020b27  push    r14
0x180020b29  push    r15
0x180020b2b  sub     rsp, 30h
0x180020b2f  xor     r13d, r13d
0x180020b32  mov     [rsp+58h+arg_0], 0FFFFFFFFh
0x180020b3a  mov     r14, r9
0x180020b3d  mov     r15d, r8d
0x180020b40  mov     r12, rdx
0x180020b43  mov     rdi, rcx
0x180020b46  test    rcx, rcx
0x180020b49  jz      loc_180020C4E
0x180020b4f  cmp     [rcx], r13w
0x180020b53  jz      loc_180020C4E
0x180020b59  mov     esi, [r9+20h]
0x180020b5d  call    FFileExists
0x180020b62  test    eax, eax
0x180020b64  jz      loc_180020C12
0x180020b6a  mov     r9, [rsp+58h+arg_20]
0x180020b72  lea     r8, [rsp+58h+arg_0]
0x180020b77  mov     edx, esi
0x180020b79  mov     rcx, rdi; lpFileName
0x180020b7c  call    LoadFile
0x180020b81  mov     ebx, eax
0x180020b83  test    eax, eax
0x180020b85  jnz     short loc_180020BFA
0x180020b87  cmp     [rsp+58h+arg_0], 0FFFFFFFFh
0x180020b8c  jz      loc_180020C36
0x180020b92  test    sil, 4
0x180020b96  jnz     short loc_180020BF8
0x180020b98  mov     rax, [r14+30h]
0x180020b9c  mov     rdx, rdi
0x180020b9f  mov     ecx, [rsp+58h+arg_0]
0x180020ba3  mov     esi, [rax+10h]
0x180020ba6  inc     esi
0x180020ba8  mov     r8d, esi
0x180020bab  call    CreateHRasfileNode
0x180020bb0  mov     rcx, [r14+30h]
0x180020bb4  mov     rdx, rax
0x180020bb7  call    DtlAddNodeLast
0x180020bbc  mov     r9d, [rsp+58h+arg_0]
0x180020bc1  mov     r8, r12
0x180020bc4  mov     edx, r15d
0x180020bc7  mov     [rsp+58h+var_38], esi
0x180020bcb  mov     rcx, r14
0x180020bce  call    ReadEntryList
0x180020bd3  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180020bd9  mov     ebx, eax
0x180020bdb  cmp     ecx, 0FFFFFFFFh
0x180020bde  jz      short loc_180020BF4
0x180020be0  mov     r9d, eax
0x180020be3  lea     r8, aReadrasfileRea; "ReadRasFile: ReadEntryList returned %d"
0x180020bea  lea     edx, [r13+0Ch]; dwFlags
0x180020bee  call    cs:__imp_TracePrintfExA
0x180020bf4  test    ebx, ebx
0x180020bf6  jz      short loc_180020C3D
0x180020bf8  mov     eax, ebx
0x180020bfa  mov     rbx, [rsp+58h+arg_8]
0x180020bff  mov     rsi, [rsp+58h+arg_10]
0x180020c04  add     rsp, 30h
0x180020c08  pop     r15
0x180020c0a  pop     r14
0x180020c0c  pop     r13
0x180020c0e  pop     r12
0x180020c10  pop     rdi
0x180020c11  retn
0x180020c12  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180020c18  cmp     ecx, 0FFFFFFFFh
0x180020c1b  jz      short loc_180020C32
0x180020c1d  mov     r9, rdi
0x180020c20  lea     r8, aReadrasfileFil; "ReadRasFile: File %S does not exist"
0x180020c27  mov     edx, 0Ch; dwFlags
0x180020c2c  call    cs:__imp_TracePrintfExA
0x180020c32  xor     eax, eax
0x180020c34  jmp     short loc_180020BFA
0x180020c36  mov     eax, 26Eh
0x180020c3b  jmp     short loc_180020BFA
0x180020c3d  mov     rax, [rsp+58h+arg_28]
0x180020c45  test    rax, rax
0x180020c48  jz      short loc_180020BF8
0x180020c4a  mov     [rax], esi
0x180020c4c  jmp     short loc_180020BF8
0x180020c4e  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180020c54  cmp     ecx, 0FFFFFFFFh
0x180020c57  jz      short loc_180020C6B
0x180020c59  lea     r8, aReadrasfileCal; "ReadRasFile called with NULL path"
0x180020c60  mov     edx, 0Ch; dwFlags
0x180020c65  call    cs:__imp_TracePrintfExA
0x180020c6b  mov     eax, 3
0x180020c70  jmp     short loc_180020BFA
```
