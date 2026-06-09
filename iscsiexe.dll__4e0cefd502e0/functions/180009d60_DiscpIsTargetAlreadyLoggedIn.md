# DiscpIsTargetAlreadyLoggedIn

- ea: `0x180009d60`
- end: `0x180009e27`
- name: `DiscpIsTargetAlreadyLoggedIn`
- size: `199`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009898`

## callees

- `0x180009d60`
- `0x180019038`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180009df0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180009df0`
- `ISCSIUM!DiscpAllocMemory` at `0x180009d9d`
- `ISCSIUM!DiscpAllocMemory` at `0x180009d9d`
- `ISCSIUM!DiscpFreeMemory` at `0x180009dc7`
- `ISCSIUM!DiscpFreeMemory` at `0x180009e11`
- `ISCSIUM!DiscpFreeMemory` at `0x180009dc7`
- `ISCSIUM!DiscpFreeMemory` at `0x180009e11`

## pseudocode

```c
__int64 __fastcall DiscpIsTargetAlreadyLoggedIn(__int64 a1)
{
  __int64 v2; // rdi
  unsigned int IScsiSessionList; // ebx
  __int64 v4; // rax
  unsigned int v5; // esi
  unsigned int v7; // [rsp+48h] [rbp+10h] BYREF
  unsigned int v8; // [rsp+50h] [rbp+18h] BYREF

  v7 = 0;
  v8 = 0;
  v2 = 0;
  IScsiSessionList = DiscpGetIScsiSessionList(&v8, &v7, 0);
  if ( IScsiSessionList == 122 )
  {
    while ( 1 )
    {
      v4 = DiscpAllocMemory(v8);
      v2 = v4;
      if ( !v4 )
        return 8;
      IScsiSessionList = DiscpGetIScsiSessionList(&v8, &v7, v4);
      if ( IScsiSessionList != 122 )
        goto LABEL_6;
      DiscpFreeMemory(v2);
    }
  }
  else
  {
LABEL_6:
    if ( !IScsiSessionList )
    {
      v5 = 0;
      if ( v7 )
      {
        while ( (unsigned int)_o__wcsicmp(a1, *(_QWORD *)(((unsigned __int64)v5 << 6) + v2 + 32)) )
        {
          if ( ++v5 >= v7 )
            goto LABEL_12;
        }
        IScsiSessionList = -268500929;
      }
    }
LABEL_12:
    if ( v2 )
      DiscpFreeMemory(v2);
  }
  return IScsiSessionList;
}

```

## disassembly

```asm
0x180009d60  mov     rax, rsp
0x180009d63  mov     [rax+8], rbx
0x180009d67  push    rsi
0x180009d68  push    rdi
0x180009d69  push    r14
0x180009d6b  sub     rsp, 20h
0x180009d6f  mov     r14, rcx
0x180009d72  mov     dword ptr [rax+10h], 0
0x180009d79  lea     rcx, [rax+18h]
0x180009d7d  mov     dword ptr [rax+18h], 0
0x180009d84  xor     r8d, r8d
0x180009d87  lea     rdx, [rax+10h]
0x180009d8b  xor     edi, edi
0x180009d8d  call    DiscpGetIScsiSessionList
0x180009d92  mov     ebx, eax
0x180009d94  cmp     eax, 7Ah ; 'z'
0x180009d97  jnz     short loc_180009DD6
0x180009d99  mov     ecx, [rsp+38h+arg_10]
0x180009d9d  call    cs:__imp_DiscpAllocMemory
0x180009da3  mov     rdi, rax
0x180009da6  test    rax, rax
0x180009da9  jz      short loc_180009DCF
0x180009dab  mov     r8, rax
0x180009dae  lea     rdx, [rsp+38h+arg_8]
0x180009db3  lea     rcx, [rsp+38h+arg_10]
0x180009db8  call    DiscpGetIScsiSessionList
0x180009dbd  mov     ebx, eax
0x180009dbf  cmp     eax, 7Ah ; 'z'
0x180009dc2  jnz     short loc_180009DD6
0x180009dc4  mov     rcx, rdi
0x180009dc7  call    cs:__imp_DiscpFreeMemory
0x180009dcd  jmp     short loc_180009D99
0x180009dcf  mov     ebx, 8
0x180009dd4  jmp     short loc_180009E17
0x180009dd6  test    ebx, ebx
0x180009dd8  jnz     short loc_180009E09
0x180009dda  xor     esi, esi
0x180009ddc  cmp     [rsp+38h+arg_8], esi
0x180009de0  jbe     short loc_180009E09
0x180009de2  mov     edx, esi
0x180009de4  mov     rcx, r14
0x180009de7  shl     rdx, 6
0x180009deb  mov     rdx, [rdx+rdi+20h]
0x180009df0  call    cs:__imp__o__wcsicmp
0x180009df6  test    eax, eax
0x180009df8  jz      short loc_180009E04
0x180009dfa  inc     esi
0x180009dfc  cmp     esi, [rsp+38h+arg_8]
0x180009e00  jb      short loc_180009DE2
0x180009e02  jmp     short loc_180009E09
0x180009e04  mov     ebx, 0EFFF003Fh
0x180009e09  test    rdi, rdi
0x180009e0c  jz      short loc_180009E17
0x180009e0e  mov     rcx, rdi
0x180009e11  call    cs:__imp_DiscpFreeMemory
0x180009e17  mov     eax, ebx
0x180009e19  mov     rbx, [rsp+38h+arg_0]
0x180009e1e  add     rsp, 20h
0x180009e22  pop     r14
0x180009e24  pop     rdi
0x180009e25  pop     rsi
0x180009e26  retn
```
