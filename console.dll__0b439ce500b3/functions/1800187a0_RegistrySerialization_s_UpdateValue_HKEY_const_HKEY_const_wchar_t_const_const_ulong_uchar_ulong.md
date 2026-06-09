# RegistrySerialization::s_UpdateValue(HKEY__ * const,HKEY__ * const,wchar_t const * const,ulong,uchar *,ulong)

- ea: `0x1800187a0`
- end: `0x180018866`
- name: `?s_UpdateValue@RegistrySerialization@@SAJQEAUHKEY__@@0QEB_WKPEAEK@Z`
- size: `198`
- prototype: `__int64 __fastcall(HKEY, HKEY, const wchar_t *const, unsigned int, unsigned __int8 *Buf1, size_t Size)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180011f44`

## callees

- `0x180001980`
- `0x1800019bc`
- `0x180018544`
- `0x1800186e4`
- `0x180018760`
- `0x1800187a0`
- `0x180018d00`

## pseudocode

```c
__int64 __fastcall RegistrySerialization::s_UpdateValue(
        HKEY a1,
        HKEY a2,
        const WCHAR *a3,
        DWORD a4,
        unsigned __int8 *Buf1,
        size_t Size)
{
  unsigned int v10; // ebx
  unsigned __int8 *v11; // rax
  unsigned __int8 *v12; // rdi
  unsigned int v13; // eax

  v10 = -1073741823;
  v11 = (unsigned __int8 *)operator new[]((unsigned int)Size, (const struct std::nothrow_t *)&std::nothrow);
  v12 = v11;
  if ( v11 )
  {
    if ( a1 == a2
      || (int)RegistrySerialization::s_QueryValue(a1, a3, Size, a4, v11, 0) < 0
      || memcmp_0(Buf1, v12, (unsigned int)Size) )
    {
      v13 = RegistrySerialization::s_SetValue(a2, a3, a4, Buf1, Size);
    }
    else
    {
      v13 = RegistrySerialization::s_DeleteValue(a2, a3);
    }
    v10 = v13;
    operator delete(v12);
  }
  return v10;
}

```

## disassembly

```asm
0x1800187a0  push    rbx
0x1800187a2  push    rbp
0x1800187a3  push    rsi
0x1800187a4  push    rdi
0x1800187a5  push    r12
0x1800187a7  push    r13
0x1800187a9  push    r14
0x1800187ab  push    r15
0x1800187ad  sub     rsp, 38h
0x1800187b1  mov     r15d, dword ptr [rsp+78h+Size]
0x1800187b9  mov     rsi, rdx
0x1800187bc  mov     r14, rcx
0x1800187bf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800187c6  mov     ecx, r15d; unsigned __int64
0x1800187c9  mov     r12d, r9d
0x1800187cc  mov     rbp, r8
0x1800187cf  mov     ebx, 0C0000001h
0x1800187d4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800187d9  mov     rdi, rax
0x1800187dc  test    rax, rax
0x1800187df  jz      short loc_180018852
0x1800187e1  cmp     r14, rsi
0x1800187e4  jz      short loc_18001882D
0x1800187e6  mov     [rsp+78h+var_50], 0; unsigned int *
0x1800187ef  mov     r9d, r12d; unsigned int
0x1800187f2  mov     r8d, r15d; unsigned int
0x1800187f5  mov     [rsp+78h+var_58], rax; unsigned __int8 *
0x1800187fa  mov     rdx, rbp; wchar_t *
0x1800187fd  mov     rcx, r14; HKEY
0x180018800  call    ?s_QueryValue@RegistrySerialization@@SAJQEAUHKEY__@@QEB_WKKQEAEQEAK@Z; RegistrySerialization::s_QueryValue(HKEY__ * const,wchar_t const * const,ulong,ulong,uchar * const,ulong * const)
0x180018805  test    eax, eax
0x180018807  js      short loc_18001882D
0x180018809  mov     rcx, [rsp+78h+Buf1]; Buf1
0x180018811  mov     r8d, r15d; Size
0x180018814  mov     rdx, rdi; Buf2
0x180018817  call    memcmp_0
0x18001881c  test    eax, eax
0x18001881e  jnz     short loc_18001882D
0x180018820  mov     rdx, rbp; wchar_t *
0x180018823  mov     rcx, rsi; HKEY
0x180018826  call    ?s_DeleteValue@RegistrySerialization@@SAJQEAUHKEY__@@QEB_W@Z; RegistrySerialization::s_DeleteValue(HKEY__ * const,wchar_t const * const)
0x18001882b  jmp     short loc_180018848
0x18001882d  mov     r9, [rsp+78h+Buf1]; unsigned __int8 *
0x180018835  mov     r8d, r12d; unsigned int
0x180018838  mov     rdx, rbp; wchar_t *
0x18001883b  mov     dword ptr [rsp+78h+var_58], r15d; unsigned int
0x180018840  mov     rcx, rsi; HKEY
0x180018843  call    ?s_SetValue@RegistrySerialization@@SAJQEAUHKEY__@@QEB_WKQEAEK@Z; RegistrySerialization::s_SetValue(HKEY__ * const,wchar_t const * const,ulong,uchar * const,ulong)
0x180018848  mov     rcx, rdi; void *
0x18001884b  mov     ebx, eax
0x18001884d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180018852  mov     eax, ebx
0x180018854  add     rsp, 38h
0x180018858  pop     r15
0x18001885a  pop     r14
0x18001885c  pop     r13
0x18001885e  pop     r12
0x180018860  pop     rdi
0x180018861  pop     rsi
0x180018862  pop     rbp
0x180018863  pop     rbx
0x180018864  retn
```
