# ceDispatchSetErrorInfo(long,ushort const *,ushort const *,_GUID const *)

- ea: `0x180005f70`
- end: `0x180006093`
- name: `?ceDispatchSetErrorInfo@@YAJJPEBG0PEBU_GUID@@@Z`
- size: `291`
- prototype: `int(int, const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *)`
- caller_count: `6`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180002270`
- `0x180002a90`
- `0x180003710`
- `0x180004100`
- `0x180005380`
- `0x1800078f0`

## callees

- `0x1800053bc`
- `0x18000550c`
- `0x180005f70`
- `0x18000609c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005fd4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005fd4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000606c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000607a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000606c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000607a`

## pseudocode

```c
__int64 __fastcall ceDispatchSetErrorInfo(
        DWORD a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *const *a3,
        const struct _GUID *a4)
{
  const unsigned __int16 *v6; // rsi
  unsigned __int16 *v8; // rbx
  const unsigned __int16 *v9; // rdx
  __int64 v10; // rcx
  unsigned __int16 *ErrorMessageText; // rdi
  __int64 v12; // rcx
  __int64 v13; // rax
  unsigned __int64 v14; // r14
  unsigned __int16 *v15; // rax
  __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  unsigned __int16 *v18; // rcx
  IErrorInfo *v20; // [rsp+28h] [rbp-60h]

  v6 = a2;
  if ( a2 )
  {
    v8 = 0;
    ErrorMessageText = (unsigned __int16 *)ceGetErrorMessageTextEx(
                                             a1,
                                             (__int64)a2,
                                             a3,
                                             (const unsigned __int16 *const *)a4);
    if ( ErrorMessageText )
    {
      v12 = -1;
      v13 = -1;
      do
        ++v13;
      while ( v6[v13] );
      do
        ++v12;
      while ( ErrorMessageText[v12] );
      v14 = v12 + v13 + 2;
      v15 = (unsigned __int16 *)LocalAlloc(0, 2 * v14);
      v8 = v15;
      if ( v15 )
      {
        if ( v14 )
        {
          if ( v14 <= 0x7FFFFFFF )
          {
            v16 = 2147483646;
            v17 = v14;
            do
            {
              if ( !v16 )
                break;
              if ( !*v6 )
                break;
              *v15++ = *v6++;
              --v16;
              --v17;
            }
            while ( v17 );
            v18 = v15 - 1;
            if ( v17 )
              v18 = v15;
            *v18 = 0;
          }
          else
          {
            *v15 = 0;
          }
        }
        StringCchCatW(v8, v14, L" ");
        StringCchCatW(v8, v14, ErrorMessageText);
        v6 = v8;
      }
    }
    ceDispatchSetErrorInfoSub(v10, v9, v6, (const unsigned __int16 *)a3, a4, v20);
    if ( v8 )
      LocalFree(v8);
    if ( ErrorMessageText )
      LocalFree(ErrorMessageText);
  }
  return a1;
}

```

## disassembly

```asm
0x180005f70  push    rbx
0x180005f72  push    rbp
0x180005f73  push    rsi
0x180005f74  push    rdi
0x180005f75  push    r12
0x180005f77  push    r13
0x180005f79  push    r14
0x180005f7b  push    r15
0x180005f7d  sub     rsp, 48h
0x180005f81  xor     r13d, r13d
0x180005f84  mov     r15, r9
0x180005f87  mov     r12, r8
0x180005f8a  mov     rsi, rdx
0x180005f8d  mov     ebp, ecx
0x180005f8f  test    rdx, rdx
0x180005f92  jz      loc_180006080
0x180005f98  mov     ebx, r13d
0x180005f9b  call    ?ceGetErrorMessageTextEx@@YAPEBGJHPEBQEBG@Z; ceGetErrorMessageTextEx(long,int,ushort const * const *)
0x180005fa0  mov     rdi, rax
0x180005fa3  test    rax, rax
0x180005fa6  jz      loc_180006054
0x180005fac  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180005fb0  mov     rax, rcx
0x180005fb3  inc     rax
0x180005fb6  cmp     [rsi+rax*2], r13w
0x180005fbb  jnz     short loc_180005FB3
0x180005fbd  inc     rcx
0x180005fc0  cmp     [rdi+rcx*2], r13w
0x180005fc5  jnz     short loc_180005FBD
0x180005fc7  lea     r14, [rax+2]
0x180005fcb  add     r14, rcx
0x180005fce  xor     ecx, ecx; uFlags
0x180005fd0  lea     rdx, [r14+r14]; uBytes
0x180005fd4  call    cs:__imp_LocalAlloc
0x180005fda  mov     rbx, rax
0x180005fdd  test    rax, rax
0x180005fe0  jz      short loc_180006054
0x180005fe2  test    r14, r14
0x180005fe5  jz      short loc_180006031
0x180005fe7  cmp     r14, 7FFFFFFFh
0x180005fee  jbe     short loc_180005FF6
0x180005ff0  mov     [rax], r13w
0x180005ff4  jmp     short loc_180006031
0x180005ff6  mov     ecx, 7FFFFFFEh
0x180005ffb  mov     rdx, r14
0x180005ffe  test    rcx, rcx
0x180006001  jz      short loc_180006022
0x180006003  movzx   r8d, word ptr [rsi]
0x180006007  test    r8w, r8w
0x18000600b  jz      short loc_180006022
0x18000600d  mov     [rax], r8w
0x180006011  add     rsi, 2
0x180006015  add     rax, 2
0x180006019  dec     rcx
0x18000601c  sub     rdx, 1
0x180006020  jnz     short loc_180005FFE
0x180006022  test    rdx, rdx
0x180006025  lea     rcx, [rax-2]
0x180006029  cmovnz  rcx, rax
0x18000602d  mov     [rcx], r13w
0x180006031  lea     r8, asc_18000C3F4; " "
0x180006038  mov     rdx, r14; unsigned __int64
0x18000603b  mov     rcx, rbx; unsigned __int16 *
0x18000603e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006043  mov     r8, rdi; unsigned __int16 *
0x180006046  mov     rdx, r14; unsigned __int64
0x180006049  mov     rcx, rbx; unsigned __int16 *
0x18000604c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006051  mov     rsi, rbx
0x180006054  mov     r9, r12; unsigned __int16 *
0x180006057  mov     [rsp+88h+var_68], r15; struct _GUID *
0x18000605c  mov     r8, rsi; unsigned __int16 *
0x18000605f  call    ?ceDispatchSetErrorInfoSub@@YAJJPEBG00PEBU_GUID@@0K@Z; ceDispatchSetErrorInfoSub(long,ushort const *,ushort const *,ushort const *,_GUID const *,ushort const *,ulong)
0x180006064  test    rbx, rbx
0x180006067  jz      short loc_180006072
0x180006069  mov     rcx, rbx; hMem
0x18000606c  call    cs:__imp_LocalFree
0x180006072  test    rdi, rdi
0x180006075  jz      short loc_180006080
0x180006077  mov     rcx, rdi; hMem
0x18000607a  call    cs:__imp_LocalFree
0x180006080  mov     eax, ebp
0x180006082  add     rsp, 48h
0x180006086  pop     r15
0x180006088  pop     r14
0x18000608a  pop     r13
0x18000608c  pop     r12
0x18000608e  pop     rdi
0x18000608f  pop     rsi
0x180006090  pop     rbp
0x180006091  pop     rbx
0x180006092  retn
```
