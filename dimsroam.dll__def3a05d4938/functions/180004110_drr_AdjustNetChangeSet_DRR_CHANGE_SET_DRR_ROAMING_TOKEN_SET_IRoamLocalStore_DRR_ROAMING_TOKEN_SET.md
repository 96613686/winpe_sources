# _drr_AdjustNetChangeSet(DRR_CHANGE_SET *,DRR_ROAMING_TOKEN_SET *,IRoamLocalStore *,DRR_ROAMING_TOKEN_SET *)

- ea: `0x180004110`
- end: `0x18000421c`
- name: `?_drr_AdjustNetChangeSet@@YAKPEAUDRR_CHANGE_SET@@PEAUDRR_ROAMING_TOKEN_SET@@PEAUIRoamLocalStore@@1@Z`
- size: `268`
- prototype: `__int64 __fastcall(struct DRR_CHANGE_SET *, struct DRR_ROAMING_TOKEN_SET *, struct IRoamLocalStore *, struct DRR_ROAMING_TOKEN_SET *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180006230`

## callees

- `0x180004110`
- `0x18000cde8`
- `0x18000cfe8`
- `0x18000d054`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004202`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004202`

## pseudocode

```c
__int64 __fastcall _drr_AdjustNetChangeSet(
        struct DRR_CHANGE_SET *a1,
        struct DRR_ROAMING_TOKEN_SET *a2,
        struct IRoamLocalStore *a3,
        struct DRR_ROAMING_TOKEN_SET *a4)
{
  __int64 v4; // r12
  unsigned int v5; // r14d
  __int64 v6; // rbx
  struct DRR_ROAMING_TOKEN_SET *v8; // r8
  __int64 v10; // rdi
  __int64 v11; // rbp
  __int64 RoamingTokenFromSet; // rax
  __int64 v14; // rax
  int v15; // ecx
  __int64 v16; // [rsp+60h] [rbp+8h] BYREF
  struct DRR_ROAMING_TOKEN_SET *v17; // [rsp+68h] [rbp+10h]
  struct DRR_ROAMING_TOKEN_SET *v18; // [rsp+78h] [rbp+20h]

  v18 = a4;
  v17 = a2;
  v4 = *(_QWORD *)a1;
  v5 = 0;
  v6 = 0;
  v8 = a2;
  while ( (unsigned int)v6 < *((_DWORD *)a1 + 2) )
  {
    v10 = *(_QWORD *)(v4 + 8 * v6);
    if ( ((*(_DWORD *)v10 - 1) & 0xFFFFFFFD) == 0 )
    {
      v11 = *(_QWORD *)(v10 + 8);
      if ( !*(_DWORD *)(v11 + 128) )
      {
        RoamingTokenFromSet = DRR_GetRoamingTokenFromSet(v8, *(_QWORD *)(v10 + 8));
        if ( RoamingTokenFromSet )
        {
          *(_QWORD *)(v10 + 8) = RoamingTokenFromSet;
        }
        else
        {
          if ( !a3 )
            goto LABEL_16;
          v14 = *(_QWORD *)a3;
          v16 = 0;
          v15 = (*(__int64 (__fastcall **)(struct IRoamLocalStore *, __int64, __int64 *))(v14 + 40))(a3, v11, &v16);
          if ( (v15 & 0x1FFF0000) == 0x70000 )
            v15 = (unsigned __int16)v15;
          if ( v15 )
          {
LABEL_16:
            LocalFree(*(HLOCAL *)(v4 + 8 * v6));
            DRR_DeleteAnyGrowableArray(a1, (unsigned int)v6);
            v8 = v17;
            continue;
          }
          v5 = DRR_AddRoamingTokenToSet(v18, v16, 0);
          if ( v5 )
            return v5;
          *(_QWORD *)(*(_QWORD *)(v4 + 8 * v6) + 8LL) = v16;
        }
        v8 = v17;
      }
    }
    v6 = (unsigned int)(v6 + 1);
  }
  return v5;
}

```

