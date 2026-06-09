# DiscpRemovePersistentLogin

- ea: `0x18000b17c`
- end: `0x18000b2d5`
- name: `DiscpRemovePersistentLogin`
- size: `345`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180009898`

## callees

- `0x18000629c`
- `0x18000b17c`
- `0x180016d20`

## import_xrefs

- `ISCSIUM!DiscpCopyToCountedString` at `0x18000b1dd`
- `ISCSIUM!DiscpCopyToCountedString` at `0x18000b1dd`
- `ISCSIUM!DiscpExecuteMethod` at `0x18000b28c`
- `ISCSIUM!DiscpExecuteMethod` at `0x18000b28c`
- `ISCSIUM!DiscpAllocMemory` at `0x18000b1bb`
- `ISCSIUM!DiscpAllocMemory` at `0x18000b1bb`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b29f`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b2b9`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b29f`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b2b9`

## pseudocode

```c
__int64 __fastcall DiscpRemovePersistentLogin(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  unsigned int InitiatorInstance; // ebx
  _DWORD *v8; // rax
  _DWORD *v9; // rdi
  volatile signed __int32 *v10; // rbp
  int v12; // [rsp+50h] [rbp-58h] BYREF
  unsigned int *v13; // [rsp+58h] [rbp-50h] BYREF
  volatile signed __int32 *v14; // [rsp+60h] [rbp-48h] BYREF

  v14 = 0;
  v13 = 0;
  v12 = 0;
  InitiatorInstance = DiscpFindInitiatorInstance(a1, &v14);
  if ( !InitiatorInstance )
  {
    v8 = (_DWORD *)DiscpAllocMemory(1008);
    v9 = v8;
    if ( v8 )
    {
      *v8 = a2;
      DiscpCopyToCountedString(v8 + 1, a3, 223);
      v10 = v14;
      if ( a4 && *(_WORD *)(a4 + 512) )
      {
        *((_WORD *)v9 + 502) = *(_WORD *)(a4 + 1024);
        InitiatorInstance = DiscpBuildIScsiIpAddress(v10[5] & 1, a4 + 512, 1, v9 + 113);
        if ( InitiatorInstance )
          return InitiatorInstance;
      }
      else
      {
        *((_WORD *)v9 + 502) = 0;
        v9[113] = 3;
        *((_WORD *)v9 + 242) = 512;
      }
      v12 = 260;
      v13 = 0;
      InitiatorInstance = DiscpExecuteMethod(
                            MSiSCSI_Operations_GUID,
                            0,
                            *((_QWORD *)v10 + 5),
                            33,
                            v9,
                            1008,
                            &v13,
                            &v12,
                            4);
      if ( !InitiatorInstance )
      {
        InitiatorInstance = *v13;
        DiscpFreeMemory(v13);
      }
      if ( InitiatorInstance - 4200 <= 2 )
        InitiatorInstance = -268500924;
      DiscpFreeMemory(v9);
    }
    else
    {
      return 8;
    }
  }
  return InitiatorInstance;
}

