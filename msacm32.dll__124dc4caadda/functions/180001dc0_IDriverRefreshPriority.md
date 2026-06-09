# IDriverRefreshPriority

- ea: `0x180001dc0`
- end: `0x180001e4b`
- name: `IDriverRefreshPriority`
- size: `139`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001ad0`
- `0x1800089c0`
- `0x180008c00`
- `0x180008d00`

## callees

- `0x180001dc0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001e31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001e31`

## pseudocode

```c
void __fastcall IDriverRefreshPriority(__int64 a1)
{
  int v2; // esi
  __int64 i; // rbx
  __int64 CurrentThreadId; // rax
  int v5; // ecx

  v2 = 1;
  for ( i = 0; !i; *(_DWORD *)(i + 16) = v2++ )
  {
    i = *(_QWORD *)(a1 + 96);
    CurrentThreadId = GetCurrentThreadId();
    while ( 1 )
    {
LABEL_5:
      while ( !i )
      {
        if ( !CurrentThreadId )
          return;
        i = *(_QWORD *)(a1 + 96);
        CurrentThreadId = 0;
      }
      if ( *(_QWORD *)(i + 36) == CurrentThreadId )
      {
        v5 = *(_DWORD *)(i + 56);
        if ( (v5 & 0x10000000) == 0 && (v5 & 0x40000000) == 0 && !*(_DWORD *)(i + 12) )
          break;
      }
      i = *(_QWORD *)(i + 20);
    }
  }
  if ( a1 == *(_QWORD *)(i + 4) )
  {
    CurrentThreadId = *(_QWORD *)(i + 36);
    i = *(_QWORD *)(i + 20);
    goto LABEL_5;
  }
}

```

## disassembly

```asm
0x180001dc0  mov     [rsp+arg_0], rbx
0x180001dc5  mov     [rsp+arg_8], rsi
0x180001dca  push    rdi
0x180001dcb  sub     rsp, 20h
0x180001dcf  mov     rdi, rcx
0x180001dd2  mov     esi, 1
0x180001dd7  xor     ebx, ebx
0x180001dd9  nop     dword ptr [rax+00000000h]
0x180001de0  test    rbx, rbx
0x180001de3  jz      short loc_180001E2D
0x180001de5  cmp     rdi, [rbx+4]
0x180001de9  jnz     short loc_180001E3B
0x180001deb  mov     rax, [rbx+24h]
0x180001def  mov     rbx, [rbx+14h]
0x180001df3  test    rbx, rbx
0x180001df6  jz      short loc_180001E20
0x180001df8  cmp     [rbx+24h], rax
0x180001dfc  jz      short loc_180001E04
0x180001dfe  mov     rbx, [rbx+14h]
0x180001e02  jmp     short loc_180001DF3
0x180001e04  mov     ecx, [rbx+38h]
0x180001e07  bt      ecx, 1Ch
0x180001e0b  jb      short loc_180001DFE
0x180001e0d  bt      ecx, 1Eh
0x180001e11  jb      short loc_180001DFE
0x180001e13  cmp     dword ptr [rbx+0Ch], 0
0x180001e17  jnz     short loc_180001DFE
0x180001e19  mov     [rbx+10h], esi
0x180001e1c  inc     esi
0x180001e1e  jmp     short loc_180001DE0
0x180001e20  test    rax, rax
0x180001e23  jz      short loc_180001E3B
0x180001e25  mov     rbx, [rdi+60h]
0x180001e29  xor     eax, eax
0x180001e2b  jmp     short loc_180001DF3
0x180001e2d  mov     rbx, [rdi+60h]
0x180001e31  call    cs:__imp_GetCurrentThreadId
0x180001e37  mov     eax, eax
0x180001e39  jmp     short loc_180001DF3
0x180001e3b  mov     rbx, [rsp+28h+arg_0]
0x180001e40  mov     rsi, [rsp+28h+arg_8]
0x180001e45  add     rsp, 20h
0x180001e49  pop     rdi
0x180001e4a  retn
```
