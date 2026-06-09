# WdipReadParameterFromFile(void *)

- ea: `0x180017b20`
- end: `0x180017d76`
- name: `?WdipReadParameterFromFile@@YAPEAU__WDIP_PARAMETER@@PEAX@Z`
- size: `598`
- prototype: `struct __WDIP_PARAMETER *__fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180018680`

## callees

- `0x1800013a0`
- `0x180008f70`
- `0x180009090`
- `0x180009660`
- `0x18000a856`
- `0x180017b20`

## string_xrefs

- `0x180017b74`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`
- `0x180017d48`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`
- `0x180017b6d`: `WdipReadParameterFromFile`
- `0x180017d41`: `WdipReadParameterFromFile`

## pseudocode

```c
struct __WDIP_PARAMETER *__fastcall WdipReadParameterFromFile(HANDLE hFile)
{
  __int64 v1; // r14
  char *v3; // rax
  char *v4; // rbx
  int Args; // eax
  int v6; // r8d
  __int64 v7; // rcx
  size_t v8; // rsi
  void *v9; // rax
  DWORD *v10; // rsi
  void *v11; // rax
  int v13; // [rsp+68h] [rbp+38h] BYREF
  DWORD Buffer; // [rsp+70h] [rbp+40h] BYREF
  void *v15; // [rsp+78h] [rbp+48h] BYREF

  v1 = 0;
  v13 = 0;
  Buffer = 0;
  v3 = (char *)WdipAlloc(64);
  v15 = v3;
  v4 = v3;
  if ( v3 )
  {
    memset_0(v3, 0, 0x40u);
    Args = WdipReadFile(hFile, v4, 0x10u, &v13);
    if ( Args >= 0 )
    {
      Args = WdipReadFile(hFile, v4 + 16, 0x10u, &v13);
      if ( Args >= 0 )
      {
        Args = WdipReadFile(hFile, v4 + 32, 4u, &v13);
        if ( Args >= 0 )
        {
          Args = WdipReadFile(hFile, v4 + 36, 4u, &v13);
          if ( Args >= 0 )
          {
            Args = WdipReadFile(hFile, v4 + 44, 4u, &v13);
            if ( Args >= 0 )
            {
              Args = WdipReadFile(hFile, (char *)&Buffer, 4u, &v13);
              if ( Args >= 0 )
              {
                v7 = Buffer + 2;
                if ( (unsigned int)v7 >= Buffer )
                {
                  v8 = (unsigned int)v7;
                  v9 = (void *)WdipAlloc(v7);
                  *((_QWORD *)v4 + 6) = v9;
                  if ( v9 )
                  {
                    memset_0(v9, 0, v8);
                    Args = WdipReadFile(hFile, *((char **)v4 + 6), Buffer, &v13);
                    if ( Args < 0 )
                    {
                      v6 = 828;
                      goto LABEL_28;
                    }
                    v10 = (DWORD *)(v4 + 40);
                    Args = WdipReadFile(hFile, v4 + 40, 4u, &v13);
                    if ( Args < 0 )
                    {
                      v6 = 836;
                      goto LABEL_28;
                    }
                    v11 = (void *)WdipAlloc(*v10);
                    *((_QWORD *)v4 + 7) = v11;
                    if ( v11 )
                    {
                      memset_0(v11, 0, *v10);
                      Args = WdipReadFile(hFile, *((char **)v4 + 7), *v10, &v13);
                      if ( Args >= 0 )
                        return (struct __WDIP_PARAMETER *)v4;
                      v6 = 848;
                      goto LABEL_28;
                    }
                    v6 = 839;
                  }
                  else
                  {
                    v6 = 819;
                  }
                  LOBYTE(Args) = 14;
                }
                else
                {
                  v6 = 816;
                  LOBYTE(Args) = 22;
                }
              }
              else
              {
                v6 = 804;
              }
            }
            else
            {
              v6 = 796;
            }
          }
          else
          {
            v6 = 788;
          }
        }
        else
        {
          v6 = 780;
        }
      }
      else
      {
        v6 = 771;
      }
    }
    else
    {
      v6 = 763;
    }
LABEL_28:
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
      (int)L"WdipReadParameterFromFile",
      v6,
      (int)L"Error = %d",
      Args);
    WdipDeleteParameter(&v15);
    return (struct __WDIP_PARAMETER *)v1;
  }
  WdipTraceError(
    (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
    (int)L"WdipReadParameterFromFile",
    754,
    (int)L"Error = %d",
    14);
  return (struct __WDIP_PARAMETER *)v1;
}

```

