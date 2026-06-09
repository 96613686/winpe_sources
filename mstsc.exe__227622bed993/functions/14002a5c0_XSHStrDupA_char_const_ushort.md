# XSHStrDupA(char const *,ushort * *)

- ea: `0x14002a5c0`
- end: `0x14002a71a`
- name: `?XSHStrDupA@@YAJPEBDPEAPEAG@Z`
- size: `346`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14002a720`

## callees

- `0x14000b7d8`
- `0x14000cfb0`
- `0x14002a5c0`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x14002a5fb`
- `KERNEL32!MultiByteToWideChar` at `0x14002a697`
- `KERNEL32!MultiByteToWideChar` at `0x14002a5fb`
- `KERNEL32!MultiByteToWideChar` at `0x14002a697`
- `KERNEL32!GetLastError` at `0x14002a608`
- `KERNEL32!GetLastError` at `0x14002a6a1`
- `KERNEL32!GetLastError` at `0x14002a608`
- `KERNEL32!GetLastError` at `0x14002a6a1`
- `ole32!CoTaskMemAlloc` at `0x14002a66d`
- `ole32!CoTaskMemAlloc` at `0x14002a66d`
- `ole32!CoTaskMemFree` at `0x14002a6f3`
- `ole32!CoTaskMemFree` at `0x14002a6f3`

## pseudocode

