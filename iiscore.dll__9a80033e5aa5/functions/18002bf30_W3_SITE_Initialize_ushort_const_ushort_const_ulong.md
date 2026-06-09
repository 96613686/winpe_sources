# W3_SITE::Initialize(ushort const *,ushort const *,ulong)

- ea: `0x18002bf30`
- end: `0x18002c0f5`
- name: `?Initialize@W3_SITE@@QEAAJPEBG0K@Z`
- size: `453`
- prototype: `__int64 __fastcall(W3_SITE *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180008f30`

## callees

- `0x18002b93c`
- `0x18002bf30`
- `0x180035010`

## import_xrefs

- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18002bfe3`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18002bfe3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002bfff`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002c075`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002bfff`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002c075`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x18002c05a`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x18002c05a`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18002c0c2`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18002c0c2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002bf79`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002bf93`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002bf79`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002bf93`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x18002bfda`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x18002bfda`

## pseudocode

```c
__int64 __fastcall W3_SITE::Initialize(W3_SITE *this, const unsigned __int16 *a2, const unsigned __int16 *a3, int a4)
{
  const unsigned __int16 *v4; // rsi
  int lambda_66d6c8ed0ed2deee44b2b0fee89d5763___lambda_f6098c0808415f863707cccac41fba4f; // ebx
  W3_SERVER *v9; // rax
  STRU *v10; // rdi
  BUFFER *Buffer; // rax
  __int64 (__fastcall *v12)(__int64, const unsigned __int16 *, const wchar_t *, unsigned __int16 *, unsigned int *, _QWORD, _QWORD, _QWORD); // rbx
  unsigned __int16 *Str; // rax
  __int64 (__fastcall *v14)(__int64, const unsigned __int16 *, const wchar_t *, unsigned __int16 *, unsigned int *, _QWORD, _QWORD, _QWORD); // rbx
  unsigned __int16 *v15; // rax
  __int64 v17; // [rsp+50h] [rbp-28h] BYREF
  unsigned int Size; // [rsp+80h] [rbp+8h] BYREF

  v4 = a2;
  v17 = 0;
  LOBYTE(a2) = 0;
  lambda_66d6c8ed0ed2deee44b2b0fee89d5763___lambda_f6098c0808415f863707cccac41fba4f = PER_CPU_IISWPSiteCounters_::Create__lambda_66d6c8ed0ed2deee44b2b0fee89d5763___lambda_f6098c0808415f863707cccac41fba4f___(
                                                                                        *((unsigned int *)this + 4),
                                                                                        a2,
                                                                                        (char *)this + 664);
  if ( lambda_66d6c8ed0ed2deee44b2b0fee89d5763___lambda_f6098c0808415f863707cccac41fba4f >= 0 )
  {
    lambda_66d6c8ed0ed2deee44b2b0fee89d5763___lambda_f6098c0808415f863707cccac41fba4f = STRU::Copy(
                                                                                          (W3_SITE *)((char *)this + 24),
                                                                                          v4);
    if ( lambda_66d6c8ed0ed2deee44b2b0fee89d5763___lambda_f6098c0808415f863707cccac41fba4f >= 0 )
    {
      lambda_66d6c8ed0ed2deee44b2b0fee89d5763___lambda_f6098c0808415f863707cccac41fba4f = STRU::Copy(
                                                                                            (W3_SITE *)((char *)this + 144),
                                                                                            a3);
      if ( lambda_66d6c8ed0ed2deee44b2b0fee89d5763___lambda_f6098c0808415f863707cccac41fba4f >= 0 )
      {
        v9 = g_pW3Server;
        *((_DWORD *)this + 5) = a4;
        lambda_66d6c8ed0ed2deee44b2b0fee89d5763___lambda_f6098c0808415f863707cccac41fba4f = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)v9 + 187) + 56LL))(
                                                                                              *((_QWORD *)v9 + 187),
                                                                                              &v17);
        if ( lambda_66d6c8ed0ed2deee44b2b0fee89d5763___lambda_f6098c0808415f863707cccac41fba4f >= 0 )
        {
          v10 = (W3_SITE *)((char *)this + 264);
          Buffer = STRU::QueryBuffer(v10);
          Size = BUFFER::QuerySize(Buffer);
          v12 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const wchar_t *, unsigned __int16 *, unsigned int *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v17 + 40LL);
          Str = STRU::QueryStr(v10);
          lambda_66d6c8ed0ed2deee44b2b0fee89d5763___lambda_f6098c0808415f863707cccac41fba4f = v12(
                                                                                                v17,
                                                                                                v4,
                                                                                                L"/",
                                                                                                Str,
                                                                                                &Size,
                                                                                                0,
                                                                                                0,
                                                                                                0);
          if ( lambda_66d6c8ed0ed2deee44b2b0fee89d5763___lambda_f6098c0808415f863707cccac41fba4f == -2147024774 )
          {
            lambda_66d6c8ed0ed2deee44b2b0fee89d5763___lambda_f6098c0808415f863707cccac41fba4f = STRU::Resize(v10, Size);
            if ( lambda_66d6c8ed0ed2deee44b2b0fee89d5763___lambda_f6098c0808415f863707cccac41fba4f < 0 )
              goto LABEL_9;
            v14 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const wchar_t *, unsigned __int16 *, unsigned int *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v17 + 40LL);
            v15 = STRU::QueryStr(v10);
            lambda_66d6c8ed0ed2deee44b2b0fee89d5763___lambda_f6098c0808415f863707cccac41fba4f = v14(
                                                                                                  v17,
                                                                                                  v4,
                                                                                                  L"/",
                                                                                                  v15,
                                                                                                  &Size,
                                                                                                  0,
                                                                                                  0,
                                                                                                  0);
          }
          STRU::SyncWithBuffer(v10);
        }
      }
    }
  }
LABEL_9:
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  return (unsigned int)lambda_66d6c8ed0ed2deee44b2b0fee89d5763___lambda_f6098c0808415f863707cccac41fba4f;
}

```

