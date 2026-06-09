# _PCW_INSTANCE::Create(_PCW_INSTANCE * *,_PCW_REGISTRATION const *,_UNICODE_STRING const *,ulong,_PCW_DATA const *)

- ea: `0x14000d0b8`
- end: `0x14000d2d7`
- name: `?Create@_PCW_INSTANCE@@SAJPEAPEAU1@PEBU_PCW_REGISTRATION@@PEBU_UNICODE_STRING@@KPEBU_PCW_DATA@@@Z`
- size: `543`
- prototype: `__int64 __fastcall(struct _PCW_INSTANCE **, const struct _PCW_REGISTRATION *, const struct _UNICODE_STRING *, unsigned int, const struct _PCW_DATA *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000db70`

## callees

- `0x1400099e0`
- `0x140009a08`
- `0x14000d0b8`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d255`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d255`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d2a9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d2a9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000d26a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000d26a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000d29d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000d29d`
- `ntoskrnl!ExAllocatePool2` at `0x14000d18a`
- `ntoskrnl!ExAllocatePool2` at `0x14000d18a`

## pseudocode

```c
__int64 __fastcall _PCW_INSTANCE::Create(
        struct _PCW_INSTANCE **a1,
        const struct _PCW_REGISTRATION *a2,
        const struct _UNICODE_STRING *a3,
        unsigned int a4,
        const struct _PCW_DATA *a5)
{
  unsigned int v10; // r9d
  unsigned int v11; // r8d
  __int128 v12; // xmm6
  int v13; // ebx
  __int64 Pool2; // rax
  __int64 v15; // rbx
  __int64 v16; // r8
  unsigned int i; // edx
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rcx
  signed __int32 v24; // eax
  __int64 v25; // rdi
  __int64 v26; // rsi
  __int64 *v27; // rax
  __int64 v28; // rdi
  __int128 v29; // [rsp+20h] [rbp-58h] BYREF

  if ( *((_DWORD *)a2 + 7) != a4 )
    return 3221225714LL;
  v10 = *((_DWORD *)a2 + 6);
  if ( !v10 )
  {
LABEL_7:
    if ( a4 > 0x1FFFFFF5 )
      return 3221225621LL;
    v12 = 0;
    v29 = 0;
    if ( a3 && a3->Length )
    {
      v13 = AllocatedUnicodeString::Capture((AllocatedUnicodeString *)&v29, a3->Buffer, a3->Length, KernelMode);
      if ( v13 < 0 )
        goto LABEL_16;
      v12 = v29;
    }
    Pool2 = ExAllocatePool2(256, 8 * a4 + 80, 1232560976);
    v15 = Pool2;
    if ( Pool2 )
    {
      v16 = Pool2 + 80;
      for ( i = 0; i < a4; *(_QWORD *)(v16 + 8 * v19) = a5[v18].Data )
      {
        v18 = i;
        v19 = i++;
      }
      *(_OWORD *)v15 = 0;
      *(_OWORD *)(v15 + 16) = v12;
      v20 = *((_QWORD *)a2 + 4);
      v29 = 0;
      if ( v20 )
        _InterlockedIncrement((volatile signed __int32 *)(v20 + 152));
      *(_QWORD *)(v15 + 32) = v20;
      v21 = *((_QWORD *)a2 + 5);
      if ( v21 )
        _InterlockedIncrement((volatile signed __int32 *)(v21 + 132));
      *(_QWORD *)(v15 + 40) = v21;
      *(_QWORD *)(v15 + 48) = 0;
      *(_QWORD *)(v15 + 56) = a2;
      *(_QWORD *)(v15 + 64) = v16;
      v22 = *((_QWORD *)a2 + 4);
      if ( v22 )
        v23 = *(_QWORD *)(v22 + 80);
      else
        v23 = *((_QWORD *)a2 + 5);
      v24 = _InterlockedIncrement((volatile signed __int32 *)(v23 + 128));
      *(_DWORD *)(v15 + 76) = 1;
      *(_DWORD *)(v15 + 72) = v24;
      v25 = *(_QWORD *)(v15 + 32);
      if ( !v25 )
        v25 = *(_QWORD *)(v15 + 40);
      KeEnterCriticalRegion();
      v26 = v25 + 56;
      ExAcquirePushLockExclusiveEx(v25 + 56, 0);
      v27 = *(__int64 **)(v25 + 72);
      v28 = v25 + 64;
      if ( *v27 != v28 )
        __fastfail(3u);
      *(_QWORD *)v15 = v28;
      *(_QWORD *)(v15 + 8) = v27;
      *v27 = v15;
      *(_QWORD *)(v28 + 8) = v15;
      ExReleasePushLockExclusiveEx(v26, 0);
      KeLeaveCriticalRegion();
      *a1 = (struct _PCW_INSTANCE *)v15;
      AllocatedUnicodeString::~AllocatedUnicodeString((AllocatedUnicodeString *)&v29);
      return 0;
    }
    v13 = -1073741801;
LABEL_16:
    AllocatedUnicodeString::~AllocatedUnicodeString((AllocatedUnicodeString *)&v29);
    return (unsigned int)v13;
  }
  v11 = 0;
  while ( a5[*(unsigned __int16 *)(*((_QWORD *)a2 + 8) + 8LL * v11 + 2)].Size >= *(unsigned __int16 *)(*((_QWORD *)a2 + 8) + 8LL * v11 + 4)
                                                                               + (unsigned int)*(unsigned __int16 *)(*((_QWORD *)a2 + 8) + 8LL * v11 + 6) )
  {
    if ( ++v11 >= v10 )
      goto LABEL_7;
  }
  return 3221225990LL;
}

