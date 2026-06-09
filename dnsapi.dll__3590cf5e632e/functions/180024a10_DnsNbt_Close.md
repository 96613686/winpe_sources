# DnsNbt_Close

- ea: `0x180024a10`
- end: `0x180024b6b`
- name: `DnsNbt_Close`
- size: `347`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800249b8`
- `0x18002625c`

## callees

- `0x180024a10`
- `0x18002b050`
- `0x1800317e0`
- `0x1800ddfa8`
- `0x1800dfa80`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024ae0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024ae0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180024b5a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180024b5a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024ab0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024ab0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180024a6e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180024a6e`

## pseudocode

```c
__int64 __fastcall DnsNbt_Close(char *lpMem)
{
  unsigned int v2; // r14d
  char *v3; // rdi
  unsigned int i; // esi
  struct _TP_IO *v5; // rbp
  void *v6; // rcx
  void *v7; // rcx
  HMODULE v8; // rcx
  __int64 result; // rax

  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    result = WPP_SF_q(1035, 10, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids, lpMem);
  if ( lpMem )
  {
    v2 = *((_DWORD *)lpMem + 3);
    v3 = lpMem + 624;
    for ( i = 0; i < v2; ++i )
    {
      if ( *(_QWORD *)v3 )
        CloseHandle(*(HANDLE *)v3);
      v5 = (struct _TP_IO *)*((_QWORD *)v3 + 72);
      if ( v5 )
      {
        if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
          WPP_SF_qD(1035, 18, WPP_0ee542721a7b375122a881c30985be4a_Traceguids, v5, 0);
        CloseThreadpoolIo(v5);
      }
      v3 += 1776;
    }
    v6 = (void *)*((_QWORD *)lpMem + 2);
    if ( v6 )
      DnsApiFree(v6);
    v7 = (void *)*((_QWORD *)lpMem + 4);
    if ( v7 )
    {
      DeRefQueryBlobEx(v7);
      *((_QWORD *)lpMem + 4) = 0;
    }
    if ( *((_DWORD *)lpMem + 11) )
      DeleteCriticalSection((LPCRITICAL_SECTION)(lpMem + 568));
    v8 = (HMODULE)*((_QWORD *)lpMem + 77);
    if ( v8 )
      FreeLibrary(v8);
    return DnsApiFree(lpMem);
  }
  return result;
}

```

## disassembly

```asm
0x180024a10  push    rbx
0x180024a12  push    rbp
0x180024a13  push    rsi
0x180024a14  push    rdi
0x180024a15  push    r14
0x180024a17  sub     rsp, 30h
0x180024a1b  mov     rbx, rcx
0x180024a1e  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180024a25  jnz     loc_180024AF1
0x180024a2b  test    rbx, rbx
0x180024a2e  jz      loc_180024AD4
0x180024a34  mov     r14d, [rbx+0Ch]
0x180024a38  lea     rdi, [rbx+270h]
0x180024a3f  xor     esi, esi
0x180024a41  test    r14d, r14d
0x180024a44  jz      short loc_180024A88
0x180024a46  mov     rcx, [rdi]; hObject
0x180024a49  test    rcx, rcx
0x180024a4c  jnz     loc_180024AE0
0x180024a52  mov     rbp, [rdi+240h]
0x180024a59  test    rbp, rbp
0x180024a5c  jz      short loc_180024A7A
0x180024a5e  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180024a65  jnz     loc_180024B0F
0x180024a6b  mov     rcx, rbp; pio
0x180024a6e  call    cs:__imp_CloseThreadpoolIo
0x180024a75  nop     dword ptr [rax+rax+00h]
0x180024a7a  add     rdi, 6F0h
0x180024a81  inc     esi
0x180024a83  cmp     esi, r14d
0x180024a86  jb      short loc_180024A46
0x180024a88  mov     rcx, [rbx+10h]; lpMem
0x180024a8c  test    rcx, rcx
0x180024a8f  jz      short loc_180024A96
0x180024a91  call    DnsApiFree
0x180024a96  mov     rcx, [rbx+20h]; lpMem
0x180024a9a  test    rcx, rcx
0x180024a9d  jnz     loc_180024B35
0x180024aa3  cmp     dword ptr [rbx+2Ch], 0
0x180024aa7  jz      short loc_180024ABC
0x180024aa9  lea     rcx, [rbx+238h]; lpCriticalSection
0x180024ab0  call    cs:__imp_DeleteCriticalSection
0x180024ab7  nop     dword ptr [rax+rax+00h]
0x180024abc  mov     rcx, [rbx+268h]; hLibModule
0x180024ac3  test    rcx, rcx
0x180024ac6  jnz     loc_180024B5A
0x180024acc  mov     rcx, rbx; lpMem
0x180024acf  call    DnsApiFree
0x180024ad4  add     rsp, 30h
0x180024ad8  pop     r14
0x180024ada  pop     rdi
0x180024adb  pop     rsi
0x180024adc  pop     rbp
0x180024add  pop     rbx
0x180024ade  retn
0x180024ae0  call    cs:__imp_CloseHandle
0x180024ae7  nop     dword ptr [rax+rax+00h]
0x180024aec  jmp     loc_180024A52
0x180024af1  mov     edx, 0Ah
0x180024af6  lea     r8, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids
0x180024afd  mov     ecx, 40Bh
0x180024b02  mov     r9, rbx
0x180024b05  call    WPP_SF_q
0x180024b0a  jmp     loc_180024A2B
0x180024b0f  mov     edx, 12h
0x180024b14  mov     [rsp+58h+var_38], 0
0x180024b1c  mov     ecx, 40Bh
0x180024b21  lea     r8, WPP_0ee542721a7b375122a881c30985be4a_Traceguids
0x180024b28  mov     r9, rbp
0x180024b2b  call    WPP_SF_qD
0x180024b30  jmp     loc_180024A6B
0x180024b35  mov     r9d, 11h
0x180024b3b  lea     rdx, aDnsnbtClose; "DnsNbt_Close"
0x180024b42  mov     r8d, 0E4h
0x180024b48  call    DeRefQueryBlobEx
0x180024b4d  mov     qword ptr [rbx+20h], 0
0x180024b55  jmp     loc_180024AA3
0x180024b5a  call    cs:__imp_FreeLibrary
0x180024b61  nop     dword ptr [rax+rax+00h]
0x180024b66  jmp     loc_180024ACC
```
