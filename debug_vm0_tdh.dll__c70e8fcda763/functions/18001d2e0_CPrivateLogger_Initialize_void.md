# CPrivateLogger::Initialize(void)

- ea: `0x18001d2e0`
- end: `0x18001d438`
- name: `?Initialize@CPrivateLogger@@AEAAJXZ`
- size: `344`
- prototype: `__int64 __fastcall(CPrivateLogger *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180018a90`

## callees

- `0x180012f5c`
- `0x18001c7d0`
- `0x18001d2e0`
- `0x1800207c0`
- `0x180020c98`
- `0x180021490`
- `0x18003dfdc`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18001d3f7`
- `RPCRT4!UuidCreate` at `0x18001d3f7`

## pseudocode

```c
__int64 __fastcall CPrivateLogger::Initialize(CPrivateLogger *this)
{
  __int64 **v2; // rcx
  unsigned int v3; // edi
  __int64 *i; // rax
  void *v5; // rax
  RPC_STATUS v7; // eax
  UUID Uuid; // [rsp+20h] [rbp-38h] BYREF

  v2 = (__int64 **)((char *)this + 104);
  v3 = 0;
  for ( i = *v2; i != (__int64 *)v2; i = (__int64 *)*i )
    v3 += *((_DWORD *)i + 4);
  v5 = operator new[](v3 + 4216, (const struct std::nothrow_t *)&std::nothrow);
  *((_QWORD *)this + 12) = v5;
  if ( !v5 )
    return 2147942414LL;
  memset_0(v5, 0, v3 + 4216);
  **((_DWORD **)this + 12) = v3 + 4216;
  *(_DWORD *)(*((_QWORD *)this + 12) + 44LL) = 0x20000;
  *(_DWORD *)(*((_QWORD *)this + 12) + 64LL) = 537073665;
  if ( *((_BYTE *)this + 216) )
    *(_DWORD *)(*((_QWORD *)this + 12) + 64LL) |= 0x4000000u;
  if ( *((_BYTE *)this + 217) )
    *(_DWORD *)(*((_QWORD *)this + 12) + 64LL) |= 0x100000u;
  *(_DWORD *)(*((_QWORD *)this + 12) + 48LL) = 64;
  CPrivateLogger::SynthesizeHeaders(this, (unsigned __int8 *)(*((_QWORD *)this + 12) + 120LL), v3);
  *(_DWORD *)(*((_QWORD *)this + 12) + 112LL) = v3 + 120;
  *(_DWORD *)(*((_QWORD *)this + 12) + 116LL) = *(_DWORD *)(*((_QWORD *)this + 12) + 112LL) + 2048;
  StringCchCopyW(
    (unsigned __int16 *)(*((_QWORD *)this + 12) + *(unsigned int *)(*((_QWORD *)this + 12) + 112LL)),
    0x400u,
    *((const unsigned __int16 **)this + 1));
  if ( !*((_WORD *)this + 8) )
  {
    Uuid = 0;
    v7 = UuidCreate(&Uuid);
    if ( !v7 || v7 == 1824 )
      tlx::guid_to_string_upper<unsigned short>((char *)this + 16, &Uuid);
  }
  return 0;
}

