# SendFileDataOverVC(IRDPSRAPIVirtualChannel *,long,void *,ulong)

- ea: `0x14004a060`
- end: `0x14004a18a`
- name: `?SendFileDataOverVC@@YAJPEAUIRDPSRAPIVirtualChannel@@JPEAXK@Z`
- size: `298`
- prototype: `__int64 __fastcall(struct IRDPSRAPIVirtualChannel *, unsigned int, void *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140045be8`

## callees

- `0x14004a060`
- `0x14004d010`

## import_xrefs

- `KERNEL32!ReadFile` at `0x14004a0f3`
- `KERNEL32!ReadFile` at `0x14004a0f3`
- `msvcrt!malloc` at `0x14004a0af`
- `msvcrt!malloc` at `0x14004a0af`
- `msvcrt!free` at `0x14004a164`
- `msvcrt!free` at `0x14004a164`
- `OLEAUT32!__imp_SysFreeString` at `0x14004a155`
- `OLEAUT32!__imp_SysFreeString` at `0x14004a155`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x14004a11d`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x14004a11d`

## pseudocode

```c
__int64 __fastcall SendFileDataOverVC(struct IRDPSRAPIVirtualChannel *a1, unsigned int a2, void *a3, unsigned int a4)
{
  unsigned int v8; // ebx
  __int64 v9; // rsi
  CHAR *v10; // rax
  CHAR *v11; // rdi
  BSTR v12; // rax
  OLECHAR *v13; // rsi
  DWORD NumberOfBytesRead; // [rsp+60h] [rbp+8h] BYREF

  NumberOfBytesRead = 0;
  if ( a1 )
  {
    if ( a3 )
    {
      v9 = 1025;
      v10 = (CHAR *)malloc(0x401u);
      v11 = v10;
      if ( v10 )
      {
        v8 = 1;
        do
        {
          *v10++ = 0;
          --v9;
        }
        while ( v9 );
        if ( ReadFile(a3, v11, 0x400u, &NumberOfBytesRead, 0) )
        {
          if ( NumberOfBytesRead )
          {
            v11[NumberOfBytesRead] = 0;
            v12 = SysAllocStringByteLen(v11, NumberOfBytesRead);
            v13 = v12;
            if ( v12 )
            {
              v8 = ((__int64 (__fastcall *)(struct IRDPSRAPIVirtualChannel *, BSTR, _QWORD, _QWORD))a1->lpVtbl->SendData)(
                     a1,
                     v12,
                     a2,
                     a4);
              SysFreeString(v13);
            }
            else
            {
              v8 = -2147024882;
            }
          }
        }
        else
        {
          v8 = -2147467259;
        }
        free(v11);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
    else
    {
      return (unsigned int)-2147024890;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v8;
}

```

## disassembly

```asm
0x14004a060  mov     [rsp+arg_8], rbx
0x14004a065  mov     [rsp+arg_10], rbp
0x14004a06a  push    rsi
0x14004a06b  push    rdi
0x14004a06c  push    r12
0x14004a06e  push    r14
0x14004a070  push    r15
0x14004a072  sub     rsp, 30h
0x14004a076  mov     [rsp+58h+NumberOfBytesRead], 0
0x14004a07e  mov     r15d, r9d
0x14004a081  mov     rbp, r8
0x14004a084  mov     r12d, edx
0x14004a087  mov     r14, rcx
0x14004a08a  test    rcx, rcx
0x14004a08d  jnz     short loc_14004A099
0x14004a08f  mov     ebx, 80004003h
0x14004a094  jmp     loc_14004A170
0x14004a099  test    rbp, rbp
0x14004a09c  jnz     short loc_14004A0A8
0x14004a09e  mov     ebx, 80070006h
0x14004a0a3  jmp     loc_14004A170
0x14004a0a8  mov     esi, 401h
0x14004a0ad  mov     ecx, esi; Size
0x14004a0af  call    cs:__imp_malloc
0x14004a0b6  nop     dword ptr [rax+rax+00h]
0x14004a0bb  mov     rdi, rax
0x14004a0be  test    rax, rax
0x14004a0c1  jnz     short loc_14004A0CD
0x14004a0c3  mov     ebx, 8007000Eh
0x14004a0c8  jmp     loc_14004A170
0x14004a0cd  mov     ebx, 1
0x14004a0d2  mov     byte ptr [rax], 0
0x14004a0d5  add     rax, rbx
0x14004a0d8  sub     rsi, rbx
0x14004a0db  jnz     short loc_14004A0D2
0x14004a0dd  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x14004a0e2  mov     [rsp+58h+lpOverlapped], rsi; lpOverlapped
0x14004a0e7  mov     r8d, 400h; nNumberOfBytesToRead
0x14004a0ed  mov     rdx, rdi; lpBuffer
0x14004a0f0  mov     rcx, rbp; hFile
0x14004a0f3  call    cs:__imp_ReadFile
0x14004a0fa  nop     dword ptr [rax+rax+00h]
0x14004a0ff  test    eax, eax
0x14004a101  jnz     short loc_14004A10A
0x14004a103  mov     ebx, 80004005h
0x14004a108  jmp     short loc_14004A161
0x14004a10a  mov     eax, [rsp+58h+NumberOfBytesRead]
0x14004a10e  test    eax, eax
0x14004a110  jz      short loc_14004A161
0x14004a112  mov     byte ptr [rax+rdi], 0
0x14004a116  mov     rcx, rdi; psz
0x14004a119  mov     edx, [rsp+58h+NumberOfBytesRead]; len
0x14004a11d  call    cs:__imp_SysAllocStringByteLen
0x14004a124  nop     dword ptr [rax+rax+00h]
0x14004a129  mov     rsi, rax
0x14004a12c  test    rax, rax
0x14004a12f  jnz     short loc_14004A138
0x14004a131  mov     ebx, 8007000Eh
0x14004a136  jmp     short loc_14004A161
0x14004a138  mov     rax, [r14]
0x14004a13b  mov     r9d, r15d
0x14004a13e  mov     r8d, r12d
0x14004a141  mov     rdx, rsi
0x14004a144  mov     rcx, r14
0x14004a147  mov     rax, [rax+38h]
0x14004a14b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a150  mov     ebx, eax
0x14004a152  mov     rcx, rsi; bstrString
0x14004a155  call    cs:__imp_SysFreeString
0x14004a15c  nop     dword ptr [rax+rax+00h]
0x14004a161  mov     rcx, rdi; Block
0x14004a164  call    cs:__imp_free
0x14004a16b  nop     dword ptr [rax+rax+00h]
0x14004a170  mov     rbp, [rsp+58h+arg_10]
0x14004a175  mov     eax, ebx
0x14004a177  mov     rbx, [rsp+58h+arg_8]
0x14004a17c  add     rsp, 30h
0x14004a180  pop     r15
0x14004a182  pop     r14
0x14004a184  pop     r12
0x14004a186  pop     rdi
0x14004a187  pop     rsi
0x14004a188  retn
```
