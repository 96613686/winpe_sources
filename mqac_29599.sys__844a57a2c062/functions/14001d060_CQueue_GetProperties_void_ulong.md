# CQueue::GetProperties(void *,ulong)

- ea: `0x14001d060`
- end: `0x14001d154`
- name: `?GetProperties@CQueue@@UEAAJPEAXK@Z`
- size: `244`
- prototype: `int(CQueue *__hidden this, void *, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14001d060`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x14001d07c`
- `ntoskrnl!ProbeForWrite` at `0x14001d07c`

## pseudocode

```c
__int64 __fastcall CQueue::GetProperties(CQueue *this, _DWORD *a2, unsigned int a3)
{
  int v5; // ecx
  int v6; // eax
  __int64 v7; // rdx
  int v8; // eax
  _QWORD **v9; // rdi
  _QWORD *v10; // rcx
  _QWORD *v11; // rdx
  _QWORD *i; // r8

  ProbeForWrite(a2, a3, 1u);
  *a2 = *((_DWORD *)this + 48);
  v5 = -1;
  if ( *((_QWORD *)this + 23) >= 0xFFFFFFFF )
    v6 = -1;
  else
    v6 = *((_DWORD *)this + 46);
  a2[1] = v6;
  a2[4] = *((_DWORD *)this + 61);
  a2[5] = *((_DWORD *)this + 62) + 1;
  *((_QWORD *)a2 + 3) = *((_QWORD *)this + 32);
  v7 = *((_QWORD *)this + 19);
  if ( v7 )
  {
    a2[2] = *(_DWORD *)(v7 + 192);
    if ( *(_QWORD *)(v7 + 184) < 0xFFFFFFFF )
      v5 = *(_DWORD *)(v7 + 184);
    a2[3] = v5;
  }
  else
  {
    *((_QWORD *)a2 + 1) = 0;
  }
  if ( *((_BYTE *)a2 + 32) )
  {
    v8 = 0;
    v9 = (_QWORD **)((char *)this + 360);
    v10 = *v9;
    v11 = *v9;
    for ( i = *v9; v9 != v11 && i; i = v11 )
    {
      ++v8;
      v11 = (_QWORD *)*v10;
      v10 = v11;
    }
    a2[8] = v8;
  }
  return 0;
}

```

## disassembly

```asm
0x14001d060  mov     [rsp+arg_0], rbx
0x14001d065  push    rdi
0x14001d066  sub     rsp, 40h
0x14001d06a  mov     rbx, rdx
0x14001d06d  mov     rdi, rcx
0x14001d070  mov     edx, r8d; Length
0x14001d073  mov     r8d, 1; Alignment
0x14001d079  mov     rcx, rbx; Address
0x14001d07c  call    cs:__imp_ProbeForWrite
0x14001d083  nop     dword ptr [rax+rax+00h]
0x14001d088  mov     eax, [rdi+0C0h]
0x14001d08e  mov     [rbx], eax
0x14001d090  mov     ecx, 0FFFFFFFFh
0x14001d095  cmp     [rdi+0B8h], rcx
0x14001d09c  jnb     short loc_14001D0A6
0x14001d09e  mov     eax, [rdi+0B8h]
0x14001d0a4  jmp     short loc_14001D0A8
0x14001d0a6  mov     eax, ecx
0x14001d0a8  mov     [rbx+4], eax
0x14001d0ab  mov     eax, [rdi+0F4h]
0x14001d0b1  mov     [rbx+10h], eax
0x14001d0b4  mov     eax, [rdi+0F8h]
0x14001d0ba  inc     eax
0x14001d0bc  mov     [rbx+14h], eax
0x14001d0bf  mov     rax, [rdi+100h]
0x14001d0c6  mov     [rbx+18h], rax
0x14001d0ca  mov     rdx, [rdi+98h]
0x14001d0d1  xor     r9d, r9d
0x14001d0d4  test    rdx, rdx
0x14001d0d7  jz      short loc_14001D0F6
0x14001d0d9  mov     eax, [rdx+0C0h]
0x14001d0df  mov     [rbx+8], eax
0x14001d0e2  cmp     [rdx+0B8h], rcx
0x14001d0e9  jnb     short loc_14001D0F1
0x14001d0eb  mov     ecx, [rdx+0B8h]
0x14001d0f1  mov     [rbx+0Ch], ecx
0x14001d0f4  jmp     short loc_14001D0FA
0x14001d0f6  mov     [rbx+8], r9
0x14001d0fa  cmp     [rbx+20h], r9b
0x14001d0fe  jz      short loc_14001D144
0x14001d100  mov     eax, r9d
0x14001d103  mov     [rsp+48h+var_28], eax
0x14001d107  add     rdi, 168h
0x14001d10e  mov     [rsp+48h+var_20], rdi
0x14001d113  mov     rcx, [rdi]
0x14001d116  mov     [rsp+48h+var_18], rcx
0x14001d11b  mov     rdx, rcx
0x14001d11e  mov     r8, rcx
0x14001d121  cmp     rdi, rdx
0x14001d124  jz      short loc_14001D141
0x14001d126  test    r8, r8
0x14001d129  jz      short loc_14001D141
0x14001d12b  inc     eax
0x14001d12d  mov     [rsp+48h+var_28], eax
0x14001d131  mov     rdx, [rcx]
0x14001d134  mov     rcx, rdx
0x14001d137  mov     [rsp+48h+var_18], rdx
0x14001d13c  mov     r8, rdx
0x14001d13f  jmp     short loc_14001D121
0x14001d141  mov     [rbx+20h], eax
0x14001d144  xor     eax, eax
0x14001d146  jmp     short $+2
0x14001d148  mov     rbx, [rsp+48h+arg_0]
0x14001d14d  add     rsp, 40h
0x14001d151  pop     rdi
0x14001d152  retn
```
