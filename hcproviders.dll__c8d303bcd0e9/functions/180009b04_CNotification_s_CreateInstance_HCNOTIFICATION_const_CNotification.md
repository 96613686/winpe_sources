# CNotification::s_CreateInstance(HCNOTIFICATION const *,CNotification * *)

- ea: `0x180009b04`
- end: `0x180009be3`
- name: `?s_CreateInstance@CNotification@@SAJPEBUHCNOTIFICATION@@PEAPEAV1@@Z`
- size: `223`
- prototype: `__int64 __fastcall(const struct HCNOTIFICATION *, struct CNotification **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800019f0`

## callees

- `0x180004fc8`
- `0x180009a10`
- `0x180009b04`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall CNotification::s_CreateInstance(const struct HCNOTIFICATION *a1, struct CNotification **a2)
{
  struct CNotification *v4; // rax
  struct CNotification *v5; // rbx
  int v6; // edi

  v4 = (struct CNotification *)operator new(0xD0u);
  v5 = v4;
  if ( v4 )
  {
    *((_DWORD *)v4 + 2) = 1;
    *(_QWORD *)v4 = &CNotification::`vftable';
    *((_WORD *)v4 + 6) = 0;
    *((_QWORD *)v4 + 18) = 0;
    *((_QWORD *)v4 + 19) = 0;
    *((_QWORD *)v4 + 20) = 0;
    *((_QWORD *)v4 + 21) = 0;
    *((_QWORD *)v4 + 22) = 0;
    *((_QWORD *)v4 + 23) = 0;
    *((_QWORD *)v4 + 24) = 0;
    *((_DWORD *)v4 + 50) = 10;
    _InterlockedIncrement(&g_cLocks);
    v6 = CNotification::_Initialize(v4, a1);
    if ( v6 < 0 )
      (*(void (__fastcall **)(struct CNotification *))(*(_QWORD *)v5 + 16LL))(v5);
    else
      *a2 = v5;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180009b04  mov     [rsp+arg_0], rbx
0x180009b09  mov     [rsp+arg_8], rsi
0x180009b0e  push    rdi
0x180009b0f  sub     rsp, 20h
0x180009b13  mov     rdi, rcx
0x180009b16  mov     rsi, rdx
0x180009b19  mov     ecx, 0D0h; Size
0x180009b1e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009b23  mov     rbx, rax
0x180009b26  test    rax, rax
0x180009b29  jz      loc_180009BCB
0x180009b2f  lea     rax, ??_7CNotification@@6B@; const CNotification::`vftable'
0x180009b36  mov     dword ptr [rbx+8], 1
0x180009b3d  mov     [rbx], rax
0x180009b40  xor     eax, eax
0x180009b42  mov     [rbx+0Ch], ax
0x180009b46  mov     qword ptr [rbx+90h], 0
0x180009b51  mov     qword ptr [rbx+98h], 0
0x180009b5c  mov     qword ptr [rbx+0A0h], 0
0x180009b67  mov     qword ptr [rbx+0A8h], 0
0x180009b72  mov     qword ptr [rbx+0B0h], 0
0x180009b7d  mov     qword ptr [rbx+0B8h], 0
0x180009b88  mov     qword ptr [rbx+0C0h], 0
0x180009b93  mov     dword ptr [rbx+0C8h], 0Ah
0x180009b9d  lock inc cs:?g_cLocks@@3JA; long g_cLocks
0x180009ba4  mov     rdx, rdi; struct HCNOTIFICATION *
0x180009ba7  mov     rcx, rbx; this
0x180009baa  call    ?_Initialize@CNotification@@AEAAJPEBUHCNOTIFICATION@@@Z; CNotification::_Initialize(HCNOTIFICATION const *)
0x180009baf  mov     edi, eax
0x180009bb1  test    eax, eax
0x180009bb3  js      short loc_180009BBA
0x180009bb5  mov     [rsi], rbx
0x180009bb8  jmp     short loc_180009BD0
0x180009bba  mov     rax, [rbx]
0x180009bbd  mov     rcx, rbx
0x180009bc0  mov     rax, [rax+10h]
0x180009bc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bc9  jmp     short loc_180009BD0
0x180009bcb  mov     edi, 8007000Eh
0x180009bd0  mov     rbx, [rsp+28h+arg_0]
0x180009bd5  mov     eax, edi
0x180009bd7  mov     rsi, [rsp+28h+arg_8]
0x180009bdc  add     rsp, 20h
0x180009be0  pop     rdi
0x180009be1  retn
```
