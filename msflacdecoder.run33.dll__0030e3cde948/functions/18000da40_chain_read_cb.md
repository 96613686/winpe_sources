# chain_read_cb_

- ea: `0x18000da40`
- end: `0x18000dca7`
- name: `chain_read_cb_`
- size: `615`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000d1f0`

## callees

- `0x180004ad0`
- `0x180004c00`
- `0x18000da40`
- `0x18000e1f0`
- `0x18000e2a0`
- `0x18000f2f0`
- `0x180056010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18000dafa`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18000dafa`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dc50`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dc5b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dc98`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dc50`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dc5b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dc98`

## pseudocode

```c
__int64 __fastcall chain_read_cb_(
        __int64 a1,
        __int64 a2,
        __int64 (__fastcall *a3)(_BYTE *, __int64, __int64, __int64),
        __int64 (__fastcall *a4)(__int64, _QWORD, __int64),
        __int64 (__fastcall *a5)(__int64))
{
  int metadata_block_cb; // eax
  int v10; // eax
  int v11; // eax
  __int64 v13; // rax
  _QWORD *v14; // rdi
  unsigned int v15; // esi
  __int64 v16; // rax
  int v17; // ecx
  unsigned int v18; // esi
  unsigned int metadata_block_data_cb; // eax
  int equivalent_status; // eax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // r8
  __int64 i; // r9
  _DWORD *v26; // rcx
  _BYTE v27[40]; // [rsp+30h] [rbp-28h] BYREF

  metadata_block_cb = seek_to_first_metadata_block_cb_(a2, a3, a4);
  if ( !metadata_block_cb )
  {
    v13 = a5(a2);
    if ( v13 >= 0 )
    {
      *(_QWORD *)(a1 + 40) = v13;
      while ( 1 )
      {
        v14 = calloc(1u, 0x18u);
        if ( !v14 )
          goto LABEL_31;
        if ( a3(v27, 1, 4, a2) != 4 )
          break;
        v15 = v27[0];
        v16 = FLAC__metadata_object_new(v27[0] & 0x7F);
        *v14 = v16;
        if ( !v16 )
        {
          free(v14);
LABEL_31:
          *(_DWORD *)(a1 + 36) = 11;
          return 0;
        }
        v17 = v27[1] << 8;
        v18 = v15 >> 7;
        *(_DWORD *)(v16 + 4) = v18;
        *(_DWORD *)(*v14 + 8LL) = v27[3] | ((v27[2] | v17) << 8);
        metadata_block_data_cb = read_metadata_block_data_cb_(a2, a3, a4, *v14);
        equivalent_status = get_equivalent_status_(metadata_block_data_cb);
        *(_DWORD *)(a1 + 36) = equivalent_status;
        if ( equivalent_status )
        {
          if ( *v14 )
            FLAC__metadata_object_delete();
          free(v14);
          return 0;
        }
        v21 = *v14;
        v14[1] = 0;
        v14[2] = 0;
        *(_DWORD *)(v21 + 4) = 1;
        v22 = *(_QWORD *)(a1 + 24);
        if ( v22 )
          *(_DWORD *)(*(_QWORD *)v22 + 4LL) = 0;
        if ( *(_QWORD *)(a1 + 16) )
        {
          *(_QWORD *)(*(_QWORD *)(a1 + 24) + 16LL) = v14;
          v14[1] = *(_QWORD *)(a1 + 24);
        }
        else
        {
          *(_QWORD *)(a1 + 16) = v14;
        }
        ++*(_DWORD *)(a1 + 32);
        *(_QWORD *)(a1 + 24) = v14;
        if ( v18 )
        {
          v23 = a5(a2);
          if ( v23 >= 0 )
          {
            v24 = *(_QWORD *)(a1 + 16);
            *(_QWORD *)(a1 + 48) = v23;
            if ( **(_DWORD **)v24 )
            {
              *(_DWORD *)(a1 + 36) = 5;
              return 0;
            }
            for ( i = 0; v24; i += (unsigned int)(v26[2] + 4) )
            {
              v26 = *(_DWORD **)v24;
              v24 = *(_QWORD *)(v24 + 16);
            }
            *(_QWORD *)(a1 + 56) = i;
            return 1;
          }
LABEL_37:
          *(_DWORD *)(a1 + 36) = 6;
          return 0;
        }
      }
      if ( *v14 )
        FLAC__metadata_object_delete();
      free(v14);
      goto LABEL_37;
    }
LABEL_9:
    *(_DWORD *)(a1 + 36) = 6;
    return 0;
  }
  v10 = metadata_block_cb - 1;
  if ( !v10 )
    goto LABEL_9;
  v11 = v10 - 1;
  if ( v11 )
  {
    if ( v11 == 1 )
    {
      *(_DWORD *)(a1 + 36) = 3;
      return 0;
    }
  }
  else
  {
    *(_DWORD *)(a1 + 36) = 7;
  }
  return 0;
}

```

