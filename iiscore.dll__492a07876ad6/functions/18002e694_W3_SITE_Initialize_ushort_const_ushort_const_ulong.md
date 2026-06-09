# W3_SITE::Initialize(ushort const *,ushort const *,ulong)

- ea: `0x18002e694`
- end: `0x18002e88a`
- name: `?Initialize@W3_SITE@@QEAAJPEBG0K@Z`
- size: `502`
- prototype: `__int64 __fastcall(W3_SITE *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800096a0`

## callees

- `0x18002e034`
- `0x18002e694`
- `0x180038010`

## import_xrefs

- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18002e759`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18002e759`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002e77b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002e7fd`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002e77b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002e7fd`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x18002e7dc`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x18002e7dc`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18002e850`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18002e850`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002e6dd`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002e6fd`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002e6dd`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002e6fd`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x18002e74a`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x18002e74a`

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
0x18002e694  mov     [rsp+arg_8], rbx
0x18002e699  mov     [rsp+arg_10], rbp
0x18002e69e  push    rsi
0x18002e69f  push    rdi
0x18002e6a0  push    r14
0x18002e6a2  sub     rsp, 60h
0x18002e6a6  mov     rsi, rdx
0x18002e6a9  mov     [rsp+78h+var_28], 0
0x18002e6b2  xor     dl, dl
0x18002e6b4  mov     r14d, r9d
0x18002e6b7  mov     rbp, r8
0x18002e6ba  mov     rdi, rcx
0x18002e6bd  lea     r8, [rcx+298h]
0x18002e6c4  mov     ecx, [rcx+10h]
0x18002e6c7  call    PER_CPU_IISWPSiteCounters___Create__lambda_66d6c8ed0ed2deee44b2b0fee89d5763___lambda_f6098c0808415f863707cccac41fba4f___
0x18002e6cc  mov     ebx, eax
0x18002e6ce  test    eax, eax
0x18002e6d0  js      loc_18002E85C
0x18002e6d6  lea     rcx, [rdi+18h]
0x18002e6da  mov     rdx, rsi
0x18002e6dd  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002e6e4  nop     dword ptr [rax+rax+00h]
0x18002e6e9  mov     ebx, eax
0x18002e6eb  test    eax, eax
0x18002e6ed  js      loc_18002E85C
0x18002e6f3  lea     rcx, [rdi+90h]
0x18002e6fa  mov     rdx, rbp
0x18002e6fd  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002e704  nop     dword ptr [rax+rax+00h]
0x18002e709  mov     ebx, eax
0x18002e70b  test    eax, eax
0x18002e70d  js      loc_18002E85C
0x18002e713  mov     rax, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18002e71a  lea     rdx, [rsp+78h+var_28]
0x18002e71f  mov     [rdi+14h], r14d
0x18002e723  mov     rcx, [rax+5D8h]
0x18002e72a  mov     rax, [rcx]
0x18002e72d  mov     rax, [rax+38h]
0x18002e731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e736  mov     ebx, eax
0x18002e738  test    eax, eax
0x18002e73a  js      loc_18002E85C
0x18002e740  add     rdi, 108h
0x18002e747  mov     rcx, rdi
0x18002e74a  call    cs:__imp_?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ; STRU::QueryBuffer(void)
0x18002e751  nop     dword ptr [rax+rax+00h]
0x18002e756  mov     rcx, rax
0x18002e759  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18002e760  nop     dword ptr [rax+rax+00h]
0x18002e765  mov     [rsp+78h+arg_0], eax
0x18002e76c  mov     rax, [rsp+78h+var_28]
0x18002e771  mov     rcx, [rax]
0x18002e774  mov     rbx, [rcx+28h]
0x18002e778  mov     rcx, rdi
0x18002e77b  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002e782  nop     dword ptr [rax+rax+00h]
0x18002e787  mov     [rsp+78h+var_40], 0
0x18002e790  lea     rcx, [rsp+78h+arg_0]
0x18002e798  mov     [rsp+78h+var_48], 0
0x18002e7a1  lea     r8, asc_18003CBB8; "/"
0x18002e7a8  mov     r9, rax
0x18002e7ab  mov     [rsp+78h+var_50], 0
0x18002e7b4  mov     [rsp+78h+var_58], rcx
0x18002e7b9  mov     rdx, rsi
0x18002e7bc  mov     rcx, [rsp+78h+var_28]
0x18002e7c1  mov     rax, rbx
0x18002e7c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e7c9  mov     ebx, eax
0x18002e7cb  cmp     eax, 8007007Ah
0x18002e7d0  jnz     short loc_18002E84D
0x18002e7d2  mov     edx, [rsp+78h+arg_0]
0x18002e7d9  mov     rcx, rdi
0x18002e7dc  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x18002e7e3  nop     dword ptr [rax+rax+00h]
0x18002e7e8  mov     ebx, eax
0x18002e7ea  test    eax, eax
0x18002e7ec  js      short loc_18002E85C
0x18002e7ee  mov     rax, [rsp+78h+var_28]
0x18002e7f3  mov     rcx, [rax]
0x18002e7f6  mov     rbx, [rcx+28h]
0x18002e7fa  mov     rcx, rdi
0x18002e7fd  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002e804  nop     dword ptr [rax+rax+00h]
0x18002e809  mov     [rsp+78h+var_40], 0
0x18002e812  lea     rcx, [rsp+78h+arg_0]
0x18002e81a  mov     [rsp+78h+var_48], 0
0x18002e823  lea     r8, asc_18003CBB8; "/"
0x18002e82a  mov     r9, rax
0x18002e82d  mov     [rsp+78h+var_50], 0
0x18002e836  mov     [rsp+78h+var_58], rcx
0x18002e83b  mov     rdx, rsi
0x18002e83e  mov     rcx, [rsp+78h+var_28]
0x18002e843  mov     rax, rbx
0x18002e846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e84b  mov     ebx, eax
0x18002e84d  mov     rcx, rdi
0x18002e850  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x18002e857  nop     dword ptr [rax+rax+00h]
0x18002e85c  mov     rcx, [rsp+78h+var_28]
0x18002e861  test    rcx, rcx
0x18002e864  jz      short loc_18002E872
0x18002e866  mov     rax, [rcx]
0x18002e869  mov     rax, [rax+10h]
0x18002e86d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e872  lea     r11, [rsp+78h+var_18]
0x18002e877  mov     eax, ebx
0x18002e879  mov     rbx, [r11+28h]
0x18002e87d  mov     rbp, [r11+30h]
0x18002e881  mov     rsp, r11
0x18002e884  pop     r14
0x18002e886  pop     rdi
0x18002e887  pop     rsi
0x18002e888  retn
```