```

## disassembly

```asm
0x14000d0b8  push    rbx
0x14000d0ba  push    rbp
0x14000d0bb  push    rsi
0x14000d0bc  push    rdi
0x14000d0bd  push    r14
0x14000d0bf  push    r15
0x14000d0c1  sub     rsp, 48h
0x14000d0c5  mov     esi, r9d
0x14000d0c8  movaps  [rsp+78h+var_48], xmm6
0x14000d0cd  mov     r10, r8
0x14000d0d0  mov     rdi, rdx
0x14000d0d3  mov     r14, rcx
0x14000d0d6  cmp     [rdx+1Ch], r9d
0x14000d0da  jz      short loc_14000D0E6
0x14000d0dc  mov     eax, 0C00000F2h
0x14000d0e1  jmp     loc_14000D2C4
0x14000d0e6  mov     r9d, [rdx+18h]
0x14000d0ea  xor     r15d, r15d
0x14000d0ed  mov     rbp, [rsp+78h+arg_20]
0x14000d0f5  test    r9d, r9d
0x14000d0f8  jz      short loc_14000D129
0x14000d0fa  mov     r11, [rdx+40h]
0x14000d0fe  mov     r8d, r15d
0x14000d101  mov     ecx, r8d
0x14000d104  movzx   eax, word ptr [r11+rcx*8+4]
0x14000d10a  movzx   edx, word ptr [r11+rcx*8+6]
0x14000d110  add     edx, eax
0x14000d112  movzx   eax, word ptr [r11+rcx*8+2]
0x14000d118  add     rax, rax
0x14000d11b  cmp     [rbp+rax*8+8], edx
0x14000d11f  jb      short loc_14000D13B
0x14000d121  inc     r8d
0x14000d124  cmp     r8d, r9d
0x14000d127  jb      short loc_14000D101
0x14000d129  cmp     esi, 1FFFFFF5h
0x14000d12f  jbe     short loc_14000D145
0x14000d131  mov     eax, 0C0000095h
0x14000d136  jmp     loc_14000D2C4
0x14000d13b  mov     eax, 0C0000206h
0x14000d140  jmp     loc_14000D2C4
0x14000d145  xorps   xmm6, xmm6
0x14000d148  movaps  [rsp+78h+var_58], xmm6
0x14000d14d  test    r10, r10
0x14000d150  jz      short loc_14000D178
0x14000d152  movzx   r8d, word ptr [r10]; unsigned __int16
0x14000d156  test    r8w, r8w
0x14000d15a  jz      short loc_14000D178
0x14000d15c  mov     rdx, [r10+8]; unsigned __int16 *
0x14000d160  lea     rcx, [rsp+78h+var_58]; this
0x14000d165  xor     r9d, r9d; enum _MODE
0x14000d168  call    ?Capture@AllocatedUnicodeString@@QEAAJPEBGGW4_MODE@@@Z; AllocatedUnicodeString::Capture(ushort const *,ushort,_MODE)
0x14000d16d  mov     ebx, eax
0x14000d16f  test    eax, eax
0x14000d171  js      short loc_14000D1A3
0x14000d173  movaps  xmm6, [rsp+78h+var_58]
0x14000d178  lea     edx, ds:50h[rsi*8]
0x14000d17f  mov     ecx, 100h
0x14000d184  mov     r8d, 49776350h
0x14000d18a  call    cs:__imp_ExAllocatePool2
0x14000d191  nop     dword ptr [rax+rax+00h]
0x14000d196  mov     rbx, rax
0x14000d199  test    rax, rax
0x14000d19c  jnz     short loc_14000D1B4
0x14000d19e  mov     ebx, 0C0000017h
0x14000d1a3  lea     rcx, [rsp+78h+var_58]; this
0x14000d1a8  call    ??1AllocatedUnicodeString@@QEAA@XZ; AllocatedUnicodeString::~AllocatedUnicodeString(void)
0x14000d1ad  mov     eax, ebx
0x14000d1af  jmp     loc_14000D2C4
0x14000d1b4  lea     r8, [rax+50h]
0x14000d1b8  mov     edx, r15d
0x14000d1bb  test    esi, esi
0x14000d1bd  jz      short loc_14000D1D5
0x14000d1bf  mov     eax, edx
0x14000d1c1  add     rax, rax
0x14000d1c4  mov     ecx, edx
0x14000d1c6  inc     edx
0x14000d1c8  mov     rax, [rbp+rax*8+0]
0x14000d1cd  mov     [r8+rcx*8], rax
0x14000d1d1  cmp     edx, esi
0x14000d1d3  jb      short loc_14000D1BF
0x14000d1d5  xorps   xmm0, xmm0
0x14000d1d8  movups  xmmword ptr [rbx], xmm0
0x14000d1db  movdqu  xmmword ptr [rbx+10h], xmm6
0x14000d1e0  mov     rax, [rdi+20h]
0x14000d1e4  movdqa  [rsp+78h+var_58], xmm0
0x14000d1ea  test    rax, rax
0x14000d1ed  jz      short loc_14000D1F6
0x14000d1ef  lock inc dword ptr [rax+98h]
0x14000d1f6  mov     [rbx+20h], rax
0x14000d1fa  mov     rax, [rdi+28h]
0x14000d1fe  test    rax, rax
0x14000d201  jz      short loc_14000D20A
0x14000d203  lock inc dword ptr [rax+84h]
0x14000d20a  mov     [rbx+28h], rax
0x14000d20e  xor     eax, eax
0x14000d210  mov     [rbx+30h], rax
0x14000d214  mov     [rbx+38h], rdi
0x14000d218  mov     [rbx+40h], r8
0x14000d21c  mov     rcx, [rdi+20h]
0x14000d220  test    rcx, rcx
0x14000d223  jz      short loc_14000D22B
0x14000d225  mov     rcx, [rcx+50h]
0x14000d229  jmp     short loc_14000D22F
0x14000d22b  mov     rcx, [rdi+28h]
0x14000d22f  mov     eax, 1
0x14000d234  lock xadd [rcx+80h], eax
0x14000d23c  inc     eax
0x14000d23e  mov     dword ptr [rbx+4Ch], 1
0x14000d245  mov     [rbx+48h], eax
0x14000d248  mov     rdi, [rbx+20h]
0x14000d24c  test    rdi, rdi
0x14000d24f  jnz     short loc_14000D255
0x14000d251  mov     rdi, [rbx+28h]
0x14000d255  call    cs:__imp_KeEnterCriticalRegion
0x14000d25c  nop     dword ptr [rax+rax+00h]
0x14000d261  lea     rsi, [rdi+38h]
0x14000d265  xor     edx, edx
0x14000d267  mov     rcx, rsi
0x14000d26a  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000d271  nop     dword ptr [rax+rax+00h]
0x14000d276  mov     rax, [rdi+48h]
0x14000d27a  add     rdi, 40h ; '@'
0x14000d27e  cmp     [rax], rdi
0x14000d281  jz      short loc_14000D28A
0x14000d283  mov     ecx, 3
0x14000d288  int     29h; Win8: RtlFailFast(ecx)
0x14000d28a  mov     [rbx], rdi
0x14000d28d  xor     edx, edx
0x14000d28f  mov     [rbx+8], rax
0x14000d293  mov     rcx, rsi
0x14000d296  mov     [rax], rbx
0x14000d299  mov     [rdi+8], rbx
0x14000d29d  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000d2a4  nop     dword ptr [rax+rax+00h]
0x14000d2a9  call    cs:__imp_KeLeaveCriticalRegion
0x14000d2b0  nop     dword ptr [rax+rax+00h]
0x14000d2b5  lea     rcx, [rsp+78h+var_58]; this
0x14000d2ba  mov     [r14], rbx
0x14000d2bd  call    ??1AllocatedUnicodeString@@QEAA@XZ; AllocatedUnicodeString::~AllocatedUnicodeString(void)
0x14000d2c2  xor     eax, eax
0x14000d2c4  movaps  xmm6, [rsp+78h+var_48]
0x14000d2c9  add     rsp, 48h
0x14000d2cd  pop     r15
0x14000d2cf  pop     r14
0x14000d2d1  pop     rdi
0x14000d2d2  pop     rsi
0x14000d2d3  pop     rbp
0x14000d2d4  pop     rbx
0x14000d2d5  retn
```
