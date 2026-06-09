# CLdapStore::OpenStore(char const *,ulong,unsigned __int64,ulong,void const *,void *,_CERT_STORE_PROV_INFO *)

- ea: `0x18001d698`
- end: `0x18001d8ce`
- name: `?OpenStore@CLdapStore@@QEAAHPEBDK_KKPEBXPEAXPEAU_CERT_STORE_PROV_INFO@@@Z`
- size: `566`
- prototype: `__int64 __fastcall(CLdapStore *this, const char *, __int64, __int64, unsigned int, const unsigned __int16 *, void *, struct _CERT_STORE_PROV_INFO *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001d4f0`

## callees

- `0x180010ed8`
- `0x180012b4c`
- `0x180019b00`
- `0x18001ac64`
- `0x18001d04c`
- `0x18001d0d8`
- `0x18001d22c`
- `0x18001d698`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d7af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d8a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d8b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d7af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d8a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d8b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d811`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d811`

## pseudocode

```c
__int64 __fastcall CLdapStore::OpenStore(
        CLdapStore *this,
        const char *a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        const unsigned __int16 *a6,
        void *a7,
        struct _CERT_STORE_PROV_INFO *a8)
{
  const unsigned __int16 *v9; // rdx
  unsigned int v10; // r15d
  unsigned int Bindings; // ebx
  __int64 result; // rax
  unsigned int v13; // edx
  int v14; // r13d
  _QWORD *v15; // rax

  *((_DWORD *)this + 28) = a5;
  *((_QWORD *)this + 13) = a7;
  v9 = a6;
  if ( !a6 || (v10 = a5 & 0x40000, (a5 & 0x20) != 0) && v10 )
  {
    SetLastError(0x80070057);
    return 0;
  }
  else
  {
    if ( v10 )
    {
      *((_DWORD *)this + 28) = a5 & 0xFFF7FFFF;
      *((_QWORD *)this + 12) = *(_QWORD *)a6;
      v9 = (const unsigned __int16 *)*((_QWORD *)a6 + 1);
    }
    else
    {
      *((_DWORD *)this + 28) = a5 | 0x80000;
    }
    Bindings = 1;
    result = LdapCrackUrl(1u, v9, (__int64)this + 40);
    if ( (_DWORD)result )
    {
      v13 = 0x10000;
      v14 = (a5 & 0x10000) != 0 ? 1 : 3;
      if ( (a5 & 0x20000) != 0 )
        v14 = 1;
      v15 = (_QWORD *)((char *)this + 96);
      if ( !v10 )
      {
        Bindings = LdapGetBindings(*((PWSTR *)this + 5), *((_DWORD *)this + 12), 15000, 0, (__int64)this + 96);
        v15 = (_QWORD *)((char *)this + 96);
      }
      if ( Bindings == 1 )
      {
        if ( (a5 & 0x8000) == 0 )
        {
          Bindings = LdapHasWriteAccess(*v15, (char *)this + 40);
          if ( !Bindings )
            SetLastError(5u);
        }
        if ( Bindings == 1 )
        {
          if ( (*((_BYTE *)this + 112) & 0x10) != 0 )
          {
            *((_DWORD *)this + 29) = 1;
            Bindings = CLdapStore::InternalCommit(this, 0);
            if ( Bindings == 1 )
            {
              a8->dwStoreProvFlags = 2;
              if ( (a5 & 0x80000) != 0 )
                *((_DWORD *)this + 28) |= 0x80000u;
            }
          }
          else
          {
            Bindings = CLdapStore::FillCacheStore(this, 0);
            if ( !Bindings && !v10 && v14 == 3 && GetLastError() == 234 )
            {
              LdapFreeBindings(*((_QWORD *)this + 12));
              *((_QWORD *)this + 12) = 0;
              Bindings = LdapGetBindings(*((PWSTR *)this + 5), *((_DWORD *)this + 12), 15000, 0, (__int64)this + 96);
              if ( Bindings )
                Bindings = CLdapStore::FillCacheStore(this, 0);
            }
            if ( Bindings == 1 )
            {
              a8->cStoreProvFunc = 14;
              a8->rgpvStoreProvFunc = (void **)&off_180028270;
              a8->hStoreProv = this;
              if ( (a5 & 0x80000) != 0 )
                *((_DWORD *)this + 28) |= 0x80000u;
              return Bindings;
            }
          }
        }
      }
      CLdapStore::CloseStore(this, v13);
      return Bindings;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001d698  push    rbx
0x18001d69a  push    rsi
0x18001d69b  push    rdi
0x18001d69c  push    r12
0x18001d69e  push    r13
0x18001d6a0  push    r14
0x18001d6a2  push    r15
0x18001d6a4  sub     rsp, 40h
0x18001d6a8  mov     rdi, rcx
0x18001d6ab  mov     esi, [rsp+78h+arg_20]
0x18001d6b2  mov     [rcx+70h], esi
0x18001d6b5  mov     rax, [rsp+78h+arg_30]
0x18001d6bd  mov     [rcx+68h], rax
0x18001d6c1  mov     rdx, [rsp+78h+arg_28]
0x18001d6c9  test    rdx, rdx
0x18001d6cc  jz      loc_18001D8B1
0x18001d6d2  mov     r15d, esi
0x18001d6d5  and     r15d, 40000h
0x18001d6dc  test    sil, 20h
0x18001d6e0  jz      short loc_18001D6EB
0x18001d6e2  test    r15d, r15d
0x18001d6e5  jnz     loc_18001D8B1
0x18001d6eb  mov     eax, esi
0x18001d6ed  mov     r14d, 80000h
0x18001d6f3  test    r15d, r15d
0x18001d6f6  jz      short loc_18001D70C
0x18001d6f8  btr     eax, 13h
0x18001d6fc  mov     [rcx+70h], eax
0x18001d6ff  mov     rax, [rdx]
0x18001d702  mov     [rcx+60h], rax
0x18001d706  mov     rdx, [rdx+8]
0x18001d70a  jmp     short loc_18001D712
0x18001d70c  or      eax, r14d
0x18001d70f  mov     [rcx+70h], eax
0x18001d712  lea     r8, [rcx+28h]
0x18001d716  mov     ebx, 1
0x18001d71b  mov     ecx, ebx
0x18001d71d  call    LdapCrackUrl
0x18001d722  test    eax, eax
0x18001d724  jz      loc_18001D8BE
0x18001d72a  mov     ecx, esi
0x18001d72c  mov     edx, 10000h
0x18001d731  and     ecx, edx
0x18001d733  mov     eax, ecx
0x18001d735  neg     eax
0x18001d737  sbb     r13d, r13d
0x18001d73a  and     r13d, 0FFFFFFFEh
0x18001d73e  add     r13d, 3
0x18001d742  neg     ecx
0x18001d744  sbb     r12d, r12d
0x18001d747  and     r12d, edx
0x18001d74a  bt      esi, 11h
0x18001d74e  jnb     short loc_18001D758
0x18001d750  bts     r12d, 12h
0x18001d755  mov     r13d, ebx
0x18001d758  lea     rax, [rdi+60h]
0x18001d75c  test    r15d, r15d
0x18001d75f  jnz     short loc_18001D78F
0x18001d761  mov     [rsp+78h+var_48], rax; __int64
0x18001d766  mov     [rsp+78h+var_50], 0; __int64
0x18001d76f  mov     [rsp+78h+var_58], 3A98h; int
0x18001d777  mov     r9d, r13d
0x18001d77a  mov     r8d, r12d
0x18001d77d  mov     edx, [rdi+30h]; PortNumber
0x18001d780  mov     rcx, [rdi+28h]; HostName
0x18001d784  call    LdapGetBindings
0x18001d789  mov     ebx, eax
0x18001d78b  lea     rax, [rdi+60h]
0x18001d78f  cmp     ebx, 1
0x18001d792  jnz     short loc_18001D7EC
0x18001d794  bt      esi, 0Fh
0x18001d798  jb      short loc_18001D7B5
0x18001d79a  lea     rdx, [rdi+28h]
0x18001d79e  mov     rcx, [rax]
0x18001d7a1  call    LdapHasWriteAccess
0x18001d7a6  mov     ebx, eax
0x18001d7a8  test    eax, eax
0x18001d7aa  jnz     short loc_18001D7B5
0x18001d7ac  lea     ecx, [rax+5]; dwErrCode
0x18001d7af  call    cs:__imp_SetLastError
0x18001d7b5  cmp     ebx, 1
0x18001d7b8  jnz     short loc_18001D7EC
0x18001d7ba  xor     edx, edx; int
0x18001d7bc  mov     rcx, rdi; this
0x18001d7bf  test    byte ptr [rdi+70h], 10h
0x18001d7c3  jz      short loc_18001D7FB
0x18001d7c5  mov     [rdi+74h], ebx
0x18001d7c8  call    ?InternalCommit@CLdapStore@@AEAAHK@Z; CLdapStore::InternalCommit(ulong)
0x18001d7cd  mov     ebx, eax
0x18001d7cf  cmp     eax, 1
0x18001d7d2  jnz     short loc_18001D7EC
0x18001d7d4  mov     rcx, [rsp+78h+arg_38]
0x18001d7dc  mov     dword ptr [rcx+18h], 2
0x18001d7e3  test    r14d, esi
0x18001d7e6  jz      short loc_18001D7EC
0x18001d7e8  or      [rdi+70h], r14d
0x18001d7ec  mov     rcx, rdi; this
0x18001d7ef  call    ?CloseStore@CLdapStore@@QEAAXK@Z; CLdapStore::CloseStore(ulong)
0x18001d7f4  mov     eax, ebx
0x18001d7f6  jmp     loc_18001D8BE
0x18001d7fb  call    ?FillCacheStore@CLdapStore@@AEAAHH@Z; CLdapStore::FillCacheStore(int)
0x18001d800  mov     ebx, eax
0x18001d802  test    eax, eax
0x18001d804  jnz     short loc_18001D86C
0x18001d806  test    r15d, r15d
0x18001d809  jnz     short loc_18001D86C
0x18001d80b  cmp     r13d, 3
0x18001d80f  jnz     short loc_18001D86C
0x18001d811  call    cs:__imp_GetLastError
0x18001d817  cmp     eax, 0EAh
0x18001d81c  jnz     short loc_18001D86C
0x18001d81e  lea     rbx, [rdi+60h]
0x18001d822  mov     rcx, [rbx]
0x18001d825  call    LdapFreeBindings
0x18001d82a  mov     qword ptr [rbx], 0
0x18001d831  mov     [rsp+78h+var_48], rbx; __int64
0x18001d836  mov     [rsp+78h+var_50], 0; __int64
0x18001d83f  mov     [rsp+78h+var_58], 3A98h; int
0x18001d847  lea     r9d, [r15+2]
0x18001d84b  mov     r8d, r12d
0x18001d84e  mov     edx, [rdi+30h]; PortNumber
0x18001d851  mov     rcx, [rdi+28h]; HostName
0x18001d855  call    LdapGetBindings
0x18001d85a  mov     ebx, eax
0x18001d85c  test    eax, eax
0x18001d85e  jz      short loc_18001D86C
0x18001d860  xor     edx, edx; int
0x18001d862  mov     rcx, rdi; this
0x18001d865  call    ?FillCacheStore@CLdapStore@@AEAAHH@Z; CLdapStore::FillCacheStore(int)
0x18001d86a  mov     ebx, eax
0x18001d86c  cmp     ebx, 1
0x18001d86f  jnz     loc_18001D7EC
0x18001d875  mov     rax, [rsp+78h+arg_38]
0x18001d87d  mov     dword ptr [rax+4], 0Eh
0x18001d884  lea     rcx, off_180028270
0x18001d88b  mov     [rax+8], rcx
0x18001d88f  mov     [rax+10h], rdi
0x18001d893  test    r14d, esi
0x18001d896  jz      loc_18001D7F4
0x18001d89c  or      [rdi+70h], r14d
0x18001d8a0  jmp     loc_18001D7F4
0x18001d8a5  mov     ecx, eax; dwErrCode
0x18001d8a7  call    cs:__imp_SetLastError
0x18001d8ad  xor     eax, eax
0x18001d8af  jmp     short loc_18001D8BE
0x18001d8b1  mov     ecx, 80070057h; dwErrCode
0x18001d8b6  call    cs:__imp_SetLastError
0x18001d8bc  xor     eax, eax
0x18001d8be  add     rsp, 40h
0x18001d8c2  pop     r15
0x18001d8c4  pop     r14
0x18001d8c6  pop     r13
0x18001d8c8  pop     r12
0x18001d8ca  pop     rdi
0x18001d8cb  pop     rsi
0x18001d8cc  pop     rbx
0x18001d8cd  retn
```
