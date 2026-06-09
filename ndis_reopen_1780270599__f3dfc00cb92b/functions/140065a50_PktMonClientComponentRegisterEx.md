# PktMonClientComponentRegisterEx

- ea: `0x140065a50`
- end: `0x140065b4a`
- name: `PktMonClientComponentRegisterEx`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400659e0`

## callees

- `0x140065a50`
- `0x1400eb460`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140065b32`
- `ntoskrnl!KeReleaseMutex` at `0x140065b32`
- `ntoskrnl!KeWaitForSingleObject` at `0x140065aae`
- `ntoskrnl!KeWaitForSingleObject` at `0x140065aae`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400f2180`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400f2180`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140065b1d`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140065b1d`

## pseudocode

```c
__int64 __fastcall PktMonClientComponentRegisterEx(__int64 a1, __int64 a2, __int64 a3, int a4, int a5)
{
  unsigned int v9; // ebx
  __int64 v11; // rax
  __int128 v12; // [rsp+30h] [rbp-58h] BYREF
  __int128 v13; // [rsp+40h] [rbp-48h]
  __int128 v14; // [rsp+50h] [rbp-38h]

  v12 = 0;
  v13 = 0;
  v14 = 0;
  if ( (_QWORD)xmmword_140123740 )
  {
    KeWaitForSingleObject(&PktMonCompMutex, Executive, 0, 0, 0);
    if ( (_QWORD)xmmword_140123740 )
    {
      if ( *(_QWORD *)(a1 + 40) )
      {
        v9 = -1073741816;
      }
      else
      {
        *(_DWORD *)(a1 + 32) = 0;
        *(_QWORD *)(a1 + 24) = a1 + 16;
        *(_QWORD *)(a1 + 16) = a1 + 16;
        LOWORD(v12) = 48;
        *((_QWORD *)&v12 + 1) = a1;
        *(_QWORD *)&v13 = a2;
        *((_QWORD *)&v13 + 1) = a3;
        LODWORD(v14) = a4;
        *(_QWORD *)((char *)&v14 + 4) = 0x400000003LL;
        if ( ExAcquireRundownProtectionCacheAware(RunRefCacheAware) )
        {
          v9 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, __int64))(*((_QWORD *)&xmmword_140123740 + 1) + 8LL))(
                 xmmword_140123740,
                 &v12,
                 a1 + 40);
          if ( !v9 )
          {
            *(_DWORD *)(a1 + 52) = a5;
            *(_DWORD *)(a1 + 48) = a4;
            v11 = PktMonCompList;
            if ( *(__int64 **)(PktMonCompList + 8) != &PktMonCompList )
              __fastfail(3u);
            ++PktMonCompCount;
            *(_QWORD *)a1 = PktMonCompList;
            *(_QWORD *)(a1 + 8) = &PktMonCompList;
            *(_QWORD *)(v11 + 8) = a1;
            PktMonCompList = a1;
          }
          ExReleaseRundownProtectionCacheAware(RunRefCacheAware);
        }
        else
        {
          v9 = -1073741738;
        }
      }
    }
    else
    {
      v9 = -1073741661;
    }
    KeReleaseMutex(&PktMonCompMutex, 0);
  }
  else
  {
    return (unsigned int)-1073741661;
  }
  return v9;
}

```

## disassembly