## disassembly

```asm
0x180004110  mov     [rsp+arg_10], rbx
0x180004115  mov     [rsp+arg_18], r9
0x18000411a  mov     [rsp+arg_8], rdx
0x18000411f  push    rbp
0x180004120  push    rsi
0x180004121  push    rdi
0x180004122  push    r12
0x180004124  push    r13
0x180004126  push    r14
0x180004128  push    r15
0x18000412a  sub     rsp, 20h
0x18000412e  mov     r12, [rcx]
0x180004131  xor     r14d, r14d
0x180004134  xor     ebx, ebx
0x180004136  mov     r13, r8
0x180004139  mov     r8, rdx
0x18000413c  mov     rsi, rcx
0x18000413f  cmp     [rcx+8], ebx
0x180004142  jbe     short loc_180004180
0x180004144  mov     rdi, [r12+rbx*8]
0x180004148  mov     eax, [rdi]
0x18000414a  dec     eax
0x18000414c  test    eax, 0FFFFFFFDh
0x180004151  jnz     short loc_180004179
0x180004153  mov     rbp, [rdi+8]
0x180004157  cmp     dword ptr [rbp+80h], 0
0x18000415e  jnz     short loc_180004179
0x180004160  mov     rdx, rbp
0x180004163  mov     rcx, r8
0x180004166  call    DRR_GetRoamingTokenFromSet
0x18000416b  test    rax, rax
0x18000416e  jz      short loc_180004198
0x180004170  mov     [rdi+8], rax
0x180004174  mov     r8, [rsp+58h+arg_8]
0x180004179  inc     ebx
0x18000417b  cmp     ebx, [rsi+8]
0x18000417e  jb      short loc_180004144
0x180004180  mov     rbx, [rsp+58h+arg_10]
0x180004185  mov     eax, r14d
0x180004188  add     rsp, 20h
0x18000418c  pop     r15
0x18000418e  pop     r14
0x180004190  pop     r13
0x180004192  pop     r12
0x180004194  pop     rdi
0x180004195  pop     rsi
0x180004196  pop     rbp
0x180004197  retn
0x180004198  test    r13, r13
0x18000419b  jz      short loc_1800041FE
0x18000419d  mov     rax, [r13+0]
0x1800041a1  lea     r8, [rsp+58h+arg_0]
0x1800041a6  mov     rdx, rbp
0x1800041a9  mov     [rsp+58h+arg_0], 0
0x1800041b2  mov     rcx, r13
0x1800041b5  mov     rax, [rax+28h]
0x1800041b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041be  mov     ecx, eax
0x1800041c0  and     eax, 1FFF0000h
0x1800041c5  cmp     eax, 70000h
0x1800041ca  jnz     short loc_1800041CF
0x1800041cc  movzx   ecx, cx
0x1800041cf  test    ecx, ecx
0x1800041d1  jnz     short loc_1800041FE
0x1800041d3  mov     rdx, [rsp+58h+arg_0]
0x1800041d8  xor     r8d, r8d
0x1800041db  mov     rcx, [rsp+58h+arg_18]
0x1800041e0  call    DRR_AddRoamingTokenToSet
0x1800041e5  mov     r14d, eax
0x1800041e8  test    eax, eax
0x1800041ea  jnz     short loc_180004180
0x1800041ec  mov     rdx, [r12+rbx*8]
0x1800041f0  mov     rcx, [rsp+58h+arg_0]
0x1800041f5  mov     [rdx+8], rcx
0x1800041f9  jmp     loc_180004174
0x1800041fe  mov     rcx, [r12+rbx*8]; hMem
0x180004202  call    cs:__imp_LocalFree
0x180004208  mov     edx, ebx
0x18000420a  mov     rcx, rsi
0x18000420d  call    DRR_DeleteAnyGrowableArray
0x180004212  mov     r8, [rsp+58h+arg_8]
0x180004217  jmp     loc_18000417B
```
