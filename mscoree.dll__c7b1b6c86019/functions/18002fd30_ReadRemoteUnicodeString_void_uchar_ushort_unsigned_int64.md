# ReadRemoteUnicodeString(void *,uchar *,ushort *,unsigned __int64)

- ea: `0x18002fd30`
- end: `0x18002fde2`
- name: `?ReadRemoteUnicodeString@@YA_NPEAXPEAEPEAG_K@Z`
- size: `178`
- prototype: `bool __fastcall(HANDLE hProcess, LPCVOID lpBaseAddress, unsigned __int16 *lpBuffer, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002ff24`

## callees

- `0x18002fd30`

## import_xrefs

- `KERNEL32!ReadProcessMemory` at `0x18002fd97`
- `KERNEL32!ReadProcessMemory` at `0x18002fd97`

## pseudocode

```c
bool __fastcall ReadRemoteUnicodeString(HANDLE hProcess, char *lpBaseAddress, unsigned __int16 *lpBuffer)
{
  __int64 v3; // rbx
  unsigned __int16 *v4; // rbp
  bool v8; // si
  unsigned __int64 i; // rdi
  SIZE_T v10; // r9
  bool result; // al
  SIZE_T NumberOfBytesRead; // [rsp+78h] [rbp+20h] BYREF

  v3 = 0;
  v4 = lpBuffer;
  NumberOfBytesRead = 0;
  v8 = 1;
  for ( i = 520; i; i -= (unsigned int)NumberOfBytesRead )
  {
    v10 = i;
    if ( i >= 4096 - ((unsigned __int16)lpBaseAddress & 0xFFFu) )
      v10 = 4096 - ((unsigned __int16)lpBaseAddress & 0xFFFu);
    if ( !ReadProcessMemory(hProcess, lpBaseAddress, v4, v10, &NumberOfBytesRead) )
    {
      v8 = v3 != 0;
      break;
    }
    v3 += NumberOfBytesRead;
    lpBaseAddress += NumberOfBytesRead;
    v4 = (unsigned __int16 *)((char *)v4 + NumberOfBytesRead);
  }
  result = v8;
  lpBuffer[259] = 0;
  return result;
}

```

## disassembly

```asm
0x18002fd30  mov     rax, rsp
0x18002fd33  mov     [rax+8], rbx
0x18002fd37  mov     [rax+10h], rbp
0x18002fd3b  mov     [rax+20h], r9
0x18002fd3f  push    rsi
0x18002fd40  push    rdi
0x18002fd41  push    r12
0x18002fd43  push    r14
0x18002fd45  push    r15
0x18002fd47  sub     rsp, 30h
0x18002fd4b  xor     ebx, ebx
0x18002fd4d  mov     rbp, r8
0x18002fd50  mov     [rax+20h], rbx
0x18002fd54  mov     r14, rdx
0x18002fd57  mov     r12, rcx
0x18002fd5a  mov     r15, r8
0x18002fd5d  mov     sil, 1
0x18002fd60  mov     edi, 208h
0x18002fd65  test    rdi, rdi
0x18002fd68  jz      short loc_18002FDBE
0x18002fd6a  mov     ecx, 1000h
0x18002fd6f  lea     rax, [rsp+58h+NumberOfBytesRead]
0x18002fd74  mov     edx, r14d
0x18002fd77  mov     [rsp+58h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x18002fd7c  and     edx, 0FFFh
0x18002fd82  mov     r9, rdi
0x18002fd85  sub     ecx, edx
0x18002fd87  mov     r8, rbp; lpBuffer
0x18002fd8a  cmp     rdi, rcx
0x18002fd8d  mov     rdx, r14; lpBaseAddress
0x18002fd90  cmovnb  r9, rcx; nSize
0x18002fd94  mov     rcx, r12; hProcess
0x18002fd97  call    cs:__imp_ReadProcessMemory
0x18002fd9d  test    eax, eax
0x18002fd9f  jz      short loc_18002FDB6
0x18002fda1  mov     rax, [rsp+58h+NumberOfBytesRead]
0x18002fda6  add     rbx, rax
0x18002fda9  add     r14, rax
0x18002fdac  add     rbp, rax
0x18002fdaf  mov     eax, eax
0x18002fdb1  sub     rdi, rax
0x18002fdb4  jmp     short loc_18002FD65
0x18002fdb6  neg     rbx
0x18002fdb9  sbb     al, al
0x18002fdbb  and     sil, al
0x18002fdbe  mov     rbx, [rsp+58h+arg_0]
0x18002fdc3  xor     ecx, ecx
0x18002fdc5  mov     rbp, [rsp+58h+arg_8]
0x18002fdca  mov     al, sil
0x18002fdcd  mov     [r15+206h], cx
0x18002fdd5  add     rsp, 30h
0x18002fdd9  pop     r15
0x18002fddb  pop     r14
0x18002fddd  pop     r12
0x18002fddf  pop     rdi
0x18002fde0  pop     rsi
0x18002fde1  retn
```
