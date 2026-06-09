# CFvePolicyReader::ReOpen(void)

- ea: `0x18002aa30`
- end: `0x18002aac5`
- name: `?ReOpen@CFvePolicyReader@@UEAAJXZ`
- size: `149`
- prototype: `__int64 __fastcall(CFvePolicyReader *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180001bb0`
- `0x180002774`
- `0x18000b978`
- `0x18002aa30`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall CFvePolicyReader::ReOpen(CFvePolicyReader *this)
{
  int v2; // ebx
  unsigned __int16 v4[264]; // [rsp+20h] [rbp-228h] BYREF

  v2 = 0;
  memset_0(v4, 0, 0x208u);
  if ( *((_BYTE *)this + 33) )
  {
    v2 = StringCchCopyW(v4, 0x104u, (const unsigned __int16 *)this + 17);
    if ( v2 >= 0 )
    {
      v2 = (*(__int64 (__fastcall **)(CFvePolicyReader *, unsigned __int16 *))(*(_QWORD *)this + 48LL))(this, v4);
      if ( v2 >= 0 )
        *((_BYTE *)this + 33) = 0;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18002aa30  mov     [rsp+arg_8], rbx
0x18002aa35  push    rdi
0x18002aa36  sub     rsp, 240h
0x18002aa3d  mov     rax, cs:__security_cookie
0x18002aa44  xor     rax, rsp
0x18002aa47  mov     [rsp+248h+var_18], rax
0x18002aa4f  mov     rdi, rcx
0x18002aa52  xor     edx, edx; Val
0x18002aa54  lea     rcx, [rsp+248h+var_228]; void *
0x18002aa59  mov     r8d, 208h; Size
0x18002aa5f  xor     ebx, ebx
0x18002aa61  call    memset_0
0x18002aa66  cmp     [rdi+21h], bl
0x18002aa69  jz      short loc_18002AAA2
0x18002aa6b  lea     r8, [rdi+22h]; unsigned __int16 *
0x18002aa6f  mov     edx, 104h; unsigned __int64
0x18002aa74  lea     rcx, [rsp+248h+var_228]; unsigned __int16 *
0x18002aa79  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002aa7e  mov     ebx, eax
0x18002aa80  test    eax, eax
0x18002aa82  js      short loc_18002AAA2
0x18002aa84  mov     rax, [rdi]
0x18002aa87  lea     rdx, [rsp+248h+var_228]
0x18002aa8c  mov     rcx, rdi
0x18002aa8f  mov     rax, [rax+30h]
0x18002aa93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa98  mov     ebx, eax
0x18002aa9a  test    eax, eax
0x18002aa9c  js      short loc_18002AAA2
0x18002aa9e  mov     byte ptr [rdi+21h], 0
0x18002aaa2  mov     eax, ebx
0x18002aaa4  mov     rcx, [rsp+248h+var_18]
0x18002aaac  xor     rcx, rsp; StackCookie
0x18002aaaf  call    __security_check_cookie
0x18002aab4  mov     rbx, [rsp+248h+arg_8]
0x18002aabc  add     rsp, 240h
0x18002aac3  pop     rdi
0x18002aac4  retn
```
