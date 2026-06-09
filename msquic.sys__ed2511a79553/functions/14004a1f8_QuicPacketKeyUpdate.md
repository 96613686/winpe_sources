# QuicPacketKeyUpdate

- ea: `0x14004a1f8`
- end: `0x14004a323`
- name: `QuicPacketKeyUpdate`
- size: `299`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1400465f4`

## callees

- `0x140008bb0`
- `0x140034788`
- `0x140034814`
- `0x140038d1c`
- `0x140038d74`
- `0x14003c8e0`
- `0x14003ce00`
- `0x14004a1f8`

## pseudocode

```c
__int64 __fastcall QuicPacketKeyUpdate(int a1, __int64 a2, __int64 a3)
{
  _DWORD *v6; // r14
  unsigned __int16 v7; // ax
  int v8; // esi
  int v9; // r9d
  BCRYPT_HASH_HANDLE hHash; // [rsp+30h] [rbp-A8h] BYREF
  _DWORD v12[20]; // [rsp+40h] [rbp-98h] BYREF

  if ( !a2 || *(_DWORD *)a2 != 3 )
    return 3221225860LL;
  hHash = 0;
  memset(v12, 0, 0x48u);
  v6 = (_DWORD *)(a2 + 36);
  v7 = CxPlatHashLength(*(unsigned int *)(a2 + 36));
  v8 = CxPlatHashCreate(*(_DWORD *)(a2 + 36), (UCHAR *)(a2 + 44), v7, &hHash);
  if ( v8 >= 0 )
  {
    v8 = CxPlatHkdfExpandLabel(hHash, (PUCHAR)&v12[2]);
    if ( v8 >= 0 )
    {
      v12[0] = *v6;
      v12[1] = *(_DWORD *)(a2 + 40);
      v8 = QuicPacketKeyDerive(3, a1, (unsigned int)v12, v9, 0, a3);
      memset(v12, 0, 0x48u);
      memset(v6, 0, 0x48u);
    }
  }
  CxPlatHashFree(hHash);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14004a1f8  mov     [rsp+arg_18], rbx
0x14004a1fd  push    rbp
0x14004a1fe  push    rsi
0x14004a1ff  push    rdi
0x14004a200  push    r12
0x14004a202  push    r13
0x14004a204  push    r14
0x14004a206  push    r15
0x14004a208  sub     rsp, 0A0h
0x14004a20f  mov     rax, cs:__security_cookie
0x14004a216  xor     rax, rsp
0x14004a219  mov     [rsp+0D8h+var_48], rax
0x14004a221  mov     r12, r8
0x14004a224  mov     rbx, rdx
0x14004a227  mov     rbp, rcx
0x14004a22a  test    rdx, rdx
0x14004a22d  jz      loc_14004A2F2
0x14004a233  cmp     dword ptr [rdx], 3
0x14004a236  jnz     loc_14004A2F2
0x14004a23c  and     [rsp+0D8h+hHash], 0
0x14004a242  lea     rcx, [rsp+0D8h+var_98]; void *
0x14004a247  mov     r13d, 48h ; 'H'
0x14004a24d  xor     edx, edx; Val
0x14004a24f  mov     r8d, r13d; Size
0x14004a252  call    memset
0x14004a257  lea     r14, [rbx+24h]
0x14004a25b  mov     ecx, [r14]
0x14004a25e  call    CxPlatHashLength
0x14004a263  mov     ecx, [r14]
0x14004a266  lea     rdx, [rbx+2Ch]
0x14004a26a  movzx   edi, ax
0x14004a26d  lea     r9, [rsp+0D8h+hHash]
0x14004a272  mov     r8d, edi
0x14004a275  call    CxPlatHashCreate
0x14004a27a  mov     esi, eax
0x14004a27c  test    eax, eax
0x14004a27e  js      short loc_14004A2E4
0x14004a280  mov     rdx, [rbp+18h]
0x14004a284  lea     rax, [rsp+0D8h+var_90]
0x14004a289  mov     rcx, [rsp+0D8h+hHash]; hHash
0x14004a28e  mov     r9d, edi
0x14004a291  movzx   r8d, di
0x14004a295  mov     [rsp+0D8h+var_B8], rax; PUCHAR
0x14004a29a  call    CxPlatHkdfExpandLabel
0x14004a29f  mov     esi, eax
0x14004a2a1  test    eax, eax
0x14004a2a3  js      short loc_14004A2E4
0x14004a2a5  mov     eax, [r14]
0x14004a2a8  lea     r8, [rsp+0D8h+var_98]
0x14004a2ad  mov     [rsp+0D8h+var_98], eax
0x14004a2b1  lea     ecx, [r13-45h]
0x14004a2b5  mov     eax, [rbx+28h]
0x14004a2b8  mov     rdx, rbp
0x14004a2bb  mov     [rsp+0D8h+var_B0], r12
0x14004a2c0  mov     [rsp+0D8h+var_94], eax
0x14004a2c4  mov     byte ptr [rsp+0D8h+var_B8], 0
0x14004a2c9  call    QuicPacketKeyDerive
0x14004a2ce  mov     esi, eax
0x14004a2d0  lea     rdi, [rsp+0D8h+var_98]
0x14004a2d5  xor     eax, eax
0x14004a2d7  mov     ecx, r13d
0x14004a2da  rep stosb
0x14004a2dc  mov     rdi, r14
0x14004a2df  mov     ecx, r13d
0x14004a2e2  rep stosb
0x14004a2e4  mov     rcx, [rsp+0D8h+hHash]
0x14004a2e9  call    CxPlatHashFree
0x14004a2ee  mov     eax, esi
0x14004a2f0  jmp     short loc_14004A2F7
0x14004a2f2  mov     eax, 0C0000184h
0x14004a2f7  mov     rcx, [rsp+0D8h+var_48]
0x14004a2ff  xor     rcx, rsp; StackCookie
0x14004a302  call    __security_check_cookie
0x14004a307  mov     rbx, [rsp+0D8h+arg_18]
0x14004a30f  add     rsp, 0A0h
0x14004a316  pop     r15
0x14004a318  pop     r14
0x14004a31a  pop     r13
0x14004a31c  pop     r12
0x14004a31e  pop     rdi
0x14004a31f  pop     rsi
0x14004a320  pop     rbp
0x14004a321  retn
```
