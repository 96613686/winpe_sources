# GetProcessName(void *,STRU *)

- ea: `0x180006198`
- end: `0x1800062ad`
- name: `?GetProcessName@@YAJPEAXPEAVSTRU@@@Z`
- size: `277`
- prototype: `__int64 __fastcall(HANDLE hProcess, struct STRU *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180005514`

## callees

- `0x180006198`
- `0x18000fb50`

## import_xrefs

- `KERNEL32!QueryFullProcessImageNameW` at `0x180006229`
- `KERNEL32!QueryFullProcessImageNameW` at `0x180006229`
- `KERNEL32!GetLastError` at `0x180006233`
- `KERNEL32!GetLastError` at `0x180006233`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180006209`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180006209`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180006285`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180006285`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x180006267`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x180006267`

## pseudocode

```c
__int64 __fastcall GetProcessName(HANDLE hProcess, struct STRU *a2)
{
  int v4; // ebx
  __int64 v5; // rdi
  WCHAR *v6; // r8
  __int64 v7; // rax
  DWORD dwSize; // [rsp+20h] [rbp-40h] BYREF
  _QWORD v10[4]; // [rsp+28h] [rbp-38h] BYREF
  LPWSTR lpExeName; // [rsp+48h] [rbp-18h]
  int v12; // [rsp+50h] [rbp-10h]
  __int16 v13; // [rsp+54h] [rbp-Ch]

  v12 = 32;
  v10[0] = 0;
  lpExeName = (LPWSTR)v10;
  v13 = 256;
  v4 = 1;
  if ( a2 && hProcess )
  {
    LODWORD(v5) = 130;
    while ( 1 )
    {
      v5 = (unsigned int)(2 * v5);
      dwSize = v5 + 1;
      if ( !BUFFER::Resize((BUFFER *)v10, 2 * v5 + 2) )
      {
        v4 = -2147024882;
        goto LABEL_17;
      }
      v6 = lpExeName;
      *lpExeName = 0;
      v6[v5] = 0;
      if ( QueryFullProcessImageNameW(hProcess, 0, v6, &dwSize) )
        break;
      if ( GetLastError() != 122 )
        goto LABEL_17;
      if ( (unsigned int)v5 > 0x41000 )
        goto LABEL_12;
    }
    v7 = -1;
    do
      ++v7;
    while ( lpExeName[v7] );
    if ( !v7 || (v4 = STRU::Copy(a2, lpExeName), v4 >= 0) )
LABEL_12:
      v4 = 0;
  }
  else
  {
    v4 = -2147024809;
  }
LABEL_17:
  BUFFER::~BUFFER((BUFFER *)v10);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180006198  mov     [rsp-28h+arg_10], rbx
0x18000619d  push    rbp
0x18000619e  push    rsi
0x18000619f  push    rdi
0x1800061a0  push    r14
0x1800061a2  push    r15
0x1800061a4  mov     rbp, rsp
0x1800061a7  sub     rsp, 60h
0x1800061ab  mov     rax, cs:__security_cookie
0x1800061b2  xor     rax, rsp
0x1800061b5  mov     [rbp+var_8], rax
0x1800061b9  xor     r15d, r15d
0x1800061bc  mov     [rbp+var_10], 20h ; ' '
0x1800061c3  mov     [rbp+var_38], r15
0x1800061c7  lea     rax, [rbp+var_38]
0x1800061cb  mov     [rbp+lpExeName], rax
0x1800061cf  mov     r14, rdx
0x1800061d2  mov     [rbp+var_C], 100h
0x1800061d8  mov     rsi, rcx
0x1800061db  lea     ebx, [r15+1]
0x1800061df  test    rdx, rdx
0x1800061e2  jz      loc_18000627C
0x1800061e8  test    rcx, rcx
0x1800061eb  jz      loc_18000627C
0x1800061f1  mov     edi, 82h
0x1800061f6  add     edi, edi
0x1800061f8  lea     rcx, [rbp+var_38]
0x1800061fc  lea     eax, [rdi+1]
0x1800061ff  lea     edx, ds:2[rdi*2]
0x180006206  mov     [rbp+dwSize], eax
0x180006209  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000620f  test    al, al
0x180006211  jz      short loc_180006275
0x180006213  mov     r8, [rbp+lpExeName]; lpExeName
0x180006217  lea     r9, [rbp+dwSize]; lpdwSize
0x18000621b  xor     edx, edx; dwFlags
0x18000621d  mov     rcx, rsi; hProcess
0x180006220  mov     [r8], r15w
0x180006224  mov     [r8+rdi*2], r15w
0x180006229  call    cs:__imp_QueryFullProcessImageNameW
0x18000622f  test    eax, eax
0x180006231  jnz     short loc_180006248
0x180006233  call    cs:__imp_GetLastError
0x180006239  cmp     eax, 7Ah ; 'z'
0x18000623c  jnz     short loc_180006281
0x18000623e  cmp     edi, 41000h
0x180006244  jbe     short loc_1800061F6
0x180006246  jmp     short loc_18000625F
0x180006248  mov     rdx, [rbp+lpExeName]
0x18000624c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006250  inc     rax
0x180006253  cmp     [rdx+rax*2], r15w
0x180006258  jnz     short loc_180006250
0x18000625a  test    rax, rax
0x18000625d  jnz     short loc_180006264
0x18000625f  mov     ebx, r15d
0x180006262  jmp     short loc_180006281
0x180006264  mov     rcx, r14
0x180006267  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000626d  mov     ebx, eax
0x18000626f  test    eax, eax
0x180006271  js      short loc_180006281
0x180006273  jmp     short loc_18000625F
0x180006275  mov     ebx, 8007000Eh
0x18000627a  jmp     short loc_180006281
0x18000627c  mov     ebx, 80070057h
0x180006281  lea     rcx, [rbp+var_38]
0x180006285  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000628b  mov     eax, ebx
0x18000628d  mov     rcx, [rbp+var_8]
0x180006291  xor     rcx, rsp; StackCookie
0x180006294  call    __security_check_cookie
0x180006299  mov     rbx, [rsp+60h+arg_10]
0x1800062a1  add     rsp, 60h
0x1800062a5  pop     r15
0x1800062a7  pop     r14
0x1800062a9  pop     rdi
0x1800062aa  pop     rsi
0x1800062ab  pop     rbp
0x1800062ac  retn
```
