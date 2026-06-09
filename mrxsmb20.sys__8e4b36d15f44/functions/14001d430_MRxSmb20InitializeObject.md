# MRxSmb20InitializeObject

- ea: `0x14001d430`
- end: `0x14001d62f`
- name: `MRxSmb20InitializeObject`
- size: `511`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14001d430`

## import_xrefs

- `rdbss!RxNameCacheInitializeEx` at `0x14001d4aa`
- `rdbss!RxNameCacheInitializeEx` at `0x14001d4e9`
- `rdbss!RxNameCacheInitializeEx` at `0x14001d526`
- `rdbss!RxNameCacheInitializeEx` at `0x14001d559`
- `rdbss!RxNameCacheInitializeEx` at `0x14001d599`
- `rdbss!RxNameCacheInitializeEx` at `0x14001d5d9`
- `rdbss!RxNameCacheInitializeEx` at `0x14001d619`
- `rdbss!RxNameCacheInitializeEx` at `0x14001d4aa`
- `rdbss!RxNameCacheInitializeEx` at `0x14001d4e9`
- `rdbss!RxNameCacheInitializeEx` at `0x14001d526`
- `rdbss!RxNameCacheInitializeEx` at `0x14001d559`
- `rdbss!RxNameCacheInitializeEx` at `0x14001d599`
- `rdbss!RxNameCacheInitializeEx` at `0x14001d5d9`
- `rdbss!RxNameCacheInitializeEx` at `0x14001d619`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x14001d476`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x14001d4b9`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x14001d4f8`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x14001d568`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x14001d5a8`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x14001d5e8`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x14001d476`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x14001d4b9`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x14001d4f8`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x14001d568`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x14001d5a8`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x14001d5e8`

## pseudocode

```c
__int64 __fastcall MRxSmb20InitializeObject(__m128i *a1)
{
  __int64 v3; // rbx
  __int64 InstanceConfigurationBlock; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax

  if ( a1->m128i_u16[0] == 57857 )
  {
    v3 = a1[1].m128i_i64[1];
    InstanceConfigurationBlock = MRxSmbGetInstanceConfigurationBlock(v3);
    RxNameCacheInitializeEx(&a1[12], 32, (unsigned int)(2 * *(_DWORD *)(InstanceConfigurationBlock + 24)), 0, 0, 0);
    v5 = MRxSmbGetInstanceConfigurationBlock(v3);
    RxNameCacheInitializeEx(
      &a1[23].m128i_u64[1],
      128,
      *(unsigned int *)(v5 + 24),
      0,
      Smb2FileInfoCacheEntryDestructor,
      a1);
    v6 = MRxSmbGetInstanceConfigurationBlock(v3);
    RxNameCacheInitializeEx(&a1[35], 0, *(unsigned int *)(v6 + 28), 0, 0, 0);
    RxNameCacheInitializeEx(&a1[46].m128i_u64[1], 168, 4, 0, 0, 0);
    v7 = MRxSmbGetInstanceConfigurationBlock(v3);
    RxNameCacheInitializeEx(
      &a1[69].m128i_u64[1],
      0,
      *(unsigned int *)(v7 + 32),
      Smb2ConstructDirCacheObject,
      Smb2DirCacheObjectDestructor,
      a1);
    v8 = MRxSmbGetInstanceConfigurationBlock(v3);
    RxNameCacheInitializeEx(&a1[58], 4, *(unsigned int *)(v8 + 48), 0, 0, 0);
    v9 = MRxSmbGetInstanceConfigurationBlock(v3);
    RxNameCacheInitializeEx(&a1[81], 0, (unsigned int)(2 * *(_DWORD *)(v9 + 24)), 0, 0, 0);
  }
  else if ( a1->m128i_u16[0] == 57860 )
  {
    a1[40] = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    a1[41].m128i_i32[0] = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x14001d430  push    rdi
0x14001d432  sub     rsp, 30h
0x14001d436  movzx   eax, word ptr [rcx]
0x14001d439  mov     rdi, rcx
0x14001d43c  sub     eax, 0E201h
0x14001d441  jz      short loc_14001D46A
0x14001d443  cmp     eax, 3
0x14001d446  jnz     short loc_14001D461
0x14001d448  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14001d450  movups  xmmword ptr [rcx+280h], xmm0
0x14001d457  mov     dword ptr [rcx+290h], 0
0x14001d461  xor     eax, eax
0x14001d463  add     rsp, 30h
0x14001d467  pop     rdi
0x14001d468  retn
0x14001d46a  mov     [rsp+38h+arg_0], rbx
0x14001d46f  mov     rbx, [rcx+18h]
0x14001d473  mov     rcx, rbx
0x14001d476  call    cs:__imp_MRxSmbGetInstanceConfigurationBlock
0x14001d47d  nop     dword ptr [rax+rax+00h]
0x14001d482  lea     rcx, [rdi+0C0h]
0x14001d489  mov     [rsp+38h+var_10], 0
0x14001d492  xor     r9d, r9d
0x14001d495  mov     [rsp+38h+var_18], 0
0x14001d49e  mov     edx, 20h ; ' '
0x14001d4a3  mov     r8d, [rax+18h]
0x14001d4a7  add     r8d, r8d
0x14001d4aa  call    cs:__imp_RxNameCacheInitializeEx
0x14001d4b1  nop     dword ptr [rax+rax+00h]
0x14001d4b6  mov     rcx, rbx
0x14001d4b9  call    cs:__imp_MRxSmbGetInstanceConfigurationBlock
0x14001d4c0  nop     dword ptr [rax+rax+00h]
0x14001d4c5  lea     rdx, Smb2FileInfoCacheEntryDestructor
0x14001d4cc  mov     [rsp+38h+var_10], rdi
0x14001d4d1  mov     [rsp+38h+var_18], rdx
0x14001d4d6  lea     rcx, [rdi+178h]
0x14001d4dd  xor     r9d, r9d
0x14001d4e0  mov     edx, 80h
0x14001d4e5  mov     r8d, [rax+18h]
0x14001d4e9  call    cs:__imp_RxNameCacheInitializeEx
0x14001d4f0  nop     dword ptr [rax+rax+00h]
0x14001d4f5  mov     rcx, rbx
0x14001d4f8  call    cs:__imp_MRxSmbGetInstanceConfigurationBlock
0x14001d4ff  nop     dword ptr [rax+rax+00h]
0x14001d504  lea     rcx, [rdi+230h]
0x14001d50b  mov     [rsp+38h+var_10], 0
0x14001d514  xor     r9d, r9d
0x14001d517  mov     [rsp+38h+var_18], 0
0x14001d520  xor     edx, edx
0x14001d522  mov     r8d, [rax+1Ch]
0x14001d526  call    cs:__imp_RxNameCacheInitializeEx
0x14001d52d  nop     dword ptr [rax+rax+00h]
0x14001d532  lea     rcx, [rdi+2E8h]
0x14001d539  mov     [rsp+38h+var_10], 0
0x14001d542  xor     r9d, r9d
0x14001d545  mov     [rsp+38h+var_18], 0
0x14001d54e  mov     edx, 0A8h
0x14001d553  mov     r8d, 4
0x14001d559  call    cs:__imp_RxNameCacheInitializeEx
0x14001d560  nop     dword ptr [rax+rax+00h]
0x14001d565  mov     rcx, rbx
0x14001d568  call    cs:__imp_MRxSmbGetInstanceConfigurationBlock
0x14001d56f  nop     dword ptr [rax+rax+00h]
0x14001d574  lea     r8, Smb2DirCacheObjectDestructor
0x14001d57b  mov     [rsp+38h+var_10], rdi
0x14001d580  mov     [rsp+38h+var_18], r8
0x14001d585  lea     rcx, [rdi+458h]
0x14001d58c  lea     r9, Smb2ConstructDirCacheObject
0x14001d593  xor     edx, edx
0x14001d595  mov     r8d, [rax+20h]
0x14001d599  call    cs:__imp_RxNameCacheInitializeEx
0x14001d5a0  nop     dword ptr [rax+rax+00h]
0x14001d5a5  mov     rcx, rbx
0x14001d5a8  call    cs:__imp_MRxSmbGetInstanceConfigurationBlock
0x14001d5af  nop     dword ptr [rax+rax+00h]
0x14001d5b4  lea     rcx, [rdi+3A0h]
0x14001d5bb  mov     [rsp+38h+var_10], 0
0x14001d5c4  xor     r9d, r9d
0x14001d5c7  mov     [rsp+38h+var_18], 0
0x14001d5d0  mov     edx, 4
0x14001d5d5  mov     r8d, [rax+30h]
0x14001d5d9  call    cs:__imp_RxNameCacheInitializeEx
0x14001d5e0  nop     dword ptr [rax+rax+00h]
0x14001d5e5  mov     rcx, rbx
0x14001d5e8  call    cs:__imp_MRxSmbGetInstanceConfigurationBlock
0x14001d5ef  nop     dword ptr [rax+rax+00h]
0x14001d5f4  lea     rcx, [rdi+510h]
0x14001d5fb  mov     [rsp+38h+var_10], 0
0x14001d604  xor     r9d, r9d
0x14001d607  mov     [rsp+38h+var_18], 0
0x14001d610  xor     edx, edx
0x14001d612  mov     r8d, [rax+18h]
0x14001d616  add     r8d, r8d
0x14001d619  call    cs:__imp_RxNameCacheInitializeEx
0x14001d620  nop     dword ptr [rax+rax+00h]
0x14001d625  mov     rbx, [rsp+38h+arg_0]
0x14001d62a  jmp     loc_14001D461
```
