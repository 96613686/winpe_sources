# basessp::BaseSSP::WSTDereferenceCredential(basessp::_WST_CREDENTIAL *)

- ea: `0x180004230`
- end: `0x1800043d2`
- name: `?WSTDereferenceCredential@BaseSSP@basessp@@QEAAXPEAU_WST_CREDENTIAL@2@@Z`
- size: `418`
- prototype: `void __fastcall(basessp::BaseSSP *__hidden this, struct basessp::_WST_CREDENTIAL *)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800032c0`
- `0x180003500`
- `0x180003a10`
- `0x18000a29c`
- `0x18001de38`

## callees

- `0x180004230`
- `0x180020010`

## import_xrefs

- `msvcrt!tolower` at `0x1800042b8`
- `msvcrt!tolower` at `0x1800042c4`
- `msvcrt!tolower` at `0x1800042d1`
- `msvcrt!tolower` at `0x1800042de`
- `msvcrt!tolower` at `0x1800042eb`
- `msvcrt!tolower` at `0x1800042f8`
- `msvcrt!tolower` at `0x180004305`
- `msvcrt!tolower` at `0x180004312`
- `msvcrt!tolower` at `0x1800042b8`
- `msvcrt!tolower` at `0x1800042c4`
- `msvcrt!tolower` at `0x1800042d1`
- `msvcrt!tolower` at `0x1800042de`
- `msvcrt!tolower` at `0x1800042eb`
- `msvcrt!tolower` at `0x1800042f8`
- `msvcrt!tolower` at `0x180004305`
- `msvcrt!tolower` at `0x180004312`
- `ntdll!NtClose` at `0x180004289`
- `ntdll!NtClose` at `0x180004289`

## pseudocode

```c
void __fastcall basessp::BaseSSP::WSTDereferenceCredential(basessp::BaseSSP *this, struct basessp::_WST_CREDENTIAL *a2)
{
  void *v4; // rcx
  __int64 v5; // rdx
  char *v6; // rax
  __int64 v7; // rcx
  unsigned int v8; // r8d
  unsigned int v9; // r9d
  __int64 v10; // r9
  char *v11; // rax

  if ( a2
    && *(_QWORD *)a2 == 0x444552434F545357LL
    && _InterlockedExchangeAdd((volatile signed __int32 *)a2 + 2, 0xFFFFFFFF) <= 1
    && !*((_DWORD *)a2 + 3) )
  {
    v4 = (void *)*((_QWORD *)a2 + 6);
    if ( v4 )
    {
      NtClose(v4);
      LOWORD(v4) = 0;
      *((_QWORD *)a2 + 6) = 0;
    }
    v5 = *((unsigned int *)a2 + 23);
    if ( (_DWORD)v5 )
    {
      v8 = *((unsigned __int16 *)a2 + 48);
      if ( (_WORD)v8 )
      {
        if ( (unsigned int)v5 >= *((unsigned __int16 *)a2 + 12) )
        {
          v9 = *((_DWORD *)a2 + 7);
          if ( (unsigned int)v5 <= v9 && (unsigned __int16)v8 <= 0xFFFAu && v8 <= v9 - (unsigned int)v5 )
          {
            v10 = *((unsigned __int16 *)a2 + 48);
            v11 = (char *)a2 + v5;
            do
            {
              *v11++ = 0;
              --v10;
            }
            while ( v10 );
          }
        }
      }
    }
    *((_WORD *)a2 + 48) = (_WORD)v4;
    v6 = (char *)a2 + 104;
    v7 = *((unsigned __int16 *)a2 + 53);
    if ( *((_WORD *)a2 + 53) )
    {
      do
      {
        *v6++ = 0;
        --v7;
      }
      while ( v7 );
    }
    *(_BYTE *)a2 = tolower(*(unsigned __int8 *)a2);
    *((_BYTE *)a2 + 1) = tolower(*((unsigned __int8 *)a2 + 1));
    *((_BYTE *)a2 + 2) = tolower(*((unsigned __int8 *)a2 + 2));
    *((_BYTE *)a2 + 3) = tolower(*((unsigned __int8 *)a2 + 3));
    *((_BYTE *)a2 + 4) = tolower(*((unsigned __int8 *)a2 + 4));
    *((_BYTE *)a2 + 5) = tolower(*((unsigned __int8 *)a2 + 5));
    *((_BYTE *)a2 + 6) = tolower(*((unsigned __int8 *)a2 + 6));
    *((_BYTE *)a2 + 7) = tolower(*((unsigned __int8 *)a2 + 7));
    if ( *((_DWORD *)this + 52) == 1 )
      (*(void (__fastcall **)(struct basessp::_WST_CREDENTIAL *))(*((_QWORD *)this + 30) + 392LL))(a2);
    else
      (*(void (__fastcall **)(struct basessp::_WST_CREDENTIAL *))(*((_QWORD *)this + 31) + 8LL))(a2);
  }
}

```

## disassembly

