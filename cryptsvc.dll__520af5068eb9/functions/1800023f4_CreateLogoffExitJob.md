# CreateLogoffExitJob

- ea: `0x1800023f4`
- end: `0x180002471`
- name: `CreateLogoffExitJob`
- size: `125`
- prototype: `_QWORD *__fastcall(int, int, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004364`

## callees

- `0x1800023f4`
- `0x1800033a0`
- `0x18000b8c0`

## import_xrefs

- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180002445`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180002445`

## pseudocode

```c
_QWORD *__fastcall CreateLogoffExitJob(int a1, int a2, _QWORD *a3)
{
  __int64 v6; // rax
  _QWORD *v7; // rbx
  __int64 v8; // rax

  v6 = PkiZeroAlloc(0x50u);
  v7 = (_QWORD *)v6;
  if ( v6 )
  {
    if ( a1 )
    {
      *(_DWORD *)(v6 + 40) = a1;
    }
    else
    {
      *(_DWORD *)(v6 + 44) = a2;
      *(_QWORD *)(v6 + 48) = *a3;
      *a3 = 0;
      v8 = RegisterWaitForSingleObjectEx(*(_QWORD *)(v6 + 48), UrlCacheSvcProcessExitCallback, v6, 0xFFFFFFFFLL, 8);
      v7[7] = v8;
      if ( !v8 )
      {
        FreeLogoffExitJob(v7);
        return 0;
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1800023f4  push    rbx
0x1800023f6  push    rbp
0x1800023f7  push    rsi
0x1800023f8  push    rdi
0x1800023f9  sub     rsp, 38h
0x1800023fd  mov     edi, ecx
0x1800023ff  mov     rsi, r8
0x180002402  mov     ecx, 50h ; 'P'; uBytes
0x180002407  mov     ebp, edx
0x180002409  call    PkiZeroAlloc
0x18000240e  mov     rbx, rax
0x180002411  test    rax, rax
0x180002414  jz      short loc_180002454
0x180002416  test    edi, edi
0x180002418  jnz     short loc_180002460
0x18000241a  mov     [rax+2Ch], ebp
0x18000241d  lea     rdx, ?UrlCacheSvcProcessExitCallback@@YAXPEAXE@Z; UrlCacheSvcProcessExitCallback(void *,uchar)
0x180002424  mov     rax, [rsi]
0x180002427  or      r9d, 0FFFFFFFFh
0x18000242b  mov     [rbx+30h], rax
0x18000242f  mov     r8, rbx
0x180002432  mov     qword ptr [rsi], 0
0x180002439  mov     rcx, [rbx+30h]
0x18000243d  mov     [rsp+58h+var_38], 8
0x180002445  call    cs:__imp_RegisterWaitForSingleObjectEx
0x18000244b  mov     [rbx+38h], rax
0x18000244f  test    rax, rax
0x180002452  jz      short loc_180002465
0x180002454  mov     rax, rbx
0x180002457  add     rsp, 38h
0x18000245b  pop     rdi
0x18000245c  pop     rsi
0x18000245d  pop     rbp
0x18000245e  pop     rbx
0x18000245f  retn
0x180002460  mov     [rax+28h], edi
0x180002463  jmp     short loc_180002454
0x180002465  mov     rcx, rbx; hMem
0x180002468  call    FreeLogoffExitJob
0x18000246d  xor     ebx, ebx
0x18000246f  jmp     short loc_180002454
```
