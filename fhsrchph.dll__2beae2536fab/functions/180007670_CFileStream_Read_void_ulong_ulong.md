# CFileStream::Read(void *,ulong,ulong *)

- ea: `0x180007670`
- end: `0x180007709`
- name: `?Read@CFileStream@@UEAAJPEAXKPEAK@Z`
- size: `153`
- prototype: `int __fastcall(HANDLE *this, void *, DWORD, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180002de4`
- `0x180007670`

## import_xrefs

- `KERNEL32!ReadFile` at `0x1800076d7`
- `KERNEL32!ReadFile` at `0x1800076d7`
- `KERNEL32!GetLastError` at `0x1800076e1`
- `KERNEL32!GetLastError` at `0x1800076e1`

## pseudocode

```c
int __fastcall CFileStream::Read(HANDLE *this, void *a2, DWORD a3, unsigned int *a4)
{
  int result; // eax

  if ( !a2 )
    return -2147467261;
  if ( !a3 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), a3 + 10, WPP_e018cca1a23b38b4b0c6d109423cc739_Traceguids);
  if ( ReadFile(this[3], a2, a3, a4, 0) )
    return *a4 != a3 ? 0x80070026 : 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180007670  push    rbx
0x180007672  push    rbp
0x180007673  push    rsi
0x180007674  push    rdi
0x180007675  sub     rsp, 38h
0x180007679  mov     rdi, r9
0x18000767c  mov     ebx, r8d
0x18000767f  mov     rsi, rdx
0x180007682  mov     rbp, rcx
0x180007685  test    rdx, rdx
0x180007688  jnz     short loc_180007691
0x18000768a  mov     eax, 80004003h
0x18000768f  jmp     short loc_180007700
0x180007691  test    ebx, ebx
0x180007693  jnz     short loc_1800076C1
0x180007695  mov     rcx, cs:WPP_GLOBAL_Control
0x18000769c  lea     rax, WPP_GLOBAL_Control
0x1800076a3  cmp     rcx, rax
0x1800076a6  jz      short loc_1800076C1
0x1800076a8  test    byte ptr [rcx+1Ch], 1
0x1800076ac  jz      short loc_1800076C1
0x1800076ae  mov     rcx, [rcx+10h]
0x1800076b2  lea     edx, [rbx+0Ah]
0x1800076b5  lea     r8, WPP_e018cca1a23b38b4b0c6d109423cc739_Traceguids
0x1800076bc  call    WPP_SF_
0x1800076c1  mov     rcx, [rbp+18h]; hFile
0x1800076c5  mov     r9, rdi; lpNumberOfBytesRead
0x1800076c8  mov     r8d, ebx; nNumberOfBytesToRead
0x1800076cb  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x1800076d4  mov     rdx, rsi; lpBuffer
0x1800076d7  call    cs:__imp_ReadFile
0x1800076dd  test    eax, eax
0x1800076df  jnz     short loc_1800076F5
0x1800076e1  call    cs:__imp_GetLastError
0x1800076e7  test    eax, eax
0x1800076e9  jle     short loc_180007700
0x1800076eb  movzx   eax, ax
0x1800076ee  or      eax, 80070000h
0x1800076f3  jmp     short loc_180007700
0x1800076f5  sub     ebx, [rdi]
0x1800076f7  neg     ebx
0x1800076f9  sbb     eax, eax
0x1800076fb  and     eax, 80070026h
0x180007700  add     rsp, 38h
0x180007704  pop     rdi
0x180007705  pop     rsi
0x180007706  pop     rbp
0x180007707  pop     rbx
0x180007708  retn
```
