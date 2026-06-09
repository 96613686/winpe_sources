# CValue::FSaveToRegistry(HKEY__ *,ushort const *)

- ea: `0x18000aa78`
- end: `0x18000ab47`
- name: `?FSaveToRegistry@CValue@@QEAAHPEAUHKEY__@@PEBG@Z`
- size: `207`
- prototype: `__int64 __fastcall(CValue *__hidden this, HKEY hKey, LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180008cc0`

## callees

- `0x180001f90`
- `0x180002a40`
- `0x18000aa78`
- `0x18000ae10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000ab15`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000ab15`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000aac1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000aac1`

## pseudocode

```c
_BOOL8 __fastcall CValue::FSaveToRegistry(CValue *this, HKEY hKey, LPCWSTR lpValueName)
{
  __int64 v7; // rax
  unsigned __int16 Data[256]; // [rsp+30h] [rbp-228h] BYREF

  memset_0(Data, 0, sizeof(Data));
  if ( *((_DWORD *)this + 4) )
  {
    CValue::ToString(this, Data, 0x100u);
    v7 = -1;
    do
      ++v7;
    while ( Data[v7] );
    return RegSetValueExW(hKey, lpValueName, 0, 1u, (const BYTE *)Data, 2 * v7 + 2) == 0;
  }
  else
  {
    RegDeleteValueW(hKey, lpValueName);
    return 1;
  }
}

```

## disassembly

```asm
0x18000aa78  mov     [rsp+arg_18], rbx
0x18000aa7d  push    rbp
0x18000aa7e  push    rsi
0x18000aa7f  push    rdi
0x18000aa80  sub     rsp, 240h
0x18000aa87  mov     rax, cs:__security_cookie
0x18000aa8e  xor     rax, rsp
0x18000aa91  mov     [rsp+258h+var_28], rax
0x18000aa99  mov     rsi, r8
0x18000aa9c  mov     rdi, rdx
0x18000aa9f  mov     rbx, rcx
0x18000aaa2  xor     edx, edx; Val
0x18000aaa4  mov     r8d, 200h; Size
0x18000aaaa  lea     rcx, [rsp+258h+Data]; void *
0x18000aaaf  call    memset_0
0x18000aab4  xor     ebp, ebp
0x18000aab6  cmp     [rbx+10h], ebp
0x18000aab9  jnz     short loc_18000AACC
0x18000aabb  mov     rdx, rsi; lpValueName
0x18000aabe  mov     rcx, rdi; hKey
0x18000aac1  call    cs:__imp_RegDeleteValueW
0x18000aac7  lea     eax, [rbp+1]
0x18000aaca  jmp     short loc_18000AB24
0x18000aacc  mov     r8d, 100h; unsigned int
0x18000aad2  lea     rdx, [rsp+258h+Data]; unsigned __int16 *
0x18000aad7  mov     rcx, rbx; this
0x18000aada  call    ?ToString@CValue@@QEAAHPEAGI@Z; CValue::ToString(ushort *,uint)
0x18000aadf  lea     rcx, [rsp+258h+Data]
0x18000aae4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000aae8  inc     rax
0x18000aaeb  cmp     [rcx+rax*2], bp
0x18000aaef  jnz     short loc_18000AAE8
0x18000aaf1  lea     eax, ds:2[rax*2]
0x18000aaf8  mov     r9d, 1; dwType
0x18000aafe  mov     [rsp+258h+cbData], eax; cbData
0x18000ab02  xor     r8d, r8d; Reserved
0x18000ab05  lea     rax, [rsp+258h+Data]
0x18000ab0a  mov     rdx, rsi; lpValueName
0x18000ab0d  mov     rcx, rdi; hKey
0x18000ab10  mov     [rsp+258h+lpData], rax; lpData
0x18000ab15  call    cs:__imp_RegSetValueExW
0x18000ab1b  test    eax, eax
0x18000ab1d  mov     ecx, ebp
0x18000ab1f  setz    cl
0x18000ab22  mov     eax, ecx
0x18000ab24  mov     rcx, [rsp+258h+var_28]
0x18000ab2c  xor     rcx, rsp; StackCookie
0x18000ab2f  call    __security_check_cookie
0x18000ab34  mov     rbx, [rsp+258h+arg_18]
0x18000ab3c  add     rsp, 240h
0x18000ab43  pop     rdi
0x18000ab44  pop     rsi
0x18000ab45  pop     rbp
0x18000ab46  retn
```
