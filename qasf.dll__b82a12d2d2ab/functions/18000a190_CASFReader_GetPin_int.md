# CASFReader::GetPin(int)

- ea: `0x18000a190`
- end: `0x18000a24a`
- name: `?GetPin@CASFReader@@UEAAPEAVCBasePin@@H@Z`
- size: `186`
- prototype: `struct CBasePin *__fastcall(CASFReader *__hidden this, int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001460`
- `0x18000a190`
- `0x18001f010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000a1bd`
- `KERNEL32!EnterCriticalSection` at `0x18000a1bd`
- `KERNEL32!LeaveCriticalSection` at `0x18000a221`
- `KERNEL32!LeaveCriticalSection` at `0x18000a221`

## pseudocode

```c
struct CBasePin *__fastcall CASFReader::GetPin(CASFReader *this, int a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  __int64 v5; // rax
  bool v6; // zf
  __int64 v7; // r14
  __int64 v8; // rdi
  int v10; // [rsp+20h] [rbp-28h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 10);
  EnterCriticalSection(v2);
  v5 = *((_QWORD *)this + 35);
  if ( v5 )
  {
    do
    {
      v6 = *((_DWORD *)this + 112) == 0;
      v7 = *(_QWORD *)(v5 + 8);
      v8 = *(_QWORD *)(v5 + 16);
      v10 = 2;
      if ( !v6
        || ((*(void (__fastcall **)(_QWORD, _QWORD, int *))(**((_QWORD **)this + 44) + 72LL))(
              *((_QWORD *)this + 44),
              *(unsigned __int16 *)(v8 + 304),
              &v10),
            v10) )
      {
        if ( !a2 )
          goto LABEL_8;
        --a2;
      }
      v5 = v7;
    }
    while ( v7 );
  }
  v8 = 0;
LABEL_8:
  LeaveCriticalSection(v2);
  return (struct CBasePin *)v8;
}

```

## disassembly

```asm
0x18000a190  mov     [rsp+arg_8], rbx
0x18000a195  mov     [rsp+arg_10], rbp
0x18000a19a  push    rsi
0x18000a19b  push    rdi
0x18000a19c  push    r14
0x18000a19e  sub     rsp, 30h
0x18000a1a2  mov     rax, cs:__security_cookie
0x18000a1a9  xor     rax, rsp
0x18000a1ac  mov     [rsp+48h+var_20], rax
0x18000a1b1  mov     rbx, [rcx+50h]
0x18000a1b5  mov     rbp, rcx
0x18000a1b8  mov     rcx, rbx; lpCriticalSection
0x18000a1bb  mov     esi, edx
0x18000a1bd  call    cs:__imp_EnterCriticalSection
0x18000a1c3  mov     rax, [rbp+118h]
0x18000a1ca  test    rax, rax
0x18000a1cd  jz      short loc_18000A21C
0x18000a1cf  cmp     dword ptr [rbp+1C0h], 0
0x18000a1d6  mov     r14, [rax+8]
0x18000a1da  mov     rdi, [rax+10h]
0x18000a1de  mov     [rsp+48h+var_28], 2
0x18000a1e6  jnz     short loc_18000A20E
0x18000a1e8  mov     rcx, [rbp+160h]
0x18000a1ef  lea     r8, [rsp+48h+var_28]
0x18000a1f4  movzx   edx, word ptr [rdi+130h]
0x18000a1fb  mov     rax, [rcx]
0x18000a1fe  mov     rax, [rax+48h]
0x18000a202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a207  cmp     [rsp+48h+var_28], 0
0x18000a20c  jz      short loc_18000A214
0x18000a20e  test    esi, esi
0x18000a210  jz      short loc_18000A21E
0x18000a212  dec     esi
0x18000a214  mov     rax, r14
0x18000a217  test    r14, r14
0x18000a21a  jnz     short loc_18000A1CF
0x18000a21c  xor     edi, edi
0x18000a21e  mov     rcx, rbx; lpCriticalSection
0x18000a221  call    cs:__imp_LeaveCriticalSection
0x18000a227  mov     rax, rdi
0x18000a22a  mov     rcx, [rsp+48h+var_20]
0x18000a22f  xor     rcx, rsp; StackCookie
0x18000a232  call    __security_check_cookie
0x18000a237  mov     rbx, [rsp+48h+arg_8]
0x18000a23c  mov     rbp, [rsp+48h+arg_10]
0x18000a241  add     rsp, 30h
0x18000a245  pop     r14
0x18000a247  pop     rdi
0x18000a248  pop     rsi
0x18000a249  retn
```
