# __DestructExceptionObject

- ea: `0x180002890`
- end: `0x1800028fc`
- name: `__DestructExceptionObject`
- size: `108`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800029f4`
- `0x1800033d8`
- `0x1800042e0`

## callees

- `0x180002890`
- `0x180002904`
- `0x180002e18`
- `0x18000516a`
- `0x18000d010`

## pseudocode

```c
void __fastcall _DestructExceptionObject(__int64 a1)
{
  __int64 v1; // rax
  __int64 v2; // rdx
  __int64 v3; // rcx

  if ( a1 )
  {
    if ( *(_DWORD *)a1 == -529697949
      && *(_DWORD *)(a1 + 24) == 4
      && (unsigned int)(*(_DWORD *)(a1 + 32) - 429065504) <= 2 )
    {
      v1 = *(_QWORD *)(a1 + 48);
      if ( v1 )
      {
        v2 = *(int *)(v1 + 4);
        if ( (_DWORD)v2 )
        {
          ((void (__fastcall *)(_QWORD))(*(_QWORD *)(a1 + 56) + v2))(*(_QWORD *)(a1 + 40));
        }
        else if ( (*(_BYTE *)v1 & 0x10) != 0 )
        {
          v3 = **(_QWORD **)(a1 + 40);
          if ( v3 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180002890  test    rcx, rcx
0x180002893  jz      short locret_1800028FB
0x180002895  mov     [rsp+arg_8], dl
0x180002899  sub     rsp, 48h
0x18000289d  cmp     dword ptr [rcx], 0E06D7363h
0x1800028a3  jnz     short loc_1800028F7
0x1800028a5  cmp     dword ptr [rcx+18h], 4
0x1800028a9  jnz     short loc_1800028F7
0x1800028ab  mov     eax, [rcx+20h]
0x1800028ae  sub     eax, 19930520h
0x1800028b3  cmp     eax, 2
0x1800028b6  ja      short loc_1800028F7
0x1800028b8  mov     rax, [rcx+30h]
0x1800028bc  test    rax, rax
0x1800028bf  jz      short loc_1800028F7
0x1800028c1  movsxd  rdx, dword ptr [rax+4]
0x1800028c5  test    edx, edx
0x1800028c7  jz      short loc_1800028DA
0x1800028c9  add     rdx, [rcx+38h]; void *
0x1800028cd  mov     rcx, [rcx+28h]; void *
0x1800028d1  call    ?_CallMemberFunction0@@YAXQEAX0@Z; _CallMemberFunction0(void * const,void * const)
0x1800028d6  jmp     short loc_1800028F7
0x1800028d8  jmp     short loc_1800028F7
0x1800028da  test    byte ptr [rax], 10h
0x1800028dd  jz      short loc_1800028F7
0x1800028df  mov     rax, [rcx+28h]
0x1800028e3  mov     rcx, [rax]
0x1800028e6  test    rcx, rcx
0x1800028e9  jz      short loc_1800028F7
0x1800028eb  mov     rax, [rcx]
0x1800028ee  mov     rax, [rax+10h]
0x1800028f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028f7  add     rsp, 48h
0x1800028fb  retn
0x18000bda5  push    rbx
0x18000bda7  push    rbp
0x18000bda8  sub     rsp, 28h
0x18000bdac  mov     rbp, rdx
0x18000bdaf  mov     [rbp+30h], rcx
0x18000bdb3  cmp     byte ptr [rbp+58h], 0
0x18000bdb7  jz      short loc_18000BE25
0x18000bdb9  mov     rax, [rbp+30h]
0x18000bdbd  mov     rcx, [rax]
0x18000bdc0  mov     [rbp+28h], rcx
0x18000bdc4  mov     rax, [rbp+28h]
0x18000bdc8  cmp     dword ptr [rax], 0E06D7363h
0x18000bdce  jnz     short loc_18000BE25
0x18000bdd0  mov     rax, [rbp+28h]
0x18000bdd4  cmp     dword ptr [rax+18h], 4
0x18000bdd8  jnz     short loc_18000BE25
0x18000bdda  mov     rax, [rbp+28h]
0x18000bdde  cmp     dword ptr [rax+20h], 19930520h
0x18000bde5  jz      short loc_18000BE01
0x18000bde7  mov     rax, [rbp+28h]
0x18000bdeb  cmp     dword ptr [rax+20h], 19930521h
0x18000bdf2  jz      short loc_18000BE01
0x18000bdf4  mov     rax, [rbp+28h]
0x18000bdf8  cmp     dword ptr [rax+20h], 19930522h
0x18000bdff  jnz     short loc_18000BE25
0x18000be01  call    __vcrt_getptd
0x18000be06  mov     rcx, [rbp+28h]
0x18000be0a  mov     [rax+20h], rcx
0x18000be0e  mov     rax, [rbp+30h]
0x18000be12  mov     rbx, [rax+8]
0x18000be16  call    __vcrt_getptd
0x18000be1b  mov     [rax+28h], rbx
0x18000be1f  call    terminate_0
0x18000be25  mov     dword ptr [rbp+20h], 0
0x18000be2c  mov     eax, [rbp+20h]
0x18000be2f  add     rsp, 28h
0x18000be33  pop     rbp
0x18000be34  pop     rbx
0x18000be35  retn
```