## disassembly

```asm
0x18000da40  mov     [rsp+arg_18], rbx
0x18000da45  push    rbp
0x18000da46  push    r14
0x18000da48  push    r15
0x18000da4a  sub     rsp, 40h
0x18000da4e  mov     r14, r8
0x18000da51  mov     rbp, rdx
0x18000da54  mov     rbx, rcx
0x18000da57  mov     rdx, r14
0x18000da5a  mov     rcx, rbp
0x18000da5d  mov     r8, r9
0x18000da60  mov     r15, r9
0x18000da63  call    seek_to_first_metadata_block_cb_
0x18000da68  test    eax, eax
0x18000da6a  jz      short loc_18000DAAB
0x18000da6c  sub     eax, 1
0x18000da6f  jz      short loc_18000DAC0
0x18000da71  sub     eax, 1
0x18000da74  jz      short loc_18000DA93
0x18000da76  cmp     eax, 1
0x18000da79  jnz     short loc_18000DA9A
0x18000da7b  mov     dword ptr [rbx+24h], 3
0x18000da82  xor     eax, eax
0x18000da84  mov     rbx, [rsp+58h+arg_18]
0x18000da89  add     rsp, 40h
0x18000da8d  pop     r15
0x18000da8f  pop     r14
0x18000da91  pop     rbp
0x18000da92  retn
0x18000da93  mov     dword ptr [rbx+24h], 7
0x18000da9a  xor     eax, eax
0x18000da9c  mov     rbx, [rsp+58h+arg_18]
0x18000daa1  add     rsp, 40h
0x18000daa5  pop     r15
0x18000daa7  pop     r14
0x18000daa9  pop     rbp
0x18000daaa  retn
0x18000daab  mov     rax, [rsp+58h+arg_20]
0x18000dab3  mov     rcx, rbp
0x18000dab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dabb  test    rax, rax
0x18000dabe  jns     short loc_18000DAD8
0x18000dac0  mov     dword ptr [rbx+24h], 6
0x18000dac7  xor     eax, eax
0x18000dac9  mov     rbx, [rsp+58h+arg_18]
0x18000dace  add     rsp, 40h
0x18000dad2  pop     r15
0x18000dad4  pop     r14
0x18000dad6  pop     rbp
0x18000dad7  retn
0x18000dad8  mov     [rsp+58h+arg_8], rdi
0x18000dadd  mov     [rsp+58h+arg_10], r13
0x18000dae2  xor     r13d, r13d
0x18000dae5  mov     [rsp+58h+arg_0], rsi
0x18000daea  mov     [rbx+28h], rax
0x18000daee  xchg    ax, ax
0x18000daf0  mov     edx, 18h; Size
0x18000daf5  mov     ecx, 1; Count
0x18000dafa  call    cs:__imp_calloc
0x18000db00  mov     rdi, rax
0x18000db03  test    rax, rax
0x18000db06  jz      loc_18000DC61
0x18000db0c  mov     r9, rbp
0x18000db0f  lea     rcx, [rsp+58h+var_28]
0x18000db14  mov     edx, 1
0x18000db19  mov     r8d, 4
0x18000db1f  mov     rax, r14
0x18000db22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db27  cmp     rax, 4
0x18000db2b  jnz     loc_18000DC88
0x18000db31  movzx   esi, [rsp+58h+var_28]
0x18000db36  mov     ecx, esi
0x18000db38  and     ecx, 7Fh
0x18000db3b  call    FLAC__metadata_object_new
0x18000db40  mov     [rdi], rax
0x18000db43  test    rax, rax
0x18000db46  jz      loc_18000DC58
0x18000db4c  movzx   ecx, [rsp+58h+var_27]
0x18000db51  mov     r8, r15
0x18000db54  shl     ecx, 8
0x18000db57  mov     rdx, r14
0x18000db5a  shr     esi, 7
0x18000db5d  mov     [rax+4], esi
0x18000db60  movzx   eax, [rsp+58h+var_26]
0x18000db65  or      ecx, eax
0x18000db67  movzx   eax, [rsp+58h+var_25]
0x18000db6c  shl     ecx, 8
0x18000db6f  or      ecx, eax
0x18000db71  mov     rax, [rdi]
0x18000db74  mov     [rax+8], ecx
0x18000db77  mov     rcx, rbp
0x18000db7a  mov     r9, [rdi]
0x18000db7d  call    read_metadata_block_data_cb_
0x18000db82  mov     ecx, eax
0x18000db84  call    get_equivalent_status_
0x18000db89  mov     [rbx+24h], eax
0x18000db8c  test    eax, eax
0x18000db8e  jnz     loc_18000DC40
0x18000db94  mov     rax, [rdi]
0x18000db97  mov     [rdi+8], r13
0x18000db9b  mov     [rdi+10h], r13
0x18000db9f  mov     dword ptr [rax+4], 1
0x18000dba6  mov     rax, [rbx+18h]
0x18000dbaa  test    rax, rax
0x18000dbad  jz      short loc_18000DBB6
0x18000dbaf  mov     rax, [rax]
0x18000dbb2  mov     [rax+4], r13d
0x18000dbb6  cmp     [rbx+10h], r13
0x18000dbba  jnz     short loc_18000DBC2
0x18000dbbc  mov     [rbx+10h], rdi
0x18000dbc0  jmp     short loc_18000DBD2
0x18000dbc2  mov     rax, [rbx+18h]
0x18000dbc6  mov     [rax+10h], rdi
0x18000dbca  mov     rax, [rbx+18h]
0x18000dbce  mov     [rdi+8], rax
0x18000dbd2  inc     dword ptr [rbx+20h]
0x18000dbd5  mov     [rbx+18h], rdi
0x18000dbd9  test    esi, esi
0x18000dbdb  jz      loc_18000DAF0
0x18000dbe1  mov     rax, [rsp+58h+arg_20]
0x18000dbe9  mov     rcx, rbp
0x18000dbec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbf1  test    rax, rax
0x18000dbf4  js      loc_18000DC9E
0x18000dbfa  mov     r8, [rbx+10h]
0x18000dbfe  mov     [rbx+30h], rax
0x18000dc02  mov     rax, [r8]
0x18000dc05  cmp     [rax], r13d
0x18000dc08  jz      short loc_18000DC13
0x18000dc0a  mov     dword ptr [rbx+24h], 5
0x18000dc11  jmp     short loc_18000DC68
0x18000dc13  mov     r9, r13
0x18000dc16  test    r8, r8
0x18000dc19  jz      short loc_18000DC35
0x18000dc1b  nop     dword ptr [rax+rax+00h]
0x18000dc20  mov     rcx, [r8]
0x18000dc23  mov     r8, [r8+10h]
0x18000dc27  mov     ecx, [rcx+8]
0x18000dc2a  add     ecx, 4
0x18000dc2d  add     r9, rcx
0x18000dc30  test    r8, r8
0x18000dc33  jnz     short loc_18000DC20
0x18000dc35  mov     [rbx+38h], r9
0x18000dc39  mov     eax, 1
0x18000dc3e  jmp     short loc_18000DC6A
0x18000dc40  mov     rcx, [rdi]
0x18000dc43  test    rcx, rcx
0x18000dc46  jz      short loc_18000DC4D
0x18000dc48  call    FLAC__metadata_object_delete
0x18000dc4d  mov     rcx, rdi; Block
0x18000dc50  call    cs:__imp_free
0x18000dc56  jmp     short loc_18000DC68
0x18000dc58  mov     rcx, rdi; Block
0x18000dc5b  call    cs:__imp_free
0x18000dc61  mov     dword ptr [rbx+24h], 0Bh
0x18000dc68  xor     eax, eax
0x18000dc6a  mov     rsi, [rsp+58h+arg_0]
0x18000dc6f  mov     rdi, [rsp+58h+arg_8]
0x18000dc74  mov     r13, [rsp+58h+arg_10]
0x18000dc79  mov     rbx, [rsp+58h+arg_18]
0x18000dc7e  add     rsp, 40h
0x18000dc82  pop     r15
0x18000dc84  pop     r14
0x18000dc86  pop     rbp
0x18000dc87  retn
0x18000dc88  mov     rcx, [rdi]
0x18000dc8b  test    rcx, rcx
0x18000dc8e  jz      short loc_18000DC95
0x18000dc90  call    FLAC__metadata_object_delete
0x18000dc95  mov     rcx, rdi; Block
0x18000dc98  call    cs:__imp_free
0x18000dc9e  mov     dword ptr [rbx+24h], 6
0x18000dca5  jmp     short loc_18000DC68
```
