# CEnergyTaskHandler::TracesCleanup(ushort const *,ulong)

- ea: `0x180002c8c`
- end: `0x180002d8e`
- name: `?TracesCleanup@CEnergyTaskHandler@@AEAAJPEBGK@Z`
- size: `258`
- prototype: `__int64 __fastcall(CEnergyTaskHandler *this, WCHAR *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, loader_planting, service_task`

## callers

- `0x1800029bc`

## callees

- `0x18000200c`
- `0x180002c8c`
- `0x180003a92`
- `0x180003ac0`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180002d3a`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180002d3a`

## pseudocode

```c
__int64 __fastcall CEnergyTaskHandler::TracesCleanup(CEnergyTaskHandler *this, WCHAR *a2, unsigned int a3)
{
  WCHAR *v4; // r10
  __int64 v5; // rax
  __int64 v6; // r9
  WCHAR *v7; // rcx
  HRESULT v8; // edx
  unsigned int i; // ebx
  CEnergyTaskHandler *v10; // rcx
  WCHAR pszPath[264]; // [rsp+20h] [rbp-238h] BYREF

  v4 = pszPath;
  v5 = 2147483646;
  v6 = 260;
  do
  {
    if ( !v5 )
      break;
    if ( !*a2 )
      break;
    *v4++ = *a2++;
    --v5;
    --v6;
  }
  while ( v6 );
  v7 = v4 - 1;
  v8 = v6 == 0 ? 0x8007007A : 0;
  if ( v6 )
    v7 = v4;
  *v7 = 0;
  if ( v6 )
  {
    for ( i = 0; i < 5; ++i )
    {
      if ( !wcscmp_0(off_180008000[i], L"ScreenOnPowerStudyTraceSession-*.etl") )
      {
        v8 = PathCchAppend(pszPath, 0x104u, L"ScreenOn");
        if ( v8 < 0 )
          break;
      }
      v8 = CEnergyTaskHandler::PurgeOldFiles(v10, pszPath, a3, off_180008000[i]);
      if ( v8 < 0 )
        break;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180002c8c  mov     [rsp+arg_0], rbx
0x180002c91  mov     [rsp+arg_8], rbp
0x180002c96  push    rsi
0x180002c97  push    rdi
0x180002c98  push    r14
0x180002c9a  sub     rsp, 240h
0x180002ca1  mov     rax, cs:__security_cookie
0x180002ca8  xor     rax, rsp
0x180002cab  mov     [rsp+258h+var_28], rax
0x180002cb3  mov     esi, r8d
0x180002cb6  lea     r10, [rsp+258h+pszPath]
0x180002cbb  mov     eax, 7FFFFFFEh
0x180002cc0  mov     r9d, 104h
0x180002cc6  xor     ebp, ebp
0x180002cc8  test    rax, rax
0x180002ccb  jz      short loc_180002CEA
0x180002ccd  movzx   ecx, word ptr [rdx]
0x180002cd0  test    cx, cx
0x180002cd3  jz      short loc_180002CEA
0x180002cd5  mov     [r10], cx
0x180002cd9  add     rdx, 2
0x180002cdd  add     r10, 2
0x180002ce1  dec     rax
0x180002ce4  sub     r9, 1
0x180002ce8  jnz     short loc_180002CC8
0x180002cea  mov     rax, r9
0x180002ced  lea     rcx, [r10-2]
0x180002cf1  neg     rax
0x180002cf4  sbb     edx, edx
0x180002cf6  not     edx
0x180002cf8  and     edx, 8007007Ah
0x180002cfe  test    r9, r9
0x180002d01  cmovnz  rcx, r10
0x180002d05  mov     [rcx], bp
0x180002d08  jz      short loc_180002D64
0x180002d0a  mov     ebx, ebp
0x180002d0c  mov     edi, ebx
0x180002d0e  lea     r14, off_180008000; "sleepstudy-trace-*.etl"
0x180002d15  lea     rdx, aScreenonpowers; "ScreenOnPowerStudyTraceSession-*.etl"
0x180002d1c  mov     rcx, [r14+rdi*8]; String1
0x180002d20  call    wcscmp_0
0x180002d25  test    eax, eax
0x180002d27  jnz     short loc_180002D46
0x180002d29  lea     r8, aScreenon; "ScreenOn"
0x180002d30  mov     edx, 104h; cchPath
0x180002d35  lea     rcx, [rsp+258h+pszPath]; pszPath
0x180002d3a  call    cs:__imp_PathCchAppend
0x180002d40  mov     edx, eax
0x180002d42  test    eax, eax
0x180002d44  js      short loc_180002D64
0x180002d46  mov     r9, [r14+rdi*8]; unsigned __int16 *
0x180002d4a  lea     rdx, [rsp+258h+pszPath]; unsigned __int16 *
0x180002d4f  mov     r8d, esi; unsigned int
0x180002d52  call    ?PurgeOldFiles@CEnergyTaskHandler@@AEAAJPEBGK0@Z; CEnergyTaskHandler::PurgeOldFiles(ushort const *,ulong,ushort const *)
0x180002d57  mov     edx, eax
0x180002d59  test    eax, eax
0x180002d5b  js      short loc_180002D64
0x180002d5d  inc     ebx
0x180002d5f  cmp     ebx, 5
0x180002d62  jb      short loc_180002D0C
0x180002d64  mov     eax, edx
0x180002d66  mov     rcx, [rsp+258h+var_28]
0x180002d6e  xor     rcx, rsp; StackCookie
0x180002d71  call    __security_check_cookie
0x180002d76  lea     r11, [rsp+258h+var_18]
0x180002d7e  mov     rbx, [r11+20h]
0x180002d82  mov     rbp, [r11+28h]
0x180002d86  mov     rsp, r11
0x180002d89  pop     r14
0x180002d8b  pop     rdi
0x180002d8c  pop     rsi
0x180002d8d  retn
```
