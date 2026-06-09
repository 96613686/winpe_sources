# acmFormatTagDetailsW

- ea: `0x180002b00`
- end: `0x180002e63`
- name: `acmFormatTagDetailsW`
- size: `867`
- prototype: `MMRESULT __stdcall(HACMDRIVER had, LPACMFORMATTAGDETAILSW paftd, DWORD fdwDetails)`
- caller_count: `7`
- callee_count: `9`
- tags: ``

## callers

- `0x180002540`
- `0x180002e70`
- `0x180005990`
- `0x180007790`
- `0x180008160`
- `0x18000e7d4`
- `0x18000ec20`

## callees

- `0x1800021e0`
- `0x180002a80`
- `0x180002b00`
- `0x180003e80`
- `0x180003ec0`
- `0x180003f40`
- `0x1800043d0`
- `0x180004ab0`
- `0x180004af0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002c50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002c50`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180002d3a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180002d3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002d0d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002d0d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ced`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ced`

## pseudocode

```c

```

## disassembly

```asm
0x180002b00  push    rbx
0x180002b02  push    rsi
0x180002b03  push    rdi
0x180002b04  push    r12
0x180002b06  push    r15
0x180002b08  sub     rsp, 20h
0x180002b0c  mov     r12d, r8d
0x180002b0f  mov     rsi, rdx
0x180002b12  mov     rbx, rcx
0x180002b15  call    pagFindAndBoot
0x180002b1a  mov     r15, rax
0x180002b1d  test    rax, rax
0x180002b20  jz      loc_180002D4C
0x180002b26  test    r12d, 0FFFFFFF0h
0x180002b2d  jnz     loc_180002E00
0x180002b33  mov     [rsp+48h+arg_0], rbp
0x180002b38  mov     edx, 4
0x180002b3d  mov     rcx, rsi
0x180002b40  mov     [rsp+48h+arg_10], r14
0x180002b45  call    ValidateWritePointer
0x180002b4a  test    eax, eax
0x180002b4c  jz      loc_180002DF6
0x180002b52  mov     edx, [rsi]
0x180002b54  cmp     edx, 78h ; 'x'
0x180002b57  jb      loc_180002DF6
0x180002b5d  mov     rcx, rsi
0x180002b60  call    ValidateWritePointer
0x180002b65  test    eax, eax
0x180002b67  jz      loc_180002DF6
0x180002b6d  cmp     dword ptr [rsi+10h], 0
0x180002b71  jnz     loc_180002DF6
0x180002b77  mov     ebp, r12d
0x180002b7a  and     ebp, 0Fh
0x180002b7d  cmp     ebp, 1
0x180002b80  jnz     loc_180002C34
0x180002b86  cmp     dword ptr [rsi+8], 0
0x180002b8a  jz      loc_180002DF6
0x180002b90  xor     r14d, r14d
0x180002b93  test    rbx, rbx
0x180002b96  jnz     loc_180002C5D
0x180002b9c  mov     [rsp+48h+arg_8], r13
0x180002ba1  lea     rcx, [r15+80h]; lpCriticalSection
0x180002ba8  xor     r13d, r13d
0x180002bab  xor     ebx, ebx
0x180002bad  call    AcquireLockShared
0x180002bb2  mov     rcx, r15
0x180002bb5  call    threadEnterListShared
0x180002bba  test    rbx, rbx
0x180002bbd  jz      loc_180002C4C
0x180002bc3  cmp     r15, [rbx+4]
0x180002bc7  jnz     loc_180002D5D
0x180002bcd  mov     rax, [rbx+24h]
0x180002bd1  mov     rbx, [rbx+14h]
0x180002bd5  test    rbx, rbx
0x180002bd8  jz      short loc_180002C23
0x180002bda  cmp     [rbx+24h], rax
0x180002bde  jz      short loc_180002BE6
0x180002be0  mov     rbx, [rbx+14h]
0x180002be4  jmp     short loc_180002BD5
0x180002be6  mov     ecx, [rbx+38h]
0x180002be9  bt      ecx, 1Ch
0x180002bed  jb      short loc_180002BE0
0x180002bef  test    ecx, ecx
0x180002bf1  js      short loc_180002BE0
0x180002bf3  cmp     dword ptr [rbx+0Ch], 0
0x180002bf7  jnz     short loc_180002BE0
0x180002bf9  mov     eax, ebp
0x180002bfb  sub     eax, 1
0x180002bfe  jnz     loc_180002D9B
0x180002c04  xor     r8d, r8d
0x180002c07  cmp     r8d, [rbx+40h]
0x180002c0b  jnb     short loc_180002BBA
0x180002c0d  mov     rcx, [rbx+44h]
0x180002c11  mov     eax, [rsi+8]
0x180002c14  cmp     [rcx+r8*8], eax
0x180002c18  jnz     loc_180002DEE
0x180002c1e  mov     r14, rbx
0x180002c21  jmp     short loc_180002BBA
0x180002c23  test    rax, rax
0x180002c26  jz      loc_180002D5D
0x180002c2c  mov     rbx, [r15+60h]
0x180002c30  xor     eax, eax
0x180002c32  jmp     short loc_180002BD5
0x180002c34  test    ebp, ebp
0x180002c36  jz      loc_180002E0A
0x180002c3c  cmp     ebp, 2
0x180002c3f  jz      loc_180002B90
0x180002c45  mov     eax, 8
0x180002c4a  jmp     short loc_180002CBA
0x180002c4c  mov     rbx, [r15+60h]
0x180002c50  call    cs:__imp_GetCurrentThreadId
0x180002c56  mov     eax, eax
0x180002c58  jmp     loc_180002BD5
0x180002c5d  xor     edx, edx
0x180002c5f  mov     rcx, rbx
0x180002c62  call    ValidateHandle
0x180002c67  test    eax, eax
0x180002c69  jz      loc_180002E2D
0x180002c6f  cmp     dword ptr [rbx], 1
0x180002c72  jnz     short loc_180002C83
0x180002c74  cmp     [rbx+38h], r14d
0x180002c78  jl      loc_180002E23
0x180002c7e  mov     r14, rbx
0x180002c81  jmp     short loc_180002CA5
0x180002c83  mov     edx, 2
0x180002c88  mov     rcx, rbx
0x180002c8b  call    ValidateHandle
0x180002c90  test    eax, eax
0x180002c92  jz      loc_180002E2D
0x180002c98  mov     r14, [rbx+14h]
0x180002c9c  test    r14, r14
0x180002c9f  jz      loc_180002B9C
0x180002ca5  mov     edi, 200h
0x180002caa  cmp     ebp, 1
0x180002cad  jz      short loc_180002CD0
0x180002caf  test    ebp, ebp
0x180002cb1  jz      short loc_180002CE9
0x180002cb3  cmp     ebp, 2
0x180002cb6  jz      short loc_180002CE9
0x180002cb8  mov     eax, edi
0x180002cba  mov     rbp, [rsp+48h+arg_0]
0x180002cbf  mov     r14, [rsp+48h+arg_10]
0x180002cc4  add     rsp, 20h
0x180002cc8  pop     r15
0x180002cca  pop     r12
0x180002ccc  pop     rdi
0x180002ccd  pop     rsi
0x180002cce  pop     rbx
0x180002ccf  retn
0x180002cd0  mov     r9d, [r14+40h]
0x180002cd4  xor     r8d, r8d
0x180002cd7  cmp     r8d, r9d
0x180002cda  jnb     short loc_180002CB8
0x180002cdc  mov     rcx, [r14+44h]
0x180002ce0  mov     eax, [rsi+8]
0x180002ce3  cmp     [rcx+r8*8], eax
0x180002ce7  jnz     short loc_180002D47
0x180002ce9  lea     rcx, [r14-28h]; lpCriticalSection
0x180002ced  call    cs:__imp_EnterCriticalSection
0x180002cf3  mov     r9, r12
0x180002cf6  mov     r8, rsi
0x180002cf9  mov     edx, 6019h
0x180002cfe  mov     rcx, r14
0x180002d01  call    IDriverMessageId
0x180002d06  lea     rcx, [r14-28h]; lpCriticalSection
0x180002d0a  mov     rdi, rax
0x180002d0d  call    cs:__imp_LeaveCriticalSection
0x180002d13  test    edi, edi
0x180002d15  jnz     short loc_180002CB8
0x180002d17  mov     ecx, [rsi+8]
0x180002d1a  test    ecx, ecx
0x180002d1c  jz      loc_180002E37
0x180002d22  cmp     ecx, 1
0x180002d25  jnz     short loc_180002D40
0x180002d27  mov     rcx, [r15+58h]; hInstance
0x180002d2b  lea     r8, [rsi+18h]; lpBuffer
0x180002d2f  mov     r9d, 30h ; '0'; cchBufferMax
0x180002d35  mov     edx, 12Ch; uID
0x180002d3a  call    cs:__imp_LoadStringW
0x180002d40  xor     edi, edi
0x180002d42  jmp     loc_180002CB8
0x180002d47  inc     r8d
0x180002d4a  jmp     short loc_180002CD7
0x180002d4c  mov     eax, 1
0x180002d51  add     rsp, 20h
0x180002d55  pop     r15
0x180002d57  pop     r12
0x180002d59  pop     rdi
0x180002d5a  pop     rsi
0x180002d5b  pop     rbx
0x180002d5c  retn
0x180002d5d  mov     rcx, r15
0x180002d60  call    threadLeaveListShared
0x180002d65  lea     rcx, [r15+80h]
0x180002d6c  call    ReleaseLock
0x180002d71  mov     r13, [rsp+48h+arg_8]
0x180002d76  test    r14, r14
0x180002d79  jnz     loc_180002CA5
0x180002d7f  cmp     ebp, 1
0x180002d82  jnz     loc_180002E41
0x180002d88  cmp     [rsi+8], ebp
0x180002d8b  jz      loc_180002E41
0x180002d91  mov     eax, 200h
0x180002d96  jmp     loc_180002CBA
0x180002d9b  cmp     eax, 1
0x180002d9e  jnz     loc_180002BBA
0x180002da4  mov     r9d, [rbx+40h]
0x180002da8  test    r9d, r9d
0x180002dab  jz      loc_180002BBA
0x180002db1  mov     r10d, [rsi+8]
0x180002db5  xor     edx, edx
0x180002db7  lea     rcx, ds:0[rdx*8]
0x180002dbf  test    r10d, r10d
0x180002dc2  jz      short loc_180002DCE
0x180002dc4  mov     rax, [rbx+44h]
0x180002dc8  cmp     [rcx+rax], r10d
0x180002dcc  jnz     short loc_180002DE2
0x180002dce  mov     rax, [rbx+44h]
0x180002dd2  mov     r8d, [rax+rcx+4]
0x180002dd7  cmp     r8d, r13d
0x180002dda  jbe     short loc_180002DE2
0x180002ddc  mov     r13d, r8d
0x180002ddf  mov     r14, rbx
0x180002de2  inc     edx
0x180002de4  cmp     edx, r9d
0x180002de7  jb      short loc_180002DB7
0x180002de9  jmp     loc_180002BBA
0x180002dee  inc     r8d
0x180002df1  jmp     loc_180002C07
0x180002df6  mov     eax, 0Bh
0x180002dfb  jmp     loc_180002CBA
0x180002e00  mov     eax, 0Ah
0x180002e05  jmp     loc_180002CC4
0x180002e0a  xor     edx, edx
0x180002e0c  mov     rcx, rbx
0x180002e0f  call    ValidateHandle
0x180002e14  test    eax, eax
0x180002e16  jz      short loc_180002E2D
0x180002e18  cmp     dword ptr [rsi+8], 0
0x180002e1c  jnz     short loc_180002DF6
0x180002e1e  jmp     loc_180002B90
0x180002e23  mov     eax, 3
0x180002e28  jmp     loc_180002CBA
0x180002e2d  mov     eax, 5
0x180002e32  jmp     loc_180002CBA
0x180002e37  mov     edi, 1
0x180002e3c  jmp     loc_180002CB8
0x180002e41  mov     dword ptr [rsi+4], 0
0x180002e48  mov     dword ptr [rsi+8], 1
0x180002e4f  mov     qword ptr [rsi+0Ch], 10h
0x180002e57  mov     dword ptr [rsi+14h], 10h
0x180002e5e  jmp     loc_180002D27
```
