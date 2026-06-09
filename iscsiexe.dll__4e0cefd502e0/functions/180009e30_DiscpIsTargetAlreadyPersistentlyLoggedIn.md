# DiscpIsTargetAlreadyPersistentlyLoggedIn

- ea: `0x180009e30`
- end: `0x180009f0d`
- name: `DiscpIsTargetAlreadyPersistentlyLoggedIn`
- size: `221`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800085c4`
- `0x180009898`

## callees

- `0x180009e30`
- `0x1800192e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180009ed7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180009ed7`
- `ISCSIUM!DiscpAllocMemory` at `0x180009e72`
- `ISCSIUM!DiscpAllocMemory` at `0x180009e72`
- `ISCSIUM!DiscpFreeMemory` at `0x180009ead`
- `ISCSIUM!DiscpFreeMemory` at `0x180009ef8`
- `ISCSIUM!DiscpFreeMemory` at `0x180009ead`
- `ISCSIUM!DiscpFreeMemory` at `0x180009ef8`

## pseudocode

```c
__int64 __fastcall DiscpIsTargetAlreadyPersistentlyLoggedIn(__int64 a1)
{
  __int64 v1; // rdi
  unsigned int v3; // ebx
  __int64 v4; // rax
  unsigned int v5; // esi
  int v7; // [rsp+28h] [rbp-20h]
  unsigned int v8; // [rsp+58h] [rbp+10h] BYREF
  unsigned int v9; // [rsp+60h] [rbp+18h] BYREF

  v1 = 0;
  v8 = 0;
  v9 = 0;
  v3 = DiscpReportPeristentLogins((unsigned int)&v8, 0, (unsigned int)&v9, 0, 0, 0);
  if ( v3 == 122 )
  {
    while ( 1 )
    {
      v4 = DiscpAllocMemory(v9);
      v1 = v4;
      if ( !v4 )
        return 8;
      LOBYTE(v7) = 0;
      v3 = DiscpReportPeristentLogins((unsigned int)&v8, v4, (unsigned int)&v9, 0, 0, v7);
      if ( v3 != 122 )
        goto LABEL_6;
      DiscpFreeMemory(v1);
    }
  }
  else
  {
LABEL_6:
    if ( !v3 )
    {
      v5 = 0;
      if ( v8 )
      {
        while ( (unsigned int)_o__wcsicmp(a1, v1 + 2080LL * v5) )
        {
          if ( ++v5 >= v8 )
            goto LABEL_12;
        }
        v3 = -268500929;
      }
    }
LABEL_12:
    if ( v1 )
      DiscpFreeMemory(v1);
  }
  return v3;
}

```

## disassembly

```asm
0x180009e30  mov     rax, rsp
0x180009e33  mov     [rax+8], rbx
0x180009e37  push    rbp
0x180009e38  push    rsi
0x180009e39  push    rdi
0x180009e3a  sub     rsp, 30h
0x180009e3e  xor     edi, edi
0x180009e40  mov     dword ptr [rax+10h], 0
0x180009e47  mov     rbp, rcx
0x180009e4a  mov     [rax-20h], dil
0x180009e4e  xor     r9d, r9d
0x180009e51  mov     [rax-28h], rdi
0x180009e55  lea     r8, [rax+18h]
0x180009e59  mov     [rax+18h], edi
0x180009e5c  xor     edx, edx
0x180009e5e  lea     rcx, [rax+10h]
0x180009e62  call    DiscpReportPeristentLogins
0x180009e67  mov     ebx, eax
0x180009e69  cmp     eax, 7Ah ; 'z'
0x180009e6c  jnz     short loc_180009EBC
0x180009e6e  mov     ecx, [rsp+48h+arg_10]
0x180009e72  call    cs:__imp_DiscpAllocMemory
0x180009e78  mov     rdi, rax
0x180009e7b  test    rax, rax
0x180009e7e  jz      short loc_180009EB5
0x180009e80  mov     byte ptr [rsp+48h+var_20], 0
0x180009e85  lea     r8, [rsp+48h+arg_10]
0x180009e8a  xor     r9d, r9d
0x180009e8d  mov     [rsp+48h+var_28], 0
0x180009e96  mov     rdx, rax
0x180009e99  lea     rcx, [rsp+48h+arg_8]
0x180009e9e  call    DiscpReportPeristentLogins
0x180009ea3  mov     ebx, eax
0x180009ea5  cmp     eax, 7Ah ; 'z'
0x180009ea8  jnz     short loc_180009EBC
0x180009eaa  mov     rcx, rdi
0x180009ead  call    cs:__imp_DiscpFreeMemory
0x180009eb3  jmp     short loc_180009E6E
0x180009eb5  mov     ebx, 8
0x180009eba  jmp     short loc_180009EFE
0x180009ebc  test    ebx, ebx
0x180009ebe  jnz     short loc_180009EF0
0x180009ec0  xor     esi, esi
0x180009ec2  cmp     [rsp+48h+arg_8], esi
0x180009ec6  jbe     short loc_180009EF0
0x180009ec8  mov     eax, esi
0x180009eca  mov     rcx, rbp
0x180009ecd  imul    rdx, rax, 820h
0x180009ed4  add     rdx, rdi
0x180009ed7  call    cs:__imp__o__wcsicmp
0x180009edd  test    eax, eax
0x180009edf  jz      short loc_180009EEB
0x180009ee1  inc     esi
0x180009ee3  cmp     esi, [rsp+48h+arg_8]
0x180009ee7  jb      short loc_180009EC8
0x180009ee9  jmp     short loc_180009EF0
0x180009eeb  mov     ebx, 0EFFF003Fh
0x180009ef0  test    rdi, rdi
0x180009ef3  jz      short loc_180009EFE
0x180009ef5  mov     rcx, rdi
0x180009ef8  call    cs:__imp_DiscpFreeMemory
0x180009efe  mov     eax, ebx
0x180009f00  mov     rbx, [rsp+48h+arg_0]
0x180009f05  add     rsp, 30h
0x180009f09  pop     rdi
0x180009f0a  pop     rsi
0x180009f0b  pop     rbp
0x180009f0c  retn
```