```asm
0x180004230  test    rdx, rdx
0x180004233  jz      locret_180004344
0x180004239  mov     [rsp+arg_0], rbx
0x18000423e  push    rdi
0x18000423f  sub     rsp, 20h
0x180004243  mov     rbx, rdx
0x180004246  mov     rdi, rcx
0x180004249  mov     rax, 444552434F545357h
0x180004253  cmp     [rdx], rax
0x180004256  jnz     loc_18000433A
0x18000425c  jmp     short loc_180004263
0x18000425e  jmp     loc_18000433A
0x180004263  mov     eax, 0FFFFFFFFh
0x180004268  lock xadd [rdx+8], eax
0x18000426d  sub     eax, 1
0x180004270  jg      loc_18000433A
0x180004276  cmp     dword ptr [rdx+0Ch], 0
0x18000427a  jnz     loc_18000433A
0x180004280  mov     rcx, [rdx+30h]; Handle
0x180004284  test    rcx, rcx
0x180004287  jz      short loc_180004295
0x180004289  call    cs:__imp_NtClose
0x18000428f  xor     ecx, ecx
0x180004291  mov     [rbx+30h], rcx
0x180004295  mov     edx, [rbx+5Ch]
0x180004298  test    edx, edx
0x18000429a  jnz     loc_180004364
0x1800042a0  mov     [rbx+60h], cx
0x1800042a4  lea     rax, [rbx+68h]
0x1800042a8  movzx   ecx, word ptr [rax+2]
0x1800042ac  test    rcx, rcx
0x1800042af  jnz     loc_1800043C0
0x1800042b5  movzx   ecx, byte ptr [rbx]; C
0x1800042b8  call    cs:__imp_tolower
0x1800042be  mov     [rbx], al
0x1800042c0  movzx   ecx, byte ptr [rbx+1]; C
0x1800042c4  call    cs:__imp_tolower
0x1800042ca  mov     [rbx+1], al
0x1800042cd  movzx   ecx, byte ptr [rbx+2]; C
0x1800042d1  call    cs:__imp_tolower
0x1800042d7  mov     [rbx+2], al
0x1800042da  movzx   ecx, byte ptr [rbx+3]; C
0x1800042de  call    cs:__imp_tolower
0x1800042e4  mov     [rbx+3], al
0x1800042e7  movzx   ecx, byte ptr [rbx+4]; C
0x1800042eb  call    cs:__imp_tolower
0x1800042f1  mov     [rbx+4], al
0x1800042f4  movzx   ecx, byte ptr [rbx+5]; C
0x1800042f8  call    cs:__imp_tolower
0x1800042fe  mov     [rbx+5], al
0x180004301  movzx   ecx, byte ptr [rbx+6]; C
0x180004305  call    cs:__imp_tolower
0x18000430b  mov     [rbx+6], al
0x18000430e  movzx   ecx, byte ptr [rbx+7]; C
0x180004312  call    cs:__imp_tolower
0x180004318  mov     [rbx+7], al
0x18000431b  mov     rcx, rbx
0x18000431e  cmp     dword ptr [rdi+0D0h], 1
0x180004325  jnz     short loc_18000434A
0x180004327  mov     rax, [rdi+0F0h]
0x18000432e  mov     rax, [rax+188h]
0x180004335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000433a  mov     rbx, [rsp+28h+arg_0]
0x18000433f  add     rsp, 20h
0x180004343  pop     rdi
0x180004344  retn
0x180004345  jmp     loc_180004295
0x18000434a  mov     rax, [rdi+0F8h]
0x180004351  mov     rax, [rax+8]
0x180004355  mov     rbx, [rsp+28h+arg_0]
0x18000435a  add     rsp, 20h
0x18000435e  pop     rdi
0x18000435f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180004364  movzx   r8d, word ptr [rbx+60h]
0x180004369  test    r8w, r8w
0x18000436d  jz      loc_1800042A0
0x180004373  movzx   eax, word ptr [rbx+18h]
0x180004377  cmp     edx, eax
0x180004379  jb      loc_1800042A0
0x18000437f  mov     r9d, [rbx+1Ch]
0x180004383  cmp     edx, r9d
0x180004386  ja      loc_1800042A0
0x18000438c  mov     eax, 0FFFAh
0x180004391  cmp     r8w, ax
0x180004395  ja      loc_1800042A0
0x18000439b  sub     r9d, edx
0x18000439e  cmp     r8d, r9d
0x1800043a1  ja      loc_1800042A0
0x1800043a7  mov     r9d, r8d
0x1800043aa  lea     rax, [rbx+rdx]
0x1800043ae  mov     byte ptr [rax], 0
0x1800043b1  lea     rax, [rax+1]
0x1800043b5  sub     r9, 1
0x1800043b9  jnz     short loc_1800043AE
0x1800043bb  jmp     loc_1800042A0
0x1800043c0  mov     byte ptr [rax], 0
0x1800043c3  lea     rax, [rax+1]
0x1800043c7  sub     rcx, 1
0x1800043cb  jnz     short loc_1800043C0
0x1800043cd  jmp     loc_1800042B5
```
