# _GetAuthMethodGuids

- ea: `0x18000cf64`
- end: `0x18000d09d`
- name: `_GetAuthMethodGuids`
- size: `313`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _DWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007b00`
- `0x180007e20`

## callees

- `0x18000c33c`
- `0x18000cf64`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000d082`
- `KERNEL32!HeapFree` at `0x18000d082`
- `KERNEL32!HeapAlloc` at `0x18000d01d`
- `KERNEL32!HeapAlloc` at `0x18000d01d`
- `KERNEL32!GetProcessHeap` at `0x18000d00b`
- `KERNEL32!GetProcessHeap` at `0x18000d074`
- `KERNEL32!GetProcessHeap` at `0x18000d00b`
- `KERNEL32!GetProcessHeap` at `0x18000d074`
- `FVEAPI!FveGetAuthMethodGuids` at `0x18000cfd5`
- `FVEAPI!FveGetAuthMethodGuids` at `0x18000d041`
- `FVEAPI!FveGetAuthMethodGuids` at `0x18000cfd5`
- `FVEAPI!FveGetAuthMethodGuids` at `0x18000d041`
- `FVEAPI!FveCloseVolume` at `0x18000d061`
- `FVEAPI!FveCloseVolume` at `0x18000d061`
- `FVEAPI!FveOpenVolumeW` at `0x18000cfb8`
- `FVEAPI!FveOpenVolumeW` at `0x18000cfb8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetAuthMethodGuids(__int64 a1, _QWORD *a2, _DWORD *a3)
{
  int v5; // ebx
  void *v6; // rdi
  int AuthMethodGuids; // eax
  HANDLE ProcessHeap; // rax
  LPVOID v9; // rax
  int v10; // eax
  HANDLE v11; // rax
  int v13; // [rsp+20h] [rbp-10h] BYREF
  __int64 v14; // [rsp+28h] [rbp-8h] BYREF
  unsigned int v15; // [rsp+58h] [rbp+28h] BYREF
  SIZE_T dwBytes; // [rsp+68h] [rbp+38h] BYREF

  LODWORD(dwBytes) = 0;
  v15 = 0;
  v13 = 0;
  v14 = -1;
  if ( a2 && a3 )
  {
    v6 = 0;
    v5 = FveOpenVolumeW(a1, 0, &v14);
    if ( v5 >= 0 )
    {
      AuthMethodGuids = FveGetAuthMethodGuids(v14, 0, 0, &v15);
      v5 = 0;
      if ( AuthMethodGuids != 1 )
        v5 = AuthMethodGuids;
      if ( v5 >= 0 )
      {
        if ( v15 )
        {
          v5 = ULongLongToULong(16LL * v15, (unsigned int *)&dwBytes);
          if ( v5 >= 0 )
          {
            ProcessHeap = GetProcessHeap();
            v9 = HeapAlloc(ProcessHeap, 8u, (unsigned int)dwBytes);
            v6 = v9;
            if ( v9 )
            {
              v5 = FveGetAuthMethodGuids(v14, v9, v15, &v13);
              if ( v5 >= 0 )
              {
                v10 = v13;
                *a2 = v6;
                v6 = 0;
                *a3 = v10;
              }
            }
            else
            {
              v5 = -2147024882;
            }
          }
        }
        else
        {
          v5 = -2147023728;
        }
      }
    }
    if ( v14 != -1 )
    {
      FveCloseVolume();
      v14 = -1;
    }
    if ( v6 )
    {
      v11 = GetProcessHeap();
      HeapFree(v11, 0, v6);
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000cf64  mov     [rsp-18h+arg_0], rbx
0x18000cf69  mov     [rsp-18h+arg_10], rsi
0x18000cf6e  push    rbp
0x18000cf6f  push    rdi
0x18000cf70  push    r14
0x18000cf72  mov     rbp, rsp
0x18000cf75  sub     rsp, 30h
0x18000cf79  mov     dword ptr [rbp+dwBytes], 0
0x18000cf80  mov     rsi, r8
0x18000cf83  mov     [rbp+arg_8], 0
0x18000cf8a  mov     r14, rdx
0x18000cf8d  mov     [rbp+var_10], 0
0x18000cf94  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFFh
0x18000cf9c  test    rdx, rdx
0x18000cf9f  jnz     short loc_18000CFAB
0x18000cfa1  mov     ebx, 80004003h
0x18000cfa6  jmp     loc_18000D088
0x18000cfab  test    rsi, rsi
0x18000cfae  jz      short loc_18000CFA1
0x18000cfb0  lea     r8, [rbp+var_8]
0x18000cfb4  xor     edx, edx
0x18000cfb6  xor     edi, edi
0x18000cfb8  call    cs:__imp_FveOpenVolumeW
0x18000cfbe  mov     ebx, eax
0x18000cfc0  test    eax, eax
0x18000cfc2  js      loc_18000D057
0x18000cfc8  mov     rcx, [rbp+var_8]
0x18000cfcc  lea     r9, [rbp+arg_8]
0x18000cfd0  xor     r8d, r8d
0x18000cfd3  xor     edx, edx
0x18000cfd5  call    cs:__imp_FveGetAuthMethodGuids
0x18000cfdb  xor     ebx, ebx
0x18000cfdd  cmp     eax, 1
0x18000cfe0  cmovnz  ebx, eax
0x18000cfe3  test    ebx, ebx
0x18000cfe5  js      short loc_18000D057
0x18000cfe7  mov     eax, [rbp+arg_8]
0x18000cfea  test    eax, eax
0x18000cfec  jnz     short loc_18000CFF5
0x18000cfee  mov     ebx, 80070490h
0x18000cff3  jmp     short loc_18000D057
0x18000cff5  mov     rcx, rax
0x18000cff8  lea     rdx, [rbp+dwBytes]; unsigned int *
0x18000cffc  shl     rcx, 4; unsigned __int64
0x18000d000  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18000d005  mov     ebx, eax
0x18000d007  test    eax, eax
0x18000d009  js      short loc_18000D057
0x18000d00b  call    cs:__imp_GetProcessHeap
0x18000d011  mov     r8d, dword ptr [rbp+dwBytes]; dwBytes
0x18000d015  mov     edx, 8; dwFlags
0x18000d01a  mov     rcx, rax; hHeap
0x18000d01d  call    cs:__imp_HeapAlloc
0x18000d023  mov     rdi, rax
0x18000d026  test    rax, rax
0x18000d029  jnz     short loc_18000D032
0x18000d02b  mov     ebx, 8007000Eh
0x18000d030  jmp     short loc_18000D057
0x18000d032  mov     r8d, [rbp+arg_8]
0x18000d036  lea     r9, [rbp+var_10]
0x18000d03a  mov     rcx, [rbp+var_8]
0x18000d03e  mov     rdx, rdi
0x18000d041  call    cs:__imp_FveGetAuthMethodGuids
0x18000d047  mov     ebx, eax
0x18000d049  test    eax, eax
0x18000d04b  js      short loc_18000D057
0x18000d04d  mov     eax, [rbp+var_10]
0x18000d050  mov     [r14], rdi
0x18000d053  xor     edi, edi
0x18000d055  mov     [rsi], eax
0x18000d057  mov     rcx, [rbp+var_8]
0x18000d05b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000d05f  jz      short loc_18000D06F
0x18000d061  call    cs:__imp_FveCloseVolume
0x18000d067  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFFh
0x18000d06f  test    rdi, rdi
0x18000d072  jz      short loc_18000D088
0x18000d074  call    cs:__imp_GetProcessHeap
0x18000d07a  mov     r8, rdi; lpMem
0x18000d07d  xor     edx, edx; dwFlags
0x18000d07f  mov     rcx, rax; hHeap
0x18000d082  call    cs:__imp_HeapFree
0x18000d088  mov     rsi, [rsp+30h+arg_10]
0x18000d08d  mov     eax, ebx
0x18000d08f  mov     rbx, [rsp+30h+arg_0]
0x18000d094  add     rsp, 30h
0x18000d098  pop     r14
0x18000d09a  pop     rdi
0x18000d09b  pop     rbp
0x18000d09c  retn
```