```

## disassembly

```asm
0x18000b17c  mov     rax, rsp
0x18000b17f  push    rbx
0x18000b180  push    rbp
0x18000b181  push    rsi
0x18000b182  push    rdi
0x18000b183  push    r14
0x18000b185  push    r15
0x18000b187  sub     rsp, 78h
0x18000b18b  xor     r15d, r15d
0x18000b18e  mov     r14d, edx
0x18000b191  lea     rdx, [rax-48h]
0x18000b195  mov     [rax-48h], r15
0x18000b199  mov     [rax-50h], r15
0x18000b19d  mov     rsi, r9
0x18000b1a0  mov     [rax-58h], r15d
0x18000b1a4  mov     rbp, r8
0x18000b1a7  call    DiscpFindInitiatorInstance
0x18000b1ac  mov     ebx, eax
0x18000b1ae  test    eax, eax
0x18000b1b0  jnz     loc_18000B2C6
0x18000b1b6  mov     ecx, 3F0h
0x18000b1bb  call    cs:__imp_DiscpAllocMemory
0x18000b1c1  mov     rdi, rax
0x18000b1c4  test    rax, rax
0x18000b1c7  jz      loc_18000B2C1
0x18000b1cd  lea     rcx, [rax+4]
0x18000b1d1  mov     [rax], r14d
0x18000b1d4  mov     r8d, 0DFh
0x18000b1da  mov     rdx, rbp
0x18000b1dd  call    cs:__imp_DiscpCopyToCountedString
0x18000b1e3  mov     rbp, [rsp+0A8h+var_48]
0x18000b1e8  test    rsi, rsi
0x18000b1eb  jz      short loc_18000B228
0x18000b1ed  lea     rdx, [rsi+200h]
0x18000b1f4  cmp     [rdx], r15w
0x18000b1f8  jz      short loc_18000B228
0x18000b1fa  movzx   eax, word ptr [rsi+400h]
0x18000b201  lea     r9, [rdi+1C4h]
0x18000b208  mov     [rdi+3ECh], ax
0x18000b20f  mov     r8b, 1
0x18000b212  mov     ecx, [rbp+14h]
0x18000b215  and     cl, r8b
0x18000b218  call    DiscpBuildIScsiIpAddress
0x18000b21d  mov     ebx, eax
0x18000b21f  test    eax, eax
0x18000b221  jz      short loc_18000B243
0x18000b223  jmp     loc_18000B2C6
0x18000b228  mov     [rdi+3ECh], r15w
0x18000b230  mov     dword ptr [rdi+1C4h], 3
0x18000b23a  mov     word ptr [rdi+1E4h], 200h
0x18000b243  mov     [rsp+0A8h+var_68], 4
0x18000b24b  lea     rax, [rsp+0A8h+var_58]
0x18000b250  mov     [rsp+0A8h+var_70], rax
0x18000b255  lea     rcx, MSiSCSI_Operations_GUID
0x18000b25c  lea     rax, [rsp+0A8h+var_50]
0x18000b261  mov     [rsp+0A8h+var_58], 104h
0x18000b269  mov     [rsp+0A8h+var_78], rax
0x18000b26e  mov     r9d, 21h ; '!'
0x18000b274  mov     [rsp+0A8h+var_50], r15
0x18000b279  xor     edx, edx
0x18000b27b  mov     r8, [rbp+28h]
0x18000b27f  mov     [rsp+0A8h+var_80], 3F0h
0x18000b287  mov     [rsp+0A8h+var_88], rdi
0x18000b28c  call    cs:__imp_DiscpExecuteMethod
0x18000b292  mov     ebx, eax
0x18000b294  test    eax, eax
0x18000b296  jnz     short loc_18000B2A5
0x18000b298  mov     rcx, [rsp+0A8h+var_50]
0x18000b29d  mov     ebx, [rcx]
0x18000b29f  call    cs:__imp_DiscpFreeMemory
0x18000b2a5  lea     eax, [rbx-1068h]
0x18000b2ab  mov     ecx, 0EFFF0044h
0x18000b2b0  cmp     eax, 2
0x18000b2b3  cmovbe  ebx, ecx
0x18000b2b6  mov     rcx, rdi
0x18000b2b9  call    cs:__imp_DiscpFreeMemory
0x18000b2bf  jmp     short loc_18000B2C6
0x18000b2c1  mov     ebx, 8
0x18000b2c6  mov     eax, ebx
0x18000b2c8  add     rsp, 78h
0x18000b2cc  pop     r15
0x18000b2ce  pop     r14
0x18000b2d0  pop     rdi
0x18000b2d1  pop     rsi
0x18000b2d2  pop     rbp
0x18000b2d3  pop     rbx
0x18000b2d4  retn
```