```c
__int64 __fastcall XSHStrDupA(LPCCH lpMultiByteStr, unsigned __int16 **a2)
{
  unsigned int v4; // ebp
  int v5; // eax
  int cchWideChar; // r14d
  DWORD v7; // ebx
  unsigned int v8; // eax
  unsigned __int16 *lpWideCharStr; // rax
  unsigned __int16 *v10; // rsi
  DWORD LastError; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax

  v4 = -2147024882;
  if ( lpMultiByteStr )
  {
    v5 = MultiByteToWideChar(0, 0, lpMultiByteStr, -1, 0, 0);
    cchWideChar = v5;
    if ( v5 )
    {
      lpWideCharStr = (unsigned __int16 *)CoTaskMemAlloc(2LL * (unsigned int)(v5 + 1));
      *a2 = lpWideCharStr;
      v10 = lpWideCharStr;
      if ( lpWideCharStr )
      {
        if ( MultiByteToWideChar(0, 0, lpMultiByteStr, -1, lpWideCharStr, cchWideChar) )
        {
          return 0;
        }
        else
        {
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              11,
              WPP_b7ae6d635a30399768ffbc73af776916_Traceguids,
              CurrentThreadActivityIdPrefix,
              LastError);
          }
          CoTaskMemFree(v10);
          *a2 = 0;
        }
      }
    }
    else
    {
      v7 = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v8 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b7ae6d635a30399768ffbc73af776916_Traceguids, v8, v7);
      }
    }
  }
  else
  {
    *a2 = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x14002a5c0  push    rbx
0x14002a5c2  push    rbp
0x14002a5c3  push    rsi
0x14002a5c4  push    rdi
0x14002a5c5  push    r14
0x14002a5c7  sub     rsp, 30h
0x14002a5cb  mov     rbx, rdx
0x14002a5ce  mov     rdi, rcx
0x14002a5d1  mov     ebp, 8007000Eh
0x14002a5d6  test    rcx, rcx
0x14002a5d9  jz      loc_14002A706
0x14002a5df  mov     r8, rcx; lpMultiByteStr
0x14002a5e2  mov     [rsp+58h+cchWideChar], 0; cchWideChar
0x14002a5ea  xor     ecx, ecx; CodePage
0x14002a5ec  mov     [rsp+58h+lpWideCharStr], 0; lpWideCharStr
0x14002a5f5  or      r9d, 0FFFFFFFFh; cbMultiByte
0x14002a5f9  xor     edx, edx; dwFlags
0x14002a5fb  call    cs:__imp_MultiByteToWideChar
0x14002a601  mov     r14d, eax
0x14002a604  test    eax, eax
0x14002a606  jnz     short loc_14002A667
0x14002a608  call    cs:__imp_GetLastError
0x14002a60e  mov     ebx, eax
0x14002a610  mov     rax, cs:WPP_GLOBAL_Control
0x14002a617  lea     rcx, WPP_GLOBAL_Control
0x14002a61e  cmp     rax, rcx
0x14002a621  jz      loc_14002A70D
0x14002a627  test    byte ptr [rax+1Ch], 8
0x14002a62b  jz      loc_14002A70D
0x14002a631  cmp     byte ptr [rax+19h], 2
0x14002a635  jb      loc_14002A70D
0x14002a63b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14002a640  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a647  lea     edx, [r14+0Ah]
0x14002a64b  mov     r9d, eax
0x14002a64e  mov     dword ptr [rsp+58h+lpWideCharStr], ebx
0x14002a652  lea     r8, WPP_b7ae6d635a30399768ffbc73af776916_Traceguids
0x14002a659  mov     rcx, [rcx+10h]
0x14002a65d  call    WPP_SF_Dd
0x14002a662  jmp     loc_14002A70D
0x14002a667  lea     ecx, [rax+1]
0x14002a66a  add     rcx, rcx; cb
0x14002a66d  call    cs:__imp_CoTaskMemAlloc
0x14002a673  mov     [rbx], rax
0x14002a676  mov     rsi, rax
0x14002a679  test    rax, rax
0x14002a67c  jz      loc_14002A70D
0x14002a682  mov     [rsp+58h+cchWideChar], r14d; cchWideChar
0x14002a687  or      r9d, 0FFFFFFFFh; cbMultiByte
0x14002a68b  mov     r8, rdi; lpMultiByteStr
0x14002a68e  mov     [rsp+58h+lpWideCharStr], rax; lpWideCharStr
0x14002a693  xor     edx, edx; dwFlags
0x14002a695  xor     ecx, ecx; CodePage
0x14002a697  call    cs:__imp_MultiByteToWideChar
0x14002a69d  test    eax, eax
0x14002a69f  jnz     short loc_14002A702
0x14002a6a1  call    cs:__imp_GetLastError
0x14002a6a7  mov     edi, eax
0x14002a6a9  mov     rax, cs:WPP_GLOBAL_Control
0x14002a6b0  lea     rcx, WPP_GLOBAL_Control
0x14002a6b7  cmp     rax, rcx
0x14002a6ba  jz      short loc_14002A6F0
0x14002a6bc  test    byte ptr [rax+1Ch], 8
0x14002a6c0  jz      short loc_14002A6F0
0x14002a6c2  cmp     byte ptr [rax+19h], 2
0x14002a6c6  jb      short loc_14002A6F0
0x14002a6c8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14002a6cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a6d4  lea     r8, WPP_b7ae6d635a30399768ffbc73af776916_Traceguids
0x14002a6db  mov     edx, 0Bh
0x14002a6e0  mov     dword ptr [rsp+58h+lpWideCharStr], edi
0x14002a6e4  mov     r9d, eax
0x14002a6e7  mov     rcx, [rcx+10h]
0x14002a6eb  call    WPP_SF_Dd
0x14002a6f0  mov     rcx, rsi; pv
0x14002a6f3  call    cs:__imp_CoTaskMemFree
0x14002a6f9  mov     qword ptr [rbx], 0
0x14002a700  jmp     short loc_14002A70D
0x14002a702  xor     ebp, ebp
0x14002a704  jmp     short loc_14002A70D
0x14002a706  mov     qword ptr [rdx], 0
0x14002a70d  mov     eax, ebp
0x14002a70f  add     rsp, 30h
0x14002a713  pop     r14
0x14002a715  pop     rdi
0x14002a716  pop     rsi
0x14002a717  pop     rbp
0x14002a718  pop     rbx
0x14002a719  retn
```
