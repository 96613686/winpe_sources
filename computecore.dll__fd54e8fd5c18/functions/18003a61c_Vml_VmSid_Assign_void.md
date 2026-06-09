# Vml::VmSid::Assign(void *)

- ea: `0x18003a61c`
- end: `0x18003a6ea`
- name: `?Assign@VmSid@Vml@@QEAAXPEAX@Z`
- size: `206`
- prototype: `void(Vml::VmSid *__hidden this, void *)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18003ae9c`
- `0x18003b0dc`
- `0x18003ba60`
- `0x18003bc98`

## callees

- `0x18001017c`
- `0x18003a61c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a679`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a679`
- `KERNELBASE!LocalAlloc` at `0x18003a643`
- `KERNELBASE!LocalAlloc` at `0x18003a643`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003a636`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003a636`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003a65f`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003a65f`

## string_xrefs

- `0x18003a6c5`: `onecore\vm\common\vml\VmSecurity.h`
- `0x18003a6d7`: `onecore\vm\common\vml\VmSecurity.h`

## pseudocode

```c
void __fastcall Vml::VmSid::Assign(Vml::VmSid *this, void *a2)
{
  HLOCAL v4; // rdi
  DWORD LengthSid; // r14d
  HLOCAL v6; // rax
  const char *v7; // r9
  const char *v8; // r9
  void *v9; // rcx
  _QWORD *v10; // rcx
  _QWORD *v11; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HLOCAL v13; // [rsp+58h] [rbp+10h]

  v4 = 0;
  if ( a2 )
  {
    LengthSid = GetLengthSid(a2);
    v6 = LocalAlloc(0, LengthSid);
    v4 = v6;
    if ( !v6 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1540,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
        v7);
    if ( !CopySid(LengthSid, v6, a2) )
    {
      try
      {
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x1545,
          (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
          v8);
      }
      catch ( ... )
      {
        LocalFree(v13);
        throw;
      }
    }
  }
  v9 = *(void **)this;
  *(_QWORD *)this = v4;
  if ( v9 )
    LocalFree(v9);
  *((_DWORD *)this + 2) = 7;
  v10 = (_QWORD *)((char *)this + 48);
  *((_QWORD *)this + 8) = 0;
  if ( *((_QWORD *)this + 9) > 7u )
    v10 = (_QWORD *)*v10;
  *(_WORD *)v10 = 0;
  v11 = (_QWORD *)((char *)this + 16);
  *((_QWORD *)this + 4) = 0;
  if ( *((_QWORD *)this + 5) > 7u )
    v11 = (_QWORD *)*v11;
  *(_WORD *)v11 = 0;
}

```

## disassembly

```asm
0x18003a61c  push    rbx
0x18003a61e  push    rsi
0x18003a61f  push    rdi
0x18003a620  push    r14
0x18003a622  sub     rsp, 28h
0x18003a626  mov     rsi, rdx
0x18003a629  mov     rbx, rcx
0x18003a62c  xor     edi, edi
0x18003a62e  test    rdx, rdx
0x18003a631  jz      short loc_18003A66E
0x18003a633  mov     rcx, rdx; pSid
0x18003a636  call    cs:__imp_GetLengthSid
0x18003a63c  mov     r14d, eax
0x18003a63f  mov     edx, eax; uBytes
0x18003a641  xor     ecx, ecx; uFlags
0x18003a643  call    cs:__imp_LocalAlloc
0x18003a649  mov     rdi, rax
0x18003a64c  mov     [rsp+48h+arg_8], rax
0x18003a651  test    rax, rax
0x18003a654  jz      short loc_18003A6C0
0x18003a656  mov     r8, rsi; pSourceSid
0x18003a659  mov     rdx, rax; pDestinationSid
0x18003a65c  mov     ecx, r14d; nDestinationSidLength
0x18003a65f  call    cs:__imp_CopySid
0x18003a665  mov     rcx, [rsp+48h]; this
0x18003a66a  test    eax, eax
0x18003a66c  jz      short loc_18003A6D7
0x18003a66e  mov     rcx, [rbx]; hMem
0x18003a671  mov     [rbx], rdi
0x18003a674  test    rcx, rcx
0x18003a677  jz      short loc_18003A67F
0x18003a679  call    cs:__imp_LocalFree
0x18003a67f  mov     dword ptr [rbx+8], 7
0x18003a686  lea     rcx, [rbx+30h]
0x18003a68a  mov     qword ptr [rcx+10h], 0
0x18003a692  cmp     qword ptr [rcx+18h], 7
0x18003a697  jbe     short loc_18003A69C
0x18003a699  mov     rcx, [rcx]
0x18003a69c  xor     eax, eax
0x18003a69e  mov     [rcx], ax
0x18003a6a1  lea     rcx, [rbx+10h]
0x18003a6a5  mov     [rcx+10h], rax
0x18003a6a9  cmp     qword ptr [rcx+18h], 7
0x18003a6ae  jbe     short loc_18003A6B3
0x18003a6b0  mov     rcx, [rcx]
0x18003a6b3  mov     [rcx], ax
0x18003a6b6  add     rsp, 28h
0x18003a6ba  pop     r14
0x18003a6bc  pop     rdi
0x18003a6bd  pop     rsi
0x18003a6be  pop     rbx
0x18003a6bf  retn
0x18003a6c0  mov     rcx, [rsp+48h]; this
0x18003a6c5  lea     r8, aOnecoreVmCommo_31; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x18003a6cc  mov     edx, 1540h; void *
0x18003a6d1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18003a6d7  lea     r8, aOnecoreVmCommo_31; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x18003a6de  mov     edx, 1545h; void *
0x18003a6e3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
