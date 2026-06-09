# NtWin32LiveSystemProvider::GetOsCsdString(ushort *,ulong)

- ea: `0x180024940`
- end: `0x1800249d9`
- name: `?GetOsCsdString@NtWin32LiveSystemProvider@@UEAAJPEAGK@Z`
- size: `153`
- prototype: `int(NtWin32LiveSystemProvider *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001710`
- `0x1800021f4`
- `0x1800132b0`
- `0x18001bec8`
- `0x180024940`
- `0x18002c010`

## pseudocode

```c
int __fastcall NtWin32LiveSystemProvider::GetOsCsdString(
        __int64 (__fastcall **this)(int *),
        unsigned __int16 *a2,
        unsigned int a3)
{
  int result; // eax
  __int64 (__fastcall *v7)(int *); // rbx
  int v8; // eax
  int v9; // [rsp+20h] [rbp-148h] BYREF
  _BYTE v10[16]; // [rsp+24h] [rbp-144h] BYREF
  unsigned __int16 v11[134]; // [rsp+34h] [rbp-134h] BYREF

  result = Win32LiveSystemProvider::GetOsCsdString((Win32LiveSystemProvider *)this, a2, a3);
  if ( result >= 0 )
  {
    v7 = this[123];
    if ( v7 )
    {
      memset_0(v10, 0, 0x110u);
      v9 = 276;
      v8 = v7(&v9);
      if ( v8 < 0 )
        return v8 | 0x10000000;
      GenStrCopyNW(a2, v11, a3);
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180024940  push    rbx
0x180024942  push    rsi
0x180024943  push    rdi
0x180024944  sub     rsp, 150h
0x18002494b  mov     rax, cs:__security_cookie
0x180024952  xor     rax, rsp
0x180024955  mov     [rsp+168h+var_28], rax
0x18002495d  mov     esi, r8d
0x180024960  mov     rdi, rdx
0x180024963  mov     rbx, rcx
0x180024966  call    ?GetOsCsdString@Win32LiveSystemProvider@@UEAAJPEAGK@Z; Win32LiveSystemProvider::GetOsCsdString(ushort *,ulong)
0x18002496b  test    eax, eax
0x18002496d  js      short loc_1800249BE
0x18002496f  mov     rbx, [rbx+3D8h]
0x180024976  test    rbx, rbx
0x180024979  jz      short loc_1800249BC
0x18002497b  xor     edx, edx; Val
0x18002497d  lea     rcx, [rsp+168h+var_144]; void *
0x180024982  mov     r8d, 110h; Size
0x180024988  call    memset_0
0x18002498d  lea     rcx, [rsp+168h+var_148]
0x180024992  mov     [rsp+168h+var_148], 114h
0x18002499a  mov     rax, rbx
0x18002499d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249a2  test    eax, eax
0x1800249a4  jns     short loc_1800249AC
0x1800249a6  bts     eax, 1Ch
0x1800249aa  jmp     short loc_1800249BE
0x1800249ac  mov     r8d, esi; int
0x1800249af  lea     rdx, [rsp+168h+var_134]; unsigned __int16 *
0x1800249b4  mov     rcx, rdi; unsigned __int16 *
0x1800249b7  call    ?GenStrCopyNW@@YAPEAGPEAGPEBGH@Z; GenStrCopyNW(ushort *,ushort const *,int)
0x1800249bc  xor     eax, eax
0x1800249be  mov     rcx, [rsp+168h+var_28]
0x1800249c6  xor     rcx, rsp; StackCookie
0x1800249c9  call    __security_check_cookie
0x1800249ce  add     rsp, 150h
0x1800249d5  pop     rdi
0x1800249d6  pop     rsi
0x1800249d7  pop     rbx
0x1800249d8  retn
```
