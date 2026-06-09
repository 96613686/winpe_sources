# LDAP_CONN::LDAP_CONN(void)

- ea: `0x1803508a0`
- end: `0x1803509d1`
- name: `??0LDAP_CONN@@QEAA@XZ`
- size: `305`
- prototype: `LDAP_CONN *__fastcall(LDAP_CONN *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180350d98`

## callees

- `0x1803508a0`
- `0x18035a98c`
- `0x18035eb68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1803508ed`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18035090c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180350934`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18035095c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18035098a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1803508ed`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18035090c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180350934`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18035095c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18035098a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18035091c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180350944`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18035096c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180350975`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18035099a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1803509a3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1803509ac`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18035091c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180350944`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18035096c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180350975`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18035099a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1803509a3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1803509ac`

## pseudocode

```c
LDAP_CONN *__fastcall LDAP_CONN::LDAP_CONN(LDAP_CONN *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rcx

  LDAP_REQUEST::LDAP_REQUEST((LDAP_CONN *)((char *)this + 216));
  LDAP_CONN::Reset(this);
  *((_QWORD *)this + 6) = (char *)this + 40;
  *((_QWORD *)this + 5) = (char *)this + 40;
  *((_QWORD *)this + 4) = (char *)this + 24;
  *((_QWORD *)this + 3) = (char *)this + 24;
  if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)this + 54, 0x190u) )
  {
    if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 144), 0x190u) )
    {
      if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)this + 55, 0x190u) )
      {
        if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)this + 56, 0x190u) )
        {
          if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 1752), 0x190u) )
          {
            *((_DWORD *)this + 114) &= ~2u;
            return this;
          }
          *((_DWORD *)this + 2) = 0;
          DeleteCriticalSection((LPCRITICAL_SECTION)this + 54);
          DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
          DeleteCriticalSection((LPCRITICAL_SECTION)this + 55);
          v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 2240);
        }
        else
        {
          *((_DWORD *)this + 2) = 0;
          DeleteCriticalSection((LPCRITICAL_SECTION)this + 54);
          DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
          v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 2200);
        }
      }
      else
      {
        *((_DWORD *)this + 2) = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)this + 54);
        v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 144);
      }
    }
    else
    {
      *((_DWORD *)this + 2) = 0;
      v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 2160);
    }
    DeleteCriticalSection(v2);
  }
  else
  {
    *((_DWORD *)this + 2) = 0;
  }
  return this;
}

```

## disassembly

```asm
0x1803508a0  push    rbx
0x1803508a2  push    rbp
0x1803508a3  push    rsi
0x1803508a4  push    rdi
0x1803508a5  push    r12
0x1803508a7  push    r14
0x1803508a9  sub     rsp, 28h
0x1803508ad  mov     rbx, rcx
0x1803508b0  add     rcx, 0D8h; this
0x1803508b7  call    ??0LDAP_REQUEST@@QEAA@XZ; LDAP_REQUEST::LDAP_REQUEST(void)
0x1803508bc  mov     rcx, rbx; this
0x1803508bf  call    ?Reset@LDAP_CONN@@QEAAXXZ; LDAP_CONN::Reset(void)
0x1803508c4  lea     rax, [rbx+28h]
0x1803508c8  mov     r12d, 190h
0x1803508ce  mov     [rax+8], rax
0x1803508d2  lea     rdi, [rbx+870h]
0x1803508d9  mov     [rax], rax
0x1803508dc  mov     edx, r12d; dwSpinCount
0x1803508df  lea     rax, [rbx+18h]
0x1803508e3  mov     rcx, rdi; lpCriticalSection
0x1803508e6  mov     [rax+8], rax
0x1803508ea  mov     [rax], rax
0x1803508ed  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1803508f3  test    eax, eax
0x1803508f5  jnz     short loc_1803508FF
0x1803508f7  mov     [rbx+8], eax
0x1803508fa  jmp     loc_1803509C1
0x1803508ff  lea     rsi, [rbx+90h]
0x180350906  mov     edx, r12d; dwSpinCount
0x180350909  mov     rcx, rsi; lpCriticalSection
0x18035090c  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180350912  test    eax, eax
0x180350914  jnz     short loc_180350927
0x180350916  mov     [rbx+8], eax
0x180350919  mov     rcx, rdi; lpCriticalSection
0x18035091c  call    cs:__imp_DeleteCriticalSection
0x180350922  jmp     loc_1803509C1
0x180350927  lea     rbp, [rbx+898h]
0x18035092e  mov     edx, r12d; dwSpinCount
0x180350931  mov     rcx, rbp; lpCriticalSection
0x180350934  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18035093a  test    eax, eax
0x18035093c  jnz     short loc_18035094F
0x18035093e  mov     rcx, rdi; lpCriticalSection
0x180350941  mov     [rbx+8], eax
0x180350944  call    cs:__imp_DeleteCriticalSection
0x18035094a  mov     rcx, rsi
0x18035094d  jmp     short loc_18035091C
0x18035094f  lea     r14, [rbx+8C0h]
0x180350956  mov     edx, r12d; dwSpinCount
0x180350959  mov     rcx, r14; lpCriticalSection
0x18035095c  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180350962  test    eax, eax
0x180350964  jnz     short loc_180350980
0x180350966  mov     rcx, rdi; lpCriticalSection
0x180350969  mov     [rbx+8], eax
0x18035096c  call    cs:__imp_DeleteCriticalSection
0x180350972  mov     rcx, rsi; lpCriticalSection
0x180350975  call    cs:__imp_DeleteCriticalSection
0x18035097b  mov     rcx, rbp
0x18035097e  jmp     short loc_18035091C
0x180350980  lea     rcx, [rbx+6D8h]; lpCriticalSection
0x180350987  mov     edx, r12d; dwSpinCount
0x18035098a  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180350990  test    eax, eax
0x180350992  jnz     short loc_1803509BA
0x180350994  mov     rcx, rdi; lpCriticalSection
0x180350997  mov     [rbx+8], eax
0x18035099a  call    cs:__imp_DeleteCriticalSection
0x1803509a0  mov     rcx, rsi; lpCriticalSection
0x1803509a3  call    cs:__imp_DeleteCriticalSection
0x1803509a9  mov     rcx, rbp; lpCriticalSection
0x1803509ac  call    cs:__imp_DeleteCriticalSection
0x1803509b2  mov     rcx, r14
0x1803509b5  jmp     loc_18035091C
0x1803509ba  and     dword ptr [rbx+1C8h], 0FFFFFFFDh
0x1803509c1  mov     rax, rbx
0x1803509c4  add     rsp, 28h
0x1803509c8  pop     r14
0x1803509ca  pop     r12
0x1803509cc  pop     rdi
0x1803509cd  pop     rsi
0x1803509ce  pop     rbp
0x1803509cf  pop     rbx
0x1803509d0  retn
```