## disassembly

```asm
0x18002bf30  mov     [rsp+arg_8], rbx
0x18002bf35  mov     [rsp+arg_10], rbp
0x18002bf3a  push    rsi
0x18002bf3b  push    rdi
0x18002bf3c  push    r14
0x18002bf3e  sub     rsp, 60h
0x18002bf42  mov     rsi, rdx
0x18002bf45  mov     [rsp+78h+var_28], 0
0x18002bf4e  xor     dl, dl
0x18002bf50  mov     r14d, r9d
0x18002bf53  mov     rbp, r8
0x18002bf56  mov     rdi, rcx
0x18002bf59  lea     r8, [rcx+298h]
0x18002bf60  mov     ecx, [rcx+10h]
0x18002bf63  call    PER_CPU_IISWPSiteCounters___Create__lambda_66d6c8ed0ed2deee44b2b0fee89d5763___lambda_f6098c0808415f863707cccac41fba4f___
0x18002bf68  mov     ebx, eax
0x18002bf6a  test    eax, eax
0x18002bf6c  js      loc_18002C0C8
0x18002bf72  lea     rcx, [rdi+18h]
0x18002bf76  mov     rdx, rsi
0x18002bf79  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002bf7f  mov     ebx, eax
0x18002bf81  test    eax, eax
0x18002bf83  js      loc_18002C0C8
0x18002bf89  lea     rcx, [rdi+90h]
0x18002bf90  mov     rdx, rbp
0x18002bf93  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002bf99  mov     ebx, eax
0x18002bf9b  test    eax, eax
0x18002bf9d  js      loc_18002C0C8
0x18002bfa3  mov     rax, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18002bfaa  lea     rdx, [rsp+78h+var_28]
0x18002bfaf  mov     [rdi+14h], r14d
0x18002bfb3  mov     rcx, [rax+5D8h]
0x18002bfba  mov     rax, [rcx]
0x18002bfbd  mov     rax, [rax+38h]
0x18002bfc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bfc6  mov     ebx, eax
0x18002bfc8  test    eax, eax
0x18002bfca  js      loc_18002C0C8
0x18002bfd0  add     rdi, 108h
0x18002bfd7  mov     rcx, rdi
0x18002bfda  call    cs:__imp_?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ; STRU::QueryBuffer(void)
0x18002bfe0  mov     rcx, rax
0x18002bfe3  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18002bfe9  mov     [rsp+78h+arg_0], eax
0x18002bff0  mov     rax, [rsp+78h+var_28]
0x18002bff5  mov     rcx, [rax]
0x18002bff8  mov     rbx, [rcx+28h]
0x18002bffc  mov     rcx, rdi
0x18002bfff  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002c005  mov     [rsp+78h+var_40], 0
0x18002c00e  lea     rcx, [rsp+78h+arg_0]
0x18002c016  mov     [rsp+78h+var_48], 0
0x18002c01f  lea     r8, asc_180039BB8; "/"
0x18002c026  mov     r9, rax
0x18002c029  mov     [rsp+78h+var_50], 0
0x18002c032  mov     [rsp+78h+var_58], rcx
0x18002c037  mov     rdx, rsi
0x18002c03a  mov     rcx, [rsp+78h+var_28]
0x18002c03f  mov     rax, rbx
0x18002c042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c047  mov     ebx, eax
0x18002c049  cmp     eax, 8007007Ah
0x18002c04e  jnz     short loc_18002C0BF
0x18002c050  mov     edx, [rsp+78h+arg_0]
0x18002c057  mov     rcx, rdi
0x18002c05a  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x18002c060  mov     ebx, eax
0x18002c062  test    eax, eax
0x18002c064  js      short loc_18002C0C8
0x18002c066  mov     rax, [rsp+78h+var_28]
0x18002c06b  mov     rcx, [rax]
0x18002c06e  mov     rbx, [rcx+28h]
0x18002c072  mov     rcx, rdi
0x18002c075  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002c07b  mov     [rsp+78h+var_40], 0
0x18002c084  lea     rcx, [rsp+78h+arg_0]
0x18002c08c  mov     [rsp+78h+var_48], 0
0x18002c095  lea     r8, asc_180039BB8; "/"
0x18002c09c  mov     r9, rax
0x18002c09f  mov     [rsp+78h+var_50], 0
0x18002c0a8  mov     [rsp+78h+var_58], rcx
0x18002c0ad  mov     rdx, rsi
0x18002c0b0  mov     rcx, [rsp+78h+var_28]
0x18002c0b5  mov     rax, rbx
0x18002c0b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c0bd  mov     ebx, eax
0x18002c0bf  mov     rcx, rdi
0x18002c0c2  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x18002c0c8  mov     rcx, [rsp+78h+var_28]
0x18002c0cd  test    rcx, rcx
0x18002c0d0  jz      short loc_18002C0DE
0x18002c0d2  mov     rax, [rcx]
0x18002c0d5  mov     rax, [rax+10h]
0x18002c0d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c0de  lea     r11, [rsp+78h+var_18]
0x18002c0e3  mov     eax, ebx
0x18002c0e5  mov     rbx, [r11+28h]
0x18002c0e9  mov     rbp, [r11+30h]
0x18002c0ed  mov     rsp, r11
0x18002c0f0  pop     r14
0x18002c0f2  pop     rdi
0x18002c0f3  pop     rsi
0x18002c0f4  retn
```
