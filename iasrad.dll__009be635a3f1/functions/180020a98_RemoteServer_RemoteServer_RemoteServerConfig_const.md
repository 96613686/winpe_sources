# RemoteServer::RemoteServer(RemoteServerConfig const &)

- ea: `0x180020a98`
- end: `0x180020c00`
- name: `??0RemoteServer@@QEAA@AEBURemoteServerConfig@@@Z`
- size: `360`
- prototype: `RemoteServer *__fastcall(RemoteServer *__hidden this, const struct RemoteServerConfig *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001d4d0`

## callees

- `0x18000e470`
- `0x180020744`
- `0x180020a00`
- `0x180020a98`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180020b02`
- `msvcrt!wcscpy_s` at `0x180020b3f`
- `msvcrt!wcscpy_s` at `0x180020b02`
- `msvcrt!wcscpy_s` at `0x180020b3f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
RemoteServer *__fastcall RemoteServer::RemoteServer(RemoteServer *this, const struct RemoteServerConfig *a2)
{
  const wchar_t *v4; // rbp
  __int64 v5; // rbx
  unsigned __int64 v6; // rbx
  wchar_t *v7; // rax
  const wchar_t *v8; // rbp
  __int64 v9; // rbx
  unsigned __int64 v10; // rbx
  wchar_t *v11; // rax

  *(_QWORD *)this = &RemoteServer::`vftable';
  *((_DWORD *)this + 2) = 0;
  *(_OWORD *)((char *)this + 12) = *(_OWORD *)a2;
  v4 = (const wchar_t *)*((_QWORD *)a2 + 4);
  v5 = -1;
  do
    ++v5;
  while ( v4[v5] );
  v6 = v5 + 1;
  v7 = (wchar_t *)operator new(saturated_mul(v6, 2u));
  *((_QWORD *)this + 4) = v7;
  wcscpy_s(v7, v6, v4);
  v8 = (const wchar_t *)*((_QWORD *)a2 + 3);
  v9 = -1;
  do
    ++v9;
  while ( v8[v9] );
  v10 = v9 + 1;
  v11 = (wchar_t *)operator new(saturated_mul(v10, 2u));
  *((_QWORD *)this + 5) = v11;
  wcscpy_s(v11, v10, v8);
  RemotePort::RemotePort(
    (RemoteServer *)((char *)this + 48),
    *((struct sockaddr **)a2 + 2),
    *((_WORD *)a2 + 20),
    *((const char **)a2 + 6));
  RemotePort::RemotePort(
    (RemoteServer *)((char *)this + 200),
    *((struct sockaddr **)a2 + 2),
    *((_WORD *)a2 + 21),
    *((const char **)a2 + 7));
  *((_DWORD *)this + 88) = *((_DWORD *)a2 + 16);
  *((_DWORD *)this + 89) = *((_DWORD *)a2 + 17);
  *((_DWORD *)this + 90) = *((_DWORD *)a2 + 18);
  *((_DWORD *)this + 91) = *((_DWORD *)a2 + 19);
  *((_DWORD *)this + 92) = *((_DWORD *)a2 + 20);
  *((_BYTE *)this + 372) = *((_BYTE *)a2 + 84);
  *((_DWORD *)this + 94) = *((_DWORD *)a2 + 22);
  *((_BYTE *)this + 380) = *((_BYTE *)a2 + 85);
  CriticalSection::CriticalSection((RemoteServer *)((char *)this + 384));
  *((_WORD *)this + 212) = 1;
  *((_DWORD *)this + 107) = 0;
  *((_QWORD *)this + 54) = 0;
  *((_QWORD *)this + 55) = 0;
  *((_DWORD *)this + 112) = 0;
  return this;
}

```

## disassembly

```asm
0x180020a98  mov     [rsp+arg_0], rcx
0x180020a9d  push    rbx
0x180020a9e  push    rbp
0x180020a9f  push    rsi
0x180020aa0  push    rdi
0x180020aa1  push    r14
0x180020aa3  push    r15
0x180020aa5  sub     rsp, 28h
0x180020aa9  mov     rsi, rdx
0x180020aac  mov     rdi, rcx
0x180020aaf  lea     rax, ??_7RemoteServer@@6B@; const RemoteServer::`vftable'
0x180020ab6  mov     [rcx], rax
0x180020ab9  xor     r14d, r14d
0x180020abc  mov     [rcx+8], r14d
0x180020ac0  movups  xmm0, xmmword ptr [rdx]
0x180020ac3  movdqu  xmmword ptr [rcx+0Ch], xmm0
0x180020ac8  mov     rbp, [rdx+20h]
0x180020acc  or      r15, 0FFFFFFFFFFFFFFFFh
0x180020ad0  mov     rbx, r15
0x180020ad3  inc     rbx
0x180020ad6  cmp     [rbp+rbx*2+0], r14w
0x180020adc  jnz     short loc_180020AD3
0x180020ade  inc     rbx
0x180020ae1  mov     eax, 2
0x180020ae6  mul     rbx
0x180020ae9  cmovb   rax, r15
0x180020aed  mov     rcx, rax; Size
0x180020af0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020af5  mov     [rdi+20h], rax
0x180020af9  mov     r8, rbp; Source
0x180020afc  mov     rdx, rbx; SizeInWords
0x180020aff  mov     rcx, rax; Destination
0x180020b02  call    cs:__imp_wcscpy_s
0x180020b08  nop
0x180020b09  mov     rbp, [rsi+18h]
0x180020b0d  mov     rbx, r15
0x180020b10  inc     rbx
0x180020b13  cmp     [rbp+rbx*2+0], r14w
0x180020b19  jnz     short loc_180020B10
0x180020b1b  inc     rbx
0x180020b1e  mov     eax, 2
0x180020b23  mul     rbx
0x180020b26  cmovb   rax, r15
0x180020b2a  mov     rcx, rax; Size
0x180020b2d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020b32  mov     [rdi+28h], rax
0x180020b36  mov     r8, rbp; Source
0x180020b39  mov     rdx, rbx; SizeInWords
0x180020b3c  mov     rcx, rax; Destination
0x180020b3f  call    cs:__imp_wcscpy_s
0x180020b45  nop
0x180020b46  lea     rcx, [rdi+30h]; this
0x180020b4a  mov     r9, [rsi+30h]; char *
0x180020b4e  movzx   r8d, word ptr [rsi+28h]; unsigned __int16
0x180020b53  mov     rdx, [rsi+10h]; struct sockaddr *
0x180020b57  call    ??0RemotePort@@QEAA@PEAUsockaddr@@GPEBD@Z; RemotePort::RemotePort(sockaddr *,ushort,char const *)
0x180020b5c  nop
0x180020b5d  lea     rcx, [rdi+0C8h]; this
0x180020b64  mov     r9, [rsi+38h]; char *
0x180020b68  movzx   r8d, word ptr [rsi+2Ah]; unsigned __int16
0x180020b6d  mov     rdx, [rsi+10h]; struct sockaddr *
0x180020b71  call    ??0RemotePort@@QEAA@PEAUsockaddr@@GPEBD@Z; RemotePort::RemotePort(sockaddr *,ushort,char const *)
0x180020b76  nop
0x180020b77  mov     eax, [rsi+40h]
0x180020b7a  mov     [rdi+160h], eax
0x180020b80  mov     eax, [rsi+44h]
0x180020b83  mov     [rdi+164h], eax
0x180020b89  mov     eax, [rsi+48h]
0x180020b8c  mov     [rdi+168h], eax
0x180020b92  mov     eax, [rsi+4Ch]
0x180020b95  mov     [rdi+16Ch], eax
0x180020b9b  mov     eax, [rsi+50h]
0x180020b9e  mov     [rdi+170h], eax
0x180020ba4  mov     al, [rsi+54h]
0x180020ba7  mov     [rdi+174h], al
0x180020bad  mov     eax, [rsi+58h]
0x180020bb0  mov     [rdi+178h], eax
0x180020bb6  mov     al, [rsi+55h]
0x180020bb9  mov     [rdi+17Ch], al
0x180020bbf  lea     rcx, [rdi+180h]; this
0x180020bc6  call    ??0CriticalSection@@QEAA@XZ; CriticalSection::CriticalSection(void)
0x180020bcb  mov     word ptr [rdi+1A8h], 1
0x180020bd4  mov     [rdi+1ACh], r14d
0x180020bdb  mov     [rdi+1B0h], r14
0x180020be2  mov     [rdi+1B8h], r14
0x180020be9  mov     [rdi+1C0h], r14d
0x180020bf0  mov     rax, rdi
0x180020bf3  add     rsp, 28h
0x180020bf7  pop     r15
0x180020bf9  pop     r14
0x180020bfb  pop     rdi
0x180020bfc  pop     rsi
0x180020bfd  pop     rbp
0x180020bfe  pop     rbx
0x180020bff  retn
```
