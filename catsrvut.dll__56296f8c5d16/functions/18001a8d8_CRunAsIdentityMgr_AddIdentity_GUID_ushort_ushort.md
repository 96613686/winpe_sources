# CRunAsIdentityMgr::AddIdentity(_GUID,ushort *,ushort *)

- ea: `0x18001a8d8`
- end: `0x18001a9db`
- name: `?AddIdentity@CRunAsIdentityMgr@@QEAAJU_GUID@@PEAG1@Z`
- size: `259`
- prototype: `__int64 __fastcall(CRunAsIdentityMgr *this, struct _GUID *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001abcc`

## callees

- `0x180015594`
- `0x18001a8d8`
- `0x18001c6a4`
- `0x18005583a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a97b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a9af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a97b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a9af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a92a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a92a`

## pseudocode

```c
__int64 __fastcall CRunAsIdentityMgr::AddIdentity(
        CRunAsIdentityMgr *this,
        struct _GUID *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  __int64 v8; // rsi
  int v9; // eax
  unsigned int v10; // edi
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rbx
  unsigned __int16 *v14; // r11
  unsigned int v15; // edi
  __int64 v16; // r11
  int v17; // r14d
  int v18; // edi
  __int64 v19; // r11

  if ( a3 )
    v8 = (unsigned int)safe_lstrlenW(a3) + 1;
  else
    v8 = 0;
  if ( a4 )
    v9 = safe_lstrlenW(a4) + 1;
  else
    v9 = 0;
  v10 = 2 * (v8 + v9) + 40;
  v11 = (unsigned __int16 *)CoTaskMemAlloc(v10);
  v12 = v11;
  if ( !v11 )
    return 2147942414LL;
  memset_0(v11, 0, v10);
  *(struct _GUID *)v12 = *a2;
  v14 = v12 + 20;
  v15 = v10 - 40;
  if ( a3 )
  {
    v17 = StringCbCopyW(v12 + 20, v15, a3);
    if ( v17 < 0 )
    {
      CoTaskMemFree(v12);
      return (unsigned int)v17;
    }
    *((_QWORD *)v12 + 2) = v16;
    v14 = (unsigned __int16 *)(v16 + 2 * v8);
    v15 -= 2 * v8;
  }
  if ( a4 )
  {
    v18 = StringCbCopyW(v14, v15, a4);
    if ( v18 < 0 )
    {
      CoTaskMemFree(v12);
      return (unsigned int)v18;
    }
    *((_QWORD *)v12 + 3) = v19;
  }
  *((_QWORD *)v12 + 4) = *(_QWORD *)this;
  *(_QWORD *)this = v12;
  return 0;
}

```

## disassembly

```asm
0x18001a8d8  push    rbx
0x18001a8da  push    rbp
0x18001a8db  push    rsi
0x18001a8dc  push    rdi
0x18001a8dd  push    r12
0x18001a8df  push    r13
0x18001a8e1  push    r14
0x18001a8e3  push    r15
0x18001a8e5  sub     rsp, 28h
0x18001a8e9  mov     rbp, r9
0x18001a8ec  mov     r14, r8
0x18001a8ef  mov     r13, rdx
0x18001a8f2  mov     r15, rcx
0x18001a8f5  test    r8, r8
0x18001a8f8  jz      short loc_18001A907
0x18001a8fa  mov     rcx, r8; unsigned __int16 *
0x18001a8fd  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18001a902  lea     esi, [rax+1]
0x18001a905  jmp     short loc_18001A909
0x18001a907  xor     esi, esi
0x18001a909  test    rbp, rbp
0x18001a90c  jz      short loc_18001A91A
0x18001a90e  mov     rcx, rbp; unsigned __int16 *
0x18001a911  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18001a916  inc     eax
0x18001a918  jmp     short loc_18001A91C
0x18001a91a  xor     eax, eax
0x18001a91c  add     eax, esi
0x18001a91e  lea     edi, ds:28h[rax*2]
0x18001a925  mov     r12d, edi
0x18001a928  mov     ecx, edi; cb
0x18001a92a  call    cs:__imp_CoTaskMemAlloc
0x18001a930  mov     rbx, rax
0x18001a933  test    rax, rax
0x18001a936  jnz     short loc_18001A942
0x18001a938  mov     eax, 8007000Eh
0x18001a93d  jmp     loc_18001A9CA
0x18001a942  mov     r8, r12; Size
0x18001a945  xor     edx, edx; Val
0x18001a947  mov     rcx, rbx; void *
0x18001a94a  call    memset_0
0x18001a94f  movaps  xmm0, xmmword ptr [r13+0]
0x18001a954  movdqu  xmmword ptr [rbx], xmm0
0x18001a958  lea     r11, [rbx+28h]
0x18001a95c  add     edi, 0FFFFFFD8h
0x18001a95f  test    r14, r14
0x18001a962  jz      short loc_18001A994
0x18001a964  mov     edx, edi; unsigned __int64
0x18001a966  mov     r8, r14; unsigned __int16 *
0x18001a969  mov     rcx, r11; unsigned __int16 *
0x18001a96c  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18001a971  mov     r14d, eax
0x18001a974  test    eax, eax
0x18001a976  jns     short loc_18001A987
0x18001a978  mov     rcx, rbx; pv
0x18001a97b  call    cs:__imp_CoTaskMemFree
0x18001a981  nop
0x18001a982  mov     eax, r14d
0x18001a985  jmp     short loc_18001A9CA
0x18001a987  mov     [rbx+10h], r11
0x18001a98b  lea     r11, [r11+rsi*2]
0x18001a98f  lea     eax, [rsi+rsi]
0x18001a992  sub     edi, eax
0x18001a994  test    rbp, rbp
0x18001a997  jz      short loc_18001A9BE
0x18001a999  mov     edx, edi; unsigned __int64
0x18001a99b  mov     r8, rbp; unsigned __int16 *
0x18001a99e  mov     rcx, r11; unsigned __int16 *
0x18001a9a1  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18001a9a6  mov     edi, eax
0x18001a9a8  test    eax, eax
0x18001a9aa  jns     short loc_18001A9BA
0x18001a9ac  mov     rcx, rbx; pv
0x18001a9af  call    cs:__imp_CoTaskMemFree
0x18001a9b5  nop
0x18001a9b6  mov     eax, edi
0x18001a9b8  jmp     short loc_18001A9CA
0x18001a9ba  mov     [rbx+18h], r11
0x18001a9be  mov     rax, [r15]
0x18001a9c1  mov     [rbx+20h], rax
0x18001a9c5  mov     [r15], rbx
0x18001a9c8  xor     eax, eax
0x18001a9ca  add     rsp, 28h
0x18001a9ce  pop     r15
0x18001a9d0  pop     r14
0x18001a9d2  pop     r13
0x18001a9d4  pop     r12
0x18001a9d6  pop     rdi
0x18001a9d7  pop     rsi
0x18001a9d8  pop     rbp
0x18001a9d9  pop     rbx
0x18001a9da  retn
```
