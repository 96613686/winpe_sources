# CCrashReport::MatchRemoteEnvironmentVariable(void *,wchar_t const *,wchar_t const *)

- ea: `0x1800138bc`
- end: `0x180013b6e`
- name: `?MatchRemoteEnvironmentVariable@CCrashReport@@CAJPEAXPEB_W1@Z`
- size: `690`
- prototype: `__int64 __fastcall(HANDLE hProcess, const wchar_t *, const wchar_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ff8c`
- `0x180014c34`

## callees

- `0x1800138bc`
- `0x18003e5a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180013a92`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180013a9e`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180013af4`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180013b00`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180013a92`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180013a9e`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180013af4`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180013b00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001395d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001395d`
- `ntdll!NtQueryInformationProcess` at `0x18001391e`
- `ntdll!NtQueryInformationProcess` at `0x18001391e`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180013953`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800139ac`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180013a32`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180013953`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800139ac`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180013a32`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800139da`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800139da`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180013b4b`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180013b4b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCrashReport::MatchRemoteEnvironmentVariable(HANDLE hProcess, const wchar_t *a2, const wchar_t *a3)
{
  char *v4; // r14
  NTSTATUS v5; // ebx
  int v6; // ebx
  signed int LastError; // eax
  char *v8; // rbx
  unsigned __int64 v9; // r13
  __int64 v10; // rdx
  int v11; // r15d
  __int64 v12; // rdi
  SIZE_T v13; // rcx
  unsigned __int16 v14; // si
  __int16 v15; // bx
  __int16 v16; // bx
  __int16 v17; // ax
  bool v18; // zf
  SIZE_T NumberOfBytesRead; // [rsp+38h] [rbp-39h] BYREF
  char *v21; // [rsp+40h] [rbp-31h]
  __int64 Buffer; // [rsp+48h] [rbp-29h] BYREF
  LPCVOID lpBaseAddress; // [rsp+50h] [rbp-21h] BYREF
  __int64 v24; // [rsp+58h] [rbp-19h]
  char *v25; // [rsp+60h] [rbp-11h]
  _OWORD ProcessInformation[6]; // [rsp+68h] [rbp-9h] BYREF
  ULONG ReturnLength; // [rsp+E0h] [rbp+6Fh] BYREF
  int v28; // [rsp+E4h] [rbp+73h]
  const wchar_t *v29; // [rsp+E8h] [rbp+77h]
  SIZE_T v30; // [rsp+F0h] [rbp+7Fh] BYREF

  v29 = a3;
  v28 = HIDWORD(a2);
  ReturnLength = 0;
  NumberOfBytesRead = 0;
  memset(ProcessInformation, 0, 48);
  Buffer = 0;
  lpBaseAddress = 0;
  v4 = 0;
  v30 = 0;
  v5 = NtQueryInformationProcess(hProcess, ProcessBasicInformation, ProcessInformation, 0x30u, &ReturnLength);
  if ( v5 < 0 )
  {
    v6 = v5 | 0x10000000;
    goto LABEL_41;
  }
  if ( !ReadProcessMemory(
          hProcess,
          (LPCVOID)(*((_QWORD *)&ProcessInformation[0] + 1) + 32LL),
          &Buffer,
          8u,
          &NumberOfBytesRead) )
    goto LABEL_4;
  if ( NumberOfBytesRead != 8 )
    goto LABEL_10;
  if ( !ReadProcessMemory(hProcess, (LPCVOID)(Buffer + 128), &lpBaseAddress, 8u, &NumberOfBytesRead) )
  {
LABEL_4:
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 >= 0 )
      v6 = -2147467259;
    goto LABEL_41;
  }
  if ( NumberOfBytesRead != 8 )
  {
LABEL_10:
    v6 = -2147024597;
    goto LABEL_41;
  }
  v8 = (char *)lpBaseAddress;
  v21 = (char *)lpBaseAddress;
  v30 = 0;
  v4 = (char *)VirtualAlloc(0, 0x1000u, 0x1000u, 4u);
  v25 = v4;
  if ( v4 )
  {
    v9 = 0;
    v10 = 0;
    v11 = 0;
    v12 = 0;
    v13 = v30;
    while ( 1 )
    {
      if ( v10 + 2 > v13 )
      {
        if ( v10 != v13 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v13);
        if ( !ReadProcessMemory(hProcess, v8, v4, 0x1000u, &v30) )
          goto LABEL_4;
        v10 = 0;
        v13 = v30;
        v8 += v30;
        v21 = v8;
        v9 += v30;
      }
      v24 = v10 + 2;
      if ( v10 + 2 > v13 )
      {
LABEL_29:
        v6 = -2147024886;
        goto LABEL_41;
      }
      v14 = *(_WORD *)&v4[v10];
      if ( v11 )
      {
        if ( v11 == 1 )
        {
          v15 = _o_towlower(v29[v12]);
          if ( v15 != (unsigned __int16)_o_towlower(v14) )
          {
            v6 = -2147024883;
            goto LABEL_41;
          }
          if ( !v14 )
          {
            v6 = 0;
            goto LABEL_41;
          }
          ++v12;
          v13 = v30;
          v8 = v21;
        }
        else if ( !v14 )
        {
          v11 = 0;
        }
      }
      else
      {
        if ( !v14 )
        {
          v6 = -2147024693;
          goto LABEL_41;
        }
        if ( v14 != 61 || aJsDebug[v12] )
        {
          v16 = _o_towlower(aJsDebug[v12]);
          v17 = _o_towlower(v14);
          v13 = v30;
          v18 = v16 == v17;
          v8 = v21;
          if ( v18 )
          {
            ++v12;
          }
          else
          {
            v12 = 0;
            v11 = 2;
          }
        }
        else
        {
          v12 = 0;
          v11 = 1;
        }
      }
      v10 = v24;
      if ( v9 >= 0x40000 )
        goto LABEL_29;
    }
  }
  v6 = -2147024882;
