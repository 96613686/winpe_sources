# CComponentData::_UpdateCMenuItems(CLogInfo *)

- ea: `0x180008a6c`
- end: `0x180008b67`
- name: `?_UpdateCMenuItems@CComponentData@@AEAAXPEAVCLogInfo@@@Z`
- size: `251`
- prototype: `void __fastcall(CComponentData *__hidden this, struct CLogInfo *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800053c0`

## callees

- `0x180008a6c`
- `0x180024010`

## pseudocode

```c
void __fastcall CComponentData::_UpdateCMenuItems(CComponentData *this, struct CLogInfo *a2)
{
  __int64 v4; // rcx
  struct CLogInfo *v5; // rax
  __int64 v6; // rcx
  int v7; // eax
  struct CLogInfo *v8; // [rsp+30h] [rbp+8h] BYREF

  dword_18002F4AC = (*((_BYTE *)a2 + 24) & 1) != 0 ? 3 : 0;
  dword_18002F474 = (*((_WORD *)a2 + 12) & 0x200) != 0 ? 3 : 0;
  if ( (*((_BYTE *)a2 + 24) & 2) != 0 )
  {
    dword_18002F3B0 = 520;
    dword_18002F394 = 0;
  }
  else
  {
    dword_18002F3B0 = 0;
    dword_18002F394 = 520;
  }
  v4 = *((_QWORD *)this + 9);
  v5 = 0;
  v8 = 0;
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64, struct CLogInfo **))(*(_QWORD *)(v4 + 40) + 40LL))(v4 + 40, &v8);
    v5 = v8;
  }
  v6 = *((_QWORD *)this + 9);
  if ( v6 && a2 == v5 )
  {
    v7 = *(_DWORD *)(v6 + 1600);
    if ( v7 == 8 )
    {
      dword_18002F3E8 = 8;
LABEL_10:
      dword_18002F404 = 0;
      return;
    }
    dword_18002F3E8 = 0;
    if ( v7 != 9 )
      goto LABEL_10;
    dword_18002F404 = 8;
  }
  else
  {
    dword_18002F3E8 = 3;
    dword_18002F404 = 3;
  }
}

```

## disassembly

```asm
0x180008a6c  mov     [rsp+arg_8], rsi
0x180008a71  push    rdi
0x180008a72  sub     rsp, 20h
0x180008a76  mov     al, [rdx+18h]
0x180008a79  mov     rdi, rdx
0x180008a7c  and     al, 1
0x180008a7e  mov     rsi, rcx
0x180008a81  neg     al
0x180008a83  mov     eax, 200h
0x180008a88  sbb     r8d, r8d
0x180008a8b  and     r8d, 3
0x180008a8f  mov     cs:dword_18002F4AC, r8d
0x180008a96  and     ax, [rdx+18h]
0x180008a9a  neg     ax
0x180008a9d  sbb     eax, eax
0x180008a9f  and     eax, 3
0x180008aa2  mov     cs:dword_18002F474, eax
0x180008aa8  test    byte ptr [rdx+18h], 2
0x180008aac  jz      short loc_180008AC4
0x180008aae  mov     cs:dword_18002F3B0, 208h
0x180008ab8  mov     cs:dword_18002F394, 0
0x180008ac2  jmp     short loc_180008AD8
0x180008ac4  mov     cs:dword_18002F3B0, 0
0x180008ace  mov     cs:dword_18002F394, 208h
0x180008ad8  mov     rcx, [rcx+48h]
0x180008adc  xor     eax, eax
0x180008ade  mov     [rsp+28h+arg_0], rax
0x180008ae3  test    rcx, rcx
0x180008ae6  jz      short loc_180008B02
0x180008ae8  add     rcx, 28h ; '('
0x180008aec  lea     rdx, [rsp+28h+arg_0]
0x180008af1  mov     rax, [rcx]
0x180008af4  mov     rax, [rax+28h]
0x180008af8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008afd  mov     rax, [rsp+28h+arg_0]
0x180008b02  mov     rcx, [rsi+48h]
0x180008b06  test    rcx, rcx
0x180008b09  jz      short loc_180008B48
0x180008b0b  cmp     rdi, rax
0x180008b0e  jnz     short loc_180008B48
0x180008b10  mov     eax, [rcx+640h]
0x180008b16  mov     ecx, 8
0x180008b1b  cmp     eax, ecx
0x180008b1d  jnz     short loc_180008B31
0x180008b1f  mov     cs:dword_18002F3E8, ecx
0x180008b25  mov     cs:dword_18002F404, 0
0x180008b2f  jmp     short loc_180008B5C
0x180008b31  mov     cs:dword_18002F3E8, 0
0x180008b3b  cmp     eax, 9
0x180008b3e  jnz     short loc_180008B25
0x180008b40  mov     cs:dword_18002F404, ecx
0x180008b46  jmp     short loc_180008B5C
0x180008b48  mov     cs:dword_18002F3E8, 3
0x180008b52  mov     cs:dword_18002F404, 3
0x180008b5c  mov     rsi, [rsp+28h+arg_8]
0x180008b61  add     rsp, 20h
0x180008b65  pop     rdi
0x180008b66  retn
```