```asm
0x140065a50  push    rbx
0x140065a52  push    rbp
0x140065a53  push    rsi
0x140065a54  push    rdi
0x140065a55  push    r14
0x140065a57  sub     rsp, 60h
0x140065a5b  cmp     qword ptr cs:xmmword_140123740, 0
0x140065a63  xorps   xmm0, xmm0
0x140065a66  movups  [rsp+88h+var_58], xmm0
0x140065a6b  mov     esi, r9d
0x140065a6e  mov     rbx, r8
0x140065a71  movups  [rsp+88h+var_48], xmm0
0x140065a76  mov     rbp, rdx
0x140065a79  mov     rdi, rcx
0x140065a7c  movups  [rsp+88h+var_38], xmm0
0x140065a81  jnz     short loc_140065A96
0x140065a83  mov     ebx, 0C00000A3h
0x140065a88  mov     eax, ebx
0x140065a8a  add     rsp, 60h
0x140065a8e  pop     r14
0x140065a90  pop     rdi
0x140065a91  pop     rsi
0x140065a92  pop     rbp
0x140065a93  pop     rbx
0x140065a94  retn
0x140065a96  xor     r9d, r9d; Alertable
0x140065a99  mov     [rsp+88h+Timeout], 0; Timeout
0x140065aa2  xor     r8d, r8d; WaitMode
0x140065aa5  lea     rcx, PktMonCompMutex; Object
0x140065aac  xor     edx, edx; WaitReason
0x140065aae  call    cs:__imp_KeWaitForSingleObject
0x140065ab5  nop     dword ptr [rax+rax+00h]
0x140065aba  cmp     qword ptr cs:xmmword_140123740, 0
0x140065ac2  jz      short loc_140065B43
0x140065ac4  cmp     qword ptr [rdi+28h], 0
0x140065ac9  jz      loc_1400F213A
0x140065acf  mov     ebx, 0C0000008h
0x140065ad4  jmp     short loc_140065B29
0x140065ad6  mov     eax, [rsp+88h+arg_20]
0x140065add  lea     rdx, PktMonCompList
0x140065ae4  mov     [rdi+34h], eax
0x140065ae7  mov     [rdi+30h], esi
0x140065aea  mov     rax, cs:PktMonCompList
0x140065af1  cmp     [rax+8], rdx
0x140065af5  jz      short loc_140065AFE
0x140065af7  mov     ecx, 3
0x140065afc  int     29h; Win8: RtlFailFast(ecx)
0x140065afe  inc     cs:PktMonCompCount
0x140065b04  mov     [rdi], rax
0x140065b07  mov     [rdi+8], rdx
0x140065b0b  mov     [rax+8], rdi
0x140065b0f  mov     cs:PktMonCompList, rdi
0x140065b16  mov     rcx, cs:RunRefCacheAware; RunRefCacheAware
0x140065b1d  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140065b24  nop     dword ptr [rax+rax+00h]
0x140065b29  xor     edx, edx; Wait
0x140065b2b  lea     rcx, PktMonCompMutex; Mutex
0x140065b32  call    cs:__imp_KeReleaseMutex
0x140065b39  nop     dword ptr [rax+rax+00h]
0x140065b3e  jmp     loc_140065A88
0x140065b43  mov     ebx, 0C00000A3h
0x140065b48  jmp     short loc_140065B29
0x1400f213a  lea     rax, [rdi+10h]
0x1400f213e  mov     dword ptr [rdi+20h], 0
0x1400f2145  mov     [rax+8], rax
0x1400f2149  mov     [rax], rax
0x1400f214c  mov     eax, 30h ; '0'
0x1400f2151  mov     rcx, cs:RunRefCacheAware; RunRefCacheAware
0x1400f2158  mov     word ptr [rsp+88h+var_58], ax
0x1400f215d  mov     qword ptr [rsp+88h+var_58+8], rdi
0x1400f2162  mov     qword ptr [rsp+88h+var_48], rbp
0x1400f2167  mov     qword ptr [rsp+88h+var_48+8], rbx
0x1400f216c  mov     dword ptr [rsp+88h+var_38], esi
0x1400f2170  mov     dword ptr [rsp+88h+var_38+4], 3
0x1400f2178  mov     dword ptr [rsp+88h+var_38+8], 4
0x1400f2180  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x1400f2187  nop     dword ptr [rax+rax+00h]
0x1400f218c  test    al, al
0x1400f218e  jnz     short loc_1400F219A
0x1400f2190  mov     ebx, 0C0000056h
0x1400f2195  jmp     loc_140065B29
0x1400f219a  mov     rax, qword ptr cs:xmmword_140123740+8
0x1400f21a1  lea     r8, [rdi+28h]
0x1400f21a5  mov     rcx, qword ptr cs:xmmword_140123740
0x1400f21ac  lea     rdx, [rsp+88h+var_58]
0x1400f21b1  mov     rax, [rax+8]
0x1400f21b5  call    _guard_dispatch_icall
0x1400f21ba  mov     ebx, eax
0x1400f21bc  test    eax, eax
0x1400f21be  jnz     loc_140065B16
0x1400f21c4  jmp     loc_140065AD6
```
