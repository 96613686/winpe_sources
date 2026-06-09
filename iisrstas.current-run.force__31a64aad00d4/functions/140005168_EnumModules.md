# EnumModules

- ea: `0x140005168`
- end: `0x1400053e2`
- name: `EnumModules`
- size: `634`
- prototype: `__int64 __fastcall(HANDLE hProcess)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400049b0`

## callees

- `0x140005168`
- `0x14000548e`
- `0x1400054c0`

## import_xrefs

- `msvcrt!sprintf_s` at `0x140005304`
- `msvcrt!sprintf_s` at `0x14000535e`
- `msvcrt!sprintf_s` at `0x140005304`
- `msvcrt!sprintf_s` at `0x14000535e`
- `msvcrt!_strcmpi` at `0x14000538d`
- `msvcrt!_strcmpi` at `0x14000538d`
- `ntdll!NtQueryInformationProcess` at `0x1400051f9`
- `ntdll!NtQueryInformationProcess` at `0x1400051f9`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140005233`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140005261`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14000529e`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1400052d3`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140005331`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140005233`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140005261`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14000529e`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1400052d3`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140005331`

## pseudocode

```c
char __fastcall EnumModules(HANDLE hProcess, __int64 a2, __int64 a3)
{
  __int64 v5; // rdi
  __int64 v6; // rax
  const char *v7; // rdx
  __int64 v9; // [rsp+30h] [rbp-D0h] BYREF
  __int64 Buffer; // [rsp+38h] [rbp-C8h] BYREF
  _OWORD ProcessInformation[3]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v12[16]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v13; // [rsp+80h] [rbp-80h]
  __int64 v14; // [rsp+A0h] [rbp-60h]
  __int64 v15; // [rsp+A8h] [rbp-58h]
  int v16; // [rsp+B0h] [rbp-50h]
  unsigned __int16 v17; // [rsp+BAh] [rbp-46h]
  LPCVOID v18; // [rsp+C0h] [rbp-40h]
  unsigned __int16 v19; // [rsp+CAh] [rbp-36h]
  LPCVOID lpBaseAddress; // [rsp+D0h] [rbp-30h]
  _QWORD v21[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  int v22; // [rsp+1C0h] [rbp+C0h]
  char String1[260]; // [rsp+1C4h] [rbp+C4h] BYREF
  char v24[264]; // [rsp+2C8h] [rbp+1C8h] BYREF
  _BYTE v25[518]; // [rsp+3D0h] [rbp+2D0h] BYREF
  __int16 v26; // [rsp+5D6h] [rbp+4D6h]

  Buffer = 0;
  v9 = 0;
  memset(ProcessInformation, 0, 44);
  memset_0(v12, 0, 0x138u);
  memset_0(v21, 0, 0x220u);
  if ( NtQueryInformationProcess(hProcess, ProcessBasicInformation, ProcessInformation, 0x30u, 0) >= 0 )
  {
    if ( *((_QWORD *)&ProcessInformation[0] + 1) )
    {
      if ( ReadProcessMemory(hProcess, (LPCVOID)(*((_QWORD *)&ProcessInformation[0] + 1) + 24LL), &Buffer, 8u, 0) )
      {
        v5 = Buffer + 32;
        if ( ReadProcessMemory(hProcess, (LPCVOID)(Buffer + 32), &v9, 8u, 0) )
        {
          v6 = v9;
          if ( v9 == v5 )
            return 1;
          while ( ReadProcessMemory(hProcess, (LPCVOID)(v6 - 16), v12, 0x138u, 0) )
          {
            if ( v19 > 0x208u )
              break;
            if ( !ReadProcessMemory(hProcess, lpBaseAddress, v25, v19, 0) )
              break;
            v26 = 0;
            sprintf_s(String1, 0x104u, "%ws", v25);
            if ( v17 > 0x208u || !ReadProcessMemory(hProcess, v18, v25, v17, 0) )
              break;
            v26 = 0;
            sprintf_s(v24, 0x104u, "%ws", v25);
            v7 = *(const char **)a3;
            v21[0] = v14;
            v21[1] = v15;
            v22 = v16;
            if ( !_strcmpi(String1, v7) )
            {
              **(_DWORD **)(a3 + 8) = 1;
              return 1;
            }
            v6 = v13;
            v9 = v13;
            if ( v13 == v5 )
              return 1;
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140005168  mov     [rsp-8+arg_8], rbx
0x14000516d  mov     [rsp-8+arg_18], rsi
0x140005172  push    rbp
0x140005173  push    rdi
0x140005174  push    r15
0x140005176  lea     rbp, [rsp-4F0h]
0x14000517e  sub     rsp, 5F0h
0x140005185  mov     rax, cs:__security_cookie
0x14000518c  xor     rax, rsp
0x14000518f  mov     [rbp+500h+var_20], rax
0x140005196  xorps   xmm0, xmm0
0x140005199  xor     eax, eax
0x14000519b  mov     rsi, r8
0x14000519e  mov     [rsp+600h+Buffer], rax
0x1400051a3  mov     rbx, rcx
0x1400051a6  mov     [rsp+600h+var_5D0], rax
0x1400051ab  movups  xmmword ptr [rsp+600h+var_5B0], xmm0
0x1400051b0  xor     edx, edx; Val
0x1400051b2  lea     rcx, [rsp+600h+var_590]; void *
0x1400051b7  mov     r8d, 138h; Size
0x1400051bd  movups  xmmword ptr [rsp+600h+var_5B0+0Ch], xmm0
0x1400051c2  movups  [rsp+600h+ProcessInformation], xmm0
0x1400051c7  call    memset_0
0x1400051cc  xor     edx, edx; Val
0x1400051ce  lea     rcx, [rbp+500h+var_450]; void *
0x1400051d5  mov     r8d, 220h; Size
0x1400051db  call    memset_0
0x1400051e0  mov     r9d, 30h ; '0'; ProcessInformationLength
0x1400051e6  mov     [rsp+600h+ReturnLength], 0; ReturnLength
0x1400051ef  lea     r8, [rsp+600h+ProcessInformation]; ProcessInformation
0x1400051f4  xor     edx, edx; ProcessInformationClass
0x1400051f6  mov     rcx, rbx; ProcessHandle
0x1400051f9  call    cs:__imp_NtQueryInformationProcess
0x1400051ff  test    eax, eax
0x140005201  js      loc_1400053B9
0x140005207  mov     rdx, qword ptr [rsp+600h+ProcessInformation+8]
0x14000520c  test    rdx, rdx
0x14000520f  jz      loc_1400053B9
0x140005215  mov     r15d, 8
0x14000521b  mov     [rsp+600h+ReturnLength], 0; lpNumberOfBytesRead
0x140005224  mov     r9d, r15d; nSize
0x140005227  lea     r8, [rsp+600h+Buffer]; lpBuffer
0x14000522c  add     rdx, 18h; lpBaseAddress
0x140005230  mov     rcx, rbx; hProcess
0x140005233  call    cs:__imp_ReadProcessMemory
0x140005239  test    eax, eax
0x14000523b  jz      loc_1400053B9
0x140005241  mov     rdi, [rsp+600h+Buffer]
0x140005246  lea     r8, [rsp+600h+var_5D0]; lpBuffer
0x14000524b  add     rdi, 20h ; ' '
0x14000524f  mov     [rsp+600h+ReturnLength], 0; lpNumberOfBytesRead
0x140005258  mov     rdx, rdi; lpBaseAddress
0x14000525b  mov     r9d, r15d; nSize
0x14000525e  mov     rcx, rbx; hProcess
0x140005261  call    cs:__imp_ReadProcessMemory
0x140005267  test    eax, eax
0x140005269  jz      loc_1400053B9
0x14000526f  mov     rax, [rsp+600h+var_5D0]
0x140005274  cmp     rax, rdi
0x140005277  jz      loc_1400053B5
0x14000527d  mov     r15d, 208h
0x140005283  lea     rdx, [rax-10h]; lpBaseAddress
0x140005287  mov     [rsp+600h+ReturnLength], 0; lpNumberOfBytesRead
0x140005290  mov     r9d, 138h; nSize
0x140005296  lea     r8, [rsp+600h+var_590]; lpBuffer
0x14000529b  mov     rcx, rbx; hProcess
0x14000529e  call    cs:__imp_ReadProcessMemory
0x1400052a4  test    eax, eax
0x1400052a6  jz      loc_1400053B9
0x1400052ac  cmp     [rbp+500h+var_536], r15w
0x1400052b1  ja      loc_1400053B9
0x1400052b7  movzx   r9d, [rbp+500h+var_536]; nSize
0x1400052bc  lea     r8, [rbp+500h+var_230]; lpBuffer
0x1400052c3  mov     rdx, [rbp+500h+lpBaseAddress]; lpBaseAddress
0x1400052c7  mov     rcx, rbx; hProcess
0x1400052ca  mov     [rsp+600h+ReturnLength], 0; lpNumberOfBytesRead
0x1400052d3  call    cs:__imp_ReadProcessMemory
0x1400052d9  test    eax, eax
0x1400052db  jz      loc_1400053B9
0x1400052e1  xor     eax, eax
0x1400052e3  lea     r9, [rbp+500h+var_230]
0x1400052ea  lea     r8, aWs; "%ws"
0x1400052f1  mov     [rbp+500h+var_2A], ax
0x1400052f8  mov     edx, 104h; BufferCount
0x1400052fd  lea     rcx, [rbp+500h+String1]; Buffer
0x140005304  call    cs:__imp_sprintf_s
0x14000530a  cmp     [rbp+500h+var_546], r15w
0x14000530f  ja      loc_1400053B9
0x140005315  movzx   r9d, [rbp+500h+var_546]; nSize
0x14000531a  lea     r8, [rbp+500h+var_230]; lpBuffer
0x140005321  mov     rdx, [rbp+500h+var_540]; lpBaseAddress
0x140005325  mov     rcx, rbx; hProcess
0x140005328  mov     [rsp+600h+ReturnLength], 0; lpNumberOfBytesRead
0x140005331  call    cs:__imp_ReadProcessMemory
0x140005337  test    eax, eax
0x140005339  jz      short loc_1400053B9
0x14000533b  xor     eax, eax
0x14000533d  lea     r9, [rbp+500h+var_230]
0x140005344  lea     r8, aWs; "%ws"
0x14000534b  mov     [rbp+500h+var_2A], ax
0x140005352  mov     edx, 104h; BufferCount
0x140005357  lea     rcx, [rbp+500h+var_338]; Buffer
0x14000535e  call    cs:__imp_sprintf_s
0x140005364  mov     rax, [rbp+500h+var_560]
0x140005368  lea     rcx, [rbp+500h+String1]; String1
0x14000536f  mov     rdx, [rsi]; String2
0x140005372  mov     [rbp+500h+var_450], rax
0x140005379  mov     rax, [rbp+500h+var_558]
0x14000537d  mov     [rbp+500h+var_448], rax
0x140005384  mov     eax, [rbp+500h+var_550]
0x140005387  mov     [rbp+500h+var_440], eax
0x14000538d  call    cs:__imp__strcmpi
0x140005393  test    eax, eax
0x140005395  jz      short loc_1400053AB
0x140005397  mov     rax, [rbp+500h+var_580]
0x14000539b  mov     [rsp+600h+var_5D0], rax
0x1400053a0  cmp     rax, rdi
0x1400053a3  jnz     loc_140005283
0x1400053a9  jmp     short loc_1400053B5
0x1400053ab  mov     rcx, [rsi+8]
0x1400053af  mov     dword ptr [rcx], 1
0x1400053b5  mov     al, 1
0x1400053b7  jmp     short loc_1400053BB
0x1400053b9  xor     al, al
0x1400053bb  mov     rcx, [rbp+500h+var_20]
0x1400053c2  xor     rcx, rsp; StackCookie
0x1400053c5  call    __security_check_cookie
0x1400053ca  lea     r11, [rsp+600h+var_10]
0x1400053d2  mov     rbx, [r11+28h]
0x1400053d6  mov     rsi, [r11+38h]
0x1400053da  mov     rsp, r11
0x1400053dd  pop     r15
0x1400053df  pop     rdi
0x1400053e0  pop     rbp
0x1400053e1  retn
```
