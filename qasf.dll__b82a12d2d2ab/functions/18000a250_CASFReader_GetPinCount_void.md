# CASFReader::GetPinCount(void)

- ea: `0x18000a250`
- end: `0x18000a2f8`
- name: `?GetPinCount@CASFReader@@UEAAHXZ`
- size: `168`
- prototype: `__int64 __fastcall(CASFReader *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001460`
- `0x18000a250`
- `0x18001f010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000a272`
- `KERNEL32!EnterCriticalSection` at `0x18000a272`
- `KERNEL32!LeaveCriticalSection` at `0x18000a2da`
- `KERNEL32!LeaveCriticalSection` at `0x18000a2da`

## pseudocode

```c
__int64 __fastcall CASFReader::GetPinCount(CASFReader *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  unsigned int v3; // edi
  __int64 v4; // rdx
  __int64 v5; // rbp
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v9; // [rsp+20h] [rbp-38h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 10);
  EnterCriticalSection(v1);
  if ( *((_DWORD *)this + 112) )
  {
    v3 = *((_DWORD *)this + 74);
  }
  else
  {
    v4 = *((_QWORD *)this + 35);
    v3 = 0;
    if ( v4 )
    {
      do
      {
        v5 = *(_QWORD *)(v4 + 8);
        v6 = *(_QWORD *)(v4 + 16);
        v7 = *((_QWORD *)this + 44);
        v9 = 0;
        (*(void (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v7 + 72LL))(
          v7,
          *(unsigned __int16 *)(v6 + 304),
          &v9);
        if ( v9 )
          ++v3;
        v4 = v5;
      }
      while ( v5 );
    }
  }
  LeaveCriticalSection(v1);
  return v3;
}

```

## disassembly

```asm
0x18000a250  push    rbx
0x18000a252  push    rbp
0x18000a253  push    rsi
0x18000a254  push    rdi
0x18000a255  sub     rsp, 38h
0x18000a259  mov     rax, cs:__security_cookie
0x18000a260  xor     rax, rsp
0x18000a263  mov     [rsp+58h+var_30], rax
0x18000a268  mov     rbx, [rcx+50h]
0x18000a26c  mov     rsi, rcx
0x18000a26f  mov     rcx, rbx; lpCriticalSection
0x18000a272  call    cs:__imp_EnterCriticalSection
0x18000a278  cmp     dword ptr [rsi+1C0h], 0
0x18000a27f  jz      short loc_18000A289
0x18000a281  mov     edi, [rsi+128h]
0x18000a287  jmp     short loc_18000A2D7
0x18000a289  mov     rdx, [rsi+118h]
0x18000a290  xor     edi, edi
0x18000a292  test    rdx, rdx
0x18000a295  jz      short loc_18000A2D7
0x18000a297  mov     rbp, [rdx+8]
0x18000a29b  lea     r8, [rsp+58h+var_38]
0x18000a2a0  mov     rdx, [rdx+10h]
0x18000a2a4  mov     rcx, [rsi+160h]
0x18000a2ab  mov     [rsp+58h+var_38], 0
0x18000a2b3  movzx   edx, word ptr [rdx+130h]
0x18000a2ba  mov     rax, [rcx]
0x18000a2bd  mov     rax, [rax+48h]
0x18000a2c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2c6  cmp     [rsp+58h+var_38], 0
0x18000a2cb  jz      short loc_18000A2CF
0x18000a2cd  inc     edi
0x18000a2cf  mov     rdx, rbp
0x18000a2d2  test    rbp, rbp
0x18000a2d5  jnz     short loc_18000A297
0x18000a2d7  mov     rcx, rbx; lpCriticalSection
0x18000a2da  call    cs:__imp_LeaveCriticalSection
0x18000a2e0  mov     eax, edi
0x18000a2e2  mov     rcx, [rsp+58h+var_30]
0x18000a2e7  xor     rcx, rsp; StackCookie
0x18000a2ea  call    __security_check_cookie
0x18000a2ef  add     rsp, 38h
0x18000a2f3  pop     rdi
0x18000a2f4  pop     rsi
0x18000a2f5  pop     rbp
0x18000a2f6  pop     rbx
0x18000a2f7  retn
```