LABEL_41:
  if ( v4 )
    VirtualFree(v4, 0, 0x8000u);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800138bc  mov     rax, rsp
0x1800138bf  mov     [rax+8], rbx
0x1800138c3  mov     [rax+18h], r8
0x1800138c7  mov     [rax+10h], rdx
0x1800138cb  push    rbp
0x1800138cc  push    rsi
0x1800138cd  push    rdi
0x1800138ce  push    r12
0x1800138d0  push    r13
0x1800138d2  push    r14
0x1800138d4  push    r15
0x1800138d6  lea     rbp, [rax-5Fh]
0x1800138da  sub     rsp, 90h
0x1800138e1  mov     r12, rcx
0x1800138e4  xor     esi, esi
0x1800138e6  mov     [rbp+57h+ReturnLength], esi
0x1800138e9  mov     [rbp+57h+NumberOfBytesRead], rsi
0x1800138ed  xorps   xmm0, xmm0
0x1800138f0  movups  [rbp+57h+ProcessInformation], xmm0
0x1800138f4  movups  [rbp+57h+var_50], xmm0
0x1800138f8  movups  [rbp+57h+var_40], xmm0
0x1800138fc  mov     [rbp+57h+Buffer], rsi
0x180013900  mov     [rbp+57h+lpBaseAddress], rsi
0x180013904  mov     r14d, esi
0x180013907  mov     [rbp+57h+arg_18], rsi
0x18001390b  lea     rax, [rbp+57h+ReturnLength]
0x18001390f  mov     [rsp+20h], rax; ReturnLength
0x180013914  lea     r9d, [rsi+30h]; ProcessInformationLength
0x180013918  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x18001391c  xor     edx, edx; ProcessInformationClass
0x18001391e  call    cs:__imp_NtQueryInformationProcess
0x180013924  mov     ebx, eax
0x180013926  test    eax, eax
0x180013928  jns     short loc_180013933
0x18001392a  bts     ebx, 1Ch
0x18001392e  jmp     loc_180013B3B
0x180013933  mov     rdx, qword ptr [rbp+57h+ProcessInformation+8]
0x180013937  add     rdx, 20h ; ' '; lpBaseAddress
0x18001393b  lea     rax, [rbp+57h+NumberOfBytesRead]
0x18001393f  mov     [rsp+20h], rax; lpNumberOfBytesRead
0x180013944  mov     ebx, 8
0x180013949  mov     r9d, ebx; nSize
0x18001394c  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x180013950  mov     rcx, r12; hProcess
0x180013953  call    cs:__imp_ReadProcessMemory
0x180013959  test    eax, eax
0x18001395b  jnz     short loc_180013981
0x18001395d  call    cs:__imp_GetLastError
0x180013963  mov     ebx, eax
0x180013965  test    eax, eax
0x180013967  jle     short loc_180013972
0x180013969  movzx   ebx, ax
0x18001396c  or      ebx, 80070000h
0x180013972  mov     eax, 80004005h
0x180013977  test    ebx, ebx
0x180013979  cmovns  ebx, eax
0x18001397c  jmp     loc_180013B3B
0x180013981  cmp     [rbp+57h+NumberOfBytesRead], rbx
0x180013985  jz      short loc_180013991
0x180013987  mov     ebx, 8007012Bh
0x18001398c  jmp     loc_180013B3B
0x180013991  mov     rdx, [rbp+57h+Buffer]
0x180013995  sub     rdx, 0FFFFFFFFFFFFFF80h; lpBaseAddress
0x180013999  lea     rax, [rbp+57h+NumberOfBytesRead]
0x18001399d  mov     [rsp+20h], rax; lpNumberOfBytesRead
0x1800139a2  mov     r9, rbx; nSize
0x1800139a5  lea     r8, [rbp+57h+lpBaseAddress]; lpBuffer
0x1800139a9  mov     rcx, r12; hProcess
0x1800139ac  call    cs:__imp_ReadProcessMemory
0x1800139b2  test    eax, eax
0x1800139b4  jz      short loc_18001395D
0x1800139b6  cmp     [rbp+57h+NumberOfBytesRead], rbx
0x1800139ba  jnz     short loc_180013987
0x1800139bc  mov     rbx, [rbp+57h+lpBaseAddress]
0x1800139c0  mov     [rbp+57h+var_88], rbx
0x1800139c4  mov     [rbp+57h+arg_18], rsi
0x1800139c8  mov     eax, 1000h
0x1800139cd  mov     r9d, 4; flProtect
0x1800139d3  mov     r8d, eax; flAllocationType
0x1800139d6  mov     edx, eax; dwSize
0x1800139d8  xor     ecx, ecx; lpAddress
0x1800139da  call    cs:__imp_VirtualAlloc
0x1800139e0  mov     r14, rax
0x1800139e3  mov     [rbp+57h+var_68], rax
0x1800139e7  test    rax, rax
0x1800139ea  jz      loc_180013B36
0x1800139f0  mov     r13, rsi
0x1800139f3  mov     rdx, rsi
0x1800139f6  mov     r15d, esi
0x1800139f9  mov     rdi, rsi
0x1800139fc  mov     rcx, [rbp+57h+arg_18]
0x180013a00  lea     r8, aJsDebug; "JS_DEBUG"
0x180013a07  lea     rax, [rdx+2]
0x180013a0b  cmp     rax, rcx
0x180013a0e  jbe     short loc_180013A58
0x180013a10  cmp     rdx, rcx
0x180013a13  jz      short loc_180013A1A
0x180013a15  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180013a1a  lea     rax, [rbp+57h+arg_18]
0x180013a1e  mov     [rsp+20h], rax; lpNumberOfBytesRead
0x180013a23  mov     r9d, 1000h; nSize
0x180013a29  mov     r8, r14; lpBuffer
0x180013a2c  mov     rdx, rbx; lpBaseAddress
0x180013a2f  mov     rcx, r12; hProcess
0x180013a32  call    cs:__imp_ReadProcessMemory
0x180013a38  test    eax, eax
0x180013a3a  jz      loc_18001395D
0x180013a40  mov     rdx, rsi
0x180013a43  mov     rcx, [rbp+57h+arg_18]
0x180013a47  add     rbx, rcx
0x180013a4a  mov     [rbp+57h+var_88], rbx
0x180013a4e  add     r13, rcx
0x180013a51  lea     r8, aJsDebug; "JS_DEBUG"
0x180013a58  lea     rax, [rdx+2]
0x180013a5c  mov     [rbp+57h+var_70], rax
0x180013a60  cmp     rax, rcx
0x180013a63  ja      short loc_180013ACC
0x180013a65  movzx   esi, word ptr [r14+rdx]
0x180013a6a  mov     edx, r15d
0x180013a6d  xor     eax, eax
0x180013a6f  test    r15d, r15d
0x180013a72  jz      short loc_180013AD3
0x180013a74  sub     edx, 1
0x180013a77  jz      short loc_180013A8A
0x180013a79  cmp     edx, 1
0x180013a7c  jnz     short loc_180013AB9
0x180013a7e  test    si, si
0x180013a81  jnz     short loc_180013AB9
0x180013a83  xor     esi, esi
0x180013a85  mov     r15d, esi
0x180013a88  jmp     short loc_180013ABB
0x180013a8a  mov     rax, [rbp+57h+arg_10]
0x180013a8e  movzx   ecx, word ptr [rax+rdi*2]
0x180013a92  call    cs:__imp__o_towlower
0x180013a98  movzx   ebx, ax
0x180013a9b  movzx   ecx, si
0x180013a9e  call    cs:__imp__o_towlower
0x180013aa4  cmp     bx, ax
0x180013aa7  jnz     short loc_180013B28
0x180013aa9  test    si, si
0x180013aac  jz      short loc_180013B22
0x180013aae  inc     rdi
0x180013ab1  mov     rcx, [rbp+57h+arg_18]
0x180013ab5  mov     rbx, [rbp+57h+var_88]
0x180013ab9  xor     esi, esi
0x180013abb  mov     rdx, [rbp+57h+var_70]
0x180013abf  cmp     r13, 40000h
0x180013ac6  jb      loc_180013A00
0x180013acc  mov     ebx, 8007000Ah
0x180013ad1  jmp     short loc_180013B3B
0x180013ad3  test    si, si
0x180013ad6  jz      short loc_180013B2F
0x180013ad8  cmp     si, 3Dh ; '='
0x180013adc  jnz     short loc_180013AEF
0x180013ade  cmp     [r8+rdi*2], ax
0x180013ae3  jnz     short loc_180013AEF
0x180013ae5  xor     esi, esi
0x180013ae7  mov     edi, esi
0x180013ae9  lea     r15d, [rsi+1]
0x180013aed  jmp     short loc_180013ABB
0x180013aef  movzx   ecx, word ptr [r8+rdi*2]
0x180013af4  call    cs:__imp__o_towlower
0x180013afa  movzx   ebx, ax
0x180013afd  movzx   ecx, si
0x180013b00  call    cs:__imp__o_towlower
0x180013b06  mov     rcx, [rbp+57h+arg_18]
0x180013b0a  cmp     bx, ax
0x180013b0d  mov     rbx, [rbp+57h+var_88]
0x180013b11  jnz     short loc_180013B18
0x180013b13  inc     rdi
0x180013b16  jmp     short loc_180013AB9
0x180013b18  xor     esi, esi
0x180013b1a  mov     edi, esi
0x180013b1c  lea     r15d, [rsi+2]
0x180013b20  jmp     short loc_180013ABB
0x180013b22  xor     esi, esi
0x180013b24  mov     ebx, esi
0x180013b26  jmp     short loc_180013B3B
0x180013b28  mov     ebx, 8007000Dh
0x180013b2d  jmp     short loc_180013B3B
0x180013b2f  mov     ebx, 800700CBh
0x180013b34  jmp     short loc_180013B3B
0x180013b36  mov     ebx, 8007000Eh
0x180013b3b  test    r14, r14
0x180013b3e  jz      short loc_180013B51
0x180013b40  xor     edx, edx; dwSize
0x180013b42  mov     r8d, 8000h; dwFreeType
0x180013b48  mov     rcx, r14; lpAddress
0x180013b4b  call    cs:__imp_VirtualFree
0x180013b51  mov     eax, ebx
0x180013b53  mov     rbx, [rsp+0C0h+arg_0]
0x180013b5b  add     rsp, 90h
0x180013b62  pop     r15
0x180013b64  pop     r14
0x180013b66  pop     r13
0x180013b68  pop     r12
0x180013b6a  pop     rdi
0x180013b6b  pop     rsi
0x180013b6c  pop     rbp
0x180013b6d  retn
```