## disassembly

```asm
0x180017b20  mov     [rsp-28h+arg_0], rbx
0x180017b25  push    rbp
0x180017b26  push    rsi
0x180017b27  push    rdi
0x180017b28  push    r14
0x180017b2a  push    r15
0x180017b2c  mov     rbp, rsp
0x180017b2f  sub     rsp, 30h
0x180017b33  xor     r14d, r14d
0x180017b36  mov     rdi, rcx
0x180017b39  mov     [rbp+arg_8], r14d
0x180017b3d  mov     [rbp+Buffer], r14d
0x180017b41  lea     esi, [r14+40h]
0x180017b45  mov     ecx, esi
0x180017b47  call    WdipAlloc
0x180017b4c  mov     [rbp+arg_18], rax
0x180017b50  mov     rbx, rax
0x180017b53  test    rax, rax
0x180017b56  jnz     short loc_180017B85
0x180017b58  lea     r9, aErrorD; "Error = %d"
0x180017b5f  mov     dword ptr [rsp+30h+Args], 0Eh; Args
0x180017b67  mov     r8d, 2F2h; int
0x180017b6d  lea     rdx, aWdipreadparame; "WdipReadParameterFromFile"
0x180017b74  lea     rcx, aClientcoreBase_9; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180017b7b  call    WdipTraceError
0x180017b80  jmp     loc_180017D62
0x180017b85  mov     r8, rsi; Size
0x180017b88  xor     edx, edx; Val
0x180017b8a  mov     rcx, rbx; void *
0x180017b8d  call    memset_0
0x180017b92  mov     esi, 10h
0x180017b97  lea     r9, [rbp+arg_8]
0x180017b9b  mov     r8d, esi; nNumberOfBytesToRead
0x180017b9e  mov     rdx, rbx; lpBuffer
0x180017ba1  mov     rcx, rdi; hFile
0x180017ba4  call    WdipReadFile
0x180017ba9  test    eax, eax
0x180017bab  jns     short loc_180017BB8
0x180017bad  mov     r8d, 2FBh
0x180017bb3  jmp     loc_180017D33
0x180017bb8  lea     rdx, [rbx+10h]; lpBuffer
0x180017bbc  mov     r8d, esi; nNumberOfBytesToRead
0x180017bbf  lea     r9, [rbp+arg_8]
0x180017bc3  mov     rcx, rdi; hFile
0x180017bc6  call    WdipReadFile
0x180017bcb  test    eax, eax
0x180017bcd  jns     short loc_180017BDA
0x180017bcf  mov     r8d, 303h
0x180017bd5  jmp     loc_180017D33
0x180017bda  mov     r15d, 4
0x180017be0  lea     rdx, [rbx+20h]; lpBuffer
0x180017be4  mov     r8d, r15d; nNumberOfBytesToRead
0x180017be7  lea     r9, [rbp+arg_8]
0x180017beb  mov     rcx, rdi; hFile
0x180017bee  call    WdipReadFile
0x180017bf3  test    eax, eax
0x180017bf5  jns     short loc_180017C02
0x180017bf7  mov     r8d, 30Ch
0x180017bfd  jmp     loc_180017D33
0x180017c02  lea     rdx, [rbx+24h]; lpBuffer
0x180017c06  mov     r8d, r15d; nNumberOfBytesToRead
0x180017c09  lea     r9, [rbp+arg_8]
0x180017c0d  mov     rcx, rdi; hFile
0x180017c10  call    WdipReadFile
0x180017c15  test    eax, eax
0x180017c17  jns     short loc_180017C24
0x180017c19  mov     r8d, 314h
0x180017c1f  jmp     loc_180017D33
0x180017c24  lea     rdx, [rbx+2Ch]; lpBuffer
0x180017c28  mov     r8d, r15d; nNumberOfBytesToRead
0x180017c2b  lea     r9, [rbp+arg_8]
0x180017c2f  mov     rcx, rdi; hFile
0x180017c32  call    WdipReadFile
0x180017c37  test    eax, eax
0x180017c39  jns     short loc_180017C46
0x180017c3b  mov     r8d, 31Ch
0x180017c41  jmp     loc_180017D33
0x180017c46  lea     r9, [rbp+arg_8]
0x180017c4a  mov     r8d, r15d; nNumberOfBytesToRead
0x180017c4d  lea     rdx, [rbp+Buffer]; lpBuffer
0x180017c51  mov     rcx, rdi; hFile
0x180017c54  call    WdipReadFile
0x180017c59  test    eax, eax
0x180017c5b  jns     short loc_180017C68
0x180017c5d  mov     r8d, 324h
0x180017c63  jmp     loc_180017D33
0x180017c68  mov     eax, [rbp+Buffer]
0x180017c6b  lea     ecx, [rax+2]
0x180017c6e  cmp     ecx, eax
0x180017c70  jnb     short loc_180017C82
0x180017c72  mov     r8d, 330h
0x180017c78  mov     eax, 216h
0x180017c7d  jmp     loc_180017D36
0x180017c82  mov     esi, ecx
0x180017c84  call    WdipAlloc
0x180017c89  mov     [rbx+30h], rax
0x180017c8d  test    rax, rax
0x180017c90  jnz     short loc_180017CA2
0x180017c92  mov     r8d, 333h
0x180017c98  mov     eax, 0Eh
0x180017c9d  jmp     loc_180017D36
0x180017ca2  mov     r8, rsi; Size
0x180017ca5  xor     edx, edx; Val
0x180017ca7  mov     rcx, rax; void *
0x180017caa  call    memset_0
0x180017caf  mov     r8d, [rbp+Buffer]; nNumberOfBytesToRead
0x180017cb3  lea     r9, [rbp+arg_8]
0x180017cb7  mov     rdx, [rbx+30h]; lpBuffer
0x180017cbb  mov     rcx, rdi; hFile
0x180017cbe  call    WdipReadFile
0x180017cc3  test    eax, eax
0x180017cc5  jns     short loc_180017CCF
0x180017cc7  mov     r8d, 33Ch
0x180017ccd  jmp     short loc_180017D33
0x180017ccf  lea     rsi, [rbx+28h]
0x180017cd3  mov     r8d, r15d; nNumberOfBytesToRead
0x180017cd6  mov     rdx, rsi; lpBuffer
0x180017cd9  lea     r9, [rbp+arg_8]
0x180017cdd  mov     rcx, rdi; hFile
0x180017ce0  call    WdipReadFile
0x180017ce5  test    eax, eax
0x180017ce7  jns     short loc_180017CF1
0x180017ce9  mov     r8d, 344h
0x180017cef  jmp     short loc_180017D33
0x180017cf1  mov     ecx, [rsi]
0x180017cf3  call    WdipAlloc
0x180017cf8  mov     [rbx+38h], rax
0x180017cfc  test    rax, rax
0x180017cff  jnz     short loc_180017D09
0x180017d01  mov     r8d, 347h
0x180017d07  jmp     short loc_180017C98
0x180017d09  mov     r8d, [rsi]; Size
0x180017d0c  xor     edx, edx; Val
0x180017d0e  mov     rcx, rax; void *
0x180017d11  call    memset_0
0x180017d16  mov     r8d, [rsi]; nNumberOfBytesToRead
0x180017d19  lea     r9, [rbp+arg_8]
0x180017d1d  mov     rdx, [rbx+38h]; lpBuffer
0x180017d21  mov     rcx, rdi; hFile
0x180017d24  call    WdipReadFile
0x180017d29  test    eax, eax
0x180017d2b  jns     short loc_180017D5F
0x180017d2d  mov     r8d, 350h; int
0x180017d33  movzx   eax, ax
0x180017d36  lea     r9, aErrorD; "Error = %d"
0x180017d3d  mov     dword ptr [rsp+30h+Args], eax; Args
0x180017d41  lea     rdx, aWdipreadparame; "WdipReadParameterFromFile"
0x180017d48  lea     rcx, aClientcoreBase_9; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180017d4f  call    WdipTraceError
0x180017d54  lea     rcx, [rbp+arg_18]
0x180017d58  call    WdipDeleteParameter
0x180017d5d  jmp     short loc_180017D62
0x180017d5f  mov     r14, rbx
0x180017d62  mov     rbx, [rsp+30h+arg_0]
0x180017d67  mov     rax, r14
0x180017d6a  add     rsp, 30h
0x180017d6e  pop     r15
0x180017d70  pop     r14
0x180017d72  pop     rdi
0x180017d73  pop     rsi
0x180017d74  pop     rbp
0x180017d75  retn
```
