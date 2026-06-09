# CUserProfileRoamingProvider::_IsRoaming(int *)

- ea: `0x180009dfc`
- end: `0x180009f32`
- name: `?_IsRoaming@CUserProfileRoamingProvider@@AEAAJPEAH@Z`
- size: `310`
- prototype: `__int64 __fastcall(CUserProfileRoamingProvider *__hidden this, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800159b0`

## callees

- `0x180009dfc`
- `0x180009f38`
- `0x18000fca8`
- `0x180020010`

## string_xrefs

- `0x180009ef0`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`

## pseudocode

```c
__int64 __fastcall CUserProfileRoamingProvider::_IsRoaming(CUserProfileRoamingProvider *this, int *a2)
{
  __int64 v3; // rcx
  const unsigned __int16 *v5; // rax
  int v6; // eax
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = *((_QWORD *)this + 1);
  *a2 = 0;
  if ( *(_WORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 80LL))(v3)
    && (((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1)) & 0x10) != 0
     || ((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1)) & 8) != 0)
    && ((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1)) & 0x800) == 0
    && ((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1)) & 0x400) == 0
    && (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 120LL))(*((_QWORD *)this + 1))
    && ((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1)) & 0x10000) == 0
    && ((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1)) & 1) == 0 )
  {
    v5 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 80LL))(*((_QWORD *)this + 1));
    v6 = CUserProfileRoamingProvider::_CheckRupSlowLink(this, v5);
    if ( v6 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xB63,
        (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
        (const char *)(unsigned int)v6,
        v8);
    if ( ((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1)) & 0x400) == 0 )
      *a2 = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180009dfc  mov     [rsp+arg_0], rbx
0x180009e01  mov     [rsp+arg_8], rsi
0x180009e06  push    rdi; int
0x180009e07  sub     rsp, 20h
0x180009e0b  mov     rbx, rcx
0x180009e0e  xor     esi, esi
0x180009e10  mov     rcx, [rcx+8]
0x180009e14  mov     rdi, rdx
0x180009e17  mov     [rdx], esi
0x180009e19  mov     rax, [rcx]
0x180009e1c  mov     rax, [rax+50h]
0x180009e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e25  cmp     [rax], si
0x180009e28  jz      loc_180009F20
0x180009e2e  mov     rcx, [rbx+8]
0x180009e32  mov     rax, [rcx]
0x180009e35  mov     rax, [rax+10h]
0x180009e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e3e  test    al, 10h
0x180009e40  jnz     short loc_180009E5A
0x180009e42  mov     rcx, [rbx+8]
0x180009e46  mov     rax, [rcx]
0x180009e49  mov     rax, [rax+10h]
0x180009e4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e52  test    al, 8
0x180009e54  jz      loc_180009F20
0x180009e5a  mov     rcx, [rbx+8]
0x180009e5e  mov     rax, [rcx]
0x180009e61  mov     rax, [rax+10h]
0x180009e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e6a  bt      eax, 0Bh
0x180009e6e  jb      loc_180009F20
0x180009e74  mov     rcx, [rbx+8]
0x180009e78  mov     rax, [rcx]
0x180009e7b  mov     rax, [rax+10h]
0x180009e7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e84  bt      eax, 0Ah
0x180009e88  jb      loc_180009F20
0x180009e8e  mov     rcx, [rbx+8]
0x180009e92  mov     rax, [rcx]
0x180009e95  mov     rax, [rax+78h]
0x180009e99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e9e  test    eax, eax
0x180009ea0  jz      short loc_180009F20
0x180009ea2  mov     rcx, [rbx+8]
0x180009ea6  mov     rax, [rcx]
0x180009ea9  mov     rax, [rax+10h]
0x180009ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009eb2  bt      eax, 10h
0x180009eb6  jb      short loc_180009F20
0x180009eb8  mov     rcx, [rbx+8]
0x180009ebc  mov     rax, [rcx]
0x180009ebf  mov     rax, [rax+10h]
0x180009ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ec8  test    al, 1
0x180009eca  jnz     short loc_180009F20
0x180009ecc  mov     rcx, [rbx+8]
0x180009ed0  mov     rax, [rcx]
0x180009ed3  mov     rax, [rax+50h]
0x180009ed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009edc  mov     rdx, rax; unsigned __int16 *
0x180009edf  mov     rcx, rbx; this
0x180009ee2  call    ?_CheckRupSlowLink@CUserProfileRoamingProvider@@AEAAJPEBG@Z; CUserProfileRoamingProvider::_CheckRupSlowLink(ushort const *)
0x180009ee7  test    eax, eax
0x180009ee9  jns     short loc_180009F04
0x180009eeb  mov     rcx, [rsp+28h]; this
0x180009ef0  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180009ef7  mov     r9d, eax; char *
0x180009efa  mov     edx, 0B63h; void *
0x180009eff  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180009f04  mov     rcx, [rbx+8]
0x180009f08  mov     rax, [rcx]
0x180009f0b  mov     rax, [rax+10h]
0x180009f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f14  bt      eax, 0Ah
0x180009f18  jb      short loc_180009F20
0x180009f1a  mov     dword ptr [rdi], 1
0x180009f20  mov     rbx, [rsp+28h+arg_0]
0x180009f25  xor     eax, eax
0x180009f27  mov     rsi, [rsp+28h+arg_8]
0x180009f2c  add     rsp, 20h
0x180009f30  pop     rdi
0x180009f31  retn
```