```

## disassembly

```asm
0x18001d2e0  mov     [rsp+arg_8], rbx
0x18001d2e5  mov     [rsp+arg_10], rbp
0x18001d2ea  push    rsi
0x18001d2eb  push    rdi
0x18001d2ec  push    r14
0x18001d2ee  sub     rsp, 40h
0x18001d2f2  mov     rax, cs:__security_cookie
0x18001d2f9  xor     rax, rsp
0x18001d2fc  mov     [rsp+58h+var_28], rax
0x18001d301  xor     r14d, r14d
0x18001d304  mov     rbx, rcx
0x18001d307  add     rcx, 68h ; 'h'
0x18001d30b  mov     edi, r14d
0x18001d30e  mov     rax, [rcx]
0x18001d311  jmp     short loc_18001D319
0x18001d313  add     edi, [rax+10h]
0x18001d316  mov     rax, [rax]
0x18001d319  cmp     rax, rcx
0x18001d31c  jnz     short loc_18001D313
0x18001d31e  lea     esi, [rdi+1078h]
0x18001d324  mov     ecx, esi; unsigned __int64
0x18001d326  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d32d  mov     ebp, esi
0x18001d32f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001d334  mov     [rbx+60h], rax
0x18001d338  test    rax, rax
0x18001d33b  jnz     short loc_18001D347
0x18001d33d  mov     eax, 8007000Eh
0x18001d342  jmp     loc_18001D418
0x18001d347  mov     r8, rbp; Size
0x18001d34a  xor     edx, edx; Val
0x18001d34c  mov     rcx, rax; void *
0x18001d34f  call    memset_0
0x18001d354  mov     rax, [rbx+60h]
0x18001d358  mov     [rax], esi
0x18001d35a  mov     rax, [rbx+60h]
0x18001d35e  mov     dword ptr [rax+2Ch], 20000h
0x18001d365  mov     rax, [rbx+60h]
0x18001d369  mov     dword ptr [rax+40h], 20031801h
0x18001d370  cmp     [rbx+0D8h], r14b
0x18001d377  jz      short loc_18001D382
0x18001d379  mov     rax, [rbx+60h]
0x18001d37d  bts     dword ptr [rax+40h], 1Ah
0x18001d382  cmp     [rbx+0D9h], r14b
0x18001d389  jz      short loc_18001D394
0x18001d38b  mov     rax, [rbx+60h]
0x18001d38f  bts     dword ptr [rax+40h], 14h
0x18001d394  mov     rax, [rbx+60h]
0x18001d398  mov     r8d, edi; unsigned int
0x18001d39b  mov     rcx, rbx; this
0x18001d39e  mov     dword ptr [rax+30h], 40h ; '@'
0x18001d3a5  mov     rdx, [rbx+60h]
0x18001d3a9  add     rdx, 78h ; 'x'; unsigned __int8 *
0x18001d3ad  call    ?SynthesizeHeaders@CPrivateLogger@@AEAAJPEAEK@Z; CPrivateLogger::SynthesizeHeaders(uchar *,ulong)
0x18001d3b2  mov     rax, [rbx+60h]
0x18001d3b6  lea     ecx, [rdi+78h]
0x18001d3b9  mov     edx, 400h; unsigned __int64
0x18001d3be  mov     [rax+70h], ecx
0x18001d3c1  mov     rcx, [rbx+60h]
0x18001d3c5  mov     eax, [rcx+70h]
0x18001d3c8  add     eax, 800h
0x18001d3cd  mov     [rcx+74h], eax
0x18001d3d0  mov     rax, [rbx+60h]
0x18001d3d4  mov     r8, [rbx+8]; unsigned __int16 *
0x18001d3d8  mov     ecx, [rax+70h]
0x18001d3db  add     rcx, rax; unsigned __int16 *
0x18001d3de  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001d3e3  cmp     [rbx+10h], r14w
0x18001d3e8  jnz     short loc_18001D416
0x18001d3ea  xorps   xmm0, xmm0
0x18001d3ed  lea     rcx, [rsp+58h+Uuid]; Uuid
0x18001d3f2  movups  xmmword ptr [rsp+58h+Uuid.Data1], xmm0
0x18001d3f7  call    cs:__imp_UuidCreate
0x18001d3fd  test    eax, eax
0x18001d3ff  jz      short loc_18001D408
0x18001d401  cmp     eax, 720h
0x18001d406  jnz     short loc_18001D416
0x18001d408  lea     rdx, [rsp+58h+Uuid]
0x18001d40d  lea     rcx, [rbx+10h]
0x18001d411  call    ??$guid_to_string_upper@G@tlx@@YAXPEAGAEBU_GUID@@_N@Z; tlx::guid_to_string_upper<ushort>(ushort *,_GUID const &,bool)
0x18001d416  xor     eax, eax
0x18001d418  mov     rcx, [rsp+58h+var_28]
0x18001d41d  xor     rcx, rsp; StackCookie
0x18001d420  call    __security_check_cookie
0x18001d425  mov     rbx, [rsp+58h+arg_8]
0x18001d42a  mov     rbp, [rsp+58h+arg_10]
0x18001d42f  add     rsp, 40h
0x18001d433  pop     r14
0x18001d435  pop     rdi
0x18001d436  pop     rsi
0x18001d437  retn
```
