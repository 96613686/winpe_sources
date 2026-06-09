# rasGetFileLine

- ea: `0x18000dff0`
- end: `0x18000e0f2`
- name: `rasGetFileLine`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x18000e820`

## callees

- `0x18000dff0`

## import_xrefs

- `ntdll!DbgPrint` at `0x18000e0ea`
- `ntdll!DbgPrint` at `0x18000e0ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0db`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000e0ac`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000e0ac`

## string_xrefs

- `0x18000e0e3`: `\n ReadFile failed with error %d\n`

## pseudocode

```c
__int64 __fastcall rasGetFileLine(__int64 a1, char *a2, __int64 a3, _DWORD *a4)
{
  unsigned int v5; // edi
  __int64 v8; // rcx
  char v9; // al
  DWORD v11; // eax
  DWORD LastError; // eax
  DWORD NumberOfBytesRead; // [rsp+60h] [rbp+18h] BYREF

  NumberOfBytesRead = 0;
  v5 = 0;
LABEL_2:
  if ( *(_DWORD *)(a1 + 48) == 2048 )
  {
    if ( !ReadFile(*(HANDLE *)(a1 + 24), *(LPVOID *)(a1 + 40), 0x800u, &NumberOfBytesRead, 0) )
    {
      LastError = GetLastError();
      DbgPrint("\n ReadFile failed with error %d\n", LastError);
      return 0;
    }
    v11 = NumberOfBytesRead;
    *(_DWORD *)(a1 + 48) = 0;
    if ( !v11 )
      return 0;
    if ( v11 < 0x800 )
      *(_BYTE *)(v11 + *(_QWORD *)(a1 + 40)) = 0;
  }
  v8 = *(unsigned int *)(a1 + 48);
  if ( !*(_BYTE *)(v8 + *(_QWORD *)(a1 + 40)) )
    return 0;
  while ( 1 )
  {
    if ( (unsigned int)v8 >= 0x800 )
    {
      if ( v5 < 0x600 )
        goto LABEL_2;
LABEL_12:
      *a4 = 625;
      return 0;
    }
    if ( v5 >= 0x600 )
      goto LABEL_12;
    *a2 = *(_BYTE *)(v8 + *(_QWORD *)(a1 + 40));
    ++*(_DWORD *)(a1 + 48);
    v9 = *a2;
    if ( *a2 == 13 )
      goto LABEL_10;
    if ( v9 == 10 )
      break;
    if ( !v9 )
      return 1;
    ++a2;
LABEL_10:
    v8 = *(unsigned int *)(a1 + 48);
    ++v5;
  }
  *a2 = 0;
  return 1;
}

```

## disassembly

```asm
0x18000dff0  mov     [rsp+arg_0], rbx
0x18000dff5  mov     [rsp+arg_8], rbp
0x18000dffa  mov     [rsp+NumberOfBytesRead], r8d
0x18000dfff  push    rsi
0x18000e000  push    rdi
0x18000e001  push    r14
0x18000e003  sub     rsp, 30h
0x18000e007  xor     ebp, ebp
0x18000e009  mov     r14, r9
0x18000e00c  mov     [rsp+48h+NumberOfBytesRead], ebp
0x18000e010  mov     edi, ebp
0x18000e012  mov     rbx, rdx
0x18000e015  mov     rsi, rcx
0x18000e018  cmp     dword ptr [rsi+30h], 800h
0x18000e01f  jz      short loc_18000E094
0x18000e021  mov     ecx, [rsi+30h]
0x18000e024  mov     rax, [rsi+28h]
0x18000e028  cmp     [rcx+rax], bpl
0x18000e02c  jz      short loc_18000E075
0x18000e02e  xchg    ax, ax
0x18000e030  cmp     ecx, 800h
0x18000e036  jnb     short loc_18000E066
0x18000e038  cmp     edi, 600h
0x18000e03e  jnb     short loc_18000E06E
0x18000e040  mov     rax, [rsi+28h]
0x18000e044  movzx   ecx, byte ptr [rcx+rax]
0x18000e048  mov     [rbx], cl
0x18000e04a  inc     dword ptr [rsi+30h]
0x18000e04d  movzx   eax, byte ptr [rbx]
0x18000e050  cmp     al, 0Dh
0x18000e052  jz      short loc_18000E05F
0x18000e054  cmp     al, 0Ah
0x18000e056  jz      short loc_18000E079
0x18000e058  test    al, al
0x18000e05a  jz      short loc_18000E07C
0x18000e05c  inc     rbx
0x18000e05f  mov     ecx, [rsi+30h]
0x18000e062  inc     edi
0x18000e064  jmp     short loc_18000E030
0x18000e066  cmp     edi, 600h
0x18000e06c  jb      short loc_18000E018
0x18000e06e  mov     dword ptr [r14], 271h
0x18000e075  xor     eax, eax
0x18000e077  jmp     short loc_18000E081
0x18000e079  mov     [rbx], bpl
0x18000e07c  mov     eax, 1
0x18000e081  mov     rbx, [rsp+48h+arg_0]
0x18000e086  mov     rbp, [rsp+48h+arg_8]
0x18000e08b  add     rsp, 30h
0x18000e08f  pop     r14
0x18000e091  pop     rdi
0x18000e092  pop     rsi
0x18000e093  retn
0x18000e094  mov     rdx, [rsi+28h]; lpBuffer
0x18000e098  lea     r9, [rsp+48h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000e09d  mov     rcx, [rsi+18h]; hFile
0x18000e0a1  mov     r8d, 800h; nNumberOfBytesToRead
0x18000e0a7  mov     [rsp+48h+lpOverlapped], rbp; lpOverlapped
0x18000e0ac  call    cs:__imp_ReadFile
0x18000e0b2  test    eax, eax
0x18000e0b4  jz      short loc_18000E0DB
0x18000e0b6  mov     eax, [rsp+48h+NumberOfBytesRead]
0x18000e0ba  mov     [rsi+30h], ebp
0x18000e0bd  test    eax, eax
0x18000e0bf  jz      short loc_18000E075
0x18000e0c1  cmp     eax, 800h
0x18000e0c6  jnb     loc_18000E021
0x18000e0cc  mov     ecx, eax
0x18000e0ce  mov     rax, [rsi+28h]
0x18000e0d2  mov     [rcx+rax], bpl
0x18000e0d6  jmp     loc_18000E021
0x18000e0db  call    cs:__imp_GetLastError
0x18000e0e1  mov     edx, eax
0x18000e0e3  lea     rcx, Format; "\n ReadFile failed with error %d\n"
0x18000e0ea  call    cs:__imp_DbgPrint
0x18000e0f0  jmp     short loc_18000E075
```
