# CreateDhcpContext

- ea: `0x18003b988`
- end: `0x18003ba7d`
- name: `CreateDhcpContext`
- size: `245`
- prototype: `__int64 __fastcall(_QWORD *, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18003ba84`
- `0x18003c554`
- `0x18003c9d8`

## callees

- `0x180005670`
- `0x180006440`
- `0x18001d826`
- `0x18003b988`
- `0x18004d1a0`
- `0x18004d1e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003ba45`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003ba45`

## pseudocode

```c
__int64 __fastcall CreateDhcpContext(_QWORD *a1, unsigned int a2)
{
  __int64 v2; // rsi
  unsigned int v4; // eax
  unsigned int v5; // ecx
  unsigned int v6; // ebx
  unsigned int v7; // eax
  __int64 v8; // rcx
  size_t v9; // rbp
  char *v10; // rax
  char *v11; // rdi
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rax

  v2 = a2;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 11, WPP_c84194e7b785338e3b207dae288fd792_Traceguids);
  v4 = (v2 + 7) & 0xFFFFFFF8;
  v5 = v4 + 2176;
  if ( v4 + 2176 < v4 || (v7 = v4 + 6272, v5 + 4096 < v5) || (v8 = v5 + 12288, (unsigned int)v8 < v7) )
  {
    v6 = WX_WIN32_FROM_HR(2147942934LL);
  }
  else
  {
    v9 = (unsigned int)v8;
    v10 = (char *)DhcpAlloc(v8);
    v11 = v10;
    if ( v10 )
    {
      v6 = 0;
      memset_0(v10, 0, v9);
      v12 = (unsigned __int64)(v11 + 2183) & 0xFFFFFFFFFFFFFFF8uLL;
      *((_QWORD *)v11 + 11) = v12;
      v13 = (v12 + v2 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      *((_QWORD *)v11 + 94) = v13;
      *((_QWORD *)v11 + 250) = (v13 + 4103) & 0xFFFFFFFFFFFFFFF8uLL;
      InitializeCriticalSection((LPCRITICAL_SECTION)(v11 + 592));
      *a1 = v11;
    }
    else
    {
      v6 = 8;
    }
  }
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 12, WPP_c84194e7b785338e3b207dae288fd792_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18003b988  push    rbx
0x18003b98a  push    rbp
0x18003b98b  push    rsi
0x18003b98c  push    rdi
0x18003b98d  push    r14
0x18003b98f  sub     rsp, 20h
0x18003b993  mov     esi, edx
0x18003b995  mov     r14, rcx
0x18003b998  test    byte ptr cs:xmmword_1800616A0, 10h
0x18003b99f  jz      short loc_18003B9B7
0x18003b9a1  mov     edx, 0Bh
0x18003b9a6  lea     r8, WPP_c84194e7b785338e3b207dae288fd792_Traceguids
0x18003b9ad  mov     ecx, 404h
0x18003b9b2  call    WPP_SF_
0x18003b9b7  lea     eax, [rsi+7]
0x18003b9ba  and     eax, 0FFFFFFF8h
0x18003b9bd  lea     ecx, [rax+880h]
0x18003b9c3  cmp     ecx, eax
0x18003b9c5  jnb     short loc_18003B9D5
0x18003b9c7  mov     ecx, 80070216h
0x18003b9cc  call    WX_WIN32_FROM_HR
0x18003b9d1  mov     ebx, eax
0x18003b9d3  jmp     short loc_18003BA4E
0x18003b9d5  lea     eax, [rcx+1000h]
0x18003b9db  cmp     eax, ecx
0x18003b9dd  jb      short loc_18003B9C7
0x18003b9df  lea     ecx, [rax+2000h]
0x18003b9e5  cmp     ecx, eax
0x18003b9e7  jb      short loc_18003B9C7
0x18003b9e9  mov     ebp, ecx
0x18003b9eb  call    DhcpAlloc
0x18003b9f0  mov     rdi, rax
0x18003b9f3  test    rax, rax
0x18003b9f6  jnz     short loc_18003B9FD
0x18003b9f8  lea     ebx, [rax+8]
0x18003b9fb  jmp     short loc_18003BA4E
0x18003b9fd  mov     r8, rbp; Size
0x18003ba00  xor     edx, edx; Val
0x18003ba02  mov     rcx, rdi; void *
0x18003ba05  xor     ebx, ebx
0x18003ba07  call    memset_0
0x18003ba0c  lea     rcx, [rdi+887h]
0x18003ba13  and     rcx, 0FFFFFFFFFFFFFFF8h
0x18003ba17  lea     rax, [rsi+7]
0x18003ba1b  add     rax, rcx
0x18003ba1e  mov     [rdi+58h], rcx
0x18003ba22  and     rax, 0FFFFFFFFFFFFFFF8h
0x18003ba26  lea     rcx, [rdi+250h]; lpCriticalSection
0x18003ba2d  mov     [rdi+2F0h], rax
0x18003ba34  add     rax, 1007h
0x18003ba3a  and     rax, 0FFFFFFFFFFFFFFF8h
0x18003ba3e  mov     [rdi+7D0h], rax
0x18003ba45  call    cs:__imp_InitializeCriticalSection
0x18003ba4b  mov     [r14], rdi
0x18003ba4e  test    byte ptr cs:xmmword_1800616A0, 10h
0x18003ba55  jz      short loc_18003BA70
0x18003ba57  mov     edx, 0Ch
0x18003ba5c  lea     r8, WPP_c84194e7b785338e3b207dae288fd792_Traceguids
0x18003ba63  mov     ecx, 404h
0x18003ba68  mov     r9d, ebx
0x18003ba6b  call    WPP_SF_D
0x18003ba70  mov     eax, ebx
0x18003ba72  add     rsp, 20h
0x18003ba76  pop     r14
0x18003ba78  pop     rdi
0x18003ba79  pop     rsi
0x18003ba7a  pop     rbp
0x18003ba7b  pop     rbx
0x18003ba7c  retn
```
