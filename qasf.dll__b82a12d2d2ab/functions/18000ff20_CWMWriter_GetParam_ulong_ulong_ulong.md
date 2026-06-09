# CWMWriter::GetParam(ulong,ulong *,ulong *)

- ea: `0x18000ff20`
- end: `0x18000ffa8`
- name: `?GetParam@CWMWriter@@UEAAJKPEAK0@Z`
- size: `136`
- prototype: `__int64 __fastcall(CWMWriter *__hidden this, unsigned int, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000ff20`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000ff60`
- `KERNEL32!EnterCriticalSection` at `0x18000ff6f`
- `KERNEL32!EnterCriticalSection` at `0x18000ff81`
- `KERNEL32!EnterCriticalSection` at `0x18000ff60`
- `KERNEL32!EnterCriticalSection` at `0x18000ff6f`
- `KERNEL32!EnterCriticalSection` at `0x18000ff81`
- `KERNEL32!LeaveCriticalSection` at `0x18000ff90`
- `KERNEL32!LeaveCriticalSection` at `0x18000ff90`

## pseudocode

```c
__int64 __fastcall CWMWriter::GetParam(CWMWriter *this, int a2, unsigned int *a3, unsigned int *a4)
{
  int v7; // edx
  int v8; // edx
  unsigned int v9; // eax

  if ( !a3 )
    return 2147500035LL;
  if ( a4 )
    return 2147942487LL;
  v7 = a2 - 1;
  if ( v7 )
  {
    v8 = v7 - 1;
    if ( v8 )
    {
      if ( v8 != 1 )
        return 2147942487LL;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
      v9 = *((_DWORD *)this + 20);
    }
    else
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
      v9 = *((_DWORD *)this + 61);
    }
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    v9 = *((_DWORD *)this + 17);
  }
  *a3 = v9;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  return 0;
}

```

## disassembly

```asm
0x18000ff20  mov     [rsp+arg_0], rbx
0x18000ff25  mov     [rsp+arg_8], rsi
0x18000ff2a  push    rdi
0x18000ff2b  sub     rsp, 20h
0x18000ff2f  mov     rsi, r8
0x18000ff32  mov     rdi, rcx
0x18000ff35  test    r8, r8
0x18000ff38  jnz     short loc_18000FF41
0x18000ff3a  mov     eax, 80004003h
0x18000ff3f  jmp     short loc_18000FF98
0x18000ff41  test    r9, r9
0x18000ff44  jnz     short loc_18000FF55
0x18000ff46  sub     edx, 1
0x18000ff49  jz      short loc_18000FF7D
0x18000ff4b  sub     edx, 1
0x18000ff4e  jz      short loc_18000FF6B
0x18000ff50  cmp     edx, 1
0x18000ff53  jz      short loc_18000FF5C
0x18000ff55  mov     eax, 80070057h
0x18000ff5a  jmp     short loc_18000FF98
0x18000ff5c  add     rcx, 58h ; 'X'; lpCriticalSection
0x18000ff60  call    cs:__imp_EnterCriticalSection
0x18000ff66  mov     eax, [rdi+50h]
0x18000ff69  jmp     short loc_18000FF8A
0x18000ff6b  add     rcx, 58h ; 'X'; lpCriticalSection
0x18000ff6f  call    cs:__imp_EnterCriticalSection
0x18000ff75  mov     eax, [rdi+0F4h]
0x18000ff7b  jmp     short loc_18000FF8A
0x18000ff7d  add     rcx, 58h ; 'X'; lpCriticalSection
0x18000ff81  call    cs:__imp_EnterCriticalSection
0x18000ff87  mov     eax, [rdi+44h]
0x18000ff8a  lea     rcx, [rdi+58h]; lpCriticalSection
0x18000ff8e  mov     [rsi], eax
0x18000ff90  call    cs:__imp_LeaveCriticalSection
0x18000ff96  xor     eax, eax
0x18000ff98  mov     rbx, [rsp+28h+arg_0]
0x18000ff9d  mov     rsi, [rsp+28h+arg_8]
0x18000ffa2  add     rsp, 20h
0x18000ffa6  pop     rdi
0x18000ffa7  retn
```
